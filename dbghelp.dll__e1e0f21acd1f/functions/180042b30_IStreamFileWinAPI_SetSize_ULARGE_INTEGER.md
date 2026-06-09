# IStreamFileWinAPI::SetSize(_ULARGE_INTEGER)

- ea: `0x180042b30`
- end: `0x180042bd6`
- name: `?SetSize@IStreamFileWinAPI@@UEAAJT_ULARGE_INTEGER@@@Z`
- size: `166`
- prototype: `int(IStreamFileWinAPI *__hidden this, union _ULARGE_INTEGER)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180042b30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180042b5d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180042b76`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180042b9f`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180042b5d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180042b76`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180042b9f`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180042b84`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180042b84`

## pseudocode

```c
__int64 __fastcall IStreamFileWinAPI::SetSize(HANDLE *this, union _ULARGE_INTEGER a2)
{
  BOOL v4; // eax
  unsigned int v5; // ecx
  union _LARGE_INTEGER v7; // [rsp+30h] [rbp+8h] BYREF
  union _LARGE_INTEGER NewFilePointer; // [rsp+40h] [rbp+18h] BYREF

  v7.QuadPart = 0;
  if ( !SetFilePointerEx(this[4], 0, &NewFilePointer, 1u)
    || !SetFilePointerEx(this[4], (LARGE_INTEGER)a2.QuadPart, &v7, 0)
    || !SetEndOfFile(this[4]) )
  {
    return 2147680257LL;
  }
  v4 = SetFilePointerEx(this[4], NewFilePointer, &v7, 0);
  v5 = -2147287039;
  if ( v4 )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x180042b30  mov     [rsp+arg_8], rbx
0x180042b35  mov     [rsp+arg_18], rsi
0x180042b3a  push    rdi
0x180042b3b  sub     rsp, 20h
0x180042b3f  xor     esi, esi
0x180042b41  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x180042b46  mov     rbx, rdx
0x180042b49  mov     qword ptr [rsp+28h+arg_0], rsi
0x180042b4e  mov     rdi, rcx
0x180042b51  mov     edx, esi; liDistanceToMove
0x180042b53  mov     rcx, [rcx+20h]; hFile
0x180042b57  mov     r9d, 1; dwMoveMethod
0x180042b5d  call    cs:__imp_SetFilePointerEx
0x180042b63  test    eax, eax
0x180042b65  jz      short loc_180042BC1
0x180042b67  mov     rcx, [rdi+20h]; hFile
0x180042b6b  lea     r8, [rsp+28h+arg_0]; lpNewFilePointer
0x180042b70  xor     r9d, r9d; dwMoveMethod
0x180042b73  mov     rdx, rbx; liDistanceToMove
0x180042b76  call    cs:__imp_SetFilePointerEx
0x180042b7c  test    eax, eax
0x180042b7e  jz      short loc_180042BC1
0x180042b80  mov     rcx, [rdi+20h]; hFile
0x180042b84  call    cs:__imp_SetEndOfFile
0x180042b8a  test    eax, eax
0x180042b8c  jz      short loc_180042BC1
0x180042b8e  mov     rdx, qword ptr [rsp+28h+NewFilePointer]; liDistanceToMove
0x180042b93  lea     r8, [rsp+28h+arg_0]; lpNewFilePointer
0x180042b98  mov     rcx, [rdi+20h]; hFile
0x180042b9c  xor     r9d, r9d; dwMoveMethod
0x180042b9f  call    cs:__imp_SetFilePointerEx
0x180042ba5  test    eax, eax
0x180042ba7  mov     ecx, 80030001h
0x180042bac  cmovnz  ecx, esi
0x180042baf  mov     eax, ecx
0x180042bb1  mov     rbx, [rsp+28h+arg_8]
0x180042bb6  mov     rsi, [rsp+28h+arg_18]
0x180042bbb  add     rsp, 20h
0x180042bbf  pop     rdi
0x180042bc0  retn
0x180042bc1  mov     rbx, [rsp+28h+arg_8]
0x180042bc6  mov     eax, 80030001h
0x180042bcb  mov     rsi, [rsp+28h+arg_18]
0x180042bd0  add     rsp, 20h
0x180042bd4  pop     rdi
0x180042bd5  retn
```
