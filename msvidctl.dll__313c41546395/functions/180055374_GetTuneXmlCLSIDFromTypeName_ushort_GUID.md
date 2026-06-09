# GetTuneXmlCLSIDFromTypeName(ushort *,_GUID *)

- ea: `0x180055374`
- end: `0x180055440`
- name: `?GetTuneXmlCLSIDFromTypeName@@YAJPEAGPEAU_GUID@@@Z`
- size: `204`
- prototype: `__int64 __fastcall(OLECHAR *psz, LPCLSID pclsid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180053e90`

## callees

- `0x18000e294`
- `0x18000ff74`
- `0x180055374`
- `0x180055e80`
- `0x180056044`

## import_xrefs

- `ole32!CLSIDFromString` at `0x18005542a`
- `ole32!CLSIDFromString` at `0x18005542a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800553bc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800553bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800553eb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800553eb`

## string_xrefs

- `0x1800553a2`: `SOFTWARE\Microsoft\Multimedia\TV\Persist Tune Xml\Type Map`

## pseudocode

```c
HRESULT __fastcall GetTuneXmlCLSIDFromTypeName(OLECHAR *psz, LPCLSID pclsid)
{
  HRESULT result; // eax
  OLECHAR *v5; // rbx
  OLECHAR *v6; // rdi
  __int64 v7; // rax
  BSTR v8; // [rsp+38h] [rbp+10h] BYREF
  char v9; // [rsp+40h] [rbp+18h] BYREF

  if ( !pclsid )
    return -2147467261;
  if ( qword_18021D138
    || (result = LoadTuneXmlLookupMap(
                   &qword_18021D130,
                   L"SOFTWARE\\Microsoft\\Multimedia\\TV\\Persist Tune Xml\\Type Map"),
        result >= 0) )
  {
    v8 = SysAllocString(psz);
    v5 = v8;
    v6 = *(OLECHAR **)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComBSTR,less_bstr_insensitive,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComBSTR>>,0>>::find(
                        &qword_18021D130,
                        &v9,
                        &v8);
    v8 = v6;
    SysFreeString(v5);
    if ( v6 == *(OLECHAR **)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
                              &qword_18021D130,
                              &v9) )
    {
      result = -2147023728;
      *pclsid = GUID_00000000_0000_0000_0000_000000000000;
    }
    else
    {
      v7 = std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,ATL::CComVariant>>>>::operator*(&v8);
      return CLSIDFromString(*(LPCOLESTR *)(v7 + 8), pclsid);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180055374  mov     [rsp+arg_0], rbx
0x180055379  mov     [rsp+arg_18], rsi
0x18005537e  push    rdi
0x18005537f  sub     rsp, 20h
0x180055383  mov     rsi, rdx
0x180055386  mov     rbx, rcx
0x180055389  test    rdx, rdx
0x18005538c  jnz     short loc_180055398
0x18005538e  mov     eax, 80004003h
0x180055393  jmp     loc_180055430
0x180055398  cmp     cs:qword_18021D138, 0
0x1800553a0  jnz     short loc_1800553B9
0x1800553a2  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Multimedia\\TV\\Pe"...
0x1800553a9  lea     rcx, qword_18021D130
0x1800553b0  call    ?LoadTuneXmlLookupMap@@YAJPEAV?$map@VCComBSTR@ATL@@V12@Uless_bstr_insensitive@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V12@@std@@@std@@@std@@PEBG@Z; LoadTuneXmlLookupMap(std::map<ATL::CComBSTR,ATL::CComBSTR,less_bstr_insensitive,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComBSTR>>> *,ushort const *)
0x1800553b5  test    eax, eax
0x1800553b7  js      short loc_180055430
0x1800553b9  mov     rcx, rbx; psz
0x1800553bc  call    cs:__imp_SysAllocString
0x1800553c2  lea     r8, [rsp+28h+arg_8]
0x1800553c7  mov     [rsp+28h+arg_8], rax
0x1800553cc  lea     rdx, [rsp+28h+arg_10]
0x1800553d1  mov     rbx, rax
0x1800553d4  lea     rcx, qword_18021D130
0x1800553db  call    ?find@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@V12@Uless_bstr_insensitive@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V12@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@V12@@std@@@std@@@std@@@2@AEBVCComBSTR@ATL@@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComBSTR,less_bstr_insensitive,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComBSTR>>,0>>::find(ATL::CComBSTR const &)
0x1800553e0  mov     rcx, rbx; bstrString
0x1800553e3  mov     rdi, [rax]
0x1800553e6  mov     [rsp+28h+arg_8], rdi
0x1800553eb  call    cs:__imp_SysFreeString
0x1800553f1  lea     rdx, [rsp+28h+arg_10]
0x1800553f6  lea     rcx, qword_18021D130
0x1800553fd  call    ?end@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@KU?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ulong,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ulong>>,0>>::end(void)
0x180055402  cmp     rdi, [rax]
0x180055405  jnz     short loc_180055419
0x180055407  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18005540e  mov     eax, 80070490h
0x180055413  movdqu  xmmword ptr [rsi], xmm0
0x180055417  jmp     short loc_180055430
0x180055419  lea     rcx, [rsp+28h+arg_8]
0x18005541e  call    ??D?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKVCComVariant@ATL@@@std@@@std@@@std@@@std@@QEBAAEAU?$pair@$$CBKVCComVariant@ATL@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ATL::CComVariant>>>>::operator*(void)
0x180055423  mov     rdx, rsi; pclsid
0x180055426  mov     rcx, [rax+8]; lpsz
0x18005542a  call    cs:__imp_CLSIDFromString
0x180055430  mov     rbx, [rsp+28h+arg_0]
0x180055435  mov     rsi, [rsp+28h+arg_18]
0x18005543a  add     rsp, 20h
0x18005543e  pop     rdi
0x18005543f  retn
```
