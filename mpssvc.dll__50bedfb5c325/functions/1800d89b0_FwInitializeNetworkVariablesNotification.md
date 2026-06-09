# FwInitializeNetworkVariablesNotification

- ea: `0x1800d89b0`
- end: `0x1800d8e72`
- name: `FwInitializeNetworkVariablesNotification`
- size: `1218`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800d8390`
- `0x1800e30fc`

## callees

- `0x18000a710`
- `0x1800729c0`
- `0x180073488`
- `0x1800d89b0`
- `0x1800d8e78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800d8c0e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800d8c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8b5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8c26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8b5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8c26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8dd3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d8a75`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d8aea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d8b9e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d8a75`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d8aea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d8b9e`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800d8b43`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800d8b43`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d8e28`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d8e28`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d8dbb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d8dbb`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x1800d8d59`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x1800d8d59`
- `IPHLPAPI!NotifyRouteChange2` at `0x1800d8c99`
- `IPHLPAPI!NotifyRouteChange2` at `0x1800d8c99`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x1800d8d04`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x1800d8d04`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800d8c68`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800d8d9c`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800d8e3d`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800d8c68`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800d8d9c`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800d8e3d`
- `fwbase!FwHResultToWindowsError` at `0x1800d8a18`
- `fwbase!FwHResultToWindowsError` at `0x1800d8a18`
- `fwbase!FwCriticalSectionCreate` at `0x1800d8a0a`
- `fwbase!FwCriticalSectionCreate` at `0x1800d8a0a`

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
  qword_180137D38 = a2;
  v6 = FwCriticalSectionCreate(qword_180137CF8);
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
  qword_180137CB8 = (__int64)CreateEventW(0, 1, 0, 0);
  if ( qword_180137CB8 )
  {
    qword_180137CC0 = (__int64)CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
    if ( !qword_180137CC0 )
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
    qword_180137CE8 = (__int64)CreateEventW(0, 0, 0, 0);
    if ( !qword_180137CE8 )
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
    qword_180137CE0 = (__int64)CreateThread(0, 0, NVNWorkerThread, &g_FwNVN, 0, 0);
    if ( !qword_180137CE0 )
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
    dword_180137CF0 = 1;
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
      LastError = NotifyIpInterfaceChange(0, NotifyIpInterfaceCallback, &g_FwNVN, 0, &qword_180137CD0);
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
        LastError = NotifyUnicastIpAddressChange(0, NotifyIpUnicastAddrCallback, &g_FwNVN, 0, &qword_180137CD8);
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
          ThreadpoolTimer = CreateThreadpoolTimer(pfnti, qword_180137D38, 0);
          qword_180137D40 = (__int64)ThreadpoolTimer;
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
0x1800d89b0  push    rbx
0x1800d89b2  push    rbp
0x1800d89b3  push    rsi
0x1800d89b4  push    rdi
0x1800d89b5  push    r12
0x1800d89b7  push    r14
0x1800d89b9  sub     rsp, 48h
0x1800d89bd  mov     rax, cs:__security_cookie
0x1800d89c4  xor     rax, rsp
0x1800d89c7  mov     [rsp+78h+var_40], rax
0x1800d89cc  mov     r14, r8
0x1800d89cf  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0
0x1800d89d8  mov     rdi, rdx
0x1800d89db  lea     r12, ?g_FwNVN@@3U_tag_FW_NETVARS_NOTIFY_STATE_OBJECT@@A; _tag_FW_NETVARS_NOTIFY_STATE_OBJECT g_FwNVN
0x1800d89e2  mov     rbx, rcx
0x1800d89e5  xor     edx, edx; Val
0x1800d89e7  mov     rcx, r12; void *
0x1800d89ea  mov     r8d, 0A0h; Size
0x1800d89f0  call    memset_0
0x1800d89f5  lea     rcx, qword_180137CF8
0x1800d89fc  mov     cs:pfnti, rbx
0x1800d8a03  mov     cs:qword_180137D38, rdi
0x1800d8a0a  call    cs:__imp_FwCriticalSectionCreate
0x1800d8a11  nop     dword ptr [rax+rax+00h]
0x1800d8a16  mov     ecx, eax
0x1800d8a18  call    cs:__imp_FwHResultToWindowsError
0x1800d8a1f  nop     dword ptr [rax+rax+00h]
0x1800d8a24  mov     ebx, eax
0x1800d8a26  test    eax, eax
0x1800d8a28  jz      short loc_1800D8A6B
0x1800d8a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8a31  lea     rax, WPP_GLOBAL_Control
0x1800d8a38  cmp     rcx, rax
0x1800d8a3b  jz      loc_1800D8E4D
0x1800d8a41  mov     edi, 1
0x1800d8a46  test    [rcx+1Ch], dil
0x1800d8a4a  jz      loc_1800D8E4D
0x1800d8a50  mov     rcx, [rcx+10h]
0x1800d8a54  lea     edx, [rdi+11h]
0x1800d8a57  mov     r9d, ebx
0x1800d8a5a  lea     r8, WPP_ce1109f0951b354d722b86413ac0b1f2_Traceguids
0x1800d8a61  call    WPP_SF_d
0x1800d8a66  jmp     loc_1800D8E4D
0x1800d8a6b  xor     r9d, r9d; lpName
0x1800d8a6e  xor     r8d, r8d; bInitialState
0x1800d8a71  xor     edx, edx; bManualReset
0x1800d8a73  xor     ecx, ecx; lpEventAttributes
0x1800d8a75  call    cs:__imp_CreateEventW
0x1800d8a7c  nop     dword ptr [rax+rax+00h]
0x1800d8a81  mov     cs:?g_FwNVN@@3U_tag_FW_NETVARS_NOTIFY_STATE_OBJECT@@A, rax; _tag_FW_NETVARS_NOTIFY_STATE_OBJECT g_FwNVN
0x1800d8a88  test    rax, rax
0x1800d8a8b  jnz     short loc_1800D8ADC
0x1800d8a8d  call    cs:__imp_GetLastError
0x1800d8a94  nop     dword ptr [rax+rax+00h]
0x1800d8a99  mov     ebx, eax
0x1800d8a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8aa2  lea     rax, WPP_GLOBAL_Control
0x1800d8aa9  cmp     rcx, rax
0x1800d8aac  jz      loc_1800D8E49
0x1800d8ab2  mov     edi, 1
0x1800d8ab7  test    [rcx+1Ch], dil
0x1800d8abb  jz      loc_1800D8E49
0x1800d8ac1  lea     edx, [rdi+12h]
0x1800d8ac4  mov     rcx, [rcx+10h]
0x1800d8ac8  lea     r8, WPP_ce1109f0951b354d722b86413ac0b1f2_Traceguids
0x1800d8acf  mov     r9d, ebx
0x1800d8ad2  call    WPP_SF_d
0x1800d8ad7  jmp     loc_1800D8E49
0x1800d8adc  xor     r9d, r9d; lpName
0x1800d8adf  xor     r8d, r8d; bInitialState
0x1800d8ae2  xor     ecx, ecx; lpEventAttributes
0x1800d8ae4  lea     edi, [r9+1]
0x1800d8ae8  mov     edx, edi; bManualReset
0x1800d8aea  call    cs:__imp_CreateEventW
0x1800d8af1  nop     dword ptr [rax+rax+00h]
0x1800d8af6  mov     cs:qword_180137CB8, rax
0x1800d8afd  test    rax, rax
0x1800d8b00  jnz     short loc_1800D8B36
0x1800d8b02  call    cs:__imp_GetLastError
0x1800d8b09  nop     dword ptr [rax+rax+00h]
0x1800d8b0e  mov     ebx, eax
0x1800d8b10  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8b17  lea     rax, WPP_GLOBAL_Control
0x1800d8b1e  cmp     rcx, rax
0x1800d8b21  jz      loc_1800D8E49
0x1800d8b27  test    [rcx+1Ch], dil
0x1800d8b2b  jz      loc_1800D8E49
0x1800d8b31  lea     edx, [rdi+13h]
0x1800d8b34  jmp     short loc_1800D8AC4
0x1800d8b36  mov     r9d, 1F0003h; dwDesiredAccess
0x1800d8b3c  mov     r8d, edi; dwFlags
0x1800d8b3f  xor     edx, edx; lpTimerName
0x1800d8b41  xor     ecx, ecx; lpTimerAttributes
0x1800d8b43  call    cs:__imp_CreateWaitableTimerExW
0x1800d8b4a  nop     dword ptr [rax+rax+00h]
0x1800d8b4f  mov     cs:qword_180137CC0, rax
0x1800d8b56  test    rax, rax
0x1800d8b59  jnz     short loc_1800D8B94
0x1800d8b5b  call    cs:__imp_GetLastError
0x1800d8b62  nop     dword ptr [rax+rax+00h]
0x1800d8b67  mov     ebx, eax
0x1800d8b69  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8b70  lea     rax, WPP_GLOBAL_Control
0x1800d8b77  cmp     rcx, rax
0x1800d8b7a  jz      loc_1800D8E49
0x1800d8b80  test    [rcx+1Ch], dil
0x1800d8b84  jz      loc_1800D8E49
0x1800d8b8a  mov     edx, 15h
0x1800d8b8f  jmp     loc_1800D8AC4
0x1800d8b94  xor     r9d, r9d; lpName
0x1800d8b97  xor     r8d, r8d; bInitialState
0x1800d8b9a  xor     edx, edx; bManualReset
0x1800d8b9c  xor     ecx, ecx; lpEventAttributes
0x1800d8b9e  call    cs:__imp_CreateEventW
0x1800d8ba5  nop     dword ptr [rax+rax+00h]
0x1800d8baa  mov     cs:qword_180137CE8, rax
0x1800d8bb1  test    rax, rax
0x1800d8bb4  jnz     short loc_1800D8BEF
0x1800d8bb6  call    cs:__imp_GetLastError
0x1800d8bbd  nop     dword ptr [rax+rax+00h]
0x1800d8bc2  mov     ebx, eax
0x1800d8bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8bcb  lea     rax, WPP_GLOBAL_Control
0x1800d8bd2  cmp     rcx, rax
0x1800d8bd5  jz      loc_1800D8E49
0x1800d8bdb  test    [rcx+1Ch], dil
0x1800d8bdf  jz      loc_1800D8E49
0x1800d8be5  mov     edx, 16h
0x1800d8bea  jmp     loc_1800D8AC4
0x1800d8bef  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x1800d8bf8  lea     r8, ?NVNWorkerThread@@YAKPEAX@Z; lpStartAddress
0x1800d8bff  mov     r9, r12; lpParameter
0x1800d8c02  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x1800d8c0a  xor     edx, edx; dwStackSize
0x1800d8c0c  xor     ecx, ecx; lpThreadAttributes
0x1800d8c0e  call    cs:__imp_CreateThread
0x1800d8c15  nop     dword ptr [rax+rax+00h]
0x1800d8c1a  mov     cs:qword_180137CE0, rax
0x1800d8c21  test    rax, rax
0x1800d8c24  jnz     short loc_1800D8C5F
0x1800d8c26  call    cs:__imp_GetLastError
0x1800d8c2d  nop     dword ptr [rax+rax+00h]
0x1800d8c32  mov     ebx, eax
0x1800d8c34  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8c3b  lea     rax, WPP_GLOBAL_Control
0x1800d8c42  cmp     rcx, rax
0x1800d8c45  jz      loc_1800D8E49
0x1800d8c4b  test    [rcx+1Ch], dil
0x1800d8c4f  jz      loc_1800D8E49
0x1800d8c55  mov     edx, 17h
0x1800d8c5a  jmp     loc_1800D8AC4
0x1800d8c5f  or      ecx, 0FFFFFFFFh; CompartmentScope
0x1800d8c62  mov     cs:dword_180137CF0, edi
0x1800d8c68  call    cs:__imp_SetCurrentThreadCompartmentScope
0x1800d8c6f  nop     dword ptr [rax+rax+00h]
0x1800d8c74  xor     esi, esi
0x1800d8c76  lea     rdx, ?NotifyRouteCallback@@YAXPEAXPEAU_MIB_IPFORWARD_ROW2@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x1800d8c7d  test    eax, eax
0x1800d8c7f  mov     ebp, eax
0x1800d8c81  lea     rax, NotificationHandle
0x1800d8c88  mov     r8, r12; CallerContext
0x1800d8c8b  setz    sil
0x1800d8c8f  mov     qword ptr [rsp+78h+dwCreationFlags], rax; NotificationHandle
0x1800d8c94  xor     ecx, ecx; AddressFamily
0x1800d8c96  xor     r9d, r9d; InitialNotification
0x1800d8c99  call    cs:__imp_NotifyRouteChange2
0x1800d8ca0  nop     dword ptr [rax+rax+00h]
0x1800d8ca5  mov     ebx, eax
0x1800d8ca7  test    eax, eax
0x1800d8ca9  jz      short loc_1800D8CE9
0x1800d8cab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8cb2  lea     rax, WPP_GLOBAL_Control
0x1800d8cb9  cmp     rcx, rax
0x1800d8cbc  jz      loc_1800D8E37
0x1800d8cc2  test    [rcx+1Ch], dil
0x1800d8cc6  jz      loc_1800D8E37
0x1800d8ccc  mov     edx, 18h
0x1800d8cd1  mov     rcx, [rcx+10h]
0x1800d8cd5  lea     r8, WPP_ce1109f0951b354d722b86413ac0b1f2_Traceguids
0x1800d8cdc  mov     r9d, ebx
0x1800d8cdf  call    WPP_SF_d
0x1800d8ce4  jmp     loc_1800D8E37
0x1800d8ce9  lea     rax, qword_180137CD0
0x1800d8cf0  xor     ecx, ecx; Family
0x1800d8cf2  xor     r9d, r9d; InitialNotification
0x1800d8cf5  mov     qword ptr [rsp+78h+dwCreationFlags], rax; NotificationHandle
0x1800d8cfa  mov     r8, r12; CallerContext
0x1800d8cfd  lea     rdx, ?NotifyIpInterfaceCallback@@YAXPEAXPEAU_MIB_IPFORWARD_ROW2@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x1800d8d04  call    cs:__imp_NotifyIpInterfaceChange
0x1800d8d0b  nop     dword ptr [rax+rax+00h]
0x1800d8d10  mov     ebx, eax
0x1800d8d12  test    eax, eax
0x1800d8d14  jz      short loc_1800D8D3E
0x1800d8d16  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8d1d  lea     rax, WPP_GLOBAL_Control
0x1800d8d24  cmp     rcx, rax
0x1800d8d27  jz      loc_1800D8E37
0x1800d8d2d  test    [rcx+1Ch], dil
0x1800d8d31  jz      loc_1800D8E37
0x1800d8d37  mov     edx, 19h
0x1800d8d3c  jmp     short loc_1800D8CD1
0x1800d8d3e  lea     rax, qword_180137CD8
0x1800d8d45  xor     ecx, ecx; Family
0x1800d8d47  xor     r9d, r9d; InitialNotification
0x1800d8d4a  mov     qword ptr [rsp+78h+dwCreationFlags], rax; NotificationHandle
0x1800d8d4f  mov     r8, r12; CallerContext
0x1800d8d52  lea     rdx, ?NotifyIpUnicastAddrCallback@@YAXPEAXPEAU_MIB_IPFORWARD_ROW2@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x1800d8d59  call    cs:__imp_NotifyUnicastIpAddressChange
0x1800d8d60  nop     dword ptr [rax+rax+00h]
0x1800d8d65  mov     ebx, eax
0x1800d8d67  test    eax, eax
0x1800d8d69  jz      short loc_1800D8D96
0x1800d8d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8d72  lea     rax, WPP_GLOBAL_Control
0x1800d8d79  cmp     rcx, rax
0x1800d8d7c  jz      loc_1800D8E37
0x1800d8d82  test    [rcx+1Ch], dil
0x1800d8d86  jz      loc_1800D8E37
0x1800d8d8c  mov     edx, 1Ah
0x1800d8d91  jmp     loc_1800D8CD1
0x1800d8d96  test    ebp, ebp
0x1800d8d98  jnz     short loc_1800D8DAA
0x1800d8d9a  xor     ecx, ecx; CompartmentScope
0x1800d8d9c  call    cs:__imp_SetCurrentThreadCompartmentScope
0x1800d8da3  nop     dword ptr [rax+rax+00h]
0x1800d8da8  xor     esi, esi
0x1800d8daa  mov     rdx, cs:qword_180137D38; pv
0x1800d8db1  xor     r8d, r8d; pcbe
0x1800d8db4  mov     rcx, cs:pfnti; pfnti
0x1800d8dbb  call    cs:__imp_CreateThreadpoolTimer
0x1800d8dc2  nop     dword ptr [rax+rax+00h]
0x1800d8dc7  mov     cs:qword_180137D40, rax
0x1800d8dce  test    rax, rax
0x1800d8dd1  jnz     short loc_1800D8E04
0x1800d8dd3  call    cs:__imp_GetLastError
0x1800d8dda  nop     dword ptr [rax+rax+00h]
0x1800d8ddf  mov     ebx, eax
0x1800d8de1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8de8  lea     rax, WPP_GLOBAL_Control
0x1800d8def  cmp     rcx, rax
0x1800d8df2  jz      short loc_1800D8E37
0x1800d8df4  test    [rcx+1Ch], dil
0x1800d8df8  jz      short loc_1800D8E37
0x1800d8dfa  mov     edx, 1Bh
0x1800d8dff  jmp     loc_1800D8CD1
0x1800d8e04  mov     r9d, 493E0h; msWindowLength
0x1800d8e0a  mov     [rsp+78h+pftDueTime.dwHighDateTime], 0FFFFFFFDh
0x1800d8e12  mov     r8d, 0DBBA0h; msPeriod
0x1800d8e18  mov     [rsp+78h+pftDueTime.dwLowDateTime], 0E78EE600h
0x1800d8e20  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1800d8e25  mov     rcx, rax; pti
0x1800d8e28  call    cs:__imp_SetThreadpoolTimer
0x1800d8e2f  nop     dword ptr [rax+rax+00h]
0x1800d8e34  mov     [r14], r12
0x1800d8e37  test    esi, esi
0x1800d8e39  jz      short loc_1800D8E49
0x1800d8e3b  xor     ecx, ecx; CompartmentScope
0x1800d8e3d  call    cs:__imp_SetCurrentThreadCompartmentScope
0x1800d8e44  nop     dword ptr [rax+rax+00h]
0x1800d8e49  test    ebx, ebx
0x1800d8e4b  jz      short loc_1800D8E55
0x1800d8e4d  mov     rcx, r12; void *
0x1800d8e50  call    FwShutdownNetworkVariablesNotification
0x1800d8e55  mov     eax, ebx
0x1800d8e57  mov     rcx, [rsp+78h+var_40]
0x1800d8e5c  xor     rcx, rsp; StackCookie
0x1800d8e5f  call    __security_check_cookie
0x1800d8e64  add     rsp, 48h
0x1800d8e68  pop     r14
0x1800d8e6a  pop     r12
0x1800d8e6c  pop     rdi
0x1800d8e6d  pop     rsi
0x1800d8e6e  pop     rbp
0x1800d8e6f  pop     rbx
0x1800d8e70  retn
```
