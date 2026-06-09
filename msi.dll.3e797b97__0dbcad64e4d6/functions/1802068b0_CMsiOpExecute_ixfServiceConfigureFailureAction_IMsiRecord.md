# CMsiOpExecute::ixfServiceConfigureFailureAction(IMsiRecord &)

- ea: `0x1802068b0`
- end: `0x1802073f2`
- name: `?ixfServiceConfigureFailureAction@CMsiOpExecute@@IEAA?AW4iesEnum@@AEAVIMsiRecord@@@Z`
- size: `2882`
- prototype: ``
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x1800c6ebc`
- `0x18012c888`
- `0x1801328bc`
- `0x1801e8810`

## callees

- `0x18000c4bc`
- `0x180018ee0`
- `0x180019cc0`
- `0x180065abc`
- `0x180066708`
- `0x18008c93c`
- `0x1800b91ac`
- `0x1800c0678`
- `0x1800d04fc`
- `0x1800d7594`
- `0x1800dcef8`
- `0x1801e7390`
- `0x1801e9fa8`
- `0x1801ea0fc`
- `0x1801eb9bc`
- `0x1801f5b68`
- `0x1802068b0`
- `0x180266010`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x1802071fc`
- `ADVAPI32!CloseServiceHandle` at `0x1802071fc`
- `KERNEL32!GetLastError` at `0x180206c9d`
- `KERNEL32!GetLastError` at `0x1802070c0`
- `KERNEL32!GetLastError` at `0x1802071dd`
- `KERNEL32!GetLastError` at `0x180206c9d`
- `KERNEL32!GetLastError` at `0x1802070c0`
- `KERNEL32!GetLastError` at `0x1802071dd`

## string_xrefs

- `0x180206984`: `Changing configuration of failure action for service %s.`
- `0x1802071e9`: `Error: %d. Failed to change configuration of failure action for service %s because handle to the service could be obtained. Check if the service exists on the system.`
- `0x180206a53`: `Warning: ResetPeriod is <blank>. Trying to change current configuration of failure action for service %s. Replacing with default argument INFINITE`
- `0x180207180`: `Error: invalid ResetPeriod %d. Failed to change configuration of failure action for service %s`
- `0x180206be6`: `Error: Number of Actions (%s) != Number of DelayActions (%s). Failed to change configuration of failure action for service %s`
- `0x180206cae`: `Error: %d. Failed to change configuration of failure action for service %s`
- `0x180206d9c`: `Error <Type: %s; Delay:%s> is an invalid Failure Action. Failed to change configuration of failure action for service %s`
- `0x1802070cc`: `Error: %d. Failed to change current configuration of failure action for service %s`
- `0x18020726a`: `Failed to change configuration of failure action for service %s`
- `0x180207349`: `Done changing configuration of failure action for service %s`

## pseudocode

