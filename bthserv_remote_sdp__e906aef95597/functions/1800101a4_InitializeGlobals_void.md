# InitializeGlobals(void)

- ea: `0x1800101a4`
- end: `0x1800105d4`
- name: `?InitializeGlobals@@YAXXZ`
- size: `1072`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010f60`

## callees

- `0x180001b94`
- `0x18000ab30`
- `0x18000ab64`
- `0x1800101a4`
- `0x180012004`
- `0x1800120b8`
- `0x18001eb6c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180010415`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001043b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180010415`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001043b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010291`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010291`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800102e1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800102e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001046e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001046e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800104a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800104a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010576`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010576`

## string_xrefs

- `0x180010457`: `SYSTEM\CurrentControlSet\Services\BthServ\Parameters`

## pseudocode

```c
void InitializeGlobals(void)
{
  char v0; // bl
  char v1; // dl
  HANDLE EventW; // rax
  struct _TP_TIMER *ThreadpoolTimer; // rax
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *v4; // rcx
  char v5; // dl
  Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *v6; // rdi
  char v7; // dl
  HANDLE MutexW; // rax
  int v9; // edx
  int v10; // r8d
  unsigned int v11; // eax
  _BYTE *v12; // rcx
  char v13; // dl
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  int *v15; // [rsp+58h] [rbp-10h] BYREF
  int v16; // [rsp+A0h] [rbp+38h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+48h] BYREF
  unsigned int Data; // [rsp+B8h] [rbp+50h] BYREF

  Type = 4;
  hKey = 0;
  Data = 0;
  cbData = 4;
  v0 = 1;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v1 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
    v1 = 0;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v1,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  hModule = 0;
  dword_180046FD0 = 32;
  dword_180046FDC = 32;
  dword_180046FE8 = 32;
  *(_OWORD *)&pv = 0;
  qword_180046FC0 = 0;
  qword_180046FC8 = 0;
  qword_180046FD4 = 8;
  dword_180046FE0 = 1;
  dword_180046FE4 = 10;
  qword_180047028 = 0;
  hServiceStatus = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  hEvent = 0;
  Globals = EventW;
  *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode = 0;
  ServiceStatus.dwWaitHint = 0;
  xmmword_180047058 = 0;
  *(_OWORD *)&hObject = 0;
  *(_OWORD *)&ServiceStatus.dwServiceType = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(PolicyTimerCallback, 0, 0);
  v4 = qword_1800470F8;
  pti = ThreadpoolTimer;
  v16 = 0;
  qword_1800470F8 = 0;
  if ( v4 )
    (**(void (__fastcall ***)(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *, __int64))v4)(
      v4,
      1);
  v15 = &v16;
  v16 = wil::ResultFromException__lambda_c16bf91101c9118b5e2e61d840e8728a___(&v15);
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v5 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      v5 = 0;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  v6 = (Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *)qword_180047110;
  qword_180047110 = 0;
  if ( v6 )
  {
    Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::~BthServDeviceRefresher(v6);
    operator delete(v6, (const struct std::nothrow_t *)0x28);
  }
  LOBYTE(v16) = 0;
  if ( (int)wil::ResultFromException__lambda_55b676508b23d6fc517a7e1a7ea2e59f___(&v16) < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v7 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      v7 = 0;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  qword_180047088 = 0;
  qword_180047090 = 0;
  MutexW = CreateMutexW(0, 0, 0);
  dword_1800470A8 = 1;
  hMutex = MutexW;
  dword_1800470AC = 1;
  qword_1800470A0 = CreateMutexW(0, 0, 0);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BthServ\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"ChannelAvoidanceRange", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
    {
      v11 = Data;
      *(_DWORD *)&dword_1800470E4 = Data;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v9) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
      {
        LOBYTE(v9) = 0;
      }
      if ( !(_BYTE)v9 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, *((_QWORD *)WPP_GLOBAL_Control + 5));
      v11 = *(_DWORD *)&dword_1800470E4;
    }
    else
    {
      v11 = 0;
      *(_DWORD *)&dword_1800470E4 = 0;
    }
    v12 = WPP_GLOBAL_Control;
LABEL_37:
    if ( v11 > 0x3B )
    {
      if ( v12 == (_BYTE *)&WPP_GLOBAL_Control || (v13 = 1, v12[25] < 3u) )
        v13 = 0;
      if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_s(
          *((_QWORD *)v12 + 2),
          v13,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)v12 + 5));
      *(_DWORD *)&dword_1800470E4 = 0;
    }
    RegCloseKey(hKey);
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    v0 = 0;
  if ( v0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v0,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
}

```

