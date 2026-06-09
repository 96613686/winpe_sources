# AsyncNotificationCallback(void *,uchar)

- ea: `0x18005b600`
- end: `0x18005bee9`
- name: `?AsyncNotificationCallback@@YAXPEAXE@Z`
- size: `2281`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18005cce8`

## callees

- `0x18001236c`
- `0x180025478`
- `0x18005b05c`
- `0x18005b0b0`
- `0x18005b600`
- `0x18005c960`
- `0x18005cce8`
- `0x18005cea0`
- `0x18005cfcc`
- `0x18005ffe4`
- `0x18006f910`
- `0x18009e2d8`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18005b655`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005b655`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005bebe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005bebe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bdf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bdf5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005bb57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005bb57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005be8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005be8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b89c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bd8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005be27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b89c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bd8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005be27`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b735`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b994`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ba67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bba0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bc5b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bd08`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b735`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b994`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ba67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bba0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bc5b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bd08`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005b6c9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005b6c9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18005be84`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18005be84`

## string_xrefs

- `0x18005bb0b`: `Received ERROR_INVALID_FUNCTION in NotifyThread. Going to exit..`
- `0x18005be2f`: `ERROR_INVALID_PARAMETER detected in NotifyThread, continuing`
- `0x18005bd9d`: `MystrlenW Failed in NotifyThread, posting reconnect packets and continuing.`
- `0x18005bc89`: `Failed StringCopy in NotifyThread, posting reconnect packets and continuing.`
- `0x18005bdfe`: `Cluster is dead, exiting notify thread`
- `0x18005be94`: `NotifyThread broken out of loop, exiting.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AsyncNotificationCallback(char *a1)
{
  unsigned int v2; // r14d
  __int64 v3; // rdi
  __int64 v4; // r15
  char i; // al
  unsigned int v6; // ecx
  RPC_STATUS v7; // eax
  char *v8; // rax
  char *v9; // rbx
  __int64 v10; // r9
  unsigned int k; // r15d
  __int64 v12; // rcx
  __int64 v13; // rax
  char *v14; // rax
  unsigned int j; // r15d
  __int64 v16; // rcx
  char *v17; // rax
  const wchar_t *v18; // r13
  __int64 *v19; // rax
  __int64 *v20; // r15
  char *v21; // rax
  _DWORD *v22; // r14
  __int64 v23; // rdx
  unsigned int v24; // r12d
  wchar_t *v25; // rax
  __int64 v26; // r8
  __int64 v27; // r9
  unsigned int v28; // r12d
  wchar_t *v29; // rax
  __int64 v30; // [rsp+28h] [rbp-51h]
  __int64 v31; // [rsp+30h] [rbp-49h]
  __int64 v32; // [rsp+38h] [rbp-41h]
  __int64 v33; // [rsp+40h] [rbp-39h]
  __int64 v34; // [rsp+48h] [rbp-31h] BYREF
  int v35; // [rsp+50h] [rbp-29h]
  int v36; // [rsp+54h] [rbp-25h]
  __int64 v37; // [rsp+58h] [rbp-21h] BYREF
  int v38; // [rsp+60h] [rbp-19h]
  int v39; // [rsp+64h] [rbp-15h]
  __int128 v40; // [rsp+68h] [rbp-11h] BYREF
  __int64 *v41; // [rsp+78h] [rbp-1h]
  __int128 v42; // [rsp+80h] [rbp+7h] BYREF
  __int64 *v43; // [rsp+90h] [rbp+17h]
  unsigned int Reply; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v45; // [rsp+F0h] [rbp+77h] BYREF
  char *v46; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = 0;
  v3 = *(_QWORD *)a1;
  v4 = *(_QWORD *)(*(_QWORD *)a1 + 48LL);
  v33 = v4;
  for ( i = 0; ; i = 1 )
  {
    if ( i )
    {
      IssueAsyncNotification((struct _NotifyThreadContext *)a1);
      return;
    }
    v6 = 0;
    Reply = 0;
    v7 = *((_DWORD *)a1 + 2);
    if ( !v7 )
    {
      v7 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)(a1 + 56), &Reply);
      *((_DWORD *)a1 + 2) = v7;
      v6 = Reply;
      if ( !v7 )
      {
        *((_DWORD *)a1 + 2) = 0;
        v7 = 0;
      }
    }
    if ( v6 || v7 )
    {
      ++*((_DWORD *)a1 + 3);
      LODWORD(v31) = v7;
      LODWORD(v30) = v6;
      TraceMsg(
        4,
        0,
        L"Clusapi",
        0,
        L"Getting an AsyncNotification exited with cluster_error = %d, rpc_error = %d",
        v30,
        v31);
      v2 = ReconnectCluster((struct _CLUSTER *)v4, *((_DWORD *)a1 + 2), Reply, *((_DWORD *)a1 + 4), 1);
      if ( !v2 )
      {
        if ( *((_DWORD *)a1 + 3) > 0x20u )
          Sleep(0x1F4u);
        if ( *((_DWORD *)a1 + 3) <= 0x40u )
        {
          v2 = 0;
          continue;
        }
        v2 = *((_DWORD *)a1 + 2);
      }
    }
    *((_DWORD *)a1 + 3) = 0;
    v36 = 0;
    v35 = *((_DWORD *)a1 + 42);
    v34 = *((_QWORD *)a1 + 5);
    v42 = 0;
    v43 = &v34;
    v39 = 0;
    v38 = v35;
    v37 = *((_QWORD *)a1 + 6);
    v40 = 0;
    v41 = &v37;
    if ( v2 == 14 )
    {
      NotifyPortReconnect((struct _CNOTIFY_SESSION *)v3);
      goto LABEL_83;
    }
    v8 = (char *)LocalAlloc(0, 0x80u);
    v9 = v8;
    v46 = v8;
    if ( !v8 )
    {
      NotifyPortReconnect((struct _CNOTIFY_SESSION *)v3);
      goto LABEL_50;
    }
    *((_QWORD *)v8 + 15) = v3;
    *((_QWORD *)v8 + 13) = 0;
    *((_QWORD *)v8 + 12) = 0;
    *((_QWORD *)v8 + 10) = 0;
    *((_QWORD *)v8 + 11) = 0;
    *((_QWORD *)v8 + 4) = 0;
    *((_QWORD *)v8 + 8) = 0;
    *((_DWORD *)v8 + 18) = 0;
    *((_DWORD *)v8 + 12) = 0;
    *((_QWORD *)v8 + 7) = 0;
    *((_QWORD *)v8 + 3) = 0;
    *((_QWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 5) = 0;
    *((_QWORD *)v8 + 14) = 0;
    if ( v2 )
      break;
    if ( *(_DWORD *)(*(_QWORD *)a1 + 96LL) == 1 )
    {
      if ( !*((_QWORD *)a1 + 6) )
      {
        v10 = 1732;
        goto LABEL_33;
      }
      for ( j = 0; j < *((_DWORD *)a1 + 42); ++j )
      {
        v16 = *((_QWORD *)a1 + 6);
        *((_DWORD *)v9 + 5) = *(_DWORD *)(v16 + 16LL * j);
        *((_DWORD *)v9 + 6) = *(_DWORD *)(v16 + 16LL * j + 4);
        *((_DWORD *)v9 + 4) = 0;
        *((_QWORD *)v9 + 4) = *(_QWORD *)(v16 + 16LL * j + 8);
        *(_QWORD *)(v16 + 16LL * j + 8) = 0;
        ClRtlInsertTailQueue(*(_QWORD *)(v3 + 80) + 56LL, v9);
        if ( j != *((_DWORD *)a1 + 42) - 1 )
        {
          v17 = (char *)LocalAlloc(0, 0x80u);
          v9 = v17;
          if ( v17 )
          {
            *((_QWORD *)v17 + 15) = v3;
            *((_QWORD *)v17 + 13) = 0;
            *((_QWORD *)v17 + 12) = 0;
            *((_QWORD *)v17 + 10) = 0;
            *((_QWORD *)v17 + 11) = 0;
            *((_QWORD *)v17 + 4) = 0;
            *((_QWORD *)v17 + 8) = 0;
            *((_DWORD *)v17 + 18) = 0;
            *((_DWORD *)v17 + 12) = 0;
            *((_QWORD *)v17 + 7) = 0;
            *((_QWORD *)v17 + 3) = 0;
            *((_QWORD *)v17 + 2) = 0;
            *((_QWORD *)v17 + 5) = 0;
            *((_QWORD *)v17 + 14) = 0;
          }
          else
          {
            NotifyPortReconnect((struct _CNOTIFY_SESSION *)v3);
          }
        }
      }
    }
    else
    {
      if ( *(_DWORD *)(*(_QWORD *)a1 + 96LL) != 2 )
        goto LABEL_50;
      if ( !*((_QWORD *)a1 + 5) )
      {
        v10 = 1799;
LABEL_33:
        TraceMsg(4, 7, L"AsyncNotificationCallback", v10, L"RPC returned null data for notifications and no error");
        std::unique_ptr<AsyncNotificationArrayDeleterStruct,AsyncNotificationArrayDeleterStruct>::~unique_ptr<AsyncNotificationArrayDeleterStruct,AsyncNotificationArrayDeleterStruct>(&v40);
        std::unique_ptr<NotificationArrayDeleterStruct,NotificationArrayDeleterStruct>::~unique_ptr<NotificationArrayDeleterStruct,NotificationArrayDeleterStruct>(&v42);
        continue;
      }
      for ( k = 0; k < *((_DWORD *)a1 + 42); ++k )
      {
        v12 = 9LL * k;
        v13 = *((_QWORD *)a1 + 5);
        *(_OWORD *)(v9 + 40) = *(_OWORD *)(v13 + 72LL * k);
        *(_OWORD *)(v9 + 56) = *(_OWORD *)(v13 + 72LL * k + 16);
        *(_OWORD *)(v9 + 72) = *(_OWORD *)(v13 + 72LL * k + 32);
        *(_OWORD *)(v9 + 88) = *(_OWORD *)(v13 + 72LL * k + 48);
        *((_QWORD *)v9 + 13) = *(_QWORD *)(v13 + 72LL * k + 64);
        *(_QWORD *)(v13 + 8 * v12 + 24) = 0;
        *(_QWORD *)(v13 + 8 * v12 + 40) = 0;
        *(_QWORD *)(v13 + 8 * v12 + 48) = 0;
        *(_QWORD *)(v13 + 8 * v12 + 56) = 0;
        *(_QWORD *)(v13 + 8 * v12 + 64) = 0;
        *((_DWORD *)v9 + 5) = *((_DWORD *)v9 + 10);
        *((_DWORD *)v9 + 4) = 0;
        ClRtlInsertTailQueue(*(_QWORD *)(v3 + 80) + 56LL, v9);
        if ( k != *((_DWORD *)a1 + 42) - 1 )
        {
          v14 = (char *)LocalAlloc(0, 0x80u);
          v9 = v14;
          if ( v14 )
          {
            *((_QWORD *)v14 + 15) = v3;
            *((_QWORD *)v14 + 13) = 0;
            *((_QWORD *)v14 + 12) = 0;
            *((_QWORD *)v14 + 10) = 0;
            *((_QWORD *)v14 + 11) = 0;
            *((_QWORD *)v14 + 4) = 0;
            *((_QWORD *)v14 + 8) = 0;
            *((_DWORD *)v14 + 18) = 0;
            *((_DWORD *)v14 + 12) = 0;
            *((_QWORD *)v14 + 7) = 0;
            *((_QWORD *)v14 + 3) = 0;
            *((_QWORD *)v14 + 2) = 0;
            *((_QWORD *)v14 + 5) = 0;
            *((_QWORD *)v14 + 14) = 0;
          }
          else
          {
            NotifyPortReconnect((struct _CNOTIFY_SESSION *)v3);
          }
        }
      }
    }
    v4 = v33;
LABEL_50:
    std::unique_ptr<AsyncNotificationArrayDeleterStruct,AsyncNotificationArrayDeleterStruct>::~unique_ptr<AsyncNotificationArrayDeleterStruct,AsyncNotificationArrayDeleterStruct>(&v40);
    std::unique_ptr<NotificationArrayDeleterStruct,NotificationArrayDeleterStruct>::~unique_ptr<NotificationArrayDeleterStruct,NotificationArrayDeleterStruct>(&v42);
    if ( v2 )
      goto LABEL_84;
  }
  LODWORD(v32) = *((_DWORD *)a1 + 2);
  LODWORD(v31) = v2;
  TraceMsg(
    3,
    7,
    L"AsyncNotificationCallback",
    1499,
    L"ApiGetNotify on hNotify=0x%p returns %u with rpc_error %u",
    *(_QWORD *)(v3 + 56),
    v31,
    v32);
  if ( v2 == 259 )
  {
    if ( !*(_QWORD *)(v3 + 56) )
      goto LABEL_53;
    v2 = 0;
    FreePacket(&v46, *(unsigned int *)(v3 + 96), 0);
    TraceMsg(4, 7, L"AsyncNotificationCallback", 1509, L"mapping error to success");
    goto LABEL_50;
  }
  if ( v2 == 1 )
  {
    FreePacket(&v46, *(unsigned int *)(v3 + 96), 0);
    if ( !*(_DWORD *)(v3 + 92) )
    {
      *(_DWORD *)(v3 + 288) = 1523;
      *(_DWORD *)(v3 + 284) = 1;
      *(_DWORD *)(v3 + 280) = *((_DWORD *)a1 + 2);
      TraceMsg(
        4,
        7,
        L"AsyncNotificationCallback",
        1524,
        L"Received ERROR_INVALID_FUNCTION in NotifyThread. Going to exit..");
      goto LABEL_83;
    }
    *(_DWORD *)(v3 + 92) = 0;
    v2 = 0;
    goto LABEL_50;
  }
  if ( v2 != 87 )
  {
    if ( *(_QWORD *)(v3 + 56) && (*(_BYTE *)(v4 + 32) & 2) == 0 && v2 != 1722 )
    {
      *(_DWORD *)(v3 + 288) = 1715;
      *(_DWORD *)(v3 + 284) = v2;
      *(_DWORD *)(v3 + 280) = *((_DWORD *)a1 + 2);
      NotifyPortReconnect((struct _CNOTIFY_SESSION *)v3);
      LocalFree(v9);
      goto LABEL_50;
    }
LABEL_53:
    *(_DWORD *)(v3 + 288) = 1546;
    *(_DWORD *)(v3 + 284) = v2;
    *(_DWORD *)(v3 + 280) = *((_DWORD *)a1 + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 232));
    v18 = *(const wchar_t **)(v4 + 16);
    v19 = (__int64 *)(v3 + 32);
    v20 = *(__int64 **)(v3 + 32);
    while ( 2 )
    {
      if ( v20 == v19 )
      {
LABEL_80:
        LeaveCriticalSection((LPCRITICAL_SECTION)(v33 + 232));
        v2 = 0;
        TraceMsg(4, 7, L"AsyncNotificationCallback", 1703, L"Cluster is dead, exiting notify thread");
        LocalFree(v9);
        goto LABEL_83;
      }
      if ( (v20[5] & 0x20000000) == 0 && (*((_DWORD *)v20 + 28) != 1 || (v20[15] & 2) == 0) )
        goto LABEL_76;
      if ( !v9 )
      {
        v21 = (char *)LocalAlloc(0, 0x80u);
        v9 = v21;
        v46 = v21;
        if ( !v21 )
        {
          LocalFree(0);
LABEL_78:
          NotifyPortReconnect((struct _CNOTIFY_SESSION *)v3);
          goto LABEL_80;
        }
        *((_QWORD *)v21 + 15) = v3;
        *((_QWORD *)v21 + 13) = 0;
        *((_QWORD *)v21 + 12) = 0;
        *((_QWORD *)v21 + 10) = 0;
        *((_QWORD *)v21 + 11) = 0;
        *((_QWORD *)v21 + 4) = 0;
        *((_QWORD *)v21 + 8) = 0;
        *((_DWORD *)v21 + 18) = 0;
        *((_DWORD *)v21 + 12) = 0;
        *((_QWORD *)v21 + 7) = 0;
        *((_QWORD *)v21 + 3) = 0;
        *((_QWORD *)v21 + 2) = 0;
        *((_QWORD *)v21 + 5) = 0;
        *((_QWORD *)v21 + 14) = 0;
      }
      v22 = (_DWORD *)(v3 + 96);
      if ( (unsigned int)MIDLAllocateUnusedStringPacketValuesToEmpty(&v46, *(unsigned int *)(v3 + 96)) )
        goto LABEL_78;
      *((_DWORD *)v9 + 4) = 0;
      v45 = 0;
      if ( MylstrlenW(v18, 0x7FFFFFFFu, &v45) )
      {
        TraceMsg(
          4,
          7,
          L"AsyncNotificationCallback",
          1605,
          L"MystrlenW Failed in NotifyThread, posting reconnect packets and continuing.");
        FreePacket(&v46, (unsigned int)*v22, 0);
        NotifyPortReconnect((struct _CNOTIFY_SESSION *)v3);
        goto LABEL_80;
      }
      v23 = v45 + 1;
      if ( *v22 == 1 )
      {
        *((_DWORD *)v9 + 6) = 0x20000000;
        *((_DWORD *)v9 + 5) = *((_DWORD *)v20 + 15);
        v28 = v23;
        v29 = (wchar_t *)LocalAlloc(0x40u, 2 * v23);
        *((_QWORD *)v9 + 4) = v29;
        if ( v29 )
        {
          if ( (int)StringCchCopyW(v29, v28, v18) >= 0 )
            goto LABEL_70;
          v27 = 1627;
LABEL_68:
          TraceMsg(
            4,
            7,
            L"AsyncNotificationCallback",
            v27,
            L"Failed StringCopy in NotifyThread, posting reconnect packets and continuing.");
        }
      }
      else
      {
        if ( *v22 != 2 )
          goto LABEL_70;
        *((_QWORD *)v9 + 5) = *((unsigned int *)v20 + 15);
        *((_DWORD *)v9 + 12) = 1;
        *((_QWORD *)v9 + 7) = 2;
        v24 = v23;
        v25 = (wchar_t *)LocalAlloc(0x40u, 2 * v23);
        *((_QWORD *)v9 + 12) = v25;
        if ( v25 )
        {
          if ( (int)StringCchCopyW(v25, v24, v18) < 0 )
          {
            v27 = 1660;
            goto LABEL_68;
          }
          *((_DWORD *)v9 + 5) = *((_DWORD *)v9 + 10);
LABEL_70:
          TraceMsg(4, 7, L"AsyncNotificationCallback", 1686, L"Posting CLUSTER_CHANGE_CLUSTER_STATE to notify queue");
          ClRtlInsertTailQueue(*(_QWORD *)(v3 + 80) + 56LL, v9);
LABEL_75:
          v9 = 0;
          v46 = 0;
          v19 = (__int64 *)(v3 + 32);
LABEL_76:
          v20 = (__int64 *)*v20;
          continue;
        }
      }
      break;
    }
    LOBYTE(v26) = 0;
    FreePacket(&v46, (unsigned int)*v22, v26);
    NotifyPortReconnect((struct _CNOTIFY_SESSION *)v3);
    TraceMsg(4, 7, L"AsyncNotificationCallback", 1692, L"Filling out packet failed");
    goto LABEL_75;
  }
  TraceMsg(4, 7, L"AsyncNotificationCallback", 1530, L"ERROR_INVALID_PARAMETER detected in NotifyThread, continuing");
LABEL_83:
  std::unique_ptr<AsyncNotificationArrayDeleterStruct,AsyncNotificationArrayDeleterStruct>::~unique_ptr<AsyncNotificationArrayDeleterStruct,AsyncNotificationArrayDeleterStruct>(&v40);
  std::unique_ptr<NotificationArrayDeleterStruct,NotificationArrayDeleterStruct>::~unique_ptr<NotificationArrayDeleterStruct,NotificationArrayDeleterStruct>(&v42);
LABEL_84:
  if ( !*(_DWORD *)(v3 + 288) )
  {
    *(_DWORD *)(v3 + 288) = 1857;
    *(_DWORD *)(v3 + 284) = v2;
    *(_DWORD *)(v3 + 280) = *((_DWORD *)a1 + 2);
  }
  UnregisterWait(*((HANDLE *)a1 + 4));
  CloseHandle(*((HANDLE *)a1 + 3));
  TraceMsg(4, 7, L"AsyncNotificationCallback", 1862, L"NotifyThread broken out of loop, exiting.");
  SetEvent(*(HANDLE *)(v3 + 72));
}

```

