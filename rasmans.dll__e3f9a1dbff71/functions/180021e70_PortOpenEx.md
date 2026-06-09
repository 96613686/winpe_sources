# PortOpenEx

- ea: `0x180021e70`
- end: `0x1800228c7`
- name: `PortOpenEx`
- size: `2647`
- prototype: `int __fastcall(__int64, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180035a90`

## callees

- `0x180005c6c`
- `0x180005d18`
- `0x180005e0c`
- `0x180005e34`
- `0x180005e74`
- `0x18000bfb0`
- `0x18000c00c`
- `0x180021e70`
- `0x180031fec`
- `0x180032118`
- `0x18003426c`
- `0x180037dc4`
- `0x180044d00`
- `0x180047714`
- `0x1800486b4`
- `0x1800a49ec`
- `0x1800a4d0c`
- `0x1800a56d8`
- `0x1800e9010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180021fcf`
- `msvcrt!_stricmp` at `0x180022062`
- `msvcrt!_stricmp` at `0x18002218e`
- `msvcrt!_stricmp` at `0x180021fcf`
- `msvcrt!_stricmp` at `0x180022062`
- `msvcrt!_stricmp` at `0x18002218e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021f87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022587`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021f87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022587`
- `ntdll!NtQueryInformationProcess` at `0x1800225c5`
- `ntdll!NtQueryInformationProcess` at `0x1800225c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800225df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800225df`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800225a0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800225a0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180022773`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180022773`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800227b0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800227b0`

## string_xrefs

