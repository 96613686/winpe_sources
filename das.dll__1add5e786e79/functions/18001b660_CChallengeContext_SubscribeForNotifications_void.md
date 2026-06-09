# CChallengeContext::SubscribeForNotifications(void)

- ea: `0x18001b660`
- end: `0x18001b7fc`
- name: `?SubscribeForNotifications@CChallengeContext@@IEAAJXZ`
- size: `412`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b24c`

## callees

- `0x180007500`
- `0x18001b660`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b69e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b69e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b72d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b72d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001b71b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001b71b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001b7e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001b7e9`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18001b789`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18001b789`

## pseudocode

```c
__int64 __fastcall CChallengeContext::SubscribeForNotifications(PVOID pv)
{
  HANDLE EventW; // rax
  signed int v3; // eax
  int v4; // edx
  int v5; // r8d
  int v6; // ebx
  int v7; // r9d
  PTP_WAIT ThreadpoolWait; // rax
  signed int LastError; // eax
  void *v10; // rdx
  struct _TP_WAIT *v11; // rcx
  RPC_ASYNC_NOTIFICATION_INFO NotificationInfo; // [rsp+30h] [rbp-28h] BYREF

  memset(&NotificationInfo, 0, sizeof(NotificationInfo));
  *((_DWORD *)pv + 72) = 0;
  if ( *((_QWORD *)pv + 34) || (EventW = CreateEventW(0, 0, 0, 0), (*((_QWORD *)pv + 34) = EventW) != 0) )
  {
    if ( *((_QWORD *)pv + 35)
      || (ThreadpoolWait = CreateThreadpoolWait(CChallengeContext::AsyncNotificationWaitCallback, pv, 0),
          (*((_QWORD *)pv + 35) = ThreadpoolWait) != 0) )
    {
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)pv + 8LL))(pv);
      NotificationInfo.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)*((_QWORD *)pv + 34);
      v6 = RpcServerSubscribeForNotification(0, RpcNotificationCallCancel, RpcNotificationTypeEvent, &NotificationInfo);
      if ( !v6 )
      {
        v10 = (void *)*((_QWORD *)pv + 34);
        v6 = 0;
        v11 = (struct _TP_WAIT *)*((_QWORD *)pv + 35);
        *((_DWORD *)pv + 72) = 1;
        SetThreadpoolWait(v11, v10, 0);
        return (unsigned int)v6;
      }
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)pv + 16LL))(pv);
      if ( v6 >= 0 )
        v6 = (unsigned __int16)v6 | 0x80010000;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v7 = 35;
        goto LABEL_7;
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v7 = 34;
        goto LABEL_7;
      }
    }
  }
  else
  {
    v3 = GetLastError();
    v6 = v3;
    if ( v3 > 0 )
      v6 = (unsigned __int16)v3 | 0x80070000;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v7 = 33;
LABEL_7:
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v4,
        v5,
        v7,
        &WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids,
        v6);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001b660  mov     [rsp+arg_0], rbx
0x18001b665  push    rdi
0x18001b666  sub     rsp, 50h
0x18001b66a  xor     eax, eax
0x18001b66c  mov     qword ptr [rsp+58h+NotificationInfo], 0
0x18001b675  xorps   xmm0, xmm0
0x18001b678  mov     rdi, rcx
0x18001b67b  movups  xmmword ptr [rsp+58h+NotificationInfo+8], xmm0
0x18001b680  mov     qword ptr [rsp+58h+NotificationInfo+18h], rax
0x18001b685  mov     [rcx+120h], eax
0x18001b68b  cmp     [rcx+110h], rax
0x18001b692  jnz     short loc_18001B704
0x18001b694  xor     r9d, r9d; lpName
0x18001b697  xor     r8d, r8d; bInitialState
0x18001b69a  xor     edx, edx; bManualReset
0x18001b69c  xor     ecx, ecx; lpEventAttributes
0x18001b69e  call    cs:__imp_CreateEventW
0x18001b6a4  mov     [rdi+110h], rax
0x18001b6ab  test    rax, rax
0x18001b6ae  jnz     short loc_18001B704
0x18001b6b0  call    cs:__imp_GetLastError
0x18001b6b6  mov     ebx, eax
0x18001b6b8  test    eax, eax
0x18001b6ba  jle     short loc_18001B6C5
0x18001b6bc  movzx   ebx, ax
0x18001b6bf  or      ebx, 80070000h
0x18001b6c5  lea     rax, WPP_RECORDER_INITIALIZED
0x18001b6cc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001b6d3  jz      loc_18001B7EF
0x18001b6d9  mov     r9d, 21h ; '!'; int
0x18001b6df  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6e6  lea     rax, WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids
0x18001b6ed  mov     dword ptr [rsp+58h+var_30], ebx; char
0x18001b6f1  mov     [rsp+58h+MessageGuid], rax; MessageGuid
0x18001b6f6  mov     rcx, [rcx+28h]; int
0x18001b6fa  call    WPP_RECORDER_SF_D
0x18001b6ff  jmp     loc_18001B7EF
0x18001b704  cmp     qword ptr [rdi+118h], 0
0x18001b70c  jnz     short loc_18001B75E
0x18001b70e  xor     r8d, r8d; pcbe
0x18001b711  lea     rcx, ?AsyncNotificationWaitCallback@CChallengeContext@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18001b718  mov     rdx, rdi; pv
0x18001b71b  call    cs:__imp_CreateThreadpoolWait
0x18001b721  mov     [rdi+118h], rax
0x18001b728  test    rax, rax
0x18001b72b  jnz     short loc_18001B75E
0x18001b72d  call    cs:__imp_GetLastError
0x18001b733  mov     ebx, eax
0x18001b735  test    eax, eax
0x18001b737  jle     short loc_18001B742
0x18001b739  movzx   ebx, ax
0x18001b73c  or      ebx, 80070000h
0x18001b742  lea     rax, WPP_RECORDER_INITIALIZED
0x18001b749  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001b750  jz      loc_18001B7EF
0x18001b756  mov     r9d, 22h ; '"'
0x18001b75c  jmp     short loc_18001B6DF
0x18001b75e  mov     rax, [rdi]
0x18001b761  mov     rcx, rdi
0x18001b764  mov     rax, [rax+8]
0x18001b768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b76d  mov     rax, [rdi+110h]
0x18001b774  lea     r9, [rsp+58h+NotificationInfo]; NotificationInfo
0x18001b779  mov     edx, 2; Notification
0x18001b77e  mov     qword ptr [rsp+58h+NotificationInfo], rax
0x18001b783  xor     ecx, ecx; Binding
0x18001b785  lea     r8d, [rdx-1]; NotificationType
0x18001b789  call    cs:__imp_RpcServerSubscribeForNotification
0x18001b78f  mov     ebx, eax
0x18001b791  test    eax, eax
0x18001b793  jz      short loc_18001B7CC
0x18001b795  mov     rax, [rdi]
0x18001b798  mov     rcx, rdi
0x18001b79b  mov     rax, [rax+10h]
0x18001b79f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7a4  test    ebx, ebx
0x18001b7a6  js      short loc_18001B7B1
0x18001b7a8  movzx   ebx, bx
0x18001b7ab  or      ebx, 80010000h
0x18001b7b1  lea     rax, WPP_RECORDER_INITIALIZED
0x18001b7b8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001b7bf  jz      short loc_18001B7EF
0x18001b7c1  mov     r9d, 23h ; '#'
0x18001b7c7  jmp     loc_18001B6DF
0x18001b7cc  mov     rdx, [rdi+110h]; h
0x18001b7d3  xor     ebx, ebx
0x18001b7d5  mov     rcx, [rdi+118h]; pwa
0x18001b7dc  xor     r8d, r8d; pftTimeout
0x18001b7df  mov     dword ptr [rdi+120h], 1
0x18001b7e9  call    cs:__imp_SetThreadpoolWait
0x18001b7ef  mov     eax, ebx
0x18001b7f1  mov     rbx, [rsp+58h+arg_0]
0x18001b7f6  add     rsp, 50h
0x18001b7fa  pop     rdi
0x18001b7fb  retn
```
