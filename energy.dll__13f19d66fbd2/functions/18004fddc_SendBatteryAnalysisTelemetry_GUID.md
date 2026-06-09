# SendBatteryAnalysisTelemetry(_GUID)

- ea: `0x18004fddc`
- end: `0x1800502fb`
- name: `?SendBatteryAnalysisTelemetry@@YAXU_GUID@@@Z`
- size: `1311`
- prototype: `void __fastcall(struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005e770`

## callees

- `0x180001ec0`
- `0x180001fb4`
- `0x1800056dc`
- `0x180008740`
- `0x18003742c`
- `0x18004ca90`
- `0x18004e1f0`
- `0x18004e4e0`
- `0x18004fcf0`
- `0x18004fd24`
- `0x18004fddc`
- `0x180053664`

## import_xrefs

- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x18004fe56`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x18004fe56`
- `ntdll!RtlGetPersistedStateLocation` at `0x18004fe9a`
- `ntdll!RtlGetPersistedStateLocation` at `0x18004fe9a`
- `ntdll!RtlNtStatusToDosError` at `0x18004fea2`
- `ntdll!RtlNtStatusToDosError` at `0x18004fea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050261`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180050267`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180050267`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004ff56`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004ff56`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004fefc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004fefc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800502a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800502a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800502b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800502b7`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18004ffcf`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18004ffcf`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18004ffac`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18004ffac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004ff12`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004ff12`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall SendBatteryAnalysisTelemetry(struct _GUID *a1)
{
  NTSTATUS PersistedStateLocation; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  LSTATUS ValueW; // eax
  struct _FILETIME v7; // rax
  struct _FILETIME v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 i; // rbx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  HKEY v15; // rcx
  _BYTE v16[4]; // [rsp+60h] [rbp-418h] BYREF
  int v17; // [rsp+64h] [rbp-414h] BYREF
  int v18; // [rsp+68h] [rbp-410h] BYREF
  int v19; // [rsp+6Ch] [rbp-40Ch] BYREF
  int v20; // [rsp+70h] [rbp-408h] BYREF
  __int64 pvData; // [rsp+78h] [rbp-400h] BYREF
  unsigned int v22; // [rsp+80h] [rbp-3F8h] BYREF
  DWORD pcbData; // [rsp+84h] [rbp-3F4h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-3F0h] BYREF
  BYTE Data[8]; // [rsp+90h] [rbp-3E8h] BYREF
  HKEY hkey; // [rsp+98h] [rbp-3E0h] BYREF
  int v27; // [rsp+A0h] [rbp-3D8h] BYREF
  struct _GUID *v28; // [rsp+A8h] [rbp-3D0h] BYREF
  struct _GUID *v29; // [rsp+B0h] [rbp-3C8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B8h] [rbp-3C0h] BYREF
  _BYTE v31[248]; // [rsp+D0h] [rbp-3A8h] BYREF
  __int64 v32; // [rsp+1C8h] [rbp-2B0h]
  __int64 v33; // [rsp+1D0h] [rbp-2A8h]
  __int64 v34; // [rsp+218h] [rbp-260h]
  __int64 v35; // [rsp+220h] [rbp-258h]
  WCHAR SubKey[264]; // [rsp+250h] [rbp-228h] BYREF

  v22 = 0;
  BatteryReportData::BatteryReportData((BatteryReportData *)v31);
  SystemTimeAsFileTime = 0;
  pcbData = 0;
  pvData = 0;
  SystemTime = 0;
  hkey = 0;
  *(_QWORD *)Data = 0;
  ProviderRegistrationGuard<&_tlgProvider_t const * const BatteryLoggingProvider>::ProviderRegistrationGuard<&_tlgProvider_t const * const BatteryLoggingProvider>(v16);
  if ( CoInitialize(0) >= 0 )
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"BatteryTelemetryAnalysis",
                               0,
                               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PowerEfficiencyDiagnostics",
                               0,
                               SubKey,
                               520,
                               &v22);
    if ( RtlNtStatusToDosError(PersistedStateLocation) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v4, v3, v5);
