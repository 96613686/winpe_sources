# SyncPollingOptions(ushort const *,ushort const *,bool,EnrollmentEnrollType,bool)

- ea: `0x18001c054`
- end: `0x18001c613`
- name: `?SyncPollingOptions@@YAJPEBG0_NW4EnrollmentEnrollType@@1@Z`
- size: `1471`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000be00`

## callees

- `0x1800022e0`
- `0x180006294`
- `0x1800097fc`
- `0x180011ccc`
- `0x180017558`
- `0x1800178d4`
- `0x180019904`
- `0x18001a1c4`
- `0x18001bc64`
- `0x18001c054`
- `0x18001d2a4`
- `0x18001dce8`
- `0x18001dd4c`
- `0x18001ddc8`
- `0x18001de38`
- `0x18001df24`
- `0x18001dfa0`
- `0x18001e08c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001c489`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001c489`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c552`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c552`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c4d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c56f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c4d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c56f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c516`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c516`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001c252`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001c252`

## string_xrefs

- `0x18001c213`: `Schedule #1 created by enrollment client`
- `0x18001c2ae`: `Schedule #2 created by enrollment client`
- `0x18001c328`: `Schedule #3 created by enrollment client`
- `0x18001c3a1`: `Maintenance Schedule created by enrollment client`

## pseudocode

