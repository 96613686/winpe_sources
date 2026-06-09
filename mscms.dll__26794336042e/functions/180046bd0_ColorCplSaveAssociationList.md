# ColorCplSaveAssociationList

- ea: `0x180046bd0`
- end: `0x180046de2`
- name: `ColorCplSaveAssociationList`
- size: `530`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18002e614`
- `0x180046bd0`
- `0x180046fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046cca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046d91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046cca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046d91`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180046cb8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180046cb8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180046dc3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180046dc3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180046d3b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180046d6a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180046d3b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180046d6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046da9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046da9`

## pseudocode

```c
__int64 __fastcall ColorCplSaveAssociationList(
        enum WCS_PROFILE_MANAGEMENT_SCOPE a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        const WCHAR *a4,
        int a5)
{
  char *v6; // rsi
  signed int ProfileAssociationList; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  HANDLE FileW; // rax
  void *v11; // r15
  signed int LastError; // eax
  char *i; // rdi
  __int64 v14; // r14
  signed int v15; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+44h] [rbp-Ch] BYREF
  LPCVOID lpBuffer; // [rsp+48h] [rbp-8h] BYREF

  v6 = 0;
  lpBuffer = 0;
  if ( !dword_18009F478 )
  {
    ProfileAssociationList = -2147221495;
LABEL_38:
    DeleteFileW(a4);
    goto LABEL_39;
  }
  if ( !a2 )
    goto LABEL_37;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( !v8 || a3 != 1835955314 && a3 != 1886549106 && a3 != 1935896178 )
    goto LABEL_37;
  if ( (unsigned int)a1 > WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER )
    goto LABEL_37;
  if ( !a4 )
    goto LABEL_37;
  v9 = -1;
  do
    ++v9;
  while ( a4[v9] );
  if ( !v9 )
  {
LABEL_37:
    ProfileAssociationList = -2147024809;
    goto LABEL_38;
  }
  v18 = 0;
  ProfileAssociationList = ColorCplSupportUtil::GetProfileAssociationList(
                             a1,
                             a2,
                             a3,
                             a5,
                             (unsigned __int16 **)&lpBuffer,
                             &v18);
  if ( ProfileAssociationList < 0 )
  {
    v6 = (char *)lpBuffer;
    goto LABEL_38;
  }
  FileW = CreateFileW(a4, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v6 = (char *)lpBuffer;
  v11 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    ProfileAssociationList = LastError;
    if ( LastError > 0 )
      ProfileAssociationList = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    if ( v18 )
    {
      for ( i = (char *)lpBuffer; *(_WORD *)i && i < &v6[2 * v18]; i += 2 * (unsigned int)(v14 + 1) )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)&i[2 * v14] );
        NumberOfBytesWritten = 0;
        LODWORD(lpBuffer) = 2 * v14;
        if ( !WriteFile(v11, i, 2 * v14, &NumberOfBytesWritten, 0) )
          goto LABEL_31;
        if ( NumberOfBytesWritten != (_DWORD)lpBuffer )
          goto LABEL_30;
        if ( !WriteFile(v11, L"\r\n", 4u, &NumberOfBytesWritten, 0) )
        {
LABEL_31:
          v15 = GetLastError();
          ProfileAssociationList = v15;
          if ( v15 > 0 )
            ProfileAssociationList = (unsigned __int16)v15 | 0x80070000;
          break;
        }
        if ( NumberOfBytesWritten != 4 )
        {
LABEL_30:
          ProfileAssociationList = -2147221501;
          break;
        }
      }
    }
    CloseHandle(v11);
  }
  if ( ProfileAssociationList < 0 )
    goto LABEL_38;
LABEL_39:
  operator delete(v6);
  return (unsigned int)ProfileAssociationList;
}

```

## disassembly