```c
__int64 __fastcall CMsiOpExecute::ixfServiceConfigureFailureAction(CMsiOpExecute *a1, __int64 *a2)
{
  const struct IMsiString *v3; // r12
  const struct IMsiString *v4; // rbx
  const struct IMsiString *ServiceDisplayNameW; // rdi
  const struct IMsiString *v6; // rbx
  const struct IMsiString *v7; // rsi
  void *v8; // r15
  const unsigned __int16 *v9; // rax
  const struct IMsiString *v10; // r14
  SC_HANDLE ServiceHandle; // rax
  __int64 v12; // rcx
  const unsigned __int16 *v13; // rax
  int v14; // eax
  const unsigned __int16 *v15; // r14
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  const struct IMsiString *v20; // r14
  CMsiOpExecute *v21; // rcx
  CMsiOpExecute *v22; // rcx
  unsigned __int16 **v23; // rax
  int v24; // r14d
  const unsigned __int16 *v25; // r15
  MsiString *v26; // rax
  const unsigned __int16 *v27; // r14
  MsiString *v28; // rax
  const unsigned __int16 *v29; // rax
  char v30; // r14
  const unsigned __int16 *v31; // r14
  DWORD v32; // eax
  char v33; // r14
  int i; // eax
  __int64 v35; // r14
  int IntegerValue; // eax
  const unsigned __int16 *v37; // rax
  void (__fastcall *v38)(struct IMsiRecord *, __int64, __int64); // r15
  __int64 v39; // r14
  void (__fastcall *v40)(struct IMsiRecord *, __int64, __int64); // r15
  __int64 v41; // rax
  struct IMsiRecord *v42; // r13
  __int64 v43; // r14
  MsiString *v44; // rax
  __int64 v45; // rcx
  const unsigned __int16 **v46; // r15
  void (__fastcall *v47)(struct IMsiRecord *, __int64, _QWORD); // r14
  MsiString *v48; // rax
  void (__fastcall *v49)(struct IMsiRecord *, __int64, _QWORD); // r14
  MsiString *v50; // rax
  bool v51; // zf
  unsigned int v52; // r13d
  int v53; // r14d
  MsiString *v54; // rax
  unsigned int v55; // r13d
  int v56; // r14d
  MsiString *v57; // rax
  __int64 v58; // r9
  const unsigned __int16 *v59; // r14
  DWORD LastError; // eax
  const unsigned __int16 *v61; // r9
  __int64 v62; // rcx
  const unsigned __int16 *v63; // rax
  const unsigned __int16 *v64; // rax
  const unsigned __int16 *v66; // rax
  _DWORD *v67; // [rsp+60h] [rbp-69h]
  __int64 v68; // [rsp+68h] [rbp-61h] BYREF
  __int64 v69; // [rsp+70h] [rbp-59h] BYREF
  int v70; // [rsp+78h] [rbp-51h]
  int v71; // [rsp+7Ch] [rbp-4Dh]
  __int64 v72; // [rsp+80h] [rbp-49h] BYREF
  SC_HANDLE hSCObject; // [rsp+88h] [rbp-41h]
  void *v74; // [rsp+90h] [rbp-39h]
  void *v75; // [rsp+98h] [rbp-31h]
  const struct IMsiString *v76; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v77; // [rsp+A8h] [rbp-21h]
  __int64 v78; // [rsp+B0h] [rbp-19h]
  _DWORD v79[2]; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v80; // [rsp+C0h] [rbp-9h]
  __int64 v81; // [rsp+C8h] [rbp-1h]
  int v82; // [rsp+D0h] [rbp+7h]
  int v83; // [rsp+D4h] [rbp+Bh]
  _DWORD *v84; // [rsp+D8h] [rbp+Fh]
  int v86; // [rsp+138h] [rbp+6Fh] BYREF
  unsigned int *v87; // [rsp+140h] [rbp+77h] BYREF
  struct IMsiRecord *SharedRecord; // [rsp+148h] [rbp+7Fh] BYREF

  LODWORD(SharedRecord) = 0;
  v3 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 2);
  v76 = v3;
  v4 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 1);
  ServiceDisplayNameW = GetServiceDisplayNameW(v4, v3);
  (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v4 + 16LL))(v4);
  v6 = (const struct IMsiString *)&MsiString::s_NullString;
  v7 = (const struct IMsiString *)&MsiString::s_NullString;
  MsiString::MsiString((MsiString *)&v69, &Default);
  MsiString::MsiString((MsiString *)&v68, &Default);
  v8 = 0;
  v75 = 0;
  v74 = 0;
  if ( g_dmDiagnosticMode )
  {
    v9 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
    DebugString(
      10,
      0,
      0,
      L"Changing configuration of failure action for service %s.",
      v9,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
  v10 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 1);
  ServiceHandle = GetServiceHandle(v10, v3, 3u);
  v12 = *(_QWORD *)v10;
  hSCObject = ServiceHandle;
  (*(void (__fastcall **)(const struct IMsiString *))(v12 + 16))(v10);
  if ( (unsigned __int64)hSCObject - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( !g_dmDiagnosticMode )
      goto LABEL_42;
    v59 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
    LastError = GetLastError();
    v61 = L"Error: %d. Failed to change configuration of failure action for service %s because handle to the service could"
           " be obtained. Check if the service exists on the system.";
LABEL_41:
    DebugString(
      9,
      0,
      0,
      v61,
      (const unsigned __int16 *)LastError,
      v59,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
LABEL_42:
    v33 = 0;
    goto LABEL_51;
  }
  if ( (*(unsigned int (__fastcall **)(__int64 *, __int64))(*a2 + 32))(a2, 4) )
  {
    if ( g_dmDiagnosticMode )
    {
      v13 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
      DebugString(
        9,
        0,
        0,
        L"Warning: ResetPeriod is <blank>. Trying to change current configuration of failure action for service %s. Replac"
         "ing with default argument INFINITE",
        v13,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    v71 = -1;
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 56))(a2, 4);
    v15 = (const unsigned __int16 *)v14;
    v71 = v14;
    if ( v14 < 0 )
    {
      if ( g_dmDiagnosticMode )
      {
        v63 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
        DebugString(
          9,
          0,
          0,
          L"Error: invalid ResetPeriod %d. Failed to change configuration of failure action for service %s",
          v15,
          v63,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      goto LABEL_48;
    }
  }
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 80))(a2, 5);
  v17 = *a2;
  v78 = v16;
  v18 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v17 + 80))(a2, 6);
  v19 = *a2;
  v77 = v18;
  v7 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *, __int64))(v19 + 72))(a2, 7);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  v20 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 8);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  v86 = 0;
  LODWORD(v87) = 0;
  v6 = v20;
  v74 = CMsiOpExecute::NewArgumentArray(v21, v7, &v86);
  v23 = CMsiOpExecute::NewArgumentArray(v22, v20, (int *)&v87);
  v24 = v86;
  v75 = v23;
  if ( v86 != (_DWORD)v87 )
  {
    if ( g_dmDiagnosticMode )
    {
      v25 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
      v26 = MsiString::MsiString((MsiString *)&v72, (int)v87);
      v27 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v26 + 80LL))(*(_QWORD *)v26);
      v28 = MsiString::MsiString((MsiString *)&SharedRecord, v86);
      v29 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 80LL))(*(_QWORD *)v28);
      DebugString(
        9,
        0,
        0,
        L"Error: Number of Actions (%s) != Number of DelayActions (%s). Failed to change configuration of failure action for service %s",
        v29,
        v27,
        v25,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
      v30 = 3;
    }
    else
    {
      v30 = 0;
    }
    if ( (v30 & 2) != 0 )
    {
      v30 &= ~2u;
      (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)SharedRecord + 16LL))(SharedRecord);
    }
    if ( (v30 & 1) != 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
LABEL_48:
    v33 = 0;
    v8 = 0;
    goto LABEL_51;
  }
  v67 = operator new(saturated_mul(v86, 8u));
  if ( v67 )
  {
    for ( i = 0; ; i = v70 + 1 )
    {
      v70 = i;
      if ( i >= v24 )
        break;
      v35 = i;
      LODWORD(v87) = 0;
      LODWORD(SharedRecord) = 0;
      LODWORD(v72) = GetIntegerValue(*((const unsigned __int16 **)v74 + i), (enum Bool *)&v87);
      IntegerValue = GetIntegerValue(*((const unsigned __int16 **)v75 + v35), (enum Bool *)&SharedRecord);
      if ( !(_DWORD)v87 || !(_DWORD)SharedRecord || IntegerValue < 0 )
      {
        if ( g_dmDiagnosticMode )
        {
          v37 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
          DebugString(
            9,
            0,
            0,
            L"Error <Type: %s; Delay:%s> is an invalid Failure Action. Failed to change configuration of failure action for service %s",
            *((const unsigned __int16 **)v74 + v35),
            *((const unsigned __int16 **)v75 + v35),
            v37,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        goto LABEL_20;
      }
      v67[2 * v35] = v72;
      v67[2 * v35 + 1] = IntegerValue;
      v24 = v86;
    }
    SharedRecord = CMsiOpExecute::GetSharedRecord(a1, 8);
    v38 = *(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)SharedRecord + 120LL);
    v39 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 1);
    v38(SharedRecord, 1, v39);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v40 = *(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)SharedRecord + 120LL);
    v41 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 2);
    v42 = SharedRecord;
    v43 = v41;
    v40(SharedRecord, 2, v41);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v87 = 0;
    v44 = MsiString::MsiString((MsiString *)&v72, (const struct MsiString *)&v76);
    if ( !(unsigned __int8)CMsiOpExecute::QueryServiceConfiguration(v45, hSCObject, v44, 2, &v87) )
      goto LABEL_20;
    v46 = (const unsigned __int16 **)v87;
    (*(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)v42 + 104LL))(v42, 4, *v87);
    v47 = *(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)v42 + 120LL);
    v48 = MsiString::MsiString((MsiString *)&v87, v46[1]);
    v47(v42, 5, *(_QWORD *)v48);
    (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v87 + 16LL))(v87);
    v49 = *(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)v42 + 120LL);
    v50 = MsiString::MsiString((MsiString *)&v87, v46[2]);
    v49(v42, 6, *(_QWORD *)v50);
    (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v87 + 16LL))(v87);
    v51 = *((_DWORD *)v46 + 6) == 0;
    LODWORD(v87) = 0;
    if ( !v51 )
    {
      v52 = (unsigned int)v87;
      do
      {
        v53 = *(_DWORD *)&v46[4][4 * v52];
        MsiString::operator+=(&v69, &dword_1802C8B84);
        v54 = MsiString::MsiString((MsiString *)&v87, v53);
        MsiString::operator+=(&v69, v54);
        (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v87 + 16LL))(v87);
        ++v52;
      }
      while ( v52 < *((_DWORD *)v46 + 6) );
      v42 = SharedRecord;
    }
    MsiString::operator+=(&v69, &dword_1802C8B84);
    (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)v42 + 120LL))(v42, 7, v69);
    v51 = *((_DWORD *)v46 + 6) == 0;
    LODWORD(v87) = 0;
    if ( !v51 )
    {
      v55 = (unsigned int)v87;
      do
      {
        v56 = *(_DWORD *)&v46[4][4 * v55 + 2];
        MsiString::operator+=(&v68, &dword_1802C8B84);
        v57 = MsiString::MsiString((MsiString *)&v87, v56);
        MsiString::operator+=(&v68, v57);
        (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v87 + 16LL))(v87);
        ++v55;
      }
      while ( v55 < *((_DWORD *)v46 + 6) );
      v42 = SharedRecord;
    }
    MsiString::operator+=(&v68, &dword_1802C8B84);
    (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)v42 + 120LL))(v42, 8, v68);
    v8 = v67;
    v82 = v86;
    v79[0] = v71;
    v81 = v77;
    v80 = v78;
    v79[1] = 0;
    v83 = 0;
    v84 = v67;
    if ( (unsigned int)((__int64 (__fastcall *)(SC_HANDLE, __int64, _DWORD *))ADVAPI32::ChangeServiceConfig2W)(
                         hSCObject,
                         2,
                         v79) )
    {
      v33 = 1;
      v62 = *((_QWORD *)a1 + 4);
      if ( !v62 )
        goto LABEL_51;
      LOBYTE(v58) = 1;
      if ( (unsigned __int8)WriteScriptRecord(v62, 151, v42, v58, *((_QWORD *)a1 + 2)) )
        goto LABEL_51;
      goto LABEL_42;
    }
    if ( !g_dmDiagnosticMode )
      goto LABEL_42;
    v59 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
    LastError = GetLastError();
    v61 = L"Error: %d. Failed to change current configuration of failure action for service %s";
    goto LABEL_41;
  }
  if ( g_dmDiagnosticMode )
  {
    v31 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
    v32 = GetLastError();
    DebugString(
      9,
      0,
      0,
      L"Error: %d. Failed to change configuration of failure action for service %s",
      (const unsigned __int16 *)v32,
      v31,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
LABEL_20:
  v8 = v67;
  v33 = 0;
LABEL_51:
  CloseServiceHandle(hSCObject);
  if ( v74 )
    operator delete(v74);
  if ( v75 )
    operator delete(v75);
  if ( v8 )
    operator delete(v8);
  if ( v33 )
  {
    if ( g_dmDiagnosticMode )
    {
      v66 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
      DebugString(
        10,
        0,
        0,
        L"Done changing configuration of failure action for service %s",
        v66,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v6 + 16LL))(v6);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v7 + 16LL))(v7);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)ServiceDisplayNameW + 16LL))(ServiceDisplayNameW);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 16LL))(v3);
    return 1;
  }
  else
  {
    if ( g_dmDiagnosticMode )
    {
      v64 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
      DebugString(
        9,
        0,
        0,
        L"Failed to change configuration of failure action for service %s",
        v64,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    CMsiOpExecute::DispatchError(a1, 0x1000000, 1939, ServiceDisplayNameW, v3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v6 + 16LL))(v6);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v7 + 16LL))(v7);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)ServiceDisplayNameW + 16LL))(ServiceDisplayNameW);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 16LL))(v3);
    return 3;
  }
}

```

