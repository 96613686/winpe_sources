# AuthenticationContext::Update(OAuthTokenRequestBase const *)

- ea: `0x140009518`
- end: `0x140009810`
- name: `?Update@AuthenticationContext@@QEAAXPEBVOAuthTokenRequestBase@@@Z`
- size: `760`
- prototype: `void __fastcall(AuthenticationContext *__hidden this, const struct OAuthTokenRequestBase *)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x140014ea4`

## callees

- `0x140005458`
- `0x14000579c`
- `0x140005c80`
- `0x140005ea0`
- `0x140007bf8`
- `0x140008f78`
- `0x1400090ec`
- `0x140009518`
- `0x140009898`
- `0x14000e000`
- `0x14000e70c`
- `0x14000f2ac`
- `0x140014bd8`
- `0x140014e0c`
- `0x14002c3e8`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall AuthenticationContext::Update(AuthenticationContext *this, const struct OAuthTokenRequestBase *a2)
{
  int v4; // ebx
  char v5; // r14
  _QWORD *IdToken; // rax
  char v7; // r12
  volatile signed __int32 *v8; // rsi
  _WORD *v9; // rcx
  const unsigned __int16 *v10; // rsi
  const unsigned __int16 **v11; // rax
  int v12; // ebx
  _QWORD *v13; // rdx
  volatile signed __int32 *v14; // rdx
  _QWORD *v15; // rax
  _QWORD *v16; // rdx
  int v17; // eax
  __int64 v18; // [rsp+20h] [rbp-40h] BYREF
  volatile signed __int32 *v19; // [rsp+28h] [rbp-38h]
  _BYTE pExceptionObject[16]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+40h] [rbp-20h] BYREF
  __int64 v22; // [rsp+48h] [rbp-18h] BYREF
  __int64 v23; // [rsp+50h] [rbp-10h]
  int v24; // [rsp+A8h] [rbp+48h] BYREF
  volatile signed __int32 *v25; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v26; // [rsp+B8h] [rbp+58h] BYREF

  v4 = 0;
  v24 = 0;
  v5 = 1;
  if ( !*(_DWORD *)(**((_QWORD **)a2 + 13) - 16LL)
    || (IdToken = OAuthTokenRequestBase::GetIdToken(a2, &v18),
        v4 = 1,
        v24 = 1,
        v7 = 1,
        IdToken::operator==((_QWORD *)*IdToken, *((_QWORD **)this + 38))) )
  {
    v7 = 0;
  }
  if ( (v4 & 1) != 0 )
  {
    v4 &= ~1u;
    v24 = v4;
    v8 = v19;
    if ( v19 )
    {
      if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
  }
  if ( v7 )
  {
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<TokenCache::Item>>::RemoveAll((char *)this + 96);
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<TokenCache::Item>>::RemoveAll((char *)this + 176);
    AuthenticationContext::UpdateUserInfo(this, a2);
  }
  v9 = (_WORD *)*OAuthTokenRequestBase::GetRefreshToken((__int64 *)a2, &v25);
  if ( !v9 || !*v9 )
    v5 = 0;
  CSecureString::~CSecureString((CSecureString *)&v25);
  if ( v5 )
  {
    v10 = (const unsigned __int16 *)*OAuthTokenRequestBase::GetRefreshToken((__int64 *)a2, &v18);
    if ( (*(unsigned int (__fastcall **)(const struct OAuthTokenRequestBase *))(*(_QWORD *)a2 + 48LL))(a2) )
    {
      v17 = (*(__int64 (__fastcall **)(const struct OAuthTokenRequestBase *))(*(_QWORD *)a2 + 48LL))(a2);
      InvalidCallException::InvalidCallException((InvalidCallException *)pExceptionObject, v17);
      throw (InvalidCallException *)pExceptionObject;
    }
    if ( *((_BYTE *)a2 + 56) )
    {
      v25 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
              (void *const *)&v25,
              0) )
        ATL::CSimpleStringT<unsigned short,0>::Empty(&v25);
      v11 = (const unsigned __int16 **)&v25;
      v12 = v4 | 2;
    }
    else
    {
      v11 = (const unsigned __int16 **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                         &v26,
                                         (__int64 *)a2 + 2);
      v12 = v4 | 4;
    }
    v24 = v12;
    AuthenticationContext::SetRefreshToken(this, *v11, v10);
    if ( (v12 & 4) != 0 )
    {
      LOBYTE(v12) = v12 & 0xFB;
      v13 = (_QWORD *)(v26 - 24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
    }
    if ( (v12 & 2) != 0 )
    {
      v14 = v25 - 6;
      if ( _InterlockedExchangeAdd(v25 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
    }
    CSecureString::~CSecureString((CSecureString *)&v18);
  }
  v21 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v22 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v23 = 0;
  v15 = (_QWORD *)(*(__int64 (__fastcall **)(const struct OAuthTokenRequestBase *, int *))(*(_QWORD *)a2 + 16LL))(
                    a2,
                    &v24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(&v22, v15);
  CSecureString::~CSecureString((CSecureString *)&v24);
  v23 = (*(__int64 (__fastcall **)(const struct OAuthTokenRequestBase *))(*(_QWORD *)a2 + 24LL))(a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    &v21,
    (_QWORD *)a2 + 2);
  TokenCache::Add((AuthenticationContext *)((char *)this + 88), (const struct TokenCache::Item *)&v21);
  CSecureString::~CSecureString((CSecureString *)&v22);
  v16 = (_QWORD *)(v21 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v21 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 8LL))(*v16);
}

```

## disassembly

```asm
0x140009518  mov     [rsp-38h+arg_0], rbx
0x14000951d  push    rbp
0x14000951e  push    rsi
0x14000951f  push    rdi
0x140009520  push    r12
0x140009522  push    r13
0x140009524  push    r14
0x140009526  push    r15
0x140009528  mov     rbp, rsp
0x14000952b  sub     rsp, 60h
0x14000952f  mov     rdi, rdx
0x140009532  mov     r15, rcx
0x140009535  xor     r13d, r13d
0x140009538  mov     ebx, r13d
0x14000953b  mov     [rbp+arg_8], ebx
0x14000953e  mov     rax, [rdx+68h]
0x140009542  mov     r8, [rax]
0x140009545  lea     r14d, [r13+1]
0x140009549  cmp     [r8-10h], r13d
0x14000954d  jz      short loc_140009577
0x14000954f  lea     rdx, [rbp+var_40]
0x140009553  mov     rcx, rdi
0x140009556  call    ?GetIdToken@OAuthTokenRequestBase@@QEBA?AV?$shared_ptr@VIdToken@@@std@@XZ; OAuthTokenRequestBase::GetIdToken(void)
0x14000955b  mov     ebx, r14d
0x14000955e  mov     [rbp+arg_8], ebx
0x140009561  mov     rdx, [r15+130h]
0x140009568  mov     rcx, [rax]
0x14000956b  call    ??8IdToken@@QEBA_NAEBV0@@Z; IdToken::operator==(IdToken const &)
0x140009570  test    al, al
0x140009572  mov     r12b, r14b
0x140009575  jz      short loc_14000957A
0x140009577  mov     r12b, r13b
0x14000957a  test    r14b, bl
0x14000957d  jz      short loc_1400095C5
0x14000957f  and     ebx, 0FFFFFFFEh
0x140009582  mov     [rbp+arg_8], ebx
0x140009585  mov     rsi, [rbp+var_38]
0x140009589  test    rsi, rsi
0x14000958c  jz      short loc_1400095C5
0x14000958e  or      eax, 0FFFFFFFFh
0x140009591  lock xadd [rsi+8], eax
0x140009596  cmp     eax, r14d
0x140009599  jnz     short loc_1400095C5
0x14000959b  mov     rax, [rsi]
0x14000959e  mov     rcx, rsi
0x1400095a1  mov     rax, [rax]
0x1400095a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095a9  or      eax, 0FFFFFFFFh
0x1400095ac  lock xadd [rsi+0Ch], eax
0x1400095b1  cmp     eax, r14d
0x1400095b4  jnz     short loc_1400095C5
0x1400095b6  mov     rax, [rsi]
0x1400095b9  mov     rcx, rsi
0x1400095bc  mov     rax, [rax+8]
0x1400095c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095c5  test    r12b, r12b
0x1400095c8  jz      short loc_1400095EA
0x1400095ca  lea     rcx, [r15+60h]
0x1400095ce  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VItem@TokenCache@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VItem@TokenCache@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::RemoveAll(void)
0x1400095d3  lea     rcx, [r15+0B0h]
0x1400095da  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VItem@TokenCache@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VItem@TokenCache@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::RemoveAll(void)
0x1400095df  mov     rdx, rdi; struct OAuthTokenRequestBase *
0x1400095e2  mov     rcx, r15; this
0x1400095e5  call    ?UpdateUserInfo@AuthenticationContext@@AEAAXAEBVOAuthTokenRequestBase@@@Z; AuthenticationContext::UpdateUserInfo(OAuthTokenRequestBase const &)
0x1400095ea  lea     rdx, [rbp+arg_10]
0x1400095ee  mov     rcx, rdi
0x1400095f1  call    ?GetRefreshToken@OAuthTokenRequestBase@@QEBA?AVCSecureString@@XZ; OAuthTokenRequestBase::GetRefreshToken(void)
0x1400095f6  mov     rcx, [rax]
0x1400095f9  test    rcx, rcx
0x1400095fc  jz      short loc_140009604
0x1400095fe  cmp     [rcx], r13w
0x140009602  jnz     short loc_140009607
0x140009604  mov     r14b, r13b
0x140009607  lea     rcx, [rbp+arg_10]; this
0x14000960b  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140009610  lea     r12, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140009617  test    r14b, r14b
0x14000961a  jz      loc_14000970E
0x140009620  lea     rdx, [rbp+var_40]
0x140009624  mov     rcx, rdi
0x140009627  call    ?GetRefreshToken@OAuthTokenRequestBase@@QEBA?AVCSecureString@@XZ; OAuthTokenRequestBase::GetRefreshToken(void)
0x14000962c  nop
0x14000962d  mov     rsi, [rax]
0x140009630  mov     rax, [rdi]
0x140009633  mov     rcx, rdi
0x140009636  mov     rax, [rax+30h]
0x14000963a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000963f  test    eax, eax
0x140009641  jnz     loc_1400097E5
0x140009647  cmp     [rdi+38h], r13b
0x14000964b  jz      short loc_14000968A
0x14000964d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140009654  mov     rcx, r12
0x140009657  mov     rax, [rax+18h]
0x14000965b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009660  add     rax, 18h
0x140009664  mov     [rbp+arg_10], rax
0x140009668  xor     edx, edx
0x14000966a  lea     rcx, [rbp+arg_10]
0x14000966e  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140009673  test    al, al
0x140009675  jnz     short loc_140009681
0x140009677  lea     rcx, [rbp+arg_10]
0x14000967b  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140009680  nop
0x140009681  lea     rax, [rbp+arg_10]
0x140009685  or      ebx, 2
0x140009688  jmp     short loc_14000969B
0x14000968a  lea     rdx, [rdi+10h]
0x14000968e  lea     rcx, [rbp+arg_18]
0x140009692  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140009697  nop
0x140009698  or      ebx, 4
0x14000969b  mov     [rbp+arg_8], ebx
0x14000969e  mov     r8, rsi; unsigned __int16 *
0x1400096a1  mov     rdx, [rax]; unsigned __int16 *
0x1400096a4  mov     rcx, r15; this
0x1400096a7  call    ?SetRefreshToken@AuthenticationContext@@QEAAXPEBG0@Z; AuthenticationContext::SetRefreshToken(ushort const *,ushort const *)
0x1400096ac  nop
0x1400096ad  test    bl, 4
0x1400096b0  jz      short loc_1400096DA
0x1400096b2  and     ebx, 0FFFFFFFBh
0x1400096b5  mov     rdx, [rbp+arg_18]
0x1400096b9  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400096bd  or      eax, 0FFFFFFFFh
0x1400096c0  lock xadd [rdx+10h], eax
0x1400096c5  sub     eax, 1
0x1400096c8  jg      short loc_1400096DA
0x1400096ca  mov     rcx, [rdx]
0x1400096cd  mov     rax, [rcx]
0x1400096d0  mov     rax, [rax+8]
0x1400096d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400096d9  nop
0x1400096da  test    bl, 2
0x1400096dd  jz      short loc_140009704
0x1400096df  mov     rdx, [rbp+arg_10]
0x1400096e3  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400096e7  or      eax, 0FFFFFFFFh
0x1400096ea  lock xadd [rdx+10h], eax
0x1400096ef  sub     eax, 1
0x1400096f2  jg      short loc_140009704
0x1400096f4  mov     rcx, [rdx]
0x1400096f7  mov     rax, [rcx]
0x1400096fa  mov     rax, [rax+8]
0x1400096fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009703  nop
0x140009704  lea     rcx, [rbp+var_40]; this
0x140009708  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x14000970d  nop
0x14000970e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140009715  mov     rcx, r12
0x140009718  mov     rax, [rax+18h]
0x14000971c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009721  add     rax, 18h
0x140009725  mov     [rbp+var_20], rax
0x140009729  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140009730  mov     rcx, r12
0x140009733  mov     rax, [rax+18h]
0x140009737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000973c  add     rax, 18h
0x140009740  mov     [rbp+var_18], rax
0x140009744  mov     [rbp+var_10], r13
0x140009748  mov     rax, [rdi]
0x14000974b  lea     rdx, [rbp+arg_8]
0x14000974f  mov     rcx, rdi
0x140009752  mov     rax, [rax+10h]
0x140009756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000975b  nop
0x14000975c  mov     rdx, rax
0x14000975f  lea     rcx, [rbp+var_18]
0x140009763  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140009768  nop
0x140009769  lea     rcx, [rbp+arg_8]; this
0x14000976d  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140009772  mov     rax, [rdi]
0x140009775  mov     rcx, rdi
0x140009778  mov     rax, [rax+18h]
0x14000977c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009781  mov     [rbp+var_10], rax
0x140009785  lea     rdx, [rdi+10h]
0x140009789  lea     rcx, [rbp+var_20]
0x14000978d  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140009792  lea     rcx, [r15+58h]; this
0x140009796  lea     rdx, [rbp+var_20]; struct TokenCache::Item *
0x14000979a  call    ?Add@TokenCache@@QEAAXAEBVItem@1@@Z; TokenCache::Add(TokenCache::Item const &)
0x14000979f  nop
0x1400097a0  lea     rcx, [rbp+var_18]; this
0x1400097a4  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x1400097a9  mov     rdx, [rbp+var_20]
0x1400097ad  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400097b1  or      eax, 0FFFFFFFFh
0x1400097b4  lock xadd [rdx+10h], eax
0x1400097b9  sub     eax, 1
0x1400097bc  jg      short loc_1400097CD
0x1400097be  mov     rcx, [rdx]
0x1400097c1  mov     rax, [rcx]
0x1400097c4  mov     rax, [rax+8]
0x1400097c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400097cd  mov     rbx, [rsp+60h+arg_0]
0x1400097d5  add     rsp, 60h
0x1400097d9  pop     r15
0x1400097db  pop     r14
0x1400097dd  pop     r13
0x1400097df  pop     r12
0x1400097e1  pop     rdi
0x1400097e2  pop     rsi
0x1400097e3  pop     rbp
0x1400097e4  retn
0x1400097e5  mov     rax, [rdi]
0x1400097e8  mov     rcx, rdi
0x1400097eb  mov     rax, [rax+30h]
0x1400097ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400097f4  mov     edx, eax; unsigned int
0x1400097f6  lea     rcx, [rbp+pExceptionObject]; this
0x1400097fa  call    ??0InvalidCallException@@QEAA@K@Z; InvalidCallException::InvalidCallException(ulong)
0x1400097ff  lea     rdx, _TI3?AVInvalidCallException@@; pThrowInfo
0x140009806  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000980a  call    _CxxThrowException_0
```