```asm
0x180046bd0  push    rbp
0x180046bd2  push    rbx
0x180046bd3  push    rsi
0x180046bd4  push    rdi
0x180046bd5  push    r13
0x180046bd7  push    r14
0x180046bd9  push    r15
0x180046bdb  mov     rbp, rsp
0x180046bde  sub     rsp, 50h
0x180046be2  xor     r14d, r14d
0x180046be5  mov     r13, r9
0x180046be8  cmp     cs:dword_18009F478, r14d
0x180046bef  mov     esi, r14d
0x180046bf2  mov     [rbp+lpBuffer], r14
0x180046bf6  jnz     short loc_180046C02
0x180046bf8  mov     ebx, 80040009h
0x180046bfd  jmp     loc_180046DC0
0x180046c02  test    rdx, rdx
0x180046c05  jz      loc_180046DBB
0x180046c0b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180046c0f  mov     rax, rdi
0x180046c12  inc     rax
0x180046c15  cmp     [rdx+rax*2], r14w
0x180046c1a  jnz     short loc_180046C12
0x180046c1c  test    rax, rax
0x180046c1f  jz      loc_180046DBB
0x180046c25  cmp     r8d, 6D6E7472h
0x180046c2c  jz      short loc_180046C44
0x180046c2e  cmp     r8d, 70727472h
0x180046c35  jz      short loc_180046C44
0x180046c37  cmp     r8d, 73636E72h
0x180046c3e  jnz     loc_180046DBB
0x180046c44  cmp     ecx, 1
0x180046c47  ja      loc_180046DBB
0x180046c4d  test    r13, r13
0x180046c50  jz      loc_180046DBB
0x180046c56  mov     rax, rdi
0x180046c59  inc     rax
0x180046c5c  cmp     [r9+rax*2], r14w
0x180046c61  jnz     short loc_180046C59
0x180046c63  test    rax, rax
0x180046c66  jz      loc_180046DBB
0x180046c6c  mov     r9d, [rbp+arg_20]; int
0x180046c70  lea     rax, [rbp+var_C]
0x180046c74  mov     qword ptr [rsp+50h+dwFlagsAndAttributes], rax; unsigned int *
0x180046c79  lea     rax, [rbp+lpBuffer]
0x180046c7d  mov     qword ptr [rsp+50h+dwCreationDisposition], rax; unsigned __int16 **
0x180046c82  mov     [rbp+var_C], r14d
0x180046c86  call    ?GetProfileAssociationList@ColorCplSupportUtil@@SAJW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGKHPEAPEAGPEAK@Z; ColorCplSupportUtil::GetProfileAssociationList(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,int,ushort * *,ulong *)
0x180046c8b  mov     ebx, eax
0x180046c8d  test    eax, eax
0x180046c8f  js      loc_180046DB5
0x180046c95  mov     [rsp+50h+hTemplateFile], r14; hTemplateFile
0x180046c9a  xor     r9d, r9d; lpSecurityAttributes
0x180046c9d  mov     [rsp+50h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180046ca5  xor     r8d, r8d; dwShareMode
0x180046ca8  mov     edx, 40000000h; dwDesiredAccess
0x180046cad  mov     [rsp+50h+dwCreationDisposition], 2; dwCreationDisposition
0x180046cb5  mov     rcx, r13; lpFileName
0x180046cb8  call    cs:__imp_CreateFileW
0x180046cbe  mov     rsi, [rbp+lpBuffer]
0x180046cc2  mov     r15, rax
0x180046cc5  cmp     rax, rdi
0x180046cc8  jnz     short loc_180046CE8
0x180046cca  call    cs:__imp_GetLastError
0x180046cd0  mov     ebx, eax
0x180046cd2  test    eax, eax
0x180046cd4  jle     loc_180046DAF
0x180046cda  movzx   ebx, ax
0x180046cdd  or      ebx, 80070000h
0x180046ce3  jmp     loc_180046DAF
0x180046ce8  cmp     [rbp+var_C], r14d
0x180046cec  jbe     loc_180046DA6
0x180046cf2  mov     rdi, rsi
0x180046cf5  cmp     [rdi], r14w
0x180046cf9  jz      loc_180046DA6
0x180046cff  mov     eax, [rbp+var_C]
0x180046d02  lea     rcx, [rsi+rax*2]
0x180046d06  cmp     rdi, rcx
0x180046d09  jnb     loc_180046DA6
0x180046d0f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180046d13  xor     ecx, ecx
0x180046d15  inc     r14
0x180046d18  cmp     [rdi+r14*2], cx
0x180046d1d  jnz     short loc_180046D15
0x180046d1f  lea     eax, [r14+r14]
0x180046d23  mov     [rbp+NumberOfBytesWritten], ecx
0x180046d26  mov     qword ptr [rsp+50h+dwCreationDisposition], rcx; lpOverlapped
0x180046d2b  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180046d2f  mov     r8d, eax; nNumberOfBytesToWrite
0x180046d32  mov     dword ptr [rbp+lpBuffer], eax
0x180046d35  mov     rdx, rdi; lpBuffer
0x180046d38  mov     rcx, r15; hFile
0x180046d3b  call    cs:__imp_WriteFile
0x180046d41  test    eax, eax
0x180046d43  jz      short loc_180046D91
0x180046d45  mov     eax, dword ptr [rbp+lpBuffer]
0x180046d48  cmp     [rbp+NumberOfBytesWritten], eax
0x180046d4b  jnz     short loc_180046D8A
0x180046d4d  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180046d51  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x180046d5a  mov     r8d, 4; nNumberOfBytesToWrite
0x180046d60  lea     rdx, asc_18008C338; "\r\n"
0x180046d67  mov     rcx, r15; hFile
0x180046d6a  call    cs:__imp_WriteFile
0x180046d70  test    eax, eax
0x180046d72  jz      short loc_180046D91
0x180046d74  cmp     [rbp+NumberOfBytesWritten], 4
0x180046d78  jnz     short loc_180046D8A
0x180046d7a  lea     eax, [r14+1]
0x180046d7e  xor     r14d, r14d
0x180046d81  lea     rdi, [rdi+rax*2]
0x180046d85  jmp     loc_180046CF5
0x180046d8a  mov     ebx, 80040003h
0x180046d8f  jmp     short loc_180046DA6
0x180046d91  call    cs:__imp_GetLastError
0x180046d97  mov     ebx, eax
0x180046d99  test    eax, eax
0x180046d9b  jle     short loc_180046DA6
0x180046d9d  movzx   ebx, ax
0x180046da0  or      ebx, 80070000h
0x180046da6  mov     rcx, r15; hObject
0x180046da9  call    cs:__imp_CloseHandle
0x180046daf  test    ebx, ebx
0x180046db1  jns     short loc_180046DC9
0x180046db3  jmp     short loc_180046DC0
0x180046db5  mov     rsi, [rbp+lpBuffer]
0x180046db9  jmp     short loc_180046DC0
0x180046dbb  mov     ebx, 80070057h
0x180046dc0  mov     rcx, r13; lpFileName
0x180046dc3  call    cs:__imp_DeleteFileW
0x180046dc9  mov     rcx, rsi; void *
0x180046dcc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180046dd1  mov     eax, ebx
0x180046dd3  add     rsp, 50h
0x180046dd7  pop     r15
0x180046dd9  pop     r14
0x180046ddb  pop     r13
0x180046ddd  pop     rdi
0x180046dde  pop     rsi
0x180046ddf  pop     rbx
0x180046de0  pop     rbp
0x180046de1  retn
```
