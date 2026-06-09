# EnterpriseTreatmentsProvider::BackupFeatureConfigs(void)

- ea: `0x1800938bc`
- end: `0x180093bdd`
- name: `?BackupFeatureConfigs@EnterpriseTreatmentsProvider@@AEAAJXZ`
- size: `801`
- prototype: `__int64 __fastcall(EnterpriseTreatmentsProvider *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800938b0`

## callees

- `0x180003220`
- `0x18000949c`
- `0x180016698`
- `0x180019704`
- `0x180019890`
- `0x18001e820`
- `0x180029090`
- `0x18005be88`
- `0x18005beb8`
- `0x180060f10`
- `0x180069ab4`
- `0x180069ad8`
- `0x180092aa8`
- `0x180092ae4`
- `0x180093454`
- `0x1800938bc`
- `0x180093be4`
- `0x1800949b0`
- `0x180094d8c`
- `0x180094f70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800938ef`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800938ef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180093abf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180093abf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180093946`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180093946`

## string_xrefs

- `0x1800938de`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Fcon\FeatureManagement\CommitedOverrides`
- `0x18009393c`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Fcon\FeatureManagement\CommitedOverrides`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EnterpriseTreatmentsProvider::BackupFeatureConfigs(EnterpriseTreatmentsProvider *this)
{
  __int64 v2; // r8
  LSTATUS v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // edi
  __int64 v6; // rcx
  __int64 v7; // rbx
  unsigned int v8; // edi
  _WORD *v9; // r9
  unsigned int v10; // r8d
  _WORD *v11; // r9
  const WCHAR *v12; // rax
  LSTATUS v13; // eax
  __int64 v14; // rdx
  void *v15; // rdx
  __int64 v16; // rcx
  unsigned int v17; // r8d
  _QWORD *v18; // rax
  __int64 v19; // rcx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v28[2]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v29[2]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v30[16]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v31[16]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v32[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v33[42]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v34[48]; // [rsp+102h] [rbp+2h] BYREF
  _BYTE v35[6]; // [rsp+132h] [rbp+32h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  RegDeleteTreeW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Fcon\\FeatureManagement\\CommitedOverrides");
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0,
    v2);
  v3 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Fcon\\FeatureManagement\\CommitedOverrides",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         0);
  v5 = v3;
  if ( v3 > 0 )
    v5 = (unsigned __int16)v3 | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
    EnterpriseTreatmentsProvider::GetTreatmentsForCommit(this, v30);
    BatchTreatments::GetTreatments(v30, v29);
    v6 = *(_QWORD *)v29[0];
    v27 = *(_QWORD *)v29[0];
    while ( !*(_BYTE *)(v6 + 25) )
    {
      Treatment::GetVariantConfigurations(v6 + 32, v28);
      v7 = *(_QWORD *)v28[0];
      v26 = *(_QWORD *)v28[0];
      while ( !*(_BYTE *)(v7 + 25) )
      {
        *(_DWORD *)Data = *(unsigned __int8 *)(v7 + 32);
        v8 = __ROR4__(_byteswap_ulong(*(_DWORD *)(v7 + 36) ^ 0x74161A4E) ^ 0x8FB23D4F, 255) ^ 0x833EA8FF;
        v9 = v34;
        v10 = v8;
        do
        {
          *--v9 = v10 % 0xA + 48;
          v10 /= 0xAu;
        }
        while ( v10 );
        std::wstring::wstring(v32, v9, v34);
        v11 = v35;
        do
        {
          *--v11 = v8 % 0xA + 48;
          v8 /= 0xAu;
        }
        while ( v8 );
        std::wstring::wstring(v33, v11, v35);
        v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
        v13 = RegSetValueExW(hKey, v12, 0, 4u, Data, 4u);
        v5 = v13;
        if ( v13 > 0 )
          v5 = (unsigned __int16)v13 | 0x80070000;
        std::wstring::_Tidy_deallocate(v33, v14);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata>::GetImpl'::`2'::impl)
          || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPVersionFilters>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_GPVersionFilters>::GetImpl'::`2'::impl) )
        {
          v23 = *(_DWORD *)(v7 + 36);
          v18 = (_QWORD *)std::map<int,EnterprisePayload>::_Try_emplace<int,>((char *)this + 8, v31, &v23);
          EnterpriseTreatmentsProvider::BackupFeatureMetadata(v19, &hKey, (__int64)v32, *v18 + 40LL);
        }
        if ( (v5 & 0x80000000) != 0 )
        {
          if ( (Microsoft_Windows_FeatureConfigurationEnableBits & 2) != 0 )
            McTemplateU0d_EventWriteTransfer(v16, ErrorWritingFeatureConfigsBackup, v5);
          wil::details::in1diag3::Log_Hr(retaddr, v15, v17, (const char *)v5, dwOptionsa);
        }
        std::wstring::_Tidy_deallocate(v32, v15);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WinFlagsFeature>>,std::_Iterator_base0>::operator++(&v26);
        v7 = v26;
      }
      std::_Tree_val<std::_Tree_simple_types<VariantConfiguration>>::_Erase_head<std::allocator<std::_Tree_node<VariantConfiguration,void *>>>(
        v28,
        v28);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WinFlagsFeature>>,std::_Iterator_base0>::operator++(&v27);
      v6 = v27;
    }
    std::_Tree_val<std::_Tree_simple_types<Treatment>>::_Erase_head<std::allocator<std::_Tree_node<Treatment,void *>>>(
      v29,
      v29);
    *((_BYTE *)this + 40) = (v5 & 0x80000000) == 0;
    std::_Tree_val<std::_Tree_simple_types<Treatment>>::_Erase_head<std::allocator<std::_Tree_node<Treatment,void *>>>(
      v30,
      v30);
  }
  else
  {
    if ( (Microsoft_Windows_FeatureConfigurationEnableBits & 2) != 0 )
      McTemplateU0d_EventWriteTransfer(v4, ErrorWritingFeatureConfigsBackup, v5);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22B,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\enterprise\\enterprisetreatmentsprovider.cpp",
      (const char *)v5,
      dwOptions);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v5;
}

