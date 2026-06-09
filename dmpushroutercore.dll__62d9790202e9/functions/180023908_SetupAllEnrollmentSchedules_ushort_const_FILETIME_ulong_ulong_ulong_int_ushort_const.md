# SetupAllEnrollmentSchedules(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)

- ea: `0x180023908`
- end: `0x180023b14`
- name: `?SetupAllEnrollmentSchedules@@YAJPEBGU_FILETIME@@KKKH0@Z`
- size: `524`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME, unsigned int, unsigned int, unsigned int, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000ea90`

## callees

- `0x180010254`
- `0x18001cdb8`
- `0x180020418`
- `0x1800211c0`
- `0x180021690`
- `0x1800229f0`
- `0x180023908`
- `0x180023ce0`
- `0x1800245fc`
- `0x180024cbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180023990`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180023990`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x18002394e`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x18002394e`

## pseudocode

```c
__int64 __fastcall SetupAllEnrollmentSchedules(
        OLECHAR *a1,
        struct _FILETIME a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        unsigned __int16 *a7)
{
  int IsSystemOrAdmin; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  CEnrollmentLogger *Logger; // rax
  int lpData; // [rsp+20h] [rbp-48h]
  int Data; // [rsp+40h] [rbp-28h] BYREF
  int v19; // [rsp+44h] [rbp-24h] BYREF
  _QWORD v20[4]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v19 = 0;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
    McTemplateU0s_EventWriteTransfer(a1, EnteringScopeEvent, "SetupAllEnrollmentSchedules");
  IsSystemOrAdmin = DmIsSystemOrAdmin(&v19);
  v20[0] = "SetupAllEnrollmentSchedules";
  v20[1] = &Data;
  Data = IsSystemOrAdmin;
  if ( IsSystemOrAdmin < 0 )
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"DmIsSystemOrAdmin", 4u, &Data, 4u);
    v12 = Data;
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v20);
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
      goto LABEL_27;
    return v12;
  }
  Data = ScheduleOMADMClientTask(a1, a7);
  if ( Data >= 0 || !v19 )
  {
    v14 = ScheduleDeviceEnrollerOnPFW(a1, a7);
    Data = v14;
    if ( v14 == -2147023179 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE32,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)0x800706B5LL,
        lpData);
      Data = 1;
    }
    else if ( v14 < 0 && v19 && v14 != -2147024769 && v14 != -2147024846 && v14 != -2147009889 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE3C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v14,
        lpData);
      goto LABEL_26;
    }
    Data = ScheduleRenewalSession(a1, a2, a3, a4, a5, a6, a7);
    if ( Data < 0 && v19 )
    {
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogEnrollManualCertRenewScheduleFailed(Logger, Data);
    }
    else
    {
      Data = ScheduleAlertTask(a1, 0);
      if ( Data >= 0 || !v19 )
      {
        Data = ScheduleAlertTask(a1, 1);
        if ( Data >= 0 || !v19 )
        {
          Data = ScheduleAlertTask(a1, 2);
          if ( Data >= 0 || !v19 )
            Data = 0;
        }
      }
    }
  }
LABEL_26:
  v12 = Data;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v20);
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
LABEL_27:
    McTemplateU0s_EventWriteTransfer(v13, LeavingScopeEvent, "SetupAllEnrollmentSchedules");
  return v12;
}

```

## disassembly

