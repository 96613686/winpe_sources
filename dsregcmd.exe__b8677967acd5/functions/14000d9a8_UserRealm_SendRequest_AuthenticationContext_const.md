# UserRealm::SendRequest(AuthenticationContext const &)

- ea: `0x14000d9a8`
- end: `0x14000df3d`
- name: `?SendRequest@UserRealm@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVAuthenticationContext@@@Z`
- size: `1429`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000d134`

## callees

- `0x140005458`
- `0x1400054e8`
- `0x14000579c`
- `0x14000598c`
- `0x140005c80`
- `0x1400061dc`
- `0x140007bf8`
- `0x1400081d8`
- `0x14000d7a8`
- `0x14000d9a8`
- `0x14000e000`
- `0x140013c8c`
- `0x14001e1a8`
- `0x1400223d0`
- `0x14002266c`
- `0x140022b14`
- `0x140022bd8`
- `0x1400231f8`
- `0x1400232e0`
- `0x140023430`
- `0x14002c3e8`
- `0x140030010`

## string_xrefs

- `0x14000d9ff`: `/common/UserRealm/%s`
- `0x14000db1c`: `application/json`
- `0x14000db36`: `application/json`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall UserRealm::SendRequest(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v6; // rax
  _QWORD *v7; // rax
  volatile signed __int32 *v8; // rdx
  volatile signed __int32 *v9; // rdx
  struct WebRequest *v10; // rbx
  __int64 v11; // rdi
  volatile signed __int32 *v12; // rdx
  volatile signed __int32 *v13; // rdx
  volatile signed __int32 *v14; // rdx
  volatile signed __int32 *v15; // rdx
  _WORD *v16; // rdx
  volatile signed __int32 *v17; // rdx
  volatile signed __int32 *v18; // rdx
  const wchar_t *v19; // rdx
  volatile signed __int32 *v20; // rdx
  volatile signed __int32 *v21; // rdx
  volatile signed __int32 *v22; // rdx
  __int64 *v23; // rax
  volatile signed __int32 *v24; // rdx
  WebRequest *v26; // rbx
  unsigned __int16 v27; // ax
  __int64 v28; // r8
  struct WebRequest *v29; // [rsp+38h] [rbp-28h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+40h] [rbp-20h] BYREF
  volatile signed __int32 *v31; // [rsp+90h] [rbp+30h] BYREF
  volatile signed __int32 *v32; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v33; // [rsp+A8h] [rbp+48h] BYREF

  WebRequestFactory::CreateBasicConnection(&v29, a3, 0);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v33,
    (__int64 *)(a1 + 16));
  v6 = UserRealm::ResolveUPN(a1, &v32);
  v7 = (_QWORD *)StringUtility::UrlFormEncodeBlock(&v31, v6);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &v33,
    L"/common/UserRealm/%s",
    *v7);
  v8 = v31 - 6;
  if ( _InterlockedDecrement(v31 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
  v9 = v32 - 6;
  if ( _InterlockedDecrement(v32 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &v33,
    L"?api-version=%s",
    *(_QWORD *)(a1 + 8));
  v10 = v29;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v32,
    (__int64 *)(a3 + 40));
  v11 = v33;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v31,
    v33);
  WebRequest::Open((__int64)v10, &WebRequest::MethodGet, &v31, &v32);
  v12 = v31 - 6;
  if ( _InterlockedDecrement(v31 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12);
  v13 = v32 - 6;
  if ( _InterlockedDecrement(v32 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
  v32 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v32,
          (__int64)L"application/json") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v32, L"application/json", 16);
  v31 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v31,
          (__int64)L"Accept") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v31, L"Accept", 6);
  WebRequest::SetRequestHeader(v10, &v31, &v32);
  v14 = v31 - 6;
  if ( _InterlockedDecrement(v31 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
  v15 = v32 - 6;
  if ( _InterlockedDecrement(v32 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 8LL))(*(_QWORD *)v15);
  v16 = *(_WORD **)(a1 + 32);
  if ( *v16 && *((_DWORD *)v16 - 4) == 36 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v32,
      (__int64)v16);
    v31 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v31,
            (__int64)L"client-request-id") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v31, L"client-request-id", 17);
    WebRequest::SetRequestHeader(v10, &v31, &v32);
    v17 = v31 - 6;
    if ( _InterlockedDecrement(v31 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 8LL))(*(_QWORD *)v17);
    v18 = v32 - 6;
    if ( _InterlockedDecrement(v32 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18);
    v19 = L"true";
    if ( !*(_BYTE *)(a1 + 40) )
      v19 = L"false";
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v32,
      (__int64)v19);
    v31 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v31,
            (__int64)L"return-client-request-id") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v31, L"return-client-request-id", 24);
    WebRequest::SetRequestHeader(v10, &v31, &v32);
    v20 = v31 - 6;
    if ( _InterlockedDecrement(v31 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v20 + 8LL))(*(_QWORD *)v20);
    v21 = v32 - 6;
    if ( _InterlockedDecrement(v32 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 8LL))(*(_QWORD *)v21);
  }
  v31 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v31,
          (__int64)&dword_14003353C) )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v31, &dword_14003353C, 0);
  WebRequest::Send(v10);
  v22 = v31 - 6;
  if ( _InterlockedDecrement(v31 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v22 + 8LL))(*(_QWORD *)v22);
  if ( *((_WORD *)v10 + 44) != 4 )
  {
    InvalidCallException::InvalidCallException((InvalidCallException *)pExceptionObject, -895418365);
    throw (InvalidCallException *)pExceptionObject;
  }
  WebRequest::GetHeaderValue(v10, &v31, L"client-request-id");
  if ( *((_DWORD *)v31 - 4) )
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (_QWORD *)(a1 + 24),
      &v31);
  if ( *((_WORD *)v10 + 46) != 200 )
  {
    v26 = (WebRequest *)std::unique_ptr<WebRequest>::operator->((__int64)&v29);
    WebRequest::ResponseText(v26, &v32);
    v27 = WebRequest::Status(v26);
    HttpException::HttpException(pExceptionObject, v27, v28);
    throw (HttpException *)pExceptionObject;
  }
  v23 = (__int64 *)WebRequest::ResponseText(v10, &v32);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    a2,
    v23);
  CSecureString::~CSecureString((CSecureString *)&v32);
  v24 = v31 - 6;
  if ( _InterlockedDecrement(v31 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v11 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v11 - 24) + 8LL))(*(_QWORD *)(v11 - 24));
  if ( v10 )
    (**(void (__fastcall ***)(struct WebRequest *, __int64))v10)(v10, 1);
  return a2;
}

```

