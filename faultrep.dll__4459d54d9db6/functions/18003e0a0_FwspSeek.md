# FwspSeek

- ea: `0x18003e0a0`
- end: `0x18003e105`
- name: `FwspSeek`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18003e0a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e0e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e0e4`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003e0d6`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003e0d6`

## pseudocode

```c
signed int __fastcall FwspSeek(__int64 a1, LARGE_INTEGER a2, DWORD a3, union _LARGE_INTEGER *a4)
{
  signed int result; // eax

  if ( a3 && a3 - 1 >= 2 )
  {
    if ( a4 )
      a4->QuadPart = 0;
    return -2147024809;
  }
  else if ( SetFilePointerEx(*(HANDLE *)(a1 + 8), a2, a4, a3) )
  {
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x18003e0a0  sub     rsp, 28h
0x18003e0a4  mov     r10, r9
0x18003e0a7  mov     eax, r8d
0x18003e0aa  test    r8d, r8d
0x18003e0ad  jz      short loc_18003E0CC
0x18003e0af  sub     eax, 1
0x18003e0b2  jz      short loc_18003E0CC
0x18003e0b4  cmp     eax, 1
0x18003e0b7  jz      short loc_18003E0CC
0x18003e0b9  test    r9, r9
0x18003e0bc  jz      short loc_18003E0C5
0x18003e0be  mov     qword ptr [r9], 0
0x18003e0c5  mov     eax, 80070057h
0x18003e0ca  jmp     short loc_18003E100
0x18003e0cc  mov     rcx, [rcx+8]; hFile
0x18003e0d0  mov     r9d, r8d; dwMoveMethod
0x18003e0d3  mov     r8, r10; lpNewFilePointer
0x18003e0d6  call    cs:__imp_SetFilePointerEx
0x18003e0dc  test    eax, eax
0x18003e0de  jz      short loc_18003E0E4
0x18003e0e0  xor     eax, eax
0x18003e0e2  jmp     short loc_18003E100
0x18003e0e4  call    cs:__imp_GetLastError
0x18003e0ea  test    eax, eax
0x18003e0ec  jle     short loc_18003E0F6
0x18003e0ee  movzx   eax, ax
0x18003e0f1  or      eax, 80070000h
0x18003e0f6  test    eax, eax
0x18003e0f8  mov     ecx, 80004005h
0x18003e0fd  cmovns  eax, ecx
0x18003e100  add     rsp, 28h
0x18003e104  retn
```
