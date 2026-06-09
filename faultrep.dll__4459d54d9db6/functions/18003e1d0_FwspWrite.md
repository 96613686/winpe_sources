# FwspWrite

- ea: `0x18003e1d0`
- end: `0x18003e210`
- name: `FwspWrite`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18003e1d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e1ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e1ef`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003e1e1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003e1e1`

## pseudocode

```c
signed int __fastcall FwspWrite(__int64 a1, const void *a2, DWORD a3, DWORD *a4)
{
  signed int result; // eax

  if ( WriteFile(*(HANDLE *)(a1 + 8), a2, a3, a4, 0) )
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
0x18003e1d0  sub     rsp, 38h
0x18003e1d4  mov     rcx, [rcx+8]; hFile
0x18003e1d8  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18003e1e1  call    cs:__imp_WriteFile
0x18003e1e7  test    eax, eax
0x18003e1e9  jz      short loc_18003E1EF
0x18003e1eb  xor     eax, eax
0x18003e1ed  jmp     short loc_18003E20B
0x18003e1ef  call    cs:__imp_GetLastError
0x18003e1f5  test    eax, eax
0x18003e1f7  jle     short loc_18003E201
0x18003e1f9  movzx   eax, ax
0x18003e1fc  or      eax, 80070000h
0x18003e201  test    eax, eax
0x18003e203  mov     ecx, 80004005h
0x18003e208  cmovns  eax, ecx
0x18003e20b  add     rsp, 38h
0x18003e20f  retn
```
