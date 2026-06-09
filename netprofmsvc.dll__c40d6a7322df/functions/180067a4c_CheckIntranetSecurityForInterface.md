# CheckIntranetSecurityForInterface

- ea: `0x180067a4c`
- end: `0x180067dbd`
- name: `CheckIntranetSecurityForInterface`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801176a8`

## callees

- `0x18001ec8c`
- `0x18002a7ec`
- `0x18002b250`
- `0x18002bd40`
- `0x18002ce40`
- `0x18002e4d4`
- `0x1800307cc`
- `0x18003b250`
- `0x18004068c`
- `0x180044b24`
- `0x18004e190`
- `0x180067a4c`
- `0x18006ac64`
- `0x180086588`
- `0x1800a88a0`
- `0x180108940`
- `0x1801162f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180067bbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180067bbf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180067b54`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180067b54`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180067d59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180067d59`

## string_xrefs

- `0x180067b69`: `onecore\net\netprofiles\service\src\signatures\lib\nlmsignatures.cpp`
- `0x180067bd4`: `onecore\net\netprofiles\service\src\signatures\lib\nlmsignatures.cpp`
- `0x180067d6e`: `onecore\net\netprofiles\service\src\signatures\lib\nlmsignatures.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CheckIntranetSecurityForInterface(char a1, _OWORD *a2, _DWORD *a3)
{
  __int64 *v6; // rdx
  const WCHAR *v7; // rdx
  unsigned int v8; // eax
  HKEY v9; // rcx
  unsigned int v10; // eax
  bool v11; // si
  bool IsDomainJoined; // al
  _OWORD *v13; // rax
  __int128 v14; // xmm1
  _OWORD *v15; // rax
  __int128 v16; // xmm1
  unsigned int v17; // eax
  const char *v18; // r9
  unsigned int dwOptions; // [rsp+20h] [rbp-E8h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E8h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E8h]
  char v22; // [rsp+50h] [rbp-B8h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp-9Ch] BYREF
  __int128 v27; // [rsp+70h] [rbp-98h] BYREF
  __int64 v28; // [rsp+80h] [rbp-88h]
  LPCWSTR lpSubKey[4]; // [rsp+90h] [rbp-78h] BYREF
  __m256i v30; // [rsp+B0h] [rbp-58h] BYREF
  GUID v31; // [rsp+D0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v6 = &qword_1801C7220;
  if ( (unsigned __int64)qword_1801C7238 > 7 )
    v6 = (__int64 *)qword_1801C7220;
  try
  {
    std::wstring::wstring(lpSubKey, v6);
    std::wstring::push_back(lpSubKey, 92);
    HexStringFromBytes<std::array<unsigned char,32>>(&v27, a2);
    std::wstring::_Append<wchar_t>(lpSubKey);
    std::pair<std::wstring,enum Marshal::UnmarshalError>::~pair<std::wstring,enum Marshal::UnmarshalError>(&v27);
    hKey = 0;
    dwDisposition = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v7 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v7 = lpSubKey[0];
    v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
    if ( v8 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\signatures\\lib\\nlmsignatures.cpp",
        (const char *)v8,
        dwOptions);
    v9 = hKey;
    if ( !hKey )
      goto LABEL_24;
    if ( dwDisposition == 2 )
    {
      *(_DWORD *)Data = 0;
      cbData = 4;
      v10 = RegQueryValueExW(hKey, 0, 0, 0, Data, &cbData);
      if ( v10 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x42,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\signatures\\lib\\nlmsignatures.cpp",
          (const char *)v10,
          dwOptionsa);
      if ( cbData == 4 )
      {
        v11 = *(_DWORD *)Data != 0;
        IsDomainJoined = NlmDomain::IsDomainJoined();
        if ( !a1 )
        {
          if ( v11 && IsDomainJoined )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding>::GetImpl'::`2'::impl) )
            {
              v27 = 0;
              v28 = 0;
              std::vector<unsigned char>::reserve(&v27, 48);
              std::vector<unsigned char>::insert<std::_Array_const_iterator<unsigned char,32>,0>(
                (unsigned int)&v27,
                (unsigned int)&v22,
                DWORD2(v27),
                (_DWORD)a2,
                (__int64)(a2 + 2));
              ApplySecurityDowngrade(a3, &v27);
              v15 = (_OWORD *)Sha256Hash::ValueFromBytes(&v30, v27, *((_QWORD *)&v27 + 1) - v27);
              v16 = v15[1];
              *a2 = *v15;
              a2[1] = v16;
              std::vector<unsigned char>::_Tidy(&v27);
            }
            else
            {
              memset(&v30, 0, sizeof(v30));
              v30 = *(__m256i *)a2;
              v31 = GUID_NLA_Downgrade;
              v13 = (_OWORD *)Sha256Hash::ValueFromBytes(&v27, &v30, 48);
              v14 = v13[1];
              *a2 = *v13;
              a2[1] = v14;
              *a3 |= 0x10000u;
            }
          }
          goto LABEL_24;
        }
        v9 = hKey;
        goto LABEL_22;
      }
      v9 = hKey;
    }
    if ( !a1 )
    {
LABEL_24:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::pair<std::wstring,enum Marshal::UnmarshalError>::~pair<std::wstring,enum Marshal::UnmarshalError>(lpSubKey);
      return;
    }
