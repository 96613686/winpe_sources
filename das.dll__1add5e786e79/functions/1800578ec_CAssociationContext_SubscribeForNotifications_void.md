# CAssociationContext::SubscribeForNotifications(void)

- ea: `0x1800578ec`
- end: `0x180057aa3`
- name: `?SubscribeForNotifications@CAssociationContext@@IEAAJXZ`
- size: `439`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800549f4`
- `0x180054cc4`
- `0x18005508c`
- `0x180056878`
- `0x180056dd8`
- `0x180057aac`

## callees

- `0x180007500`
- `0x1800578ec`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005792a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005792a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005793c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800579b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005793c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800579b9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800579a7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800579a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180057a90`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180057a90`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x180057a15`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x180057a15`

## pseudocode

```c
__int64 __fastcall CAssociationContext::SubscribeForNotifications(PVOID pv)
{
  HANDLE EventW; // rax
  signed int v3; // eax
  int v4; // edx
  int v5; // r8d
  unsigned int v6; // ebx
  int v7; // r9d
  PTP_WAIT ThreadpoolWait; // rax
  signed int LastError; // eax
  RPC_STATUS v10; // eax
  int v11; // edx
  int v12; // r8d
  void *v13; // rdx
  struct _TP_WAIT *v14; // rcx
  RPC_ASYNC_NOTIFICATION_INFO NotificationInfo; // [rsp+30h] [rbp-28h] BYREF

  memset(&NotificationInfo, 0, sizeof(NotificationInfo));
  *((_DWORD *)pv + 94) = 0;
  if ( *((_QWORD *)pv + 79) || (EventW = CreateEventW(0, 0, 0, 0), (*((_QWORD *)pv + 79) = EventW) != 0) )
  {
    if ( *((_QWORD *)pv + 80)
      || (ThreadpoolWait = CreateThreadpoolWait(
                             (PTP_WAIT_CALLBACK)CAssociationContext::AsyncNotificationWaitCallback,
                             pv,
                             0),
          (*((_QWORD *)pv + 80) = ThreadpoolWait) != 0) )
    {
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)pv + 8LL))(pv);
      NotificationInfo.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)*((_QWORD *)pv + 79);
      v10 = RpcServerSubscribeForNotification(0, RpcNotificationCallCancel, RpcNotificationTypeEvent, &NotificationInfo);
      v6 = v10;
      if ( v10 )
      {
        if ( v10 >= 0 )
          v6 = (unsigned __int16)v10 | 0x80010000;
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v11,
            v12,
            118,
            &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
            v6);
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)pv + 16LL))(pv);
      }
      else
      {
        v13 = (void *)*((_QWORD *)pv + 79);
        v6 = 0;
        v14 = (struct _TP_WAIT *)*((_QWORD *)pv + 80);
        *((_DWORD *)pv + 94) = 1;
        SetThreadpoolWait(v14, v13, 0);
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
        v7 = 117;
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
      v7 = 116;
LABEL_7:
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v4,
        v5,
        v7,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        v6);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800578ec  mov     [rsp+arg_0], rbx
