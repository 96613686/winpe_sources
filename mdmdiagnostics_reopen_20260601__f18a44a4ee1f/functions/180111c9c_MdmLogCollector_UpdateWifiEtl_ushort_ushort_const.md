# MdmLogCollector::UpdateWifiEtl(ushort *,ushort const *)

- ea: `0x180111c9c`
- end: `0x180111e2c`
- name: `?UpdateWifiEtl@MdmLogCollector@@AEAAJPEAGPEBG@Z`
- size: `400`
- prototype: `int(MdmLogCollector *__hidden this, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18010f3c4`

## callees

- `0x18001a054`
- `0x1800ed44c`
- `0x1800fa50c`
- `0x1801055f4`
- `0x180109d50`
- `0x180111c9c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180111d09`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180111d09`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180111ddd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180111ddd`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180111da6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180111da6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180111ded`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180111dfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180111ded`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180111dfd`

## string_xrefs

- `0x180111dbf`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

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
    v8 = 1922;
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
    v8 = 1943;
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
0x180111c9c  mov     [rsp-8+arg_8], rbx
0x180111ca1  mov     [rsp-8+arg_10], rdi
0x180111ca6  push    rbp
0x180111ca7  lea     rbp, [rsp-57h]
0x180111cac  sub     rsp, 0F0h
0x180111cb3  mov     rdi, rdx
0x180111cb6  mov     rbx, r8
0x180111cb9  lea     rdx, [rcx+20h]
0x180111cbd  mov     rcx, r8
0x180111cc0  call    ?AddEntry@MdmLogCollector@@CAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmLogCollector::AddEntry(ushort const *,std::vector<std::wstring> &)
0x180111cc5  xor     eax, eax
0x180111cc7  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x180111ccb  mov     [rsp+0F0h+hTemplateFile], rax; hTemplateFile
0x180111cd0  xorps   xmm0, xmm0
0x180111cd3  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x180111cd7  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x180111cdb  mov     edx, 40000000h; dwDesiredAccess
0x180111ce0  lea     r8d, [rax+3]; dwShareMode
0x180111ce4  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180111cec  mov     rcx, rbx; lpFileName
0x180111cef  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x180111cf6  mov     [rbp+57h+SecurityAttributes.bInheritHandle], 1
0x180111cfd  mov     [rbp+57h+arg_0], rax
0x180111d01  mov     [rsp+0F0h+dwCreationDisposition], 2; dwCreationDisposition
0x180111d09  call    cs:__imp_CreateFileW
0x180111d10  nop     dword ptr [rax+rax+00h]
0x180111d15  mov     rdx, rax
0x180111d18  lea     rcx, [rbp+57h+arg_0]
0x180111d1c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180111d21  mov     rbx, [rbp+57h+arg_0]
0x180111d25  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180111d29  jnz     short loc_180111D35
0x180111d2b  mov     edx, 782h
0x180111d30  jmp     loc_180111DBB
0x180111d35  xor     edx, edx; Val
0x180111d37  lea     rcx, [rbp+57h+StartupInfo]; void *
0x180111d3b  lea     r8d, [rdx+68h]; Size
0x180111d3f  call    memset_0
0x180111d44  xor     eax, eax
0x180111d46  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x180111d4d  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x180111d51  xorps   xmm0, xmm0
0x180111d54  lea     rax, [rbp+57h+ProcessInformation]
0x180111d58  mov     [rbp+57h+StartupInfo.dwFlags], 100h
0x180111d5f  mov     [rsp+0F0h+lpProcessInformation], rax; lpProcessInformation
0x180111d64  xor     r9d, r9d; lpThreadAttributes
0x180111d67  lea     rax, [rbp+57h+StartupInfo]
0x180111d6b  mov     [rbp+57h+StartupInfo.hStdOutput], rbx
0x180111d6f  mov     [rsp+0F0h+lpStartupInfo], rax; lpStartupInfo
0x180111d74  xor     r8d, r8d; lpProcessAttributes
0x180111d77  mov     [rsp+0F0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180111d80  mov     rdx, rdi; lpCommandLine
0x180111d83  mov     [rsp+0F0h+hTemplateFile], 0; lpEnvironment
0x180111d8c  xor     ecx, ecx; lpApplicationName
0x180111d8e  mov     [rsp+0F0h+dwFlagsAndAttributes], 8000000h; dwCreationFlags
0x180111d96  mov     [rsp+0F0h+dwCreationDisposition], 1; bInheritHandles
0x180111d9e  mov     [rbp+57h+StartupInfo.hStdError], rbx
0x180111da2  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x180111da6  call    cs:__imp_CreateProcessW
0x180111dad  nop     dword ptr [rax+rax+00h]
0x180111db2  test    eax, eax
0x180111db4  jnz     short loc_180111DCF
0x180111db6  mov     edx, 797h; void *
0x180111dbb  mov     rcx, [rbp+5Fh]; this
0x180111dbf  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180111dc6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180111dcb  mov     ebx, eax
0x180111dcd  jmp     short loc_180111E0B
0x180111dcf  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hHandle
0x180111dd3  test    rcx, rcx
0x180111dd6  jz      short loc_180111E09
0x180111dd8  mov     edx, 1D4C0h; dwMilliseconds
0x180111ddd  call    cs:__imp_WaitForSingleObject
0x180111de4  nop     dword ptr [rax+rax+00h]
0x180111de9  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x180111ded  call    cs:__imp_CloseHandle
0x180111df4  nop     dword ptr [rax+rax+00h]
0x180111df9  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x180111dfd  call    cs:__imp_CloseHandle
0x180111e04  nop     dword ptr [rax+rax+00h]
0x180111e09  xor     ebx, ebx
0x180111e0b  lea     rcx, [rbp+57h+arg_0]
0x180111e0f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180111e14  lea     r11, [rsp+0F0h+var_s0]
0x180111e1c  mov     eax, ebx
0x180111e1e  mov     rbx, [r11+18h]
0x180111e22  mov     rdi, [r11+20h]
0x180111e26  mov     rsp, r11
0x180111e29  pop     rbp
0x180111e2a  retn
```