```asm
0x180023908  push    rbp
0x18002390a  push    rbx
0x18002390b  push    rsi
0x18002390c  push    rdi
0x18002390d  push    r14
0x18002390f  push    r15
0x180023911  mov     rbp, rsp
0x180023914  sub     rsp, 68h
0x180023918  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x18002391f  lea     rsi, aSetupallenroll; "SetupAllEnrollmentSchedules"
0x180023926  mov     r14d, r9d
0x180023929  mov     [rbp+var_24], 0
0x180023930  mov     r15d, r8d
0x180023933  mov     rbx, rdx
0x180023936  mov     rdi, rcx
0x180023939  jz      short loc_18002394A
0x18002393b  mov     r8, rsi
0x18002393e  lea     rdx, EnteringScopeEvent
0x180023945  call    McTemplateU0s_EventWriteTransfer
0x18002394a  lea     rcx, [rbp+var_24]
0x18002394e  call    cs:__imp_?DmIsSystemOrAdmin@@YAJPEAH@Z; DmIsSystemOrAdmin(int *)
0x180023954  lea     rcx, [rbp+Data]
0x180023958  mov     [rbp+var_20], rsi
0x18002395c  mov     [rbp+var_18], rcx
0x180023960  mov     [rbp+Data], eax
0x180023963  test    eax, eax
0x180023965  jns     short loc_1800239B7
0x180023967  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x18002396e  lea     rax, [rbp+Data]
0x180023972  mov     r9d, 4; dwType
0x180023978  lea     r8, aDmissystemorad_0; "DmIsSystemOrAdmin"
0x18002397f  mov     [rsp+68h+cbData], r9d; cbData
0x180023984  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002398b  mov     [rsp+68h+lpData], rax; lpData
0x180023990  call    cs:__imp_RegSetKeyValueW
0x180023996  mov     ebx, [rbp+Data]
0x180023999  lea     rcx, [rbp+var_20]; this
0x18002399d  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800239a2  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x1800239a9  jz      loc_180023B05
0x1800239af  mov     r8, rsi
0x1800239b2  jmp     loc_180023AF9
0x1800239b7  mov     rsi, [rbp+arg_30]
0x1800239bb  mov     rcx, rdi; OLECHAR *
0x1800239be  mov     rdx, rsi; unsigned __int16 *
0x1800239c1  call    ?ScheduleOMADMClientTask@@YAJPEBG0@Z; ScheduleOMADMClientTask(ushort const *,ushort const *)
0x1800239c6  mov     [rbp+Data], eax
0x1800239c9  test    eax, eax
0x1800239cb  jns     short loc_1800239D7
0x1800239cd  cmp     [rbp+var_24], 0
0x1800239d1  jnz     loc_180023ADD
0x1800239d7  mov     rdx, rsi; unsigned __int16 *
0x1800239da  mov     rcx, rdi; OLECHAR *
0x1800239dd  call    ScheduleDeviceEnrollerOnPFW
0x1800239e2  mov     r9d, 800706B5h; char *
0x1800239e8  mov     [rbp+Data], eax
0x1800239eb  cmp     eax, r9d
0x1800239ee  jnz     short loc_180023A52
0x1800239f0  mov     rcx, [rbp+30h]; this
0x1800239f4  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800239fb  mov     edx, 0E32h; void *
0x180023a00  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023a05  mov     [rbp+Data], 1
0x180023a0c  mov     eax, [rbp+arg_28]
0x180023a0f  mov     r9d, r14d; unsigned int
0x180023a12  mov     [rsp+68h+var_38], rsi; unsigned __int16 *
0x180023a17  mov     r8d, r15d; unsigned int
0x180023a1a  mov     [rsp+68h+cbData], eax; int
0x180023a1e  mov     rdx, rbx; struct _FILETIME
0x180023a21  mov     eax, [rbp+arg_20]
0x180023a24  mov     rcx, rdi; unsigned __int16 *
0x180023a27  mov     dword ptr [rsp+68h+lpData], eax; unsigned int
0x180023a2b  call    ?ScheduleRenewalSession@@YAJPEBGU_FILETIME@@KKKH0@Z; ScheduleRenewalSession(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)
0x180023a30  mov     [rbp+Data], eax
0x180023a33  test    eax, eax
0x180023a35  jns     short loc_180023A8B
0x180023a37  cmp     [rbp+var_24], 0
0x180023a3b  jz      short loc_180023A8B
0x180023a3d  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180023a42  mov     edx, [rbp+Data]; int
0x180023a45  mov     rcx, rax; this
0x180023a48  call    ?LogEnrollManualCertRenewScheduleFailed@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogEnrollManualCertRenewScheduleFailed(long)
0x180023a4d  jmp     loc_180023ADD
0x180023a52  test    eax, eax
0x180023a54  jns     short loc_180023A0C
0x180023a56  cmp     [rbp+var_24], 0
0x180023a5a  jz      short loc_180023A0C
0x180023a5c  cmp     eax, 8007007Fh
0x180023a61  jz      short loc_180023A0C
0x180023a63  cmp     eax, 80070032h
0x180023a68  jz      short loc_180023A0C
0x180023a6a  cmp     eax, 80073A9Fh
0x180023a6f  jz      short loc_180023A0C
0x180023a71  mov     rcx, [rbp+30h]; this
0x180023a75  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180023a7c  mov     r9d, eax; char *
0x180023a7f  mov     edx, 0E3Ch; void *
0x180023a84  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023a89  jmp     short loc_180023ADD
0x180023a8b  xor     edx, edx
0x180023a8d  mov     rcx, rdi
0x180023a90  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x180023a95  mov     [rbp+Data], eax
0x180023a98  test    eax, eax
0x180023a9a  jns     short loc_180023AA2
0x180023a9c  cmp     [rbp+var_24], 0
0x180023aa0  jnz     short loc_180023ADD
0x180023aa2  mov     edx, 1
0x180023aa7  mov     rcx, rdi
0x180023aaa  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x180023aaf  mov     [rbp+Data], eax
0x180023ab2  test    eax, eax
0x180023ab4  jns     short loc_180023ABC
0x180023ab6  cmp     [rbp+var_24], 0
0x180023aba  jnz     short loc_180023ADD
0x180023abc  mov     edx, 2
0x180023ac1  mov     rcx, rdi
0x180023ac4  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x180023ac9  mov     [rbp+Data], eax
0x180023acc  test    eax, eax
0x180023ace  jns     short loc_180023AD6
0x180023ad0  cmp     [rbp+var_24], 0
0x180023ad4  jnz     short loc_180023ADD
0x180023ad6  mov     [rbp+Data], 0
0x180023add  mov     ebx, [rbp+Data]
0x180023ae0  lea     rcx, [rbp+var_20]; this
0x180023ae4  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180023ae9  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x180023af0  jz      short loc_180023B05
0x180023af2  lea     r8, aSetupallenroll; "SetupAllEnrollmentSchedules"
0x180023af9  lea     rdx, LeavingScopeEvent
0x180023b00  call    McTemplateU0s_EventWriteTransfer
0x180023b05  mov     eax, ebx
0x180023b07  add     rsp, 68h
0x180023b0b  pop     r15
0x180023b0d  pop     r14
0x180023b0f  pop     rdi
0x180023b10  pop     rsi
0x180023b11  pop     rbx
0x180023b12  pop     rbp
0x180023b13  retn
```
