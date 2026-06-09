# CUserProfile::CheckNtUserIni(ushort const *)

- ea: `0x180028ad0`
- end: `0x180028c64`
- name: `?CheckNtUserIni@CUserProfile@@UEAAJPEBG@Z`
- size: `404`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800084bc`
- `0x18000d030`
- `0x18000e1a0`
- `0x180028ad0`
- `0x180030ad0`
- `0x180031060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028bd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028c3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028c3f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028b5a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028b5a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180028c26`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180028c26`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028b9a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028bc3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028b9a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028bc3`

## string_xrefs

- `0x180028b19`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180028bf1`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfile::CheckNtUserIni(CUserProfile *this, const unsigned __int16 *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  char *FileW; // rbx
  DWORD LastError; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-40h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-40h]
  LPCWSTR lpFileName[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  char *NumberOfBytesWritten; // [rsp+80h] [rbp+20h] BYREF

  memset(lpFileName, 0, 24);
  v2 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpFileName,
         L"%s\\%s",
         a2,
         L"ntuser.ini");
  v3 = v2;
  if ( v2 >= 0 )
  {
    FileW = (char *)CreateFileW(lpFileName[0], 0x10000000u, 0, 0, 1u, 6u, 0);
    NumberOfBytesWritten = FileW;
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LODWORD(NumberOfBytesWritten) = 0;
      WriteFile(FileW, &qword_180067EF8, 6u, (LPDWORD)&NumberOfBytesWritten, 0);
      WriteFile(FileW, L"     \r\n", 0xEu, (LPDWORD)&NumberOfBytesWritten, 0);
LABEL_11:
      CloseHandle(FileW);
      goto LABEL_12;
    }
    LastError = GetLastError();
    if ( LastError == 183 || LastError == 80 )
    {
      SetFileAttributesW(lpFileName[0], 6u);
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_11;
    }
    else
    {
      if ( LastError )
      {
        v3 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xB8F,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
               (const char *)LastError,
               dwCreationDispositiona);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NumberOfBytesWritten);
        goto LABEL_13;
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NumberOfBytesWritten);
    }
LABEL_12:
    v3 = 0;
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB75,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)(unsigned int)v2,
    dwCreationDisposition);
LABEL_13:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
  return v3;
}

```

## disassembly

```asm
0x180028ad0  mov     [rsp-8+arg_0], rbx
0x180028ad5  push    rbp
0x180028ad6  mov     rbp, rsp
0x180028ad9  sub     rsp, 60h
0x180028add  mov     r8, rdx
0x180028ae0  mov     [rbp+lpFileName], 0
0x180028ae8  lea     rdx, aSS_0; "%s\\%s"
0x180028aef  mov     [rbp+var_18], 0
0x180028af7  lea     r9, ?c_szNTUserIni@@3QBGB; "ntuser.ini"
0x180028afe  mov     [rbp+var_10], 0
0x180028b06  lea     rcx, [rbp+lpFileName]
0x180028b0a  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180028b0f  mov     ebx, eax
0x180028b11  test    eax, eax
0x180028b13  jns     short loc_180028B32
0x180028b15  mov     rcx, [rbp+8]; this
0x180028b19  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180028b20  mov     r9d, eax; char *
0x180028b23  mov     edx, 0B75h; void *
0x180028b28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028b2d  jmp     loc_180028C4D
0x180028b32  mov     rcx, [rbp+lpFileName]; lpFileName
0x180028b36  xor     r9d, r9d; lpSecurityAttributes
0x180028b39  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x180028b42  xor     r8d, r8d; dwShareMode
0x180028b45  mov     [rsp+60h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x180028b4d  mov     edx, 10000000h; dwDesiredAccess
0x180028b52  mov     [rsp+60h+dwCreationDisposition], 1; unsigned int
0x180028b5a  call    cs:__imp_CreateFileW
0x180028b61  nop     dword ptr [rax+rax+00h]
0x180028b66  mov     rbx, rax
0x180028b69  mov     [rbp+NumberOfBytesWritten], rax
0x180028b6d  dec     rax
0x180028b70  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028b74  ja      short loc_180028BD1
0x180028b76  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180028b7a  mov     dword ptr [rbp+NumberOfBytesWritten], 0
0x180028b81  mov     r8d, 6; nNumberOfBytesToWrite
0x180028b87  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; lpOverlapped
0x180028b90  lea     rdx, qword_180067EF8; lpBuffer
0x180028b97  mov     rcx, rbx; hFile
0x180028b9a  call    cs:__imp_WriteFile
0x180028ba1  nop     dword ptr [rax+rax+00h]
0x180028ba6  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180028baa  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; lpOverlapped
0x180028bb3  mov     r8d, 0Eh; nNumberOfBytesToWrite
0x180028bb9  lea     rdx, asc_180067F00; "     \r\n"
0x180028bc0  mov     rcx, rbx; hFile
0x180028bc3  call    cs:__imp_WriteFile
0x180028bca  nop     dword ptr [rax+rax+00h]
0x180028bcf  jmp     short loc_180028C3C
0x180028bd1  call    cs:__imp_GetLastError
0x180028bd8  nop     dword ptr [rax+rax+00h]
0x180028bdd  cmp     eax, 0B7h
0x180028be2  jz      short loc_180028C1D
0x180028be4  cmp     eax, 50h ; 'P'
0x180028be7  jz      short loc_180028C1D
0x180028be9  test    eax, eax
0x180028beb  jz      short loc_180028C12
0x180028bed  mov     rcx, [rbp+8]; this
0x180028bf1  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180028bf8  mov     r9d, eax; char *
0x180028bfb  mov     edx, 0B8Fh; void *
0x180028c00  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180028c05  lea     rcx, [rbp+NumberOfBytesWritten]
0x180028c09  mov     ebx, eax
0x180028c0b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180028c10  jmp     short loc_180028C4D
0x180028c12  lea     rcx, [rbp+NumberOfBytesWritten]
0x180028c16  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180028c1b  jmp     short loc_180028C4B
0x180028c1d  mov     rcx, [rbp+lpFileName]; lpFileName
0x180028c21  mov     edx, 6; dwFileAttributes
0x180028c26  call    cs:__imp_SetFileAttributesW
0x180028c2d  nop     dword ptr [rax+rax+00h]
0x180028c32  lea     rax, [rbx-1]
0x180028c36  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028c3a  ja      short loc_180028C4B
0x180028c3c  mov     rcx, rbx; hObject
0x180028c3f  call    cs:__imp_CloseHandle
0x180028c46  nop     dword ptr [rax+rax+00h]
0x180028c4b  xor     ebx, ebx
0x180028c4d  lea     rcx, [rbp+lpFileName]
0x180028c51  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180028c56  mov     eax, ebx
0x180028c58  mov     rbx, [rsp+60h+arg_0]
0x180028c5d  add     rsp, 60h
0x180028c61  pop     rbp
0x180028c62  retn
```
