# LPA::EnterpriseManager::LoadEsimDetailsFromRegistry(void)

- ea: `0x18007ba00`
- end: `0x18007bde3`
- name: `?LoadEsimDetailsFromRegistry@EnterpriseManager@LPA@@AEAAXXZ`
- size: `995`
- prototype: `void __fastcall(LPA::EnterpriseManager *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

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
- `0x1800741d0`
- `0x180075554`
- `0x1800759d4`
- `0x1800769bc`
- `0x1800775b4`
- `0x180079550`
- `0x180079bec`
- `0x18007ba00`
- `0x18007bdec`
- `0x180081154`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007bd47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007bd47`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007bb7d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007bb7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007ba75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007ba75`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007bae7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007bae7`

## string_xrefs

- `0x18007ba9a`: `LpaServiceEnterpriseManager`
- `0x18007bcc0`: `LpaServiceEnterpriseManager`
- `0x18007ba93`: `LPA::EnterpriseManager::LoadEsimDetailsFromRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall LPA::EnterpriseManager::LoadEsimDetailsFromRegistry(LPA::EnterpriseManager *this)
{
  __int64 EnterpriseSettingsEuiccsKey; // rax
  const WCHAR *v3; // rax
  LSTATUS v4; // eax
  signed int v5; // edi
  int v6; // r8d
  int v7; // r9d
  LSTATUS v8; // eax
  DWORD v9; // esi
  __m128i si128; // xmm6
  WCHAR *v11; // rax
  LSTATUS v12; // eax
  int v13; // r8d
  int v14; // r9d
  signed int v15; // ecx
  const unsigned __int16 *v16; // rax
  const WCHAR *v17; // rax
  unsigned int *v18; // r9
  int DwordFromRegistry; // eax
  _DWORD *v20; // rbx
  const WCHAR *v21; // rax
  unsigned int *v22; // r9
  __int64 v23; // rax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp-9Ch] BYREF
  BYTE v26[4]; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD v28; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+74h] [rbp-8Ch] BYREF
  _DWORD *v30; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  const char *v32; // [rsp+88h] [rbp-78h] BYREF
  const char *v33; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v34[16]; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v35[2]; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD v36[2]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v37[40]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 v38[40]; // [rsp+110h] [rbp+10h] BYREF

  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  EnterpriseSettingsEuiccsKey = LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsKey(this, v37, 0);
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(EnterpriseSettingsEuiccsKey);
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  std::wstring::_Tidy_deallocate(v37);
  if ( v5 >= 0 )
  {
    v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    if ( v5 >= 0 )
    {
      v9 = 0;
      if ( cSubKeys )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        do
        {
          memset_0(v38, 0, 0x42u);
          cchName = cbMaxSubKeyLen + 1;
          v36[0] = 0;
          v36[1] = si128;
          LOWORD(v36[0]) = 0;
          std::wstring::resize(v36, cbMaxSubKeyLen + 1, 0);
          v11 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
          v12 = RegEnumKeyExW(hKey, v9, v11, &cchName, 0, 0, 0, 0);
          v15 = v12;
          if ( v12 > 0 )
            v15 = (unsigned __int16)v12 | 0x80070000;
          if ( v15 < 0
            || (v16 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36),
                v15 = StringCchCopyW(v38, 0x21u, v16),
                v15 < 0) )
          {
            if ( (unsigned int)CallbackContext > 3 )
            {
              *(_DWORD *)v26 = cchName;
              *(_DWORD *)Data = v9;
              v28 = v15;
              v32 = "LPA::EnterpriseManager::LoadEsimDetailsFromRegistry";
              v33 = "LpaServiceEnterpriseManager";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v15,
                (unsigned int)byte_18012BB6D,
                v13,
                v14,
                (__int64)&v33,
                (__int64)&v32,
                (__int64)&v28,
                (__int64)Data,
                (__int64)v26);
            }
          }
          else
          {
            *(_DWORD *)Data = 0;
            *(_DWORD *)v26 = 0;
            v35[0] = 0;
            v35[1] = si128;
            LOWORD(v35[0]) = 0;
            std::make_unique<LPA::EnterpriseManager::EsimDetails,,0>(&v30);
            LPA::EnterpriseManager::AssembleEuiccRegKey(this, v38, 0, v35);
            v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
            DwordFromRegistry = CommonUtil::GetDwordFromRegistry(v17, L"Policies", Data, v18);
            v20 = v30;
            if ( DwordFromRegistry >= 0 )
            {
              v30[1] = *(_DWORD *)Data;
              *v20 |= 1u;
            }
            v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
            if ( (int)CommonUtil::GetDwordFromRegistry(v21, L"ActionResult", v26, v22) >= 0 )
            {
              v20[2] = *(_DWORD *)v26;
              *v20 |= 2u;
            }
            if ( (int)LPA::EnterpriseManager::LoadProfileDetailsFromRegistry(
                        (__int64)this,
                        (__int64)v38,
                        (__int64 *)&v30) >= 0
              || *v30 )
            {
              std::wstring::wstring(v37, v38);
              v23 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::EsimDetails>>::_Try_emplace<std::wstring,>(
                      (char *)this + 88,
                      v34,
                      v37);
              std::unique_ptr<LPA::EnterpriseManager::EsimDetails>::operator=<std::default_delete<LPA::EnterpriseManager::EsimDetails>,0>(
                (__int64 *)(*(_QWORD *)v23 + 64LL),
                (__int64 *)&v30);
              std::wstring::_Tidy_deallocate(v37);
            }
            std::unique_ptr<LPA::EnterpriseManager::EsimDetails>::~unique_ptr<LPA::EnterpriseManager::EsimDetails>(&v30);
            std::wstring::_Tidy_deallocate(v35);
          }
          std::wstring::_Tidy_deallocate(v36);
          ++v9;
        }
        while ( v9 < cSubKeys );
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147024894 && (unsigned int)CallbackContext > 3 )
  {
    v28 = cSubKeys;
    cchName = v5;
    v33 = "LPA::EnterpriseManager::LoadEsimDetailsFromRegistry";
    v32 = "LpaServiceEnterpriseManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      0x80000000,
      (unsigned int)&unk_18012BB28,
      v6,
      v7,
      (__int64)&v32,
      (__int64)&v33,
      (__int64)&cchName,
      (__int64)&v28);
  }
}

```

