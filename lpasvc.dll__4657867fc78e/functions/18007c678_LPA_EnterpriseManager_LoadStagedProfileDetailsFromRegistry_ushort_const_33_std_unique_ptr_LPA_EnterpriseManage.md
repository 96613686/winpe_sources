# LPA::EnterpriseManager::LoadStagedProfileDetailsFromRegistry(ushort const (&)[33],std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails,std::default_delete<LPA::EnterpriseManager::StagedEsimDetails>> const &)

- ea: `0x18007c678`
- end: `0x18007cc03`
- name: `?LoadStagedProfileDetailsFromRegistry@EnterpriseManager@LPA@@AEAAJAEAY0CB@$$CBGAEBV?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@std@@@Z`
- size: `1419`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007c304`

## callees

- `0x1800018b4`
- `0x18000199c`
- `0x18000df90`
- `0x18005cd20`
- `0x180063668`
- `0x1800709e4`
- `0x180071344`
- `0x180071650`
- `0x180071a8c`
- `0x1800742d8`
- `0x1800757a0`
- `0x180075d30`
- `0x180076a74`
- `0x180077628`
- `0x1800776c4`
- `0x180079550`
- `0x18007a4d8`
- `0x18007c678`
- `0x180081154`
- `0x1800f1cd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007cb54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007cb54`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007c814`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007c814`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007c714`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007c714`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007c777`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007c777`

## string_xrefs

- `0x18007cabd`: `LpaServiceEnterpriseManager`
- `0x18007cb8c`: `LpaServiceEnterpriseManager`
- `0x18007c72a`: `LPA::EnterpriseManager::LoadStagedProfileDetailsFromRegistry`
- `0x18007c7a4`: `LPA::EnterpriseManager::LoadStagedProfileDetailsFromRegistry`
- `0x18007cb44`: `LPA::EnterpriseManager::LoadStagedProfileDetailsFromRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall LPA::EnterpriseManager::LoadStagedProfileDetailsFromRegistry(
        __int64 a1,
        const wchar_t *a2,
        __int64 *a3)
{
  __int64 *v3; // r12
  __m128i si128; // xmm6
  const WCHAR *v7; // rax
  LSTATUS v8; // eax
  int v9; // r8d
  int v10; // r9d
  signed int v11; // edi
  LSTATUS v12; // eax
  DWORD v13; // esi
  WCHAR *v14; // rax
  int v15; // eax
  int v16; // r9d
  bool v17; // sf
  const unsigned __int16 *v18; // rax
  const WCHAR *v19; // rax
  int StringFromRegistry; // ecx
  int v21; // r8d
  int v22; // r9d
  const WCHAR *v23; // rax
  const WCHAR *v24; // rax
  unsigned int *v25; // r9
  const WCHAR *v26; // rax
  const WCHAR *v27; // rax
  unsigned int *v28; // r9
  int v29; // eax
  const char *v30; // rcx
  int v31; // eax
  __int64 v32; // rbx
  __int64 v33; // rax
  char v35; // [rsp+68h] [rbp-A0h] BYREF
  bool v36; // [rsp+69h] [rbp-9Fh] BYREF
  DWORD v37; // [rsp+6Ch] [rbp-9Ch] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-98h] BYREF
  DWORD v39; // [rsp+74h] [rbp-94h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+78h] [rbp-90h] BYREF
  BYTE Data[4]; // [rsp+7Ch] [rbp-8Ch] BYREF
  BYTE v42[4]; // [rsp+80h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+84h] [rbp-84h] BYREF
  LSTATUS v44; // [rsp+88h] [rbp-80h]
  __int64 v45; // [rsp+90h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-70h] BYREF
  const char *v47; // [rsp+A0h] [rbp-68h] BYREF
  const char *v48; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v51[8]; // [rsp+C0h] [rbp-48h] BYREF
  std::_Ref_count_base *v52; // [rsp+C8h] [rbp-40h]
  _BYTE v53[16]; // [rsp+D0h] [rbp-38h] BYREF
  _OWORD v54[2]; // [rsp+E0h] [rbp-28h] BYREF
  _OWORD v55[2]; // [rsp+100h] [rbp-8h] BYREF
  _OWORD v56[2]; // [rsp+120h] [rbp+18h] BYREF
  _OWORD v57[2]; // [rsp+140h] [rbp+38h] BYREF
  _OWORD v58[2]; // [rsp+160h] [rbp+58h] BYREF
  _OWORD v59[2]; // [rsp+180h] [rbp+78h] BYREF
  _BYTE v60[32]; // [rsp+1A0h] [rbp+98h] BYREF
  unsigned __int16 v61[8]; // [rsp+1C0h] [rbp+B8h] BYREF
  _BYTE v62[26]; // [rsp+1D0h] [rbp+C8h] BYREF

  v3 = a3;
  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v59[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v59[1] = si128;
  LOWORD(v59[0]) = 0;
  LOBYTE(a3) = 1;
  LPA::EnterpriseManager::AssembleProfilesRegKey(a1, a2, a3, v59);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &hKey);
  v11 = v8;
  if ( v8 > 0 )
    v11 = (unsigned __int16)v8 | 0x80070000;
  if ( v11 >= 0 )
  {
    v12 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    v11 = v12;
    v44 = v12;
    if ( v12 > 0 )
    {
      v11 = (unsigned __int16)v12 | 0x80070000;
      v44 = v11;
    }
    if ( v11 >= 0 )
    {
      v13 = 0;
      if ( cSubKeys )
      {
        do
        {
          *(_OWORD *)v61 = 0;
          memset(v62, 0, sizeof(v62));
          cchName = cbMaxSubKeyLen + 1;
          v55[0] = 0;
          v55[1] = si128;
          LOWORD(v55[0]) = 0;
          std::wstring::resize(v55, cbMaxSubKeyLen + 1, 0);
          v14 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v55);
          v15 = RegEnumKeyExW(hKey, v13, v14, &cchName, 0, 0, 0, 0);
          v17 = v15 < 0;
          if ( v15 > 0 )
          {
            v15 = (unsigned __int16)v15 | 0x80070000;
            v17 = v15 < 0;
          }
          if ( !v17 )
          {
            v18 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v55);
            v15 = StringCchCopyW(v61, 0x15u, v18);
          }
          if ( v15 >= 0 )
          {
            v54[0] = 0;
            v54[1] = si128;
            LOWORD(v54[0]) = 0;
            v58[0] = 0;
            v58[1] = si128;
            LOWORD(v58[0]) = 0;
            v57[0] = 0;
            v57[1] = si128;
            LOWORD(v57[0]) = 0;
            *(_DWORD *)Data = 0;
            v56[0] = 0;
            v56[1] = si128;
            LOWORD(v56[0]) = 0;
            *(_DWORD *)v42 = 0;
            LOBYTE(v16) = 1;
            LPA::EnterpriseManager::AssembleProfileRegKey(a1, (_DWORD)a2, (unsigned int)v61, v16, (__int64)v54);
            v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
            StringFromRegistry = CommonUtil::GetStringFromRegistry(v19, L"ServerName");
            if ( StringFromRegistry < 0 )
              goto LABEL_23;
            v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
            StringFromRegistry = CommonUtil::GetStringFromRegistry(v23, L"MatchingId");
            if ( StringFromRegistry < 0
              || (v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54),
                  StringFromRegistry = CommonUtil::GetDwordFromRegistry(v24, L"Enable", Data, v25),
                  StringFromRegistry < 0)
              || (v26 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54),
                  StringFromRegistry = CommonUtil::GetStringFromRegistry(v26, L"AccountId"),
                  StringFromRegistry < 0)
              || (v27 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54),
                  StringFromRegistry = CommonUtil::GetDwordFromRegistry(v27, L"RetriesLeft", v42, v28),
                  StringFromRegistry < 0) )
            {
LABEL_23:
              if ( (unsigned int)CallbackContext > 3 )
              {
                v37 = cchName;
                v39 = v13;
                LODWORD(v45) = StringFromRegistry;
                v48 = "LPA::EnterpriseManager::LoadStagedProfileDetailsFromRegistry";
                v47 = "LpaServiceEnterpriseManager";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  StringFromRegistry,
                  (unsigned int)&word_18012B7DE,
                  v21,
                  v22,
                  (__int64)&v47,
                  (__int64)&v48,
                  (__int64)&v45,
                  (__int64)&v39,
                  (__int64)&v37);
              }
            }
            else
            {
              v35 = 1;
              v39 = 0;
              v37 = 0;
              v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56);
              v36 = *(_DWORD *)Data != 0;
              v50 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v57);
              v47 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
              v29 = wcsncmp_0(a2, L"Default", 0x21u);
              v30 = 0;
              if ( v29 )
                v30 = (const char *)a2;
              v48 = v30;
              v31 = std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(a1 + 24, v51);
              std::make_unique<LPA::EnterpriseManager::StagedProfileDetails,std::shared_ptr<LPA::EnterpriseManager>,unsigned short const (* &)[33],unsigned short const * &,unsigned short const * &,bool &,unsigned short const * &,unsigned long &,int,int,bool &,0>(
                (unsigned int)&v49,
                v31,
                (unsigned int)&v48,
                (unsigned int)&v47,
                (__int64)&v50,
                (__int64)&v36,
                (__int64)&v45,
                (__int64)v42,
                (__int64)&v37,
                (__int64)&v39,
                (__int64)&v35);
              if ( v52 )
                std::_Ref_count_base::_Decref(v52);
              v32 = *v3;
              std::wstring::wstring(v60, v61);
              v33 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring,>(
                      v32,
                      v53,
                      v60);
              std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>::operator=<std::default_delete<LPA::EnterpriseManager::StagedProfileDetails>,0>(
                (__int64 *)(*(_QWORD *)v33 + 64LL),
                &v49);
              std::wstring::_Tidy_deallocate(v60);
              std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>::~unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>(&v49);
            }
            std::wstring::_Tidy_deallocate(v56);
            std::wstring::_Tidy_deallocate(v57);
            std::wstring::_Tidy_deallocate(v58);
            std::wstring::_Tidy_deallocate(v54);
          }
          std::wstring::_Tidy_deallocate(v55);
          ++v13;
        }
        while ( v13 < cSubKeys );
        v11 = v44;
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147024894 && (unsigned int)CallbackContext > 3 )
  {
    LODWORD(v45) = cSubKeys;
    v37 = v11;
    v48 = "LPA::EnterpriseManager::LoadStagedProfileDetailsFromRegistry";
    v47 = "LpaServiceEnterpriseManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      0x80000000,
      (unsigned int)byte_18012B799,
      v9,
      v10,
      (__int64)&v47,
      (__int64)&v48,
      (__int64)&v37,
      (__int64)&v45);
  }
  std::wstring::_Tidy_deallocate(v59);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18007c678  mov     rax, rsp
