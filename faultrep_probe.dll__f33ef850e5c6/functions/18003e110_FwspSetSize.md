# FwspSetSize

- ea: `0x18003e110`
- end: `0x18003e1ca`
- name: `FwspSetSize`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18003e110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e189`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003e138`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003e16d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003e1b7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003e138`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003e16d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003e1b7`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18003e17b`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18003e17b`

## pseudocode

```c
signed int __fastcall FwspSetSize(__int64 a1, LARGE_INTEGER a2)
{
  signed int result; // eax
  signed int v5; // ebx
  signed int LastError; // eax
  union _LARGE_INTEGER NewFilePointer; // [rsp+30h] [rbp+8h] BYREF

  NewFilePointer.QuadPart = 0;
  if ( SetFilePointerEx(*(HANDLE *)(a1 + 8), 0, &NewFilePointer, 1u) && SetFilePointerEx(*(HANDLE *)(a1 + 8), a2, 0, 0) )
  {
    if ( SetEndOfFile(*(HANDLE *)(a1 + 8)) )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
    }
    SetFilePointerEx(*(HANDLE *)(a1 + 8), NewFilePointer, 0, 0);
    return v5;
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
0x18003e110  mov     [rsp+arg_8], rbx
0x18003e115  push    rdi
0x18003e116  sub     rsp, 20h
0x18003e11a  mov     rbx, rdx
0x18003e11d  mov     qword ptr [rsp+28h+NewFilePointer], 0
0x18003e126  xor     edx, edx; liDistanceToMove
0x18003e128  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x18003e12d  mov     rdi, rcx
0x18003e130  mov     rcx, [rcx+8]; hFile
0x18003e134  lea     r9d, [rdx+1]; dwMoveMethod
0x18003e138  call    cs:__imp_SetFilePointerEx
0x18003e13e  test    eax, eax
0x18003e140  jnz     short loc_18003E160
0x18003e142  call    cs:__imp_GetLastError
0x18003e148  test    eax, eax
0x18003e14a  jle     short loc_18003E154
0x18003e14c  movzx   eax, ax
0x18003e14f  or      eax, 80070000h
0x18003e154  test    eax, eax
0x18003e156  mov     ecx, 80004005h
0x18003e15b  cmovns  eax, ecx
0x18003e15e  jmp     short loc_18003E1BF
0x18003e160  mov     rcx, [rdi+8]; hFile
0x18003e164  xor     r9d, r9d; dwMoveMethod
0x18003e167  xor     r8d, r8d; lpNewFilePointer
0x18003e16a  mov     rdx, rbx; liDistanceToMove
0x18003e16d  call    cs:__imp_SetFilePointerEx
0x18003e173  test    eax, eax
0x18003e175  jz      short loc_18003E142
0x18003e177  mov     rcx, [rdi+8]; hFile
0x18003e17b  call    cs:__imp_SetEndOfFile
0x18003e181  test    eax, eax
0x18003e183  jz      short loc_18003E189
0x18003e185  xor     ebx, ebx
0x18003e187  jmp     short loc_18003E1A8
0x18003e189  call    cs:__imp_GetLastError
0x18003e18f  mov     ebx, eax
0x18003e191  test    eax, eax
0x18003e193  jle     short loc_18003E19E
0x18003e195  movzx   ebx, ax
0x18003e198  or      ebx, 80070000h
0x18003e19e  test    ebx, ebx
0x18003e1a0  mov     ecx, 80004005h
0x18003e1a5  cmovns  ebx, ecx
0x18003e1a8  mov     rdx, qword ptr [rsp+28h+NewFilePointer]; liDistanceToMove
0x18003e1ad  xor     r9d, r9d; dwMoveMethod
0x18003e1b0  mov     rcx, [rdi+8]; hFile
0x18003e1b4  xor     r8d, r8d; lpNewFilePointer
0x18003e1b7  call    cs:__imp_SetFilePointerEx
0x18003e1bd  mov     eax, ebx
0x18003e1bf  mov     rbx, [rsp+28h+arg_8]
0x18003e1c4  add     rsp, 20h
0x18003e1c8  pop     rdi
0x18003e1c9  retn
```
