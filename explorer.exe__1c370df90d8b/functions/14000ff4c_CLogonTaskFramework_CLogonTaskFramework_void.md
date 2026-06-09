# CLogonTaskFramework::CLogonTaskFramework(void)

- ea: `0x14000ff4c`
- end: `0x140010215`
- name: `??0CLogonTaskFramework@@QEAA@XZ`
- size: `713`
- prototype: `CLogonTaskFramework *__fastcall(CLogonTaskFramework *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000fea4`

## callees

- `0x14000ff4c`
- `0x14001d3cc`
- `0x1400a7de0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000ffae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000ffd1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000ffed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140010009`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140010025`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140010041`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000ffae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000ffd1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000ffed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140010009`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140010025`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140010041`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000ff9a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000ff9a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400101ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400101ac`

## string_xrefs

- `0x14000fffb`: `AppResolverReadyEvent`
- `0x140010017`: `SignInSuggestionsReadyEvent`
- `0x14000ffa0`: `ShellLauncherReadyEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CLogonTaskFramework *__fastcall CLogonTaskFramework::CLogonTaskFramework(CLogonTaskFramework *this)
{
  *((_DWORD *)this + 3) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILogonFramework>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &CLogonTaskFramework::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  InitializeSRWLock((PSRWLOCK)this + 4);
  *((_QWORD *)this + 6) = CreateEventW(0, 1, 0, L"ShellLauncherReadyEvent");
  *((_QWORD *)this + 5) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *((_QWORD *)this + 8) = CreateEventW(0, 1, 0, L"Local\\ShellStartupEvent");
  *((_QWORD *)this + 7) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *((_QWORD *)this + 10) = CreateEventW(0, 1, 0, L"BINotifiedNewSessionEvent");
  *((_QWORD *)this + 9) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *((_QWORD *)this + 12) = CreateEventW(0, 1, 0, L"AppResolverReadyEvent");
  *((_QWORD *)this + 11) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *((_QWORD *)this + 14) = CreateEventW(0, 1, 0, L"SignInSuggestionsReadyEvent");
  *((_QWORD *)this + 13) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *((_QWORD *)this + 16) = CreateEventW(0, 1, 0, L"SignInSuggestionsCallbackEvent");
  *((_QWORD *)this + 15) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
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
  *((_OWORD *)this + 30) = 0;
  *((_OWORD *)this + 31) = 0;
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 1;
  *((_DWORD *)this + 134) = GetTickCount();
  *(_QWORD *)((char *)this + 540) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 70) = 0;
  *((_WORD *)this + 284) = 0;
  *((_QWORD *)this + 72) = 0;
  *((_QWORD *)this + 73) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_QWORD *)this + 75) = 0;
  wil::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>((CLogonTaskFramework *)((char *)this + 608));
  *((_QWORD *)this + 76) = &LogonFrameworkTelemetry::AllLogonTasks::`vftable';
  return this;
}

