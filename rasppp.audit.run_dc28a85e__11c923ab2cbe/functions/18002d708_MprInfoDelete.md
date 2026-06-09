# MprInfoDelete

- ea: `0x18002d708`
- end: `0x18002d744`
- name: `MprInfoDelete`
- size: `60`
- prototype: `DWORD __stdcall(LPVOID lpHeader)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180019098`
- `0x18001928c`
- `0x18001973c`

## callees

- `0x18002d708`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d72f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d72f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d71b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d71b`

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
0x18002d708  push    rbx
0x18002d70a  sub     rsp, 20h
0x18002d70e  mov     rbx, rcx
0x18002d711  test    rcx, rcx
0x18002d714  jnz     short loc_18002D71B
0x18002d716  lea     eax, [rcx+57h]
0x18002d719  jmp     short loc_18002D73D
0x18002d71b  call    cs:__imp_GetProcessHeap
0x18002d722  nop     dword ptr [rax+rax+00h]
0x18002d727  mov     r8, rbx; lpMem
0x18002d72a  xor     edx, edx; dwFlags
0x18002d72c  mov     rcx, rax; hHeap
0x18002d72f  call    cs:__imp_HeapFree
0x18002d736  nop     dword ptr [rax+rax+00h]
0x18002d73b  xor     eax, eax
0x18002d73d  add     rsp, 20h
0x18002d741  pop     rbx
0x18002d742  retn
```
