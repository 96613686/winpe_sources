# SetMultiStringRegValWithVector(ushort const *,ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x18005e458`
- end: `0x18005e64b`
- name: `?SetMultiStringRegValWithVector@@YAJPEBG0AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `499`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041b34`

## callees

- `0x18003bf28`
- `0x18003dd9c`
- `0x180040024`
- `0x18004317c`
- `0x180045b80`
- `0x1800471d0`
- `0x18004755c`
- `0x18004af14`
- `0x18005b6d4`
- `0x18005e458`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005e606`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005e606`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005e5b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005e5b0`

## string_xrefs

- `0x18005e540`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005e5bf`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005e5fb`: `UserAccountSids`
- `0x18005e5a2`: `Software\Microsoft\IdentityStore\DeferredCacheCleanup`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetMultiStringRegValWithVector(__int64 a1, HKEY a2, __int64 *a3)
{
  unsigned int v4; // edi
  __int64 i; // rcx
  char *v6; // r14
  unsigned __int64 v7; // rcx
  BYTE *v8; // rax
  size_t v9; // rbx
  unsigned __int16 *v10; // r14
  unsigned int v11; // r15d
  __int64 v12; // r11
  __int64 v13; // rsi
  const unsigned __int16 *v14; // r8
  int v15; // eax
  __int64 v16; // r11
  unsigned int v17; // ebx
  unsigned int v19; // eax
  __int64 v20; // rdx
  int phkResult; // [rsp+20h] [rbp-38h]
  unsigned int phkResulta; // [rsp+20h] [rbp-38h]
  BYTE *lpData; // [rsp+30h] [rbp-28h] BYREF
  void *v24; // [rsp+38h] [rbp-20h]
  __int64 v25; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  HKEY hKey; // [rsp+98h] [rbp+40h] BYREF

  hKey = a2;
  v4 = 1;
  for ( i = *a3; i != a3[1]; i += 32 )
    v4 += *(_DWORD *)(i + 16) + 1;
  std::vector<std::wstring>::vector<std::wstring>(&lpData);
  v6 = (char *)v24;
  v7 = ((_BYTE *)v24 - lpData) >> 1;
  if ( v4 < v7 )
  {
    v8 = &lpData[2 * v4];
LABEL_10:
    v24 = v8;
    goto LABEL_11;
  }
  if ( v4 > v7 )
  {
    if ( v4 <= (unsigned __int64)((v25 - (__int64)lpData) >> 1) )
    {
      v9 = 2 * (v4 - v7);
      memset_0(v24, 0, v9);
      v8 = (BYTE *)&v6[v9];
      goto LABEL_10;
    }
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&lpData, v4);
  }
LABEL_11:
  v10 = (unsigned __int16 *)lpData;
  v11 = v4;
  v12 = *a3;
  v13 = a3[1];
  while ( v12 != v13 )
  {
    if ( *(_QWORD *)(v12 + 24) <= 7u )
      v14 = (const unsigned __int16 *)v12;
    else
      v14 = *(const unsigned __int16 **)v12;
    v15 = StringCchCopyW(v10, v11, v14);
    v17 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x386,
        (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
        (const char *)(unsigned int)v15,
        phkResult);
LABEL_19:
      if ( lpData )
        std::_Deallocate<16>(lpData, 2 * ((v25 - (__int64)lpData) >> 1));
      return v17;
    }
    v10 += *(_QWORD *)(v16 + 16) + 1;
    v11 += -1 - *(_DWORD *)(v16 + 16);
    v12 = v16 + 32;
  }
  *(_WORD *)&lpData[2 * v4 - 2] = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v19 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\IdentityStore\\DeferredCacheCleanup",
          0,
          0x20006u,
          &hKey);
  if ( v19 )
  {
    v20 = 910;
LABEL_24:
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v20,
            (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
            (const char *)v19,
            phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_19;
  }
  v19 = RegSetValueExW(hKey, L"UserAccountSids", 0, 7u, lpData, 2 * v4);
  if ( v19 )
  {
    v20 = 917;
    goto LABEL_24;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  if ( lpData )
    std::_Deallocate<16>(lpData, 2 * ((v25 - (__int64)lpData) >> 1));
  return 0;
}

```

## disassembly

