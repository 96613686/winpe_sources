# FrsLogFile::CreateNewLogFile(void)

- ea: `0x1401b7dbc`
- end: `0x1401b810d`
- name: `?CreateNewLogFile@FrsLogFile@@AEAAPEAVFrsStatus@@XZ`
- size: `849`
- prototype: `struct FrsStatus *__fastcall(FrsLogFile *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1401b7ba8`
- `0x1401b8204`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x14000e34c`
- `0x14000ee94`
- `0x1400248f4`
- `0x1400ae800`
- `0x1401b723c`
- `0x1401b743c`
- `0x1401b786c`
- `0x1401b78b0`
- `0x1401b7dbc`
- `0x1401b86cc`
- `0x1401b8788`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x1401b80d6`
- `KERNEL32!FindFirstFileW` at `0x1401b80d6`
- `KERNEL32!FindClose` at `0x1401b80ef`
- `KERNEL32!FindClose` at `0x1401b80ef`
- `KERNEL32!CreateFileW` at `0x1401b7f65`
- `KERNEL32!CreateFileW` at `0x1401b7f65`
- `KERNEL32!GetLastError` at `0x1401b7ed0`
- `KERNEL32!GetLastError` at `0x1401b7f7f`
- `KERNEL32!GetLastError` at `0x1401b7ed0`
- `KERNEL32!GetLastError` at `0x1401b7f7f`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7ede`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7fc3`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7ede`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7fc3`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1401b7ec0`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1401b7ec0`

## string_xrefs

- `0x1401b7e76`: `FrsLogFile::CreateNewLogFile`
- `0x1401b7fe1`: `FrsLogFile::CreateNewLogFile`
- `0x1401b800d`: `FrsLogFile::CreateNewLogFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct FrsStatus *__fastcall FrsLogFile::CreateNewLogFile(FrsLogFile *this)
{
  struct FrsStatus *v2; // rbx
  int v3; // esi
  int v4; // r15d
  unsigned int v5; // edx
  FrsLogFile *v6; // rcx
  unsigned int v7; // edx
  DWORD v8; // ebx
  DWORD v9; // eax
  __int64 v10; // rcx
  HANDLE v11; // rax
  FrsLogFile *v12; // rcx
  DWORD LastError; // r14d
  DWORD CurrentThreadId; // eax
  __int64 v15; // rcx
  unsigned int v17; // edx
  HANDLE FirstFileW; // rax
  struct FrsStatus *v19; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  void **v21; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  void **v23; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+80h] [rbp-80h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF

  v2 = 0;
  v3 = 0;
  v4 = 0;
  FilePath::FilePath((FilePath *)&v23);
  FilePath::FilePath((FilePath *)&v21);
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FrsLogFile::Close(this);
  v5 = *((_DWORD *)this + 3);
  if ( v5 )
  {
    FrsLogFile::MakeFilePaths(this, v5, (struct FilePath *)&v23, (struct FilePath *)&v21);
    v19 = FrsLogFile::Compress(v6, (const struct FilePath *)&v23, (const struct FilePath *)&v21);
    CLEAR_ERROR(&v19);
    v2 = v19;
  }
  do
  {
    v7 = *((_DWORD *)this + 3);
    if ( v7 < *((_DWORD *)this + 4) )
    {
      v17 = v7 + 1;
      *((_DWORD *)this + 3) = v17;
      FrsLogFile::MakeFilePaths(this, v17, (struct FilePath *)&v23, (struct FilePath *)&v21);
      FirstFileW = FindFirstFileW((LPCWSTR)(v22 + 18), &FindFileData);
      if ( FirstFileW != (HANDLE)-1LL )
      {
        FindClose(FirstFileW);
        continue;
      }
    }
    else
    {
      v2 = FrsLogFile::ShiftLogFiles(this);
      v4 = 1;
      if ( v2 )
        v3 = 1;
    }
    SecurityDescriptor = 0;
    if ( !v2 )
    {
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
             L"O:BAD:P(A;NP;FA;;;BA)(A;NP;FA;;;SY)",
             1u,
             &SecurityDescriptor,
             0)
        || (v8 = GetLastError(),
            v9 = GetCurrentThreadId(),
            (v2 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                        v10,
                                        v8,
                                        0,
                                        1,
                                        "base\\fs\\remotefs\\frs\\src\\util\\frslogger.cpp",
                                        "FrsLogFile::CreateNewLogFile",
                                        795,
                                        v9,
                                        0)) == 0) )
      {
        SecurityAttributes.nLength = 24;
        SecurityAttributes.bInheritHandle = 0;
        SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
        v11 = CreateFileW(
                (LPCWSTR)(v24 + 18),
                0x40000000u,
                3u,
                &SecurityAttributes,
                1u,
                0x80u,
                (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        *((_QWORD *)this + 3) = v11;
        if ( v11 == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          if ( LastError == 80 )
          {
            v19 = FrsLogFile::Compress(v12, (const struct FilePath *)&v23, (const struct FilePath *)&v21);
            CLEAR_ERROR(&v19);
            v2 = v19;
          }
          if ( *((_DWORD *)this + 3) >= *((_DWORD *)this + 4) && v4 )
          {
            CurrentThreadId = GetCurrentThreadId();
            v2 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                       v15,
                                       LastError,
                                       0,
                                       1,
                                       "base\\fs\\remotefs\\frs\\src\\util\\frslogger.cpp",
                                       "FrsLogFile::CreateNewLogFile",
                                       837,
                                       CurrentThreadId,
                                       0);
            v3 = 1;
          }
        }
        else
        {
          ++*((_DWORD *)this + 2);
          v3 = 1;
        }
      }
    }
    scoped_any<void *,close_fun<void * (*)(void *),&void * LocalFree(void *)>,null_t,0>::~scoped_any<void *,close_fun<void * (*)(void *),&void * LocalFree(void *)>,null_t,0>(&SecurityDescriptor);
  }
  while ( !v3 );
  if ( !v2 )
  {
    *(_DWORD *)this = 0;
    v19 = FrsLogFile::AddProductHeader(this);
    CLEAR_ERROR(&v19);
    v19 = FrsLogFile::AddConfigurationToLog(this);
    CLEAR_ERROR(&v19);
    v2 = v19;
  }
  v21 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v22);
  v23 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v24);
  return v2;
}

```

