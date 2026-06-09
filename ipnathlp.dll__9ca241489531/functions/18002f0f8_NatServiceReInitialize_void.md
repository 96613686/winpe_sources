# NatServiceReInitialize(void)

- ea: `0x18002f0f8`
- end: `0x18002f68a`
- name: `?NatServiceReInitialize@@YAXXZ`
- size: `1426`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002eca0`
- `0x18003eee0`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18001ec08`
- `0x18002ee44`
- `0x18002f0f8`
- `0x18002f690`
- `0x18002f7ac`
- `0x18002fa90`
- `0x18002fb44`
- `0x18003b1e0`
- `0x18003eca4`
- `0x18006f0cc`
- `0x18006f22c`
- `0x1800710f8`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f1ce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f2d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f40d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f1ce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f2d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f40d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f3f2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f46a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f3f2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f46a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f41f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f41f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002f1a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002f1a4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002f1b1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002f1b1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18002f25e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18002f25e`

## string_xrefs

- `0x18002f357`: `SharedAccess`

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
         &xmmword_1800A7330,
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
  if ( *(&xmmword_1800A7330 + 1) )
  {
    ResetEvent(*(&xmmword_1800A7330 + 1));
  }
  else
  {
    *(&xmmword_1800A7330 + 1) = CreateEventW(0, 1, 0, 0);
    if ( !*(&xmmword_1800A7330 + 1) )
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
0x18002f0f8  mov     [rsp+arg_10], rbx
0x18002f0fd  push    rbp
0x18002f0fe  push    rsi
0x18002f0ff  push    r12
0x18002f101  push    r13
0x18002f103  push    r15
0x18002f105  sub     rsp, 40h
0x18002f109  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f110  lea     r12, WPP_GLOBAL_Control
0x18002f117  lea     r13, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18002f11e  mov     r15d, 200h
0x18002f124  cmp     rcx, r12
0x18002f127  jz      short loc_18002F146
0x18002f129  test    [rcx+1Ch], r15d
0x18002f12d  jz      short loc_18002F146
0x18002f12f  cmp     byte ptr [rcx+19h], 6
0x18002f133  jb      short loc_18002F146
0x18002f135  mov     rcx, [rcx+10h]
0x18002f139  mov     edx, 0E1h
0x18002f13e  mov     r8, r13
0x18002f141  call    WPP_SF_
0x18002f146  xor     ebx, ebx
0x18002f148  lea     rcx, [rsp+68h+arg_8]; int *
0x18002f14d  mov     [rsp+68h+arg_0], ebx
0x18002f151  xor     ebp, ebp
0x18002f153  mov     [rsp+68h+arg_8], ebx
0x18002f157  call    ?NatServiceShouldStop@@YAHPEAH@Z; NatServiceShouldStop(int *)
0x18002f15c  test    eax, eax
0x18002f15e  jz      short loc_18002F193
0x18002f160  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f167  cmp     rcx, r12
0x18002f16a  jz      short loc_18002F189
0x18002f16c  test    [rcx+1Ch], r15d
0x18002f170  jz      short loc_18002F189
0x18002f172  cmp     byte ptr [rcx+19h], 5
0x18002f176  jb      short loc_18002F189
0x18002f178  mov     rcx, [rcx+10h]
0x18002f17c  mov     edx, 0E2h
0x18002f181  mov     r8, r13
0x18002f184  call    WPP_SF_
0x18002f189  call    ?SetServiceStartupTypeToManual@@YAXXZ; SetServiceStartupTypeToManual(void)
0x18002f18e  jmp     loc_18002F609
0x18002f193  call    ?ClearPersistentDhcpExceptions@@YAXXZ; ClearPersistentDhcpExceptions(void)
0x18002f198  mov     rcx, cs:?g_FirewallExceptionBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18002f19f  mov     edx, 1; fCancelPendingCallbacks
0x18002f1a4  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002f1aa  mov     rcx, cs:?g_FirewallExceptionBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18002f1b1  call    cs:__imp_SubmitThreadpoolWork
0x18002f1b7  cmp     cs:hObject, rbx
0x18002f1be  jnz     loc_18002F2B7
0x18002f1c4  xor     r9d, r9d; lpName
0x18002f1c7  xor     r8d, r8d; bInitialState
0x18002f1ca  xor     edx, edx; bManualReset
0x18002f1cc  xor     ecx, ecx; lpEventAttributes
0x18002f1ce  call    cs:__imp_CreateEventW
0x18002f1d4  mov     cs:hObject, rax
0x18002f1db  test    rax, rax
0x18002f1de  jnz     short loc_18002F23E
0x18002f1e0  call    cs:__imp_GetLastError
0x18002f1e6  mov     ebx, eax
0x18002f1e8  test    eax, eax
0x18002f1ea  jle     short loc_18002F1F5
0x18002f1ec  movzx   ebx, ax
0x18002f1ef  or      ebx, 80070000h
0x18002f1f5  mov     [rsp+68h+arg_0], ebx
0x18002f1f9  test    ebx, ebx
0x18002f1fb  jns     loc_18002F609
0x18002f201  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f208  cmp     rcx, r12
0x18002f20b  jz      loc_18002F609
0x18002f211  test    [rcx+1Ch], r15d
0x18002f215  jz      loc_18002F609
0x18002f21b  cmp     byte ptr [rcx+19h], 2
0x18002f21f  jb      loc_18002F609
0x18002f225  mov     edx, 0E3h
0x18002f22a  mov     r9d, ebx
0x18002f22d  mov     rcx, [rcx+10h]
0x18002f231  mov     r8, r13
0x18002f234  call    WPP_SF_d
0x18002f239  jmp     loc_18002F609
0x18002f23e  mov     [rsp+68h+dwFlags], ebx; dwFlags
0x18002f242  lea     r8, ?NatServiceOnControl@@YAXPEAXE@Z; Callback
0x18002f249  xor     r9d, r9d; Context
0x18002f24c  mov     [rsp+68h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18002f254  mov     rdx, rax; hObject
0x18002f257  lea     rcx, WaitHandle; phNewWaitObject
0x18002f25e  call    cs:__imp_RegisterWaitForSingleObject
0x18002f264  test    eax, eax
0x18002f266  jnz     short loc_18002F2B7
0x18002f268  call    cs:__imp_GetLastError
0x18002f26e  mov     ebx, eax
0x18002f270  test    eax, eax
0x18002f272  jle     short loc_18002F27D
0x18002f274  movzx   ebx, ax
0x18002f277  or      ebx, 80070000h
0x18002f27d  mov     [rsp+68h+arg_0], ebx
0x18002f281  test    ebx, ebx
0x18002f283  jns     loc_18002F609
0x18002f289  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f290  cmp     rcx, r12
0x18002f293  jz      loc_18002F609
0x18002f299  test    [rcx+1Ch], r15d
0x18002f29d  jz      loc_18002F609
0x18002f2a3  cmp     byte ptr [rcx+19h], 2
0x18002f2a7  jb      loc_18002F609
0x18002f2ad  mov     edx, 0E4h
0x18002f2b2  jmp     loc_18002F22A
0x18002f2b7  mov     rcx, qword ptr cs:WaitHandle+8; hEvent
0x18002f2be  mov     esi, 80070000h
0x18002f2c3  test    rcx, rcx
0x18002f2c6  jnz     loc_18002F3F2
0x18002f2cc  xor     r9d, r9d; lpName
0x18002f2cf  lea     edx, [rcx+1]; bManualReset
0x18002f2d2  xor     r8d, r8d; bInitialState
0x18002f2d5  call    cs:__imp_CreateEventW
0x18002f2db  mov     qword ptr cs:WaitHandle+8, rax
0x18002f2e2  mov     r8, rax
0x18002f2e5  test    rax, rax
0x18002f2e8  jnz     short loc_18002F335
0x18002f2ea  call    cs:__imp_GetLastError
0x18002f2f0  mov     ebx, eax
0x18002f2f2  test    eax, eax
0x18002f2f4  jle     short loc_18002F2FB
0x18002f2f6  movzx   ebx, ax
0x18002f2f9  or      ebx, esi
0x18002f2fb  mov     [rsp+68h+arg_0], ebx
0x18002f2ff  test    ebx, ebx
0x18002f301  jns     loc_18002F609
0x18002f307  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f30e  cmp     rcx, r12
0x18002f311  jz      loc_18002F609
0x18002f317  test    [rcx+1Ch], r15d
0x18002f31b  jz      loc_18002F609
0x18002f321  cmp     byte ptr [rcx+19h], 2
0x18002f325  jb      loc_18002F609
0x18002f32b  mov     edx, 0E5h
0x18002f330  jmp     loc_18002F22A
0x18002f335  mov     rax, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x18002f33c  test    rax, rax
0x18002f33f  jz      short loc_18002F3A8
0x18002f341  mov     rax, [rax+0C0h]
0x18002f348  lea     r9, ?StopServiceCallback@@YAXPEAXE@Z; StopServiceCallback(void *,uchar)
0x18002f34f  mov     [rsp+68h+dwFlags], 8
0x18002f357  lea     rdx, aSharedaccess; "SharedAccess"
0x18002f35e  lea     rcx, xmmword_1800A7330
0x18002f365  mov     qword ptr [rsp+68h+dwMilliseconds], rbx
0x18002f36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f36f  test    eax, eax
0x18002f371  jz      short loc_18002F3A1
0x18002f373  jg      short loc_18002F379
0x18002f375  mov     ebx, eax
0x18002f377  jmp     short loc_18002F37E
0x18002f379  movzx   ebx, ax
0x18002f37c  or      ebx, esi
0x18002f37e  mov     [rsp+68h+arg_0], ebx
0x18002f382  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f389  cmp     rcx, r12
0x18002f38c  jz      short loc_18002F3E9
0x18002f38e  test    [rcx+1Ch], r15d
0x18002f392  jz      short loc_18002F3E9
0x18002f394  cmp     byte ptr [rcx+19h], 2
0x18002f398  jb      short loc_18002F3E9
0x18002f39a  mov     edx, 0E6h
0x18002f39f  jmp     short loc_18002F3DA
0x18002f3a1  mov     ebp, 1
0x18002f3a6  jmp     short loc_18002F3E9
0x18002f3a8  mov     ebx, 80004005h
0x18002f3ad  mov     [rsp+68h+arg_0], ebx
0x18002f3b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f3b8  cmp     rcx, r12
0x18002f3bb  jz      loc_18002F609
0x18002f3c1  test    [rcx+1Ch], r15d
0x18002f3c5  jz      loc_18002F609
0x18002f3cb  cmp     byte ptr [rcx+19h], 2
0x18002f3cf  jb      loc_18002F609
0x18002f3d5  mov     edx, 0E7h
0x18002f3da  mov     rcx, [rcx+10h]
0x18002f3de  mov     r9d, ebx
0x18002f3e1  mov     r8, r13
0x18002f3e4  call    WPP_SF_d
0x18002f3e9  test    ebx, ebx
0x18002f3eb  jns     short loc_18002F3F8
0x18002f3ed  jmp     loc_18002F609
0x18002f3f2  call    cs:__imp_ResetEvent
0x18002f3f8  mov     rcx, qword ptr cs:xmmword_1800A7330+8; hEvent
0x18002f3ff  test    rcx, rcx
0x18002f402  jnz     short loc_18002F46A
0x18002f404  xor     r9d, r9d; lpName
0x18002f407  lea     edx, [rcx+1]; bManualReset
0x18002f40a  xor     r8d, r8d; bInitialState
0x18002f40d  call    cs:__imp_CreateEventW
0x18002f413  mov     qword ptr cs:xmmword_1800A7330+8, rax
0x18002f41a  test    rax, rax
0x18002f41d  jnz     short loc_18002F470
0x18002f41f  call    cs:__imp_GetLastError
0x18002f425  mov     ebx, eax
0x18002f427  test    eax, eax
0x18002f429  jle     short loc_18002F430
0x18002f42b  movzx   ebx, ax
0x18002f42e  or      ebx, esi
0x18002f430  mov     [rsp+68h+arg_0], ebx
0x18002f434  test    ebx, ebx
0x18002f436  jns     loc_18002F609
0x18002f43c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f443  cmp     rcx, r12
0x18002f446  jz      loc_18002F609
0x18002f44c  test    [rcx+1Ch], r15d
0x18002f450  jz      loc_18002F609
0x18002f456  cmp     byte ptr [rcx+19h], 2
0x18002f45a  jb      loc_18002F609
0x18002f460  mov     edx, 0E8h
0x18002f465  jmp     loc_18002F22A
0x18002f46a  call    cs:__imp_ResetEvent
0x18002f470  call    NatSetupUpgradeInitialize
0x18002f475  test    eax, eax
0x18002f477  jns     short loc_18002F4A5
0x18002f479  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f480  cmp     rcx, r12
0x18002f483  jz      short loc_18002F4A5
0x18002f485  test    [rcx+1Ch], r15d
0x18002f489  jz      short loc_18002F4A5
0x18002f48b  cmp     byte ptr [rcx+19h], 3
0x18002f48f  jb      short loc_18002F4A5
0x18002f491  mov     rcx, [rcx+10h]
0x18002f495  mov     edx, 0E9h
0x18002f49a  mov     r9d, eax
0x18002f49d  mov     r8, r13
0x18002f4a0  call    WPP_SF_d
0x18002f4a5  call    ?ICSRpcServerInitialize@@YAKXZ; ICSRpcServerInitialize(void)
0x18002f4aa  test    eax, eax
0x18002f4ac  jz      short loc_18002F4FE
0x18002f4ae  jg      short loc_18002F4B4
0x18002f4b0  mov     ebx, eax
0x18002f4b2  jmp     short loc_18002F4B9
0x18002f4b4  movzx   ebx, ax
0x18002f4b7  or      ebx, esi
0x18002f4b9  mov     [rsp+68h+arg_0], ebx
0x18002f4bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4c4  cmp     rcx, r12
0x18002f4c7  jz      loc_18002F609
0x18002f4cd  test    [rcx+1Ch], r15d
0x18002f4d1  jz      loc_18002F609
0x18002f4d7  cmp     byte ptr [rcx+19h], 2
0x18002f4db  jb      loc_18002F609
0x18002f4e1  mov     rcx, [rcx+10h]
0x18002f4e5  mov     edx, 0EAh
0x18002f4ea  mov     r9d, eax
0x18002f4ed  mov     [rsp+68h+dwMilliseconds], ebx
0x18002f4f1  mov     r8, r13
0x18002f4f4  call    WPP_SF_Dd
0x18002f4f9  jmp     loc_18002F609
0x18002f4fe  xor     edx, edx; bool
0x18002f500  mov     cs:ServiceStatus.dwControlsAccepted, 0
0x18002f50a  lea     ecx, [rdx+4]; unsigned int
0x18002f50d  call    ?NatServiceChangeState@@YAJK_N@Z; NatServiceChangeState(ulong,bool)
0x18002f512  mov     [rsp+68h+arg_0], eax
0x18002f516  mov     ebx, eax
0x18002f518  test    eax, eax
0x18002f51a  jns     short loc_18002F54D
0x18002f51c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f523  cmp     rcx, r12
0x18002f526  jz      loc_18002F609
0x18002f52c  test    [rcx+1Ch], r15d
0x18002f530  jz      loc_18002F609
0x18002f536  cmp     byte ptr [rcx+19h], 2
0x18002f53a  jb      loc_18002F609
0x18002f540  mov     edx, 0EBh
0x18002f545  mov     r9d, eax
0x18002f548  jmp     loc_18002F22D
0x18002f54d  mov     esi, 1
0x18002f552  mov     dl, sil; bool
0x18002f555  mov     cs:ServiceStatus.dwControlsAccepted, esi
0x18002f55b  lea     ecx, [rsi+3]; unsigned int
0x18002f55e  call    ?NatServiceChangeState@@YAJK_N@Z; NatServiceChangeState(ulong,bool)
0x18002f563  mov     [rsp+68h+arg_0], eax
0x18002f567  mov     ebx, eax
0x18002f569  test    eax, eax
0x18002f56b  jns     short loc_18002F599
0x18002f56d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f574  cmp     rcx, r12
0x18002f577  jz      short loc_18002F599
0x18002f579  test    [rcx+1Ch], r15d
0x18002f57d  jz      short loc_18002F599
0x18002f57f  cmp     byte ptr [rcx+19h], 2
0x18002f583  jb      short loc_18002F599
0x18002f585  mov     rcx, [rcx+10h]
0x18002f589  mov     edx, 0ECh
0x18002f58e  mov     r9d, eax
0x18002f591  mov     r8, r13
0x18002f594  call    WPP_SF_d
0x18002f599  cmp     [rsp+68h+arg_8], 0
0x18002f59e  jnz     short loc_18002F617
0x18002f5a0  call    ?GetEnableRebootPersistConnection@@YAHXZ; GetEnableRebootPersistConnection(void)
0x18002f5a5  test    eax, eax
0x18002f5a7  jz      short loc_18002F617
0x18002f5a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5b0  cmp     rcx, r12
0x18002f5b3  jz      short loc_18002F5D2
0x18002f5b5  test    [rcx+1Ch], r15d
0x18002f5b9  jz      short loc_18002F5D2
  ... truncated ...
```