```

## disassembly

```asm
0x14000ff4c  push    rbx
0x14000ff4e  push    rbp
0x14000ff4f  push    rsi
0x14000ff50  push    rdi
0x14000ff51  sub     rsp, 28h
0x14000ff55  mov     rdi, rcx
0x14000ff58  mov     ebp, 1
0x14000ff5d  mov     [rcx+0Ch], ebp
0x14000ff60  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UILogonFramework@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILogonFramework>::`vftable'
0x14000ff67  mov     [rcx], rax
0x14000ff6a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000ff71  xor     esi, esi
0x14000ff73  test    rcx, rcx
0x14000ff76  jz      short loc_14000FF85
0x14000ff78  mov     rax, [rcx]
0x14000ff7b  mov     rax, [rax+8]
0x14000ff7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff84  nop
0x14000ff85  lea     rax, ??_7CLogonTaskFramework@@6B@; const CLogonTaskFramework::`vftable'
0x14000ff8c  mov     [rdi], rax
0x14000ff8f  mov     [rdi+10h], rsi
0x14000ff93  mov     [rdi+18h], esi
0x14000ff96  lea     rcx, [rdi+20h]; SRWLock
0x14000ff9a  call    cs:__imp_InitializeSRWLock
0x14000ffa0  lea     r9, aShelllauncherr; "ShellLauncherReadyEvent"
0x14000ffa7  xor     r8d, r8d; bInitialState
0x14000ffaa  mov     edx, ebp; bManualReset
0x14000ffac  xor     ecx, ecx; lpEventAttributes
0x14000ffae  call    cs:__imp_CreateEventW
0x14000ffb4  mov     [rdi+30h], rax
0x14000ffb8  lea     rbx, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x14000ffbf  mov     [rdi+28h], rbx
0x14000ffc3  lea     r9, aLocalShellstar; "Local\\ShellStartupEvent"
0x14000ffca  xor     r8d, r8d; bInitialState
0x14000ffcd  mov     edx, ebp; bManualReset
0x14000ffcf  xor     ecx, ecx; lpEventAttributes
0x14000ffd1  call    cs:__imp_CreateEventW
0x14000ffd7  mov     [rdi+40h], rax
0x14000ffdb  mov     [rdi+38h], rbx
0x14000ffdf  lea     r9, aBinotifiednews; "BINotifiedNewSessionEvent"
0x14000ffe6  xor     r8d, r8d; bInitialState
0x14000ffe9  mov     edx, ebp; bManualReset
0x14000ffeb  xor     ecx, ecx; lpEventAttributes
0x14000ffed  call    cs:__imp_CreateEventW
0x14000fff3  mov     [rdi+50h], rax
0x14000fff7  mov     [rdi+48h], rbx
0x14000fffb  lea     r9, aAppresolverrea; "AppResolverReadyEvent"
0x140010002  xor     r8d, r8d; bInitialState
0x140010005  mov     edx, ebp; bManualReset
0x140010007  xor     ecx, ecx; lpEventAttributes
0x140010009  call    cs:__imp_CreateEventW
0x14001000f  mov     [rdi+60h], rax
0x140010013  mov     [rdi+58h], rbx
0x140010017  lea     r9, aSigninsuggesti_2; "SignInSuggestionsReadyEvent"
0x14001001e  xor     r8d, r8d; bInitialState
0x140010021  mov     edx, ebp; bManualReset
0x140010023  xor     ecx, ecx; lpEventAttributes
0x140010025  call    cs:__imp_CreateEventW
0x14001002b  mov     [rdi+70h], rax
0x14001002f  mov     [rdi+68h], rbx
0x140010033  lea     r9, aSigninsuggesti; "SignInSuggestionsCallbackEvent"
0x14001003a  xor     r8d, r8d; bInitialState
0x14001003d  mov     edx, ebp; bManualReset
0x14001003f  xor     ecx, ecx; lpEventAttributes
0x140010041  call    cs:__imp_CreateEventW
0x140010047  mov     [rdi+80h], rax
0x14001004e  mov     [rdi+78h], rbx
0x140010052  mov     [rdi+88h], rsi
0x140010059  mov     [rdi+90h], rsi
0x140010060  mov     [rdi+98h], rsi
0x140010067  mov     [rdi+0A0h], rsi
0x14001006e  mov     [rdi+0A8h], rsi
0x140010075  lea     rcx, [rdi+0B0h]; this
0x14001007c  call    ??0LogonFrameworkSyncHelper@@QEAA@XZ; LogonFrameworkSyncHelper::LogonFrameworkSyncHelper(void)
0x140010081  mov     [rdi+0D0h], rsi
0x140010088  mov     [rdi+0D8h], rsi
0x14001008f  mov     [rdi+0E0h], rsi
0x140010096  mov     [rdi+0E8h], rsi
0x14001009d  mov     [rdi+0F0h], sil
0x1400100a4  mov     [rdi+0F2h], si
0x1400100ab  mov     [rdi+0F5h], si
0x1400100b2  mov     dword ptr [rdi+0F8h], 668A0h
0x1400100bc  mov     [rdi+100h], rsi
0x1400100c3  mov     [rdi+108h], rsi
0x1400100ca  mov     [rdi+110h], sil
0x1400100d1  mov     [rdi+118h], rsi
0x1400100d8  mov     dword ptr [rdi+120h], 2710h
0x1400100e2  mov     [rdi+124h], si
0x1400100e9  mov     [rdi+128h], esi
0x1400100ef  mov     [rdi+130h], rsi
0x1400100f6  mov     [rdi+138h], sil
0x1400100fd  mov     [rdi+140h], rsi
0x140010104  mov     [rdi+148h], rsi
0x14001010b  mov     [rdi+150h], rsi
0x140010112  mov     [rdi+158h], rsi
0x140010119  mov     [rdi+160h], rsi
0x140010120  mov     [rdi+168h], rsi
0x140010127  mov     [rdi+170h], rsi
0x14001012e  mov     [rdi+178h], rsi
0x140010135  mov     [rdi+180h], rsi
0x14001013c  mov     [rdi+188h], rsi
0x140010143  mov     [rdi+190h], rsi
0x14001014a  mov     [rdi+198h], rsi
0x140010151  mov     [rdi+1A0h], rsi
0x140010158  mov     [rdi+1A8h], rsi
0x14001015f  mov     [rdi+1B0h], rsi
0x140010166  mov     [rdi+1B8h], rsi
0x14001016d  mov     [rdi+1C0h], rsi
0x140010174  mov     [rdi+1C8h], rsi
0x14001017b  mov     [rdi+1D0h], rsi
0x140010182  mov     [rdi+1D8h], rsi
0x140010189  xorps   xmm0, xmm0
0x14001018c  movups  xmmword ptr [rdi+1E0h], xmm0
0x140010193  movups  xmmword ptr [rdi+1F0h], xmm0
0x14001019a  mov     [rdi+208h], rsi
0x1400101a1  mov     qword ptr [rdi+210h], 1
0x1400101ac  call    cs:__imp_GetTickCount
0x1400101b2  mov     [rdi+218h], eax
0x1400101b8  mov     [rdi+21Ch], rsi
0x1400101bf  mov     [rdi+228h], rsi
0x1400101c6  mov     [rdi+230h], rsi
0x1400101cd  mov     [rdi+238h], si
0x1400101d4  mov     [rdi+240h], rsi
0x1400101db  mov     [rdi+248h], rsi
0x1400101e2  mov     [rdi+250h], rsi
0x1400101e9  mov     [rdi+258h], rsi
0x1400101f0  lea     rbx, [rdi+260h]
0x1400101f7  mov     rcx, rbx; struct wil::details::IFailureCallback *
0x1400101fa  call    ??0?$ActivityBase@VLogonFrameworkLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400101ff  lea     rax, ??_7AllLogonTasks@LogonFrameworkTelemetry@@6B@; const LogonFrameworkTelemetry::AllLogonTasks::`vftable'
0x140010206  mov     [rbx], rax
0x140010209  mov     rax, rdi
0x14001020c  add     rsp, 28h
0x140010210  pop     rdi
0x140010211  pop     rsi
0x140010212  pop     rbp
0x140010213  pop     rbx
0x140010214  retn
```
