# ServiceMain

- ea: `0x180025350`
- end: `0x180025671`
- name: `ServiceMain`
- size: `801`
- prototype: `HRESULT()`
- caller_count: `0`
- callee_count: `21`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005670`
- `0x180009038`
- `0x180009580`
- `0x18000eafc`
- `0x180015630`
- `0x1800199d8`
- `0x18001c02c`
- `0x18001c660`
- `0x18001cef0`
- `0x18001d826`
- `0x18001e228`
- `0x180020e78`
- `0x180021420`
- `0x180023928`
- `0x180025350`
- `0x1800258fc`
- `0x180043508`
- `0x180045328`
- `0x180045a18`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800254dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002558d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800254dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002558d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002564d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002564d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025635`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025635`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002550d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002550d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800254c5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800254c5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002556d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002556d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800255fd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800255fd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800254f8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800255a9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800255cc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800254f8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800255a9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800255cc`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerSetFlags` at `0x180025396`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerSetFlags` at `0x180025396`
- `WS2_32!__imp_WSAStartup` at `0x1800253bb`
- `WS2_32!__imp_WSAStartup` at `0x1800253bb`
- `ext-ms-win-firewallapi-webproxy-l1-1-1!FWResetIndicatedPortInUse` at `0x18002545b`
- `ext-ms-win-firewallapi-webproxy-l1-1-1!FWResetIndicatedPortInUse` at `0x18002545b`

## string_xrefs

- `0x1800254b9`: `dhcpcore6.dll`

## pseudocode

```c
HRESULT ServiceMain()
{
  HRESULT result; // eax
  void *v1; // rdi
  int v2; // ecx
  int v3; // r8d
  unsigned int v4; // eax
  CRpcWatchDog *v5; // rcx
  HMODULE v6; // rsi
  unsigned int inited; // eax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // eax
  HMODULE Library; // rax
  DWORD LastError; // eax
  __int64 v14; // rcx
  ULONG (__stdcall *ProcAddress)(PVOID); // rbp
  HANDLE v16; // rax
  DWORD v17; // eax
  __int64 v18; // rcx
  int v19; // ecx
  int v20; // r8d
  __int128 Parameter; // [rsp+30h] [rbp-208h] BYREF
  int *v22; // [rsp+40h] [rbp-1F8h]
  WSAData WSAData; // [rsp+50h] [rbp-1E8h] BYREF
  _BYTE v24[16]; // [rsp+1F0h] [rbp-48h] BYREF

  v22 = 0;
  Parameter = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  result = WerSetFlags(2u);
  if ( DhcpGlobalServiceStatus.dwCurrentState == 1 )
  {
    v1 = 0;
    if ( WSAStartup(0x101u, &WSAData) )
      goto LABEL_38;
    DhcpGlobalWinSockInitialized = 1;
    McGenEventRegister_EventRegister();
    if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 0x20) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(v2, (unsigned int)ServiceStart, v3, 1, (__int64)v24);
    v4 = CRpcWatchDog::Start();
    if ( (unsigned int)WX_WIN32_FROM_HR(v4) )
      goto LABEL_38;
    if ( (unsigned int)DhcpCommonInit() )
    {
LABEL_37:
      CRpcWatchDog::Stop(v5);
LABEL_38:
      result = McGenEventUnregister_EventUnregister();
      if ( v1 )
        return CloseHandle(v1);
      return result;
    }
    v6 = 0;
    inited = DhcpInitData();
    v9 = inited;
    if ( !inited )
    {
      if ( (unsigned __int8)IsFWResetIndicatedPortInUsePresent() )
      {
        v10 = FWResetIndicatedPortInUse(4);
        if ( (xmmword_1800616A0 & 0x10) != 0 )
          WPP_SF_D(1028, 11, WPP_52380679383138217cb423d182f11bb5_Traceguids, v10);
      }
      else if ( (xmmword_1800616A0 & 2) != 0 )
      {
        WPP_SF_(1025, 10, WPP_52380679383138217cb423d182f11bb5_Traceguids);
      }
      v11 = DhcpFirewallInit();
      v9 = v11;
      if ( v11 )
      {
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_D(1025, 169, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v11);
LABEL_34:
        DhcpCleanup(v9);
        if ( v6 && !DhcpGlobalIsShuttingDown )
          FreeLibrary(v6);
        goto LABEL_37;
      }
      Library = LoadLibraryExW(L"dhcpcore6.dll", 0, 0);
      v6 = Library;
      if ( !Library || (ProcAddress = (ULONG (__stdcall *)(PVOID))GetProcAddress(Library, "Dhcpv6Main")) == 0 )
      {
        if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 0x40) != 0 )
        {
          LastError = GetLastError();
          McTemplateU0q_EtwEventWriteTransfer(v14, Dhcpv6InitFailed, LastError);
        }
        SetEvent(DhcpGlobalServiceSyncEvent);
        goto LABEL_27;
      }
      UpdateStatus();
      inited = SystemInitialize();
      v9 = inited;
      if ( !inited )
      {
        PdcInitialize();
        *(_QWORD *)&Parameter = DhcpGlobalTerminateEvent;
        *((_QWORD *)&Parameter + 1) = DhcpGlobalServiceSyncEvent;
        v22 = &DhcpGlobalIsShuttingDown;
        v16 = CreateThread(0, 0, ProcAddress, &Parameter, 0, 0);
        v1 = v16;
        if ( !v16 || v16 == (HANDLE)-1LL )
        {
          if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 0x40) != 0 )
          {
            v17 = GetLastError();
            McTemplateU0q_EtwEventWriteTransfer(v18, Dhcpv6InitFailed, v17);
          }
          SetEvent(DhcpGlobalServiceSyncEvent);
        }
LABEL_27:
        v9 = ProcessDhcpRequestForever(1);
        if ( v1 && DhcpGlobalTerminateEvent )
        {
          SetEvent(DhcpGlobalTerminateEvent);
          if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 0x20) != 0 )
            McGenEventWrite_EtwEventWriteTransfer(v19, (unsigned int)WaitingOnDhcpV6ServiceStop, v20, 1, (__int64)v24);
          WaitForSingleObject(v1, 0xFFFFFFFF);
        }
        goto LABEL_34;
      }
    }
    if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 0x40) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v8, ErrorInitService, inited);
    goto LABEL_34;
  }
  return result;
}

```

