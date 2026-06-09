# EndpointDlp::Policy::AuthorizedGroups::_anonymous_namespace_::IsMatch

- ea: `0x1800b14d8`
- end: `0x1800b16a8`
- name: `EndpointDlp::Policy::AuthorizedGroups::_anonymous_namespace_::IsMatch`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800aea7c`

## callees

- `0x180069470`
- `0x18009ce28`
- `0x1800a2384`
- `0x1800b14d8`

## import_xrefs

- `SHLWAPI!PathMatchSpecW` at `0x1800b15e6`
- `SHLWAPI!PathMatchSpecW` at `0x1800b161b`
- `SHLWAPI!PathMatchSpecW` at `0x1800b1650`
- `SHLWAPI!PathMatchSpecW` at `0x1800b1689`
- `SHLWAPI!PathMatchSpecW` at `0x1800b15e6`
- `SHLWAPI!PathMatchSpecW` at `0x1800b161b`
- `SHLWAPI!PathMatchSpecW` at `0x1800b1650`
- `SHLWAPI!PathMatchSpecW` at `0x1800b1689`

## pseudocode

```c
bool __fastcall EndpointDlp::Policy::AuthorizedGroups::_anonymous_namespace_::IsMatch(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // r8
  __int64 v7; // rax
  const WCHAR *v8; // rdx
  const WCHAR *v9; // rcx
  const WCHAR *v10; // rdx
  const WCHAR *v11; // rcx
  const WCHAR *v12; // rdx
  const WCHAR *v13; // rcx
  const WCHAR *v15; // rdx
  const WCHAR *v16; // rcx
  _BYTE v17[16]; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v18[16]; // [rsp+30h] [rbp-10h] BYREF

  if ( *(_BYTE *)(a2 + 4) && *(_DWORD *)a1 != *(_DWORD *)a2 )
    return 0;
  if ( *(_BYTE *)(a2 + 80) )
  {
    std::wstring::operator std::wstring_view(a1 + 8, v17);
    v4 = std::optional<std::wstring>::value(a2 + 48);
    std::wstring::operator std::wstring_view(v4, v18);
    if ( !(unsigned __int8)EndpointDlp::Common::IsEqual(v18, v17) )
      return 0;
  }
  if ( *(_BYTE *)(a2 + 120) )
  {
    std::wstring::operator std::wstring_view(a1 + 40, v18);
    v5 = std::optional<std::wstring>::value(a2 + 88);
    std::wstring::operator std::wstring_view(v5, v17);
    if ( !(unsigned __int8)EndpointDlp::Common::IsEqual(v17, v18) )
      return 0;
  }
  if ( *(_BYTE *)(a2 + 160) )
  {
    std::wstring::operator std::wstring_view(a1 + 72, v18);
    v7 = std::optional<std::wstring>::value(v6);
    std::wstring::operator std::wstring_view(v7, v17);
    if ( !(unsigned __int8)EndpointDlp::Common::IsEqual(v17, v18) )
      return 0;
  }
  if ( *(_BYTE *)(a2 + 200) )
  {
    v8 = (const WCHAR *)(a2 + 168);
    if ( *(_QWORD *)(a2 + 192) > 7u )
      v8 = *(const WCHAR **)v8;
    v9 = (const WCHAR *)(a1 + 104);
    if ( *(_QWORD *)(a1 + 128) > 7u )
      v9 = *(const WCHAR **)v9;
    if ( !PathMatchSpecW(v9, v8) )
      return 0;
  }
  if ( *(_BYTE *)(a2 + 240) )
  {
    v10 = (const WCHAR *)(a2 + 208);
    if ( *(_QWORD *)(a2 + 232) > 7u )
      v10 = *(const WCHAR **)v10;
    v11 = (const WCHAR *)(a1 + 136);
    if ( *(_QWORD *)(a1 + 160) > 7u )
      v11 = *(const WCHAR **)v11;
    if ( !PathMatchSpecW(v11, v10) )
      return 0;
  }
  if ( *(_BYTE *)(a2 + 280) )
  {
    v12 = (const WCHAR *)(a2 + 248);
    if ( *(_QWORD *)(a2 + 272) > 7u )
      v12 = *(const WCHAR **)v12;
    v13 = (const WCHAR *)(a1 + 168);
    if ( *(_QWORD *)(a1 + 192) > 7u )
      v13 = *(const WCHAR **)v13;
    if ( !PathMatchSpecW(v13, v12) )
      return 0;
  }
  if ( !*(_BYTE *)(a2 + 320) )
    return 1;
  v15 = (const WCHAR *)(a2 + 288);
  if ( *(_QWORD *)(a2 + 312) > 7u )
    v15 = *(const WCHAR **)v15;
  v16 = (const WCHAR *)(a1 + 200);
  if ( *(_QWORD *)(a1 + 224) > 7u )
    v16 = *(const WCHAR **)v16;
  return PathMatchSpecW(v16, v15);
}

