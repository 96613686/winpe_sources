# SetupAllEnrollmentSchedules(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)

- ea: `0x180065d70`
- end: `0x180065f33`
- name: `?SetupAllEnrollmentSchedules@@YAJPEBGU_FILETIME@@KKKH0@Z`
- size: `451`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _FILETIME, unsigned int, unsigned int, unsigned int, int, const unsigned __int16 *Data)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180050558`

## callees

- `0x1800128c4`
- `0x1800140d0`
- `0x18001aec8`
- `0x18004e314`
- `0x180062ee0`
- `0x180063b68`
- `0x180063fdc`
- `0x18006508c`
- `0x180065d70`
- `0x180065f3c`
- `0x1800721f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180065dec`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180065dec`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x180065daa`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x180065daa`

## pseudocode

```c
__int64 __fastcall SetupAllEnrollmentSchedules(
        unsigned __int16 *a1,
        struct _FILETIME a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        const unsigned __int16 *Data)
{
  int IsSystemOrAdmin; // eax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // edx
  int v14; // eax
  CEnrollmentLogger *Logger; // rax
  unsigned int v16; // ebx
  int lpData; // [rsp+20h] [rbp-48h]
  const unsigned __int16 *v19; // [rsp+30h] [rbp-38h]
  int v20; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v21[8]; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v22[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v20 = 0;
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v21, "SetupAllEnrollmentSchedules");
  IsSystemOrAdmin = DmIsSystemOrAdmin(&v20);
  v22[0] = "SetupAllEnrollmentSchedules";
  v22[1] = &Data;
  LODWORD(Data) = IsSystemOrAdmin;
  if ( IsSystemOrAdmin >= 0 )
  {
    LODWORD(Data) = ScheduleOMADMClientTask(a1, v12);
    if ( (int)Data >= 0 || !v20 )
    {
      v14 = ScheduleDeviceEnrollerOnPFW(a1, v13);
      LODWORD(Data) = v14;
      if ( v14 == -2147023179 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE32,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
          (const char *)0x800706B5LL,
          lpData);
        LODWORD(Data) = 1;
      }
      else if ( v14 < 0 && v20 && v14 != -2147024769 && v14 != -2147024846 && v14 != -2147009889 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE3C,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
          (const char *)(unsigned int)v14,
          lpData);
        goto LABEL_23;
      }
      LODWORD(Data) = ScheduleRenewalSession(a1, a2, a3, a4, a5, a6, v19);
      if ( (int)Data < 0 && v20 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogEnrollManualCertRenewScheduleFailed(Logger, (int)Data);
      }
      else
      {
        LODWORD(Data) = ScheduleAlertTask(a1, 0);
        if ( (int)Data >= 0 || !v20 )
        {
          LODWORD(Data) = ScheduleAlertTask(a1, 1);
          if ( (int)Data >= 0 || !v20 )
          {
            LODWORD(Data) = ScheduleAlertTask(a1, 2);
            if ( (int)Data >= 0 || !v20 )
              LODWORD(Data) = 0;
          }
        }
      }
    }
  }
  else
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"DmIsSystemOrAdmin", 4u, &Data, 4u);
  }
LABEL_23:
  v16 = (unsigned int)Data;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v22);
  EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
  return v16;
}

```

## disassembly