- `0x18002286b`: `PortOpenEx: Failed`
- `0x180022766`: `wevtapi.dll`
- `0x180022784`: `Windows Networking Vpn Plugin Platform/Operational`
- `0x180022799`: `Windows Networking Vpn Plugin Platform/OperationalVerbose`

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
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 106, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
    WPP_SF_s(v5[1].Flink, 107, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, a3 + 44);
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
      WPP_SF_d(v5[1].Flink, v12, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v11);
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
        LODWORD(Library) = WPP_SF_d(Flink, v28, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v29);
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
          WPP_SF_d(v15[1].Flink, v25, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, 259);
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
        WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
        WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
        WPP_SF_(v15[1].Flink, 114, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
      WPP_SF_d(v15[1].Flink, v24, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v23);
      v15 = WPP_GLOBAL_Control;
LABEL_64:
      if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v15[1].Blink) & 0x2000) != 0
        && BYTE1(v15[1].Blink) >= 2u )
      {
        WPP_SF_sd(v15[1].Flink, 117, (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, (_DWORD)v9 + 8, v10);
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
        WPP_SF_(v15[1].Flink, 118, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
      WPP_SF_(v15[1].Flink, 119, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
      WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
      WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 123, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v38);
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
                                     WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
    LODWORD(Library) = WPP_SF_d(v43[1].Flink, 127, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v10);
  }
  return (int)Library;
}

```

## disassembly

```asm
0x180021e70  mov     [rsp+arg_0], rbx
0x180021e75  push    rbp
0x180021e76  push    rsi
0x180021e77  push    rdi
0x180021e78  push    r12
0x180021e7a  push    r13
0x180021e7c  push    r14
0x180021e7e  push    r15
0x180021e80  sub     rsp, 40h
0x180021e84  mov     r13, r8
0x180021e87  mov     rsi, rdx
0x180021e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e91  lea     rdx, WPP_GLOBAL_Control
0x180021e98  cmp     rcx, rdx
0x180021e9b  jz      short loc_180021ECF
0x180021e9d  test    dword ptr [rcx+1Ch], 2000h
0x180021ea4  jz      short loc_180021ECF
0x180021ea6  cmp     byte ptr [rcx+19h], 6
0x180021eaa  jb      short loc_180021ECF
0x180021eac  mov     rcx, [rcx+10h]
0x180021eb0  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180021eb7  mov     edx, 6Ah ; 'j'
0x180021ebc  call    WPP_SF_
0x180021ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ec8  lea     rdx, WPP_GLOBAL_Control
0x180021ecf  mov     eax, [r13+28h]
0x180021ed3  lea     r14, [r13+2Ch]
0x180021ed7  mov     ebp, [r13+8]
0x180021edb  xor     r15d, r15d
0x180021ede  mov     [rsp+78h+arg_10], r15d
0x180021ee6  mov     ebx, r15d
0x180021ee9  mov     [rsp+78h+var_48], r15d
0x180021eee  mov     edi, 279h
0x180021ef3  mov     [rsp+78h+ProcessInformation], eax
0x180021efa  mov     [rsp+78h+arg_8], ebp
0x180021f01  mov     ebp, 2000h
0x180021f06  cmp     rcx, rdx
0x180021f09  jz      short loc_180021F3B
0x180021f0b  test    [rcx+1Ch], ebp
0x180021f0e  jz      short loc_180021F3B
0x180021f10  cmp     byte ptr [rcx+19h], 4
0x180021f14  jb      short loc_180021F3B
0x180021f16  mov     rcx, [rcx+10h]
0x180021f1a  lea     edx, [r15+6Bh]
0x180021f1e  mov     r9, r14
0x180021f21  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180021f28  call    WPP_SF_s
0x180021f2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f34  lea     rdx, WPP_GLOBAL_Control
0x180021f3b  cmp     [rsi], r15d
0x180021f3e  jz      short loc_180021F5B
0x180021f40  mov     r12d, [rsi+8]
0x180021f44  cmp     rcx, rdx
0x180021f47  jz      short loc_180021F87
0x180021f49  test    [rcx+1Ch], ebp
0x180021f4c  jz      short loc_180021F87
0x180021f4e  cmp     byte ptr [rcx+19h], 5
0x180021f52  jb      short loc_180021F87
0x180021f54  mov     edx, 6Ch ; 'l'
0x180021f59  jmp     short loc_180021F74
0x180021f5b  mov     r12d, [r13+4]
0x180021f5f  cmp     rcx, rdx
0x180021f62  jz      short loc_180021F87
0x180021f64  test    [rcx+1Ch], ebp
0x180021f67  jz      short loc_180021F87
0x180021f69  cmp     byte ptr [rcx+19h], 5
0x180021f6d  jb      short loc_180021F87
0x180021f6f  mov     edx, 6Dh ; 'm'
0x180021f74  mov     rcx, [rcx+10h]
0x180021f78  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180021f7f  mov     r9d, r12d
0x180021f82  call    WPP_SF_d
0x180021f87  call    cs:__imp_GetCurrentProcessId
0x180021f8d  cmp     cs:MaxPorts, ebx
0x180021f93  mov     edx, 2
0x180021f98  mov     r10, cs:WPP_GLOBAL_Control
0x180021f9f  mov     [rsp+78h+var_44], eax
0x180021fa3  jbe     loc_18002234F
0x180021fa9  lea     ebp, [rdx-1]
0x180021fac  mov     rcx, cs:Pcb
0x180021fb3  movzx   edx, r15w
0x180021fb7  mov     rbx, [rcx+rdx*8]
0x180021fbb  test    rbx, rbx
0x180021fbe  jz      loc_1800222E6
0x180021fc4  mov     rdx, r14; String2
0x180021fc7  lea     rcx, [rbx+48h]; String1
0x180021fcb  lea     rsi, [rbx+18h]
0x180021fcf  call    cs:__imp__stricmp
0x180021fd5  mov     edx, 2
0x180021fda  test    eax, eax
0x180021fdc  jnz     short loc_180022012
0x180021fde  mov     eax, [rsi]
0x180021fe0  lea     r8d, [rdx-1]
0x180021fe4  mov     ecx, [rsp+78h+arg_10]
0x180021feb  sub     eax, edx
0x180021fed  cmp     eax, r8d
0x180021ff0  mov     rax, [rbx+4D0h]
0x180021ff7  cmova   ecx, r8d
0x180021ffb  mov     [rsp+78h+arg_10], ecx
0x180022002  mov     ecx, [rsp+78h+ProcessInformation]
0x180022009  cmp     ecx, [rax+4Ch]
0x18002200c  jnb     loc_180022303
0x180022012  mov     eax, [rsi]
0x180022014  sub     eax, edx
0x180022016  cmp     eax, 1
0x180022019  jbe     loc_1800222DA
0x18002201f  mov     eax, [rsp+78h+arg_8]
0x180022026  test    [rbx+24h], eax
0x180022029  jz      loc_1800222DA
0x18002202f  cmp     r12d, [rsp+78h+var_44]
0x180022034  jz      short loc_18002203F
0x180022036  test    [rbx+24h], dl
0x180022039  jz      loc_1800222DA
0x18002203f  test    byte ptr [rbx+4C8h], 8
0x180022046  jnz     loc_1800222DA
0x18002204c  lea     r14, [rbx+2Ch]
0x180022050  cmp     [r14], dx
0x180022054  jnb     loc_1800222DA
0x18002205a  lea     rdx, [r13+2Ch]; String2
0x18002205e  lea     rcx, [rbx+48h]; String1
0x180022062  call    cs:__imp__stricmp
0x180022068  test    eax, eax
0x18002206a  jnz     loc_1800222DA
0x180022070  cmp     dword ptr [rsi], 1
0x180022073  mov     ebp, [rsp+78h+arg_8]
0x18002207a  jz      short loc_180022085
0x18002207c  test    [rbx+28h], ebp
0x18002207f  jnz     loc_1800222DA
0x180022085  mov     r10, cs:WPP_GLOBAL_Control
0x18002208c  lea     rdx, WPP_GLOBAL_Control
0x180022093  cmp     r10, rdx
0x180022096  jz      short loc_1800220D6
0x180022098  test    dword ptr [r10+1Ch], 2000h
0x1800220a0  jz      short loc_1800220D6
0x1800220a2  cmp     byte ptr [r10+19h], 5
0x1800220a7  jb      short loc_1800220D6
0x1800220a9  mov     eax, [rbx+28h]
0x1800220ac  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800220b3  mov     r9, [rbx]
0x1800220b6  mov     edx, 6Fh ; 'o'
0x1800220bb  mov     rcx, [r10+10h]
0x1800220bf  mov     dword ptr [rsp+78h+ReturnLength], eax
0x1800220c3  call    WPP_SF_qD
0x1800220c8  mov     r10, cs:WPP_GLOBAL_Control
0x1800220cf  lea     rdx, WPP_GLOBAL_Control
0x1800220d6  test    bpl, bpl
0x1800220d9  jns     short loc_1800220E5
0x1800220db  cmp     dword ptr [rbx+1Ch], 1
0x1800220df  jnz     loc_1800222E1
0x1800220e5  mov     rax, [rbx+4D0h]
0x1800220ec  mov     ecx, [rsp+78h+ProcessInformation]
0x1800220f3  cmp     ecx, [rax+4Ch]
0x1800220f6  jnb     loc_1800223EA
0x1800220fc  mov     ebp, [rsp+78h+var_48]
0x180022100  cmp     ecx, ebp
0x180022102  jbe     short loc_18002210F
0x180022104  inc     ebp
0x180022106  mov     [rsp+78h+var_48], ebp
0x18002210a  jmp     loc_1800222E1
0x18002210f  lea     rdi, WPP_GLOBAL_Control
0x180022116  mov     ebp, 2000h
0x18002211b  cmp     r10, rdi
0x18002211e  jz      short loc_180022153
0x180022120  test    [r10+1Ch], ebp
0x180022124  jz      short loc_180022153
0x180022126  cmp     byte ptr [r10+19h], 5
0x18002212b  jb      short loc_180022153
0x18002212d  mov     eax, [rbx+1Ch]
0x180022130  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180022137  mov     r9d, [rsi]
0x18002213a  mov     edx, 71h ; 'q'
0x18002213f  mov     rcx, [r10+10h]
0x180022143  mov     dword ptr [rsp+78h+ReturnLength], eax
0x180022147  call    WPP_SF_Dd
0x18002214c  mov     r10, cs:WPP_GLOBAL_Control
0x180022153  cmp     dword ptr [rsi], 1
0x180022156  jnz     loc_180022293
0x18002215c  cmp     r10, rdi
0x18002215f  jz      short loc_180022183
0x180022161  test    [r10+1Ch], ebp
0x180022165  jz      short loc_180022183
0x180022167  cmp     byte ptr [r10+19h], 5
0x18002216c  jb      short loc_180022183
0x18002216e  mov     rcx, [r10+10h]
0x180022172  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180022179  mov     edx, 72h ; 'r'
0x18002217e  call    WPP_SF_
0x180022183  mov     rcx, [rbx+30h]; String1
0x180022187  lea     rdx, String2; "rastapi"
0x18002218e  call    cs:__imp__stricmp
0x180022194  mov     r9d, [rbx]
0x180022197  lea     rbp, [rbx+8]
0x18002219b  mov     r8, cs:hIoCompletionPort
0x1800221a2  lea     rdx, [rbx+0D8h]
0x1800221a9  mov     rcx, rbp
0x1800221ac  test    eax, eax
0x1800221ae  jnz     short loc_180022201
0x1800221b0  mov     eax, [rsp+78h+arg_8]
0x1800221b7  mov     dword ptr [rsp+78h+ReturnLength], eax
0x1800221bb  mov     rax, cs:RastapiPortOpen
0x1800221c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221c7  mov     rdi, rax
0x1800221ca  test    eax, eax
0x1800221cc  jz      loc_180022440
0x1800221d2  mov     r10, cs:WPP_GLOBAL_Control
0x1800221d9  lea     rsi, WPP_GLOBAL_Control
0x1800221e0  cmp     r10, rsi
0x1800221e3  jz      loc_1800222E1
0x1800221e9  test    dword ptr [r10+1Ch], 2000h
0x1800221f1  jz      short loc_18002225F
0x1800221f3  cmp     byte ptr [r10+19h], 2
0x1800221f8  jb      short loc_18002225F
0x1800221fa  mov     edx, 73h ; 's'
0x1800221ff  jmp     short loc_180022245
0x180022201  mov     rax, [rbx+30h]
0x180022205  mov     rax, [rax+18h]
0x180022209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002220e  mov     edi, eax
0x180022210  test    eax, eax
0x180022212  jz      loc_180022440
0x180022218  mov     r10, cs:WPP_GLOBAL_Control
0x18002221f  lea     rsi, WPP_GLOBAL_Control
0x180022226  cmp     r10, rsi
0x180022229  jz      loc_1800222E1
0x18002222f  test    dword ptr [r10+1Ch], 2000h
0x180022237  jz      short loc_18002225F
0x180022239  cmp     byte ptr [r10+19h], 2
0x18002223e  jb      short loc_18002225F
0x180022240  mov     edx, 74h ; 't'
0x180022245  mov     rcx, [r10+10h]
0x180022249  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180022250  mov     r9d, eax
0x180022253  call    WPP_SF_d
0x180022258  mov     r10, cs:WPP_GLOBAL_Control
0x18002225f  cmp     r10, rsi
0x180022262  jz      short loc_1800222E1
0x180022264  test    dword ptr [r10+1Ch], 2000h
0x18002226c  jz      short loc_1800222E1
0x18002226e  cmp     byte ptr [r10+19h], 2
0x180022273  jb      short loc_1800222E1
0x180022275  mov     rcx, [r10+10h]
0x180022279  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180022280  mov     edx, 75h ; 'u'
0x180022285  mov     dword ptr [rsp+78h+ReturnLength], edi
0x180022289  mov     r9, rbp
0x18002228c  call    WPP_SF_sd
0x180022291  jmp     short loc_1800222DA
0x180022293  cmp     dword ptr [rbx+1Ch], 1
0x180022297  jz      loc_1800223B9
0x18002229d  cmp     dword ptr [rbx+1Ch], 4
0x1800222a1  jz      loc_1800223A0
0x1800222a7  mov     edi, 25Ah
0x1800222ac  lea     rsi, WPP_GLOBAL_Control
0x1800222b3  cmp     r10, rsi
0x1800222b6  jz      short loc_1800222E1
0x1800222b8  test    [r10+1Ch], ebp
0x1800222bc  jz      short loc_1800222E1
0x1800222be  cmp     byte ptr [r10+19h], 5
0x1800222c3  jb      short loc_1800222E1
0x1800222c5  mov     rcx, [r10+10h]
0x1800222c9  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800222d0  mov     edx, 77h ; 'w'
0x1800222d5  call    WPP_SF_
0x1800222da  mov     r10, cs:WPP_GLOBAL_Control
0x1800222e1  mov     ebp, 1
0x1800222e6  add     r15w, bp
0x1800222ea  movzx   eax, r15w
0x1800222ee  cmp     eax, cs:MaxPorts
0x1800222f4  jnb     loc_18002241F
0x1800222fa  lea     r14, [r13+2Ch]
0x1800222fe  jmp     loc_180021FAC
0x180022303  mov     edi, 103h
0x180022308  mov     r10, cs:WPP_GLOBAL_Control
0x18002230f  lea     rax, WPP_GLOBAL_Control
0x180022316  cmp     r10, rax
0x180022319  jz      short loc_18002234F
0x18002231b  test    dword ptr [r10+1Ch], 2000h
0x180022323  jz      short loc_18002234F
0x180022325  cmp     [r10+19h], dl
0x180022329  jb      short loc_18002234F
0x18002232b  mov     edx, 6Eh ; 'n'
0x180022330  mov     rcx, [r10+10h]
0x180022334  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002233b  mov     r9d, edi
0x18002233e  call    WPP_SF_d
0x180022343  mov     r10, cs:WPP_GLOBAL_Control
0x18002234a  mov     edx, 2
0x18002234f  xor     r14d, r14d
0x180022352  movzx   eax, r15w
0x180022356  cmp     eax, cs:MaxPorts
0x18002235c  jnz     loc_1800227F1
0x180022362  mov     edi, 103h
0x180022367  lea     rsi, WPP_GLOBAL_Control
0x18002236e  cmp     r10, rsi
0x180022371  jz      loc_1800227F8
0x180022377  test    dword ptr [r10+1Ch], 2000h
0x18002237f  jz      loc_1800227F8
0x180022385  cmp     [r10+19h], dl
0x180022389  jb      loc_1800227F8
0x18002238f  mov     rcx, [r10+10h]
  ... truncated ...
```
