# NsiFreePersistentDataWithMaskTable

- ea: `0x180002f60`
- end: `0x180002fc0`
- name: `NsiFreePersistentDataWithMaskTable`
- size: `96`
- prototype: `__int64 __fastcall(LPVOID lpMem, LPVOID, LPVOID)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002bd0`

## callees

- `0x180002f60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002faf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002faf`

## pseudocode

```c
BOOL __fastcall NsiFreePersistentDataWithMaskTable(LPVOID lpMem, LPVOID a2, LPVOID a3)
{
  BOOL result; // eax

  if ( lpMem )
    result = HeapFree(g_NsiHeap, 0, lpMem);
  if ( a2 )
    result = HeapFree(g_NsiHeap, 0, a2);
  if ( a3 )
    return HeapFree(g_NsiHeap, 0, a3);
  return result;
}

```

## disassembly

```asm
0x180002f60  mov     [rsp+arg_0], rbx
0x180002f65  push    rdi
0x180002f66  sub     rsp, 20h
0x180002f6a  mov     rbx, r8
0x180002f6d  mov     rdi, rdx
0x180002f70  test    rcx, rcx
0x180002f73  jz      short loc_180002F87
0x180002f75  mov     r8, rcx; lpMem
0x180002f78  xor     edx, edx; dwFlags
0x180002f7a  mov     rcx, cs:g_NsiHeap; hHeap
0x180002f81  call    cs:__imp_HeapFree
0x180002f87  test    rdi, rdi
0x180002f8a  jz      short loc_180002F9E
0x180002f8c  mov     rcx, cs:g_NsiHeap; hHeap
0x180002f93  mov     r8, rdi; lpMem
0x180002f96  xor     edx, edx; dwFlags
0x180002f98  call    cs:__imp_HeapFree
0x180002f9e  test    rbx, rbx
0x180002fa1  jz      short loc_180002FB5
0x180002fa3  mov     rcx, cs:g_NsiHeap; hHeap
0x180002faa  mov     r8, rbx; lpMem
0x180002fad  xor     edx, edx; dwFlags
0x180002faf  call    cs:__imp_HeapFree
0x180002fb5  mov     rbx, [rsp+28h+arg_0]
0x180002fba  add     rsp, 20h
0x180002fbe  pop     rdi
0x180002fbf  retn
```