```

## disassembly

```asm
0x1800938bc  push    rbp
0x1800938be  push    rbx
0x1800938bf  push    rsi
0x1800938c0  push    rdi
0x1800938c1  lea     rbp, [rsp-48h]
0x1800938c6  sub     rsp, 148h
0x1800938cd  mov     rax, cs:__security_cookie
0x1800938d4  xor     rax, rsp
0x1800938d7  mov     [rbp+60h+var_28], rax
0x1800938db  mov     rsi, rcx
0x1800938de  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800938e5  mov     rbx, 0FFFFFFFF80000002h
0x1800938ec  mov     rcx, rbx; hKey
0x1800938ef  call    cs:__imp_RegDeleteTreeW
0x1800938f5  mov     [rsp+160h+hKey], 0
0x1800938fe  xor     edx, edx
0x180093900  lea     rcx, [rsp+160h+hKey]
0x180093905  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009390a  mov     [rsp+160h+lpdwDisposition], 0; lpdwDisposition
0x180093913  lea     rax, [rsp+160h+hKey]
0x180093918  mov     [rsp+160h+phkResult], rax; phkResult
0x18009391d  mov     [rsp+160h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180093926  mov     [rsp+160h+samDesired], 2001Fh; samDesired
0x18009392e  mov     [rsp+160h+dwOptions], 0; int
0x180093936  xor     r9d, r9d; lpClass
0x180093939  xor     r8d, r8d; Reserved
0x18009393c  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180093943  mov     rcx, rbx; hKey
0x180093946  call    cs:__imp_RegCreateKeyExW
0x18009394c  mov     edi, eax
0x18009394e  test    eax, eax
0x180093950  jle     short loc_18009395B
0x180093952  movzx   edi, ax
0x180093955  or      edi, 80070000h
0x18009395b  test    edi, edi
0x18009395d  jns     short loc_180093994
0x18009395f  test    cs:Microsoft_Windows_FeatureConfigurationEnableBits, 2
0x180093966  jz      short loc_180093977
0x180093968  mov     r8d, edi
0x18009396b  lea     rdx, ErrorWritingFeatureConfigsBackup
0x180093972  call    McTemplateU0d_EventWriteTransfer
0x180093977  mov     rcx, [rbp+68h]; this
0x18009397b  mov     r9d, edi; char *
0x18009397e  lea     r8, aOnecoreBaseFli_36; "onecore\\base\\flighting\\featuremanage"...
0x180093985  mov     edx, 22Bh; void *
0x18009398a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009398f  jmp     loc_180093BB9
0x180093994  lea     rdx, [rbp+60h+var_C8]
0x180093998  mov     rcx, rsi
0x18009399b  call    ?GetTreatmentsForCommit@EnterpriseTreatmentsProvider@@UEAA?AVBatchTreatments@@XZ; EnterpriseTreatmentsProvider::GetTreatmentsForCommit(void)
0x1800939a0  nop
0x1800939a1  lea     rdx, [rbp+60h+var_D8]
0x1800939a5  lea     rcx, [rbp+60h+var_C8]
0x1800939a9  call    ?GetTreatments@BatchTreatments@@QEBA?AV?$set@VTreatment@@U?$less@VTreatment@@@std@@V?$allocator@VTreatment@@@3@@std@@XZ; BatchTreatments::GetTreatments(void)
0x1800939ae  nop
0x1800939af  mov     rcx, [rbp+60h+var_D8]
0x1800939b3  mov     rcx, [rcx]
0x1800939b6  mov     [rsp+160h+var_F0], rcx
0x1800939bb  cmp     byte ptr [rcx+19h], 0
0x1800939bf  jnz     loc_180093B94
0x1800939c5  add     rcx, 20h ; ' '
0x1800939c9  lea     rdx, [rsp+160h+var_E8]
0x1800939ce  call    ?GetVariantConfigurations@Treatment@@QEBA?AV?$set@VVariantConfiguration@@U?$less@VVariantConfiguration@@@std@@V?$allocator@VVariantConfiguration@@@3@@std@@XZ; Treatment::GetVariantConfigurations(void)
0x1800939d3  nop
0x1800939d4  mov     rbx, [rsp+160h+var_E8]
0x1800939d9  mov     rbx, [rbx]
0x1800939dc  mov     [rsp+160h+var_F8], rbx
0x1800939e1  cmp     byte ptr [rbx+19h], 0
0x1800939e5  jnz     loc_180093B71
0x1800939eb  movzx   eax, byte ptr [rbx+20h]
0x1800939ef  mov     dword ptr [rsp+160h+Data], eax
0x1800939f3  mov     edi, [rbx+24h]
0x1800939f6  xor     edi, 74161A4Eh
0x1800939fc  bswap   edi
0x1800939fe  xor     edi, 8FB23D4Fh
0x180093a04  ror     edi, 0FFh
0x180093a07  xor     edi, 833EA8FFh
0x180093a0d  lea     r9, [rbp+60h+var_5E]
0x180093a11  mov     r8d, edi
0x180093a14  sub     r9, 2
0x180093a18  mov     eax, 0CCCCCCCDh
0x180093a1d  mul     r8d
0x180093a20  shr     edx, 3
0x180093a23  movzx   eax, dx
0x180093a26  shl     ax, 2
0x180093a2a  lea     ecx, [rax+rdx]
0x180093a2d  add     cx, cx
0x180093a30  sub     r8w, cx
0x180093a34  add     r8w, 30h ; '0'
0x180093a39  mov     [r9], r8w
0x180093a3d  mov     r8d, edx
0x180093a40  test    edx, edx
0x180093a42  jnz     short loc_180093A14
0x180093a44  lea     r8, [rbp+60h+var_5E]
0x180093a48  mov     rdx, r9
0x180093a4b  lea     rcx, [rbp+60h+var_A8]
0x180093a4f  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x180093a54  nop
0x180093a55  lea     r9, [rbp+60h+var_2E]
0x180093a59  sub     r9, 2
0x180093a5d  mov     eax, 0CCCCCCCDh
0x180093a62  mul     edi
0x180093a64  shr     edx, 3
0x180093a67  movzx   eax, dx
0x180093a6a  shl     ax, 2
0x180093a6e  lea     ecx, [rax+rdx]
0x180093a71  add     cx, cx
0x180093a74  sub     di, cx
0x180093a77  add     di, 30h ; '0'
0x180093a7b  mov     [r9], di
0x180093a7f  mov     edi, edx
0x180093a81  test    edx, edx
0x180093a83  jnz     short loc_180093A59
0x180093a85  lea     r8, [rbp+60h+var_2E]
0x180093a89  mov     rdx, r9
0x180093a8c  lea     rcx, [rbp+60h+var_88]
0x180093a90  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x180093a95  lea     rcx, [rbp+60h+var_88]
0x180093a99  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180093a9e  mov     rdx, rax; lpValueName
0x180093aa1  mov     [rsp+160h+samDesired], 4; cbData
0x180093aa9  lea     rax, [rsp+160h+Data]
0x180093aae  mov     qword ptr [rsp+160h+dwOptions], rax; int
0x180093ab3  lea     r9d, [rdi+4]; dwType
0x180093ab7  xor     r8d, r8d; Reserved
0x180093aba  mov     rcx, [rsp+160h+hKey]; hKey
0x180093abf  call    cs:__imp_RegSetValueExW
0x180093ac5  mov     edi, eax
0x180093ac7  test    eax, eax
0x180093ac9  jle     short loc_180093AD4
0x180093acb  movzx   edi, ax
0x180093ace  or      edi, 80070000h
0x180093ad4  lea     rcx, [rbp+60h+var_88]
0x180093ad8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180093add  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata> `wil::Feature<__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata>::GetImpl(void)'::`2'::impl
0x180093ae4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata>::__private_IsEnabled(void)
0x180093ae9  test    al, al
0x180093aeb  jnz     short loc_180093AFD
0x180093aed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_GPVersionFilters@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GPVersionFilters@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPVersionFilters> `wil::Feature<__WilFeatureTraits_Feature_Servicing_GPVersionFilters>::GetImpl(void)'::`2'::impl
0x180093af4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GPVersionFilters@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPVersionFilters>::__private_IsEnabled(void)
0x180093af9  test    al, al
0x180093afb  jz      short loc_180093B2B
0x180093afd  mov     eax, [rbx+24h]
0x180093b00  mov     [rsp+160h+var_110], eax
0x180093b04  lea     rcx, [rsi+8]
0x180093b08  lea     r8, [rsp+160h+var_110]
0x180093b0d  lea     rdx, [rbp+60h+var_B8]
0x180093b11  call    ??$_Try_emplace@H$$V@?$map@HUEnterprisePayload@@U?$less@H@std@@V?$allocator@U?$pair@$$CBHUEnterprisePayload@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBHUEnterprisePayload@@@std@@PEAX@std@@_N@1@$$QEAH@Z; std::map<int,EnterprisePayload>::_Try_emplace<int,>(int &&)
0x180093b16  mov     r9, [rax]
0x180093b19  add     r9, 28h ; '('
0x180093b1d  lea     r8, [rbp+60h+var_A8]
0x180093b21  lea     rdx, [rsp+160h+hKey]
0x180093b26  call    ?BackupFeatureMetadata@EnterpriseTreatmentsProvider@@AEAAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUEnterprisePayload@@@Z; EnterpriseTreatmentsProvider::BackupFeatureMetadata(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,EnterprisePayload const &)
0x180093b2b  test    edi, edi
0x180093b2d  jns     short loc_180093B54
0x180093b2f  test    cs:Microsoft_Windows_FeatureConfigurationEnableBits, 2
0x180093b36  jz      short loc_180093B47
0x180093b38  mov     r8d, edi
0x180093b3b  lea     rdx, ErrorWritingFeatureConfigsBackup
0x180093b42  call    McTemplateU0d_EventWriteTransfer
0x180093b47  mov     rcx, [rbp+68h]; this
0x180093b4b  mov     r9d, edi; char *
0x180093b4e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180093b53  nop
0x180093b54  lea     rcx, [rbp+60h+var_A8]
0x180093b58  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180093b5d  lea     rcx, [rsp+160h+var_F8]
0x180093b62  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VWinFlagsFeature@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WinFlagsFeature>>,std::_Iterator_base0>::operator++(void)
0x180093b67  mov     rbx, [rsp+160h+var_F8]
0x180093b6c  jmp     loc_1800939E1
0x180093b71  lea     rdx, [rsp+160h+var_E8]
0x180093b76  lea     rcx, [rsp+160h+var_E8]
0x180093b7b  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@VVariantConfiguration@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@VVariantConfiguration@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@VVariantConfiguration@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<VariantConfiguration>>::_Erase_head<std::allocator<std::_Tree_node<VariantConfiguration,void *>>>(std::allocator<std::_Tree_node<VariantConfiguration,void *>> &)
0x180093b80  lea     rcx, [rsp+160h+var_F0]
0x180093b85  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VWinFlagsFeature@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WinFlagsFeature>>,std::_Iterator_base0>::operator++(void)
0x180093b8a  mov     rcx, [rsp+160h+var_F0]
0x180093b8f  jmp     loc_1800939BB
0x180093b94  lea     rdx, [rbp+60h+var_D8]
0x180093b98  lea     rcx, [rbp+60h+var_D8]
0x180093b9c  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@VTreatment@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@VTreatment@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@VTreatment@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<Treatment>>::_Erase_head<std::allocator<std::_Tree_node<Treatment,void *>>>(std::allocator<std::_Tree_node<Treatment,void *>> &)
0x180093ba1  mov     eax, edi
0x180093ba3  shr     eax, 1Fh
0x180093ba6  xor     al, 1
0x180093ba8  mov     [rsi+28h], al
0x180093bab  lea     rdx, [rbp+60h+var_C8]
0x180093baf  lea     rcx, [rbp+60h+var_C8]
0x180093bb3  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@VTreatment@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@VTreatment@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@VTreatment@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<Treatment>>::_Erase_head<std::allocator<std::_Tree_node<Treatment,void *>>>(std::allocator<std::_Tree_node<Treatment,void *>> &)
0x180093bb8  nop
0x180093bb9  lea     rcx, [rsp+160h+hKey]
0x180093bbe  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180093bc3  mov     eax, edi
0x180093bc5  mov     rcx, [rbp+60h+var_28]
0x180093bc9  xor     rcx, rsp; StackCookie
0x180093bcc  call    __security_check_cookie
0x180093bd1  add     rsp, 148h
0x180093bd8  pop     rdi
0x180093bd9  pop     rsi
0x180093bda  pop     rbx
0x180093bdb  pop     rbp
0x180093bdc  retn
```
