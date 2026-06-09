# NsiFreeTable

- ea: `0x180002600`
- end: `0x180002684`
- name: `NsiFreeTable`
- size: `132`
- prototype: `__int64 __fastcall(LPVOID lpMem, LPVOID, LPVOID, LPVOID)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002600`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002629`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002640`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002657`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000266e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002629`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002640`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002657`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000266e`

## pseudocode

```c
BOOL __fastcall NsiFreeTable(LPVOID lpMem, LPVOID a2, LPVOID a3, LPVOID a4)
{
  BOOL result; // eax

  if ( lpMem )
    result = HeapFree(g_NsiHeap, 0, lpMem);
  if ( a2 )
    result = HeapFree(g_NsiHeap, 0, a2);
  if ( a3 )
    result = HeapFree(g_NsiHeap, 0, a3);
  if ( a4 )
    return HeapFree(g_NsiHeap, 0, a4);
  return result;
}

```

## disassembly

```asm
0x180002600  mov     [rsp+arg_0], rbx
0x180002605  mov     [rsp+arg_8], rsi
0x18000260a  push    rdi
0x18000260b  sub     rsp, 20h
0x18000260f  mov     rbx, r9
0x180002612  mov     rdi, r8
0x180002615  mov     rsi, rdx
0x180002618  test    rcx, rcx
0x18000261b  jz      short loc_18000262F
0x18000261d  mov     r8, rcx; lpMem
0x180002620  xor     edx, edx; dwFlags
0x180002622  mov     rcx, cs:g_NsiHeap; hHeap
0x180002629  call    cs:__imp_HeapFree
0x18000262f  test    rsi, rsi
0x180002632  jz      short loc_180002646
0x180002634  mov     rcx, cs:g_NsiHeap; hHeap
0x18000263b  mov     r8, rsi; lpMem
0x18000263e  xor     edx, edx; dwFlags
0x180002640  call    cs:__imp_HeapFree
0x180002646  test    rdi, rdi
0x180002649  jz      short loc_18000265D
0x18000264b  mov     rcx, cs:g_NsiHeap; hHeap
0x180002652  mov     r8, rdi; lpMem
0x180002655  xor     edx, edx; dwFlags
0x180002657  call    cs:__imp_HeapFree
0x18000265d  test    rbx, rbx
0x180002660  jz      short loc_180002674
0x180002662  mov     rcx, cs:g_NsiHeap; hHeap
0x180002669  mov     r8, rbx; lpMem
0x18000266c  xor     edx, edx; dwFlags
0x18000266e  call    cs:__imp_HeapFree
0x180002674  mov     rbx, [rsp+28h+arg_0]
0x180002679  mov     rsi, [rsp+28h+arg_8]
0x18000267e  add     rsp, 20h
0x180002682  pop     rdi
0x180002683  retn
```
