# SetupNodeATCIntents(_HCLUSTER *,wchar_t const *,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,ulong>>> const &,PhaseManager &)

- ea: `0x18008f978`
- end: `0x180090070`
- name: `?SetupNodeATCIntents@@YAKPEAU_HCLUSTER@@PEB_WAEBV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAVPhaseManager@@@Z`
- size: `1784`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180040790`

## callees

- `0x180002f50`
- `0x180003c14`
- `0x18001aa48`
- `0x18001b10c`
- `0x18001cc2c`
- `0x18001ecdc`
- `0x180024d98`
- `0x180028f30`
- `0x180029410`
- `0x180029450`
- `0x180029578`
- `0x18002fbc0`
- `0x180033190`
- `0x180063cb0`
- `0x180063f44`
- `0x1800647c0`
- `0x18006f17c`
- `0x18006f910`
- `0x180078c2c`
- `0x18008f6f4`
- `0x18008f978`
- `0x180090078`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fffa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008fc94`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008fc94`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18008fedf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18008fef5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18008fedf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18008fef5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008faa7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008fe63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008faa7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008fe63`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18008fa12`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18008fa12`

## string_xrefs

- `0x18008fa23`: `RegConnectRegistry failed to connect to remote registry on node %ws.`
- `0x18008fa9b`: `SYSTEM\CurrentControlSet\Services\NetworkATC\Requests`
- `0x18008faba`: `RegOpenKeyEx failed to open registry key on node %ws.`
- `0x18008fc58`: `Copying Network ATC intent %ws to node %ws.`
- `0x18008fd6d`: `RegSetValueEx failed to copy Network ATC intent %ws on node %ws with error %d.`
- `0x18008fe00`: `Inconsistent Configuration: NetworkATC feature is not installed on node %ws.`
- `0x18008fe57`: `SYSTEM\CurrentControlSet\Services\NetworkATC\GoalStates`
- `0x18008fe73`: `RegOpenKeyEx failed with error %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SetupNodeATCIntents(struct _HCLUSTER *a1, const WCHAR *a2, const WCHAR ***a3, PhaseManager *a4)
{
  HKEY v5; // rbx
  unsigned int v6; // esi
  DWORD v8; // edi
  DWORD v9; // eax
  __int64 v10; // rdi
  __int64 v11; // rax
  LPBYTE v12; // rsi
  BYTE *v13; // rax
  size_t v14; // rdi
  DWORD v15; // edi
  LSTATUS v16; // eax
  __int64 v17; // rax
  __int64 v18; // r9
  const WCHAR *v19; // rax
  const WCHAR *v20; // rdi
  const wchar_t *v21; // rax
  __int64 v22; // rax
  LSTATUS v23; // eax
  const WCHAR ***v24; // rdi
  __int64 v25; // rax
  const WCHAR *v26; // rax
  const WCHAR *v27; // rax
  __int64 v28; // rax
  const wchar_t *v29; // rax
  DWORD LastError; // edi
  LPBYTE lpData; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwIndex; // [rsp+44h] [rbp-BCh]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchValueName; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v37; // [rsp+60h] [rbp-A0h] BYREF
  const WCHAR *v38; // [rsp+68h] [rbp-98h] BYREF
  LPBYTE v39[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h]
  const WCHAR ***v41; // [rsp+88h] [rbp-78h]
  __int128 v42; // [rsp+90h] [rbp-70h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-60h]
  PhaseManager *v44; // [rsp+A8h] [rbp-58h]
  HKEY v45; // [rsp+B0h] [rbp-50h]
  _OWORD v46[2]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v47[40]; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR szValueName[128]; // [rsp+100h] [rbp+0h] BYREF

  v44 = a4;
  v41 = a3;
  v38 = a2;
  v46[0] = 0;
  v46[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v46[0]) = 0;
  v5 = OpenClusterRelative(a1, L"NetworkAtc", L"IntentRequests", 0x20019u);
  v45 = v5;
  if ( (unsigned __int64)v5 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    TraceMsg(2, 11, L"SetupNodeATCIntents", 91, L"Failed to get Cluster NetworkATC key with error %d.", LastError);
    std::wstring::_Tidy_deallocate(v46);
    return LastError;
  }
  phkResult = 0;
  v6 = RegConnectRegistryW(a2, HKEY_LOCAL_MACHINE, &phkResult);
  if ( v6 )
  {
    TraceMsg(
      2,
      11,
      L"SetupNodeATCIntents",
      99,
      L"RegConnectRegistry failed to connect to remote registry on node %ws.",
      a2);
LABEL_4:
    cxl::AutoHandle<HKEY__ *,long,&long RegCloseKey(HKEY__ *),0>::Close(&phkResult);
    ClusterRegCloseKeyCommon(v5, 1);
    std::wstring::_Tidy_deallocate(v46);
    return v6;
  }
  hKey = 0;
  cxl::AutoHandle<HKEY__ *,long,&long RegCloseKey(HKEY__ *),0>::Close(&hKey);
  v6 = RegOpenKeyExW(phkResult, L"SYSTEM\\CurrentControlSet\\Services\\NetworkATC\\Requests", 0, 2u, &hKey);
  if ( v6 )
  {
    TraceMsg(2, 11, L"SetupNodeATCIntents", 112, L"RegOpenKeyEx failed to open registry key on node %ws.", a2);
LABEL_7:
    cxl::AutoHandle<HKEY__ *,long,&long RegCloseKey(HKEY__ *),0>::Close(&hKey);
    goto LABEL_4;
  }
  v42 = 0;
  v43 = 0;
  v8 = 0;
  dwIndex = 0;
  do
  {
    cchValueName = 128;
    cbData = 0;
    *(_OWORD *)v39 = 0;
    v40 = 0;
    v9 = ClusterRegEnumValue(v5, v8, szValueName, &cchValueName, 0, 0, &cbData);
    v6 = v9;
    if ( !v9 )
    {
      v10 = std::wstring::wstring(v47, szValueName);
      v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v10);
      LOBYTE(v10) = std::_Traits_equal<std::char_traits<wchar_t>>(v11, *(_QWORD *)(v10 + 16), L"globalintent", 12);
      std::wstring::_Tidy_deallocate(v47);
      if ( (_BYTE)v10 )
      {
        v8 = ++dwIndex;
        goto LABEL_23;
      }
      cchValueName = 128;
      v12 = v39[1];
      if ( (LPBYTE)cbData < (LPBYTE)(v39[1] - v39[0]) )
      {
        v13 = &v39[0][cbData];
LABEL_18:
        v39[1] = v13;
        goto LABEL_19;
      }
      if ( (LPBYTE)cbData > (LPBYTE)(v39[1] - v39[0]) )
      {
        if ( cbData <= v40 - (unsigned __int64)v39[0] )
        {
          v14 = cbData - (unsigned __int64)(v39[1] - v39[0]);
          memset_0(v39[1], 0, v14);
          v13 = &v12[v14];
          goto LABEL_18;
        }
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v39, cbData);
      }
LABEL_19:
      v15 = dwIndex;
      v6 = ClusterRegEnumValue(v5, dwIndex, szValueName, &cchValueName, 0, v39[0], &cbData);
      if ( !v6 )
      {
        TraceMsg(4, 11, L"SetupNodeATCIntents", 160, L"Copying Network ATC intent %ws to node %ws.", szValueName, v38);
        v16 = RegSetValueExW(hKey, szValueName, 0, 1u, v39[0], cbData);
        v6 = v16;
        if ( !v16 )
        {
          v8 = v15 + 1;
          dwIndex = v8;
          v17 = std::wstring::wstring(v47, szValueName);
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v42, v17);
          std::wstring::_Tidy_deallocate(v47);
          TraceMsg(
            4,
            11,
            L"SetupNodeATCIntents",
            177,
            L"Successfully copied Network ATC intent %ws to node %ws.",
            szValueName,
            v38);
          goto LABEL_23;
        }
        TraceMsg(
          2,
          11,
          L"SetupNodeATCIntents",
          171,
          L"RegSetValueEx failed to copy Network ATC intent %ws on node %ws with error %d.",
          szValueName,
          v38,
          v16);
LABEL_27:
        std::vector<unsigned char>::_Tidy(v39);
        goto LABEL_28;
      }
      LODWORD(lpData) = v6;
      v18 = 181;
LABEL_30:
      TraceMsg(2, 11, L"SetupNodeATCIntents", v18, L"ClusterRegEnumValue failed with error %d.", lpData);
      goto LABEL_27;
    }
    if ( v9 != 259 )
    {
      LODWORD(lpData) = v9;
      v18 = 189;
      goto LABEL_30;
    }
LABEL_23:
    std::vector<unsigned char>::_Tidy(v39);
  }
  while ( !v6 );
  if ( (_QWORD)v42 == *((_QWORD *)&v42 + 1) )
  {
    TraceMsg(4, 11, L"SetupNodeATCIntents", 198, L"There are no Network ATC intents on the cluster.");
    v6 = 0;
LABEL_28:
    std::vector<std::wstring>::_Tidy(&v42);
    goto LABEL_7;
  }
  v19 = **v41;
  v38 = v19;
  while ( !*((_BYTE *)v19 + 25) )
  {
    v20 = v19 + 16;
    v21 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v19 + 16);
    if ( !(unsigned int)IsNetworkATCFeatureInstalled(v21) )
    {
      v22 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v20);
      TraceMsg(
        4,
        11,
        L"SetupNodeATCIntents",
        206,
        L"Inconsistent Configuration: NetworkATC feature is not installed on node %ws.",
        v22);
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>,std::_Iterator_base0>::operator++(&v38);
    v19 = v38;
  }
  v37 = 0;
  cxl::AutoHandle<HKEY__ *,long,&long RegCloseKey(HKEY__ *),0>::Close(&v37);
  v23 = RegOpenKeyExW(phkResult, L"SYSTEM\\CurrentControlSet\\Services\\NetworkATC\\GoalStates", 0, 3u, &v37);
  v6 = v23;
  if ( v23 )
  {
    LODWORD(lpData) = v23;
    TraceMsg(2, 11, L"SetupNodeATCIntents", 223, L"RegOpenKeyEx failed with error %d.", lpData);
LABEL_38:
    cxl::AutoHandle<HKEY__ *,long,&long RegCloseKey(HKEY__ *),0>::Close(&v37);
    goto LABEL_28;
  }
  v41 = (const WCHAR ***)*((_QWORD *)&v42 + 1);
  v24 = (const WCHAR ***)v42;
  if ( (_QWORD)v42 != *((_QWORD *)&v42 + 1) )
  {
    while ( 1 )
    {
      v25 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v24);
      v6 = WaitForProvisioningToComplete(&v37, v25, v44);
      v26 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v24);
      RegDeleteValueW(hKey, v26);
      v27 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v24);
      RegDeleteValueW(v37, v27);
      if ( v6 )
        break;
      v24 += 4;
      if ( v24 == v41 )
        goto LABEL_42;
    }
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v24);
    v28 = HelperFormatMessage(v47, g_ClusapiModule, 31);
    std::wstring::operator=(v46, v28);
    std::wstring::_Tidy_deallocate(v47);
    v29 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v46);
    PhaseManager::ReportPhaseStatus(v44, v29, v6, ClusterSetupPhaseWarning);
    LODWORD(lpData) = v6;
    TraceMsg(4, 11, L"SetupNodeATCIntents", 243, L"Provisioning Network ATC intents did not succeed %d.", lpData);
    goto LABEL_38;
  }
LABEL_42:
  TraceMsg(4, 11, L"SetupNodeATCIntents", 249, L"Provisioning Network ATC intents succeeded.");
  cxl::AutoHandle<HKEY__ *,long,&long RegCloseKey(HKEY__ *),0>::Close(&v37);
  std::vector<std::wstring>::_Tidy(&v42);
  cxl::AutoHandle<HKEY__ *,long,&long RegCloseKey(HKEY__ *),0>::Close(&hKey);
  cxl::AutoHandle<HKEY__ *,long,&long RegCloseKey(HKEY__ *),0>::Close(&phkResult);
  ClusterRegCloseKeyCommon(v5, 1);
  std::wstring::_Tidy_deallocate(v46);
  return 0;
}

```

