# EnterpriseTreatmentsProvider::GetDataFromRegistry(ushort const *,std::map<int,EnterprisePayload,std::less<int>,std::allocator<std::pair<int const,EnterprisePayload>>> &)

- ea: `0x1800940d4`
- end: `0x180094500`
- name: `?GetDataFromRegistry@EnterpriseTreatmentsProvider@@AEAAJPEBGAEAV?$map@HUEnterprisePayload@@U?$less@H@std@@V?$allocator@U?$pair@$$CBHUEnterprisePayload@@@std@@@3@@std@@@Z`
- size: `1068`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180092f6c`
- `0x180093fb8`

## callees

- `0x180003220`
- `0x18000949c`
- `0x180015af4`
- `0x180016698`
- `0x180018ab4`
- `0x180019890`
- `0x18001e820`
- `0x180035f90`
- `0x1800450e8`
- `0x18004bf64`
- `0x180092aa8`
- `0x180092ae4`
- `0x18009338c`
- `0x180093454`
- `0x1800940d4`
- `0x180094508`
- `0x180094dd0`
- `0x180094e14`
- `0x180094fc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800941aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800941aa`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180094242`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180094242`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18009441d`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180094477`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800944e2`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18009441d`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180094477`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800944e2`

## string_xrefs

- `0x1800941e1`: `Error: Found invalid feature configurations, valid DWORD value expected, value index: %u`
- `0x180094393`: `Error: Found invalid feature configurations, valid DWORD value expected, value index: %u`
- `0x1800943e5`: `Error: Found invalid feature configurations, valid DWORD value expected, value index: %u`

## pseudocode

```c
__int64 __fastcall EnterpriseTreatmentsProvider::GetDataFromRegistry(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3)
{
  unsigned int v5; // r8d
  int v6; // eax
  unsigned int v7; // edi
  unsigned int v8; // ebx
  unsigned int v9; // eax
  DWORD i; // esi
  LSTATUS v11; // eax
  signed int v12; // ebx
  WCHAR *v13; // rbx
  unsigned __int32 v14; // edi
  int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  int v22; // edx
  int v23; // ecx
  int v24; // edx
  int v25; // ecx
  int v26; // edx
  int v27; // ecx
  int lpcSubKeys; // [rsp+20h] [rbp-E0h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-E0h]
  const char *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  unsigned __int32 v31; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchValueName; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbData; // [rsp+7Ch] [rbp-84h] BYREF
  BYTE Data[8]; // [rsp+80h] [rbp-80h] BYREF
  PWSTR ppszPathOut; // [rsp+88h] [rbp-78h] BYREF
  PWSTR v39; // [rsp+90h] [rbp-70h] BYREF
  PWSTR v40; // [rsp+98h] [rbp-68h] BYREF
  WCHAR *v41; // [rsp+A0h] [rbp-60h] BYREF
  int v42; // [rsp+A8h] [rbp-58h]
  _BYTE v43[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v44[16]; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v45[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v46; // [rsp+D8h] [rbp-28h]
  __int64 v47; // [rsp+E0h] [rbp-20h]
  __int128 v48; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v49; // [rsp+F8h] [rbp-8h]
  WCHAR ValueName[8]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v51; // [rsp+110h] [rbp+10h]
  __int128 v52; // [rsp+120h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0,
    a3);
  v6 = RegWow64Helpers::OpenKey(HKEY_LOCAL_MACHINE, a2, v5, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 >= 0 )
  {
    cValues = 0;
    v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
    if ( v9 )
    {
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x149,
             (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\enterprise\\enterprisetreatmentsprovider.cpp",
             (const char *)v9,
             lpcSubKeysa);
    }
    else
    {
      for ( i = 0; i < cValues; ++i )
      {
        *(_OWORD *)ValueName = 0;
        v51 = 0;
        v52 = 0;
        cchValueName = 24;
        Type = 0;
        cbData = 4;
        *(_DWORD *)Data = 0;
        v11 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, Data, &cbData);
        v12 = v11;
        if ( v11 > 0 )
          v12 = (unsigned __int16)v11 | 0x80070000;
        if ( v12 < 0 )
        {
          LODWORD(lpcbMaxSubKeyLen) = i;
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0x183,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\enterprise\\enterprisetreatmentsprovider.cpp",
            (const char *)(unsigned int)v12,
            (int)"Error: Found invalid feature configurations, valid DWORD value expected, value index: %u",
            lpcbMaxSubKeyLen);
          v40 = 0;
          PathAllocCombine(L"HKLM", a2, 0, &v40);
          if ( (Microsoft_Windows_FeatureConfigurationEnableBits & 2) != 0 )
            McTemplateU0zzqd_EventWriteTransfer(v27, v26, (_DWORD)v40, (unsigned int)ValueName, Type, v12);
        }
        else
        {
          v31 = 0;
          v13 = &ValueName[cchValueName];
          utl::_FromCharsImpl<utl::from_wchars_result,unsigned long,unsigned short>(&v41, ValueName, v13, &v31);
          if ( v42 || v41 != v13 )
          {
            LODWORD(lpcbMaxSubKeyLen) = i;
            wil::details::in1diag3::Log_Win32Msg(
              retaddr,
              (void *)0x160,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\enterprise\\enterprisetreatmentsprovider.cpp",
              (const char *)0x7B,
              (unsigned int)"Error: Found invalid feature configurations, valid DWORD value expected, value index: %u",
              lpcbMaxSubKeyLen);
            v39 = 0;
            PathAllocCombine(L"HKLM", a2, 0, &v39);
            if ( (Microsoft_Windows_FeatureConfigurationEnableBits & 2) != 0 )
              McTemplateU0zzqd_EventWriteTransfer(v25, v24, (_DWORD)v39, (unsigned int)ValueName, Type, 123);
          }
          else
          {
            v14 = _byteswap_ulong(__ROL4__(v31 ^ 0x833EA8FF, 255) ^ 0x8FB23D4F) ^ 0x74161A4E;
            if ( v14 && Type == 4 && cbData == 4 )
            {
              v45[0] = v14;
              v15 = *(_DWORD *)Data;
              v45[1] = *(_DWORD *)Data;
              BYTE4(v46) = 0;
              BYTE4(v47) = 0;
              v48 = 0;
              v49 = 0;
              v31 = v14;
              v16 = *(_QWORD *)std::map<int,EnterprisePayload>::_Try_emplace<int,>(a3, v43, &v31);
              *(_DWORD *)(v16 + 40) = v14;
              *(_DWORD *)(v16 + 44) = v15;
              *(_QWORD *)(v16 + 48) = v46;
              *(_QWORD *)(v16 + 56) = v47;
              std::vector<RTL_PROPERTY_BAG_ITEM>::operator=(v16 + 64, &v48);
              std::vector<RTL_PROPERTY_BAG_ITEM>::_Tidy(&v48);
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata>::GetImpl'::`2'::impl)
                || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPVersionFilters>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_GPVersionFilters>::GetImpl'::`2'::impl) )
              {
                v31 = v14;
                v17 = *(_QWORD *)std::map<int,EnterprisePayload>::_Try_emplace<int,>(a3, v44, &v31);
                v18 = std::wstring::wstring(v45);
                EnterpriseTreatmentsProvider::GetFeatureMetadataFromRegistry(v19, &hKey, v18, v17 + 40);
                std::wstring::_Tidy_deallocate(v45, v20);
              }
            }
            else
            {
              LODWORD(lpcbMaxSubKeyLen) = i;
              wil::details::in1diag3::Log_Win32Msg(
                retaddr,
                (void *)0x177,
                (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\enterprise\\enterprisetreatmentsprovider.cpp",
                (const char *)0xD,
                (unsigned int)"Error: Found invalid feature configurations, valid DWORD value expected, value index: %u",
                lpcbMaxSubKeyLen);
              ppszPathOut = 0;
              PathAllocCombine(L"HKLM", a2, 0, &ppszPathOut);
              if ( (Microsoft_Windows_FeatureConfigurationEnableBits & 2) != 0 )
                McTemplateU0zzqd_EventWriteTransfer(v23, v22, (_DWORD)ppszPathOut, (unsigned int)ValueName, Type, 13);
            }
          }
        }
      }
      v8 = 0;
    }
  }
  else
  {
    v8 = -2147024894;
    if ( v6 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x144,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\enterprise\\enterprisetreatmentsprovider.cpp",
        (const char *)(unsigned int)v6,
        lpcSubKeys);
      v8 = v7;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v8;
}

