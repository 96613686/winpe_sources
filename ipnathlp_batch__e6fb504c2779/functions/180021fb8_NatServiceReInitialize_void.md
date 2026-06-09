# NatServiceReInitialize(void)

- ea: `0x180021fb8`
- end: `0x180022593`
- name: `?NatServiceReInitialize@@YAXXZ`
- size: `1499`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180021b40`
- `0x180042360`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x1800202e0`
- `0x180021cf0`
- `0x180021fb8`
- `0x18002259c`
- `0x1800226e0`
- `0x1800229dc`
- `0x180022a90`
- `0x18003e3a0`
- `0x180042114`
- `0x180074960`
- `0x180074adc`
- `0x180076b4c`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002209a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800221b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022303`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002209a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800221b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022303`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800222e2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002236c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800222e2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002236c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800221d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002231b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800221d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002231b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180022064`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180022064`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180022077`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180022077`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180022136`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180022136`

## string_xrefs

- `0x180022247`: `SharedAccess`

## pseudocode

```c
void NatServiceReInitialize(void)
{
  signed int v0; // ebx
  int v1; // ebp
  HANDLE EventW; // rax
  signed int LastError; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  signed int v7; // eax
  signed int v8; // eax
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  signed int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned int updated; // eax
  __int16 v18; // [rsp+72h] [rbp+Ah]
  int v19; // [rsp+78h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 225, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  v0 = 0;
  v18 = 0;
  v1 = 0;
  v19 = 0;
  if ( (unsigned int)NatServiceShouldStop(&v19) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
    }
    SetServiceStartupTypeToManual();
    goto LABEL_101;
  }
  ClearPersistentDhcpExceptions();
  WaitForThreadpoolWorkCallbacks(g_FirewallExceptionBackgroundWork, 1);
  SubmitThreadpoolWork(g_FirewallExceptionBackgroundWork);
  if ( !hObject )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    hObject = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
      v18 = HIWORD(v0);
      if ( v0 >= 0 )
        goto LABEL_101;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_101;
      }
      v5 = 227;
      goto LABEL_20;
    }
    if ( !RegisterWaitForSingleObject(&WaitHandle, EventW, NatServiceOnControl, 0, 0xFFFFFFFF, 0) )
    {
      v7 = GetLastError();
      v0 = v7;
      if ( v7 > 0 )
        v0 = (unsigned __int16)v7 | 0x80070000;
      v18 = HIWORD(v0);
      if ( v0 >= 0 )
        goto LABEL_101;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_101;
      }
      v5 = 228;
      goto LABEL_20;
    }
  }
  if ( *(&WaitHandle + 1) )
  {
    ResetEvent(*(&WaitHandle + 1));
    goto LABEL_57;
  }
  *(&WaitHandle + 1) = CreateEventW(0, 1, 0, 0);
  if ( !*(&WaitHandle + 1) )
  {
    v8 = GetLastError();
    v0 = v8;
    if ( v8 > 0 )
      v0 = (unsigned __int16)v8 | 0x80070000;
    v18 = HIWORD(v0);
    if ( v0 >= 0 )
      goto LABEL_101;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_101;
    }
    v5 = 229;
    goto LABEL_20;
  }
  if ( !g_pSvchostSharedGlobals )
  {
    v0 = -2147467259;
    v18 = 0x8000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_101;
    }
    v11 = 231;
    goto LABEL_53;
  }
  v9 = (*((__int64 (__fastcall **)(HANDLE *, const WCHAR *, _QWORD, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))g_pSvchostSharedGlobals
        + 24))(
         &xmmword_1800AE3F0,
         L"SharedAccess",
         *(&WaitHandle + 1),
         StopServiceCallback,
         0,
         8);
  if ( !v9 )
  {
    v1 = 1;
    goto LABEL_54;
  }
  if ( v9 > 0 )
    v0 = (unsigned __int16)v9 | 0x80070000;
  else
    v0 = v9;
  v18 = HIWORD(v0);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 230;
LABEL_53:
    WPP_SF_d(v10[2], v11, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, (unsigned int)v0);
  }
LABEL_54:
  if ( v0 < 0 )
    goto LABEL_101;
LABEL_57:
  if ( *(&xmmword_1800AE3F0 + 1) )
  {
    ResetEvent(*(&xmmword_1800AE3F0 + 1));
  }
  else
  {
    *(&xmmword_1800AE3F0 + 1) = CreateEventW(0, 1, 0, 0);
    if ( !*(&xmmword_1800AE3F0 + 1) )
    {
      v12 = GetLastError();
      v0 = v12;
      if ( v12 > 0 )
        v0 = (unsigned __int16)v12 | 0x80070000;
      v18 = HIWORD(v0);
      if ( v0 >= 0 )
        goto LABEL_101;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_101;
      }
      v5 = 232;
LABEL_20:
      v6 = (unsigned int)v0;
LABEL_21:
      WPP_SF_d(v4[2], v5, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v6);
      goto LABEL_101;
    }
  }
  v13 = NatSetupUpgradeInitialize();
  if ( v13 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      233,
      &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      (unsigned int)v13);
  }
  v14 = ICSRpcServerInitialize();
  if ( v14 )
  {
    if ( v14 > 0 )
      v0 = (unsigned __int16)v14 | 0x80070000;
    else
      v0 = v14;
    v18 = HIWORD(v0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        234,
        &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
        (unsigned int)v14,
        v0);
    }
    goto LABEL_101;
  }
  ServiceStatus.dwControlsAccepted = 0;
  v15 = NatServiceChangeState(4u, 0);
  v18 = HIWORD(v15);
  v0 = v15;
  if ( v15 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_101;
    }
    v5 = 235;
    v6 = (unsigned int)v15;
    goto LABEL_21;
  }
  ServiceStatus.dwControlsAccepted = 1;
  v16 = NatServiceChangeState(4u, 1);
  v18 = HIWORD(v16);
  v0 = v16;
  if ( v16 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      236,
      &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      (unsigned int)v16);
  }
  if ( v19 || !(unsigned int)GetEnableRebootPersistConnection() )
    goto LABEL_102;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  updated = IpNatHlpRpcServerUpdateSharingSettingsFromStorage(0);
  if ( !updated )
  {
LABEL_102:
    NatSetInitializationState(1);
    goto LABEL_103;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 238, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, updated);
  }
LABEL_101:
  NatSetInitializationFailure(v1 == 0);
LABEL_103:
  if ( v0 < 0 )
  {
    LOWORD(ServiceStatus.dwWin32ExitCode) = v0;
    HIWORD(ServiceStatus.dwWin32ExitCode) = v18;
    if ( (v0 & 0x1FFF0000) == 0x70000 )
      HIWORD(ServiceStatus.dwWin32ExitCode) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
}

```

