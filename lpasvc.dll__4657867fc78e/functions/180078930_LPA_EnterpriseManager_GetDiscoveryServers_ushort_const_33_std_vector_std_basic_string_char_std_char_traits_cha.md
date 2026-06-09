# LPA::EnterpriseManager::GetDiscoveryServers(ushort const (*)[33],std::vector<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::allocator<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> &)

- ea: `0x180078930`
- end: `0x180078dca`
- name: `?GetDiscoveryServers@EnterpriseManager@LPA@@UEAAXPEAY0CB@$$CBGAEAV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@@Z`
- size: `1178`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000df90`
- `0x180071320`
- `0x180071344`
- `0x180071610`
- `0x180071650`
- `0x180074898`
- `0x180074970`
- `0x1800754a0`
- `0x180076070`
- `0x18007618c`
- `0x1800766c4`
- `0x180076a90`
- `0x180078930`
- `0x180079b14`
- `0x18007ac3c`
- `0x180081010`
- `0x180081104`
- `0x180081154`
- `0x1800d972c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180078cb1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180078cb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180078bdb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180078bdb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180078c4a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180078c4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall LPA::EnterpriseManager::GetDiscoveryServers(__int64 a1, __int64 a2, _QWORD *a3)
{
  __m128i si128; // xmm6
  __int64 *v7; // rbx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 **v10; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 k; // rsi
  __int64 m; // r14
  HKEY *phkResult; // rbx
  const WCHAR *v16; // rax
  DWORD n; // ebx
  WCHAR *v18; // rax
  __int64 v19; // rax
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp-9Ch] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-98h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+74h] [rbp-94h] BYREF
  DWORD cbMaxValueLen; // [rsp+78h] [rbp-90h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+7Ch] [rbp-8Ch] BYREF
  DWORD cValues; // [rsp+80h] [rbp-88h] BYREF
  DWORD cbMaxClassLen; // [rsp+84h] [rbp-84h] BYREF
  DWORD cchClass; // [rsp+88h] [rbp-80h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+90h] [rbp-78h] BYREF
  HKEY hKey[2]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v32[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v33[2]; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v34[3]; // [rsp+C8h] [rbp-40h]
  __int128 v35; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v36; // [rsp+F0h] [rbp-18h]
  __int64 v37; // [rsp+F8h] [rbp-10h]
  __int128 v38; // [rsp+100h] [rbp-8h] BYREF
  __int64 v39; // [rsp+110h] [rbp+8h]
  __int64 v40; // [rsp+118h] [rbp+10h]
  _OWORD v41[2]; // [rsp+120h] [rbp+18h] BYREF
  _OWORD v42[2]; // [rsp+140h] [rbp+38h] BYREF
  _OWORD v43[2]; // [rsp+160h] [rbp+58h] BYREF
  WCHAR Class[264]; // [rsp+188h] [rbp+80h] BYREF

  v43[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v43[1] = si128;
  LOWORD(v43[0]) = 0;
  v42[0] = 0;
  v42[1] = si128;
  LOWORD(v42[0]) = 0;
  v35 = 0;
  v36 = 0;
  v37 = 15;
  LOBYTE(v35) = 0;
  if ( *a3 != a3[1] )
  {
    std::_Destroy_range<std::allocator<std::string>>(*a3);
    a3[1] = *a3;
  }
  std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>>::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>>(v32);
  if ( (int)LPA::EnterpriseManager::LoadDownloadServersFromRegistry(a1 - 8, a2, (__int64)v32) >= 0 )
  {
    v7 = *(__int64 **)v32[0];
    while ( !*((_BYTE *)v7 + 25) )
    {
      v8 = v7[8];
      if ( (unsigned int)(*(_DWORD *)(v8 + 128) - 3) > 1
        && *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>>,0>>::find(
                        a1 + 168,
                        &ftLastWriteTime,
                        v8) != *(_QWORD *)(a1 + 168) )
      {
        if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring const &,>(
                                                 a1 + 168,
                                                 v33,
                                                 v7[8])
                                  + 64LL)
                      + 196LL) )
        {
          if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring const &,>(
                                                    a1 + 168,
                                                    hKey,
                                                    v7[8])
                                     + 64LL)
                         + 197LL) )
          {
            v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7[8]);
            if ( (int)LPA::Util::ConvertUtf16ToUtf8(v9, &v35) >= 0 )
            {
              if ( a3[1] == a3[2] )
              {
                std::vector<std::string>::_Emplace_reallocate<std::string const &>(a3, a3[1], &v35);
              }
              else
              {
                std::string::string(a3[1], &v35);
                a3[1] += 32LL;
              }
            }
          }
        }
      }
      v10 = (__int64 **)v7[2];
      if ( *((_BYTE *)v10 + 25) )
      {
        for ( i = (__int64 *)v7[1]; !*((_BYTE *)i + 25) && v7 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v7 = i;
        v7 = i;
      }
      else
      {
        v7 = (__int64 *)v7[2];
        for ( j = *v10; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v7 = j;
      }
    }
  }
  v34[0] = L"OS";
  v34[1] = L"OEM";
  v34[2] = L"Enterprise";
  v33[0] = a2;
  v33[1] = L"Default";
  for ( k = 0; k != 3; ++k )
  {
    for ( m = 0; m != 2; ++m )
    {
      v41[0] = 0;
      v41[1] = si128;
      LOWORD(v41[0]) = 0;
      LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDiscoveryServerKey(a1 - 8, v34[k], v33[m], v41);
      hKey[0] = 0;
      cchClass = 260;
      cSubKeys = 0;
      cbMaxSubKeyLen = 0;
      cbMaxClassLen = 0;
      cValues = 0;
      cbMaxValueNameLen = 0;
      cbMaxValueLen = 0;
      cbSecurityDescriptor = 0;
      ftLastWriteTime = 0;
      v38 = 0;
      v39 = 0;
      v40 = 7;
      LOWORD(v38) = 0;
      cchName = 0;
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
      v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v16, 0, 0x20019u, phkResult)
        && !RegQueryInfoKeyW(
              hKey[0],
              Class,
              &cchClass,
              0,
              &cSubKeys,
              &cbMaxSubKeyLen,
              &cbMaxClassLen,
              &cValues,
              &cbMaxValueNameLen,
              &cbMaxValueLen,
              &cbSecurityDescriptor,
              &ftLastWriteTime) )
      {
        for ( n = 0; n < cSubKeys; ++n )
        {
          std::wstring::resize(&v38, cbMaxSubKeyLen + 1, 0);
          cchName = cbMaxSubKeyLen + 1;
          v18 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v38);
          if ( !RegEnumKeyExW(hKey[0], n, v18, &cchName, 0, 0, 0, &ftLastWriteTime) )
          {
            std::wstring::resize(&v38, cchName, 0);
            v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v38);
            if ( (int)LPA::Util::ConvertUtf16ToUtf8(v19, &v35) >= 0 )
            {
              if ( a3[1] == a3[2] )
              {
                std::vector<std::string>::_Emplace_reallocate<std::string const &>(a3, a3[1], &v35);
              }
              else
              {
                std::string::string(a3[1], &v35);
                a3[1] += 32LL;
              }
            }
          }
          v39 = 0;
          *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v38) = 0;
          v36 = 0;
          *(_BYTE *)std::_String_val<std::_Simple_types<char>>::_Myptr(&v35) = 0;
        }
      }
      std::wstring::_Tidy_deallocate(&v38);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
      std::wstring::_Tidy_deallocate(v41);
    }
  }
  std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>>>,0>>(v32);
  std::string::_Tidy_deallocate(&v35);
  std::wstring::_Tidy_deallocate(v42);
  return std::wstring::_Tidy_deallocate(v43);
}

