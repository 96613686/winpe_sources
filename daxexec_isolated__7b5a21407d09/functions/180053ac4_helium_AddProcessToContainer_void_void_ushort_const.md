# helium::AddProcessToContainer(void *,void *,ushort const *)

- ea: `0x180053ac4`
- end: `0x180053d37`
- name: `?AddProcessToContainer@helium@@YA_NPEAX0PEBG@Z`
- size: `627`
- prototype: `char __fastcall(helium *this, HANDLE hJob, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180053d40`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x180013510`
- `0x180014e74`
- `0x1800164f8`
- `0x180016b98`
- `0x1800190e0`
- `0x18001f808`
- `0x180021118`
- `0x180053444`
- `0x180053520`
- `0x180053ac4`
- `0x180054540`
- `0x1800550c4`
- `0x1800b1b68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053b57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053b57`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180053b78`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180053c61`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180053b78`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180053c61`
- `ntdll!NtQueryInformationProcess` at `0x180053c2b`
- `ntdll!NtQueryInformationProcess` at `0x180053c2b`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x180053b43`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x180053b43`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall helium::AddProcessToContainer(helium *this, HANDLE hJob, void *a3, const unsigned __int16 *a4)
{
  const unsigned __int16 *v6; // rbx
  signed int LastError; // ebx
  __int64 v8; // rsi
  unsigned int v9; // ecx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  NTSTATUS InformationProcess; // eax
  __int64 v15; // rcx
  __int64 ContainerIdStringSafe; // rbx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned int ReturnLength; // [rsp+20h] [rbp-E0h]
  DWORD ProcessId; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v23; // [rsp+34h] [rbp-CCh] BYREF
  void *v24; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v25[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD ProcessInformation[7]; // [rsp+60h] [rbp-A0h] BYREF
  char v27; // [rsp+98h] [rbp-68h]
  _QWORD v28[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v24 = a3;
  helium::GetContainerIdStringSafe(v25, hJob);
  v6 = (const unsigned __int16 *)v25;
  if ( v25[3] > (unsigned __int16 *)7 )
    v6 = v25[0];
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v28,
    "AddProcessToContainer");
  v28[0] = &DesktopAppXProvider::AddProcessToContainer::`vftable';
  DesktopAppXProvider::AddProcessToContainer::StartActivity((DesktopAppXProvider::AddProcessToContainer *)v28, this, v6);
  if ( AssignProcessToJobObject(hJob, this) )
  {
    ContainerIdStringSafe = helium::GetContainerIdStringSafe(ProcessInformation, hJob);
    ProcessId = GetProcessId(this);
    LogAppModelRuntimeEvent<unsigned long,unsigned short const * &,std::wstring>(
      v17,
      &ProcessId,
      &v24,
      ContainerIdStringSafe);
    std::wstring::~wstring(ProcessInformation);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v28, 0);
    v28[0] = &DesktopAppXProvider::AddProcessToContainer::`vftable';
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v28, v18, v19, v20);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v28);
    std::wstring::~wstring(v25);
    return 1;
  }
  else
  {
    LastError = GetLastError();
    v8 = helium::GetContainerIdStringSafe(ProcessInformation, hJob);
    v23 = GetProcessId(this);
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    else
      v9 = LastError;
    ProcessId = v9;
    LogAppModelRuntimeEvent<long,unsigned long,unsigned short const * &,std::wstring>(
      v9,
      (unsigned int)&ProcessId,
      (unsigned int)&v23,
      (unsigned int)&v24,
      v8);
    std::wstring::~wstring(ProcessInformation);
    if ( LastError != 1115 )
    {
      if ( LastError == -2147024891 )
      {
        memset_0(ProcessInformation, 0, 0x40u);
        ProcessInformation[0] = 64;
        InformationProcess = NtQueryInformationProcess(this, ProcessBasicInformation, ProcessInformation, 0x40u, 0);
        if ( InformationProcess < 0 )
          wil::details::in1diag3::Throw_NtStatus(
            retaddr,
            (void *)0x17F,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\helium.cpp",
            (const char *)(unsigned int)InformationProcess,
            ReturnLength);
        if ( (v27 & 4) != 0 )
          wil::details::in1diag3::Throw_NtStatus(
            retaddr,
            (void *)0x185,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\helium.cpp",
            (const char *)0xC000010ALL,
            ReturnLength);
        MicrosoftTelemetryAssertTriggeredNoArgs(v15);
      }
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x18D,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\helium.cpp",
        (const char *)(unsigned int)LastError,
        ReturnLength);
    }
    v28[0] = &DesktopAppXProvider::AddProcessToContainer::`vftable';
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v28, v10, v11, v12);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v28);
    std::wstring::~wstring(v25);
    return 0;
  }
}

