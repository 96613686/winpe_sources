# WSTrustResponse::WSTrustResponse(WebRequest *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ILogContext * const)

- ea: `0x140026f30`
- end: `0x140027394`
- name: `??0WSTrustResponse@@QEAA@PEAVWebRequest@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAVILogContext@@@Z`
- size: `1124`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1400176b4`

## callees

- `0x140005458`
- `0x14000579c`
- `0x140005c80`
- `0x1400061dc`
- `0x140007bf8`
- `0x14000bbf0`
- `0x14000caac`
- `0x14000cacc`
- `0x140022b14`
- `0x140026f30`
- `0x140027410`
- `0x140027534`
- `0x14002c3e8`
- `0x140030010`

## string_xrefs

- `0x140027204`: `urn:ietf:params:oauth:token-type:jwt`
- `0x14002721f`: `urn:ietf:params:oauth:token-type:jwt`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WSTrustResponse::WSTrustResponse(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v6; // r12
  _WORD *v7; // r13
  __int64 v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // rdx
  __int64 v11; // rax
  _QWORD *v12; // rdx
  __int64 v13; // rax
  _QWORD *v14; // rdx
  __int64 v15; // rax
  _QWORD *v16; // rdx
  __int64 v17; // rdx
  _QWORD *v18; // rax
  char v19; // di
  _QWORD *v20; // rdx
  _QWORD *v21; // rdx
  __int64 v23; // [rsp+28h] [rbp-70h] BYREF
  _BYTE v24[8]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v25; // [rsp+38h] [rbp-60h] BYREF
  __int64 v26; // [rsp+40h] [rbp-58h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+48h] [rbp-50h] BYREF

  *(_QWORD *)a1 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_QWORD *)(a1 + 16) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_QWORD *)(a1 + 24) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_QWORD *)(a1 + 32) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v6 = (_QWORD *)(a1 + 40);
  v26 = a1 + 40;
  *(_QWORD *)(a1 + 40) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_QWORD *)(a1 + 48) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v7 = (_WORD *)(a1 + 8);
  v25 = a1 + 8;
  *(_WORD *)(a1 + 8) = *(_WORD *)(a2 + 92);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    a1 + 48,
    a3);
  v8 = WebRequest::ResponseText(a2, &v23);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(a1, v8);
  CSecureString::~CSecureString((CSecureString *)&v23);
  if ( !*(_DWORD *)(*(_QWORD *)a1 - 16LL) )
  {
    Exception::Exception((Exception *)pExceptionObject, -894894078);
    throw (Exception *)pExceptionObject;
  }
  v9 = WSTrustResponse::ExtractErrorMessage(a1, &v23);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    a1 + 40,
    v9);
  v10 = (_QWORD *)(v23 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v23 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
  if ( !*(_DWORD *)(*v6 - 16LL) )
  {
    v23 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                             &v23,
                             L"urn:oasis:names:tc:SAML:1.0:assertion") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v23, L"urn:oasis:names:tc:SAML:1.0:assertion", 37);
    v11 = WSTrustResponse::ExtractToken(a1, v24, &v23);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      a1 + 24,
      v11);
    CSecureString::~CSecureString((CSecureString *)v24);
    v12 = (_QWORD *)(v23 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v23 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 8LL))(*v12);
    v23 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                             &v23,
                             L"urn:oasis:names:tc:SAML:2.0:assertion") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v23, L"urn:oasis:names:tc:SAML:2.0:assertion", 37);
    v13 = WSTrustResponse::ExtractToken(a1, v24, &v23);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      a1 + 16,
      v13);
    CSecureString::~CSecureString((CSecureString *)v24);
    v14 = (_QWORD *)(v23 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v23 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
    v23 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                             &v23,
                             L"urn:ietf:params:oauth:token-type:jwt") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v23, L"urn:ietf:params:oauth:token-type:jwt", 36);
    v15 = WSTrustResponse::ExtractToken(a1, v24, &v23);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      a1 + 32,
      v15);
    CSecureString::~CSecureString((CSecureString *)v24);
    v16 = (_QWORD *)(v23 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v23 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 8LL))(*v16);
  }
  if ( *v7 != 200 && !*(_DWORD *)(*v6 - 16LL) )
  {
    if ( *(_DWORD *)(*(_QWORD *)a1 - 16LL) )
    {
      v18 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v26,
              (__int64 *)a1);
      v19 = 2;
    }
    else
    {
      v17 = Utils::TranslateHttpErrorCode((unsigned __int16)*v7);
      v18 = (_QWORD *)Exception::FormatErrorMessage(&v25, v17);
      v19 = 1;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(v6, v18);
    if ( (v19 & 2) != 0 )
    {
      v19 &= ~2u;
      v20 = (_QWORD *)(v26 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v26 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
    }
    if ( (v19 & 1) != 0 )
    {
      v21 = (_QWORD *)(v25 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v25 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 8LL))(*v21);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140026f30  mov     rax, rsp
0x140026f33  mov     [rax+20h], r9
0x140026f37  mov     [rax+10h], rdx
0x140026f3b  mov     [rax+8], rcx
0x140026f3f  push    rbx
0x140026f40  push    rsi
0x140026f41  push    rdi
0x140026f42  push    r12
0x140026f44  push    r13
0x140026f46  push    r14
0x140026f48  push    r15
0x140026f4a  sub     rsp, 60h
0x140026f4e  mov     rdi, r8
0x140026f51  mov     rsi, rdx
0x140026f54  mov     r15, rcx
0x140026f57  xor     r14d, r14d
0x140026f5a  mov     [rax-78h], r14d
0x140026f5e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140026f65  lea     r13, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140026f6c  mov     rcx, r13
0x140026f6f  mov     rax, [rax+18h]
0x140026f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f78  add     rax, 18h
0x140026f7c  mov     [r15], rax
0x140026f7f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140026f86  mov     rcx, r13
0x140026f89  mov     rax, [rax+18h]
0x140026f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f92  add     rax, 18h
0x140026f96  mov     [r15+10h], rax
0x140026f9a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140026fa1  mov     rcx, r13
0x140026fa4  mov     rax, [rax+18h]
0x140026fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026fad  add     rax, 18h
0x140026fb1  mov     [r15+18h], rax
0x140026fb5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140026fbc  mov     rcx, r13
0x140026fbf  mov     rax, [rax+18h]
0x140026fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026fc8  add     rax, 18h
0x140026fcc  mov     [r15+20h], rax
0x140026fd0  lea     r12, [r15+28h]
0x140026fd4  mov     [rsp+98h+var_58], r12
0x140026fd9  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140026fe0  mov     rcx, r13
0x140026fe3  mov     rax, [rax+18h]
0x140026fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026fec  add     rax, 18h
0x140026ff0  mov     [r12], rax
0x140026ff4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140026ffb  mov     rcx, r13
0x140026ffe  mov     rax, [rax+18h]
0x140027002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027007  add     rax, 18h
0x14002700b  mov     [r15+30h], rax
0x14002700f  lea     r13, [r15+8]
0x140027013  mov     [rsp+98h+var_60], r13
0x140027018  movzx   eax, word ptr [rsi+5Ch]
0x14002701c  mov     [r13+0], ax
0x140027021  mov     rdx, rdi
0x140027024  lea     rcx, [r15+30h]
0x140027028  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14002702d  lea     rdx, [rsp+98h+var_70]
0x140027032  mov     rcx, rsi
0x140027035  call    ?ResponseText@WebRequest@@QEBA?AVCSecureString@@XZ; WebRequest::ResponseText(void)
0x14002703a  nop
0x14002703b  mov     rdx, rax
0x14002703e  mov     rcx, r15
0x140027041  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140027046  nop
0x140027047  lea     rcx, [rsp+98h+var_70]; this
0x14002704c  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140027051  nop
0x140027052  mov     rax, [r15]
0x140027055  cmp     [rax-10h], r14d
0x140027059  jz      loc_140027372
0x14002705f  lea     rdx, [rsp+98h+var_70]
0x140027064  mov     rcx, r15
0x140027067  call    ?ExtractErrorMessage@WSTrustResponse@@AEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; WSTrustResponse::ExtractErrorMessage(void)
0x14002706c  nop
0x14002706d  mov     rdx, rax
0x140027070  mov     rcx, r12
0x140027073  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140027078  nop
0x140027079  mov     rdx, [rsp+98h+var_70]
0x14002707e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140027082  or      ebx, 0FFFFFFFFh
0x140027085  mov     eax, ebx
0x140027087  lock xadd [rdx+10h], eax
0x14002708c  add     eax, ebx
0x14002708e  test    eax, eax
0x140027090  jg      short loc_1400270A1
0x140027092  mov     rcx, [rdx]
0x140027095  mov     rax, [rcx]
0x140027098  mov     rax, [rax+8]
0x14002709c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400270a1  mov     rax, [r12]
0x1400270a5  cmp     [rax-10h], r14d
0x1400270a9  jnz     loc_140027282
0x1400270af  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400270b6  lea     rdi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400270bd  mov     rcx, rdi
0x1400270c0  mov     rax, [rax+18h]
0x1400270c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400270c9  add     rax, 18h
0x1400270cd  mov     [rsp+98h+var_70], rax
0x1400270d2  lea     rdx, aUrnOasisNamesT; "urn:oasis:names:tc:SAML:1.0:assertion"
0x1400270d9  lea     rcx, [rsp+98h+var_70]
0x1400270de  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1400270e3  test    al, al
0x1400270e5  jnz     short loc_1400270FF
0x1400270e7  mov     r8d, 25h ; '%'
0x1400270ed  lea     rdx, aUrnOasisNamesT; "urn:oasis:names:tc:SAML:1.0:assertion"
0x1400270f4  lea     rcx, [rsp+98h+var_70]
0x1400270f9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400270fe  nop
0x1400270ff  lea     r8, [rsp+98h+var_70]
0x140027104  lea     rdx, [rsp+98h+var_68]
0x140027109  mov     rcx, r15
0x14002710c  call    ?ExtractToken@WSTrustResponse@@QEBA?AVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WSTrustResponse::ExtractToken(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140027111  nop
0x140027112  mov     rdx, rax
0x140027115  lea     rcx, [r15+18h]
0x140027119  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14002711e  nop
0x14002711f  lea     rcx, [rsp+98h+var_68]; this
0x140027124  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140027129  nop
0x14002712a  mov     rdx, [rsp+98h+var_70]
0x14002712f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140027133  mov     eax, ebx
0x140027135  lock xadd [rdx+10h], eax
0x14002713a  add     eax, ebx
0x14002713c  test    eax, eax
0x14002713e  jg      short loc_14002714F
0x140027140  mov     rcx, [rdx]
0x140027143  mov     rax, [rcx]
0x140027146  mov     rax, [rax+8]
0x14002714a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002714f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140027156  mov     rcx, rdi
0x140027159  mov     rax, [rax+18h]
0x14002715d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027162  add     rax, 18h
0x140027166  mov     [rsp+98h+var_70], rax
0x14002716b  lea     rdx, aUrnOasisNamesT_0; "urn:oasis:names:tc:SAML:2.0:assertion"
0x140027172  lea     rcx, [rsp+98h+var_70]
0x140027177  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14002717c  test    al, al
0x14002717e  jnz     short loc_140027198
0x140027180  mov     r8d, 25h ; '%'
0x140027186  lea     rdx, aUrnOasisNamesT_0; "urn:oasis:names:tc:SAML:2.0:assertion"
0x14002718d  lea     rcx, [rsp+98h+var_70]
0x140027192  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140027197  nop
0x140027198  lea     r8, [rsp+98h+var_70]
0x14002719d  lea     rdx, [rsp+98h+var_68]
0x1400271a2  mov     rcx, r15
0x1400271a5  call    ?ExtractToken@WSTrustResponse@@QEBA?AVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WSTrustResponse::ExtractToken(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400271aa  nop
0x1400271ab  mov     rdx, rax
0x1400271ae  lea     rcx, [r15+10h]
0x1400271b2  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400271b7  nop
0x1400271b8  lea     rcx, [rsp+98h+var_68]; this
0x1400271bd  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x1400271c2  nop
0x1400271c3  mov     rdx, [rsp+98h+var_70]
0x1400271c8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400271cc  mov     eax, ebx
0x1400271ce  lock xadd [rdx+10h], eax
0x1400271d3  add     eax, ebx
0x1400271d5  test    eax, eax
0x1400271d7  jg      short loc_1400271E8
0x1400271d9  mov     rcx, [rdx]
0x1400271dc  mov     rax, [rcx]
0x1400271df  mov     rax, [rax+8]
0x1400271e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400271e8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400271ef  mov     rcx, rdi
0x1400271f2  mov     rax, [rax+18h]
0x1400271f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400271fb  add     rax, 18h
0x1400271ff  mov     [rsp+98h+var_70], rax
0x140027204  lea     rdx, aUrnIetfParamsO_0; "urn:ietf:params:oauth:token-type:jwt"
0x14002720b  lea     rcx, [rsp+98h+var_70]
0x140027210  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140027215  test    al, al
0x140027217  jnz     short loc_140027231
0x140027219  mov     r8d, 24h ; '$'
0x14002721f  lea     rdx, aUrnIetfParamsO_0; "urn:ietf:params:oauth:token-type:jwt"
0x140027226  lea     rcx, [rsp+98h+var_70]
0x14002722b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140027230  nop
0x140027231  lea     r8, [rsp+98h+var_70]
0x140027236  lea     rdx, [rsp+98h+var_68]
0x14002723b  mov     rcx, r15
0x14002723e  call    ?ExtractToken@WSTrustResponse@@QEBA?AVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WSTrustResponse::ExtractToken(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140027243  nop
0x140027244  mov     rdx, rax
0x140027247  lea     rcx, [r15+20h]
0x14002724b  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140027250  nop
0x140027251  lea     rcx, [rsp+98h+var_68]; this
0x140027256  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x14002725b  nop
0x14002725c  mov     rdx, [rsp+98h+var_70]
0x140027261  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140027265  mov     eax, ebx
0x140027267  lock xadd [rdx+10h], eax
0x14002726c  add     eax, ebx
0x14002726e  test    eax, eax
0x140027270  jg      short loc_140027282
0x140027272  mov     rcx, [rdx]
0x140027275  mov     rax, [rcx]
0x140027278  mov     rax, [rax+8]
0x14002727c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027281  nop
0x140027282  jmp     short loc_14002729C
0x140027284  xor     r14d, r14d
0x140027287  or      ebx, 0FFFFFFFFh
0x14002728a  mov     r15, [rsp+98h+arg_0]
0x140027292  mov     r13, [rsp+98h+var_60]
0x140027297  mov     r12, [rsp+98h+var_58]
0x14002729c  mov     eax, 0C8h
0x1400272a1  cmp     [r13+0], ax
0x1400272a6  jz      loc_14002735F
0x1400272ac  mov     rax, [r12]
0x1400272b0  cmp     [rax-10h], r14d
0x1400272b4  jnz     loc_14002735F
0x1400272ba  mov     rax, [r15]
0x1400272bd  cmp     [rax-10h], r14d
0x1400272c1  jnz     short loc_1400272E1
0x1400272c3  movzx   ecx, word ptr [r13+0]; int
0x1400272c8  call    ?TranslateHttpErrorCode@Utils@@SAKH@Z; Utils::TranslateHttpErrorCode(int)
0x1400272cd  mov     edx, eax
0x1400272cf  lea     rcx, [rsp+98h+var_60]
0x1400272d4  call    ?FormatErrorMessage@Exception@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@K@Z; Exception::FormatErrorMessage(ulong)
0x1400272d9  nop
0x1400272da  mov     edi, 1
0x1400272df  jmp     short loc_1400272F4
0x1400272e1  mov     rdx, r15
0x1400272e4  lea     rcx, [rsp+98h+var_58]
0x1400272e9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400272ee  nop
0x1400272ef  mov     edi, 2
0x1400272f4  mov     [rsp+98h+var_78], edi
0x1400272f8  mov     rdx, rax
0x1400272fb  mov     rcx, r12
0x1400272fe  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140027303  nop
0x140027304  test    dil, 2
0x140027308  jz      short loc_140027333
0x14002730a  and     edi, 0FFFFFFFDh
0x14002730d  mov     rdx, [rsp+98h+var_58]
0x140027312  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140027316  mov     eax, ebx
0x140027318  lock xadd [rdx+10h], eax
0x14002731d  add     eax, ebx
0x14002731f  test    eax, eax
0x140027321  jg      short loc_140027333
0x140027323  mov     rcx, [rdx]
0x140027326  mov     rax, [rcx]
0x140027329  mov     rax, [rax+8]
0x14002732d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027332  nop
0x140027333  test    dil, 1
0x140027337  jz      short loc_14002735F
0x140027339  mov     rdx, [rsp+98h+var_60]
0x14002733e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140027342  mov     eax, ebx
0x140027344  lock xadd [rdx+10h], eax
0x140027349  add     eax, ebx
0x14002734b  test    eax, eax
0x14002734d  jg      short loc_14002735F
0x14002734f  mov     rcx, [rdx]
0x140027352  mov     rax, [rcx]
0x140027355  mov     rax, [rax+8]
0x140027359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002735e  nop
0x14002735f  mov     rax, r15
0x140027362  add     rsp, 60h
0x140027366  pop     r15
0x140027368  pop     r14
0x14002736a  pop     r13
0x14002736c  pop     r12
0x14002736e  pop     rdi
0x14002736f  pop     rsi
0x140027370  pop     rbx
0x140027371  retn
0x140027372  mov     edx, 0CAA90002h; unsigned int
0x140027377  lea     rcx, [rsp+98h+pExceptionObject]; this
0x14002737c  call    ??0Exception@@QEAA@K@Z; Exception::Exception(ulong)
0x140027381  lea     rdx, _TI1?AVException@@; pThrowInfo
0x140027388  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x14002738d  call    _CxxThrowException_0
```
