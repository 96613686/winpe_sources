# TSCMain(HINSTANCE__ *,HINSTANCE__ *,HACCEL__ *,ushort const *)

- ea: `0x140062680`
- end: `0x140062ed9`
- name: `?TSCMain@@YAHPEAUHINSTANCE__@@0PEAUHACCEL__@@PEBG@Z`
- size: `2137`
- prototype: `__int64 __fastcall(HINSTANCE, HINSTANCE, HACCEL, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14006379c`

## callees

- `0x1400010a0`
- `0x140001158`
- `0x140003b2c`
- `0x14000b134`
- `0x14000b7d8`
- `0x14000c570`
- `0x14000c69c`
- `0x14000c7d0`
- `0x14000c7f8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x14000d3a0`
- `0x14002d8a4`
- `0x1400357a0`
- `0x1400360ec`
- `0x140040814`
- `0x1400411a0`
- `0x140041360`
- `0x1400414c0`
- `0x140041e24`
- `0x140042088`
- `0x140054098`
- `0x140054d7c`
- `0x14005db2c`
- `0x1400615dc`
- `0x140061f20`
- `0x140062144`
- `0x140062680`
- `0x140112010`

## import_xrefs

- `USER32!IsDialogMessageW` at `0x140062ca6`
- `USER32!IsDialogMessageW` at `0x140062ca6`
- `USER32!TranslateAcceleratorW` at `0x140062c94`
- `USER32!TranslateAcceleratorW` at `0x140062c94`
- `USER32!DispatchMessageW` at `0x140062cc0`
- `USER32!DispatchMessageW` at `0x140062cc0`
- `USER32!TranslateMessage` at `0x140062cb5`
- `USER32!TranslateMessage` at `0x140062cb5`
- `USER32!GetMessageW` at `0x140062c76`
- `USER32!GetMessageW` at `0x140062c76`
- `KERNEL32!Sleep` at `0x140062df8`
- `KERNEL32!Sleep` at `0x140062df8`
- `KERNEL32!DeleteFileW` at `0x140062b6c`
- `KERNEL32!DeleteFileW` at `0x140062e17`
- `KERNEL32!DeleteFileW` at `0x140062b6c`
- `KERNEL32!DeleteFileW` at `0x140062e17`
- `KERNEL32!GetLastError` at `0x140062cc8`
- `KERNEL32!GetLastError` at `0x140062cc8`
- `ole32!CoRevokeClassObject` at `0x140062dca`
- `ole32!CoRevokeClassObject` at `0x140062dca`

## string_xrefs

- `0x140062dbe`: `CommandLineData`
- `0x1400629cf`: `CreateInstance failed. Exiting!`

## pseudocode

