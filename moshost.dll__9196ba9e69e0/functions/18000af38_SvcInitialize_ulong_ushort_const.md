# SvcInitialize(ulong,ushort * * const)

- ea: `0x18000af38`
- end: `0x18000b304`
- name: `?SvcInitialize@@YAJKQEAPEAG@Z`
- size: `972`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000b720`

## callees

- `0x180001d00`
- `0x180002722`
- `0x180007298`
- `0x18000a6a4`
- `0x18000ac7c`
- `0x18000af38`
- `0x18000c12c`
- `0x18000c368`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b002`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b01c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b002`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b01c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b24b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b24b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b12a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b22c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b12a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b22c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b030`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b030`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000b057`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000b057`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b0ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b0ad`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b041`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b041`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000b25b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000b25b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000b217`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000b217`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000b23a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000b23a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b17c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b17c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b243`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b243`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b1ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b1ae`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000b27f`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000b27f`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000b071`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000b154`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000b071`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000b154`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000afca`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b112`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b2db`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000afca`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b112`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b2db`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x18000afe3`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x18000afe3`

## string_xrefs

- `0x18000b109`: `MapsBackgroundTransferRegisterComServer`
- `0x18000b261`: `[MosHost] Service - Startup - SvcInitialize - using idle timeout: %d seconds`

## pseudocode

```c
__int64 __fastcall SvcInitialize(unsigned int a1, unsigned __int16 **const a2)
{
  __int64 v4; // rcx
  int VolatileRegistryLocation; // eax
  int v6; // r8d
  int v7; // eax
  DWORD dwLowDateTime; // r15d
  bool v9; // di
  int v10; // ebx
  BOOL v11; // esi
  int IsAnyOperationPending; // eax
  HRESULT Instance; // eax
  int v14; // r8d
  int v15; // r8d
  signed int LastError; // eax
  unsigned int v18; // edi
  PTP_WORK ThreadpoolWork; // rax
  struct _TP_WORK *v20; // r14
  struct _TP_WORK *v21; // rsi
  DWORD v22; // ebx
  __int64 v23; // rcx
  bool v25; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME pftDueTime; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  v25 = 0;
  pftDueTime.dwLowDateTime = 0;
  memset_0(SubKey, 0, 0x208u);
  VolatileRegistryLocation = RegUtils::GetVolatileRegistryLocation(v4, SubKey);
  if ( VolatileRegistryLocation < 0 )
  {
    v6 = 824;
  }
  else
  {
    VolatileRegistryLocation = RegUtils::GetRegDword(SubKey, L"IdleTimeoutInSeconds", 0xAu, (unsigned int *)&pftDueTime);
    if ( VolatileRegistryLocation >= 0 )
      goto LABEL_7;
    v6 = 830;
  }
  v7 = ZTraceReportPropagationNoThis(VolatileRegistryLocation, "RegUtils::GetMapsVolatileRegDword", v6);
  if ( v7 < 0 )
    ZTraceReportIgnoreNoThis(v7, "GetIdleTimeoutInSeconds", 100);
LABEL_7:
  dwLowDateTime = pftDueTime.dwLowDateTime;
  if ( a1 >= 2 && !(unsigned int)_o__wcsicmp(a2[1], L"debug") )
  {
    v9 = a1 >= 3 && !(unsigned int)_o__wcsicmp(a2[2], L"breakOnStartup");
    v10 = 0;
    while ( 1 )
    {
      v11 = IsDebuggerPresent();
      if ( !v11 )
        Sleep(0x3E8u);
      if ( (unsigned int)++v10 >= 0x3C )
        break;
      if ( v11 )
      {
        if ( v9 )
          DebugBreak();
        goto LABEL_21;
      }
    }
    IsAnyOperationPending = ZTraceReportOriginationNoThis(-2147023436, "WaitForDebugger", 121);
    if ( IsAnyOperationPending >= 0 )
    {
LABEL_21:
      dwLowDateTime = 600;
      goto LABEL_22;
    }
    v15 = 337;
    return (unsigned int)ZTraceReportPropagationNoThis(IsAnyOperationPending, "SvcInitialize", v15);
  }
LABEL_22:
  if ( ppv )
    __int2c();
  Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, &ppv);
  if ( Instance < 0 )
  {
    v14 = 69;
  }
  else
  {
    Instance = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 RegisterClassFactory,
                 0,
                 &IID_IContextCallback,
                 5,
                 0);
    if ( Instance >= 0 )
      goto LABEL_30;
    v14 = 71;
  }
  IsAnyOperationPending = ZTraceReportPropagationNoThis(Instance, "MapsBackgroundTransferRegisterComServer", v14);
  if ( IsAnyOperationPending < 0 )
  {
    v15 = 343;
    return (unsigned int)ZTraceReportPropagationNoThis(IsAnyOperationPending, "SvcInitialize", v15);
  }
