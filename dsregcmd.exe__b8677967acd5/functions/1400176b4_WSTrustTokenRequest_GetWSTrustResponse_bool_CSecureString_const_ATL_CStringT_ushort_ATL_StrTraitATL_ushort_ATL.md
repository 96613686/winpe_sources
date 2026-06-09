# WSTrustTokenRequest::GetWSTrustResponse(bool,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool)

- ea: `0x1400176b4`
- end: `0x140017c18`
- name: `?GetWSTrustResponse@WSTrustTokenRequest@@AEAA?AV?$unique_ptr@VWSTrustResponse@@U?$default_delete@VWSTrustResponse@@@std@@@std@@_NAEBVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `1380`
- prototype: `__int64 *__fastcall(__int64, __int64 *, bool, __int64 *, __int64 *, char)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140016a04`

## callees

- `0x140001814`
- `0x140005458`
- `0x1400054e8`
- `0x140005c80`
- `0x1400061dc`
- `0x14000c384`
- `0x14000e000`
- `0x1400176b4`
- `0x14001e1a8`
- `0x14002266c`
- `0x140022bd8`
- `0x140022f3c`
- `0x1400231f8`
- `0x140026f30`
- `0x14002c3e8`
- `0x140030010`

## string_xrefs

- `0x1400177be`: `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`
- `0x1400177d9`: `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`
- `0x14001787e`: `http://docs.oasis-open.org/ws-sx/ws-trust/200512/RST/Issue`
- `0x140017899`: `http://docs.oasis-open.org/ws-sx/ws-trust/200512/RST/Issue`
- `0x140017972`: `application/soap+xml; charset=utf-8`
- `0x14001798d`: `application/soap+xml; charset=utf-8`
- `0x140017b8c`: `onecore\ds\security\dsreg\win32\adal.native\wstrusttokenrequest.cpp`

## pseudocode