```

## disassembly

```asm
0x1800b14d8  mov     [rsp-8+arg_0], rbx
0x1800b14dd  mov     [rsp-8+arg_8], rdi
0x1800b14e2  push    rbp
0x1800b14e3  mov     rbp, rsp
0x1800b14e6  sub     rsp, 40h
0x1800b14ea  cmp     byte ptr [rdx+4], 0
0x1800b14ee  mov     rbx, rdx
0x1800b14f1  mov     rdi, rcx
0x1800b14f4  jz      short loc_1800B1500
0x1800b14f6  mov     eax, [rdx]
0x1800b14f8  cmp     [rcx], eax
0x1800b14fa  jnz     loc_1800B165A
0x1800b1500  cmp     byte ptr [rdx+50h], 0
0x1800b1504  jz      short loc_1800B153D
0x1800b1506  add     rcx, 8
0x1800b150a  lea     rdx, [rbp+var_20]
0x1800b150e  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800b1513  lea     rcx, [rbx+30h]
0x1800b1517  call    ?value@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEGBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::optional<std::wstring>::value(void)
0x1800b151c  lea     rdx, [rbp+var_10]
0x1800b1520  mov     rcx, rax
0x1800b1523  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800b1528  lea     rdx, [rbp+var_20]
0x1800b152c  lea     rcx, [rbp+var_10]
0x1800b1530  call    ?IsEqual@Common@EndpointDlp@@YA_NAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_N@Z; EndpointDlp::Common::IsEqual(std::wstring_view const &,std::wstring_view const &,bool)
0x1800b1535  test    al, al
0x1800b1537  jz      loc_1800B165A
0x1800b153d  cmp     byte ptr [rbx+78h], 0
0x1800b1541  jz      short loc_1800B157A
0x1800b1543  lea     rcx, [rdi+28h]
0x1800b1547  lea     rdx, [rbp+var_10]
0x1800b154b  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800b1550  lea     rcx, [rbx+58h]
0x1800b1554  call    ?value@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEGBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::optional<std::wstring>::value(void)
0x1800b1559  lea     rdx, [rbp+var_20]
0x1800b155d  mov     rcx, rax
0x1800b1560  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800b1565  lea     rdx, [rbp+var_10]
0x1800b1569  lea     rcx, [rbp+var_20]
0x1800b156d  call    ?IsEqual@Common@EndpointDlp@@YA_NAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_N@Z; EndpointDlp::Common::IsEqual(std::wstring_view const &,std::wstring_view const &,bool)
0x1800b1572  test    al, al
0x1800b1574  jz      loc_1800B165A
0x1800b157a  lea     r8, [rbx+80h]
0x1800b1581  cmp     byte ptr [r8+20h], 0
0x1800b1586  jz      short loc_1800B15BE
0x1800b1588  lea     rcx, [rdi+48h]
0x1800b158c  lea     rdx, [rbp+var_10]
0x1800b1590  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800b1595  mov     rcx, r8
0x1800b1598  call    ?value@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEGBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::optional<std::wstring>::value(void)
0x1800b159d  lea     rdx, [rbp+var_20]
0x1800b15a1  mov     rcx, rax
0x1800b15a4  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800b15a9  lea     rdx, [rbp+var_10]
0x1800b15ad  lea     rcx, [rbp+var_20]
0x1800b15b1  call    ?IsEqual@Common@EndpointDlp@@YA_NAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_N@Z; EndpointDlp::Common::IsEqual(std::wstring_view const &,std::wstring_view const &,bool)
0x1800b15b6  test    al, al
0x1800b15b8  jz      loc_1800B165A
0x1800b15be  cmp     byte ptr [rbx+0C8h], 0
0x1800b15c5  jz      short loc_1800B15F0
0x1800b15c7  lea     rdx, [rbx+0A8h]
0x1800b15ce  cmp     qword ptr [rdx+18h], 7
0x1800b15d3  jbe     short loc_1800B15D8
0x1800b15d5  mov     rdx, [rdx]; pszSpec
0x1800b15d8  lea     rcx, [rdi+68h]
0x1800b15dc  cmp     qword ptr [rcx+18h], 7
0x1800b15e1  jbe     short loc_1800B15E6
0x1800b15e3  mov     rcx, [rcx]; pszFile
0x1800b15e6  call    cs:__imp_PathMatchSpecW
0x1800b15ec  test    eax, eax
0x1800b15ee  jz      short loc_1800B165A
0x1800b15f0  cmp     byte ptr [rbx+0F0h], 0
0x1800b15f7  jz      short loc_1800B1625
0x1800b15f9  lea     rdx, [rbx+0D0h]
0x1800b1600  cmp     qword ptr [rdx+18h], 7
0x1800b1605  jbe     short loc_1800B160A
0x1800b1607  mov     rdx, [rdx]; pszSpec
0x1800b160a  lea     rcx, [rdi+88h]
0x1800b1611  cmp     qword ptr [rcx+18h], 7
0x1800b1616  jbe     short loc_1800B161B
0x1800b1618  mov     rcx, [rcx]; pszFile
0x1800b161b  call    cs:__imp_PathMatchSpecW
0x1800b1621  test    eax, eax
0x1800b1623  jz      short loc_1800B165A
0x1800b1625  cmp     byte ptr [rbx+118h], 0
0x1800b162c  jz      short loc_1800B165E
0x1800b162e  lea     rdx, [rbx+0F8h]
0x1800b1635  cmp     qword ptr [rdx+18h], 7
0x1800b163a  jbe     short loc_1800B163F
0x1800b163c  mov     rdx, [rdx]; pszSpec
0x1800b163f  lea     rcx, [rdi+0A8h]
0x1800b1646  cmp     qword ptr [rcx+18h], 7
0x1800b164b  jbe     short loc_1800B1650
0x1800b164d  mov     rcx, [rcx]; pszFile
0x1800b1650  call    cs:__imp_PathMatchSpecW
0x1800b1656  test    eax, eax
0x1800b1658  jnz     short loc_1800B165E
0x1800b165a  xor     al, al
0x1800b165c  jmp     short loc_1800B1698
0x1800b165e  cmp     byte ptr [rbx+140h], 0
0x1800b1665  jz      short loc_1800B1696
0x1800b1667  lea     rdx, [rbx+120h]
0x1800b166e  cmp     qword ptr [rdx+18h], 7
0x1800b1673  jbe     short loc_1800B1678
0x1800b1675  mov     rdx, [rdx]; pszSpec
0x1800b1678  lea     rcx, [rdi+0C8h]
0x1800b167f  cmp     qword ptr [rcx+18h], 7
0x1800b1684  jbe     short loc_1800B1689
0x1800b1686  mov     rcx, [rcx]; pszFile
0x1800b1689  call    cs:__imp_PathMatchSpecW
0x1800b168f  test    eax, eax
0x1800b1691  setnz   al
0x1800b1694  jmp     short loc_1800B1698
0x1800b1696  mov     al, 1
0x1800b1698  mov     rbx, [rsp+40h+arg_0]
0x1800b169d  mov     rdi, [rsp+40h+arg_8]
0x1800b16a2  add     rsp, 40h
0x1800b16a6  pop     rbp
0x1800b16a7  retn
```
