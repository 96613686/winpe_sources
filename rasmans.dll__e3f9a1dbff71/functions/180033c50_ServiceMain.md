# ServiceMain

- ea: `0x180033c50`
- end: `0x180034264`
- name: `ServiceMain`
- size: `1556`
- prototype: `int __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180005e74`
- `0x18000aa60`
- `0x18000be30`
- `0x18000c00c`
- `0x18000cdc4`
- `0x18000e6c8`
- `0x180028cd0`
- `0x180032f4c`
- `0x180033c50`
- `0x1800de2d8`
- `0x1800df9c0`
- `0x1800e7260`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034021`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034021`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180033f4d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180033f4d`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerSetFlags` at `0x180033ccd`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerSetFlags` at `0x180033ccd`
- `rtutils!RouterLogEventStringA` at `0x18003400c`
- `rtutils!RouterLogEventStringA` at `0x18003400c`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerExA` at `0x180033cfa`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerExA` at `0x180033cfa`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180033d6e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180034079`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800341e7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180033d6e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180034079`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800341e7`

## string_xrefs

- `0x180033f40`: `GDI32.DLL`

## pseudocode

```c
int __fastcall ServiceMain(unsigned int a1)
{
  SERVICE_STATUS_HANDLE v1; // rax
  struct _LIST_ENTRY *v2; // rcx
  struct _LIST_ENTRY *Flink; // rbx
  DWORD LastError; // eax
  DWORD dwErrorCode; // edi
  DWORD v6; // eax
  unsigned int v7; // esi
  unsigned __int64 v8; // rbx
  DWORD v9; // eax
  unsigned int v10; // eax
  int v11; // esi
  HMODULE Library; // rax
  struct _LIST_ENTRY *v13; // rbx
  DWORD v14; // eax
  FARPROC ProcAddress; // rax
  unsigned int v16; // eax
  struct _LIST_ENTRY *v17; // rcx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[1].Flink, 53, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, a1, dwCurrentState);
  }
  WerSetFlags(2u);
  ServiceStatus.dwServiceType = 32;
  memset(&ServiceStatus.dwCurrentState, 0, 24);
  v1 = RegisterServiceCtrlHandlerExA("rasman", ServiceHandlerEx, 0);
  hService = v1;
  if ( !v1 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        Flink = WPP_GLOBAL_Control[1].Flink;
        LastError = GetLastError();
        LODWORD(v1) = WPP_SF_d(Flink, 54, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, LastError);
        goto LABEL_90;
      }
      goto LABEL_91;
    }
    return (int)v1;
  }
  dwCurrentState = 2;
  ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwWaitHint = 180000;
  SetServiceStatus(v1, &ServiceStatus);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 55, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
  }
  if ( (unsigned int)GetModernStackStatus() )
  {
    dwErrorCode = 711;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x800) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 56, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, 711);
      v2 = WPP_GLOBAL_Control;
    }
    goto LABEL_83;
  }
  v6 = RasmanInit();
  dwErrorCode = v6;
  if ( v6 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
LABEL_82:
      if ( dwErrorCode < 0x258 )
      {
        ServiceStatus.dwWin32ExitCode = dwErrorCode;
        ServiceStatus.dwServiceSpecificExitCode = 0;
        goto LABEL_85;
      }
LABEL_83:
      ServiceStatus.dwWin32ExitCode = 1066;
      ServiceStatus.dwServiceSpecificExitCode = dwErrorCode;
      goto LABEL_85;
    }
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 57, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, v6);
LABEL_81:
    v2 = WPP_GLOBAL_Control;
    goto LABEL_82;
  }
  v7 = 0;
  while ( 1 )
  {
    v8 = (unsigned __int64)v7 << 6;
    if ( !*(_DWORD *)((char *)&protocolEngine + v8 + 16) )
      break;
LABEL_32:
    if ( ++v7 >= 4 )
    {
      v10 = VpnProfileLibInitialize(hModule);
      if ( v10
        && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 60, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, v10);
      }
      v11 = 1;
      dwErrorCode = 0;
      goto LABEL_39;
    }
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control[1].Flink,
      58,
      (unsigned int)WPP_101c73712a933762328fe4f7a83f8625_Traceguids,
      (unsigned int)*(char **)((char *)&protocolEngine + v8),
      *(_DWORD *)((char *)&protocolEngine + v8 + 24));
  }
  v9 = (*(__int64 (__fastcall **)(HANDLE, _QWORD, __int64))((char *)&protocolEngine + v8 + 40))(
         hLogEvents,
         *(unsigned int *)((char *)&protocolEngine + v8 + 24),
         1);
  dwErrorCode = v9;
  if ( !v9 )
  {
    *(_DWORD *)((char *)&protocolEngine + v8 + 20) = 1;
    goto LABEL_32;
  }
  v11 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 59, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, v9);
  }
  RouterLogEventStringA(hLogEvents, 1u, 0x4E5Fu, 1u, (LPSTR *)((char *)&qword_18010A068 + v8), dwErrorCode, 0);
LABEL_39:
  if ( !g_RasMobileCore )
  {
    Library = LoadLibraryExA("GDI32.DLL", 0, 0x800u);
    g_hGdi32 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "DeviceCapabilitiesExA");
      g_pfnDeviceCapabilitiesExA = (__int64)ProcAddress;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v13 = WPP_GLOBAL_Control[1].Flink;
        v14 = GetLastError();
        WPP_SF_d(v13, 62, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, v14);
      }
      ProcAddress = (FARPROC)g_pfnDeviceCapabilitiesExA;
    }
    if ( ProcAddress )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(0, 0, 0, 0, 0, 0);
  }
  if ( dwErrorCode )
  {
    if ( v11 == 1 )
      VpnProfileLibShutdown();
    UninitializeProtocolEngines();
    RasmanCleanup();
    goto LABEL_81;
  }
  dwControlsAccepted = 4293;
  ServiceStatus.dwControlsAccepted = 4293;
  dwCurrentState = 4;
  ServiceStatus.dwCurrentState = 4;
  SetServiceStatus((SERVICE_STATUS_HANDLE)hService, &ServiceStatus);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 63, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
  }
  v16 = CheckModemState();
  if ( v16 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 64, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, v16);
      v17 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v17 = WPP_GLOBAL_Control;
  }
  if ( !g_fModemPresent && RastapiCheckRasmanDependency )
  {
    RastapiCheckRasmanDependency();
    v17 = WPP_GLOBAL_Control;
  }
  if ( v17 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v17[1].Blink) & 0x2000) != 0
    && BYTE1(v17[1].Blink) >= 6u )
  {
    WPP_SF_(v17[1].Flink, 13, WPP_7ba71f3b71eb31c5bb73738abca13a5c_Traceguids);
  }
  RequestThread(0);
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 14, WPP_7ba71f3b71eb31c5bb73738abca13a5c_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
LABEL_85:
  LODWORD(v1) = (_DWORD)hService;
  if ( !hService )
    goto LABEL_91;
  dwControlsAccepted = 0;
  dwCurrentState = 1;
  *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
  LODWORD(v1) = SetServiceStatus((SERVICE_STATUS_HANDLE)hService, &ServiceStatus);
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      LODWORD(v1) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 65, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
LABEL_90:
      v2 = WPP_GLOBAL_Control;
    }
LABEL_91:
    if ( v2 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v2[1].Blink) & 0x2000) != 0
      && BYTE1(v2[1].Blink) >= 6u )
    {
      LODWORD(v1) = WPP_SF_(v2[1].Flink, 66, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
    }
  }
  return (int)v1;
}

```