LABEL_30:
  if ( pti )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    return (unsigned int)ZTraceReportOriginationNoThis(LastError, "SvcInitialize", 346);
  }
  dword_1800186E8 = dwLowDateTime;
  dword_1800185D8 = 0;
  pti = CreateThreadpoolTimer(anonymous_namespace_::TimerCallback, 0, 0);
  pftDueTime = (struct _FILETIME)-(__int64)(unsigned int)(10000000 * dword_1800186E8);
  SetThreadpoolTimer(pti, &pftDueTime, 0, 100 * dword_1800186E8);
  IsAnyOperationPending = AllowUnmarshalerCLSID(L"{a5183349-82de-4bfc-9c13-7d9dc578729c}");
  if ( IsAnyOperationPending < 0 )
  {
    v15 = 348;
    return (unsigned int)ZTraceReportPropagationNoThis(IsAnyOperationPending, "SvcInitialize", v15);
  }
  IsAnyOperationPending = AllowUnmarshalerCLSID(L"{be88f957-42cc-4da7-92cf-9bc35c5d5ee2}");
  if ( IsAnyOperationPending < 0 )
  {
    v15 = 349;
    return (unsigned int)ZTraceReportPropagationNoThis(IsAnyOperationPending, "SvcInitialize", v15);
  }
  IsAnyOperationPending = AllowUnmarshalerCLSID(L"{ccc63ae1-56a5-4f9c-abe8-e55674f0c0a6}");
  if ( IsAnyOperationPending < 0 )
  {
    v15 = 350;
    return (unsigned int)ZTraceReportPropagationNoThis(IsAnyOperationPending, "SvcInitialize", v15);
  }
  IsAnyOperationPending = ServiceManager_IsAnyOperationPending(&v25);
  if ( IsAnyOperationPending < 0 )
  {
    v15 = 352;
    return (unsigned int)ZTraceReportPropagationNoThis(IsAnyOperationPending, "SvcInitialize", v15);
  }
  v18 = 0;
  if ( v25 )
  {
    ThreadpoolWork = CreateThreadpoolWork(lambda_ca3332a445b0f585815e028b4e5c30a8_::_lambda_invoker_cdecl_, 0, 0);
    v20 = pwk;
    v21 = ThreadpoolWork;
    if ( pwk )
    {
      v22 = GetLastError();
      WaitForThreadpoolWorkCallbacks(v20, 1);
      CloseThreadpoolWork(v20);
      SetLastError(v22);
    }
    pwk = v21;
    SubmitThreadpoolWork(v21);
  }
  ZTraceHelperNoThis(
    3,
    "SvcInitialize",
    377,
    "[MosHost] Service - Startup - SvcInitialize - using idle timeout: %d seconds",
    dwLowDateTime);
  if ( (Microsoft_Windows_MosHostEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v23, ServiceStart);
  return v18;
}

