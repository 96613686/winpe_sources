# MdmLogCollector::UpdateWifiEtl(ushort *,ushort const *)

- ea: `0x1801107fc`
- end: `0x18011096d`
- name: `?UpdateWifiEtl@MdmLogCollector@@AEAAJPEAGPEBG@Z`
- size: `369`
- prototype: `int(MdmLogCollector *__hidden this, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18010de78`

## callees

- `0x180019fc4`
- `0x1800ece3c`
- `0x1800f9534`
- `0x1801043d4`
- `0x1801089c0`
- `0x1801107fc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180110869`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180110869`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180110931`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180110931`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180110900`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180110900`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011093b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180110945`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011093b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180110945`

## string_xrefs

- `0x180110913`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
__int64 __fastcall MdmLogCollector::UpdateWifiEtl(
        MdmLogCollector *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HANDLE v5; // rax
  const char *v6; // r9
  void *v7; // rbx
  __int64 v8; // rdx
  unsigned int LastError; // ebx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-49h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-31h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  void *v15; // [rsp+100h] [rbp+67h] BYREF

  MdmLogCollector::AddEntry(a3, (char *)this + 32);
  *(_OWORD *)&SecurityAttributes.nLength = 0;
  *(&SecurityAttributes.bInheritHandle + 1) = 0;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 1;
  v15 = 0;
  v5 = CreateFileW(a3, 0x40000000u, 3u, &SecurityAttributes, 2u, 0x80u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v15,
    v5);
  v7 = v15;
  if ( v15 == (void *)-1LL )
  {
    v8 = 1963;
LABEL_5:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                  v6);
    goto LABEL_9;
  }
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 256;
  StartupInfo.hStdOutput = v7;
  StartupInfo.hStdError = v7;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessW(0, a2, 0, 0, 1, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    v8 = 1984;
    goto LABEL_5;
  }
  if ( ProcessInformation.hProcess )
  {
    WaitForSingleObject(ProcessInformation.hProcess, 0x1D4C0u);
    CloseHandle(ProcessInformation.hProcess);
    CloseHandle(ProcessInformation.hThread);
  }
  LastError = 0;
LABEL_9:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
  return LastError;
}

```

## disassembly

```asm
0x1801107fc  mov     [rsp-8+arg_8], rbx
0x180110801  mov     [rsp-8+arg_10], rdi
0x180110806  push    rbp
0x180110807  lea     rbp, [rsp-57h]
0x18011080c  sub     rsp, 0F0h
0x180110813  mov     rdi, rdx
0x180110816  mov     rbx, r8
0x180110819  lea     rdx, [rcx+20h]
0x18011081d  mov     rcx, r8
0x180110820  call    ?AddEntry@MdmLogCollector@@CAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmLogCollector::AddEntry(ushort const *,std::vector<std::wstring> &)
0x180110825  xor     eax, eax
0x180110827  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18011082b  mov     [rsp+0F0h+hTemplateFile], rax; hTemplateFile
0x180110830  xorps   xmm0, xmm0
0x180110833  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x180110837  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x18011083b  mov     edx, 40000000h; dwDesiredAccess
0x180110840  lea     r8d, [rax+3]; dwShareMode
0x180110844  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18011084c  mov     rcx, rbx; lpFileName
0x18011084f  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x180110856  mov     [rbp+57h+SecurityAttributes.bInheritHandle], 1
0x18011085d  mov     [rbp+57h+arg_0], rax
0x180110861  mov     [rsp+0F0h+dwCreationDisposition], 2; dwCreationDisposition
0x180110869  call    cs:__imp_CreateFileW
0x18011086f  mov     rdx, rax
0x180110872  lea     rcx, [rbp+57h+arg_0]
0x180110876  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18011087b  mov     rbx, [rbp+57h+arg_0]
0x18011087f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180110883  jnz     short loc_18011088F
0x180110885  mov     edx, 7ABh
0x18011088a  jmp     loc_18011090F
0x18011088f  xor     edx, edx; Val
0x180110891  lea     rcx, [rbp+57h+StartupInfo]; void *
0x180110895  lea     r8d, [rdx+68h]; Size
0x180110899  call    memset_0
0x18011089e  xor     eax, eax
0x1801108a0  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x1801108a7  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x1801108ab  xorps   xmm0, xmm0
0x1801108ae  lea     rax, [rbp+57h+ProcessInformation]
0x1801108b2  mov     [rbp+57h+StartupInfo.dwFlags], 100h
0x1801108b9  mov     [rsp+0F0h+lpProcessInformation], rax; lpProcessInformation
0x1801108be  xor     r9d, r9d; lpThreadAttributes
0x1801108c1  lea     rax, [rbp+57h+StartupInfo]
0x1801108c5  mov     [rbp+57h+StartupInfo.hStdOutput], rbx
0x1801108c9  mov     [rsp+0F0h+lpStartupInfo], rax; lpStartupInfo
0x1801108ce  xor     r8d, r8d; lpProcessAttributes
0x1801108d1  mov     [rsp+0F0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1801108da  mov     rdx, rdi; lpCommandLine
0x1801108dd  mov     [rsp+0F0h+hTemplateFile], 0; lpEnvironment
0x1801108e6  xor     ecx, ecx; lpApplicationName
0x1801108e8  mov     [rsp+0F0h+dwFlagsAndAttributes], 8000000h; dwCreationFlags
0x1801108f0  mov     [rsp+0F0h+dwCreationDisposition], 1; bInheritHandles
0x1801108f8  mov     [rbp+57h+StartupInfo.hStdError], rbx
0x1801108fc  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x180110900  call    cs:__imp_CreateProcessW
0x180110906  test    eax, eax
0x180110908  jnz     short loc_180110923
0x18011090a  mov     edx, 7C0h; void *
0x18011090f  mov     rcx, [rbp+5Fh]; this
0x180110913  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011091a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18011091f  mov     ebx, eax
0x180110921  jmp     short loc_18011094D
0x180110923  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hHandle
0x180110927  test    rcx, rcx
0x18011092a  jz      short loc_18011094B
0x18011092c  mov     edx, 1D4C0h; dwMilliseconds
0x180110931  call    cs:__imp_WaitForSingleObject
0x180110937  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18011093b  call    cs:__imp_CloseHandle
0x180110941  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x180110945  call    cs:__imp_CloseHandle
0x18011094b  xor     ebx, ebx
0x18011094d  lea     rcx, [rbp+57h+arg_0]
0x180110951  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180110956  lea     r11, [rsp+0F0h+var_s0]
0x18011095e  mov     eax, ebx
0x180110960  mov     rbx, [r11+18h]
0x180110964  mov     rdi, [r11+20h]
0x180110968  mov     rsp, r11
0x18011096b  pop     rbp
0x18011096c  retn
```