0x18007c67b  mov     [rax+20h], rbx
0x18007c67f  push    rbp
0x18007c680  push    rsi
0x18007c681  push    rdi
0x18007c682  push    r12
0x18007c684  push    r13
0x18007c686  push    r14
0x18007c688  push    r15
0x18007c68a  lea     rbp, [rax-138h]
0x18007c691  sub     rsp, 200h
0x18007c698  movaps  xmmword ptr [rax-48h], xmm6
0x18007c69c  mov     rax, cs:__security_cookie
0x18007c6a3  xor     rax, rsp
0x18007c6a6  mov     [rbp+130h+var_48], rax
0x18007c6ad  mov     r12, r8
0x18007c6b0  mov     r14, rdx
0x18007c6b3  mov     r15, rcx
0x18007c6b6  xor     r13d, r13d
0x18007c6b9  mov     [rbp+130h+hKey], r13
0x18007c6bd  mov     [rsp+230h+cSubKeys], r13d
0x18007c6c2  mov     [rsp+230h+cbMaxSubKeyLen], r13d
0x18007c6c7  xorps   xmm0, xmm0
0x18007c6ca  movups  [rbp+130h+var_B8], xmm0
0x18007c6ce  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18007c6d6  movdqu  [rbp+130h+var_A8], xmm6
0x18007c6de  mov     word ptr [rbp+130h+var_B8], r13w
0x18007c6e3  lea     r9, [rbp+130h+var_B8]
0x18007c6e7  mov     r8b, 1
0x18007c6ea  call    ?AssembleProfilesRegKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBG_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::AssembleProfilesRegKey(ushort const (&)[33],bool,std::wstring &)
0x18007c6ef  lea     rcx, [rbp+130h+var_B8]
0x18007c6f3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c6f8  mov     rdx, rax; lpSubKey
0x18007c6fb  lea     rax, [rbp+130h+hKey]
0x18007c6ff  mov     [rsp+230h+phkResult], rax; phkResult
0x18007c704  mov     r9d, 20019h; samDesired
0x18007c70a  xor     r8d, r8d; ulOptions
0x18007c70d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007c714  call    cs:__imp_RegOpenKeyExW
0x18007c71a  mov     edi, eax
0x18007c71c  mov     ebx, 80070000h
0x18007c721  test    eax, eax
0x18007c723  jle     short loc_18007C72A
0x18007c725  movzx   edi, ax
0x18007c728  or      edi, ebx
0x18007c72a  lea     rsi, aLpaEnterprisem_0; "LPA::EnterpriseManager::LoadStagedProfi"...
0x18007c731  test    edi, edi
0x18007c733  js      loc_18007CB4B
0x18007c739  mov     [rsp+230h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18007c73e  mov     [rsp+230h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18007c743  mov     [rsp+230h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18007c748  mov     [rsp+230h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18007c74d  mov     [rsp+230h+lpcValues], r13; lpcValues
0x18007c752  mov     [rsp+230h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18007c757  lea     rax, [rsp+230h+cbMaxSubKeyLen]
0x18007c75c  mov     [rsp+230h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18007c761  lea     rax, [rsp+230h+cSubKeys]
0x18007c766  mov     [rsp+230h+phkResult], rax; lpcSubKeys
0x18007c76b  xor     r9d, r9d; lpReserved
0x18007c76e  xor     r8d, r8d; lpcchClass
0x18007c771  xor     edx, edx; lpClass
0x18007c773  mov     rcx, [rbp+130h+hKey]; hKey
0x18007c777  call    cs:__imp_RegQueryInfoKeyW
0x18007c77d  mov     edi, eax
0x18007c77f  mov     [rbp+130h+var_1B0], eax
0x18007c782  test    eax, eax
0x18007c784  jle     short loc_18007C78E
0x18007c786  movzx   edi, ax
0x18007c789  or      edi, ebx
0x18007c78b  mov     [rbp+130h+var_1B0], edi
0x18007c78e  test    edi, edi
0x18007c790  js      loc_18007CB4B
0x18007c796  mov     esi, r13d
0x18007c799  cmp     [rsp+230h+cSubKeys], r13d
0x18007c79e  jbe     loc_18007CB44
0x18007c7a4  lea     rdi, aLpaEnterprisem_0; "LPA::EnterpriseManager::LoadStagedProfi"...
0x18007c7ab  xorps   xmm0, xmm0
0x18007c7ae  movups  xmmword ptr [rbp+130h+var_78], xmm0
0x18007c7b5  movups  xmmword ptr [rbp+130h+var_68], xmm0
0x18007c7bc  movups  xmmword ptr [rbp+130h+var_68+0Ah], xmm0
0x18007c7c3  mov     ecx, [rsp+230h+cbMaxSubKeyLen]
0x18007c7c7  inc     ecx
0x18007c7c9  mov     [rsp+230h+cchName], ecx
0x18007c7cd  movups  [rbp+130h+var_138], xmm0
0x18007c7d1  movdqu  [rbp+130h+var_128], xmm6
0x18007c7d6  mov     word ptr [rbp+130h+var_138], r13w
0x18007c7db  xor     r8d, r8d
0x18007c7de  mov     edx, ecx
0x18007c7e0  lea     rcx, [rbp+130h+var_138]
0x18007c7e4  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18007c7e9  lea     rcx, [rbp+130h+var_138]
0x18007c7ed  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c7f2  mov     r8, rax; lpName
0x18007c7f5  mov     [rsp+230h+lpcValues], r13; lpftLastWriteTime
0x18007c7fa  mov     [rsp+230h+lpcbMaxClassLen], r13; lpcchClass
0x18007c7ff  mov     [rsp+230h+lpcbMaxSubKeyLen], r13; lpClass
0x18007c804  mov     [rsp+230h+phkResult], r13; lpReserved
0x18007c809  lea     r9, [rsp+230h+cchName]; lpcchName
0x18007c80e  mov     edx, esi; dwIndex
0x18007c810  mov     rcx, [rbp+130h+hKey]; hKey
0x18007c814  call    cs:__imp_RegEnumKeyExW
0x18007c81a  test    eax, eax
0x18007c81c  jle     short loc_18007C825
0x18007c81e  movzx   eax, ax
0x18007c821  or      eax, ebx
0x18007c823  test    eax, eax
0x18007c825  js      short loc_18007C844
0x18007c827  lea     rcx, [rbp+130h+var_138]
0x18007c82b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c830  mov     r8, rax; unsigned __int16 *
0x18007c833  mov     edx, 15h; unsigned __int64
0x18007c838  lea     rcx, [rbp+130h+var_78]; unsigned __int16 *
0x18007c83f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007c844  test    eax, eax
0x18007c846  js      loc_18007CB2C
0x18007c84c  xorps   xmm0, xmm0
0x18007c84f  movups  [rbp+130h+var_158], xmm0
0x18007c853  movdqu  [rbp+130h+var_148], xmm6
0x18007c858  mov     word ptr [rbp+130h+var_158], r13w
0x18007c85d  movups  [rbp+130h+var_D8], xmm0
0x18007c861  movdqu  [rbp+130h+var_C8], xmm6
0x18007c866  mov     word ptr [rbp+130h+var_D8], r13w
0x18007c86b  movups  [rbp+130h+var_F8], xmm0
0x18007c86f  movdqu  [rbp+130h+var_E8], xmm6
0x18007c874  mov     word ptr [rbp+130h+var_F8], r13w
0x18007c879  mov     dword ptr [rsp+230h+Data], r13d
0x18007c87e  movups  [rbp+130h+var_118], xmm0
0x18007c882  movdqu  [rbp+130h+var_108], xmm6
0x18007c887  mov     word ptr [rbp+130h+var_118], r13w
0x18007c88c  mov     dword ptr [rsp+230h+var_1B8], r13d
0x18007c891  lea     rax, [rbp+130h+var_158]
0x18007c895  mov     [rsp+230h+phkResult], rax
0x18007c89a  mov     r9b, 1
0x18007c89d  lea     r8, [rbp+130h+var_78]
0x18007c8a4  mov     rdx, r14
0x18007c8a7  mov     rcx, r15
0x18007c8aa  call    ?AssembleProfileRegKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBGAEAY0BF@$$CBG_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::AssembleProfileRegKey(ushort const (&)[33],ushort const (&)[21],bool,std::wstring &)
0x18007c8af  lea     rcx, [rbp+130h+var_158]
0x18007c8b3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c8b8  mov     rcx, rax; lpSubKey
0x18007c8bb  lea     r8, [rbp+130h+var_D8]
0x18007c8bf  lea     rdx, aServername; "ServerName"
0x18007c8c6  call    ?GetStringFromRegistry@CommonUtil@@YAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommonUtil::GetStringFromRegistry(ushort const *,ushort const *,std::wstring &)
0x18007c8cb  mov     ecx, eax
0x18007c8cd  test    eax, eax
0x18007c8cf  js      loc_18007CA9F
0x18007c8d5  lea     rcx, [rbp+130h+var_158]
0x18007c8d9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c8de  mov     rcx, rax; lpSubKey
0x18007c8e1  lea     r8, [rbp+130h+var_F8]
0x18007c8e5  lea     rdx, aMatchingid_0; "MatchingId"
0x18007c8ec  call    ?GetStringFromRegistry@CommonUtil@@YAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommonUtil::GetStringFromRegistry(ushort const *,ushort const *,std::wstring &)
0x18007c8f1  mov     ecx, eax
0x18007c8f3  test    eax, eax
0x18007c8f5  js      loc_18007CA9F
0x18007c8fb  lea     rcx, [rbp+130h+var_158]
0x18007c8ff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c904  mov     rcx, rax; lpSubKey
0x18007c907  lea     r8, [rsp+230h+Data]; lpData
0x18007c90c  lea     rdx, aEnable; "Enable"
0x18007c913  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007c918  mov     ecx, eax
0x18007c91a  test    eax, eax
0x18007c91c  js      loc_18007CA9F
0x18007c922  lea     rcx, [rbp+130h+var_158]
0x18007c926  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c92b  mov     rcx, rax; lpSubKey
0x18007c92e  lea     r8, [rbp+130h+var_118]
0x18007c932  lea     rdx, aAccountid; "AccountId"
0x18007c939  call    ?GetStringFromRegistry@CommonUtil@@YAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommonUtil::GetStringFromRegistry(ushort const *,ushort const *,std::wstring &)
0x18007c93e  mov     ecx, eax
0x18007c940  test    eax, eax
0x18007c942  js      loc_18007CA9F
0x18007c948  lea     rcx, [rbp+130h+var_158]
0x18007c94c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c951  mov     rcx, rax; lpSubKey
0x18007c954  lea     r8, [rsp+230h+var_1B8]; lpData
0x18007c959  lea     rdx, aRetriesleft; "RetriesLeft"
0x18007c960  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007c965  mov     ecx, eax
0x18007c967  test    eax, eax
0x18007c969  js      loc_18007CA9F
0x18007c96f  mov     byte ptr [rsp+230h+var_1D0], 1
0x18007c974  mov     [rsp+230h+var_1C4], r13d
0x18007c979  mov     [rsp+230h+var_1CC], r13d
0x18007c97e  lea     rcx, [rbp+130h+var_118]
0x18007c982  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c987  mov     [rbp+130h+var_1A8], rax
0x18007c98b  cmp     dword ptr [rsp+230h+Data], r13d
0x18007c990  setnz   byte ptr [rsp+230h+var_1D0+1]
0x18007c995  lea     rcx, [rbp+130h+var_F8]
0x18007c999  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c99e  mov     [rbp+130h+var_180], rax
0x18007c9a2  lea     rcx, [rbp+130h+var_D8]
0x18007c9a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007c9ab  mov     [rbp+130h+var_198], rax
0x18007c9af  mov     r8d, 21h ; '!'; MaxCount
0x18007c9b5  lea     rdx, aDefault; "Default"
0x18007c9bc  mov     rcx, r14; String1
0x18007c9bf  call    wcsncmp_0
0x18007c9c4  mov     rcx, r13
0x18007c9c7  test    eax, eax
0x18007c9c9  cmovnz  rcx, r14
0x18007c9cd  mov     [rbp+130h+var_190], rcx
0x18007c9d1  lea     rcx, [r15+18h]
0x18007c9d5  lea     rdx, [rbp+130h+var_178]
0x18007c9d9  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x18007c9de  nop
0x18007c9df  lea     rcx, [rsp+230h+var_1D0]
0x18007c9e4  mov     [rsp+230h+lpcbSecurityDescriptor], rcx
0x18007c9e9  lea     rcx, [rsp+230h+var_1C4]
0x18007c9ee  mov     [rsp+230h+lpcbMaxValueLen], rcx
0x18007c9f3  lea     rcx, [rsp+230h+var_1CC]
0x18007c9f8  mov     [rsp+230h+lpcbMaxValueNameLen], rcx
0x18007c9fd  lea     rcx, [rsp+230h+var_1B8]
0x18007ca02  mov     [rsp+230h+lpcValues], rcx
0x18007ca07  lea     rcx, [rbp+130h+var_1A8]
0x18007ca0b  mov     [rsp+230h+lpcbMaxClassLen], rcx
0x18007ca10  lea     rcx, [rsp+230h+var_1D0+1]
0x18007ca15  mov     [rsp+230h+lpcbMaxSubKeyLen], rcx
0x18007ca1a  lea     rcx, [rbp+130h+var_180]
0x18007ca1e  mov     [rsp+230h+phkResult], rcx
0x18007ca23  lea     r9, [rbp+130h+var_198]
0x18007ca27  lea     r8, [rbp+130h+var_190]
0x18007ca2b  mov     rdx, rax
0x18007ca2e  lea     rcx, [rbp+130h+var_188]
0x18007ca32  call    ??$make_unique@VStagedProfileDetails@EnterpriseManager@LPA@@V?$shared_ptr@VEnterpriseManager@LPA@@@std@@AEAPEAY0CB@$$CBGAEAPEBGAEAPEBGAEA_NAEAPEBGAEAKHHAEA_N$0A@@std@@YA?AV?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@0@$$QEAV?$shared_ptr@VEnterpriseManager@LPA@@@0@AEAPEAY0CB@$$CBGAEAPEBG2AEA_N2AEAK$$QEAH53@Z; std::make_unique<LPA::EnterpriseManager::StagedProfileDetails,std::shared_ptr<LPA::EnterpriseManager>,ushort const (* &)[33],ushort const * &,ushort const * &,bool &,ushort const * &,ulong &,int,int,bool &,0>(std::shared_ptr<LPA::EnterpriseManager> &&,ushort const (* &)[33],ushort const * &,ushort const * &,bool &,ushort const * &,ulong &,int &&,int &&,bool &)
0x18007ca37  nop
0x18007ca38  mov     rcx, [rbp+130h+var_170]; this
0x18007ca3c  test    rcx, rcx
0x18007ca3f  jz      short loc_18007CA46
0x18007ca41  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007ca46  mov     rbx, [r12]
0x18007ca4a  lea     rdx, [rbp+130h+var_78]
0x18007ca51  lea     rcx, [rbp+130h+var_98]
0x18007ca58  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007ca5d  nop
0x18007ca5e  lea     r8, [rbp+130h+var_98]
0x18007ca65  lea     rdx, [rbp+130h+var_168]
0x18007ca69  mov     rcx, rbx
0x18007ca6c  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007ca71  mov     rcx, [rax]
0x18007ca74  add     rcx, 40h ; '@'
0x18007ca78  lea     rdx, [rbp+130h+var_188]
0x18007ca7c  call    ??$?4U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@$0A@@?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>::operator=<std::default_delete<LPA::EnterpriseManager::StagedProfileDetails>,0>(std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails> &&)
0x18007ca81  nop
0x18007ca82  lea     rcx, [rbp+130h+var_98]
0x18007ca89  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007ca8e  nop
0x18007ca8f  lea     rcx, [rbp+130h+var_188]
0x18007ca93  call    ??1?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>::~unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>(void)
0x18007ca98  mov     ebx, 80070000h
0x18007ca9d  jmp     short loc_18007CB04
0x18007ca9f  mov     eax, cs:CallbackContext
0x18007caa5  cmp     eax, 3
0x18007caa8  jbe     short loc_18007CB04
0x18007caaa  mov     eax, [rsp+230h+cchName]
0x18007caae  mov     [rsp+230h+var_1CC], eax
0x18007cab2  mov     [rsp+230h+var_1C4], esi
0x18007cab6  mov     dword ptr [rbp+130h+var_1A8], ecx
0x18007cab9  mov     [rbp+130h+var_190], rdi
0x18007cabd  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007cac4  mov     [rbp+130h+var_198], rax
0x18007cac8  lea     rax, [rsp+230h+var_1CC]
0x18007cacd  mov     [rsp+230h+lpcbMaxValueNameLen], rax
0x18007cad2  lea     rax, [rsp+230h+var_1C4]
0x18007cad7  mov     [rsp+230h+lpcValues], rax
0x18007cadc  lea     rax, [rbp+130h+var_1A8]
0x18007cae0  mov     [rsp+230h+lpcbMaxClassLen], rax
0x18007cae5  lea     rax, [rbp+130h+var_190]
0x18007cae9  mov     [rsp+230h+lpcbMaxSubKeyLen], rax
0x18007caee  lea     rax, [rbp+130h+var_198]
0x18007caf2  mov     [rsp+230h+phkResult], rax
0x18007caf7  lea     rdx, word_18012B7DE
0x18007cafe  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007cb03  nop
0x18007cb04  lea     rcx, [rbp+130h+var_118]
0x18007cb08  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007cb0d  nop
0x18007cb0e  lea     rcx, [rbp+130h+var_F8]
0x18007cb12  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007cb17  nop
0x18007cb18  lea     rcx, [rbp+130h+var_D8]
0x18007cb1c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007cb21  nop
0x18007cb22  lea     rcx, [rbp+130h+var_158]
0x18007cb26  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007cb2b  nop
0x18007cb2c  lea     rcx, [rbp+130h+var_138]
0x18007cb30  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007cb35  inc     esi
0x18007cb37  cmp     esi, [rsp+230h+cSubKeys]
0x18007cb3b  jb      loc_18007C7AB
0x18007cb41  mov     edi, [rbp+130h+var_1B0]
0x18007cb44  lea     rsi, aLpaEnterprisem_0; "LPA::EnterpriseManager::LoadStagedProfi"...
0x18007cb4b  mov     rcx, [rbp+130h+hKey]; hKey
0x18007cb4f  test    rcx, rcx
0x18007cb52  jz      short loc_18007CB5E
0x18007cb54  call    cs:__imp_RegCloseKey
0x18007cb5a  mov     [rbp+130h+hKey], r13
  ... truncated ...
```
