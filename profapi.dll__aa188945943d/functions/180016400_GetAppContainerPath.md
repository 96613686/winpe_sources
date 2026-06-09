# GetAppContainerPath

- ea: `0x180016400`
- end: `0x1800165c3`
- name: `GetAppContainerPath`
- size: `451`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002484`
- `0x180003fdc`
- `0x180005b60`
- `0x180005b90`
- `0x18000608c`
- `0x18000a540`
- `0x18000cf24`
- `0x18000dc34`
- `0x18000f0b8`
- `0x18000f13c`
- `0x180016400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001644a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001644a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001643c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001643c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016488`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016488`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001649a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001649a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016426`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016426`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016471`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016471`

## string_xrefs

- `0x18001653b`: `_GetAppContainerPath %ws`

## pseudocode

```c
__int64 __fastcall GetAppContainerPath(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int64 a3)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *v8; // rbx
  HANDLE CurrentProcess; // rax
  const char *v10; // r9
  int v11; // eax
  int AppContainerPath; // ebx
  int v13; // eax
  unsigned int v15; // [rsp+20h] [rbp-30h]
  _BYTE v16[8]; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-18h] BYREF
  __int64 v18; // [rsp+40h] [rbp-10h]
  __int64 v19; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  void *TokenHandle; // [rsp+88h] [rbp+38h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_10;
  LastError = GetLastError();
  if ( LastError != 1008 )
  {
    if ( LastError )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x163,
              (unsigned int)"minio\\profapi\\appcontainer.cpp",
              (const char *)LastError,
              v15);
      goto LABEL_9;
    }
    goto LABEL_17;
  }
  v8 = TokenHandle;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v16);
    CloseHandle(v8);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v16);
  }
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
LABEL_10:
    v17 = 0;
    v18 = 0;
    v19 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v17);
    v18 = -1;
    v19 = -1;
    AppContainerPath = _GetAppContainerPath(TokenHandle, a1, &v17);
    if ( AppContainerPath == -2147024877 )
    {
LABEL_11:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v17);
      goto LABEL_18;
    }
    if ( AppContainerPath < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x16A,
        (unsigned int)"minio\\profapi\\appcontainer.cpp",
        (const char *)(unsigned int)AppContainerPath,
        (int)"_GetAppContainerPath %ws",
        (const char *)a1);
      goto LABEL_11;
    }
    v13 = StringCchCopyW(a2, a3, v17);
    AppContainerPath = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16B,
        (unsigned int)"minio\\profapi\\appcontainer.cpp",
        (const char *)(unsigned int)v13,
        v15);
      goto LABEL_11;
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v17);
LABEL_17:
    AppContainerPath = 0;
    goto LABEL_18;
  }
  v11 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x15F,
          (unsigned int)"minio\\profapi\\appcontainer.cpp",
          v10);
LABEL_9:
  AppContainerPath = v11;
LABEL_18:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return (unsigned int)AppContainerPath;
}

```

## disassembly

