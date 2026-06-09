# helium::AddProcessToContainer(void *,void *,ushort const *)

- ea: `0x180051eb8`
- end: `0x1800521b2`
- name: `?AddProcessToContainer@helium@@YA_NPEAX0PEBG@Z`
- size: `762`
- prototype: `bool __fastcall(helium *__hidden this, HANDLE hJob, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800521b8`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x180011820`
- `0x180013100`
- `0x1800148e8`
- `0x180014f4c`
- `0x18001748c`
- `0x18001ec94`
- `0x180020338`
- `0x180048f40`
- `0x1800518a0`
- `0x180051904`
- `0x180051eb8`
- `0x180052aa0`
- `0x1800535b4`
- `0x1800af978`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051f4b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180051f6c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18005205b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180051f6c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18005205b`
- `ntdll!EtwEventUnregister` at `0x1800520d3`
- `ntdll!EtwEventUnregister` at `0x1800520d3`
- `ntdll!EtwEventWrite` at `0x1800520c2`
- `ntdll!EtwEventWrite` at `0x1800520c2`
- `ntdll!EtwEventRegister` at `0x18005209b`
- `ntdll!EtwEventRegister` at `0x18005209b`
- `ntdll!NtQueryInformationProcess` at `0x180052022`
- `ntdll!NtQueryInformationProcess` at `0x180052022`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x180051f37`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x180051f37`

## string_xrefs

- `0x1800520ed`: `onecore\base\appmodel\execmodel\desktopappx\lib\ManifestedETWHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall helium::AddProcessToContainer(helium *this, HANDLE hJob, void *a3, const unsigned __int16 *a4)
{
  const unsigned __int16 *v6; // rbx
  __int64 v7; // r8
  __int64 v8; // r9
  signed int LastError; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rsi
  unsigned int v13; // ecx
  NTSTATUS InformationProcess; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 ContainerIdStringSafe; // rbx
  unsigned int v19; // eax
  unsigned int ReturnLength; // [rsp+20h] [rbp-E0h]
  unsigned int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  DWORD ProcessId; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  void *v24; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v25[4]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v26[40]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v27[42]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD ProcessInformation[7]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v29; // [rsp+218h] [rbp+118h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v24 = a3;
  helium::GetContainerIdStringSafe(v25, hJob, a3, a4);
  v6 = (const unsigned __int16 *)v25;
  if ( v25[3] > (unsigned __int16 *)7 )
    v6 = v25[0];
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v27,
    "AddProcessToContainer");
  v27[0] = &DesktopAppXProvider::AddProcessToContainer::`vftable';
  DesktopAppXProvider::AddProcessToContainer::StartActivity((DesktopAppXProvider::AddProcessToContainer *)v27, this, v6);
  if ( AssignProcessToJobObject(hJob, this) )
  {
    ContainerIdStringSafe = helium::GetContainerIdStringSafe(v26, hJob, v7, v8);
    ProcessId = GetProcessId(this);
    EtwLogging::details::CreateEventDataDescriptors<unsigned long,unsigned short const * &,std::wstring>(
      ProcessInformation,
      &ProcessId,
      &v24,
      ContainerIdStringSafe);
    v23 = 0;
    if ( !(unsigned int)EtwEventRegister(&AppModelRuntimeProviderId, 0, 0, &v23) )
    {
      EtwEventWrite(v23, &AppModelDesktopAppXContainerAddProcessSuccess, 3, ProcessInformation);
      v19 = EtwEventUnregister(v23);
      if ( v19 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x64,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\ManifestedETWHelpers.h",
          (const char *)v19,
          ReturnLength);
    }
    std::wstring::~wstring(v26);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v27, 0);
    v27[0] = &DesktopAppXProvider::AddProcessToContainer::`vftable';
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v27);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v27);
    std::wstring::~wstring(v25);
    return 1;
  }
  else
  {
    LastError = GetLastError();
    v12 = helium::GetContainerIdStringSafe(v26, hJob, v10, v11);
    LODWORD(v23) = GetProcessId(this);
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    else
      v13 = LastError;
    ProcessId = v13;
    LogAppModelRuntimeEvent<long,unsigned long,unsigned short const * &,std::wstring>(
      v13,
      (unsigned int)&ProcessId,
      (unsigned int)&v23,
      (unsigned int)&v24,
      v12);
    std::wstring::~wstring(v26);
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
            ReturnLengtha);
        if ( (v29 & 4) != 0 )
          wil::details::in1diag3::Throw_NtStatus(
            retaddr,
            (void *)0x185,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\helium.cpp",
            (const char *)0xC000010ALL,
            ReturnLengtha);
        MicrosoftTelemetryAssertTriggeredNoArgs(v17, v16);
      }
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x18D,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\helium.cpp",
        (const char *)(unsigned int)LastError,
        ReturnLengtha);
    }
    v27[0] = &DesktopAppXProvider::AddProcessToContainer::`vftable';
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v27);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v27);
    std::wstring::~wstring(v25);
    return 0;
  }
}