## disassembly

```asm
0x180033c50  push    rbp
0x180033c52  push    rbx
0x180033c53  push    rsi
0x180033c54  push    rdi
0x180033c55  push    r12
0x180033c57  push    r13
0x180033c59  push    r14
0x180033c5b  push    r15
0x180033c5d  mov     rbp, rsp
0x180033c60  sub     rsp, 78h
0x180033c64  mov     rax, cs:__security_cookie
0x180033c6b  xor     rax, rsp
0x180033c6e  mov     [rbp+var_18], rax
0x180033c72  mov     r9d, ecx
0x180033c75  mov     rcx, cs:WPP_GLOBAL_Control
0x180033c7c  lea     r15, WPP_GLOBAL_Control
0x180033c83  mov     r12d, 2000h
0x180033c89  cmp     rcx, r15
0x180033c8c  jz      short loc_180033CB9
0x180033c8e  test    [rcx+1Ch], r12d
0x180033c92  jz      short loc_180033CB9
0x180033c94  cmp     byte ptr [rcx+19h], 6
0x180033c98  jb      short loc_180033CB9
0x180033c9a  mov     eax, cs:dwCurrentState
0x180033ca0  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180033ca7  mov     rcx, [rcx+10h]
0x180033cab  mov     edx, 35h ; '5'
0x180033cb0  mov     dword ptr [rsp+78h+plpszSubStringArray], eax
0x180033cb4  call    WPP_SF_Dd
0x180033cb9  xorps   xmm0, xmm0
0x180033cbc  mov     r13d, 2
0x180033cc2  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x180033cc6  mov     ecx, r13d; dwFlags
0x180033cc9  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x180033ccd  call    cs:__imp_WerSetFlags
0x180033cd3  xorps   xmm0, xmm0
0x180033cd6  mov     [rbp+ServiceStatus.dwServiceType], 20h ; ' '
0x180033cdd  xor     r14d, r14d
0x180033ce0  lea     rdx, ServiceHandlerEx; lpHandlerProc
0x180033ce7  xor     r8d, r8d; lpContext
0x180033cea  mov     qword ptr [rbp+ServiceStatus.dwCheckPoint], r14
0x180033cee  lea     rcx, aRasman_1; "rasman"
0x180033cf5  movdqu  xmmword ptr [rbp+ServiceStatus.dwCurrentState], xmm0
0x180033cfa  call    cs:__imp_RegisterServiceCtrlHandlerExA
0x180033d00  mov     cs:hService, rax
0x180033d07  test    rax, rax
0x180033d0a  jnz     short loc_180033D55
0x180033d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d13  cmp     rcx, r15
0x180033d16  jz      loc_180034247
0x180033d1c  test    [rcx+1Ch], r12d
0x180033d20  jz      loc_180034221
0x180033d26  cmp     [rcx+19h], r13b
0x180033d2a  jb      loc_180034221
0x180033d30  mov     rbx, [rcx+10h]
0x180033d34  call    cs:__imp_GetLastError
0x180033d3a  lea     edx, [r13+34h]
0x180033d3e  mov     rcx, rbx
0x180033d41  mov     r9d, eax
0x180033d44  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180033d4b  call    WPP_SF_d
0x180033d50  jmp     loc_18003421A
0x180033d55  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x180033d59  mov     cs:dwCurrentState, r13d
0x180033d60  mov     rcx, rax; hServiceStatus
0x180033d63  mov     [rbp+ServiceStatus.dwCurrentState], r13d
0x180033d67  mov     [rbp+ServiceStatus.dwWaitHint], 2BF20h
0x180033d6e  call    cs:__imp_SetServiceStatus
0x180033d74  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d7b  cmp     rcx, r15
0x180033d7e  jz      short loc_180033DA1
0x180033d80  test    [rcx+1Ch], r12d
0x180033d84  jz      short loc_180033DA1
0x180033d86  cmp     byte ptr [rcx+19h], 5
0x180033d8a  jb      short loc_180033DA1
0x180033d8c  mov     rcx, [rcx+10h]
0x180033d90  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180033d97  mov     edx, 37h ; '7'
0x180033d9c  call    WPP_SF_
0x180033da1  call    GetModernStackStatus
0x180033da6  test    eax, eax
0x180033da8  jz      short loc_180033DFA
0x180033daa  mov     edi, 2C7h
0x180033daf  mov     rcx, cs:WPP_GLOBAL_Control
0x180033db6  cmp     rcx, r15
0x180033db9  jz      loc_1800341A7
0x180033dbf  test    dword ptr [rcx+1Ch], 800h
0x180033dc6  jz      loc_1800341A7
0x180033dcc  cmp     [rcx+19h], r13b
0x180033dd0  jb      loc_1800341A7
0x180033dd6  mov     rcx, [rcx+10h]
0x180033dda  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180033de1  mov     edx, 38h ; '8'
0x180033de6  mov     r9d, edi
0x180033de9  call    WPP_SF_d
0x180033dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180033df5  jmp     loc_1800341A7
0x180033dfa  call    _RasmanInit
0x180033dff  mov     edi, eax
0x180033e01  test    eax, eax
0x180033e03  jz      short loc_180033E46
0x180033e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180033e0c  cmp     rcx, r15
0x180033e0f  jz      loc_18003419F
0x180033e15  test    [rcx+1Ch], r12d
0x180033e19  jz      loc_18003419F
0x180033e1f  cmp     [rcx+19h], r13b
0x180033e23  jb      loc_18003419F
0x180033e29  mov     rcx, [rcx+10h]
0x180033e2d  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180033e34  mov     edx, 39h ; '9'
0x180033e39  mov     r9d, eax
0x180033e3c  call    WPP_SF_d
0x180033e41  jmp     loc_180034198
0x180033e46  mov     esi, r14d
0x180033e49  lea     rdi, protocolEngine
0x180033e50  mov     ebx, esi
0x180033e52  shl     rbx, 6
0x180033e56  cmp     [rbx+rdi+10h], r14d
0x180033e5b  jnz     short loc_180033ECA
0x180033e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180033e64  cmp     rcx, r15
0x180033e67  jz      short loc_180033E96
0x180033e69  test    [rcx+1Ch], r12d
0x180033e6d  jz      short loc_180033E96
0x180033e6f  cmp     byte ptr [rcx+19h], 5
0x180033e73  jb      short loc_180033E96
0x180033e75  mov     eax, [rbx+rdi+18h]
0x180033e79  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180033e80  mov     r9, [rbx+rdi]
0x180033e84  mov     edx, 3Ah ; ':'
0x180033e89  mov     rcx, [rcx+10h]
0x180033e8d  mov     dword ptr [rsp+78h+plpszSubStringArray], eax
0x180033e91  call    WPP_SF_sd
0x180033e96  mov     edx, [rbx+rdi+18h]
0x180033e9a  mov     r8d, 1
0x180033ea0  mov     rcx, cs:hLogEvents
0x180033ea7  mov     rax, [rbx+rdi+28h]
0x180033eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033eb1  mov     edi, eax
0x180033eb3  test    eax, eax
0x180033eb5  jnz     loc_180033FA8
0x180033ebb  lea     rdi, protocolEngine
0x180033ec2  mov     dword ptr [rbx+rdi+14h], 1
0x180033eca  inc     esi
0x180033ecc  cmp     esi, 4
0x180033ecf  jb      loc_180033E50
0x180033ed5  mov     r9d, cs:dword_18010A0B4
0x180033edc  mov     r8, cs:qword_18010A0C0
0x180033ee3  mov     edx, cs:dword_18010A134
0x180033ee9  mov     rcx, cs:hModule; hModule
0x180033ef0  call    VpnProfileLibInitialize
0x180033ef5  test    eax, eax
0x180033ef7  jz      short loc_180033F29
0x180033ef9  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f00  cmp     rcx, r15
0x180033f03  jz      short loc_180033F29
0x180033f05  test    [rcx+1Ch], r12d
0x180033f09  jz      short loc_180033F29
0x180033f0b  cmp     [rcx+19h], r13b
0x180033f0f  jb      short loc_180033F29
0x180033f11  mov     rcx, [rcx+10h]
0x180033f15  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180033f1c  mov     edx, 3Ch ; '<'
0x180033f21  mov     r9d, eax
0x180033f24  call    WPP_SF_d
0x180033f29  mov     esi, 1
0x180033f2e  mov     edi, r14d
0x180033f31  cmp     cs:g_RasMobileCore, r14d
0x180033f38  jnz     loc_18003404C
0x180033f3e  xor     edx, edx; hFile
0x180033f40  lea     rcx, aGdi32Dll; "GDI32.DLL"
0x180033f47  mov     r8d, 800h; dwFlags
0x180033f4d  call    cs:__imp_LoadLibraryExA
0x180033f53  mov     cs:g_hGdi32, rax
0x180033f5a  test    rax, rax
0x180033f5d  jnz     loc_180034017
0x180033f63  mov     rbx, cs:WPP_GLOBAL_Control
0x180033f6a  cmp     rbx, r15
0x180033f6d  jz      short loc_180033F9C
0x180033f6f  test    [rbx+1Ch], r12d
0x180033f73  jz      short loc_180033F9C
0x180033f75  cmp     [rbx+19h], r13b
0x180033f79  jb      short loc_180033F9C
0x180033f7b  mov     rbx, [rbx+10h]
0x180033f7f  call    cs:__imp_GetLastError
0x180033f85  mov     edx, 3Eh ; '>'
0x180033f8a  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180033f91  mov     r9d, eax
0x180033f94  mov     rcx, rbx
0x180033f97  call    WPP_SF_d
0x180033f9c  mov     rax, cs:g_pfnDeviceCapabilitiesExA
0x180033fa3  jmp     loc_18003402E
0x180033fa8  mov     esi, r14d
0x180033fab  mov     rcx, cs:WPP_GLOBAL_Control
0x180033fb2  cmp     rcx, r15
0x180033fb5  jz      short loc_180033FDB
0x180033fb7  test    [rcx+1Ch], r12d
0x180033fbb  jz      short loc_180033FDB
0x180033fbd  cmp     [rcx+19h], r13b
0x180033fc1  jb      short loc_180033FDB
0x180033fc3  mov     rcx, [rcx+10h]
0x180033fc7  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180033fce  mov     edx, 3Bh ; ';'
0x180033fd3  mov     r9d, edi
0x180033fd6  call    WPP_SF_d
0x180033fdb  mov     rcx, cs:hLogEvents; hLogHandle
0x180033fe2  lea     rax, protocolEngine
0x180033fe9  add     rax, 8
0x180033fed  mov     [rsp+78h+dwErrorIndex], r14d; dwErrorIndex
0x180033ff2  mov     edx, 1; dwEventType
0x180033ff7  mov     [rsp+78h+dwErrorCode], edi; dwErrorCode
0x180033ffb  add     rax, rbx
0x180033ffe  mov     r9d, edx; dwSubStringCount
0x180034001  mov     r8d, 4E5Fh; dwMessageId
0x180034007  mov     [rsp+78h+plpszSubStringArray], rax; plpszSubStringArray
0x18003400c  call    cs:__imp_RouterLogEventStringA
0x180034012  jmp     loc_180033F31
0x180034017  lea     rdx, aDevicecapabili; "DeviceCapabilitiesExA"
0x18003401e  mov     rcx, rax; hModule
0x180034021  call    cs:__imp_GetProcAddress
0x180034027  mov     cs:g_pfnDeviceCapabilitiesExA, rax
0x18003402e  test    rax, rax
0x180034031  jz      short loc_18003404C
0x180034033  mov     qword ptr [rsp+78h+dwErrorCode], r14
0x180034038  xor     r9d, r9d
0x18003403b  xor     r8d, r8d
0x18003403e  mov     [rsp+78h+plpszSubStringArray], r14
0x180034043  xor     edx, edx
0x180034045  xor     ecx, ecx
0x180034047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003404c  test    edi, edi
0x18003404e  jnz     loc_180034184
0x180034054  mov     rcx, cs:hService; hServiceStatus
0x18003405b  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x18003405f  mov     eax, 10C5h
0x180034064  mov     cs:dwControlsAccepted, eax
0x18003406a  mov     [rbp+ServiceStatus.dwControlsAccepted], eax
0x18003406d  lea     eax, [rdi+4]
0x180034070  mov     cs:dwCurrentState, eax
0x180034076  mov     [rbp+ServiceStatus.dwCurrentState], eax
0x180034079  call    cs:__imp_SetServiceStatus
0x18003407f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034086  cmp     rcx, r15
0x180034089  jz      short loc_1800340AA
0x18003408b  test    [rcx+1Ch], r12d
0x18003408f  jz      short loc_1800340AA
0x180034091  cmp     byte ptr [rcx+19h], 5
0x180034095  jb      short loc_1800340AA
0x180034097  mov     rcx, [rcx+10h]
0x18003409b  lea     edx, [rdi+3Fh]
0x18003409e  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x1800340a5  call    WPP_SF_
0x1800340aa  call    CheckModemState
0x1800340af  mov     edi, eax
0x1800340b1  test    eax, eax
0x1800340b3  jz      short loc_1800340F1
0x1800340b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800340bc  cmp     rcx, r15
0x1800340bf  jz      short loc_1800340EC
0x1800340c1  test    [rcx+1Ch], r12d
0x1800340c5  jz      short loc_1800340EC
0x1800340c7  cmp     [rcx+19h], r13b
0x1800340cb  jb      short loc_1800340EC
0x1800340cd  mov     rcx, [rcx+10h]
0x1800340d1  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x1800340d8  mov     edx, 40h ; '@'
0x1800340dd  mov     r9d, eax
0x1800340e0  call    WPP_SF_d
0x1800340e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800340ec  mov     edi, r14d
0x1800340ef  jmp     short loc_1800340F8
0x1800340f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800340f8  cmp     cs:g_fModemPresent, r14d
0x1800340ff  jnz     short loc_180034119
0x180034101  mov     rax, cs:RastapiCheckRasmanDependency
0x180034108  test    rax, rax
0x18003410b  jz      short loc_180034119
0x18003410d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034112  mov     rcx, cs:WPP_GLOBAL_Control
0x180034119  cmp     rcx, r15
0x18003411c  jz      short loc_18003413F
0x18003411e  test    [rcx+1Ch], r12d
0x180034122  jz      short loc_18003413F
0x180034124  cmp     byte ptr [rcx+19h], 6
0x180034128  jb      short loc_18003413F
0x18003412a  mov     rcx, [rcx+10h]
0x18003412e  lea     r8, WPP_7ba71f3b71eb31c5bb73738abca13a5c_Traceguids
0x180034135  mov     edx, 0Dh
0x18003413a  call    WPP_SF_
0x18003413f  xor     ecx, ecx
0x180034141  call    RequestThread
0x180034146  mov     rcx, cs:WPP_GLOBAL_Control
0x18003414d  cmp     rcx, r15
0x180034150  jz      short loc_18003417A
0x180034152  test    [rcx+1Ch], r12d
0x180034156  jz      short loc_18003417A
0x180034158  cmp     byte ptr [rcx+19h], 6
0x18003415c  jb      short loc_18003417A
0x18003415e  mov     rcx, [rcx+10h]
  ... truncated ...
```