## disassembly

```asm
0x18007ba00  mov     rax, rsp
0x18007ba03  mov     [rax+10h], rbx
0x18007ba07  mov     [rax+18h], rsi
0x18007ba0b  push    rbp
0x18007ba0c  push    rdi
0x18007ba0d  push    r13
0x18007ba0f  push    r14
0x18007ba11  push    r15
0x18007ba13  lea     rbp, [rsp-80h]
0x18007ba18  sub     rsp, 180h
0x18007ba1f  movaps  xmmword ptr [rax-38h], xmm6
0x18007ba23  mov     rax, cs:__security_cookie
0x18007ba2a  xor     rax, rsp
0x18007ba2d  mov     [rbp+0A0h+var_40], rax
0x18007ba31  mov     r14, rcx
0x18007ba34  xor     r15d, r15d
0x18007ba37  mov     [rbp+0A0h+hKey], r15
0x18007ba3b  mov     [rsp+1A0h+cSubKeys], r15d
0x18007ba40  mov     [rsp+1A0h+cbMaxSubKeyLen], r15d
0x18007ba45  xor     r8d, r8d
0x18007ba48  lea     rdx, [rbp+0A0h+var_B8]
0x18007ba4c  call    ?GetEnterpriseSettingsEuiccsKey@EnterpriseManager@LPA@@AEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsKey(bool)
0x18007ba51  mov     rcx, rax
0x18007ba54  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007ba59  lea     rcx, [rbp+0A0h+hKey]
0x18007ba5d  mov     [rsp+1A0h+phkResult], rcx; phkResult
0x18007ba62  mov     r9d, 20019h; samDesired
0x18007ba68  xor     r8d, r8d; ulOptions
0x18007ba6b  mov     rdx, rax; lpSubKey
0x18007ba6e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007ba75  call    cs:__imp_RegOpenKeyExW
0x18007ba7b  mov     edi, eax
0x18007ba7d  test    eax, eax
0x18007ba7f  jle     short loc_18007BA8A
0x18007ba81  movzx   edi, ax
0x18007ba84  or      edi, 80070000h
0x18007ba8a  lea     rcx, [rbp+0A0h+var_B8]
0x18007ba8e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007ba93  lea     r13, aLpaEnterprisem; "LPA::EnterpriseManager::LoadEsimDetails"...
0x18007ba9a  lea     rbx, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007baa1  test    edi, edi
0x18007baa3  js      loc_18007BD3E
0x18007baa9  mov     [rsp+1A0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18007baae  mov     [rsp+1A0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18007bab3  mov     [rsp+1A0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18007bab8  mov     [rsp+1A0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18007babd  mov     [rsp+1A0h+lpcValues], r15; lpcValues
0x18007bac2  mov     [rsp+1A0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18007bac7  lea     rax, [rsp+1A0h+cbMaxSubKeyLen]
0x18007bacc  mov     [rsp+1A0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18007bad1  lea     rax, [rsp+1A0h+cSubKeys]
0x18007bad6  mov     [rsp+1A0h+phkResult], rax; lpcSubKeys
0x18007badb  xor     r9d, r9d; lpReserved
0x18007bade  xor     r8d, r8d; lpcchClass
0x18007bae1  xor     edx, edx; lpClass
0x18007bae3  mov     rcx, [rbp+0A0h+hKey]; hKey
0x18007bae7  call    cs:__imp_RegQueryInfoKeyW
0x18007baed  mov     edi, eax
0x18007baef  test    eax, eax
0x18007baf1  jle     short loc_18007BAFC
0x18007baf3  movzx   edi, ax
0x18007baf6  or      edi, 80070000h
0x18007bafc  test    edi, edi
0x18007bafe  js      loc_18007BD3E
0x18007bb04  mov     esi, r15d
0x18007bb07  cmp     [rsp+1A0h+cSubKeys], r15d
0x18007bb0c  jbe     loc_18007BD3E
0x18007bb12  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18007bb1a  xor     edx, edx; Val
0x18007bb1c  lea     r8d, [rdx+42h]; Size
0x18007bb20  lea     rcx, [rbp+0A0h+var_90]; void *
0x18007bb24  call    memset_0
0x18007bb29  mov     ecx, [rsp+1A0h+cbMaxSubKeyLen]
0x18007bb2d  inc     ecx
0x18007bb2f  mov     [rsp+1A0h+cchName], ecx
0x18007bb33  xorps   xmm0, xmm0
0x18007bb36  movups  [rbp+0A0h+var_D8], xmm0
0x18007bb3a  movdqu  [rbp+0A0h+var_C8], xmm6
0x18007bb3f  mov     word ptr [rbp+0A0h+var_D8], r15w
0x18007bb44  xor     r8d, r8d
0x18007bb47  mov     edx, ecx
0x18007bb49  lea     rcx, [rbp+0A0h+var_D8]
0x18007bb4d  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18007bb52  lea     rcx, [rbp+0A0h+var_D8]
0x18007bb56  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007bb5b  mov     r8, rax; lpName
0x18007bb5e  mov     [rsp+1A0h+lpcValues], r15; lpftLastWriteTime
0x18007bb63  mov     [rsp+1A0h+lpcbMaxClassLen], r15; lpcchClass
0x18007bb68  mov     [rsp+1A0h+lpcbMaxSubKeyLen], r15; lpClass
0x18007bb6d  mov     [rsp+1A0h+phkResult], r15; lpReserved
0x18007bb72  lea     r9, [rsp+1A0h+cchName]; lpcchName
0x18007bb77  mov     edx, esi; dwIndex
0x18007bb79  mov     rcx, [rbp+0A0h+hKey]; hKey
0x18007bb7d  call    cs:__imp_RegEnumKeyExW
0x18007bb83  mov     ecx, eax
0x18007bb85  test    eax, eax
0x18007bb87  jle     short loc_18007BB92
0x18007bb89  movzx   ecx, ax
0x18007bb8c  or      ecx, 80070000h
0x18007bb92  test    ecx, ecx
0x18007bb94  js      loc_18007BCC9
0x18007bb9a  lea     rcx, [rbp+0A0h+var_D8]
0x18007bb9e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007bba3  mov     r8, rax; unsigned __int16 *
0x18007bba6  mov     edx, 21h ; '!'; unsigned __int64
0x18007bbab  lea     rcx, [rbp+0A0h+var_90]; unsigned __int16 *
0x18007bbaf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007bbb4  mov     ecx, eax
0x18007bbb6  test    eax, eax
0x18007bbb8  js      loc_18007BCC9
0x18007bbbe  mov     dword ptr [rsp+1A0h+Data], r15d
0x18007bbc3  mov     dword ptr [rsp+1A0h+var_138], r15d
0x18007bbc8  xorps   xmm0, xmm0
0x18007bbcb  movups  [rbp+0A0h+var_F8], xmm0
0x18007bbcf  movdqu  [rbp+0A0h+var_E8], xmm6
0x18007bbd4  mov     word ptr [rbp+0A0h+var_F8], r15w
0x18007bbd9  lea     rcx, [rsp+1A0h+var_128]
0x18007bbde  call    ??$make_unique@UEsimDetails@EnterpriseManager@LPA@@$$V$0A@@std@@YA?AV?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@0@XZ; std::make_unique<LPA::EnterpriseManager::EsimDetails,,0>(void)
0x18007bbe3  nop
0x18007bbe4  lea     r9, [rbp+0A0h+var_F8]
0x18007bbe8  xor     r8d, r8d
0x18007bbeb  lea     rdx, [rbp+0A0h+var_90]
0x18007bbef  mov     rcx, r14
0x18007bbf2  call    ?AssembleEuiccRegKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBG_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::AssembleEuiccRegKey(ushort const (&)[33],bool,std::wstring &)
0x18007bbf7  lea     rcx, [rbp+0A0h+var_F8]
0x18007bbfb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007bc00  mov     rcx, rax; lpSubKey
0x18007bc03  lea     r8, [rsp+1A0h+Data]; lpData
0x18007bc08  lea     rdx, aPolicies; "Policies"
0x18007bc0f  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007bc14  mov     rbx, [rsp+1A0h+var_128]
0x18007bc19  test    eax, eax
0x18007bc1b  js      short loc_18007BC27
0x18007bc1d  mov     eax, dword ptr [rsp+1A0h+Data]
0x18007bc21  mov     [rbx+4], eax
0x18007bc24  or      dword ptr [rbx], 1
0x18007bc27  lea     rcx, [rbp+0A0h+var_F8]
0x18007bc2b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007bc30  mov     rcx, rax; lpSubKey
0x18007bc33  lea     r8, [rsp+1A0h+var_138]; lpData
0x18007bc38  lea     rdx, aActionresult; "ActionResult"
0x18007bc3f  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007bc44  test    eax, eax
0x18007bc46  js      short loc_18007BC52
0x18007bc48  mov     eax, dword ptr [rsp+1A0h+var_138]
0x18007bc4c  mov     [rbx+8], eax
0x18007bc4f  or      dword ptr [rbx], 2
0x18007bc52  lea     r8, [rsp+1A0h+var_128]
0x18007bc57  lea     rdx, [rbp+0A0h+var_90]
0x18007bc5b  mov     rcx, r14
0x18007bc5e  call    ?LoadProfileDetailsFromRegistry@EnterpriseManager@LPA@@AEAAJAEAY0CB@$$CBGAEBV?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@std@@@Z; LPA::EnterpriseManager::LoadProfileDetailsFromRegistry(ushort const (&)[33],std::unique_ptr<LPA::EnterpriseManager::EsimDetails> const &)
0x18007bc63  test    eax, eax
0x18007bc65  jns     short loc_18007BC71
0x18007bc67  mov     rax, [rsp+1A0h+var_128]
0x18007bc6c  cmp     [rax], r15d
0x18007bc6f  jz      short loc_18007BCAC
0x18007bc71  lea     rdx, [rbp+0A0h+var_90]
0x18007bc75  lea     rcx, [rbp+0A0h+var_B8]
0x18007bc79  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007bc7e  nop
0x18007bc7f  lea     rcx, [r14+58h]
0x18007bc83  lea     r8, [rbp+0A0h+var_B8]
0x18007bc87  lea     rdx, [rbp+0A0h+var_108]
0x18007bc8b  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::EsimDetails>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007bc90  mov     rcx, [rax]
0x18007bc93  add     rcx, 40h ; '@'
0x18007bc97  lea     rdx, [rsp+1A0h+var_128]
0x18007bc9c  call    ??$?4U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@$0A@@?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA::EnterpriseManager::EsimDetails>::operator=<std::default_delete<LPA::EnterpriseManager::EsimDetails>,0>(std::unique_ptr<LPA::EnterpriseManager::EsimDetails> &&)
0x18007bca1  nop
0x18007bca2  lea     rcx, [rbp+0A0h+var_B8]
0x18007bca6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007bcab  nop
0x18007bcac  lea     rcx, [rsp+1A0h+var_128]
0x18007bcb1  call    ??1?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::EnterpriseManager::EsimDetails>::~unique_ptr<LPA::EnterpriseManager::EsimDetails>(void)
0x18007bcb6  nop
0x18007bcb7  lea     rcx, [rbp+0A0h+var_F8]
0x18007bcbb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007bcc0  lea     rbx, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007bcc7  jmp     short loc_18007BD29
0x18007bcc9  mov     eax, cs:CallbackContext
0x18007bccf  cmp     eax, 3
0x18007bcd2  jbe     short loc_18007BD29
0x18007bcd4  mov     eax, [rsp+1A0h+cchName]
0x18007bcd8  mov     dword ptr [rsp+1A0h+var_138], eax
0x18007bcdc  mov     dword ptr [rsp+1A0h+Data], esi
0x18007bce0  mov     [rsp+1A0h+var_130], ecx
0x18007bce4  mov     [rbp+0A0h+var_118], r13
0x18007bce8  mov     [rbp+0A0h+var_110], rbx
0x18007bcec  lea     rax, [rsp+1A0h+var_138]
0x18007bcf1  mov     [rsp+1A0h+lpcbMaxValueNameLen], rax
0x18007bcf6  lea     rax, [rsp+1A0h+Data]
0x18007bcfb  mov     [rsp+1A0h+lpcValues], rax
0x18007bd00  lea     rax, [rsp+1A0h+var_130]
0x18007bd05  mov     [rsp+1A0h+lpcbMaxClassLen], rax
0x18007bd0a  lea     rax, [rbp+0A0h+var_118]
0x18007bd0e  mov     [rsp+1A0h+lpcbMaxSubKeyLen], rax
0x18007bd13  lea     rax, [rbp+0A0h+var_110]
0x18007bd17  mov     [rsp+1A0h+phkResult], rax
0x18007bd1c  lea     rdx, byte_18012BB6D
0x18007bd23  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007bd28  nop
0x18007bd29  lea     rcx, [rbp+0A0h+var_D8]
0x18007bd2d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007bd32  inc     esi
0x18007bd34  cmp     esi, [rsp+1A0h+cSubKeys]
0x18007bd38  jb      loc_18007BB1A
0x18007bd3e  mov     rcx, [rbp+0A0h+hKey]; hKey
0x18007bd42  test    rcx, rcx
0x18007bd45  jz      short loc_18007BD51
0x18007bd47  call    cs:__imp_RegCloseKey
0x18007bd4d  mov     [rbp+0A0h+hKey], r15
0x18007bd51  mov     ecx, 80000000h
0x18007bd56  lea     eax, [rdi+rcx]
0x18007bd59  test    ecx, eax
0x18007bd5b  jnz     short loc_18007BDB6
0x18007bd5d  cmp     edi, 80070002h
0x18007bd63  jz      short loc_18007BDB6
0x18007bd65  mov     eax, cs:CallbackContext
0x18007bd6b  cmp     eax, 3
0x18007bd6e  jbe     short loc_18007BDB6
0x18007bd70  mov     eax, [rsp+1A0h+cSubKeys]
0x18007bd74  mov     [rsp+1A0h+var_130], eax
0x18007bd78  mov     [rsp+1A0h+cchName], edi
0x18007bd7c  mov     [rbp+0A0h+var_110], r13
0x18007bd80  mov     [rbp+0A0h+var_118], rbx
0x18007bd84  lea     rax, [rsp+1A0h+var_130]
0x18007bd89  mov     [rsp+1A0h+lpcValues], rax
0x18007bd8e  lea     rax, [rsp+1A0h+cchName]
0x18007bd93  mov     [rsp+1A0h+lpcbMaxClassLen], rax
0x18007bd98  lea     rax, [rbp+0A0h+var_110]
0x18007bd9c  mov     [rsp+1A0h+lpcbMaxSubKeyLen], rax
0x18007bda1  lea     rax, [rbp+0A0h+var_118]
0x18007bda5  mov     [rsp+1A0h+phkResult], rax
0x18007bdaa  lea     rdx, unk_18012BB28
0x18007bdb1  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007bdb6  mov     rcx, [rbp+0A0h+var_40]
0x18007bdba  xor     rcx, rsp; StackCookie
0x18007bdbd  call    __security_check_cookie
0x18007bdc2  lea     r11, [rsp+1A0h+var_20]
0x18007bdca  mov     rbx, [r11+38h]
0x18007bdce  mov     rsi, [r11+40h]
0x18007bdd2  movaps  xmm6, xmmword ptr [r11-10h]
0x18007bdd7  mov     rsp, r11
0x18007bdda  pop     r15
0x18007bddc  pop     r14
0x18007bdde  pop     r13
0x18007bde0  pop     rdi
0x18007bde1  pop     rbp
0x18007bde2  retn
```