LABEL_30:
      CoUninitialize();
      goto LABEL_31;
    }
    if ( v22 > 0x208 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v4, v3, v5);
    if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hkey, 0) )
      goto LABEL_30;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    pcbData = 8;
    ValueW = RegGetValueW(hkey, 0, L"LastBatterySqmTime", 0x48u, 0, &pvData, &pcbData);
    if ( ValueW == 2 )
    {
      v7 = SystemTimeAsFileTime;
      v8 = SystemTimeAsFileTime;
      pvData = (__int64)SystemTimeAsFileTime;
    }
    else
    {
      if ( ValueW )
        goto LABEL_30;
      v7 = SystemTimeAsFileTime;
      v8 = (struct _FILETIME)pvData;
    }
    if ( *(_QWORD *)&v8 < *(_QWORD *)&v7 - 24192000000000LL )
      pvData = *(_QWORD *)&v7 - 24192000000000LL;
    if ( FileTimeToSystemTime((const FILETIME *)&pvData, &SystemTime)
      && (*(_QWORD *)&SystemTime.wHour = 0, SystemTimeToFileTime(&SystemTime, (LPFILETIME)&pvData)) )
    {
      *(_QWORD *)Data = pvData;
      if ( (int)QuerySrumHistoryData((struct BatteryReportData *)v31, pvData) >= 0
        && (int)CaptureBatteryState((struct ReportData *)v31) >= 0
        && v33 != v32
        && v35 != v34 )
      {
        if ( (unsigned int)dword_1800C6000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C6000, 0x400000000000LL) )
        {
          v17 = -1431655765 * ((v33 - v32) >> 6);
          v18 = *(_DWORD *)(v35 - 48);
          v19 = *(_DWORD *)(v35 - 52);
          v20 = *(_DWORD *)(v35 - 56);
          v28 = a1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v35,
            (__int64)&byte_1800B347F,
            v9,
            v10,
            (__int64 *)&v28,
            (__int64)&v20,
            (__int64)&v19,
            (__int64)&v18,
            (__int64)&v17);
        }
        for ( i = v34; i != v35 && *(_QWORD *)(i + 8) < *(unsigned __int64 *)&SystemTimeAsFileTime; i += 72 )
        {
          if ( (unsigned int)dword_1800C6000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C6000, 0x400000000000LL) )
          {
            v20 = v13;
            v19 = v14;
            v18 = *(_DWORD *)(i + 36);
            v17 = *(_DWORD *)(i + 28);
            v27 = *(_DWORD *)(i + 40);
            LODWORD(v28) = *(_DWORD *)(i + 32);
            v29 = a1;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v12,
              (__int64)&dword_1800B34FC,
              v13,
              v14,
              (__int64 *)&v29,
              (__int64)&v28,
              (__int64)&v27,
              (__int64)&v17,
              (__int64)&v18,
              (__int64)&v19,
              (__int64)&v20);
          }
          *(_QWORD *)Data = *(_QWORD *)(i + 8) + 1LL;
        }
      }
    }
    else
    {
      GetLastError();
    }
    goto LABEL_30;
  }
LABEL_31:
  v15 = hkey;
  if ( hkey )
  {
    if ( *(_QWORD *)Data )
    {
      RegSetValueExW(hkey, L"LastBatterySqmTime", 0, 0xBu, Data, 8u);
      v15 = hkey;
    }
    RegCloseKey(v15);
  }
  ProviderRegistrationGuard<&_tlgProvider_t const * const BatteryLoggingProvider>::~ProviderRegistrationGuard<&_tlgProvider_t const * const BatteryLoggingProvider>(v16);
  BatteryReportData::~BatteryReportData((BatteryReportData *)v31);
}

