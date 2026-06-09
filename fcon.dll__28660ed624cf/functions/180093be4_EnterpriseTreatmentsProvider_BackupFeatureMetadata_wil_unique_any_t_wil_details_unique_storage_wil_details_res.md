# EnterpriseTreatmentsProvider::BackupFeatureMetadata(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,EnterprisePayload const &)

- ea: `0x180093be4`
- end: `0x180093fb1`
- name: `?BackupFeatureMetadata@EnterpriseTreatmentsProvider@@AEAAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUEnterprisePayload@@@Z`
- size: `973`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800938bc`

## callees

- `0x180003220`
- `0x180004c0b`
- `0x18000949c`
- `0x180015aac`
- `0x180016698`
- `0x180019704`
- `0x180019800`
- `0x180019890`
- `0x18001e820`
- `0x180027290`
- `0x18002b0c0`
- `0x18002bc18`
- `0x180034b64`
- `0x180035504`
- `0x18009297c`
- `0x180093be4`
- `0x180094f50`
- `0x180094f70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180093d92`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180093dc3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180093f02`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180093f5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180093d92`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180093dc3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180093f02`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180093f5e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180093c66`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180093d0b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180093c66`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180093d0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EnterpriseTreatmentsProvider::BackupFeatureMetadata(__int64 a1, HKEY *a2, __int64 a3, __int64 a4)
{
  LSTATUS v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int v10; // ebx
  const WCHAR *v11; // rax
  LSTATUS v12; // eax
  __int64 v13; // rcx
  const BYTE *v14; // rax
  const BYTE *v15; // rax
  const struct RTL_PROPERTY_BAG_ITEM *v16; // rsi
  const struct RTL_PROPERTY_BAG_ITEM *i; // rbx
  const WCHAR *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 j; // rcx
  _WORD *v22; // r15
  __int64 v23; // rdi
  __int64 v24; // r14
  __int64 v25; // rax
  const void *v26; // rdx
  const WCHAR *v27; // rax
  const BYTE *v28; // r8
  DWORD v29; // r9d
  __int64 v30; // rdx
  const WCHAR *v31; // rax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+68h] [rbp-98h]
  void *v39; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v40[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v41[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v42; // [rsp+D0h] [rbp-30h]
  BYTE Data[32]; // [rsp+E0h] [rbp-20h] BYREF
  int v44; // [rsp+100h] [rbp+0h]
  _BYTE v45[32]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0,
    a3);
  v7 = RegCreateKeyExW(*a2, L"Metadata", 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  v10 = v7;
  if ( v7 > 0 )
    v10 = (unsigned __int16)v7 | 0x80070000;
  if ( (v10 & 0x80000000) == 0 )
  {
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0,
      v9);
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
    v12 = RegCreateKeyExW(hKey, v11, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
    v10 = v12;
    if ( v12 > 0 )
      v10 = (unsigned __int16)v12 | 0x80070000;
    if ( (v10 & 0x80000000) == 0 )
    {
      if ( *(_BYTE *)(a4 + 12) )
      {
        v14 = (const BYTE *)std::optional<unsigned long>::value();
        RegSetValueExW(phkResult, L"ChangeTime", 0, 4u, v14, 4u);
      }
      if ( *(_BYTE *)(a4 + 20) )
      {
        v15 = (const BYTE *)std::optional<unsigned long>::value();
        RegSetValueExW(phkResult, L"ChangeTimeOverride", 0, 4u, v15, 4u);
      }
      v16 = *(const struct RTL_PROPERTY_BAG_ITEM **)(a4 + 32);
      for ( i = *(const struct RTL_PROPERTY_BAG_ITEM **)(a4 + 24);
            i != v16;
            i = (const struct RTL_PROPERTY_BAG_ITEM *)((char *)i + 72) )
      {
        RTL_PROPERTY_BAG_ITEM::RTL_PROPERTY_BAG_ITEM((RTL_PROPERTY_BAG_ITEM *)v41, i);
        v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
        if ( v44 == 1 )
        {
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                  v18,
                                  v42,
                                  L"ApplicableOSVersion",
                                  19) )
          {
            std::wstring::wstring(v45, Data);
            v19 = std::wstring::wstring(v40, v45);
            VersionUtils::SplitStringByDelimiter(&v37, v19, 59);
            v20 = 0;
            for ( j = v37; j != v38; j += 32 )
              v20 += 2LL * *(_QWORD *)(j + 16) + 2;
            std::vector<unsigned short>::vector<unsigned short>(&v39, (unsigned __int64)(v20 + 2) >> 1);
            v22 = v39;
            v23 = v37;
            v24 = v38;
            while ( v23 != v24 )
            {
              std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
              v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
              memmove_0(v22, v26, v25 + 2LL * *(_QWORD *)(v23 + 16) - (_QWORD)v26);
              v22 += *(_QWORD *)(v23 + 16) + 1;
              v23 += 32;
            }
            *v22 = 0;
            v27 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
            RegSetValueExW(phkResult, v27, 0, 7u, v28, v29);
            std::vector<unsigned short>::_Tidy(&v39);
            std::vector<std::wstring>::_Tidy(&v37);
            std::wstring::_Tidy_deallocate(v45, v30);
          }
          else
          {
            v31 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
            RegSetValueExW(phkResult, v31, 0, 1u, Data, 2u);
          }
        }
        else
        {
          RegSetValueExW(phkResult, v18, 0, 4u, Data, 4u);
        }
        std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v41);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      v10 = 0;
    }
    else
    {
      if ( (Microsoft_Windows_FeatureConfigurationEnableBits & 2) != 0 )
        McTemplateU0d_EventWriteTransfer(v13, ErrorWritingFeatureConfigsBackup, v10);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B7,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\enterprise\\enterprisetreatmentsprovider.cpp",
        (const char *)v10,
        dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
  }
  else
  {
    if ( (Microsoft_Windows_FeatureConfigurationEnableBits & 2) != 0 )
      McTemplateU0d_EventWriteTransfer(v8, ErrorWritingFeatureConfigsBackup, v10);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\enterprise\\enterprisetreatmentsprovider.cpp",
      (const char *)v10,
      dwOptions);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v10;
}

```

## disassembly

```asm
0x180093be4  push    rbp
0x180093be6  push    rbx
0x180093be7  push    rsi
0x180093be8  push    rdi
0x180093be9  push    r13
0x180093beb  push    r14
0x180093bed  push    r15
0x180093bef  lea     rbp, [rsp-40h]
0x180093bf4  sub     rsp, 140h
0x180093bfb  mov     rax, cs:__security_cookie
0x180093c02  xor     rax, rsp
0x180093c05  mov     [rbp+70h+var_40], rax
0x180093c09  mov     rdi, r9
0x180093c0c  mov     rsi, r8
0x180093c0f  mov     rbx, rdx
0x180093c12  mov     [rsp+170h+hKey], 0
0x180093c1b  xor     edx, edx
0x180093c1d  lea     rcx, [rsp+170h+hKey]
0x180093c22  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180093c27  mov     [rsp+170h+lpdwDisposition], 0; lpdwDisposition
0x180093c30  lea     rax, [rsp+170h+hKey]
0x180093c35  mov     [rsp+170h+phkResult], rax; phkResult
0x180093c3a  mov     [rsp+170h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180093c43  mov     r15d, 2001Fh
0x180093c49  mov     [rsp+170h+samDesired], r15d; samDesired
0x180093c4e  mov     [rsp+170h+dwOptions], 0; int
0x180093c56  xor     r9d, r9d; lpClass
0x180093c59  xor     r8d, r8d; Reserved
0x180093c5c  lea     rdx, aMetadata; "Metadata"
0x180093c63  mov     rcx, [rbx]; hKey
0x180093c66  call    cs:__imp_RegCreateKeyExW
0x180093c6c  mov     ebx, eax
0x180093c6e  mov     r14d, 80070000h
0x180093c74  test    eax, eax
0x180093c76  jle     short loc_180093C7E
0x180093c78  movzx   ebx, ax
0x180093c7b  or      ebx, r14d
0x180093c7e  test    ebx, ebx
0x180093c80  jns     short loc_180093CB7
0x180093c82  test    cs:Microsoft_Windows_FeatureConfigurationEnableBits, 2
0x180093c89  jz      short loc_180093C9A
0x180093c8b  mov     r8d, ebx
0x180093c8e  lea     rdx, ErrorWritingFeatureConfigsBackup
0x180093c95  call    McTemplateU0d_EventWriteTransfer
0x180093c9a  mov     rcx, [rbp+78h]; this
0x180093c9e  mov     r9d, ebx; char *
0x180093ca1  lea     r8, aOnecoreBaseFli_36; "onecore\\base\\flighting\\featuremanage"...
0x180093ca8  mov     edx, 1A3h; void *
0x180093cad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093cb2  jmp     loc_180093F87
0x180093cb7  mov     [rsp+170h+var_120], 0
0x180093cc0  xor     edx, edx
0x180093cc2  lea     rcx, [rsp+170h+var_120]
0x180093cc7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180093ccc  mov     rcx, rsi
0x180093ccf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180093cd4  mov     [rsp+170h+lpdwDisposition], 0; lpdwDisposition
0x180093cdd  lea     rcx, [rsp+170h+var_120]
0x180093ce2  mov     [rsp+170h+phkResult], rcx; phkResult
0x180093ce7  mov     [rsp+170h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180093cf0  mov     [rsp+170h+samDesired], r15d; samDesired
0x180093cf5  mov     [rsp+170h+dwOptions], 0; int
0x180093cfd  xor     r9d, r9d; lpClass
0x180093d00  xor     r8d, r8d; Reserved
0x180093d03  mov     rdx, rax; lpSubKey
0x180093d06  mov     rcx, [rsp+170h+hKey]; hKey
0x180093d0b  call    cs:__imp_RegCreateKeyExW
0x180093d11  mov     ebx, eax
0x180093d13  test    eax, eax
0x180093d15  jle     short loc_180093D1D
0x180093d17  movzx   ebx, ax
0x180093d1a  or      ebx, r14d
0x180093d1d  test    ebx, ebx
0x180093d1f  jns     short loc_180093D61
0x180093d21  test    cs:Microsoft_Windows_FeatureConfigurationEnableBits, 2
0x180093d28  jz      short loc_180093D39
0x180093d2a  mov     r8d, ebx
0x180093d2d  lea     rdx, ErrorWritingFeatureConfigsBackup
0x180093d34  call    McTemplateU0d_EventWriteTransfer
0x180093d39  mov     rcx, [rbp+78h]; this
0x180093d3d  mov     r9d, ebx; char *
0x180093d40  lea     r8, aOnecoreBaseFli_36; "onecore\\base\\flighting\\featuremanage"...
0x180093d47  mov     edx, 1B7h; void *
0x180093d4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093d51  nop
0x180093d52  lea     rcx, [rsp+170h+var_120]
0x180093d57  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180093d5c  jmp     loc_180093F87
0x180093d61  lea     rcx, [rdi+8]
0x180093d65  mov     r13d, 4
0x180093d6b  cmp     byte ptr [rcx+4], 0
0x180093d6f  jz      short loc_180093D98
0x180093d71  call    ?value@?$optional@K@std@@QEGBAAEBKXZ; std::optional<ulong>::value(void)
0x180093d76  mov     [rsp+170h+samDesired], r13d; cbData
0x180093d7b  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x180093d80  mov     r9d, r13d; dwType
0x180093d83  xor     r8d, r8d; Reserved
0x180093d86  lea     rdx, aChangetime; "ChangeTime"
0x180093d8d  mov     rcx, [rsp+170h+var_120]; hKey
0x180093d92  call    cs:__imp_RegSetValueExW
0x180093d98  lea     rcx, [rdi+10h]
0x180093d9c  cmp     byte ptr [rcx+4], 0
0x180093da0  jz      short loc_180093DC9
0x180093da2  call    ?value@?$optional@K@std@@QEGBAAEBKXZ; std::optional<ulong>::value(void)
0x180093da7  mov     [rsp+170h+samDesired], r13d; cbData
0x180093dac  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x180093db1  mov     r9d, r13d; dwType
0x180093db4  xor     r8d, r8d; Reserved
0x180093db7  lea     rdx, aChangetimeover; "ChangeTimeOverride"
0x180093dbe  mov     rcx, [rsp+170h+var_120]; hKey
0x180093dc3  call    cs:__imp_RegSetValueExW
0x180093dc9  mov     rsi, [rdi+20h]
0x180093dcd  mov     rbx, [rdi+18h]
0x180093dd1  jmp     loc_180093F72
0x180093dd6  mov     rdx, rbx; struct RTL_PROPERTY_BAG_ITEM *
0x180093dd9  lea     rcx, [rbp+70h+var_B0]; this
0x180093ddd  call    ??0RTL_PROPERTY_BAG_ITEM@@QEAA@AEBU0@@Z; RTL_PROPERTY_BAG_ITEM::RTL_PROPERTY_BAG_ITEM(RTL_PROPERTY_BAG_ITEM const &)
0x180093de2  nop
0x180093de3  lea     rcx, [rbp+70h+var_B0]
0x180093de7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180093dec  cmp     [rbp+70h+var_70], 1
0x180093df0  jnz     loc_180093F42
0x180093df6  mov     rcx, rax
0x180093df9  mov     r9d, 13h
0x180093dff  lea     r8, aApplicableosve; "ApplicableOSVersion"
0x180093e06  mov     rdx, [rbp+70h+var_A0]
0x180093e0a  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180093e0f  test    al, al
0x180093e11  jz      loc_180093F29
0x180093e17  lea     rdx, [rbp+70h+Data]
0x180093e1b  lea     rcx, [rbp+70h+var_60]
0x180093e1f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180093e24  nop
0x180093e25  lea     rdx, [rbp+70h+var_60]
0x180093e29  lea     rcx, [rbp+70h+var_D8]
0x180093e2d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180093e32  mov     r8d, 3Bh ; ';'
0x180093e38  mov     rdx, rax
0x180093e3b  lea     rcx, [rsp+170h+var_110]
0x180093e40  call    ?SplitStringByDelimiter@VersionUtils@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@G@Z; VersionUtils::SplitStringByDelimiter(std::wstring,ushort)
0x180093e45  nop
0x180093e46  xor     edx, edx
0x180093e48  mov     rcx, [rsp+170h+var_110]
0x180093e4d  jmp     short loc_180093E5F
0x180093e4f  mov     rax, [rcx+10h]
0x180093e53  lea     rdx, [rdx+rax*2]
0x180093e57  add     rdx, 2
0x180093e5b  add     rcx, 20h ; ' '
0x180093e5f  cmp     rcx, [rsp+170h+var_108]
0x180093e64  jnz     short loc_180093E4F
0x180093e66  add     rdx, 2
0x180093e6a  shr     rdx, 1
0x180093e6d  lea     rcx, [rsp+170h+var_F8]
0x180093e72  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180093e77  mov     r15, [rsp+170h+var_F8]
0x180093e7c  mov     rdi, [rsp+170h+var_110]
0x180093e81  mov     r14, [rsp+170h+var_108]
0x180093e86  jmp     short loc_180093EC1
0x180093e88  mov     rcx, rdi
0x180093e8b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180093e90  mov     rdx, rax
0x180093e93  mov     rcx, rdi
0x180093e96  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180093e9b  mov     rcx, [rdi+10h]
0x180093e9f  lea     r8, [rcx+rcx]
0x180093ea3  sub     r8, rdx
0x180093ea6  add     r8, rax; Size
0x180093ea9  mov     rcx, r15; void *
0x180093eac  call    memmove_0
0x180093eb1  mov     rax, [rdi+10h]
0x180093eb5  lea     r15, [r15+rax*2]
0x180093eb9  add     r15, 2
0x180093ebd  add     rdi, 20h ; ' '
0x180093ec1  cmp     rdi, r14
0x180093ec4  jnz     short loc_180093E88
0x180093ec6  xor     eax, eax
0x180093ec8  mov     [r15], ax
0x180093ecc  mov     r9, [rbp+70h+var_F0]
0x180093ed0  mov     r8, [rsp+170h+var_F8]
0x180093ed5  sub     r9, r8
0x180093ed8  sar     r9, 1
0x180093edb  add     r9d, r9d
0x180093ede  lea     rcx, [rbp+70h+var_B0]
0x180093ee2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180093ee7  mov     rdx, rax; lpValueName
0x180093eea  mov     [rsp+170h+samDesired], r9d; cbData
0x180093eef  mov     qword ptr [rsp+170h+dwOptions], r8; lpData
0x180093ef4  mov     r9d, 7; dwType
0x180093efa  xor     r8d, r8d; Reserved
0x180093efd  mov     rcx, [rsp+170h+var_120]; hKey
0x180093f02  call    cs:__imp_RegSetValueExW
0x180093f08  lea     rcx, [rsp+170h+var_F8]
0x180093f0d  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180093f12  nop
0x180093f13  lea     rcx, [rsp+170h+var_110]
0x180093f18  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180093f1d  nop
0x180093f1e  lea     rcx, [rbp+70h+var_60]
0x180093f22  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180093f27  jmp     short loc_180093F65
0x180093f29  lea     rcx, [rbp+70h+var_B0]
0x180093f2d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180093f32  mov     [rsp+170h+samDesired], 2
0x180093f3a  mov     r9d, 1
0x180093f40  jmp     short loc_180093F4A
0x180093f42  mov     [rsp+170h+samDesired], r13d; cbData
0x180093f47  mov     r9d, r13d; dwType
0x180093f4a  mov     rdx, rax; lpValueName
0x180093f4d  lea     rax, [rbp+70h+Data]
0x180093f51  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x180093f56  xor     r8d, r8d; Reserved
0x180093f59  mov     rcx, [rsp+170h+var_120]; hKey
0x180093f5e  call    cs:__imp_RegSetValueExW
0x180093f64  nop
0x180093f65  lea     rcx, [rbp+70h+var_B0]
0x180093f69  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x180093f6e  add     rbx, 48h ; 'H'
0x180093f72  cmp     rbx, rsi
0x180093f75  jnz     loc_180093DD6
0x180093f7b  lea     rcx, [rsp+170h+var_120]
0x180093f80  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180093f85  xor     ebx, ebx
0x180093f87  lea     rcx, [rsp+170h+hKey]
0x180093f8c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180093f91  mov     eax, ebx
0x180093f93  mov     rcx, [rbp+70h+var_40]
0x180093f97  xor     rcx, rsp; StackCookie
0x180093f9a  call    __security_check_cookie
0x180093f9f  add     rsp, 140h
0x180093fa6  pop     r15
0x180093fa8  pop     r14
0x180093faa  pop     r13
0x180093fac  pop     rdi
0x180093fad  pop     rsi
0x180093fae  pop     rbx
0x180093faf  pop     rbp
0x180093fb0  retn
```