## disassembly

```asm
0x180025350  push    rbx
0x180025352  push    rbp
0x180025353  push    rsi
0x180025354  push    rdi
0x180025355  push    r15
0x180025357  sub     rsp, 210h
0x18002535e  mov     rax, cs:__security_cookie
0x180025365  xor     rax, rsp
0x180025368  mov     [rsp+238h+var_38], rax
0x180025370  xorps   xmm0, xmm0
0x180025373  lea     rcx, [rsp+238h+WSAData]; void *
0x180025378  xor     eax, eax
0x18002537a  xor     edx, edx; Val
0x18002537c  mov     r8d, 198h; Size
0x180025382  mov     [rsp+238h+var_1F8], rax
0x180025387  movups  [rsp+238h+Parameter], xmm0
0x18002538c  call    memset_0
0x180025391  mov     ecx, 2; dwFlags
0x180025396  call    cs:__imp_WerSetFlags
0x18002539c  mov     r15d, 1
0x1800253a2  cmp     cs:DhcpGlobalServiceStatus.dwCurrentState, r15d
0x1800253a9  jnz     loc_180025653
0x1800253af  mov     ecx, 101h; wVersionRequested
0x1800253b4  lea     rdx, [rsp+238h+WSAData]; lpWSAData
0x1800253b9  xor     edi, edi
0x1800253bb  call    cs:__imp_WSAStartup
0x1800253c1  test    eax, eax
0x1800253c3  jnz     loc_180025640
0x1800253c9  mov     cs:DhcpGlobalWinSockInitialized, r15d
0x1800253d0  call    McGenEventRegister_EventRegister
0x1800253d5  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 20h
0x1800253dc  jz      short loc_1800253FA
0x1800253de  lea     rax, [rsp+238h+var_48]
0x1800253e6  mov     r9d, r15d
0x1800253e9  lea     rdx, ServiceStart
0x1800253f0  mov     qword ptr [rsp+238h+dwCreationFlags], rax
0x1800253f5  call    McGenEventWrite_EtwEventWriteTransfer
0x1800253fa  call    ?Start@CRpcWatchDog@@QEAAJW4_WatchDogReportType@@@Z; CRpcWatchDog::Start(_WatchDogReportType)
0x1800253ff  mov     ecx, eax
0x180025401  call    WX_WIN32_FROM_HR
0x180025406  test    eax, eax
0x180025408  jnz     loc_180025640
0x18002540e  call    DhcpCommonInit
0x180025413  test    eax, eax
0x180025415  jnz     loc_18002563B
0x18002541b  xor     esi, esi
0x18002541d  call    DhcpInitData
0x180025422  mov     ebx, eax
0x180025424  test    eax, eax
0x180025426  jnz     loc_180025605
0x18002542c  call    IsFWResetIndicatedPortInUsePresent
0x180025431  mov     ebp, 401h
0x180025436  test    al, al
0x180025438  jnz     short loc_180025456
0x18002543a  test    byte ptr cs:xmmword_1800616A0, 2
0x180025441  jz      short loc_180025483
0x180025443  lea     edx, [rsi+0Ah]
0x180025446  mov     ecx, ebp
0x180025448  lea     r8, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x18002544f  call    WPP_SF_
0x180025454  jmp     short loc_180025483
0x180025456  mov     ecx, 4
0x18002545b  call    cs:__imp_FWResetIndicatedPortInUse
0x180025461  test    byte ptr cs:xmmword_1800616A0, 10h
0x180025468  jz      short loc_180025483
0x18002546a  mov     edx, 0Bh
0x18002546f  lea     r8, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x180025476  mov     ecx, 404h
0x18002547b  mov     r9d, eax
0x18002547e  call    WPP_SF_D
0x180025483  call    DhcpFirewallInit
0x180025488  mov     ebx, eax
0x18002548a  test    eax, eax
0x18002548c  jz      short loc_1800254B6
0x18002548e  test    byte ptr cs:xmmword_1800616A0, 2
0x180025495  jz      loc_18002561D
0x18002549b  mov     edx, 0A9h
0x1800254a0  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x1800254a7  mov     ecx, ebp
0x1800254a9  mov     r9d, eax
0x1800254ac  call    WPP_SF_D
0x1800254b1  jmp     loc_18002561D
0x1800254b6  xor     r8d, r8d; dwFlags
0x1800254b9  lea     rcx, LibFileName; "dhcpcore6.dll"
0x1800254c0  xor     edx, edx; hFile
0x1800254c2  mov     ebx, r15d
0x1800254c5  call    cs:__imp_LoadLibraryExW
0x1800254cb  mov     rsi, rax
0x1800254ce  test    rax, rax
0x1800254d1  jnz     short loc_180025503
0x1800254d3  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 40h
0x1800254da  jz      short loc_1800254F1
0x1800254dc  call    cs:__imp_GetLastError
0x1800254e2  mov     r8d, eax
0x1800254e5  lea     rdx, Dhcpv6InitFailed
0x1800254ec  call    McTemplateU0q_EtwEventWriteTransfer
0x1800254f1  mov     rcx, cs:DhcpGlobalServiceSyncEvent; hEvent
0x1800254f8  call    cs:__imp_SetEvent
0x1800254fe  jmp     loc_1800255B2
0x180025503  lea     rdx, ProcName; "Dhcpv6Main"
0x18002550a  mov     rcx, rax; hModule
0x18002550d  call    cs:__imp_GetProcAddress
0x180025513  mov     rbp, rax
0x180025516  test    rax, rax
0x180025519  jz      short loc_1800254D3
0x18002551b  call    UpdateStatus
0x180025520  call    SystemInitialize
0x180025525  mov     ebx, eax
0x180025527  test    eax, eax
0x180025529  jnz     loc_180025605
0x18002552f  call    PdcInitialize
0x180025534  mov     rax, cs:DhcpGlobalTerminateEvent
0x18002553b  lea     r9, [rsp+238h+Parameter]; lpParameter
0x180025540  mov     qword ptr [rsp+238h+Parameter], rax
0x180025545  mov     r8, rbp; lpStartAddress
0x180025548  mov     rax, cs:DhcpGlobalServiceSyncEvent
0x18002554f  xor     edx, edx; dwStackSize
0x180025551  mov     qword ptr [rsp+238h+Parameter+8], rax
0x180025556  xor     ecx, ecx; lpThreadAttributes
0x180025558  lea     rax, DhcpGlobalIsShuttingDown
0x18002555f  mov     [rsp+238h+lpThreadId], rdi; lpThreadId
0x180025564  mov     [rsp+238h+var_1F8], rax
0x180025569  mov     [rsp+238h+dwCreationFlags], edi; dwCreationFlags
0x18002556d  call    cs:__imp_CreateThread
0x180025573  mov     rdi, rax
0x180025576  test    rax, rax
0x180025579  jz      short loc_180025584
0x18002557b  mov     ebx, r15d
0x18002557e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025582  jnz     short loc_1800255B2
0x180025584  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 40h
0x18002558b  jz      short loc_1800255A2
0x18002558d  call    cs:__imp_GetLastError
0x180025593  mov     r8d, eax
0x180025596  lea     rdx, Dhcpv6InitFailed
0x18002559d  call    McTemplateU0q_EtwEventWriteTransfer
0x1800255a2  mov     rcx, cs:DhcpGlobalServiceSyncEvent; hEvent
0x1800255a9  call    cs:__imp_SetEvent
0x1800255af  mov     ebx, r15d
0x1800255b2  mov     ecx, ebx
0x1800255b4  call    ProcessDhcpRequestForever
0x1800255b9  mov     ebx, eax
0x1800255bb  test    rdi, rdi
0x1800255be  jz      short loc_18002561D
0x1800255c0  mov     rcx, cs:DhcpGlobalTerminateEvent; hEvent
0x1800255c7  test    rcx, rcx
0x1800255ca  jz      short loc_18002561D
0x1800255cc  call    cs:__imp_SetEvent
0x1800255d2  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 20h
0x1800255d9  jz      short loc_1800255F7
0x1800255db  lea     rax, [rsp+238h+var_48]
0x1800255e3  mov     r9d, r15d
0x1800255e6  lea     rdx, WaitingOnDhcpV6ServiceStop
0x1800255ed  mov     qword ptr [rsp+238h+dwCreationFlags], rax
0x1800255f2  call    McGenEventWrite_EtwEventWriteTransfer
0x1800255f7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800255fa  mov     rcx, rdi; hHandle
0x1800255fd  call    cs:__imp_WaitForSingleObject
0x180025603  jmp     short loc_18002561D
0x180025605  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 40h
0x18002560c  jz      short loc_18002561D
0x18002560e  mov     r8d, eax
0x180025611  lea     rdx, ErrorInitService
0x180025618  call    McTemplateU0q_EtwEventWriteTransfer
0x18002561d  mov     ecx, ebx
0x18002561f  call    DhcpCleanup
0x180025624  test    rsi, rsi
0x180025627  jz      short loc_18002563B
0x180025629  cmp     cs:DhcpGlobalIsShuttingDown, 0
0x180025630  jnz     short loc_18002563B
0x180025632  mov     rcx, rsi; hLibModule
0x180025635  call    cs:__imp_FreeLibrary
0x18002563b  call    ?Stop@CRpcWatchDog@@QEAAXXZ; CRpcWatchDog::Stop(void)
0x180025640  call    McGenEventUnregister_EventUnregister
0x180025645  test    rdi, rdi
0x180025648  jz      short loc_180025653
0x18002564a  mov     rcx, rdi; hObject
0x18002564d  call    cs:__imp_CloseHandle
0x180025653  mov     rcx, [rsp+238h+var_38]
0x18002565b  xor     rcx, rsp; StackCookie
0x18002565e  call    __security_check_cookie
0x180025663  add     rsp, 210h
0x18002566a  pop     r15
0x18002566c  pop     rdi
0x18002566d  pop     rsi
0x18002566e  pop     rbp
0x18002566f  pop     rbx
0x180025670  retn
```
