# SyncPollingOptions(ushort const *,ushort const *,bool,EnrollmentEnrollType,bool)

- ea: `0x180012370`
- end: `0x1800128bc`
- name: `?SyncPollingOptions@@YAJPEBG0_NW4EnrollmentEnrollType@@1@Z`
- size: `1356`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004ff88`

## callees

- `0x1800071c0`
- `0x18000dd20`
- `0x180011938`
- `0x180012370`
- `0x1800128c4`
- `0x18001aec8`
- `0x18002e1a0`
- `0x18003dba8`
- `0x18004e314`
- `0x180060f5c`
- `0x180062988`
- `0x180062c88`
- `0x1800643c0`
- `0x180064cfc`
- `0x180065c78`
- `0x180070ff4`
- `0x18007106c`
- `0x1800710d8`
- `0x180071168`
- `0x1800711e0`
- `0x180071270`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012847`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012847`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001280b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001280b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800127c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012864`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800127c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012864`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180012777`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180012777`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800124fd`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800124fd`

## string_xrefs

- `0x1800124be`: `Schedule #1 created by enrollment client`
- `0x1800126a8`: `Maintenance Schedule created by enrollment client`
- `0x180012629`: `Schedule #3 created by enrollment client`
- `0x180012584`: `Schedule #2 created by enrollment client`

## pseudocode

