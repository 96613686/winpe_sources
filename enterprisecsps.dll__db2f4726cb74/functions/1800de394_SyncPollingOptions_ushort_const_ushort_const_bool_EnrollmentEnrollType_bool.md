# SyncPollingOptions(ushort const *,ushort const *,bool,EnrollmentEnrollType,bool)

- ea: `0x1800de394`
- end: `0x1800de85d`
- name: `?SyncPollingOptions@@YAJPEBG0_NW4EnrollmentEnrollType@@1@Z`
- size: `1225`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002e510`

## callees

- `0x180008de0`
- `0x18000d4d4`
- `0x180015e90`
- `0x180025ac0`
- `0x18002dcc8`
- `0x1800d11a4`
- `0x1800d1214`
- `0x1800d12ac`
- `0x1800d1344`
- `0x1800d71f4`
- `0x1800d72d0`
- `0x1800d7d1c`
- `0x1800da990`
- `0x1800daca0`
- `0x1800dbe9c`
- `0x1800ddecc`
- `0x1800de394`
- `0x1800dffac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800de7e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800de7e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800de7a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800de7a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800de70d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800de70d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800de515`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800de515`

## string_xrefs

- `0x1800de4d6`: `Schedule #1 created by enrollment client`
- `0x1800de5b6`: `Schedule #2 created by enrollment client`
- `0x1800de66f`: `Schedule #3 created by enrollment client`
- `0x1800de6f0`: `Maintenance Schedule created by enrollment client`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SyncPollingOptions(const unsigned __int16 *a1)
{
  int v2; // edi
  int i; // r14d
  unsigned int PollValueFromRegistry; // ebx
  __int64 j; // rbx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rbx
  unsigned int v10; // edi
  CEnrollmentLogger *v11; // rax
  CEnrollmentLogger *Logger; // rax
  unsigned int v13; // r12d
  __int64 v14; // r14
  __int64 v15; // r15
  CEnrollmentLogger *v16; // rax
  unsigned int v17; // ecx
  unsigned int v18; // r13d
  unsigned int v19; // r12d
  int DeviceEnrollerKey; // eax
  LSTATUS ValueW; // eax
  CEnrollmentLogger *v22; // rax
  int lpData; // [rsp+20h] [rbp-91h]
  int pcbData; // [rsp+30h] [rbp-81h]
  int pcbDataa; // [rsp+30h] [rbp-81h]
  int pcbDatab; // [rsp+30h] [rbp-81h]
  int pcbDatac; // [rsp+30h] [rbp-81h]
  int v28; // [rsp+38h] [rbp-79h]
  int v29; // [rsp+38h] [rbp-79h]
  int v30; // [rsp+38h] [rbp-79h]
  int v31; // [rsp+38h] [rbp-79h]
  int Data; // [rsp+50h] [rbp-61h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-59h] BYREF
  _BYTE v34[8]; // [rsp+60h] [rbp-51h] BYREF
  unsigned int v35; // [rsp+68h] [rbp-49h] BYREF
  unsigned int v36; // [rsp+6Ch] [rbp-45h] BYREF
  DWORD v37; // [rsp+70h] [rbp-41h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+78h] [rbp-39h] BYREF
  __int128 pvData; // [rsp+88h] [rbp-29h] BYREF
  unsigned int v40[4]; // [rsp+98h] [rbp-19h] BYREF
  unsigned int v41[4]; // [rsp+A8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  *(_OWORD *)v40 = 0;
  *(_OWORD *)v41 = 0;
  Data = 0;
  v35 = 0;
  v36 = 0;
  v2 = 0;
  hkey = 0;
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v34, "SyncPollingOptions");
  for ( i = 0; i < 8; ++i )
  {
    PollValueFromRegistry = GetPollValueFromRegistry(a1, (LPCWSTR)(&g_RegistryKeyNames)[i], &v40[i]);
    Data = PollValueFromRegistry;
    if ( (int)(PollValueFromRegistry + 0x80000000) >= 0 && PollValueFromRegistry != -2147024894 )
    {
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v34);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return PollValueFromRegistry;
    }
    if ( PollValueFromRegistry != -2147024894 )
      v2 = 1;
  }
  if ( !v2 )
  {
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v34);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return 1;
  }
  ClearSchedulesAfterInfinite(v40);
  for ( j = 0; j != 8; ++j )
  {
    SetPollValueToRegistry(a1, (LPCWSTR)(&g_RegistryKeyNames)[j], v40[j]);
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
      McTemplateU0zq_EventWriteTransfer(v8, v7, (&g_RegistryKeyNames)[j], v40[j]);
  }
  v9 = v40[0];
  v10 = v40[1];
  Data = ScheduleOneOmaDmSession(
           a1,
           L"Schedule #1 created by enrollment client",
           v40[1],
           v40[0],
           v40[0],
           0,
           pcbData,
           v28,
           1,
           0);
  if ( Data >= 0 )
  {
    Data = ULongLongToULong(v9 * (v10 + 1), &v35);
    if ( Data < 0
      || (v13 = v35,
          v14 = v40[2],
          v15 = v40[3],
          Data = ScheduleOneOmaDmSession(
                   a1,
                   L"Schedule #2 created by enrollment client",
                   v40[3],
                   v40[2],
                   v35,
                   0,
                   pcbDataa,
                   v29,
                   1,
                   0),
          Data < 0) )
    {
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(Logger, Data);
      PollValueFromRegistry = Data;
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v34);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    }
    else
    {
      Data = ULongLongToULong(v15 * v14, &v36);
      if ( Data >= 0 )
      {
        v17 = v36 + v13;
        if ( v36 + v13 < v36 )
        {
          v22 = CEnrollmentLogger::GetLogger();
          CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(v22, -2147024362);
          PollValueFromRegistry = -2147024362;
          EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v34);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          return PollValueFromRegistry;
        }
        v18 = v41[0];
        v19 = v41[1];
        Data = ScheduleOneOmaDmSession(
                 a1,
                 L"Schedule #3 created by enrollment client",
                 v41[1],
                 v41[0],
                 v17,
                 0,
                 pcbDatab,
                 v30,
                 0,
                 0);
        if ( Data >= 0 )
        {
          if ( (v19 || !v18) && ((_DWORD)v15 || !(_DWORD)v14) && (v10 || !(_DWORD)v9) )
            Data = ScheduleOneOmaDmSession(
                     a1,
                     L"Maintenance Schedule created by enrollment client",
                     1u,
                     1u,
                     0,
                     1,
                     pcbDatac,
                     v31,
                     1,
                     0);
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &hkey,
            0);
          DeviceEnrollerKey = GetDeviceEnrollerKey(a1, &hkey);
          PollValueFromRegistry = DeviceEnrollerKey;
          if ( DeviceEnrollerKey >= 0 )
          {
            pvData = 0;
            v37 = 16;
            ValueW = RegGetValueW(hkey, 0, L"FirstScheduleTimestamp", 8u, 0, &pvData, &v37);
            PollValueFromRegistry = ValueW;
            if ( ValueW > 0 )
              PollValueFromRegistry = (unsigned __int16)ValueW | 0x80070000;
            Data = PollValueFromRegistry;
            if ( (PollValueFromRegistry & 0x80000000) != 0 )
            {
              PollValueFromRegistry = RegSetValueExW(
                                        hkey,
                                        L"FirstScheduleTimestamp",
                                        0,
                                        3u,
                                        (const BYTE *)&SystemTime,
                                        0x10u);
              Data = PollValueFromRegistry;
            }
            EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v34);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC9F,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
              (const char *)(unsigned int)DeviceEnrollerKey,
              lpData);
            EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v34);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          }
          return PollValueFromRegistry;
        }
      }
      v16 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(v16, Data);
      PollValueFromRegistry = Data;
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v34);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    }
  }
  else
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"ScheduleOneOmaDmSession", 4u, &Data, 4u);
    v11 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollScheduleSetupFail(v11, Data);
    PollValueFromRegistry = Data;
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v34);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  }
  return PollValueFromRegistry;
}

