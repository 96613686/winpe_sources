# GetTuneXmlNamespaceFromCLSID(_GUID const &,ushort * *)

- ea: `0x180055448`
- end: `0x180055550`
- name: `?GetTuneXmlNamespaceFromCLSID@@YAJAEBU_GUID@@PEAPEAG@Z`
- size: `264`
- prototype: `__int64 __fastcall(IID *rclsid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180055558`

## callees

- `0x18000e294`
- `0x18000ff74`
- `0x180015f90`
- `0x180015fbc`
- `0x180055448`
- `0x180055e80`
- `0x180056044`

## import_xrefs

- `ole32!StringFromCLSID` at `0x1800554a3`
- `ole32!StringFromCLSID` at `0x1800554a3`
- `ole32!CoTaskMemFree` at `0x1800554cb`
- `ole32!CoTaskMemFree` at `0x1800554cb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800554b5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800554b5`
- `OLEAUT32!__imp_SysFreeString` at `0x180055532`
- `OLEAUT32!__imp_SysFreeString` at `0x18005553b`
- `OLEAUT32!__imp_SysFreeString` at `0x180055532`
- `OLEAUT32!__imp_SysFreeString` at `0x18005553b`

## string_xrefs

- `0x18005547d`: `SOFTWARE\Microsoft\Multimedia\TV\Persist Tune Xml\Type Namespace Map`

## pseudocode

