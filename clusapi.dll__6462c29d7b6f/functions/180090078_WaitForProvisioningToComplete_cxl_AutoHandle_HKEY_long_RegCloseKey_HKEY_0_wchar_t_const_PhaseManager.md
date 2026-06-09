# WaitForProvisioningToComplete(cxl::AutoHandle<HKEY__ *,long,&RegCloseKey(HKEY__ *),0> &,wchar_t const *,PhaseManager &)

- ea: `0x180090078`
- end: `0x18009044b`
- name: `?WaitForProvisioningToComplete@@YAKAEAU?$AutoHandle@PEAUHKEY__@@J$1?RegCloseKey@@YAJPEAU1@@Z$0A@@cxl@@PEB_WAEAVPhaseManager@@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18008f978`

## callees

- `0x180002f50`
- `0x180003c14`
- `0x1800098a0`
- `0x18000a560`
- `0x18000a580`
- `0x18001cc2c`
- `0x180024d98`
- `0x180028f30`
- `0x180029410`
- `0x180029578`
- `0x180029f38`
- `0x18006f17c`
- `0x18006f910`
- `0x18008f2d0`
- `0x18008f4a4`
- `0x18008f68c`
- `0x180090078`
- `0x1800904d0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180090413`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180090413`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180090175`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180090175`

## string_xrefs

- `0x18009019a`: `WaitForProvisioningToComplete`
- `0x1800902fe`: `WaitForProvisioningToComplete`
- `0x1800903ac`: `WaitForProvisioningToComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaitForProvisioningToComplete(HKEY *a1, const WCHAR *a2, PhaseManager *a3)
{
  const WCHAR *v3; // r14
  HKEY *v4; // r13
  unsigned int v5; // esi
  unsigned int v6; // edi
  LPBYTE v7; // rdi
  BYTE *v8; // rax
  size_t v9; // rbx
  LSTATUS v10; // eax
  struct web::json::object *v11; // rbx
  web::json::value *v12; // rax
  unsigned int v13; // ebx
  const wchar_t *v14; // rdx
  __int64 StatusString; // rbx
  const wchar_t *v16; // rax
  _QWORD *v17; // rax
  __int64 v19; // rax
  LPDWORD lpcbData; // [rsp+28h] [rbp-130h]
  _BYTE v21[4]; // [rsp+40h] [rbp-118h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-114h] BYREF
  int v23; // [rsp+48h] [rbp-110h]
  LSTATUS v24; // [rsp+4Ch] [rbp-10Ch]
  PhaseManager *v25; // [rsp+50h] [rbp-108h]
  _BYTE v26[8]; // [rsp+58h] [rbp-100h] BYREF
  LPBYTE lpData[2]; // [rsp+60h] [rbp-F8h] BYREF
  __int64 v28; // [rsp+70h] [rbp-E8h]
  const WCHAR *v29; // [rsp+78h] [rbp-E0h]
  HKEY *v30; // [rsp+80h] [rbp-D8h]
  PhaseManager *v31; // [rsp+88h] [rbp-D0h]
  __int64 v32; // [rsp+90h] [rbp-C8h] BYREF
  const std::exception *v33; // [rsp+98h] [rbp-C0h] BYREF
  _BYTE v34[8]; // [rsp+A0h] [rbp-B8h] BYREF
  _BYTE v35[32]; // [rsp+A8h] [rbp-B0h] BYREF
  _BYTE v36[32]; // [rsp+C8h] [rbp-90h] BYREF
  _BYTE v37[32]; // [rsp+E8h] [rbp-70h] BYREF
  _BYTE v38[32]; // [rsp+108h] [rbp-50h] BYREF

  v25 = a3;
  v3 = a2;
  v4 = a1;
  v30 = a1;
  v29 = a2;
  v31 = a3;
  v5 = 1460;
  v6 = 1460;
  *(_OWORD *)lpData = 0;
  v28 = 0;
  cbData = 18000;
  std::chrono::steady_clock::now(&v32);
  while ( v6 )
  {
    v7 = lpData[1];
    if ( (LPBYTE)(lpData[1] - lpData[0]) != (LPBYTE)cbData )
    {
      v21[0] = 0;
      if ( (LPBYTE)(lpData[1] - lpData[0]) > (LPBYTE)cbData )
      {
        v8 = &lpData[0][cbData];
LABEL_10:
        lpData[1] = v8;
        goto LABEL_11;
      }
      if ( (LPBYTE)(lpData[1] - lpData[0]) < (LPBYTE)cbData )
      {
        if ( cbData <= v28 - (unsigned __int64)lpData[0] )
        {
          v9 = cbData - (unsigned __int64)(lpData[1] - lpData[0]);
          memset_0(lpData[1], 0, v9);
          v8 = &v7[v9];
          goto LABEL_10;
        }
        std::vector<unsigned char>::_Resize_reallocate<unsigned char>(lpData, cbData, v21);
      }
    }
LABEL_11:
    v10 = RegQueryValueExW(*v4, v3, 0, 0, lpData[0], &cbData);
    v6 = v10;
    v24 = v10;
    if ( v10 == 234 )
    {
      cbData += 1000;
    }
    else
    {
      if ( v10 )
      {
        LODWORD(lpcbData) = v10;
        TraceMsg(
          4u,
          0xBu,
          (__int64)L"WaitForProvisioningToComplete",
          285,
          L"RegQueryValueEx failed with error %d for intent %ws.",
          lpcbData,
          v3);
      }
      else
      {
        LODWORD(lpcbData) = cbData;
        TraceMsg(
          4u,
          0xBu,
          (__int64)L"WaitForProvisioningToComplete",
          289,
          L"We succeeded in getting data of size %d for intent %ws.",
          lpcbData,
          v3);
        std::wstring::wstring(v35, lpData[0]);
        web::json::value::parse(v26, v35);
        v23 = 6;
        try
        {
          v11 = web::json::value::as_object((web::json::value *)v26);
          std::wstring::wstring(v36, L"Status");
          v12 = (web::json::value *)web::json::object::at(v11, v36);
          v13 = web::json::value::as_integer(v12);
          v23 = v13;
          std::wstring::_Tidy_deallocate(v36);
        }
        catch ( const std::exception *v33 )
        {
          v19 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v33 + 8LL))(v33);
          TraceMsg(
            4u,
            0xBu,
            (__int64)L"WaitForProvisioningToComplete",
            301,
            L"Failed to get Status field for intent %ws with error  %S.",
            v29,
            v19);
          v5 = 1460;
          v6 = v24;
          v13 = v23;
          v4 = v30;
          v3 = v29;
          v25 = v31;
        }
        if ( v13 != 2 )
        {
          if ( v13 == 4 )
          {
            v5 = 10;
            HelperFormatMessage(v37, g_ClusapiModule, 31);
            v14 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v37);
            PhaseManager::ReportPhaseStatus(v25, v14, 0xAu, ClusterSetupPhaseInformational);
            TraceMsg(
              4u,
              0xBu,
              (__int64)L"WaitForProvisioningToComplete",
              315,
              L"Provisioning Network ATC Intent %ws failed.",
              v3);
            std::wstring::_Tidy_deallocate(v37);
            std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v26);
            std::wstring::_Tidy_deallocate(v35);
            goto LABEL_24;
          }
          v6 = -2147483638;
        }
        StatusString = GetStatusString(v13);
        HelperFormatMessage(v38, g_ClusapiModule, 32);
        v16 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v38);
        PhaseManager::ReportPhaseStatus(v25, v16, v6, ClusterSetupPhaseInformational);
        TraceMsg(
          4u,
          0xBu,
          (__int64)L"WaitForProvisioningToComplete",
          329,
          L"The current status for Network ATC intent %ws is %ws.",
          v3,
          StatusString);
        std::wstring::_Tidy_deallocate(v38);
        std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v26);
        std::wstring::_Tidy_deallocate(v35);
      }
      v17 = (_QWORD *)std::chrono::steady_clock::now(v34);
      if ( *v17 - v32 >= 900000000000LL )
        goto LABEL_24;
      Sleep(0x1F4u);
    }
  }
  v5 = 0;
