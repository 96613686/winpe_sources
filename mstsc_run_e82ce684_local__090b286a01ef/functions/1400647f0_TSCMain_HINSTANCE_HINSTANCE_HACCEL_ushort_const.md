# TSCMain(HINSTANCE__ *,HINSTANCE__ *,HACCEL__ *,ushort const *)

- ea: `0x1400647f0`
- end: `0x140065049`
- name: `?TSCMain@@YAHPEAUHINSTANCE__@@0PEAUHACCEL__@@PEBG@Z`
- size: `2137`
- prototype: `__int64 __fastcall(HINSTANCE, HINSTANCE, HACCEL, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14006590c`

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
- `0x140037094`
- `0x1400379dc`
- `0x1400427d8`
- `0x140043310`
- `0x1400434d0`
- `0x140043630`
- `0x140043f94`
- `0x1400441f8`
- `0x140056208`
- `0x140056eec`
- `0x14005fc9c`
- `0x14006374c`
- `0x140064090`
- `0x1400642b4`
- `0x1400647f0`
- `0x140114010`

## import_xrefs

- `USER32!IsDialogMessageW` at `0x140064e16`
- `USER32!IsDialogMessageW` at `0x140064e16`
- `USER32!TranslateAcceleratorW` at `0x140064e04`
- `USER32!TranslateAcceleratorW` at `0x140064e04`
- `USER32!DispatchMessageW` at `0x140064e30`
- `USER32!DispatchMessageW` at `0x140064e30`
- `USER32!TranslateMessage` at `0x140064e25`
- `USER32!TranslateMessage` at `0x140064e25`
- `USER32!GetMessageW` at `0x140064de6`
- `USER32!GetMessageW` at `0x140064de6`
- `KERNEL32!Sleep` at `0x140064f68`
- `KERNEL32!Sleep` at `0x140064f68`
- `KERNEL32!DeleteFileW` at `0x140064cdc`
- `KERNEL32!DeleteFileW` at `0x140064f87`
- `KERNEL32!DeleteFileW` at `0x140064cdc`
- `KERNEL32!DeleteFileW` at `0x140064f87`
- `KERNEL32!GetLastError` at `0x140064e38`
- `KERNEL32!GetLastError` at `0x140064e38`
- `ole32!CoRevokeClassObject` at `0x140064f3a`
- `ole32!CoRevokeClassObject` at `0x140064f3a`

## string_xrefs

