# ToString(WlanAvailableNetworks const &,ulong)

- ea: `0x18003d25c`
- end: `0x18003d497`
- name: `?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUWlanAvailableNetworks@@K@Z`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003c0b8`

## callees

- `0x18000f388`
- `0x180010124`
- `0x180011614`
- `0x18003d25c`
- `0x18003d4a0`
- `0x18003da38`
- `0x18003db10`
- `0x18003db70`
- `0x18003e114`

## string_xrefs

- `0x18003d421`: `\n   >>>>>> WLAN Available Network %ws [%u] <<<<<< \n      ProfileName: %ws\n      NetworkConnectable: %ws\n      SecurityEnabled: %ws\n      MorePhyTypes: %ws\n      dot11BssType: %ws\n      dot11DefaultAuthAlgorithm: %ws\n      dot11DefaultCipherAlgorithm: %ws\n      dot11PhyTypes: %ws\n      dot11Ssid: %ws\n      Flags: %u\n      NumberOfBssids: %u\n      NotConnectableReason: %u (0x%x)\n      SignalQuality: %u\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ToString(__int64 a1, _DWORD *a2, unsigned int a3)
{
  int v4; // eax
  const wchar_t *v5; // rax
  bool v6; // zf
  int v7; // r14d
  int v8; // r15d
  int v9; // r12d
  int v10; // r13d
  __int64 v11; // rbp
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  const wchar_t *v16; // r9
  const wchar_t *v17; // rdx
  const wchar_t *v18; // rcx
  int v20; // [rsp+68h] [rbp-120h]
  int v21; // [rsp+70h] [rbp-118h]
  int v22; // [rsp+78h] [rbp-110h]
  int v23; // [rsp+80h] [rbp-108h]
  int v24; // [rsp+88h] [rbp-100h]
  _BYTE v25[32]; // [rsp+98h] [rbp-F0h] BYREF
  _BYTE v26[32]; // [rsp+B8h] [rbp-D0h] BYREF
  _BYTE v27[32]; // [rsp+D8h] [rbp-B0h] BYREF
  _BYTE v28[32]; // [rsp+F8h] [rbp-90h] BYREF
  _BYTE v29[112]; // [rsp+118h] [rbp-70h] BYREF
  const wchar_t *v33; // [rsp+1A8h] [rbp+20h]

  v4 = a2[157];
  if ( (v4 & 3) != 0 )
  {
    v5 = L"<Adhoc and ManualHidden>";
  }
  else if ( (v4 & 1) != 0 )
  {
    v5 = L"<Adhoc>";
  }
  else
  {
    v6 = (v4 & 2) == 0;
    v5 = L"<ManualHidden>";
    if ( v6 )
      v5 = &LocaleName;
  }
  v33 = v5;
  v7 = a2[151];
  v8 = a2[140];
  v9 = a2[138];
  v10 = a2[155];
  ToString(v29, a2 + 128);
  v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToString(v28, a2 + 142, (unsigned int)a2[141]);
  v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToString(v27, a2 + 154);
  v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToString(v26, a2 + 153);
  v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToString(v25, a2 + 137);
  v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v16 = L"true";
  v17 = L"true";
  if ( !a2[150] )
    v17 = L"false";
  v18 = L"true";
  if ( !a2[152] )
    v18 = L"false";
  if ( !a2[139] )
    v16 = L"false";
  v24 = v7;
  v23 = v8;
  v22 = v8;
  v21 = v9;
  v20 = v10;
  wil::str_printf<std::wstring>(
    a1,
    (__int64)L"\n"
              "   >>>>>> WLAN Available Network %ws [%u] <<<<<< \n"
              "      ProfileName: %ws\n"
              "      NetworkConnectable: %ws\n"
              "      SecurityEnabled: %ws\n"
              "      MorePhyTypes: %ws\n"
              "      dot11BssType: %ws\n"
              "      dot11DefaultAuthAlgorithm: %ws\n"
              "      dot11DefaultCipherAlgorithm: %ws\n"
              "      dot11PhyTypes: %ws\n"
              "      dot11Ssid: %ws\n"
              "      Flags: %u\n"
              "      NumberOfBssids: %u\n"
              "      NotConnectableReason: %u (0x%x)\n"
              "      SignalQuality: %u\n",
    v33,
    a3,
    a2,
    v16,
    v18,
    v17,
    v15,
    v14,
    v13,
    v12,
    v11,
    v20,
    v21,
    v22,
    v23,
    v24);
  std::wstring::_Tidy_deallocate((__int64)v25);
  std::wstring::_Tidy_deallocate((__int64)v26);
  std::wstring::_Tidy_deallocate((__int64)v27);
  std::wstring::_Tidy_deallocate((__int64)v28);
  std::wstring::_Tidy_deallocate((__int64)v29);
  return a1;
}