```

## disassembly

```asm
0x1800de394  push    rbp
0x1800de396  push    rbx
0x1800de397  push    rsi
0x1800de398  push    rdi
0x1800de399  push    r12
0x1800de39b  push    r13
0x1800de39d  push    r14
0x1800de39f  push    r15
0x1800de3a1  lea     rbp, [rsp-17h]
0x1800de3a6  sub     rsp, 0C8h
0x1800de3ad  mov     rax, cs:__security_cookie
0x1800de3b4  xor     rax, rsp
0x1800de3b7  mov     [rbp+4Fh+var_48], rax
0x1800de3bb  mov     rsi, rcx
0x1800de3be  xorps   xmm0, xmm0
0x1800de3c1  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x1800de3c5  movups  xmmword ptr [rbp+4Fh+var_58], xmm0
0x1800de3c9  xor     r13d, r13d
0x1800de3cc  mov     [rbp+4Fh+Data], r13d
0x1800de3d0  mov     [rbp+4Fh+var_98], r13d
0x1800de3d4  mov     [rbp+4Fh+var_94], r13d
0x1800de3d8  mov     edi, r13d
0x1800de3db  mov     [rbp+4Fh+hkey], r13
0x1800de3df  lea     rdx, aSyncpollingopt_0; "SyncPollingOptions"
0x1800de3e6  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800de3ea  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x1800de3ef  mov     r14d, r13d
0x1800de3f2  lea     r12, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x1800de3f9  lea     r15d, [r13+1]
0x1800de3fd  cmp     r14d, 8
0x1800de401  jge     short loc_1800DE45A
0x1800de403  movsxd  rdx, r14d
0x1800de406  lea     r8, [rbp+4Fh+var_68]
0x1800de40a  lea     r8, [r8+rdx*4]; unsigned int *
0x1800de40e  mov     rdx, [r12+rdx*8]; lpValue
0x1800de412  mov     rcx, rsi; unsigned __int16 *
0x1800de415  call    ?GetPollValueFromRegistry@@YAJPEBG0PEAK@Z; GetPollValueFromRegistry(ushort const *,ushort const *,ulong *)
0x1800de41a  mov     ebx, eax
0x1800de41c  mov     [rbp+4Fh+Data], eax
0x1800de41f  mov     ecx, 80000000h
0x1800de424  add     eax, ecx
0x1800de426  test    ecx, eax
0x1800de428  jnz     short loc_1800DE432
0x1800de42a  cmp     ebx, 80070002h
0x1800de430  jnz     short loc_1800DE441
0x1800de432  cmp     ebx, 80070002h
0x1800de438  cmovnz  edi, r15d
0x1800de43c  add     r14d, r15d
0x1800de43f  jmp     short loc_1800DE3FD
0x1800de441  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800de445  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800de44a  nop
0x1800de44b  lea     rcx, [rbp+4Fh+hkey]
0x1800de44f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800de454  nop
0x1800de455  jmp     loc_1800DE83A
0x1800de45a  test    edi, edi
0x1800de45c  jnz     short loc_1800DE47A
0x1800de45e  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800de462  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800de467  nop
0x1800de468  lea     rcx, [rbp+4Fh+hkey]
0x1800de46c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800de471  nop
0x1800de472  mov     eax, r15d
0x1800de475  jmp     loc_1800DE83C
0x1800de47a  lea     rcx, [rbp+4Fh+var_68]
0x1800de47e  call    ClearSchedulesAfterInfinite
0x1800de483  mov     rbx, r13
0x1800de486  mov     r8d, [rbp+rbx*4+4Fh+var_68]; unsigned int
0x1800de48b  mov     rdx, [r12+rbx*8]; lpValueName
0x1800de48f  mov     rcx, rsi; unsigned __int16 *
0x1800de492  call    ?SetPollValueToRegistry@@YAJPEBG0K@Z; SetPollValueToRegistry(ushort const *,ushort const *,ulong)
0x1800de497  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x1800de49e  jz      short loc_1800DE4AE
0x1800de4a0  mov     r9d, [rbp+rbx*4+4Fh+var_68]
0x1800de4a5  mov     r8, [r12+rbx*8]
0x1800de4a9  call    McTemplateU0zq_EventWriteTransfer
0x1800de4ae  add     rbx, r15
0x1800de4b1  cmp     rbx, 8
0x1800de4b5  jnz     short loc_1800DE486
0x1800de4b7  mov     [rsp+100h+var_B8], r13d; int
0x1800de4bc  mov     [rsp+100h+var_C0], r15d; int
0x1800de4c1  mov     [rsp+100h+cbData], r13d; int
0x1800de4c6  mov     ebx, [rbp+4Fh+var_68]
0x1800de4c9  mov     dword ptr [rsp+100h+lpData], ebx; unsigned int
0x1800de4cd  mov     r9d, ebx; unsigned int
0x1800de4d0  mov     edi, [rbp+4Fh+var_68+4]
0x1800de4d3  mov     r8d, edi; unsigned int
0x1800de4d6  lea     rdx, aSchedule1Creat; "Schedule #1 created by enrollment clien"...
0x1800de4dd  mov     rcx, rsi; unsigned __int16 *
0x1800de4e0  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x1800de4e5  mov     [rbp+4Fh+Data], eax
0x1800de4e8  test    eax, eax
0x1800de4ea  jns     short loc_1800DE54D
0x1800de4ec  mov     r9d, 4; dwType
0x1800de4f2  mov     [rsp+100h+cbData], r9d; cbData
0x1800de4f7  lea     rax, [rbp+4Fh+Data]
0x1800de4fb  mov     [rsp+100h+lpData], rax; lpData
0x1800de500  lea     r8, aScheduleoneoma; "ScheduleOneOmaDmSession"
0x1800de507  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x1800de50e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800de515  call    cs:__imp_RegSetKeyValueW
0x1800de51c  nop     dword ptr [rax+rax+00h]
0x1800de521  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800de526  mov     edx, [rbp+4Fh+Data]; int
0x1800de529  mov     rcx, rax; this
0x1800de52c  call    ?LogDMPollScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollScheduleSetupFail(long)
0x1800de531  mov     ebx, [rbp+4Fh+Data]
0x1800de534  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800de538  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800de53d  nop
0x1800de53e  lea     rcx, [rbp+4Fh+hkey]
0x1800de542  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800de547  nop
0x1800de548  jmp     loc_1800DE83A
0x1800de54d  lea     ecx, [rdi+1]
0x1800de550  imul    rcx, rbx; unsigned __int64
0x1800de554  lea     rdx, [rbp+4Fh+var_98]; unsigned int *
0x1800de558  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800de55d  mov     [rbp+4Fh+Data], eax
0x1800de560  test    eax, eax
0x1800de562  jns     short loc_1800DE590
0x1800de564  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800de569  mov     edx, [rbp+4Fh+Data]; int
0x1800de56c  mov     rcx, rax; this
0x1800de56f  call    ?LogDMPollAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(long)
0x1800de574  mov     ebx, [rbp+4Fh+Data]
0x1800de577  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800de57b  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800de580  nop
0x1800de581  lea     rcx, [rbp+4Fh+hkey]
0x1800de585  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800de58a  nop
0x1800de58b  jmp     loc_1800DE83A
0x1800de590  mov     [rsp+100h+var_B8], r13d; int
0x1800de595  mov     [rsp+100h+var_C0], r15d; int
0x1800de59a  mov     [rsp+100h+cbData], r13d; int
0x1800de59f  mov     r12d, [rbp+4Fh+var_98]
0x1800de5a3  mov     dword ptr [rsp+100h+lpData], r12d; unsigned int
0x1800de5a8  mov     r14d, [rbp+4Fh+var_68+8]
0x1800de5ac  mov     r9d, r14d; unsigned int
0x1800de5af  mov     r15d, [rbp+4Fh+var_68+0Ch]
0x1800de5b3  mov     r8d, r15d; unsigned int
0x1800de5b6  lea     rdx, aSchedule2Creat; "Schedule #2 created by enrollment clien"...
0x1800de5bd  mov     rcx, rsi; unsigned __int16 *
0x1800de5c0  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x1800de5c5  mov     [rbp+4Fh+Data], eax
0x1800de5c8  test    eax, eax
0x1800de5ca  jns     short loc_1800DE5F8
0x1800de5cc  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800de5d1  mov     edx, [rbp+4Fh+Data]; int
0x1800de5d4  mov     rcx, rax; this
0x1800de5d7  call    ?LogDMPollAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(long)
0x1800de5dc  mov     ebx, [rbp+4Fh+Data]
0x1800de5df  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800de5e3  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800de5e8  nop
0x1800de5e9  lea     rcx, [rbp+4Fh+hkey]
0x1800de5ed  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800de5f2  nop
0x1800de5f3  jmp     loc_1800DE83A
0x1800de5f8  mov     rcx, r14
0x1800de5fb  imul    rcx, r15; unsigned __int64
0x1800de5ff  lea     rdx, [rbp+4Fh+var_94]; unsigned int *
0x1800de603  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800de608  mov     [rbp+4Fh+Data], eax
0x1800de60b  test    eax, eax
0x1800de60d  jns     short loc_1800DE63B
0x1800de60f  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800de614  mov     edx, [rbp+4Fh+Data]; int
0x1800de617  mov     rcx, rax; this
0x1800de61a  call    ?LogDMPollSecondAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(long)
0x1800de61f  mov     ebx, [rbp+4Fh+Data]
0x1800de622  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800de626  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800de62b  nop
0x1800de62c  lea     rcx, [rbp+4Fh+hkey]
0x1800de630  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800de635  nop
0x1800de636  jmp     loc_1800DE83A
0x1800de63b  mov     eax, [rbp+4Fh+var_94]
0x1800de63e  lea     ecx, [rax+r12]
0x1800de642  cmp     ecx, eax
0x1800de644  jb      loc_1800DE80C
0x1800de64a  mov     [rbp+4Fh+Data], r13d
0x1800de64e  mov     [rsp+100h+var_B8], r13d; int
0x1800de653  mov     [rsp+100h+var_C0], r13d; int
0x1800de658  mov     [rsp+100h+cbData], r13d; int
0x1800de65d  mov     dword ptr [rsp+100h+lpData], ecx; unsigned int
0x1800de661  mov     r13d, [rbp+4Fh+var_58]
0x1800de665  mov     r9d, r13d; unsigned int
0x1800de668  mov     r12d, [rbp+4Fh+var_58+4]
0x1800de66c  mov     r8d, r12d; unsigned int
0x1800de66f  lea     rdx, aSchedule3Creat; "Schedule #3 created by enrollment clien"...
0x1800de676  mov     rcx, rsi; unsigned __int16 *
0x1800de679  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x1800de67e  mov     [rbp+4Fh+Data], eax
0x1800de681  test    eax, eax
0x1800de683  jns     short loc_1800DE6B1
0x1800de685  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800de68a  mov     edx, [rbp+4Fh+Data]; int
0x1800de68d  mov     rcx, rax; this
0x1800de690  call    ?LogDMPollSecondAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(long)
0x1800de695  mov     ebx, [rbp+4Fh+Data]
0x1800de698  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800de69c  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800de6a1  nop
0x1800de6a2  lea     rcx, [rbp+4Fh+hkey]
0x1800de6a6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800de6ab  nop
0x1800de6ac  jmp     loc_1800DE83A
0x1800de6b1  test    r12d, r12d
0x1800de6b4  jnz     short loc_1800DE6BB
0x1800de6b6  test    r13d, r13d
0x1800de6b9  jnz     short loc_1800DE702
0x1800de6bb  test    r15d, r15d
0x1800de6be  jnz     short loc_1800DE6C5
0x1800de6c0  test    r14d, r14d
0x1800de6c3  jnz     short loc_1800DE702
0x1800de6c5  test    edi, edi
0x1800de6c7  jnz     short loc_1800DE6CD
0x1800de6c9  test    ebx, ebx
0x1800de6cb  jnz     short loc_1800DE702
0x1800de6cd  mov     [rsp+100h+var_B8], 0; int
0x1800de6d5  mov     r8d, 1; unsigned int
0x1800de6db  mov     [rsp+100h+var_C0], r8d; int
0x1800de6e0  mov     [rsp+100h+cbData], r8d; int
0x1800de6e5  mov     dword ptr [rsp+100h+lpData], 0; int
0x1800de6ed  mov     r9d, r8d; unsigned int
0x1800de6f0  lea     rdx, aMaintenanceSch; "Maintenance Schedule created by enrollm"...
0x1800de6f7  mov     rcx, rsi; unsigned __int16 *
0x1800de6fa  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x1800de6ff  mov     [rbp+4Fh+Data], eax
0x1800de702  xorps   xmm0, xmm0
0x1800de705  movups  xmmword ptr [rbp+4Fh+SystemTime.wYear], xmm0
0x1800de709  lea     rcx, [rbp+4Fh+SystemTime]; lpSystemTime
0x1800de70d  call    cs:__imp_GetSystemTime
0x1800de714  nop     dword ptr [rax+rax+00h]
0x1800de719  xor     edx, edx
0x1800de71b  lea     rcx, [rbp+4Fh+hkey]
0x1800de71f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800de724  lea     rdx, [rbp+4Fh+hkey]; HKEY *
0x1800de728  mov     rcx, rsi; pszMore
0x1800de72b  call    ?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)
0x1800de730  mov     ebx, eax
0x1800de732  test    eax, eax
0x1800de734  jns     short loc_1800DE767
0x1800de736  mov     rcx, [rbp+57h]; this
0x1800de73a  mov     r9d, eax; char *
0x1800de73d  lea     r8, aOnecoreuapAdmi_82; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800de744  mov     edx, 0C9Fh; void *
0x1800de749  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800de74e  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800de752  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800de757  nop
0x1800de758  lea     rcx, [rbp+4Fh+hkey]
0x1800de75c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800de761  nop
0x1800de762  jmp     loc_1800DE83A
0x1800de767  xorps   xmm0, xmm0
0x1800de76a  movups  [rbp+4Fh+pvData], xmm0
0x1800de76e  mov     edi, 10h
0x1800de773  mov     [rbp+4Fh+var_90], edi
0x1800de776  lea     rax, [rbp+4Fh+var_90]
0x1800de77a  mov     [rsp+100h+pcbData], rax; pcbData
0x1800de77f  lea     rax, [rbp+4Fh+pvData]
0x1800de783  mov     qword ptr [rsp+100h+cbData], rax; pvData
0x1800de788  mov     [rsp+100h+lpData], 0; pdwType
0x1800de791  lea     r9d, [rdi-8]; dwFlags
0x1800de795  lea     r8, aFirstschedulet; "FirstScheduleTimestamp"
0x1800de79c  xor     edx, edx; lpSubKey
0x1800de79e  mov     rcx, [rbp+4Fh+hkey]; hkey
0x1800de7a2  call    cs:__imp_RegGetValueW
0x1800de7a9  nop     dword ptr [rax+rax+00h]
0x1800de7ae  mov     ebx, eax
0x1800de7b0  test    eax, eax
0x1800de7b2  jle     short loc_1800DE7BD
0x1800de7b4  movzx   ebx, ax
0x1800de7b7  or      ebx, 80070000h
0x1800de7bd  mov     [rbp+4Fh+Data], ebx
0x1800de7c0  test    ebx, ebx
0x1800de7c2  jns     short loc_1800DE7F6
0x1800de7c4  mov     [rsp+100h+cbData], edi; cbData
0x1800de7c8  lea     rax, [rbp+4Fh+SystemTime]
0x1800de7cc  mov     [rsp+100h+lpData], rax; lpData
0x1800de7d1  mov     r9d, 3; dwType
0x1800de7d7  xor     r8d, r8d; Reserved
0x1800de7da  lea     rdx, aFirstschedulet; "FirstScheduleTimestamp"
0x1800de7e1  mov     rcx, [rbp+4Fh+hkey]; hKey
0x1800de7e5  call    cs:__imp_RegSetValueExW
0x1800de7ec  nop     dword ptr [rax+rax+00h]
0x1800de7f1  mov     ebx, eax
0x1800de7f3  mov     [rbp+4Fh+Data], eax
0x1800de7f6  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800de7fa  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800de7ff  nop
0x1800de800  lea     rcx, [rbp+4Fh+hkey]
0x1800de804  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800de809  nop
  ... truncated ...
```