```c
__int64 *__fastcall WSTrustTokenRequest::GetWSTrustResponse(
        __int64 a1,
        __int64 *a2,
        bool a3,
        __int64 *a4,
        __int64 *a5,
        char a6)
{
  struct WebRequest *v9; // rbx
  volatile signed __int32 *v10; // rdx
  volatile signed __int32 *v11; // rdx
  volatile signed __int32 *v12; // rax
  volatile signed __int32 *v13; // rdx
  volatile signed __int32 *v14; // rdx
  volatile signed __int32 *v15; // rdx
  volatile signed __int32 *v16; // rdx
  volatile signed __int32 *v17; // rdx
  volatile signed __int32 *v18; // rdx
  volatile signed __int32 *v19; // rdx
  _QWORD *v20; // rdi
  volatile signed __int32 *v21; // rdx
  volatile signed __int32 *v22; // rdx
  volatile signed __int32 *v23; // rdx
  __int64 v24; // rax
  __int64 *result; // rax
  const struct Exception *v26; // rbx
  __int64 v27; // rcx
  _QWORD *v28; // rax
  ResourceId *v29; // rax
  volatile signed __int32 *v30; // [rsp+30h] [rbp-78h] BYREF
  volatile signed __int32 *v31; // [rsp+38h] [rbp-70h] BYREF
  _QWORD *v32; // [rsp+40h] [rbp-68h]
  struct WebRequest *v33[3]; // [rsp+48h] [rbp-60h] BYREF
  const Exception *v34; // [rsp+60h] [rbp-48h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+68h] [rbp-40h] BYREF
  const struct ILogContext *v36; // [rsp+B0h] [rbp+8h] BYREF

  v36 = (const struct ILogContext *)a1;
  LODWORD(v31) = 1;
  WebRequestFactory::CreateBasicConnection(v33, *(_QWORD *)(a1 + 8), a3);
  v9 = v33[0];
  try
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v31,
      (__int64 *)(*(_QWORD *)(a1 + 8) + 40LL));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v30,
      *a5);
    WebRequest::Open(v9, &WebRequest::MethodPost, &v30, &v31);
    v10 = v30 - 6;
    if ( _InterlockedDecrement(v30 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
    v11 = v31 - 6;
    if ( _InterlockedDecrement(v31 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
    v12 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( a6 )
    {
      v30 = v12;
      if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
              (void *const *)&v30,
              (__int64)L"http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(
          &v30,
          L"http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue",
          53);
      v31 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
              (void *const *)&v31,
              (__int64)L"SOAPAction") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v31, L"SOAPAction", 10);
      WebRequest::SetRequestHeader(v9, &v31, &v30);
      v13 = v31 - 6;
      if ( _InterlockedDecrement(v31 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
      v14 = v30;
    }
    else
    {
      v31 = v12;
      if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
              (void *const *)&v31,
              (__int64)L"http://docs.oasis-open.org/ws-sx/ws-trust/200512/RST/Issue") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(
          &v31,
          L"http://docs.oasis-open.org/ws-sx/ws-trust/200512/RST/Issue",
          58);
      v30 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
              (void *const *)&v30,
              (__int64)L"SOAPAction") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v30, L"SOAPAction", 10);
      WebRequest::SetRequestHeader(v9, &v30, &v31);
      v15 = v30 - 6;
      if ( _InterlockedDecrement(v30 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 8LL))(*(_QWORD *)v15);
      v14 = v31;
    }
    v16 = v14 - 6;
    if ( _InterlockedDecrement(v16 + 4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 8LL))(*(_QWORD *)v16);
    v31 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v31,
            (__int64)L"application/soap+xml; charset=utf-8") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v31, L"application/soap+xml; charset=utf-8", 35);
    v30 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v30,
            (__int64)L"Content-Type") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v30, L"Content-Type", 12);
    WebRequest::SetRequestHeader(v9, &v30, &v31);
    v17 = v30 - 6;
    if ( _InterlockedDecrement(v30 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 8LL))(*(_QWORD *)v17);
    v18 = v31 - 6;
    if ( _InterlockedDecrement(v31 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v30,
      (__int64 *)(*(_QWORD *)(a1 + 8) + 72LL));
    WebRequest::SetAdditionalRequestHeaders(v9, &v30);
    v19 = v30 - 6;
    if ( _InterlockedDecrement(v30 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v19 + 8LL))(*(_QWORD *)v19);
    v33[1] = (struct WebRequest *)&v30;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v30,
      (__int64 *)(*(_QWORD *)(a1 + 8) + 40LL));
    v33[2] = (struct WebRequest *)&v30;
    v20 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v31,
            a5);
    v32 = v20;
    Log::InfoInternal(a1, 1252589584, 1252917253);
    v21 = (volatile signed __int32 *)(*v20 - 24LL);
    if ( _InterlockedDecrement(v21 + 4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 8LL))(*(_QWORD *)v21);
    v22 = v30 - 6;
    if ( _InterlockedDecrement(v30 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v22 + 8LL))(*(_QWORD *)v22);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v30,
      *a4);
    WebRequest::Send(v9);
    v23 = v30 - 6;
    if ( _InterlockedDecrement(v30 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 8LL))(*(_QWORD *)v23);
    if ( *((_WORD *)v9 + 44) != 4 )
    {
      InvalidCallException::InvalidCallException((InvalidCallException *)pExceptionObject, -895418365);
      throw (InvalidCallException *)pExceptionObject;
    }
    v24 = (__int64)operator new(0x38u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\wstrusttokenrequest.cpp");
    v32 = (_QWORD *)v24;
    if ( v24 )
      v24 = WSTrustResponse::WSTrustResponse(v24, (__int64)v9, (__int64)a5);
    *a2 = v24;
    if ( v9 )
      (**(void (__fastcall ***)(struct WebRequest *, __int64))v9)(v9, 1);
    result = a2;
  }
  catch ( const Exception *v34 )
  {
    v26 = v34;
    *((_DWORD *)v36 + 15) = Exception::ErrorCode(v34);
    v28 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, const struct ILogContext **))(*(_QWORD *)v26 + 8LL))(v27, &v36);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (_QWORD *)v36 + 9,
      v28);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v36);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (char *)v36 + 64,
      L"authentication_failed");
    Log::Error(v36, v26);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v30,
      a5);
    v29 = ResourceId::ResourceId((ResourceId *)&v36, 0x4AAE0009u);
    Log::Error<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(
      v36,
      *((unsigned int *)v36 + 15),
      *(unsigned int *)v29);
    throw;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v31,
    (__int64 *)(*(_QWORD *)(a1 + 8) + 40LL));
}

```