```

## disassembly

```asm
0x180078930  mov     rax, rsp
0x180078933  mov     [rax+20h], rbx
0x180078937  push    rbp
0x180078938  push    rsi
0x180078939  push    rdi
0x18007893a  push    r12
0x18007893c  push    r13
0x18007893e  push    r14
0x180078940  push    r15
0x180078942  lea     rbp, [rax-2E8h]
0x180078949  sub     rsp, 3B0h
0x180078950  movaps  xmmword ptr [rax-48h], xmm6
0x180078954  mov     rax, cs:__security_cookie
0x18007895b  xor     rax, rsp
0x18007895e  mov     [rbp+2E0h+var_50], rax
0x180078965  mov     rdi, r8
0x180078968  mov     r14, rdx
0x18007896b  mov     r15, rcx
0x18007896e  xorps   xmm0, xmm0
0x180078971  movups  [rbp+2E0h+var_288], xmm0
0x180078975  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18007897d  movdqu  [rbp+2E0h+var_278], xmm6
0x180078982  xor     r13d, r13d
0x180078985  mov     word ptr [rbp+2E0h+var_288], r13w
0x18007898a  movups  [rbp+2E0h+var_2A8], xmm0
0x18007898e  movdqu  [rbp+2E0h+var_298], xmm6
0x180078993  mov     word ptr [rbp+2E0h+var_2A8], r13w
0x180078998  movups  [rbp+2E0h+var_308], xmm0
0x18007899c  mov     [rbp+2E0h+var_2F8], r13
0x1800789a0  mov     [rbp+2E0h+var_2F0], 0Fh
0x1800789a8  mov     byte ptr [rbp+2E0h+var_308], r13b
0x1800789ac  mov     rdx, [r8+8]
0x1800789b0  cmp     [r8], rdx
0x1800789b3  jz      short loc_1800789C4
0x1800789b5  mov     rcx, [r8]
0x1800789b8  call    ??$_Destroy_range@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@YAXPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::string>>(std::string *,std::string * const,std::allocator<std::string> &)
0x1800789bd  mov     rax, [rdi]
0x1800789c0  mov     [rdi+8], rax
0x1800789c4  lea     rcx, [rbp+2E0h+var_340]
0x1800789c8  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VConfiguredDownloadServer@EnterpriseManager@LPA@@U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VConfiguredDownloadServer@EnterpriseManager@LPA@@U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>>::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>>(void)
0x1800789cd  nop
0x1800789ce  lea     r8, [rbp+2E0h+var_340]
0x1800789d2  mov     rdx, r14; int
0x1800789d5  lea     rcx, [r15-8]; int
0x1800789d9  call    ?LoadDownloadServersFromRegistry@EnterpriseManager@LPA@@AEAAJPEAY0CB@$$CBGAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VConfiguredDownloadServer@EnterpriseManager@LPA@@U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VConfiguredDownloadServer@EnterpriseManager@LPA@@U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@@Z; LPA::EnterpriseManager::LoadDownloadServersFromRegistry(ushort const (*)[33],std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>> &)
0x1800789de  test    eax, eax
0x1800789e0  js      loc_180078B01
0x1800789e6  mov     rbx, [rbp+2E0h+var_340]
0x1800789ea  mov     rbx, [rbx]
0x1800789ed  cmp     [rbx+19h], r13b
0x1800789f1  jnz     loc_180078B01
0x1800789f7  mov     r8, [rbx+40h]
0x1800789fb  mov     eax, [r8+80h]
0x180078a02  sub     eax, 3
0x180078a05  cmp     eax, 1
0x180078a08  jbe     loc_180078AB2
0x180078a0e  lea     rsi, [r15+0A8h]
0x180078a15  lea     rdx, [rbp+2E0h+ftLastWriteTime]
0x180078a19  mov     rcx, rsi
0x180078a1c  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>>,0>>::find(std::wstring const &)
0x180078a21  mov     rcx, [rsi]
0x180078a24  cmp     [rax], rcx
0x180078a27  jz      loc_180078AB2
0x180078a2d  mov     r8, [rbx+40h]
0x180078a31  lea     rdx, [rbp+2E0h+var_330]
0x180078a35  mov     rcx, rsi
0x180078a38  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180078a3d  mov     rdx, [rax]
0x180078a40  mov     rax, [rdx+40h]
0x180078a44  cmp     [rax+0C4h], r13b
0x180078a4b  jz      short loc_180078AB2
0x180078a4d  mov     r8, [rbx+40h]
0x180078a51  lea     rdx, [rbp+2E0h+hKey]
0x180078a55  mov     rcx, rsi
0x180078a58  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180078a5d  mov     rcx, [rax]
0x180078a60  mov     rax, [rcx+40h]
0x180078a64  cmp     [rax+0C5h], r13b
0x180078a6b  jnz     short loc_180078AB2
0x180078a6d  mov     rcx, [rbx+40h]
0x180078a71  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180078a76  lea     rdx, [rbp+2E0h+var_308]
0x180078a7a  mov     rcx, rax
0x180078a7d  call    ?ConvertUtf16ToUtf8@Util@LPA@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@4@@Z; LPA::Util::ConvertUtf16ToUtf8(ushort const *,std::string &,std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>> *)
0x180078a82  test    eax, eax
0x180078a84  js      short loc_180078AB2
0x180078a86  mov     rax, [rdi+8]
0x180078a8a  cmp     rax, [rdi+10h]
0x180078a8e  jz      short loc_180078AA3
0x180078a90  lea     rdx, [rbp+2E0h+var_308]
0x180078a94  mov     rcx, rax
0x180078a97  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180078a9c  add     qword ptr [rdi+8], 20h ; ' '
0x180078aa1  jmp     short loc_180078AB2
0x180078aa3  lea     r8, [rbp+2E0h+var_308]
0x180078aa7  mov     rdx, rax
0x180078aaa  mov     rcx, rdi
0x180078aad  call    ??$_Emplace_reallocate@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@QEAV21@AEBV21@@Z; std::vector<std::string>::_Emplace_reallocate<std::string const &>(std::string * const,std::string const &)
0x180078ab2  mov     rcx, [rbx+10h]
0x180078ab6  cmp     [rcx+19h], r13b
0x180078aba  jz      short loc_180078ADD
0x180078abc  mov     rax, [rbx+8]
0x180078ac0  jmp     short loc_180078ACF
0x180078ac2  cmp     rbx, [rax+10h]
0x180078ac6  jnz     short loc_180078AD5
0x180078ac8  mov     rbx, rax
0x180078acb  mov     rax, [rax+8]
0x180078acf  cmp     [rax+19h], r13b
0x180078ad3  jz      short loc_180078AC2
0x180078ad5  mov     rbx, rax
0x180078ad8  jmp     loc_1800789ED
0x180078add  mov     rbx, rcx
0x180078ae0  mov     rcx, [rcx]
0x180078ae3  cmp     [rcx+19h], r13b
0x180078ae7  jnz     loc_1800789ED
0x180078aed  mov     rbx, rcx
0x180078af0  mov     rax, [rcx]
0x180078af3  mov     rcx, rax
0x180078af6  cmp     [rax+19h], r13b
0x180078afa  jz      short loc_180078AED
0x180078afc  jmp     loc_1800789ED
0x180078b01  lea     rax, aOs; "OS"
0x180078b08  mov     [rbp+2E0h+var_320], rax
0x180078b0c  lea     rax, aOem; "OEM"
0x180078b13  mov     [rbp+2E0h+var_318], rax
0x180078b17  lea     rax, aEnterprise; "Enterprise"
0x180078b1e  mov     [rbp+2E0h+var_310], rax
0x180078b22  mov     [rbp+2E0h+var_330], r14
0x180078b26  lea     rax, aDefault; "Default"
0x180078b2d  mov     [rbp+2E0h+var_328], rax
0x180078b31  mov     rsi, r13
0x180078b34  mov     r14, r13
0x180078b37  xorps   xmm0, xmm0
0x180078b3a  movups  [rbp+2E0h+var_2C8], xmm0
0x180078b3e  movdqu  [rbp+2E0h+var_2B8], xmm6
0x180078b43  mov     word ptr [rbp+2E0h+var_2C8], r13w
0x180078b48  lea     r9, [rbp+2E0h+var_2C8]
0x180078b4c  mov     r8, [rbp+r14*8+2E0h+var_330]
0x180078b51  mov     rdx, [rbp+rsi*8+2E0h+var_320]
0x180078b56  lea     rcx, [r15-8]
0x180078b5a  call    ?GetEnterpriseSettingsEuiccsDiscoveryServerKey@EnterpriseManager@LPA@@AEAAXPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDiscoveryServerKey(ushort const *,ushort const *,std::wstring &)
0x180078b5f  mov     [rbp+2E0h+hKey], r13
0x180078b63  mov     [rbp+2E0h+cchClass], 104h
0x180078b6a  mov     [rsp+3E0h+cSubKeys], r13d
0x180078b6f  mov     [rsp+3E0h+cbMaxSubKeyLen], r13d
0x180078b74  mov     [rsp+3E0h+cbMaxClassLen], r13d
0x180078b79  mov     [rsp+3E0h+cValues], r13d
0x180078b7e  mov     [rsp+3E0h+cbMaxValueNameLen], r13d
0x180078b83  mov     [rsp+3E0h+cbMaxValueLen], r13d
0x180078b88  mov     [rsp+3E0h+cbSecurityDescriptor], r13d
0x180078b8d  mov     qword ptr [rbp+2E0h+ftLastWriteTime.dwLowDateTime], r13
0x180078b91  xorps   xmm0, xmm0
0x180078b94  movups  [rbp+2E0h+var_2E8], xmm0
0x180078b98  mov     [rbp+2E0h+var_2D8], r13
0x180078b9c  mov     [rbp+2E0h+var_2D0], 7
0x180078ba4  mov     word ptr [rbp+2E0h+var_2E8], r13w
0x180078ba9  mov     [rsp+3E0h+cchName], r13d
0x180078bae  lea     rcx, [rbp+2E0h+hKey]
0x180078bb2  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180078bb7  mov     rbx, rax
0x180078bba  lea     rcx, [rbp+2E0h+var_2C8]
0x180078bbe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180078bc3  mov     rdx, rax; lpSubKey
0x180078bc6  mov     [rsp+3E0h+phkResult], rbx; phkResult
0x180078bcb  mov     r9d, 20019h; samDesired
0x180078bd1  xor     r8d, r8d; ulOptions
0x180078bd4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180078bdb  call    cs:__imp_RegOpenKeyExW
0x180078be1  test    eax, eax
0x180078be3  jnz     loc_180078D3D
0x180078be9  lea     rax, [rbp+2E0h+ftLastWriteTime]
0x180078bed  mov     [rsp+3E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180078bf2  lea     rax, [rsp+3E0h+cbSecurityDescriptor]
0x180078bf7  mov     [rsp+3E0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x180078bfc  lea     rax, [rsp+3E0h+cbMaxValueLen]
0x180078c01  mov     [rsp+3E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180078c06  lea     rax, [rsp+3E0h+cbMaxValueNameLen]
0x180078c0b  mov     [rsp+3E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180078c10  lea     rax, [rsp+3E0h+cValues]
0x180078c15  mov     [rsp+3E0h+lpcValues], rax; lpcValues
0x180078c1a  lea     rax, [rsp+3E0h+cbMaxClassLen]
0x180078c1f  mov     [rsp+3E0h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x180078c24  lea     rax, [rsp+3E0h+cbMaxSubKeyLen]
0x180078c29  mov     [rsp+3E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180078c2e  lea     rax, [rsp+3E0h+cSubKeys]
0x180078c33  mov     [rsp+3E0h+phkResult], rax; lpcSubKeys
0x180078c38  xor     r9d, r9d; lpReserved
0x180078c3b  lea     r8, [rbp+2E0h+cchClass]; lpcchClass
0x180078c3f  lea     rdx, [rbp+2E0h+Class]; lpClass
0x180078c46  mov     rcx, [rbp+2E0h+hKey]; hKey
0x180078c4a  call    cs:__imp_RegQueryInfoKeyW
0x180078c50  test    eax, eax
0x180078c52  jnz     loc_180078D3D
0x180078c58  mov     ebx, r13d
0x180078c5b  cmp     [rsp+3E0h+cSubKeys], r13d
0x180078c60  jbe     loc_180078D3D
0x180078c66  xor     r8d, r8d
0x180078c69  mov     edx, [rsp+3E0h+cbMaxSubKeyLen]
0x180078c6d  inc     edx
0x180078c6f  lea     rcx, [rbp+2E0h+var_2E8]
0x180078c73  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180078c78  mov     eax, [rsp+3E0h+cbMaxSubKeyLen]
0x180078c7c  inc     eax
0x180078c7e  mov     [rsp+3E0h+cchName], eax
0x180078c82  lea     rcx, [rbp+2E0h+var_2E8]
0x180078c86  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180078c8b  mov     r8, rax; lpName
0x180078c8e  lea     rax, [rbp+2E0h+ftLastWriteTime]
0x180078c92  mov     [rsp+3E0h+lpcValues], rax; lpftLastWriteTime
0x180078c97  mov     [rsp+3E0h+lpcbMaxClassLen], r13; lpcchClass
0x180078c9c  mov     [rsp+3E0h+lpcbMaxSubKeyLen], r13; lpClass
0x180078ca1  mov     [rsp+3E0h+phkResult], r13; lpReserved
0x180078ca6  lea     r9, [rsp+3E0h+cchName]; lpcchName
0x180078cab  mov     edx, ebx; dwIndex
0x180078cad  mov     rcx, [rbp+2E0h+hKey]; hKey
0x180078cb1  call    cs:__imp_RegEnumKeyExW
0x180078cb7  test    eax, eax
0x180078cb9  jnz     short loc_180078D10
0x180078cbb  xor     r8d, r8d
0x180078cbe  mov     edx, [rsp+3E0h+cchName]
0x180078cc2  lea     rcx, [rbp+2E0h+var_2E8]
0x180078cc6  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180078ccb  lea     rcx, [rbp+2E0h+var_2E8]
0x180078ccf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180078cd4  mov     rcx, rax
0x180078cd7  lea     rdx, [rbp+2E0h+var_308]
0x180078cdb  call    ?ConvertUtf16ToUtf8@Util@LPA@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@4@@Z; LPA::Util::ConvertUtf16ToUtf8(ushort const *,std::string &,std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>> *)
0x180078ce0  test    eax, eax
0x180078ce2  js      short loc_180078D10
0x180078ce4  mov     rax, [rdi+8]
0x180078ce8  cmp     rax, [rdi+10h]
0x180078cec  jz      short loc_180078D01
0x180078cee  lea     rdx, [rbp+2E0h+var_308]
0x180078cf2  mov     rcx, rax
0x180078cf5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180078cfa  add     qword ptr [rdi+8], 20h ; ' '
0x180078cff  jmp     short loc_180078D10
0x180078d01  lea     r8, [rbp+2E0h+var_308]
0x180078d05  mov     rdx, rax
0x180078d08  mov     rcx, rdi
0x180078d0b  call    ??$_Emplace_reallocate@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@QEAV21@AEBV21@@Z; std::vector<std::string>::_Emplace_reallocate<std::string const &>(std::string * const,std::string const &)
0x180078d10  mov     [rbp+2E0h+var_2D8], r13
0x180078d14  lea     rcx, [rbp+2E0h+var_2E8]
0x180078d18  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180078d1d  mov     [rax], r13w
0x180078d21  mov     [rbp+2E0h+var_2F8], r13
0x180078d25  lea     rcx, [rbp+2E0h+var_308]
0x180078d29  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180078d2e  mov     [rax], r13b
0x180078d31  inc     ebx
0x180078d33  cmp     ebx, [rsp+3E0h+cSubKeys]
0x180078d37  jb      loc_180078C66
0x180078d3d  lea     rcx, [rbp+2E0h+var_2E8]
0x180078d41  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078d46  nop
0x180078d47  lea     rcx, [rbp+2E0h+hKey]
0x180078d4b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180078d50  nop
0x180078d51  lea     rcx, [rbp+2E0h+var_2C8]
0x180078d55  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078d5a  inc     r14
0x180078d5d  cmp     r14, 2
0x180078d61  jnz     loc_180078B37
0x180078d67  inc     rsi
0x180078d6a  cmp     rsi, 3
0x180078d6e  jnz     loc_180078B34
0x180078d74  lea     rcx, [rbp+2E0h+var_340]
0x180078d78  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VConfiguredDownloadServer@EnterpriseManager@LPA@@U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VConfiguredDownloadServer@EnterpriseManager@LPA@@U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>>>,0>>(void)
0x180078d7d  nop
0x180078d7e  lea     rcx, [rbp+2E0h+var_308]
0x180078d82  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180078d87  nop
0x180078d88  lea     rcx, [rbp+2E0h+var_2A8]
0x180078d8c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078d91  nop
0x180078d92  lea     rcx, [rbp+2E0h+var_288]
0x180078d96  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078d9b  mov     rcx, [rbp+2E0h+var_50]
0x180078da2  xor     rcx, rsp; StackCookie
0x180078da5  call    __security_check_cookie
0x180078daa  lea     r11, [rsp+3E0h+var_30]
0x180078db2  mov     rbx, [r11+58h]
0x180078db6  movaps  xmm6, xmmword ptr [r11-10h]
0x180078dbb  mov     rsp, r11
0x180078dbe  pop     r15
0x180078dc0  pop     r14
0x180078dc2  pop     r13
0x180078dc4  pop     r12
0x180078dc6  pop     rdi
0x180078dc7  pop     rsi
0x180078dc8  pop     rbp
0x180078dc9  retn
```
