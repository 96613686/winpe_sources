# XmlException::ThrowIfError(_com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> const &)

- ea: `0x14002aebc`
- end: `0x14002b060`
- name: `?ThrowIfError@XmlException@@SAXAEBV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140028040`

## callees

- `0x140005564`
- `0x140005678`
- `0x14000598c`
- `0x140008644`
- `0x14001413c`
- `0x1400193b4`
- `0x140019428`
- `0x14002abe8`
- `0x14002ac64`
- `0x14002ad04`
- `0x14002ad4c`
- `0x14002ad94`
- `0x14002ae28`
- `0x14002aebc`
- `0x14002c070`
- `0x14002c084`
- `0x14002c3e8`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall XmlException::ThrowIfError(struct IUnknown **a1)
{
  struct IUnknown *v1; // rbx
  int v2; // eax
  struct IUnknown *v3; // rbx
  int v4; // eax
  struct IUnknown *v6; // rax
  _QWORD *v7; // rax
  __int64 v8; // r14
  struct IUnknown *v9; // rax
  int v10; // esi
  struct IUnknown *v11; // rax
  unsigned int v12; // edi
  struct IUnknown *v13; // rax
  _QWORD *v14; // rax
  __int64 v15; // rbx
  ResourceMsg *v16; // rax
  __int64 v17; // rax
  const unsigned __int16 *v18; // rax
  __int64 v19; // [rsp+30h] [rbp-20h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-18h] BYREF
  struct IUnknown *v21; // [rsp+80h] [rbp+30h] BYREF
  struct IUnknown *v22; // [rsp+88h] [rbp+38h] BYREF
  __int64 v23; // [rsp+90h] [rbp+40h] BYREF
  __int64 v24; // [rsp+98h] [rbp+48h] BYREF

  v1 = *a1;
  if ( !*a1 )
    _com_issue_error(-2147467261);
  v21 = 0;
  v2 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v1->lpVtbl[20].QueryInterface)(v1, &v21);
  if ( v2 < 0 )
    _com_issue_errorex(v2, v1, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
  v3 = v21;
  v22 = v21;
  if ( !v21 )
    _com_issue_error(-2147467261);
  LODWORD(v21) = 0;
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v3->lpVtbl[2].AddRef)(v3, &v21);
  if ( v4 < 0 )
    _com_issue_errorex(v4, v3, &GUID_3efaa426_272f_11d2_836f_0000f87a7782);
  if ( (_DWORD)v21 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v21);
    v6 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML::IXMLDOMParseError,&__s_GUID const _GUID_3efaa426_272f_11d2_836f_0000f87a7782>>::operator->((__int64 *)&v22);
    v7 = MSXML::IXMLDOMParseError::GetsrcText(v6, &v19);
    v8 = _bstr_t::operator unsigned short const *(v7);
    v9 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML::IXMLDOMParseError,&__s_GUID const _GUID_3efaa426_272f_11d2_836f_0000f87a7782>>::operator->((__int64 *)&v22);
    v10 = MSXML::IXMLDOMParseError::Getlinepos(v9);
    v11 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML::IXMLDOMParseError,&__s_GUID const _GUID_3efaa426_272f_11d2_836f_0000f87a7782>>::operator->((__int64 *)&v22);
    v12 = MSXML::IXMLDOMParseError::Getline(v11);
    v13 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML::IXMLDOMParseError,&__s_GUID const _GUID_3efaa426_272f_11d2_836f_0000f87a7782>>::operator->((__int64 *)&v22);
    v14 = MSXML::IXMLDOMParseError::Getreason(v13, &v24);
    v15 = _bstr_t::operator unsigned short const *(v14);
    v16 = ResourceMsg::ResourceMsg((ResourceMsg *)&v23, 0x4AAE0016u);
    v17 = std::unique_ptr<WebRequest>::operator->((__int64)v16);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      (__int64)&v21,
      v17,
      v15,
      v12,
      v10,
      v8);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v23);
    _bstr_t::~_bstr_t((_bstr_t *)&v24);
    _bstr_t::~_bstr_t((_bstr_t *)&v19);
    v18 = (const unsigned __int16 *)std::unique_ptr<WebRequest>::operator->((__int64)&v21);
    XmlException::XmlException((XmlException *)pExceptionObject, -894894036, v18);
    throw (XmlException *)pExceptionObject;
  }
  return ((__int64 (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
}

```

## disassembly

```asm
0x14002aebc  push    rbp
0x14002aebe  push    rbx
0x14002aebf  push    rsi
0x14002aec0  push    rdi
0x14002aec1  push    r14
0x14002aec3  mov     rbp, rsp
0x14002aec6  sub     rsp, 50h
0x14002aeca  xor     edi, edi
0x14002aecc  mov     rbx, [rcx]
0x14002aecf  test    rbx, rbx
0x14002aed2  jz      short loc_14002AF44
0x14002aed4  mov     [rbp+arg_0], rdi
0x14002aed8  mov     rax, [rbx]
0x14002aedb  lea     rdx, [rbp+arg_0]
0x14002aedf  mov     rcx, rbx
0x14002aee2  mov     rax, [rax+1E0h]
0x14002aee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aeee  test    eax, eax
0x14002aef0  js      short loc_14002AF4F
0x14002aef2  mov     rbx, [rbp+arg_0]
0x14002aef6  mov     [rbp+arg_8], rbx
0x14002aefa  test    rbx, rbx
0x14002aefd  jz      short loc_14002AF39
0x14002aeff  mov     dword ptr [rbp+arg_0], edi
0x14002af02  mov     rax, [rbx]
0x14002af05  lea     rdx, [rbp+arg_0]
0x14002af09  mov     rcx, rbx
0x14002af0c  mov     rax, [rax+38h]
0x14002af10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002af15  test    eax, eax
0x14002af17  js      short loc_14002AF61
0x14002af19  cmp     dword ptr [rbp+arg_0], edi
0x14002af1c  jnz     short loc_14002AF73
0x14002af1e  mov     rax, [rbx]
0x14002af21  mov     rcx, rbx
0x14002af24  mov     rax, [rax+10h]
0x14002af28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002af2d  nop
0x14002af2e  add     rsp, 50h
0x14002af32  pop     r14
0x14002af34  pop     rdi
0x14002af35  pop     rsi
0x14002af36  pop     rbx
0x14002af37  pop     rbp
0x14002af38  retn
0x14002af39  mov     ecx, 80004003h; int
0x14002af3e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14002af44  mov     ecx, 80004003h; int
0x14002af49  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14002af4f  lea     r8, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14002af56  mov     rdx, rbx; struct IUnknown *
0x14002af59  mov     ecx, eax; int
0x14002af5b  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14002af61  lea     r8, _GUID_3efaa426_272f_11d2_836f_0000f87a7782; struct _GUID *
0x14002af68  mov     rdx, rbx; struct IUnknown *
0x14002af6b  mov     ecx, eax; int
0x14002af6d  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14002af73  lea     rcx, [rbp+arg_0]
0x14002af77  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x14002af7c  nop
0x14002af7d  lea     rcx, [rbp+arg_8]
0x14002af81  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMParseError@MSXML@@$1?_GUID_3efaa426_272f_11d2_836f_0000f87a7782@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMParseError@MSXML@@XZ; _com_ptr_t<_com_IIID<MSXML::IXMLDOMParseError,&__s_GUID const _GUID_3efaa426_272f_11d2_836f_0000f87a7782>>::operator->(void)
0x14002af86  lea     rdx, [rbp+var_20]
0x14002af8a  mov     rcx, rax
0x14002af8d  call    ?GetsrcText@IXMLDOMParseError@MSXML@@QEAA?AV_bstr_t@@XZ; MSXML::IXMLDOMParseError::GetsrcText(void)
0x14002af92  nop
0x14002af93  mov     rcx, rax
0x14002af96  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x14002af9b  mov     r14, rax
0x14002af9e  lea     rcx, [rbp+arg_8]
0x14002afa2  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMParseError@MSXML@@$1?_GUID_3efaa426_272f_11d2_836f_0000f87a7782@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMParseError@MSXML@@XZ; _com_ptr_t<_com_IIID<MSXML::IXMLDOMParseError,&__s_GUID const _GUID_3efaa426_272f_11d2_836f_0000f87a7782>>::operator->(void)
0x14002afa7  mov     rcx, rax; this
0x14002afaa  call    ?Getlinepos@IXMLDOMParseError@MSXML@@QEAAJXZ; MSXML::IXMLDOMParseError::Getlinepos(void)
0x14002afaf  mov     esi, eax
0x14002afb1  lea     rcx, [rbp+arg_8]
0x14002afb5  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMParseError@MSXML@@$1?_GUID_3efaa426_272f_11d2_836f_0000f87a7782@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMParseError@MSXML@@XZ; _com_ptr_t<_com_IIID<MSXML::IXMLDOMParseError,&__s_GUID const _GUID_3efaa426_272f_11d2_836f_0000f87a7782>>::operator->(void)
0x14002afba  mov     rcx, rax; this
0x14002afbd  call    ?Getline@IXMLDOMParseError@MSXML@@QEAAJXZ; MSXML::IXMLDOMParseError::Getline(void)
0x14002afc2  mov     edi, eax
0x14002afc4  lea     rcx, [rbp+arg_8]
0x14002afc8  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMParseError@MSXML@@$1?_GUID_3efaa426_272f_11d2_836f_0000f87a7782@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMParseError@MSXML@@XZ; _com_ptr_t<_com_IIID<MSXML::IXMLDOMParseError,&__s_GUID const _GUID_3efaa426_272f_11d2_836f_0000f87a7782>>::operator->(void)
0x14002afcd  lea     rdx, [rbp+arg_18]
0x14002afd1  mov     rcx, rax
0x14002afd4  call    ?Getreason@IXMLDOMParseError@MSXML@@QEAA?AV_bstr_t@@XZ; MSXML::IXMLDOMParseError::Getreason(void)
0x14002afd9  nop
0x14002afda  mov     rcx, rax
0x14002afdd  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x14002afe2  mov     rbx, rax
0x14002afe5  mov     edx, 4AAE0016h; unsigned int
0x14002afea  lea     rcx, [rbp+arg_10]; this
0x14002afee  call    ??0ResourceMsg@@QEAA@K@Z; ResourceMsg::ResourceMsg(ulong)
0x14002aff3  nop
0x14002aff4  mov     rcx, rax
0x14002aff7  call    ??C?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@QEBAPEAVWebRequest@@XZ; std::unique_ptr<WebRequest>::operator->(void)
0x14002affc  mov     [rsp+50h+var_28], r14
0x14002b001  mov     [rsp+50h+var_30], esi
0x14002b005  mov     r9d, edi
0x14002b008  mov     r8, rbx
0x14002b00b  mov     rdx, rax
0x14002b00e  lea     rcx, [rbp+arg_0]
0x14002b012  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14002b017  nop
0x14002b018  lea     rcx, [rbp+arg_10]
0x14002b01c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x14002b021  nop
0x14002b022  lea     rcx, [rbp+arg_18]; this
0x14002b026  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14002b02b  nop
0x14002b02c  lea     rcx, [rbp+var_20]; this
0x14002b030  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14002b035  lea     rcx, [rbp+arg_0]
0x14002b039  call    ??C?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@QEBAPEAVWebRequest@@XZ; std::unique_ptr<WebRequest>::operator->(void)
0x14002b03e  mov     r8, rax; unsigned __int16 *
0x14002b041  mov     edx, 0CAA9002Ch; unsigned int
0x14002b046  lea     rcx, [rbp+pExceptionObject]; this
0x14002b04a  call    ??0XmlException@@QEAA@KPEBG@Z; XmlException::XmlException(ulong,ushort const *)
0x14002b04f  lea     rdx, _TI2?AVXmlException@@; pThrowInfo
0x14002b056  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14002b05a  call    _CxxThrowException_0
```
