# GuestStateFile::Store(ushort const *,unsigned __int64,ushort const *,ushort const *)

- ea: `0x18005a870`
- end: `0x18005abf0`
- name: `?Store@GuestStateFile@@UEAAXPEBG_K00@Z`
- size: `896`
- prototype: `void __usercall(GuestStateFile *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int64@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180009e8c`
- `0x1800136d0`
- `0x18001587c`
- `0x180020c90`
- `0x1800526dc`
- `0x180052930`
- `0x180052a30`
- `0x180053c84`
- `0x180053e24`
- `0x180054890`
- `0x1800548e8`
- `0x180057704`
- `0x18005782c`
- `0x18005a870`
- `0x18005ae50`
- `0x18005b3c8`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ab0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ab0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005aa8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005aa8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005aa94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005aa94`
- `RPCRT4!UuidFromStringW` at `0x18005a955`
- `RPCRT4!UuidFromStringW` at `0x18005a955`

## string_xrefs

- `0x18005aba8`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x18005abc3`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x18005abde`: `onecore\vm\common\gueststate\gueststatefile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall GuestStateFile::Store(
        RTL_SRWLOCK *this,
        const unsigned __int16 *a2,
        unsigned __int64 a3,
        const unsigned __int16 *a4,
        unsigned __int16 *StringUuid)
{
  __int64 v9; // r8
  _QWORD *v10; // rax
  void (__fastcall ***v11)(_QWORD, __int64); // rcx
  void (__fastcall ***v12)(_QWORD, __int64); // r8
  RTL_SRWLOCK *v13; // rcx
  _QWORD *v14; // rax
  void (__fastcall ***v15)(_QWORD, __int64); // rcx
  void (__fastcall ***v16)(_QWORD, __int64); // r8
  bool BackingStore; // al
  void (__fastcall ***Ptr)(_QWORD, __int64); // rcx
  const struct _GUID *v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  RTL_SRWLOCK *v21; // [rsp+30h] [rbp-D0h] BYREF
  char v22; // [rsp+38h] [rbp-C8h]
  _QWORD *v23; // [rsp+40h] [rbp-C0h] BYREF
  bool v24; // [rsp+48h] [rbp-B8h]
  int v25; // [rsp+49h] [rbp-B7h]
  __int16 v26; // [rsp+4Dh] [rbp-B3h]
  unsigned __int8 v27; // [rsp+4Fh] [rbp-B1h]
  const unsigned __int16 *v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  void (__fastcall ***v30)(_QWORD, __int64); // [rsp+60h] [rbp-A0h] BYREF
  UUID Uuid; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v32[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v33[42]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  memset_0(v33, 0, sizeof(v33));
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v33,
    "GuestStateFileStore");
  v33[0] = &GuestStateFileTraceProvider::GuestStateFileStore::`vftable';
  GuestStateFileTraceProvider::GuestStateFileStore::StartActivity(
    (GuestStateFileTraceProvider::GuestStateFileStore *)v33,
    StringUuid,
    a2,
    a3,
    v19);
  if ( !GuestStateFile::IsTransient((GuestStateFile *)this) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x80070032LL,
      v20);
  v32[0] = 0;
  v32[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v32[0]) = 0;
  Uuid = 0;
  if ( a4 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a4[v9] );
    std::wstring::_Assign<unsigned short>(v32, a4);
  }
  if ( StringUuid && UuidFromStringW(StringUuid, &Uuid) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23E,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x80070057LL,
      v20);
  v30 = 0;
  if ( ((__int64)this[27].Ptr & 1) != 0 )
  {
    v10 = (_QWORD *)GuestStateRawData::CreateInstance(&v21);
    v11 = (void (__fastcall ***)(_QWORD, __int64))*v10;
    *v10 = 0;
    v12 = v30;
    v30 = v11;
    if ( v12 )
      (**v12)(v12, 1);
    v13 = v21;
LABEL_15:
    if ( v13 )
      (*(void (__fastcall **)(RTL_SRWLOCK *, __int64))v13->Ptr)(v13, 1);
    goto LABEL_17;
  }
  v14 = (_QWORD *)GuestStateData::CreateInstance(&v21);
  v15 = (void (__fastcall ***)(_QWORD, __int64))*v14;
  *v14 = 0;
  v16 = v30;
  v30 = v15;
  if ( v16 )
    (**v16)(v16, 1);
  v13 = v21;
  if ( v21 )
    goto LABEL_15;
LABEL_17:
  BackingStore = GuestStateFile::CreateBackingStore(a2, a3, (const struct _GUID *)(v33[34] + 8LL));
  v23 = &v30;
  v24 = BackingStore;
  v25 = *(_DWORD *)&Uuid.Data4[1];
  v26 = *(_WORD *)&Uuid.Data4[5];
  v27 = Uuid.Data4[7];
  v28 = a2;
  v29 = 1;
  if ( !((unsigned __int8 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64), const unsigned __int16 *, _QWORD, const unsigned __int16 *))(*v30)[1])(
          v30,
          a2,
          0,
          a4) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x257,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x8000FFFFLL,
      (int)StringUuid);
  AcquireSRWLockExclusive(this + 5);
  LODWORD(this[6].Ptr) = GetCurrentThreadId();
  v21 = this + 5;
  v22 = 1;
  if ( ((__int64)this[27].Ptr & 1) == 0 )
    (*(void (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)this[7].Ptr + 152LL))(this[7].Ptr, v30);
  Ptr = (void (__fastcall ***)(_QWORD, __int64))this[7].Ptr;
  this[7].Ptr = v30;
  v30 = Ptr;
  std::wstring::operator=(&this[8], v32);
  *(UUID *)&this[12].Ptr = Uuid;
  LODWORD(this[14].Ptr) = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)this[7].Ptr + 128LL))(this[7].Ptr);
  LODWORD(this[6].Ptr) = 0;
  ReleaseSRWLockExclusive(this + 5);
  LOBYTE(v29) = 0;
  GuestStateFile::LogDebugTrace((GuestStateFile *)this, L"Stored file successfully.");
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v33);
  wil::details::ScopeExitFn__lambda_8ba4ae170b665c49a99a578f7b0bfdfe___::_ScopeExitFn__lambda_8ba4ae170b665c49a99a578f7b0bfdfe___(&v23);
  if ( v30 )
    (**v30)(v30, 1);
  std::wstring::~wstring(v32);
  v33[0] = &GuestStateFileTraceProvider::GuestStateFileStore::`vftable';
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v33);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(v33);
}