0x1800578f1  push    rdi
0x1800578f2  sub     rsp, 50h
0x1800578f6  xor     eax, eax
0x1800578f8  mov     qword ptr [rsp+58h+NotificationInfo], 0
0x180057901  xorps   xmm0, xmm0
0x180057904  mov     rdi, rcx
0x180057907  movups  xmmword ptr [rsp+58h+NotificationInfo+8], xmm0
0x18005790c  mov     qword ptr [rsp+58h+NotificationInfo+18h], rax
0x180057911  mov     [rcx+178h], eax
0x180057917  cmp     [rcx+278h], rax
0x18005791e  jnz     short loc_180057990
0x180057920  xor     r9d, r9d; lpName
0x180057923  xor     r8d, r8d; bInitialState
0x180057926  xor     edx, edx; bManualReset
0x180057928  xor     ecx, ecx; lpEventAttributes
0x18005792a  call    cs:__imp_CreateEventW
0x180057930  mov     [rdi+278h], rax
0x180057937  test    rax, rax
0x18005793a  jnz     short loc_180057990
0x18005793c  call    cs:__imp_GetLastError
0x180057942  mov     ebx, eax
0x180057944  test    eax, eax
0x180057946  jle     short loc_180057951
0x180057948  movzx   ebx, ax
0x18005794b  or      ebx, 80070000h
0x180057951  lea     rax, WPP_RECORDER_INITIALIZED
0x180057958  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005795f  jz      loc_180057A96
0x180057965  mov     r9d, 74h ; 't'; int
0x18005796b  mov     rcx, cs:WPP_GLOBAL_Control
0x180057972  lea     rax, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x180057979  mov     dword ptr [rsp+58h+var_30], ebx; char
0x18005797d  mov     [rsp+58h+MessageGuid], rax; MessageGuid
0x180057982  mov     rcx, [rcx+28h]; int
0x180057986  call    WPP_RECORDER_SF_D
0x18005798b  jmp     loc_180057A96
0x180057990  cmp     qword ptr [rdi+280h], 0
0x180057998  jnz     short loc_1800579EA
0x18005799a  xor     r8d, r8d; pcbe
0x18005799d  lea     rcx, ?AsyncNotificationWaitCallback@CAssociationContext@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800579a4  mov     rdx, rdi; pv
0x1800579a7  call    cs:__imp_CreateThreadpoolWait
0x1800579ad  mov     [rdi+280h], rax
0x1800579b4  test    rax, rax
0x1800579b7  jnz     short loc_1800579EA
0x1800579b9  call    cs:__imp_GetLastError
0x1800579bf  mov     ebx, eax
0x1800579c1  test    eax, eax
0x1800579c3  jle     short loc_1800579CE
0x1800579c5  movzx   ebx, ax
0x1800579c8  or      ebx, 80070000h
0x1800579ce  lea     rax, WPP_RECORDER_INITIALIZED
0x1800579d5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800579dc  jz      loc_180057A96
0x1800579e2  mov     r9d, 75h ; 'u'
0x1800579e8  jmp     short loc_18005796B
0x1800579ea  mov     rax, [rdi]
0x1800579ed  mov     rcx, rdi
0x1800579f0  mov     rax, [rax+8]
0x1800579f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800579f9  mov     rax, [rdi+278h]
0x180057a00  lea     r9, [rsp+58h+NotificationInfo]; NotificationInfo
0x180057a05  mov     edx, 2; Notification
0x180057a0a  mov     qword ptr [rsp+58h+NotificationInfo], rax
0x180057a0f  xor     ecx, ecx; Binding
0x180057a11  lea     r8d, [rdx-1]; NotificationType
0x180057a15  call    cs:__imp_RpcServerSubscribeForNotification
0x180057a1b  mov     ebx, eax
0x180057a1d  test    eax, eax
0x180057a1f  jz      short loc_180057A73
0x180057a21  js      short loc_180057A2C
0x180057a23  movzx   ebx, ax
0x180057a26  or      ebx, 80010000h
0x180057a2c  lea     rax, WPP_RECORDER_INITIALIZED
0x180057a33  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180057a3a  jz      short loc_180057A62
0x180057a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180057a43  lea     rax, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x180057a4a  mov     r9d, 76h ; 'v'; int
0x180057a50  mov     dword ptr [rsp+58h+var_30], ebx; char
0x180057a54  mov     [rsp+58h+MessageGuid], rax; MessageGuid
0x180057a59  mov     rcx, [rcx+28h]; int
0x180057a5d  call    WPP_RECORDER_SF_D
0x180057a62  mov     rax, [rdi]
0x180057a65  mov     rcx, rdi
0x180057a68  mov     rax, [rax+10h]
0x180057a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a71  jmp     short loc_180057A96
0x180057a73  mov     rdx, [rdi+278h]; h
0x180057a7a  xor     ebx, ebx
0x180057a7c  mov     rcx, [rdi+280h]; pwa
0x180057a83  xor     r8d, r8d; pftTimeout
0x180057a86  mov     dword ptr [rdi+178h], 1
0x180057a90  call    cs:__imp_SetThreadpoolWait
0x180057a96  mov     eax, ebx
0x180057a98  mov     rbx, [rsp+58h+arg_0]
0x180057a9d  add     rsp, 50h
0x180057aa1  pop     rdi
0x180057aa2  retn
```
