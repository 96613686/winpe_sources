# ServiceMain

- ea: `0x1800353b0`
- end: `0x180035a01`
- name: `ServiceMain`
- size: `1617`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180005c40`
- `0x18000acb4`
- `0x18000c238`
- `0x18000c424`
- `0x18000d21c`
- `0x18000ecd0`
- `0x180029de0`
- `0x1800345f0`
- `0x1800353b0`
- `0x1800e0e34`
- `0x1800e1f2c`
- `0x1800e8ef0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800354a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800354a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800356c5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800356c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800357ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800357ab`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerSetFlags` at `0x18003542d`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerSetFlags` at `0x18003542d`
- `rtutils!RouterLogEventStringA` at `0x180035790`
- `rtutils!RouterLogEventStringA` at `0x180035790`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerExA` at `0x180035460`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerExA` at `0x180035460`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800354e0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180035809`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003597d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800354e0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180035809`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003597d`

## string_xrefs

- `0x1800356b8`: `GDI32.DLL`

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
      v10 = VpnProfileLibInitialize(hModule, dword_18010B134, (HMODULE)qword_18010B0C0, (unsigned int)dword_18010B0B4);
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
  RouterLogEventStringA(hLogEvents, 1u, 0x4E5Fu, 1u, (LPSTR *)((char *)&qword_18010B068 + v8), dwErrorCode, 0);
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
0x1800353b0  push    rbp
0x1800353b2  push    rbx
0x1800353b3  push    rsi
0x1800353b4  push    rdi
0x1800353b5  push    r12
0x1800353b7  push    r13
0x1800353b9  push    r14
0x1800353bb  push    r15
0x1800353bd  mov     rbp, rsp
0x1800353c0  sub     rsp, 78h
0x1800353c4  mov     rax, cs:__security_cookie
0x1800353cb  xor     rax, rsp
0x1800353ce  mov     [rbp+var_18], rax
0x1800353d2  mov     r9d, ecx
0x1800353d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800353dc  lea     r15, WPP_GLOBAL_Control
0x1800353e3  mov     r12d, 2000h
0x1800353e9  cmp     rcx, r15
0x1800353ec  jz      short loc_180035419
0x1800353ee  test    [rcx+1Ch], r12d
0x1800353f2  jz      short loc_180035419
0x1800353f4  cmp     byte ptr [rcx+19h], 6
0x1800353f8  jb      short loc_180035419
0x1800353fa  mov     eax, cs:dwCurrentState
0x180035400  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180035407  mov     rcx, [rcx+10h]
0x18003540b  mov     edx, 35h ; '5'
0x180035410  mov     dword ptr [rsp+78h+plpszSubStringArray], eax
0x180035414  call    WPP_SF_Dd
0x180035419  xorps   xmm0, xmm0
0x18003541c  mov     r13d, 2
0x180035422  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x180035426  mov     ecx, r13d; dwFlags
0x180035429  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x18003542d  call    cs:__imp_WerSetFlags
0x180035434  nop     dword ptr [rax+rax+00h]
0x180035439  xorps   xmm0, xmm0
0x18003543c  mov     [rbp+ServiceStatus.dwServiceType], 20h ; ' '
0x180035443  xor     r14d, r14d
0x180035446  lea     rdx, ServiceHandlerEx; lpHandlerProc
0x18003544d  xor     r8d, r8d; lpContext
0x180035450  mov     qword ptr [rbp+ServiceStatus.dwCheckPoint], r14
0x180035454  lea     rcx, aRasman_1; "rasman"
0x18003545b  movdqu  xmmword ptr [rbp+ServiceStatus.dwCurrentState], xmm0
0x180035460  call    cs:__imp_RegisterServiceCtrlHandlerExA
0x180035467  nop     dword ptr [rax+rax+00h]
0x18003546c  mov     cs:hService, rax
0x180035473  test    rax, rax
0x180035476  jnz     short loc_1800354C7
0x180035478  mov     rcx, cs:WPP_GLOBAL_Control
0x18003547f  cmp     rcx, r15
0x180035482  jz      loc_1800359E3
0x180035488  test    [rcx+1Ch], r12d
0x18003548c  jz      loc_1800359BD
0x180035492  cmp     [rcx+19h], r13b
0x180035496  jb      loc_1800359BD
0x18003549c  mov     rbx, [rcx+10h]
0x1800354a0  call    cs:__imp_GetLastError
0x1800354a7  nop     dword ptr [rax+rax+00h]
0x1800354ac  lea     edx, [r13+34h]
0x1800354b0  mov     rcx, rbx
0x1800354b3  mov     r9d, eax
0x1800354b6  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x1800354bd  call    WPP_SF_d
0x1800354c2  jmp     loc_1800359B6
0x1800354c7  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x1800354cb  mov     cs:dwCurrentState, r13d
0x1800354d2  mov     rcx, rax; hServiceStatus
0x1800354d5  mov     [rbp+ServiceStatus.dwCurrentState], r13d
0x1800354d9  mov     [rbp+ServiceStatus.dwWaitHint], 2BF20h
0x1800354e0  call    cs:__imp_SetServiceStatus
0x1800354e7  nop     dword ptr [rax+rax+00h]
0x1800354ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800354f3  cmp     rcx, r15
0x1800354f6  jz      short loc_180035519
0x1800354f8  test    [rcx+1Ch], r12d
0x1800354fc  jz      short loc_180035519
0x1800354fe  cmp     byte ptr [rcx+19h], 5
0x180035502  jb      short loc_180035519
0x180035504  mov     rcx, [rcx+10h]
0x180035508  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x18003550f  mov     edx, 37h ; '7'
0x180035514  call    WPP_SF_
0x180035519  call    GetModernStackStatus
0x18003551e  test    eax, eax
0x180035520  jz      short loc_180035572
0x180035522  mov     edi, 2C7h
0x180035527  mov     rcx, cs:WPP_GLOBAL_Control
0x18003552e  cmp     rcx, r15
0x180035531  jz      loc_18003593D
0x180035537  test    dword ptr [rcx+1Ch], 800h
0x18003553e  jz      loc_18003593D
0x180035544  cmp     [rcx+19h], r13b
0x180035548  jb      loc_18003593D
0x18003554e  mov     rcx, [rcx+10h]
0x180035552  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180035559  mov     edx, 38h ; '8'
0x18003555e  mov     r9d, edi
0x180035561  call    WPP_SF_d
0x180035566  mov     rcx, cs:WPP_GLOBAL_Control
0x18003556d  jmp     loc_18003593D
0x180035572  call    _RasmanInit
0x180035577  mov     edi, eax
0x180035579  test    eax, eax
0x18003557b  jz      short loc_1800355BE
0x18003557d  mov     rcx, cs:WPP_GLOBAL_Control
0x180035584  cmp     rcx, r15
0x180035587  jz      loc_180035935
0x18003558d  test    [rcx+1Ch], r12d
0x180035591  jz      loc_180035935
0x180035597  cmp     [rcx+19h], r13b
0x18003559b  jb      loc_180035935
0x1800355a1  mov     rcx, [rcx+10h]
0x1800355a5  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x1800355ac  mov     edx, 39h ; '9'
0x1800355b1  mov     r9d, eax
0x1800355b4  call    WPP_SF_d
0x1800355b9  jmp     loc_18003592E
0x1800355be  mov     esi, r14d
0x1800355c1  lea     rdi, protocolEngine
0x1800355c8  mov     ebx, esi
0x1800355ca  shl     rbx, 6
0x1800355ce  cmp     [rbx+rdi+10h], r14d
0x1800355d3  jnz     short loc_180035642
0x1800355d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800355dc  cmp     rcx, r15
0x1800355df  jz      short loc_18003560E
0x1800355e1  test    [rcx+1Ch], r12d
0x1800355e5  jz      short loc_18003560E
0x1800355e7  cmp     byte ptr [rcx+19h], 5
0x1800355eb  jb      short loc_18003560E
0x1800355ed  mov     eax, [rbx+rdi+18h]
0x1800355f1  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x1800355f8  mov     r9, [rbx+rdi]
0x1800355fc  mov     edx, 3Ah ; ':'
0x180035601  mov     rcx, [rcx+10h]
0x180035605  mov     dword ptr [rsp+78h+plpszSubStringArray], eax
0x180035609  call    WPP_SF_sd
0x18003560e  mov     edx, [rbx+rdi+18h]
0x180035612  mov     r8d, 1
0x180035618  mov     rcx, cs:hLogEvents
0x18003561f  mov     rax, [rbx+rdi+28h]
0x180035624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035629  mov     edi, eax
0x18003562b  test    eax, eax
0x18003562d  jnz     loc_18003572C
0x180035633  lea     rdi, protocolEngine
0x18003563a  mov     dword ptr [rbx+rdi+14h], 1
0x180035642  inc     esi
0x180035644  cmp     esi, 4
0x180035647  jb      loc_1800355C8
0x18003564d  mov     r9d, cs:dword_18010B0B4
0x180035654  mov     r8, cs:qword_18010B0C0
0x18003565b  mov     edx, cs:dword_18010B134
0x180035661  mov     rcx, cs:hModule; hModule
0x180035668  call    VpnProfileLibInitialize
0x18003566d  test    eax, eax
0x18003566f  jz      short loc_1800356A1
0x180035671  mov     rcx, cs:WPP_GLOBAL_Control
0x180035678  cmp     rcx, r15
0x18003567b  jz      short loc_1800356A1
0x18003567d  test    [rcx+1Ch], r12d
0x180035681  jz      short loc_1800356A1
0x180035683  cmp     [rcx+19h], r13b
0x180035687  jb      short loc_1800356A1
0x180035689  mov     rcx, [rcx+10h]
0x18003568d  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180035694  mov     edx, 3Ch ; '<'
0x180035699  mov     r9d, eax
0x18003569c  call    WPP_SF_d
0x1800356a1  mov     esi, 1
0x1800356a6  mov     edi, r14d
0x1800356a9  cmp     cs:g_RasMobileCore, r14d
0x1800356b0  jnz     loc_1800357DC
0x1800356b6  xor     edx, edx; hFile
0x1800356b8  lea     rcx, aGdi32Dll; "GDI32.DLL"
0x1800356bf  mov     r8d, 800h; dwFlags
0x1800356c5  call    cs:__imp_LoadLibraryExA
0x1800356cc  nop     dword ptr [rax+rax+00h]
0x1800356d1  mov     cs:g_hGdi32, rax
0x1800356d8  test    rax, rax
0x1800356db  jnz     loc_1800357A1
0x1800356e1  mov     rbx, cs:WPP_GLOBAL_Control
0x1800356e8  cmp     rbx, r15
0x1800356eb  jz      short loc_180035720
0x1800356ed  test    [rbx+1Ch], r12d
0x1800356f1  jz      short loc_180035720
0x1800356f3  cmp     [rbx+19h], r13b
0x1800356f7  jb      short loc_180035720
0x1800356f9  mov     rbx, [rbx+10h]
0x1800356fd  call    cs:__imp_GetLastError
0x180035704  nop     dword ptr [rax+rax+00h]
0x180035709  mov     edx, 3Eh ; '>'
0x18003570e  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180035715  mov     r9d, eax
0x180035718  mov     rcx, rbx
0x18003571b  call    WPP_SF_d
0x180035720  mov     rax, cs:g_pfnDeviceCapabilitiesExA
0x180035727  jmp     loc_1800357BE
0x18003572c  mov     esi, r14d
0x18003572f  mov     rcx, cs:WPP_GLOBAL_Control
0x180035736  cmp     rcx, r15
0x180035739  jz      short loc_18003575F
0x18003573b  test    [rcx+1Ch], r12d
0x18003573f  jz      short loc_18003575F
0x180035741  cmp     [rcx+19h], r13b
0x180035745  jb      short loc_18003575F
0x180035747  mov     rcx, [rcx+10h]
0x18003574b  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180035752  mov     edx, 3Bh ; ';'
0x180035757  mov     r9d, edi
0x18003575a  call    WPP_SF_d
0x18003575f  mov     rcx, cs:hLogEvents; hLogHandle
0x180035766  lea     rax, protocolEngine
0x18003576d  add     rax, 8
0x180035771  mov     [rsp+78h+dwErrorIndex], r14d; dwErrorIndex
0x180035776  mov     edx, 1; dwEventType
0x18003577b  mov     [rsp+78h+dwErrorCode], edi; dwErrorCode
0x18003577f  add     rax, rbx
0x180035782  mov     r9d, edx; dwSubStringCount
0x180035785  mov     r8d, 4E5Fh; dwMessageId
0x18003578b  mov     [rsp+78h+plpszSubStringArray], rax; plpszSubStringArray
0x180035790  call    cs:__imp_RouterLogEventStringA
0x180035797  nop     dword ptr [rax+rax+00h]
0x18003579c  jmp     loc_1800356A9
0x1800357a1  lea     rdx, aDevicecapabili; "DeviceCapabilitiesExA"
0x1800357a8  mov     rcx, rax; hModule
0x1800357ab  call    cs:__imp_GetProcAddress
0x1800357b2  nop     dword ptr [rax+rax+00h]
0x1800357b7  mov     cs:g_pfnDeviceCapabilitiesExA, rax
0x1800357be  test    rax, rax
0x1800357c1  jz      short loc_1800357DC
0x1800357c3  mov     qword ptr [rsp+78h+dwErrorCode], r14
0x1800357c8  xor     r9d, r9d
0x1800357cb  xor     r8d, r8d
0x1800357ce  mov     [rsp+78h+plpszSubStringArray], r14
0x1800357d3  xor     edx, edx
0x1800357d5  xor     ecx, ecx
0x1800357d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357dc  test    edi, edi
0x1800357de  jnz     loc_18003591A
0x1800357e4  mov     rcx, cs:hService; hServiceStatus
0x1800357eb  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x1800357ef  mov     eax, 10C5h
0x1800357f4  mov     cs:dwControlsAccepted, eax
0x1800357fa  mov     [rbp+ServiceStatus.dwControlsAccepted], eax
0x1800357fd  lea     eax, [rdi+4]
0x180035800  mov     cs:dwCurrentState, eax
0x180035806  mov     [rbp+ServiceStatus.dwCurrentState], eax
0x180035809  call    cs:__imp_SetServiceStatus
0x180035810  nop     dword ptr [rax+rax+00h]
0x180035815  mov     rcx, cs:WPP_GLOBAL_Control
0x18003581c  cmp     rcx, r15
0x18003581f  jz      short loc_180035840
0x180035821  test    [rcx+1Ch], r12d
0x180035825  jz      short loc_180035840
0x180035827  cmp     byte ptr [rcx+19h], 5
0x18003582b  jb      short loc_180035840
0x18003582d  mov     rcx, [rcx+10h]
0x180035831  lea     edx, [rdi+3Fh]
0x180035834  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x18003583b  call    WPP_SF_
0x180035840  call    CheckModemState
0x180035845  mov     edi, eax
0x180035847  test    eax, eax
0x180035849  jz      short loc_180035887
0x18003584b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035852  cmp     rcx, r15
0x180035855  jz      short loc_180035882
0x180035857  test    [rcx+1Ch], r12d
0x18003585b  jz      short loc_180035882
0x18003585d  cmp     [rcx+19h], r13b
0x180035861  jb      short loc_180035882
0x180035863  mov     rcx, [rcx+10h]
0x180035867  lea     r8, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x18003586e  mov     edx, 40h ; '@'
0x180035873  mov     r9d, eax
0x180035876  call    WPP_SF_d
0x18003587b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035882  mov     edi, r14d
0x180035885  jmp     short loc_18003588E
0x180035887  mov     rcx, cs:WPP_GLOBAL_Control
0x18003588e  cmp     cs:g_fModemPresent, r14d
0x180035895  jnz     short loc_1800358AF
0x180035897  mov     rax, cs:RastapiCheckRasmanDependency
0x18003589e  test    rax, rax
0x1800358a1  jz      short loc_1800358AF
0x1800358a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800358af  cmp     rcx, r15
0x1800358b2  jz      short loc_1800358D5
0x1800358b4  test    [rcx+1Ch], r12d
0x1800358b8  jz      short loc_1800358D5
0x1800358ba  cmp     byte ptr [rcx+19h], 6
0x1800358be  jb      short loc_1800358D5
0x1800358c0  mov     rcx, [rcx+10h]
0x1800358c4  lea     r8, WPP_7ba71f3b71eb31c5bb73738abca13a5c_Traceguids
0x1800358cb  mov     edx, 0Dh
0x1800358d0  call    WPP_SF_
0x1800358d5  xor     ecx, ecx
  ... truncated ...
```
