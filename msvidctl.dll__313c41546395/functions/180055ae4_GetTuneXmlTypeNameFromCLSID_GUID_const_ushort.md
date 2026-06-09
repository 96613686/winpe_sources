# GetTuneXmlTypeNameFromCLSID(_GUID const &,ushort * *)

- ea: `0x180055ae4`
- end: `0x180055c6f`
- name: `?GetTuneXmlTypeNameFromCLSID@@YAJAEBU_GUID@@PEAPEAG@Z`
- size: `395`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800176bc`
- `0x18002d37c`
- `0x180052898`
- `0x180053df0`

## callees

- `0x18000e294`
- `0x18000e2a0`
- `0x18000ff74`
- `0x180015fbc`
- `0x180054aa4`
- `0x180054b08`
- `0x180055558`
- `0x180055ae4`
- `0x180055e80`

## import_xrefs

- `ole32!StringFromCLSID` at `0x180055b62`
- `ole32!StringFromCLSID` at `0x180055b62`
- `ole32!CoTaskMemFree` at `0x180055b8a`
- `ole32!CoTaskMemFree` at `0x180055b8a`
- `OLEAUT32!__imp_SysAllocString` at `0x180055b74`
- `OLEAUT32!__imp_SysAllocString` at `0x180055b74`
- `OLEAUT32!__imp_SysFreeString` at `0x180055bbc`
- `OLEAUT32!__imp_SysFreeString` at `0x180055bf2`
- `OLEAUT32!__imp_SysFreeString` at `0x180055bfc`
- `OLEAUT32!__imp_SysFreeString` at `0x180055c2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180055c35`
- `OLEAUT32!__imp_SysFreeString` at `0x180055c3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180055bbc`
- `OLEAUT32!__imp_SysFreeString` at `0x180055bf2`
- `OLEAUT32!__imp_SysFreeString` at `0x180055bfc`
- `OLEAUT32!__imp_SysFreeString` at `0x180055c2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180055c35`
- `OLEAUT32!__imp_SysFreeString` at `0x180055c3f`

## string_xrefs

- `0x180055b11`: `SOFTWARE\Microsoft\Multimedia\TV\Persist Tune Xml\Type Map`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall GetTuneXmlTypeNameFromCLSID(const struct _GUID *a1, unsigned __int16 **a2)
{
  HRESULT result; // eax
  _QWORD *v5; // rax
  __int64 v6; // r8
  OLECHAR *v7; // rbx
  unsigned __int16 **v8; // rsi
  int TuneXmlPrefixFromCLSID; // edi
  OLECHAR *v10; // rdi
  int v11; // esi
  unsigned __int16 *v12; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v13[8]; // [rsp+28h] [rbp-18h] BYREF
  OLECHAR *v14; // [rsp+30h] [rbp-10h]
  BSTR i; // [rsp+78h] [rbp+38h] BYREF
  LPOLESTR lpsz; // [rsp+80h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+48h] BYREF

  if ( !a2 )
    return -2147467261;
  if ( qword_18021D138
    || (result = LoadTuneXmlLookupMap(
                   &qword_18021D130,
                   L"SOFTWARE\\Microsoft\\Multimedia\\TV\\Persist Tune Xml\\Type Map"),
        result >= 0) )
  {
    for ( i = *(BSTR *)qword_18021D130;
          ;
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,ATL::CComBSTR>>>,std::_Iterator_base0>::operator++(&i) )
    {
      v5 = (_QWORD *)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
                       &qword_18021D130,
                       v13);
      if ( v6 == *v5 )
        return -2147023728;
      lpsz = 0;
      result = StringFromCLSID(a1, &lpsz);
      if ( result < 0 )
        return result;
      v7 = SysAllocString(lpsz);
      v14 = v7;
      if ( lpsz )
        CoTaskMemFree(lpsz);
      bstrString = v7;
      v8 = (unsigned __int16 **)std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,ATL::CComVariant>>>>::operator*(&i);
      v12 = v8[1];
      if ( (unsigned int)IsEqualBSTRInsensitive(&v12, &bstrString) )
        break;
      SysFreeString(v7);
    }
    bstrString = 0;
    TuneXmlPrefixFromCLSID = GetTuneXmlPrefixFromCLSID(a1, &bstrString);
    if ( TuneXmlPrefixFromCLSID >= 0 )
    {
      i = 0;
      v10 = bstrString;
      v11 = PrefixType(bstrString, *v8, &i);
      if ( v11 >= 0 )
      {
        v11 = ATL::CComBSTR::CopyTo((ATL::CComBSTR *)&i, a2);
        if ( v11 >= 0 )
          v11 = 0;
      }
      SysFreeString(i);
      SysFreeString(v10);
      SysFreeString(v7);
      return v11;
    }
    else
    {
      SysFreeString(bstrString);
      SysFreeString(v7);
      return TuneXmlPrefixFromCLSID;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180055ae4  push    rbp
0x180055ae6  push    rbx
0x180055ae7  push    rsi
0x180055ae8  push    rdi
0x180055ae9  push    r14
0x180055aeb  mov     rbp, rsp
0x180055aee  sub     rsp, 40h
0x180055af2  mov     r14, rdx
0x180055af5  mov     rdi, rcx
0x180055af8  test    rdx, rdx
0x180055afb  jnz     short loc_180055B07
0x180055afd  mov     eax, 80004003h
0x180055b02  jmp     loc_180055C64
0x180055b07  cmp     cs:qword_18021D138, 0
0x180055b0f  jnz     short loc_180055B2C
0x180055b11  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Multimedia\\TV\\Pe"...
0x180055b18  lea     rcx, qword_18021D130
0x180055b1f  call    ?LoadTuneXmlLookupMap@@YAJPEAV?$map@VCComBSTR@ATL@@V12@Uless_bstr_insensitive@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V12@@std@@@std@@@std@@PEBG@Z; LoadTuneXmlLookupMap(std::map<ATL::CComBSTR,ATL::CComBSTR,less_bstr_insensitive,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComBSTR>>> *,ushort const *)
0x180055b24  test    eax, eax
0x180055b26  js      loc_180055C64
0x180055b2c  mov     r8, cs:qword_18021D130
0x180055b33  mov     r8, [r8]
0x180055b36  mov     [rbp+arg_8], r8
0x180055b3a  lea     rdx, [rbp+var_18]
0x180055b3e  lea     rcx, qword_18021D130
0x180055b45  call    ?end@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@KU?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ulong,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ulong>>,0>>::end(void)
0x180055b4a  cmp     r8, [rax]
0x180055b4d  jz      loc_180055C5F
0x180055b53  mov     [rbp+lpsz], 0
0x180055b5b  lea     rdx, [rbp+lpsz]; lplpsz
0x180055b5f  mov     rcx, rdi; rclsid
0x180055b62  call    cs:__imp_StringFromCLSID
0x180055b68  test    eax, eax
0x180055b6a  js      loc_180055C64
0x180055b70  mov     rcx, [rbp+lpsz]; psz
0x180055b74  call    cs:__imp_SysAllocString
0x180055b7a  mov     rbx, rax
0x180055b7d  mov     [rbp+var_10], rax
0x180055b81  mov     rcx, [rbp+lpsz]; pv
0x180055b85  test    rcx, rcx
0x180055b88  jz      short loc_180055B90
0x180055b8a  call    cs:__imp_CoTaskMemFree
0x180055b90  mov     [rbp+bstrString], rbx
0x180055b94  lea     rcx, [rbp+arg_8]
0x180055b98  call    ??D?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKVCComVariant@ATL@@@std@@@std@@@std@@@std@@QEBAAEAU?$pair@$$CBKVCComVariant@ATL@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ATL::CComVariant>>>>::operator*(void)
0x180055b9d  mov     rsi, rax
0x180055ba0  mov     rcx, [rax+8]
0x180055ba4  mov     [rbp+var_20], rcx
0x180055ba8  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x180055bac  lea     rcx, [rbp+var_20]; unsigned __int16 **
0x180055bb0  call    ?IsEqualBSTRInsensitive@@YAHAEBQEAG0@Z; IsEqualBSTRInsensitive(ushort * const &,ushort * const &)
0x180055bb5  test    eax, eax
0x180055bb7  jnz     short loc_180055BD4
0x180055bb9  mov     rcx, rbx; bstrString
0x180055bbc  call    cs:__imp_SysFreeString
0x180055bc2  lea     rcx, [rbp+arg_8]
0x180055bc6  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,ATL::CComBSTR>>>,std::_Iterator_base0>::operator++(void)
0x180055bcb  mov     r8, [rbp+arg_8]
0x180055bcf  jmp     loc_180055B3A
0x180055bd4  mov     [rbp+bstrString], 0
0x180055bdc  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x180055be0  mov     rcx, rdi; struct _GUID *
0x180055be3  call    ?GetTuneXmlPrefixFromCLSID@@YAJAEBU_GUID@@PEAPEAG@Z; GetTuneXmlPrefixFromCLSID(_GUID const &,ushort * *)
0x180055be8  mov     edi, eax
0x180055bea  test    eax, eax
0x180055bec  jns     short loc_180055C06
0x180055bee  mov     rcx, [rbp+bstrString]; bstrString
0x180055bf2  call    cs:__imp_SysFreeString
0x180055bf8  nop
0x180055bf9  mov     rcx, rbx; bstrString
0x180055bfc  call    cs:__imp_SysFreeString
0x180055c02  mov     eax, edi
0x180055c04  jmp     short loc_180055C64
0x180055c06  mov     [rbp+arg_8], 0
0x180055c0e  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x180055c12  mov     rdx, [rsi]; unsigned __int16 *
0x180055c15  mov     rdi, [rbp+bstrString]
0x180055c19  mov     rcx, rdi; unsigned __int16 *
0x180055c1c  call    ?PrefixType@@YAJPEAG0PEAPEAG@Z; PrefixType(ushort *,ushort *,ushort * *)
0x180055c21  mov     esi, eax
0x180055c23  test    eax, eax
0x180055c25  jns     short loc_180055C49
0x180055c27  mov     rcx, [rbp+arg_8]; bstrString
0x180055c2b  call    cs:__imp_SysFreeString
0x180055c31  nop
0x180055c32  mov     rcx, rdi; bstrString
0x180055c35  call    cs:__imp_SysFreeString
0x180055c3b  nop
0x180055c3c  mov     rcx, rbx; bstrString
0x180055c3f  call    cs:__imp_SysFreeString
0x180055c45  mov     eax, esi
0x180055c47  jmp     short loc_180055C64
0x180055c49  mov     rdx, r14; unsigned __int16 **
0x180055c4c  lea     rcx, [rbp+arg_8]; this
0x180055c50  call    ?CopyTo@CComBSTR@ATL@@QEAAJPEAPEAG@Z; ATL::CComBSTR::CopyTo(ushort * *)
0x180055c55  mov     esi, eax
0x180055c57  test    eax, eax
0x180055c59  js      short loc_180055C27
0x180055c5b  xor     esi, esi
0x180055c5d  jmp     short loc_180055C27
0x180055c5f  mov     eax, 80070490h
0x180055c64  add     rsp, 40h
0x180055c68  pop     r14
0x180055c6a  pop     rdi
0x180055c6b  pop     rsi
0x180055c6c  pop     rbx
0x180055c6d  pop     rbp
0x180055c6e  retn
```
