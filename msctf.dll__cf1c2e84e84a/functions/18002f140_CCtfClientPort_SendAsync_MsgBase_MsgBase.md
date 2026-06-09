# CCtfClientPort::SendAsync(MsgBase *,MsgBase * *)

- ea: `0x18002f140`
- end: `0x18002ff61`
- name: `?SendAsync@CCtfClientPort@@QEAAJPEAUMsgBase@@PEAPEAU2@@Z`
- size: `3617`
- prototype: `__int64 __fastcall(CCtfClientPort *__hidden this, struct MsgBase *, struct MsgBase **)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180010a20`
- `0x18002dd14`
- `0x18008969c`

## callees

- `0x18000f450`
- `0x1800139c0`
- `0x18002f140`
- `0x18002ff70`
- `0x180043548`
- `0x18008c530`
- `0x18008cb5c`
- `0x18008ced0`
- `0x18009ead2`
- `0x1800b4434`
- `0x180106a60`

## import_xrefs

- `ntdll!AlpcGetMessageAttribute` at `0x18002f2f2`
- `ntdll!AlpcGetMessageAttribute` at `0x18002f30a`
- `ntdll!AlpcGetMessageAttribute` at `0x18002f2f2`
- `ntdll!AlpcGetMessageAttribute` at `0x18002f30a`
- `ntdll!NtAlpcDeletePortSection` at `0x18002ff2f`
- `ntdll!NtAlpcDeletePortSection` at `0x18002ff2f`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18002f36d`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18002f36d`
- `ntdll!AlpcInitializeMessageAttribute` at `0x18002f1a2`
- `ntdll!AlpcInitializeMessageAttribute` at `0x18002f1ea`
- `ntdll!AlpcInitializeMessageAttribute` at `0x18002f1a2`
- `ntdll!AlpcInitializeMessageAttribute` at `0x18002f1ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f2d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f2d3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f524`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f524`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002fb41`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002fb41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f4d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f4d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f38f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f3ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fc6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fcb4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fcfc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fd4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fd93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fde2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fe95`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fea0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002feab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002feb6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fec1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f38f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f3ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fc6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fcb4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fcfc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fd4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fd93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fde2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fe95`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fea0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002feab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002feb6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002fec1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f1c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f26e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f1c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f26e`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18002f4b1`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18002fbae`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18002fc33`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18002f4b1`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18002fbae`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18002fc33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f4c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f694`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fc48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fc5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fe30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f4c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f694`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fc48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fc5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fe30`
- `USER32!MsgWaitForMultipleObjects` at `0x18002f655`
- `USER32!MsgWaitForMultipleObjects` at `0x18002f655`
- `USER32!DispatchMessageW` at `0x18002fc78`
- `USER32!DispatchMessageW` at `0x18002fcc1`
- `USER32!DispatchMessageW` at `0x18002fd09`
- `USER32!DispatchMessageW` at `0x18002fd57`
- `USER32!DispatchMessageW` at `0x18002fda0`
- `USER32!DispatchMessageW` at `0x18002fdef`
- `USER32!DispatchMessageW` at `0x18002fc78`
- `USER32!DispatchMessageW` at `0x18002fcc1`
- `USER32!DispatchMessageW` at `0x18002fd09`
- `USER32!DispatchMessageW` at `0x18002fd57`
- `USER32!DispatchMessageW` at `0x18002fda0`
- `USER32!DispatchMessageW` at `0x18002fdef`
- `USER32!PostQuitMessage` at `0x18002ff1e`
- `USER32!PostQuitMessage` at `0x18002ff1e`
- `USER32!PeekMessageW` at `0x18002f58b`
- `USER32!PeekMessageW` at `0x18002f5c0`
- `USER32!PeekMessageW` at `0x18002f5f5`
- `USER32!PeekMessageW` at `0x18002f62a`
- `USER32!PeekMessageW` at `0x18002f6fc`
- `USER32!PeekMessageW` at `0x18002f73d`
- `USER32!PeekMessageW` at `0x18002f772`
- `USER32!PeekMessageW` at `0x18002f7b0`
- `USER32!PeekMessageW` at `0x18002f7e2`
- `USER32!PeekMessageW` at `0x18002f81d`
- `USER32!PeekMessageW` at `0x18002f85c`
- `USER32!PeekMessageW` at `0x18002f8a0`
- `USER32!PeekMessageW` at `0x18002f8dd`
- `USER32!PeekMessageW` at `0x18002f91b`
- `USER32!PeekMessageW` at `0x18002f950`
- `USER32!PeekMessageW` at `0x18002f98a`
- `USER32!PeekMessageW` at `0x18002f9bf`
- `USER32!PeekMessageW` at `0x18002f9fa`
- `USER32!PeekMessageW` at `0x18002fa4e`
- `USER32!PeekMessageW` at `0x18002fa8e`
- `USER32!PeekMessageW` at `0x18002fac9`
- `USER32!PeekMessageW` at `0x18002fb00`
- `USER32!PeekMessageW` at `0x18002fc94`
- `USER32!PeekMessageW` at `0x18002fcdc`
- `USER32!PeekMessageW` at `0x18002fd2a`
- `USER32!PeekMessageW` at `0x18002fd73`
- `USER32!PeekMessageW` at `0x18002fdc2`
- `USER32!PeekMessageW` at `0x18002fe0d`
- `USER32!PeekMessageW` at `0x18002ff09`
- `USER32!PeekMessageW` at `0x18002f58b`
- `USER32!PeekMessageW` at `0x18002f5c0`
- `USER32!PeekMessageW` at `0x18002f5f5`
- `USER32!PeekMessageW` at `0x18002f62a`
- `USER32!PeekMessageW` at `0x18002f6fc`
- `USER32!PeekMessageW` at `0x18002f73d`
- `USER32!PeekMessageW` at `0x18002f772`
- `USER32!PeekMessageW` at `0x18002f7b0`
- `USER32!PeekMessageW` at `0x18002f7e2`
- `USER32!PeekMessageW` at `0x18002f81d`
- `USER32!PeekMessageW` at `0x18002f85c`
- `USER32!PeekMessageW` at `0x18002f8a0`
- `USER32!PeekMessageW` at `0x18002f8dd`
- `USER32!PeekMessageW` at `0x18002f91b`
- `USER32!PeekMessageW` at `0x18002f950`
- `USER32!PeekMessageW` at `0x18002f98a`
- `USER32!PeekMessageW` at `0x18002f9bf`
- `USER32!PeekMessageW` at `0x18002f9fa`
- `USER32!PeekMessageW` at `0x18002fa4e`
- `USER32!PeekMessageW` at `0x18002fa8e`
- `USER32!PeekMessageW` at `0x18002fac9`
- `USER32!PeekMessageW` at `0x18002fb00`
- `USER32!PeekMessageW` at `0x18002fc94`
- `USER32!PeekMessageW` at `0x18002fcdc`
- `USER32!PeekMessageW` at `0x18002fd2a`
- `USER32!PeekMessageW` at `0x18002fd73`
- `USER32!PeekMessageW` at `0x18002fdc2`
- `USER32!PeekMessageW` at `0x18002fe0d`
- `USER32!PeekMessageW` at `0x18002ff09`
- `USER32!GetQueueStatus` at `0x18002f542`
- `USER32!GetQueueStatus` at `0x18002f6ad`
- `USER32!GetQueueStatus` at `0x18002fed3`
- `USER32!GetQueueStatus` at `0x18002f542`
- `USER32!GetQueueStatus` at `0x18002f6ad`
- `USER32!GetQueueStatus` at `0x18002fed3`

## pseudocode

```c
__int64 __fastcall CCtfClientPort::SendAsync(CCtfClientPort *this, struct MsgBase *a2, struct MsgBase **a3)
{
  _DWORD *v5; // rax
  _DWORD *v6; // r15
  __int64 v7; // r12
  signed int v8; // edi
  unsigned int v9; // ebx
  void *v10; // rcx
  HLOCAL *v11; // r14
  SIZE_T v12; // rdx
  HLOCAL v13; // rax
  int v14; // eax
  HANDLE v15; // rbx
  __int64 MessageAttribute; // rax
  __int64 v17; // rax
  struct MsgBase *v18; // rbx
  struct MsgBase **v19; // rcx
  int v20; // eax
  int v21; // edi
  struct tagSYSTHREAD *v22; // rsi
  int wParam; // r15d
  int v24; // r14d
  char v25; // bl
  DWORD v26; // edi
  struct MsgBase *v27; // rcx
  int i; // edx
  int v29; // edx
  int v30; // r8d
  int v31; // ecx
  int v32; // eax
  int v33; // ebx
  unsigned __int64 v34; // rax
  HLOCAL v35; // rax
  __int64 v36; // r8
  DWORD v38; // eax
  DWORD QueueStatus; // eax
  UINT v40; // ebx
  HWND v41; // rdi
  UINT v42; // ebx
  DWORD v43; // eax
  int v44; // r12d
  UINT v45; // ebx
  HWND v46; // rdi
  UINT v47; // ebx
  UINT v48; // ebx
  HWND OleMainThreadWindow; // rbx
  _DWORD *v50; // rcx
  int v51; // edx
  int v52; // r8d
  int v53; // ecx
  int v54; // eax
  int v55; // ebx
  unsigned __int64 v56; // rax
  HLOCAL v57; // rax
  DWORD TickCount; // esi
  DWORD v59; // edi
  DWORD v60; // ebx
  DWORD v61; // esi
  DWORD v62; // edi
  DWORD v63; // ebx
  int v64; // r8d
  tagMSG Msg; // [rsp+40h] [rbp-89h] BYREF
  int v66; // [rsp+70h] [rbp-59h]
  int v67; // [rsp+74h] [rbp-55h]
  int v68; // [rsp+78h] [rbp-51h]
  DWORD v69; // [rsp+80h] [rbp-49h]
  SIZE_T uBytes; // [rsp+88h] [rbp-41h] BYREF
  int v71; // [rsp+90h] [rbp-39h]
  struct tagSYSTHREAD *v72; // [rsp+98h] [rbp-31h]
  struct MsgBase *v73; // [rsp+A0h] [rbp-29h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp-21h]
  struct MsgBase *v75; // [rsp+B0h] [rbp-19h]
  void *v76; // [rsp+B8h] [rbp-11h] BYREF
  HANDLE hObject; // [rsp+C0h] [rbp-9h]
  HANDLE pHandles; // [rsp+C8h] [rbp-1h] BYREF
  struct MsgBase **v79; // [rsp+D0h] [rbp+7h]
  _DWORD *v80; // [rsp+D8h] [rbp+Fh] BYREF

  v79 = a3;
  *a3 = 0;
  v75 = a2;
  if ( !*((_QWORD *)this + 1) )
  {
    if ( g_dwTLSIndexForFLS == -1 )
      return 2147500037LL;
    if ( TlsGetValue(g_dwTLSIndexForFLS) )
      return 2147500037LL;
    v50 = (_DWORD *)*((_QWORD *)this + 5);
    Msg.hwnd = (HWND)4194328;
    memset(&Msg.message, 0, 20);
    Msg.time = 0;
    Msg.pt.y = v50[27];
    *((_DWORD *)&Msg.pt + 2) = v50[26];
    v66 = v50[28];
    v67 = v50[29];
    v68 = v50[34];
    if ( !CAlpcPort::Open(this, (struct MsgConnect *)&Msg) )
      return 2147500037LL;
  }
  uBytes = 0;
  if ( (unsigned int)AlpcInitializeMessageAttribute(1879048192, 0, 0, &uBytes) != -1073741789 )
    return 2147942414LL;
  if ( !uBytes )
    return 2147942414LL;
  v5 = LocalAlloc(0x40u, (unsigned int)uBytes);
  v80 = v5;
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  if ( (int)AlpcInitializeMessageAttribute(1879048192, v5, uBytes, &uBytes) < 0 )
  {
    LocalFree(v6);
    return 2147942414LL;
  }
  v7 = *((int *)this + 18);
  v73 = a2;
  hMem = 0;
  v71 = v7;
  if ( (int)v7 < 0 )
    goto LABEL_136;
  v8 = v7 + 1;
  if ( __OFSUB__((_DWORD)v7, v7 + 1) )
    goto LABEL_136;
  if ( *((_DWORD *)this + 19) >= v8 )
  {
    v11 = (HLOCAL *)((char *)this + 64);
    goto LABEL_16;
  }
  v9 = (int)v7 / 2 + v7;
  if ( v8 > (int)v9 )
    v9 = v7 + 1;
  if ( v9 > 0xFFFFFFF
    || ((v10 = (void *)*((_QWORD *)this + 8), v11 = (HLOCAL *)((char *)this + 64), v12 = 8 * v9, v10)
      ? (v13 = LocalReAlloc(v10, v12, 0x42u))
      : (v13 = LocalAlloc(0, v12)),
        !v13) )
  {
LABEL_136:
    LocalFree(v6);
    return 2147942414LL;
  }
  *v11 = v13;
  *((_DWORD *)this + 19) = v9;
LABEL_16:
  v14 = *((_DWORD *)this + 18);
  if ( (int)v7 < v14 )
  {
    v11 = (HLOCAL *)((char *)this + 64);
    memmove_0(
      (void *)(*((_QWORD *)this + 8) + 8LL * v8),
      (const void *)(*((_QWORD *)this + 8) + 8 * v7),
      8LL * (v14 - (int)v7));
  }
  if ( (int)v7 < ++*((_DWORD *)this + 18) && *v11 )
    *((_QWORD *)*v11 + v7) = &v73;
  hObject = CreateEventW(0, 0, 0, 0);
  v15 = hObject;
  if ( hObject == (HANDLE)-1LL )
  {
    v51 = v7 + 1;
    if ( (int)v7 + 1 >= 0 )
    {
      v52 = *((_DWORD *)this + 18);
      if ( v51 <= v52 )
      {
        if ( v51 < v52 )
          memmove_0((char *)*v11 + 8 * v7, (char *)*v11 + 8 * v51, 8LL * (v52 + ~(_DWORD)v7));
        v53 = *((_DWORD *)this + 19);
        --*((_DWORD *)this + 18);
        v54 = v53 / 2;
        v55 = v53 / 2;
        if ( v53 / 2 != v53 && v54 > *((_DWORD *)this + 18) && v54 >= 0 )
        {
          v56 = 8LL * (unsigned int)v54;
          if ( v56 <= 0xFFFFFFFF )
          {
            v57 = LocalReAlloc(*v11, (unsigned int)v56, 0x42u);
            if ( v57 )
            {
              *v11 = v57;
              *((_DWORD *)this + 19) = v55;
            }
          }
        }
      }
    }
    goto LABEL_135;
  }
  MessageAttribute = AlpcGetMessageAttribute(v6, 0x10000000);
  *(_DWORD *)MessageAttribute = 196608;
  *(_QWORD *)(MessageAttribute + 8) = v15;
  v17 = AlpcGetMessageAttribute(v6, 0x20000000);
  v18 = v75;
  v19 = &v73;
  *(_QWORD *)(v17 + 8) = &v73;
  v6[1] = 805306368;
  v20 = *((_DWORD *)v18 + 10);
  v76 = 0;
  if ( (v20 & 0x4000000) != 0 )
  {
    *((_DWORD *)v18 + 10) = v20 & 0xFBFFFFFF;
    if ( (unsigned int)CreateDataView(
                         *((void **)this + 1),
                         (const void **)v18,
                         (struct _ALPC_MESSAGE_ATTRIBUTES *)v6,
                         &v76) )
    {
      CVoidPtrArray::Remove((CCtfClientPort *)((char *)this + 56), v7, v64);
LABEL_135:
      LocalFree(v6);
      return 2147500037LL;
    }
  }
  if ( Microsoft_Windows_TSF_msctfEnableBits < 0 )
    McTemplateU0qqQ4_EventWriteTransfer(
      (_DWORD)v19,
      (unsigned int)SendAsyncRequest_Start,
      *((_DWORD *)v18 + 10),
      *((_DWORD *)v18 + 12),
      (__int64)v18 + 56);
  v21 = -2147467259;
  if ( (int)NtAlpcSendWaitReceivePort(*((_QWORD *)this + 1), 0, v18, v6, 0, 0, 0, 0) >= 0 )
  {
    v22 = (struct tagSYSTHREAD *)*((_QWORD *)this + 5);
    wParam = 0;
    v72 = v22;
    v24 = 0;
    ++*((_DWORD *)v22 + 87);
    v25 = 1;
    v26 = GetTickCount() / 0xA + 300;
    v69 = v26;
    while ( 1 )
    {
      if ( v26 < GetTickCount() / 0xA )
      {
LABEL_69:
        v27 = (struct MsgBase *)hMem;
        v21 = -2147467259;
        goto LABEL_70;
      }
      if ( v25 )
      {
        CCtfClientPort::Receive(this);
        v27 = (struct MsgBase *)hMem;
        if ( hMem )
          break;
      }
      pHandles = hObject;
      v38 = WaitForSingleObject(hObject, 0);
      if ( v38 )
      {
        if ( v38 != 258 )
          goto LABEL_73;
        QueueStatus = GetQueueStatus(8u);
        if ( (((unsigned __int8)QueueStatus | BYTE2(QueueStatus)) & 8) != 0 )
        {
          v40 = g_msgRpcSendReceive;
          v41 = (HWND)*((_QWORD *)v22 + 17);
          memset(&Msg, 0, sizeof(Msg));
          while ( PeekMessageW(&Msg, v41, v40, v40, 3u) )
          {
            while ( Msg.message == 18 )
            {
              wParam = Msg.wParam;
              v24 = 1;
              if ( !PeekMessageW(&Msg, v41, v40, v40, 3u) )
                goto LABEL_61;
            }
            TickCount = GetTickCount();
            DispatchMessageW(&Msg);
            if ( PeekMessageW(&Msg, v41, v40, v40, 2u) )
            {
              if ( (int)(Msg.time - TickCount) > 0 )
                break;
            }
          }
LABEL_61:
          v42 = g_msgPrivate;
          memset(&Msg, 0, sizeof(Msg));
          while ( PeekMessageW(&Msg, 0, v42, v42, 3u) )
          {
            while ( Msg.message == 18 )
            {
              wParam = Msg.wParam;
              v24 = 1;
              if ( !PeekMessageW(&Msg, 0, v42, v42, 3u) )
                goto LABEL_65;
            }
            v59 = GetTickCount();
            DispatchMessageW(&Msg);
            if ( PeekMessageW(&Msg, 0, v42, v42, 2u) )
            {
              if ( (int)(Msg.time - v59) > 0 )
                break;
            }
          }
LABEL_65:
          v22 = v72;
          v26 = v69;
        }
        v38 = MsgWaitForMultipleObjects(1u, &pHandles, 0, 0x1F4u, 0x59FFu);
        if ( v38 )
        {
LABEL_73:
          if ( v38 == 1 )
          {
            v43 = GetQueueStatus(0x59FFu);
            v44 = (unsigned __int16)v43 | HIWORD(v43);
            if ( (((unsigned __int8)v43 | BYTE2(v43)) & 1) == 0 )
            {
              if ( (((unsigned __int8)v43 | BYTE2(v43)) & 6) != 0 )
              {
                memset(&Msg, 0, sizeof(Msg));
                while ( PeekMessageW(&Msg, 0, 0x200u, 0x200u, 3u) )
                {
                  while ( Msg.message == 18 )
                  {
                    wParam = Msg.wParam;
                    v24 = 1;
                    if ( !PeekMessageW(&Msg, 0, 0x200u, 0x200u, 3u) )
                      goto LABEL_80;
                  }
                  GetTickCount();
                }
LABEL_80:
                memset(&Msg, 0, sizeof(Msg));
                while ( PeekMessageW(&Msg, 0, 0xA0u, 0xADu, 3u) )
                {
                  while ( Msg.message == 18 )
                  {
                    wParam = Msg.wParam;
                    v24 = 1;
                    if ( !PeekMessageW(&Msg, 0, 0xA0u, 0xADu, 3u) )
                      goto LABEL_84;
                  }
                  GetTickCount();
                }
LABEL_84:
                memset(&Msg, 0, sizeof(Msg));
                while ( PeekMessageW(&Msg, 0, 0x23u, 0x23u, 3u) )
                {
                  while ( Msg.message == 18 )
                  {
                    wParam = Msg.wParam;
                    v24 = 1;
                    if ( !PeekMessageW(&Msg, 0, 0x23u, 0x23u, 3u) )
                      goto LABEL_88;
                  }
                  GetTickCount();
                }
              }
LABEL_88:
              if ( (v44 & 8) != 0 )
              {
                memset(&Msg, 0, sizeof(Msg));
                while ( PeekMessageW(&Msg, 0, 0x3E0u, 0x3E8u, 3u) )
                {
                  while ( Msg.message == 18 )
                  {
                    wParam = Msg.wParam;
                    v24 = 1;
                    if ( !PeekMessageW(&Msg, 0, 0x3E0u, 0x3E8u, 3u) )
                      goto LABEL_93;
                  }
                  v60 = GetTickCount();
                  DispatchMessageW(&Msg);
                  if ( PeekMessageW(&Msg, 0, 0x3E0u, 0x3E8u, 2u) )
                  {
                    if ( (int)(Msg.time - v60) > 0 )
                      break;
                  }
                }
LABEL_93:
                v45 = g_msgRpcSendReceive;
                v46 = (HWND)*((_QWORD *)v22 + 17);
                memset(&Msg, 0, sizeof(Msg));
                while ( PeekMessageW(&Msg, v46, v45, v45, 3u) )
                {
                  while ( Msg.message == 18 )
                  {
                    wParam = Msg.wParam;
                    v24 = 1;
                    if ( !PeekMessageW(&Msg, v46, v45, v45, 3u) )
                      goto LABEL_97;
                  }
                  v61 = GetTickCount();
                  DispatchMessageW(&Msg);
                  if ( PeekMessageW(&Msg, v46, v45, v45, 2u) )
                  {
                    if ( (int)(Msg.time - v61) > 0 )
                      break;
                  }
                }
LABEL_97:
                v47 = g_msgPrivate;
                memset(&Msg, 0, sizeof(Msg));
                while ( PeekMessageW(&Msg, 0, v47, v47, 3u) )
                {
                  while ( Msg.message == 18 )
                  {
                    wParam = Msg.wParam;
                    v24 = 1;
                    if ( !PeekMessageW(&Msg, 0, v47, v47, 3u) )
                      goto LABEL_101;
                  }
                  GetTickCount();
                }
LABEL_101:
                v48 = g_msgLBarModal;
                memset(&Msg, 0, sizeof(Msg));
                while ( PeekMessageW(&Msg, 0, v48, v48, 3u) )
                {
                  while ( Msg.message == 18 )
                  {
                    wParam = Msg.wParam;
                    v24 = 1;
                    if ( !PeekMessageW(&Msg, 0, v48, v48, 3u) )
                      goto LABEL_105;
                  }
                  GetTickCount();
                }
LABEL_105:
                v22 = v72;
                memset(&Msg, 0, sizeof(Msg));
                OleMainThreadWindow = GetOleMainThreadWindow(v72);
                if ( OleMainThreadWindow )
                {
                  while ( PeekMessageW(&Msg, OleMainThreadWindow, 0x400u, 0xFFFFFFFF, 3u) )
                  {
                    while ( Msg.message == 18 )
                    {
                      wParam = Msg.wParam;
                      v24 = 1;
                      if ( !PeekMessageW(&Msg, OleMainThreadWindow, 0x400u, 0xFFFFFFFF, 3u) )
                        goto LABEL_109;
                    }
                    v62 = GetTickCount();
                    DispatchMessageW(&Msg);
                    if ( PeekMessageW(&Msg, OleMainThreadWindow, 0x400u, 0xFFFFFFFF, 2u) )
                    {
                      if ( (int)(Msg.time - v62) > 0 )
                        break;
                    }
                  }
                }
LABEL_109:
                v26 = v69;
              }
              if ( (v44 & 0x20) != 0 )
              {
                memset(&Msg, 0, sizeof(Msg));
                while ( PeekMessageW(&Msg, 0, 0xFu, 0xFu, 3u) )
                {
                  while ( Msg.message == 18 )
                  {
                    wParam = Msg.wParam;
                    v24 = 1;
                    if ( !PeekMessageW(&Msg, 0, 0xFu, 0xFu, 3u) )
                      goto LABEL_115;
                  }
                  v63 = GetTickCount();
                  DispatchMessageW(&Msg);
                  if ( PeekMessageW(&Msg, 0, 0xFu, 0xFu, 2u) )
                  {
                    if ( (int)(Msg.time - v63) > 0 )
                      break;
                  }
                }
              }
            }
LABEL_115:
            v25 = 0;
          }
          else
          {
            v25 = 0;
            if ( (GetQueueStatus(0x40u) & 0x400000) != 0 )
            {
              memset(&Msg, 0, sizeof(Msg));
              PeekMessageW(&Msg, 0, 0, 0, 0x400000u);
            }
          }
        }
        else
        {
          v25 = 1;
        }
      }
      else
      {
        v25 = 1;
      }
      if ( !*((_QWORD *)this + 1) )
        goto LABEL_69;
    }
    v21 = *((_DWORD *)hMem + 13);
    if ( v21 >= 0 )
    {
      *v79 = (struct MsgBase *)hMem;
      goto LABEL_32;
    }
LABEL_70:
    if ( v27 && v27 != v75 )
      LocalFree(v27);
LABEL_32:
    hMem = 0;
    for ( i = 0; ; ++i )
    {
      if ( i >= *((_DWORD *)this + 18) )
      {
        LODWORD(v7) = v71;
        goto LABEL_35;
      }
      if ( &v73 == *(struct MsgBase ***)(*((_QWORD *)this + 8) + 8LL * i) )
        break;
    }
    LODWORD(v7) = i;
LABEL_35:
    if ( v24 )
      PostQuitMessage(wParam);
    tagSYSTHREAD::Release(v22);
    v6 = v80;
    v11 = (HLOCAL *)((char *)this + 64);
  }
  if ( v76 )
    NtAlpcDeletePortSection(*((_QWORD *)this + 1), 0);
  if ( (int)v7 >= 0 )
  {
    v29 = v7 + 1;
    if ( (int)v7 + 1 >= 0 )
    {
      v30 = *((_DWORD *)this + 18);
      if ( v29 <= v30 )
      {
        if ( v29 < v30 )
          memmove_0((char *)*v11 + 8 * (int)v7, (char *)*v11 + 8 * v29, 8LL * (v30 + ~(_DWORD)v7));
        v31 = *((_DWORD *)this + 19);
        --*((_DWORD *)this + 18);
        v32 = v31 / 2;
        v33 = v31 / 2;
        if ( v31 / 2 != v31 && v32 > *((_DWORD *)this + 18) && v32 >= 0 )
        {
          v34 = 8LL * (unsigned int)v32;
          if ( v34 <= 0xFFFFFFFF )
          {
            v35 = LocalReAlloc(*v11, (unsigned int)v34, 0x42u);
            if ( v35 )
            {
              *v11 = v35;
              *((_DWORD *)this + 19) = v33;
            }
          }
        }
      }
    }
  }
  LocalFree(v6);
  CloseHandle(hObject);
  if ( Microsoft_Windows_TSF_msctfEnableBits < 0 )
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_TSF_msctf_Context, SendAsyncRequest_End, v36, 1, &v80);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18002f140  push    rbp
0x18002f142  push    rbx
0x18002f143  push    rsi
0x18002f144  push    rdi
0x18002f145  push    r13
0x18002f147  lea     rbp, [rsp-37h]
0x18002f14c  sub     rsp, 100h
0x18002f153  mov     rax, cs:__security_cookie
0x18002f15a  xor     rax, rsp
0x18002f15d  mov     [rbp+57h+var_38], rax
0x18002f161  xor     edi, edi
0x18002f163  mov     [rbp+57h+var_50], r8
0x18002f167  mov     [r8], rdi
0x18002f16a  mov     rbx, rdx
0x18002f16d  mov     r13, rcx
0x18002f170  mov     [rbp+57h+var_70], rdx
0x18002f174  mov     eax, 0FFFFFFFFh
0x18002f179  mov     esi, 40h ; '@'
0x18002f17e  cmp     [rcx+8], rdi
0x18002f182  jz      loc_18002FB37
0x18002f188  lea     r9, [rbp+57h+uBytes]
0x18002f18c  mov     [rsp+120h+var_30], r15
0x18002f194  xor     r8d, r8d
0x18002f197  mov     [rbp+57h+uBytes], rdi
0x18002f19b  xor     edx, edx
0x18002f19d  mov     ecx, 70000000h
0x18002f1a2  call    cs:__imp_AlpcInitializeMessageAttribute
0x18002f1a8  cmp     eax, 0C0000023h
0x18002f1ad  jnz     loc_18002FE36
0x18002f1b3  mov     rax, [rbp+57h+uBytes]
0x18002f1b7  test    rax, rax
0x18002f1ba  jz      loc_18002FE36
0x18002f1c0  mov     edx, eax; uBytes
0x18002f1c2  mov     ecx, esi; uFlags
0x18002f1c4  call    cs:__imp_LocalAlloc
0x18002f1ca  mov     [rbp+57h+var_48], rax
0x18002f1ce  mov     r15, rax
0x18002f1d1  test    rax, rax
0x18002f1d4  jz      loc_18002FE36
0x18002f1da  mov     r8, [rbp+57h+uBytes]
0x18002f1de  lea     r9, [rbp+57h+uBytes]
0x18002f1e2  mov     rdx, rax
0x18002f1e5  mov     ecx, 70000000h
0x18002f1ea  call    cs:__imp_AlpcInitializeMessageAttribute
0x18002f1f0  test    eax, eax
0x18002f1f2  js      loc_18002FE2D
0x18002f1f8  mov     [rsp+120h+arg_18], r12
0x18002f200  movsxd  r12, dword ptr [r13+48h]
0x18002f204  mov     [rsp+120h+var_28], r14
0x18002f20c  mov     [rbp+57h+var_80], rbx
0x18002f210  mov     [rbp+57h+hMem], rdi
0x18002f214  mov     [rbp+57h+var_90], r12d
0x18002f218  test    r12d, r12d
0x18002f21b  js      loc_18002FC58
0x18002f221  lea     edi, [r12+1]
0x18002f226  cmp     r12d, edi
0x18002f229  jg      loc_18002FC58
0x18002f22f  cmp     [r13+4Ch], edi
0x18002f233  jge     loc_18002FB11
0x18002f239  mov     eax, r12d
0x18002f23c  cdq
0x18002f23d  sub     eax, edx
0x18002f23f  sar     eax, 1
0x18002f241  lea     ebx, [rax+r12]
0x18002f245  cmp     edi, ebx
0x18002f247  cmovg   ebx, edi
0x18002f24a  cmp     ebx, 0FFFFFFFh
0x18002f250  ja      loc_18002FC58
0x18002f256  mov     rcx, [r13+40h]; hMem
0x18002f25a  lea     r14, [r13+40h]
0x18002f25e  lea     edx, ds:0[rbx*8]; uBytes
0x18002f265  test    rcx, rcx
0x18002f268  jnz     loc_18002FBA8
0x18002f26e  call    cs:__imp_LocalAlloc
0x18002f274  test    rax, rax
0x18002f277  jz      loc_18002FC58
0x18002f27d  mov     [r14], rax
0x18002f280  mov     [r13+4Ch], ebx
0x18002f284  mov     eax, [r13+48h]
0x18002f288  cmp     r12d, eax
0x18002f28b  jge     short loc_18002F2AF
0x18002f28d  mov     rcx, [r13+40h]
0x18002f291  lea     r14, [r13+40h]
0x18002f295  sub     eax, r12d
0x18002f298  movsxd  r8, eax
0x18002f29b  movsxd  rax, edi
0x18002f29e  lea     rdx, [rcx+r12*8]; Src
0x18002f2a2  shl     r8, 3; Size
0x18002f2a6  lea     rcx, [rcx+rax*8]; void *
0x18002f2aa  call    memmove_0
0x18002f2af  inc     dword ptr [r13+48h]
0x18002f2b3  cmp     r12d, [r13+48h]
0x18002f2b7  jge     short loc_18002F2C9
0x18002f2b9  mov     rcx, [r14]
0x18002f2bc  test    rcx, rcx
0x18002f2bf  jz      short loc_18002F2C9
0x18002f2c1  lea     rdx, [rbp+57h+var_80]
0x18002f2c5  mov     [rcx+r12*8], rdx
0x18002f2c9  xor     r9d, r9d; lpName
0x18002f2cc  xor     r8d, r8d; bInitialState
0x18002f2cf  xor     edx, edx; bManualReset
0x18002f2d1  xor     ecx, ecx; lpEventAttributes
0x18002f2d3  call    cs:__imp_CreateEventW
0x18002f2d9  mov     [rbp+57h+hObject], rax
0x18002f2dd  mov     rbx, rax
0x18002f2e0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002f2e4  jz      loc_18002FBC3
0x18002f2ea  mov     edx, 10000000h
0x18002f2ef  mov     rcx, r15
0x18002f2f2  call    cs:__imp_AlpcGetMessageAttribute
0x18002f2f8  mov     edx, 20000000h
0x18002f2fd  mov     rcx, r15
0x18002f300  mov     dword ptr [rax], 30000h
0x18002f306  mov     [rax+8], rbx
0x18002f30a  call    cs:__imp_AlpcGetMessageAttribute
0x18002f310  mov     rbx, [rbp+57h+var_70]
0x18002f314  lea     rcx, [rbp+57h+var_80]
0x18002f318  mov     [rax+8], rcx
0x18002f31c  mov     dword ptr [r15+4], 30000000h
0x18002f324  mov     eax, [rbx+28h]
0x18002f327  mov     [rbp+57h+var_68], 0
0x18002f32f  bt      eax, 1Ah
0x18002f333  jb      loc_18002FE40
0x18002f339  cmp     cs:Microsoft_Windows_TSF_msctfEnableBits, 0
0x18002f340  jl      loc_18002FE73
0x18002f346  mov     rcx, [r13+8]
0x18002f34a  xor     eax, eax
0x18002f34c  mov     [rsp+120h+var_E8], rax
0x18002f351  mov     r9, r15
0x18002f354  mov     [rsp+120h+var_F0], rax
0x18002f359  mov     r8, rbx
0x18002f35c  mov     [rsp+120h+var_F8], rax
0x18002f361  xor     edx, edx
0x18002f363  mov     qword ptr [rsp+120h+wRemoveMsg], rax
0x18002f368  mov     edi, 80004005h
0x18002f36d  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18002f373  test    eax, eax
0x18002f375  js      loc_18002F428
0x18002f37b  mov     rsi, [r13+28h]
0x18002f37f  xor     r15d, r15d
0x18002f382  mov     [rbp+57h+var_88], rsi
0x18002f386  xor     r14d, r14d
0x18002f389  inc     dword ptr [rsi+15Ch]
0x18002f38f  call    cs:__imp_GetTickCount
0x18002f395  mov     ecx, eax
0x18002f397  mov     bl, 1
0x18002f399  mov     eax, 0CCCCCCCDh
0x18002f39e  mul     ecx
0x18002f3a0  mov     edi, edx
0x18002f3a2  shr     edi, 3
0x18002f3a5  add     edi, 12Ch
0x18002f3ab  mov     [rbp+57h+var_A0], edi
0x18002f3ae  call    cs:__imp_GetTickCount
0x18002f3b4  mov     ecx, eax
0x18002f3b6  mov     eax, 0CCCCCCCDh
0x18002f3bb  mul     ecx
0x18002f3bd  shr     edx, 3
0x18002f3c0  cmp     edi, edx
0x18002f3c2  jb      loc_18002F66F
0x18002f3c8  test    bl, bl
0x18002f3ca  jz      loc_18002F517
0x18002f3d0  mov     rcx, r13; this
0x18002f3d3  call    ?Receive@CCtfClientPort@@QEAAJXZ; CCtfClientPort::Receive(void)
0x18002f3d8  mov     rcx, [rbp+57h+hMem]
0x18002f3dc  test    rcx, rcx
0x18002f3df  jz      loc_18002F517
0x18002f3e5  mov     edi, [rcx+34h]
0x18002f3e8  test    edi, edi
0x18002f3ea  js      loc_18002F678
0x18002f3f0  mov     rax, [rbp+57h+var_50]
0x18002f3f4  mov     [rax], rcx
0x18002f3f7  mov     [rbp+57h+hMem], 0
0x18002f3ff  xor     edx, edx
0x18002f401  cmp     edx, [r13+48h]
0x18002f405  jl      loc_18002FB1A
0x18002f40b  mov     r12d, [rbp+57h+var_90]
0x18002f40f  test    r14d, r14d
0x18002f412  jnz     loc_18002FF1B
0x18002f418  mov     rcx, rsi; this
0x18002f41b  call    ?Release@tagSYSTHREAD@@QEAAKXZ; tagSYSTHREAD::Release(void)
0x18002f420  mov     r15, [rbp+57h+var_48]
0x18002f424  lea     r14, [r13+40h]
0x18002f428  mov     r8, [rbp+57h+var_68]
0x18002f42c  test    r8, r8
0x18002f42f  jnz     loc_18002FF29
0x18002f435  test    r12d, r12d
0x18002f438  js      loc_18002F4C3
0x18002f43e  lea     edx, [r12+1]
0x18002f443  test    edx, edx
0x18002f445  js      short loc_18002F4C3
0x18002f447  mov     r8d, [r13+48h]
0x18002f44b  cmp     edx, r8d
0x18002f44e  jg      short loc_18002F4C3
0x18002f450  jge     short loc_18002F477
0x18002f452  mov     rcx, [r14]
0x18002f455  mov     eax, r12d
0x18002f458  not     eax
0x18002f45a  add     eax, r8d
0x18002f45d  movsxd  r8, eax
0x18002f460  movsxd  rax, edx
0x18002f463  shl     r8, 3; Size
0x18002f467  lea     rdx, [rcx+rax*8]; Src
0x18002f46b  movsxd  rax, r12d
0x18002f46e  lea     rcx, [rcx+rax*8]; void *
0x18002f472  call    memmove_0
0x18002f477  mov     ecx, [r13+4Ch]
0x18002f47b  mov     eax, ecx
0x18002f47d  dec     dword ptr [r13+48h]
0x18002f481  cdq
0x18002f482  sub     eax, edx
0x18002f484  sar     eax, 1
0x18002f486  mov     ebx, eax
0x18002f488  cmp     ebx, ecx
0x18002f48a  jz      short loc_18002F4C3
0x18002f48c  cmp     eax, [r13+48h]
0x18002f490  jle     short loc_18002F4C3
0x18002f492  test    ebx, ebx
0x18002f494  js      short loc_18002F4C3
0x18002f496  mov     eax, ebx
0x18002f498  mov     ecx, 0FFFFFFFFh
0x18002f49d  shl     rax, 3
0x18002f4a1  cmp     rax, rcx
0x18002f4a4  ja      short loc_18002F4C3
0x18002f4a6  mov     rcx, [r14]; hMem
0x18002f4a9  mov     r8d, 42h ; 'B'; uFlags
0x18002f4af  mov     edx, eax; uBytes
0x18002f4b1  call    cs:__imp_LocalReAlloc
0x18002f4b7  test    rax, rax
0x18002f4ba  jz      short loc_18002F4C3
0x18002f4bc  mov     [r14], rax
0x18002f4bf  mov     [r13+4Ch], ebx
0x18002f4c3  mov     rcx, r15; hMem
0x18002f4c6  call    cs:__imp_LocalFree
0x18002f4cc  mov     rcx, [rbp+57h+hObject]; hObject
0x18002f4d0  call    cs:__imp_CloseHandle
0x18002f4d6  cmp     cs:Microsoft_Windows_TSF_msctfEnableBits, 0
0x18002f4dd  jl      loc_18002FF3A
0x18002f4e3  mov     eax, edi
0x18002f4e5  mov     r14, [rsp+120h+var_28]
0x18002f4ed  mov     r12, [rsp+120h+arg_18]
0x18002f4f5  mov     r15, [rsp+120h+var_30]
0x18002f4fd  mov     rcx, [rbp+57h+var_38]
0x18002f501  xor     rcx, rsp; StackCookie
0x18002f504  call    __security_check_cookie
0x18002f509  add     rsp, 100h
0x18002f510  pop     r13
0x18002f512  pop     rdi
0x18002f513  pop     rsi
0x18002f514  pop     rbx
0x18002f515  pop     rbp
0x18002f516  retn
0x18002f517  mov     rax, [rbp+57h+hObject]
0x18002f51b  xor     edx, edx; dwMilliseconds
0x18002f51d  mov     rcx, rax; hHandle
0x18002f520  mov     [rbp+57h+pHandles], rax
0x18002f524  call    cs:__imp_WaitForSingleObject
0x18002f52a  test    eax, eax
0x18002f52c  jz      loc_18002FBB9
0x18002f532  cmp     eax, 102h
0x18002f537  jnz     loc_18002F69F
0x18002f53d  mov     ecx, 8; flags
0x18002f542  call    cs:__imp_GetQueueStatus
0x18002f548  mov     ecx, eax
0x18002f54a  shr     ecx, 10h
0x18002f54d  or      cl, al
0x18002f54f  test    cl, 8
0x18002f552  jz      loc_18002F63B
0x18002f558  mov     ebx, cs:?g_msgRpcSendReceive@@3IA; uint g_msgRpcSendReceive
0x18002f55e  xorps   xmm0, xmm0
0x18002f561  mov     rdi, [rsi+88h]
0x18002f568  movups  xmmword ptr [rsp+120h+Msg.hwnd], xmm0
0x18002f56d  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18002f571  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x18002f575  mov     r9d, ebx; wMsgFilterMax
0x18002f578  mov     [rsp+120h+wRemoveMsg], 3; wRemoveMsg
0x18002f580  mov     r8d, ebx; wMsgFilterMin
0x18002f583  lea     rcx, [rsp+120h+Msg]; lpMsg
0x18002f588  mov     rdx, rdi; hWnd
0x18002f58b  call    cs:__imp_PeekMessageW
0x18002f591  test    eax, eax
0x18002f593  jz      short loc_18002F5CA
0x18002f595  cmp     [rsp+120h+Msg.message], 12h
0x18002f59a  jnz     loc_18002FC6B
0x18002f5a0  mov     r15d, dword ptr [rbp+57h+Msg.wParam]
0x18002f5a4  lea     rcx, [rsp+120h+Msg]; lpMsg
0x18002f5a9  mov     r9d, ebx; wMsgFilterMax
0x18002f5ac  mov     [rsp+120h+wRemoveMsg], 3; wRemoveMsg
0x18002f5b4  mov     r8d, ebx; wMsgFilterMin
0x18002f5b7  mov     rdx, rdi; hWnd
0x18002f5ba  mov     r14d, 1
0x18002f5c0  call    cs:__imp_PeekMessageW
0x18002f5c6  test    eax, eax
0x18002f5c8  jnz     short loc_18002F595
0x18002f5ca  mov     ebx, cs:?g_msgPrivate@@3IA; uint g_msgPrivate
0x18002f5d0  xorps   xmm0, xmm0
0x18002f5d3  movups  xmmword ptr [rsp+120h+Msg.hwnd], xmm0
0x18002f5d8  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18002f5dc  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x18002f5e0  mov     r9d, ebx; wMsgFilterMax
0x18002f5e3  mov     [rsp+120h+wRemoveMsg], 3; wRemoveMsg
  ... truncated ...
```