```

## disassembly

```asm
0x18000af38  push    rbp
0x18000af3a  push    rbx
0x18000af3b  push    rsi
0x18000af3c  push    rdi
0x18000af3d  push    r14
0x18000af3f  push    r15
0x18000af41  lea     rbp, [rsp-188h]
0x18000af49  sub     rsp, 288h
0x18000af50  mov     rax, cs:__security_cookie
0x18000af57  xor     rax, rsp
0x18000af5a  mov     [rbp+1B0h+var_40], rax
0x18000af61  mov     rdi, rdx
0x18000af64  mov     [rsp+2B0h+var_270], 0
0x18000af69  mov     ebx, ecx
0x18000af6b  mov     [rsp+2B0h+pftDueTime.dwLowDateTime], 0
0x18000af73  xor     edx, edx; Val
0x18000af75  lea     rcx, [rsp+2B0h+SubKey]; void *
0x18000af7a  mov     r8d, 208h; Size
0x18000af80  call    memset_0
0x18000af85  lea     rdx, [rsp+2B0h+SubKey]
0x18000af8a  call    ?GetVolatileRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetVolatileRegistryLocation(MapsRegKeys,ushort *,ulong)
0x18000af8f  test    eax, eax
0x18000af91  js      short loc_18000AFBB
0x18000af93  lea     r9, [rsp+2B0h+pftDueTime]; unsigned int *
0x18000af98  mov     r8d, 0Ah; unsigned int
0x18000af9e  lea     rdx, aIdletimeoutins; "IdleTimeoutInSeconds"
0x18000afa5  lea     rcx, [rsp+2B0h+SubKey]; lpSubKey
0x18000afaa  call    ?GetRegDword@RegUtils@@SAJPEBG0KPEAK@Z; RegUtils::GetRegDword(ushort const *,ushort const *,ulong,ulong *)
0x18000afaf  test    eax, eax
0x18000afb1  jns     short loc_18000AFE9
0x18000afb3  mov     r8d, 33Eh
0x18000afb9  jmp     short loc_18000AFC1
0x18000afbb  mov     r8d, 338h
0x18000afc1  lea     rdx, aRegutilsGetmap; "RegUtils::GetMapsVolatileRegDword"
0x18000afc8  mov     ecx, eax
0x18000afca  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000afd0  test    eax, eax
0x18000afd2  jns     short loc_18000AFE9
0x18000afd4  mov     r8d, 64h ; 'd'
0x18000afda  lea     rdx, aGetidletimeout; "GetIdleTimeoutInSeconds"
0x18000afe1  mov     ecx, eax
0x18000afe3  call    cs:__imp_?ZTraceReportIgnoreNoThis@@YAXHPEBDH@Z; ZTraceReportIgnoreNoThis(int,char const *,int)
0x18000afe9  mov     r15d, [rsp+2B0h+pftDueTime.dwLowDateTime]
0x18000afee  cmp     ebx, 2
0x18000aff1  jb      loc_18000B081
0x18000aff7  mov     rcx, [rdi+8]
0x18000affb  lea     rdx, aDebug; "debug"
0x18000b002  call    cs:__imp__o__wcsicmp
0x18000b008  test    eax, eax
0x18000b00a  jnz     short loc_18000B081
0x18000b00c  cmp     ebx, 3
0x18000b00f  jb      short loc_18000B02B
0x18000b011  mov     rcx, [rdi+10h]
0x18000b015  lea     rdx, aBreakonstartup; "breakOnStartup"
0x18000b01c  call    cs:__imp__o__wcsicmp
0x18000b022  test    eax, eax
0x18000b024  jnz     short loc_18000B02B
0x18000b026  mov     dil, 1
0x18000b029  jmp     short loc_18000B02E
0x18000b02b  xor     dil, dil
0x18000b02e  xor     ebx, ebx
0x18000b030  call    cs:__imp_IsDebuggerPresent
0x18000b036  mov     esi, eax
0x18000b038  test    eax, eax
0x18000b03a  jnz     short loc_18000B047
0x18000b03c  mov     ecx, 3E8h; dwMilliseconds
0x18000b041  call    cs:__imp_Sleep
0x18000b047  inc     ebx
0x18000b049  cmp     ebx, 3Ch ; '<'
0x18000b04c  jnb     short loc_18000B05F
0x18000b04e  test    esi, esi
0x18000b050  jz      short loc_18000B030
0x18000b052  test    dil, dil
0x18000b055  jz      short loc_18000B07B
0x18000b057  call    cs:__imp_DebugBreak
0x18000b05d  jmp     short loc_18000B07B
0x18000b05f  mov     r8d, 79h ; 'y'
0x18000b065  lea     rdx, aWaitfordebugge; "WaitForDebugger"
0x18000b06c  mov     ecx, 800705B4h
0x18000b071  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000b077  test    eax, eax
0x18000b079  js      short loc_18000B0F8
0x18000b07b  mov     r15d, 258h
0x18000b081  cmp     cs:ppv, 0
0x18000b089  jz      short loc_18000B08D
0x18000b08b  int     2Ch; Windows NT - assertion failure
0x18000b08d  xor     edx, edx; pUnkOuter
0x18000b08f  lea     rax, ppv
0x18000b096  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18000b09d  mov     [rsp+2B0h+ppv], rax; ppv
0x18000b0a2  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18000b0a9  lea     r8d, [rdx+1]; dwClsContext
0x18000b0ad  call    cs:__imp_CoCreateInstance
0x18000b0b3  test    eax, eax
0x18000b0b5  js      short loc_18000B103
0x18000b0b7  mov     rcx, cs:ppv
0x18000b0be  lea     r9, IID_IContextCallback
0x18000b0c5  mov     [rsp+2B0h+var_288], 0
0x18000b0ce  lea     rdx, RegisterClassFactory
0x18000b0d5  xor     r8d, r8d
0x18000b0d8  mov     dword ptr [rsp+2B0h+ppv], 5
0x18000b0e0  mov     rax, [rcx]
0x18000b0e3  mov     rax, [rax+18h]
0x18000b0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0ec  test    eax, eax
0x18000b0ee  jns     short loc_18000B120
0x18000b0f0  mov     r8d, 47h ; 'G'
0x18000b0f6  jmp     short loc_18000B109
0x18000b0f8  mov     r8d, 151h
0x18000b0fe  jmp     loc_18000B2D2
0x18000b103  mov     r8d, 45h ; 'E'
0x18000b109  lea     rdx, aMapsbackground_0; "MapsBackgroundTransferRegisterComServer"
0x18000b110  mov     ecx, eax
0x18000b112  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000b118  test    eax, eax
0x18000b11a  js      loc_18000B2CC
0x18000b120  cmp     cs:pti, 0
0x18000b128  jz      short loc_18000B15F
0x18000b12a  call    cs:__imp_GetLastError
0x18000b130  test    eax, eax
0x18000b132  jz      short loc_18000B140
0x18000b134  jle     short loc_18000B145
0x18000b136  movzx   eax, ax
0x18000b139  or      eax, 80070000h
0x18000b13e  jmp     short loc_18000B145
0x18000b140  mov     eax, 80390004h
0x18000b145  mov     r8d, 15Ah
0x18000b14b  lea     rdx, aSvcinitialize; "SvcInitialize"
0x18000b152  mov     ecx, eax
0x18000b154  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000b15a  jmp     loc_18000B2E1
0x18000b15f  mov     cs:dword_1800186E8, r15d
0x18000b166  lea     rcx, _anonymous_namespace___TimerCallback; pfnti
0x18000b16d  xor     r8d, r8d; pcbe
0x18000b170  mov     cs:dword_1800185D8, 0
0x18000b17a  xor     edx, edx; pv
0x18000b17c  call    cs:__imp_CreateThreadpoolTimer
0x18000b182  imul    edx, cs:dword_1800186E8, 989680h
0x18000b18c  xor     r8d, r8d; msPeriod
0x18000b18f  imul    r9d, cs:dword_1800186E8, 64h ; 'd'; msWindowLength
0x18000b197  mov     rcx, rax; pti
0x18000b19a  mov     cs:pti, rax
0x18000b1a1  neg     rdx
0x18000b1a4  mov     qword ptr [rsp+2B0h+pftDueTime.dwLowDateTime], rdx
0x18000b1a9  lea     rdx, [rsp+2B0h+pftDueTime]; pftDueTime
0x18000b1ae  call    cs:__imp_SetThreadpoolTimer
0x18000b1b4  lea     rcx, aA518334982de4b; "{a5183349-82de-4bfc-9c13-7d9dc578729c}"
0x18000b1bb  call    ?AllowUnmarshalerCLSID@@YAJPEBG@Z; AllowUnmarshalerCLSID(ushort const *)
0x18000b1c0  test    eax, eax
0x18000b1c2  js      loc_18000B2C4
0x18000b1c8  lea     rcx, aBe88f95742cc4d; "{be88f957-42cc-4da7-92cf-9bc35c5d5ee2}"
0x18000b1cf  call    ?AllowUnmarshalerCLSID@@YAJPEBG@Z; AllowUnmarshalerCLSID(ushort const *)
0x18000b1d4  test    eax, eax
0x18000b1d6  js      loc_18000B2BC
0x18000b1dc  lea     rcx, aCcc63ae156a54f; "{ccc63ae1-56a5-4f9c-abe8-e55674f0c0a6}"
0x18000b1e3  call    ?AllowUnmarshalerCLSID@@YAJPEBG@Z; AllowUnmarshalerCLSID(ushort const *)
0x18000b1e8  test    eax, eax
0x18000b1ea  js      loc_18000B2B4
0x18000b1f0  lea     rcx, [rsp+2B0h+var_270]; bool *
0x18000b1f5  call    ?ServiceManager_IsAnyOperationPending@@YAJPEA_N@Z; ServiceManager_IsAnyOperationPending(bool *)
0x18000b1fa  test    eax, eax
0x18000b1fc  js      loc_18000B2AC
0x18000b202  xor     edi, edi
0x18000b204  cmp     [rsp+2B0h+var_270], dil
0x18000b209  jz      short loc_18000B261
0x18000b20b  xor     r8d, r8d; pcbe
0x18000b20e  lea     rcx, _lambda_ca3332a445b0f585815e028b4e5c30a8____lambda_invoker_cdecl_; pfnwk
0x18000b215  xor     edx, edx; pv
0x18000b217  call    cs:__imp_CreateThreadpoolWork
0x18000b21d  mov     r14, cs:pwk
0x18000b224  mov     rsi, rax
0x18000b227  test    r14, r14
0x18000b22a  jz      short loc_18000B251
0x18000b22c  call    cs:__imp_GetLastError
0x18000b232  lea     edx, [rdi+1]; fCancelPendingCallbacks
0x18000b235  mov     rcx, r14; pwk
0x18000b238  mov     ebx, eax
0x18000b23a  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000b240  mov     rcx, r14; pwk
0x18000b243  call    cs:__imp_CloseThreadpoolWork
0x18000b249  mov     ecx, ebx; dwErrCode
0x18000b24b  call    cs:__imp_SetLastError
0x18000b251  mov     rcx, rsi; pwk
0x18000b254  mov     cs:pwk, rsi
0x18000b25b  call    cs:__imp_SubmitThreadpoolWork
0x18000b261  lea     r9, aMoshostService_5; "[MosHost] Service - Startup - SvcInitia"...
0x18000b268  mov     dword ptr [rsp+2B0h+ppv], r15d
0x18000b26d  mov     r8d, 179h
0x18000b273  lea     rdx, aSvcinitialize; "SvcInitialize"
0x18000b27a  mov     ecx, 3
0x18000b27f  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18000b285  test    cs:Microsoft_Windows_MosHostEnableBits, 1
0x18000b28c  jz      short loc_18000B2E3
0x18000b28e  lea     rax, [rsp+2B0h+pftDueTime]
0x18000b293  mov     r9d, 1
0x18000b299  lea     rdx, ServiceStart
0x18000b2a0  mov     [rsp+2B0h+ppv], rax
0x18000b2a5  call    McGenEventWrite_EventWriteTransfer
0x18000b2aa  jmp     short loc_18000B2E3
0x18000b2ac  mov     r8d, 160h
0x18000b2b2  jmp     short loc_18000B2D2
0x18000b2b4  mov     r8d, 15Eh
0x18000b2ba  jmp     short loc_18000B2D2
0x18000b2bc  mov     r8d, 15Dh
0x18000b2c2  jmp     short loc_18000B2D2
0x18000b2c4  mov     r8d, 15Ch
0x18000b2ca  jmp     short loc_18000B2D2
0x18000b2cc  mov     r8d, 157h
0x18000b2d2  lea     rdx, aSvcinitialize; "SvcInitialize"
0x18000b2d9  mov     ecx, eax
0x18000b2db  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000b2e1  mov     edi, eax
0x18000b2e3  mov     eax, edi
0x18000b2e5  mov     rcx, [rbp+1B0h+var_40]
0x18000b2ec  xor     rcx, rsp; StackCookie
0x18000b2ef  call    __security_check_cookie
0x18000b2f4  add     rsp, 288h
0x18000b2fb  pop     r15
0x18000b2fd  pop     r14
0x18000b2ff  pop     rdi
0x18000b300  pop     rsi
0x18000b301  pop     rbx
0x18000b302  pop     rbp
0x18000b303  retn
```
