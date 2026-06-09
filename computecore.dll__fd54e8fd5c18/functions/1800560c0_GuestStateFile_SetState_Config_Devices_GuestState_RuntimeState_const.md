# GuestStateFile::SetState(Config::Devices::GuestState::RuntimeState const &)

- ea: `0x1800560c0`
- end: `0x180056336`
- name: `?SetState@GuestStateFile@@UEAAXAEBURuntimeState@GuestState@Devices@Config@@@Z`
- size: `630`
- prototype: `void __fastcall(RTL_SRWLOCK *this, const struct Config::Devices::GuestState::RuntimeState *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180009e8c`
- `0x180011a4c`
- `0x18001587c`
- `0x180021c4c`
- `0x180052014`
- `0x1800522d4`
- `0x1800526dc`
- `0x180052930`
- `0x180053e24`
- `0x180054180`
- `0x1800548e8`
- `0x1800560c0`
- `0x1800575c4`
- `0x18005782c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056268`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056268`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180056194`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180056194`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005619a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005619a`

## string_xrefs

- `0x180056309`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x180056324`: `onecore\vm\common\gueststate\gueststatefile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GuestStateFile::SetState(RTL_SRWLOCK *this, const struct Config::Devices::GuestState::RuntimeState *a2)
{
  __int64 FilePath; // rbx
  __int64 v5; // r14
  PVOID Ptr; // rdx
  __int64 v7; // r14
  unsigned int v8; // eax
  unsigned __int64 v9; // rbx
  int v10; // edx
  _QWORD *v11; // rax
  __int64 v12; // rax
  int v13; // [rsp+20h] [rbp-E0h]
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v15[3]; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v16; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v17[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[32]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD Src[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v20[42]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  memset_0(v20, 0, sizeof(v20));
  FilePath = GuestStateFile::GetFilePath(this, v18);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v20,
    "GuestStateFileSetState");
  v20[0] = &GuestStateFileTraceProvider::GuestStateFileSetState::`vftable';
  v17[0] = *(_OWORD *)FilePath;
  v17[1] = *(_OWORD *)(FilePath + 16);
  *(_QWORD *)(FilePath + 16) = 0;
  *(_QWORD *)(FilePath + 24) = 7;
  *(_WORD *)FilePath = 0;
  v16 = *(_OWORD *)&this[12].Ptr;
  GuestStateFileTraceProvider::GuestStateFileSetState::StartActivity(v20, &v16, v17);
  std::wstring::~wstring(v18);
  Marshal::ToJson<Config::Devices::GuestState::RuntimeState const &,>(Src, a2);
  v5 = Src[2];
  AcquireSRWLockExclusive(this + 5);
  LODWORD(this[6].Ptr) = GetCurrentThreadId();
  *(_QWORD *)&v17[0] = this + 5;
  BYTE8(v17[0]) = 1;
  Ptr = this[7].Ptr;
  if ( !Ptr )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x356,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x80070015LL,
      v13);
  v7 = 2 * v5 + 2;
  v8 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 120LL))(this[7].Ptr);
  v9 = (v7 + v8 - 1LL) & ~(v8 - 1LL);
  if ( v9 > (*(unsigned int (__fastcall **)(PVOID))(*(_QWORD *)this[7].Ptr + 112LL))(this[7].Ptr) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x35E,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x80070070LL,
      v13);
  std::wstring::resize(Src);
  v15[0] = v7;
  v14 = v9;
  v11 = Src;
  if ( Src[3] > 7u )
    v11 = (_QWORD *)Src[0];
  *(_QWORD *)&v16 = v11;
  ___InvokeMethodWithRetryAndLockHeld_PEBXKK__ZPEBGKK_GuestStateFile__AEBAXP8IGuestStateData__EAAXPEBXKK_Z__QEAPEBG__QEAK3_Z(
    (_DWORD)this,
    v10,
    (unsigned int)&v16,
    (unsigned int)&v14,
    (__int64)v15);
  LODWORD(this[6].Ptr) = 0;
  ReleaseSRWLockExclusive(this + 5);
  v12 = Vml::FormatString(v18, (wchar_t *)L"Changed state to %s");
  if ( *(_QWORD *)(v12 + 24) > 7u )
    v12 = *(_QWORD *)v12;
  GuestStateFile::LogDebugTrace((GuestStateFile *)this, (const unsigned __int16 *)v12);
  std::wstring::~wstring(v18);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v20);
  std::wstring::~wstring(Src);
  v20[0] = &GuestStateFileTraceProvider::GuestStateFileSetState::`vftable';
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v20);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(v20);
}

