# EapHost::BaseXmlHelper::String2Document(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)

- ea: `0x1800162d4`
- end: `0x1800163f9`
- name: `?String2Document@BaseXmlHelper@EapHost@@SA?AV?$CComPtr@UIXMLDOMDocument2@@@ATL@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `293`
- prototype: `LPVOID *__fastcall(LPVOID *ppv, __int64)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d430`
- `0x18000d6e0`
- `0x180015fc4`
- `0x18001e8b0`

## callees

- `0x180004ec0`
- `0x18000eb74`
- `0x18001549c`
- `0x180015ed4`
- `0x18001617c`
- `0x1800162a4`
- `0x1800162d4`
- `0x180034010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800163d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800163d0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016364`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016364`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
LPVOID *__fastcall EapHost::BaseXmlHelper::String2Document(LPVOID *ppv, __int64 a2)
{
  HRESULT Instance; // eax
  unsigned int v5; // ecx
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, _QWORD, __int16 *); // rbx
  const wchar_t *v8; // rax
  _QWORD *v9; // rax
  unsigned int v10; // ebx
  void **v12; // [rsp+38h] [rbp-28h] BYREF
  char v13; // [rsp+40h] [rbp-20h]
  __int64 v14; // [rsp+44h] [rbp-1Ch]
  int v15; // [rsp+50h] [rbp-10h]
  __int16 v16; // [rsp+A0h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+A8h] [rbp+48h] BYREF

  *ppv = 0;
  v13 = 0;
  v14 = 0;
  v12 = &EapHost::EapMethodType::`vftable';
  v15 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_1dc4107c12973fe87cbae404ee4330ac_Traceguids);
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, ppv);
  if ( Instance < 0 )
  {
    v5 = (unsigned __int16)Instance;
    if ( (Instance & 0x1FFF0000) != 0x70000 )
      v5 = Instance;
    EapHost::EapException::Throw(v5, (const struct EapHost::EapMethodType *)&v12, Instance);
  }
  v16 = 0;
  v6 = *ppv;
  v7 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int16 *))(*(_QWORD *)*ppv + 520LL);
  v8 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  v9 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v8);
  v10 = v7(v6, *v9, &v16);
  SysFreeString(bstrString);
  if ( v10 )
  {
    ATL::CComPtrBase<IXMLDOMDocument2>::Release(ppv);
    EapHost::BaseXmlHelper::GetXmlErrorAndThrow(v10);
  }
  return ppv;
}

```

## disassembly

```asm
0x1800162d4  mov     [rsp-28h+arg_0], rcx
0x1800162d9  push    rbp
0x1800162da  push    rbx
0x1800162db  push    rsi
0x1800162dc  push    rdi
0x1800162dd  push    r14
0x1800162df  mov     rbp, rsp
0x1800162e2  sub     rsp, 60h
0x1800162e6  mov     r14, rdx
0x1800162e9  mov     rsi, rcx
0x1800162ec  mov     [rbp+var_30], 0
0x1800162f3  mov     qword ptr [rcx], 0
0x1800162fa  mov     ebx, 1
0x1800162ff  mov     [rbp+var_30], ebx
0x180016302  mov     [rbp+var_20], 0
0x180016306  mov     [rbp+var_1C], 0
0x18001630e  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180016315  mov     [rbp+var_28], rax
0x180016319  mov     [rbp+var_10], 0
0x180016320  lea     rax, WPP_GLOBAL_Control
0x180016327  mov     rcx, cs:WPP_GLOBAL_Control
0x18001632e  cmp     rcx, rax
0x180016331  jz      short loc_18001634C
0x180016333  test    byte ptr [rcx+1Ch], 4
0x180016337  jz      short loc_18001634C
0x180016339  lea     edx, [rbx+10h]
0x18001633c  lea     r8, WPP_1dc4107c12973fe87cbae404ee4330ac_Traceguids
0x180016343  mov     rcx, [rcx+10h]
0x180016347  call    WPP_SF_
0x18001634c  mov     [rsp+60h+ppv], rsi; ppv
0x180016351  lea     r9, IID_IXMLDOMDocument2; riid
0x180016358  mov     r8d, ebx; dwClsContext
0x18001635b  xor     edx, edx; pUnkOuter
0x18001635d  lea     rcx, CLSID_DOMDocument60; rclsid
0x180016364  call    cs:__imp_CoCreateInstance
0x18001636a  test    eax, eax
0x18001636c  jns     short loc_180016390
0x18001636e  mov     ecx, eax
0x180016370  and     ecx, 1FFF0000h
0x180016376  cmp     ecx, 70000h
0x18001637c  movzx   ecx, ax
0x18001637f  jz      short loc_180016383
0x180016381  mov     ecx, eax; unsigned int
0x180016383  mov     r8d, eax; unsigned int
0x180016386  lea     rdx, [rbp+var_28]; struct EapHost::EapMethodType *
0x18001638a  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x180016390  xor     eax, eax
0x180016392  mov     [rbp+arg_10], ax
0x180016396  mov     rdi, [rsi]
0x180016399  mov     rax, [rdi]
0x18001639c  mov     rbx, [rax+208h]
0x1800163a3  mov     rcx, r14
0x1800163a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800163ab  mov     rdx, rax; wchar_t *
0x1800163ae  lea     rcx, [rbp+bstrString]; this
0x1800163b2  call    ??0CComBSTR@ATL@@QEAA@PEB_W@Z; ATL::CComBSTR::CComBSTR(wchar_t const *)
0x1800163b7  nop
0x1800163b8  lea     r8, [rbp+arg_10]
0x1800163bc  mov     rdx, [rax]
0x1800163bf  mov     rcx, rdi
0x1800163c2  mov     rax, rbx
0x1800163c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163ca  mov     ebx, eax
0x1800163cc  mov     rcx, [rbp+bstrString]; bstrString
0x1800163d0  call    cs:__imp_SysFreeString
0x1800163d6  test    ebx, ebx
0x1800163d8  jz      short loc_1800163EA
0x1800163da  mov     rcx, rsi
0x1800163dd  call    ?Release@?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMDocument2>::Release(void)
0x1800163e2  mov     ecx, ebx; unsigned int
0x1800163e4  call    ?GetXmlErrorAndThrow@BaseXmlHelper@EapHost@@SAXJ@Z; EapHost::BaseXmlHelper::GetXmlErrorAndThrow(long)
0x1800163ea  mov     rax, rsi
0x1800163ed  add     rsp, 60h
0x1800163f1  pop     r14
0x1800163f3  pop     rdi
0x1800163f4  pop     rsi
0x1800163f5  pop     rbx
0x1800163f6  pop     rbp
0x1800163f7  retn
```
