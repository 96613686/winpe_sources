# AggregatedTokenRequest::UseWindowsIntegratedAuthEnterprise(ushort const *)

- ea: `0x14000b7e0`
- end: `0x14000baef`
- name: `?UseWindowsIntegratedAuthEnterprise@AggregatedTokenRequest@@QEAAXPEBG@Z`
- size: `783`
- prototype: `void __fastcall(AggregatedTokenRequest *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006f24`

## callees

- `0x140001814`
- `0x140005458`
- `0x14000579c`
- `0x140005c80`
- `0x1400061dc`
- `0x1400081d8`
- `0x14000a28c`
- `0x14000b0fc`
- `0x14000b7e0`
- `0x14000c7d8`
- `0x14000e000`
- `0x14001425c`
- `0x140016a04`
- `0x14002c3e8`
- `0x140030010`

## string_xrefs

- `0x14000b8c5`: `onecore\ds\security\dsreg\win32\adal.native\aggregatedtokenrequest.cpp`
- `0x14000b85a`: `AggregatedTokenRequest::UseWindowsIntegratedAuthEnterprise`
- `0x14000b88c`: `https://%s/adfs/services/trust/mex`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall AggregatedTokenRequest::UseWindowsIntegratedAuthEnterprise(
        AggregatedTokenRequest *this,
        const unsigned __int16 *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  _QWORD *v7; // rsi
  __int64 v8; // rcx
  FailedTokenRequest *v9; // rax
  __int64 *v10; // rax
  void *v11; // [rsp+30h] [rbp-98h] BYREF
  __int64 v12; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v13[8]; // [rsp+40h] [rbp-88h] BYREF
  __int64 v14[2]; // [rsp+48h] [rbp-80h] BYREF
  __int64 v15[4]; // [rsp+58h] [rbp-70h] BYREF
  const Exception *v16; // [rsp+78h] [rbp-50h] BYREF
  _BYTE v17[16]; // [rsp+80h] [rbp-48h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+90h] [rbp-38h] BYREF
  void *v20; // [rsp+E0h] [rbp+18h] BYREF
  FailedTokenRequest *v21; // [rsp+E8h] [rbp+20h] BYREF

  v14[0] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v14[1] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v15[0] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  Log::Verbose(this, L"AggregatedTokenRequest::UseWindowsIntegratedAuthEnterprise");
  if ( *((_QWORD *)this + 4) )
  {
    InvalidCallException::InvalidCallException((InvalidCallException *)v17, -895418313);
    throw (InvalidCallException *)v17;
  }
  try
  {
    if ( !a2 || !*a2 )
    {
      Log::Verbose(this, L"Error, federationServer MUST be provided.");
      InvalidCallException::InvalidCallException((InvalidCallException *)pExceptionObject, -2147024809);
      throw (InvalidCallException *)pExceptionObject;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      v14,
      L"https://%s/adfs/services/trust/mex",
      a2);
    v4 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
           &v20,
           v14);
    AggregatedTokenRequest::ParseMexToRealmInfo(this, v4, v13);
    v5 = operator new(0x90u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\aggregatedtokenrequest.cpp");
    v6 = v5;
    v20 = v5;
    if ( v5 )
    {
      OAuthTokenRequestBase::OAuthTokenRequestBase(
        (__int64)v5,
        *((_QWORD *)this + 1),
        (__int64)this + 16,
        (__int64)this + 24);
      *v6 = &WSTrustTokenRequest::`vftable';
    }
    else
    {
      v6 = 0;
    }
    v15[1] = (__int64)v6;
    v15[2] = (__int64)&v20;
    v20 = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            &v20,
            (__int64)&dword_14003353C) )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v20, &dword_14003353C, 0);
    v15[3] = (__int64)&v12;
    v7 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
           &v12,
           v15);
    v11 = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            &v11,
            (__int64)&dword_14003353C) )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v11, &dword_14003353C, 0);
    v21 = (FailedTokenRequest *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v21,
            (__int64)&dword_14003353C) )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v21, &dword_14003353C, 0);
    WSTrustTokenRequest::AcquireToken((__int64)v6, &v21, &v11, v7, (__int64 *)&v20, 0);
    CSecureString::~CSecureString((CSecureString *)&v21);
    CSecureString::~CSecureString((CSecureString *)&v11);
    v8 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = v6;
    if ( v8 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 8LL))(v8, 1);
    AggregatedTokenRequest::RealmInfo::~RealmInfo((AggregatedTokenRequest::RealmInfo *)v13);
  }
  catch ( const Exception *v16 )
  {
    v9 = (FailedTokenRequest *)operator new(
                                 0x38u,
                                 1,
                                 "onecore\\ds\\security\\dsreg\\win32\\adal.native\\aggregatedtokenrequest.cpp");
    v21 = v9;
    if ( v9 )
      v9 = FailedTokenRequest::FailedTokenRequest(v9, this, v16);
    v10 = std::unique_ptr<TokenRequest>::unique_ptr<TokenRequest>(&v20, (__int64)v9);
    std::unique_ptr<TokenRequest>::operator=<std::default_delete<TokenRequest>,0>((__int64 *)this + 4, v10);
    std::unique_ptr<TokenRequest>::~unique_ptr<TokenRequest>((__int64 *)&v20);
    throw;
  }
}

```

## disassembly

```asm
0x14000b7e0  mov     [rsp+arg_8], rbx
0x14000b7e5  mov     [rsp+arg_0], rcx
0x14000b7ea  push    rsi
0x14000b7eb  push    rdi
0x14000b7ec  push    r13
0x14000b7ee  push    r14
0x14000b7f0  push    r15
0x14000b7f2  sub     rsp, 0A0h
0x14000b7f9  mov     rbx, rdx
0x14000b7fc  mov     rdi, rcx
0x14000b7ff  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b806  lea     r13, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b80d  mov     rcx, r13
0x14000b810  mov     rax, [rax+18h]
0x14000b814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b819  add     rax, 18h
0x14000b81d  mov     [rsp+0C8h+var_80], rax
0x14000b822  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b829  mov     rcx, r13
0x14000b82c  mov     rax, [rax+18h]
0x14000b830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b835  add     rax, 18h
0x14000b839  mov     [rsp+0C8h+var_78], rax
0x14000b83e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b845  mov     rcx, r13
0x14000b848  mov     rax, [rax+18h]
0x14000b84c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b851  add     rax, 18h
0x14000b855  mov     [rsp+0C8h+var_70], rax
0x14000b85a  lea     rdx, aAggregatedtoke_2; "AggregatedTokenRequest::UseWindowsInteg"...
0x14000b861  mov     rcx, rdi; struct ILogContext *
0x14000b864  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000b869  xor     r14d, r14d
0x14000b86c  cmp     [rdi+20h], r14
0x14000b870  jnz     loc_14000BAC8
0x14000b876  test    rbx, rbx
0x14000b879  jz      loc_14000BA92
0x14000b87f  cmp     [rbx], r14w
0x14000b883  jz      loc_14000BA92
0x14000b889  mov     r8, rbx
0x14000b88c  lea     rdx, aHttpsSAdfsServ; "https://%s/adfs/services/trust/mex"
0x14000b893  lea     rcx, [rsp+0C8h+var_80]
0x14000b898  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14000b89d  lea     rdx, [rsp+0C8h+var_80]
0x14000b8a2  lea     rcx, [rsp+0C8h+arg_10]
0x14000b8aa  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000b8af  lea     r8, [rsp+0C8h+var_88]
0x14000b8b4  mov     rdx, rax
0x14000b8b7  mov     rcx, rdi
0x14000b8ba  call    ?ParseMexToRealmInfo@AggregatedTokenRequest@@AEAAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAURealmInfo@1@@Z; AggregatedTokenRequest::ParseMexToRealmInfo(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,AggregatedTokenRequest::RealmInfo &)
0x14000b8bf  mov     r9d, 0DCh; int
0x14000b8c5  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14000b8cc  mov     edx, 1; int
0x14000b8d1  lea     ecx, [r9-4Ch]; unsigned __int64
0x14000b8d5  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14000b8da  mov     rbx, rax
0x14000b8dd  mov     [rsp+0C8h+arg_10], rax
0x14000b8e5  test    rax, rax
0x14000b8e8  jz      short loc_14000B90A
0x14000b8ea  lea     r9, [rdi+18h]
0x14000b8ee  lea     r8, [rdi+10h]
0x14000b8f2  mov     rdx, [rdi+8]
0x14000b8f6  mov     rcx, rax
0x14000b8f9  call    ??0OAuthTokenRequestBase@@QEAA@PEAVAuthenticationContext@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1@Z; OAuthTokenRequestBase::OAuthTokenRequestBase(AuthenticationContext *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000b8fe  lea     rax, ??_7WSTrustTokenRequest@@6B@; const WSTrustTokenRequest::`vftable'
0x14000b905  mov     [rbx], rax
0x14000b908  jmp     short loc_14000B90D
0x14000b90a  mov     rbx, r14
0x14000b90d  mov     [rsp+0C8h+var_68], rbx
0x14000b912  lea     rax, [rsp+0C8h+arg_10]
0x14000b91a  mov     [rsp+0C8h+var_60], rax
0x14000b91f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b926  mov     rcx, r13
0x14000b929  mov     rax, [rax+18h]
0x14000b92d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b932  add     rax, 18h
0x14000b936  mov     [rsp+0C8h+arg_10], rax
0x14000b93e  lea     r15, dword_14003353C
0x14000b945  mov     rdx, r15
0x14000b948  lea     rcx, [rsp+0C8h+arg_10]
0x14000b950  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000b955  test    al, al
0x14000b957  jnz     short loc_14000B96D
0x14000b959  xor     r8d, r8d
0x14000b95c  mov     rdx, r15
0x14000b95f  lea     rcx, [rsp+0C8h+arg_10]
0x14000b967  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000b96c  nop
0x14000b96d  lea     rax, [rsp+0C8h+var_90]
0x14000b972  mov     [rsp+0C8h+var_58], rax
0x14000b977  lea     rdx, [rsp+0C8h+var_70]
0x14000b97c  lea     rcx, [rsp+0C8h+var_90]
0x14000b981  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000b986  mov     rsi, rax
0x14000b989  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b990  mov     rax, [rcx+18h]
0x14000b994  mov     rcx, r13
0x14000b997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b99c  add     rax, 18h
0x14000b9a0  mov     [rsp+0C8h+var_98], rax
0x14000b9a5  mov     rdx, r15
0x14000b9a8  lea     rcx, [rsp+0C8h+var_98]
0x14000b9ad  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000b9b2  test    al, al
0x14000b9b4  jnz     short loc_14000B9C7
0x14000b9b6  xor     r8d, r8d
0x14000b9b9  mov     rdx, r15
0x14000b9bc  lea     rcx, [rsp+0C8h+var_98]
0x14000b9c1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000b9c6  nop
0x14000b9c7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b9ce  mov     rcx, r13
0x14000b9d1  mov     rax, [rax+18h]
0x14000b9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b9da  add     rax, 18h
0x14000b9de  mov     [rsp+0C8h+arg_18], rax
0x14000b9e6  mov     rdx, r15
0x14000b9e9  lea     rcx, [rsp+0C8h+arg_18]
0x14000b9f1  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000b9f6  test    al, al
0x14000b9f8  jnz     short loc_14000BA0E
0x14000b9fa  xor     r8d, r8d
0x14000b9fd  mov     rdx, r15
0x14000ba00  lea     rcx, [rsp+0C8h+arg_18]
0x14000ba08  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000ba0d  nop
0x14000ba0e  mov     [rsp+0C8h+var_A0], r14b
0x14000ba13  lea     rax, [rsp+0C8h+arg_10]
0x14000ba1b  mov     [rsp+0C8h+var_A8], rax
0x14000ba20  mov     r9, rsi
0x14000ba23  lea     r8, [rsp+0C8h+var_98]
0x14000ba28  lea     rdx, [rsp+0C8h+arg_18]
0x14000ba30  mov     rcx, rbx
0x14000ba33  call    ?AcquireToken@WSTrustTokenRequest@@QEAA_NAEBVCSecureString@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1_N@Z; WSTrustTokenRequest::AcquireToken(CSecureString const &,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool)
0x14000ba38  nop
0x14000ba39  lea     rcx, [rsp+0C8h+arg_18]; this
0x14000ba41  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x14000ba46  nop
0x14000ba47  lea     rcx, [rsp+0C8h+var_98]; this
0x14000ba4c  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x14000ba51  mov     rcx, [rdi+20h]
0x14000ba55  mov     [rdi+20h], rbx
0x14000ba59  test    rcx, rcx
0x14000ba5c  jz      short loc_14000BA70
0x14000ba5e  mov     rax, [rcx]
0x14000ba61  mov     edx, 1
0x14000ba66  mov     rax, [rax+8]
0x14000ba6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba6f  nop
0x14000ba70  lea     rcx, [rsp+0C8h+var_88]; this
0x14000ba75  call    ??1RealmInfo@AggregatedTokenRequest@@QEAA@XZ; AggregatedTokenRequest::RealmInfo::~RealmInfo(void)
0x14000ba7a  mov     rbx, [rsp+0C8h+arg_8]
0x14000ba82  add     rsp, 0A0h
0x14000ba89  pop     r15
0x14000ba8b  pop     r14
0x14000ba8d  pop     r13
0x14000ba8f  pop     rdi
0x14000ba90  pop     rsi
0x14000ba91  retn
0x14000ba92  lea     rdx, aErrorFederatio; "Error, federationServer MUST be provide"...
0x14000ba99  mov     rcx, rdi; struct ILogContext *
0x14000ba9c  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000baa1  mov     edx, 80070057h; unsigned int
0x14000baa6  lea     rcx, [rsp+0C8h+pExceptionObject]; this
0x14000baae  call    ??0InvalidCallException@@QEAA@K@Z; InvalidCallException::InvalidCallException(ulong)
0x14000bab3  lea     rdx, _TI3?AVInvalidCallException@@; pThrowInfo
0x14000baba  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x14000bac2  call    _CxxThrowException_0
0x14000bac8  mov     edx, 0CAA10037h; unsigned int
0x14000bacd  lea     rcx, [rsp+0C8h+var_48]; this
0x14000bad5  call    ??0InvalidCallException@@QEAA@K@Z; InvalidCallException::InvalidCallException(ulong)
0x14000bada  lea     rdx, _TI3?AVInvalidCallException@@; pThrowInfo
0x14000bae1  lea     rcx, [rsp+0C8h+var_48]; pExceptionObject
0x14000bae9  call    _CxxThrowException_0
```