LABEL_24:
  std::vector<unsigned char>::_Tidy(lpData);
  return v5;
}

```

## disassembly

```asm
0x180090078  push    rbx
0x18009007a  push    rsi
0x18009007b  push    rdi
0x18009007c  push    r13
0x18009007e  push    r14
0x180090080  sub     rsp, 130h
0x180090087  mov     rax, cs:__security_cookie
0x18009008e  xor     rax, rsp
0x180090091  mov     [rsp+158h+var_30], rax
0x180090099  mov     rax, r8
0x18009009c  mov     [rsp+158h+var_108], rax
0x1800900a1  mov     r14, rdx
0x1800900a4  mov     r13, rcx
0x1800900a7  mov     [rsp+158h+var_D8], rcx
0x1800900af  mov     [rsp+158h+var_E0], rdx
0x1800900b4  mov     [rsp+158h+var_D0], rax
0x1800900bc  mov     esi, 5B4h
0x1800900c1  mov     edi, esi
0x1800900c3  xorps   xmm0, xmm0
0x1800900c6  movdqu  xmmword ptr [rsp+158h+var_F8], xmm0
0x1800900cc  mov     [rsp+158h+var_E8], 0
0x1800900d5  mov     [rsp+158h+cbData], 4650h
0x1800900dd  lea     rcx, [rsp+158h+var_C8]
0x1800900e5  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800900ea  test    edi, edi
0x1800900ec  jz      loc_18009041E
0x1800900f2  mov     ebx, [rsp+158h+cbData]
0x1800900f6  mov     rdx, [rsp+158h+var_F8]
0x1800900fb  mov     rdi, [rsp+158h+var_F8+8]
0x180090100  mov     rcx, rdi
0x180090103  sub     rcx, rdx
0x180090106  cmp     rcx, rbx
0x180090109  jz      short loc_180090154
0x18009010b  mov     [rsp+158h+var_118], 0
0x180090110  jbe     short loc_180090118
0x180090112  lea     rax, [rbx+rdx]
0x180090116  jmp     short loc_18009014F
0x180090118  jnb     short loc_180090154
0x18009011a  mov     rax, [rsp+158h+var_E8]
0x18009011f  sub     rax, rdx
0x180090122  cmp     rbx, rax
0x180090125  jbe     short loc_18009013B
0x180090127  lea     r8, [rsp+158h+var_118]
0x18009012c  mov     rdx, rbx
0x18009012f  lea     rcx, [rsp+158h+var_F8]
0x180090134  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x180090139  jmp     short loc_180090154
0x18009013b  sub     rbx, rcx
0x18009013e  mov     r8, rbx; Size
0x180090141  xor     edx, edx; Val
0x180090143  mov     rcx, rdi; void *
0x180090146  call    memset_0
0x18009014b  lea     rax, [rbx+rdi]
0x18009014f  mov     [rsp+158h+var_F8+8], rax
0x180090154  mov     rax, [rsp+158h+var_F8]
0x180090159  lea     rcx, [rsp+158h+cbData]
0x18009015e  mov     [rsp+158h+lpcbData], rcx; lpcbData
0x180090163  mov     [rsp+158h+lpData], rax; lpData
0x180090168  xor     r9d, r9d; lpType
0x18009016b  xor     r8d, r8d; lpReserved
0x18009016e  mov     rdx, r14; lpValueName
0x180090171  mov     rcx, [r13+0]; hKey
0x180090175  call    cs:__imp_RegQueryValueExW
0x18009017b  mov     edi, eax
0x18009017d  mov     [rsp+158h+var_10C], eax
0x180090181  cmp     eax, 0EAh
0x180090186  jnz     short loc_180090195
0x180090188  add     [rsp+158h+cbData], 3E8h
0x180090190  jmp     loc_1800900EA
0x180090195  mov     [rsp+158h+var_128], r14
0x18009019a  lea     r8, aWaitforprovisi; "WaitForProvisioningToComplete"
0x1800901a1  mov     edx, 0Bh
0x1800901a6  lea     ecx, [rdx-7]
0x1800901a9  test    eax, eax
0x1800901ab  jz      short loc_1800901CD
0x1800901ad  mov     dword ptr [rsp+158h+lpcbData], eax
0x1800901b1  lea     rax, aRegqueryvaluee; "RegQueryValueEx failed with error %d fo"...
0x1800901b8  mov     [rsp+158h+lpData], rax
0x1800901bd  mov     r9d, 11Dh
0x1800901c3  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800901c8  jmp     loc_1800903E7
0x1800901cd  mov     eax, [rsp+158h+cbData]
0x1800901d1  mov     dword ptr [rsp+158h+lpcbData], eax
0x1800901d5  lea     rax, aWeSucceededInG; "We succeeded in getting data of size %d"...
0x1800901dc  mov     [rsp+158h+lpData], rax
0x1800901e1  mov     r9d, 121h
0x1800901e7  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800901ec  mov     rdx, [rsp+158h+var_F8]
0x1800901f1  lea     rcx, [rsp+158h+var_B0]
0x1800901f9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800901fe  nop
0x1800901ff  lea     rdx, [rsp+158h+var_B0]
0x180090207  lea     rcx, [rsp+158h+var_100]
0x18009020c  call    ?parse@value@json@web@@SA?AV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::parse(std::wstring const &)
0x180090211  nop
0x180090212  mov     [rsp+158h+var_110], 6
0x18009021a  lea     rcx, [rsp+158h+var_100]; this
0x18009021f  call    ?as_object@value@json@web@@QEAAAEAVobject@23@XZ; web::json::value::as_object(void)
0x180090224  mov     rbx, rax
0x180090227  lea     rdx, aStatus_0; "Status"
0x18009022e  lea     rcx, [rsp+158h+var_90]
0x180090236  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18009023b  nop
0x18009023c  lea     rdx, [rsp+158h+var_90]
0x180090244  mov     rcx, rbx
0x180090247  call    ?at@object@json@web@@QEAAAEAVvalue@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::object::at(std::wstring const &)
0x18009024c  mov     rcx, rax; this
0x18009024f  call    ?as_integer@value@json@web@@QEBAHXZ; web::json::value::as_integer(void)
0x180090254  mov     ebx, eax
0x180090256  mov     [rsp+158h+var_110], eax
0x18009025a  lea     rcx, [rsp+158h+var_90]
0x180090262  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180090267  nop
0x180090268  jmp     short loc_180090291
0x18009026a  mov     esi, 5B4h
0x18009026f  mov     edi, [rsp+158h+var_10C]
0x180090273  mov     ebx, [rsp+158h+var_110]
0x180090277  mov     r13, [rsp+158h+var_D8]
0x18009027f  mov     r14, [rsp+158h+var_E0]
0x180090284  mov     rax, [rsp+158h+var_D0]
0x18009028c  mov     [rsp+158h+var_108], rax
0x180090291  cmp     ebx, 2
0x180090294  jz      loc_180090340
0x18009029a  cmp     ebx, 4
0x18009029d  jnz     loc_18009033B
0x1800902a3  lea     esi, [rbx+6]
0x1800902a6  mov     dword ptr [rsp+158h+lpData], esi
0x1800902aa  mov     r9, r14
0x1800902ad  lea     r8d, [rbx+1Bh]
0x1800902b1  mov     rdx, cs:?g_ClusapiModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_ClusapiModule
0x1800902b8  lea     rcx, [rsp+158h+var_70]
0x1800902c0  call    ?HelperFormatMessage@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@KZZ; HelperFormatMessage(HINSTANCE__ *,ulong,...)
0x1800902c5  nop
0x1800902c6  lea     rcx, [rsp+158h+var_70]
0x1800902ce  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800902d3  mov     rdx, rax; wchar_t *
0x1800902d6  lea     r9d, [rbx-3]; enum _CLUSTER_SETUP_PHASE_SEVERITY
0x1800902da  mov     r8d, esi; unsigned int
0x1800902dd  mov     rcx, [rsp+158h+var_108]; this
0x1800902e2  call    ?ReportPhaseStatus@PhaseManager@@QEAAXPEB_WKW4_CLUSTER_SETUP_PHASE_SEVERITY@@@Z; PhaseManager::ReportPhaseStatus(wchar_t const *,ulong,_CLUSTER_SETUP_PHASE_SEVERITY)
0x1800902e7  mov     [rsp+158h+lpcbData], r14
0x1800902ec  lea     rax, aProvisioningNe_1; "Provisioning Network ATC Intent %ws fai"...
0x1800902f3  mov     [rsp+158h+lpData], rax
0x1800902f8  mov     r9d, 13Bh
0x1800902fe  lea     r8, aWaitforprovisi; "WaitForProvisioningToComplete"
0x180090305  lea     edx, [rbx+7]
0x180090308  mov     ecx, ebx
0x18009030a  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18009030f  nop
0x180090310  lea     rcx, [rsp+158h+var_70]
0x180090318  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009031d  nop
0x18009031e  lea     rcx, [rsp+158h+var_100]
0x180090323  call    ??1?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@QEAA@XZ; std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(void)
0x180090328  nop
0x180090329  lea     rcx, [rsp+158h+var_B0]
0x180090331  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180090336  jmp     loc_180090420
0x18009033b  mov     edi, 8000000Ah
0x180090340  mov     ecx, ebx
0x180090342  call    ?GetStatusString@@YAPEB_WW4GoalStateStatus@@@Z; GetStatusString(GoalStateStatus)
0x180090347  mov     rbx, rax
0x18009034a  mov     [rsp+158h+lpData], rax
0x18009034f  mov     r9, r14
0x180090352  mov     r8d, 20h ; ' '
0x180090358  mov     rdx, cs:?g_ClusapiModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_ClusapiModule
0x18009035f  lea     rcx, [rsp+158h+var_50]
0x180090367  call    ?HelperFormatMessage@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@KZZ; HelperFormatMessage(HINSTANCE__ *,ulong,...)
0x18009036c  nop
0x18009036d  lea     rcx, [rsp+158h+var_50]
0x180090375  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18009037a  mov     rdx, rax; wchar_t *
0x18009037d  mov     r9d, 1; enum _CLUSTER_SETUP_PHASE_SEVERITY
0x180090383  mov     r8d, edi; unsigned int
0x180090386  mov     rcx, [rsp+158h+var_108]; this
0x18009038b  call    ?ReportPhaseStatus@PhaseManager@@QEAAXPEB_WKW4_CLUSTER_SETUP_PHASE_SEVERITY@@@Z; PhaseManager::ReportPhaseStatus(wchar_t const *,ulong,_CLUSTER_SETUP_PHASE_SEVERITY)
0x180090390  mov     [rsp+158h+var_128], rbx
0x180090395  mov     [rsp+158h+lpcbData], r14
0x18009039a  lea     rax, aTheCurrentStat; "The current status for Network ATC inte"...
0x1800903a1  mov     [rsp+158h+lpData], rax
0x1800903a6  mov     r9d, 149h
0x1800903ac  lea     r8, aWaitforprovisi; "WaitForProvisioningToComplete"
0x1800903b3  mov     edx, 0Bh
0x1800903b8  lea     ecx, [rdx-7]
0x1800903bb  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800903c0  nop
0x1800903c1  lea     rcx, [rsp+158h+var_50]
0x1800903c9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800903ce  nop
0x1800903cf  lea     rcx, [rsp+158h+var_100]
0x1800903d4  call    ??1?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@QEAA@XZ; std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(void)
0x1800903d9  nop
0x1800903da  lea     rcx, [rsp+158h+var_B0]
0x1800903e2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800903e7  lea     rcx, [rsp+158h+var_B8]
0x1800903ef  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800903f4  mov     rcx, [rax]
0x1800903f7  sub     rcx, [rsp+158h+var_C8]
0x1800903ff  mov     rax, 0D18C2E2800h
0x180090409  cmp     rcx, rax
0x18009040c  jge     short loc_180090420
0x18009040e  mov     ecx, 1F4h; dwMilliseconds
0x180090413  call    cs:__imp_Sleep
0x180090419  jmp     loc_1800900EA
0x18009041e  xor     esi, esi
0x180090420  lea     rcx, [rsp+158h+var_F8]
0x180090425  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18009042a  mov     eax, esi
0x18009042c  mov     rcx, [rsp+158h+var_30]
0x180090434  xor     rcx, rsp; StackCookie
0x180090437  call    __security_check_cookie
0x18009043c  add     rsp, 130h
0x180090443  pop     r14
0x180090445  pop     r13
0x180090447  pop     rdi
0x180090448  pop     rsi
0x180090449  pop     rbx
0x18009044a  retn
```
