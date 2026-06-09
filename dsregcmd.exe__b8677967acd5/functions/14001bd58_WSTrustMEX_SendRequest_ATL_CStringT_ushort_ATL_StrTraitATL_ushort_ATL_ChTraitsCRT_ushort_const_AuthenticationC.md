# WSTrustMEX::SendRequest(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,AuthenticationContext const &)

- ea: `0x14001bd58`
- end: `0x14001c021`
- name: `?SendRequest@WSTrustMEX@@CA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@AEBVAuthenticationContext@@@Z`
- size: `713`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x14000b0fc`

## callees

- `0x140005458`
- `0x1400054e8`
- `0x14000579c`
- `0x14000598c`
- `0x140005c80`
- `0x1400061dc`
- `0x14000e000`
- `0x14001bd58`
- `0x14001e1a8`
- `0x14002266c`
- `0x140022b14`
- `0x140022bd8`
- `0x1400231f8`
- `0x1400232e0`
- `0x140023430`
- `0x14002c3e8`
- `0x140030010`

## string_xrefs

- `0x14001be24`: `application/soap+xml`
- `0x14001be3e`: `application/soap+xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall WSTrustMEX::SendRequest(_QWORD *a1, __int64 *a2, __int64 a3)
{
  struct WebRequest *v6; // rbx
  volatile signed __int32 *v7; // rdx
  volatile signed __int32 *v8; // rdx
  volatile signed __int32 *v9; // rdx
  volatile signed __int32 *v10; // rdx
  volatile signed __int32 *v11; // rdx
  __int64 *v12; // rax
  WebRequest *v14; // rbx
  unsigned __int16 v15; // ax
  __int64 v16; // r8
  _BYTE pExceptionObject[40]; // [rsp+38h] [rbp-28h] BYREF
  volatile signed __int32 *v18; // [rsp+98h] [rbp+38h] BYREF
  volatile signed __int32 *v19; // [rsp+A0h] [rbp+40h] BYREF
  struct WebRequest *v20; // [rsp+A8h] [rbp+48h] BYREF

  WebRequestFactory::CreateBasicConnection(&v20, a3, 0);
  v6 = v20;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v19,
    (__int64 *)(a3 + 40));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v18,
    *a2);
  WebRequest::Open((__int64)v6, &WebRequest::MethodGet, &v18, &v19);
  v7 = v18 - 6;
  if ( _InterlockedDecrement(v18 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
  v8 = v19 - 6;
  if ( _InterlockedDecrement(v19 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
  v19 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v19,
          (__int64)L"application/soap+xml") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v19, L"application/soap+xml", 20);
  v18 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v18,
          (__int64)L"Content-Type") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v18, L"Content-Type", 12);
  WebRequest::SetRequestHeader(v6, &v18, &v19);
  v9 = v18 - 6;
  if ( _InterlockedDecrement(v18 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9);
  v10 = v19 - 6;
  if ( _InterlockedDecrement(v19 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
  v18 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v18,
          (__int64)&dword_14003353C) )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v18, &dword_14003353C, 0);
  WebRequest::Send(v6);
  v11 = v18 - 6;
  if ( _InterlockedDecrement(v18 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
  if ( *((_WORD *)v6 + 44) != 4 )
  {
    InvalidCallException::InvalidCallException((InvalidCallException *)pExceptionObject, -895418365);
    throw (InvalidCallException *)pExceptionObject;
  }
  if ( *((_WORD *)v6 + 46) != 200 )
  {
    v14 = (WebRequest *)std::unique_ptr<WebRequest>::operator->((__int64)&v20);
    WebRequest::ResponseText(v14, &v18);
    v15 = WebRequest::Status(v14);
    HttpException::HttpException(pExceptionObject, v15, v16);
    throw (HttpException *)pExceptionObject;
  }
  v12 = (__int64 *)WebRequest::ResponseText(v6, &v18);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    a1,
    v12);
  CSecureString::~CSecureString((CSecureString *)&v18);
  if ( v6 )
    (**(void (__fastcall ***)(struct WebRequest *, __int64))v6)(v6, 1);
  return a1;
}