## disassembly

```asm
0x18008f978  push    rbp
0x18008f97a  push    rbx
0x18008f97b  push    rsi
0x18008f97c  push    rdi
0x18008f97d  push    r13
0x18008f97f  push    r14
0x18008f981  push    r15
0x18008f983  lea     rbp, [rsp-110h]
0x18008f98b  sub     rsp, 210h
0x18008f992  mov     rax, cs:__security_cookie
0x18008f999  xor     rax, rsp
0x18008f99c  mov     [rbp+140h+var_40], rax
0x18008f9a3  mov     [rbp+140h+var_198], r9
0x18008f9a7  mov     [rbp+140h+var_1B8], r8
0x18008f9ab  mov     rdi, rdx
0x18008f9ae  mov     [rsp+240h+var_1D8], rdx
0x18008f9b3  xorps   xmm0, xmm0
0x18008f9b6  movups  [rbp+140h+var_188], xmm0
0x18008f9ba  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18008f9c2  movdqu  [rbp+140h+var_178], xmm1
0x18008f9c7  xor     eax, eax
0x18008f9c9  mov     word ptr [rbp+140h+var_188], ax
0x18008f9cd  mov     r9d, 20019h; samDesired
0x18008f9d3  lea     r8, aIntentrequests; "IntentRequests"
0x18008f9da  lea     rdx, aNetworkatc; "NetworkAtc"
0x18008f9e1  call    ?OpenClusterRelative@@YAPEAUHKEY__@@PEAU_HCLUSTER@@PEB_W1K@Z; OpenClusterRelative(_HCLUSTER *,wchar_t const *,wchar_t const *,ulong)
0x18008f9e6  mov     rbx, rax
0x18008f9e9  mov     [rbp+140h+var_190], rax
0x18008f9ed  dec     rax
0x18008f9f0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008f9f4  ja      loc_18008FFFA
0x18008f9fa  mov     [rsp+240h+phkResult], 0
0x18008fa03  lea     r8, [rsp+240h+phkResult]; phkResult
0x18008fa08  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18008fa0f  mov     rcx, rdi; lpMachineName
0x18008fa12  call    cs:__imp_RegConnectRegistryW
0x18008fa18  mov     esi, eax
0x18008fa1a  test    eax, eax
0x18008fa1c  jz      short loc_18008FA72
0x18008fa1e  mov     [rsp+240h+lpData], rdi
0x18008fa23  lea     rax, aRegconnectregi_1; "RegConnectRegistry failed to connect to"...
0x18008fa2a  mov     [rsp+240h+var_220], rax
0x18008fa2f  mov     r9d, 63h ; 'c'
0x18008fa35  lea     r8, aSetupnodeatcin; "SetupNodeATCIntents"
0x18008fa3c  lea     edx, [r9-58h]
0x18008fa40  lea     ecx, [rdx-9]
0x18008fa43  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008fa48  nop
0x18008fa49  lea     rcx, [rsp+240h+phkResult]
0x18008fa4e  call    ?Close@?$AutoHandle@PEAUHKEY__@@J$1?RegCloseKey@@YAJPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<HKEY__ *,long,&RegCloseKey(HKEY__ *),0>::Close(void)
0x18008fa53  nop
0x18008fa54  mov     edx, 1; int
0x18008fa59  mov     rcx, rbx; HKEY
0x18008fa5c  call    ?ClusterRegCloseKeyCommon@@YAJPEAUHKEY__@@H@Z; ClusterRegCloseKeyCommon(HKEY__ *,int)
0x18008fa61  nop
0x18008fa62  lea     rcx, [rbp+140h+var_188]
0x18008fa66  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008fa6b  mov     eax, esi
0x18008fa6d  jmp     loc_18009004F
0x18008fa72  mov     [rsp+240h+hKey], 0
0x18008fa7b  lea     rcx, [rsp+240h+hKey]
0x18008fa80  call    ?Close@?$AutoHandle@PEAUHKEY__@@J$1?RegCloseKey@@YAJPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<HKEY__ *,long,&RegCloseKey(HKEY__ *),0>::Close(void)
0x18008fa85  lea     rax, [rsp+240h+hKey]
0x18008fa8a  mov     [rsp+240h+var_220], rax; phkResult
0x18008fa8f  mov     r13d, 2
0x18008fa95  mov     r9d, r13d; samDesired
0x18008fa98  xor     r8d, r8d; ulOptions
0x18008fa9b  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x18008faa2  mov     rcx, [rsp+240h+phkResult]; hKey
0x18008faa7  call    cs:__imp_RegOpenKeyExW
0x18008faad  mov     esi, eax
0x18008faaf  xor     ecx, ecx
0x18008fab1  test    eax, eax
0x18008fab3  jz      short loc_18008FAEC
0x18008fab5  mov     [rsp+240h+lpData], rdi
0x18008faba  lea     rax, aRegopenkeyexFa_0; "RegOpenKeyEx failed to open registry ke"...
0x18008fac1  mov     [rsp+240h+var_220], rax
0x18008fac6  lea     r9d, [r13+6Eh]
0x18008faca  lea     r8, aSetupnodeatcin; "SetupNodeATCIntents"
0x18008fad1  lea     edx, [rcx+0Bh]
0x18008fad4  mov     ecx, r13d
0x18008fad7  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008fadc  nop
0x18008fadd  lea     rcx, [rsp+240h+hKey]
0x18008fae2  call    ?Close@?$AutoHandle@PEAUHKEY__@@J$1?RegCloseKey@@YAJPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<HKEY__ *,long,&RegCloseKey(HKEY__ *),0>::Close(void)
0x18008fae7  jmp     loc_18008FA49
0x18008faec  xorps   xmm0, xmm0
0x18008faef  movdqu  [rbp+140h+var_1B0], xmm0
0x18008faf4  mov     [rbp+140h+var_1A0], rcx
0x18008faf8  mov     edi, ecx
0x18008fafa  mov     [rsp+240h+dwIndex], ecx
0x18008fafe  lea     r14, aSetupnodeatcin; "SetupNodeATCIntents"
0x18008fb05  mov     r15d, 0Bh
0x18008fb0b  mov     [rsp+240h+cchValueName], 80h
0x18008fb13  mov     [rsp+240h+cbData], ecx
0x18008fb17  xorps   xmm0, xmm0
0x18008fb1a  movdqu  xmmword ptr [rsp+240h+var_1D0], xmm0
0x18008fb20  mov     [rbp+140h+var_1C0], rcx
0x18008fb24  lea     rax, [rsp+240h+cbData]
0x18008fb29  mov     [rsp+240h+lpcbData], rax; lpcbData
0x18008fb2e  mov     [rsp+240h+lpData], rcx; lpData
0x18008fb33  mov     [rsp+240h+var_220], rcx; lpdwType
0x18008fb38  lea     r9, [rsp+240h+cchValueName]; lpcchValueName
0x18008fb3d  lea     r8, [rbp+140h+szValueName]; lpszValueName
0x18008fb41  mov     edx, edi; dwIndex
0x18008fb43  mov     rcx, rbx; hKey
0x18008fb46  call    ClusterRegEnumValue
0x18008fb4b  mov     esi, eax
0x18008fb4d  test    eax, eax
0x18008fb4f  jnz     loc_18008FD03
0x18008fb55  lea     rdx, [rbp+140h+szValueName]
0x18008fb59  lea     rcx, [rbp+140h+var_168]
0x18008fb5d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008fb62  mov     rdi, rax
0x18008fb65  mov     rcx, rax
0x18008fb68  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18008fb6d  lea     r9d, [rsi+0Ch]
0x18008fb71  lea     r8, aGlobalintent; "globalintent"
0x18008fb78  mov     rdx, [rdi+10h]
0x18008fb7c  mov     rcx, rax
0x18008fb7f  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18008fb84  mov     dil, al
0x18008fb87  lea     rcx, [rbp+140h+var_168]
0x18008fb8b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008fb90  test    dil, dil
0x18008fb93  jz      short loc_18008FBA4
0x18008fb95  mov     edi, [rsp+240h+dwIndex]
0x18008fb99  inc     edi
0x18008fb9b  mov     [rsp+240h+dwIndex], edi
0x18008fb9f  jmp     loc_18008FD0E
0x18008fba4  mov     [rsp+240h+cchValueName], 80h
0x18008fbac  mov     edi, [rsp+240h+cbData]
0x18008fbb0  mov     rdx, [rsp+240h+var_1D0]
0x18008fbb5  mov     rsi, [rsp+240h+var_1D0+8]
0x18008fbba  mov     rcx, rsi
0x18008fbbd  sub     rcx, rdx
0x18008fbc0  cmp     rdi, rcx
0x18008fbc3  jnb     short loc_18008FBCB
0x18008fbc5  lea     rax, [rdx+rdi]
0x18008fbc9  jmp     short loc_18008FBFC
0x18008fbcb  jbe     short loc_18008FC01
0x18008fbcd  mov     rax, [rbp+140h+var_1C0]
0x18008fbd1  sub     rax, rdx
0x18008fbd4  cmp     rdi, rax
0x18008fbd7  jbe     short loc_18008FBE8
0x18008fbd9  mov     rdx, rdi
0x18008fbdc  lea     rcx, [rsp+240h+var_1D0]
0x18008fbe1  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18008fbe6  jmp     short loc_18008FC01
0x18008fbe8  sub     rdi, rcx
0x18008fbeb  mov     r8, rdi; Size
0x18008fbee  xor     edx, edx; Val
0x18008fbf0  mov     rcx, rsi; void *
0x18008fbf3  call    memset_0
0x18008fbf8  lea     rax, [rsi+rdi]
0x18008fbfc  mov     [rsp+240h+var_1D0+8], rax
0x18008fc01  mov     rax, [rsp+240h+var_1D0]
0x18008fc06  lea     rcx, [rsp+240h+cbData]
0x18008fc0b  mov     [rsp+240h+lpcbData], rcx; lpcbData
0x18008fc10  mov     [rsp+240h+lpData], rax; lpData
0x18008fc15  mov     [rsp+240h+var_220], 0; lpdwType
0x18008fc1e  lea     r9, [rsp+240h+cchValueName]; lpcchValueName
0x18008fc23  lea     r8, [rbp+140h+szValueName]; lpszValueName
0x18008fc27  mov     edi, [rsp+240h+dwIndex]
0x18008fc2b  mov     edx, edi; dwIndex
0x18008fc2d  mov     rcx, rbx; hKey
0x18008fc30  call    ClusterRegEnumValue
0x18008fc35  mov     esi, eax
0x18008fc37  mov     r8, r14
0x18008fc3a  mov     edx, r15d
0x18008fc3d  test    eax, eax
0x18008fc3f  jnz     loc_18008FDA7
0x18008fc45  mov     rax, [rsp+240h+var_1D8]
0x18008fc4a  mov     [rsp+240h+lpcbData], rax
0x18008fc4f  lea     rax, [rbp+140h+szValueName]
0x18008fc53  mov     [rsp+240h+lpData], rax
0x18008fc58  lea     rax, aCopyingNetwork; "Copying Network ATC intent %ws to node "...
0x18008fc5f  mov     [rsp+240h+var_220], rax
0x18008fc64  mov     r9d, 0A0h
0x18008fc6a  lea     ecx, [rsi+4]
0x18008fc6d  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008fc72  mov     eax, [rsp+240h+cbData]
0x18008fc76  mov     rdx, [rsp+240h+var_1D0]
0x18008fc7b  mov     dword ptr [rsp+240h+lpData], eax; cbData
0x18008fc7f  mov     [rsp+240h+var_220], rdx; lpData
0x18008fc84  lea     r9d, [rsi+1]; dwType
0x18008fc88  xor     r8d, r8d; Reserved
0x18008fc8b  lea     rdx, [rbp+140h+szValueName]; lpValueName
0x18008fc8f  mov     rcx, [rsp+240h+hKey]; hKey
0x18008fc94  call    cs:__imp_RegSetValueExW
0x18008fc9a  mov     esi, eax
0x18008fc9c  test    eax, eax
0x18008fc9e  jnz     loc_18008FD56
0x18008fca4  inc     edi
0x18008fca6  mov     [rsp+240h+dwIndex], edi
0x18008fcaa  lea     rdx, [rbp+140h+szValueName]
0x18008fcae  lea     rcx, [rbp+140h+var_168]
0x18008fcb2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008fcb7  nop
0x18008fcb8  mov     rdx, rax
0x18008fcbb  lea     rcx, [rbp+140h+var_1B0]
0x18008fcbf  call    ??$_Emplace_one_at_back@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x18008fcc4  nop
0x18008fcc5  lea     rcx, [rbp+140h+var_168]
0x18008fcc9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008fcce  mov     rax, [rsp+240h+var_1D8]
0x18008fcd3  mov     [rsp+240h+lpcbData], rax
0x18008fcd8  lea     rax, [rbp+140h+szValueName]
0x18008fcdc  mov     [rsp+240h+lpData], rax
0x18008fce1  lea     rax, aSuccessfullyCo; "Successfully copied Network ATC intent "...
0x18008fce8  mov     [rsp+240h+var_220], rax
0x18008fced  mov     r9d, 0B1h
0x18008fcf3  mov     r8, r14
0x18008fcf6  mov     edx, r15d
0x18008fcf9  lea     ecx, [rsi+4]
0x18008fcfc  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008fd01  jmp     short loc_18008FD0E
0x18008fd03  cmp     eax, 103h
0x18008fd08  jnz     loc_18008FFE5
0x18008fd0e  lea     rcx, [rsp+240h+var_1D0]
0x18008fd13  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008fd18  xor     ecx, ecx
0x18008fd1a  test    esi, esi
0x18008fd1c  jz      loc_18008FB0B
0x18008fd22  mov     rax, qword ptr [rbp+140h+var_1B0+8]
0x18008fd26  cmp     qword ptr [rbp+140h+var_1B0], rax
0x18008fd2a  jnz     loc_18008FDC7
0x18008fd30  lea     rax, aThereAreNoNetw; "There are no Network ATC intents on the"...
0x18008fd37  mov     [rsp+240h+var_220], rax
0x18008fd3c  mov     r9d, 0C6h
0x18008fd42  mov     r8, r14
0x18008fd45  mov     edx, r15d
0x18008fd48  mov     ecx, 4
0x18008fd4d  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008fd52  xor     esi, esi
0x18008fd54  jmp     short loc_18008FD99
0x18008fd56  mov     [rsp+240h+var_208], esi
0x18008fd5a  mov     rax, [rsp+240h+var_1D8]
0x18008fd5f  mov     [rsp+240h+lpcbData], rax
0x18008fd64  lea     rax, [rbp+140h+szValueName]
0x18008fd68  mov     [rsp+240h+lpData], rax
0x18008fd6d  lea     rax, aRegsetvalueexF; "RegSetValueEx failed to copy Network AT"...
0x18008fd74  mov     [rsp+240h+var_220], rax
0x18008fd79  mov     r9d, 0ABh
0x18008fd7f  mov     r8, r14
0x18008fd82  mov     edx, r15d
0x18008fd85  mov     ecx, r13d
0x18008fd88  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008fd8d  nop
0x18008fd8e  lea     rcx, [rsp+240h+var_1D0]
0x18008fd93  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008fd98  nop
0x18008fd99  lea     rcx, [rbp+140h+var_1B0]
0x18008fd9d  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18008fda2  jmp     loc_18008FADD
0x18008fda7  mov     dword ptr [rsp+240h+lpData], esi
0x18008fdab  mov     r9d, 0B5h
0x18008fdb1  lea     rax, aClusterregenum_1; "ClusterRegEnumValue failed with error %"...
0x18008fdb8  mov     [rsp+240h+var_220], rax
0x18008fdbd  mov     ecx, r13d
0x18008fdc0  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008fdc5  jmp     short loc_18008FD8E
0x18008fdc7  mov     rax, [rbp+140h+var_1B8]
0x18008fdcb  mov     rax, [rax]
0x18008fdce  mov     rax, [rax]
0x18008fdd1  mov     [rsp+240h+var_1D8], rax
0x18008fdd6  cmp     [rax+19h], cl
0x18008fdd9  jnz     short loc_18008FE35
0x18008fddb  lea     rdi, [rax+20h]
0x18008fddf  mov     rcx, rdi
0x18008fde2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18008fde7  mov     rcx, rax; wchar_t *
0x18008fdea  call    ?IsNetworkATCFeatureInstalled@@YAHPEB_W@Z; IsNetworkATCFeatureInstalled(wchar_t const *)
0x18008fdef  test    eax, eax
0x18008fdf1  jnz     short loc_18008FE22
0x18008fdf3  mov     rcx, rdi
0x18008fdf6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18008fdfb  mov     [rsp+240h+lpData], rax
0x18008fe00  lea     rax, aInconsistentCo; "Inconsistent Configuration: NetworkATC "...
0x18008fe07  mov     [rsp+240h+var_220], rax
0x18008fe0c  mov     r9d, 0CEh
0x18008fe12  mov     r8, r14
0x18008fe15  mov     edx, r15d
0x18008fe18  mov     ecx, 4
0x18008fe1d  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008fe22  lea     rcx, [rsp+240h+var_1D8]
0x18008fe27  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>,std::_Iterator_base0>::operator++(void)
0x18008fe2c  mov     rax, [rsp+240h+var_1D8]
0x18008fe31  xor     ecx, ecx
0x18008fe33  jmp     short loc_18008FDD6
0x18008fe35  mov     [rsp+240h+var_1E0], rcx
0x18008fe3a  lea     rcx, [rsp+240h+var_1E0]
0x18008fe3f  call    ?Close@?$AutoHandle@PEAUHKEY__@@J$1?RegCloseKey@@YAJPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<HKEY__ *,long,&RegCloseKey(HKEY__ *),0>::Close(void)
0x18008fe44  lea     rax, [rsp+240h+var_1E0]
0x18008fe49  mov     [rsp+240h+var_220], rax; phkResult
0x18008fe4e  mov     r9d, 3; samDesired
0x18008fe54  xor     r8d, r8d; ulOptions
0x18008fe57  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x18008fe5e  mov     rcx, [rsp+240h+phkResult]; hKey
0x18008fe63  call    cs:__imp_RegOpenKeyExW
  ... truncated ...
```