```

## disassembly

```asm
0x18003d25c  mov     [rsp+arg_10], r8d
0x18003d261  mov     [rsp+arg_8], rdx
0x18003d266  mov     [rsp+arg_0], rcx
0x18003d26b  push    rbx
0x18003d26c  push    rbp
0x18003d26d  push    rsi
0x18003d26e  push    rdi
0x18003d26f  push    r12
0x18003d271  push    r13
0x18003d273  push    r14
0x18003d275  push    r15
0x18003d277  sub     rsp, 148h
0x18003d27e  mov     rbx, rdx
0x18003d281  mov     eax, [rdx+274h]
0x18003d287  test    al, 3
0x18003d289  jz      short loc_18003D294
0x18003d28b  lea     rax, aAdhocAndManual; "<Adhoc and ManualHidden>"
0x18003d292  jmp     short loc_18003D2B5
0x18003d294  test    al, 1
0x18003d296  jz      short loc_18003D2A1
0x18003d298  lea     rax, aAdhoc; "<Adhoc>"
0x18003d29f  jmp     short loc_18003D2B5
0x18003d2a1  test    al, 2
0x18003d2a3  lea     rax, aManualhidden; "<ManualHidden>"
0x18003d2aa  lea     rcx, LocaleName
0x18003d2b1  cmovz   rax, rcx
0x18003d2b5  mov     [rsp+188h+arg_18], rax
0x18003d2bd  mov     r14d, [rdx+25Ch]
0x18003d2c4  mov     r15d, [rdx+230h]
0x18003d2cb  mov     r12d, [rdx+228h]
0x18003d2d2  mov     r13d, [rdx+26Ch]
0x18003d2d9  add     rdx, 200h
0x18003d2e0  lea     rcx, [rsp+188h+var_70]
0x18003d2e8  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_DOT11_SSID@@@Z; ToString(_DOT11_SSID const &)
0x18003d2ed  nop
0x18003d2ee  mov     rcx, rax
0x18003d2f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003d2f6  mov     rbp, rax
0x18003d2f9  lea     rdx, [rbx+238h]
0x18003d300  mov     r8d, [rbx+234h]
0x18003d307  lea     rcx, [rsp+188h+var_90]
0x18003d30f  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBW4_DOT11_PHY_TYPE@@K@Z; ToString(_DOT11_PHY_TYPE const *,ulong)
0x18003d314  nop
0x18003d315  mov     rcx, rax
0x18003d318  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003d31d  mov     rsi, rax
0x18003d320  lea     rdx, [rbx+268h]
0x18003d327  lea     rcx, [rsp+188h+var_B0]
0x18003d32f  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4_DOT11_CIPHER_ALGORITHM@@@Z; ToString(_DOT11_CIPHER_ALGORITHM const &)
0x18003d334  nop
0x18003d335  mov     rcx, rax
0x18003d338  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003d33d  mov     rdi, rax
0x18003d340  lea     rdx, [rbx+264h]
0x18003d347  lea     rcx, [rsp+188h+var_D0]
0x18003d34f  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4_DOT11_AUTH_ALGORITHM@@@Z; ToString(_DOT11_AUTH_ALGORITHM const &)
0x18003d354  nop
0x18003d355  mov     rcx, rax
0x18003d358  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003d35d  mov     rbx, rax
0x18003d360  mov     rdx, [rsp+188h+arg_8]
0x18003d368  add     rdx, 224h
0x18003d36f  lea     rcx, [rsp+188h+var_F0]
0x18003d377  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4_DOT11_BSS_TYPE@@@Z; ToString(_DOT11_BSS_TYPE const &)
0x18003d37c  nop
0x18003d37d  mov     rcx, rax
0x18003d380  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003d385  lea     r10, aFalse_0; "false"
0x18003d38c  lea     r9, aTrue_0; "true"
0x18003d393  mov     rdx, r9
0x18003d396  mov     r8, [rsp+188h+arg_8]
0x18003d39e  xor     r11d, r11d
0x18003d3a1  cmp     [r8+258h], r11d
0x18003d3a8  cmovz   rdx, r10
0x18003d3ac  mov     rcx, r9
0x18003d3af  cmp     [r8+260h], r11d
0x18003d3b6  cmovz   rcx, r10
0x18003d3ba  cmp     [r8+22Ch], r11d
0x18003d3c1  cmovz   r9, r10
0x18003d3c5  mov     [rsp+188h+var_100], r14d
0x18003d3cd  mov     [rsp+188h+var_108], r15d
0x18003d3d5  mov     [rsp+188h+var_110], r15d
0x18003d3da  mov     [rsp+188h+var_118], r12d
0x18003d3df  mov     [rsp+188h+var_120], r13d
0x18003d3e4  mov     [rsp+188h+var_128], rbp
0x18003d3e9  mov     [rsp+188h+var_130], rsi
0x18003d3ee  mov     [rsp+188h+var_138], rdi
0x18003d3f3  mov     [rsp+188h+var_140], rbx
0x18003d3f8  mov     [rsp+188h+var_148], rax
0x18003d3fd  mov     [rsp+188h+var_150], rdx
0x18003d402  mov     [rsp+188h+var_158], rcx
0x18003d407  mov     [rsp+188h+var_160], r9
0x18003d40c  mov     [rsp+188h+var_168], r8
0x18003d411  mov     r9d, [rsp+188h+arg_10]
0x18003d419  mov     r8, [rsp+188h+arg_18]
0x18003d421  lea     rdx, aWlanAvailableN; "\n   >>>>>> WLAN Available Network %ws "...
0x18003d428  mov     rcx, [rsp+188h+arg_0]
0x18003d430  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003d435  nop
0x18003d436  lea     rcx, [rsp+188h+var_F0]
0x18003d43e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003d443  nop
0x18003d444  lea     rcx, [rsp+188h+var_D0]
0x18003d44c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003d451  nop
0x18003d452  lea     rcx, [rsp+188h+var_B0]
0x18003d45a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003d45f  nop
0x18003d460  lea     rcx, [rsp+188h+var_90]
0x18003d468  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003d46d  nop
0x18003d46e  lea     rcx, [rsp+188h+var_70]
0x18003d476  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003d47b  mov     rax, [rsp+188h+arg_0]
0x18003d483  add     rsp, 148h
0x18003d48a  pop     r15
0x18003d48c  pop     r14
0x18003d48e  pop     r13
0x18003d490  pop     r12
0x18003d492  pop     rdi
0x18003d493  pop     rsi
0x18003d494  pop     rbp
0x18003d495  pop     rbx
0x18003d496  retn
```