```

## disassembly

```asm
0x1800560c0  mov     [rsp-8+arg_10], rbx
0x1800560c5  push    rbp
0x1800560c6  push    rsi
0x1800560c7  push    rdi
0x1800560c8  push    r14
0x1800560ca  push    r15
0x1800560cc  lea     rbp, [rsp-110h]
0x1800560d4  sub     rsp, 210h
0x1800560db  mov     rax, cs:__security_cookie
0x1800560e2  xor     rax, rsp
0x1800560e5  mov     [rbp+130h+var_30], rax
0x1800560ec  mov     rdi, rdx
0x1800560ef  mov     rsi, rcx
0x1800560f2  xor     edx, edx; Val
0x1800560f4  mov     r8d, 150h; Size
0x1800560fa  lea     rcx, [rbp+130h+var_180]; void *
0x1800560fe  call    memset_0
0x180056103  lea     rdx, [rsp+230h+var_1C0]
0x180056108  mov     rcx, rsi
0x18005610b  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x180056110  mov     rbx, rax
0x180056113  lea     rdx, aGueststatefile_14; "GuestStateFileSetState"
0x18005611a  lea     rcx, [rbp+130h+var_180]
0x18005611e  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180056123  lea     rax, ??_7GuestStateFileSetState@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileSetState::`vftable'
0x18005612a  mov     [rbp+130h+var_180], rax
0x18005612e  movups  xmm0, xmmword ptr [rbx]
0x180056131  movups  [rsp+230h+var_1E0], xmm0
0x180056136  movups  xmm1, xmmword ptr [rbx+10h]
0x18005613a  movups  [rsp+230h+var_1D0], xmm1
0x18005613f  mov     qword ptr [rbx+10h], 0
0x180056147  mov     qword ptr [rbx+18h], 7
0x18005614f  xor     eax, eax
0x180056151  mov     [rbx], ax
0x180056154  movups  xmm0, xmmword ptr [rsi+60h]
0x180056158  movdqu  [rsp+230h+var_1F0], xmm0
0x18005615e  lea     r8, [rsp+230h+var_1E0]
0x180056163  lea     rdx, [rsp+230h+var_1F0]
0x180056168  lea     rcx, [rbp+130h+var_180]
0x18005616c  call    ?StartActivity@GuestStateFileSetState@GuestStateFileTraceProvider@@QEAAXU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileSetState::StartActivity(_GUID,std::wstring,_GUID const *)
0x180056171  nop
0x180056172  lea     rcx, [rsp+230h+var_1C0]
0x180056177  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005617c  mov     rdx, rdi
0x18005617f  lea     rcx, [rbp+130h+Src]
0x180056183  call    ??$ToJson@AEBURuntimeState@GuestState@Devices@Config@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBURuntimeState@GuestState@Devices@Config@@W4MarshalFlags@0@@Z; Marshal::ToJson<Config::Devices::GuestState::RuntimeState const &,>(Config::Devices::GuestState::RuntimeState const &,Marshal::MarshalFlags)
0x180056188  nop
0x180056189  mov     r14, [rbp+130h+var_190]
0x18005618d  lea     r15, [rsi+28h]
0x180056191  mov     rcx, r15; SRWLock
0x180056194  call    cs:__imp_AcquireSRWLockExclusive
0x18005619a  call    cs:__imp_GetCurrentThreadId
0x1800561a0  mov     [r15+8], eax
0x1800561a4  mov     qword ptr [rsp+230h+var_1E0], r15
0x1800561a9  mov     byte ptr [rsp+230h+var_1E0+8], 1
0x1800561ae  mov     rdx, [rsi+38h]
0x1800561b2  test    rdx, rdx
0x1800561b5  setz    al
0x1800561b8  mov     rcx, [rbp+138h]; this
0x1800561bf  test    al, al
0x1800561c1  jnz     loc_18005631E
0x1800561c7  lea     r14, ds:2[r14*2]
0x1800561cf  mov     rax, [rdx]
0x1800561d2  mov     rcx, rdx
0x1800561d5  mov     rax, [rax+78h]
0x1800561d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561de  mov     eax, eax
0x1800561e0  lea     rbx, [rax-1]
0x1800561e4  not     rbx
0x1800561e7  dec     rax
0x1800561ea  add     rax, r14
0x1800561ed  and     rbx, rax
0x1800561f0  mov     rcx, [rsi+38h]
0x1800561f4  mov     rdi, [rbp+138h]
0x1800561fb  mov     rax, [rcx]
0x1800561fe  mov     rax, [rax+70h]
0x180056202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056207  mov     eax, eax
0x180056209  cmp     rbx, rax
0x18005620c  ja      loc_180056303
0x180056212  mov     rdx, rbx
0x180056215  shr     rdx, 1
0x180056218  dec     rdx
0x18005621b  lea     rcx, [rbp+130h+Src]; Src
0x18005621f  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180056224  mov     [rsp+230h+var_1FC], r14d
0x180056229  mov     [rsp+230h+var_200], ebx
0x18005622d  lea     rax, [rbp+130h+Src]
0x180056231  cmp     [rbp+130h+var_188], 7
0x180056236  cmova   rax, [rbp+130h+Src]
0x18005623b  mov     qword ptr [rsp+230h+var_1F0], rax
0x180056240  lea     rax, [rsp+230h+var_1FC]
0x180056245  mov     qword ptr [rsp+230h+var_210], rax
0x18005624a  lea     r9, [rsp+230h+var_200]
0x18005624f  lea     r8, [rsp+230h+var_1F0]
0x180056254  mov     rcx, rsi
0x180056257  call    ??$InvokeMethodWithRetryAndLockHeld@PEBXKK$$ZPEBGKK@GuestStateFile@@AEBAXP8IGuestStateData@@EAAXPEBXKK@Z$$QEAPEBG$$QEAK3@Z
0x18005625c  nop
0x18005625d  mov     dword ptr [r15+8], 0
0x180056265  mov     rcx, r15; SRWLock
0x180056268  call    cs:__imp_ReleaseSRWLockExclusive
0x18005626e  lea     r8, [rbp+130h+Src]
0x180056272  cmp     [rbp+130h+var_188], 7
0x180056277  cmova   r8, [rbp+130h+Src]
0x18005627c  lea     rdx, aChangedStateTo; "Changed state to %s"
0x180056283  lea     rcx, [rsp+230h+var_1C0]; Src
0x180056288  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x18005628d  cmp     qword ptr [rax+18h], 7
0x180056292  jbe     short loc_180056297
0x180056294  mov     rax, [rax]
0x180056297  mov     rdx, rax; unsigned __int16 *
0x18005629a  mov     rcx, rsi; this
0x18005629d  call    ?LogDebugTrace@GuestStateFile@@IEBAXPEBG@Z; GuestStateFile::LogDebugTrace(ushort const *)
0x1800562a2  lea     rcx, [rsp+230h+var_1C0]
0x1800562a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800562ac  lea     rcx, [rbp+130h+var_180]
0x1800562b0  call    ?Stop@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800562b5  nop
0x1800562b6  lea     rcx, [rbp+130h+Src]
0x1800562ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800562bf  nop
0x1800562c0  lea     rax, ??_7GuestStateFileSetState@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileSetState::`vftable'
0x1800562c7  mov     [rbp+130h+var_180], rax
0x1800562cb  lea     rcx, [rbp+130h+var_180]
0x1800562cf  call    ?Destroy@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800562d4  lea     rcx, [rbp+130h+var_180]
0x1800562d8  call    ??1?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800562dd  mov     rcx, [rbp+130h+var_30]
0x1800562e4  xor     rcx, rsp; StackCookie
0x1800562e7  call    __security_check_cookie
0x1800562ec  mov     rbx, [rsp+230h+arg_10]
0x1800562f4  add     rsp, 210h
0x1800562fb  pop     r15
0x1800562fd  pop     r14
0x1800562ff  pop     rdi
0x180056300  pop     rsi
0x180056301  pop     rbp
0x180056302  retn
0x180056303  mov     r9d, 80070070h; char *
0x180056309  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x180056310  mov     edx, 35Eh; void *
0x180056315  mov     rcx, rdi; this
0x180056318  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005631e  mov     r9d, 80070015h; char *
0x180056324  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x18005632b  mov     edx, 356h; void *
0x180056330  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