```asm
0x180065d70  push    rbp
0x180065d72  push    rbx
0x180065d73  push    rsi
0x180065d74  push    rdi
0x180065d75  push    r14
0x180065d77  push    r15
0x180065d79  mov     rbp, rsp
0x180065d7c  sub     rsp, 68h
0x180065d80  mov     rbx, rdx
0x180065d83  mov     [rbp+var_28], 0
0x180065d8a  mov     rdi, rcx
0x180065d8d  lea     r15, aSetupallenroll; "SetupAllEnrollmentSchedules"
0x180065d94  mov     rdx, r15; char *
0x180065d97  lea     rcx, [rbp+var_20]; this
0x180065d9b  mov     esi, r9d
0x180065d9e  mov     r14d, r8d
0x180065da1  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x180065da6  lea     rcx, [rbp+var_28]
0x180065daa  call    cs:__imp_?DmIsSystemOrAdmin@@YAJPEAH@Z; DmIsSystemOrAdmin(int *)
0x180065db0  lea     rcx, [rbp+Data]
0x180065db4  mov     [rbp+var_18], r15
0x180065db8  mov     [rbp+var_10], rcx
0x180065dbc  mov     dword ptr [rbp+Data], eax
0x180065dbf  test    eax, eax
0x180065dc1  jns     short loc_180065DF7
0x180065dc3  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x180065dca  lea     rax, [rbp+Data]
0x180065dce  mov     r9d, 4; dwType
0x180065dd4  lea     r8, aDmissystemorad_0; "DmIsSystemOrAdmin"
0x180065ddb  mov     [rsp+68h+cbData], r9d; cbData
0x180065de0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180065de7  mov     [rsp+68h+lpData], rax; lpData
0x180065dec  call    cs:__imp_RegSetKeyValueW
0x180065df2  jmp     loc_180065F0F
0x180065df7  mov     rcx, rdi; unsigned __int16 *
0x180065dfa  call    ?ScheduleOMADMClientTask@@YAJPEBG0@Z; ScheduleOMADMClientTask(ushort const *,ushort const *)
0x180065dff  mov     dword ptr [rbp+Data], eax
0x180065e02  test    eax, eax
0x180065e04  jns     short loc_180065E10
0x180065e06  cmp     [rbp+var_28], 0
0x180065e0a  jnz     loc_180065F0F
0x180065e10  mov     rcx, rdi
0x180065e13  call    ScheduleDeviceEnrollerOnPFW
0x180065e18  mov     r9d, 800706B5h; char *
0x180065e1e  mov     dword ptr [rbp+Data], eax
0x180065e21  mov     r15d, 1
0x180065e27  cmp     eax, r9d
0x180065e2a  jnz     short loc_180065E86
0x180065e2c  mov     rcx, [rbp+30h]; this
0x180065e30  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180065e37  mov     edx, 0E32h; void *
0x180065e3c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065e41  mov     dword ptr [rbp+Data], r15d
0x180065e45  mov     eax, [rbp+arg_28]
0x180065e48  mov     r9d, esi; unsigned int
0x180065e4b  mov     [rsp+68h+cbData], eax; int
0x180065e4f  mov     r8d, r14d; unsigned int
0x180065e52  mov     eax, [rbp+arg_20]
0x180065e55  mov     rdx, rbx; struct _FILETIME
0x180065e58  mov     rcx, rdi; unsigned __int16 *
0x180065e5b  mov     dword ptr [rsp+68h+lpData], eax; unsigned int
0x180065e5f  call    ?ScheduleRenewalSession@@YAJPEBGU_FILETIME@@KKKH0@Z; ScheduleRenewalSession(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)
0x180065e64  mov     dword ptr [rbp+Data], eax
0x180065e67  test    eax, eax
0x180065e69  jns     short loc_180065EBF
0x180065e6b  cmp     [rbp+var_28], 0
0x180065e6f  jz      short loc_180065EBF
0x180065e71  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180065e76  mov     edx, dword ptr [rbp+Data]; int
0x180065e79  mov     rcx, rax; this
0x180065e7c  call    ?LogEnrollManualCertRenewScheduleFailed@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogEnrollManualCertRenewScheduleFailed(long)
0x180065e81  jmp     loc_180065F0F
0x180065e86  test    eax, eax
0x180065e88  jns     short loc_180065E45
0x180065e8a  cmp     [rbp+var_28], 0
0x180065e8e  jz      short loc_180065E45
0x180065e90  cmp     eax, 8007007Fh
0x180065e95  jz      short loc_180065E45
0x180065e97  cmp     eax, 80070032h
0x180065e9c  jz      short loc_180065E45
0x180065e9e  cmp     eax, 80073A9Fh
0x180065ea3  jz      short loc_180065E45
0x180065ea5  mov     rcx, [rbp+30h]; this
0x180065ea9  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180065eb0  mov     r9d, eax; char *
0x180065eb3  mov     edx, 0E3Ch; void *
0x180065eb8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065ebd  jmp     short loc_180065F0F
0x180065ebf  xor     edx, edx
0x180065ec1  mov     rcx, rdi
0x180065ec4  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x180065ec9  mov     dword ptr [rbp+Data], eax
0x180065ecc  test    eax, eax
0x180065ece  jns     short loc_180065ED6
0x180065ed0  cmp     [rbp+var_28], 0
0x180065ed4  jnz     short loc_180065F0F
0x180065ed6  mov     edx, r15d
0x180065ed9  mov     rcx, rdi
0x180065edc  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x180065ee1  mov     dword ptr [rbp+Data], eax
0x180065ee4  test    eax, eax
0x180065ee6  jns     short loc_180065EEE
0x180065ee8  cmp     [rbp+var_28], 0
0x180065eec  jnz     short loc_180065F0F
0x180065eee  mov     edx, 2
0x180065ef3  mov     rcx, rdi
0x180065ef6  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x180065efb  mov     dword ptr [rbp+Data], eax
0x180065efe  test    eax, eax
0x180065f00  jns     short loc_180065F08
0x180065f02  cmp     [rbp+var_28], 0
0x180065f06  jnz     short loc_180065F0F
0x180065f08  mov     dword ptr [rbp+Data], 0
0x180065f0f  mov     ebx, dword ptr [rbp+Data]
0x180065f12  lea     rcx, [rbp+var_18]; this
0x180065f16  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180065f1b  lea     rcx, [rbp+var_20]; this
0x180065f1f  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x180065f24  mov     eax, ebx
0x180065f26  add     rsp, 68h
0x180065f2a  pop     r15
0x180065f2c  pop     r14
0x180065f2e  pop     rdi
0x180065f2f  pop     rsi
0x180065f30  pop     rbx
0x180065f31  pop     rbp
0x180065f32  retn
```
