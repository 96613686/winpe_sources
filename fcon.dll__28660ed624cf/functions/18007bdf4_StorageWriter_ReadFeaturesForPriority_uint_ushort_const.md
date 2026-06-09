# StorageWriter::ReadFeaturesForPriority(uint,ushort const *)

- ea: `0x18007bdf4`
- end: `0x18007c073`
- name: `?ReadFeaturesForPriority@StorageWriter@@SA?AV?$vector@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@@std@@IPEBG@Z`
- size: `639`
- prototype: ``
- caller_count: `7`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x18006416c`
- `0x180064558`
- `0x18006ae28`
- `0x18007607c`
- `0x18007611c`
- `0x1800761a0`
- `0x180078450`

## callees

- `0x180003220`
- `0x1800109ac`
- `0x180015af4`
- `0x180016698`
- `0x180019768`
- `0x180019890`
- `0x180034cb8`
- `0x180035b60`
- `0x18004dcd0`
- `0x180077c18`
- `0x18007afd8`
- `0x18007b668`
- `0x18007bdf4`
- `0x18007d310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007bec4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007bec4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007bf23`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007bf45`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007bf23`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007bf45`

## string_xrefs

- `0x18007c01f`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18007c034`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18007c049`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18007c05e`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall StorageWriter::ReadFeaturesForPriority(__int64 a1, unsigned int a2, __int64 a3)
{
  int v6; // ecx
  char v7; // al
  unsigned int v8; // eax
  DWORD i; // esi
  unsigned int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rdx
  unsigned __int32 v13; // ebx
  __int64 v14; // rdx
  int lpcSubKeys; // [rsp+20h] [rbp-E0h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-E0h]
  unsigned int lpcSubKeysb; // [rsp+20h] [rbp-E0h]
  unsigned int lpcSubKeysc; // [rsp+20h] [rbp-E0h]
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  int v23; // [rsp+70h] [rbp-90h]
  __int64 v24; // [rsp+78h] [rbp-88h]
  _BYTE v25[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v26[144]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Name[12]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v24 = a1;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v23 = 1;
  hKey = 0;
  v6 = StorageWriter::OpenPriorityKeyForRead(a2, &hKey);
  if ( (int)(v6 + 0x80000000) < 0 || (v7 = 1, v6 == -2147024894) )
    v7 = 0;
  if ( v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x418,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
      (const char *)(unsigned int)v6,
      lpcSubKeys);
  if ( v6 >= 0 )
  {
    cSubKeys = 0;
    v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( v8 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x41E,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
        (const char *)v8,
        lpcSubKeysa);
    for ( i = 0; i < cSubKeys; ++i )
    {
      cchName = 11;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterErrorCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterErrorCheck>::GetImpl'::`2'::impl) )
      {
        v10 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
        if ( v10 == 259 )
          break;
        if ( v10 )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            (void *)0x42C,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
            (const char *)v10,
            lpcSubKeysb);
      }
      else
      {
        v11 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
        if ( v11 )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            (void *)0x430,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
            (const char *)v11,
            lpcSubKeysc);
      }
      std::wstring::wstring(v25);
      v13 = _byteswap_ulong(__ROL4__(std::stoul(v25, v12, 10) ^ 0x833EA8FF, 255) ^ 0x8FB23D4F) ^ 0x74161A4E;
      std::wstring::_Tidy_deallocate(v25, v14);
      StorageWriter::ReadFeatureForPriority(v26, a2, v13, a3);
      if ( *(_QWORD *)(a1 + 8) == *(_QWORD *)(a1 + 16) )
      {
        std::vector<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>::_Emplace_reallocate<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR const &>(
          a1,
          *(_QWORD *)(a1 + 8),
          v26);
      }
      else
      {
        _RTL_FEATURE_CONFIGURATION_DESCRIPTOR::_RTL_FEATURE_CONFIGURATION_DESCRIPTOR(
          *(_RTL_FEATURE_CONFIGURATION_DESCRIPTOR **)(a1 + 8),
          (const struct _RTL_FEATURE_CONFIGURATION_DESCRIPTOR *)v26);
        *(_QWORD *)(a1 + 8) += 136LL;
      }
      _RTL_FEATURE_CONFIGURATION_DESCRIPTOR::~_RTL_FEATURE_CONFIGURATION_DESCRIPTOR((_RTL_FEATURE_CONFIGURATION_DESCRIPTOR *)v26);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return a1;
}