```

## disassembly

```asm
0x180053ac4  push    rbp
0x180053ac6  push    rbx
0x180053ac7  push    rsi
0x180053ac8  push    rdi
0x180053ac9  push    r14
0x180053acb  lea     rbp, [rsp-100h]
0x180053ad3  sub     rsp, 200h
0x180053ada  mov     rax, cs:__security_cookie
0x180053ae1  xor     rax, rsp
0x180053ae4  mov     [rbp+120h+var_30], rax
0x180053aeb  mov     rsi, rdx
0x180053aee  mov     rdi, rcx
0x180053af1  mov     [rsp+220h+var_1E8], r8
0x180053af6  lea     rcx, [rsp+220h+var_1E0]
0x180053afb  call    ?GetContainerIdStringSafe@helium@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; helium::GetContainerIdStringSafe(void *)
0x180053b00  nop
0x180053b01  lea     rbx, [rsp+220h+var_1E0]
0x180053b06  cmp     [rsp+220h+var_1C8], 7
0x180053b0c  cmova   rbx, [rsp+220h+var_1E0]
0x180053b12  lea     rdx, aAddprocesstoco; "AddProcessToContainer"
0x180053b19  lea     rcx, [rbp+120h+var_180]
0x180053b1d  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180053b22  lea     r14, ??_7AddProcessToContainer@DesktopAppXProvider@@6B@; const DesktopAppXProvider::AddProcessToContainer::`vftable'
0x180053b29  mov     [rbp+120h+var_180], r14
0x180053b2d  mov     r8, rbx; unsigned __int16 *
0x180053b30  mov     rdx, rdi; void *
0x180053b33  lea     rcx, [rbp+120h+var_180]; this
0x180053b37  call    ?StartActivity@AddProcessToContainer@DesktopAppXProvider@@QEAAXPEAXPEBG@Z; DesktopAppXProvider::AddProcessToContainer::StartActivity(void *,ushort const *)
0x180053b3c  nop
0x180053b3d  mov     rdx, rdi; hProcess
0x180053b40  mov     rcx, rsi; hJob
0x180053b43  call    cs:__imp_AssignProcessToJobObject
0x180053b4a  nop     dword ptr [rax+rax+00h]
0x180053b4f  test    eax, eax
0x180053b51  jnz     loc_180053C4E
0x180053b57  call    cs:__imp_GetLastError
0x180053b5e  nop     dword ptr [rax+rax+00h]
0x180053b63  mov     ebx, eax
0x180053b65  mov     rdx, rsi
0x180053b68  lea     rcx, [rsp+220h+ProcessInformation]
0x180053b6d  call    ?GetContainerIdStringSafe@helium@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; helium::GetContainerIdStringSafe(void *)
0x180053b72  mov     rsi, rax
0x180053b75  mov     rcx, rdi; Process
0x180053b78  call    cs:__imp_GetProcessId
0x180053b7f  nop     dword ptr [rax+rax+00h]
0x180053b84  mov     [rsp+220h+var_1EC], eax
0x180053b88  test    ebx, ebx
0x180053b8a  jg      short loc_180053B90
0x180053b8c  mov     ecx, ebx
0x180053b8e  jmp     short loc_180053B99
0x180053b90  movzx   ecx, bx
0x180053b93  or      ecx, 80070000h
0x180053b99  mov     [rsp+220h+var_1F0], ecx
0x180053b9d  mov     qword ptr [rsp+220h+ReturnLength], rsi
0x180053ba2  lea     r9, [rsp+220h+var_1E8]
0x180053ba7  lea     r8, [rsp+220h+var_1EC]
0x180053bac  lea     rdx, [rsp+220h+var_1F0]
0x180053bb1  call    ??$LogAppModelRuntimeEvent@JKAEAPEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@YAXAEBU_EVENT_DESCRIPTOR@@$$QEAJ$$QEAKAEAPEBG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LogAppModelRuntimeEvent<long,ulong,ushort const * &,std::wstring>(_EVENT_DESCRIPTOR const &,long &&,ulong &&,ushort const * &,std::wstring &&)
0x180053bb6  lea     rcx, [rsp+220h+ProcessInformation]; void *
0x180053bbb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180053bc0  cmp     ebx, 45Bh
0x180053bc6  jnz     short loc_180053BF0
0x180053bc8  mov     [rbp+120h+var_180], r14
0x180053bcc  lea     rcx, [rbp+120h+var_180]
0x180053bd0  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180053bd5  lea     rcx, [rbp+120h+var_180]
0x180053bd9  call    ??1?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180053bde  nop
0x180053bdf  lea     rcx, [rsp+220h+var_1E0]; void *
0x180053be4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180053be9  xor     al, al
0x180053beb  jmp     loc_180053CBC
0x180053bf0  cmp     ebx, 80070005h
0x180053bf6  jnz     loc_180053CE0
0x180053bfc  mov     esi, 40h ; '@'
0x180053c01  mov     r8d, esi; Size
0x180053c04  xor     edx, edx; Val
0x180053c06  lea     rcx, [rsp+220h+ProcessInformation]; void *
0x180053c0b  call    memset_0
0x180053c10  mov     [rsp+220h+ProcessInformation], rsi
0x180053c15  mov     qword ptr [rsp+220h+ReturnLength], 0; int
0x180053c1e  mov     r9d, esi; ProcessInformationLength
0x180053c21  lea     r8, [rsp+220h+ProcessInformation]; ProcessInformation
0x180053c26  xor     edx, edx; ProcessInformationClass
0x180053c28  mov     rcx, rdi; ProcessHandle
0x180053c2b  call    cs:__imp_NtQueryInformationProcess
0x180053c32  nop     dword ptr [rax+rax+00h]
0x180053c37  test    eax, eax
0x180053c39  js      loc_180053D1B
0x180053c3f  test    [rbp+120h+var_188], 4
0x180053c43  jnz     loc_180053CFC
0x180053c49  jmp     loc_180053CDA
0x180053c4e  mov     rdx, rsi
0x180053c51  lea     rcx, [rsp+220h+ProcessInformation]
0x180053c56  call    ?GetContainerIdStringSafe@helium@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; helium::GetContainerIdStringSafe(void *)
0x180053c5b  mov     rbx, rax
0x180053c5e  mov     rcx, rdi; Process
0x180053c61  call    cs:__imp_GetProcessId
0x180053c68  nop     dword ptr [rax+rax+00h]
0x180053c6d  mov     [rsp+220h+var_1F0], eax
0x180053c71  mov     r9, rbx
0x180053c74  lea     r8, [rsp+220h+var_1E8]
0x180053c79  lea     rdx, [rsp+220h+var_1F0]
0x180053c7e  call    ??$LogAppModelRuntimeEvent@KAEAPEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@YAXAEBU_EVENT_DESCRIPTOR@@$$QEAKAEAPEBG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LogAppModelRuntimeEvent<ulong,ushort const * &,std::wstring>(_EVENT_DESCRIPTOR const &,ulong &&,ushort const * &,std::wstring &&)
0x180053c83  lea     rcx, [rsp+220h+ProcessInformation]; void *
0x180053c88  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180053c8d  xor     edx, edx
0x180053c8f  lea     rcx, [rbp+120h+var_180]
0x180053c93  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180053c98  nop
0x180053c99  mov     [rbp+120h+var_180], r14
0x180053c9d  lea     rcx, [rbp+120h+var_180]
0x180053ca1  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180053ca6  lea     rcx, [rbp+120h+var_180]
0x180053caa  call    ??1?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180053caf  nop
0x180053cb0  lea     rcx, [rsp+220h+var_1E0]; void *
0x180053cb5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180053cba  mov     al, 1
0x180053cbc  mov     rcx, [rbp+120h+var_30]
0x180053cc3  xor     rcx, rsp; StackCookie
0x180053cc6  call    __security_check_cookie
0x180053ccb  add     rsp, 200h
0x180053cd2  pop     r14
0x180053cd4  pop     rdi
0x180053cd5  pop     rsi
0x180053cd6  pop     rbx
0x180053cd7  pop     rbp
0x180053cd8  retn
0x180053cda  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false")
0x180053cdf  nop
0x180053ce0  mov     rcx, [rbp+128h]; this
0x180053ce7  mov     r9d, ebx; char *
0x180053cea  lea     r8, aOnecoreBaseApp_55; "onecore\\base\\appmodel\\execmodel\\des"...
0x180053cf1  mov     edx, 18Dh; void *
0x180053cf6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180053cfc  mov     rcx, [rbp+128h]; this
0x180053d03  mov     r9d, 0C000010Ah; char *
0x180053d09  lea     r8, aOnecoreBaseApp_55; "onecore\\base\\appmodel\\execmodel\\des"...
0x180053d10  mov     edx, 185h; void *
0x180053d15  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180053d1b  mov     rcx, [rbp+128h]; this
0x180053d22  mov     r9d, eax; char *
0x180053d25  lea     r8, aOnecoreBaseApp_55; "onecore\\base\\appmodel\\execmodel\\des"...
0x180053d2c  mov     edx, 17Fh; void *
0x180053d31  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