## disassembly

```asm
0x1401b7dbc  mov     [rsp-8+arg_8], rbx
0x1401b7dc1  mov     [rsp-8+arg_10], rsi
0x1401b7dc6  push    rbp
0x1401b7dc7  push    rdi
0x1401b7dc8  push    r13
0x1401b7dca  push    r14
0x1401b7dcc  push    r15
0x1401b7dce  lea     rbp, [rsp-200h]
0x1401b7dd6  sub     rsp, 300h
0x1401b7ddd  mov     rax, cs:__security_cookie
0x1401b7de4  xor     rax, rsp
0x1401b7de7  mov     [rbp+220h+var_30], rax
0x1401b7dee  mov     rdi, rcx
0x1401b7df1  xor     ebx, ebx
0x1401b7df3  xor     esi, esi
0x1401b7df5  xor     r15d, r15d
0x1401b7df8  lea     rcx, [rsp+320h+var_2B0]; this
0x1401b7dfd  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x1401b7e02  nop
0x1401b7e03  lea     rcx, [rsp+320h+var_2C0]; this
0x1401b7e08  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x1401b7e0d  nop
0x1401b7e0e  xorps   xmm0, xmm0
0x1401b7e11  xor     eax, eax
0x1401b7e13  movups  xmmword ptr [rbp+220h+SecurityAttributes.nLength], xmm0
0x1401b7e17  mov     qword ptr [rbp+220h+SecurityAttributes.bInheritHandle], rax
0x1401b7e1b  xor     edx, edx; Val
0x1401b7e1d  mov     r8d, 250h; Size
0x1401b7e23  lea     rcx, [rbp+220h+FindFileData]; void *
0x1401b7e27  call    memset_0
0x1401b7e2c  mov     rcx, rdi; this
0x1401b7e2f  call    ?Close@FrsLogFile@@QEAAXXZ; FrsLogFile::Close(void)
0x1401b7e34  mov     edx, [rdi+0Ch]; unsigned int
0x1401b7e37  test    edx, edx
0x1401b7e39  jz      short loc_1401B7E70
0x1401b7e3b  lea     r9, [rsp+320h+var_2C0]; struct FilePath *
0x1401b7e40  lea     r8, [rsp+320h+var_2B0]; struct FilePath *
0x1401b7e45  mov     rcx, rdi; this
0x1401b7e48  call    ?MakeFilePaths@FrsLogFile@@AEAAXKAEAVFilePath@@0@Z; FrsLogFile::MakeFilePaths(ulong,FilePath &,FilePath &)
0x1401b7e4d  lea     r8, [rsp+320h+var_2C0]; struct FilePath *
0x1401b7e52  lea     rdx, [rsp+320h+var_2B0]; struct FilePath *
0x1401b7e57  call    ?Compress@FrsLogFile@@AEAAPEAVFrsStatus@@AEBVFilePath@@0@Z; FrsLogFile::Compress(FilePath const &,FilePath const &)
0x1401b7e5c  mov     [rsp+320h+var_2D0], rax
0x1401b7e61  lea     rcx, [rsp+320h+var_2D0]; struct FrsStatus **
0x1401b7e66  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401b7e6b  mov     rbx, [rsp+320h+var_2D0]
0x1401b7e70  mov     r13d, 1
0x1401b7e76  lea     r14, aFrslogfileCrea; "FrsLogFile::CreateNewLogFile"
0x1401b7e7d  mov     edx, [rdi+0Ch]
0x1401b7e80  mov     rcx, rdi; this
0x1401b7e83  cmp     edx, [rdi+10h]
0x1401b7e86  jb      loc_1401B80B5
0x1401b7e8c  call    ?ShiftLogFiles@FrsLogFile@@AEAAPEAVFrsStatus@@XZ; FrsLogFile::ShiftLogFiles(void)
0x1401b7e91  mov     rbx, rax
0x1401b7e94  mov     r15d, r13d
0x1401b7e97  test    rax, rax
0x1401b7e9a  jz      short loc_1401B7E9F
0x1401b7e9c  mov     esi, r13d
0x1401b7e9f  and     [rsp+320h+SecurityDescriptor], 0
0x1401b7ea5  test    rbx, rbx
0x1401b7ea8  jnz     loc_1401B8014
0x1401b7eae  xor     r9d, r9d; SecurityDescriptorSize
0x1401b7eb1  lea     r8, [rsp+320h+SecurityDescriptor]; SecurityDescriptor
0x1401b7eb6  mov     edx, r13d; StringSDRevision
0x1401b7eb9  lea     rcx, aOBadPANpFaBaAN; "O:BAD:P(A;NP;FA;;;BA)(A;NP;FA;;;SY)"
0x1401b7ec0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1401b7ec7  nop     dword ptr [rax+rax+00h]
0x1401b7ecc  test    eax, eax
0x1401b7ece  jnz     short loc_1401B7F26
0x1401b7ed0  call    cs:__imp_GetLastError
0x1401b7ed7  nop     dword ptr [rax+rax+00h]
0x1401b7edc  mov     ebx, eax
0x1401b7ede  call    cs:__imp_GetCurrentThreadId
0x1401b7ee5  nop     dword ptr [rax+rax+00h]
0x1401b7eea  and     [rsp+320h+var_2E0], 0
0x1401b7ef0  mov     [rsp+320h+var_2E8], eax
0x1401b7ef4  mov     dword ptr [rsp+320h+hTemplateFile], 31Bh; hTemplateFile
0x1401b7efc  mov     qword ptr [rsp+320h+dwFlagsAndAttributes], r14
0x1401b7f01  lea     rax, aBaseFsRemotefs_92; "base\\fs\\remotefs\\frs\\src\\util\\frs"...
0x1401b7f08  mov     qword ptr [rsp+320h+dwCreationDisposition], rax
0x1401b7f0d  mov     r9d, r13d
0x1401b7f10  xor     r8d, r8d
0x1401b7f13  mov     edx, ebx
0x1401b7f15  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401b7f1a  mov     rbx, rax
0x1401b7f1d  test    rax, rax
0x1401b7f20  jnz     loc_1401B8014
0x1401b7f26  mov     [rbp+220h+SecurityAttributes.nLength], 18h
0x1401b7f2d  and     [rbp+220h+SecurityAttributes.bInheritHandle], 0
0x1401b7f31  mov     rax, [rsp+320h+SecurityDescriptor]
0x1401b7f36  mov     [rbp+220h+SecurityAttributes.lpSecurityDescriptor], rax
0x1401b7f3a  mov     rcx, [rsp+320h+var_2A8]
0x1401b7f3f  add     rcx, 12h; lpFileName
0x1401b7f43  or      [rsp+320h+hTemplateFile], 0FFFFFFFFFFFFFFFFh
0x1401b7f49  mov     [rsp+320h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1401b7f51  mov     [rsp+320h+dwCreationDisposition], r13d; dwCreationDisposition
0x1401b7f56  lea     r9, [rbp+220h+SecurityAttributes]; lpSecurityAttributes
0x1401b7f5a  mov     edx, 40000000h; dwDesiredAccess
0x1401b7f5f  mov     r8d, 3; dwShareMode
0x1401b7f65  call    cs:__imp_CreateFileW
0x1401b7f6c  nop     dword ptr [rax+rax+00h]
0x1401b7f71  mov     [rdi+18h], rax
0x1401b7f75  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401b7f79  jnz     loc_1401B8100
0x1401b7f7f  call    cs:__imp_GetLastError
0x1401b7f86  nop     dword ptr [rax+rax+00h]
0x1401b7f8b  mov     r14d, eax
0x1401b7f8e  cmp     eax, 50h ; 'P'
0x1401b7f91  jnz     short loc_1401B7FB6
0x1401b7f93  lea     r8, [rsp+320h+var_2C0]; struct FilePath *
0x1401b7f98  lea     rdx, [rsp+320h+var_2B0]; struct FilePath *
0x1401b7f9d  call    ?Compress@FrsLogFile@@AEAAPEAVFrsStatus@@AEBVFilePath@@0@Z; FrsLogFile::Compress(FilePath const &,FilePath const &)
0x1401b7fa2  mov     [rsp+320h+var_2D0], rax
0x1401b7fa7  lea     rcx, [rsp+320h+var_2D0]; struct FrsStatus **
0x1401b7fac  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401b7fb1  mov     rbx, [rsp+320h+var_2D0]
0x1401b7fb6  mov     eax, [rdi+10h]
0x1401b7fb9  cmp     [rdi+0Ch], eax
0x1401b7fbc  jb      short loc_1401B800D
0x1401b7fbe  test    r15d, r15d
0x1401b7fc1  jz      short loc_1401B800D
0x1401b7fc3  call    cs:__imp_GetCurrentThreadId
0x1401b7fca  nop     dword ptr [rax+rax+00h]
0x1401b7fcf  and     [rsp+320h+var_2E0], 0
0x1401b7fd5  mov     [rsp+320h+var_2E8], eax
0x1401b7fd9  mov     dword ptr [rsp+320h+hTemplateFile], 345h
0x1401b7fe1  lea     rax, aFrslogfileCrea; "FrsLogFile::CreateNewLogFile"
0x1401b7fe8  mov     qword ptr [rsp+320h+dwFlagsAndAttributes], rax
0x1401b7fed  lea     rax, aBaseFsRemotefs_92; "base\\fs\\remotefs\\frs\\src\\util\\frs"...
0x1401b7ff4  mov     qword ptr [rsp+320h+dwCreationDisposition], rax
0x1401b7ff9  mov     r9d, r13d
0x1401b7ffc  xor     r8d, r8d
0x1401b7fff  mov     edx, r14d
0x1401b8002  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401b8007  mov     rbx, rax
0x1401b800a  mov     esi, r13d
0x1401b800d  lea     r14, aFrslogfileCrea; "FrsLogFile::CreateNewLogFile"
0x1401b8014  lea     rcx, [rsp+320h+SecurityDescriptor]
0x1401b8019  call    ??1?$scoped_any@PEAXU?$close_fun@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<void *,close_fun<void * (*)(void *),&LocalFree(void *)>,null_t,0>::~scoped_any<void *,close_fun<void * (*)(void *),&LocalFree(void *)>,null_t,0>(void)
0x1401b801e  test    esi, esi
0x1401b8020  jz      loc_1401B7E7D
0x1401b8026  test    rbx, rbx
0x1401b8029  jnz     short loc_1401B8060
0x1401b802b  and     [rdi], ebx
0x1401b802d  mov     rcx, rdi; this
0x1401b8030  call    ?AddProductHeader@FrsLogFile@@AEAAPEAVFrsStatus@@XZ; FrsLogFile::AddProductHeader(void)
0x1401b8035  mov     [rsp+320h+var_2D0], rax
0x1401b803a  lea     rcx, [rsp+320h+var_2D0]; struct FrsStatus **
0x1401b803f  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401b8044  mov     rcx, rdi; this
0x1401b8047  call    ?AddConfigurationToLog@FrsLogFile@@AEAAPEAVFrsStatus@@XZ; FrsLogFile::AddConfigurationToLog(void)
0x1401b804c  mov     [rsp+320h+var_2D0], rax
0x1401b8051  lea     rcx, [rsp+320h+var_2D0]; struct FrsStatus **
0x1401b8056  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401b805b  mov     rbx, [rsp+320h+var_2D0]
0x1401b8060  lea     rdi, ??_7FilePath@@6B@; const FilePath::`vftable'
0x1401b8067  mov     [rsp+320h+var_2C0], rdi
0x1401b806c  lea     rcx, [rsp+320h+var_2B8]
0x1401b8071  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401b8076  nop
0x1401b8077  mov     [rsp+320h+var_2B0], rdi
0x1401b807c  lea     rcx, [rsp+320h+var_2A8]
0x1401b8081  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401b8086  mov     rax, rbx
0x1401b8089  mov     rcx, [rbp+220h+var_30]
0x1401b8090  xor     rcx, rsp; StackCookie
0x1401b8093  call    __security_check_cookie
0x1401b8098  lea     r11, [rsp+320h+var_20]
0x1401b80a0  mov     rbx, [r11+38h]
0x1401b80a4  mov     rsi, [r11+40h]
0x1401b80a8  mov     rsp, r11
0x1401b80ab  pop     r15
0x1401b80ad  pop     r14
0x1401b80af  pop     r13
0x1401b80b1  pop     rdi
0x1401b80b2  pop     rbp
0x1401b80b3  retn
0x1401b80b5  inc     edx; unsigned int
0x1401b80b7  mov     [rdi+0Ch], edx
0x1401b80ba  lea     r9, [rsp+320h+var_2C0]; struct FilePath *
0x1401b80bf  lea     r8, [rsp+320h+var_2B0]; struct FilePath *
0x1401b80c4  call    ?MakeFilePaths@FrsLogFile@@AEAAXKAEAVFilePath@@0@Z; FrsLogFile::MakeFilePaths(ulong,FilePath &,FilePath &)
0x1401b80c9  mov     rcx, [rsp+320h+var_2B8]
0x1401b80ce  add     rcx, 12h; lpFileName
0x1401b80d2  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x1401b80d6  call    cs:__imp_FindFirstFileW
0x1401b80dd  nop     dword ptr [rax+rax+00h]
0x1401b80e2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401b80e6  jz      loc_1401B7E9F
0x1401b80ec  mov     rcx, rax; hFindFile
0x1401b80ef  call    cs:__imp_FindClose
0x1401b80f6  nop     dword ptr [rax+rax+00h]
0x1401b80fb  jmp     loc_1401B801E
0x1401b8100  add     [rdi+8], r13d
0x1401b8104  mov     esi, r13d
0x1401b8107  jmp     loc_1401B8014
```