```

## disassembly

```asm
0x14001bd58  push    rbp
0x14001bd5a  push    rbx
0x14001bd5b  push    rsi
0x14001bd5c  push    rdi
0x14001bd5d  push    r14
0x14001bd5f  mov     rbp, rsp
0x14001bd62  sub     rsp, 60h
0x14001bd66  mov     rdi, r8
0x14001bd69  mov     rsi, rdx
0x14001bd6c  mov     r14, rcx
0x14001bd6f  xor     r8d, r8d
0x14001bd72  mov     rdx, rdi
0x14001bd75  lea     rcx, [rbp+arg_18]
0x14001bd79  call    ?CreateBasicConnection@WebRequestFactory@@CA?AV?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@AEBVAuthenticationContext@@_N@Z; WebRequestFactory::CreateBasicConnection(AuthenticationContext const &,bool)
0x14001bd7e  nop
0x14001bd7f  mov     rbx, [rbp+arg_18]
0x14001bd83  lea     rdx, [rdi+28h]
0x14001bd87  lea     rcx, [rbp+arg_10]
0x14001bd8b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001bd90  nop
0x14001bd91  mov     rdx, [rsi]
0x14001bd94  lea     rcx, [rbp+arg_8]
0x14001bd98  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001bd9d  nop
0x14001bd9e  lea     r9, [rbp+arg_10]
0x14001bda2  lea     r8, [rbp+arg_8]
0x14001bda6  lea     rdx, ?MethodGet@WebRequest@@2V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const WebRequest::MethodGet
0x14001bdad  mov     rcx, rbx
0x14001bdb0  call    ?Open@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00_NP6AX_KJ@Z@Z; WebRequest::Open(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,void (*)(unsigned __int64,long))
0x14001bdb5  nop
0x14001bdb6  mov     rdx, [rbp+arg_8]
0x14001bdba  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001bdbe  or      edi, 0FFFFFFFFh
0x14001bdc1  mov     eax, edi
0x14001bdc3  lock xadd [rdx+10h], eax
0x14001bdc8  add     eax, edi
0x14001bdca  test    eax, eax
0x14001bdcc  jg      short loc_14001BDDE
0x14001bdce  mov     rcx, [rdx]
0x14001bdd1  mov     rax, [rcx]
0x14001bdd4  mov     rax, [rax+8]
0x14001bdd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bddd  nop
0x14001bdde  mov     rdx, [rbp+arg_10]
0x14001bde2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001bde6  mov     eax, edi
0x14001bde8  lock xadd [rdx+10h], eax
0x14001bded  add     eax, edi
0x14001bdef  test    eax, eax
0x14001bdf1  jg      short loc_14001BE02
0x14001bdf3  mov     rcx, [rdx]
0x14001bdf6  mov     rax, [rcx]
0x14001bdf9  mov     rax, [rax+8]
0x14001bdfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001be02  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001be09  lea     rsi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001be10  mov     rcx, rsi
0x14001be13  mov     rax, [rax+18h]
0x14001be17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001be1c  add     rax, 18h
0x14001be20  mov     [rbp+arg_10], rax
0x14001be24  lea     rdx, aApplicationSoa_0; "application/soap+xml"
0x14001be2b  lea     rcx, [rbp+arg_10]
0x14001be2f  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001be34  test    al, al
0x14001be36  jnz     short loc_14001BE4F
0x14001be38  mov     r8d, 14h
0x14001be3e  lea     rdx, aApplicationSoa_0; "application/soap+xml"
0x14001be45  lea     rcx, [rbp+arg_10]
0x14001be49  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001be4e  nop
0x14001be4f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001be56  mov     rcx, rsi
0x14001be59  mov     rax, [rax+18h]
0x14001be5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001be62  add     rax, 18h
0x14001be66  mov     [rbp+arg_8], rax
0x14001be6a  lea     rdx, aContentType_0; "Content-Type"
0x14001be71  lea     rcx, [rbp+arg_8]
0x14001be75  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001be7a  test    al, al
0x14001be7c  jnz     short loc_14001BE95
0x14001be7e  mov     r8d, 0Ch
0x14001be84  lea     rdx, aContentType_0; "Content-Type"
0x14001be8b  lea     rcx, [rbp+arg_8]
0x14001be8f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001be94  nop
0x14001be95  lea     r8, [rbp+arg_10]
0x14001be99  lea     rdx, [rbp+arg_8]
0x14001be9d  mov     rcx, rbx
0x14001bea0  call    ?SetRequestHeader@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WebRequest::SetRequestHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001bea5  nop
0x14001bea6  mov     rdx, [rbp+arg_8]
0x14001beaa  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001beae  mov     eax, edi
0x14001beb0  lock xadd [rdx+10h], eax
0x14001beb5  add     eax, edi
0x14001beb7  test    eax, eax
0x14001beb9  jg      short loc_14001BECB
0x14001bebb  mov     rcx, [rdx]
0x14001bebe  mov     rax, [rcx]
0x14001bec1  mov     rax, [rax+8]
0x14001bec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001beca  nop
0x14001becb  mov     rdx, [rbp+arg_10]
0x14001becf  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001bed3  mov     eax, edi
0x14001bed5  lock xadd [rdx+10h], eax
0x14001beda  add     eax, edi
0x14001bedc  test    eax, eax
0x14001bede  jg      short loc_14001BEEF
0x14001bee0  mov     rcx, [rdx]
0x14001bee3  mov     rax, [rcx]
0x14001bee6  mov     rax, [rax+8]
0x14001beea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001beef  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001bef6  mov     rcx, rsi
0x14001bef9  mov     rax, [rax+18h]
0x14001befd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bf02  add     rax, 18h
0x14001bf06  mov     [rbp+arg_8], rax
0x14001bf0a  lea     rdx, dword_14003353C
0x14001bf11  lea     rcx, [rbp+arg_8]
0x14001bf15  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001bf1a  test    al, al
0x14001bf1c  jnz     short loc_14001BF32
0x14001bf1e  xor     r8d, r8d
0x14001bf21  lea     rdx, dword_14003353C
0x14001bf28  lea     rcx, [rbp+arg_8]
0x14001bf2c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001bf31  nop
0x14001bf32  lea     rdx, [rbp+arg_8]
0x14001bf36  mov     rcx, rbx; struct WebRequest *
0x14001bf39  call    ?Send@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebRequest::Send(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001bf3e  nop
0x14001bf3f  mov     rdx, [rbp+arg_8]
0x14001bf43  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001bf47  mov     eax, edi
0x14001bf49  lock xadd [rdx+10h], eax
0x14001bf4e  add     eax, edi
0x14001bf50  test    eax, eax
0x14001bf52  jg      short loc_14001BF63
0x14001bf54  mov     rcx, [rdx]
0x14001bf57  mov     rax, [rcx]
0x14001bf5a  mov     rax, [rax+8]
0x14001bf5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bf63  cmp     word ptr [rbx+58h], 4
0x14001bf68  jnz     loc_14001C002
0x14001bf6e  mov     eax, 0C8h
0x14001bf73  cmp     [rbx+5Ch], ax
0x14001bf77  jnz     short loc_14001BFC2
0x14001bf79  lea     rdx, [rbp+arg_8]
0x14001bf7d  mov     rcx, rbx
0x14001bf80  call    ?ResponseText@WebRequest@@QEBA?AVCSecureString@@XZ; WebRequest::ResponseText(void)
0x14001bf85  nop
0x14001bf86  mov     rdx, rax
0x14001bf89  mov     rcx, r14
0x14001bf8c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001bf91  nop
0x14001bf92  lea     rcx, [rbp+arg_8]; this
0x14001bf96  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x14001bf9b  nop
0x14001bf9c  test    rbx, rbx
0x14001bf9f  jz      short loc_14001BFB4
0x14001bfa1  mov     rax, [rbx]
0x14001bfa4  mov     edx, 1
0x14001bfa9  mov     rcx, rbx
0x14001bfac  mov     rax, [rax]
0x14001bfaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bfb4  mov     rax, r14
0x14001bfb7  add     rsp, 60h
0x14001bfbb  pop     r14
0x14001bfbd  pop     rdi
0x14001bfbe  pop     rsi
0x14001bfbf  pop     rbx
0x14001bfc0  pop     rbp
0x14001bfc1  retn
0x14001bfc2  lea     rcx, [rbp+arg_18]
0x14001bfc6  call    ??C?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@QEBAPEAVWebRequest@@XZ; std::unique_ptr<WebRequest>::operator->(void)
0x14001bfcb  mov     rbx, rax
0x14001bfce  lea     rdx, [rbp+arg_8]
0x14001bfd2  mov     rcx, rax
0x14001bfd5  call    ?ResponseText@WebRequest@@QEBA?AVCSecureString@@XZ; WebRequest::ResponseText(void)
0x14001bfda  mov     r8, rax
0x14001bfdd  mov     rcx, rbx; this
0x14001bfe0  call    ?Status@WebRequest@@QEBAGXZ; WebRequest::Status(void)
0x14001bfe5  movzx   edx, ax
0x14001bfe8  lea     rcx, [rbp+pExceptionObject]
0x14001bfec  call    ??0HttpException@@QEAA@KAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; HttpException::HttpException(ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001bff1  lea     rdx, _TI2?AVHttpException@@; pThrowInfo
0x14001bff8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14001bffc  call    _CxxThrowException_0
0x14001c002  mov     edx, 0CAA10003h; unsigned int
0x14001c007  lea     rcx, [rbp+pExceptionObject]; this
0x14001c00b  call    ??0InvalidCallException@@QEAA@K@Z; InvalidCallException::InvalidCallException(ulong)
0x14001c010  lea     rdx, _TI3?AVInvalidCallException@@; pThrowInfo
0x14001c017  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14001c01b  call    _CxxThrowException_0
```