## disassembly

```asm
0x1400176b4  mov     rax, rsp
0x1400176b7  mov     [rax+10h], rbx
0x1400176bb  mov     [rax+18h], rsi
0x1400176bf  mov     [rax+8], rcx
0x1400176c3  push    rdi
0x1400176c4  push    r12
0x1400176c6  push    r13
0x1400176c8  push    r14
0x1400176ca  push    r15
0x1400176cc  sub     rsp, 80h
0x1400176d3  mov     r12, r9
0x1400176d6  mov     r14, rdx
0x1400176d9  mov     rsi, rcx
0x1400176dc  mov     dword ptr [rsp+0A8h+var_70], 1
0x1400176e4  mov     rdx, [rcx+8]
0x1400176e8  lea     rcx, [rax-60h]
0x1400176ec  call    ?CreateBasicConnection@WebRequestFactory@@CA?AV?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@AEBVAuthenticationContext@@_N@Z; WebRequestFactory::CreateBasicConnection(AuthenticationContext const &,bool)
0x1400176f1  nop
0x1400176f2  mov     rbx, [rsp+0A8h+var_60]
0x1400176f7  mov     rdx, [rsi+8]
0x1400176fb  add     rdx, 28h ; '('
0x1400176ff  lea     rcx, [rsp+0A8h+var_70]
0x140017704  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140017709  nop
0x14001770a  mov     r15, [rsp+0A8h+arg_20]
0x140017712  mov     rdx, [r15]
0x140017715  lea     rcx, [rsp+0A8h+var_78]
0x14001771a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001771f  nop
0x140017720  lea     r9, [rsp+0A8h+var_70]
0x140017725  lea     r8, [rsp+0A8h+var_78]
0x14001772a  lea     rdx, ?MethodPost@WebRequest@@2V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const WebRequest::MethodPost
0x140017731  mov     rcx, rbx
0x140017734  call    ?Open@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00_NP6AX_KJ@Z@Z; WebRequest::Open(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,void (*)(unsigned __int64,long))
0x140017739  nop
0x14001773a  mov     rdx, [rsp+0A8h+var_78]
0x14001773f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140017743  or      r13d, 0FFFFFFFFh
0x140017747  mov     eax, r13d
0x14001774a  lock xadd [rdx+10h], eax
0x14001774f  add     eax, r13d
0x140017752  test    eax, eax
0x140017754  jg      short loc_140017766
0x140017756  mov     rcx, [rdx]
0x140017759  mov     rax, [rcx]
0x14001775c  mov     rax, [rax+8]
0x140017760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017765  nop
0x140017766  mov     rdx, [rsp+0A8h+var_70]
0x14001776b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001776f  mov     eax, r13d
0x140017772  lock xadd [rdx+10h], eax
0x140017777  add     eax, r13d
0x14001777a  test    eax, eax
0x14001777c  jg      short loc_14001778D
0x14001777e  mov     rcx, [rdx]
0x140017781  mov     rax, [rcx]
0x140017784  mov     rax, [rax+8]
0x140017788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001778d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140017794  lea     rdi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001779b  mov     rax, [rax+18h]
0x14001779f  mov     rcx, rdi
0x1400177a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400177a7  add     rax, 18h
0x1400177ab  cmp     [rsp+0A8h+arg_28], 0
0x1400177b3  jz      loc_140017879
0x1400177b9  mov     [rsp+0A8h+var_78], rax
0x1400177be  lea     rdx, aHttpSchemasXml_0; "http://schemas.xmlsoap.org/ws/2005/02/t"...
0x1400177c5  lea     rcx, [rsp+0A8h+var_78]
0x1400177ca  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1400177cf  test    al, al
0x1400177d1  jnz     short loc_1400177EB
0x1400177d3  mov     r8d, 35h ; '5'
0x1400177d9  lea     rdx, aHttpSchemasXml_0; "http://schemas.xmlsoap.org/ws/2005/02/t"...
0x1400177e0  lea     rcx, [rsp+0A8h+var_78]
0x1400177e5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400177ea  nop
0x1400177eb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400177f2  mov     rcx, rdi
0x1400177f5  mov     rax, [rax+18h]
0x1400177f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400177fe  add     rax, 18h
0x140017802  mov     [rsp+0A8h+var_70], rax
0x140017807  lea     rdx, aSoapaction; "SOAPAction"
0x14001780e  lea     rcx, [rsp+0A8h+var_70]
0x140017813  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140017818  test    al, al
0x14001781a  jnz     short loc_140017834
0x14001781c  mov     r8d, 0Ah
0x140017822  lea     rdx, aSoapaction; "SOAPAction"
0x140017829  lea     rcx, [rsp+0A8h+var_70]
0x14001782e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140017833  nop
0x140017834  lea     r8, [rsp+0A8h+var_78]
0x140017839  lea     rdx, [rsp+0A8h+var_70]
0x14001783e  mov     rcx, rbx
0x140017841  call    ?SetRequestHeader@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WebRequest::SetRequestHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140017846  nop
0x140017847  mov     rdx, [rsp+0A8h+var_70]
0x14001784c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140017850  mov     eax, r13d
0x140017853  lock xadd [rdx+10h], eax
0x140017858  add     eax, r13d
0x14001785b  test    eax, eax
0x14001785d  jg      short loc_14001786F
0x14001785f  mov     rcx, [rdx]
0x140017862  mov     rax, [rcx]
0x140017865  mov     rax, [rax+8]
0x140017869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001786e  nop
0x14001786f  mov     rdx, [rsp+0A8h+var_78]
0x140017874  jmp     loc_140017934
0x140017879  mov     [rsp+0A8h+var_70], rax
0x14001787e  lea     rdx, aHttpDocsOasisO; "http://docs.oasis-open.org/ws-sx/ws-tru"...
0x140017885  lea     rcx, [rsp+0A8h+var_70]
0x14001788a  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001788f  test    al, al
0x140017891  jnz     short loc_1400178AB
0x140017893  mov     r8d, 3Ah ; ':'
0x140017899  lea     rdx, aHttpDocsOasisO; "http://docs.oasis-open.org/ws-sx/ws-tru"...
0x1400178a0  lea     rcx, [rsp+0A8h+var_70]
0x1400178a5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400178aa  nop
0x1400178ab  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400178b2  mov     rcx, rdi
0x1400178b5  mov     rax, [rax+18h]
0x1400178b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400178be  add     rax, 18h
0x1400178c2  mov     [rsp+0A8h+var_78], rax
0x1400178c7  lea     rdx, aSoapaction; "SOAPAction"
0x1400178ce  lea     rcx, [rsp+0A8h+var_78]
0x1400178d3  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1400178d8  test    al, al
0x1400178da  jnz     short loc_1400178F4
0x1400178dc  mov     r8d, 0Ah
0x1400178e2  lea     rdx, aSoapaction; "SOAPAction"
0x1400178e9  lea     rcx, [rsp+0A8h+var_78]
0x1400178ee  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400178f3  nop
0x1400178f4  lea     r8, [rsp+0A8h+var_70]
0x1400178f9  lea     rdx, [rsp+0A8h+var_78]
0x1400178fe  mov     rcx, rbx
0x140017901  call    ?SetRequestHeader@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WebRequest::SetRequestHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140017906  nop
0x140017907  mov     rdx, [rsp+0A8h+var_78]
0x14001790c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140017910  mov     eax, r13d
0x140017913  lock xadd [rdx+10h], eax
0x140017918  add     eax, r13d
0x14001791b  test    eax, eax
0x14001791d  jg      short loc_14001792F
0x14001791f  mov     rcx, [rdx]
0x140017922  mov     rax, [rcx]
0x140017925  mov     rax, [rax+8]
0x140017929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001792e  nop
0x14001792f  mov     rdx, [rsp+0A8h+var_70]
0x140017934  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140017938  mov     eax, r13d
0x14001793b  lock xadd [rdx+10h], eax
0x140017940  add     eax, r13d
0x140017943  test    eax, eax
0x140017945  jg      short loc_140017956
0x140017947  mov     rcx, [rdx]
0x14001794a  mov     rax, [rcx]
0x14001794d  mov     rax, [rax+8]
0x140017951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017956  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001795d  mov     rcx, rdi
0x140017960  mov     rax, [rax+18h]
0x140017964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017969  add     rax, 18h
0x14001796d  mov     [rsp+0A8h+var_70], rax
0x140017972  lea     rdx, aApplicationSoa; "application/soap+xml; charset=utf-8"
0x140017979  lea     rcx, [rsp+0A8h+var_70]
0x14001797e  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140017983  test    al, al
0x140017985  jnz     short loc_14001799F
0x140017987  mov     r8d, 23h ; '#'
0x14001798d  lea     rdx, aApplicationSoa; "application/soap+xml; charset=utf-8"
0x140017994  lea     rcx, [rsp+0A8h+var_70]
0x140017999  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001799e  nop
0x14001799f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400179a6  mov     rcx, rdi
0x1400179a9  mov     rax, [rax+18h]
0x1400179ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400179b2  add     rax, 18h
0x1400179b6  mov     [rsp+0A8h+var_78], rax
0x1400179bb  lea     rdx, aContentType_0; "Content-Type"
0x1400179c2  lea     rcx, [rsp+0A8h+var_78]
0x1400179c7  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1400179cc  test    al, al
0x1400179ce  jnz     short loc_1400179E8
0x1400179d0  mov     r8d, 0Ch
0x1400179d6  lea     rdx, aContentType_0; "Content-Type"
0x1400179dd  lea     rcx, [rsp+0A8h+var_78]
0x1400179e2  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400179e7  nop
0x1400179e8  lea     r8, [rsp+0A8h+var_70]
0x1400179ed  lea     rdx, [rsp+0A8h+var_78]
0x1400179f2  mov     rcx, rbx
0x1400179f5  call    ?SetRequestHeader@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WebRequest::SetRequestHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400179fa  nop
0x1400179fb  mov     rdx, [rsp+0A8h+var_78]
0x140017a00  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140017a04  mov     eax, r13d
0x140017a07  lock xadd [rdx+10h], eax
0x140017a0c  add     eax, r13d
0x140017a0f  test    eax, eax
0x140017a11  jg      short loc_140017A23
0x140017a13  mov     rcx, [rdx]
0x140017a16  mov     rax, [rcx]
0x140017a19  mov     rax, [rax+8]
0x140017a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017a22  nop
0x140017a23  mov     rdx, [rsp+0A8h+var_70]
0x140017a28  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140017a2c  mov     eax, r13d
0x140017a2f  lock xadd [rdx+10h], eax
0x140017a34  add     eax, r13d
0x140017a37  test    eax, eax
0x140017a39  jg      short loc_140017A4A
0x140017a3b  mov     rcx, [rdx]
0x140017a3e  mov     rax, [rcx]
0x140017a41  mov     rax, [rax+8]
0x140017a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017a4a  mov     rdx, [rsi+8]
0x140017a4e  add     rdx, 48h ; 'H'
0x140017a52  lea     rcx, [rsp+0A8h+var_78]
0x140017a57  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140017a5c  nop
0x140017a5d  lea     rdx, [rsp+0A8h+var_78]
0x140017a62  mov     rcx, rbx
0x140017a65  call    ?SetAdditionalRequestHeaders@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebRequest::SetAdditionalRequestHeaders(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140017a6a  nop
0x140017a6b  mov     rdx, [rsp+0A8h+var_78]
0x140017a70  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140017a74  mov     eax, r13d
0x140017a77  lock xadd [rdx+10h], eax
0x140017a7c  add     eax, r13d
0x140017a7f  test    eax, eax
0x140017a81  jg      short loc_140017A92
0x140017a83  mov     rcx, [rdx]
0x140017a86  mov     rax, [rcx]
0x140017a89  mov     rax, [rax+8]
0x140017a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017a92  lea     rax, [rsp+0A8h+var_78]
0x140017a97  mov     [rsp+0A8h+var_58], rax
0x140017a9c  mov     rdx, [rsi+8]
0x140017aa0  add     rdx, 28h ; '('
0x140017aa4  lea     rcx, [rsp+0A8h+var_78]
0x140017aa9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140017aae  lea     rax, [rsp+0A8h+var_78]
0x140017ab3  mov     [rsp+0A8h+var_50], rax
0x140017ab8  mov     rdx, r15
0x140017abb  lea     rcx, [rsp+0A8h+var_70]
0x140017ac0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140017ac5  mov     rdi, rax
0x140017ac8  mov     [rsp+0A8h+var_68], rax
0x140017acd  mov     rcx, [rsp+0A8h+var_78]
0x140017ad2  mov     [rsp+0A8h+var_88], rcx
0x140017ad7  mov     r9, [rax]
0x140017ada  mov     edx, 4AA90010h
0x140017adf  mov     r8d, 4AAE0005h
0x140017ae5  mov     rcx, rsi
0x140017ae8  call    ?InfoInternal@Log@@CAXPEBVILogContext@@KVResourceId@@ZZ; Log::InfoInternal(ILogContext const *,ulong,ResourceId,...)
0x140017aed  nop
0x140017aee  mov     rdx, [rdi]
0x140017af1  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140017af5  mov     eax, r13d
0x140017af8  lock xadd [rdx+10h], eax
0x140017afd  add     eax, r13d
0x140017b00  test    eax, eax
0x140017b02  jg      short loc_140017B14
0x140017b04  mov     rcx, [rdx]
0x140017b07  mov     rax, [rcx]
0x140017b0a  mov     rax, [rax+8]
0x140017b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017b13  nop
0x140017b14  mov     rdx, [rsp+0A8h+var_78]
0x140017b19  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140017b1d  mov     eax, r13d
0x140017b20  lock xadd [rdx+10h], eax
0x140017b25  add     eax, r13d
0x140017b28  test    eax, eax
0x140017b2a  jg      short loc_140017B3B
0x140017b2c  mov     rcx, [rdx]
0x140017b2f  mov     rax, [rcx]
0x140017b32  mov     rax, [rax+8]
0x140017b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017b3b  mov     rdx, [r12]
0x140017b3f  lea     rcx, [rsp+0A8h+var_78]
0x140017b44  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140017b49  nop
0x140017b4a  lea     rdx, [rsp+0A8h+var_78]
0x140017b4f  mov     rcx, rbx; struct WebRequest *
0x140017b52  call    ?Send@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebRequest::Send(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140017b57  nop
  ... truncated ...
```
