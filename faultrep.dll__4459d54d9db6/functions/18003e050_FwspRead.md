# FwspRead

- ea: `0x18003e050`
- end: `0x18003e090`
- name: `FwspRead`
- size: `64`
- prototype: `signed int __fastcall(__int64, void *, DWORD, DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18003e050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e06f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e06f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003e061`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003e061`

## pseudocode

```c
signed int __fastcall FwspRead(__int64 a1, void *a2, DWORD a3, DWORD *a4)
{
  signed int result; // eax

  if ( ReadFile(*(HANDLE *)(a1 + 8), a2, a3, a4, 0) )
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
0x18003e050  sub     rsp, 38h
0x18003e054  mov     rcx, [rcx+8]; hFile
0x18003e058  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18003e061  call    cs:__imp_ReadFile
0x18003e067  test    eax, eax
0x18003e069  jz      short loc_18003E06F
0x18003e06b  xor     eax, eax
0x18003e06d  jmp     short loc_18003E08B
0x18003e06f  call    cs:__imp_GetLastError
0x18003e075  test    eax, eax
0x18003e077  jle     short loc_18003E081
0x18003e079  movzx   eax, ax
0x18003e07c  or      eax, 80070000h
0x18003e081  test    eax, eax
0x18003e083  mov     ecx, 80004005h
0x18003e088  cmovns  eax, ecx
0x18003e08b  add     rsp, 38h
0x18003e08f  retn
```
