# CertDiagWriteBytesToFile

- ea: `0x1800c19fc`
- end: `0x1800c1aff`
- name: `CertDiagWriteBytesToFile`
- size: `259`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800c1828`
- `0x1800f11c4`

## callees

- `0x1800823c0`
- `0x180082450`
- `0x1800c19fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1a6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1a6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c1a7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c1a7d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c1a66`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c1a66`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c1aa6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c1aa6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c1ac8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c1ac8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800c1a91`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800c1a91`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800c1ad5`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800c1ad5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1ade`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1ade`

## pseudocode

```c
void __fastcall CertDiagWriteBytesToFile(LPCWSTR lpFileName, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, int a4)
{
  void *v8; // rbp
  HANDLE FileW; // rbx
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+18h] BYREF

  if ( nNumberOfBytesToWrite )
  {
    NumberOfBytesWritten = 0;
    if ( lpBuffer )
    {
      v8 = CertDiagPrvRevertImpersonateToken();
      FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 4u, a4 != 0 ? 4 : 0, 0);
      LastError = GetLastError();
      if ( FileW == (HANDLE)-1LL )
      {
        SetLastError(LastError);
      }
      else
      {
        if ( LastError != 183 || nNumberOfBytesToWrite != GetFileSize(FileW, 0) && SetFilePointer(FileW, 0, 0, 0) != -1 )
        {
          if ( WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
            SetEndOfFile(FileW);
        }
        CloseHandle(FileW);
      }
      CertDiagPrvRestoreImpersonateToken(v8);
    }
  }
}

```

## disassembly

```asm
0x1800c19fc  test    r8d, r8d
0x1800c19ff  jz      locret_1800C1AFE
0x1800c1a05  mov     [rsp+arg_0], rbx
0x1800c1a0a  mov     [rsp+arg_8], rbp
0x1800c1a0f  push    rsi
0x1800c1a10  push    rdi
0x1800c1a11  push    r14
0x1800c1a13  sub     rsp, 40h
0x1800c1a17  mov     [rsp+58h+NumberOfBytesWritten], 0
0x1800c1a1f  mov     ebx, r9d
0x1800c1a22  mov     edi, r8d
0x1800c1a25  mov     rsi, rdx
0x1800c1a28  mov     r14, rcx
0x1800c1a2b  test    rdx, rdx
0x1800c1a2e  jz      loc_1800C1AEC
0x1800c1a34  call    ?CertDiagPrvRevertImpersonateToken@@YAPEAXXZ; CertDiagPrvRevertImpersonateToken(void)
0x1800c1a39  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x1800c1a42  neg     ebx
0x1800c1a44  mov     rcx, r14; lpFileName
0x1800c1a47  mov     rbp, rax
0x1800c1a4a  sbb     edx, edx
0x1800c1a4c  xor     r9d, r9d; lpSecurityAttributes
0x1800c1a4f  and     edx, 4
0x1800c1a52  xor     r8d, r8d; dwShareMode
0x1800c1a55  mov     [rsp+58h+dwFlagsAndAttributes], edx; dwFlagsAndAttributes
0x1800c1a59  mov     edx, 0C0000000h; dwDesiredAccess
0x1800c1a5e  mov     [rsp+58h+dwCreationDisposition], 4; dwCreationDisposition
0x1800c1a66  call    cs:__imp_CreateFileW
0x1800c1a6c  mov     rbx, rax
0x1800c1a6f  call    cs:__imp_GetLastError
0x1800c1a75  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800c1a79  jnz     short loc_1800C1A85
0x1800c1a7b  mov     ecx, eax; dwErrCode
0x1800c1a7d  call    cs:__imp_SetLastError
0x1800c1a83  jmp     short loc_1800C1AE4
0x1800c1a85  cmp     eax, 0B7h
0x1800c1a8a  jnz     short loc_1800C1AB1
0x1800c1a8c  xor     edx, edx; lpFileSizeHigh
0x1800c1a8e  mov     rcx, rbx; hFile
0x1800c1a91  call    cs:__imp_GetFileSize
0x1800c1a97  cmp     edi, eax
0x1800c1a99  jz      short loc_1800C1ADB
0x1800c1a9b  xor     r9d, r9d; dwMoveMethod
0x1800c1a9e  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800c1aa1  xor     edx, edx; lDistanceToMove
0x1800c1aa3  mov     rcx, rbx; hFile
0x1800c1aa6  call    cs:__imp_SetFilePointer
0x1800c1aac  cmp     eax, 0FFFFFFFFh
0x1800c1aaf  jz      short loc_1800C1ADB
0x1800c1ab1  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c1ab6  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOverlapped
0x1800c1abf  mov     r8d, edi; nNumberOfBytesToWrite
0x1800c1ac2  mov     rdx, rsi; lpBuffer
0x1800c1ac5  mov     rcx, rbx; hFile
0x1800c1ac8  call    cs:__imp_WriteFile
0x1800c1ace  test    eax, eax
0x1800c1ad0  jz      short loc_1800C1ADB
0x1800c1ad2  mov     rcx, rbx; hFile
0x1800c1ad5  call    cs:__imp_SetEndOfFile
0x1800c1adb  mov     rcx, rbx; hObject
0x1800c1ade  call    cs:__imp_CloseHandle
0x1800c1ae4  mov     rcx, rbp; hObject
0x1800c1ae7  call    ?CertDiagPrvRestoreImpersonateToken@@YAXPEAX@Z; CertDiagPrvRestoreImpersonateToken(void *)
0x1800c1aec  mov     rbx, [rsp+58h+arg_0]
0x1800c1af1  mov     rbp, [rsp+58h+arg_8]
0x1800c1af6  add     rsp, 40h
0x1800c1afa  pop     r14
0x1800c1afc  pop     rdi
0x1800c1afd  pop     rsi
0x1800c1afe  retn
```
