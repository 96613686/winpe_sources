# LPA::EnterpriseManager::LoadProfileDetailsFromRegistry(ushort const (&)[33],std::unique_ptr<LPA::EnterpriseManager::EsimDetails,std::default_delete<LPA::EnterpriseManager::EsimDetails>> const &)

- ea: `0x18007bdec`
- end: `0x18007c2fc`
- name: `?LoadProfileDetailsFromRegistry@EnterpriseManager@LPA@@AEAAJAEAY0CB@$$CBGAEBV?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@std@@@Z`
- size: `1296`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007ba00`

## callees

- `0x1800018b4`
- `0x18000199c`
- `0x18000df90`
- `0x18000ebf4`
- `0x18005cd20`
- `0x180063668`
- `0x180071344`
- `0x180071650`
- `0x180074204`
- `0x180075618`
- `0x1800769fc`
- `0x1800774b0`
- `0x180077628`
- `0x1800776c4`
- `0x180079550`
- `0x18007a4d8`
- `0x18007bdec`
- `0x180081154`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c24b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c24b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007bfa1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007bfa1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007be92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007be92`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007bf00`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007bf00`

## string_xrefs

- `0x18007beb2`: `LpaServiceEnterpriseManager`
- `0x18007c1d0`: `LpaServiceEnterpriseManager`
- `0x18007c23b`: `LpaServiceEnterpriseManager`
- `0x18007beab`: `LPA::EnterpriseManager::LoadProfileDetailsFromRegistry`
- `0x18007c1c5`: `LPA::EnterpriseManager::LoadProfileDetailsFromRegistry`
- `0x18007c234`: `LPA::EnterpriseManager::LoadProfileDetailsFromRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall LPA::EnterpriseManager::LoadProfileDetailsFromRegistry(__int64 a1, __int64 a2, __int64 *a3)
{
  int v3; // r13d
  int v4; // r12d
  __m128i si128; // xmm6
  const WCHAR *v6; // rax
  LSTATUS v7; // eax
  int v8; // r8d
  int v9; // r9d
  signed int v10; // r14d
  LSTATUS v11; // eax
  DWORD v12; // r15d
  __int64 *v13; // r14
  WCHAR *v14; // rax
  LSTATUS v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  signed int StringFromRegistry; // edi
  const unsigned __int16 *v20; // rax
  const WCHAR *v21; // rax
  const WCHAR *v22; // rax
  const WCHAR *v23; // rax
  unsigned int *v24; // r9
  const WCHAR *v25; // rax
  unsigned int *v26; // r9
  int v27; // edi
  int v28; // esi
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rbx
  __int64 v33; // rax
  DWORD cSubKeys; // [rsp+68h] [rbp-A0h] BYREF
  BYTE v36[4]; // [rsp+6Ch] [rbp-9Ch] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-98h] BYREF
  __int64 *v38; // [rsp+78h] [rbp-90h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+80h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+84h] [rbp-84h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-80h] BYREF
  const char *v42; // [rsp+90h] [rbp-78h] BYREF
  const char *v43; // [rsp+98h] [rbp-70h] BYREF
  char v44[24]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v45[80]; // [rsp+B8h] [rbp-50h] BYREF
  _OWORD v46[2]; // [rsp+108h] [rbp+0h] BYREF
  _OWORD v47[2]; // [rsp+128h] [rbp+20h] BYREF
  _OWORD v48[2]; // [rsp+148h] [rbp+40h] BYREF
  _OWORD v49[2]; // [rsp+168h] [rbp+60h] BYREF
  _OWORD v50[2]; // [rsp+188h] [rbp+80h] BYREF
  _BYTE v51[32]; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int16 v52[8]; // [rsp+1C8h] [rbp+C0h] BYREF
  _BYTE v53[26]; // [rsp+1D8h] [rbp+D0h] BYREF

  v38 = a3;
  v3 = a2;
  v4 = a1;
  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v50[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v50[1] = si128;
  LOWORD(v50[0]) = 0;
  LPA::EnterpriseManager::AssembleProfilesRegKey(a1, a2, 0, v50);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey);
  v10 = v7;
  if ( v7 > 0 )
    v10 = (unsigned __int16)v7 | 0x80070000;
  if ( v10 >= 0 )
  {
    v11 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    v10 = v11;
    *(_DWORD *)&Data[4] = v11;
    if ( v11 > 0 )
    {
      v10 = (unsigned __int16)v11 | 0x80070000;
      *(_DWORD *)&Data[4] = v10;
    }
    if ( v10 >= 0 )
    {
      v12 = 0;
      if ( cSubKeys )
      {
        v13 = v38;
        do
        {
          *(_OWORD *)v52 = 0;
          memset(v53, 0, sizeof(v53));
          cchName = cbMaxSubKeyLen + 1;
          v47[0] = 0;
          v47[1] = si128;
          LOWORD(v47[0]) = 0;
          std::wstring::resize(v47, cbMaxSubKeyLen + 1, 0);
          v14 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
          v15 = RegEnumKeyExW(hKey, v12, v14, &cchName, 0, 0, 0, 0);
          StringFromRegistry = v15;
          if ( v15 > 0 )
            StringFromRegistry = (unsigned __int16)v15 | 0x80070000;
          if ( StringFromRegistry < 0 )
            goto LABEL_21;
          v20 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
          StringFromRegistry = StringCchCopyW(v52, 0x15u, v20);
          if ( StringFromRegistry < 0 )
            goto LABEL_21;
          v46[0] = 0;
          v46[1] = si128;
          LOWORD(v46[0]) = 0;
          v49[0] = 0;
          v49[1] = si128;
          LOWORD(v49[0]) = 0;
          v48[0] = 0;
          v48[1] = si128;
          LOWORD(v48[0]) = 0;
          *(_DWORD *)Data = 0;
          *(_DWORD *)v36 = 0;
          LPA::EnterpriseManager::AssembleProfileRegKey(v4, v3, (unsigned int)v52, 0, (__int64)v46);
          v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
          StringFromRegistry = CommonUtil::GetStringFromRegistry(v21, L"ServerName");
          if ( StringFromRegistry >= 0 )
          {
            v22 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
            StringFromRegistry = CommonUtil::GetStringFromRegistry(v22, L"MatchingId");
            if ( StringFromRegistry >= 0 )
            {
              v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
              StringFromRegistry = CommonUtil::GetDwordFromRegistry(v23, L"State", Data, v24);
              if ( StringFromRegistry >= 0 )
              {
                v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
                StringFromRegistry = CommonUtil::GetDwordFromRegistry(v25, L"ErrorDetail", v36, v26);
                if ( StringFromRegistry >= 0 )
                {
                  memset_0(v45, 0, 0x42u);
                  v38 = 0;
                  v27 = *(_DWORD *)v36;
                  v28 = *(_DWORD *)Data;
                  v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v48);
                  v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v49);
                  StringFromRegistry = LPA::EnterpriseManager::AssembleEnterpriseProfileDetails(
                                         v31,
                                         v45,
                                         v52,
                                         v30,
                                         v29,
                                         v28,
                                         v27,
                                         &v38);
                  if ( StringFromRegistry >= 0 )
                  {
                    v32 = *v13;
                    std::wstring::wstring(v51, v52);
                    v33 = std::map<std::wstring,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>>::_Try_emplace<std::wstring,>(
                            v32 + 16,
                            v44,
                            v51);
                    std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>::operator=<std::default_delete<LPA_ENTERPRISE_PROFILE_DETAILS>,0>(
                      (void **)(*(_QWORD *)v33 + 64LL),
                      (void **)&v38);
                    std::wstring::_Tidy_deallocate(v51);
                  }
                  std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>::~unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>(&v38);
                }
              }
            }
          }
          std::wstring::_Tidy_deallocate(v48);
          std::wstring::_Tidy_deallocate(v49);
          std::wstring::_Tidy_deallocate(v46);
          if ( StringFromRegistry < 0 )
          {
LABEL_21:
            if ( (unsigned int)CallbackContext > 3 )
            {
              *(_DWORD *)Data = cchName;
              *(_DWORD *)v36 = v12;
              LODWORD(v38) = StringFromRegistry;
              v42 = "LPA::EnterpriseManager::LoadProfileDetailsFromRegistry";
              v43 = "LpaServiceEnterpriseManager";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v16,
                (unsigned int)&dword_18012B904,
                v17,
                v18,
                (__int64)&v43,
                (__int64)&v42,
                (__int64)&v38,
                (__int64)v36,
                (__int64)Data);
            }
          }
          std::wstring::_Tidy_deallocate(v47);
          ++v12;
        }
        while ( v12 < cSubKeys );
        v10 = *(_DWORD *)&Data[4];
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (int)(v10 + 0x80000000) >= 0 && v10 != -2147024894 && (unsigned int)CallbackContext > 3 )
  {
    LODWORD(v38) = cSubKeys;
    *(_DWORD *)&Data[4] = v10;
    v43 = "LPA::EnterpriseManager::LoadProfileDetailsFromRegistry";
    v42 = "LpaServiceEnterpriseManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      0x80000000,
      (unsigned int)&byte_18012B8BF,
      v8,
      v9,
      (__int64)&v42,
      (__int64)&v43,
      (__int64)&Data[4],
      (__int64)&v38);
  }
  std::wstring::_Tidy_deallocate(v50);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18007bdec  mov     rax, rsp
0x18007bdef  mov     [rax+20h], rbx
0x18007bdf3  push    rbp
0x18007bdf4  push    rsi
0x18007bdf5  push    rdi
0x18007bdf6  push    r12
0x18007bdf8  push    r13
0x18007bdfa  push    r14
0x18007bdfc  push    r15
0x18007bdfe  lea     rbp, [rax-148h]
0x18007be05  sub     rsp, 210h
0x18007be0c  movaps  xmmword ptr [rax-48h], xmm6
0x18007be10  mov     rax, cs:__security_cookie
0x18007be17  xor     rax, rsp
0x18007be1a  mov     [rbp+140h+var_50], rax
0x18007be21  mov     [rsp+240h+var_1D0], r8
0x18007be26  mov     r13, rdx
0x18007be29  mov     r12, rcx
0x18007be2c  xor     ebx, ebx
0x18007be2e  mov     [rbp+140h+hKey], rbx
0x18007be32  mov     [rsp+240h+cSubKeys], ebx
0x18007be36  mov     [rsp+240h+cbMaxSubKeyLen], ebx
0x18007be3a  xorps   xmm0, xmm0
0x18007be3d  movups  [rbp+140h+var_C0], xmm0
0x18007be44  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18007be4c  movdqu  [rbp+140h+var_B0], xmm6
0x18007be54  mov     word ptr [rbp+140h+var_C0], bx
0x18007be5b  lea     r9, [rbp+140h+var_C0]
0x18007be62  xor     r8d, r8d
0x18007be65  call    ?AssembleProfilesRegKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBG_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::AssembleProfilesRegKey(ushort const (&)[33],bool,std::wstring &)
0x18007be6a  lea     rcx, [rbp+140h+var_C0]
0x18007be71  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007be76  mov     rdx, rax; lpSubKey
0x18007be79  lea     rax, [rbp+140h+hKey]
0x18007be7d  mov     [rsp+240h+phkResult], rax; phkResult
0x18007be82  mov     r9d, 20019h; samDesired
0x18007be88  xor     r8d, r8d; ulOptions
0x18007be8b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007be92  call    cs:__imp_RegOpenKeyExW
0x18007be98  mov     r14d, eax
0x18007be9b  mov     esi, 80070000h
0x18007bea0  test    eax, eax
0x18007bea2  jle     short loc_18007BEAB
0x18007bea4  movzx   r14d, ax
0x18007bea8  or      r14d, esi
0x18007beab  lea     rdi, aLpaEnterprisem_12; "LPA::EnterpriseManager::LoadProfileDeta"...
0x18007beb2  lea     r15, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007beb9  test    r14d, r14d
0x18007bebc  js      loc_18007C242
0x18007bec2  mov     [rsp+240h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18007bec7  mov     [rsp+240h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18007becc  mov     [rsp+240h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x18007bed1  mov     [rsp+240h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x18007bed6  mov     [rsp+240h+lpcValues], rbx; lpcValues
0x18007bedb  mov     [rsp+240h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x18007bee0  lea     rax, [rsp+240h+cbMaxSubKeyLen]
0x18007bee5  mov     [rsp+240h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18007beea  lea     rax, [rsp+240h+cSubKeys]
0x18007beef  mov     [rsp+240h+phkResult], rax; lpcSubKeys
0x18007bef4  xor     r9d, r9d; lpReserved
0x18007bef7  xor     r8d, r8d; lpcchClass
0x18007befa  xor     edx, edx; lpClass
0x18007befc  mov     rcx, [rbp+140h+hKey]; hKey
0x18007bf00  call    cs:__imp_RegQueryInfoKeyW
0x18007bf06  mov     r14d, eax
0x18007bf09  mov     dword ptr [rsp+240h+Data+4], eax
0x18007bf0d  test    eax, eax
0x18007bf0f  jle     short loc_18007BF1D
0x18007bf11  movzx   r14d, ax
0x18007bf15  or      r14d, esi
0x18007bf18  mov     dword ptr [rsp+240h+Data+4], r14d
0x18007bf1d  test    r14d, r14d
0x18007bf20  js      loc_18007C242
0x18007bf26  mov     r15d, ebx
0x18007bf29  cmp     [rsp+240h+cSubKeys], ebx
0x18007bf2d  jbe     loc_18007C23B
0x18007bf33  mov     r14, [rsp+240h+var_1D0]
0x18007bf38  xorps   xmm0, xmm0
0x18007bf3b  movups  xmmword ptr [rbp+140h+var_80], xmm0
0x18007bf42  movups  xmmword ptr [rbp+140h+var_70], xmm0
0x18007bf49  movups  xmmword ptr [rbp+140h+var_70+0Ah], xmm0
0x18007bf50  mov     ecx, [rsp+240h+cbMaxSubKeyLen]
0x18007bf54  inc     ecx
0x18007bf56  mov     [rsp+240h+cchName], ecx
0x18007bf5a  movups  [rbp+140h+var_120], xmm0
0x18007bf5e  movdqu  [rbp+140h+var_110], xmm6
0x18007bf63  mov     word ptr [rbp+140h+var_120], bx
0x18007bf67  xor     r8d, r8d
0x18007bf6a  mov     edx, ecx
0x18007bf6c  lea     rcx, [rbp+140h+var_120]
0x18007bf70  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18007bf75  lea     rcx, [rbp+140h+var_120]
0x18007bf79  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007bf7e  mov     r8, rax; lpName
0x18007bf81  mov     [rsp+240h+lpcValues], rbx; lpftLastWriteTime
0x18007bf86  mov     [rsp+240h+lpcbMaxClassLen], rbx; lpcchClass
0x18007bf8b  mov     [rsp+240h+lpcbMaxSubKeyLen], rbx; lpClass
0x18007bf90  mov     [rsp+240h+phkResult], rbx; lpReserved
0x18007bf95  lea     r9, [rsp+240h+cchName]; lpcchName
0x18007bf9a  mov     edx, r15d; dwIndex
0x18007bf9d  mov     rcx, [rbp+140h+hKey]; hKey
0x18007bfa1  call    cs:__imp_RegEnumKeyExW
0x18007bfa7  mov     edi, eax
0x18007bfa9  test    eax, eax
0x18007bfab  jle     short loc_18007BFB2
0x18007bfad  movzx   edi, ax
0x18007bfb0  or      edi, esi
0x18007bfb2  test    edi, edi
0x18007bfb4  js      loc_18007C1A9
0x18007bfba  lea     rcx, [rbp+140h+var_120]
0x18007bfbe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007bfc3  mov     r8, rax; unsigned __int16 *
0x18007bfc6  mov     edx, 15h; unsigned __int64
0x18007bfcb  lea     rcx, [rbp+140h+var_80]; unsigned __int16 *
0x18007bfd2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007bfd7  mov     edi, eax
0x18007bfd9  test    eax, eax
0x18007bfdb  js      loc_18007C1A9
0x18007bfe1  xorps   xmm0, xmm0
0x18007bfe4  movups  [rbp+140h+var_140], xmm0
0x18007bfe8  movdqu  [rbp+140h+var_130], xmm6
0x18007bfed  mov     word ptr [rbp+140h+var_140], bx
0x18007bff1  movups  [rbp+140h+var_E0], xmm0
0x18007bff5  movdqu  [rbp+140h+var_D0], xmm6
0x18007bffa  mov     word ptr [rbp+140h+var_E0], bx
0x18007bffe  movups  [rbp+140h+var_100], xmm0
0x18007c002  movdqu  [rbp+140h+var_F0], xmm6
0x18007c007  mov     word ptr [rbp+140h+var_100], bx
0x18007c00b  mov     dword ptr [rsp+240h+Data], ebx
0x18007c00f  mov     dword ptr [rsp+240h+var_1DC], ebx
0x18007c013  lea     rax, [rbp+140h+var_140]
0x18007c017  mov     [rsp+240h+phkResult], rax
0x18007c01c  xor     r9d, r9d
0x18007c01f  lea     r8, [rbp+140h+var_80]
0x18007c026  mov     rdx, r13
0x18007c029  mov     rcx, r12
0x18007c02c  call    ?AssembleProfileRegKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBGAEAY0BF@$$CBG_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::AssembleProfileRegKey(ushort const (&)[33],ushort const (&)[21],bool,std::wstring &)
0x18007c031  lea     rcx, [rbp+140h+var_140]
0x18007c035  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c03a  mov     rcx, rax; lpSubKey
0x18007c03d  lea     r8, [rbp+140h+var_E0]
0x18007c041  lea     rdx, aServername; "ServerName"
0x18007c048  call    ?GetStringFromRegistry@CommonUtil@@YAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommonUtil::GetStringFromRegistry(ushort const *,ushort const *,std::wstring &)
0x18007c04d  mov     edi, eax
0x18007c04f  test    eax, eax
0x18007c051  js      loc_18007C188
0x18007c057  lea     rcx, [rbp+140h+var_140]
0x18007c05b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c060  mov     rcx, rax; lpSubKey
0x18007c063  lea     r8, [rbp+140h+var_100]
0x18007c067  lea     rdx, aMatchingid_0; "MatchingId"
0x18007c06e  call    ?GetStringFromRegistry@CommonUtil@@YAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommonUtil::GetStringFromRegistry(ushort const *,ushort const *,std::wstring &)
0x18007c073  mov     edi, eax
0x18007c075  test    eax, eax
0x18007c077  js      loc_18007C188
0x18007c07d  lea     rcx, [rbp+140h+var_140]
0x18007c081  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c086  mov     rcx, rax; lpSubKey
0x18007c089  lea     r8, [rsp+240h+Data]; lpData
0x18007c08e  lea     rdx, aState; "State"
0x18007c095  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007c09a  mov     edi, eax
0x18007c09c  test    eax, eax
0x18007c09e  js      loc_18007C188
0x18007c0a4  lea     rcx, [rbp+140h+var_140]
0x18007c0a8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c0ad  mov     rcx, rax; lpSubKey
0x18007c0b0  lea     r8, [rsp+240h+var_1DC]; lpData
0x18007c0b5  lea     rdx, aErrordetail; "ErrorDetail"
0x18007c0bc  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007c0c1  mov     edi, eax
0x18007c0c3  test    eax, eax
0x18007c0c5  js      loc_18007C188
0x18007c0cb  xor     edx, edx; Val
0x18007c0cd  lea     r8d, [rdx+42h]; Size
0x18007c0d1  lea     rcx, [rbp+140h+var_190]; void *
0x18007c0d5  call    memset_0
0x18007c0da  mov     [rsp+240h+var_1D0], rbx
0x18007c0df  mov     edi, dword ptr [rsp+240h+var_1DC]
0x18007c0e3  mov     esi, dword ptr [rsp+240h+Data]
0x18007c0e7  lea     rcx, [rbp+140h+var_100]
0x18007c0eb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c0f0  mov     rbx, rax
0x18007c0f3  lea     rcx, [rbp+140h+var_E0]
0x18007c0f7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c0fc  mov     r9, rax
0x18007c0ff  lea     rax, [rsp+240h+var_1D0]
0x18007c104  mov     [rsp+240h+lpcValues], rax
0x18007c109  mov     dword ptr [rsp+240h+lpcbMaxClassLen], edi
0x18007c10d  mov     dword ptr [rsp+240h+lpcbMaxSubKeyLen], esi
0x18007c111  mov     [rsp+240h+phkResult], rbx
0x18007c116  lea     r8, [rbp+140h+var_80]
0x18007c11d  lea     rdx, [rbp+140h+var_190]
0x18007c121  call    ?AssembleEnterpriseProfileDetails@EnterpriseManager@LPA@@AEAAJAEAY0CB@$$CBGAEAY0BF@$$CBGPEBG2W4LPAENTERPRISEPROFILESTATE@@W4LPAERROR@@AEAV?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@std@@@Z; LPA::EnterpriseManager::AssembleEnterpriseProfileDetails(ushort const (&)[33],ushort const (&)[21],ushort const *,ushort const *,LPAENTERPRISEPROFILESTATE,LPAERROR,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS> &)
0x18007c126  mov     edi, eax
0x18007c128  xor     ebx, ebx
0x18007c12a  test    eax, eax
0x18007c12c  js      short loc_18007C179
0x18007c12e  mov     rbx, [r14]
0x18007c131  lea     rdx, [rbp+140h+var_80]
0x18007c138  lea     rcx, [rbp+140h+var_A0]
0x18007c13f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007c144  nop
0x18007c145  lea     r8, [rbp+140h+var_A0]
0x18007c14c  lea     rdx, [rbp+140h+var_1A8]
0x18007c150  lea     rcx, [rbx+10h]
0x18007c154  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007c159  mov     rcx, [rax]
0x18007c15c  add     rcx, 40h ; '@'
0x18007c160  lea     rdx, [rsp+240h+var_1D0]
0x18007c165  call    ??$?4U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@$0A@@?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>::operator=<std::default_delete<LPA_ENTERPRISE_PROFILE_DETAILS>,0>(std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS> &&)
0x18007c16a  nop
0x18007c16b  lea     rcx, [rbp+140h+var_A0]
0x18007c172  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c177  xor     ebx, ebx
0x18007c179  lea     rcx, [rsp+240h+var_1D0]
0x18007c17e  call    ??1?$unique_ptr@ULPA_ENTERPRISE_PROFILE_DETAILS@@U?$default_delete@ULPA_ENTERPRISE_PROFILE_DETAILS@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>::~unique_ptr<LPA_ENTERPRISE_PROFILE_DETAILS>(void)
0x18007c183  mov     esi, 80070000h
0x18007c188  lea     rcx, [rbp+140h+var_100]
0x18007c18c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c191  nop
0x18007c192  lea     rcx, [rbp+140h+var_E0]
0x18007c196  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c19b  nop
0x18007c19c  lea     rcx, [rbp+140h+var_140]
0x18007c1a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c1a5  test    edi, edi
0x18007c1a7  jns     short loc_18007C218
0x18007c1a9  mov     eax, cs:CallbackContext
0x18007c1af  cmp     eax, 3
0x18007c1b2  jbe     short loc_18007C218
0x18007c1b4  mov     eax, [rsp+240h+cchName]
0x18007c1b8  mov     dword ptr [rsp+240h+Data], eax
0x18007c1bc  mov     dword ptr [rsp+240h+var_1DC], r15d
0x18007c1c1  mov     dword ptr [rsp+240h+var_1D0], edi
0x18007c1c5  lea     rax, aLpaEnterprisem_12; "LPA::EnterpriseManager::LoadProfileDeta"...
0x18007c1cc  mov     [rbp+140h+var_1B8], rax
0x18007c1d0  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007c1d7  mov     [rbp+140h+var_1B0], rax
0x18007c1db  lea     rax, [rsp+240h+Data]
0x18007c1e0  mov     [rsp+240h+lpcbMaxValueNameLen], rax
0x18007c1e5  lea     rax, [rsp+240h+var_1DC]
0x18007c1ea  mov     [rsp+240h+lpcValues], rax
0x18007c1ef  lea     rax, [rsp+240h+var_1D0]
0x18007c1f4  mov     [rsp+240h+lpcbMaxClassLen], rax
0x18007c1f9  lea     rax, [rbp+140h+var_1B8]
0x18007c1fd  mov     [rsp+240h+lpcbMaxSubKeyLen], rax
0x18007c202  lea     rax, [rbp+140h+var_1B0]
0x18007c206  mov     [rsp+240h+phkResult], rax
0x18007c20b  lea     rdx, dword_18012B904
0x18007c212  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007c217  nop
0x18007c218  lea     rcx, [rbp+140h+var_120]
0x18007c21c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c221  inc     r15d
0x18007c224  cmp     r15d, [rsp+240h+cSubKeys]
0x18007c229  jb      loc_18007BF38
0x18007c22f  mov     r14d, dword ptr [rsp+240h+Data+4]
0x18007c234  lea     rdi, aLpaEnterprisem_12; "LPA::EnterpriseManager::LoadProfileDeta"...
0x18007c23b  lea     r15, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007c242  mov     rcx, [rbp+140h+hKey]; hKey
0x18007c246  test    rcx, rcx
0x18007c249  jz      short loc_18007C255
0x18007c24b  call    cs:__imp_RegCloseKey
0x18007c251  mov     [rbp+140h+hKey], rbx
0x18007c255  mov     ecx, 80000000h
0x18007c25a  lea     eax, [r14+rcx]
0x18007c25e  test    ecx, eax
0x18007c260  jnz     short loc_18007C2BE
0x18007c262  cmp     r14d, 80070002h
0x18007c269  jz      short loc_18007C2BE
0x18007c26b  mov     eax, cs:CallbackContext
0x18007c271  cmp     eax, 3
0x18007c274  jbe     short loc_18007C2BE
0x18007c276  mov     eax, [rsp+240h+cSubKeys]
0x18007c27a  mov     dword ptr [rsp+240h+var_1D0], eax
0x18007c27e  mov     dword ptr [rsp+240h+Data+4], r14d
0x18007c283  mov     [rbp+140h+var_1B0], rdi
0x18007c287  mov     [rbp+140h+var_1B8], r15
0x18007c28b  lea     rax, [rsp+240h+var_1D0]
0x18007c290  mov     [rsp+240h+lpcValues], rax
0x18007c295  lea     rax, [rsp+240h+Data+4]
0x18007c29a  mov     [rsp+240h+lpcbMaxClassLen], rax
0x18007c29f  lea     rax, [rbp+140h+var_1B0]
0x18007c2a3  mov     [rsp+240h+lpcbMaxSubKeyLen], rax
0x18007c2a8  lea     rax, [rbp+140h+var_1B8]
0x18007c2ac  mov     [rsp+240h+phkResult], rax
0x18007c2b1  lea     rdx, byte_18012B8BF
0x18007c2b8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007c2bd  nop
0x18007c2be  lea     rcx, [rbp+140h+var_C0]
0x18007c2c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c2ca  mov     eax, r14d
0x18007c2cd  mov     rcx, [rbp+140h+var_50]
0x18007c2d4  xor     rcx, rsp; StackCookie
0x18007c2d7  call    __security_check_cookie
0x18007c2dc  lea     r11, [rsp+240h+var_30]
0x18007c2e4  mov     rbx, [r11+58h]
0x18007c2e8  movaps  xmm6, xmmword ptr [r11-10h]
0x18007c2ed  mov     rsp, r11
  ... truncated ...
```