```c
__int64 __fastcall SyncPollingOptions(const unsigned __int16 *a1, __int64 a2, __int64 a3, int a4)
{
  int v5; // esi
  __int64 v6; // rdx
  __int64 v7; // r8
  int i; // r14d
  unsigned int PollValueFromRegistry; // ebx
  const unsigned __int16 * near **v11; // r9
  __int64 j; // rbx
  __int64 v13; // rcx
  __int64 v14; // rbx
  unsigned int v15; // esi
  CEnrollmentLogger *Logger; // rax
  CEnrollmentLogger *v17; // rax
  unsigned int v18; // r12d
  __int64 v19; // r15
  __int64 v20; // r14
  CEnrollmentLogger *v21; // rax
  unsigned int v22; // ecx
  unsigned int v23; // r13d
  unsigned int v24; // r12d
  __int64 v25; // rbx
  __int64 v26; // rsi
  CEnrollmentLogger *v27; // rax
  CEnrollmentLogger *v28; // rax
  CEnrollmentLogger *v29; // rax
  int v30; // r8d
  int DeviceEnrollerKey; // eax
  HKEY v32; // rbx
  LSTATUS ValueW; // eax
  int v34; // edi
  CEnrollmentLogger *v35; // rax
  int lpData; // [rsp+20h] [rbp-91h]
  int pcbData; // [rsp+30h] [rbp-81h]
  int pcbDataa; // [rsp+30h] [rbp-81h]
  int pcbDatab; // [rsp+30h] [rbp-81h]
  int pcbDatac; // [rsp+30h] [rbp-81h]
  int v41; // [rsp+38h] [rbp-79h]
  int v42; // [rsp+38h] [rbp-79h]
  int v43; // [rsp+38h] [rbp-79h]
  int v44; // [rsp+38h] [rbp-79h]
  int Data; // [rsp+50h] [rbp-61h] BYREF
  _BYTE v46[8]; // [rsp+58h] [rbp-59h] BYREF
  unsigned int v47; // [rsp+60h] [rbp-51h] BYREF
  unsigned int v48; // [rsp+64h] [rbp-4Dh] BYREF
  HKEY hKey; // [rsp+68h] [rbp-49h] BYREF
  int v50; // [rsp+70h] [rbp-41h]
  DWORD v51; // [rsp+74h] [rbp-3Dh] BYREF
  __int64 v52; // [rsp+78h] [rbp-39h]
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-31h] BYREF
  __int128 pvData; // [rsp+90h] [rbp-21h] BYREF
  unsigned int v55[4]; // [rsp+A0h] [rbp-11h] BYREF
  unsigned int v56[4]; // [rsp+B0h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v50 = a4;
  v52 = a2;
  *(_OWORD *)v55 = 0;
  *(_OWORD *)v56 = 0;
  Data = 0;
  v47 = 0;
  v48 = 0;
  v5 = 0;
  hKey = 0;
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v46, "SyncPollingOptions");
  for ( i = 0; i < 8; ++i )
  {
    PollValueFromRegistry = GetPollValueFromRegistry(a1, (LPCWSTR)(&g_RegistryKeyNames)[i], &v55[i]);
    Data = PollValueFromRegistry;
    if ( (int)(PollValueFromRegistry + 0x80000000) >= 0 && PollValueFromRegistry != -2147024894 )
    {
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
      return PollValueFromRegistry;
    }
    if ( PollValueFromRegistry != -2147024894 )
      v5 = 1;
  }
  if ( !v5 )
  {
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
    return 1;
  }
  ClearSchedulesAfterInfinite(v55, v6, v7, &g_RegistryKeyNames);
  for ( j = 0; j != 8; ++j )
  {
    SetPollValueToRegistry(a1, (LPCWSTR)v11[j], v55[j]);
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
      McTemplateU0zq_EventWriteTransfer(v13, DMScheduleAdminPollValues, (&g_RegistryKeyNames)[j], v55[j]);
    v11 = &g_RegistryKeyNames;
  }
  v14 = v55[0];
  v15 = v55[1];
  Data = ScheduleOneOmaDmSession(
           a1,
           L"Schedule #1 created by enrollment client",
           v55[1],
           v55[0],
           v55[0],
           0,
           pcbData,
           v41,
           1,
           0);
  if ( Data < 0 )
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"ScheduleOneOmaDmSession", 4u, &Data, 4u);
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollScheduleSetupFail(Logger, Data);
    PollValueFromRegistry = Data;
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
    return PollValueFromRegistry;
  }
  Data = ULongLongToULong(v14 * (v15 + 1), &v47);
  if ( Data < 0
    || (v18 = v47,
        v19 = v55[2],
        v20 = v55[3],
        Data = ScheduleOneOmaDmSession(
                 a1,
                 L"Schedule #2 created by enrollment client",
                 v55[3],
                 v55[2],
                 v47,
                 0,
                 pcbDataa,
                 v42,
                 1,
                 0),
        Data < 0) )
  {
    v17 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(v17, Data);
    PollValueFromRegistry = Data;
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
    return PollValueFromRegistry;
  }
  Data = ULongLongToULong(v20 * v19, &v48);
  if ( Data < 0 )
    goto LABEL_21;
  v22 = v48 + v18;
  if ( v48 + v18 < v48 )
  {
    v35 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(v35, -2147024362);
    PollValueFromRegistry = -2147024362;
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
    return PollValueFromRegistry;
  }
  v23 = v56[0];
  v24 = v56[1];
  Data = ScheduleOneOmaDmSession(
           a1,
           L"Schedule #3 created by enrollment client",
           v56[1],
           v56[0],
           v22,
           0,
           pcbDatab,
           v43,
           0,
           0);
  if ( Data < 0 )
  {
LABEL_21:
    v21 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(v21, Data);
    PollValueFromRegistry = Data;
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
    return PollValueFromRegistry;
  }
  if ( (v24 || !v23) && ((_DWORD)v20 || !(_DWORD)v19) && (v15 || !(_DWORD)v14) )
    Data = ScheduleOneOmaDmSession(
             a1,
             L"Maintenance Schedule created by enrollment client",
             1u,
             1u,
             0,
             1,
             pcbDatac,
             v44,
             1,
             0);
  v25 = (1LL << v50) & 0x9402021;
  v26 = v52;
  if ( v56[2] )
  {
    if ( !v25 || v52 )
    {
      Data = ScheduleOneOmaDmSessionOnLogin(
               a1,
               (const unsigned __int16 *)(v52 & ((unsigned __int128)-(__int128)(unsigned __int64)v25 >> 64)),
               0);
      if ( Data >= 0 )
        goto LABEL_37;
    }
    else
    {
      Data = -2102788088;
    }
    v27 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollLoginSetupFail(v27, Data);
  }
LABEL_37:
  if ( !v56[3] )
    goto LABEL_44;
  if ( v25 && !v26 )
  {
    Data = -2102788088;
LABEL_42:
    v28 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupFail(v28, Data);
    goto LABEL_44;
  }
  Data = ScheduleOneOmaDmSessionOnLogin(a1, (const unsigned __int16 *)(v26 & -(__int64)(v25 != 0)), 1);
  if ( Data < 0 )
    goto LABEL_42;
  v29 = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupSuccess(v29);
LABEL_44:
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  DeviceEnrollerKey = GetDeviceEnrollerKey(a1, &hKey, v30);
  PollValueFromRegistry = DeviceEnrollerKey;
  if ( DeviceEnrollerKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)DeviceEnrollerKey,
      lpData);
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
    if ( hKey )
      RegCloseKey(hKey);
    return PollValueFromRegistry;
  }
  pvData = 0;
  v51 = 16;
  v32 = hKey;
  ValueW = RegGetValueW(hKey, 0, L"FirstScheduleTimestamp", 8u, 0, &pvData, &v51);
  v34 = ValueW;
  if ( ValueW > 0 )
    v34 = (unsigned __int16)ValueW | 0x80070000;
  Data = v34;
  if ( v34 < 0 )
  {
    v34 = RegSetValueExW(v32, L"FirstScheduleTimestamp", 0, 3u, (const BYTE *)&SystemTime, 0x10u);
    Data = v34;
  }
  EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v46);
  if ( v32 )
    RegCloseKey(v32);
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x180012370  mov     [rsp-8+arg_10], rbx
0x180012375  push    rbp
0x180012376  push    rsi
0x180012377  push    rdi
0x180012378  push    r12
0x18001237a  push    r13
0x18001237c  push    r14
0x18001237e  push    r15
0x180012380  lea     rbp, [rsp-1Fh]
0x180012385  sub     rsp, 0D0h
0x18001238c  mov     rax, cs:__security_cookie
0x180012393  xor     rax, rsp
0x180012396  mov     [rbp+4Fh+var_40], rax
0x18001239a  mov     [rbp+4Fh+var_90], r9d
0x18001239e  mov     [rbp+4Fh+var_88], rdx
0x1800123a2  mov     rdi, rcx
0x1800123a5  xorps   xmm0, xmm0
0x1800123a8  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x1800123ac  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x1800123b0  xor     r13d, r13d
0x1800123b3  mov     [rbp+4Fh+Data], r13d
0x1800123b7  mov     [rbp+4Fh+var_A0], r13d
0x1800123bb  mov     [rbp+4Fh+var_9C], r13d
0x1800123bf  mov     esi, r13d
0x1800123c2  mov     [rbp+4Fh+hKey], r13
0x1800123c6  lea     rdx, aSyncpollingopt_0; "SyncPollingOptions"
0x1800123cd  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800123d1  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x1800123d6  mov     r14d, r13d
0x1800123d9  mov     r12d, 80070002h
0x1800123df  lea     r15d, [r13+1]
0x1800123e3  lea     r9, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x1800123ea  cmp     r14d, 8
0x1800123ee  jge     short loc_180012437
0x1800123f0  movsxd  rdx, r14d
0x1800123f3  lea     r8, [rbp+4Fh+var_60]
0x1800123f7  lea     r8, [r8+rdx*4]; unsigned int *
0x1800123fb  mov     rdx, [r9+rdx*8]; lpValue
0x1800123ff  mov     rcx, rdi; unsigned __int16 *
0x180012402  call    ?GetPollValueFromRegistry@@YAJPEBG0PEAK@Z; GetPollValueFromRegistry(ushort const *,ushort const *,ulong *)
0x180012407  mov     ebx, eax
0x180012409  mov     [rbp+4Fh+Data], eax
0x18001240c  mov     ecx, 80000000h
0x180012411  add     eax, ecx
0x180012413  test    ecx, eax
0x180012415  jnz     short loc_18001241C
0x180012417  cmp     ebx, r12d
0x18001241a  jnz     short loc_180012428
0x18001241c  cmp     ebx, r12d
0x18001241f  cmovnz  esi, r15d
0x180012423  add     r14d, r15d
0x180012426  jmp     short loc_1800123E3
0x180012428  lea     rcx, [rbp+4Fh+var_A8]; this
0x18001242c  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x180012431  nop
0x180012432  jmp     loc_180012893
0x180012437  test    esi, esi
0x180012439  jnz     short loc_18001244D
0x18001243b  lea     rcx, [rbp+4Fh+var_A8]; this
0x18001243f  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x180012444  nop
0x180012445  mov     eax, r15d
0x180012448  jmp     loc_180012895
0x18001244d  lea     rcx, [rbp+4Fh+var_60]
0x180012451  call    ClearSchedulesAfterInfinite
0x180012456  mov     rbx, r13
0x180012459  mov     r8d, [rbp+rbx*4+4Fh+var_60]; unsigned int
0x18001245e  mov     rdx, [r9+rbx*8]; lpValueName
0x180012462  mov     rcx, rdi; unsigned __int16 *
0x180012465  call    ?SetPollValueToRegistry@@YAJPEBG0K@Z; SetPollValueToRegistry(ushort const *,ushort const *,ulong)
0x18001246a  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x180012471  jz      short loc_18001248F
0x180012473  mov     r9d, [rbp+rbx*4+4Fh+var_60]
0x180012478  lea     r8, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x18001247f  mov     r8, [r8+rbx*8]
0x180012483  lea     rdx, DMScheduleAdminPollValues
0x18001248a  call    McTemplateU0zq_EventWriteTransfer
0x18001248f  add     rbx, r15
0x180012492  cmp     rbx, 8
0x180012496  lea     r9, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x18001249d  jnz     short loc_180012459
0x18001249f  mov     [rsp+100h+var_B8], r13d; int
0x1800124a4  mov     [rsp+100h+var_C0], r15d; int
0x1800124a9  mov     [rsp+100h+cbData], r13d; int
0x1800124ae  mov     ebx, [rbp+4Fh+var_60]
0x1800124b1  mov     dword ptr [rsp+100h+lpData], ebx; unsigned int
0x1800124b5  mov     r9d, ebx; unsigned int
0x1800124b8  mov     esi, [rbp+4Fh+var_60+4]
0x1800124bb  mov     r8d, esi; unsigned int
0x1800124be  lea     rdx, aSchedule1Creat; "Schedule #1 created by enrollment clien"...
0x1800124c5  mov     rcx, rdi; unsigned __int16 *
0x1800124c8  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x1800124cd  mov     [rbp+4Fh+Data], eax
0x1800124d0  test    eax, eax
0x1800124d2  jns     short loc_180012525
0x1800124d4  mov     r9d, 4; dwType
0x1800124da  mov     [rsp+100h+cbData], r9d; cbData
0x1800124df  lea     rax, [rbp+4Fh+Data]
0x1800124e3  mov     [rsp+100h+lpData], rax; lpData
0x1800124e8  lea     r8, aScheduleoneoma; "ScheduleOneOmaDmSession"
0x1800124ef  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x1800124f6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800124fd  call    cs:__imp_RegSetKeyValueW
0x180012503  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180012508  mov     edx, [rbp+4Fh+Data]; int
0x18001250b  mov     rcx, rax; this
0x18001250e  call    ?LogDMPollScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollScheduleSetupFail(long)
0x180012513  mov     ebx, [rbp+4Fh+Data]
0x180012516  lea     rcx, [rbp+4Fh+var_A8]; this
0x18001251a  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001251f  nop
0x180012520  jmp     loc_180012893
0x180012525  lea     ecx, [rsi+1]
0x180012528  imul    rcx, rbx; unsigned __int64
0x18001252c  lea     rdx, [rbp+4Fh+var_A0]; unsigned int *
0x180012530  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180012535  mov     [rbp+4Fh+Data], eax
0x180012538  test    eax, eax
0x18001253a  jns     short loc_18001255E
0x18001253c  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180012541  mov     edx, [rbp+4Fh+Data]; int
0x180012544  mov     rcx, rax; this
0x180012547  call    ?LogDMPollAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(long)
0x18001254c  mov     ebx, [rbp+4Fh+Data]
0x18001254f  lea     rcx, [rbp+4Fh+var_A8]; this
0x180012553  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x180012558  nop
0x180012559  jmp     loc_180012893
0x18001255e  mov     [rsp+100h+var_B8], r13d; int
0x180012563  mov     [rsp+100h+var_C0], r15d; int
0x180012568  mov     [rsp+100h+cbData], r13d; int
0x18001256d  mov     r12d, [rbp+4Fh+var_A0]
0x180012571  mov     dword ptr [rsp+100h+lpData], r12d; unsigned int
0x180012576  mov     r15d, [rbp+4Fh+var_60+8]
0x18001257a  mov     r9d, r15d; unsigned int
0x18001257d  mov     r14d, [rbp+4Fh+var_60+0Ch]
0x180012581  mov     r8d, r14d; unsigned int
0x180012584  lea     rdx, aSchedule2Creat; "Schedule #2 created by enrollment clien"...
0x18001258b  mov     rcx, rdi; unsigned __int16 *
0x18001258e  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x180012593  mov     [rbp+4Fh+Data], eax
0x180012596  test    eax, eax
0x180012598  jns     short loc_1800125BC
0x18001259a  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001259f  mov     edx, [rbp+4Fh+Data]; int
0x1800125a2  mov     rcx, rax; this
0x1800125a5  call    ?LogDMPollAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollAuxiliaryScheduleSetupFail(long)
0x1800125aa  mov     ebx, [rbp+4Fh+Data]
0x1800125ad  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800125b1  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800125b6  nop
0x1800125b7  jmp     loc_180012893
0x1800125bc  mov     rcx, r15
0x1800125bf  imul    rcx, r14; unsigned __int64
0x1800125c3  lea     rdx, [rbp+4Fh+var_9C]; unsigned int *
0x1800125c7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800125cc  mov     [rbp+4Fh+Data], eax
0x1800125cf  test    eax, eax
0x1800125d1  jns     short loc_1800125F5
0x1800125d3  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800125d8  mov     edx, [rbp+4Fh+Data]; int
0x1800125db  mov     rcx, rax; this
0x1800125de  call    ?LogDMPollSecondAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(long)
0x1800125e3  mov     ebx, [rbp+4Fh+Data]
0x1800125e6  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800125ea  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800125ef  nop
0x1800125f0  jmp     loc_180012893
0x1800125f5  mov     eax, [rbp+4Fh+var_9C]
0x1800125f8  lea     ecx, [rax+r12]
0x1800125fc  cmp     ecx, eax
0x1800125fe  jb      loc_18001286F
0x180012604  mov     [rbp+4Fh+Data], r13d
0x180012608  mov     [rsp+100h+var_B8], r13d; int
0x18001260d  mov     [rsp+100h+var_C0], r13d; int
0x180012612  mov     [rsp+100h+cbData], r13d; int
0x180012617  mov     dword ptr [rsp+100h+lpData], ecx; unsigned int
0x18001261b  mov     r13d, [rbp+4Fh+var_50]
0x18001261f  mov     r9d, r13d; unsigned int
0x180012622  mov     r12d, [rbp+4Fh+var_50+4]
0x180012626  mov     r8d, r12d; unsigned int
0x180012629  lea     rdx, aSchedule3Creat; "Schedule #3 created by enrollment clien"...
0x180012630  mov     rcx, rdi; unsigned __int16 *
0x180012633  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x180012638  mov     [rbp+4Fh+Data], eax
0x18001263b  test    eax, eax
0x18001263d  jns     short loc_180012661
0x18001263f  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180012644  mov     edx, [rbp+4Fh+Data]; int
0x180012647  mov     rcx, rax; this
0x18001264a  call    ?LogDMPollSecondAuxiliaryScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollSecondAuxiliaryScheduleSetupFail(long)
0x18001264f  mov     ebx, [rbp+4Fh+Data]
0x180012652  lea     rcx, [rbp+4Fh+var_A8]; this
0x180012656  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001265b  nop
0x18001265c  jmp     loc_180012893
0x180012661  test    r12d, r12d
0x180012664  jnz     short loc_180012670
0x180012666  xor     r12d, r12d
0x180012669  test    r13d, r13d
0x18001266c  jnz     short loc_1800126BA
0x18001266e  jmp     short loc_180012673
0x180012670  xor     r12d, r12d
0x180012673  test    r14d, r14d
0x180012676  jnz     short loc_18001267D
0x180012678  test    r15d, r15d
0x18001267b  jnz     short loc_1800126BA
0x18001267d  test    esi, esi
0x18001267f  jnz     short loc_180012685
0x180012681  test    ebx, ebx
0x180012683  jnz     short loc_1800126BA
0x180012685  mov     [rsp+100h+var_B8], r12d; int
0x18001268a  mov     [rsp+100h+var_C0], 1; int
0x180012692  mov     [rsp+100h+cbData], 1; int
0x18001269a  mov     dword ptr [rsp+100h+lpData], r12d; int
0x18001269f  mov     r9d, 1; unsigned int
0x1800126a5  mov     r8d, r9d; unsigned int
0x1800126a8  lea     rdx, aMaintenanceSch; "Maintenance Schedule created by enrollm"...
0x1800126af  mov     rcx, rdi; unsigned __int16 *
0x1800126b2  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x1800126b7  mov     [rbp+4Fh+Data], eax
0x1800126ba  mov     ecx, [rbp+4Fh+var_90]
0x1800126bd  mov     ebx, 1
0x1800126c2  shl     rbx, cl
0x1800126c5  and     ebx, 9402021h
0x1800126cb  mov     r14d, 82AA0008h
0x1800126d1  mov     rsi, [rbp+4Fh+var_88]
0x1800126d5  cmp     [rbp+4Fh+var_50+8], r12d
0x1800126d9  jz      short loc_180012719
0x1800126db  test    rbx, rbx
0x1800126de  jz      short loc_1800126EB
0x1800126e0  test    rsi, rsi
0x1800126e3  jnz     short loc_1800126EB
0x1800126e5  mov     [rbp+4Fh+Data], r14d
0x1800126e9  jmp     short loc_180012709
0x1800126eb  mov     rax, rbx
0x1800126ee  neg     rax
0x1800126f1  sbb     rdx, rdx
0x1800126f4  and     rdx, rsi; unsigned __int16 *
0x1800126f7  xor     r8d, r8d; int
0x1800126fa  mov     rcx, rdi; unsigned __int16 *
0x1800126fd  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x180012702  mov     [rbp+4Fh+Data], eax
0x180012705  test    eax, eax
0x180012707  jns     short loc_180012719
0x180012709  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001270e  mov     edx, [rbp+4Fh+Data]; int
0x180012711  mov     rcx, rax; this
0x180012714  call    ?LogDMPollLoginSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollLoginSetupFail(long)
0x180012719  cmp     [rbp+4Fh+var_50+0Ch], r12d
0x18001271d  jz      short loc_18001276C
0x18001271f  test    rbx, rbx
0x180012722  jz      short loc_18001272F
0x180012724  test    rsi, rsi
0x180012727  jnz     short loc_18001272F
0x180012729  mov     [rbp+4Fh+Data], r14d
0x18001272d  jmp     short loc_18001274D
0x18001272f  neg     rbx
0x180012732  sbb     rdx, rdx
0x180012735  and     rdx, rsi; unsigned __int16 *
0x180012738  mov     r8d, 1; int
0x18001273e  mov     rcx, rdi; unsigned __int16 *
0x180012741  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x180012746  mov     [rbp+4Fh+Data], eax
0x180012749  test    eax, eax
0x18001274b  jns     short loc_18001275F
0x18001274d  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180012752  mov     edx, [rbp+4Fh+Data]; int
0x180012755  mov     rcx, rax; this
0x180012758  call    ?LogDMAllUsersPollOnFirstLoginSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupFail(long)
0x18001275d  jmp     short loc_18001276C
0x18001275f  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180012764  mov     rcx, rax; this
0x180012767  call    ?LogDMAllUsersPollOnFirstLoginSetupSuccess@CEnrollmentLogger@@QEAAXXZ; CEnrollmentLogger::LogDMAllUsersPollOnFirstLoginSetupSuccess(void)
0x18001276c  xorps   xmm0, xmm0
0x18001276f  movups  xmmword ptr [rbp+4Fh+SystemTime.wYear], xmm0
0x180012773  lea     rcx, [rbp+4Fh+SystemTime]; lpSystemTime
0x180012777  call    cs:__imp_GetSystemTime
0x18001277d  xor     edx, edx
0x18001277f  lea     rcx, [rbp+4Fh+hKey]
0x180012783  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180012788  lea     rdx, [rbp+4Fh+hKey]; HKEY *
0x18001278c  mov     rcx, rdi; pszMore
0x18001278f  call    ?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)
0x180012794  mov     ebx, eax
0x180012796  test    eax, eax
0x180012798  jns     short loc_1800127D1
0x18001279a  mov     rcx, [rbp+57h]; this
0x18001279e  mov     r9d, eax; char *
0x1800127a1  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800127a8  mov     edx, 0C9Fh; void *
0x1800127ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800127b2  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800127b6  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800127bb  nop
0x1800127bc  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800127c0  test    rcx, rcx
0x1800127c3  jz      short loc_1800127CC
0x1800127c5  call    cs:__imp_RegCloseKey
0x1800127cb  nop
  ... truncated ...
```
