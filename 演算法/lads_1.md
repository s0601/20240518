## GenAI_Algorithm_lab1 ==> 二元搜尋樹的各種實作(heap sort)
- `提問詞`:請寫出heap sort的演算法
- `提問詞`:請計算heap sort樹演算法的時間複雜度
- `提問詞`:請用Python寫出heap sort的演算法
- `提問詞`:請用C寫出heap sort的演算法
- `提問詞`:請用C++寫出heap sort的演算法
- `提問詞`:請用JAVA寫出heap sort的演算法
- `提問詞`:請用Rust寫出heap sort的演算法
- `提問詞`:請用go寫出heap sort的演算法
- `提問詞`:請用C#寫出heap sort的演算法
- `提問詞`:請用Javascript寫出二heap sort的演算法
##`提問詞`:請寫出heap sort的演算法
```
Heap Sort（堆排序）是一種基於比較的排序演算法，其基本思想是利用堆這種資料結構來進行排序。以下是堆排序的詳細步驟和Python實現。

堆排序演算法步驟
建堆（Heapify）：
將輸入數列轉換為一個最大堆。最大堆是一個完全二元樹，其中每個節點的值都大於或等於其子節點的值。

排序：
重複以下步驟直到堆的大小為1：

將堆的根（即最大值）與堆的最後一個元素交換。
減少堆的大小，將最後一個元素排除在堆之外。
對新的堆的根進行堆化（維護最大堆性質）。
主要操作函數
最大堆化（Max-Heapify）：保持最大堆的性質。
建堆（Build-Max-Heap）：從數列構建最大堆。
堆排序（Heap-Sort）：利用最大堆進行排序。

def heapify(arr, n, i):
    largest = i  # 初始化最大值為根節點
    left = 2 * i + 1  # 左子節點
    right = 2 * i + 2  # 右子節點

    # 如果左子節點存在且大於根節點
    if left < n and arr[i] < arr[left]:
        largest = left

    # 如果右子節點存在且大於當前最大值
    if right < n and arr[largest] < arr[right]:
        largest = right

    # 如果最大值不是根節點
    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]  # 交換
        heapify(arr, n, largest)  # 繼續堆化

def heapSort(arr):
    n = len(arr)

    # 建立最大堆
    for i in range(n // 2 - 1, -1, -1):
        heapify(arr, n, i)

    # 一個一個地取出元素
    for i in range(n - 1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]  # 交換
        heapify(arr, i, 0)

# 測試堆排序
if __name__ == "__main__":
    arr = [12, 11, 13, 5, 6, 7]
    print("Unsorted array is:", arr)
    heapSort(arr)
    print("Sorted array is:", arr)

- Online Python Interpreter
  - [Online Python Compiler (Interpreter) - Programiz](https://www.programiz.com/python-programming/online-compiler/)

![labs_1_1.png](labs_1_1.png)
