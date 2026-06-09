# CUserProfile::CheckNtUserIni(ushort const *)

- ea: `0x180026700`
- end: `0x18002686f`
- name: `?CheckNtUserIni@CUserProfile@@UEAAJPEBG@Z`
- size: `367`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000a9b8`
- `0x180010f30`
- `0x1800111a0`
- `0x180026700`
- `0x18002d2d8`
- `0x18002e648`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026851`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026851`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002678a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002678a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002683e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002683e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800267c4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800267e7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800267c4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800267e7`

## string_xrefs

- `0x180026749`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180026809`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

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
  void *NumberOfBytesWritten; // [rsp+80h] [rbp+20h] BYREF

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
      WriteFile(FileW, &qword_180064FF8, 6u, (LPDWORD)&NumberOfBytesWritten, 0);
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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpFileName);
  return v3;
}

```

## disassembly

```asm
0x180026700  mov     [rsp-8+arg_0], rbx
0x180026705  push    rbp
0x180026706  mov     rbp, rsp
0x180026709  sub     rsp, 60h
0x18002670d  mov     r8, rdx
0x180026710  mov     [rbp+lpFileName], 0
0x180026718  lea     rdx, aSS_0; "%s\\%s"
0x18002671f  mov     [rbp+var_18], 0
0x180026727  lea     r9, ?c_szNTUserIni@@3QBGB; "ntuser.ini"
0x18002672e  mov     [rbp+var_10], 0
0x180026736  lea     rcx, [rbp+lpFileName]
0x18002673a  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002673f  mov     ebx, eax
0x180026741  test    eax, eax
0x180026743  jns     short loc_180026762
0x180026745  mov     rcx, [rbp+8]; this
0x180026749  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180026750  mov     r9d, eax; char *
0x180026753  mov     edx, 0B75h; void *
0x180026758  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002675d  jmp     loc_180026859
0x180026762  mov     rcx, [rbp+lpFileName]; lpFileName
0x180026766  xor     r9d, r9d; lpSecurityAttributes
0x180026769  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x180026772  xor     r8d, r8d; dwShareMode
0x180026775  mov     [rsp+60h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x18002677d  mov     edx, 10000000h; dwDesiredAccess
0x180026782  mov     [rsp+60h+dwCreationDisposition], 1; unsigned int
0x18002678a  call    cs:__imp_CreateFileW
0x180026790  mov     rbx, rax
0x180026793  mov     [rbp+NumberOfBytesWritten], rax
0x180026797  dec     rax
0x18002679a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002679e  ja      short loc_1800267EF
0x1800267a0  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800267a4  mov     dword ptr [rbp+NumberOfBytesWritten], 0
0x1800267ab  mov     r8d, 6; nNumberOfBytesToWrite
0x1800267b1  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; lpOverlapped
0x1800267ba  lea     rdx, qword_180064FF8; lpBuffer
0x1800267c1  mov     rcx, rbx; hFile
0x1800267c4  call    cs:__imp_WriteFile
0x1800267ca  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800267ce  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; lpOverlapped
0x1800267d7  mov     r8d, 0Eh; nNumberOfBytesToWrite
0x1800267dd  lea     rdx, asc_180065000; "     \r\n"
0x1800267e4  mov     rcx, rbx; hFile
0x1800267e7  call    cs:__imp_WriteFile
0x1800267ed  jmp     short loc_18002684E
0x1800267ef  call    cs:__imp_GetLastError
0x1800267f5  cmp     eax, 0B7h
0x1800267fa  jz      short loc_180026835
0x1800267fc  cmp     eax, 50h ; 'P'
0x1800267ff  jz      short loc_180026835
0x180026801  test    eax, eax
0x180026803  jz      short loc_18002682A
0x180026805  mov     rcx, [rbp+8]; this
0x180026809  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180026810  mov     r9d, eax; char *
0x180026813  mov     edx, 0B8Fh; void *
0x180026818  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002681d  lea     rcx, [rbp+NumberOfBytesWritten]
0x180026821  mov     ebx, eax
0x180026823  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180026828  jmp     short loc_180026859
0x18002682a  lea     rcx, [rbp+NumberOfBytesWritten]
0x18002682e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180026833  jmp     short loc_180026857
0x180026835  mov     rcx, [rbp+lpFileName]; lpFileName
0x180026839  mov     edx, 6; dwFileAttributes
0x18002683e  call    cs:__imp_SetFileAttributesW
0x180026844  lea     rax, [rbx-1]
0x180026848  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002684c  ja      short loc_180026857
0x18002684e  mov     rcx, rbx; hObject
0x180026851  call    cs:__imp_CloseHandle
0x180026857  xor     ebx, ebx
0x180026859  lea     rcx, [rbp+lpFileName]
0x18002685d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180026862  mov     eax, ebx
0x180026864  mov     rbx, [rsp+60h+arg_0]
0x180026869  add     rsp, 60h
0x18002686d  pop     rbp
0x18002686e  retn
```
