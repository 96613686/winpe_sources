# MSXML::Create(ushort const *,ushort const *)

- ea: `0x140028040`
- end: `0x14002844e`
- name: `?Create@MSXML@@YA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEBG0@Z`
- size: `1038`
- prototype: `struct IUnknown **__fastcall(struct IUnknown **, const unsigned __int16 *, const OLECHAR *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140019e24`
- `0x140027410`
- `0x140027534`
- `0x140027d80`

## callees

- `0x140018d0c`
- `0x1400193b4`
- `0x140027f04`
- `0x140028040`
- `0x140028454`
- `0x14002aebc`
- `0x14002c070`
- `0x14002c084`
- `0x140030010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400281cb`
- `OLEAUT32!__imp_SysAllocString` at `0x1400281cb`
- `OLEAUT32!__imp_VariantClear` at `0x140028209`
- `OLEAUT32!__imp_VariantClear` at `0x1400282d3`
- `OLEAUT32!__imp_VariantClear` at `0x14002831a`
- `OLEAUT32!__imp_VariantClear` at `0x140028209`
- `OLEAUT32!__imp_VariantClear` at `0x1400282d3`
- `OLEAUT32!__imp_VariantClear` at `0x14002831a`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct IUnknown **__fastcall MSXML::Create(struct IUnknown **a1, const unsigned __int16 *a2, const OLECHAR *a3)
{
  const OLECHAR *v3; // r15
  const unsigned __int16 *v4; // r12
  struct IUnknown **v5; // r14
  __int64 v6; // rdi
  IUnknown *v7; // r8
  IUnknown *v8; // r8
  LPVOID v9; // rcx
  struct IUnknown *v10; // rbx
  struct IUnknown *v11; // rdx
  LPVOID v12; // rcx
  struct IUnknown *v13; // rbx
  struct IUnknown *v14; // rdx
  struct IUnknown *v15; // rbx
  _bstr_t *v16; // rax
  struct IUnknown *v17; // rbx
  int v18; // eax
  struct IUnknown *v19; // rbx
  int v20; // eax
  struct IUnknown *v21; // rbx
  int v22; // eax
  struct IUnknown *v23; // rbx
  _bstr_t *v24; // rax
  struct IUnknown *v25; // rbx
  _bstr_t *v26; // rax
  struct IUnknown *v27; // rbx
  _bstr_t *v28; // rax
  _bstr_t *v29; // r15
  __int64 v30; // rdx
  int v31; // eax
  const wchar_t **v33; // rax
  __int64 *v34; // rax
  _QWORD **v35; // rcx
  ResourceMsg *v36; // rax
  const wchar_t *v37; // rax
  const unsigned __int16 *v38; // rax
  __int64 v39; // [rsp+20h] [rbp-98h] BYREF
  int v40; // [rsp+28h] [rbp-90h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-88h] BYREF
  char v42[8]; // [rsp+48h] [rbp-70h] BYREF
  const COMException *v43; // [rsp+50h] [rbp-68h] BYREF
  const COMException *v44[2]; // [rsp+58h] [rbp-60h] BYREF
  _BYTE v45[80]; // [rsp+68h] [rbp-50h] BYREF
  LPVOID ppv; // [rsp+D8h] [rbp+20h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = a1;
  *a1 = 0;
  v40 = 1;
  v6 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v39 = v6;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    _com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::_com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>(
      &ppv,
      &GUID_88d96a06_f192_11d4_a65f_0040963251e5,
      v7,
      23);
    v9 = ppv;
    if ( *v5 != ppv )
    {
      v10 = (struct IUnknown *)ppv;
      if ( ppv )
      {
        (*(void (**)(void))(*(_QWORD *)ppv + 8LL))();
        v9 = ppv;
      }
      v11 = *v5;
      *v5 = v10;
      if ( v11 )
      {
        ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
        v9 = ppv;
      }
    }
    if ( v9 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &COMException `RTTI Type Descriptor', &v43) )
    {
      if ( *((_DWORD *)v43 + 2) == -2147221164 )
      {
        v33 = (const wchar_t **)ResourceMsg::ResourceMsg((ResourceMsg *)&ppv, 0x4AAE0014u);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          &v39,
          *v33,
          L"Msxml2.FreeThreadedDOMDocument.6.0",
          L"88d96a06-f192-11d4-a65f-0040963251e5");
      }
      else
      {
        v34 = (__int64 *)(*(__int64 (__fastcall **)(const COMException *, LPVOID *))(*(_QWORD *)v43 + 8LL))(v43, &ppv);
        ATL::CSimpleStringT<unsigned short,0>::Append(&v39, *v34, *(unsigned int *)(*v34 - 16));
      }
      v35 = (_QWORD **)ppv;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)ppv - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, _QWORD **))(**(v35 - 3) + 8LL))(*(v35 - 3), v35 - 3);
      v3 = a3;
      v4 = a2;
      v5 = a1;
      v6 = v39;
      __eh34_try_continuation(0, &COMException `RTTI Type Descriptor', &loc_140028112);
    }
  }
  if ( !*v5 )
  {
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      _com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::_com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>(
        &ppv,
        &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
        v8,
        23);
      v12 = ppv;
      if ( *v5 != ppv )
      {
        v13 = (struct IUnknown *)ppv;
        if ( ppv )
        {
          (*(void (**)(void))(*(_QWORD *)ppv + 8LL))();
          v12 = ppv;
        }
        v14 = *v5;
        *v5 = v13;
        if ( v14 )
        {
          ((void (__fastcall *)(struct IUnknown *))v14->lpVtbl->Release)(v14);
          v12 = ppv;
        }
      }
      if ( v12 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &COMException `RTTI Type Descriptor', v44) )
      {
        if ( *((_DWORD *)v44[0] + 2) == -2147221164 )
        {
          v36 = ResourceMsg::ResourceMsg((ResourceMsg *)&ppv, 0x4AAE0014u);
          v37 = (const wchar_t *)std::unique_ptr<WebRequest>::operator->((__int64)v36);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            &v39,
            v37,
            L"Msxml2.DOMDocument.6.0",
            L"88d96a05-f192-11d4-a65f-0040963251e5");
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&ppv);
          v38 = (const unsigned __int16 *)std::unique_ptr<WebRequest>::operator->((__int64)&v39);
          XmlException::XmlException((XmlException *)v45, -895156223, v38);
          throw (XmlException *)v45;
        }
        throw;
      }
    }
  }
  if ( v3 )
  {
    v15 = *v5;
    if ( !*v5 )
      _com_issue_error(-2147467261);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(v3);
    if ( !pvarg.llVal )
      _com_issue_error(-2147024882);
    v16 = _bstr_t::_bstr_t((_bstr_t *)&ppv, L"SelectionNamespaces");
    MSXML::IXMLDOMDocument2::setProperty(v15, v16, &pvarg);
    VariantClear(&pvarg);
  }
  v17 = *v5;
  if ( !*v5 )
    goto LABEL_38;
  v18 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v17->lpVtbl[21].QueryInterface)(*v5, 0);
  if ( v18 < 0 )
    _com_issue_errorex(v18, v17, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
  v19 = *v5;
  if ( !*v5 )
    goto LABEL_38;
  v20 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v19->lpVtbl[22].Release)(*v5, 0);
  if ( v20 < 0 )
    _com_issue_errorex(v20, v19, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
  v21 = *v5;
  if ( !*v5 )
LABEL_38:
    _com_issue_error(-2147467261);
  v22 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v21->lpVtbl[23].AddRef)(*v5, 0);
  if ( v22 < 0 )
    _com_issue_errorex(v22, v21, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
  v23 = *v5;
  if ( !*v5 )
    _com_issue_error(-2147467261);
  pvarg.vt = 11;
  pvarg.iVal = -1;
  v24 = _bstr_t::_bstr_t((_bstr_t *)&ppv, L"ProhibitDTD");
  MSXML::IXMLDOMDocument2::setProperty(v23, v24, &pvarg);
  VariantClear(&pvarg);
  v25 = *v5;
  if ( !*v5 )
    _com_issue_error(-2147467261);
  pvarg.vt = 11;
  pvarg.iVal = 0;
  v26 = _bstr_t::_bstr_t((_bstr_t *)&ppv, L"AllowXsltScript");
  MSXML::IXMLDOMDocument2::setProperty(v25, v26, &pvarg);
  VariantClear(&pvarg);
  v27 = *v5;
  if ( !*v5 )
    _com_issue_error(-2147467261);
  v28 = _bstr_t::_bstr_t((_bstr_t *)v42, v4);
  v29 = v28;
  v44[1] = v28;
  LOWORD(ppv) = 0;
  if ( *(_QWORD *)v28 )
    v30 = **(_QWORD **)v28;
  else
    v30 = 0;
  v31 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, LPVOID *))v27->lpVtbl[21].Release)(v27, v30, &ppv);
  if ( v31 < 0 )
    _com_issue_errorex(v31, v27, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
  _bstr_t::~_bstr_t(v29);
  XmlException::ThrowIfError(v5);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v6 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 - 24) + 8LL))(*(_QWORD *)(v6 - 24));
  return v5;
}

```

## disassembly

```asm
0x140028040  mov     [rsp+arg_10], r8
0x140028045  mov     [rsp+arg_8], rdx
0x14002804a  mov     [rsp+arg_0], rcx
0x14002804f  push    rbx
0x140028050  push    rsi
0x140028051  push    rdi
0x140028052  push    r12
0x140028054  push    r13
0x140028056  push    r14
0x140028058  push    r15
0x14002805a  sub     rsp, 80h
0x140028061  mov     r15, r8
0x140028064  mov     r12, rdx
0x140028067  mov     r14, rcx
0x14002806a  xor     esi, esi
0x14002806c  mov     [rsp+0B8h+var_90], esi
0x140028070  mov     [rcx], rsi
0x140028073  mov     [rsp+0B8h+var_90], 1
0x14002807b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140028082  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140028089  mov     rax, [rax+18h]
0x14002808d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028092  lea     rdi, [rax+18h]
0x140028096  mov     [rsp+0B8h+var_98], rdi
0x14002809b  lea     r9d, [rsi+17h]
0x14002809f  lea     rdx, _GUID_88d96a06_f192_11d4_a65f_0040963251e5; rclsid
0x1400280a6  lea     rcx, [rsp+0B8h+ppv]; ppv
0x1400280ae  call    ??0?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAA@AEBU_GUID@@PEAUIUnknown@@K@Z; _com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::_com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>(_GUID const &,IUnknown *,ulong)
0x1400280b3  mov     rcx, [rsp+0B8h+ppv]
0x1400280bb  cmp     [r14], rcx
0x1400280be  jz      short loc_1400280FE
0x1400280c0  mov     rbx, rcx
0x1400280c3  test    rcx, rcx
0x1400280c6  jz      short loc_1400280DC
0x1400280c8  mov     rax, [rcx]
0x1400280cb  mov     rax, [rax+8]
0x1400280cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400280d4  mov     rcx, [rsp+0B8h+ppv]
0x1400280dc  mov     rdx, [r14]
0x1400280df  mov     [r14], rbx
0x1400280e2  test    rdx, rdx
0x1400280e5  jz      short loc_1400280FE
0x1400280e7  mov     rax, [rdx]
0x1400280ea  mov     rcx, rdx
0x1400280ed  mov     rax, [rax+10h]
0x1400280f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400280f6  mov     rcx, [rsp+0B8h+ppv]
0x1400280fe  test    rcx, rcx
0x140028101  jz      short loc_140028110
0x140028103  mov     rax, [rcx]
0x140028106  mov     rax, [rax+10h]
0x14002810a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002810f  nop
0x140028110  jmp     short loc_140028131
0x140028112  xor     esi, esi
0x140028114  mov     r15, [rsp+0B8h+arg_10]
0x14002811c  mov     r12, [rsp+0B8h+arg_8]
0x140028124  mov     r14, [rsp+0B8h+arg_0]
0x14002812c  mov     rdi, [rsp+0B8h+var_98]
0x140028131  cmp     [r14], rsi
0x140028134  jnz     short loc_1400281AD
0x140028136  mov     r9d, 17h
0x14002813c  lea     rdx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x140028143  lea     rcx, [rsp+0B8h+ppv]; ppv
0x14002814b  call    ??0?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAA@AEBU_GUID@@PEAUIUnknown@@K@Z; _com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::_com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>(_GUID const &,IUnknown *,ulong)
0x140028150  mov     rcx, [rsp+0B8h+ppv]
0x140028158  cmp     [r14], rcx
0x14002815b  jz      short loc_14002819B
0x14002815d  mov     rbx, rcx
0x140028160  test    rcx, rcx
0x140028163  jz      short loc_140028179
0x140028165  mov     rax, [rcx]
0x140028168  mov     rax, [rax+8]
0x14002816c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028171  mov     rcx, [rsp+0B8h+ppv]
0x140028179  mov     rdx, [r14]
0x14002817c  mov     [r14], rbx
0x14002817f  test    rdx, rdx
0x140028182  jz      short loc_14002819B
0x140028184  mov     rax, [rdx]
0x140028187  mov     rcx, rdx
0x14002818a  mov     rax, [rax+10h]
0x14002818e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028193  mov     rcx, [rsp+0B8h+ppv]
0x14002819b  test    rcx, rcx
0x14002819e  jz      short loc_1400281AD
0x1400281a0  mov     rax, [rcx]
0x1400281a3  mov     rax, [rax+10h]
0x1400281a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400281ac  nop
0x1400281ad  test    r15, r15
0x1400281b0  jz      short loc_14002820F
0x1400281b2  mov     rbx, [r14]
0x1400281b5  test    rbx, rbx
0x1400281b8  jz      loc_1400283EC
0x1400281be  mov     eax, 8
0x1400281c3  mov     word ptr [rsp+0B8h+pvarg], ax
0x1400281c8  mov     rcx, r15; psz
0x1400281cb  call    cs:__imp_SysAllocString
0x1400281d1  mov     qword ptr [rsp+0B8h+pvarg+8], rax
0x1400281d6  test    rax, rax
0x1400281d9  jz      loc_1400283CF
0x1400281df  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x1400281e6  lea     rcx, [rsp+0B8h+ppv]; this
0x1400281ee  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1400281f3  lea     r8, [rsp+0B8h+pvarg]
0x1400281f8  mov     rdx, rax
0x1400281fb  mov     rcx, rbx
0x1400281fe  call    ?setProperty@IXMLDOMDocument2@MSXML@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; MSXML::IXMLDOMDocument2::setProperty(_bstr_t,_variant_t const &)
0x140028203  nop
0x140028204  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x140028209  call    cs:__imp_VariantClear
0x14002820f  mov     rbx, [r14]
0x140028212  test    rbx, rbx
0x140028215  jz      loc_1400283C4
0x14002821b  mov     rax, [rbx]
0x14002821e  xor     edx, edx
0x140028220  mov     rcx, rbx
0x140028223  mov     rax, [rax+1F8h]
0x14002822a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002822f  test    eax, eax
0x140028231  js      loc_1400283DA
0x140028237  mov     rbx, [r14]
0x14002823a  test    rbx, rbx
0x14002823d  jz      loc_1400283C4
0x140028243  mov     rax, [rbx]
0x140028246  xor     edx, edx
0x140028248  mov     rcx, rbx
0x14002824b  mov     rax, [rax+220h]
0x140028252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028257  test    eax, eax
0x140028259  js      loc_1400283F7
0x14002825f  mov     rbx, [r14]
0x140028262  test    rbx, rbx
0x140028265  jz      loc_1400283C4
0x14002826b  mov     rax, [rbx]
0x14002826e  xor     edx, edx
0x140028270  mov     rcx, rbx
0x140028273  mov     rax, [rax+230h]
0x14002827a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002827f  test    eax, eax
0x140028281  js      loc_140028409
0x140028287  mov     rbx, [r14]
0x14002828a  test    rbx, rbx
0x14002828d  jz      loc_140028443
0x140028293  mov     r15d, 0Bh
0x140028299  mov     word ptr [rsp+0B8h+pvarg], r15w
0x14002829f  or      r13d, 0FFFFFFFFh
0x1400282a3  mov     word ptr [rsp+0B8h+pvarg+8], r13w
0x1400282a9  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x1400282b0  lea     rcx, [rsp+0B8h+ppv]; this
0x1400282b8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1400282bd  lea     r8, [rsp+0B8h+pvarg]
0x1400282c2  mov     rdx, rax
0x1400282c5  mov     rcx, rbx
0x1400282c8  call    ?setProperty@IXMLDOMDocument2@MSXML@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; MSXML::IXMLDOMDocument2::setProperty(_bstr_t,_variant_t const &)
0x1400282cd  nop
0x1400282ce  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1400282d3  call    cs:__imp_VariantClear
0x1400282d9  mov     rbx, [r14]
0x1400282dc  test    rbx, rbx
0x1400282df  jz      loc_140028438
0x1400282e5  mov     word ptr [rsp+0B8h+pvarg], r15w
0x1400282eb  mov     word ptr [rsp+0B8h+pvarg+8], si
0x1400282f0  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x1400282f7  lea     rcx, [rsp+0B8h+ppv]; this
0x1400282ff  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140028304  lea     r8, [rsp+0B8h+pvarg]
0x140028309  mov     rdx, rax
0x14002830c  mov     rcx, rbx
0x14002830f  call    ?setProperty@IXMLDOMDocument2@MSXML@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; MSXML::IXMLDOMDocument2::setProperty(_bstr_t,_variant_t const &)
0x140028314  nop
0x140028315  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x14002831a  call    cs:__imp_VariantClear
0x140028320  mov     rbx, [r14]
0x140028323  test    rbx, rbx
0x140028326  jz      loc_14002842D
0x14002832c  mov     rdx, r12; unsigned __int16 *
0x14002832f  lea     rcx, [rsp+0B8h+var_70]; this
0x140028334  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140028339  mov     r15, rax
0x14002833c  mov     [rsp+0B8h+var_58], rax
0x140028341  mov     word ptr [rsp+0B8h+ppv], si
0x140028349  mov     rcx, [rbx]
0x14002834c  mov     rax, [rcx+208h]
0x140028353  mov     rdx, [r15]
0x140028356  test    rdx, rdx
0x140028359  jz      short loc_140028360
0x14002835b  mov     rdx, [rdx]
0x14002835e  jmp     short loc_140028363
0x140028360  mov     rdx, rsi
0x140028363  lea     r8, [rsp+0B8h+ppv]
0x14002836b  mov     rcx, rbx
0x14002836e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028373  test    eax, eax
0x140028375  js      loc_14002841B
0x14002837b  mov     rcx, r15; this
0x14002837e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x140028383  mov     rcx, r14
0x140028386  call    ?ThrowIfError@XmlException@@SAXAEBV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; XmlException::ThrowIfError(_com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> const &)
0x14002838b  nop
0x14002838c  lea     rdx, [rdi-18h]
0x140028390  mov     eax, r13d
0x140028393  lock xadd [rdx+10h], eax
0x140028398  add     eax, r13d
0x14002839b  test    eax, eax
0x14002839d  jg      short loc_1400283AE
0x14002839f  mov     rcx, [rdx]
0x1400283a2  mov     rax, [rcx]
0x1400283a5  mov     rax, [rax+8]
0x1400283a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400283ae  mov     rax, r14
0x1400283b1  add     rsp, 80h
0x1400283b8  pop     r15
0x1400283ba  pop     r14
0x1400283bc  pop     r13
0x1400283be  pop     r12
0x1400283c0  pop     rdi
0x1400283c1  pop     rsi
0x1400283c2  pop     rbx
0x1400283c3  retn
0x1400283c4  mov     ecx, 80004003h; int
0x1400283c9  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400283cf  mov     ecx, 8007000Eh; int
0x1400283d4  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400283da  lea     r8, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x1400283e1  mov     rdx, rbx; struct IUnknown *
0x1400283e4  mov     ecx, eax; int
0x1400283e6  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x1400283ec  mov     ecx, 80004003h; int
0x1400283f1  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400283f7  lea     r8, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x1400283fe  mov     rdx, rbx; struct IUnknown *
0x140028401  mov     ecx, eax; int
0x140028403  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x140028409  lea     r8, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x140028410  mov     rdx, rbx; struct IUnknown *
0x140028413  mov     ecx, eax; int
0x140028415  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14002841b  lea     r8, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x140028422  mov     rdx, rbx; struct IUnknown *
0x140028425  mov     ecx, eax; int
0x140028427  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14002842d  mov     ecx, 80004003h; int
0x140028432  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140028438  mov     ecx, 80004003h; int
0x14002843d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140028443  mov     ecx, 80004003h; int
0x140028448  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