```

## disassembly

```asm
0x18007bdf4  push    rbp
0x18007bdf6  push    rbx
0x18007bdf7  push    rsi
0x18007bdf8  push    rdi
0x18007bdf9  push    r12
0x18007bdfb  push    r14
0x18007bdfd  push    r15
0x18007bdff  lea     rbp, [rsp-50h]
0x18007be04  sub     rsp, 150h
0x18007be0b  mov     rax, cs:__security_cookie
0x18007be12  xor     rax, rsp
0x18007be15  mov     [rbp+80h+var_38], rax
0x18007be19  mov     r15, r8
0x18007be1c  mov     r14d, edx
0x18007be1f  mov     rdi, rcx
0x18007be22  mov     [rsp+180h+var_108], rcx
0x18007be27  xor     r12d, r12d
0x18007be2a  mov     [rsp+180h+var_110], r12d
0x18007be2f  mov     [rcx], r12
0x18007be32  mov     [rcx+8], r12
0x18007be36  mov     [rcx+10h], r12
0x18007be3a  mov     [rsp+180h+var_110], 1
0x18007be42  mov     [rsp+180h+hKey], r12
0x18007be47  lea     rdx, [rsp+180h+hKey]
0x18007be4c  mov     ecx, r14d
0x18007be4f  call    ?OpenPriorityKeyForRead@StorageWriter@@CAJIAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; StorageWriter::OpenPriorityKeyForRead(uint,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *)
0x18007be54  mov     ecx, eax
0x18007be56  mov     edx, 80000000h
0x18007be5b  add     eax, edx
0x18007be5d  test    edx, eax
0x18007be5f  jnz     short loc_18007BE6B
0x18007be61  cmp     ecx, 80070002h
0x18007be67  mov     al, 1
0x18007be69  jnz     short loc_18007BE6E
0x18007be6b  mov     al, r12b
0x18007be6e  mov     r10, [rbp+88h]
0x18007be75  test    al, al
0x18007be77  jnz     loc_18007C05B
0x18007be7d  test    ecx, ecx
0x18007be7f  js      loc_18007BFF1
0x18007be85  mov     [rsp+180h+cSubKeys], r12d
0x18007be8a  mov     [rsp+180h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18007be8f  mov     [rsp+180h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18007be94  mov     [rsp+180h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18007be99  mov     [rsp+180h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18007be9e  mov     [rsp+180h+lpcValues], r12; lpcValues
0x18007bea3  mov     [rsp+180h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18007bea8  mov     [rsp+180h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18007bead  lea     rax, [rsp+180h+cSubKeys]
0x18007beb2  mov     [rsp+180h+lpcSubKeys], rax; unsigned int
0x18007beb7  xor     r9d, r9d; lpReserved
0x18007beba  xor     r8d, r8d; lpcchClass
0x18007bebd  xor     edx, edx; lpClass
0x18007bebf  mov     rcx, [rsp+180h+hKey]; hKey
0x18007bec4  call    cs:__imp_RegQueryInfoKeyW
0x18007beca  mov     rcx, [rbp+88h]; this
0x18007bed1  test    eax, eax
0x18007bed3  jnz     loc_18007C01C
0x18007bed9  mov     esi, r12d
0x18007bedc  cmp     [rsp+180h+cSubKeys], r12d
0x18007bee1  jbe     loc_18007BFF1
0x18007bee7  mov     [rsp+180h+cchName], 0Bh
0x18007beef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterErrorCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterErrorCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterErrorCheck> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterErrorCheck>::GetImpl(void)'::`2'::impl
0x18007bef6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterErrorCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterErrorCheck>::__private_IsEnabled(void)
0x18007befb  mov     [rsp+180h+lpcValues], r12; lpftLastWriteTime
0x18007bf00  lea     r9, [rsp+180h+cchName]; lpcchName
0x18007bf05  lea     r8, [rbp+80h+Name]; lpName
0x18007bf09  mov     edx, esi; dwIndex
0x18007bf0b  mov     rcx, [rsp+180h+hKey]; hKey
0x18007bf10  mov     [rsp+180h+lpcbMaxClassLen], r12; lpcchClass
0x18007bf15  mov     [rsp+180h+lpcbMaxSubKeyLen], r12; lpClass
0x18007bf1a  mov     [rsp+180h+lpcSubKeys], r12; unsigned int
0x18007bf1f  test    al, al
0x18007bf21  jz      short loc_18007BF45
0x18007bf23  call    cs:__imp_RegEnumKeyExW
0x18007bf29  cmp     eax, 103h
0x18007bf2e  jz      loc_18007BFF1
0x18007bf34  mov     rcx, [rbp+88h]; this
0x18007bf3b  test    eax, eax
0x18007bf3d  jnz     loc_18007C031
0x18007bf43  jmp     short loc_18007BF5A
0x18007bf45  call    cs:__imp_RegEnumKeyExW
0x18007bf4b  mov     rcx, [rbp+88h]; this
0x18007bf52  test    eax, eax
0x18007bf54  jnz     loc_18007C046
0x18007bf5a  lea     rdx, [rbp+80h+Name]
0x18007bf5e  lea     rcx, [rbp+80h+var_100]
0x18007bf62  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007bf67  nop
0x18007bf68  mov     r8d, 0Ah
0x18007bf6e  lea     rcx, [rbp+80h+var_100]
0x18007bf72  call    ?stoul@std@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoul(std::wstring const &,unsigned __int64 *,int)
0x18007bf77  mov     ebx, eax
0x18007bf79  xor     ebx, 833EA8FFh
0x18007bf7f  rol     ebx, 0FFh
0x18007bf82  xor     ebx, 8FB23D4Fh
0x18007bf88  bswap   ebx
0x18007bf8a  xor     ebx, 74161A4Eh
0x18007bf90  lea     rcx, [rbp+80h+var_100]
0x18007bf94  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007bf99  mov     r9, r15
0x18007bf9c  mov     r8d, ebx
0x18007bf9f  mov     edx, r14d
0x18007bfa2  lea     rcx, [rbp+80h+var_E0]
0x18007bfa6  call    ?ReadFeatureForPriority@StorageWriter@@SA?AU_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@IIPEBG@Z; StorageWriter::ReadFeatureForPriority(uint,uint,ushort const *)
0x18007bfab  nop
0x18007bfac  mov     rax, [rdi+8]
0x18007bfb0  cmp     rax, [rdi+10h]
0x18007bfb4  jz      short loc_18007BFCC
0x18007bfb6  lea     rdx, [rbp+80h+var_E0]; struct _RTL_FEATURE_CONFIGURATION_DESCRIPTOR *
0x18007bfba  mov     rcx, rax; this
0x18007bfbd  call    ??0_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@QEAA@AEBU0@@Z; _RTL_FEATURE_CONFIGURATION_DESCRIPTOR::_RTL_FEATURE_CONFIGURATION_DESCRIPTOR(_RTL_FEATURE_CONFIGURATION_DESCRIPTOR const &)
0x18007bfc2  add     qword ptr [rdi+8], 88h
0x18007bfca  jmp     short loc_18007BFDC
0x18007bfcc  lea     r8, [rbp+80h+var_E0]
0x18007bfd0  mov     rdx, rax
0x18007bfd3  mov     rcx, rdi
0x18007bfd6  call    ??$_Emplace_reallocate@AEBU_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@?$vector@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@@std@@@std@@AEAAPEAU_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@QEAU2@AEBU2@@Z; std::vector<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR>::_Emplace_reallocate<_RTL_FEATURE_CONFIGURATION_DESCRIPTOR const &>(_RTL_FEATURE_CONFIGURATION_DESCRIPTOR * const,_RTL_FEATURE_CONFIGURATION_DESCRIPTOR const &)
0x18007bfdb  nop
0x18007bfdc  lea     rcx, [rbp+80h+var_E0]; this
0x18007bfe0  call    ??1_RTL_FEATURE_CONFIGURATION_DESCRIPTOR@@QEAA@XZ; _RTL_FEATURE_CONFIGURATION_DESCRIPTOR::~_RTL_FEATURE_CONFIGURATION_DESCRIPTOR(void)
0x18007bfe5  inc     esi
0x18007bfe7  cmp     esi, [rsp+180h+cSubKeys]
0x18007bfeb  jb      loc_18007BEE7
0x18007bff1  lea     rcx, [rsp+180h+hKey]
0x18007bff6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007bffb  mov     rax, rdi
0x18007bffe  mov     rcx, [rbp+80h+var_38]
0x18007c002  xor     rcx, rsp; StackCookie
0x18007c005  call    __security_check_cookie
0x18007c00a  add     rsp, 150h
0x18007c011  pop     r15
0x18007c013  pop     r14
0x18007c015  pop     r12
0x18007c017  pop     rdi
0x18007c018  pop     rsi
0x18007c019  pop     rbx
0x18007c01a  pop     rbp
0x18007c01b  retn
0x18007c01c  mov     r9d, eax; char *
0x18007c01f  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007c026  mov     edx, 41Eh; void *
0x18007c02b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18007c031  mov     r9d, eax; char *
0x18007c034  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007c03b  mov     edx, 42Ch; void *
0x18007c040  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18007c046  mov     r9d, eax; char *
0x18007c049  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007c050  mov     edx, 430h; void *
0x18007c055  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18007c05b  mov     r9d, ecx; char *
0x18007c05e  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007c065  mov     edx, 418h; void *
0x18007c06a  mov     rcx, r10; this
0x18007c06d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
