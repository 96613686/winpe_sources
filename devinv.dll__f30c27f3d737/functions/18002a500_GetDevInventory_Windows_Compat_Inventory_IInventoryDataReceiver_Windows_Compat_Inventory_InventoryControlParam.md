# GetDevInventory(Windows::Compat::Inventory::IInventoryDataReceiver *,Windows::Compat::Inventory::InventoryControlParams *,char const *)

- ea: `0x18002a500`
- end: `0x18002a91a`
- name: `?GetDevInventory@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEAUInventoryControlParams@234@PEBD@Z`
- size: `1050`
- prototype: `__int64 __fastcall(struct Windows::Compat::Inventory::IInventoryDataReceiver *, struct Windows::Compat::Inventory::InventoryControlParams *, const char *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180027f40`

## callees

- `0x180005e40`
- `0x180006210`
- `0x180006ec4`
- `0x1800178f8`
- `0x180017cb8`
- `0x1800273e4`
- `0x180029b40`
- `0x180029efc`
- `0x18002a500`
- `0x18002d2d0`
- `0x18002db94`
- `0x180030ee8`
- `0x180031850`
- `0x180032160`
- `0x18003d8c0`
- `0x180066c10`
- `0x180069990`
- `0x180079de0`
- `0x18007a120`
- `0x18007a250`
- `0x18007a37c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002a585`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002a839`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002a585`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002a839`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002a5b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002a5b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002a539`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002a82d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002a539`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002a82d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002a695`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002a695`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18002a593`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18002a847`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18002a593`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18002a847`

## string_xrefs

- `0x18002a7c2`: `UpdateCache failed [%#x]`
- `0x18002a7b0`: `UpdateCache succeeded`
- `0x18002a7eb`: `Skipping scan, returning cached inventory`
- `0x18002a618`: `GetSystemDirectory failed %#x`
- `0x18002a5d9`: `GetInvModuleInPath failed %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetDevInventory(
        struct Windows::Compat::Inventory::IInventoryDataReceiver *a1,
        struct Windows::Compat::Inventory::InventoryControlParams *a2,
        const char *a3)
{
  int TickCount64; // r12d
  HANDLE CurrentThread; // rax
  int InvModuleInPath; // eax
  signed int v9; // edi
  int AdditionalInventory; // ebx
  signed int LastError; // eax
  unsigned int i; // edi
  Windows::Compat::Shared::Telemetry::TelemetryProvider *v13; // rcx
  bool v14; // dl
  __int64 v15; // rcx
  struct TraceLoggingCorrelationVector *v16; // rax
  struct TelCacheProvider *v17; // rcx
  __int64 v18; // rcx
  unsigned int v19; // edi
  HANDLE v20; // rax
  unsigned __int64 v21; // rdx
  int v22; // eax
  const char *v23; // rdx
  unsigned __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 CycleTime; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[80]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+A8h] [rbp-58h]
  __int16 v30; // [rsp+B0h] [rbp-50h]
  __int64 v31; // [rsp+B8h] [rbp-48h]
  __int128 v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+D0h] [rbp-30h]
  int v34; // [rsp+D8h] [rbp-28h]
  char v35; // [rsp+DCh] [rbp-24h]
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF

  TickCount64 = GetTickCount64();
  CycleTime = 0;
  v25 = 0;
  memset_0(v28, 0, 0x4Eu);
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v29 = 0;
  v27 = 0;
  CurrentThread = GetCurrentThread();
  QueryThreadCycleTime(CurrentThread, &CycleTime);
  memset_0(Buffer, 0, 0x208u);
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    AslLogCallPrintf(1, "GetInvIsSystemModule", 453, "GetSystemDirectory failed %#x", v9);
    AdditionalInventory = v9;
    if ( v9 < 0 )
      goto LABEL_51;
  }
  else
  {
    InvModuleInPath = GetInvModuleInPath(Buffer);
    v9 = InvModuleInPath;
    if ( InvModuleInPath < 0 )
    {
      AslLogCallPrintf(1, "GetInvIsSystemModule", 460, "GetInvModuleInPath failed %#x", InvModuleInPath);
      AdditionalInventory = v9;
      goto LABEL_51;
    }
    AdditionalInventory = InvModuleInPath;
  }
  if ( v9 != 1
    || (AdditionalInventory = TelCacheProvider::Initialize(&v27, L"InventoryDevicePnp", 0, 2, 3, 3, 0x64u),
        AdditionalInventory < 0) )
  {
LABEL_17:
    GetInvModuleVersion(a1);
    if ( (*((_DWORD *)a2 + 4) & 0xFFFFFFFC) != 0 )
      goto LABEL_42;
    if ( *((_DWORD *)a2 + 4) == 1 )
    {
LABEL_43:
      AdditionalInventory = GetAdditionalInventory(a1);
      if ( AdditionalInventory < 0 )
        goto LABEL_51;
LABEL_44:
      v19 = GetTickCount64() - TickCount64;
      v20 = GetCurrentThread();
      QueryThreadCycleTime(v20, &v25);
      v21 = (v25 - CycleTime) / 0x5F5E100;
      v22 = *((_DWORD *)a2 + 4);
      if ( v22 )
      {
        if ( v22 == 2 )
        {
          AslTelemetryTrackMetric(P, "Devinv_SetupDevices_Cpu_0.1gCycles", (unsigned int)v21);
          v23 = "Devinv_SetupDevices_Ms";
        }
        else
        {
          if ( v22 != 1 )
            goto LABEL_51;
          AslTelemetryTrackMetric(P, "Devinv_SetupSystem_Cpu_0.1gCycles", (unsigned int)v21);
          v23 = "Devinv_SetupSystem_Ms";
        }
      }
      else
      {
        AslTelemetryTrackMetric(P, "Devinv_Nightly_Cpu_0.1gCycles", (unsigned int)v21);
        v23 = "Devinv_Nightly_Ms";
      }
      AslTelemetryTrackMetric(P, v23, v19);
      goto LABEL_51;
    }
    Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(v13, *((_DWORD *)a2 + 5) == 1);
    SetDevInvDebugCorrelationVector(a3);
    if ( a3 )
    {
      if ( Block )
      {
        operator delete(Block);
        byte_1801559D8 = 0;
      }
      v16 = TraceLoggingCorrelationVector::Extend(a3, v14);
      Block = v16;
      if ( v16 )
        TraceLoggingCorrelationVector::ToString(v16, &byte_1801559D8);
    }
    LOBYTE(v15) = *((_DWORD *)a2 + 2) != 0;
    AdditionalInventory = DeviceMapInitializeTelemetryAndCache(v15);
    if ( AdditionalInventory < 0 )
      goto LABEL_51;
    if ( *((_DWORD *)a2 + 4) == 3
      || qword_180157118 && !(unsigned int)IsInventoryCacheFresh(v17) && !*((_DWORD *)a2 + 3) )
    {
      AslLogCallPrintf(3, "GetDevInventory", 730, "Skipping scan, returning cached inventory");
LABEL_41:
      AdditionalInventory = GetItemsFromCache(a1);
      if ( AdditionalInventory < 0 )
        goto LABEL_51;
LABEL_42:
      if ( *((_DWORD *)a2 + 4) > 1u )
        goto LABEL_44;
      goto LABEL_43;
    }
    if ( !*((_DWORD *)a2 + 3)
      || !*((_DWORD *)a2 + 2)
      || (AdditionalInventory = ClearDevinvCacheAndSendStartSyncs(), AdditionalInventory >= 0) )
    {
      if ( *((_DWORD *)a2 + 4) )
      {
        if ( *((_DWORD *)a2 + 4) != 2 )
        {
          AdditionalInventory = -2147024809;
          goto LABEL_39;
        }
        v18 = 4098;
      }
      else
      {
        v18 = 0x1000000;
      }
      AdditionalInventory = CreateDeviceInventory(v18, 0);
      if ( AdditionalInventory >= 0 )
      {
        AslLogCallPrintf(3, "GetDevInventory", 726, "UpdateCache succeeded");
        goto LABEL_41;
      }
    }
LABEL_39:
    AslLogCallPrintf(1, "GetDevInventory", 723, "UpdateCache failed [%#x]", AdditionalInventory);
    goto LABEL_51;
  }
  for ( i = 0; ; ++i )
  {
    AdditionalInventory = GetInvInboxRedirectImpl("GetDevInventory", a1, a2, a3);
    if ( !AdditionalInventory )
      break;
    if ( AdditionalInventory == 1 )
      goto LABEL_17;
    if ( AdditionalInventory >= 0 || i >= 0x28 )
      break;
    Sleep(0x7530u);
  }
LABEL_51:
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v27);
  return (unsigned int)AdditionalInventory;
}

```

## disassembly

```asm
0x18002a500  mov     [rsp-8+arg_18], rbx
0x18002a505  push    rbp
0x18002a506  push    rsi
0x18002a507  push    rdi
0x18002a508  push    r12
0x18002a50a  push    r13
0x18002a50c  push    r14
0x18002a50e  push    r15
0x18002a510  lea     rbp, [rsp-200h]
0x18002a518  sub     rsp, 300h
0x18002a51f  mov     rax, cs:__security_cookie
0x18002a526  xor     rax, rsp
0x18002a529  mov     [rbp+230h+var_40], rax
0x18002a530  mov     r14, r8
0x18002a533  mov     rsi, rdx
0x18002a536  mov     r15, rcx
0x18002a539  call    cs:__imp_GetTickCount64
0x18002a53f  mov     r12, rax
0x18002a542  xor     r13d, r13d
0x18002a545  mov     [rsp+330h+CycleTime], r13
0x18002a54a  mov     [rsp+330h+var_2F0], r13
0x18002a54f  xor     edx, edx; Val
0x18002a551  lea     r8d, [r13+4Eh]; Size
0x18002a555  lea     rcx, [rsp+330h+var_2D8]; void *
0x18002a55a  call    memset_0
0x18002a55f  mov     [rbp+230h+var_280], r13w
0x18002a564  mov     [rbp+230h+var_278], r13
0x18002a568  xorps   xmm0, xmm0
0x18002a56b  movdqa  [rbp+230h+var_270], xmm0
0x18002a570  mov     [rbp+230h+var_260], r13
0x18002a574  mov     [rbp+230h+var_258], r13d
0x18002a578  mov     [rbp+230h+var_254], r13b
0x18002a57c  mov     [rbp+230h+var_288], r13
0x18002a580  mov     [rsp+330h+var_2E0], r13
0x18002a585  call    cs:__imp_GetCurrentThread
0x18002a58b  mov     rcx, rax; ThreadHandle
0x18002a58e  lea     rdx, [rsp+330h+CycleTime]; CycleTime
0x18002a593  call    cs:__imp_QueryThreadCycleTime
0x18002a599  xor     edx, edx; Val
0x18002a59b  mov     r8d, 208h; Size
0x18002a5a1  lea     rcx, [rbp+230h+Buffer]; void *
0x18002a5a5  call    memset_0
0x18002a5aa  mov     edx, 104h; uSize
0x18002a5af  lea     rcx, [rbp+230h+Buffer]; lpBuffer
0x18002a5b3  call    cs:__imp_GetSystemDirectoryW
0x18002a5b9  dec     eax
0x18002a5bb  lea     ebx, [r13+1]
0x18002a5bf  cmp     eax, 102h
0x18002a5c4  ja      short loc_18002A5FF
0x18002a5c6  lea     rcx, [rbp+230h+Buffer]; pszFile2
0x18002a5ca  call    ?GetInvModuleInPath@@YAJPEBG@Z; GetInvModuleInPath(ushort const *)
0x18002a5cf  mov     edi, eax
0x18002a5d1  test    eax, eax
0x18002a5d3  jns     short loc_18002A5FB
0x18002a5d5  mov     [rsp+330h+var_310], eax
0x18002a5d9  lea     r9, aGetinvmodulein; "GetInvModuleInPath failed %#x"
0x18002a5e0  mov     r8d, 1CCh
0x18002a5e6  lea     rdx, aGetinvissystem; "GetInvIsSystemModule"
0x18002a5ed  mov     ecx, ebx
0x18002a5ef  call    AslLogCallPrintf
0x18002a5f4  mov     ebx, edi
0x18002a5f6  jmp     loc_18002A8E4
0x18002a5fb  mov     ebx, edi
0x18002a5fd  jmp     short loc_18002A63D
0x18002a5ff  call    cs:__imp_GetLastError
0x18002a605  mov     edi, eax
0x18002a607  test    eax, eax
0x18002a609  jle     short loc_18002A614
0x18002a60b  movzx   edi, ax
0x18002a60e  or      edi, 80070000h
0x18002a614  mov     [rsp+330h+var_310], edi
0x18002a618  lea     r9, aGetsystemdirec_0; "GetSystemDirectory failed %#x"
0x18002a61f  mov     r8d, 1C5h
0x18002a625  lea     rdx, aGetinvissystem; "GetInvIsSystemModule"
0x18002a62c  mov     ecx, ebx
0x18002a62e  call    AslLogCallPrintf
0x18002a633  mov     ebx, edi
0x18002a635  test    edi, edi
0x18002a637  js      loc_18002A8E4
0x18002a63d  mov     eax, 3
0x18002a642  cmp     edi, 1
0x18002a645  jnz     short loc_18002A6BD
0x18002a647  mov     [rsp+330h+var_300], 64h ; 'd'
0x18002a64f  mov     [rsp+330h+var_308], eax
0x18002a653  mov     [rsp+330h+var_310], eax
0x18002a657  lea     r9d, [rax-1]
0x18002a65b  xor     r8d, r8d
0x18002a65e  lea     rdx, aInventorydevic_5; "InventoryDevicePnp"
0x18002a665  lea     rcx, [rsp+330h+var_2E0]
0x18002a66a  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x18002a66f  mov     ebx, eax
0x18002a671  test    eax, eax
0x18002a673  js      short loc_18002A6BD
0x18002a675  mov     edi, r13d
0x18002a678  jmp     short loc_18002A69D
0x18002a67a  cmp     ebx, 1
0x18002a67d  jz      short loc_18002A6BD
0x18002a67f  test    ebx, ebx
0x18002a681  jns     loc_18002A8E4
0x18002a687  cmp     edi, 28h ; '('
0x18002a68a  jnb     loc_18002A8E4
0x18002a690  mov     ecx, 7530h; dwMilliseconds
0x18002a695  call    cs:__imp_Sleep
0x18002a69b  inc     edi
0x18002a69d  mov     r9, r14; char *
0x18002a6a0  mov     r8, rsi; struct Windows::Compat::Inventory::InventoryControlParams *
0x18002a6a3  mov     rdx, r15; struct Windows::Compat::Inventory::IInventoryDataReceiver *
0x18002a6a6  lea     rcx, aGetdevinventor_0; "GetDevInventory"
0x18002a6ad  call    ?GetInvInboxRedirectImpl@@YAJPEBDPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEAUInventoryControlParams@234@0@Z; GetInvInboxRedirectImpl(char const *,Windows::Compat::Inventory::IInventoryDataReceiver *,Windows::Compat::Inventory::InventoryControlParams *,char const *)
0x18002a6b2  test    eax, eax
0x18002a6b4  mov     ebx, eax
0x18002a6b6  jnz     short loc_18002A67A
0x18002a6b8  jmp     loc_18002A8E4
0x18002a6bd  mov     rcx, r15; struct Windows::Compat::Inventory::IInventoryDataReceiver *
0x18002a6c0  call    ?GetInvModuleVersion@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@@Z; GetInvModuleVersion(Windows::Compat::Inventory::IInventoryDataReceiver *)
0x18002a6c5  test    dword ptr [rsi+10h], 0FFFFFFFCh
0x18002a6cc  jnz     loc_18002A815
0x18002a6d2  cmp     dword ptr [rsi+10h], 1
0x18002a6d6  jz      loc_18002A81B
0x18002a6dc  cmp     dword ptr [rsi+14h], 1
0x18002a6e0  setz    dl; bool
0x18002a6e3  call    ?InitializeCoreProvider@TelemetryProvider@Telemetry@Shared@Compat@Windows@@IEAAX_N@Z; Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(bool)
0x18002a6e8  mov     rcx, r14
0x18002a6eb  call    SetDevInvDebugCorrelationVector
0x18002a6f0  test    r14, r14
0x18002a6f3  jz      short loc_18002A735
0x18002a6f5  mov     rcx, cs:Block; Block
0x18002a6fc  test    rcx, rcx
0x18002a6ff  jz      short loc_18002A712
0x18002a701  mov     edx, 90h
0x18002a706  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002a70b  mov     cs:byte_1801559D8, r13b
0x18002a712  mov     rcx, r14; char *
0x18002a715  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x18002a71a  mov     cs:Block, rax
0x18002a721  test    rax, rax
0x18002a724  jz      short loc_18002A735
0x18002a726  lea     rdx, byte_1801559D8; char *
0x18002a72d  mov     rcx, rax; this
0x18002a730  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x18002a735  cmp     [rsi+8], r13d
0x18002a739  setnz   cl
0x18002a73c  call    DeviceMapInitializeTelemetryAndCache
0x18002a741  mov     ebx, eax
0x18002a743  test    eax, eax
0x18002a745  js      loc_18002A8E4
0x18002a74b  cmp     dword ptr [rsi+10h], 3
0x18002a74f  jz      loc_18002A7E5
0x18002a755  cmp     cs:qword_180157118, r13
0x18002a75c  jz      short loc_18002A76D
0x18002a75e  call    ?IsInventoryCacheFresh@@YAJAEAVTelCacheProvider@@@Z; IsInventoryCacheFresh(TelCacheProvider &)
0x18002a763  test    eax, eax
0x18002a765  jnz     short loc_18002A76D
0x18002a767  cmp     [rsi+0Ch], r13d
0x18002a76b  jz      short loc_18002A7E5
0x18002a76d  cmp     [rsi+0Ch], r13d
0x18002a771  jz      short loc_18002A784
0x18002a773  cmp     [rsi+8], r13d
0x18002a777  jz      short loc_18002A784
0x18002a779  call    ?ClearDevinvCacheAndSendStartSyncs@@YAJXZ; ClearDevinvCacheAndSendStartSyncs(void)
0x18002a77e  mov     ebx, eax
0x18002a780  test    eax, eax
0x18002a782  js      short loc_18002A7BE
0x18002a784  cmp     [rsi+10h], r13d
0x18002a788  jnz     short loc_18002A791
0x18002a78a  mov     ecx, 1000000h
0x18002a78f  jmp     short loc_18002A79C
0x18002a791  cmp     dword ptr [rsi+10h], 2
0x18002a795  jnz     short loc_18002A7B9
0x18002a797  mov     ecx, 1002h
0x18002a79c  mov     rdx, r13
0x18002a79f  call    CreateDeviceInventory
0x18002a7a4  mov     ebx, eax
0x18002a7a6  test    eax, eax
0x18002a7a8  js      short loc_18002A7BE
0x18002a7aa  mov     r8d, 2D6h
0x18002a7b0  lea     r9, aUpdatecacheSuc; "UpdateCache succeeded"
0x18002a7b7  jmp     short loc_18002A7F2
0x18002a7b9  mov     ebx, 80070057h
0x18002a7be  mov     [rsp+330h+var_310], ebx
0x18002a7c2  lea     r9, aUpdatecacheFai; "UpdateCache failed [%#x]"
0x18002a7c9  mov     r8d, 2D3h
0x18002a7cf  lea     rdx, aGetdevinventor_0; "GetDevInventory"
0x18002a7d6  mov     ecx, 1
0x18002a7db  call    AslLogCallPrintf
0x18002a7e0  jmp     loc_18002A8E4
0x18002a7e5  mov     r8d, 2DAh
0x18002a7eb  lea     r9, aSkippingScanRe; "Skipping scan, returning cached invento"...
0x18002a7f2  lea     rdx, aGetdevinventor_0; "GetDevInventory"
0x18002a7f9  mov     ecx, 3
0x18002a7fe  call    AslLogCallPrintf
0x18002a803  mov     rcx, r15; struct Windows::Compat::Inventory::IInventoryDataReceiver *
0x18002a806  call    ?GetItemsFromCache@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@@Z; GetItemsFromCache(Windows::Compat::Inventory::IInventoryDataReceiver *)
0x18002a80b  mov     ebx, eax
0x18002a80d  test    eax, eax
0x18002a80f  js      loc_18002A8E4
0x18002a815  cmp     dword ptr [rsi+10h], 1
0x18002a819  ja      short loc_18002A82D
0x18002a81b  mov     rcx, r15; struct Windows::Compat::Inventory::IInventoryDataReceiver *
0x18002a81e  call    ?GetAdditionalInventory@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@@Z; GetAdditionalInventory(Windows::Compat::Inventory::IInventoryDataReceiver *)
0x18002a823  mov     ebx, eax
0x18002a825  test    eax, eax
0x18002a827  js      loc_18002A8E4
0x18002a82d  call    cs:__imp_GetTickCount64
0x18002a833  mov     rdi, rax
0x18002a836  sub     edi, r12d
0x18002a839  call    cs:__imp_GetCurrentThread
0x18002a83f  mov     rcx, rax; ThreadHandle
0x18002a842  lea     rdx, [rsp+330h+var_2F0]; CycleTime
0x18002a847  call    cs:__imp_QueryThreadCycleTime
0x18002a84d  mov     rcx, [rsp+330h+var_2F0]
0x18002a852  sub     rcx, [rsp+330h+CycleTime]
0x18002a857  mov     rax, 0ABCC77118461CEFDh
0x18002a861  mul     rcx
0x18002a864  shr     rdx, 1Ah
0x18002a868  mov     eax, [rsi+10h]
0x18002a86b  test    eax, eax
0x18002a86d  jnz     short loc_18002A88E
0x18002a86f  mov     r8d, edx
0x18002a872  lea     rdx, aDevinvNightlyC; "Devinv_Nightly_Cpu_0.1gCycles"
0x18002a879  mov     rcx, cs:P
0x18002a880  call    AslTelemetryTrackMetric
0x18002a885  lea     rdx, aDevinvNightlyM; "Devinv_Nightly_Ms"
0x18002a88c  jmp     short loc_18002A8D4
0x18002a88e  cmp     eax, 2
0x18002a891  jnz     short loc_18002A8B2
0x18002a893  mov     r8d, edx
0x18002a896  lea     rdx, aDevinvSetupdev; "Devinv_SetupDevices_Cpu_0.1gCycles"
0x18002a89d  mov     rcx, cs:P
0x18002a8a4  call    AslTelemetryTrackMetric
0x18002a8a9  lea     rdx, aDevinvSetupdev_0; "Devinv_SetupDevices_Ms"
0x18002a8b0  jmp     short loc_18002A8D4
0x18002a8b2  cmp     eax, 1
0x18002a8b5  jnz     short loc_18002A8E4
0x18002a8b7  mov     r8d, edx
0x18002a8ba  lea     rdx, aDevinvSetupsys_0; "Devinv_SetupSystem_Cpu_0.1gCycles"
0x18002a8c1  mov     rcx, cs:P
0x18002a8c8  call    AslTelemetryTrackMetric
0x18002a8cd  lea     rdx, aDevinvSetupsys; "Devinv_SetupSystem_Ms"
0x18002a8d4  mov     r8d, edi
0x18002a8d7  mov     rcx, cs:P
0x18002a8de  call    AslTelemetryTrackMetric
0x18002a8e3  nop
0x18002a8e4  lea     rcx, [rsp+330h+var_2E0]; this
0x18002a8e9  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x18002a8ee  mov     eax, ebx
0x18002a8f0  mov     rcx, [rbp+230h+var_40]
0x18002a8f7  xor     rcx, rsp; StackCookie
0x18002a8fa  call    __security_check_cookie
0x18002a8ff  mov     rbx, [rsp+330h+arg_18]
0x18002a907  add     rsp, 300h
0x18002a90e  pop     r15
0x18002a910  pop     r14
0x18002a912  pop     r13
0x18002a914  pop     r12
0x18002a916  pop     rdi
0x18002a917  pop     rsi
0x18002a918  pop     rbp
0x18002a919  retn
```