```c
__int64 __fastcall TSCMain(HINSTANCE a1, HINSTANCE a2, HACCEL a3, const unsigned __int16 *a4)
{
  CTscSettings *v4; // rsi
  unsigned int v6; // r13d
  CommandLineData *v7; // rdi
  PVOID *v10; // rcx
  int v11; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v13; // eax
  CTSClientModule *v14; // rcx
  signed int AllSettings; // ebx
  unsigned int v16; // eax
  int v17; // edx
  const char *v18; // rcx
  __int64 *v19; // rcx
  HRESULT v20; // eax
  GUID ***i; // rsi
  GUID **v22; // rdx
  CommandLineData *v23; // rax
  CommandLineData *v24; // rax
  bool v25; // r8
  unsigned int v26; // esi
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  unsigned int v34; // eax
  CTscSettings *v35; // rax
  unsigned int v36; // eax
  int v37; // edx
  const char *v38; // rcx
  int v39; // eax
  unsigned int v40; // eax
  int started; // eax
  HWND TscDialogHandle; // rsi
  int MessageW; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  int v46; // edx
  const char *v47; // rcx
  unsigned int v48; // eax
  unsigned int v50; // [rsp+30h] [rbp-D0h] BYREF
  CTscRemoteSession *v51; // [rsp+38h] [rbp-C8h] BYREF
  CTscSettings *v52; // [rsp+40h] [rbp-C0h] BYREF
  struct tagMSG Msg; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v54[12]; // [rsp+80h] [rbp-80h] BYREF
  HINSTANCE v55; // [rsp+158h] [rbp+58h] BYREF

  v55 = a2;
  v4 = 0;
  v51 = 0;
  v52 = 0;
  memset(&Msg, 0, sizeof(Msg));
  v6 = 0;
  v7 = 0;
  v11 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1401500E0);
  if ( v11 < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_b43a4c2333b03a5b3f0d65e5fddc42d4_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"TraceLoggingRegister Failed",
          v11);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 && *((_BYTE *)v10 + 25) >= 2u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          (unsigned int)WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
          v13,
          (__int64)"MSTSCTelemetryTraceLogging_Registe failed",
          v11);
      }
    }
  }
  AllSettings = CTSClientModule::PreMessageLoop((CTSClientModule *)v10);
  if ( AllSettings < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 25;
      v18 = "_AtlModule.PreMessageLoop failed!";
LABEL_15:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        (unsigned int)WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
        v16,
        (__int64)v18,
        AllSettings);
      goto LABEL_20;
    }
    goto LABEL_20;
  }
  if ( AllSettings == 262656 )
    goto LABEL_20;
  if ( dword_1401519AC )
  {
    if ( dword_1401519A8 )
      CTSClientModule::RunMessageLoopSingleUse(v14, a3);
    else
      CTSClientModule::RunMessageLoopMultiUse(v14, a3);
    goto LABEL_20;
  }
  v23 = (CommandLineData *)operator new(0x19F0u);
  if ( !v23 || (v24 = CommandLineData::CommandLineData(v23), (v7 = v24) == 0) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_99;
    }
    v45 = RdpWppGetCurrentThreadActivityIdPrefix();
    v46 = 26;
    v47 = "CommandLineData";
    goto LABEL_98;
  }
  v26 = CommandLineData::ProcessCommand(v24, a4, v25, 0);
  if ( a4 && *a4 )
  {
    v27 = *((_OWORD *)v7 + 408);
    v54[0] = *((_OWORD *)v7 + 407);
    v28 = *((_OWORD *)v7 + 409);
    v54[1] = v27;
    v29 = *((_OWORD *)v7 + 410);
    v54[2] = v28;
    v30 = *((_OWORD *)v7 + 411);
    v54[3] = v29;
    v31 = *((_OWORD *)v7 + 412);
    v54[4] = v30;
    v32 = *((_OWORD *)v7 + 413);
    v54[5] = v31;
    v33 = *((_OWORD *)v7 + 414);
    v54[6] = v32;
    v54[7] = v33;
    MSTSCTelemetry::SendCmdLineLaunchEvent(v54, v26);
  }
  if ( v26 != 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v34 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids, v34, v26);
    }
    v6 = 1;
    v4 = 0;
    goto LABEL_20;
  }
  v4 = 0;
  if ( *((_DWORD *)v7 + 1194) )
  {
    AllSettings = RunShadow(v7, a1);
    goto LABEL_20;
  }
  AllSettings = CTscRemoteSession::CreateInstance(a1, &v51);
  if ( AllSettings >= 0 )
  {
    v35 = (CTscSettings *)operator new(0x35090u);
    if ( v35 )
    {
      v4 = CTscSettings::CTscSettings(v35);
      if ( v4 )
      {
        TCntPtr<CTSCoreEventSink>::SafeRelease(&v52);
        v52 = v4;
        TCntPtr<CTscSettings>::SafeAddRef(&v52);
        AllSettings = CTscSettings::Initialize(v4, v7);
        if ( AllSettings < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_53;
          }
          v36 = RdpWppGetCurrentThreadActivityIdPrefix();
          v37 = 30;
          v38 = "Failed to initialize the settings object!";
LABEL_52:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v37,
            (unsigned int)WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
            v36,
            (__int64)v38,
            AllSettings);
LABEL_53:
          v4 = 0;
          goto LABEL_20;
        }
        v39 = CTscRemoteSession::TryBindToSingletonRailProcess(
                (CommandLineData *)((char *)v7 + 2092),
                v4,
                *((_DWORD *)v7 + 784) == 0,
                a4,
                (const unsigned __int16 *)v7 + 1046,
                (const unsigned __int16 *)v7 + 1306);
        AllSettings = v39;
        if ( v39 != 262656 )
        {
          if ( v39 < 0 )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_53;
            }
            v36 = RdpWppGetCurrentThreadActivityIdPrefix();
            v37 = 31;
            v38 = "TryBindToSingletonRailProcess failed";
            goto LABEL_52;
          }
          AllSettings = CTscSettings::LoadAllSettings(v4, v7);
          if ( AllSettings < 0 )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_53;
            }
            v36 = RdpWppGetCurrentThreadActivityIdPrefix();
            v37 = 32;
            v38 = "LoadAllSettings Failed";
            goto LABEL_52;
          }
          InitializeTestObjects((CTscSettings *)((char *)v4 + 217208));
          if ( *((_WORD *)v7 + 2098) )
          {
            DeleteFileW((LPCWSTR)v7 + 2098);
            CommandLineData::`scalar deleting destructor'(v7, 1u);
            v7 = 0;
          }
          v50 = 0;
          LODWORD(v55) = 0;
          AllSettings = CTscSettings::ValidateSettings(v4, &v50, (unsigned int *)&v55);
          if ( AllSettings < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v40 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                33,
                WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
                v40,
                AllSettings);
            }
            ShowErrorMessage(a1, v50, (unsigned int)v55);
            goto LABEL_53;
          }
          started = CTscRemoteSession::StartShell(v51, 0, v4);
          v4 = 0;
          AllSettings = started;
          if ( started < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v16 = RdpWppGetCurrentThreadActivityIdPrefix();
              v17 = 34;
              v18 = "StartShell returned FALSE. Exiting!";
              goto LABEL_15;
            }
            goto LABEL_20;
          }
          TscDialogHandle = CTscRemoteSession::GetTscDialogHandle(v51);
          if ( !AllSettings )
          {
            while ( 1 )
            {
              MessageW = GetMessageW(&Msg, 0, 0, 0);
              if ( !MessageW )
                break;
              if ( MessageW == -1 )
              {
                AllSettings = GetLastError();
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v44 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    35,
                    WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
                    v44,
                    AllSettings);
                }
                v4 = 0;
                if ( AllSettings > 0 )
                  AllSettings = (unsigned __int16)AllSettings | 0x80070000;
                if ( AllSettings >= 0 )
                  AllSettings = -2147467259;
                goto LABEL_20;
              }
              if ( !TranslateAcceleratorW(TscDialogHandle, a3, &Msg) && !IsDialogMessageW(TscDialogHandle, &Msg) )
              {
                TranslateMessage(&Msg);
                DispatchMessageW(&Msg);
              }
            }
          }
        }
        v4 = 0;
        goto LABEL_20;
      }
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_99:
      AllSettings = -2147024882;
      goto LABEL_20;
    }
    v45 = RdpWppGetCurrentThreadActivityIdPrefix();
    v46 = 29;
    v47 = "CTscSettings";
