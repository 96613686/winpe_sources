# CHostContext::CreateHostProcess(void)

- ea: `0x180022624`
- end: `0x180022a4e`
- name: `?CreateHostProcess@CHostContext@@IEAAJXZ`
- size: `1066`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002cc94`

## callees

- `0x180007500`
- `0x180022624`
- `0x180022a54`
- `0x180022d24`
- `0x1800233b8`
- `0x180025f3c`
- `0x180034538`
- `0x18003bc80`
- `0x18003c79c`
- `0x18004beb0`
- `0x18004bfc8`
- `0x18007dd30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800229f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800229f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022a08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022a08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002287b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002290b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002287b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002290b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022970`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002286c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002286c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002295c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002295c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180022901`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180022901`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002294b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022a18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002294b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022a18`
- `RPCRT4!UuidCreate` at `0x180022783`
- `RPCRT4!UuidCreate` at `0x180022783`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800229ab`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800229ab`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180022966`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180022966`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022a27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022a27`
- `profapi!__imp_CreateEnvBlock` at `0x18002284f`
- `profapi!__imp_CreateEnvBlock` at `0x18002284f`
- `profapi!__imp_DestroyEnvBlock` at `0x1800229e3`
- `profapi!__imp_DestroyEnvBlock` at `0x1800229e3`

## pseudocode

```c
__int64 __fastcall CHostContext::CreateHostProcess(void **this)
{
  void *v2; // r15
  signed int v3; // eax
  signed int HostSecurityDescriptor; // ebx
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  RPC_STATUS v8; // eax
  PTP_WAIT ThreadpoolWait; // rax
  signed int LastError; // eax
  signed int v11; // eax
  CHostContext *v12; // rcx
  signed int v13; // eax
  CHostContext *v14; // rcx
  HANDLE ProcessHeap; // rax
  LPVOID lpEnvironment; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hToken; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v20[2]; // [rsp+88h] [rbp-78h] BYREF
  _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+90h] [rbp-70h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+A8h] [rbp-58h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+C0h] [rbp-40h] BYREF
  UUID Uuid; // [rsp+130h] [rbp+30h] BYREF
  WCHAR CommandLine[12]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v26[44]; // [rsp+158h] [rbp+58h] BYREF

  hToken = 0;
  hMem = 0;
  *(_QWORD *)&ProcessAttributes.nLength = 24;
  ProcessAttributes.lpSecurityDescriptor = 0;
  *(_QWORD *)&ProcessAttributes.bInheritHandle = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  Uuid = 0;
  memset_0(CommandLine, 0, 0x66u);
  lpEnvironment = 0;
  v20[0] = 7;
  v20[1] = 18;
  v2 = (void *)pSetupEnableThreadPrivileges(v20);
  if ( v2 != (void *)-1LL )
  {
    HostSecurityDescriptor = CHostContext::CreateHostTokenAndSid(
                               (CHostContext *)this,
                               *((_DWORD *)this + 10),
                               &hToken,
                               &hMem);
    if ( HostSecurityDescriptor )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v7 = 20;
LABEL_7:
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v5,
          v6,
          v7,
          &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
          HostSecurityDescriptor);
      }
    }
    else
    {
      HostSecurityDescriptor = CHostContext::CreateHostSecurityDescriptor(
                                 (CHostContext *)this,
                                 *((_DWORD *)this + 10),
                                 hMem,
                                 &ProcessAttributes.lpSecurityDescriptor);
      if ( HostSecurityDescriptor )
      {
        if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_37;
        v7 = 21;
        goto LABEL_7;
      }
      v8 = UuidCreate(&Uuid);
      HostSecurityDescriptor = v8;
      if ( v8 && v8 != 1824 )
      {
        if ( v8 >= 0 )
          HostSecurityDescriptor = (unsigned __int16)v8 | 0x80010000;
        goto LABEL_37;
      }
      HostSecurityDescriptor = StringCchPrintfW(
                                 CommandLine,
                                 0x33u,
                                 L"dashost.exe {%08x-%04x-%04x-%02x%02x%02x%02x%02x%02x%02x%02x}",
                                 Uuid.Data1,
                                 Uuid.Data2,
                                 Uuid.Data3,
                                 Uuid.Data4[0],
                                 Uuid.Data4[1],
                                 Uuid.Data4[2],
                                 Uuid.Data4[3],
                                 Uuid.Data4[4],
                                 Uuid.Data4[5],
                                 Uuid.Data4[6],
                                 Uuid.Data4[7]);
      if ( HostSecurityDescriptor < 0 )
      {
        if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_37;
        v7 = 22;
        goto LABEL_7;
      }
      HostSecurityDescriptor = CreateEnvBlock(&lpEnvironment, hToken, 0);
      if ( HostSecurityDescriptor < 0 )
        goto LABEL_37;
      ThreadpoolWait = CreateThreadpoolWait(CHostContext::ProcessWaitCallback, this, 0);
      this[6] = ThreadpoolWait;
      if ( !ThreadpoolWait )
      {
        LastError = GetLastError();
        HostSecurityDescriptor = LastError;
        if ( LastError > 0 )
          HostSecurityDescriptor = (unsigned __int16)LastError | 0x80070000;
        if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_37;
        v7 = 23;
        goto LABEL_7;
      }
      if ( !CreateProcessAsUserW(
              hToken,
              L"dashost.exe",
              CommandLine,
              &ProcessAttributes,
              0,
              0,
              0x408u,
              lpEnvironment,
              0,
              &StartupInfo,
              &ProcessInformation) )
      {
        v11 = GetLastError();
        HostSecurityDescriptor = v11;
        if ( v11 > 0 )
          HostSecurityDescriptor = (unsigned __int16)v11 | 0x80070000;
        if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_37;
        v7 = 24;
        goto LABEL_7;
      }
      this[1] = ProcessInformation.hProcess;
      CloseHandle(ProcessInformation.hThread);
      SetThreadpoolWait((PTP_WAIT)this[6], this[1], 0);
      if ( !ImpersonateLoggedOnUser(ProcessInformation.hProcess) )
      {
        HostSecurityDescriptor = CHostContext::WaitUntilRpcIsReady(v12, v26);
        RevertToSelf();
        if ( !HostSecurityDescriptor )
        {
          HostSecurityDescriptor = CHostContext::DasHostClientInitializeRpc(v14, v26, this);
          if ( HostSecurityDescriptor >= 0 )
            HostSecurityDescriptor = CHostContext::CopyDasProcessHandle((CHostContext *)this);
        }
        goto LABEL_37;
      }
      v13 = GetLastError();
      HostSecurityDescriptor = v13;
      if ( v13 > 0 )
        HostSecurityDescriptor = (unsigned __int16)v13 | 0x80070000;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v7 = 25;
        goto LABEL_7;
      }
    }
