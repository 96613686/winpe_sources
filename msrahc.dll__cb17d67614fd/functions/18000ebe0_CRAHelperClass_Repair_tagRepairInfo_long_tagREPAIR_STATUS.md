# CRAHelperClass::Repair(tagRepairInfo *,long *,tagREPAIR_STATUS *)

- ea: `0x18000ebe0`
- end: `0x18000ee99`
- name: `?Repair@CRAHelperClass@@UEAAJPEAUtagRepairInfo@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `697`
- prototype: `__int64 __fastcall(CRAHelperClass *this, const struct _EVENT_DESCRIPTOR *, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x18000ebe0`
- `0x180010d70`
- `0x180011a04`
- `0x180011af8`
- `0x180014660`
- `0x1800174e4`
- `0x1800182c4`

## string_xrefs

- `0x18000ec00`: `CRAHelperClass::Repair`
- `0x18000ed1d`: `CRAHelperClass::Repair`
- `0x18000ed9b`: `CRAHelperClass::Repair`
- `0x18000ee0d`: `CRAHelperClass::Repair`
- `0x18000ee70`: `CRAHelperClass::Repair`

## pseudocode

```c
__int64 __fastcall CRAHelperClass::Repair(
        CRAHelperClass *this,
        const struct _EVENT_DESCRIPTOR *a2,
        int *a3,
        enum tagREPAIR_STATUS *a4)
{
  unsigned int v6; // r9d
  __int64 v8; // rax
  ULONGLONG v9; // rax
  ULONGLONG v10; // rax
  ULONGLONG v11; // rax
  ULONGLONG v12; // rax
  ULONGLONG v13; // rax
  signed int v14; // eax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  __int64 v17; // r8
  unsigned int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  signed int v22; // eax
  const struct _EVENT_DESCRIPTOR *v23; // rdx
  CEventLogger *v24; // rcx
  ULONGLONG v25; // rax
  signed int v26; // eax
  const struct _EVENT_DESCRIPTOR *v27; // rdx
  CEventLogger *v28; // rcx
  signed int v29; // eax
  const struct _EVENT_DESCRIPTOR *v30; // rdx
  CEventLogger *v31; // rcx

  if ( !a4 )
  {
    v6 = 1369;
LABEL_3:
    CEventLogger::LogError(
      this,
      a2,
      L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
      v6,
      L"CRAHelperClass::Repair",
      0x80070057);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    v6 = 1370;
    goto LABEL_3;
  }
  *a4 = RS_UNREPAIRED;
  v8 = ID_RA_LOWH_REPAIR_GPSETTING_DISABLED_HT - *(_QWORD *)&a2->Id;
  if ( ID_RA_LOWH_REPAIR_GPSETTING_DISABLED_HT == *(_QWORD *)&a2->Id )
    v8 = 0x8E15370975C29793uLL - a2->Keyword;
  if ( !v8 )
    goto LABEL_43;
  v9 = ID_RA_LOWH_REPAIR_DEFAULT_EXPERT_FAILURE_HT - *(_QWORD *)&a2->Id;
  if ( (_QWORD)ID_RA_LOWH_REPAIR_DEFAULT_EXPERT_FAILURE_HT == *(_QWORD *)&a2->Id )
    v9 = *((_QWORD *)&ID_RA_LOWH_REPAIR_DEFAULT_EXPERT_FAILURE_HT + 1) - a2->Keyword;
  if ( !v9 )
    goto LABEL_43;
  v10 = ID_RA_LOWH_REPAIR_NO_PUBLIC_V4_ADDR_HT - *(_QWORD *)&a2->Id;
  if ( (_QWORD)ID_RA_LOWH_REPAIR_NO_PUBLIC_V4_ADDR_HT == *(_QWORD *)&a2->Id )
    v10 = *((_QWORD *)&ID_RA_LOWH_REPAIR_NO_PUBLIC_V4_ADDR_HT + 1) - a2->Keyword;
  if ( !v10 )
    goto LABEL_43;
  v11 = ID_RA_LOWH_REPAIR_NO_PUBLIC_V4_AND_TER_ADDR_HT - *(_QWORD *)&a2->Id;
  if ( (_QWORD)ID_RA_LOWH_REPAIR_NO_PUBLIC_V4_AND_TER_ADDR_HT == *(_QWORD *)&a2->Id )
    v11 = *((_QWORD *)&ID_RA_LOWH_REPAIR_NO_PUBLIC_V4_AND_TER_ADDR_HT + 1) - a2->Keyword;
  if ( !v11 )
    goto LABEL_43;
  v12 = ID_RA_LOWH_REPAIR_PUBLIC_FW_PROFILE_HT - *(_QWORD *)&a2->Id;
  if ( (_QWORD)ID_RA_LOWH_REPAIR_PUBLIC_FW_PROFILE_HT == *(_QWORD *)&a2->Id )
    v12 = *((_QWORD *)&ID_RA_LOWH_REPAIR_PUBLIC_FW_PROFILE_HT + 1) - a2->Keyword;
  if ( !v12 )
  {
LABEL_43:
    v29 = CNetDiagHelperImpl::UserActionRepair(this, (unsigned int *)this + 36, (unsigned int)a3, a3, a4);
    v18 = v29;
    if ( v29 < 0 )
      CEventLogger::LogError(
        v31,
        v30,
        L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
        0x567u,
        L"CRAHelperClass::Repair",
        v29);
    return v18;
  }
  v13 = ID_RA_LOWH_REPAIR_TIME_SERVER_RESYNC - *(_QWORD *)&a2->Id;
  if ( (_QWORD)ID_RA_LOWH_REPAIR_TIME_SERVER_RESYNC == *(_QWORD *)&a2->Id )
    v13 = *((_QWORD *)&ID_RA_LOWH_REPAIR_TIME_SERVER_RESYNC + 1) - a2->Keyword;
  if ( v13 )
  {
    v21 = ID_RA_LOWH_REPAIR_SYSSETTING_DISABLED - *(_QWORD *)&a2->Id;
    if ( ID_RA_LOWH_REPAIR_SYSSETTING_DISABLED == *(_QWORD *)&a2->Id )
      v21 = 0x2CC4DCA2F97CF2A8LL - a2->Keyword;
    if ( v21 )
    {
      v18 = 0;
      v25 = ID_RA_LOWH_REPAIR_FIREWALL_DISABLED - *(_QWORD *)&a2->Id;
      if ( (_QWORD)ID_RA_LOWH_REPAIR_FIREWALL_DISABLED == *(_QWORD *)&a2->Id )
        v25 = *((_QWORD *)&ID_RA_LOWH_REPAIR_FIREWALL_DISABLED + 1) - a2->Keyword;
      if ( v25 )
        return v18;
      LogRAProblem(804, 3, a3);
      v26 = EnableRAFirewallGroup();
      v18 = v26;
      if ( v26 >= 0 )
      {
        *((_DWORD *)this + 39) = 1;
        *((_DWORD *)this + 37) = 1;
        *a4 = RS_REPAIRED;
        v19 = 4;
      }
      else
      {
        CEventLogger::LogError(
          v28,
          v27,
          L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
          0x5A5u,
          L"CRAHelperClass::Repair",
          v26);
        v19 = 5;
      }
      v20 = 804;
    }
    else
    {
      LogRAProblem(803, 3, a3);
      v22 = RepairRASystemSetting();
      v18 = v22;
      if ( v22 >= 0 )
      {
        *a4 = RS_REPAIRED;
        v19 = 4;
      }
      else
      {
        CEventLogger::LogError(
          v24,
          v23,
          L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
          0x58Du,
          L"CRAHelperClass::Repair",
          v22);
        v19 = 5;
      }
      v20 = 803;
    }
  }
  else
  {
    LogRAProblem(805, 3, a3);
    v14 = ReSyncSysTime();
    v18 = v14;
    if ( v14 >= 0 )
    {
      *((_DWORD *)this + 56) = 1;
      *a4 = RS_REPAIRED;
      v19 = 4;
    }
    else
    {
      CEventLogger::LogError(
        v16,
        v15,
        L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
        0x572u,
        L"CRAHelperClass::Repair",
        v14);
      v19 = 5;
    }
    v20 = 805;
  }
  LogRAProblem(v20, v19, v17);
  return v18;
}

```

## disassembly

```asm
0x18000ebe0  mov     [rsp+arg_0], rbx
0x18000ebe5  mov     [rsp+arg_8], rsi
0x18000ebea  push    rdi
0x18000ebeb  sub     rsp, 30h
0x18000ebef  mov     rdi, r9
0x18000ebf2  mov     rsi, rcx
0x18000ebf5  test    r9, r9
0x18000ebf8  jnz     short loc_18000EC2A
0x18000ebfa  mov     r9d, 559h; unsigned int
0x18000ec00  lea     rax, aCrahelperclass_13; "CRAHelperClass::Repair"
0x18000ec07  mov     [rsp+38h+var_10], 80070057h; unsigned int
0x18000ec0f  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000ec16  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18000ec1b  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000ec20  mov     eax, 80070057h
0x18000ec25  jmp     loc_18000EE89
0x18000ec2a  test    rdx, rdx
0x18000ec2d  jnz     short loc_18000EC37
0x18000ec2f  mov     r9d, 55Ah
0x18000ec35  jmp     short loc_18000EC00
0x18000ec37  mov     dword ptr [r9], 2
0x18000ec3e  mov     rax, cs:ID_RA_LOWH_REPAIR_GPSETTING_DISABLED_HT
0x18000ec45  sub     rax, [rdx]
0x18000ec48  jnz     short loc_18000EC55
0x18000ec4a  mov     rax, qword ptr cs:byte_180020F98
0x18000ec51  sub     rax, [rdx+8]
0x18000ec55  test    rax, rax
0x18000ec58  jz      loc_18000EE4B
0x18000ec5e  mov     rax, qword ptr cs:ID_RA_LOWH_REPAIR_DEFAULT_EXPERT_FAILURE_HT
0x18000ec65  sub     rax, [rdx]
0x18000ec68  jnz     short loc_18000EC75
0x18000ec6a  mov     rax, qword ptr cs:ID_RA_LOWH_REPAIR_DEFAULT_EXPERT_FAILURE_HT+8
0x18000ec71  sub     rax, [rdx+8]
0x18000ec75  test    rax, rax
0x18000ec78  jz      loc_18000EE4B
0x18000ec7e  mov     rax, qword ptr cs:ID_RA_LOWH_REPAIR_NO_PUBLIC_V4_ADDR_HT
0x18000ec85  sub     rax, [rdx]
0x18000ec88  jnz     short loc_18000EC95
0x18000ec8a  mov     rax, qword ptr cs:ID_RA_LOWH_REPAIR_NO_PUBLIC_V4_ADDR_HT+8
0x18000ec91  sub     rax, [rdx+8]
0x18000ec95  test    rax, rax
0x18000ec98  jz      loc_18000EE4B
0x18000ec9e  mov     rax, qword ptr cs:ID_RA_LOWH_REPAIR_NO_PUBLIC_V4_AND_TER_ADDR_HT
0x18000eca5  sub     rax, [rdx]
0x18000eca8  jnz     short loc_18000ECB5
0x18000ecaa  mov     rax, qword ptr cs:ID_RA_LOWH_REPAIR_NO_PUBLIC_V4_AND_TER_ADDR_HT+8
0x18000ecb1  sub     rax, [rdx+8]
0x18000ecb5  test    rax, rax
0x18000ecb8  jz      loc_18000EE4B
0x18000ecbe  mov     rax, qword ptr cs:ID_RA_LOWH_REPAIR_PUBLIC_FW_PROFILE_HT
0x18000ecc5  sub     rax, [rdx]
0x18000ecc8  jnz     short loc_18000ECD5
0x18000ecca  mov     rax, qword ptr cs:ID_RA_LOWH_REPAIR_PUBLIC_FW_PROFILE_HT+8
0x18000ecd1  sub     rax, [rdx+8]
0x18000ecd5  test    rax, rax
0x18000ecd8  jz      loc_18000EE4B
0x18000ecde  mov     rax, qword ptr cs:ID_RA_LOWH_REPAIR_TIME_SERVER_RESYNC
0x18000ece5  sub     rax, [rdx]
0x18000ece8  jnz     short loc_18000ECF5
0x18000ecea  mov     rax, qword ptr cs:ID_RA_LOWH_REPAIR_TIME_SERVER_RESYNC+8
0x18000ecf1  sub     rax, [rdx+8]
0x18000ecf5  test    rax, rax
0x18000ecf8  jnz     short loc_18000ED5A
0x18000ecfa  lea     edx, [rax+3]
0x18000ecfd  mov     ecx, 325h
0x18000ed02  call    ?LogRAProblem@@YAXHW4_RADIAG_PROBLEMSTATUS@@@Z; LogRAProblem(int,_RADIAG_PROBLEMSTATUS)
0x18000ed07  call    ?ReSyncSysTime@@YAJXZ; ReSyncSysTime(void)
0x18000ed0c  mov     ebx, eax
0x18000ed0e  test    eax, eax
0x18000ed10  jns     short loc_18000ED48
0x18000ed12  mov     [rsp+38h+var_10], eax; unsigned int
0x18000ed16  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000ed1d  lea     rax, aCrahelperclass_13; "CRAHelperClass::Repair"
0x18000ed24  mov     r9d, 572h; unsigned int
0x18000ed2a  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18000ed2f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000ed34  mov     edx, 5
0x18000ed39  mov     ecx, 325h
0x18000ed3e  call    ?LogRAProblem@@YAXHW4_RADIAG_PROBLEMSTATUS@@@Z; LogRAProblem(int,_RADIAG_PROBLEMSTATUS)
0x18000ed43  jmp     loc_18000EE87
0x18000ed48  mov     eax, 1
0x18000ed4d  mov     [rsi+0E0h], eax
0x18000ed53  mov     [rdi], eax
0x18000ed55  lea     edx, [rax+3]
0x18000ed58  jmp     short loc_18000ED39
0x18000ed5a  mov     rax, cs:ID_RA_LOWH_REPAIR_SYSSETTING_DISABLED
0x18000ed61  sub     rax, [rdx]
0x18000ed64  jnz     short loc_18000ED71
0x18000ed66  mov     rax, qword ptr cs:byte_180020FA8
0x18000ed6d  sub     rax, [rdx+8]
0x18000ed71  test    rax, rax
0x18000ed74  jnz     short loc_18000EDC8
0x18000ed76  mov     esi, 323h
0x18000ed7b  lea     edx, [rax+3]
0x18000ed7e  mov     ecx, esi
0x18000ed80  call    ?LogRAProblem@@YAXHW4_RADIAG_PROBLEMSTATUS@@@Z; LogRAProblem(int,_RADIAG_PROBLEMSTATUS)
0x18000ed85  call    ?RepairRASystemSetting@@YAJXZ; RepairRASystemSetting(void)
0x18000ed8a  mov     ebx, eax
0x18000ed8c  test    eax, eax
0x18000ed8e  jns     short loc_18000EDBB
0x18000ed90  mov     [rsp+38h+var_10], eax; unsigned int
0x18000ed94  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000ed9b  lea     rax, aCrahelperclass_13; "CRAHelperClass::Repair"
0x18000eda2  mov     r9d, 58Dh; unsigned int
0x18000eda8  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18000edad  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000edb2  mov     edx, 5
0x18000edb7  mov     ecx, esi
0x18000edb9  jmp     short loc_18000ED3E
0x18000edbb  mov     dword ptr [rdi], 1
0x18000edc1  mov     edx, 4
0x18000edc6  jmp     short loc_18000EDB7
0x18000edc8  mov     rax, qword ptr cs:ID_RA_LOWH_REPAIR_FIREWALL_DISABLED
0x18000edcf  xor     ebx, ebx
0x18000edd1  sub     rax, [rdx]
0x18000edd4  jnz     short loc_18000EDE1
0x18000edd6  mov     rax, qword ptr cs:ID_RA_LOWH_REPAIR_FIREWALL_DISABLED+8
0x18000eddd  sub     rax, [rdx+8]
0x18000ede1  test    rax, rax
0x18000ede4  jnz     loc_18000EE87
0x18000edea  lea     edx, [rax+3]
0x18000eded  mov     ecx, 324h
0x18000edf2  call    ?LogRAProblem@@YAXHW4_RADIAG_PROBLEMSTATUS@@@Z; LogRAProblem(int,_RADIAG_PROBLEMSTATUS)
0x18000edf7  call    ?EnableRAFirewallGroup@@YAJXZ; EnableRAFirewallGroup(void)
0x18000edfc  mov     ebx, eax
0x18000edfe  test    eax, eax
0x18000ee00  jns     short loc_18000EE33
0x18000ee02  mov     [rsp+38h+var_10], eax; unsigned int
0x18000ee06  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000ee0d  lea     rax, aCrahelperclass_13; "CRAHelperClass::Repair"
0x18000ee14  mov     r9d, 5A5h; unsigned int
0x18000ee1a  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18000ee1f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000ee24  mov     edx, 5
0x18000ee29  mov     ecx, 324h; this
0x18000ee2e  jmp     loc_18000ED3E
0x18000ee33  mov     eax, 1
0x18000ee38  mov     [rsi+9Ch], eax
0x18000ee3e  mov     [rsi+94h], eax
0x18000ee44  mov     [rdi], eax
0x18000ee46  lea     edx, [rax+3]
0x18000ee49  jmp     short loc_18000EE29
0x18000ee4b  lea     rdx, [rcx+90h]; unsigned int *
0x18000ee52  mov     [rsp+38h+var_18], rdi; enum tagREPAIR_STATUS *
0x18000ee57  mov     r9, r8; int *
0x18000ee5a  call    ?UserActionRepair@CNetDiagHelperImpl@@IEAAJPEAKKPEAJPEAW4tagREPAIR_STATUS@@@Z; CNetDiagHelperImpl::UserActionRepair(ulong *,ulong,long *,tagREPAIR_STATUS *)
0x18000ee5f  mov     ebx, eax
0x18000ee61  test    eax, eax
0x18000ee63  jns     short loc_18000EE87
0x18000ee65  mov     [rsp+38h+var_10], eax; unsigned int
0x18000ee69  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000ee70  lea     rax, aCrahelperclass_13; "CRAHelperClass::Repair"
0x18000ee77  mov     r9d, 567h; unsigned int
0x18000ee7d  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18000ee82  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000ee87  mov     eax, ebx
0x18000ee89  mov     rbx, [rsp+38h+arg_0]
0x18000ee8e  mov     rsi, [rsp+38h+arg_8]
0x18000ee93  add     rsp, 30h
0x18000ee97  pop     rdi
0x18000ee98  retn
```
