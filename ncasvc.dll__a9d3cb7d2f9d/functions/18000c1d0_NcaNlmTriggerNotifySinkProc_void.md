# NcaNlmTriggerNotifySinkProc(void *)

- ea: `0x18000c1d0`
- end: `0x18000c724`
- name: `?NcaNlmTriggerNotifySinkProc@@YAKPEAX@Z`
- size: `1364`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x18000b340`
- `0x18000badc`
- `0x18000baf8`
- `0x18000be20`
- `0x18000c0cc`
- `0x18000c174`
- `0x18000c1d0`
- `0x18001abd4`
- `0x18001cc3e`
- `0x18001cc70`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c493`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c43d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c43d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c588`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c23f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c23f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c6cd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c6cd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000c6e1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000c6f5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000c6e1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000c6f5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000c2ef`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000c2ef`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000c28f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000c28f`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18000c42d`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18000c574`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18000c42d`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18000c574`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000c51e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000c51e`

## string_xrefs

- `0x18000c283`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall NcaNlmTriggerNotifySinkProc(PVOID Parameter)
{
  CNlmTriggerProfileEventSink *v1; // rdi
  CNlmTriggerInetConnEventSink *v2; // r14
  SC_HANDLE v3; // r12
  int LastError; // eax
  int v5; // r13d
  SC_HANDLE v6; // r15
  PVOID *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  SC_HANDLE v10; // rax
  CNlmTriggerProfileEventSink *v11; // rax
  CNlmTriggerProfileEventSink *v12; // rax
  CNlmTriggerInetConnEventSink *v13; // rax
  CNlmTriggerInetConnEventSink *v14; // rax
  int v15; // eax
  int v16; // ebx
  int v17; // eax
  __int128 v19; // [rsp+20h] [rbp-79h] BYREF
  __int64 v20; // [rsp+30h] [rbp-69h]
  __int128 v21; // [rsp+38h] [rbp-61h] BYREF
  __int64 v22; // [rsp+48h] [rbp-51h]
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+50h] [rbp-49h] BYREF

  v1 = 0;
  v20 = 0;
  v19 = 0;
  v2 = 0;
  v22 = 0;
  v3 = 0;
  v21 = 0;
  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  pNotifyBuffer.pContext = 0;
  pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)NcaNlmTriggerSvcNotify;
  pNotifyBuffer.dwVersion = 1;
  LastError = CoInitializeEx(0, 4u);
  if ( LastError < 0 )
  {
    v5 = 0;
    v6 = 0;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_70;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_67;
    v8 = 30;
    goto LABEL_5;
  }
  v5 = 1;
  v10 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v6 = v10;
  if ( v10 )
  {
    v3 = OpenServiceW(v10, L"NetProfm", 4u);
    if ( v3 )
    {
      v11 = (CNlmTriggerProfileEventSink *)NcaAlloc(16);
      if ( v11 && (v12 = CNlmTriggerProfileEventSink::CNlmTriggerProfileEventSink(v11), (v1 = v12) != 0) )
      {
        LastError = (**(__int64 (__fastcall ***)(CNlmTriggerProfileEventSink *, GUID *, char *))v12)(
                      v12,
                      &IID_IUnknown,
                      (char *)&v19 + 8);
        if ( LastError < 0 )
        {
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_70;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_67;
          v8 = 34;
          goto LABEL_5;
        }
        v13 = (CNlmTriggerInetConnEventSink *)NcaAlloc(16);
        if ( v13 )
        {
          v14 = CNlmTriggerInetConnEventSink::CNlmTriggerInetConnEventSink(v13);
          v2 = v14;
          if ( v14 )
          {
            LastError = (**(__int64 (__fastcall ***)(CNlmTriggerInetConnEventSink *, GUID *, char *))v14)(
                          v14,
                          &IID_IUnknown,
                          (char *)&v21 + 8);
            if ( LastError < 0 )
            {
              v7 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                goto LABEL_70;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_67;
              v8 = 36;
              goto LABEL_5;
            }
            if ( !NotifyServiceStatusChangeW(v3, 0xCu, &pNotifyBuffer) )
            {
              while ( WaitForSingleObjectEx(qword_180028CD8, 0xFFFFFFFF, 1) )
              {
                if ( pNotifyBuffer.dwNotificationStatus )
                {
                  v7 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                    goto LABEL_70;
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v8 = 38;
                    v9 = 0;
                    goto LABEL_65;
                  }
                  goto LABEL_67;
                }
                if ( pNotifyBuffer.ServiceStatus.dwCurrentState == 4 )
                {
                  while ( 1 )
                  {
                    v15 = NcaNlmTriggerConnectionPointObjectsRefresh(
                            (struct NCA_NLM_CONN_POINT_STATE *)&v19,
                            (struct NCA_NLM_CONN_POINT_STATE *)&v21);
                    if ( v15 < 0
                      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        39,
                        WPP_e3f5ab3ee88d3b7229a13de75aa7d1b1_Traceguids,
                        (unsigned int)v15);
                    }
                    v16 = NcaNlmTriggerConnectionStateAdvice((struct NCA_NLM_CONN_POINT_STATE *)&v19);
                    v17 = NcaNlmTriggerConnectionStateAdvice((struct NCA_NLM_CONN_POINT_STATE *)&v21);
                    if ( v16 != -2147483638 && v17 != -2147483638 )
                      break;
                    Sleep(0xFAu);
                  }
                  _InterlockedCompareExchange(&dword_180028CE4, 1, 0);
                  NcaSrcLnkdTriggerSignalTriggersInList(&stru_180028CF0);
                  NcaSrcLnkdTriggerSignalTriggersInList(&stru_180028D30);
                }
                else if ( ((pNotifyBuffer.ServiceStatus.dwCurrentState - 1) & 0xFFFFFFFD) == 0 )
                {
                  _InterlockedCompareExchange(&dword_180028CE4, 0, 1);
                }
                if ( NotifyServiceStatusChangeW(v3, 0xCu, &pNotifyBuffer) )
                {
                  LastError = GetLastError();
                  if ( LastError > 0 )
                    LastError = (unsigned __int16)LastError | 0x80070000;
                  v7 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                    goto LABEL_70;
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_67;
                  v8 = 40;
                  goto LABEL_5;
                }
              }
              goto LABEL_66;
            }
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v7 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 37;
                goto LABEL_5;
              }
              goto LABEL_67;
            }
            goto LABEL_70;
          }
        }
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_70;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_67;
        v8 = 35;
      }
      else
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_70;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_67;
        v8 = 33;
      }
      v9 = 2147942414LL;
      goto LABEL_65;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 32;
        goto LABEL_5;
      }
LABEL_67:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
        WPP_SF_(v7[2], 41, WPP_e3f5ab3ee88d3b7229a13de75aa7d1b1_Traceguids);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 31;
LABEL_5:
        v9 = (unsigned int)LastError;
LABEL_65:
        WPP_SF_d(v7[2], v8, WPP_e3f5ab3ee88d3b7229a13de75aa7d1b1_Traceguids, v9);
LABEL_66:
        v7 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_67;
      }
      goto LABEL_67;
    }
  }
LABEL_70:
  NcaNlmTriggerConnectionStateUnadviceRelease((struct NCA_NLM_CONN_POINT_STATE *)&v19);
  NcaNlmTriggerConnectionStateUnadviceRelease((struct NCA_NLM_CONN_POINT_STATE *)&v21);
  if ( v1 )
  {
    (*(void (__fastcall **)(CNlmTriggerProfileEventSink *))(*(_QWORD *)v1 + 16LL))(v1);
    *((_QWORD *)&v19 + 1) = 0;
  }
  if ( v2 )
  {
    (*(void (__fastcall **)(CNlmTriggerInetConnEventSink *))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)&v21 + 1) = 0;
  }
  if ( gNcaNlmTriggerComp )
  {
    ((void (__fastcall *)(struct INetworkListManager *))gNcaNlmTriggerComp->lpVtbl->Release)(gNcaNlmTriggerComp);
    gNcaNlmTriggerComp = 0;
  }
  if ( v5 == 1 )
    CoUninitialize();
  if ( v3 )
    CloseServiceHandle(v3);
  if ( v6 )
    CloseServiceHandle(v6);
  return 0;
}

```

