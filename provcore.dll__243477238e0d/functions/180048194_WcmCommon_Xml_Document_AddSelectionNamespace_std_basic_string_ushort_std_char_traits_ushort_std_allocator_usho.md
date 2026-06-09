# WcmCommon::Xml::Document::AddSelectionNamespace(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180048194`
- end: `0x180048324`
- name: `?AddSelectionNamespace@Document@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `400`
- prototype: `void __fastcall(WcmCommon::Xml::Document *this, const std::wstring *key, const std::wstring *ns)`
- caller_count: `12`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bfe0`
- `0x18001e71c`
- `0x18001edd8`
- `0x180025e30`
- `0x180041e3c`
- `0x180042f44`
- `0x180043660`
- `0x180045d80`
- `0x180045fd0`
- `0x180046114`
- `0x180046230`
- `0x18004b480`

## callees

- `0x180002790`
- `0x1800085fc`
- `0x18000af94`
- `0x18000b1e4`
- `0x180010c34`
- `0x180011844`
- `0x180011cfc`
- `0x180011fdc`
- `0x180012400`
- `0x180047a10`
- `0x180047bac`
- `0x180047dac`
- `0x180048194`
- `0x18004a4bc`
- `0x18004a83c`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180048200`
- `OLEAUT32!__imp_VariantClear` at `0x1800482f0`
- `OLEAUT32!__imp_VariantClear` at `0x180048200`
- `OLEAUT32!__imp_VariantClear` at `0x1800482f0`

## string_xrefs

- `0x180048220`: ` xmlns`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall WcmCommon::Xml::Document::AddSelectionNamespace(
        WcmCommon::Xml::Document *this,
        const std::wstring *key,
        const std::wstring *ns)
{
  MSXML2::IXMLDOMDocument2 *v6; // rbx
  _bstr_t v7; // rax
  const _variant_t *Property; // rax
  wchar_t *m_wstr; // rdx
  unsigned __int64 v10; // rax
  const wchar_t *v11; // rcx
  unsigned __int64 v12; // rax
  const wchar_t *v13; // rcx
  unsigned __int64 v14; // rax
  const wchar_t *v15; // rcx
  unsigned __int64 v16; // rax
  const wchar_t *v17; // rcx
  MSXML2::IXMLDOMDocument2 *v18; // rbx
  const wchar_t *v19; // rax
  _bstr_t v20; // rax
  _bstr_t oldns; // [rsp+20h] [rbp-60h] BYREF
  _bstr_t v22; // [rsp+28h] [rbp-58h] BYREF
  _variant_t result; // [rsp+38h] [rbp-48h] BYREF
  std::wstring newns; // [rsp+50h] [rbp-30h] BYREF

  oldns.m_Data = 0;
  v6 = (MSXML2::IXMLDOMDocument2 *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->((_com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *)this->m_details._Ptr);
  _bstr_t::_bstr_t(&v22, L"SelectionNamespaces");
  Property = MSXML2::IXMLDOMDocument2::getProperty(v6, &result, v7);
  _bstr_t::_bstr_t(&oldns, Property);
  VariantClear(&result);
  if ( oldns.m_Data )
    m_wstr = oldns.m_Data->m_wstr;
  else
    m_wstr = 0;
  std::wstring::wstring(&newns, m_wstr);
  v10 = std::_WChar_traits<unsigned short>::length(L" xmlns");
  std::wstring::_Append<unsigned short>(&newns, v11, v10);
  if ( key->_Mypair._Myval2._Mysize )
  {
    v12 = std::_WChar_traits<unsigned short>::length(L":");
    std::wstring::_Append<unsigned short>(&newns, v13, v12);
    std::wstring::append(&newns, key);
  }
  v14 = std::_WChar_traits<unsigned short>::length(L"='");
  std::wstring::_Append<unsigned short>(&newns, v15, v14);
  std::wstring::append(&newns, ns);
  v16 = std::_WChar_traits<unsigned short>::length(L"'");
  std::wstring::_Append<unsigned short>(&newns, v17, v16);
  v18 = (MSXML2::IXMLDOMDocument2 *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->((_com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *)this->m_details._Ptr);
  v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&newns._Mypair._Myval2);
  _variant_t::_variant_t(&result, v19);
  _bstr_t::_bstr_t(&v22, L"SelectionNamespaces");
  MSXML2::IXMLDOMDocument2::setProperty(v18, v20, &result);
  VariantClear(&result);
  std::wstring::_Tidy_deallocate(&newns);
  _bstr_t::_Free(&oldns);
}

```

## disassembly

