# FwInitializeNetworkVariablesNotification

- ea: `0x1800d107c`
- end: `0x1800d14bf`
- name: `FwInitializeNetworkVariablesNotification`
- size: `1091`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800d0a80`
- `0x1800dcfbc`

## callees

- `0x18000af3c`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800d107c`
- `0x1800d14c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800d129e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800d129e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d11b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d11fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d124c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d12b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d11b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d11fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d124c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d12b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1433`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800d11eb`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800d11eb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d1135`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d119e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d123a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d1135`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d119e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d123a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d1482`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d1482`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d1421`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d1421`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x1800d13cb`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x1800d13cb`
- `IPHLPAPI!NotifyRouteChange2` at `0x1800d1317`
- `IPHLPAPI!NotifyRouteChange2` at `0x1800d1317`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x1800d137c`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x1800d137c`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800d12ec`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800d1408`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800d1491`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800d12ec`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800d1408`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800d1491`
- `fwbase!FwHResultToWindowsError` at `0x1800d10de`
- `fwbase!FwHResultToWindowsError` at `0x1800d10de`
- `fwbase!FwCriticalSectionCreate` at `0x1800d10d6`
- `fwbase!FwCriticalSectionCreate` at `0x1800d10d6`

## pseudocode

```c
__int64 __fastcall FwInitializeNetworkVariablesNotification(
        void (__stdcall *a1)(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer),
        void *a2,
        _QWORD *a3)
{
  unsigned int v6; // eax
  DWORD LastError; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdx
  NTSTATUS v10; // ebp
  BOOL v11; // esi
  __int64 v12; // rcx
  __int64 v13; // rdx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-48h] BYREF

  pftDueTime = 0;
  memset_0(&g_FwNVN, 0, 0xA0u);
  pfnti = a1;
  qword_180131B68 = a2;
  v6 = FwCriticalSectionCreate(qword_180131B28);
  LastError = FwHResultToWindowsError(v6);
  if ( LastError )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_ce1109f0951b354d722b86413ac0b1f2_Traceguids, LastError);
    goto LABEL_49;
  }
  g_FwNVN = CreateEventW(0, 0, 0, 0);
  if ( !g_FwNVN )
  {
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v9 = 19;
LABEL_9:
      WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_ce1109f0951b354d722b86413ac0b1f2_Traceguids, LastError);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  qword_180131AE8 = (__int64)CreateEventW(0, 1, 0, 0);
  if ( qword_180131AE8 )
  {
    qword_180131AF0 = (__int64)CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
    if ( !qword_180131AF0 )
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 21;
        goto LABEL_9;
      }
      goto LABEL_48;
    }
    qword_180131B18 = (__int64)CreateEventW(0, 0, 0, 0);
    if ( !qword_180131B18 )
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 22;
        goto LABEL_9;
      }
      goto LABEL_48;
    }
    qword_180131B10 = (__int64)CreateThread(0, 0, NVNWorkerThread, &g_FwNVN, 0, 0);
    if ( !qword_180131B10 )
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 23;
        goto LABEL_9;
      }
      goto LABEL_48;
    }
    dword_180131B20 = 1;
    v10 = SetCurrentThreadCompartmentScope(0xFFFFFFFF);
    v11 = v10 == 0;
    LastError = NotifyRouteChange2(0, NotifyRouteCallback, &g_FwNVN, 0, &NotificationHandle);
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v13 = 24;
LABEL_30:
        WPP_SF_d(*(_QWORD *)(v12 + 16), v13, WPP_ce1109f0951b354d722b86413ac0b1f2_Traceguids, LastError);
      }
    }
    else
    {
      LastError = NotifyIpInterfaceChange(0, NotifyIpInterfaceCallback, &g_FwNVN, 0, &qword_180131B00);
      if ( LastError )
      {
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v13 = 25;
          goto LABEL_30;
        }
      }
      else
      {
        LastError = NotifyUnicastIpAddressChange(0, NotifyIpUnicastAddrCallback, &g_FwNVN, 0, &qword_180131B08);
        if ( LastError )
        {
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v13 = 26;
            goto LABEL_30;
          }
        }
        else
        {
          if ( !v10 )
          {
            SetCurrentThreadCompartmentScope(0);
            v11 = 0;
          }
          ThreadpoolTimer = CreateThreadpoolTimer(pfnti, qword_180131B68, 0);
          qword_180131B70 = (__int64)ThreadpoolTimer;
          if ( ThreadpoolTimer )
          {
            pftDueTime.dwHighDateTime = -3;
            pftDueTime.dwLowDateTime = -410065408;
            SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0xDBBA0u, 0x493E0u);
            *a3 = &g_FwNVN;
          }
          else
          {
            LastError = GetLastError();
            v12 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v13 = 27;
              goto LABEL_30;
            }
          }
        }
      }
    }
    if ( v11 )
      SetCurrentThreadCompartmentScope(0);
    goto LABEL_48;
  }
  LastError = GetLastError();
  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v9 = 20;
    goto LABEL_9;
  }
