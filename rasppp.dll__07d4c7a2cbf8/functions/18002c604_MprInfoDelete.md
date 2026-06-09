# MprInfoDelete

- ea: `0x18002c604`
- end: `0x18002c633`
- name: `MprInfoDelete`
- size: `47`
- prototype: `DWORD __stdcall(LPVOID lpHeader)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800187f8`
- `0x1800189d8`
- `0x180018e1c`

## callees

- `0x18002c604`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c625`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c625`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c617`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c617`

## pseudocode

```c
DWORD __stdcall MprInfoDelete(LPVOID lpHeader)
{
  HANDLE ProcessHeap; // rax

  if ( !lpHeader )
    return 87;
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, lpHeader);
  return 0;
}

```

## disassembly

```asm
0x18002c604  push    rbx
0x18002c606  sub     rsp, 20h
0x18002c60a  mov     rbx, rcx
0x18002c60d  test    rcx, rcx
0x18002c610  jnz     short loc_18002C617
0x18002c612  lea     eax, [rcx+57h]
0x18002c615  jmp     short loc_18002C62D
0x18002c617  call    cs:__imp_GetProcessHeap
0x18002c61d  mov     r8, rbx; lpMem
0x18002c620  xor     edx, edx; dwFlags
0x18002c622  mov     rcx, rax; hHeap
0x18002c625  call    cs:__imp_HeapFree
0x18002c62b  xor     eax, eax
0x18002c62d  add     rsp, 20h
0x18002c631  pop     rbx
0x18002c632  retn
```