```asm
0x180016400  mov     [rsp-18h+arg_0], rbx
0x180016405  mov     [rsp-18h+arg_8], rsi
0x18001640a  push    rbp
0x18001640b  push    rdi
0x18001640c  push    r14
0x18001640e  mov     rbp, rsp
0x180016411  sub     rsp, 50h
0x180016415  mov     rsi, r8
0x180016418  mov     [rbp+TokenHandle], 0
0x180016420  mov     r14, rdx
0x180016423  mov     rdi, rcx
0x180016426  call    cs:__imp_GetCurrentThread
0x18001642c  mov     edx, 8; DesiredAccess
0x180016431  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180016435  mov     rcx, rax; ThreadHandle
0x180016438  lea     r8d, [rdx-7]; OpenAsSelf
0x18001643c  call    cs:__imp_OpenThreadToken
0x180016442  test    eax, eax
0x180016444  jnz     loc_1800164E2
0x18001644a  call    cs:__imp_GetLastError
0x180016450  cmp     eax, 3F0h
0x180016455  jnz     short loc_1800164BB
0x180016457  mov     rbx, [rbp+TokenHandle]
0x18001645b  lea     rax, [rbx-1]
0x18001645f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016463  ja      short loc_180016480
0x180016465  lea     rcx, [rbp+var_20]; this
0x180016469  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001646e  mov     rcx, rbx; hObject
0x180016471  call    cs:__imp_CloseHandle
0x180016477  lea     rcx, [rbp+var_20]; this
0x18001647b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180016480  mov     [rbp+TokenHandle], 0
0x180016488  call    cs:__imp_GetCurrentProcess
0x18001648e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180016492  mov     edx, 8; DesiredAccess
0x180016497  mov     rcx, rax; ProcessHandle
0x18001649a  call    cs:__imp_OpenProcessToken
0x1800164a0  test    eax, eax
0x1800164a2  jnz     short loc_1800164E2
0x1800164a4  mov     rcx, [rbp+18h]; this
0x1800164a8  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x1800164af  mov     edx, 15Fh; void *
0x1800164b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800164b9  jmp     short loc_1800164DB
0x1800164bb  test    eax, eax
0x1800164bd  jz      loc_1800165A3
0x1800164c3  mov     rcx, [rbp+18h]; this
0x1800164c7  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x1800164ce  mov     r9d, eax; char *
0x1800164d1  mov     edx, 163h; void *
0x1800164d6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800164db  mov     ebx, eax
0x1800164dd  jmp     loc_1800165A5
0x1800164e2  lea     rcx, [rbp+var_18]
0x1800164e6  mov     [rbp+var_18], 0
0x1800164ee  mov     [rbp+var_10], 0
0x1800164f6  mov     [rbp+var_8], 0
0x1800164fe  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180016503  mov     rcx, [rbp+TokenHandle]; void *
0x180016507  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18001650b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001650f  mov     rdx, rdi; unsigned __int16 *
0x180016512  mov     [rbp+var_10], rax
0x180016516  mov     [rbp+var_8], rax
0x18001651a  call    ?_GetAppContainerPath@@YAJPEAXPEBGPEAPEAG@Z; _GetAppContainerPath(void *,ushort const *,ushort * *)
0x18001651f  mov     ebx, eax
0x180016521  cmp     eax, 80070013h
0x180016526  jnz     short loc_180016533
0x180016528  lea     rcx, [rbp+var_18]
0x18001652c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180016531  jmp     short loc_1800165A5
0x180016533  test    ebx, ebx
0x180016535  jns     short loc_18001656B
0x180016537  mov     rcx, [rbp+18h]; this
0x18001653b  lea     rax, aGetappcontaine_2; "_GetAppContainerPath %ws"
0x180016542  mov     [rsp+50h+var_28], rdi; char *
0x180016547  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x18001654e  mov     r9d, ebx; char *
0x180016551  mov     qword ptr [rsp+50h+var_30], rax; int
0x180016556  mov     edx, 16Ah; void *
0x18001655b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180016560  lea     rcx, [rbp+var_18]
0x180016564  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180016569  jmp     short loc_1800165A5
0x18001656b  mov     r8, [rbp+var_18]; unsigned __int16 *
0x18001656f  mov     rdx, rsi; unsigned __int64
0x180016572  mov     rcx, r14; unsigned __int16 *
0x180016575  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001657a  mov     ebx, eax
0x18001657c  test    eax, eax
0x18001657e  jns     short loc_18001659A
0x180016580  mov     rcx, [rbp+18h]; this
0x180016584  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x18001658b  mov     r9d, eax; char *
0x18001658e  mov     edx, 16Bh; void *
0x180016593  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016598  jmp     short loc_180016560
0x18001659a  lea     rcx, [rbp+var_18]
0x18001659e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800165a3  xor     ebx, ebx
0x1800165a5  lea     rcx, [rbp+TokenHandle]
0x1800165a9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800165ae  mov     rsi, [rsp+50h+arg_8]
0x1800165b3  mov     eax, ebx
0x1800165b5  mov     rbx, [rsp+50h+arg_0]
0x1800165ba  add     rsp, 50h
0x1800165be  pop     r14
0x1800165c0  pop     rdi
0x1800165c1  pop     rbp
0x1800165c2  retn
```