```c
__int64 __fastcall SyncPollingOptions(unsigned __int16 *a1, __int64 a2, __int64 a3, int a4)
{
  int v5; // esi
  __int64 v6; // r14
  unsigned int PollValueFromRegistry; // ebx
  unsigned int v9; // esi
  int v10; // ebx
  int v11; // r13d
  unsigned int v12; // r12d
  __int64 i; // r14
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r15
  CEnrollmentLogger *Logger; // rax
  unsigned __int64 v18; // r14
  CEnrollmentLogger *v19; // rax
  unsigned __int64 v20; // rcx
  unsigned int v21; // r14d
  CEnrollmentLogger *v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rsi
  CEnrollmentLogger *v25; // rax
  CEnrollmentLogger *v26; // rax
  CEnrollmentLogger *v27; // rax
  int DeviceEnrollerKey; // eax
  HKEY v29; // rbx
  LSTATUS ValueW; // eax
  int v31; // edi
  CEnrollmentLogger *v32; // rax
  CEnrollmentLogger *v33; // rax
  unsigned int lpData; // [rsp+20h] [rbp-A1h]
  int pcbData; // [rsp+30h] [rbp-91h]
  int pcbDataa; // [rsp+30h] [rbp-91h]
  int pcbDatab; // [rsp+30h] [rbp-91h]
  int pcbDatac; // [rsp+30h] [rbp-91h]
  int v39; // [rsp+38h] [rbp-89h]
  int v40; // [rsp+38h] [rbp-89h]
  int v41; // [rsp+38h] [rbp-89h]
  int v42; // [rsp+38h] [rbp-89h]
  int Data; // [rsp+50h] [rbp-71h] BYREF
  const char *v44; // [rsp+58h] [rbp-69h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-61h] BYREF
  unsigned int v46[4]; // [rsp+68h] [rbp-59h] BYREF
  __int128 v47; // [rsp+78h] [rbp-49h]
  unsigned int v48; // [rsp+88h] [rbp-39h]
  DWORD v49; // [rsp+8Ch] [rbp-35h] BYREF
  __int64 v50; // [rsp+90h] [rbp-31h]
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-29h] BYREF
  __int128 pvData; // [rsp+A8h] [rbp-19h] BYREF
  _BYTE v53[16]; // [rsp+B8h] [rbp-9h] BYREF
  const char *v54; // [rsp+C8h] [rbp+7h]
  __int64 v55; // [rsp+D0h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  LODWORD(hKey) = a4;
  v50 = a2;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  Data = 0;
  v5 = 0;
  v44 = "SyncPollingOptions";
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
  {
    v54 = "SyncPollingOptions";
    v55 = 19;
    McGenEventWrite_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, EnteringScopeEvent, a3, 2, v53);
  }
  v6 = 0;
  do
  {
    PollValueFromRegistry = GetPollValueFromRegistry(a1, (LPCWSTR)(&g_RegistryKeyNames)[v6], &v46[v6]);
    Data = PollValueFromRegistry;
    if ( ((PollValueFromRegistry + 0x80000000) & 0x80000000) == 0 && PollValueFromRegistry != -2147024894 )
    {
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v44);
      return PollValueFromRegistry;
    }
    if ( PollValueFromRegistry != -2147024894 )
      v5 = 1;
    v6 = (unsigned int)(v6 + 1);
  }
  while ( (int)v6 < 8 );
  if ( !v5 )
  {
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v44);
    return 1;
  }
  if ( v46[1] || !v46[0] )
  {
    v10 = v47;
    v9 = v46[2];
  }
  else
  {
    v9 = 0;
    v46[2] = 0;
    v10 = 0;
    LODWORD(v47) = 0;
  }
  if ( !v46[3] )
  {
    if ( v9 )
      v10 = 0;
    LODWORD(v47) = v10;
  }
  v11 = v46[0] != 0 ? v46[1] : 0;
  v46[1] = v11;
  v12 = v9 != 0 ? v46[3] : 0;
  v46[3] = v12;
  v48 = v10 != 0 ? DWORD1(v47) : 0;
  DWORD1(v47) = v48;
  for ( i = 0; i != 8; ++i )
  {
    SetPollValueToRegistry(a1, (LPCWSTR)(&g_RegistryKeyNames)[i], v46[i]);
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
      McTemplateU0zq_EventWriteTransfer(v15, v14, (&g_RegistryKeyNames)[i], v46[i]);
  }
  v16 = v46[0];
  Data = ScheduleOneOmaDmSession(
           a1,
           L"Schedule #1 created by enrollment client",
           v11,
           v46[0],
           v46[0],
           0,
           pcbData,
           v39,
           1,
           0);
  if ( Data < 0 )
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"ScheduleOneOmaDmSession", 4u, &Data, 4u);
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollScheduleSetupFail(Logger, Data);
    PollValueFromRegistry = Data;
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v44);
    return PollValueFromRegistry;
  }
  v18 = v16 * (unsigned int)(v11 + 1);
  if ( v18 > 0xFFFFFFFF )
  {
    v33 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(v33, -2147024362);
    PollValueFromRegistry = -2147024362;
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v44);
    return PollValueFromRegistry;
  }
  Data = ScheduleOneOmaDmSession(
           a1,
           L"Schedule #2 created by enrollment client",
           v12,
           v9,
           (int)v16 * (v11 + 1),
           0,
           pcbDataa,
           v40,
           1,
           0);
  if ( Data < 0 )
  {
    v19 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(v19, Data);
    PollValueFromRegistry = Data;
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v44);
    return PollValueFromRegistry;
  }
  v20 = v9 * (unsigned __int64)v12;
  if ( v20 > 0xFFFFFFFF || (int)v20 + (int)v18 < (unsigned int)v20 )
  {
    v32 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(v32, -2147024362);
    PollValueFromRegistry = -2147024362;
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v44);
    return PollValueFromRegistry;
  }
  lpData = v20 + v18;
  v21 = v48;
  Data = ScheduleOneOmaDmSession(
           a1,
           L"Schedule #3 created by enrollment client",
           v48,
           v10,
           lpData,
           0,
           pcbDatab,
           v41,
           0,
           0);
  if ( Data < 0 )
  {
    v22 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(v22, Data);
    PollValueFromRegistry = Data;
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v44);
    return PollValueFromRegistry;
  }
  if ( (v21 || !v10) && (v12 || !v9) && (v11 || !(_DWORD)v16) )
    Data = ScheduleOneOmaDmSession(
             a1,
             L"Maintenance Schedule created by enrollment client",
             1,
             1,
             0,
             1,
             pcbDatac,
             v42,
             1,
             0);
  v23 = (1LL << (char)hKey) & 0x9402021;
  v24 = v50;
  if ( DWORD2(v47) )
  {
    Data = ScheduleOneOmaDmSessionOnLogin(
             a1,
             (const unsigned __int16 *)(v50 & ((unsigned __int128)-(__int128)(unsigned int)v23 >> 64)),
             0);
    if ( Data < 0 )
    {
      if ( !v23 || !v24 || (Data = ScheduleOneOmaDmSessionOnLogin(a1, 0, 0), Data < 0) )
      {
        v25 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogDMPollLoginSetupFail(v25, Data);
      }
    }
  }
  if ( HIDWORD(v47) )
  {
    Data = ScheduleOneOmaDmSessionOnLogin(
             a1,
             (const unsigned __int16 *)(v24 & ((unsigned __int128)-(__int128)(unsigned __int64)v23 >> 64)),
             1);
    if ( Data >= 0 || v23 && v24 && (Data = ScheduleOneOmaDmSessionOnLogin(a1, 0, 1), Data >= 0) )
    {
      v27 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupSuccess(v27);
    }
    else
    {
      v26 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupFail(v26, Data);
    }
  }
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  hKey = 0;
  DeviceEnrollerKey = GetDeviceEnrollerKey(a1, &hKey);
  PollValueFromRegistry = DeviceEnrollerKey;
  if ( DeviceEnrollerKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9F,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)DeviceEnrollerKey);
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v44);
    if ( hKey )
      RegCloseKey(hKey);
    return PollValueFromRegistry;
  }
  pvData = 0;
  v49 = 16;
  v29 = hKey;
  ValueW = RegGetValueW(hKey, 0, L"FirstScheduleTimestamp", 8u, 0, &pvData, &v49);
  v31 = ValueW;
  if ( ValueW > 0 )
    v31 = (unsigned __int16)ValueW | 0x80070000;
  Data = v31;
  if ( v31 < 0 )
  {
    v31 = RegSetValueExW(v29, L"FirstScheduleTimestamp", 0, 3u, (const BYTE *)&SystemTime, 0x10u);
    Data = v31;
  }
  EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v44);
  if ( v29 )
    RegCloseKey(v29);
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x18001c054  mov     [rsp-8+arg_10], rbx
0x18001c059  push    rbp
0x18001c05a  push    rsi
0x18001c05b  push    rdi
0x18001c05c  push    r12
0x18001c05e  push    r13
0x18001c060  push    r14
0x18001c062  push    r15
0x18001c064  lea     rbp, [rsp-1Fh]
0x18001c069  sub     rsp, 0E0h
0x18001c070  mov     rax, cs:__security_cookie
0x18001c077  xor     rax, rsp
0x18001c07a  mov     [rbp+4Fh+var_38], rax
0x18001c07e  mov     dword ptr [rbp+4Fh+hKey], r9d
0x18001c082  mov     [rbp+4Fh+var_80], rdx
0x18001c086  mov     rdi, rcx
0x18001c089  xorps   xmm0, xmm0
0x18001c08c  movups  xmmword ptr [rbp+4Fh+var_A8], xmm0
0x18001c090  movups  [rbp+4Fh+var_98], xmm0
0x18001c094  mov     [rbp+4Fh+Data], 0
0x18001c09b  xor     esi, esi
0x18001c09d  lea     rax, aSyncpollingopt_0; "SyncPollingOptions"
0x18001c0a4  mov     [rbp+4Fh+var_B8], rax
0x18001c0a8  lea     r15d, [rsi+1]
0x18001c0ac  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, r15b
0x18001c0b3  jz      short loc_18001C0E1
0x18001c0b5  mov     [rbp+4Fh+var_48], rax
0x18001c0b9  mov     [rbp+4Fh+var_40], 13h
0x18001c0c1  lea     rax, [rbp+4Fh+var_58]
0x18001c0c5  mov     [rsp+110h+lpData], rax
0x18001c0ca  lea     r9d, [rsi+2]
0x18001c0ce  lea     rdx, EnteringScopeEvent
0x18001c0d5  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18001c0dc  call    McGenEventWrite_EventWriteTransfer
0x18001c0e1  xor     r14d, r14d
0x18001c0e4  mov     r13d, 80000000h
0x18001c0ea  mov     r12d, 80070002h
0x18001c0f0  lea     rax, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x18001c0f7  lea     r8, [rbp+4Fh+var_A8]
0x18001c0fb  lea     r8, [r8+r14*4]; unsigned int *
0x18001c0ff  mov     rdx, [rax+r14*8]; lpValue
0x18001c103  mov     rcx, rdi; unsigned __int16 *
0x18001c106  call    ?GetPollValueFromRegistry@@YAJPEBG0PEAK@Z; GetPollValueFromRegistry(ushort const *,ushort const *,ulong *)
0x18001c10b  mov     ebx, eax
0x18001c10d  mov     [rbp+4Fh+Data], eax
0x18001c110  add     eax, r13d
0x18001c113  test    r13d, eax
0x18001c116  jnz     short loc_18001C11D
0x18001c118  cmp     ebx, r12d
0x18001c11b  jnz     short loc_18001C143
0x18001c11d  cmp     ebx, r12d
0x18001c120  cmovnz  esi, r15d
0x18001c124  add     r14d, r15d
0x18001c127  cmp     r14d, 8
0x18001c12b  jl      short loc_18001C0F0
0x18001c12d  test    esi, esi
0x18001c12f  jnz     short loc_18001C152
0x18001c131  lea     rcx, [rbp+4Fh+var_B8]; this
0x18001c135  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001c13a  nop
0x18001c13b  mov     eax, r15d
0x18001c13e  jmp     loc_18001C5EC
0x18001c143  lea     rcx, [rbp+4Fh+var_B8]; this
0x18001c147  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001c14c  nop
0x18001c14d  jmp     loc_18001C5EA
0x18001c152  mov     r15d, [rbp+4Fh+var_A8]
0x18001c156  mov     edx, [rbp+4Fh+var_A8+4]
0x18001c159  test    edx, edx
0x18001c15b  jnz     short loc_18001C16E
0x18001c15d  test    r15d, r15d
0x18001c160  jz      short loc_18001C16E
0x18001c162  xor     esi, esi
0x18001c164  mov     [rbp+4Fh+var_A8+8], esi
0x18001c167  xor     ebx, ebx
0x18001c169  mov     dword ptr [rbp+4Fh+var_98], ebx
0x18001c16c  jmp     short loc_18001C174
0x18001c16e  mov     ebx, dword ptr [rbp+4Fh+var_98]
0x18001c171  mov     esi, [rbp+4Fh+var_A8+8]
0x18001c174  mov     ecx, [rbp+4Fh+var_A8+0Ch]
0x18001c177  test    ecx, ecx
0x18001c179  jnz     short loc_18001C185
0x18001c17b  xor     eax, eax
0x18001c17d  test    esi, esi
0x18001c17f  cmovnz  ebx, eax
0x18001c182  mov     dword ptr [rbp+4Fh+var_98], ebx
0x18001c185  mov     eax, r15d
0x18001c188  neg     eax
0x18001c18a  sbb     r13d, r13d
0x18001c18d  and     r13d, edx
0x18001c190  mov     [rbp+4Fh+var_A8+4], r13d
0x18001c194  mov     eax, esi
0x18001c196  neg     eax
0x18001c198  sbb     r12d, r12d
0x18001c19b  and     r12d, ecx
0x18001c19e  mov     [rbp+4Fh+var_A8+0Ch], r12d
0x18001c1a2  mov     eax, ebx
0x18001c1a4  neg     eax
0x18001c1a6  sbb     eax, eax
0x18001c1a8  and     eax, dword ptr [rbp+4Fh+var_98+4]
0x18001c1ab  mov     [rbp+4Fh+var_88], eax
0x18001c1ae  mov     dword ptr [rbp+4Fh+var_98+4], eax
0x18001c1b1  xor     r14d, r14d
0x18001c1b4  lea     r15, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x18001c1bb  mov     r8d, [rbp+r14*4+4Fh+var_A8]; unsigned int
0x18001c1c0  mov     rdx, [r15+r14*8]; lpValueName
0x18001c1c4  mov     rcx, rdi; unsigned __int16 *
0x18001c1c7  call    ?SetPollValueToRegistry@@YAJPEBG0K@Z; SetPollValueToRegistry(ushort const *,ushort const *,ulong)
0x18001c1cc  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18001c1d3  jz      short loc_18001C1E3
0x18001c1d5  mov     r9d, [rbp+r14*4+4Fh+var_A8]
0x18001c1da  mov     r8, [r15+r14*8]
0x18001c1de  call    McTemplateU0zq_EventWriteTransfer
0x18001c1e3  inc     r14
0x18001c1e6  cmp     r14, 8
0x18001c1ea  jnz     short loc_18001C1BB
0x18001c1ec  mov     [rsp+110h+var_C8], 0; int
0x18001c1f4  mov     [rsp+110h+var_D0], 1; int
0x18001c1fc  mov     [rsp+110h+cbData], 0; int
0x18001c204  mov     r15d, [rbp+4Fh+var_A8]
0x18001c208  mov     dword ptr [rsp+110h+lpData], r15d; unsigned int
0x18001c20d  mov     r9d, r15d; unsigned int
0x18001c210  mov     r8d, r13d; unsigned int
0x18001c213  lea     rdx, aSchedule1Creat; "Schedule #1 created by enrollment clien"...
0x18001c21a  mov     rcx, rdi; unsigned __int16 *
0x18001c21d  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x18001c222  mov     [rbp+4Fh+Data], eax
0x18001c225  xor     ecx, ecx
0x18001c227  test    eax, eax
0x18001c229  jns     short loc_18001C27A
0x18001c22b  lea     r9d, [r14-4]; dwType
0x18001c22f  mov     [rsp+110h+cbData], r9d; cbData
0x18001c234  lea     rax, [rbp+4Fh+Data]
0x18001c238  mov     [rsp+110h+lpData], rax; lpData
0x18001c23d  lea     r8, aScheduleoneoma; "ScheduleOneOmaDmSession"
0x18001c244  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x18001c24b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c252  call    cs:__imp_RegSetKeyValueW
0x18001c258  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001c25d  mov     edx, [rbp+4Fh+Data]; int
0x18001c260  mov     rcx, rax; this
0x18001c263  call    ?LogDMPollScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollScheduleSetupFail(long)
0x18001c268  mov     ebx, [rbp+4Fh+Data]
0x18001c26b  lea     rcx, [rbp+4Fh+var_B8]; this
0x18001c26f  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001c274  nop
0x18001c275  jmp     loc_18001C5EA
0x18001c27a  lea     r14d, [r13+1]
0x18001c27e  imul    r14, r15
0x18001c282  mov     eax, 0FFFFFFFFh
0x18001c287  cmp     r14, rax
0x18001c28a  ja      loc_18001C5C6
0x18001c290  mov     [rbp+4Fh+Data], ecx
0x18001c293  mov     [rsp+110h+var_C8], ecx; int
0x18001c297  mov     [rsp+110h+var_D0], 1; int
0x18001c29f  mov     [rsp+110h+cbData], ecx; int
0x18001c2a3  mov     dword ptr [rsp+110h+lpData], r14d; unsigned int
0x18001c2a8  mov     r9d, esi; unsigned int
0x18001c2ab  mov     r8d, r12d; unsigned int
0x18001c2ae  lea     rdx, aSchedule2Creat; "Schedule #2 created by enrollment clien"...
0x18001c2b5  mov     rcx, rdi; unsigned __int16 *
0x18001c2b8  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x18001c2bd  mov     [rbp+4Fh+Data], eax
0x18001c2c0  xor     edx, edx
0x18001c2c2  test    eax, eax
0x18001c2c4  jns     short loc_18001C2E8
0x18001c2c6  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001c2cb  mov     edx, [rbp+4Fh+Data]; int
0x18001c2ce  mov     rcx, rax; this
0x18001c2d1  call    ?LogDMPollAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(long)
0x18001c2d6  mov     ebx, [rbp+4Fh+Data]
0x18001c2d9  lea     rcx, [rbp+4Fh+var_B8]; this
0x18001c2dd  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001c2e2  nop
0x18001c2e3  jmp     loc_18001C5EA
0x18001c2e8  mov     ecx, r12d
0x18001c2eb  mov     eax, esi
0x18001c2ed  imul    rcx, rax
0x18001c2f1  mov     eax, 0FFFFFFFFh
0x18001c2f6  cmp     rcx, rax
0x18001c2f9  ja      loc_18001C5A0
0x18001c2ff  lea     eax, [rcx+r14]
0x18001c303  cmp     eax, ecx
0x18001c305  jb      loc_18001C57A
0x18001c30b  mov     [rbp+4Fh+Data], edx
0x18001c30e  mov     [rsp+110h+var_C8], edx; int
0x18001c312  mov     [rsp+110h+var_D0], edx; int
0x18001c316  mov     [rsp+110h+cbData], edx; int
0x18001c31a  mov     dword ptr [rsp+110h+lpData], eax; unsigned int
0x18001c31e  mov     r9d, ebx; unsigned int
0x18001c321  mov     r14d, [rbp+4Fh+var_88]
0x18001c325  mov     r8d, r14d; unsigned int
0x18001c328  lea     rdx, aSchedule3Creat; "Schedule #3 created by enrollment clien"...
0x18001c32f  mov     rcx, rdi; unsigned __int16 *
0x18001c332  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x18001c337  mov     [rbp+4Fh+Data], eax
0x18001c33a  test    eax, eax
0x18001c33c  jns     short loc_18001C360
0x18001c33e  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001c343  mov     edx, [rbp+4Fh+Data]; int
0x18001c346  mov     rcx, rax; this
0x18001c349  call    ?LogDMPollSecondAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(long)
0x18001c34e  mov     ebx, [rbp+4Fh+Data]
0x18001c351  lea     rcx, [rbp+4Fh+var_B8]; this
0x18001c355  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001c35a  nop
0x18001c35b  jmp     loc_18001C5EA
0x18001c360  test    r14d, r14d
0x18001c363  jnz     short loc_18001C36E
0x18001c365  xor     r14d, r14d
0x18001c368  test    ebx, ebx
0x18001c36a  jnz     short loc_18001C3B3
0x18001c36c  jmp     short loc_18001C371
0x18001c36e  xor     r14d, r14d
0x18001c371  test    r12d, r12d
0x18001c374  jnz     short loc_18001C37A
0x18001c376  test    esi, esi
0x18001c378  jnz     short loc_18001C3B3
0x18001c37a  test    r13d, r13d
0x18001c37d  jnz     short loc_18001C384
0x18001c37f  test    r15d, r15d
0x18001c382  jnz     short loc_18001C3B3
0x18001c384  mov     [rsp+110h+var_C8], r14d; int
0x18001c389  mov     eax, 1
0x18001c38e  mov     [rsp+110h+var_D0], eax; int
0x18001c392  mov     [rsp+110h+cbData], eax; int
0x18001c396  mov     dword ptr [rsp+110h+lpData], r14d; int
0x18001c39b  mov     r9d, eax; unsigned int
0x18001c39e  mov     r8d, eax; unsigned int
0x18001c3a1  lea     rdx, aMaintenanceSch; "Maintenance Schedule created by enrollm"...
0x18001c3a8  mov     rcx, rdi; unsigned __int16 *
0x18001c3ab  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x18001c3b0  mov     [rbp+4Fh+Data], eax
0x18001c3b3  mov     ecx, dword ptr [rbp+4Fh+hKey]
0x18001c3b6  mov     r15d, 1
0x18001c3bc  mov     ebx, r15d
0x18001c3bf  shl     rbx, cl
0x18001c3c2  and     ebx, 9402021h
0x18001c3c8  mov     rsi, [rbp+4Fh+var_80]
0x18001c3cc  cmp     dword ptr [rbp+4Fh+var_98+8], r14d
0x18001c3d0  jz      short loc_18001C41D
0x18001c3d2  mov     eax, ebx
0x18001c3d4  neg     rax
0x18001c3d7  sbb     rdx, rdx
0x18001c3da  and     rdx, rsi; unsigned __int16 *
0x18001c3dd  xor     r8d, r8d; int
0x18001c3e0  mov     rcx, rdi; unsigned __int16 *
0x18001c3e3  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x18001c3e8  mov     [rbp+4Fh+Data], eax
0x18001c3eb  test    eax, eax
0x18001c3ed  jns     short loc_18001C41D
0x18001c3ef  test    rbx, rbx
0x18001c3f2  jz      short loc_18001C40D
0x18001c3f4  test    rsi, rsi
0x18001c3f7  jz      short loc_18001C40D
0x18001c3f9  xor     r8d, r8d; int
0x18001c3fc  xor     edx, edx; unsigned __int16 *
0x18001c3fe  mov     rcx, rdi; unsigned __int16 *
0x18001c401  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x18001c406  mov     [rbp+4Fh+Data], eax
0x18001c409  test    eax, eax
0x18001c40b  jns     short loc_18001C41D
0x18001c40d  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001c412  mov     edx, [rbp+4Fh+Data]; int
0x18001c415  mov     rcx, rax; this
0x18001c418  call    ?LogDMPollLoginSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollLoginSetupFail(long)
0x18001c41d  cmp     dword ptr [rbp+4Fh+var_98+0Ch], r14d
0x18001c421  jz      short loc_18001C47E
0x18001c423  mov     rax, rbx
0x18001c426  neg     rax
0x18001c429  sbb     rdx, rdx
0x18001c42c  and     rdx, rsi; unsigned __int16 *
0x18001c42f  mov     r8d, r15d; int
0x18001c432  mov     rcx, rdi; unsigned __int16 *
0x18001c435  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x18001c43a  mov     [rbp+4Fh+Data], eax
0x18001c43d  test    eax, eax
0x18001c43f  jns     short loc_18001C471
0x18001c441  test    rbx, rbx
0x18001c444  jz      short loc_18001C45F
0x18001c446  test    rsi, rsi
0x18001c449  jz      short loc_18001C45F
0x18001c44b  mov     r8d, r15d; int
0x18001c44e  xor     edx, edx; unsigned __int16 *
0x18001c450  mov     rcx, rdi; unsigned __int16 *
0x18001c453  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x18001c458  mov     [rbp+4Fh+Data], eax
0x18001c45b  test    eax, eax
0x18001c45d  jns     short loc_18001C471
0x18001c45f  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001c464  mov     edx, [rbp+4Fh+Data]; int
0x18001c467  mov     rcx, rax; this
0x18001c46a  call    ?LogDMAllUsersPollOnFirstLoginSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupFail(long)
0x18001c46f  jmp     short loc_18001C47E
0x18001c471  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001c476  mov     rcx, rax; this
0x18001c479  call    ?LogDMAllUsersPollOnFirstLoginSetupSuccess@CEnrollmentLogger@@QEAAXXZ; CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupSuccess(void)
0x18001c47e  xorps   xmm0, xmm0
0x18001c481  movups  xmmword ptr [rbp+4Fh+SystemTime.wYear], xmm0
0x18001c485  lea     rcx, [rbp+4Fh+SystemTime]; lpSystemTime
  ... truncated ...
```