## disassembly

```asm
0x1802068b0  mov     [rsp-8+arg_0], rcx
0x1802068b5  push    rbp
0x1802068b6  push    rbx
0x1802068b7  push    rsi
0x1802068b8  push    rdi
0x1802068b9  push    r12
0x1802068bb  push    r13
0x1802068bd  push    r14
0x1802068bf  push    r15
0x1802068c1  lea     rbp, [rsp-1Fh]
0x1802068c6  sub     rsp, 0E8h
0x1802068cd  mov     r13, rdx
0x1802068d0  xor     r14d, r14d
0x1802068d3  mov     dword ptr [rbp+57h+arg_18], r14d
0x1802068d7  mov     rcx, r13
0x1802068da  mov     rax, [rdx]
0x1802068dd  lea     edx, [r14+2]
0x1802068e1  mov     rax, [rax+48h]
0x1802068e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802068ea  mov     r12, rax
0x1802068ed  mov     [rbp+57h+var_80], rax
0x1802068f1  mov     rax, [r13+0]
0x1802068f5  lea     edx, [r14+1]
0x1802068f9  mov     rcx, r13
0x1802068fc  mov     rax, [rax+48h]
0x180206900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206905  mov     rdx, r12; struct IMsiString *
0x180206908  mov     rcx, rax; struct IMsiString *
0x18020690b  mov     rbx, rax
0x18020690e  call    ?GetServiceDisplayNameW@@YAAEBVIMsiString@@AEBV1@0@Z; GetServiceDisplayNameW(IMsiString const &,IMsiString const &)
0x180206913  mov     rcx, [rbx]
0x180206916  mov     rdi, rax
0x180206919  mov     rax, [rcx+10h]
0x18020691d  mov     rcx, rbx
0x180206920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206925  lea     rbx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18020692c  lea     rdx, Default; unsigned __int16 *
0x180206933  mov     rsi, rbx
0x180206936  lea     rcx, [rbp+57h+var_B0]; this
0x18020693a  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x18020693f  lea     rdx, Default; unsigned __int16 *
0x180206946  lea     rcx, [rbp+57h+var_B8]; this
0x18020694a  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x18020694f  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x180206956  mov     r15d, r14d
0x180206959  mov     [rbp+57h+var_88], r14
0x18020695d  mov     [rbp+57h+var_90], r14
0x180206961  jz      short loc_1802069B6
0x180206963  mov     rax, [r12]
0x180206967  mov     rcx, r12
0x18020696a  mov     rax, [rax+50h]
0x18020696e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206973  lea     rcx, aNull; "(NULL)"
0x18020697a  mov     [rsp+120h+var_C8], r14; void *
0x18020697f  mov     [rsp+120h+var_D0], r14d; unsigned int
0x180206984  lea     r9, aChangingConfig_0; "Changing configuration of failure actio"...
0x18020698b  mov     [rsp+120h+var_D8], rcx; unsigned __int16 *
0x180206990  xor     edx, edx; unsigned __int16
0x180206992  mov     [rsp+120h+var_E0], rcx; unsigned __int16 *
0x180206997  xor     r8d, r8d; int
0x18020699a  mov     [rsp+120h+var_E8], rcx; unsigned __int16 *
0x18020699f  mov     [rsp+120h+var_F0], rcx; unsigned __int16 *
0x1802069a4  mov     [rsp+120h+var_F8], rcx; unsigned __int16 *
0x1802069a9  lea     ecx, [rdx+0Ah]; int
0x1802069ac  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x1802069b1  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1802069b6  mov     rax, [r13+0]
0x1802069ba  mov     edx, 1
0x1802069bf  mov     rcx, r13
0x1802069c2  mov     rax, [rax+48h]
0x1802069c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802069cb  mov     r8d, 3; unsigned int
0x1802069d1  mov     rdx, r12; struct IMsiString *
0x1802069d4  mov     rcx, rax; struct IMsiString *
0x1802069d7  mov     r14, rax
0x1802069da  call    ?GetServiceHandle@@YAPEAUSC_HANDLE__@@AEBVIMsiString@@0K@Z; GetServiceHandle(IMsiString const &,IMsiString const &,ulong)
0x1802069df  mov     rcx, [r14]
0x1802069e2  mov     [rbp+57h+hSCObject], rax
0x1802069e6  mov     rax, [rcx+10h]
0x1802069ea  mov     rcx, r14
0x1802069ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802069f2  mov     rcx, [rbp+57h+hSCObject]
0x1802069f6  dec     rcx
0x1802069f9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1802069fd  ja      loc_1802071BA
0x180206a03  mov     rcx, [r13+0]
0x180206a07  mov     edx, 4
0x180206a0c  mov     rax, [rcx+20h]
0x180206a10  mov     rcx, r13
0x180206a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206a18  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180206a1c  xor     r14d, r14d
0x180206a1f  mov     r15d, 9
0x180206a25  test    eax, eax
0x180206a27  jz      short loc_180206A8E
0x180206a29  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x180206a30  jz      short loc_180206A89
0x180206a32  mov     rax, [r12]
0x180206a36  mov     rcx, r12
0x180206a39  mov     rax, [rax+50h]
0x180206a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206a42  lea     rcx, aNull; "(NULL)"
0x180206a49  mov     [rsp+120h+var_C8], r14; void *
0x180206a4e  mov     [rsp+120h+var_D0], r14d; unsigned int
0x180206a53  lea     r9, aWarningResetpe; "Warning: ResetPeriod is <blank>. Trying"...
0x180206a5a  mov     [rsp+120h+var_D8], rcx; unsigned __int16 *
0x180206a5f  xor     edx, edx; unsigned __int16
0x180206a61  mov     [rsp+120h+var_E0], rcx; unsigned __int16 *
0x180206a66  xor     r8d, r8d; int
0x180206a69  mov     [rsp+120h+var_E8], rcx; unsigned __int16 *
0x180206a6e  mov     [rsp+120h+var_F0], rcx; unsigned __int16 *
0x180206a73  mov     [rsp+120h+var_F8], rcx; unsigned __int16 *
0x180206a78  mov     ecx, r15d; int
0x180206a7b  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x180206a80  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180206a85  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180206a89  mov     [rbp+57h+var_A4], ecx
0x180206a8c  jmp     short loc_180206AB2
0x180206a8e  mov     rax, [r13+0]
0x180206a92  mov     edx, 4
0x180206a97  mov     rcx, r13
0x180206a9a  mov     rax, [rax+38h]
0x180206a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206aa3  movsxd  r14, eax
0x180206aa6  mov     [rbp+57h+var_A4], r14d
0x180206aaa  test    eax, eax
0x180206aac  js      loc_180207153
0x180206ab2  mov     rcx, [r13+0]
0x180206ab6  mov     edx, 5
0x180206abb  mov     rax, [rcx+50h]
0x180206abf  mov     rcx, r13
0x180206ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206ac7  mov     rcx, [r13+0]
0x180206acb  mov     edx, 6
0x180206ad0  mov     [rbp+57h+var_70], rax
0x180206ad4  mov     rax, [rcx+50h]
0x180206ad8  mov     rcx, r13
0x180206adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206ae0  mov     rcx, [r13+0]
0x180206ae4  mov     edx, 7
0x180206ae9  mov     [rbp+57h+var_78], rax
0x180206aed  mov     rax, [rcx+48h]
0x180206af1  mov     rcx, r13
0x180206af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206af9  mov     rcx, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180206b00  mov     rsi, rax
0x180206b03  mov     rax, [rcx+10h]
0x180206b07  mov     rcx, rbx
0x180206b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206b0f  mov     rax, [r13+0]
0x180206b13  mov     edx, 8
0x180206b18  mov     rcx, r13
0x180206b1b  mov     rax, [rax+48h]
0x180206b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206b24  mov     rcx, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180206b2b  mov     r14, rax
0x180206b2e  mov     rax, [rcx+10h]
0x180206b32  mov     rcx, rbx
0x180206b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206b3a  lea     r8, [rbp+57h+arg_8]; int *
0x180206b3e  mov     [rbp+57h+arg_8], 0
0x180206b45  mov     rdx, rsi; struct IMsiString *
0x180206b48  mov     dword ptr [rbp+57h+arg_10], 0
0x180206b4f  mov     rbx, r14
0x180206b52  call    ?NewArgumentArray@CMsiOpExecute@@IEAAPEAPEAGAEBVIMsiString@@AEAH@Z; CMsiOpExecute::NewArgumentArray(IMsiString const &,int &)
0x180206b57  lea     r8, [rbp+57h+arg_10]; int *
0x180206b5b  mov     [rbp+57h+var_90], rax
0x180206b5f  mov     rdx, r14; struct IMsiString *
0x180206b62  call    ?NewArgumentArray@CMsiOpExecute@@IEAAPEAPEAGAEBVIMsiString@@AEAH@Z; CMsiOpExecute::NewArgumentArray(IMsiString const &,int &)
0x180206b67  movsxd  r14, [rbp+57h+arg_8]
0x180206b6b  mov     [rbp+57h+var_88], rax
0x180206b6f  cmp     r14d, dword ptr [rbp+57h+arg_10]
0x180206b73  jz      loc_180206C5A
0x180206b79  xor     r13d, r13d
0x180206b7c  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x180206b83  jz      loc_180206C1E
0x180206b89  mov     rcx, [r12]
0x180206b8d  mov     rax, [rcx+50h]
0x180206b91  mov     rcx, r12
0x180206b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206b99  mov     edx, dword ptr [rbp+57h+arg_10]; int
0x180206b9c  lea     rcx, [rbp+57h+var_A0]; this
0x180206ba0  mov     r15, rax
0x180206ba3  call    ??0MsiString@@QEAA@H@Z; MsiString::MsiString(int)
0x180206ba8  mov     rcx, [rax]
0x180206bab  mov     r8, [rcx]
0x180206bae  mov     rax, [r8+50h]
0x180206bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206bb7  mov     edx, [rbp+57h+arg_8]; int
0x180206bba  lea     rcx, [rbp+57h+arg_18]; this
0x180206bbe  mov     r14, rax
0x180206bc1  call    ??0MsiString@@QEAA@H@Z; MsiString::MsiString(int)
0x180206bc6  mov     rcx, [rax]
0x180206bc9  mov     rdx, [rcx]
0x180206bcc  mov     rax, [rdx+50h]
0x180206bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206bd5  mov     [rsp+120h+var_C8], r13; void *
0x180206bda  lea     rcx, aNull; "(NULL)"
0x180206be1  mov     [rsp+120h+var_D0], r13d; unsigned int
0x180206be6  lea     r9, aErrorNumberOfA; "Error: Number of Actions (%s) != Number"...
0x180206bed  mov     [rsp+120h+var_D8], rcx; unsigned __int16 *
0x180206bf2  xor     edx, edx; unsigned __int16
0x180206bf4  mov     [rsp+120h+var_E0], rcx; unsigned __int16 *
0x180206bf9  xor     r8d, r8d; int
0x180206bfc  mov     [rsp+120h+var_E8], rcx; unsigned __int16 *
0x180206c01  mov     [rsp+120h+var_F0], r15; unsigned __int16 *
0x180206c06  mov     [rsp+120h+var_F8], r14; unsigned __int16 *
0x180206c0b  lea     ecx, [rdx+9]; int
0x180206c0e  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x180206c13  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180206c18  lea     r14d, [r13+3]
0x180206c1c  jmp     short loc_180206C21
0x180206c1e  mov     r14d, r13d
0x180206c21  test    r14b, 2
0x180206c25  jz      short loc_180206C3B
0x180206c27  mov     rcx, [rbp+57h+arg_18]
0x180206c2b  and     r14d, 0FFFFFFFDh
0x180206c2f  mov     rax, [rcx]
0x180206c32  mov     rax, [rax+10h]
0x180206c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206c3b  test    r14b, 1
0x180206c3f  jz      loc_1802071B2
0x180206c45  mov     rcx, [rbp+57h+var_A0]
0x180206c49  mov     rax, [rcx]
0x180206c4c  mov     rax, [rax+10h]
0x180206c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206c55  jmp     loc_1802071B2
0x180206c5a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180206c61  mov     eax, 8
0x180206c66  mul     r14
0x180206c69  cmovb   rax, rcx
0x180206c6d  mov     rcx, rax; unsigned __int64
0x180206c70  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180206c75  mov     [rbp+57h+var_C0], rax
0x180206c79  test    rax, rax
0x180206c7c  jnz     short loc_180206CFA
0x180206c7e  xor     r13d, r13d
0x180206c81  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x180206c88  jz      short loc_180206CEE
0x180206c8a  mov     rcx, [r12]
0x180206c8e  mov     rax, [rcx+50h]
0x180206c92  mov     rcx, r12
0x180206c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206c9a  mov     r14, rax
0x180206c9d  call    cs:__imp_GetLastError
0x180206ca4  nop     dword ptr [rax+rax+00h]
0x180206ca9  mov     [rsp+120h+var_C8], r13; void *
0x180206cae  lea     r9, aErrorDFailedTo_5; "Error: %d. Failed to change configurati"...
0x180206cb5  mov     [rsp+120h+var_D0], r13d; unsigned int
0x180206cba  mov     ecx, eax
0x180206cbc  lea     rax, aNull; "(NULL)"
0x180206cc3  mov     [rsp+120h+var_D8], rax; unsigned __int16 *
0x180206cc8  mov     [rsp+120h+var_E0], rax; unsigned __int16 *
0x180206ccd  mov     [rsp+120h+var_E8], rax; unsigned __int16 *
0x180206cd2  mov     [rsp+120h+var_F0], rax; unsigned __int16 *
0x180206cd7  mov     [rsp+120h+var_F8], r14; unsigned __int16 *
0x180206cdc  mov     [rsp+120h+var_100], rcx; unsigned __int16 *
0x180206ce1  xor     edx, edx; unsigned __int16
0x180206ce3  xor     r8d, r8d; int
0x180206ce6  mov     ecx, r15d; int
0x180206ce9  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180206cee  mov     r15, [rbp+57h+var_C0]
0x180206cf2  mov     r14b, r13b
0x180206cf5  jmp     loc_1802071F8
0x180206cfa  xor     eax, eax
0x180206cfc  mov     [rbp+57h+var_A8], eax
0x180206cff  cmp     eax, r14d
0x180206d02  jge     loc_180206DD6
0x180206d08  movsxd  r14, eax
0x180206d0b  lea     rdx, [rbp+57h+arg_10]; enum Bool *
0x180206d0f  mov     rax, [rbp+57h+var_90]
0x180206d13  mov     dword ptr [rbp+57h+arg_10], 0
0x180206d1a  mov     dword ptr [rbp+57h+arg_18], 0
0x180206d21  mov     rcx, [rax+r14*8]; unsigned __int16 *
0x180206d25  call    ?GetIntegerValue@@YAHPEBGPEAW4Bool@@@Z; GetIntegerValue(ushort const *,Bool *)
0x180206d2a  mov     dword ptr [rbp+57h+var_A0], eax
0x180206d2d  lea     rdx, [rbp+57h+arg_18]; enum Bool *
0x180206d31  mov     rax, [rbp+57h+var_88]
0x180206d35  mov     rcx, [rax+r14*8]; unsigned __int16 *
0x180206d39  call    ?GetIntegerValue@@YAHPEBGPEAW4Bool@@@Z; GetIntegerValue(ushort const *,Bool *)
0x180206d3e  cmp     dword ptr [rbp+57h+arg_10], 0
0x180206d42  mov     ecx, eax
0x180206d44  jz      short loc_180206D6B
0x180206d46  cmp     dword ptr [rbp+57h+arg_18], 0
0x180206d4a  jz      short loc_180206D6B
0x180206d4c  test    eax, eax
0x180206d4e  js      short loc_180206D6B
0x180206d50  mov     rax, [rbp+57h+var_C0]
0x180206d54  mov     edx, dword ptr [rbp+57h+var_A0]
0x180206d57  mov     [rax+r14*8], edx
0x180206d5b  mov     [rax+r14*8+4], ecx
0x180206d60  mov     eax, [rbp+57h+var_A8]
0x180206d63  mov     r14d, [rbp+57h+arg_8]
0x180206d67  inc     eax
0x180206d69  jmp     short loc_180206CFC
0x180206d6b  xor     r13d, r13d
0x180206d6e  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x180206d75  jz      loc_180206CEE
0x180206d7b  mov     rax, [r12]
0x180206d7f  mov     rcx, r12
  ... truncated ...
```
