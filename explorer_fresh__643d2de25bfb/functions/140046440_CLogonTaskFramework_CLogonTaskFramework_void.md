# CLogonTaskFramework::CLogonTaskFramework(void)

- ea: `0x140046440`
- end: `0x140046745`
- name: `??0CLogonTaskFramework@@QEAA@XZ`
- size: `773`
- prototype: `CLogonTaskFramework *__fastcall(CLogonTaskFramework *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140046398`

## callees

- `0x140029b80`
- `0x140045e9c`
- `0x140046440`
- `0x1400ada84`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400464a9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400464d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400464f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140046516`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140046538`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004655a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400464a9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400464d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400464f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140046516`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140046538`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004655a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14004648b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14004648b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400466d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400466d5`

## string_xrefs

- `0x140046508`: `AppResolverReadyEvent`
- `0x140046497`: `ShellLauncherReadyEvent`
- `0x14004652a`: `SignInSuggestionsReadyEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CLogonTaskFramework *__fastcall CLogonTaskFramework::CLogonTaskFramework(CLogonTaskFramework *this)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>();
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILogonFramework>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &CLogonTaskFramework::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  InitializeSRWLock((PSRWLOCK)this + 4);
  *((_QWORD *)this + 6) = CreateEventW(0, 1, 0, L"ShellLauncherReadyEvent");
  *((_QWORD *)this + 5) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  *((_QWORD *)this + 8) = CreateEventW(0, 1, 0, L"Local\\ShellStartupEvent");
  *((_QWORD *)this + 7) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  *((_QWORD *)this + 10) = CreateEventW(0, 1, 0, L"BINotifiedNewSessionEvent");
  *((_QWORD *)this + 9) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  *((_QWORD *)this + 12) = CreateEventW(0, 1, 0, L"AppResolverReadyEvent");
  *((_QWORD *)this + 11) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  *((_QWORD *)this + 14) = CreateEventW(0, 1, 0, L"SignInSuggestionsReadyEvent");
  *((_QWORD *)this + 13) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  *((_QWORD *)this + 16) = CreateEventW(0, 1, 0, L"SignInSuggestionsCallbackEvent");
  *((_QWORD *)this + 15) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  LogonFrameworkSyncHelper::LogonFrameworkSyncHelper((CLogonTaskFramework *)((char *)this + 176));
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_BYTE *)this + 240) = 0;
  *((_WORD *)this + 121) = 0;
  *(_WORD *)((char *)this + 245) = 0;
  *((_DWORD *)this + 62) = 420000;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_BYTE *)this + 272) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 72) = 10000;
  *((_WORD *)this + 146) = 0;
  *((_DWORD *)this + 74) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_BYTE *)this + 312) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 60) = 0;
  *((_QWORD *)this + 61) = 0;
  *((_OWORD *)this + 31) = 0;
  *((_OWORD *)this + 32) = 0;
  *((_QWORD *)this + 67) = 0;
  *((_QWORD *)this + 68) = 1;
  *((_DWORD *)this + 138) = GetTickCount();
  *(_QWORD *)((char *)this + 556) = 0;
  *((_QWORD *)this + 71) = 0;
  *((_QWORD *)this + 72) = 0;
  *((_WORD *)this + 292) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 77) = 0;
  wil::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>((CLogonTaskFramework *)((char *)this + 624));
  *((_QWORD *)this + 78) = &LogonFrameworkTelemetry::AllLogonTasks::`vftable';
  return this;
}

```

## disassembly