```

## disassembly

```asm
0x18005a870  push    rbp
0x18005a872  push    rbx
0x18005a873  push    rsi
0x18005a874  push    rdi
0x18005a875  push    r12
0x18005a877  push    r13
0x18005a879  push    r14
0x18005a87b  push    r15
0x18005a87d  lea     rbp, [rsp-118h]
0x18005a885  sub     rsp, 218h
0x18005a88c  mov     rax, cs:__security_cookie
0x18005a893  xor     rax, rsp
0x18005a896  mov     [rbp+150h+var_50], rax
0x18005a89d  mov     rdi, r9
0x18005a8a0  mov     r12, r8
0x18005a8a3  mov     r15, rdx
0x18005a8a6  mov     rbx, rcx
0x18005a8a9  mov     rsi, [rbp+150h+StringUuid]
0x18005a8b0  xor     edx, edx; Val
0x18005a8b2  mov     r8d, 150h; Size
0x18005a8b8  lea     rcx, [rbp+150h+var_1A0]; void *
0x18005a8bc  call    memset_0
0x18005a8c1  nop
0x18005a8c2  lea     rdx, aGueststatefile_8; "GuestStateFileStore"
0x18005a8c9  lea     rcx, [rbp+150h+var_1A0]
0x18005a8cd  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005a8d2  lea     rax, ??_7GuestStateFileStore@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileStore::`vftable'
0x18005a8d9  mov     [rbp+150h+var_1A0], rax
0x18005a8dd  mov     r9, r12; unsigned __int64
0x18005a8e0  mov     r8, r15; unsigned __int16 *
0x18005a8e3  mov     rdx, rsi; unsigned __int16 *
0x18005a8e6  lea     rcx, [rbp+150h+var_1A0]; this
0x18005a8ea  call    ?StartActivity@GuestStateFileStore@GuestStateFileTraceProvider@@QEAAXPEBG0_KPEBU_GUID@@@Z; GuestStateFileTraceProvider::GuestStateFileStore::StartActivity(ushort const *,ushort const *,unsigned __int64,_GUID const *)
0x18005a8ef  nop
0x18005a8f0  mov     r14, [rbp+158h]
0x18005a8f7  mov     rcx, rbx; this
0x18005a8fa  call    ?IsTransient@GuestStateFile@@UEBA_NXZ; GuestStateFile::IsTransient(void)
0x18005a8ff  xor     r13d, r13d
0x18005a902  test    al, al
0x18005a904  jz      loc_18005ABBD
0x18005a90a  xorps   xmm0, xmm0
0x18005a90d  movups  [rbp+150h+var_1C0], xmm0
0x18005a911  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005a919  movdqu  [rbp+150h+var_1B0], xmm1
0x18005a91e  mov     word ptr [rbp+150h+var_1C0], r13w
0x18005a923  movdqa  xmmword ptr [rsp+250h+Uuid.Data1], xmm0
0x18005a929  test    rdi, rdi
0x18005a92c  jz      short loc_18005A948
0x18005a92e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005a932  inc     r8
0x18005a935  cmp     [rdi+r8*2], r13w
0x18005a93a  jnz     short loc_18005A932
0x18005a93c  mov     rdx, rdi
0x18005a93f  lea     rcx, [rbp+150h+var_1C0]
0x18005a943  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005a948  test    rsi, rsi
0x18005a94b  jz      short loc_18005A96F
0x18005a94d  lea     rdx, [rsp+250h+Uuid]; Uuid
0x18005a952  mov     rcx, rsi; StringUuid
0x18005a955  call    cs:__imp_UuidFromStringW
0x18005a95b  test    eax, eax
0x18005a95d  setnz   al
0x18005a960  mov     rcx, [rbp+158h]; this
0x18005a967  test    al, al
0x18005a969  jnz     loc_18005ABD8
0x18005a96f  mov     [rsp+250h+var_1F0], r13
0x18005a974  mov     edx, [rbx+0D8h]
0x18005a97a  mov     r14d, 1
0x18005a980  lea     rcx, [rsp+250h+var_220]
0x18005a985  test    r14b, dl
0x18005a988  jz      short loc_18005A9BC
0x18005a98a  call    ?CreateInstance@GuestStateRawData@@SA?AV?$unique_ptr@VIGuestStateData@@U?$default_delete@VIGuestStateData@@@std@@@std@@W4GuestStateAccessFormat@@@Z; GuestStateRawData::CreateInstance(GuestStateAccessFormat)
0x18005a98f  mov     rcx, [rax]
0x18005a992  mov     [rax], r13
0x18005a995  mov     r8, [rsp+250h+var_1F0]
0x18005a99a  mov     [rsp+250h+var_1F0], rcx
0x18005a99f  test    r8, r8
0x18005a9a2  jz      short loc_18005A9B5
0x18005a9a4  mov     rax, [r8]
0x18005a9a7  mov     edx, r14d
0x18005a9aa  mov     rcx, r8
0x18005a9ad  mov     rax, [rax]
0x18005a9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a9b5  mov     rcx, [rsp+250h+var_220]
0x18005a9ba  jmp     short loc_18005A9F1
0x18005a9bc  call    ?CreateInstance@GuestStateData@@SA?AV?$unique_ptr@VIGuestStateData@@U?$default_delete@VIGuestStateData@@@std@@@std@@XZ; GuestStateData::CreateInstance(void)
0x18005a9c1  mov     rcx, [rax]
0x18005a9c4  mov     [rax], r13
0x18005a9c7  mov     r8, [rsp+250h+var_1F0]
0x18005a9cc  mov     [rsp+250h+var_1F0], rcx
0x18005a9d1  test    r8, r8
0x18005a9d4  jz      short loc_18005A9E7
0x18005a9d6  mov     rax, [r8]
0x18005a9d9  mov     edx, r14d
0x18005a9dc  mov     rcx, r8
0x18005a9df  mov     rax, [rax]
0x18005a9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a9e7  mov     rcx, [rsp+250h+var_220]
0x18005a9ec  test    rcx, rcx
0x18005a9ef  jz      short loc_18005AA04
0x18005a9f1  test    rcx, rcx
0x18005a9f4  jz      short loc_18005AA04
0x18005a9f6  mov     rax, [rcx]
0x18005a9f9  mov     edx, r14d
0x18005a9fc  mov     rax, [rax]
0x18005a9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aa04  mov     r8, [rbp+150h+var_90]
0x18005aa0b  add     r8, 8; struct _GUID *
0x18005aa0f  mov     rdx, r12; unsigned __int64
0x18005aa12  mov     rcx, r15; unsigned __int16 *
0x18005aa15  call    ?CreateBackingStore@GuestStateFile@@CA_NPEBG_KPEBU_GUID@@@Z; GuestStateFile::CreateBackingStore(ushort const *,unsigned __int64,_GUID const *)
0x18005aa1a  xorps   xmm0, xmm0
0x18005aa1d  movups  [rsp+250h+var_210], xmm0
0x18005aa22  movups  [rsp+250h+var_200], xmm0
0x18005aa27  lea     rcx, [rsp+250h+var_1F0]
0x18005aa2c  mov     qword ptr [rsp+250h+var_210], rcx
0x18005aa31  mov     byte ptr [rsp+250h+var_210+8], al
0x18005aa35  mov     eax, dword ptr [rsp+250h+Uuid.Data4+1]
0x18005aa39  mov     dword ptr [rsp+250h+var_210+9], eax
0x18005aa3d  movzx   eax, word ptr [rsp+250h+Uuid.Data4+5]
0x18005aa42  mov     word ptr [rsp+250h+var_210+0Dh], ax
0x18005aa47  mov     al, [rsp+250h+Uuid.Data4+7]
0x18005aa4b  mov     byte ptr [rsp+250h+var_210+0Fh], al
0x18005aa4f  mov     qword ptr [rsp+250h+var_200], r15
0x18005aa54  mov     byte ptr [rsp+250h+var_200+8], r14b
0x18005aa59  mov     rcx, [rsp+250h+var_1F0]
0x18005aa5e  mov     r14, [rbp+158h]
0x18005aa65  mov     rax, [rcx]
0x18005aa68  mov     qword ptr [rsp+250h+var_230], rsi; int
0x18005aa6d  mov     r9, rdi
0x18005aa70  xor     r8d, r8d
0x18005aa73  mov     rdx, r15
0x18005aa76  mov     rax, [rax+8]
0x18005aa7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aa7f  test    al, al
0x18005aa81  jz      loc_18005ABA2
0x18005aa87  lea     rdi, [rbx+28h]
0x18005aa8b  mov     rcx, rdi; SRWLock
0x18005aa8e  call    cs:__imp_AcquireSRWLockExclusive
0x18005aa94  call    cs:__imp_GetCurrentThreadId
0x18005aa9a  mov     [rdi+8], eax
0x18005aa9d  mov     [rsp+250h+var_220], rdi
0x18005aaa2  mov     [rsp+250h+var_218], 1
0x18005aaa7  test    byte ptr [rbx+0D8h], 1
0x18005aaae  jnz     short loc_18005AAC8
0x18005aab0  mov     rcx, [rbx+38h]
0x18005aab4  mov     rax, [rcx]
0x18005aab7  mov     rdx, [rsp+250h+var_1F0]
0x18005aabc  mov     rax, [rax+98h]
0x18005aac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aac8  mov     rcx, [rbx+38h]
0x18005aacc  mov     rax, [rsp+250h+var_1F0]
0x18005aad1  mov     [rbx+38h], rax
0x18005aad5  mov     [rsp+250h+var_1F0], rcx
0x18005aada  lea     rcx, [rbx+40h]
0x18005aade  lea     rdx, [rbp+150h+var_1C0]
0x18005aae2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005aae7  movaps  xmm0, xmmword ptr [rsp+250h+Uuid.Data1]
0x18005aaec  movdqu  xmmword ptr [rbx+60h], xmm0
0x18005aaf1  mov     rcx, [rbx+38h]
0x18005aaf5  mov     rax, [rcx]
0x18005aaf8  mov     rax, [rax+80h]
0x18005aaff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab04  mov     [rbx+70h], eax
0x18005ab07  mov     [rdi+8], r13d
0x18005ab0b  mov     rcx, rdi; SRWLock
0x18005ab0e  call    cs:__imp_ReleaseSRWLockExclusive
0x18005ab14  mov     byte ptr [rsp+250h+var_200+8], r13b
0x18005ab19  lea     rdx, aStoredFileSucc; "Stored file successfully."
0x18005ab20  mov     rcx, rbx; this
0x18005ab23  call    ?LogDebugTrace@GuestStateFile@@IEBAXPEBG@Z; GuestStateFile::LogDebugTrace(ushort const *)
0x18005ab28  lea     rcx, [rbp+150h+var_1A0]
0x18005ab2c  call    ?Stop@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005ab31  nop
0x18005ab32  lea     rcx, [rsp+250h+var_210]
0x18005ab37  call    wil__details__ScopeExitFn__lambda_8ba4ae170b665c49a99a578f7b0bfdfe______ScopeExitFn__lambda_8ba4ae170b665c49a99a578f7b0bfdfe___
0x18005ab3c  nop
0x18005ab3d  mov     rcx, [rsp+250h+var_1F0]
0x18005ab42  test    rcx, rcx
0x18005ab45  jz      short loc_18005AB58
0x18005ab47  mov     rax, [rcx]
0x18005ab4a  mov     edx, 1
0x18005ab4f  mov     rax, [rax]
0x18005ab52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab57  nop
0x18005ab58  lea     rcx, [rbp+150h+var_1C0]
0x18005ab5c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005ab61  nop
0x18005ab62  lea     rax, ??_7GuestStateFileStore@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileStore::`vftable'
0x18005ab69  mov     [rbp+150h+var_1A0], rax
0x18005ab6d  lea     rcx, [rbp+150h+var_1A0]
0x18005ab71  call    ?Destroy@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18005ab76  lea     rcx, [rbp+150h+var_1A0]
0x18005ab7a  call    ??1?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18005ab7f  mov     rcx, [rbp+150h+var_50]
0x18005ab86  xor     rcx, rsp; StackCookie
0x18005ab89  call    __security_check_cookie
0x18005ab8e  add     rsp, 218h
0x18005ab95  pop     r15
0x18005ab97  pop     r14
0x18005ab99  pop     r13
0x18005ab9b  pop     r12
0x18005ab9d  pop     rdi
0x18005ab9e  pop     rsi
0x18005ab9f  pop     rbx
0x18005aba0  pop     rbp
0x18005aba1  retn
0x18005aba2  mov     r9d, 8000FFFFh; char *
0x18005aba8  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x18005abaf  mov     edx, 257h; void *
0x18005abb4  mov     rcx, r14; this
0x18005abb7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005abbd  mov     r9d, 80070032h; char *
0x18005abc3  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x18005abca  mov     edx, 232h; void *
0x18005abcf  mov     rcx, r14; this
0x18005abd2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005abd8  mov     r9d, 80070057h; char *
0x18005abde  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x18005abe5  mov     edx, 23Eh; void *
0x18005abea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
