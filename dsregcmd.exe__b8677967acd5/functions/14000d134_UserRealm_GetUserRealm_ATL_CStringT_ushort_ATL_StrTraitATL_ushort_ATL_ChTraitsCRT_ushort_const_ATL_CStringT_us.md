# UserRealm::GetUserRealm(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,AuthenticationContext const &)

- ea: `0x14000d134`
- end: `0x14000d307`
- name: `?GetUserRealm@UserRealm@@SA?AV?$unique_ptr@VUserRealm@@U?$default_delete@VUserRealm@@@std@@@std@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00AEBVAuthenticationContext@@@Z`
- size: `467`
- prototype: `UserRealm **__fastcall(UserRealm **, _QWORD *, _QWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14000ab04`

## callees

- `0x140001814`
- `0x140005c80`
- `0x1400061dc`
- `0x140007bf8`
- `0x14000cdb0`
- `0x14000d134`
- `0x14000d384`
- `0x14000d9a8`
- `0x14000f058`
- `0x14000f0f4`
- `0x14000f170`
- `0x14000f1b8`
- `0x140030010`

## string_xrefs

- `0x14000d1f0`: `onecore\ds\security\dsreg\win32\adal.native\userrealm.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
UserRealm **__fastcall UserRealm::GetUserRealm(UserRealm **a1, _QWORD *a2, _QWORD *a3, _QWORD *a4, __int64 a5)
{
  UserRealm *v9; // rax
  _QWORD *v10; // rdx
  _QWORD *v11; // rdx
  volatile signed __int32 *v12; // rdx
  volatile signed __int32 *v14; // [rsp+28h] [rbp-28h] BYREF
  UserRealm *v15; // [rsp+30h] [rbp-20h] BYREF
  __int64 v16; // [rsp+38h] [rbp-18h] BYREF
  void *v17; // [rsp+40h] [rbp-10h] BYREF
  __int64 v18; // [rsp+48h] [rbp-8h]

  Url::Url((Url *)&v17);
  Url::CreateUrl((__int64)&v17, a4);
  v14 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v14,
          (__int64)L"1.0") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v14, L"1.0", 3);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v16,
    *(_QWORD *)(v18 + 8),
    (*(_QWORD *)(v18 + 24) + 2LL * *(unsigned int *)(v18 + 32) - *(_QWORD *)(v18 + 8)) >> 1);
  v9 = (UserRealm *)operator new(0x48u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\userrealm.cpp");
  v15 = v9;
  if ( v9 )
    v9 = UserRealm::UserRealm(v9);
  *a1 = v9;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)v9 + 2,
    &v16);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)*a1 + 1,
    &v14);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)*a1 + 4,
    a3);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(*a1, a2);
  UserRealm::SendRequest(*a1, &v15, a5);
  UserRealm::ParseResponse(*a1, &v15);
  v10 = (_QWORD *)((char *)v15 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)v15 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
  v11 = (_QWORD *)(v16 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v16 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
  v12 = v14 - 6;
  if ( _InterlockedDecrement(v14 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12);
  Url::~Url(&v17);
  return a1;
}

```

## disassembly

