# PortOpenEx

- ea: `0x180022bd0`
- end: `0x180023664`
- name: `PortOpenEx`
- size: `2708`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180037410`

## callees

- `0x180005a20`
- `0x180005ad8`
- `0x180005bcc`
- `0x180005bfc`
- `0x180005c40`
- `0x18000c3c0`
- `0x18000c424`
- `0x180022bd0`
- `0x1800335f0`
- `0x18003372c`
- `0x180035a08`
- `0x1800399a4`
- `0x180046fc4`
- `0x1800499f0`
- `0x18004aa34`
- `0x1800aa728`
- `0x1800aaa98`
- `0x1800ab588`
- `0x1800eb010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180022d35`
- `msvcrt!_stricmp` at `0x180022dce`
- `msvcrt!_stricmp` at `0x180022f00`
- `msvcrt!_stricmp` at `0x180022d35`
- `msvcrt!_stricmp` at `0x180022dce`
- `msvcrt!_stricmp` at `0x180022f00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022ce7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800232ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022ce7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800232ff`
- `ntdll!NtQueryInformationProcess` at `0x180023349`
- `ntdll!NtQueryInformationProcess` at `0x180023349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023369`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023369`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002331e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002331e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023546`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023546`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023503`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023503`

## string_xrefs

- `0x180023607`: `PortOpenEx: Failed`
- `0x1800234f6`: `wevtapi.dll`
- `0x18002352f`: `Windows Networking Vpn Plugin Platform/OperationalVerbose`
- `0x18002351a`: `Windows Networking Vpn Plugin Platform/Operational`

## pseudocode

