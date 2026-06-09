# LPA::EnterpriseManager::LoadStagedEsimDetailsFromRegistry(void)

- ea: `0x18007c304`
- end: `0x18007c671`
- name: `?LoadStagedEsimDetailsFromRegistry@EnterpriseManager@LPA@@AEAAXXZ`
- size: `877`
- prototype: `void __fastcall(LPA::EnterpriseManager *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task`

## callers

- `0x18007cf20`

## callees

- `0x1800018b4`
- `0x18000199c`
- `0x18000df90`
- `0x18000ebf4`
- `0x18005cd20`
- `0x180063668`
- `0x180071344`
- `0x180071650`
- `0x18007423c`
- `0x1800756dc`
- `0x180075a7c`
- `0x180076a20`
- `0x1800775b4`
- `0x180079bec`
- `0x18007c304`
- `0x18007c678`
- `0x180081154`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c5d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c5d4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007c485`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007c485`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007c37b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007c37b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007c3ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007c3ee`

## string_xrefs

- `0x18007c3a0`: `LpaServiceEnterpriseManager`
- `0x18007c399`: `LPA::EnterpriseManager::LoadStagedEsimDetailsFromRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall LPA::EnterpriseManager::LoadStagedEsimDetailsFromRegistry(
        LPA::EnterpriseManager *this,
        __int64 a2,
        __int64 a3)
{
  __int64 EnterpriseSettingsEuiccsKey; // rax
  const WCHAR *v5; // rax
  LSTATUS v6; // eax
  signed int v7; // ebx
  int v8; // r8d
  int v9; // r9d
  LSTATUS v10; // eax
  DWORD v11; // edi
  __m128i si128; // xmm6
  WCHAR *v13; // rax
  LSTATUS v14; // eax
  int v15; // r8d
  int v16; // r9d
  signed int v17; // ecx
  const unsigned __int16 *v18; // rax
  __int64 v19; // r8
  __int64 v20; // rax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v22; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD v23; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD v27; // [rsp+80h] [rbp-80h] BYREF
  __int64 v28; // [rsp+88h] [rbp-78h] BYREF
  const char *v29; // [rsp+90h] [rbp-70h] BYREF
  const char *v30; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v31[16]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v32[2]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v33[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v34[32]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v35[40]; // [rsp+110h] [rbp+10h] BYREF

  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  LOBYTE(a3) = 1;
  EnterpriseSettingsEuiccsKey = LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsKey(this, v34, a3);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(EnterpriseSettingsEuiccsKey);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  std::wstring::_Tidy_deallocate(v34);
  if ( v7 >= 0 )
  {
    v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    v7 = v10;
    if ( v10 > 0 )
      v7 = (unsigned __int16)v10 | 0x80070000;
    if ( v7 >= 0 )
    {
      v11 = 0;
      if ( cSubKeys )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        do
        {
          memset_0(v35, 0, 0x42u);
          cchName = cbMaxSubKeyLen + 1;
          v32[0] = 0;
          v32[1] = si128;
          LOWORD(v32[0]) = 0;
          std::wstring::resize(v32, cbMaxSubKeyLen + 1, 0);
          v13 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
          v14 = RegEnumKeyExW(hKey, v11, v13, &cchName, 0, 0, 0, 0);
          v17 = v14;
          if ( v14 > 0 )
            v17 = (unsigned __int16)v14 | 0x80070000;
          if ( v17 < 0
            || (v18 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32),
                v17 = StringCchCopyW(v35, 0x21u, v18),
                v17 < 0) )
          {
            if ( (unsigned int)CallbackContext > 3 )
            {
              v27 = cchName;
              v22 = v11;
              v23 = v17;
              v29 = "LPA::EnterpriseManager::LoadStagedEsimDetailsFromRegistry";
              v30 = "LpaServiceEnterpriseManager";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v17,
                (unsigned int)byte_18012B871,
                v15,
                v16,
                (__int64)&v30,
                (__int64)&v29,
                (__int64)&v23,
                (__int64)&v22,
                (__int64)&v27);
            }
          }
          else
          {
            v33[0] = 0;
            v33[1] = si128;
            LOWORD(v33[0]) = 0;
            std::make_unique<LPA::EnterpriseManager::StagedEsimDetails,,0>(&v28);
            LOBYTE(v19) = 1;
            LPA::EnterpriseManager::AssembleEuiccRegKey(this, v35, v19, v33);
            if ( (int)LPA::EnterpriseManager::LoadStagedProfileDetailsFromRegistry((__int64)this, v35, &v28) >= 0 )
            {
              std::wstring::wstring(v34, v35);
              v20 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>::_Try_emplace<std::wstring,>(
                      (char *)this + 72,
                      v31,
                      v34);
              std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>::operator=<std::default_delete<LPA::EnterpriseManager::StagedEsimDetails>,0>(
                (__int64 *)(*(_QWORD *)v20 + 64LL),
                &v28);
              std::wstring::_Tidy_deallocate(v34);
            }
            std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>::~unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>(&v28);
            std::wstring::_Tidy_deallocate(v33);
          }
          std::wstring::_Tidy_deallocate(v32);
          ++v11;
        }
        while ( v11 < cSubKeys );
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147024894 && (unsigned int)CallbackContext > 3 )
  {
    v23 = cSubKeys;
    v22 = v7;
    v30 = "LPA::EnterpriseManager::LoadStagedEsimDetailsFromRegistry";
    v29 = "LpaServiceEnterpriseManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      0x80000000,
      (unsigned int)&dword_18012B82C,
      v8,
      v9,
      (__int64)&v29,
      (__int64)&v30,
      (__int64)&v22,
      (__int64)&v23);
  }
}