## disassembly

```asm
0x180021fb8  mov     [rsp+arg_10], rbx
0x180021fbd  push    rbp
0x180021fbe  push    rsi
0x180021fbf  push    r12
0x180021fc1  push    r13
0x180021fc3  push    r15
0x180021fc5  sub     rsp, 40h
0x180021fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fd0  lea     r12, WPP_GLOBAL_Control
0x180021fd7  lea     r13, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180021fde  mov     r15d, 200h
0x180021fe4  cmp     rcx, r12
0x180021fe7  jz      short loc_180022006
0x180021fe9  test    [rcx+1Ch], r15d
0x180021fed  jz      short loc_180022006
0x180021fef  cmp     byte ptr [rcx+19h], 6
0x180021ff3  jb      short loc_180022006
0x180021ff5  mov     rcx, [rcx+10h]
0x180021ff9  mov     edx, 0E1h
0x180021ffe  mov     r8, r13
0x180022001  call    WPP_SF_
0x180022006  xor     ebx, ebx
0x180022008  lea     rcx, [rsp+68h+arg_8]; int *
0x18002200d  mov     [rsp+68h+arg_0], ebx
0x180022011  xor     ebp, ebp
0x180022013  mov     [rsp+68h+arg_8], ebx
0x180022017  call    ?NatServiceShouldStop@@YAHPEAH@Z; NatServiceShouldStop(int *)
0x18002201c  test    eax, eax
0x18002201e  jz      short loc_180022053
0x180022020  mov     rcx, cs:WPP_GLOBAL_Control
0x180022027  cmp     rcx, r12
0x18002202a  jz      short loc_180022049
0x18002202c  test    [rcx+1Ch], r15d
0x180022030  jz      short loc_180022049
0x180022032  cmp     byte ptr [rcx+19h], 5
0x180022036  jb      short loc_180022049
0x180022038  mov     rcx, [rcx+10h]
0x18002203c  mov     edx, 0E2h
0x180022041  mov     r8, r13
0x180022044  call    WPP_SF_
0x180022049  call    ?SetServiceStartupTypeToManual@@YAXXZ; SetServiceStartupTypeToManual(void)
0x18002204e  jmp     loc_180022511
0x180022053  call    ?ClearPersistentDhcpExceptions@@YAXXZ; ClearPersistentDhcpExceptions(void)
0x180022058  mov     rcx, cs:?g_FirewallExceptionBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18002205f  mov     edx, 1; fCancelPendingCallbacks
0x180022064  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002206b  nop     dword ptr [rax+rax+00h]
0x180022070  mov     rcx, cs:?g_FirewallExceptionBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x180022077  call    cs:__imp_SubmitThreadpoolWork
0x18002207e  nop     dword ptr [rax+rax+00h]
0x180022083  cmp     cs:hObject, rbx
0x18002208a  jnz     loc_18002219B
0x180022090  xor     r9d, r9d; lpName
0x180022093  xor     r8d, r8d; bInitialState
0x180022096  xor     edx, edx; bManualReset
0x180022098  xor     ecx, ecx; lpEventAttributes
0x18002209a  call    cs:__imp_CreateEventW
0x1800220a1  nop     dword ptr [rax+rax+00h]
0x1800220a6  mov     cs:hObject, rax
0x1800220ad  test    rax, rax
0x1800220b0  jnz     short loc_180022116
0x1800220b2  call    cs:__imp_GetLastError
0x1800220b9  nop     dword ptr [rax+rax+00h]
0x1800220be  mov     ebx, eax
0x1800220c0  test    eax, eax
0x1800220c2  jle     short loc_1800220CD
0x1800220c4  movzx   ebx, ax
0x1800220c7  or      ebx, 80070000h
0x1800220cd  mov     [rsp+68h+arg_0], ebx
0x1800220d1  test    ebx, ebx
0x1800220d3  jns     loc_180022511
0x1800220d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220e0  cmp     rcx, r12
0x1800220e3  jz      loc_180022511
0x1800220e9  test    [rcx+1Ch], r15d
0x1800220ed  jz      loc_180022511
0x1800220f3  cmp     byte ptr [rcx+19h], 2
0x1800220f7  jb      loc_180022511
0x1800220fd  mov     edx, 0E3h
0x180022102  mov     r9d, ebx
0x180022105  mov     rcx, [rcx+10h]
0x180022109  mov     r8, r13
0x18002210c  call    WPP_SF_d
0x180022111  jmp     loc_180022511
0x180022116  mov     [rsp+68h+dwFlags], ebx; dwFlags
0x18002211a  lea     r8, ?NatServiceOnControl@@YAXPEAXE@Z; Callback
0x180022121  xor     r9d, r9d; Context
0x180022124  mov     [rsp+68h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18002212c  mov     rdx, rax; hObject
0x18002212f  lea     rcx, WaitHandle; phNewWaitObject
0x180022136  call    cs:__imp_RegisterWaitForSingleObject
0x18002213d  nop     dword ptr [rax+rax+00h]
0x180022142  test    eax, eax
0x180022144  jnz     short loc_18002219B
0x180022146  call    cs:__imp_GetLastError
0x18002214d  nop     dword ptr [rax+rax+00h]
0x180022152  mov     ebx, eax
0x180022154  test    eax, eax
0x180022156  jle     short loc_180022161
0x180022158  movzx   ebx, ax
0x18002215b  or      ebx, 80070000h
0x180022161  mov     [rsp+68h+arg_0], ebx
0x180022165  test    ebx, ebx
0x180022167  jns     loc_180022511
0x18002216d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022174  cmp     rcx, r12
0x180022177  jz      loc_180022511
0x18002217d  test    [rcx+1Ch], r15d
0x180022181  jz      loc_180022511
0x180022187  cmp     byte ptr [rcx+19h], 2
0x18002218b  jb      loc_180022511
0x180022191  mov     edx, 0E4h
0x180022196  jmp     loc_180022102
0x18002219b  mov     rcx, qword ptr cs:WaitHandle+8; hEvent
0x1800221a2  mov     esi, 80070000h
0x1800221a7  test    rcx, rcx
0x1800221aa  jnz     loc_1800222E2
0x1800221b0  xor     r9d, r9d; lpName
0x1800221b3  lea     edx, [rcx+1]; bManualReset
0x1800221b6  xor     r8d, r8d; bInitialState
0x1800221b9  call    cs:__imp_CreateEventW
0x1800221c0  nop     dword ptr [rax+rax+00h]
0x1800221c5  mov     qword ptr cs:WaitHandle+8, rax
0x1800221cc  mov     r8, rax
0x1800221cf  test    rax, rax
0x1800221d2  jnz     short loc_180022225
0x1800221d4  call    cs:__imp_GetLastError
0x1800221db  nop     dword ptr [rax+rax+00h]
0x1800221e0  mov     ebx, eax
0x1800221e2  test    eax, eax
0x1800221e4  jle     short loc_1800221EB
0x1800221e6  movzx   ebx, ax
0x1800221e9  or      ebx, esi
0x1800221eb  mov     [rsp+68h+arg_0], ebx
0x1800221ef  test    ebx, ebx
0x1800221f1  jns     loc_180022511
0x1800221f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221fe  cmp     rcx, r12
0x180022201  jz      loc_180022511
0x180022207  test    [rcx+1Ch], r15d
0x18002220b  jz      loc_180022511
0x180022211  cmp     byte ptr [rcx+19h], 2
0x180022215  jb      loc_180022511
0x18002221b  mov     edx, 0E5h
0x180022220  jmp     loc_180022102
0x180022225  mov     rax, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x18002222c  test    rax, rax
0x18002222f  jz      short loc_180022298
0x180022231  mov     rax, [rax+0C0h]
0x180022238  lea     r9, ?StopServiceCallback@@YAXPEAXE@Z; StopServiceCallback(void *,uchar)
0x18002223f  mov     [rsp+68h+dwFlags], 8
0x180022247  lea     rdx, aSharedaccess; "SharedAccess"
0x18002224e  lea     rcx, xmmword_1800AE3F0
0x180022255  mov     qword ptr [rsp+68h+dwMilliseconds], rbx
0x18002225a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002225f  test    eax, eax
0x180022261  jz      short loc_180022291
0x180022263  jg      short loc_180022269
0x180022265  mov     ebx, eax
0x180022267  jmp     short loc_18002226E
0x180022269  movzx   ebx, ax
0x18002226c  or      ebx, esi
0x18002226e  mov     [rsp+68h+arg_0], ebx
0x180022272  mov     rcx, cs:WPP_GLOBAL_Control
0x180022279  cmp     rcx, r12
0x18002227c  jz      short loc_1800222D9
0x18002227e  test    [rcx+1Ch], r15d
0x180022282  jz      short loc_1800222D9
0x180022284  cmp     byte ptr [rcx+19h], 2
0x180022288  jb      short loc_1800222D9
0x18002228a  mov     edx, 0E6h
0x18002228f  jmp     short loc_1800222CA
0x180022291  mov     ebp, 1
0x180022296  jmp     short loc_1800222D9
0x180022298  mov     ebx, 80004005h
0x18002229d  mov     [rsp+68h+arg_0], ebx
0x1800222a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222a8  cmp     rcx, r12
0x1800222ab  jz      loc_180022511
0x1800222b1  test    [rcx+1Ch], r15d
0x1800222b5  jz      loc_180022511
0x1800222bb  cmp     byte ptr [rcx+19h], 2
0x1800222bf  jb      loc_180022511
0x1800222c5  mov     edx, 0E7h
0x1800222ca  mov     rcx, [rcx+10h]
0x1800222ce  mov     r9d, ebx
0x1800222d1  mov     r8, r13
0x1800222d4  call    WPP_SF_d
0x1800222d9  test    ebx, ebx
0x1800222db  jns     short loc_1800222EE
0x1800222dd  jmp     loc_180022511
0x1800222e2  call    cs:__imp_ResetEvent
0x1800222e9  nop     dword ptr [rax+rax+00h]
0x1800222ee  mov     rcx, qword ptr cs:xmmword_1800AE3F0+8; hEvent
0x1800222f5  test    rcx, rcx
0x1800222f8  jnz     short loc_18002236C
0x1800222fa  xor     r9d, r9d; lpName
0x1800222fd  lea     edx, [rcx+1]; bManualReset
0x180022300  xor     r8d, r8d; bInitialState
0x180022303  call    cs:__imp_CreateEventW
0x18002230a  nop     dword ptr [rax+rax+00h]
0x18002230f  mov     qword ptr cs:xmmword_1800AE3F0+8, rax
0x180022316  test    rax, rax
0x180022319  jnz     short loc_180022378
0x18002231b  call    cs:__imp_GetLastError
0x180022322  nop     dword ptr [rax+rax+00h]
0x180022327  mov     ebx, eax
0x180022329  test    eax, eax
0x18002232b  jle     short loc_180022332
0x18002232d  movzx   ebx, ax
0x180022330  or      ebx, esi
0x180022332  mov     [rsp+68h+arg_0], ebx
0x180022336  test    ebx, ebx
0x180022338  jns     loc_180022511
0x18002233e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022345  cmp     rcx, r12
0x180022348  jz      loc_180022511
0x18002234e  test    [rcx+1Ch], r15d
0x180022352  jz      loc_180022511
0x180022358  cmp     byte ptr [rcx+19h], 2
0x18002235c  jb      loc_180022511
0x180022362  mov     edx, 0E8h
0x180022367  jmp     loc_180022102
0x18002236c  call    cs:__imp_ResetEvent
0x180022373  nop     dword ptr [rax+rax+00h]
0x180022378  call    NatSetupUpgradeInitialize
0x18002237d  test    eax, eax
0x18002237f  jns     short loc_1800223AD
0x180022381  mov     rcx, cs:WPP_GLOBAL_Control
0x180022388  cmp     rcx, r12
0x18002238b  jz      short loc_1800223AD
0x18002238d  test    [rcx+1Ch], r15d
0x180022391  jz      short loc_1800223AD
0x180022393  cmp     byte ptr [rcx+19h], 3
0x180022397  jb      short loc_1800223AD
0x180022399  mov     rcx, [rcx+10h]
0x18002239d  mov     edx, 0E9h
0x1800223a2  mov     r9d, eax
0x1800223a5  mov     r8, r13
0x1800223a8  call    WPP_SF_d
0x1800223ad  call    ?ICSRpcServerInitialize@@YAKXZ; ICSRpcServerInitialize(void)
0x1800223b2  test    eax, eax
0x1800223b4  jz      short loc_180022406
0x1800223b6  jg      short loc_1800223BC
0x1800223b8  mov     ebx, eax
0x1800223ba  jmp     short loc_1800223C1
0x1800223bc  movzx   ebx, ax
0x1800223bf  or      ebx, esi
0x1800223c1  mov     [rsp+68h+arg_0], ebx
0x1800223c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223cc  cmp     rcx, r12
0x1800223cf  jz      loc_180022511
0x1800223d5  test    [rcx+1Ch], r15d
0x1800223d9  jz      loc_180022511
0x1800223df  cmp     byte ptr [rcx+19h], 2
0x1800223e3  jb      loc_180022511
0x1800223e9  mov     rcx, [rcx+10h]
0x1800223ed  mov     edx, 0EAh
0x1800223f2  mov     r9d, eax
0x1800223f5  mov     [rsp+68h+dwMilliseconds], ebx
0x1800223f9  mov     r8, r13
0x1800223fc  call    WPP_SF_Dd
0x180022401  jmp     loc_180022511
0x180022406  xor     edx, edx; bool
0x180022408  mov     cs:ServiceStatus.dwControlsAccepted, 0
0x180022412  lea     ecx, [rdx+4]; unsigned int
0x180022415  call    ?NatServiceChangeState@@YAJK_N@Z; NatServiceChangeState(ulong,bool)
0x18002241a  mov     [rsp+68h+arg_0], eax
0x18002241e  mov     ebx, eax
0x180022420  test    eax, eax
0x180022422  jns     short loc_180022455
0x180022424  mov     rcx, cs:WPP_GLOBAL_Control
0x18002242b  cmp     rcx, r12
0x18002242e  jz      loc_180022511
0x180022434  test    [rcx+1Ch], r15d
0x180022438  jz      loc_180022511
0x18002243e  cmp     byte ptr [rcx+19h], 2
0x180022442  jb      loc_180022511
0x180022448  mov     edx, 0EBh
0x18002244d  mov     r9d, eax
0x180022450  jmp     loc_180022105
0x180022455  mov     esi, 1
0x18002245a  mov     dl, sil; bool
0x18002245d  mov     cs:ServiceStatus.dwControlsAccepted, esi
0x180022463  lea     ecx, [rsi+3]; unsigned int
0x180022466  call    ?NatServiceChangeState@@YAJK_N@Z; NatServiceChangeState(ulong,bool)
0x18002246b  mov     [rsp+68h+arg_0], eax
0x18002246f  mov     ebx, eax
0x180022471  test    eax, eax
0x180022473  jns     short loc_1800224A1
0x180022475  mov     rcx, cs:WPP_GLOBAL_Control
0x18002247c  cmp     rcx, r12
0x18002247f  jz      short loc_1800224A1
0x180022481  test    [rcx+1Ch], r15d
0x180022485  jz      short loc_1800224A1
0x180022487  cmp     byte ptr [rcx+19h], 2
0x18002248b  jb      short loc_1800224A1
0x18002248d  mov     rcx, [rcx+10h]
0x180022491  mov     edx, 0ECh
0x180022496  mov     r9d, eax
  ... truncated ...
```
