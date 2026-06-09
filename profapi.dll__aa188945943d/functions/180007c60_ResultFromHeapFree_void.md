# ResultFromHeapFree(void *)

- ea: `0x180007c60`
- end: `0x180007cae`
- name: `?ResultFromHeapFree@@YAJPEAX@Z`
- size: `78`
- prototype: `signed int __fastcall(void *lpMem)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180002340`
- `0x180004230`
- `0x1800061a4`
- `0x180006250`
- `0x1800064b0`
- `0x180006690`
- `0x180006ad0`
- `0x180006de0`
- `0x1800075e0`
- `0x180007e40`
- `0x18000cba8`
- `0x18000ccec`
- `0x18000d620`
- `0x18000e640`
- `0x18000e874`
- `0x1800121fc`

## callees

- `0x180007c60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c86`

## pseudocode

```c
signed int __fastcall ResultFromHeapFree(void *lpMem)
{
  HANDLE ProcessHeap; // rax
  signed int result; // eax

  if ( !lpMem )
    return 0;
  ProcessHeap = GetProcessHeap();
  if ( HeapFree(ProcessHeap, 0, lpMem) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x180007c60  push    rbx
0x180007c62  sub     rsp, 20h
0x180007c66  mov     rbx, rcx
0x180007c69  test    rcx, rcx
0x180007c6c  jz      short loc_180007CAA
0x180007c6e  call    cs:__imp_GetProcessHeap
0x180007c74  mov     r8, rbx; lpMem
0x180007c77  xor     edx, edx; dwFlags
0x180007c79  mov     rcx, rax; hHeap
0x180007c7c  call    cs:__imp_HeapFree
0x180007c82  test    eax, eax
0x180007c84  jnz     short loc_180007CAA
0x180007c86  call    cs:__imp_GetLastError
0x180007c8c  test    eax, eax
0x180007c8e  jg      short loc_180007CA0
0x180007c90  test    eax, eax
0x180007c92  mov     ecx, 80004005h
0x180007c97  cmovns  eax, ecx
0x180007c9a  add     rsp, 20h
0x180007c9e  pop     rbx
0x180007c9f  retn
0x180007ca0  movzx   eax, ax
0x180007ca3  or      eax, 80070000h
0x180007ca8  jmp     short loc_180007C90
0x180007caa  xor     eax, eax
0x180007cac  jmp     short loc_180007C9A
```