```c
HRESULT __fastcall GetTuneXmlNamespaceFromCLSID(IID *rclsid, unsigned __int16 **a2)
{
  HRESULT result; // eax
  OLECHAR *v5; // rbx
  _QWORD *v6; // rax
  __int64 v7; // r8
  int v8; // esi
  __int64 v9; // rax
  OLECHAR *v10; // rdi
  LPOLESTR lpsz; // [rsp+48h] [rbp+28h] BYREF
  unsigned __int16 *v12; // [rsp+50h] [rbp+30h] BYREF
  char v13; // [rsp+58h] [rbp+38h] BYREF

  if ( !a2 )
    return -2147467261;
  if ( qword_18021D148
    || (result = LoadTuneXmlLookupMap(
                   &qword_18021D140,
                   L"SOFTWARE\\Microsoft\\Multimedia\\TV\\Persist Tune Xml\\Type Namespace Map"),
        result >= 0) )
  {
    lpsz = 0;
    result = StringFromCLSID(rclsid, &lpsz);
    if ( result >= 0 )
    {
      v5 = SysAllocString(lpsz);
      v12 = v5;
      if ( lpsz )
      {
        CoTaskMemFree(lpsz);
        lpsz = 0;
      }
      v12 = *(unsigned __int16 **)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComBSTR,less_bstr_insensitive,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComBSTR>>,0>>::find(
                                    &qword_18021D140,
                                    &v13,
                                    &v12);
      v6 = (_QWORD *)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
                       &qword_18021D140,
                       &v13);
      if ( v7 == *v6 )
      {
        v8 = -2147023728;
      }
      else
      {
        v9 = std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,ATL::CComVariant>>>>::operator*(&v12);
        v12 = ATL::CComBSTR::Copy((ATL::CComBSTR *)(v9 + 8));
        v10 = v12;
        v8 = ATL::CComBSTR::CopyTo((ATL::CComBSTR *)&v12, a2);
        SysFreeString(v10);
      }
      SysFreeString(v5);
      return v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180055448  mov     [rsp-18h+arg_0], rbx
0x18005544d  push    rbp
0x18005544e  push    rsi
0x18005544f  push    rdi
0x180055450  mov     rbp, rsp
0x180055453  sub     rsp, 20h
0x180055457  mov     rsi, rdx
0x18005545a  mov     rbx, rcx
0x18005545d  test    rdx, rdx
0x180055460  jnz     short loc_18005546C
0x180055462  mov     eax, 80004003h
0x180055467  jmp     loc_180055543
0x18005546c  cmp     cs:qword_18021D148, 0
0x180055474  lea     rdi, qword_18021D140
0x18005547b  jnz     short loc_180055494
0x18005547d  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Multimedia\\TV\\Pe"...
0x180055484  mov     rcx, rdi
0x180055487  call    ?LoadTuneXmlLookupMap@@YAJPEAV?$map@VCComBSTR@ATL@@V12@Uless_bstr_insensitive@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V12@@std@@@std@@@std@@PEBG@Z; LoadTuneXmlLookupMap(std::map<ATL::CComBSTR,ATL::CComBSTR,less_bstr_insensitive,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComBSTR>>> *,ushort const *)
0x18005548c  test    eax, eax
0x18005548e  js      loc_180055543
0x180055494  lea     rdx, [rbp+lpsz]; lplpsz
0x180055498  mov     [rbp+lpsz], 0
0x1800554a0  mov     rcx, rbx; rclsid
0x1800554a3  call    cs:__imp_StringFromCLSID
0x1800554a9  test    eax, eax
0x1800554ab  js      loc_180055543
0x1800554b1  mov     rcx, [rbp+lpsz]; psz
0x1800554b5  call    cs:__imp_SysAllocString
0x1800554bb  mov     rcx, [rbp+lpsz]; pv
0x1800554bf  mov     rbx, rax
0x1800554c2  mov     [rbp+arg_10], rax
0x1800554c6  test    rcx, rcx
0x1800554c9  jz      short loc_1800554D9
0x1800554cb  call    cs:__imp_CoTaskMemFree
0x1800554d1  mov     [rbp+lpsz], 0
0x1800554d9  lea     r8, [rbp+arg_10]
0x1800554dd  mov     rcx, rdi
0x1800554e0  lea     rdx, [rbp+arg_18]
0x1800554e4  call    ?find@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@V12@Uless_bstr_insensitive@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V12@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@V12@@std@@@std@@@std@@@2@AEBVCComBSTR@ATL@@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComBSTR,less_bstr_insensitive,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComBSTR>>,0>>::find(ATL::CComBSTR const &)
0x1800554e9  lea     rdx, [rbp+arg_18]
0x1800554ed  mov     rcx, rdi
0x1800554f0  mov     r8, [rax]
0x1800554f3  mov     [rbp+arg_10], r8
0x1800554f7  call    ?end@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@KU?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ulong,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ulong>>,0>>::end(void)
0x1800554fc  cmp     r8, [rax]
0x1800554ff  jnz     short loc_180055508
0x180055501  mov     esi, 80070490h
0x180055506  jmp     short loc_180055538
0x180055508  lea     rcx, [rbp+arg_10]
0x18005550c  call    ??D?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKVCComVariant@ATL@@@std@@@std@@@std@@@std@@QEBAAEAU?$pair@$$CBKVCComVariant@ATL@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ATL::CComVariant>>>>::operator*(void)
0x180055511  lea     rcx, [rax+8]; this
0x180055515  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x18005551a  mov     rdx, rsi; unsigned __int16 **
0x18005551d  mov     [rbp+arg_10], rax
0x180055521  lea     rcx, [rbp+arg_10]; this
0x180055525  mov     rdi, rax
0x180055528  call    ?CopyTo@CComBSTR@ATL@@QEAAJPEAPEAG@Z; ATL::CComBSTR::CopyTo(ushort * *)
0x18005552d  mov     rcx, rdi; bstrString
0x180055530  mov     esi, eax
0x180055532  call    cs:__imp_SysFreeString
0x180055538  mov     rcx, rbx; bstrString
0x18005553b  call    cs:__imp_SysFreeString
0x180055541  mov     eax, esi
0x180055543  mov     rbx, [rsp+20h+arg_0]
0x180055548  add     rsp, 20h
0x18005554c  pop     rdi
0x18005554d  pop     rsi
0x18005554e  pop     rbp
0x18005554f  retn
```