LABEL_22:
    *(_DWORD *)Data = 1;
    v17 = RegSetValueExW(v9, 0, 0, 3u, Data, 4u);
    if ( v17 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\signatures\\lib\\nlmsignatures.cpp",
        (const char *)v17,
        dwOptionsb);
    goto LABEL_24;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\signatures\\lib\\nlmsignatures.cpp",
      v18);
  }
}

```

## disassembly

```asm
0x180067a4c  mov     r11, rsp
0x180067a4f  mov     [r11+8], rbx
0x180067a53  push    rsi
0x180067a54  push    rdi
0x180067a55  push    r14
0x180067a57  sub     rsp, 0F0h
0x180067a5e  mov     rax, cs:__security_cookie
0x180067a65  xor     rax, rsp
0x180067a68  mov     [rsp+108h+var_28], rax
0x180067a70  mov     rdi, r8
0x180067a73  mov     rbx, rdx
0x180067a76  mov     r14b, cl
0x180067a79  lea     rdx, qword_1801C7220
0x180067a80  cmp     cs:qword_1801C7238, 7
0x180067a88  cmova   rdx, cs:qword_1801C7220
0x180067a90  lea     rcx, [r11-78h]
0x180067a94  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180067a99  nop
0x180067a9a  mov     edx, 5Ch ; '\'
0x180067a9f  lea     rcx, [rsp+108h+lpSubKey]
0x180067aa7  call    ?push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z; std::wstring::push_back(wchar_t)
0x180067aac  mov     rdx, rbx
0x180067aaf  lea     rcx, [rsp+108h+var_98]
0x180067ab4  call    ??$HexStringFromBytes@V?$array@E$0CA@@std@@@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$array@E$0CA@@1@@Z; HexStringFromBytes<std::array<uchar,32>>(std::array<uchar,32> const &)
0x180067ab9  nop
0x180067aba  mov     r8, [rax+10h]
0x180067abe  cmp     qword ptr [rax+18h], 7
0x180067ac3  jbe     short loc_180067AC8
0x180067ac5  mov     rax, [rax]
0x180067ac8  mov     rdx, rax
0x180067acb  lea     rcx, [rsp+108h+lpSubKey]; Src
0x180067ad3  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180067ad8  nop
0x180067ad9  lea     rcx, [rsp+108h+var_98]; void *
0x180067ade  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4UnmarshalError@Marshal@@@std@@QEAA@XZ; std::pair<std::wstring,Marshal::UnmarshalError>::~pair<std::wstring,Marshal::UnmarshalError>(void)
0x180067ae3  mov     [rsp+108h+hKey], 0
0x180067aec  mov     [rsp+108h+dwDisposition], 0
0x180067af4  xor     edx, edx
0x180067af6  lea     rcx, [rsp+108h+hKey]
0x180067afb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180067b00  lea     rdx, [rsp+108h+lpSubKey]
0x180067b08  cmp     [rsp+108h+var_60], 7
0x180067b11  cmova   rdx, [rsp+108h+lpSubKey]; lpSubKey
0x180067b1a  lea     rax, [rsp+108h+dwDisposition]
0x180067b1f  mov     [rsp+108h+lpdwDisposition], rax; lpdwDisposition
0x180067b24  lea     rax, [rsp+108h+hKey]
0x180067b29  mov     [rsp+108h+phkResult], rax; phkResult
0x180067b2e  mov     [rsp+108h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180067b37  mov     [rsp+108h+samDesired], 2001Fh; samDesired
0x180067b3f  mov     [rsp+108h+dwOptions], 0; unsigned int
0x180067b47  xor     r9d, r9d; lpClass
0x180067b4a  xor     r8d, r8d; Reserved
0x180067b4d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180067b54  call    cs:__imp_RegCreateKeyExW
0x180067b5a  mov     rcx, [rsp+108h]; this
0x180067b62  test    eax, eax
0x180067b64  jz      short loc_180067B7A
0x180067b66  mov     r9d, eax; char *
0x180067b69  lea     r8, aOnecoreNetNetp_26; "onecore\\net\\netprofiles\\service\\src"...
0x180067b70  mov     edx, 3Ah ; ':'; void *
0x180067b75  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180067b7a  mov     rcx, [rsp+108h+hKey]; hKey
0x180067b7f  test    rcx, rcx
0x180067b82  jz      loc_180067D80
0x180067b88  cmp     [rsp+108h+dwDisposition], 2
0x180067b8d  jnz     loc_180067D2F
0x180067b93  mov     dword ptr [rsp+108h+Data], 0
0x180067b9b  mov     [rsp+108h+cbData], 4
0x180067ba3  lea     rax, [rsp+108h+cbData]
0x180067ba8  mov     qword ptr [rsp+108h+samDesired], rax; lpcbData
0x180067bad  lea     rax, [rsp+108h+Data]
0x180067bb2  mov     qword ptr [rsp+108h+dwOptions], rax; unsigned int
0x180067bb7  xor     r9d, r9d; lpType
0x180067bba  xor     r8d, r8d; lpReserved
0x180067bbd  xor     edx, edx; lpValueName
0x180067bbf  call    cs:__imp_RegQueryValueExW
0x180067bc5  mov     rcx, [rsp+108h]; this
0x180067bcd  test    eax, eax
0x180067bcf  jz      short loc_180067BE5
0x180067bd1  mov     r9d, eax; char *
0x180067bd4  lea     r8, aOnecoreNetNetp_26; "onecore\\net\\netprofiles\\service\\src"...
0x180067bdb  mov     edx, 42h ; 'B'; void *
0x180067be0  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180067be5  cmp     [rsp+108h+cbData], 4
0x180067bea  jnz     loc_180067D2A
0x180067bf0  cmp     dword ptr [rsp+108h+Data], 0
0x180067bf5  setnz   sil
0x180067bf9  call    ?IsDomainJoined@NlmDomain@@SA_NXZ; NlmDomain::IsDomainJoined(void)
0x180067bfe  test    r14b, r14b
0x180067c01  jnz     loc_180067D23
0x180067c07  test    sil, sil
0x180067c0a  jz      loc_180067D80
0x180067c10  test    al, al
0x180067c12  jz      loc_180067D80
0x180067c18  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding>::GetImpl(void)'::`2'::impl
0x180067c1f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding>::__private_IsEnabled(void)
0x180067c24  test    al, al
0x180067c26  jnz     short loc_180067CA2
0x180067c28  mov     qword ptr [rsp+108h+var_58], 0
0x180067c34  xorps   xmm0, xmm0
0x180067c37  movdqu  [rsp+108h+var_58+8], xmm0
0x180067c40  mov     [rsp+108h+var_40], 0
0x180067c4c  movups  xmm0, xmmword ptr [rbx]
0x180067c4f  movups  [rsp+108h+var_58], xmm0
0x180067c57  movups  xmm1, xmmword ptr [rbx+10h]
0x180067c5b  movups  xmmword ptr [rsp+0C0h], xmm1
0x180067c63  movups  xmm0, xmmword ptr cs:GUID_NLA_Downgrade.Data1
0x180067c6a  movdqu  [rsp+108h+var_38], xmm0
0x180067c73  mov     r8d, 30h ; '0'
0x180067c79  lea     rdx, [rsp+108h+var_58]
0x180067c81  lea     rcx, [rsp+108h+var_98]
0x180067c86  call    ?ValueFromBytes@Sha256Hash@@CA?AV?$array@E$0CA@@std@@PEBX_K@Z; Sha256Hash::ValueFromBytes(void const *,unsigned __int64)
0x180067c8b  movups  xmm0, xmmword ptr [rax]
0x180067c8e  movups  xmm1, xmmword ptr [rax+10h]
0x180067c92  movups  xmmword ptr [rbx], xmm0
0x180067c95  movups  xmmword ptr [rbx+10h], xmm1
0x180067c99  bts     dword ptr [rdi], 10h
0x180067c9d  jmp     loc_180067D80
0x180067ca2  xor     eax, eax
0x180067ca4  xorps   xmm1, xmm1
0x180067ca7  movdqu  [rsp+108h+var_98], xmm1
0x180067cad  mov     [rsp+108h+var_88], rax
0x180067cb5  lea     edx, [rax+30h]
0x180067cb8  lea     rcx, [rsp+108h+var_98]
0x180067cbd  call    ?reserve@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::reserve(unsigned __int64)
0x180067cc2  lea     rax, [rbx+20h]
0x180067cc6  mov     qword ptr [rsp+108h+dwOptions], rax
0x180067ccb  mov     r9, rbx
0x180067cce  mov     r8, qword ptr [rsp+108h+var_98+8]
0x180067cd3  lea     rdx, [rsp+108h+var_B8]
0x180067cd8  lea     rcx, [rsp+108h+var_98]
0x180067cdd  call    ??$insert@V?$_Array_const_iterator@E$0CA@@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Array_const_iterator@E$0CA@@1@1@Z; std::vector<uchar>::insert<std::_Array_const_iterator<uchar,32>,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Array_const_iterator<uchar,32>,std::_Array_const_iterator<uchar,32>)
0x180067ce2  lea     rdx, [rsp+108h+var_98]
0x180067ce7  mov     rcx, rdi
0x180067cea  call    ApplySecurityDowngrade
0x180067cef  mov     rdx, qword ptr [rsp+108h+var_98]
0x180067cf4  mov     r8, qword ptr [rsp+108h+var_98+8]
0x180067cf9  sub     r8, rdx
0x180067cfc  lea     rcx, [rsp+108h+var_58]
0x180067d04  call    ?ValueFromBytes@Sha256Hash@@CA?AV?$array@E$0CA@@std@@PEBX_K@Z; Sha256Hash::ValueFromBytes(void const *,unsigned __int64)
0x180067d09  movups  xmm0, xmmword ptr [rax]
0x180067d0c  movups  xmm1, xmmword ptr [rax+10h]
0x180067d10  movups  xmmword ptr [rbx], xmm0
0x180067d13  movups  xmmword ptr [rbx+10h], xmm1
0x180067d17  lea     rcx, [rsp+108h+var_98]
0x180067d1c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180067d21  jmp     short loc_180067D80
0x180067d23  mov     rcx, [rsp+108h+hKey]
0x180067d28  jmp     short loc_180067D34
0x180067d2a  mov     rcx, [rsp+108h+hKey]; hKey
0x180067d2f  test    r14b, r14b
0x180067d32  jz      short loc_180067D80
0x180067d34  mov     dword ptr [rsp+108h+Data], 1
0x180067d3c  mov     [rsp+108h+samDesired], 4; cbData
0x180067d44  lea     rax, [rsp+108h+Data]
0x180067d49  mov     qword ptr [rsp+108h+dwOptions], rax; unsigned int
0x180067d4e  mov     r9d, 3; dwType
0x180067d54  xor     r8d, r8d; Reserved
0x180067d57  xor     edx, edx; lpValueName
0x180067d59  call    cs:__imp_RegSetValueExW
0x180067d5f  mov     rcx, [rsp+108h]; this
0x180067d67  test    eax, eax
0x180067d69  jz      short loc_180067D80
0x180067d6b  mov     r9d, eax; char *
0x180067d6e  lea     r8, aOnecoreNetNetp_26; "onecore\\net\\netprofiles\\service\\src"...
0x180067d75  mov     edx, 64h ; 'd'; void *
0x180067d7a  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180067d7f  nop
0x180067d80  lea     rcx, [rsp+108h+hKey]
0x180067d85  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180067d8a  nop
0x180067d8b  lea     rcx, [rsp+108h+lpSubKey]; void *
0x180067d93  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4UnmarshalError@Marshal@@@std@@QEAA@XZ; std::pair<std::wstring,Marshal::UnmarshalError>::~pair<std::wstring,Marshal::UnmarshalError>(void)
0x180067d98  nop
0x180067d99  mov     rcx, [rsp+108h+var_28]
0x180067da1  xor     rcx, rsp; StackCookie
0x180067da4  call    __security_check_cookie
0x180067da9  mov     rbx, [rsp+108h+arg_0]
0x180067db1  add     rsp, 0F0h
0x180067db8  pop     r14
0x180067dba  pop     rdi
0x180067dbb  pop     rsi
0x180067dbc  retn
```