## disassembly

```asm
0x1800101a4  push    rbp
0x1800101a6  push    rbx
0x1800101a7  push    rsi
0x1800101a8  push    rdi
0x1800101a9  push    r12
0x1800101ab  push    r15
0x1800101ad  mov     rbp, rsp
0x1800101b0  sub     rsp, 68h
0x1800101b4  xor     esi, esi
0x1800101b6  mov     [rbp+Type], 4
0x1800101bd  mov     [rbp+hKey], rsi
0x1800101c1  mov     [rbp+Data], esi
0x1800101c4  mov     [rbp+cbData], 4
0x1800101cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101d2  lea     r15, WPP_GLOBAL_Control
0x1800101d9  lea     ebx, [rsi+1]
0x1800101dc  cmp     rcx, r15
0x1800101df  jz      short loc_1800101E9
0x1800101e1  cmp     byte ptr [rcx+19h], 5
0x1800101e5  mov     dl, bl
0x1800101e7  jnb     short loc_1800101EC
0x1800101e9  mov     dl, sil
0x1800101ec  lea     r12, WPP_RECORDER_INITIALIZED
0x1800101f3  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800101fa  lea     rdi, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x180010201  setnz   r8b
0x180010205  test    dl, dl
0x180010207  jnz     short loc_18001020E
0x180010209  test    r8b, r8b
0x18001020c  jz      short loc_180010227
0x18001020e  mov     r9, [rcx+28h]
0x180010212  mov     rcx, [rcx+10h]
0x180010216  mov     [rsp+68h+var_30], rdi
0x18001021b  mov     [rsp+68h+var_38], 14h
0x180010222  call    WPP_RECORDER_AND_TRACE_SF_s
0x180010227  mov     eax, 20h ; ' '
0x18001022c  mov     cs:hModule, rsi
0x180010233  xorps   xmm0, xmm0
0x180010236  mov     cs:dword_180046FD0, eax
0x18001023c  xor     r9d, r9d; lpName
0x18001023f  mov     cs:dword_180046FDC, eax
0x180010245  xor     r8d, r8d; bInitialState
0x180010248  mov     cs:dword_180046FE8, eax
0x18001024e  mov     edx, ebx; bManualReset
0x180010250  movdqa  cs:pv, xmm0
0x180010258  xor     ecx, ecx; lpEventAttributes
0x18001025a  mov     cs:qword_180046FC0, rsi
0x180010261  mov     cs:qword_180046FC8, rsi
0x180010268  mov     cs:qword_180046FD4, 8
0x180010273  mov     cs:dword_180046FE0, ebx
0x180010279  mov     cs:dword_180046FE4, 0Ah
0x180010283  mov     cs:qword_180047028, rsi
0x18001028a  mov     cs:hServiceStatus, rsi
0x180010291  call    cs:__imp_CreateEventW
0x180010298  nop     dword ptr [rax+rax+00h]
0x18001029d  xorps   xmm0, xmm0
0x1800102a0  mov     cs:hEvent, rsi
0x1800102a7  mov     cs:?Globals@@3VBthServGlobals@@A, rax; BthServGlobals Globals
0x1800102ae  lea     rcx, ?PolicyTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800102b5  xor     eax, eax
0x1800102b7  xorps   xmm1, xmm1
0x1800102ba  xor     r8d, r8d; pcbe
0x1800102bd  mov     qword ptr cs:ServiceStatus.dwServiceSpecificExitCode, rax
0x1800102c4  xor     edx, edx; pv
0x1800102c6  mov     cs:ServiceStatus.dwWaitHint, eax
0x1800102cc  movups  cs:xmmword_180047058, xmm0
0x1800102d3  movups  cs:hObject, xmm1
0x1800102da  movups  xmmword ptr cs:ServiceStatus.dwServiceType, xmm0
0x1800102e1  call    cs:__imp_CreateThreadpoolTimer
0x1800102e8  nop     dword ptr [rax+rax+00h]
0x1800102ed  mov     rcx, cs:qword_1800470F8
0x1800102f4  mov     cs:pti, rax
0x1800102fb  mov     [rbp+arg_0], esi
0x1800102fe  mov     cs:qword_1800470F8, rsi
0x180010305  test    rcx, rcx
0x180010308  jz      short loc_180010317
0x18001030a  mov     rax, [rcx]
0x18001030d  mov     edx, ebx
0x18001030f  mov     rax, [rax]
0x180010312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010317  lea     rax, [rbp+arg_0]
0x18001031b  lea     rcx, [rbp+var_10]
0x18001031f  mov     [rbp+var_10], rax
0x180010323  call    wil__ResultFromException__lambda_c16bf91101c9118b5e2e61d840e8728a___
0x180010328  mov     [rbp+arg_0], eax
0x18001032b  test    eax, eax
0x18001032d  jns     short loc_180010373
0x18001032f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010336  cmp     rcx, r15
0x180010339  jz      short loc_180010343
0x18001033b  cmp     byte ptr [rcx+19h], 3
0x18001033f  mov     dl, bl
0x180010341  jnb     short loc_180010346
0x180010343  mov     dl, sil
0x180010346  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001034d  setnz   r8b
0x180010351  test    dl, dl
0x180010353  jnz     short loc_18001035A
0x180010355  test    r8b, r8b
0x180010358  jz      short loc_180010373
0x18001035a  mov     r9, [rcx+28h]
0x18001035e  mov     rcx, [rcx+10h]
0x180010362  mov     [rsp+68h+var_30], rdi
0x180010367  mov     [rsp+68h+var_38], 15h
0x18001036e  call    WPP_RECORDER_AND_TRACE_SF_s
0x180010373  mov     rdi, cs:qword_180047110
0x18001037a  mov     cs:qword_180047110, rsi
0x180010381  test    rdi, rdi
0x180010384  jz      short loc_18001039B
0x180010386  mov     rcx, rdi; this
0x180010389  call    ??1BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@QEAA@XZ; Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::~BthServDeviceRefresher(void)
0x18001038e  mov     edx, 28h ; '('; struct std::nothrow_t *
0x180010393  mov     rcx, rdi; void *
0x180010396  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001039b  lea     rcx, [rbp+arg_0]
0x18001039f  mov     byte ptr [rbp+arg_0], sil
0x1800103a3  call    wil__ResultFromException__lambda_55b676508b23d6fc517a7e1a7ea2e59f___
0x1800103a8  test    eax, eax
0x1800103aa  jns     short loc_1800103F9
0x1800103ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103b3  cmp     rcx, r15
0x1800103b6  jz      short loc_1800103C0
0x1800103b8  cmp     byte ptr [rcx+19h], 3
0x1800103bc  mov     dl, bl
0x1800103be  jnb     short loc_1800103C3
0x1800103c0  mov     dl, sil
0x1800103c3  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800103ca  setnz   r8b
0x1800103ce  test    dl, dl
0x1800103d0  jnz     short loc_1800103D7
0x1800103d2  test    r8b, r8b
0x1800103d5  jz      short loc_1800103F9
0x1800103d7  mov     r9, [rcx+28h]
0x1800103db  lea     rdi, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x1800103e2  mov     rcx, [rcx+10h]
0x1800103e6  mov     [rsp+68h+var_30], rdi
0x1800103eb  mov     [rsp+68h+var_38], 16h
0x1800103f2  call    WPP_RECORDER_AND_TRACE_SF_s
0x1800103f7  jmp     short loc_180010400
0x1800103f9  lea     rdi, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x180010400  xor     r8d, r8d; lpName
0x180010403  mov     cs:qword_180047088, rsi
0x18001040a  xor     edx, edx; bInitialOwner
0x18001040c  mov     cs:qword_180047090, rsi
0x180010413  xor     ecx, ecx; lpMutexAttributes
0x180010415  call    cs:__imp_CreateMutexW
0x18001041c  nop     dword ptr [rax+rax+00h]
0x180010421  xor     r8d, r8d; lpName
0x180010424  mov     cs:dword_1800470A8, ebx
0x18001042a  xor     edx, edx; bInitialOwner
0x18001042c  mov     cs:hMutex, rax
0x180010433  xor     ecx, ecx; lpMutexAttributes
0x180010435  mov     cs:dword_1800470AC, ebx
0x18001043b  call    cs:__imp_CreateMutexW
0x180010442  nop     dword ptr [rax+rax+00h]
0x180010447  mov     cs:qword_1800470A0, rax
0x18001044e  mov     r9d, 20019h; samDesired
0x180010454  xor     r8d, r8d; ulOptions
0x180010457  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Bt"...
0x18001045e  lea     rax, [rbp+hKey]
0x180010462  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010469  mov     [rsp+68h+phkResult], rax; phkResult
0x18001046e  call    cs:__imp_RegOpenKeyExW
0x180010475  nop     dword ptr [rax+rax+00h]
0x18001047a  test    eax, eax
0x18001047c  jnz     loc_180010582
0x180010482  mov     rcx, [rbp+hKey]; hKey
0x180010486  lea     rax, [rbp+cbData]
0x18001048a  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18001048f  lea     r9, [rbp+Type]; lpType
0x180010493  lea     rax, [rbp+Data]
0x180010497  xor     r8d, r8d; lpReserved
0x18001049a  lea     rdx, aChannelavoidan; "ChannelAvoidanceRange"
0x1800104a1  mov     [rsp+68h+phkResult], rax; lpData
0x1800104a6  call    cs:__imp_RegQueryValueExW
0x1800104ad  nop     dword ptr [rax+rax+00h]
0x1800104b2  test    eax, eax
0x1800104b4  jnz     short loc_18001051B
0x1800104b6  cmp     [rbp+Type], 4
0x1800104ba  jnz     short loc_18001051B
0x1800104bc  cmp     [rbp+cbData], 4
0x1800104c0  jnz     short loc_18001051B
0x1800104c2  mov     eax, [rbp+Data]
0x1800104c5  mov     cs:dword_1800470E4, eax
0x1800104cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104d2  cmp     rcx, r15
0x1800104d5  jz      short loc_1800104DF
0x1800104d7  cmp     byte ptr [rcx+19h], 4
0x1800104db  mov     dl, bl
0x1800104dd  jnb     short loc_1800104E2
0x1800104df  mov     dl, sil
0x1800104e2  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800104e9  setnz   r8b
0x1800104ed  test    dl, dl
0x1800104ef  jnz     short loc_1800104F6
0x1800104f1  test    r8b, r8b
0x1800104f4  jz      short loc_18001052A
0x1800104f6  mov     r9, [rcx+28h]
0x1800104fa  mov     rcx, [rcx+10h]
0x1800104fe  mov     [rsp+68h+var_20], eax
0x180010502  mov     [rsp+68h+var_30], rdi
0x180010507  mov     [rsp+68h+var_38], 17h
0x18001050e  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180010513  mov     eax, cs:dword_1800470E4
0x180010519  jmp     short loc_180010523
0x18001051b  mov     eax, esi
0x18001051d  mov     cs:dword_1800470E4, eax
0x180010523  mov     rcx, cs:WPP_GLOBAL_Control
0x18001052a  cmp     eax, 3Bh ; ';'
0x18001052d  jbe     short loc_180010572
0x18001052f  cmp     rcx, r15
0x180010532  jz      short loc_18001053C
0x180010534  cmp     byte ptr [rcx+19h], 3
0x180010538  mov     dl, bl
0x18001053a  jnb     short loc_18001053F
0x18001053c  mov     dl, sil
0x18001053f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180010546  setnz   r8b
0x18001054a  test    dl, dl
0x18001054c  jnz     short loc_180010553
0x18001054e  test    r8b, r8b
0x180010551  jz      short loc_18001056C
0x180010553  mov     r9, [rcx+28h]
0x180010557  mov     rcx, [rcx+10h]
0x18001055b  mov     [rsp+68h+var_30], rdi
0x180010560  mov     [rsp+68h+var_38], 18h
0x180010567  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001056c  mov     cs:dword_1800470E4, esi
0x180010572  mov     rcx, [rbp+hKey]; hKey
0x180010576  call    cs:__imp_RegCloseKey
0x18001057d  nop     dword ptr [rax+rax+00h]
0x180010582  mov     rcx, cs:WPP_GLOBAL_Control
0x180010589  cmp     rcx, r15
0x18001058c  jz      short loc_180010594
0x18001058e  cmp     byte ptr [rcx+19h], 5
0x180010592  jnb     short loc_180010597
0x180010594  mov     bl, sil
0x180010597  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001059e  setnz   r8b
0x1800105a2  test    bl, bl
0x1800105a4  jnz     short loc_1800105AB
0x1800105a6  test    r8b, r8b
0x1800105a9  jz      short loc_1800105C6
0x1800105ab  mov     r9, [rcx+28h]
0x1800105af  mov     dl, bl
0x1800105b1  mov     rcx, [rcx+10h]
0x1800105b5  mov     [rsp+68h+var_30], rdi
0x1800105ba  mov     [rsp+68h+var_38], 19h
0x1800105c1  call    WPP_RECORDER_AND_TRACE_SF_s
0x1800105c6  add     rsp, 68h
0x1800105ca  pop     r15
0x1800105cc  pop     r12
0x1800105ce  pop     rdi
0x1800105cf  pop     rsi
0x1800105d0  pop     rbx
0x1800105d1  pop     rbp
0x1800105d2  retn
```