LABEL_48:
  if ( LastError )
LABEL_49:
    FwShutdownNetworkVariablesNotification(&g_FwNVN);
  return LastError;
}

```

## disassembly

```asm
0x1800d107c  push    rbx
0x1800d107e  push    rbp
0x1800d107f  push    rsi
0x1800d1080  push    rdi
0x1800d1081  push    r12
0x1800d1083  push    r14
0x1800d1085  sub     rsp, 48h
0x1800d1089  mov     rax, cs:__security_cookie
0x1800d1090  xor     rax, rsp
0x1800d1093  mov     [rsp+78h+var_40], rax
0x1800d1098  mov     r14, r8
0x1800d109b  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0
0x1800d10a4  mov     rdi, rdx
0x1800d10a7  lea     r12, ?g_FwNVN@@3U_tag_FW_NETVARS_NOTIFY_STATE_OBJECT@@A; _tag_FW_NETVARS_NOTIFY_STATE_OBJECT g_FwNVN
0x1800d10ae  mov     rbx, rcx
0x1800d10b1  xor     edx, edx; Val
0x1800d10b3  mov     rcx, r12; void *
0x1800d10b6  mov     r8d, 0A0h; Size
0x1800d10bc  call    memset_0
0x1800d10c1  lea     rcx, qword_180131B28
0x1800d10c8  mov     cs:pfnti, rbx
0x1800d10cf  mov     cs:qword_180131B68, rdi
0x1800d10d6  call    cs:__imp_FwCriticalSectionCreate
0x1800d10dc  mov     ecx, eax
0x1800d10de  call    cs:__imp_FwHResultToWindowsError
0x1800d10e4  mov     ebx, eax
0x1800d10e6  test    eax, eax
0x1800d10e8  jz      short loc_1800D112B
0x1800d10ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d10f1  lea     rax, WPP_GLOBAL_Control
0x1800d10f8  cmp     rcx, rax
0x1800d10fb  jz      loc_1800D149B
0x1800d1101  mov     edi, 1
0x1800d1106  test    [rcx+1Ch], dil
0x1800d110a  jz      loc_1800D149B
0x1800d1110  mov     rcx, [rcx+10h]
0x1800d1114  lea     edx, [rdi+11h]
0x1800d1117  mov     r9d, ebx
0x1800d111a  lea     r8, WPP_ce1109f0951b354d722b86413ac0b1f2_Traceguids
0x1800d1121  call    WPP_SF_d
0x1800d1126  jmp     loc_1800D149B
0x1800d112b  xor     r9d, r9d; lpName
0x1800d112e  xor     r8d, r8d; bInitialState
0x1800d1131  xor     edx, edx; bManualReset
0x1800d1133  xor     ecx, ecx; lpEventAttributes
0x1800d1135  call    cs:__imp_CreateEventW
0x1800d113b  mov     cs:?g_FwNVN@@3U_tag_FW_NETVARS_NOTIFY_STATE_OBJECT@@A, rax; _tag_FW_NETVARS_NOTIFY_STATE_OBJECT g_FwNVN
0x1800d1142  test    rax, rax
0x1800d1145  jnz     short loc_1800D1190
0x1800d1147  call    cs:__imp_GetLastError
0x1800d114d  mov     ebx, eax
0x1800d114f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1156  lea     rax, WPP_GLOBAL_Control
0x1800d115d  cmp     rcx, rax
0x1800d1160  jz      loc_1800D1497
0x1800d1166  mov     edi, 1
0x1800d116b  test    [rcx+1Ch], dil
0x1800d116f  jz      loc_1800D1497
0x1800d1175  lea     edx, [rdi+12h]
0x1800d1178  mov     rcx, [rcx+10h]
0x1800d117c  lea     r8, WPP_ce1109f0951b354d722b86413ac0b1f2_Traceguids
0x1800d1183  mov     r9d, ebx
0x1800d1186  call    WPP_SF_d
0x1800d118b  jmp     loc_1800D1497
0x1800d1190  xor     r9d, r9d; lpName
0x1800d1193  xor     r8d, r8d; bInitialState
0x1800d1196  xor     ecx, ecx; lpEventAttributes
0x1800d1198  lea     edi, [r9+1]
0x1800d119c  mov     edx, edi; bManualReset
0x1800d119e  call    cs:__imp_CreateEventW
0x1800d11a4  mov     cs:qword_180131AE8, rax
0x1800d11ab  test    rax, rax
0x1800d11ae  jnz     short loc_1800D11DE
0x1800d11b0  call    cs:__imp_GetLastError
0x1800d11b6  mov     ebx, eax
0x1800d11b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d11bf  lea     rax, WPP_GLOBAL_Control
0x1800d11c6  cmp     rcx, rax
0x1800d11c9  jz      loc_1800D1497
0x1800d11cf  test    [rcx+1Ch], dil
0x1800d11d3  jz      loc_1800D1497
0x1800d11d9  lea     edx, [rdi+13h]
0x1800d11dc  jmp     short loc_1800D1178
0x1800d11de  mov     r9d, 1F0003h; dwDesiredAccess
0x1800d11e4  mov     r8d, edi; dwFlags
0x1800d11e7  xor     edx, edx; lpTimerName
0x1800d11e9  xor     ecx, ecx; lpTimerAttributes
0x1800d11eb  call    cs:__imp_CreateWaitableTimerExW
0x1800d11f1  mov     cs:qword_180131AF0, rax
0x1800d11f8  test    rax, rax
0x1800d11fb  jnz     short loc_1800D1230
0x1800d11fd  call    cs:__imp_GetLastError
0x1800d1203  mov     ebx, eax
0x1800d1205  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d120c  lea     rax, WPP_GLOBAL_Control
0x1800d1213  cmp     rcx, rax
0x1800d1216  jz      loc_1800D1497
0x1800d121c  test    [rcx+1Ch], dil
0x1800d1220  jz      loc_1800D1497
0x1800d1226  mov     edx, 15h
0x1800d122b  jmp     loc_1800D1178
0x1800d1230  xor     r9d, r9d; lpName
0x1800d1233  xor     r8d, r8d; bInitialState
0x1800d1236  xor     edx, edx; bManualReset
0x1800d1238  xor     ecx, ecx; lpEventAttributes
0x1800d123a  call    cs:__imp_CreateEventW
0x1800d1240  mov     cs:qword_180131B18, rax
0x1800d1247  test    rax, rax
0x1800d124a  jnz     short loc_1800D127F
0x1800d124c  call    cs:__imp_GetLastError
0x1800d1252  mov     ebx, eax
0x1800d1254  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d125b  lea     rax, WPP_GLOBAL_Control
0x1800d1262  cmp     rcx, rax
0x1800d1265  jz      loc_1800D1497
0x1800d126b  test    [rcx+1Ch], dil
0x1800d126f  jz      loc_1800D1497
0x1800d1275  mov     edx, 16h
0x1800d127a  jmp     loc_1800D1178
0x1800d127f  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x1800d1288  lea     r8, ?NVNWorkerThread@@YAKPEAX@Z; lpStartAddress
0x1800d128f  mov     r9, r12; lpParameter
0x1800d1292  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x1800d129a  xor     edx, edx; dwStackSize
0x1800d129c  xor     ecx, ecx; lpThreadAttributes
0x1800d129e  call    cs:__imp_CreateThread
0x1800d12a4  mov     cs:qword_180131B10, rax
0x1800d12ab  test    rax, rax
0x1800d12ae  jnz     short loc_1800D12E3
0x1800d12b0  call    cs:__imp_GetLastError
0x1800d12b6  mov     ebx, eax
0x1800d12b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d12bf  lea     rax, WPP_GLOBAL_Control
0x1800d12c6  cmp     rcx, rax
0x1800d12c9  jz      loc_1800D1497
0x1800d12cf  test    [rcx+1Ch], dil
0x1800d12d3  jz      loc_1800D1497
0x1800d12d9  mov     edx, 17h
0x1800d12de  jmp     loc_1800D1178
0x1800d12e3  or      ecx, 0FFFFFFFFh; CompartmentScope
0x1800d12e6  mov     cs:dword_180131B20, edi
0x1800d12ec  call    cs:__imp_SetCurrentThreadCompartmentScope
0x1800d12f2  xor     esi, esi
0x1800d12f4  lea     rdx, ?NotifyRouteCallback@@YAXPEAXPEAU_MIB_IPFORWARD_ROW2@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x1800d12fb  test    eax, eax
0x1800d12fd  mov     ebp, eax
0x1800d12ff  lea     rax, NotificationHandle
0x1800d1306  mov     r8, r12; CallerContext
0x1800d1309  setz    sil
0x1800d130d  mov     qword ptr [rsp+78h+dwCreationFlags], rax; NotificationHandle
0x1800d1312  xor     ecx, ecx; AddressFamily
0x1800d1314  xor     r9d, r9d; InitialNotification
0x1800d1317  call    cs:__imp_NotifyRouteChange2
0x1800d131d  mov     ebx, eax
0x1800d131f  test    eax, eax
0x1800d1321  jz      short loc_1800D1361
0x1800d1323  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d132a  lea     rax, WPP_GLOBAL_Control
0x1800d1331  cmp     rcx, rax
0x1800d1334  jz      loc_1800D148B
0x1800d133a  test    [rcx+1Ch], dil
0x1800d133e  jz      loc_1800D148B
0x1800d1344  mov     edx, 18h
0x1800d1349  mov     rcx, [rcx+10h]
0x1800d134d  lea     r8, WPP_ce1109f0951b354d722b86413ac0b1f2_Traceguids
0x1800d1354  mov     r9d, ebx
0x1800d1357  call    WPP_SF_d
0x1800d135c  jmp     loc_1800D148B
0x1800d1361  lea     rax, qword_180131B00
0x1800d1368  xor     ecx, ecx; Family
0x1800d136a  xor     r9d, r9d; InitialNotification
0x1800d136d  mov     qword ptr [rsp+78h+dwCreationFlags], rax; NotificationHandle
0x1800d1372  mov     r8, r12; CallerContext
0x1800d1375  lea     rdx, ?NotifyIpInterfaceCallback@@YAXPEAXPEAU_MIB_IPFORWARD_ROW2@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x1800d137c  call    cs:__imp_NotifyIpInterfaceChange
0x1800d1382  mov     ebx, eax
0x1800d1384  test    eax, eax
0x1800d1386  jz      short loc_1800D13B0
0x1800d1388  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d138f  lea     rax, WPP_GLOBAL_Control
0x1800d1396  cmp     rcx, rax
0x1800d1399  jz      loc_1800D148B
0x1800d139f  test    [rcx+1Ch], dil
0x1800d13a3  jz      loc_1800D148B
0x1800d13a9  mov     edx, 19h
0x1800d13ae  jmp     short loc_1800D1349
0x1800d13b0  lea     rax, qword_180131B08
0x1800d13b7  xor     ecx, ecx; Family
0x1800d13b9  xor     r9d, r9d; InitialNotification
0x1800d13bc  mov     qword ptr [rsp+78h+dwCreationFlags], rax; NotificationHandle
0x1800d13c1  mov     r8, r12; CallerContext
0x1800d13c4  lea     rdx, ?NotifyIpUnicastAddrCallback@@YAXPEAXPEAU_MIB_IPFORWARD_ROW2@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x1800d13cb  call    cs:__imp_NotifyUnicastIpAddressChange
0x1800d13d1  mov     ebx, eax
0x1800d13d3  test    eax, eax
0x1800d13d5  jz      short loc_1800D1402
0x1800d13d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d13de  lea     rax, WPP_GLOBAL_Control
0x1800d13e5  cmp     rcx, rax
0x1800d13e8  jz      loc_1800D148B
0x1800d13ee  test    [rcx+1Ch], dil
0x1800d13f2  jz      loc_1800D148B
0x1800d13f8  mov     edx, 1Ah
0x1800d13fd  jmp     loc_1800D1349
0x1800d1402  test    ebp, ebp
0x1800d1404  jnz     short loc_1800D1410
0x1800d1406  xor     ecx, ecx; CompartmentScope
0x1800d1408  call    cs:__imp_SetCurrentThreadCompartmentScope
0x1800d140e  xor     esi, esi
0x1800d1410  mov     rdx, cs:qword_180131B68; pv
0x1800d1417  xor     r8d, r8d; pcbe
0x1800d141a  mov     rcx, cs:pfnti; pfnti
0x1800d1421  call    cs:__imp_CreateThreadpoolTimer
0x1800d1427  mov     cs:qword_180131B70, rax
0x1800d142e  test    rax, rax
0x1800d1431  jnz     short loc_1800D145E
0x1800d1433  call    cs:__imp_GetLastError
0x1800d1439  mov     ebx, eax
0x1800d143b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1442  lea     rax, WPP_GLOBAL_Control
0x1800d1449  cmp     rcx, rax
0x1800d144c  jz      short loc_1800D148B
0x1800d144e  test    [rcx+1Ch], dil
0x1800d1452  jz      short loc_1800D148B
0x1800d1454  mov     edx, 1Bh
0x1800d1459  jmp     loc_1800D1349
0x1800d145e  mov     r9d, 493E0h; msWindowLength
0x1800d1464  mov     [rsp+78h+pftDueTime.dwHighDateTime], 0FFFFFFFDh
0x1800d146c  mov     r8d, 0DBBA0h; msPeriod
0x1800d1472  mov     [rsp+78h+pftDueTime.dwLowDateTime], 0E78EE600h
0x1800d147a  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1800d147f  mov     rcx, rax; pti
0x1800d1482  call    cs:__imp_SetThreadpoolTimer
0x1800d1488  mov     [r14], r12
0x1800d148b  test    esi, esi
0x1800d148d  jz      short loc_1800D1497
0x1800d148f  xor     ecx, ecx; CompartmentScope
0x1800d1491  call    cs:__imp_SetCurrentThreadCompartmentScope
0x1800d1497  test    ebx, ebx
0x1800d1499  jz      short loc_1800D14A3
0x1800d149b  mov     rcx, r12; void *
0x1800d149e  call    FwShutdownNetworkVariablesNotification
0x1800d14a3  mov     eax, ebx
0x1800d14a5  mov     rcx, [rsp+78h+var_40]
0x1800d14aa  xor     rcx, rsp; StackCookie
0x1800d14ad  call    __security_check_cookie
0x1800d14b2  add     rsp, 48h
0x1800d14b6  pop     r14
0x1800d14b8  pop     r12
0x1800d14ba  pop     rdi
0x1800d14bb  pop     rsi
0x1800d14bc  pop     rbp
0x1800d14bd  pop     rbx
0x1800d14be  retn
```