```

## disassembly

```asm
0x18004fddc  mov     [rsp+arg_0], rbx
0x18004fde1  mov     [rsp+arg_8], rsi
0x18004fde6  push    rdi
0x18004fde7  sub     rsp, 470h
0x18004fdee  mov     rax, cs:__security_cookie
0x18004fdf5  xor     rax, rsp
0x18004fdf8  mov     [rsp+478h+var_18], rax
0x18004fe00  mov     rsi, rcx
0x18004fe03  xor     edi, edi
0x18004fe05  mov     [rsp+478h+var_3F8], edi
0x18004fe0c  lea     rcx, [rsp+478h+var_3A8]; this
0x18004fe14  call    ??0BatteryReportData@@QEAA@XZ; BatteryReportData::BatteryReportData(void)
0x18004fe19  nop
0x18004fe1a  mov     qword ptr [rsp+478h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18004fe22  mov     [rsp+478h+pcbData], edi
0x18004fe29  mov     [rsp+478h+pvData], rdi
0x18004fe2e  xorps   xmm0, xmm0
0x18004fe31  movups  xmmword ptr [rsp+478h+SystemTime.wYear], xmm0
0x18004fe39  mov     [rsp+478h+hkey], rdi
0x18004fe41  mov     qword ptr [rsp+478h+Data], rdi
0x18004fe49  lea     rcx, [rsp+478h+var_418]
0x18004fe4e  call    ??0?$ProviderRegistrationGuard@$1?BatteryLoggingProvider@@3QEBU_tlgProvider_t@@EB@@QEAA@XZ; ProviderRegistrationGuard<&_tlgProvider_t const * const BatteryLoggingProvider>::ProviderRegistrationGuard<&_tlgProvider_t const * const BatteryLoggingProvider>(void)
0x18004fe53  nop
0x18004fe54  xor     ecx, ecx; pvReserved
0x18004fe56  call    cs:__imp_CoInitialize
0x18004fe5c  test    eax, eax
0x18004fe5e  js      loc_18005026D
0x18004fe64  lea     rax, [rsp+478h+var_3F8]
0x18004fe6c  mov     [rsp+478h+lpSecurityAttributes], rax
0x18004fe71  mov     ebx, 208h
0x18004fe76  mov     [rsp+478h+samDesired], ebx
0x18004fe7a  lea     rax, [rsp+478h+SubKey]
0x18004fe82  mov     qword ptr [rsp+478h+dwOptions], rax
0x18004fe87  xor     r9d, r9d
0x18004fe8a  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004fe91  xor     edx, edx
0x18004fe93  lea     rcx, aBatterytelemet; "BatteryTelemetryAnalysis"
0x18004fe9a  call    cs:__imp_RtlGetPersistedStateLocation
0x18004fea0  mov     ecx, eax; Status
0x18004fea2  call    cs:__imp_RtlNtStatusToDosError
0x18004fea8  test    eax, eax
0x18004feaa  jz      short loc_18004FEB6
0x18004feac  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004feb1  jmp     loc_180050267
0x18004feb6  cmp     [rsp+478h+var_3F8], ebx
0x18004febd  jbe     short loc_18004FEC4
0x18004febf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004fec4  mov     [rsp+478h+lpdwDisposition], rdi; lpdwDisposition
0x18004fec9  lea     rax, [rsp+478h+hkey]
0x18004fed1  mov     [rsp+478h+phkResult], rax; phkResult
0x18004fed6  mov     [rsp+478h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18004fedb  mov     [rsp+478h+samDesired], 0F003Fh; samDesired
0x18004fee3  mov     [rsp+478h+dwOptions], edi; dwOptions
0x18004fee7  xor     r9d, r9d; lpClass
0x18004feea  xor     r8d, r8d; Reserved
0x18004feed  lea     rdx, [rsp+478h+SubKey]; lpSubKey
0x18004fef5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004fefc  call    cs:__imp_RegCreateKeyExW
0x18004ff02  test    eax, eax
0x18004ff04  jnz     loc_180050267
0x18004ff0a  lea     rcx, [rsp+478h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004ff12  call    cs:__imp_GetSystemTimeAsFileTime
0x18004ff18  mov     [rsp+478h+pcbData], 8
0x18004ff23  lea     rax, [rsp+478h+pcbData]
0x18004ff2b  mov     [rsp+478h+lpSecurityAttributes], rax; pcbData
0x18004ff30  lea     rax, [rsp+478h+pvData]
0x18004ff35  mov     qword ptr [rsp+478h+samDesired], rax; pvData
0x18004ff3a  mov     qword ptr [rsp+478h+dwOptions], rdi; pdwType
0x18004ff3f  mov     r9d, 48h ; 'H'; dwFlags
0x18004ff45  lea     r8, aLastbatterysqm; "LastBatterySqmTime"
0x18004ff4c  xor     edx, edx; lpSubKey
0x18004ff4e  mov     rcx, [rsp+478h+hkey]; hkey
0x18004ff56  call    cs:__imp_RegGetValueW
0x18004ff5c  cmp     eax, 2
0x18004ff5f  jnz     short loc_18004FF73
0x18004ff61  mov     rax, qword ptr [rsp+478h+SystemTimeAsFileTime.dwLowDateTime]
0x18004ff69  mov     rcx, rax
0x18004ff6c  mov     [rsp+478h+pvData], rax
0x18004ff71  jmp     short loc_18004FF88
0x18004ff73  test    eax, eax
0x18004ff75  jnz     loc_180050267
0x18004ff7b  mov     rax, qword ptr [rsp+478h+SystemTimeAsFileTime.dwLowDateTime]
0x18004ff83  mov     rcx, [rsp+478h+pvData]
0x18004ff88  mov     rdx, 0FFFFE9FF5C6F0000h
0x18004ff92  add     rdx, rax
0x18004ff95  cmp     rcx, rdx
0x18004ff98  jge     short loc_18004FF9F
0x18004ff9a  mov     [rsp+478h+pvData], rdx
0x18004ff9f  lea     rdx, [rsp+478h+SystemTime]; lpSystemTime
0x18004ffa7  lea     rcx, [rsp+478h+pvData]; lpFileTime
0x18004ffac  call    cs:__imp_FileTimeToSystemTime
0x18004ffb2  test    eax, eax
0x18004ffb4  jz      loc_180050261
0x18004ffba  mov     qword ptr [rsp+478h+SystemTime.wHour], rdi
0x18004ffc2  lea     rdx, [rsp+478h+pvData]; lpFileTime
0x18004ffc7  lea     rcx, [rsp+478h+SystemTime]; lpSystemTime
0x18004ffcf  call    cs:__imp_SystemTimeToFileTime
0x18004ffd5  test    eax, eax
0x18004ffd7  jz      loc_180050261
0x18004ffdd  mov     rdx, [rsp+478h+pvData]; unsigned __int64
0x18004ffe2  mov     qword ptr [rsp+478h+Data], rdx
0x18004ffea  lea     rcx, [rsp+478h+var_3A8]; struct BatteryReportData *
0x18004fff2  call    ?QuerySrumHistoryData@@YAJAEAUBatteryReportData@@_K@Z; QuerySrumHistoryData(BatteryReportData &,unsigned __int64)
0x18004fff7  test    eax, eax
0x18004fff9  jns     short loc_180050000
0x18004fffb  jmp     loc_180050267
0x180050000  lea     rcx, [rsp+478h+var_3A8]; struct ReportData *
0x180050008  call    ?CaptureBatteryState@@YAJAEAUReportData@@@Z; CaptureBatteryState(ReportData &)
0x18005000d  test    eax, eax
0x18005000f  jns     short loc_180050016
0x180050011  jmp     loc_180050267
0x180050016  mov     rax, [rsp+478h+var_2A8]
0x18005001e  cmp     rax, [rsp+478h+var_2B0]
0x180050026  jz      loc_180050267
0x18005002c  mov     rax, [rsp+478h+var_258]
0x180050034  cmp     rax, [rsp+478h+var_260]
0x18005003c  jz      loc_180050267
0x180050042  mov     eax, cs:dword_1800C6000
0x180050048  cmp     eax, 5
0x18005004b  jbe     loc_1800500FB
0x180050051  mov     rdx, 400000000000h
0x18005005b  lea     rcx, dword_1800C6000
0x180050062  call    _tlgKeywordOn
0x180050067  test    al, al
0x180050069  jz      loc_1800500FB
0x18005006f  mov     rax, [rsp+478h+var_2A8]
0x180050077  sub     rax, [rsp+478h+var_2B0]
0x18005007f  sar     rax, 6
0x180050083  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18005008d  imul    rax, rcx
0x180050091  mov     [rsp+478h+var_414], eax
0x180050095  mov     rcx, [rsp+478h+var_258]
0x18005009d  mov     eax, [rcx-30h]
0x1800500a0  mov     [rsp+478h+var_410], eax
0x1800500a4  mov     eax, [rcx-34h]
0x1800500a7  mov     [rsp+478h+var_40C], eax
0x1800500ab  mov     eax, [rcx-38h]
0x1800500ae  mov     [rsp+478h+var_408], eax
0x1800500b2  mov     [rsp+478h+var_3D0], rsi
0x1800500ba  lea     rax, [rsp+478h+var_414]
0x1800500bf  mov     [rsp+478h+lpdwDisposition], rax
0x1800500c4  lea     rax, [rsp+478h+var_410]
0x1800500c9  mov     [rsp+478h+phkResult], rax
0x1800500ce  lea     rax, [rsp+478h+var_40C]
0x1800500d3  mov     [rsp+478h+lpSecurityAttributes], rax
0x1800500d8  lea     rax, [rsp+478h+var_408]
0x1800500dd  mov     qword ptr [rsp+478h+samDesired], rax
0x1800500e2  lea     rax, [rsp+478h+var_3D0]
0x1800500ea  mov     qword ptr [rsp+478h+dwOptions], rax
0x1800500ef  lea     rdx, byte_1800B347F
0x1800500f6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800500fb  mov     rbx, [rsp+478h+var_260]
0x180050103  cmp     rbx, [rsp+478h+var_258]
0x18005010b  jz      loc_180050267
0x180050111  mov     rax, qword ptr [rsp+478h+SystemTimeAsFileTime.dwLowDateTime]
0x180050119  cmp     [rbx+8], rax
0x18005011d  jnb     loc_180050267
0x180050123  cmp     [rbx+20h], edi
0x180050126  jbe     short loc_180050153
0x180050128  mov     ecx, edi
0x18005012a  cmp     [rbx+2Ch], edi
0x18005012d  setnbe  cl
0x180050130  mov     eax, edi
0x180050132  cmp     [rbx+34h], edi
0x180050135  setnbe  al
0x180050138  test    eax, ecx
0x18005013a  jz      short loc_180050153
0x18005013c  mov     eax, [rbx+2Ch]
0x18005013f  mov     ecx, [rbx+20h]
0x180050142  imul    rax, rcx
0x180050146  mov     ecx, [rbx+34h]
0x180050149  xor     edx, edx
0x18005014b  div     rcx
0x18005014e  mov     r9, rax
0x180050151  jmp     short loc_180050156
0x180050153  mov     r9, rdi
0x180050156  cmp     [rbx+28h], edi
0x180050159  jbe     short loc_180050186
0x18005015b  mov     ecx, edi
0x18005015d  cmp     [rbx+30h], edi
0x180050160  setnbe  cl
0x180050163  mov     eax, edi
0x180050165  cmp     [rbx+38h], edi
0x180050168  setnbe  al
0x18005016b  test    eax, ecx
0x18005016d  jz      short loc_180050186
0x18005016f  mov     eax, [rbx+30h]
0x180050172  mov     ecx, [rbx+28h]
0x180050175  imul    rax, rcx
0x180050179  mov     ecx, [rbx+38h]
0x18005017c  xor     edx, edx
0x18005017e  div     rcx
0x180050181  mov     r8, rax
0x180050184  jmp     short loc_180050189
0x180050186  mov     r8, rdi
0x180050189  mov     eax, cs:dword_1800C6000
0x18005018f  cmp     eax, 5
0x180050192  jbe     loc_180050245
0x180050198  mov     rdx, 400000000000h
0x1800501a2  lea     rcx, dword_1800C6000
0x1800501a9  call    _tlgKeywordOn
0x1800501ae  test    al, al
0x1800501b0  jz      loc_180050245
0x1800501b6  mov     [rsp+478h+var_408], r8d
0x1800501bb  mov     [rsp+478h+var_40C], r9d
0x1800501c0  mov     eax, [rbx+24h]
0x1800501c3  mov     [rsp+478h+var_410], eax
0x1800501c7  mov     eax, [rbx+1Ch]
0x1800501ca  mov     [rsp+478h+var_414], eax
0x1800501ce  mov     eax, [rbx+28h]
0x1800501d1  mov     [rsp+478h+var_3D8], eax
0x1800501d8  mov     eax, [rbx+20h]
0x1800501db  mov     dword ptr [rsp+478h+var_3D0], eax
0x1800501e2  mov     [rsp+478h+var_3C8], rsi
0x1800501ea  lea     rax, [rsp+478h+var_408]
0x1800501ef  mov     [rsp+478h+var_428], rax
0x1800501f4  lea     rax, [rsp+478h+var_40C]
0x1800501f9  mov     [rsp+478h+var_430], rax
0x1800501fe  lea     rax, [rsp+478h+var_410]
0x180050203  mov     [rsp+478h+lpdwDisposition], rax
0x180050208  lea     rax, [rsp+478h+var_414]
0x18005020d  mov     [rsp+478h+phkResult], rax
0x180050212  lea     rax, [rsp+478h+var_3D8]
0x18005021a  mov     [rsp+478h+lpSecurityAttributes], rax
0x18005021f  lea     rax, [rsp+478h+var_3D0]
0x180050227  mov     qword ptr [rsp+478h+samDesired], rax
0x18005022c  lea     rax, [rsp+478h+var_3C8]
0x180050234  mov     qword ptr [rsp+478h+dwOptions], rax
0x180050239  lea     rdx, dword_1800B34FC
0x180050240  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@44444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180050245  mov     rax, [rbx+8]
0x180050249  inc     rax
0x18005024c  mov     qword ptr [rsp+478h+Data], rax
0x180050254  add     rbx, 48h ; 'H'
0x180050258  jmp     loc_180050103
0x18005025d  xor     edi, edi
0x18005025f  jmp     short loc_180050267
0x180050261  call    cs:__imp_GetLastError
0x180050267  call    cs:__imp_CoUninitialize
0x18005026d  mov     rcx, [rsp+478h+hkey]; hKey
0x180050275  test    rcx, rcx
0x180050278  jz      short loc_1800502BE
0x18005027a  cmp     qword ptr [rsp+478h+Data], rdi
0x180050282  jbe     short loc_1800502B7
0x180050284  mov     [rsp+478h+samDesired], 8; cbData
0x18005028c  lea     rax, [rsp+478h+Data]
0x180050294  mov     qword ptr [rsp+478h+dwOptions], rax; lpData
0x180050299  mov     r9d, 0Bh; dwType
0x18005029f  xor     r8d, r8d; Reserved
0x1800502a2  lea     rdx, aLastbatterysqm; "LastBatterySqmTime"
0x1800502a9  call    cs:__imp_RegSetValueExW
0x1800502af  mov     rcx, [rsp+478h+hkey]; hKey
0x1800502b7  call    cs:__imp_RegCloseKey
0x1800502bd  nop
0x1800502be  lea     rcx, [rsp+478h+var_418]
0x1800502c3  call    ??1?$ProviderRegistrationGuard@$1?BatteryLoggingProvider@@3QEBU_tlgProvider_t@@EB@@QEAA@XZ; ProviderRegistrationGuard<&_tlgProvider_t const * const BatteryLoggingProvider>::~ProviderRegistrationGuard<&_tlgProvider_t const * const BatteryLoggingProvider>(void)
0x1800502c8  nop
0x1800502c9  lea     rcx, [rsp+478h+var_3A8]; this
0x1800502d1  call    ??1BatteryReportData@@UEAA@XZ; BatteryReportData::~BatteryReportData(void)
0x1800502d6  mov     rcx, [rsp+478h+var_18]
0x1800502de  xor     rcx, rsp; StackCookie
0x1800502e1  call    __security_check_cookie
0x1800502e6  lea     r11, [rsp+478h+var_8]
0x1800502ee  mov     rbx, [r11+10h]
0x1800502f2  mov     rsi, [r11+18h]
0x1800502f6  mov     rsp, r11
0x1800502f9  pop     rdi
0x1800502fa  retn
```