LABEL_37:
    pSetupRestoreThreadPrivileges(v2);
    goto LABEL_38;
  }
  v3 = GetLastError();
  HostSecurityDescriptor = v3;
  if ( v3 > 0 )
    HostSecurityDescriptor = (unsigned __int16)v3 | 0x80070000;
LABEL_38:
  if ( lpEnvironment )
  {
    DestroyEnvBlock();
    lpEnvironment = 0;
  }
  if ( ProcessAttributes.lpSecurityDescriptor )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, ProcessAttributes.lpSecurityDescriptor);
  }
  if ( hToken )
    CloseHandle(hToken);
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)HostSecurityDescriptor;
}

```

## disassembly

```asm
0x180022624  push    rbp
0x180022626  push    rbx
0x180022627  push    rsi
0x180022628  push    rdi
0x180022629  push    r14
0x18002262b  push    r15
0x18002262d  lea     rbp, [rsp-0C8h]
0x180022635  sub     rsp, 1C8h
0x18002263c  mov     rax, cs:__security_cookie
0x180022643  xor     rax, rsp
0x180022646  mov     [rbp+0F0h+var_40], rax
0x18002264d  mov     r14, rcx
0x180022650  mov     [rsp+1F0h+hToken], 0
0x180022659  mov     [rbp+0F0h+hMem], 0
0x180022661  mov     qword ptr [rbp+0F0h+ProcessAttributes.nLength], 18h
0x180022669  mov     [rbp+0F0h+ProcessAttributes.lpSecurityDescriptor], 0
0x180022671  mov     qword ptr [rbp+0F0h+ProcessAttributes.bInheritHandle], 0
0x180022679  xor     edx, edx; Val
0x18002267b  lea     r8d, [rdx+68h]; Size
0x18002267f  lea     rcx, [rbp+0F0h+StartupInfo]; void *
0x180022683  call    memset_0
0x180022688  xorps   xmm0, xmm0
0x18002268b  xor     eax, eax
0x18002268d  movups  xmmword ptr [rbp+0F0h+ProcessInformation.hProcess], xmm0
0x180022691  mov     qword ptr [rbp+0F0h+ProcessInformation.dwProcessId], rax
0x180022695  movups  xmmword ptr [rbp+0F0h+Uuid.Data1], xmm0
0x180022699  xor     edx, edx; Val
0x18002269b  lea     r8d, [rax+66h]; Size
0x18002269f  lea     rcx, [rbp+0F0h+CommandLine]; void *
0x1800226a3  call    memset_0
0x1800226a8  mov     [rsp+1F0h+var_180], 0
0x1800226b1  mov     [rbp+0F0h+var_168], 7
0x1800226b8  mov     [rbp+0F0h+var_164], 12h
0x1800226bf  lea     rcx, [rbp+0F0h+var_168]
0x1800226c3  call    pSetupEnableThreadPrivileges
0x1800226c8  mov     r15, rax
0x1800226cb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800226cf  jnz     short loc_1800226EF
0x1800226d1  call    cs:__imp_GetLastError
0x1800226d7  mov     ebx, eax
0x1800226d9  test    eax, eax
0x1800226db  jle     loc_1800229D9
0x1800226e1  movzx   ebx, ax
0x1800226e4  or      ebx, 80070000h
0x1800226ea  jmp     loc_1800229D9
0x1800226ef  lea     r9, [rbp+0F0h+hMem]; void **
0x1800226f3  lea     r8, [rsp+1F0h+hToken]; void **
0x1800226f8  mov     edx, [r14+28h]; unsigned int
0x1800226fc  mov     rcx, r14; this
0x1800226ff  call    ?CreateHostTokenAndSid@CHostContext@@IEAAJKPEAPEAX0@Z; CHostContext::CreateHostTokenAndSid(ulong,void * *,void * *)
0x180022704  mov     ebx, eax
0x180022706  test    eax, eax
0x180022708  jz      short loc_180022749
0x18002270a  lea     rax, WPP_RECORDER_INITIALIZED
0x180022711  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180022718  jz      loc_1800229D1
0x18002271e  mov     r9d, 14h; int
0x180022724  mov     [rsp+1F0h+bInheritHandles], ebx; char
0x180022728  lea     rax, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x18002272f  mov     [rsp+1F0h+lpThreadAttributes], rax; MessageGuid
0x180022734  mov     rcx, cs:WPP_GLOBAL_Control
0x18002273b  mov     rcx, [rcx+28h]; int
0x18002273f  call    WPP_RECORDER_SF_D
0x180022744  jmp     loc_1800229D1
0x180022749  lea     r9, [rbp+0F0h+ProcessAttributes.lpSecurityDescriptor]; void **
0x18002274d  mov     r8, [rbp+0F0h+hMem]; void *
0x180022751  mov     edx, [r14+28h]; unsigned int
0x180022755  mov     rcx, r14; this
0x180022758  call    ?CreateHostSecurityDescriptor@CHostContext@@IEAAJKPEAXPEAPEAX@Z; CHostContext::CreateHostSecurityDescriptor(ulong,void *,void * *)
0x18002275d  mov     ebx, eax
0x18002275f  test    eax, eax
0x180022761  jz      short loc_18002277F
0x180022763  lea     rax, WPP_RECORDER_INITIALIZED
0x18002276a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180022771  jz      loc_1800229D1
0x180022777  mov     r9d, 15h
0x18002277d  jmp     short loc_180022724
0x18002277f  lea     rcx, [rbp+0F0h+Uuid]; Uuid
0x180022783  call    cs:__imp_UuidCreate
0x180022789  mov     ebx, eax
0x18002278b  test    eax, eax
0x18002278d  jz      short loc_1800227AC
0x18002278f  cmp     eax, 720h
0x180022794  jz      short loc_1800227AC
0x180022796  test    eax, eax
0x180022798  js      loc_1800229D1
0x18002279e  movzx   ebx, ax
0x1800227a1  or      ebx, 80010000h
0x1800227a7  jmp     loc_1800229D1
0x1800227ac  movzx   eax, [rbp+0F0h+Uuid.Data4+7]
0x1800227b0  movzx   ecx, [rbp+0F0h+Uuid.Data4+6]
0x1800227b4  movzx   edx, [rbp+0F0h+Uuid.Data4+5]
0x1800227b8  movzx   r8d, [rbp+0F0h+Uuid.Data4+4]
0x1800227bd  movzx   r9d, [rbp+0F0h+Uuid.Data4+3]
0x1800227c2  movzx   r10d, [rbp+0F0h+Uuid.Data4+2]
0x1800227c7  movzx   r11d, [rbp+0F0h+Uuid.Data4+1]
0x1800227cc  movzx   ebx, [rbp+0F0h+Uuid.Data4]
0x1800227d0  movzx   edi, [rbp+0F0h+Uuid.Data3]
0x1800227d4  movzx   esi, [rbp+0F0h+Uuid.Data2]
0x1800227d8  mov     [rsp+1F0h+var_188], eax
0x1800227dc  mov     [rsp+1F0h+var_190], ecx
0x1800227e0  mov     [rsp+1F0h+var_198], edx
0x1800227e4  mov     dword ptr [rsp+1F0h+lpProcessInformation], r8d
0x1800227e9  mov     dword ptr [rsp+1F0h+lpStartupInfo], r9d
0x1800227ee  mov     dword ptr [rsp+1F0h+lpCurrentDirectory], r10d
0x1800227f3  mov     dword ptr [rsp+1F0h+lpEnvironment], r11d
0x1800227f8  mov     [rsp+1F0h+dwCreationFlags], ebx
0x1800227fc  mov     [rsp+1F0h+bInheritHandles], edi
0x180022800  mov     dword ptr [rsp+1F0h+lpThreadAttributes], esi
0x180022804  mov     r9d, [rbp+0F0h+Uuid.Data1]
0x180022808  lea     r8, aDashostExe08x0; "dashost.exe {%08x-%04x-%04x-%02x%02x%02"...
0x18002280f  mov     edx, 33h ; '3'; unsigned __int64
0x180022814  lea     rcx, [rbp+0F0h+CommandLine]; unsigned __int16 *
0x180022818  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002281d  mov     ebx, eax
0x18002281f  test    eax, eax
0x180022821  jns     short loc_180022842
0x180022823  lea     rax, WPP_RECORDER_INITIALIZED
0x18002282a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180022831  jz      loc_1800229D1
0x180022837  mov     r9d, 16h
0x18002283d  jmp     loc_180022724
0x180022842  xor     r8d, r8d
0x180022845  mov     rdx, [rsp+1F0h+hToken]
0x18002284a  lea     rcx, [rsp+1F0h+var_180]
0x18002284f  call    cs:__imp_CreateEnvBlock
0x180022855  mov     ebx, eax
0x180022857  test    eax, eax
0x180022859  js      loc_1800229D1
0x18002285f  xor     r8d, r8d; pcbe
0x180022862  mov     rdx, r14; pv
0x180022865  lea     rcx, ?ProcessWaitCallback@CHostContext@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18002286c  call    cs:__imp_CreateThreadpoolWait
0x180022872  mov     [r14+30h], rax
0x180022876  test    rax, rax
0x180022879  jnz     short loc_1800228AF
0x18002287b  call    cs:__imp_GetLastError
0x180022881  mov     ebx, eax
0x180022883  test    eax, eax
0x180022885  jle     short loc_180022890
0x180022887  movzx   ebx, ax
0x18002288a  or      ebx, 80070000h
0x180022890  lea     rax, WPP_RECORDER_INITIALIZED
0x180022897  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002289e  jz      loc_1800229D1
0x1800228a4  mov     r9d, 17h
0x1800228aa  jmp     loc_180022724
0x1800228af  lea     rax, [rbp+0F0h+ProcessInformation]
0x1800228b3  mov     [rsp+1F0h+lpProcessInformation], rax; lpProcessInformation
0x1800228b8  lea     rax, [rbp+0F0h+StartupInfo]
0x1800228bc  mov     [rsp+1F0h+lpStartupInfo], rax; lpStartupInfo
0x1800228c1  mov     [rsp+1F0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800228ca  mov     rax, [rsp+1F0h+var_180]
0x1800228cf  mov     [rsp+1F0h+lpEnvironment], rax; lpEnvironment
0x1800228d4  mov     [rsp+1F0h+dwCreationFlags], 408h; dwCreationFlags
0x1800228dc  mov     [rsp+1F0h+bInheritHandles], 0; bInheritHandles
0x1800228e4  mov     [rsp+1F0h+lpThreadAttributes], 0; lpThreadAttributes
0x1800228ed  lea     r9, [rbp+0F0h+ProcessAttributes]; lpProcessAttributes
0x1800228f1  lea     r8, [rbp+0F0h+CommandLine]; lpCommandLine
0x1800228f5  lea     rdx, ApplicationName; "dashost.exe"
0x1800228fc  mov     rcx, [rsp+1F0h+hToken]; hToken
0x180022901  call    cs:__imp_CreateProcessAsUserW
0x180022907  test    eax, eax
0x180022909  jnz     short loc_18002293F
0x18002290b  call    cs:__imp_GetLastError
0x180022911  mov     ebx, eax
0x180022913  test    eax, eax
0x180022915  jle     short loc_180022920
0x180022917  movzx   ebx, ax
0x18002291a  or      ebx, 80070000h
0x180022920  lea     rax, WPP_RECORDER_INITIALIZED
0x180022927  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002292e  jz      loc_1800229D1
0x180022934  mov     r9d, 18h
0x18002293a  jmp     loc_180022724
0x18002293f  mov     rax, [rbp+0F0h+ProcessInformation.hProcess]
0x180022943  mov     [r14+8], rax
0x180022947  mov     rcx, [rbp+0F0h+ProcessInformation.hThread]; hObject
0x18002294b  call    cs:__imp_CloseHandle
0x180022951  xor     r8d, r8d; pftTimeout
0x180022954  mov     rdx, [r14+8]; h
0x180022958  mov     rcx, [r14+30h]; pwa
0x18002295c  call    cs:__imp_SetThreadpoolWait
0x180022962  mov     rcx, [rbp+0F0h+ProcessInformation.hProcess]; hToken
0x180022966  call    cs:__imp_ImpersonateLoggedOnUser
0x18002296c  test    eax, eax
0x18002296e  jz      short loc_1800229A0
0x180022970  call    cs:__imp_GetLastError
0x180022976  mov     ebx, eax
0x180022978  test    eax, eax
0x18002297a  jle     short loc_180022985
0x18002297c  movzx   ebx, ax
0x18002297f  or      ebx, 80070000h
0x180022985  lea     rax, WPP_RECORDER_INITIALIZED
0x18002298c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180022993  jz      short loc_1800229D1
0x180022995  mov     r9d, 19h
0x18002299b  jmp     loc_180022724
0x1800229a0  lea     rdx, [rbp+0F0h+var_98]; unsigned __int16 *
0x1800229a4  call    ?WaitUntilRpcIsReady@CHostContext@@IEAAJPEBG@Z; CHostContext::WaitUntilRpcIsReady(ushort const *)
0x1800229a9  mov     ebx, eax
0x1800229ab  call    cs:__imp_RevertToSelf
0x1800229b1  test    ebx, ebx
0x1800229b3  jnz     short loc_1800229D1
0x1800229b5  mov     r8, r14; void **
0x1800229b8  lea     rdx, [rbp+0F0h+var_98]; unsigned __int16 *
0x1800229bc  call    ?DasHostClientInitializeRpc@CHostContext@@IEAAJPEAGPEAPEAX@Z; CHostContext::DasHostClientInitializeRpc(ushort *,void * *)
0x1800229c1  mov     ebx, eax
0x1800229c3  test    eax, eax
0x1800229c5  js      short loc_1800229D1
0x1800229c7  mov     rcx, r14; this
0x1800229ca  call    ?CopyDasProcessHandle@CHostContext@@IEAAJXZ; CHostContext::CopyDasProcessHandle(void)
0x1800229cf  mov     ebx, eax
0x1800229d1  mov     rcx, r15; hObject
0x1800229d4  call    pSetupRestoreThreadPrivileges
0x1800229d9  mov     rcx, [rsp+1F0h+var_180]
0x1800229de  test    rcx, rcx
0x1800229e1  jz      short loc_1800229F2
0x1800229e3  call    cs:__imp_DestroyEnvBlock
0x1800229e9  mov     [rsp+1F0h+var_180], 0
0x1800229f2  cmp     [rbp+0F0h+ProcessAttributes.lpSecurityDescriptor], 0
0x1800229f7  jz      short loc_180022A0E
0x1800229f9  call    cs:__imp_GetProcessHeap
0x1800229ff  mov     rcx, rax; hHeap
0x180022a02  mov     r8, [rbp+0F0h+ProcessAttributes.lpSecurityDescriptor]; lpMem
0x180022a06  xor     edx, edx; dwFlags
0x180022a08  call    cs:__imp_HeapFree
0x180022a0e  mov     rcx, [rsp+1F0h+hToken]; hObject
0x180022a13  test    rcx, rcx
0x180022a16  jz      short loc_180022A1E
0x180022a18  call    cs:__imp_CloseHandle
0x180022a1e  mov     rcx, [rbp+0F0h+hMem]; hMem
0x180022a22  test    rcx, rcx
0x180022a25  jz      short loc_180022A2D
0x180022a27  call    cs:__imp_LocalFree
0x180022a2d  mov     eax, ebx
0x180022a2f  mov     rcx, [rbp+0F0h+var_40]
0x180022a36  xor     rcx, rsp; StackCookie
0x180022a39  call    __security_check_cookie
0x180022a3e  add     rsp, 1C8h
0x180022a45  pop     r15
0x180022a47  pop     r14
0x180022a49  pop     rdi
0x180022a4a  pop     rsi
0x180022a4b  pop     rbx
0x180022a4c  pop     rbp
0x180022a4d  retn
```