```

## disassembly

```asm
0x180051eb8  push    rbp
0x180051eba  push    rbx
0x180051ebb  push    rsi
0x180051ebc  push    rdi
0x180051ebd  push    r14
0x180051ebf  lea     rbp, [rsp-130h]
0x180051ec7  sub     rsp, 230h
0x180051ece  mov     rax, cs:__security_cookie
0x180051ed5  xor     rax, rsp
0x180051ed8  mov     [rbp+150h+var_30], rax
0x180051edf  mov     rsi, rdx
0x180051ee2  mov     rdi, rcx
0x180051ee5  mov     [rsp+250h+var_210], r8
0x180051eea  lea     rcx, [rsp+250h+var_208]
0x180051eef  call    ?GetContainerIdStringSafe@helium@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; helium::GetContainerIdStringSafe(void *)
0x180051ef4  nop
0x180051ef5  lea     rbx, [rsp+250h+var_208]
0x180051efa  cmp     [rsp+250h+var_1F0], 7
0x180051f00  cmova   rbx, [rsp+250h+var_208]
0x180051f06  lea     rdx, aAddprocesstoco; "AddProcessToContainer"
0x180051f0d  lea     rcx, [rbp+150h+var_1C0]
0x180051f11  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180051f16  lea     r14, ??_7AddProcessToContainer@DesktopAppXProvider@@6B@; const DesktopAppXProvider::AddProcessToContainer::`vftable'
0x180051f1d  mov     [rbp+150h+var_1C0], r14
0x180051f21  mov     r8, rbx; unsigned __int16 *
0x180051f24  mov     rdx, rdi; void *
0x180051f27  lea     rcx, [rbp+150h+var_1C0]; this
0x180051f2b  call    ?StartActivity@AddProcessToContainer@DesktopAppXProvider@@QEAAXPEAXPEBG@Z; DesktopAppXProvider::AddProcessToContainer::StartActivity(void *,ushort const *)
0x180051f30  nop
0x180051f31  mov     rdx, rdi; hProcess
0x180051f34  mov     rcx, rsi; hJob
0x180051f37  call    cs:__imp_AssignProcessToJobObject
0x180051f3e  nop     dword ptr [rax+rax+00h]
0x180051f43  test    eax, eax
0x180051f45  jnz     loc_180052048
0x180051f4b  call    cs:__imp_GetLastError
0x180051f52  nop     dword ptr [rax+rax+00h]
0x180051f57  mov     ebx, eax
0x180051f59  mov     rdx, rsi
0x180051f5c  lea     rcx, [rsp+250h+var_1E8]
0x180051f61  call    ?GetContainerIdStringSafe@helium@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; helium::GetContainerIdStringSafe(void *)
0x180051f66  mov     rsi, rax
0x180051f69  mov     rcx, rdi; Process
0x180051f6c  call    cs:__imp_GetProcessId
0x180051f73  nop     dword ptr [rax+rax+00h]
0x180051f78  mov     dword ptr [rsp+250h+var_218], eax
0x180051f7c  test    ebx, ebx
0x180051f7e  jg      short loc_180051F84
0x180051f80  mov     ecx, ebx
0x180051f82  jmp     short loc_180051F8D
0x180051f84  movzx   ecx, bx
0x180051f87  or      ecx, 80070000h
0x180051f8d  mov     [rsp+250h+var_220], ecx
0x180051f91  mov     qword ptr [rsp+250h+ReturnLength], rsi; int
0x180051f96  lea     r9, [rsp+250h+var_210]
0x180051f9b  lea     r8, [rsp+250h+var_218]
0x180051fa0  lea     rdx, [rsp+250h+var_220]
0x180051fa5  call    ??$LogAppModelRuntimeEvent@JKAEAPEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@YAXAEBU_EVENT_DESCRIPTOR@@$$QEAJ$$QEAKAEAPEBG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LogAppModelRuntimeEvent<long,ulong,ushort const * &,std::wstring>(_EVENT_DESCRIPTOR const &,long &&,ulong &&,ushort const * &,std::wstring &&)
0x180051faa  lea     rcx, [rsp+250h+var_1E8]; void *
0x180051faf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051fb4  cmp     ebx, 45Bh
0x180051fba  jnz     short loc_180051FE4
0x180051fbc  mov     [rbp+150h+var_1C0], r14
0x180051fc0  lea     rcx, [rbp+150h+var_1C0]
0x180051fc4  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180051fc9  lea     rcx, [rbp+150h+var_1C0]
0x180051fcd  call    ??1?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180051fd2  nop
0x180051fd3  lea     rcx, [rsp+250h+var_208]; void *
0x180051fd8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051fdd  xor     al, al
0x180051fdf  jmp     loc_180052137
0x180051fe4  cmp     ebx, 80070005h
0x180051fea  jnz     loc_18005215B
0x180051ff0  mov     esi, 40h ; '@'
0x180051ff5  mov     r8d, esi; Size
0x180051ff8  xor     edx, edx; Val
0x180051ffa  lea     rcx, [rbp+150h+ProcessInformation]; void *
0x180052001  call    memset_0
0x180052006  mov     [rbp+150h+ProcessInformation], rsi
0x18005200d  and     qword ptr [rsp+250h+ReturnLength], 0
0x180052013  mov     r9d, esi; ProcessInformationLength
0x180052016  lea     r8, [rbp+150h+ProcessInformation]; ProcessInformation
0x18005201d  xor     edx, edx; ProcessInformationClass
0x18005201f  mov     rcx, rdi; ProcessHandle
0x180052022  call    cs:__imp_NtQueryInformationProcess
0x180052029  nop     dword ptr [rax+rax+00h]
0x18005202e  test    eax, eax
0x180052030  js      loc_180052196
0x180052036  test    [rbp+150h+var_38], 4
0x18005203d  jnz     loc_180052177
0x180052043  jmp     loc_180052155
0x180052048  mov     rdx, rsi
0x18005204b  lea     rcx, [rsp+250h+var_1E8]
0x180052050  call    ?GetContainerIdStringSafe@helium@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; helium::GetContainerIdStringSafe(void *)
0x180052055  mov     rbx, rax
0x180052058  mov     rcx, rdi; Process
0x18005205b  call    cs:__imp_GetProcessId
0x180052062  nop     dword ptr [rax+rax+00h]
0x180052067  mov     [rsp+250h+var_220], eax
0x18005206b  mov     r9, rbx
0x18005206e  lea     r8, [rsp+250h+var_210]
0x180052073  lea     rdx, [rsp+250h+var_220]
0x180052078  lea     rcx, [rbp+150h+ProcessInformation]
0x18005207f  call    ??$CreateEventDataDescriptors@KAEAPEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@EtwLogging@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@$$QEAKAEAPEBG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; EtwLogging::details::CreateEventDataDescriptors<ulong,ushort const * &,std::wstring>(_EVENT_DATA_DESCRIPTOR *,ulong &&,ushort const * &,std::wstring &&)
0x180052084  and     [rsp+250h+var_218], 0
0x18005208a  lea     r9, [rsp+250h+var_218]
0x18005208f  xor     r8d, r8d
0x180052092  xor     edx, edx
0x180052094  lea     rcx, AppModelRuntimeProviderId
0x18005209b  call    cs:__imp_EtwEventRegister
0x1800520a2  nop     dword ptr [rax+rax+00h]
0x1800520a7  test    eax, eax
0x1800520a9  jnz     short loc_1800520FE
0x1800520ab  lea     r9, [rbp+150h+ProcessInformation]
0x1800520b2  lea     r8d, [rax+3]
0x1800520b6  lea     rdx, AppModelDesktopAppXContainerAddProcessSuccess
0x1800520bd  mov     rcx, [rsp+250h+var_218]
0x1800520c2  call    cs:__imp_EtwEventWrite
0x1800520c9  nop     dword ptr [rax+rax+00h]
0x1800520ce  mov     rcx, [rsp+250h+var_218]
0x1800520d3  call    cs:__imp_EtwEventUnregister
0x1800520da  nop     dword ptr [rax+rax+00h]
0x1800520df  mov     rcx, [rbp+158h]; this
0x1800520e6  test    eax, eax
0x1800520e8  jz      short loc_1800520FE
0x1800520ea  mov     r9d, eax; char *
0x1800520ed  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800520f4  mov     edx, 64h ; 'd'; void *
0x1800520f9  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800520fe  lea     rcx, [rsp+250h+var_1E8]; void *
0x180052103  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052108  xor     edx, edx
0x18005210a  lea     rcx, [rbp+150h+var_1C0]
0x18005210e  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180052113  nop
0x180052114  mov     [rbp+150h+var_1C0], r14
0x180052118  lea     rcx, [rbp+150h+var_1C0]
0x18005211c  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180052121  lea     rcx, [rbp+150h+var_1C0]
0x180052125  call    ??1?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18005212a  nop
0x18005212b  lea     rcx, [rsp+250h+var_208]; void *
0x180052130  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052135  mov     al, 1
0x180052137  mov     rcx, [rbp+150h+var_30]
0x18005213e  xor     rcx, rsp; StackCookie
0x180052141  call    __security_check_cookie
0x180052146  add     rsp, 230h
0x18005214d  pop     r14
0x18005214f  pop     rdi
0x180052150  pop     rsi
0x180052151  pop     rbx
0x180052152  pop     rbp
0x180052153  retn
0x180052155  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false")
0x18005215a  nop
0x18005215b  mov     rcx, [rbp+158h]; this
0x180052162  mov     r9d, ebx; char *
0x180052165  lea     r8, aOnecoreBaseApp_54; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005216c  mov     edx, 18Dh; void *
0x180052171  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180052177  mov     rcx, [rbp+158h]; this
0x18005217e  mov     r9d, 0C000010Ah; char *
0x180052184  lea     r8, aOnecoreBaseApp_54; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005218b  mov     edx, 185h; void *
0x180052190  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180052196  mov     rcx, [rbp+158h]; this
0x18005219d  mov     r9d, eax; char *
0x1800521a0  lea     r8, aOnecoreBaseApp_54; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800521a7  mov     edx, 17Fh; void *
0x1800521ac  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