## disassembly

```asm
0x18005b600  mov     [rsp-8+arg_8], rbx
0x18005b605  push    rbp
0x18005b606  push    rsi
0x18005b607  push    rdi
0x18005b608  push    r12
0x18005b60a  push    r13
0x18005b60c  push    r14
0x18005b60e  push    r15
0x18005b610  lea     rbp, [rsp-27h]
0x18005b615  sub     rsp, 0A0h
0x18005b61c  mov     rsi, rcx
0x18005b61f  xor     r12d, r12d
0x18005b622  mov     r14d, r12d
0x18005b625  mov     rdi, [rcx]
0x18005b628  mov     r15, [rdi+30h]
0x18005b62c  mov     [rbp+57h+var_90], r15
0x18005b630  mov     al, r12b
0x18005b633  lea     r13d, [r12+7]
0x18005b638  test    al, al
0x18005b63a  jnz     loc_18005BEC6
0x18005b640  mov     ecx, r12d
0x18005b643  mov     [rbp+57h+Reply], ecx
0x18005b646  mov     eax, [rsi+8]
0x18005b649  test    eax, eax
0x18005b64b  jnz     short loc_18005B66C
0x18005b64d  lea     rcx, [rsi+38h]; pAsync
0x18005b651  lea     rdx, [rbp+57h+Reply]; Reply
0x18005b655  call    cs:__imp_RpcAsyncCompleteCall
0x18005b65b  mov     [rsi+8], eax
0x18005b65e  mov     ecx, [rbp+57h+Reply]
0x18005b661  test    eax, eax
0x18005b663  jnz     short loc_18005B66C
0x18005b665  mov     [rsi+8], r12d
0x18005b669  mov     eax, r12d
0x18005b66c  test    ecx, ecx
0x18005b66e  jnz     short loc_18005B674
0x18005b670  test    eax, eax
0x18005b672  jz      short loc_18005B6E1
0x18005b674  inc     dword ptr [rsi+0Ch]
0x18005b677  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18005b67b  mov     dword ptr [rsp+0D0h+var_A8], ecx
0x18005b67f  lea     rax, aGettingAnAsync; "Getting an AsyncNotification exited wit"...
0x18005b686  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18005b68b  xor     r9d, r9d
0x18005b68e  lea     r8, aClusapi; "Clusapi"
0x18005b695  xor     edx, edx
0x18005b697  lea     ecx, [rdx+4]
0x18005b69a  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005b69f  mov     [rsp+0D0h+var_B0], 1; bool
0x18005b6a4  mov     r9d, [rsi+10h]; unsigned int
0x18005b6a8  mov     r8d, [rbp+57h+Reply]; unsigned int
0x18005b6ac  mov     edx, [rsi+8]; unsigned int
0x18005b6af  mov     rcx, r15; struct _CLUSTER *
0x18005b6b2  call    ?ReconnectCluster@@YAKPEAU_CLUSTER@@KKK_N@Z; ReconnectCluster(_CLUSTER *,ulong,ulong,ulong,bool)
0x18005b6b7  mov     r14d, eax
0x18005b6ba  test    eax, eax
0x18005b6bc  jnz     short loc_18005B6E1
0x18005b6be  cmp     dword ptr [rsi+0Ch], 20h ; ' '
0x18005b6c2  jbe     short loc_18005B6CF
0x18005b6c4  mov     ecx, 1F4h; dwMilliseconds
0x18005b6c9  call    cs:__imp_Sleep
0x18005b6cf  cmp     dword ptr [rsi+0Ch], 40h ; '@'
0x18005b6d3  ja      short loc_18005B6DD
0x18005b6d5  mov     r14d, r12d
0x18005b6d8  jmp     loc_18005BAE7
0x18005b6dd  mov     r14d, [rsi+8]
0x18005b6e1  mov     [rsi+0Ch], r12d
0x18005b6e5  mov     [rbp+57h+var_7C], r12d
0x18005b6e9  mov     ecx, [rsi+0A8h]
0x18005b6ef  mov     [rbp+57h+var_80], ecx
0x18005b6f2  mov     rax, [rsi+28h]
0x18005b6f6  mov     [rbp+57h+var_88], rax
0x18005b6fa  xorps   xmm0, xmm0
0x18005b6fd  movups  [rbp+57h+var_50], xmm0
0x18005b701  lea     rax, [rbp+57h+var_88]
0x18005b705  mov     [rbp+57h+var_40], rax
0x18005b709  mov     [rbp+57h+var_6C], r12d
0x18005b70d  mov     [rbp+57h+var_70], ecx
0x18005b710  mov     rax, [rsi+30h]
0x18005b714  mov     [rbp+57h+var_78], rax
0x18005b718  movups  [rbp+57h+var_68], xmm0
0x18005b71c  lea     rax, [rbp+57h+var_78]
0x18005b720  mov     [rbp+57h+var_58], rax
0x18005b724  cmp     r14d, 0Eh
0x18005b728  jz      loc_18005BE41
0x18005b72e  mov     edx, 80h; uBytes
0x18005b733  xor     ecx, ecx; uFlags
0x18005b735  call    cs:__imp_LocalAlloc
0x18005b73b  mov     rbx, rax
0x18005b73e  mov     [rbp+57h+arg_18], rax
0x18005b742  test    rax, rax
0x18005b745  jnz     short loc_18005B754
0x18005b747  mov     rcx, rdi; struct _CNOTIFY_SESSION *
0x18005b74a  call    ?NotifyPortReconnect@@YAXPEAU_CNOTIFY_SESSION@@@Z; NotifyPortReconnect(_CNOTIFY_SESSION *)
0x18005b74f  jmp     loc_18005BACB
0x18005b754  mov     [rax+78h], rdi
0x18005b758  mov     [rax+68h], r12
0x18005b75c  mov     [rax+60h], r12
0x18005b760  mov     [rax+50h], r12
0x18005b764  mov     [rax+58h], r12
0x18005b768  mov     [rax+20h], r12
0x18005b76c  mov     [rax+40h], r12
0x18005b770  mov     [rax+48h], r12d
0x18005b774  mov     [rax+30h], r12d
0x18005b778  mov     [rax+38h], r12
0x18005b77c  mov     [rax+18h], r12
0x18005b780  mov     [rax+10h], r12
0x18005b784  mov     [rax+28h], r12
0x18005b788  mov     [rax+70h], r12
0x18005b78c  test    r14d, r14d
0x18005b78f  jz      loc_18005B8A7
0x18005b795  mov     eax, [rsi+8]
0x18005b798  mov     dword ptr [rsp+0D0h+var_98], eax
0x18005b79c  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x18005b7a1  mov     rax, [rdi+38h]
0x18005b7a5  mov     [rsp+0D0h+var_A8], rax
0x18005b7aa  lea     rax, aApigetnotifyOn_0; "ApiGetNotify on hNotify=0x%p returns %u"...
0x18005b7b1  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18005b7b6  mov     r9d, 5DBh
0x18005b7bc  lea     r8, aAsyncnotificat; "AsyncNotificationCallback"
0x18005b7c3  mov     edx, r13d
0x18005b7c6  mov     ecx, 3
0x18005b7cb  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005b7d0  cmp     r14d, 103h
0x18005b7d7  jnz     short loc_18005B820
0x18005b7d9  cmp     [rdi+38h], r12
0x18005b7dd  jz      loc_18005BB36
0x18005b7e3  mov     r14d, r12d
0x18005b7e6  xor     r8d, r8d
0x18005b7e9  mov     edx, [rdi+60h]
0x18005b7ec  lea     rcx, [rbp+57h+arg_18]
0x18005b7f0  call    ?FreePacket@@YAKAEAPEAU_CNOTIFY_PACKET@@W4CLUSTER_NOTIFICATIONS_VERSION@@_N@Z; FreePacket(_CNOTIFY_PACKET * &,CLUSTER_NOTIFICATIONS_VERSION,bool)
0x18005b7f5  lea     rax, aMappingErrorTo; "mapping error to success"
0x18005b7fc  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18005b801  mov     r9d, 5E5h
0x18005b807  lea     r8, aAsyncnotificat; "AsyncNotificationCallback"
0x18005b80e  mov     edx, r13d
0x18005b811  mov     ecx, 4
0x18005b816  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005b81b  jmp     loc_18005BACB
0x18005b820  cmp     r14d, 1
0x18005b824  jnz     short loc_18005B84B
0x18005b826  xor     r8d, r8d
0x18005b829  mov     edx, [rdi+60h]
0x18005b82c  lea     rcx, [rbp+57h+arg_18]
0x18005b830  call    ?FreePacket@@YAKAEAPEAU_CNOTIFY_PACKET@@W4CLUSTER_NOTIFICATIONS_VERSION@@_N@Z; FreePacket(_CNOTIFY_PACKET * &,CLUSTER_NOTIFICATIONS_VERSION,bool)
0x18005b835  cmp     [rdi+5Ch], r12d
0x18005b839  jz      loc_18005BAEE
0x18005b83f  mov     [rdi+5Ch], r12d
0x18005b843  mov     r14d, r12d
0x18005b846  jmp     loc_18005BACB
0x18005b84b  cmp     r14d, 57h ; 'W'
0x18005b84f  jz      loc_18005BE2F
0x18005b855  cmp     [rdi+38h], r12
0x18005b859  jz      loc_18005BB36
0x18005b85f  test    byte ptr [r15+20h], 2
0x18005b864  jnz     loc_18005BB36
0x18005b86a  cmp     r14d, 6BAh
0x18005b871  jz      loc_18005BB36
0x18005b877  mov     dword ptr [rdi+120h], 6B3h
0x18005b881  mov     [rdi+11Ch], r14d
0x18005b888  mov     eax, [rsi+8]
0x18005b88b  mov     [rdi+118h], eax
0x18005b891  mov     rcx, rdi; struct _CNOTIFY_SESSION *
0x18005b894  call    ?NotifyPortReconnect@@YAXPEAU_CNOTIFY_SESSION@@@Z; NotifyPortReconnect(_CNOTIFY_SESSION *)
0x18005b899  mov     rcx, rbx; hMem
0x18005b89c  call    cs:__imp_LocalFree
0x18005b8a2  jmp     loc_18005BACB
0x18005b8a7  mov     rcx, [rsi]
0x18005b8aa  mov     edx, [rcx+60h]
0x18005b8ad  sub     edx, 1
0x18005b8b0  jz      loc_18005B9F9
0x18005b8b6  cmp     edx, 1
0x18005b8b9  jnz     loc_18005BACB
0x18005b8bf  cmp     [rsi+28h], r12
0x18005b8c3  jnz     short loc_18005B904
0x18005b8c5  mov     r9d, 707h
0x18005b8cb  lea     rax, aRpcReturnedNul; "RPC returned null data for notification"...
0x18005b8d2  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18005b8d7  lea     r8, aAsyncnotificat; "AsyncNotificationCallback"
0x18005b8de  mov     edx, r13d
0x18005b8e1  mov     ecx, 4
0x18005b8e6  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005b8eb  nop
0x18005b8ec  lea     rcx, [rbp+57h+var_68]
0x18005b8f0  call    ??1?$unique_ptr@UAsyncNotificationArrayDeleterStruct@@U1@@std@@QEAA@XZ; std::unique_ptr<AsyncNotificationArrayDeleterStruct,AsyncNotificationArrayDeleterStruct>::~unique_ptr<AsyncNotificationArrayDeleterStruct,AsyncNotificationArrayDeleterStruct>(void)
0x18005b8f5  nop
0x18005b8f6  lea     rcx, [rbp+57h+var_50]
0x18005b8fa  call    ??1?$unique_ptr@UNotificationArrayDeleterStruct@@U1@@std@@QEAA@XZ; std::unique_ptr<NotificationArrayDeleterStruct,NotificationArrayDeleterStruct>::~unique_ptr<NotificationArrayDeleterStruct,NotificationArrayDeleterStruct>(void)
0x18005b8ff  jmp     loc_18005BAE7
0x18005b904  mov     r15d, r12d
0x18005b907  cmp     [rsi+0A8h], r12d
0x18005b90e  jbe     loc_18005BAC7
0x18005b914  mov     eax, r15d
0x18005b917  lea     rcx, [rax+rax*8]
0x18005b91b  mov     rax, [rsi+28h]
0x18005b91f  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18005b923  movups  xmmword ptr [rbx+28h], xmm0
0x18005b927  movups  xmm1, xmmword ptr [rax+rcx*8+10h]
0x18005b92c  movups  xmmword ptr [rbx+38h], xmm1
0x18005b930  movups  xmm0, xmmword ptr [rax+rcx*8+20h]
0x18005b935  movups  xmmword ptr [rbx+48h], xmm0
0x18005b939  movups  xmm1, xmmword ptr [rax+rcx*8+30h]
0x18005b93e  movups  xmmword ptr [rbx+58h], xmm1
0x18005b942  movsd   xmm0, qword ptr [rax+rcx*8+40h]
0x18005b948  movsd   qword ptr [rbx+68h], xmm0
0x18005b94d  mov     [rax+rcx*8+18h], r12
0x18005b952  mov     [rax+rcx*8+28h], r12
0x18005b957  mov     [rax+rcx*8+30h], r12
0x18005b95c  mov     [rax+rcx*8+38h], r12
0x18005b961  mov     [rax+rcx*8+40h], r12
0x18005b966  mov     eax, [rbx+28h]
0x18005b969  mov     [rbx+14h], eax
0x18005b96c  mov     [rbx+10h], r12d
0x18005b970  mov     rcx, [rdi+50h]
0x18005b974  add     rcx, 38h ; '8'
0x18005b978  mov     rdx, rbx
0x18005b97b  call    ClRtlInsertTailQueue
0x18005b980  mov     eax, [rsi+0A8h]
0x18005b986  dec     eax
0x18005b988  cmp     r15d, eax
0x18005b98b  jz      short loc_18005B9E4
0x18005b98d  mov     edx, 80h; uBytes
0x18005b992  xor     ecx, ecx; uFlags
0x18005b994  call    cs:__imp_LocalAlloc
0x18005b99a  mov     rbx, rax
0x18005b99d  test    rax, rax
0x18005b9a0  jnz     short loc_18005B9AC
0x18005b9a2  mov     rcx, rdi; struct _CNOTIFY_SESSION *
0x18005b9a5  call    ?NotifyPortReconnect@@YAXPEAU_CNOTIFY_SESSION@@@Z; NotifyPortReconnect(_CNOTIFY_SESSION *)
0x18005b9aa  jmp     short loc_18005B9E4
0x18005b9ac  mov     [rax+78h], rdi
0x18005b9b0  mov     [rax+68h], r12
0x18005b9b4  mov     [rax+60h], r12
0x18005b9b8  mov     [rax+50h], r12
0x18005b9bc  mov     [rax+58h], r12
0x18005b9c0  mov     [rax+20h], r12
0x18005b9c4  mov     [rax+40h], r12
0x18005b9c8  mov     [rax+48h], r12d
0x18005b9cc  mov     [rax+30h], r12d
0x18005b9d0  mov     [rax+38h], r12
0x18005b9d4  mov     [rax+18h], r12
0x18005b9d8  mov     [rax+10h], r12
0x18005b9dc  mov     [rax+28h], r12
0x18005b9e0  mov     [rax+70h], r12
0x18005b9e4  inc     r15d
0x18005b9e7  cmp     r15d, [rsi+0A8h]
0x18005b9ee  jb      loc_18005B914
0x18005b9f4  jmp     loc_18005BAC7
0x18005b9f9  cmp     [rsi+30h], r12
0x18005b9fd  jnz     short loc_18005BA0A
0x18005b9ff  mov     r9d, 6C4h
0x18005ba05  jmp     loc_18005B8CB
0x18005ba0a  mov     r15d, r12d
0x18005ba0d  cmp     [rsi+0A8h], r12d
0x18005ba14  jbe     loc_18005BAC7
0x18005ba1a  mov     edx, r15d
0x18005ba1d  add     rdx, rdx
0x18005ba20  mov     rcx, [rsi+30h]
0x18005ba24  mov     eax, [rcx+rdx*8]
0x18005ba27  mov     [rbx+14h], eax
0x18005ba2a  mov     eax, [rcx+rdx*8+4]
0x18005ba2e  mov     [rbx+18h], eax
0x18005ba31  mov     [rbx+10h], r12d
0x18005ba35  mov     rax, [rcx+rdx*8+8]
0x18005ba3a  mov     [rbx+20h], rax
0x18005ba3e  mov     [rcx+rdx*8+8], r12
0x18005ba43  mov     rcx, [rdi+50h]
0x18005ba47  add     rcx, 38h ; '8'
0x18005ba4b  mov     rdx, rbx
0x18005ba4e  call    ClRtlInsertTailQueue
0x18005ba53  mov     eax, [rsi+0A8h]
0x18005ba59  dec     eax
0x18005ba5b  cmp     r15d, eax
0x18005ba5e  jz      short loc_18005BAB7
0x18005ba60  mov     edx, 80h; uBytes
0x18005ba65  xor     ecx, ecx; uFlags
0x18005ba67  call    cs:__imp_LocalAlloc
0x18005ba6d  mov     rbx, rax
0x18005ba70  test    rax, rax
0x18005ba73  jnz     short loc_18005BA7F
0x18005ba75  mov     rcx, rdi; struct _CNOTIFY_SESSION *
0x18005ba78  call    ?NotifyPortReconnect@@YAXPEAU_CNOTIFY_SESSION@@@Z; NotifyPortReconnect(_CNOTIFY_SESSION *)
0x18005ba7d  jmp     short loc_18005BAB7
0x18005ba7f  mov     [rax+78h], rdi
0x18005ba83  mov     [rax+68h], r12
0x18005ba87  mov     [rax+60h], r12
0x18005ba8b  mov     [rax+50h], r12
0x18005ba8f  mov     [rax+58h], r12
0x18005ba93  mov     [rax+20h], r12
0x18005ba97  mov     [rax+40h], r12
0x18005ba9b  mov     [rax+48h], r12d
0x18005ba9f  mov     [rax+30h], r12d
0x18005baa3  mov     [rax+38h], r12
0x18005baa7  mov     [rax+18h], r12
0x18005baab  mov     [rax+10h], r12
0x18005baaf  mov     [rax+28h], r12
0x18005bab3  mov     [rax+70h], r12
0x18005bab7  inc     r15d
0x18005baba  cmp     r15d, [rsi+0A8h]
  ... truncated ...
```