```c
int __fastcall PortOpenEx(__int64 a1, _DWORD *a2, __int64 a3)
{
  struct _LIST_ENTRY *v5; // rcx
  const char *v6; // r14
  int v7; // ebp
  unsigned __int16 v8; // r15
  _QWORD *v9; // rbx
  unsigned int v10; // edi
  DWORD v11; // r12d
  __int64 v12; // rdx
  DWORD CurrentProcessId; // eax
  __int64 v14; // r8
  struct _LIST_ENTRY *v15; // r10
  _DWORD *v16; // rsi
  int v17; // ecx
  _WORD *v18; // r14
  int v19; // eax
  __int64 v20; // r9
  _QWORD *v21; // rdx
  _QWORD *v22; // rcx
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rdx
  HMODULE Library; // rax
  struct _LIST_ENTRY *Flink; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  HMODULE v30; // rbp
  __int64 v31; // rdx
  struct _LIST_ENTRY *v32; // rcx
  __int64 v33; // rax
  HANDLE v34; // rax
  void *v35; // rdi
  __int64 i; // rax
  char *v37; // rcx
  unsigned int v38; // eax
  unsigned int j; // ebp
  unsigned int v40; // esi
  HMODULE v41; // rbp
  unsigned int v42; // eax
  struct _LIST_ENTRY *v43; // rcx
  int v44; // eax
  unsigned int v46; // [rsp+30h] [rbp-48h]
  DWORD v47; // [rsp+34h] [rbp-44h]
  int v48; // [rsp+88h] [rbp+10h]
  unsigned int v49; // [rsp+90h] [rbp+18h]
  unsigned int ProcessInformation; // [rsp+98h] [rbp+20h] BYREF

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 106, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = (const char *)(a3 + 44);
  v7 = *(_DWORD *)(a3 + 8);
  v8 = 0;
  v49 = 0;
  v9 = 0;
  v46 = 0;
  v10 = 633;
  ProcessInformation = *(_DWORD *)(a3 + 40);
  v48 = v7;
  if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v5[1].Blink) & 0x2000) != 0
    && BYTE1(v5[1].Blink) >= 4u )
  {
    WPP_SF_s(v5[1].Flink, 107, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, a3 + 44);
    v5 = WPP_GLOBAL_Control;
  }
  if ( *a2 )
  {
    v11 = a2[2];
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 5u )
    {
      v12 = 108;
LABEL_18:
      WPP_SF_d(v5[1].Flink, v12, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v11);
    }
  }
  else
  {
    v11 = *(_DWORD *)(a3 + 4);
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 5u )
    {
      v12 = 109;
      goto LABEL_18;
    }
  }
  CurrentProcessId = GetCurrentProcessId();
  v15 = WPP_GLOBAL_Control;
  v47 = CurrentProcessId;
  if ( !MaxPorts )
  {
LABEL_82:
    LODWORD(Library) = v8;
    if ( v8 == MaxPorts )
    {
      v10 = 259;
      if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v15[1].Blink) & 0x2000) != 0
        && BYTE1(v15[1].Blink) >= 2u )
      {
        Flink = v15[1].Flink;
        v28 = 125;
        v29 = 259;
LABEL_122:
        LODWORD(Library) = WPP_SF_d(Flink, v28, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v29);
      }
    }
    goto LABEL_146;
  }
  while ( 1 )
  {
    v9 = (_QWORD *)*((_QWORD *)Pcb + v8);
    if ( !v9 )
      goto LABEL_75;
    v16 = v9 + 3;
    if ( !_stricmp((const char *)v9 + 72, v6) )
    {
      v14 = 1;
      v17 = v49;
      if ( (unsigned int)(*v16 - 2) > 1 )
        v17 = 1;
      v49 = v17;
      if ( ProcessInformation >= *(_DWORD *)(v9[154] + 76LL) )
      {
        v10 = 259;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v25 = 110;
LABEL_81:
          WPP_SF_d(v15[1].Flink, v25, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, 259);
          v15 = WPP_GLOBAL_Control;
          goto LABEL_82;
        }
        goto LABEL_82;
      }
    }
    if ( (unsigned int)(*v16 - 2) <= 1
      || (v7 & *((_DWORD *)v9 + 9)) == 0
      || v11 != v47 && (*((_BYTE *)v9 + 36) & 2) == 0 )
    {
      goto LABEL_74;
    }
    if ( (v9[153] & 8) != 0 )
      goto LABEL_74;
    v18 = (_WORD *)v9 + 22;
    if ( *((_WORD *)v9 + 22) >= 2u
      || _stricmp((const char *)v9 + 72, (const char *)(a3 + 44))
      || *v16 != 1 && (v7 & (_DWORD)v9[5]) != 0 )
    {
      goto LABEL_74;
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control[1].Flink,
        111,
        WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
        *v9,
        *((_DWORD *)v9 + 10));
      v15 = WPP_GLOBAL_Control;
    }
    if ( (v7 & 0x80u) != 0 && *((_DWORD *)v9 + 7) != 1 )
      goto LABEL_75;
    if ( ProcessInformation >= *(_DWORD *)(v9[154] + 76LL) )
    {
      v10 = 259;
      if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v15[1].Blink) & 0x2000) != 0
        && BYTE1(v15[1].Blink) >= 2u )
      {
        v25 = 112;
        goto LABEL_81;
      }
      goto LABEL_82;
    }
    if ( ProcessInformation > v46 )
    {
      ++v46;
      goto LABEL_75;
    }
    if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v15[1].Blink) & 0x2000) != 0
      && BYTE1(v15[1].Blink) >= 5u )
    {
      WPP_SF_Dd(
        v15[1].Flink,
        113,
        WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
        (unsigned int)*v16,
        *((_DWORD *)v9 + 7));
      v15 = WPP_GLOBAL_Control;
    }
    if ( *v16 == 1 )
    {
      if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v15[1].Blink) & 0x2000) != 0
        && BYTE1(v15[1].Blink) >= 5u )
      {
        WPP_SF_(v15[1].Flink, 114, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      }
      v19 = _stricmp((const char *)v9[6], "rastapi");
      v20 = *(unsigned int *)v9;
      v21 = v9 + 27;
      v22 = v9 + 1;
      if ( v19 )
      {
        v23 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *, HANDLE, __int64))(v9[6] + 24LL))(
                v22,
                v21,
                hIoCompletionPort,
                v20);
        v10 = v23;
        if ( !v23 )
          goto LABEL_99;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_75;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_64;
        v24 = 116;
      }
      else
      {
        v23 = ((__int64 (__fastcall *)(_QWORD *, _QWORD *, HANDLE, __int64, int))RastapiPortOpen)(
                v22,
                v21,
                hIoCompletionPort,
                v20,
                v7);
        v10 = v23;
        if ( !v23 )
          goto LABEL_99;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_75;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_64;
        v24 = 115;
      }
      WPP_SF_d(v15[1].Flink, v24, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v23);
      v15 = WPP_GLOBAL_Control;
LABEL_64:
      if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v15[1].Blink) & 0x2000) != 0
        && BYTE1(v15[1].Blink) >= 2u )
      {
        WPP_SF_sd(v15[1].Flink, 117, (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, (_DWORD)v9 + 8, v10);
LABEL_74:
        v15 = WPP_GLOBAL_Control;
        goto LABEL_75;
      }
      goto LABEL_75;
    }
    if ( *((_DWORD *)v9 + 7) == 1 )
    {
      if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v15[1].Blink) & 0x2000) != 0
        && BYTE1(v15[1].Blink) >= 5u )
      {
        WPP_SF_(v15[1].Flink, 118, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      }
      goto LABEL_92;
    }
    if ( *((_DWORD *)v9 + 7) == 4 )
    {
      FreeNotifierHandle((HANDLE)v9[58]);
      v9[58] = -1;
LABEL_92:
      ReOpenBiplexPort(v9);
      goto LABEL_99;
    }
    v10 = 602;
    if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v15[1].Blink) & 0x2000) != 0
      && BYTE1(v15[1].Blink) >= 5u )
    {
      WPP_SF_(v15[1].Flink, 119, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      goto LABEL_74;
    }
LABEL_75:
    if ( ++v8 >= (unsigned int)MaxPorts )
      break;
    v6 = (const char *)(a3 + 44);
  }
  if ( v10 )
    goto LABEL_82;
  v16 = v9 + 3;
  v18 = (_WORD *)v9 + 22;
LABEL_99:
  v30 = 0;
  ProcessInformation = 0;
  SetRasmanServiceStopControl(0);
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control[1].Flink,
      120,
      WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
      *v9,
      (unsigned __int16)*v18);
  }
  if ( *v16 == 1 )
    *((_DWORD *)v9 + 10) = 0;
  *v16 = 0;
  SetPortConnState(v32, v31, v9, 4);
  *((_DWORD *)v9 + 67) = 3;
  ++*v18;
  *((_DWORD *)v9 + 331) = 3;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control[1].Flink,
      121,
      WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
      *v9,
      (unsigned __int16)*v18);
  }
  v33 = v9[27];
  *((_DWORD *)v9 + 306) &= 0xFFFFFFEB;
  v9[28] = v33;
  v9[160] = -1;
  v9[31] = -1;
  *((_DWORD *)v9 + 68) = v11;
  v9[70] = 0;
  v9[71] = 0;
  v9[132] = 0;
  v9[131] = 0;
  v9[133] = 0;
  *((_DWORD *)v9 + 268) = 0;
  v9[150] = 0;
  v9[151] = 0;
  v9[152] = 0;
  v9[157] = 0;
  v9[159] = 0;
  *((_DWORD *)v9 + 322) = 0;
  if ( v11 != GetCurrentProcessId() )
  {
    v34 = OpenProcess(0x400u, 0, *((_DWORD *)v9 + 68));
    v35 = v34;
    if ( v34 )
    {
      if ( !NtQueryInformationProcess(v34, ProcessSessionInformation, &ProcessInformation, 4u, 0) )
        *((_DWORD *)v9 + 323) = ProcessInformation;
      CloseHandle(v35);
    }
  }
  for ( i = 0; i != 39; ++i )
  {
    *((_DWORD *)v9 + i + 183) = 0;
    *((_DWORD *)v9 + i + 222) = 0;
    *((_DWORD *)v9 + i + 144) = 0;
  }
  *((_DWORD *)v9 + 10) |= v48;
  v37 = *(char **)(a3 + 32);
  if ( (unsigned __int64)(v37 - 1) > 0xFFFFFFFFFFFFFFFDuLL
    || (Library = (HMODULE)ValidateHandleForRasman(v37, v11),
        v30 = Library,
        (((unsigned __int64)Library + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0) )
  {
    v38 = AddNotifierToList(v9 + 53, v30, 2, v11);
    v10 = v38;
    if ( v38 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 123, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v38);
      }
      LODWORD(Library) = FreeNotifierHandle(v30);
    }
    else
    {
      *(_QWORD *)(a3 + 16) = *v9;
      LODWORD(Library) = (_DWORD)v9 + 1080;
      v9[136] = v9 + 135;
      v9[135] = v9 + 135;
      *((_DWORD *)v9 + 274) = 0;
      if ( !*(_DWORD *)(a3 + 24) )
        LODWORD(Library) = (*(__int64 (__fastcall **)(_QWORD))(v9[6] + 32LL))(v9[27]);
      if ( v11 != v47 && v48 == 2 )
      {
        LODWORD(Library) = IsDefaultTracingEnabled();
        if ( (_DWORD)Library )
        {
          for ( j = 1; j < 6; ++j )
          {
            v40 = EnableAutoWPPTracingForSubComponent(j);
            if ( v40 )
              goto LABEL_142;
          }
          Library = LoadLibraryExW(L"wevtapi.dll", 0, 0x800u);
          v41 = Library;
          if ( Library )
          {
            v40 = EnableVpnPluginETWChannel(L"Windows Networking Vpn Plugin Platform/Operational", Library);
            if ( !v40 )
            {
              v40 = 0;
              v42 = EnableVpnPluginETWChannel(L"Windows Networking Vpn Plugin Platform/OperationalVerbose", v41);
              if ( v42 )
                v40 = v42;
            }
            LODWORD(Library) = FreeLibrary(v41);
            if ( v40 )
            {
LABEL_142:
              Library = (HMODULE)&WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                LODWORD(Library) = WPP_SF_d(
                                     WPP_GLOBAL_Control[1].Flink,
                                     124,
                                     WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                                     v40);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v29 = 2147942487LL;
    v10 = -2147024809;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      Flink = WPP_GLOBAL_Control[1].Flink;
      v28 = 122;
      goto LABEL_122;
    }
  }
LABEL_146:
  *(_DWORD *)a3 = v10;
  if ( !v49 )
    *(_DWORD *)(a3 + 8) |= 0x10000000u;
  v43 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
  {
    if ( v9 )
      v44 = *((_DWORD *)v9 + 10);
    else
      v44 = 0;
    LODWORD(Library) = WPP_SF_DdD(WPP_GLOBAL_Control[1].Flink, v49, v14, v10, v49, v44);
    v43 = WPP_GLOBAL_Control;
  }
  if ( v9 && v10 && v10 != 600 )
  {
    LODWORD(Library) = TelemetryEventWriteStateChange(v9, v10, "PortOpenEx: Failed");
    v43 = WPP_GLOBAL_Control;
  }
  if ( v43 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v43[1].Blink) & 0x2000) != 0
    && BYTE1(v43[1].Blink) >= 6u )
  {
    LODWORD(Library) = WPP_SF_d(v43[1].Flink, 127, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v10);
  }
  return (int)Library;
}

```

