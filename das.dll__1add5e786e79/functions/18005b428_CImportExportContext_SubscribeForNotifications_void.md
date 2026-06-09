# CImportExportContext::SubscribeForNotifications(void)

- ea: `0x18005b428`
- end: `0x18005b5df`
- name: `?SubscribeForNotifications@CImportExportContext@@IEAAJXZ`
- size: `439`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18005aac8`
- `0x18005ae54`

## callees

- `0x180007500`
- `0x18005b428`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005b466`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005b466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b4f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b4f5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005b4e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005b4e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005b5cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005b5cc`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18005b551`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18005b551`

## pseudocode

```c
__int64 __fastcall CImportExportContext::SubscribeForNotifications(PVOID pv)
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
  *((_DWORD *)pv + 72) = 0;
  if ( *((_QWORD *)pv + 34) || (EventW = CreateEventW(0, 0, 0, 0), (*((_QWORD *)pv + 34) = EventW) != 0) )
  {
    if ( *((_QWORD *)pv + 35)
      || (ThreadpoolWait = CreateThreadpoolWait(CImportExportContext::AsyncNotificationWaitCallback, pv, 0),
          (*((_QWORD *)pv + 35) = ThreadpoolWait) != 0) )
    {
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)pv + 8LL))(pv);
      NotificationInfo.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)*((_QWORD *)pv + 34);
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
            61,
            &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
            v6);
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)pv + 16LL))(pv);
      }
      else
      {
        v13 = (void *)*((_QWORD *)pv + 34);
        v6 = 0;
        v14 = (struct _TP_WAIT *)*((_QWORD *)pv + 35);
        *((_DWORD *)pv + 72) = 1;
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
        v7 = 60;
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
      v7 = 59;
LABEL_7:
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v4,
        v5,
        v7,
        &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
        v6);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18005b428  mov     [rsp+arg_0], rbx
0x18005b42d  push    rdi
0x18005b42e  sub     rsp, 50h
0x18005b432  xor     eax, eax
0x18005b434  mov     qword ptr [rsp+58h+NotificationInfo], 0
0x18005b43d  xorps   xmm0, xmm0
0x18005b440  mov     rdi, rcx
0x18005b443  movups  xmmword ptr [rsp+58h+NotificationInfo+8], xmm0
0x18005b448  mov     qword ptr [rsp+58h+NotificationInfo+18h], rax
0x18005b44d  mov     [rcx+120h], eax
0x18005b453  cmp     [rcx+110h], rax
0x18005b45a  jnz     short loc_18005B4CC
0x18005b45c  xor     r9d, r9d; lpName
0x18005b45f  xor     r8d, r8d; bInitialState
0x18005b462  xor     edx, edx; bManualReset
0x18005b464  xor     ecx, ecx; lpEventAttributes
0x18005b466  call    cs:__imp_CreateEventW
0x18005b46c  mov     [rdi+110h], rax
0x18005b473  test    rax, rax
0x18005b476  jnz     short loc_18005B4CC
0x18005b478  call    cs:__imp_GetLastError
0x18005b47e  mov     ebx, eax
0x18005b480  test    eax, eax
0x18005b482  jle     short loc_18005B48D
0x18005b484  movzx   ebx, ax
0x18005b487  or      ebx, 80070000h
0x18005b48d  lea     rax, WPP_RECORDER_INITIALIZED
0x18005b494  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005b49b  jz      loc_18005B5D2
0x18005b4a1  mov     r9d, 3Bh ; ';'; int
0x18005b4a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b4ae  lea     rax, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x18005b4b5  mov     dword ptr [rsp+58h+var_30], ebx; char
0x18005b4b9  mov     [rsp+58h+MessageGuid], rax; MessageGuid
0x18005b4be  mov     rcx, [rcx+28h]; int
0x18005b4c2  call    WPP_RECORDER_SF_D
0x18005b4c7  jmp     loc_18005B5D2
0x18005b4cc  cmp     qword ptr [rdi+118h], 0
0x18005b4d4  jnz     short loc_18005B526
0x18005b4d6  xor     r8d, r8d; pcbe
0x18005b4d9  lea     rcx, ?AsyncNotificationWaitCallback@CImportExportContext@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18005b4e0  mov     rdx, rdi; pv
0x18005b4e3  call    cs:__imp_CreateThreadpoolWait
0x18005b4e9  mov     [rdi+118h], rax
0x18005b4f0  test    rax, rax
0x18005b4f3  jnz     short loc_18005B526
0x18005b4f5  call    cs:__imp_GetLastError
0x18005b4fb  mov     ebx, eax
0x18005b4fd  test    eax, eax
0x18005b4ff  jle     short loc_18005B50A
0x18005b501  movzx   ebx, ax
0x18005b504  or      ebx, 80070000h
0x18005b50a  lea     rax, WPP_RECORDER_INITIALIZED
0x18005b511  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005b518  jz      loc_18005B5D2
0x18005b51e  mov     r9d, 3Ch ; '<'
0x18005b524  jmp     short loc_18005B4A7
0x18005b526  mov     rax, [rdi]
0x18005b529  mov     rcx, rdi
0x18005b52c  mov     rax, [rax+8]
0x18005b530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b535  mov     rax, [rdi+110h]
0x18005b53c  lea     r9, [rsp+58h+NotificationInfo]; NotificationInfo
0x18005b541  mov     edx, 2; Notification
0x18005b546  mov     qword ptr [rsp+58h+NotificationInfo], rax
0x18005b54b  xor     ecx, ecx; Binding
0x18005b54d  lea     r8d, [rdx-1]; NotificationType
0x18005b551  call    cs:__imp_RpcServerSubscribeForNotification
0x18005b557  mov     ebx, eax
0x18005b559  test    eax, eax
0x18005b55b  jz      short loc_18005B5AF
0x18005b55d  js      short loc_18005B568
0x18005b55f  movzx   ebx, ax
0x18005b562  or      ebx, 80010000h
0x18005b568  lea     rax, WPP_RECORDER_INITIALIZED
0x18005b56f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005b576  jz      short loc_18005B59E
0x18005b578  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b57f  lea     rax, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x18005b586  mov     r9d, 3Dh ; '='; int
0x18005b58c  mov     dword ptr [rsp+58h+var_30], ebx; char
0x18005b590  mov     [rsp+58h+MessageGuid], rax; MessageGuid
0x18005b595  mov     rcx, [rcx+28h]; int
0x18005b599  call    WPP_RECORDER_SF_D
0x18005b59e  mov     rax, [rdi]
0x18005b5a1  mov     rcx, rdi
0x18005b5a4  mov     rax, [rax+10h]
0x18005b5a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b5ad  jmp     short loc_18005B5D2
0x18005b5af  mov     rdx, [rdi+110h]; h
0x18005b5b6  xor     ebx, ebx
0x18005b5b8  mov     rcx, [rdi+118h]; pwa
0x18005b5bf  xor     r8d, r8d; pftTimeout
0x18005b5c2  mov     dword ptr [rdi+120h], 1
0x18005b5cc  call    cs:__imp_SetThreadpoolWait
0x18005b5d2  mov     eax, ebx
0x18005b5d4  mov     rbx, [rsp+58h+arg_0]
0x18005b5d9  add     rsp, 50h
0x18005b5dd  pop     rdi
0x18005b5de  retn
```