```

## disassembly

```asm
0x18007c304  mov     rax, rsp
0x18007c307  mov     [rax+10h], rbx
0x18007c30b  mov     [rax+18h], rsi
0x18007c30f  push    rbp
0x18007c310  push    rdi
0x18007c311  push    r12
0x18007c313  push    r13
0x18007c315  push    r14
0x18007c317  lea     rbp, [rsp-80h]
0x18007c31c  sub     rsp, 180h
0x18007c323  movaps  xmmword ptr [rax-38h], xmm6
0x18007c327  mov     rax, cs:__security_cookie
0x18007c32e  xor     rax, rsp
0x18007c331  mov     [rbp+0A0h+var_40], rax
0x18007c335  mov     rsi, rcx
0x18007c338  xor     r14d, r14d
0x18007c33b  mov     [rsp+1A0h+hKey], r14
0x18007c340  mov     [rsp+1A0h+cSubKeys], r14d
0x18007c345  mov     [rsp+1A0h+cbMaxSubKeyLen], r14d
0x18007c34a  mov     r8b, 1
0x18007c34d  lea     rdx, [rbp+0A0h+var_B0]
0x18007c351  call    ?GetEnterpriseSettingsEuiccsKey@EnterpriseManager@LPA@@AEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsKey(bool)
0x18007c356  mov     rcx, rax
0x18007c359  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c35e  lea     rcx, [rsp+1A0h+hKey]
0x18007c363  mov     [rsp+1A0h+phkResult], rcx; phkResult
0x18007c368  mov     r9d, 20019h; samDesired
0x18007c36e  xor     r8d, r8d; ulOptions
0x18007c371  mov     rdx, rax; lpSubKey
0x18007c374  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007c37b  call    cs:__imp_RegOpenKeyExW
0x18007c381  mov     ebx, eax
0x18007c383  test    eax, eax
0x18007c385  jle     short loc_18007C390
0x18007c387  movzx   ebx, ax
0x18007c38a  or      ebx, 80070000h
0x18007c390  lea     rcx, [rbp+0A0h+var_B0]
0x18007c394  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c399  lea     r12, aLpaEnterprisem_20; "LPA::EnterpriseManager::LoadStagedEsimD"...
0x18007c3a0  lea     r13, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007c3a7  test    ebx, ebx
0x18007c3a9  js      loc_18007C5CA
0x18007c3af  mov     [rsp+1A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18007c3b4  mov     [rsp+1A0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18007c3b9  mov     [rsp+1A0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18007c3be  mov     [rsp+1A0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18007c3c3  mov     [rsp+1A0h+lpcValues], r14; lpcValues
0x18007c3c8  mov     [rsp+1A0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18007c3cd  lea     rax, [rsp+1A0h+cbMaxSubKeyLen]
0x18007c3d2  mov     [rsp+1A0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18007c3d7  lea     rax, [rsp+1A0h+cSubKeys]
0x18007c3dc  mov     [rsp+1A0h+phkResult], rax; lpcSubKeys
0x18007c3e1  xor     r9d, r9d; lpReserved
0x18007c3e4  xor     r8d, r8d; lpcchClass
0x18007c3e7  xor     edx, edx; lpClass
0x18007c3e9  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18007c3ee  call    cs:__imp_RegQueryInfoKeyW
0x18007c3f4  mov     ebx, eax
0x18007c3f6  test    eax, eax
0x18007c3f8  jle     short loc_18007C403
0x18007c3fa  movzx   ebx, ax
0x18007c3fd  or      ebx, 80070000h
0x18007c403  test    ebx, ebx
0x18007c405  js      loc_18007C5CA
0x18007c40b  mov     edi, r14d
0x18007c40e  cmp     [rsp+1A0h+cSubKeys], r14d
0x18007c413  jbe     loc_18007C5CA
0x18007c419  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18007c421  xor     edx, edx; Val
0x18007c423  lea     r8d, [rdx+42h]; Size
0x18007c427  lea     rcx, [rbp+0A0h+var_90]; void *
0x18007c42b  call    memset_0
0x18007c430  mov     ecx, [rsp+1A0h+cbMaxSubKeyLen]
0x18007c434  inc     ecx
0x18007c436  mov     [rsp+1A0h+cchName], ecx
0x18007c43a  xorps   xmm0, xmm0
0x18007c43d  movups  [rbp+0A0h+var_F0], xmm0
0x18007c441  movdqu  [rbp+0A0h+var_E0], xmm6
0x18007c446  mov     word ptr [rbp+0A0h+var_F0], r14w
0x18007c44b  xor     r8d, r8d
0x18007c44e  mov     edx, ecx
0x18007c450  lea     rcx, [rbp+0A0h+var_F0]
0x18007c454  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18007c459  lea     rcx, [rbp+0A0h+var_F0]
0x18007c45d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c462  mov     r8, rax; lpName
0x18007c465  mov     [rsp+1A0h+lpcValues], r14; lpftLastWriteTime
0x18007c46a  mov     [rsp+1A0h+lpcbMaxClassLen], r14; lpcchClass
0x18007c46f  mov     [rsp+1A0h+lpcbMaxSubKeyLen], r14; lpClass
0x18007c474  mov     [rsp+1A0h+phkResult], r14; lpReserved
0x18007c479  lea     r9, [rsp+1A0h+cchName]; lpcchName
0x18007c47e  mov     edx, edi; dwIndex
0x18007c480  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18007c485  call    cs:__imp_RegEnumKeyExW
0x18007c48b  mov     ecx, eax
0x18007c48d  test    eax, eax
0x18007c48f  jle     short loc_18007C49A
0x18007c491  movzx   ecx, ax
0x18007c494  or      ecx, 80070000h
0x18007c49a  test    ecx, ecx
0x18007c49c  js      loc_18007C557
0x18007c4a2  lea     rcx, [rbp+0A0h+var_F0]
0x18007c4a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c4ab  mov     r8, rax; unsigned __int16 *
0x18007c4ae  mov     edx, 21h ; '!'; unsigned __int64
0x18007c4b3  lea     rcx, [rbp+0A0h+var_90]; unsigned __int16 *
0x18007c4b7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007c4bc  mov     ecx, eax
0x18007c4be  test    eax, eax
0x18007c4c0  js      loc_18007C557
0x18007c4c6  xorps   xmm0, xmm0
0x18007c4c9  movups  [rbp+0A0h+var_D0], xmm0
0x18007c4cd  movdqu  [rbp+0A0h+var_C0], xmm6
0x18007c4d2  mov     word ptr [rbp+0A0h+var_D0], r14w
0x18007c4d7  lea     rcx, [rbp+0A0h+var_118]
0x18007c4db  call    ??$make_unique@UStagedEsimDetails@EnterpriseManager@LPA@@$$V$0A@@std@@YA?AV?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@0@XZ; std::make_unique<LPA::EnterpriseManager::StagedEsimDetails,,0>(void)
0x18007c4e0  nop
0x18007c4e1  lea     r9, [rbp+0A0h+var_D0]
0x18007c4e5  mov     r8b, 1
0x18007c4e8  lea     rdx, [rbp+0A0h+var_90]
0x18007c4ec  mov     rcx, rsi
0x18007c4ef  call    ?AssembleEuiccRegKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBG_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::AssembleEuiccRegKey(ushort const (&)[33],bool,std::wstring &)
0x18007c4f4  lea     r8, [rbp+0A0h+var_118]
0x18007c4f8  lea     rdx, [rbp+0A0h+var_90]
0x18007c4fc  mov     rcx, rsi
0x18007c4ff  call    ?LoadStagedProfileDetailsFromRegistry@EnterpriseManager@LPA@@AEAAJAEAY0CB@$$CBGAEBV?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@std@@@Z; LPA::EnterpriseManager::LoadStagedProfileDetailsFromRegistry(ushort const (&)[33],std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails> const &)
0x18007c504  test    eax, eax
0x18007c506  js      short loc_18007C542
0x18007c508  lea     rdx, [rbp+0A0h+var_90]
0x18007c50c  lea     rcx, [rbp+0A0h+var_B0]
0x18007c510  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007c515  nop
0x18007c516  lea     rcx, [rsi+48h]
0x18007c51a  lea     r8, [rbp+0A0h+var_B0]
0x18007c51e  lea     rdx, [rbp+0A0h+var_100]
0x18007c522  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007c527  mov     rcx, [rax]
0x18007c52a  add     rcx, 40h ; '@'
0x18007c52e  lea     rdx, [rbp+0A0h+var_118]
0x18007c532  call    ??$?4U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@$0A@@?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>::operator=<std::default_delete<LPA::EnterpriseManager::StagedEsimDetails>,0>(std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails> &&)
0x18007c537  nop
0x18007c538  lea     rcx, [rbp+0A0h+var_B0]
0x18007c53c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c541  nop
0x18007c542  lea     rcx, [rbp+0A0h+var_118]
0x18007c546  call    ??1?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>::~unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>(void)
0x18007c54b  nop
0x18007c54c  lea     rcx, [rbp+0A0h+var_D0]
0x18007c550  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c555  jmp     short loc_18007C5B5
0x18007c557  mov     eax, cs:CallbackContext
0x18007c55d  cmp     eax, 3
0x18007c560  jbe     short loc_18007C5B5
0x18007c562  mov     eax, [rsp+1A0h+cchName]
0x18007c566  mov     [rbp+0A0h+var_120], eax
0x18007c569  mov     [rsp+1A0h+var_13C], edi
0x18007c56d  mov     [rsp+1A0h+var_138], ecx
0x18007c571  mov     [rbp+0A0h+var_110], r12
0x18007c575  mov     [rbp+0A0h+var_108], r13
0x18007c579  lea     rax, [rbp+0A0h+var_120]
0x18007c57d  mov     [rsp+1A0h+lpcbMaxValueNameLen], rax
0x18007c582  lea     rax, [rsp+1A0h+var_13C]
0x18007c587  mov     [rsp+1A0h+lpcValues], rax
0x18007c58c  lea     rax, [rsp+1A0h+var_138]
0x18007c591  mov     [rsp+1A0h+lpcbMaxClassLen], rax
0x18007c596  lea     rax, [rbp+0A0h+var_110]
0x18007c59a  mov     [rsp+1A0h+lpcbMaxSubKeyLen], rax
0x18007c59f  lea     rax, [rbp+0A0h+var_108]
0x18007c5a3  mov     [rsp+1A0h+phkResult], rax
0x18007c5a8  lea     rdx, byte_18012B871
0x18007c5af  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007c5b4  nop
0x18007c5b5  lea     rcx, [rbp+0A0h+var_F0]
0x18007c5b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c5be  inc     edi
0x18007c5c0  cmp     edi, [rsp+1A0h+cSubKeys]
0x18007c5c4  jb      loc_18007C421
0x18007c5ca  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18007c5cf  test    rcx, rcx
0x18007c5d2  jz      short loc_18007C5DF
0x18007c5d4  call    cs:__imp_RegCloseKey
0x18007c5da  mov     [rsp+1A0h+hKey], r14
0x18007c5df  mov     ecx, 80000000h
0x18007c5e4  lea     eax, [rbx+rcx]
0x18007c5e7  test    ecx, eax
0x18007c5e9  jnz     short loc_18007C644
0x18007c5eb  cmp     ebx, 80070002h
0x18007c5f1  jz      short loc_18007C644
0x18007c5f3  mov     eax, cs:CallbackContext
0x18007c5f9  cmp     eax, 3
0x18007c5fc  jbe     short loc_18007C644
0x18007c5fe  mov     eax, [rsp+1A0h+cSubKeys]
0x18007c602  mov     [rsp+1A0h+var_138], eax
0x18007c606  mov     [rsp+1A0h+var_13C], ebx
0x18007c60a  mov     [rbp+0A0h+var_108], r12
0x18007c60e  mov     [rbp+0A0h+var_110], r13
0x18007c612  lea     rax, [rsp+1A0h+var_138]
0x18007c617  mov     [rsp+1A0h+lpcValues], rax
0x18007c61c  lea     rax, [rsp+1A0h+var_13C]
0x18007c621  mov     [rsp+1A0h+lpcbMaxClassLen], rax
0x18007c626  lea     rax, [rbp+0A0h+var_108]
0x18007c62a  mov     [rsp+1A0h+lpcbMaxSubKeyLen], rax
0x18007c62f  lea     rax, [rbp+0A0h+var_110]
0x18007c633  mov     [rsp+1A0h+phkResult], rax
0x18007c638  lea     rdx, dword_18012B82C
0x18007c63f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007c644  mov     rcx, [rbp+0A0h+var_40]
0x18007c648  xor     rcx, rsp; StackCookie
0x18007c64b  call    __security_check_cookie
0x18007c650  lea     r11, [rsp+1A0h+var_20]
0x18007c658  mov     rbx, [r11+38h]
0x18007c65c  mov     rsi, [r11+40h]
0x18007c660  movaps  xmm6, xmmword ptr [r11-10h]
0x18007c665  mov     rsp, r11
0x18007c668  pop     r14
0x18007c66a  pop     r13
0x18007c66c  pop     r12
0x18007c66e  pop     rdi
0x18007c66f  pop     rbp
0x18007c670  retn
```