```asm
0x14000d134  mov     [rsp-18h+arg_8], rbx
0x14000d139  mov     [rsp-18h+arg_10], rsi
0x14000d13e  mov     [rsp-18h+arg_0], rcx
0x14000d143  push    rbp
0x14000d144  push    rdi
0x14000d145  push    r14
0x14000d147  mov     rbp, rsp
0x14000d14a  sub     rsp, 50h
0x14000d14e  mov     rbx, r9
0x14000d151  mov     rsi, r8
0x14000d154  mov     r14, rdx
0x14000d157  mov     rdi, rcx
0x14000d15a  mov     [rbp+var_30], 0
0x14000d161  lea     rcx, [rbp+var_10]; this
0x14000d165  call    ??0Url@@QEAA@XZ; Url::Url(void)
0x14000d16a  nop
0x14000d16b  mov     rdx, rbx
0x14000d16e  lea     rcx, [rbp+var_10]
0x14000d172  call    ?CreateUrl@Url@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Url::CreateUrl(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000d177  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000d17e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000d185  mov     rax, [rax+18h]
0x14000d189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d18e  add     rax, 18h
0x14000d192  mov     [rbp+var_28], rax
0x14000d196  lea     rdx, a10; "1.0"
0x14000d19d  lea     rcx, [rbp+var_28]
0x14000d1a1  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000d1a6  test    al, al
0x14000d1a8  jnz     short loc_14000D1C1
0x14000d1aa  mov     r8d, 3
0x14000d1b0  lea     rdx, a10; "1.0"
0x14000d1b7  lea     rcx, [rbp+var_28]
0x14000d1bb  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000d1c0  nop
0x14000d1c1  mov     rax, [rbp+var_8]
0x14000d1c5  mov     rdx, [rax+8]
0x14000d1c9  mov     ecx, [rax+20h]
0x14000d1cc  mov     rax, [rax+18h]
0x14000d1d0  lea     r8, [rax+rcx*2]
0x14000d1d4  sub     r8, rdx
0x14000d1d7  sar     r8, 1
0x14000d1da  lea     rcx, [rbp+var_18]
0x14000d1de  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int)
0x14000d1e3  mov     [rbp+var_30], 2
0x14000d1ea  mov     r9d, 3Bh ; ';'; int
0x14000d1f0  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14000d1f7  lea     edx, [r9-3Ah]; int
0x14000d1fb  lea     ecx, [rdx+47h]; unsigned __int64
0x14000d1fe  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14000d203  mov     [rbp+var_20], rax
0x14000d207  test    rax, rax
0x14000d20a  jz      short loc_14000D215
0x14000d20c  mov     rcx, rax; this
0x14000d20f  call    ??0UserRealm@@QEAA@XZ; UserRealm::UserRealm(void)
0x14000d214  nop
0x14000d215  mov     [rdi], rax
0x14000d218  mov     [rbp+var_30], 6
0x14000d21f  lea     rcx, [rax+10h]
0x14000d223  lea     rdx, [rbp+var_18]
0x14000d227  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000d22c  mov     rcx, [rdi]
0x14000d22f  add     rcx, 8
0x14000d233  lea     rdx, [rbp+var_28]
0x14000d237  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000d23c  mov     rcx, [rdi]
0x14000d23f  add     rcx, 20h ; ' '
0x14000d243  mov     rdx, rsi
0x14000d246  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000d24b  mov     rdx, r14
0x14000d24e  mov     rcx, [rdi]
0x14000d251  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000d256  mov     r8, [rbp+arg_20]
0x14000d25a  lea     rdx, [rbp+var_20]
0x14000d25e  mov     rcx, [rdi]
0x14000d261  call    ?SendRequest@UserRealm@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVAuthenticationContext@@@Z; UserRealm::SendRequest(AuthenticationContext const &)
0x14000d266  nop
0x14000d267  lea     rdx, [rbp+var_20]
0x14000d26b  mov     rcx, [rdi]
0x14000d26e  call    ?ParseResponse@UserRealm@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; UserRealm::ParseResponse(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000d273  nop
0x14000d274  mov     rdx, [rbp+var_20]
0x14000d278  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000d27c  or      ebx, 0FFFFFFFFh
0x14000d27f  mov     eax, ebx
0x14000d281  lock xadd [rdx+10h], eax
0x14000d286  add     eax, ebx
0x14000d288  test    eax, eax
0x14000d28a  jg      short loc_14000D29C
0x14000d28c  mov     rcx, [rdx]
0x14000d28f  mov     rax, [rcx]
0x14000d292  mov     rax, [rax+8]
0x14000d296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d29b  nop
0x14000d29c  mov     rdx, [rbp+var_18]
0x14000d2a0  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000d2a4  mov     eax, ebx
0x14000d2a6  lock xadd [rdx+10h], eax
0x14000d2ab  add     eax, ebx
0x14000d2ad  test    eax, eax
0x14000d2af  jg      short loc_14000D2C1
0x14000d2b1  mov     rcx, [rdx]
0x14000d2b4  mov     rax, [rcx]
0x14000d2b7  mov     rax, [rax+8]
0x14000d2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d2c0  nop
0x14000d2c1  mov     rdx, [rbp+var_28]
0x14000d2c5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000d2c9  mov     eax, ebx
0x14000d2cb  lock xadd [rdx+10h], eax
0x14000d2d0  add     eax, ebx
0x14000d2d2  test    eax, eax
0x14000d2d4  jg      short loc_14000D2E6
0x14000d2d6  mov     rcx, [rdx]
0x14000d2d9  mov     rax, [rcx]
0x14000d2dc  mov     rax, [rax+8]
0x14000d2e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d2e5  nop
0x14000d2e6  lea     rcx, [rbp+var_10]; this
0x14000d2ea  call    ??1Url@@QEAA@XZ; Url::~Url(void)
0x14000d2ef  mov     rax, rdi
0x14000d2f2  lea     r11, [rsp+50h+var_s0]
0x14000d2f7  mov     rbx, [r11+28h]
0x14000d2fb  mov     rsi, [r11+30h]
0x14000d2ff  mov     rsp, r11
0x14000d302  pop     r14
0x14000d304  pop     rdi
0x14000d305  pop     rbp
0x14000d306  retn
```
