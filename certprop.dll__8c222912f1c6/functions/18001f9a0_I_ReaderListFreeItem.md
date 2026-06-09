# I_ReaderListFreeItem

- ea: `0x18001f9a0`
- end: `0x18001f9e3`
- name: `I_ReaderListFreeItem`
- size: `67`
- prototype: `BOOL __fastcall(LPVOID *lpMem)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003510`
- `0x180005830`
- `0x180014a04`

## callees

- `0x18000cba0`
- `0x18001f9a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f9c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f9d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f9c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f9d7`

## pseudocode

```c
BOOL __fastcall I_ReaderListFreeItem(LPVOID *lpMem)
{
  BOOL result; // eax

  if ( lpMem )
  {
    I_ReaderListFreeItemCommon(lpMem, 0);
    if ( *lpMem )
      HeapFree(hHeap, 0, *lpMem);
    return HeapFree(hHeap, 0, lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x18001f9a0  test    rcx, rcx
0x18001f9a3  jz      short locret_18001F9E2
0x18001f9a5  push    rbx
0x18001f9a6  sub     rsp, 20h
0x18001f9aa  xor     edx, edx
0x18001f9ac  mov     rbx, rcx
0x18001f9af  call    I_ReaderListFreeItemCommon
0x18001f9b4  mov     r8, [rbx]; lpMem
0x18001f9b7  test    r8, r8
0x18001f9ba  jz      short loc_18001F9CB
0x18001f9bc  mov     rcx, cs:hHeap; hHeap
0x18001f9c3  xor     edx, edx; dwFlags
0x18001f9c5  call    cs:__imp_HeapFree
0x18001f9cb  mov     rcx, cs:hHeap; hHeap
0x18001f9d2  mov     r8, rbx; lpMem
0x18001f9d5  xor     edx, edx; dwFlags
0x18001f9d7  call    cs:__imp_HeapFree
0x18001f9dd  add     rsp, 20h
0x18001f9e1  pop     rbx
0x18001f9e2  retn
```