```asm
0x140046440  push    rbx
0x140046442  push    rbp
0x140046443  push    rsi
0x140046444  push    rdi
0x140046445  sub     rsp, 28h
0x140046449  mov     rdi, rcx
0x14004644c  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIImmersiveApplication@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>(void)
0x140046451  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UILogonFramework@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILogonFramework>::`vftable'
0x140046458  mov     [rdi], rcx
0x14004645b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140046462  xor     ebp, ebp
0x140046464  test    rcx, rcx
0x140046467  jz      short loc_140046476
0x140046469  mov     rax, [rcx]
0x14004646c  mov     rax, [rax+8]
0x140046470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046475  nop
0x140046476  lea     rax, ??_7CLogonTaskFramework@@6B@; const CLogonTaskFramework::`vftable'
0x14004647d  mov     [rdi], rax
0x140046480  mov     [rdi+10h], rbp
0x140046484  mov     [rdi+18h], ebp
0x140046487  lea     rcx, [rdi+20h]; SRWLock
0x14004648b  call    cs:__imp_InitializeSRWLock
0x140046492  nop     dword ptr [rax+rax+00h]
0x140046497  lea     r9, aShelllauncherr; "ShellLauncherReadyEvent"
0x14004649e  xor     r8d, r8d; bInitialState
0x1400464a1  lea     esi, [r8+1]
0x1400464a5  mov     edx, esi; bManualReset
0x1400464a7  xor     ecx, ecx; lpEventAttributes
0x1400464a9  call    cs:__imp_CreateEventW
0x1400464b0  nop     dword ptr [rax+rax+00h]
0x1400464b5  mov     [rdi+30h], rax
0x1400464b9  lea     rbx, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1400464c0  mov     [rdi+28h], rbx
0x1400464c4  lea     r9, aLocalShellstar; "Local\\ShellStartupEvent"
0x1400464cb  xor     r8d, r8d; bInitialState
0x1400464ce  mov     edx, esi; bManualReset
0x1400464d0  xor     ecx, ecx; lpEventAttributes
0x1400464d2  call    cs:__imp_CreateEventW
0x1400464d9  nop     dword ptr [rax+rax+00h]
0x1400464de  mov     [rdi+40h], rax
0x1400464e2  mov     [rdi+38h], rbx
0x1400464e6  lea     r9, aBinotifiednews; "BINotifiedNewSessionEvent"
0x1400464ed  xor     r8d, r8d; bInitialState
0x1400464f0  mov     edx, esi; bManualReset
0x1400464f2  xor     ecx, ecx; lpEventAttributes
0x1400464f4  call    cs:__imp_CreateEventW
0x1400464fb  nop     dword ptr [rax+rax+00h]
0x140046500  mov     [rdi+50h], rax
0x140046504  mov     [rdi+48h], rbx
0x140046508  lea     r9, aAppresolverrea; "AppResolverReadyEvent"
0x14004650f  xor     r8d, r8d; bInitialState
0x140046512  mov     edx, esi; bManualReset
0x140046514  xor     ecx, ecx; lpEventAttributes
0x140046516  call    cs:__imp_CreateEventW
0x14004651d  nop     dword ptr [rax+rax+00h]
0x140046522  mov     [rdi+60h], rax
0x140046526  mov     [rdi+58h], rbx
0x14004652a  lea     r9, aSigninsuggesti_2; "SignInSuggestionsReadyEvent"
0x140046531  xor     r8d, r8d; bInitialState
0x140046534  mov     edx, esi; bManualReset
0x140046536  xor     ecx, ecx; lpEventAttributes
0x140046538  call    cs:__imp_CreateEventW
0x14004653f  nop     dword ptr [rax+rax+00h]
0x140046544  mov     [rdi+70h], rax
0x140046548  mov     [rdi+68h], rbx
0x14004654c  lea     r9, aSigninsuggesti; "SignInSuggestionsCallbackEvent"
0x140046553  xor     r8d, r8d; bInitialState
0x140046556  mov     edx, esi; bManualReset
0x140046558  xor     ecx, ecx; lpEventAttributes
0x14004655a  call    cs:__imp_CreateEventW
0x140046561  nop     dword ptr [rax+rax+00h]
0x140046566  mov     [rdi+80h], rax
0x14004656d  mov     [rdi+78h], rbx
0x140046571  mov     [rdi+88h], rbp
0x140046578  mov     [rdi+90h], rbp
0x14004657f  mov     [rdi+98h], rbp
0x140046586  mov     [rdi+0A0h], rbp
0x14004658d  mov     [rdi+0A8h], rbp
0x140046594  lea     rcx, [rdi+0B0h]; this
0x14004659b  call    ??0LogonFrameworkSyncHelper@@QEAA@XZ; LogonFrameworkSyncHelper::LogonFrameworkSyncHelper(void)
0x1400465a0  mov     [rdi+0D0h], rbp
0x1400465a7  mov     [rdi+0D8h], rbp
0x1400465ae  mov     [rdi+0E0h], rbp
0x1400465b5  mov     [rdi+0E8h], rbp
0x1400465bc  mov     [rdi+0F0h], bpl
0x1400465c3  mov     [rdi+0F2h], bp
0x1400465ca  mov     [rdi+0F5h], bp
0x1400465d1  mov     dword ptr [rdi+0F8h], 668A0h
0x1400465db  mov     [rdi+100h], rbp
0x1400465e2  mov     [rdi+108h], rbp
0x1400465e9  mov     [rdi+110h], bpl
0x1400465f0  mov     [rdi+118h], rbp
0x1400465f7  mov     dword ptr [rdi+120h], 2710h
0x140046601  mov     [rdi+124h], bp
0x140046608  mov     [rdi+128h], ebp
0x14004660e  mov     [rdi+130h], rbp
0x140046615  mov     [rdi+138h], bpl
0x14004661c  mov     [rdi+140h], rbp
0x140046623  mov     [rdi+148h], rbp
0x14004662a  mov     [rdi+150h], rbp
0x140046631  mov     [rdi+158h], rbp
0x140046638  mov     [rdi+160h], rbp
0x14004663f  mov     [rdi+168h], rbp
0x140046646  mov     [rdi+170h], rbp
0x14004664d  mov     [rdi+178h], rbp
0x140046654  mov     [rdi+180h], rbp
0x14004665b  mov     [rdi+188h], rbp
0x140046662  mov     [rdi+190h], rbp
0x140046669  mov     [rdi+198h], rbp
0x140046670  mov     [rdi+1A0h], rbp
0x140046677  mov     [rdi+1A8h], rbp
0x14004667e  mov     [rdi+1B0h], rbp
0x140046685  mov     [rdi+1B8h], rbp
0x14004668c  mov     [rdi+1C0h], rbp
0x140046693  mov     [rdi+1C8h], rbp
0x14004669a  mov     [rdi+1D0h], rbp
0x1400466a1  mov     [rdi+1D8h], rbp
0x1400466a8  mov     [rdi+1E0h], rbp
0x1400466af  mov     [rdi+1E8h], rbp
0x1400466b6  xorps   xmm0, xmm0
0x1400466b9  movups  xmmword ptr [rdi+1F0h], xmm0
0x1400466c0  movups  xmmword ptr [rdi+200h], xmm0
0x1400466c7  mov     [rdi+218h], rbp
0x1400466ce  mov     [rdi+220h], rsi
0x1400466d5  call    cs:__imp_GetTickCount
0x1400466dc  nop     dword ptr [rax+rax+00h]
0x1400466e1  mov     [rdi+228h], eax
0x1400466e7  mov     [rdi+22Ch], rbp
0x1400466ee  mov     [rdi+238h], rbp
0x1400466f5  mov     [rdi+240h], rbp
0x1400466fc  mov     [rdi+248h], bp
0x140046703  mov     [rdi+250h], rbp
0x14004670a  mov     [rdi+258h], rbp
0x140046711  mov     [rdi+260h], rbp
0x140046718  mov     [rdi+268h], rbp
0x14004671f  lea     rbx, [rdi+270h]
0x140046726  mov     rcx, rbx; struct wil::details::IFailureCallback *
0x140046729  call    ??0?$ActivityBase@VLogonFrameworkLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14004672e  lea     rax, ??_7AllLogonTasks@LogonFrameworkTelemetry@@6B@; const LogonFrameworkTelemetry::AllLogonTasks::`vftable'
0x140046735  mov     [rbx], rax
0x140046738  mov     rax, rdi
0x14004673b  add     rsp, 28h
0x14004673f  pop     rdi
0x140046740  pop     rsi
0x140046741  pop     rbp
0x140046742  pop     rbx
0x140046743  retn
```
