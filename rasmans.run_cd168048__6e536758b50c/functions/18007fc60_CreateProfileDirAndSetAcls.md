# CreateProfileDirAndSetAcls

- ea: `0x18007fc60`
- end: `0x18007fde3`
- name: `CreateProfileDirAndSetAcls`
- size: `387`
- prototype: `__int64 __usercall@<rax>(HANDLE hToken@<rcx>, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800073ac`
- `0x1800714c0`

## callees

- `0x18005e894`
- `0x18006051c`
- `0x18007e5ac`
- `0x18007fc60`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007fd8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007fd8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fdb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fdb4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18007fcce`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18007fcce`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007fd10`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007fda4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007fd10`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007fda4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007fd5c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007fd5c`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18007fd74`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18007fd74`

## pseudocode

```c
__int64 __fastcall CreateProfileDirAndSetAcls(char *hToken, __int64 a2, int a3, __int64 a4, int a5)
{
  unsigned int DirectoriesOnPath; // ebx
  int v9; // edi
  HANDLE FileW; // rax
  void *v11; // rsi
  WCHAR FileName[264]; // [rsp+50h] [rbp-248h] BYREF

  memset_0(FileName, 0, 0x20Au);
  DirectoriesOnPath = StringCchCopyWrapW(FileName, 261, a2);
  if ( DirectoriesOnPath )
    return DirectoriesOnPath;
  v9 = 0;
  if ( a3 != 4 && (unsigned __int64)(hToken - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( !ImpersonateLoggedOnUser(hToken) )
      return GetLastError();
    v9 = 1;
  }
  DirectoriesOnPath = CreateDirectoriesOnPath(FileName);
  if ( !DirectoriesOnPath )
  {
    if ( !a3 )
      UpdateAclsOnPhonebookFolder(FileName);
    if ( v9 )
    {
      v9 = 0;
      if ( !RevertToSelf() )
        return GetLastError();
    }
    if ( !a5 )
      return DirectoriesOnPath;
    FileW = CreateFileW(FileName, 0xC0000000, 1u, 0, 2u, 0x80u, 0);
    v11 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      DirectoriesOnPath = 621;
    }
    else
    {
      if ( GetFileType(FileW) != 1 )
        DirectoriesOnPath = 621;
      CloseHandle(v11);
    }
  }
  if ( v9 && !RevertToSelf() )
    return GetLastError();
  return DirectoriesOnPath;
}

```

## disassembly

```asm
0x18007fc60  push    rbx
0x18007fc62  push    rbp
0x18007fc63  push    rsi
0x18007fc64  push    rdi
0x18007fc65  push    r14
0x18007fc67  sub     rsp, 270h
0x18007fc6e  mov     rax, cs:__security_cookie
0x18007fc75  xor     rax, rsp
0x18007fc78  mov     [rsp+298h+var_38], rax
0x18007fc80  mov     esi, r8d
0x18007fc83  mov     rbx, rdx
0x18007fc86  mov     rbp, rcx
0x18007fc89  xor     edx, edx; Val
0x18007fc8b  mov     r8d, 20Ah; Size
0x18007fc91  lea     rcx, [rsp+298h+FileName]; void *
0x18007fc96  mov     r14d, r9d
0x18007fc99  call    memset_0
0x18007fc9e  mov     r8, rbx
0x18007fca1  lea     rcx, [rsp+298h+FileName]
0x18007fca6  mov     edx, 105h
0x18007fcab  call    StringCchCopyWrapW
0x18007fcb0  mov     ebx, eax
0x18007fcb2  test    eax, eax
0x18007fcb4  jnz     loc_18007FDC2
0x18007fcba  xor     edi, edi
0x18007fcbc  cmp     esi, 4
0x18007fcbf  jz      short loc_18007FCE5
0x18007fcc1  lea     rax, [rbp-1]
0x18007fcc5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007fcc9  ja      short loc_18007FCE5
0x18007fccb  mov     rcx, rbp; hToken
0x18007fcce  call    cs:__imp_ImpersonateLoggedOnUser
0x18007fcd5  nop     dword ptr [rax+rax+00h]
0x18007fcda  test    eax, eax
0x18007fcdc  jz      loc_18007FDB4
0x18007fce2  lea     edi, [rbx+1]
0x18007fce5  lea     rcx, [rsp+298h+FileName]; lpPathName
0x18007fcea  call    CreateDirectoriesOnPath
0x18007fcef  mov     ebx, eax
0x18007fcf1  test    eax, eax
0x18007fcf3  jnz     loc_18007FDA0
0x18007fcf9  test    esi, esi
0x18007fcfb  jnz     short loc_18007FD0A
0x18007fcfd  mov     r8d, r14d
0x18007fd00  lea     rcx, [rsp+298h+FileName]; pszSrc
0x18007fd05  call    UpdateAclsOnPhonebookFolder
0x18007fd0a  test    edi, edi
0x18007fd0c  jz      short loc_18007FD24
0x18007fd0e  xor     edi, edi
0x18007fd10  call    cs:__imp_RevertToSelf
0x18007fd17  nop     dword ptr [rax+rax+00h]
0x18007fd1c  test    eax, eax
0x18007fd1e  jz      loc_18007FDB4
0x18007fd24  cmp     [rsp+298h+arg_20], 0
0x18007fd2c  jz      loc_18007FDC2
0x18007fd32  xor     r9d, r9d; lpSecurityAttributes
0x18007fd35  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x18007fd3e  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18007fd46  lea     rcx, [rsp+298h+FileName]; lpFileName
0x18007fd4b  mov     edx, 0C0000000h; dwDesiredAccess
0x18007fd50  mov     [rsp+298h+dwCreationDisposition], 2; dwCreationDisposition
0x18007fd58  lea     r8d, [r9+1]; dwShareMode
0x18007fd5c  call    cs:__imp_CreateFileW
0x18007fd63  nop     dword ptr [rax+rax+00h]
0x18007fd68  mov     rsi, rax
0x18007fd6b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007fd6f  jz      short loc_18007FD9B
0x18007fd71  mov     rcx, rax; hFile
0x18007fd74  call    cs:__imp_GetFileType
0x18007fd7b  nop     dword ptr [rax+rax+00h]
0x18007fd80  cmp     eax, 1
0x18007fd83  jz      short loc_18007FD8A
0x18007fd85  mov     ebx, 26Dh
0x18007fd8a  mov     rcx, rsi; hObject
0x18007fd8d  call    cs:__imp_CloseHandle
0x18007fd94  nop     dword ptr [rax+rax+00h]
0x18007fd99  jmp     short loc_18007FDA0
0x18007fd9b  mov     ebx, 26Dh
0x18007fda0  test    edi, edi
0x18007fda2  jz      short loc_18007FDC2
0x18007fda4  call    cs:__imp_RevertToSelf
0x18007fdab  nop     dword ptr [rax+rax+00h]
0x18007fdb0  test    eax, eax
0x18007fdb2  jnz     short loc_18007FDC2
0x18007fdb4  call    cs:__imp_GetLastError
0x18007fdbb  nop     dword ptr [rax+rax+00h]
0x18007fdc0  mov     ebx, eax
0x18007fdc2  mov     eax, ebx
0x18007fdc4  mov     rcx, [rsp+298h+var_38]
0x18007fdcc  xor     rcx, rsp; StackCookie
0x18007fdcf  call    __security_check_cookie
0x18007fdd4  add     rsp, 270h
0x18007fddb  pop     r14
0x18007fddd  pop     rdi
0x18007fdde  pop     rsi
0x18007fddf  pop     rbp
0x18007fde0  pop     rbx
0x18007fde1  retn
```