```

## disassembly

```asm
0x1800940d4  mov     [rsp-8+arg_0], rbx
0x1800940d9  mov     [rsp-8+arg_18], rsi
0x1800940de  push    rbp
0x1800940df  push    rdi
0x1800940e0  push    r12
0x1800940e2  push    r14
0x1800940e4  push    r15
0x1800940e6  lea     rbp, [rsp-40h]
0x1800940eb  sub     rsp, 140h
0x1800940f2  mov     rax, cs:__security_cookie
0x1800940f9  xor     rax, rsp
0x1800940fc  mov     [rbp+60h+var_30], rax
0x180094100  mov     r15, r8
0x180094103  mov     r14, rdx
0x180094106  xor     r12d, r12d
0x180094109  mov     [rsp+160h+hKey], r12
0x18009410e  xor     edx, edx
0x180094110  lea     rcx, [rsp+160h+hKey]
0x180094115  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009411a  lea     rax, [rsp+160h+hKey]
0x18009411f  mov     [rsp+160h+lpcSubKeys], rax; int
0x180094124  mov     r9d, 20019h; unsigned int
0x18009412a  mov     rdx, r14; unsigned __int16 *
0x18009412d  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180094134  call    ?OpenKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBGKKPEAPEAU2@@Z; RegWow64Helpers::OpenKey(HKEY__ * const,ushort const * const,ulong,ulong,HKEY__ * *)
0x180094139  mov     edi, eax
0x18009413b  test    eax, eax
0x18009413d  jns     short loc_18009416B
0x18009413f  mov     ebx, 80070002h
0x180094144  cmp     eax, ebx
0x180094146  jz      loc_1800943A9
0x18009414c  mov     rcx, [rbp+68h]; this
0x180094150  mov     r9d, eax; char *
0x180094153  lea     r8, aOnecoreBaseFli_36; "onecore\\base\\flighting\\featuremanage"...
0x18009415a  mov     edx, 144h; void *
0x18009415f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094164  mov     ebx, edi
0x180094166  jmp     loc_1800943A9
0x18009416b  mov     [rsp+160h+cValues], r12d
0x180094170  mov     [rsp+160h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180094175  mov     [rsp+160h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18009417a  mov     [rsp+160h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18009417f  mov     [rsp+160h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180094184  lea     rax, [rsp+160h+cValues]
0x180094189  mov     [rsp+160h+lpcValues], rax; lpcValues
0x18009418e  mov     [rsp+160h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180094193  mov     [rsp+160h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180094198  mov     [rsp+160h+lpcSubKeys], r12; unsigned int
0x18009419d  xor     r9d, r9d; lpReserved
0x1800941a0  xor     r8d, r8d; lpcchClass
0x1800941a3  xor     edx, edx; lpClass
0x1800941a5  mov     rcx, [rsp+160h+hKey]; hKey
0x1800941aa  call    cs:__imp_RegQueryInfoKeyW
0x1800941b0  test    eax, eax
0x1800941b2  jz      short loc_1800941D3
0x1800941b4  mov     rcx, [rbp+68h]; this
0x1800941b8  mov     r9d, eax; char *
0x1800941bb  lea     r8, aOnecoreBaseFli_36; "onecore\\base\\flighting\\featuremanage"...
0x1800941c2  mov     edx, 149h; void *
0x1800941c7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800941cc  mov     ebx, eax
0x1800941ce  jmp     loc_1800943A9
0x1800941d3  mov     esi, r12d
0x1800941d6  cmp     [rsp+160h+cValues], r12d
0x1800941db  jbe     loc_1800943A6
0x1800941e1  lea     rdi, aErrorFoundInva; "Error: Found invalid feature configurat"...
0x1800941e8  xorps   xmm0, xmm0
0x1800941eb  movups  xmmword ptr [rbp+60h+ValueName], xmm0
0x1800941ef  movups  [rbp+60h+var_50], xmm0
0x1800941f3  movups  [rbp+60h+var_40], xmm0
0x1800941f7  mov     [rsp+160h+cchValueName], 18h
0x1800941ff  mov     [rsp+160h+Type], r12d
0x180094204  mov     [rsp+160h+cbData], 4
0x18009420c  mov     dword ptr [rbp+60h+Data], r12d
0x180094210  lea     rax, [rsp+160h+cbData]
0x180094215  mov     [rsp+160h+lpcValues], rax; lpcbData
0x18009421a  lea     rax, [rbp+60h+Data]
0x18009421e  mov     [rsp+160h+lpcbMaxClassLen], rax; lpData
0x180094223  lea     rax, [rsp+160h+Type]
0x180094228  mov     [rsp+160h+lpcbMaxSubKeyLen], rax; lpType
0x18009422d  mov     [rsp+160h+lpcSubKeys], r12; lpReserved
0x180094232  lea     r9, [rsp+160h+cchValueName]; lpcchValueName
0x180094237  lea     r8, [rbp+60h+ValueName]; lpValueName
0x18009423b  mov     edx, esi; dwIndex
0x18009423d  mov     rcx, [rsp+160h+hKey]; hKey
0x180094242  call    cs:__imp_RegEnumValueW
0x180094248  mov     ebx, eax
0x18009424a  test    eax, eax
0x18009424c  jle     short loc_180094257
0x18009424e  movzx   ebx, ax
0x180094251  or      ebx, 80070000h
0x180094257  test    ebx, ebx
0x180094259  js      loc_1800944AC
0x18009425f  mov     [rsp+160h+var_100], r12d
0x180094264  mov     eax, [rsp+160h+cchValueName]
0x180094268  lea     rbx, [rbp+60h+ValueName]
0x18009426c  lea     rbx, [rbx+rax*2]
0x180094270  lea     r9, [rsp+160h+var_100]
0x180094275  mov     r8, rbx
0x180094278  lea     rdx, [rbp+60h+ValueName]
0x18009427c  lea     rcx, [rbp+60h+var_C0]
0x180094280  call    ??$_FromCharsImpl@Ufrom_wchars_result@utl@@KG@utl@@YA?AUfrom_wchars_result@0@PEBG0AEAKHPEA_N@Z; utl::_FromCharsImpl<utl::from_wchars_result,ulong,ushort>(ushort const *,ushort const *,ulong &,int,bool *)
0x180094285  cmp     [rbp+60h+var_B8], r12d
0x180094289  jnz     loc_18009443E
0x18009428f  cmp     [rbp+60h+var_C0], rbx
0x180094293  jnz     loc_18009443E
0x180094299  mov     edi, [rsp+160h+var_100]
0x18009429d  xor     edi, 833EA8FFh
0x1800942a3  rol     edi, 0FFh
0x1800942a6  xor     edi, 8FB23D4Fh
0x1800942ac  bswap   edi
0x1800942ae  xor     edi, 74161A4Eh
0x1800942b4  jbe     loc_1800943DD
0x1800942ba  cmp     [rsp+160h+Type], 4
0x1800942bf  jnz     loc_1800943DD
0x1800942c5  cmp     [rsp+160h+cbData], 4
0x1800942ca  jnz     loc_1800943DD
0x1800942d0  mov     [rbp+60h+var_90], edi
0x1800942d3  mov     ebx, dword ptr [rbp+60h+Data]
0x1800942d6  mov     [rbp+60h+var_8C], ebx
0x1800942d9  mov     [rbp+60h+var_84], r12b
0x1800942dd  mov     [rbp+60h+var_7C], r12b
0x1800942e1  xorps   xmm0, xmm0
0x1800942e4  movdqu  [rbp+60h+var_78], xmm0
0x1800942e9  mov     [rbp+60h+var_68], r12
0x1800942ed  mov     [rsp+160h+var_100], edi
0x1800942f1  lea     r8, [rsp+160h+var_100]
0x1800942f6  lea     rdx, [rbp+60h+var_B0]
0x1800942fa  mov     rcx, r15
0x1800942fd  call    ??$_Try_emplace@H$$V@?$map@HUEnterprisePayload@@U?$less@H@std@@V?$allocator@U?$pair@$$CBHUEnterprisePayload@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBHUEnterprisePayload@@@std@@PEAX@std@@_N@1@$$QEAH@Z; std::map<int,EnterprisePayload>::_Try_emplace<int,>(int &&)
0x180094302  mov     rcx, [rax]
0x180094305  mov     [rcx+28h], edi
0x180094308  mov     [rcx+2Ch], ebx
0x18009430b  mov     rax, [rbp-28h]
0x18009430f  mov     [rcx+30h], rax
0x180094313  mov     rax, [rbp-20h]
0x180094317  mov     [rcx+38h], rax
0x18009431b  add     rcx, 40h ; '@'
0x18009431f  lea     rdx, [rbp+60h+var_78]
0x180094323  call    ??4?$vector@URTL_PROPERTY_BAG_ITEM@@V?$allocator@URTL_PROPERTY_BAG_ITEM@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<RTL_PROPERTY_BAG_ITEM>::operator=(std::vector<RTL_PROPERTY_BAG_ITEM> &&)
0x180094328  nop
0x180094329  lea     rcx, [rbp+60h+var_78]
0x18009432d  call    ?_Tidy@?$vector@URTL_PROPERTY_BAG_ITEM@@V?$allocator@URTL_PROPERTY_BAG_ITEM@@@std@@@std@@AEAAXXZ; std::vector<RTL_PROPERTY_BAG_ITEM>::_Tidy(void)
0x180094332  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata> `wil::Feature<__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata>::GetImpl(void)'::`2'::impl
0x180094339  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GpChangeTimeMetadata>::__private_IsEnabled(void)
0x18009433e  test    al, al
0x180094340  jnz     short loc_180094352
0x180094342  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_GPVersionFilters@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GPVersionFilters@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPVersionFilters> `wil::Feature<__WilFeatureTraits_Feature_Servicing_GPVersionFilters>::GetImpl(void)'::`2'::impl
0x180094349  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GPVersionFilters@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPVersionFilters>::__private_IsEnabled(void)
0x18009434e  test    al, al
0x180094350  jz      short loc_180094393
0x180094352  mov     [rsp+160h+var_100], edi
0x180094356  lea     r8, [rsp+160h+var_100]
0x18009435b  lea     rdx, [rbp+60h+var_A0]
0x18009435f  mov     rcx, r15
0x180094362  call    ??$_Try_emplace@H$$V@?$map@HUEnterprisePayload@@U?$less@H@std@@V?$allocator@U?$pair@$$CBHUEnterprisePayload@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBHUEnterprisePayload@@@std@@PEAX@std@@_N@1@$$QEAH@Z; std::map<int,EnterprisePayload>::_Try_emplace<int,>(int &&)
0x180094367  mov     rbx, [rax]
0x18009436a  lea     rdx, [rbp+60h+ValueName]
0x18009436e  lea     rcx, [rbp+60h+var_90]
0x180094372  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180094377  nop
0x180094378  lea     r9, [rbx+28h]
0x18009437c  mov     r8, rax
0x18009437f  lea     rdx, [rsp+160h+hKey]
0x180094384  call    ?GetFeatureMetadataFromRegistry@EnterpriseTreatmentsProvider@@AEAAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUEnterprisePayload@@@Z; EnterpriseTreatmentsProvider::GetFeatureMetadataFromRegistry(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,EnterprisePayload &)
0x180094389  nop
0x18009438a  lea     rcx, [rbp+60h+var_90]
0x18009438e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180094393  lea     rdi, aErrorFoundInva; "Error: Found invalid feature configurat"...
0x18009439a  inc     esi
0x18009439c  cmp     esi, [rsp+160h+cValues]
0x1800943a0  jb      loc_1800941E8
0x1800943a6  mov     ebx, r12d
0x1800943a9  lea     rcx, [rsp+160h+hKey]
0x1800943ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800943b3  mov     eax, ebx
0x1800943b5  mov     rcx, [rbp+60h+var_30]
0x1800943b9  xor     rcx, rsp; StackCookie
0x1800943bc  call    __security_check_cookie
0x1800943c1  lea     r11, [rsp+160h+var_20]
0x1800943c9  mov     rbx, [r11+30h]
0x1800943cd  mov     rsi, [r11+48h]
0x1800943d1  mov     rsp, r11
0x1800943d4  pop     r15
0x1800943d6  pop     r14
0x1800943d8  pop     r12
0x1800943da  pop     rdi
0x1800943db  pop     rbp
0x1800943dc  retn
0x1800943dd  mov     rcx, [rbp+68h]; this
0x1800943e1  mov     dword ptr [rsp+160h+lpcbMaxSubKeyLen], esi; char *
0x1800943e5  lea     rdi, aErrorFoundInva; "Error: Found invalid feature configurat"...
0x1800943ec  mov     [rsp+160h+lpcSubKeys], rdi; unsigned int
0x1800943f1  mov     r9d, 0Dh; char *
0x1800943f7  lea     r8, aOnecoreBaseFli_36; "onecore\\base\\flighting\\featuremanage"...
0x1800943fe  mov     edx, 177h; void *
0x180094403  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180094408  mov     [rbp+60h+ppszPathOut], r12
0x18009440c  lea     r9, [rbp+60h+ppszPathOut]; ppszPathOut
0x180094410  xor     r8d, r8d; dwFlags
0x180094413  mov     rdx, r14; pszMore
0x180094416  lea     rcx, pszPathIn; "HKLM"
0x18009441d  call    cs:__imp_PathAllocCombine
0x180094423  test    cs:Microsoft_Windows_FeatureConfigurationEnableBits, 2
0x18009442a  jz      loc_18009439A
0x180094430  mov     dword ptr [rsp+160h+lpcbMaxSubKeyLen], 8007000Dh
0x180094438  mov     r8, [rbp+60h+ppszPathOut]
0x18009443c  jmp     short loc_180094496
0x18009443e  mov     rcx, [rbp+68h]; this
0x180094442  mov     dword ptr [rsp+160h+lpcbMaxSubKeyLen], esi; char *
0x180094446  mov     [rsp+160h+lpcSubKeys], rdi; unsigned int
0x18009444b  mov     r9d, 7Bh ; '{'; char *
0x180094451  lea     r8, aOnecoreBaseFli_36; "onecore\\base\\flighting\\featuremanage"...
0x180094458  mov     edx, 160h; void *
0x18009445d  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180094462  mov     [rbp+60h+var_D0], r12
0x180094466  lea     r9, [rbp+60h+var_D0]; ppszPathOut
0x18009446a  xor     r8d, r8d; dwFlags
0x18009446d  mov     rdx, r14; pszMore
0x180094470  lea     rcx, pszPathIn; "HKLM"
0x180094477  call    cs:__imp_PathAllocCombine
0x18009447d  test    cs:Microsoft_Windows_FeatureConfigurationEnableBits, 2
0x180094484  jz      loc_18009439A
0x18009448a  mov     dword ptr [rsp+160h+lpcbMaxSubKeyLen], 8007007Bh
0x180094492  mov     r8, [rbp+60h+var_D0]
0x180094496  mov     eax, [rsp+160h+Type]
0x18009449a  mov     dword ptr [rsp+160h+lpcSubKeys], eax
0x18009449e  lea     r9, [rbp+60h+ValueName]
0x1800944a2  call    McTemplateU0zzqd_EventWriteTransfer
0x1800944a7  jmp     loc_18009439A
0x1800944ac  mov     rcx, [rbp+68h]; this
0x1800944b0  mov     dword ptr [rsp+160h+lpcbMaxSubKeyLen], esi; char *
0x1800944b4  mov     [rsp+160h+lpcSubKeys], rdi; int
0x1800944b9  mov     r9d, ebx; char *
0x1800944bc  lea     r8, aOnecoreBaseFli_36; "onecore\\base\\flighting\\featuremanage"...
0x1800944c3  mov     edx, 183h; void *
0x1800944c8  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800944cd  mov     [rbp+60h+var_C8], r12
0x1800944d1  lea     r9, [rbp+60h+var_C8]; ppszPathOut
0x1800944d5  xor     r8d, r8d; dwFlags
0x1800944d8  mov     rdx, r14; pszMore
0x1800944db  lea     rcx, pszPathIn; "HKLM"
0x1800944e2  call    cs:__imp_PathAllocCombine
0x1800944e8  test    cs:Microsoft_Windows_FeatureConfigurationEnableBits, 2
0x1800944ef  jz      loc_18009439A
0x1800944f5  mov     dword ptr [rsp+160h+lpcbMaxSubKeyLen], ebx
0x1800944f9  mov     r8, [rbp+60h+var_C8]
0x1800944fd  jmp     short loc_180094496
```