## disassembly

```asm
0x14000d9a8  mov     [rsp-28h+arg_8], rbx
0x14000d9ad  push    rbp
0x14000d9ae  push    rsi
0x14000d9af  push    rdi
0x14000d9b0  push    r14
0x14000d9b2  push    r15
0x14000d9b4  mov     rbp, rsp
0x14000d9b7  sub     rsp, 60h
0x14000d9bb  mov     rdi, r8
0x14000d9be  mov     r14, rdx
0x14000d9c1  mov     rsi, rcx
0x14000d9c4  xor     r8d, r8d
0x14000d9c7  mov     rdx, rdi
0x14000d9ca  lea     rcx, [rbp+var_28]
0x14000d9ce  call    ?CreateBasicConnection@WebRequestFactory@@CA?AV?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@AEBVAuthenticationContext@@_N@Z; WebRequestFactory::CreateBasicConnection(AuthenticationContext const &,bool)
0x14000d9d3  nop
0x14000d9d4  lea     rdx, [rsi+10h]
0x14000d9d8  lea     rcx, [rbp+arg_18]
0x14000d9dc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000d9e1  nop
0x14000d9e2  lea     rdx, [rbp+arg_10]
0x14000d9e6  mov     rcx, rsi
0x14000d9e9  call    ?ResolveUPN@UserRealm@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; UserRealm::ResolveUPN(void)
0x14000d9ee  nop
0x14000d9ef  mov     rdx, rax
0x14000d9f2  lea     rcx, [rbp+arg_0]
0x14000d9f6  call    ?UrlFormEncodeBlock@StringUtility@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@@Z; StringUtility::UrlFormEncodeBlock(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000d9fb  nop
0x14000d9fc  mov     r8, [rax]
0x14000d9ff  lea     rdx, aCommonUserreal; "/common/UserRealm/%s"
0x14000da06  lea     rcx, [rbp+arg_18]
0x14000da0a  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14000da0f  nop
0x14000da10  mov     rdx, [rbp+arg_0]
0x14000da14  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000da18  or      r15d, 0FFFFFFFFh
0x14000da1c  mov     eax, r15d
0x14000da1f  lock xadd [rdx+10h], eax
0x14000da24  add     eax, r15d
0x14000da27  test    eax, eax
0x14000da29  jg      short loc_14000DA3B
0x14000da2b  mov     rcx, [rdx]
0x14000da2e  mov     rax, [rcx]
0x14000da31  mov     rax, [rax+8]
0x14000da35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da3a  nop
0x14000da3b  mov     rdx, [rbp+arg_10]
0x14000da3f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000da43  mov     eax, r15d
0x14000da46  lock xadd [rdx+10h], eax
0x14000da4b  add     eax, r15d
0x14000da4e  test    eax, eax
0x14000da50  jg      short loc_14000DA61
0x14000da52  mov     rcx, [rdx]
0x14000da55  mov     rax, [rcx]
0x14000da58  mov     rax, [rax+8]
0x14000da5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da61  mov     r8, [rsi+8]
0x14000da65  lea     rdx, aApiVersionS; "?api-version=%s"
0x14000da6c  lea     rcx, [rbp+arg_18]
0x14000da70  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14000da75  mov     rbx, [rbp+var_28]
0x14000da79  lea     rdx, [rdi+28h]
0x14000da7d  lea     rcx, [rbp+arg_10]
0x14000da81  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000da86  nop
0x14000da87  mov     rdi, [rbp+arg_18]
0x14000da8b  mov     rdx, rdi
0x14000da8e  lea     rcx, [rbp+arg_0]
0x14000da92  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000da97  nop
0x14000da98  lea     r9, [rbp+arg_10]
0x14000da9c  lea     r8, [rbp+arg_0]
0x14000daa0  lea     rdx, ?MethodGet@WebRequest@@2V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const WebRequest::MethodGet
0x14000daa7  mov     rcx, rbx
0x14000daaa  call    ?Open@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00_NP6AX_KJ@Z@Z; WebRequest::Open(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,void (*)(unsigned __int64,long))
0x14000daaf  nop
0x14000dab0  mov     rdx, [rbp+arg_0]
0x14000dab4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000dab8  mov     eax, r15d
0x14000dabb  lock xadd [rdx+10h], eax
0x14000dac0  add     eax, r15d
0x14000dac3  test    eax, eax
0x14000dac5  jg      short loc_14000DAD7
0x14000dac7  mov     rcx, [rdx]
0x14000daca  mov     rax, [rcx]
0x14000dacd  mov     rax, [rax+8]
0x14000dad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dad6  nop
0x14000dad7  mov     rdx, [rbp+arg_10]
0x14000dadb  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000dadf  mov     eax, r15d
0x14000dae2  lock xadd [rdx+10h], eax
0x14000dae7  add     eax, r15d
0x14000daea  test    eax, eax
0x14000daec  jg      short loc_14000DAFD
0x14000daee  mov     rcx, [rdx]
0x14000daf1  mov     rax, [rcx]
0x14000daf4  mov     rax, [rax+8]
0x14000daf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dafd  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000db04  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000db0b  mov     rax, [rax+18h]
0x14000db0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db14  add     rax, 18h
0x14000db18  mov     [rbp+arg_10], rax
0x14000db1c  lea     rdx, aApplicationJso; "application/json"
0x14000db23  lea     rcx, [rbp+arg_10]
0x14000db27  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000db2c  test    al, al
0x14000db2e  jnz     short loc_14000DB47
0x14000db30  mov     r8d, 10h
0x14000db36  lea     rdx, aApplicationJso; "application/json"
0x14000db3d  lea     rcx, [rbp+arg_10]
0x14000db41  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000db46  nop
0x14000db47  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000db4e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000db55  mov     rax, [rax+18h]
0x14000db59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db5e  add     rax, 18h
0x14000db62  mov     [rbp+arg_0], rax
0x14000db66  lea     rdx, aAccept; "Accept"
0x14000db6d  lea     rcx, [rbp+arg_0]
0x14000db71  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000db76  test    al, al
0x14000db78  jnz     short loc_14000DB91
0x14000db7a  mov     r8d, 6
0x14000db80  lea     rdx, aAccept; "Accept"
0x14000db87  lea     rcx, [rbp+arg_0]
0x14000db8b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000db90  nop
0x14000db91  lea     r8, [rbp+arg_10]
0x14000db95  lea     rdx, [rbp+arg_0]
0x14000db99  mov     rcx, rbx
0x14000db9c  call    ?SetRequestHeader@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WebRequest::SetRequestHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000dba1  nop
0x14000dba2  mov     rdx, [rbp+arg_0]
0x14000dba6  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000dbaa  mov     eax, r15d
0x14000dbad  lock xadd [rdx+10h], eax
0x14000dbb2  add     eax, r15d
0x14000dbb5  test    eax, eax
0x14000dbb7  jg      short loc_14000DBC9
0x14000dbb9  mov     rcx, [rdx]
0x14000dbbc  mov     rax, [rcx]
0x14000dbbf  mov     rax, [rax+8]
0x14000dbc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dbc8  nop
0x14000dbc9  mov     rdx, [rbp+arg_10]
0x14000dbcd  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000dbd1  mov     eax, r15d
0x14000dbd4  lock xadd [rdx+10h], eax
0x14000dbd9  add     eax, r15d
0x14000dbdc  test    eax, eax
0x14000dbde  jg      short loc_14000DBF0
0x14000dbe0  mov     rcx, [rdx]
0x14000dbe3  mov     rax, [rcx]
0x14000dbe6  mov     rax, [rax+8]
0x14000dbea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dbef  nop
0x14000dbf0  mov     rdx, [rsi+20h]
0x14000dbf4  xor     eax, eax
0x14000dbf6  cmp     [rdx], ax
0x14000dbf9  jz      loc_14000DD83
0x14000dbff  cmp     dword ptr [rdx-10h], 24h ; '$'
0x14000dc03  jnz     loc_14000DD83
0x14000dc09  lea     rcx, [rbp+arg_10]
0x14000dc0d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000dc12  nop
0x14000dc13  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000dc1a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000dc21  mov     rax, [rax+18h]
0x14000dc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dc2a  add     rax, 18h
0x14000dc2e  mov     [rbp+arg_0], rax
0x14000dc32  lea     rdx, aClientRequestI; "client-request-id"
0x14000dc39  lea     rcx, [rbp+arg_0]
0x14000dc3d  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000dc42  test    al, al
0x14000dc44  jnz     short loc_14000DC5D
0x14000dc46  mov     r8d, 11h
0x14000dc4c  lea     rdx, aClientRequestI; "client-request-id"
0x14000dc53  lea     rcx, [rbp+arg_0]
0x14000dc57  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000dc5c  nop
0x14000dc5d  lea     r8, [rbp+arg_10]
0x14000dc61  lea     rdx, [rbp+arg_0]
0x14000dc65  mov     rcx, rbx
0x14000dc68  call    ?SetRequestHeader@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WebRequest::SetRequestHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000dc6d  nop
0x14000dc6e  mov     rdx, [rbp+arg_0]
0x14000dc72  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000dc76  mov     eax, r15d
0x14000dc79  lock xadd [rdx+10h], eax
0x14000dc7e  add     eax, r15d
0x14000dc81  test    eax, eax
0x14000dc83  jg      short loc_14000DC95
0x14000dc85  mov     rcx, [rdx]
0x14000dc88  mov     rax, [rcx]
0x14000dc8b  mov     rax, [rax+8]
0x14000dc8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dc94  nop
0x14000dc95  mov     rdx, [rbp+arg_10]
0x14000dc99  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000dc9d  mov     eax, r15d
0x14000dca0  lock xadd [rdx+10h], eax
0x14000dca5  add     eax, r15d
0x14000dca8  test    eax, eax
0x14000dcaa  jg      short loc_14000DCBB
0x14000dcac  mov     rcx, [rdx]
0x14000dcaf  mov     rax, [rcx]
0x14000dcb2  mov     rax, [rax+8]
0x14000dcb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dcbb  lea     rax, aFalse; "false"
0x14000dcc2  lea     rdx, aTrue; "true"
0x14000dcc9  cmp     byte ptr [rsi+28h], 0
0x14000dccd  cmovz   rdx, rax
0x14000dcd1  lea     rcx, [rbp+arg_10]
0x14000dcd5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000dcda  nop
0x14000dcdb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000dce2  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000dce9  mov     rax, [rax+18h]
0x14000dced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dcf2  add     rax, 18h
0x14000dcf6  mov     [rbp+arg_0], rax
0x14000dcfa  lea     rdx, aReturnClientRe; "return-client-request-id"
0x14000dd01  lea     rcx, [rbp+arg_0]
0x14000dd05  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000dd0a  test    al, al
0x14000dd0c  jnz     short loc_14000DD25
0x14000dd0e  mov     r8d, 18h
0x14000dd14  lea     rdx, aReturnClientRe; "return-client-request-id"
0x14000dd1b  lea     rcx, [rbp+arg_0]
0x14000dd1f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000dd24  nop
0x14000dd25  lea     r8, [rbp+arg_10]
0x14000dd29  lea     rdx, [rbp+arg_0]
0x14000dd2d  mov     rcx, rbx
0x14000dd30  call    ?SetRequestHeader@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WebRequest::SetRequestHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000dd35  nop
0x14000dd36  mov     rdx, [rbp+arg_0]
0x14000dd3a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000dd3e  mov     eax, r15d
0x14000dd41  lock xadd [rdx+10h], eax
0x14000dd46  add     eax, r15d
0x14000dd49  test    eax, eax
0x14000dd4b  jg      short loc_14000DD5D
0x14000dd4d  mov     rcx, [rdx]
0x14000dd50  mov     rax, [rcx]
0x14000dd53  mov     rax, [rax+8]
0x14000dd57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dd5c  nop
0x14000dd5d  mov     rdx, [rbp+arg_10]
0x14000dd61  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000dd65  mov     eax, r15d
0x14000dd68  lock xadd [rdx+10h], eax
0x14000dd6d  add     eax, r15d
0x14000dd70  test    eax, eax
0x14000dd72  jg      short loc_14000DD83
0x14000dd74  mov     rcx, [rdx]
0x14000dd77  mov     rax, [rcx]
0x14000dd7a  mov     rax, [rax+8]
0x14000dd7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dd83  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000dd8a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000dd91  mov     rax, [rax+18h]
0x14000dd95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dd9a  add     rax, 18h
0x14000dd9e  mov     [rbp+arg_0], rax
0x14000dda2  lea     rdx, dword_14003353C
0x14000dda9  lea     rcx, [rbp+arg_0]
0x14000ddad  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000ddb2  test    al, al
0x14000ddb4  jnz     short loc_14000DDCA
0x14000ddb6  xor     r8d, r8d
0x14000ddb9  lea     rdx, dword_14003353C
0x14000ddc0  lea     rcx, [rbp+arg_0]
0x14000ddc4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000ddc9  nop
0x14000ddca  lea     rdx, [rbp+arg_0]
0x14000ddce  mov     rcx, rbx; struct WebRequest *
0x14000ddd1  call    ?Send@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebRequest::Send(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ddd6  nop
0x14000ddd7  mov     rdx, [rbp+arg_0]
0x14000dddb  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000dddf  mov     eax, r15d
0x14000dde2  lock xadd [rdx+10h], eax
0x14000dde7  add     eax, r15d
0x14000ddea  test    eax, eax
0x14000ddec  jg      short loc_14000DDFD
0x14000ddee  mov     rcx, [rdx]
0x14000ddf1  mov     rax, [rcx]
0x14000ddf4  mov     rax, [rax+8]
0x14000ddf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ddfd  cmp     word ptr [rbx+58h], 4
0x14000de02  jnz     loc_14000DEDE
0x14000de08  lea     r8, aClientRequestI; "client-request-id"
0x14000de0f  lea     rdx, [rbp+arg_0]
  ... truncated ...
```