## disassembly

```asm
0x18000c1d0  push    rbp
0x18000c1d2  push    rbx
0x18000c1d3  push    rsi
0x18000c1d4  push    rdi
0x18000c1d5  push    r12
0x18000c1d7  push    r13
0x18000c1d9  push    r14
0x18000c1db  push    r15
0x18000c1dd  lea     rbp, [rsp-1Fh]
0x18000c1e2  sub     rsp, 0B8h
0x18000c1e9  mov     rax, cs:__security_cookie
0x18000c1f0  xor     rax, rsp
0x18000c1f3  mov     [rbp+57h+var_50], rax
0x18000c1f7  xorps   xmm0, xmm0
0x18000c1fa  lea     rcx, [rbp+57h+pNotifyBuffer]; void *
0x18000c1fe  xor     eax, eax
0x18000c200  xor     edi, edi
0x18000c202  xor     edx, edx; Val
0x18000c204  mov     [rbp+57h+var_C0], rax
0x18000c208  movups  [rbp+57h+var_D0], xmm0
0x18000c20c  xor     r14d, r14d
0x18000c20f  mov     [rbp+57h+var_A8], rax
0x18000c213  lea     r8d, [rdi+50h]; Size
0x18000c217  xor     r12d, r12d
0x18000c21a  movups  [rbp+57h+var_B8], xmm0
0x18000c21e  call    memset_0
0x18000c223  lea     rax, ?NcaNlmTriggerSvcNotify@@YAXPEAX@Z; NcaNlmTriggerSvcNotify(void *)
0x18000c22a  mov     [rbp+57h+pNotifyBuffer.pContext], rdi
0x18000c22e  lea     esi, [rdi+4]
0x18000c231  mov     [rbp+57h+pNotifyBuffer.pfnNotifyCallback], rax
0x18000c235  lea     ebx, [rdi+1]
0x18000c238  mov     edx, esi; dwCoInit
0x18000c23a  xor     ecx, ecx; pvReserved
0x18000c23c  mov     [rbp+57h+pNotifyBuffer.dwVersion], ebx
0x18000c23f  call    cs:__imp_CoInitializeEx
0x18000c246  nop     dword ptr [rax+rax+00h]
0x18000c24b  test    eax, eax
0x18000c24d  jns     short loc_18000C280
0x18000c24f  xor     r13d, r13d
0x18000c252  xor     r15d, r15d
0x18000c255  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c25c  lea     rsi, WPP_GLOBAL_Control
0x18000c263  cmp     rcx, rsi
0x18000c266  jz      loc_18000C65B
0x18000c26c  test    [rcx+1Ch], bl
0x18000c26f  jz      loc_18000C63B
0x18000c275  lea     edx, [rdi+1Eh]
0x18000c278  mov     r9d, eax
0x18000c27b  jmp     loc_18000C624
0x18000c280  mov     r8d, ebx; dwDesiredAccess
0x18000c283  lea     rdx, DatabaseName; "ServicesActive"
0x18000c28a  xor     ecx, ecx; lpMachineName
0x18000c28c  mov     r13d, ebx
0x18000c28f  call    cs:__imp_OpenSCManagerW
0x18000c296  nop     dword ptr [rax+rax+00h]
0x18000c29b  mov     r15, rax
0x18000c29e  test    rax, rax
0x18000c2a1  jnz     short loc_18000C2E2
0x18000c2a3  call    cs:__imp_GetLastError
0x18000c2aa  nop     dword ptr [rax+rax+00h]
0x18000c2af  test    eax, eax
0x18000c2b1  jle     short loc_18000C2BB
0x18000c2b3  movzx   eax, ax
0x18000c2b6  or      eax, 80070000h
0x18000c2bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2c2  lea     rsi, WPP_GLOBAL_Control
0x18000c2c9  cmp     rcx, rsi
0x18000c2cc  jz      loc_18000C65B
0x18000c2d2  test    [rcx+1Ch], bl
0x18000c2d5  jz      loc_18000C63B
0x18000c2db  mov     edx, 1Fh
0x18000c2e0  jmp     short loc_18000C278
0x18000c2e2  mov     r8d, esi; dwDesiredAccess
0x18000c2e5  lea     rdx, aNetprofm; "NetProfm"
0x18000c2ec  mov     rcx, rax; hSCManager
0x18000c2ef  call    cs:__imp_OpenServiceW
0x18000c2f6  nop     dword ptr [rax+rax+00h]
0x18000c2fb  mov     r12, rax
0x18000c2fe  test    rax, rax
0x18000c301  jnz     short loc_18000C345
0x18000c303  call    cs:__imp_GetLastError
0x18000c30a  nop     dword ptr [rax+rax+00h]
0x18000c30f  test    eax, eax
0x18000c311  jle     short loc_18000C31B
0x18000c313  movzx   eax, ax
0x18000c316  or      eax, 80070000h
0x18000c31b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c322  lea     rsi, WPP_GLOBAL_Control
0x18000c329  cmp     rcx, rsi
0x18000c32c  jz      loc_18000C65B
0x18000c332  test    [rcx+1Ch], bl
0x18000c335  jz      loc_18000C63B
0x18000c33b  mov     edx, 20h ; ' '
0x18000c340  jmp     loc_18000C278
0x18000c345  mov     esi, 10h
0x18000c34a  mov     ecx, esi
0x18000c34c  call    NcaAlloc
0x18000c351  test    rax, rax
0x18000c354  jz      loc_18000C601
0x18000c35a  mov     rcx, rax; this
0x18000c35d  call    ??0CNlmTriggerProfileEventSink@@QEAA@XZ; CNlmTriggerProfileEventSink::CNlmTriggerProfileEventSink(void)
0x18000c362  mov     rdi, rax
0x18000c365  test    rax, rax
0x18000c368  jz      loc_18000C601
0x18000c36e  mov     rax, [rax]
0x18000c371  lea     r8, [rbp+57h+var_D0+8]
0x18000c375  lea     rdx, IID_IUnknown
0x18000c37c  mov     rcx, rdi
0x18000c37f  mov     rax, [rax]
0x18000c382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c387  test    eax, eax
0x18000c389  jns     short loc_18000C3B5
0x18000c38b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c392  lea     rsi, WPP_GLOBAL_Control
0x18000c399  cmp     rcx, rsi
0x18000c39c  jz      loc_18000C65B
0x18000c3a2  test    [rcx+1Ch], bl
0x18000c3a5  jz      loc_18000C63B
0x18000c3ab  mov     edx, 22h ; '"'
0x18000c3b0  jmp     loc_18000C278
0x18000c3b5  mov     rcx, rsi
0x18000c3b8  call    NcaAlloc
0x18000c3bd  test    rax, rax
0x18000c3c0  jz      loc_18000C5E2
0x18000c3c6  mov     rcx, rax; this
0x18000c3c9  call    ??0CNlmTriggerInetConnEventSink@@QEAA@XZ; CNlmTriggerInetConnEventSink::CNlmTriggerInetConnEventSink(void)
0x18000c3ce  mov     r14, rax
0x18000c3d1  test    rax, rax
0x18000c3d4  jz      loc_18000C5E2
0x18000c3da  mov     rax, [rax]
0x18000c3dd  lea     r8, [rbp+57h+var_B8+8]
0x18000c3e1  lea     rdx, IID_IUnknown
0x18000c3e8  mov     rcx, r14
0x18000c3eb  mov     rax, [rax]
0x18000c3ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3f3  test    eax, eax
0x18000c3f5  jns     short loc_18000C421
0x18000c3f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3fe  lea     rsi, WPP_GLOBAL_Control
0x18000c405  cmp     rcx, rsi
0x18000c408  jz      loc_18000C65B
0x18000c40e  test    [rcx+1Ch], bl
0x18000c411  jz      loc_18000C63B
0x18000c417  mov     edx, 24h ; '$'
0x18000c41c  jmp     loc_18000C278
0x18000c421  lea     r8, [rbp+57h+pNotifyBuffer]; pNotifyBuffer
0x18000c425  mov     edx, 0Ch; dwNotifyMask
0x18000c42a  mov     rcx, r12; hService
0x18000c42d  call    cs:__imp_NotifyServiceStatusChangeW
0x18000c434  nop     dword ptr [rax+rax+00h]
0x18000c439  test    eax, eax
0x18000c43b  jz      short loc_18000C47F
0x18000c43d  call    cs:__imp_GetLastError
0x18000c444  nop     dword ptr [rax+rax+00h]
0x18000c449  test    eax, eax
0x18000c44b  jle     short loc_18000C455
0x18000c44d  movzx   eax, ax
0x18000c450  or      eax, 80070000h
0x18000c455  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c45c  lea     rsi, WPP_GLOBAL_Control
0x18000c463  cmp     rcx, rsi
0x18000c466  jz      loc_18000C65B
0x18000c46c  test    [rcx+1Ch], bl
0x18000c46f  jz      loc_18000C63B
0x18000c475  mov     edx, 25h ; '%'
0x18000c47a  jmp     loc_18000C278
0x18000c47f  lea     rsi, WPP_GLOBAL_Control
0x18000c486  mov     rcx, cs:qword_180028CD8; hHandle
0x18000c48d  mov     r8d, ebx; bAlertable
0x18000c490  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000c493  call    cs:__imp_WaitForSingleObjectEx
0x18000c49a  nop     dword ptr [rax+rax+00h]
0x18000c49f  test    eax, eax
0x18000c4a1  jz      loc_18000C634
0x18000c4a7  cmp     [rbp+57h+pNotifyBuffer.dwNotificationStatus], 0
0x18000c4ab  jnz     loc_18000C5C3
0x18000c4b1  mov     eax, [rbp+57h+pNotifyBuffer.ServiceStatus.dwCurrentState]
0x18000c4b4  cmp     eax, 4
0x18000c4b7  jnz     loc_18000C553
0x18000c4bd  lea     rdx, [rbp+57h+var_B8]; struct NCA_NLM_CONN_POINT_STATE *
0x18000c4c1  lea     rcx, [rbp+57h+var_D0]; struct NCA_NLM_CONN_POINT_STATE *
0x18000c4c5  call    ?NcaNlmTriggerConnectionPointObjectsRefresh@@YAJPEAUNCA_NLM_CONN_POINT_STATE@@0@Z; NcaNlmTriggerConnectionPointObjectsRefresh(NCA_NLM_CONN_POINT_STATE *,NCA_NLM_CONN_POINT_STATE *)
0x18000c4ca  test    eax, eax
0x18000c4cc  jns     short loc_18000C4F8
0x18000c4ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4d5  cmp     rcx, rsi
0x18000c4d8  jz      short loc_18000C4F8
0x18000c4da  test    byte ptr [rcx+1Ch], 4
0x18000c4de  jz      short loc_18000C4F8
0x18000c4e0  mov     rcx, [rcx+10h]
0x18000c4e4  lea     r8, WPP_e3f5ab3ee88d3b7229a13de75aa7d1b1_Traceguids
0x18000c4eb  mov     edx, 27h ; '''
0x18000c4f0  mov     r9d, eax
0x18000c4f3  call    WPP_SF_d
0x18000c4f8  lea     rcx, [rbp+57h+var_D0]; struct NCA_NLM_CONN_POINT_STATE *
0x18000c4fc  call    ?NcaNlmTriggerConnectionStateAdvice@@YAJPEAUNCA_NLM_CONN_POINT_STATE@@@Z; NcaNlmTriggerConnectionStateAdvice(NCA_NLM_CONN_POINT_STATE *)
0x18000c501  lea     rcx, [rbp+57h+var_B8]; struct NCA_NLM_CONN_POINT_STATE *
0x18000c505  mov     ebx, eax
0x18000c507  call    ?NcaNlmTriggerConnectionStateAdvice@@YAJPEAUNCA_NLM_CONN_POINT_STATE@@@Z; NcaNlmTriggerConnectionStateAdvice(NCA_NLM_CONN_POINT_STATE *)
0x18000c50c  mov     ecx, 8000000Ah
0x18000c511  cmp     ebx, ecx
0x18000c513  jz      short loc_18000C519
0x18000c515  cmp     eax, ecx
0x18000c517  jnz     short loc_18000C52C
0x18000c519  mov     ecx, 0FAh; dwMilliseconds
0x18000c51e  call    cs:__imp_Sleep
0x18000c525  nop     dword ptr [rax+rax+00h]
0x18000c52a  jmp     short loc_18000C4BD
0x18000c52c  xor     eax, eax
0x18000c52e  mov     ebx, r13d
0x18000c531  lock cmpxchg cs:dword_180028CE4, ebx
0x18000c539  lea     rcx, stru_180028CF0
0x18000c540  call    NcaSrcLnkdTriggerSignalTriggersInList
0x18000c545  lea     rcx, stru_180028D30
0x18000c54c  call    NcaSrcLnkdTriggerSignalTriggersInList
0x18000c551  jmp     short loc_18000C568
0x18000c553  dec     eax
0x18000c555  test    eax, 0FFFFFFFDh
0x18000c55a  jnz     short loc_18000C568
0x18000c55c  xor     ecx, ecx
0x18000c55e  mov     eax, ebx
0x18000c560  lock cmpxchg cs:dword_180028CE4, ecx
0x18000c568  lea     r8, [rbp+57h+pNotifyBuffer]; pNotifyBuffer
0x18000c56c  mov     edx, 0Ch; dwNotifyMask
0x18000c571  mov     rcx, r12; hService
0x18000c574  call    cs:__imp_NotifyServiceStatusChangeW
0x18000c57b  nop     dword ptr [rax+rax+00h]
0x18000c580  test    eax, eax
0x18000c582  jz      loc_18000C486
0x18000c588  call    cs:__imp_GetLastError
0x18000c58f  nop     dword ptr [rax+rax+00h]
0x18000c594  test    eax, eax
0x18000c596  jle     short loc_18000C5A0
0x18000c598  movzx   eax, ax
0x18000c59b  or      eax, 80070000h
0x18000c5a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5a7  cmp     rcx, rsi
0x18000c5aa  jz      loc_18000C65B
0x18000c5b0  test    [rcx+1Ch], bl
0x18000c5b3  jz      loc_18000C63B
0x18000c5b9  mov     edx, 28h ; '('
0x18000c5be  jmp     loc_18000C278
0x18000c5c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5ca  cmp     rcx, rsi
0x18000c5cd  jz      loc_18000C65B
0x18000c5d3  test    [rcx+1Ch], bl
0x18000c5d6  jz      short loc_18000C63B
0x18000c5d8  mov     edx, 26h ; '&'
0x18000c5dd  xor     r9d, r9d
0x18000c5e0  jmp     short loc_18000C624
0x18000c5e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5e9  lea     rsi, WPP_GLOBAL_Control
0x18000c5f0  cmp     rcx, rsi
0x18000c5f3  jz      short loc_18000C65B
0x18000c5f5  test    [rcx+1Ch], bl
0x18000c5f8  jz      short loc_18000C63B
0x18000c5fa  mov     edx, 23h ; '#'
0x18000c5ff  jmp     short loc_18000C61E
0x18000c601  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c608  lea     rsi, WPP_GLOBAL_Control
0x18000c60f  cmp     rcx, rsi
0x18000c612  jz      short loc_18000C65B
0x18000c614  test    [rcx+1Ch], bl
0x18000c617  jz      short loc_18000C63B
0x18000c619  mov     edx, 21h ; '!'
0x18000c61e  mov     r9d, 8007000Eh
0x18000c624  mov     rcx, [rcx+10h]
0x18000c628  lea     r8, WPP_e3f5ab3ee88d3b7229a13de75aa7d1b1_Traceguids
0x18000c62f  call    WPP_SF_d
0x18000c634  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c63b  cmp     rcx, rsi
0x18000c63e  jz      short loc_18000C65B
0x18000c640  test    byte ptr [rcx+1Ch], 4
0x18000c644  jz      short loc_18000C65B
0x18000c646  mov     rcx, [rcx+10h]
0x18000c64a  lea     r8, WPP_e3f5ab3ee88d3b7229a13de75aa7d1b1_Traceguids
0x18000c651  mov     edx, 29h ; ')'
0x18000c656  call    WPP_SF_
0x18000c65b  lea     rcx, [rbp+57h+var_D0]; struct NCA_NLM_CONN_POINT_STATE *
0x18000c65f  call    ?NcaNlmTriggerConnectionStateUnadviceRelease@@YAXPEAUNCA_NLM_CONN_POINT_STATE@@@Z; NcaNlmTriggerConnectionStateUnadviceRelease(NCA_NLM_CONN_POINT_STATE *)
0x18000c664  lea     rcx, [rbp+57h+var_B8]; struct NCA_NLM_CONN_POINT_STATE *
0x18000c668  call    ?NcaNlmTriggerConnectionStateUnadviceRelease@@YAXPEAUNCA_NLM_CONN_POINT_STATE@@@Z; NcaNlmTriggerConnectionStateUnadviceRelease(NCA_NLM_CONN_POINT_STATE *)
0x18000c66d  test    rdi, rdi
0x18000c670  jz      short loc_18000C689
0x18000c672  mov     rax, [rdi]
0x18000c675  mov     rcx, rdi
0x18000c678  mov     rax, [rax+10h]
0x18000c67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c681  mov     qword ptr [rbp+57h+var_D0+8], 0
0x18000c689  test    r14, r14
0x18000c68c  jz      short loc_18000C6A5
0x18000c68e  mov     rax, [r14]
0x18000c691  mov     rcx, r14
0x18000c694  mov     rax, [rax+10h]
0x18000c698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c69d  mov     qword ptr [rbp+57h+var_B8+8], 0
0x18000c6a5  mov     rcx, cs:?gNcaNlmTriggerComp@@3UNCA_NLM_TRIGGER_COMP_@@A; NCA_NLM_TRIGGER_COMP_ gNcaNlmTriggerComp
0x18000c6ac  test    rcx, rcx
0x18000c6af  jz      short loc_18000C6C8
0x18000c6b1  mov     rax, [rcx]
  ... truncated ...
```