```asm
0x180048194  push    rbp
0x180048196  push    rbx
0x180048197  push    rsi
0x180048198  push    rdi
0x180048199  push    r14
0x18004819b  mov     rbp, rsp
0x18004819e  sub     rsp, 80h
0x1800481a5  mov     rax, cs:__security_cookie
0x1800481ac  xor     rax, rsp
0x1800481af  mov     [rbp+var_10], rax
0x1800481b3  mov     r14, ns
0x1800481b6  mov     rdi, key
0x1800481b9  mov     rsi, this
0x1800481bc  mov     [rbp+oldns.m_Data], 0
0x1800481c4  mov     this, [this]; this
0x1800481c7  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMNodeList@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x1800481cc  mov     rbx, rax
0x1800481cf  lea     key, aSelectionnames; "SelectionNamespaces"
0x1800481d6  lea     this, [rbp+var_58]; this
0x1800481da  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800481df  mov     ns, rax; name
0x1800481e2  lea     key, [rbp+result]; result
0x1800481e6  mov     this, rbx; this
0x1800481e9  call    ?getProperty@IXMLDOMDocument2@MSXML2@@QEAA?AV_variant_t@@V_bstr_t@@@Z; MSXML2::IXMLDOMDocument2::getProperty(_bstr_t)
0x1800481ee  nop
0x1800481ef  mov     key, rax; var
0x1800481f2  lea     this, [rbp+oldns]; this
0x1800481f6  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x1800481fb  nop
0x1800481fc  lea     this, [rbp+result]; pvarg
0x180048200  call    cs:__imp_VariantClear
0x180048206  mov     rax, [rbp+oldns.m_Data]
0x18004820a  test    rax, rax
0x18004820d  jz      short loc_180048214
0x18004820f  mov     key, [rax]
0x180048212  jmp     short loc_180048216
0x180048214  xor     edx, edx; _Ptr
0x180048216  lea     this, [rbp+newns]; this
0x18004821a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004821f  nop
0x180048220  lea     this, aXmlns; " xmlns"
0x180048227  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18004822c  mov     ns, rax; _Count
0x18004822f  mov     key, this; _Ptr
0x180048232  lea     this, [rbp+newns]; this
0x180048236  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004823b  cmp     qword ptr [rdi+10h], 0
0x180048240  jz      short loc_180048269
0x180048242  lea     this, asc_18007B998; ":"
0x180048249  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18004824e  mov     ns, rax; _Count
0x180048251  mov     key, this; _Ptr
0x180048254  lea     this, [rbp+newns]; this
0x180048258  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004825d  mov     key, rdi; _Right
0x180048260  lea     this, [rbp+newns]; this
0x180048264  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180048269  lea     this, asc_18007B99C; "='"
0x180048270  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180048275  mov     ns, rax; _Count
0x180048278  mov     key, this; _Ptr
0x18004827b  lea     this, [rbp+newns]; this
0x18004827f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180048284  mov     key, r14; _Right
0x180048287  lea     this, [rbp+newns]; this
0x18004828b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180048290  lea     this, asc_18007B9A4; "'"
0x180048297  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18004829c  mov     ns, rax; _Count
0x18004829f  mov     key, this; _Ptr
0x1800482a2  lea     this, [rbp+newns]; this
0x1800482a6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800482ab  mov     this, [rsi]; this
0x1800482ae  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMNodeList@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x1800482b3  mov     rbx, rax
0x1800482b6  lea     this, [rbp+newns]; this
0x1800482ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800482bf  mov     key, rax; pSrc
0x1800482c2  lea     this, [rbp+result]; this
0x1800482c6  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x1800482cb  nop
0x1800482cc  lea     key, aSelectionnames; "SelectionNamespaces"
0x1800482d3  lea     this, [rbp+var_58]; this
0x1800482d7  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800482dc  lea     ns, [rbp+result]; value
0x1800482e0  mov     key, rax; name
0x1800482e3  mov     this, rbx; this
0x1800482e6  call    ?setProperty@IXMLDOMDocument2@MSXML2@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; MSXML2::IXMLDOMDocument2::setProperty(_bstr_t,_variant_t const &)
0x1800482eb  nop
0x1800482ec  lea     this, [rbp+result]; pvarg
0x1800482f0  call    cs:__imp_VariantClear
0x1800482f6  nop
0x1800482f7  lea     this, [rbp+newns]; this
0x1800482fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048300  nop
0x180048301  lea     this, [rbp+oldns]; this
0x180048305  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004830a  mov     this, [rbp+var_10]
0x18004830e  xor     this, rsp; StackCookie
0x180048311  call    __security_check_cookie
0x180048316  add     rsp, 80h
0x18004831d  pop     r14
0x18004831f  pop     rdi
0x180048320  pop     rsi
0x180048321  pop     rbx
0x180048322  pop     rbp
0x180048323  retn
```