- `0x140064f2e`: `CommandLineData`
- `0x140064b3f`: `CreateInstance failed. Exiting!`

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
  v11 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1401520E0);
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
  if ( dword_140153ADC )
  {
    if ( dword_140153AD8 )
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
  if ( dword_140153ADC != (_DWORD)v4 )
  {
    v19 = off_1401521E8;
    v20 = (int)v4;
    for ( i = off_1401521E0; i < (GUID ***)v19; ++i )
    {
      if ( v20 )
        break;
      v22 = *i;
      if ( *i )
      {
        if ( *((_DWORD *)v22 + 10) )
        {
          v20 = CoRevokeClassObject(*((_DWORD *)v22 + 10));
          v19 = off_1401521E8;
        }
        else
        {
          v20 = 0;
        }
      }
    }
    v4 = 0;
    if ( byte_140153AC0 )
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
  TraceLoggingUnregister_EventUnregister(&dword_1401520E0);
  TCntPtr<CTSCoreEventSink>::SafeRelease(&v52);
  TCntPtr<CTSCoreEventSink>::SafeRelease(&v51);
  return v6;
}

```

## disassembly

```asm
0x1400647f0  mov     [rsp-8+arg_8], rdx
0x1400647f5  push    rbp
0x1400647f6  push    rbx
0x1400647f7  push    rsi
0x1400647f8  push    rdi
0x1400647f9  push    r12
0x1400647fb  push    r13
0x1400647fd  push    r14
0x1400647ff  push    r15
0x140064801  lea     rbp, [rsp-8]
0x140064806  sub     rsp, 108h
0x14006480d  xorps   xmm0, xmm0
0x140064810  xor     esi, esi
0x140064812  mov     r15, rcx
0x140064815  mov     [rsp+140h+var_108], rsi
0x14006481a  lea     rcx, dword_1401520E0; CallbackContext
0x140064821  mov     [rsp+140h+var_100], rsi
0x140064826  movups  xmmword ptr [rsp+140h+Msg.hwnd], xmm0
0x14006482b  mov     r13d, esi
0x14006482e  mov     edi, esi
0x140064830  movups  xmmword ptr [rsp+140h+Msg.wParam], xmm0
0x140064835  mov     r14, r9
0x140064838  mov     r12, r8
0x14006483b  movups  xmmword ptr [rsp+140h+Msg.time], xmm0
0x140064840  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140064845  mov     ebx, eax
0x140064847  lea     rax, WPP_GLOBAL_Control
0x14006484e  test    ebx, ebx
0x140064850  jns     loc_1400648F7
0x140064856  mov     rcx, cs:WPP_GLOBAL_Control
0x14006485d  cmp     rcx, rax
0x140064860  jz      loc_1400648F7
0x140064866  test    byte ptr [rcx+1Ch], 8
0x14006486a  jz      short loc_1400648B2
0x14006486c  cmp     byte ptr [rcx+19h], 2
0x140064870  jb      short loc_1400648B2
0x140064872  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064877  lea     rcx, aTraceloggingre; "TraceLoggingRegister Failed"
0x14006487e  mov     dword ptr [rsp+140h+var_118], ebx
0x140064882  mov     [rsp+140h+var_120], rcx
0x140064887  lea     edx, [rsi+0Ah]
0x14006488a  mov     rcx, cs:WPP_GLOBAL_Control
0x140064891  lea     r8, WPP_b43a4c2333b03a5b3f0d65e5fddc42d4_Traceguids
0x140064898  mov     r9d, eax
0x14006489b  mov     rcx, [rcx+10h]
0x14006489f  call    WPP_SF_DsD
0x1400648a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400648ab  lea     rax, WPP_GLOBAL_Control
0x1400648b2  cmp     rcx, rax
0x1400648b5  jz      short loc_1400648F7
0x1400648b7  test    byte ptr [rcx+1Ch], 8
0x1400648bb  jz      short loc_1400648F7
0x1400648bd  cmp     byte ptr [rcx+19h], 2
0x1400648c1  jb      short loc_1400648F7
0x1400648c3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400648c8  lea     rcx, aMstsctelemetry; "MSTSCTelemetryTraceLogging_Registe fail"...
0x1400648cf  mov     dword ptr [rsp+140h+var_118], ebx
0x1400648d3  mov     [rsp+140h+var_120], rcx
0x1400648d8  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x1400648df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400648e6  mov     edx, 18h
0x1400648eb  mov     r9d, eax
0x1400648ee  mov     rcx, [rcx+10h]
0x1400648f2  call    WPP_SF_DsD
0x1400648f7  call    ?PreMessageLoop@CTSClientModule@@QEAAJXZ; CTSClientModule::PreMessageLoop(void)
0x1400648fc  mov     ebx, eax
0x1400648fe  test    eax, eax
0x140064900  jns     short loc_140064957
0x140064902  mov     rax, cs:WPP_GLOBAL_Control
0x140064909  lea     r14, WPP_GLOBAL_Control
0x140064910  cmp     rax, r14
0x140064913  jz      short loc_14006497E
0x140064915  test    byte ptr [rax+1Ch], 8
0x140064919  jz      short loc_14006497E
0x14006491b  cmp     byte ptr [rax+19h], 2
0x14006491f  jb      short loc_14006497E
0x140064921  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064926  mov     edx, 19h
0x14006492b  lea     rcx, aAtlmodulePreme; "_AtlModule.PreMessageLoop failed!"
0x140064932  mov     dword ptr [rsp+140h+var_118], ebx
0x140064936  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x14006493d  mov     [rsp+140h+var_120], rcx
0x140064942  mov     r9d, eax
0x140064945  mov     rcx, cs:WPP_GLOBAL_Control
0x14006494c  mov     rcx, [rcx+10h]
0x140064950  call    WPP_SF_DsD
0x140064955  jmp     short loc_14006497E
0x140064957  cmp     ebx, 40200h
0x14006495d  jz      short loc_140064977
0x14006495f  cmp     cs:dword_140153ADC, esi
0x140064965  jz      short loc_1400649D9
0x140064967  cmp     cs:dword_140153AD8, esi
0x14006496d  mov     rdx, r12; HACCEL
0x140064970  jz      short loc_1400649D2
0x140064972  call    ?RunMessageLoopSingleUse@CTSClientModule@@AEAAXPEAUHACCEL__@@@Z; CTSClientModule::RunMessageLoopSingleUse(HACCEL__ *)
0x140064977  lea     r14, WPP_GLOBAL_Control
0x14006497e  mov     r15d, 1
0x140064984  cmp     cs:dword_140153ADC, esi
0x14006498a  jz      loc_140064F6E
0x140064990  mov     rcx, cs:off_1401521E8
0x140064997  mov     eax, esi
0x140064999  mov     rsi, cs:off_1401521E0
0x1400649a0  cmp     rsi, rcx
0x1400649a3  jnb     loc_140064F57
0x1400649a9  xor     r8d, r8d
0x1400649ac  test    eax, eax
0x1400649ae  jnz     loc_140064F57
0x1400649b4  mov     rdx, [rsi]
0x1400649b7  test    rdx, rdx
0x1400649ba  jz      loc_140064F4A
0x1400649c0  cmp     [rdx+28h], r8d
0x1400649c4  jnz     loc_140064F37
0x1400649ca  mov     eax, r8d
0x1400649cd  jmp     loc_140064F4A
0x1400649d2  call    ?RunMessageLoopMultiUse@CTSClientModule@@AEAAXPEAUHACCEL__@@@Z; CTSClientModule::RunMessageLoopMultiUse(HACCEL__ *)
0x1400649d7  jmp     short loc_140064977
0x1400649d9  mov     ecx, 19F0h; Size
0x1400649de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400649e3  test    rax, rax
0x1400649e6  jz      loc_140064F05
0x1400649ec  mov     rcx, rax; this
0x1400649ef  call    ??0CommandLineData@@QEAA@XZ; CommandLineData::CommandLineData(void)
0x1400649f4  mov     rdi, rax
0x1400649f7  test    rax, rax
0x1400649fa  jz      loc_140064F05
0x140064a00  xor     r9d, r9d; unsigned __int16 *
0x140064a03  mov     rdx, r14; unsigned __int16 *
0x140064a06  mov     rcx, rax; this
0x140064a09  call    ?ProcessCommand@CommandLineData@@QEAAKPEBG_N0@Z; CommandLineData::ProcessCommand(ushort const *,bool,ushort const *)
0x140064a0e  mov     esi, eax
0x140064a10  xor     eax, eax
0x140064a12  test    r14, r14
0x140064a15  jz      short loc_140064A80
0x140064a17  cmp     [r14], ax
0x140064a1b  jz      short loc_140064A80
0x140064a1d  movups  xmm0, xmmword ptr [rdi+1970h]
0x140064a24  mov     edx, esi
0x140064a26  lea     rcx, [rbp+40h+var_C0]
0x140064a2a  movups  xmm1, xmmword ptr [rdi+1980h]
0x140064a31  movaps  [rbp+40h+var_C0], xmm0
0x140064a35  movups  xmm0, xmmword ptr [rdi+1990h]
0x140064a3c  movaps  [rbp+40h+var_B0], xmm1
0x140064a40  movups  xmm1, xmmword ptr [rdi+19A0h]
0x140064a47  movaps  [rbp+40h+var_A0], xmm0
0x140064a4b  movups  xmm0, xmmword ptr [rdi+19B0h]
0x140064a52  movaps  [rbp+40h+var_90], xmm1
0x140064a56  movups  xmm1, xmmword ptr [rdi+19C0h]
0x140064a5d  movaps  [rbp+40h+var_80], xmm0
0x140064a61  movups  xmm0, xmmword ptr [rdi+19D0h]
0x140064a68  movaps  [rbp+40h+var_70], xmm1
0x140064a6c  movups  xmm1, xmmword ptr [rdi+19E0h]
0x140064a73  movaps  [rbp+40h+var_60], xmm0
0x140064a77  movaps  [rbp+40h+var_50], xmm1
0x140064a7b  call    ?SendCmdLineLaunchEvent@MSTSCTelemetry@@SAXUCMDUsageData@@K@Z; MSTSCTelemetry::SendCmdLineLaunchEvent(CMDUsageData,ulong)
0x140064a80  cmp     esi, 1
0x140064a83  jz      short loc_140064ADB
0x140064a85  mov     rax, cs:WPP_GLOBAL_Control
0x140064a8c  lea     r14, WPP_GLOBAL_Control
0x140064a93  mov     r15d, 1
0x140064a99  cmp     rax, r14
0x140064a9c  jz      short loc_140064AD1
0x140064a9e  test    [rax+1Ch], r15b
0x140064aa2  jz      short loc_140064AD1
0x140064aa4  cmp     byte ptr [rax+19h], 2
0x140064aa8  jb      short loc_140064AD1
0x140064aaa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x140064ab6  lea     edx, [r15+1Ah]
0x140064aba  mov     r9d, eax
0x140064abd  mov     dword ptr [rsp+140h+var_120], esi
0x140064ac1  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140064ac8  mov     rcx, [rcx+10h]
0x140064acc  call    WPP_SF_Dd
0x140064ad1  mov     r13d, r15d
0x140064ad4  xor     esi, esi
0x140064ad6  jmp     loc_140064984
0x140064adb  xor     esi, esi
0x140064add  cmp     [rdi+12A8h], esi
0x140064ae3  jz      short loc_140064AF7
0x140064ae5  mov     rdx, r15; HINSTANCE
0x140064ae8  mov     rcx, rdi; struct CommandLineData *
0x140064aeb  call    ?RunShadow@@YAJPEAVCommandLineData@@PEAUHINSTANCE__@@@Z; RunShadow(CommandLineData *,HINSTANCE__ *)
0x140064af0  mov     ebx, eax
0x140064af2  jmp     loc_140064977
0x140064af7  lea     rdx, [rsp+140h+var_108]; struct CTscRemoteSession **
0x140064afc  mov     rcx, r15; HINSTANCE
0x140064aff  call    ?CreateInstance@CTscRemoteSession@@SAJPEAUHINSTANCE__@@PEAPEAV1@@Z; CTscRemoteSession::CreateInstance(HINSTANCE__ *,CTscRemoteSession * *)
0x140064b04  mov     ebx, eax
0x140064b06  test    eax, eax
0x140064b08  jns     short loc_140064B4B
0x140064b0a  mov     rax, cs:WPP_GLOBAL_Control
0x140064b11  lea     r14, WPP_GLOBAL_Control
0x140064b18  cmp     rax, r14
0x140064b1b  jz      loc_14006497E
0x140064b21  test    byte ptr [rax+1Ch], 8
0x140064b25  jz      loc_14006497E
0x140064b2b  cmp     byte ptr [rax+19h], 2
0x140064b2f  jb      loc_14006497E
0x140064b35  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064b3a  mov     edx, 1Ch
0x140064b3f  lea     rcx, aCreateinstance_0; "CreateInstance failed. Exiting!"
0x140064b46  jmp     loc_140064932
0x140064b4b  mov     ecx, 35090h; Size
0x140064b50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140064b55  test    rax, rax
0x140064b58  jz      loc_140064EAC
0x140064b5e  mov     rcx, rax; this
0x140064b61  call    ??0CTscSettings@@QEAA@XZ; CTscSettings::CTscSettings(void)
0x140064b66  mov     rsi, rax
0x140064b69  test    rsi, rsi
0x140064b6c  jz      loc_140064EAC
0x140064b72  lea     rcx, [rsp+140h+var_100]
0x140064b77  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x140064b7c  lea     rcx, [rsp+140h+var_100]
0x140064b81  mov     [rsp+140h+var_100], rsi
0x140064b86  call    ?SafeAddRef@?$TCntPtr@VCTscSettings@@@@AEAAXXZ; TCntPtr<CTscSettings>::SafeAddRef(void)
0x140064b8b  mov     rdx, rdi; struct CommandLineData *
0x140064b8e  mov     rcx, rsi; this
0x140064b91  call    ?Initialize@CTscSettings@@QEAAJAEBVCommandLineData@@@Z; CTscSettings::Initialize(CommandLineData const &)
0x140064b96  xor     edx, edx
0x140064b98  mov     ebx, eax
0x140064b9a  test    eax, eax
0x140064b9c  jns     short loc_140064BF8
0x140064b9e  mov     rax, cs:WPP_GLOBAL_Control
0x140064ba5  lea     r14, WPP_GLOBAL_Control
0x140064bac  cmp     rax, r14
0x140064baf  jz      short loc_140064BF1
0x140064bb1  test    byte ptr [rax+1Ch], 8
0x140064bb5  jz      short loc_140064BF1
0x140064bb7  cmp     byte ptr [rax+19h], 2
0x140064bbb  jb      short loc_140064BF1
0x140064bbd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064bc2  mov     edx, 1Eh
0x140064bc7  lea     rcx, aFailedToInitia_20; "Failed to initialize the settings objec"...
0x140064bce  mov     dword ptr [rsp+140h+var_118], ebx
0x140064bd2  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140064bd9  mov     [rsp+140h+var_120], rcx
0x140064bde  mov     r9d, eax
0x140064be1  mov     rcx, cs:WPP_GLOBAL_Control
0x140064be8  mov     rcx, [rcx+10h]
0x140064bec  call    WPP_SF_DsD
0x140064bf1  xor     esi, esi
0x140064bf3  jmp     loc_14006497E
0x140064bf8  cmp     [rdi+0C40h], edx
0x140064bfe  lea     rax, [rdi+0A34h]
0x140064c05  mov     r8d, edx
0x140064c08  mov     [rsp+140h+var_118], rax; unsigned __int16 *
0x140064c0d  lea     rcx, [rdi+82Ch]; this
0x140064c14  setz    r8b; int
0x140064c18  mov     r9, r14; unsigned __int16 *
0x140064c1b  mov     [rsp+140h+var_120], rcx; unsigned __int16 *
0x140064c20  mov     rdx, rsi; struct CTscSettings *
0x140064c23  call    ?TryBindToSingletonRailProcess@CTscRemoteSession@@QEAAJPEAVCTscSettings@@HPEBG11@Z; CTscRemoteSession::TryBindToSingletonRailProcess(CTscSettings *,int,ushort const *,ushort const *,ushort const *)
0x140064c28  mov     ebx, eax
0x140064c2a  cmp     eax, 40200h
0x140064c2f  jz      loc_140064EA5
0x140064c35  xor     r14d, r14d
0x140064c38  test    eax, eax
0x140064c3a  jns     short loc_140064C71
0x140064c3c  mov     rax, cs:WPP_GLOBAL_Control
0x140064c43  lea     r14, WPP_GLOBAL_Control
0x140064c4a  cmp     rax, r14
0x140064c4d  jz      short loc_140064BF1
0x140064c4f  test    byte ptr [rax+1Ch], 8
0x140064c53  jz      short loc_140064BF1
0x140064c55  cmp     byte ptr [rax+19h], 2
0x140064c59  jb      short loc_140064BF1
0x140064c5b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064c60  mov     edx, 1Fh
0x140064c65  lea     rcx, aTrybindtosingl; "TryBindToSingletonRailProcess failed"
0x140064c6c  jmp     loc_140064BCE
0x140064c71  mov     rdx, rdi; struct CommandLineData *
0x140064c74  mov     rcx, rsi; this
0x140064c77  call    ?LoadAllSettings@CTscSettings@@QEAAJAEBVCommandLineData@@@Z; CTscSettings::LoadAllSettings(CommandLineData const &)
0x140064c7c  mov     ebx, eax
0x140064c7e  test    eax, eax
0x140064c80  jns     short loc_140064CC3
0x140064c82  mov     rax, cs:WPP_GLOBAL_Control
0x140064c89  lea     r14, WPP_GLOBAL_Control
0x140064c90  cmp     rax, r14
0x140064c93  jz      loc_140064BF1
0x140064c99  test    byte ptr [rax+1Ch], 8
0x140064c9d  jz      loc_140064BF1
0x140064ca3  cmp     byte ptr [rax+19h], 2
0x140064ca7  jb      loc_140064BF1
0x140064cad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064cb2  mov     edx, 20h ; ' '
0x140064cb7  lea     rcx, aLoadallsetting; "LoadAllSettings Failed"
0x140064cbe  jmp     loc_140064BCE
0x140064cc3  lea     rcx, [rsi+35078h]; struct ISharedSettings *
0x140064cca  call    ?InitializeTestObjects@@YAJPEAVISharedSettings@@@Z; InitializeTestObjects(ISharedSettings *)
0x140064ccf  lea     rcx, [rdi+1064h]; lpFileName
0x140064cd6  cmp     [rcx], r14w
0x140064cda  jz      short loc_140064CF2
0x140064cdc  call    cs:__imp_DeleteFileW
0x140064ce2  mov     edx, 1; unsigned int
0x140064ce7  mov     rcx, rdi; this
0x140064cea  call    ??_GCommandLineData@@UEAAPEAXI@Z; CommandLineData::`scalar deleting destructor'(uint)
0x140064cef  mov     rdi, r14
0x140064cf2  lea     r8, [rbp+40h+arg_8]; unsigned int *
  ... truncated ...
```