## disassembly

```asm
0x180022bd0  mov     [rsp+arg_0], rbx
0x180022bd5  push    rbp
0x180022bd6  push    rsi
0x180022bd7  push    rdi
0x180022bd8  push    r12
0x180022bda  push    r13
0x180022bdc  push    r14
0x180022bde  push    r15
0x180022be0  sub     rsp, 40h
0x180022be4  mov     r13, r8
0x180022be7  mov     rsi, rdx
0x180022bea  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bf1  lea     rdx, WPP_GLOBAL_Control
0x180022bf8  cmp     rcx, rdx
0x180022bfb  jz      short loc_180022C2F
0x180022bfd  test    dword ptr [rcx+1Ch], 2000h
0x180022c04  jz      short loc_180022C2F
0x180022c06  cmp     byte ptr [rcx+19h], 6
0x180022c0a  jb      short loc_180022C2F
0x180022c0c  mov     rcx, [rcx+10h]
0x180022c10  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180022c17  mov     edx, 6Ah ; 'j'
0x180022c1c  call    WPP_SF_
0x180022c21  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c28  lea     rdx, WPP_GLOBAL_Control
0x180022c2f  mov     eax, [r13+28h]
0x180022c33  lea     r14, [r13+2Ch]
0x180022c37  mov     ebp, [r13+8]
0x180022c3b  xor     r15d, r15d
0x180022c3e  mov     [rsp+78h+arg_10], r15d
0x180022c46  mov     ebx, r15d
0x180022c49  mov     [rsp+78h+var_48], r15d
0x180022c4e  mov     edi, 279h
0x180022c53  mov     [rsp+78h+ProcessInformation], eax
0x180022c5a  mov     [rsp+78h+arg_8], ebp
0x180022c61  mov     ebp, 2000h
0x180022c66  cmp     rcx, rdx
0x180022c69  jz      short loc_180022C9B
0x180022c6b  test    [rcx+1Ch], ebp
0x180022c6e  jz      short loc_180022C9B
0x180022c70  cmp     byte ptr [rcx+19h], 4
0x180022c74  jb      short loc_180022C9B
0x180022c76  mov     rcx, [rcx+10h]
0x180022c7a  lea     edx, [r15+6Bh]
0x180022c7e  mov     r9, r14
0x180022c81  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180022c88  call    WPP_SF_s
0x180022c8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c94  lea     rdx, WPP_GLOBAL_Control
0x180022c9b  cmp     [rsi], r15d
0x180022c9e  jz      short loc_180022CBB
0x180022ca0  mov     r12d, [rsi+8]
0x180022ca4  cmp     rcx, rdx
0x180022ca7  jz      short loc_180022CE7
0x180022ca9  test    [rcx+1Ch], ebp
0x180022cac  jz      short loc_180022CE7
0x180022cae  cmp     byte ptr [rcx+19h], 5
0x180022cb2  jb      short loc_180022CE7
0x180022cb4  mov     edx, 6Ch ; 'l'
0x180022cb9  jmp     short loc_180022CD4
0x180022cbb  mov     r12d, [r13+4]
0x180022cbf  cmp     rcx, rdx
0x180022cc2  jz      short loc_180022CE7
0x180022cc4  test    [rcx+1Ch], ebp
0x180022cc7  jz      short loc_180022CE7
0x180022cc9  cmp     byte ptr [rcx+19h], 5
0x180022ccd  jb      short loc_180022CE7
0x180022ccf  mov     edx, 6Dh ; 'm'
0x180022cd4  mov     rcx, [rcx+10h]
0x180022cd8  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180022cdf  mov     r9d, r12d
0x180022ce2  call    WPP_SF_d
0x180022ce7  call    cs:__imp_GetCurrentProcessId
0x180022cee  nop     dword ptr [rax+rax+00h]
0x180022cf3  cmp     cs:MaxPorts, ebx
0x180022cf9  mov     edx, 2
0x180022cfe  mov     r10, cs:WPP_GLOBAL_Control
0x180022d05  mov     [rsp+78h+var_44], eax
0x180022d09  jbe     loc_1800230C7
0x180022d0f  lea     ebp, [rdx-1]
0x180022d12  mov     rcx, cs:Pcb
0x180022d19  movzx   edx, r15w
0x180022d1d  mov     rbx, [rcx+rdx*8]
0x180022d21  test    rbx, rbx
0x180022d24  jz      loc_18002305E
0x180022d2a  mov     rdx, r14; String2
0x180022d2d  lea     rcx, [rbx+48h]; String1
0x180022d31  lea     rsi, [rbx+18h]
0x180022d35  call    cs:__imp__stricmp
0x180022d3c  nop     dword ptr [rax+rax+00h]
0x180022d41  mov     edx, 2
0x180022d46  test    eax, eax
0x180022d48  jnz     short loc_180022D7E
0x180022d4a  mov     eax, [rsi]
0x180022d4c  lea     r8d, [rdx-1]
0x180022d50  mov     ecx, [rsp+78h+arg_10]
0x180022d57  sub     eax, edx
0x180022d59  cmp     eax, r8d
0x180022d5c  mov     rax, [rbx+4D0h]
0x180022d63  cmova   ecx, r8d
0x180022d67  mov     [rsp+78h+arg_10], ecx
0x180022d6e  mov     ecx, [rsp+78h+ProcessInformation]
0x180022d75  cmp     ecx, [rax+4Ch]
0x180022d78  jnb     loc_18002307B
0x180022d7e  mov     eax, [rsi]
0x180022d80  sub     eax, edx
0x180022d82  cmp     eax, 1
0x180022d85  jbe     loc_180023052
0x180022d8b  mov     eax, [rsp+78h+arg_8]
0x180022d92  test    [rbx+24h], eax
0x180022d95  jz      loc_180023052
0x180022d9b  cmp     r12d, [rsp+78h+var_44]
0x180022da0  jz      short loc_180022DAB
0x180022da2  test    [rbx+24h], dl
0x180022da5  jz      loc_180023052
0x180022dab  test    byte ptr [rbx+4C8h], 8
0x180022db2  jnz     loc_180023052
0x180022db8  lea     r14, [rbx+2Ch]
0x180022dbc  cmp     [r14], dx
0x180022dc0  jnb     loc_180023052
0x180022dc6  lea     rdx, [r13+2Ch]; String2
0x180022dca  lea     rcx, [rbx+48h]; String1
0x180022dce  call    cs:__imp__stricmp
0x180022dd5  nop     dword ptr [rax+rax+00h]
0x180022dda  test    eax, eax
0x180022ddc  jnz     loc_180023052
0x180022de2  cmp     dword ptr [rsi], 1
0x180022de5  mov     ebp, [rsp+78h+arg_8]
0x180022dec  jz      short loc_180022DF7
0x180022dee  test    [rbx+28h], ebp
0x180022df1  jnz     loc_180023052
0x180022df7  mov     r10, cs:WPP_GLOBAL_Control
0x180022dfe  lea     rdx, WPP_GLOBAL_Control
0x180022e05  cmp     r10, rdx
0x180022e08  jz      short loc_180022E48
0x180022e0a  test    dword ptr [r10+1Ch], 2000h
0x180022e12  jz      short loc_180022E48
0x180022e14  cmp     byte ptr [r10+19h], 5
0x180022e19  jb      short loc_180022E48
0x180022e1b  mov     eax, [rbx+28h]
0x180022e1e  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180022e25  mov     r9, [rbx]
0x180022e28  mov     edx, 6Fh ; 'o'
0x180022e2d  mov     rcx, [r10+10h]
0x180022e31  mov     dword ptr [rsp+78h+ReturnLength], eax
0x180022e35  call    WPP_SF_qD
0x180022e3a  mov     r10, cs:WPP_GLOBAL_Control
0x180022e41  lea     rdx, WPP_GLOBAL_Control
0x180022e48  test    bpl, bpl
0x180022e4b  jns     short loc_180022E57
0x180022e4d  cmp     dword ptr [rbx+1Ch], 1
0x180022e51  jnz     loc_180023059
0x180022e57  mov     rax, [rbx+4D0h]
0x180022e5e  mov     ecx, [rsp+78h+ProcessInformation]
0x180022e65  cmp     ecx, [rax+4Ch]
0x180022e68  jnb     loc_180023162
0x180022e6e  mov     ebp, [rsp+78h+var_48]
0x180022e72  cmp     ecx, ebp
0x180022e74  jbe     short loc_180022E81
0x180022e76  inc     ebp
0x180022e78  mov     [rsp+78h+var_48], ebp
0x180022e7c  jmp     loc_180023059
0x180022e81  lea     rdi, WPP_GLOBAL_Control
0x180022e88  mov     ebp, 2000h
0x180022e8d  cmp     r10, rdi
0x180022e90  jz      short loc_180022EC5
0x180022e92  test    [r10+1Ch], ebp
0x180022e96  jz      short loc_180022EC5
0x180022e98  cmp     byte ptr [r10+19h], 5
0x180022e9d  jb      short loc_180022EC5
0x180022e9f  mov     eax, [rbx+1Ch]
0x180022ea2  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180022ea9  mov     r9d, [rsi]
0x180022eac  mov     edx, 71h ; 'q'
0x180022eb1  mov     rcx, [r10+10h]
0x180022eb5  mov     dword ptr [rsp+78h+ReturnLength], eax
0x180022eb9  call    WPP_SF_Dd
0x180022ebe  mov     r10, cs:WPP_GLOBAL_Control
0x180022ec5  cmp     dword ptr [rsi], 1
0x180022ec8  jnz     loc_18002300B
0x180022ece  cmp     r10, rdi
0x180022ed1  jz      short loc_180022EF5
0x180022ed3  test    [r10+1Ch], ebp
0x180022ed7  jz      short loc_180022EF5
0x180022ed9  cmp     byte ptr [r10+19h], 5
0x180022ede  jb      short loc_180022EF5
0x180022ee0  mov     rcx, [r10+10h]
0x180022ee4  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180022eeb  mov     edx, 72h ; 'r'
0x180022ef0  call    WPP_SF_
0x180022ef5  mov     rcx, [rbx+30h]; String1
0x180022ef9  lea     rdx, String2; "rastapi"
0x180022f00  call    cs:__imp__stricmp
0x180022f07  nop     dword ptr [rax+rax+00h]
0x180022f0c  mov     r9d, [rbx]
0x180022f0f  lea     rbp, [rbx+8]
0x180022f13  mov     r8, cs:hIoCompletionPort
0x180022f1a  lea     rdx, [rbx+0D8h]
0x180022f21  mov     rcx, rbp
0x180022f24  test    eax, eax
0x180022f26  jnz     short loc_180022F79
0x180022f28  mov     eax, [rsp+78h+arg_8]
0x180022f2f  mov     dword ptr [rsp+78h+ReturnLength], eax
0x180022f33  mov     rax, cs:RastapiPortOpen
0x180022f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f3f  mov     rdi, rax
0x180022f42  test    eax, eax
0x180022f44  jz      loc_1800231B8
0x180022f4a  mov     r10, cs:WPP_GLOBAL_Control
0x180022f51  lea     rsi, WPP_GLOBAL_Control
0x180022f58  cmp     r10, rsi
0x180022f5b  jz      loc_180023059
0x180022f61  test    dword ptr [r10+1Ch], 2000h
0x180022f69  jz      short loc_180022FD7
0x180022f6b  cmp     byte ptr [r10+19h], 2
0x180022f70  jb      short loc_180022FD7
0x180022f72  mov     edx, 73h ; 's'
0x180022f77  jmp     short loc_180022FBD
0x180022f79  mov     rax, [rbx+30h]
0x180022f7d  mov     rax, [rax+18h]
0x180022f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f86  mov     edi, eax
0x180022f88  test    eax, eax
0x180022f8a  jz      loc_1800231B8
0x180022f90  mov     r10, cs:WPP_GLOBAL_Control
0x180022f97  lea     rsi, WPP_GLOBAL_Control
0x180022f9e  cmp     r10, rsi
0x180022fa1  jz      loc_180023059
0x180022fa7  test    dword ptr [r10+1Ch], 2000h
0x180022faf  jz      short loc_180022FD7
0x180022fb1  cmp     byte ptr [r10+19h], 2
0x180022fb6  jb      short loc_180022FD7
0x180022fb8  mov     edx, 74h ; 't'
0x180022fbd  mov     rcx, [r10+10h]
0x180022fc1  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180022fc8  mov     r9d, eax
0x180022fcb  call    WPP_SF_d
0x180022fd0  mov     r10, cs:WPP_GLOBAL_Control
0x180022fd7  cmp     r10, rsi
0x180022fda  jz      short loc_180023059
0x180022fdc  test    dword ptr [r10+1Ch], 2000h
0x180022fe4  jz      short loc_180023059
0x180022fe6  cmp     byte ptr [r10+19h], 2
0x180022feb  jb      short loc_180023059
0x180022fed  mov     rcx, [r10+10h]
0x180022ff1  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180022ff8  mov     edx, 75h ; 'u'
0x180022ffd  mov     dword ptr [rsp+78h+ReturnLength], edi
0x180023001  mov     r9, rbp
0x180023004  call    WPP_SF_sd
0x180023009  jmp     short loc_180023052
0x18002300b  cmp     dword ptr [rbx+1Ch], 1
0x18002300f  jz      loc_180023131
0x180023015  cmp     dword ptr [rbx+1Ch], 4
0x180023019  jz      loc_180023118
0x18002301f  mov     edi, 25Ah
0x180023024  lea     rsi, WPP_GLOBAL_Control
0x18002302b  cmp     r10, rsi
0x18002302e  jz      short loc_180023059
0x180023030  test    [r10+1Ch], ebp
0x180023034  jz      short loc_180023059
0x180023036  cmp     byte ptr [r10+19h], 5
0x18002303b  jb      short loc_180023059
0x18002303d  mov     rcx, [r10+10h]
0x180023041  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180023048  mov     edx, 77h ; 'w'
0x18002304d  call    WPP_SF_
0x180023052  mov     r10, cs:WPP_GLOBAL_Control
0x180023059  mov     ebp, 1
0x18002305e  add     r15w, bp
0x180023062  movzx   eax, r15w
0x180023066  cmp     eax, cs:MaxPorts
0x18002306c  jnb     loc_180023197
0x180023072  lea     r14, [r13+2Ch]
0x180023076  jmp     loc_180022D12
0x18002307b  mov     edi, 103h
0x180023080  mov     r10, cs:WPP_GLOBAL_Control
0x180023087  lea     rax, WPP_GLOBAL_Control
0x18002308e  cmp     r10, rax
0x180023091  jz      short loc_1800230C7
0x180023093  test    dword ptr [r10+1Ch], 2000h
0x18002309b  jz      short loc_1800230C7
0x18002309d  cmp     [r10+19h], dl
0x1800230a1  jb      short loc_1800230C7
0x1800230a3  mov     edx, 6Eh ; 'n'
0x1800230a8  mov     rcx, [r10+10h]
0x1800230ac  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800230b3  mov     r9d, edi
0x1800230b6  call    WPP_SF_d
0x1800230bb  mov     r10, cs:WPP_GLOBAL_Control
0x1800230c2  mov     edx, 2
0x1800230c7  xor     r14d, r14d
0x1800230ca  movzx   eax, r15w
0x1800230ce  cmp     eax, cs:MaxPorts
0x1800230d4  jnz     loc_18002358D
0x1800230da  mov     edi, 103h
0x1800230df  lea     rsi, WPP_GLOBAL_Control
0x1800230e6  cmp     r10, rsi
0x1800230e9  jz      loc_180023594
0x1800230ef  test    dword ptr [r10+1Ch], 2000h
  ... truncated ...
```