```asm
0x18005e458  mov     [rsp-30h+hKey], rdx
0x18005e45d  push    rbp
0x18005e45e  push    rbx
0x18005e45f  push    rsi
0x18005e460  push    rdi
0x18005e461  push    r14
0x18005e463  push    r15
0x18005e465  mov     rbp, rsp
0x18005e468  sub     rsp, 58h
0x18005e46c  mov     rsi, r8
0x18005e46f  mov     edi, 1
0x18005e474  mov     rcx, [r8]
0x18005e477  jmp     short loc_18005E482
0x18005e479  inc     edi
0x18005e47b  add     edi, [rcx+10h]
0x18005e47e  add     rcx, 20h ; ' '
0x18005e482  cmp     rcx, [r8+8]
0x18005e486  jnz     short loc_18005E479
0x18005e488  lea     rcx, [rbp+lpData]
0x18005e48c  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x18005e491  nop
0x18005e492  mov     rdx, [rbp+lpData]
0x18005e496  mov     r14, [rbp+var_20]
0x18005e49a  mov     rcx, r14
0x18005e49d  sub     rcx, rdx
0x18005e4a0  sar     rcx, 1
0x18005e4a3  mov     ebx, edi
0x18005e4a5  cmp     rbx, rcx
0x18005e4a8  jnb     short loc_18005E4B0
0x18005e4aa  lea     rax, [rdx+rbx*2]
0x18005e4ae  jmp     short loc_18005E4E6
0x18005e4b0  jbe     short loc_18005E4EA
0x18005e4b2  mov     rax, [rbp+var_18]
0x18005e4b6  sub     rax, rdx
0x18005e4b9  sar     rax, 1
0x18005e4bc  cmp     rbx, rax
0x18005e4bf  jbe     short loc_18005E4CF
0x18005e4c1  mov     rdx, rbx
0x18005e4c4  lea     rcx, [rbp+lpData]
0x18005e4c8  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005e4cd  jmp     short loc_18005E4EA
0x18005e4cf  sub     rbx, rcx
0x18005e4d2  add     rbx, rbx
0x18005e4d5  mov     r8, rbx; Size
0x18005e4d8  xor     edx, edx; Val
0x18005e4da  mov     rcx, r14; void *
0x18005e4dd  call    memset_0
0x18005e4e2  lea     rax, [rbx+r14]
0x18005e4e6  mov     [rbp+var_20], rax
0x18005e4ea  mov     r14, [rbp+lpData]
0x18005e4ee  mov     r15d, edi
0x18005e4f1  mov     r11, [rsi]
0x18005e4f4  mov     rsi, [rsi+8]
0x18005e4f8  cmp     r11, rsi
0x18005e4fb  jz      short loc_18005E574
0x18005e4fd  cmp     qword ptr [r11+18h], 7
0x18005e502  jbe     short loc_18005E509
0x18005e504  mov     r8, [r11]
0x18005e507  jmp     short loc_18005E50C
0x18005e509  mov     r8, r11; unsigned __int16 *
0x18005e50c  mov     edx, r15d; unsigned __int64
0x18005e50f  mov     rcx, r14; unsigned __int16 *
0x18005e512  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005e517  mov     ebx, eax
0x18005e519  test    eax, eax
0x18005e51b  js      short loc_18005E539
0x18005e51d  mov     rax, [r11+10h]
0x18005e521  lea     r14, [r14+rax*2]
0x18005e525  add     r14, 2
0x18005e529  or      eax, 0FFFFFFFFh
0x18005e52c  sub     eax, [r11+10h]
0x18005e530  add     r15d, eax
0x18005e533  add     r11, 20h ; ' '
0x18005e537  jmp     short loc_18005E4F8
0x18005e539  mov     rcx, [rbp+30h]; this
0x18005e53d  mov     r9d, ebx; char *
0x18005e540  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005e547  mov     edx, 386h; void *
0x18005e54c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e551  nop
0x18005e552  mov     rcx, [rbp+lpData]
0x18005e556  test    rcx, rcx
0x18005e559  jz      short loc_18005E56D
0x18005e55b  mov     rdx, [rbp+var_18]
0x18005e55f  sub     rdx, rcx
0x18005e562  sar     rdx, 1
0x18005e565  add     rdx, rdx
0x18005e568  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005e56d  mov     eax, ebx
0x18005e56f  jmp     loc_18005E63E
0x18005e574  lea     edx, [rdi-1]
0x18005e577  xor     ecx, ecx
0x18005e579  mov     rax, [rbp+lpData]
0x18005e57d  mov     [rax+rdx*2], cx
0x18005e581  mov     [rbp+hKey], rcx
0x18005e585  xor     edx, edx
0x18005e587  lea     rcx, [rbp+hKey]
0x18005e58b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005e590  lea     rax, [rbp+hKey]
0x18005e594  mov     [rsp+58h+phkResult], rax; unsigned int
0x18005e599  mov     r9d, 20006h; samDesired
0x18005e59f  xor     r8d, r8d; ulOptions
0x18005e5a2  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\IdentityStore\\Def"...
0x18005e5a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005e5b0  call    cs:__imp_RegOpenKeyExW
0x18005e5b6  test    eax, eax
0x18005e5b8  jz      short loc_18005E5E2
0x18005e5ba  mov     edx, 38Eh; void *
0x18005e5bf  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005e5c6  mov     r9d, eax; char *
0x18005e5c9  mov     rcx, [rbp+30h]; this
0x18005e5cd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005e5d2  mov     ebx, eax
0x18005e5d4  lea     rcx, [rbp+hKey]
0x18005e5d8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005e5dd  jmp     loc_18005E552
0x18005e5e2  mov     rdx, [rbp+lpData]
0x18005e5e6  lea     eax, [rdi+rdi]
0x18005e5e9  mov     [rsp+58h+cbData], eax; cbData
0x18005e5ed  mov     [rsp+58h+phkResult], rdx; lpData
0x18005e5f2  mov     r9d, 7; dwType
0x18005e5f8  xor     r8d, r8d; Reserved
0x18005e5fb  lea     rdx, aUseraccountsid; "UserAccountSids"
0x18005e602  mov     rcx, [rbp+hKey]; hKey
0x18005e606  call    cs:__imp_RegSetValueExW
0x18005e60c  test    eax, eax
0x18005e60e  jz      short loc_18005E617
0x18005e610  mov     edx, 395h
0x18005e615  jmp     short loc_18005E5BF
0x18005e617  lea     rcx, [rbp+hKey]
0x18005e61b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005e620  nop
0x18005e621  mov     rcx, [rbp+lpData]
0x18005e625  test    rcx, rcx
0x18005e628  jz      short loc_18005E63C
0x18005e62a  mov     rdx, [rbp+var_18]
0x18005e62e  sub     rdx, rcx
0x18005e631  sar     rdx, 1
0x18005e634  add     rdx, rdx
0x18005e637  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005e63c  xor     eax, eax
0x18005e63e  add     rsp, 58h
0x18005e642  pop     r15
0x18005e644  pop     r14
0x18005e646  pop     rdi
0x18005e647  pop     rsi
0x18005e648  pop     rbx
0x18005e649  pop     rbp
0x18005e64a  retn
```