LABEL_98:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v46,
      (unsigned int)WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
      v45,
      (__int64)v47);
    goto LABEL_99;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 28;
    v18 = "CreateInstance failed. Exiting!";
    goto LABEL_15;
  }
LABEL_20:
  if ( dword_1401519AC != (_DWORD)v4 )
  {
    v19 = off_1401501E8;
    v20 = (int)v4;
    for ( i = off_1401501E0; i < (GUID ***)v19; ++i )
    {
      if ( v20 )
        break;
      v22 = *i;
      if ( *i )
      {
        if ( *((_DWORD *)v22 + 10) )
        {
          v20 = CoRevokeClassObject(*((_DWORD *)v22 + 10));
          v19 = off_1401501E8;
        }
        else
        {
          v20 = 0;
        }
      }
    }
    v4 = 0;
    if ( byte_140151990 )
      Sleep(dwMilliseconds);
  }
  if ( v7 )
  {
    if ( AllSettings != 262656 && *((_WORD *)v7 + 2098) != (_WORD)v4 )
      DeleteFileW((LPCWSTR)v7 + 2098);
    CommandLineData::`scalar deleting destructor'(v7, 1u);
  }
  if ( v51 )
  {
    AllSettings = CTscRemoteSession::EndShell(v51);
    if ( AllSettings < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v48 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids, v48);
    }
  }
  if ( g_pClx )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)g_pClx + 4) + 16LL))(*((_QWORD *)g_pClx + 4));
    g_pClx = v4;
  }
  if ( AllSettings < 0 )
    v6 = 1;
  TraceLoggingUnregister_EventUnregister(&dword_1401500E0);
  TCntPtr<CTSCoreEventSink>::SafeRelease(&v52);
  TCntPtr<CTSCoreEventSink>::SafeRelease(&v51);
  return v6;
}

```

## disassembly

```asm
0x140062680  mov     [rsp-8+arg_8], rdx
0x140062685  push    rbp
0x140062686  push    rbx
0x140062687  push    rsi
0x140062688  push    rdi
0x140062689  push    r12
0x14006268b  push    r13
0x14006268d  push    r14
0x14006268f  push    r15
0x140062691  lea     rbp, [rsp-8]
0x140062696  sub     rsp, 108h
0x14006269d  xorps   xmm0, xmm0
0x1400626a0  xor     esi, esi
0x1400626a2  mov     r15, rcx
0x1400626a5  mov     [rsp+140h+var_108], rsi
0x1400626aa  lea     rcx, dword_1401500E0; CallbackContext
0x1400626b1  mov     [rsp+140h+var_100], rsi
0x1400626b6  movups  xmmword ptr [rsp+140h+Msg.hwnd], xmm0
0x1400626bb  mov     r13d, esi
0x1400626be  mov     edi, esi
0x1400626c0  movups  xmmword ptr [rsp+140h+Msg.wParam], xmm0
0x1400626c5  mov     r14, r9
0x1400626c8  mov     r12, r8
0x1400626cb  movups  xmmword ptr [rsp+140h+Msg.time], xmm0
0x1400626d0  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1400626d5  mov     ebx, eax
0x1400626d7  lea     rax, WPP_GLOBAL_Control
0x1400626de  test    ebx, ebx
0x1400626e0  jns     loc_140062787
0x1400626e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400626ed  cmp     rcx, rax
0x1400626f0  jz      loc_140062787
0x1400626f6  test    byte ptr [rcx+1Ch], 8
0x1400626fa  jz      short loc_140062742
0x1400626fc  cmp     byte ptr [rcx+19h], 2
0x140062700  jb      short loc_140062742
0x140062702  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062707  lea     rcx, aTraceloggingre; "TraceLoggingRegister Failed"
0x14006270e  mov     dword ptr [rsp+140h+var_118], ebx
0x140062712  mov     [rsp+140h+var_120], rcx
0x140062717  lea     edx, [rsi+0Ah]
0x14006271a  mov     rcx, cs:WPP_GLOBAL_Control
0x140062721  lea     r8, WPP_b43a4c2333b03a5b3f0d65e5fddc42d4_Traceguids
0x140062728  mov     r9d, eax
0x14006272b  mov     rcx, [rcx+10h]
0x14006272f  call    WPP_SF_DsD
0x140062734  mov     rcx, cs:WPP_GLOBAL_Control
0x14006273b  lea     rax, WPP_GLOBAL_Control
0x140062742  cmp     rcx, rax
0x140062745  jz      short loc_140062787
0x140062747  test    byte ptr [rcx+1Ch], 8
0x14006274b  jz      short loc_140062787
0x14006274d  cmp     byte ptr [rcx+19h], 2
0x140062751  jb      short loc_140062787
0x140062753  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062758  lea     rcx, aMstsctelemetry; "MSTSCTelemetryTraceLogging_Registe fail"...
0x14006275f  mov     dword ptr [rsp+140h+var_118], ebx
0x140062763  mov     [rsp+140h+var_120], rcx
0x140062768  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x14006276f  mov     rcx, cs:WPP_GLOBAL_Control
0x140062776  mov     edx, 18h
0x14006277b  mov     r9d, eax
0x14006277e  mov     rcx, [rcx+10h]
0x140062782  call    WPP_SF_DsD
0x140062787  call    ?PreMessageLoop@CTSClientModule@@QEAAJXZ; CTSClientModule::PreMessageLoop(void)
0x14006278c  mov     ebx, eax
0x14006278e  test    eax, eax
0x140062790  jns     short loc_1400627E7
0x140062792  mov     rax, cs:WPP_GLOBAL_Control
0x140062799  lea     r14, WPP_GLOBAL_Control
0x1400627a0  cmp     rax, r14
0x1400627a3  jz      short loc_14006280E
0x1400627a5  test    byte ptr [rax+1Ch], 8
0x1400627a9  jz      short loc_14006280E
0x1400627ab  cmp     byte ptr [rax+19h], 2
0x1400627af  jb      short loc_14006280E
0x1400627b1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400627b6  mov     edx, 19h
0x1400627bb  lea     rcx, aAtlmodulePreme; "_AtlModule.PreMessageLoop failed!"
0x1400627c2  mov     dword ptr [rsp+140h+var_118], ebx
0x1400627c6  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x1400627cd  mov     [rsp+140h+var_120], rcx
0x1400627d2  mov     r9d, eax
0x1400627d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400627dc  mov     rcx, [rcx+10h]
0x1400627e0  call    WPP_SF_DsD
0x1400627e5  jmp     short loc_14006280E
0x1400627e7  cmp     ebx, 40200h
0x1400627ed  jz      short loc_140062807
0x1400627ef  cmp     cs:dword_1401519AC, esi
0x1400627f5  jz      short loc_140062869
0x1400627f7  cmp     cs:dword_1401519A8, esi
0x1400627fd  mov     rdx, r12; HACCEL
0x140062800  jz      short loc_140062862
0x140062802  call    ?RunMessageLoopSingleUse@CTSClientModule@@AEAAXPEAUHACCEL__@@@Z; CTSClientModule::RunMessageLoopSingleUse(HACCEL__ *)
0x140062807  lea     r14, WPP_GLOBAL_Control
0x14006280e  mov     r15d, 1
0x140062814  cmp     cs:dword_1401519AC, esi
0x14006281a  jz      loc_140062DFE
0x140062820  mov     rcx, cs:off_1401501E8
0x140062827  mov     eax, esi
0x140062829  mov     rsi, cs:off_1401501E0
0x140062830  cmp     rsi, rcx
0x140062833  jnb     loc_140062DE7
0x140062839  xor     r8d, r8d
0x14006283c  test    eax, eax
0x14006283e  jnz     loc_140062DE7
0x140062844  mov     rdx, [rsi]
0x140062847  test    rdx, rdx
0x14006284a  jz      loc_140062DDA
0x140062850  cmp     [rdx+28h], r8d
0x140062854  jnz     loc_140062DC7
0x14006285a  mov     eax, r8d
0x14006285d  jmp     loc_140062DDA
0x140062862  call    ?RunMessageLoopMultiUse@CTSClientModule@@AEAAXPEAUHACCEL__@@@Z; CTSClientModule::RunMessageLoopMultiUse(HACCEL__ *)
0x140062867  jmp     short loc_140062807
0x140062869  mov     ecx, 19F0h; Size
0x14006286e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140062873  test    rax, rax
0x140062876  jz      loc_140062D95
0x14006287c  mov     rcx, rax; this
0x14006287f  call    ??0CommandLineData@@QEAA@XZ; CommandLineData::CommandLineData(void)
0x140062884  mov     rdi, rax
0x140062887  test    rax, rax
0x14006288a  jz      loc_140062D95
0x140062890  xor     r9d, r9d; unsigned __int16 *
0x140062893  mov     rdx, r14; unsigned __int16 *
0x140062896  mov     rcx, rax; this
0x140062899  call    ?ProcessCommand@CommandLineData@@QEAAKPEBG_N0@Z; CommandLineData::ProcessCommand(ushort const *,bool,ushort const *)
0x14006289e  mov     esi, eax
0x1400628a0  xor     eax, eax
0x1400628a2  test    r14, r14
0x1400628a5  jz      short loc_140062910
0x1400628a7  cmp     [r14], ax
0x1400628ab  jz      short loc_140062910
0x1400628ad  movups  xmm0, xmmword ptr [rdi+1970h]
0x1400628b4  mov     edx, esi
0x1400628b6  lea     rcx, [rbp+40h+var_C0]
0x1400628ba  movups  xmm1, xmmword ptr [rdi+1980h]
0x1400628c1  movaps  [rbp+40h+var_C0], xmm0
0x1400628c5  movups  xmm0, xmmword ptr [rdi+1990h]
0x1400628cc  movaps  [rbp+40h+var_B0], xmm1
0x1400628d0  movups  xmm1, xmmword ptr [rdi+19A0h]
0x1400628d7  movaps  [rbp+40h+var_A0], xmm0
0x1400628db  movups  xmm0, xmmword ptr [rdi+19B0h]
0x1400628e2  movaps  [rbp+40h+var_90], xmm1
0x1400628e6  movups  xmm1, xmmword ptr [rdi+19C0h]
0x1400628ed  movaps  [rbp+40h+var_80], xmm0
0x1400628f1  movups  xmm0, xmmword ptr [rdi+19D0h]
0x1400628f8  movaps  [rbp+40h+var_70], xmm1
0x1400628fc  movups  xmm1, xmmword ptr [rdi+19E0h]
0x140062903  movaps  [rbp+40h+var_60], xmm0
0x140062907  movaps  [rbp+40h+var_50], xmm1
0x14006290b  call    ?SendCmdLineLaunchEvent@MSTSCTelemetry@@SAXUCMDUsageData@@K@Z; MSTSCTelemetry::SendCmdLineLaunchEvent(CMDUsageData,ulong)
0x140062910  cmp     esi, 1
0x140062913  jz      short loc_14006296B
0x140062915  mov     rax, cs:WPP_GLOBAL_Control
0x14006291c  lea     r14, WPP_GLOBAL_Control
0x140062923  mov     r15d, 1
0x140062929  cmp     rax, r14
0x14006292c  jz      short loc_140062961
0x14006292e  test    [rax+1Ch], r15b
0x140062932  jz      short loc_140062961
0x140062934  cmp     byte ptr [rax+19h], 2
0x140062938  jb      short loc_140062961
0x14006293a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006293f  mov     rcx, cs:WPP_GLOBAL_Control
0x140062946  lea     edx, [r15+1Ah]
0x14006294a  mov     r9d, eax
0x14006294d  mov     dword ptr [rsp+140h+var_120], esi
0x140062951  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140062958  mov     rcx, [rcx+10h]
0x14006295c  call    WPP_SF_Dd
0x140062961  mov     r13d, r15d
0x140062964  xor     esi, esi
0x140062966  jmp     loc_140062814
0x14006296b  xor     esi, esi
0x14006296d  cmp     [rdi+12A8h], esi
0x140062973  jz      short loc_140062987
0x140062975  mov     rdx, r15; HINSTANCE
0x140062978  mov     rcx, rdi; struct CommandLineData *
0x14006297b  call    ?RunShadow@@YAJPEAVCommandLineData@@PEAUHINSTANCE__@@@Z; RunShadow(CommandLineData *,HINSTANCE__ *)
0x140062980  mov     ebx, eax
0x140062982  jmp     loc_140062807
0x140062987  lea     rdx, [rsp+140h+var_108]; struct CTscRemoteSession **
0x14006298c  mov     rcx, r15; HINSTANCE
0x14006298f  call    ?CreateInstance@CTscRemoteSession@@SAJPEAUHINSTANCE__@@PEAPEAV1@@Z; CTscRemoteSession::CreateInstance(HINSTANCE__ *,CTscRemoteSession * *)
0x140062994  mov     ebx, eax
0x140062996  test    eax, eax
0x140062998  jns     short loc_1400629DB
0x14006299a  mov     rax, cs:WPP_GLOBAL_Control
0x1400629a1  lea     r14, WPP_GLOBAL_Control
0x1400629a8  cmp     rax, r14
0x1400629ab  jz      loc_14006280E
0x1400629b1  test    byte ptr [rax+1Ch], 8
0x1400629b5  jz      loc_14006280E
0x1400629bb  cmp     byte ptr [rax+19h], 2
0x1400629bf  jb      loc_14006280E
0x1400629c5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400629ca  mov     edx, 1Ch
0x1400629cf  lea     rcx, aCreateinstance_0; "CreateInstance failed. Exiting!"
0x1400629d6  jmp     loc_1400627C2
0x1400629db  mov     ecx, 35090h; Size
0x1400629e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400629e5  test    rax, rax
0x1400629e8  jz      loc_140062D3C
0x1400629ee  mov     rcx, rax; this
0x1400629f1  call    ??0CTscSettings@@QEAA@XZ; CTscSettings::CTscSettings(void)
0x1400629f6  mov     rsi, rax
0x1400629f9  test    rsi, rsi
0x1400629fc  jz      loc_140062D3C
0x140062a02  lea     rcx, [rsp+140h+var_100]
0x140062a07  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x140062a0c  lea     rcx, [rsp+140h+var_100]
0x140062a11  mov     [rsp+140h+var_100], rsi
0x140062a16  call    ?SafeAddRef@?$TCntPtr@VCTscSettings@@@@AEAAXXZ; TCntPtr<CTscSettings>::SafeAddRef(void)
0x140062a1b  mov     rdx, rdi; struct CommandLineData *
0x140062a1e  mov     rcx, rsi; this
0x140062a21  call    ?Initialize@CTscSettings@@QEAAJAEBVCommandLineData@@@Z; CTscSettings::Initialize(CommandLineData const &)
0x140062a26  xor     edx, edx
0x140062a28  mov     ebx, eax
0x140062a2a  test    eax, eax
0x140062a2c  jns     short loc_140062A88
0x140062a2e  mov     rax, cs:WPP_GLOBAL_Control
0x140062a35  lea     r14, WPP_GLOBAL_Control
0x140062a3c  cmp     rax, r14
0x140062a3f  jz      short loc_140062A81
0x140062a41  test    byte ptr [rax+1Ch], 8
0x140062a45  jz      short loc_140062A81
0x140062a47  cmp     byte ptr [rax+19h], 2
0x140062a4b  jb      short loc_140062A81
0x140062a4d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062a52  mov     edx, 1Eh
0x140062a57  lea     rcx, aFailedToInitia_20; "Failed to initialize the settings objec"...
0x140062a5e  mov     dword ptr [rsp+140h+var_118], ebx
0x140062a62  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140062a69  mov     [rsp+140h+var_120], rcx
0x140062a6e  mov     r9d, eax
0x140062a71  mov     rcx, cs:WPP_GLOBAL_Control
0x140062a78  mov     rcx, [rcx+10h]
0x140062a7c  call    WPP_SF_DsD
0x140062a81  xor     esi, esi
0x140062a83  jmp     loc_14006280E
0x140062a88  cmp     [rdi+0C40h], edx
0x140062a8e  lea     rax, [rdi+0A34h]
0x140062a95  mov     r8d, edx
0x140062a98  mov     [rsp+140h+var_118], rax; unsigned __int16 *
0x140062a9d  lea     rcx, [rdi+82Ch]; this
0x140062aa4  setz    r8b; int
0x140062aa8  mov     r9, r14; unsigned __int16 *
0x140062aab  mov     [rsp+140h+var_120], rcx; unsigned __int16 *
0x140062ab0  mov     rdx, rsi; struct CTscSettings *
0x140062ab3  call    ?TryBindToSingletonRailProcess@CTscRemoteSession@@QEAAJPEAVCTscSettings@@HPEBG11@Z; CTscRemoteSession::TryBindToSingletonRailProcess(CTscSettings *,int,ushort const *,ushort const *,ushort const *)
0x140062ab8  mov     ebx, eax
0x140062aba  cmp     eax, 40200h
0x140062abf  jz      loc_140062D35
0x140062ac5  xor     r14d, r14d
0x140062ac8  test    eax, eax
0x140062aca  jns     short loc_140062B01
0x140062acc  mov     rax, cs:WPP_GLOBAL_Control
0x140062ad3  lea     r14, WPP_GLOBAL_Control
0x140062ada  cmp     rax, r14
0x140062add  jz      short loc_140062A81
0x140062adf  test    byte ptr [rax+1Ch], 8
0x140062ae3  jz      short loc_140062A81
0x140062ae5  cmp     byte ptr [rax+19h], 2
0x140062ae9  jb      short loc_140062A81
0x140062aeb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062af0  mov     edx, 1Fh
0x140062af5  lea     rcx, aTrybindtosingl; "TryBindToSingletonRailProcess failed"
0x140062afc  jmp     loc_140062A5E
0x140062b01  mov     rdx, rdi; struct CommandLineData *
0x140062b04  mov     rcx, rsi; this
0x140062b07  call    ?LoadAllSettings@CTscSettings@@QEAAJAEBVCommandLineData@@@Z; CTscSettings::LoadAllSettings(CommandLineData const &)
0x140062b0c  mov     ebx, eax
0x140062b0e  test    eax, eax
0x140062b10  jns     short loc_140062B53
0x140062b12  mov     rax, cs:WPP_GLOBAL_Control
0x140062b19  lea     r14, WPP_GLOBAL_Control
0x140062b20  cmp     rax, r14
0x140062b23  jz      loc_140062A81
0x140062b29  test    byte ptr [rax+1Ch], 8
0x140062b2d  jz      loc_140062A81
0x140062b33  cmp     byte ptr [rax+19h], 2
0x140062b37  jb      loc_140062A81
0x140062b3d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062b42  mov     edx, 20h ; ' '
0x140062b47  lea     rcx, aLoadallsetting; "LoadAllSettings Failed"
0x140062b4e  jmp     loc_140062A5E
0x140062b53  lea     rcx, [rsi+35078h]; struct ISharedSettings *
0x140062b5a  call    ?InitializeTestObjects@@YAJPEAVISharedSettings@@@Z; InitializeTestObjects(ISharedSettings *)
0x140062b5f  lea     rcx, [rdi+1064h]; lpFileName
0x140062b66  cmp     [rcx], r14w
0x140062b6a  jz      short loc_140062B82
0x140062b6c  call    cs:__imp_DeleteFileW
0x140062b72  mov     edx, 1; unsigned int
0x140062b77  mov     rcx, rdi; this
0x140062b7a  call    ??_GCommandLineData@@UEAAPEAXI@Z; CommandLineData::`scalar deleting destructor'(uint)
0x140062b7f  mov     rdi, r14
0x140062b82  lea     r8, [rbp+40h+arg_8]; unsigned int *
  ... truncated ...
```
