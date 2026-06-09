# DownstreamTransport::RpcAsyncPipeDownload(_RPC_ASYNC_STATE &,ASYNC_pipe_BYTE_PIPE &,uchar *,ulong,Writer &,int const volatile &)

- ea: `0x1401ac200`
- end: `0x1401acc48`
- name: `?RpcAsyncPipeDownload@DownstreamTransport@@IEAAPEAVFrsStatus@@AEAU_RPC_ASYNC_STATE@@AEAUASYNC_pipe_BYTE_PIPE@@PEAEKAEAVWriter@@AEDH@Z`
- size: `2632`
- prototype: `struct FrsStatus *(DownstreamTransport *__hidden this, struct _RPC_ASYNC_STATE *, struct ASYNC_pipe_BYTE_PIPE *, unsigned __int8 *, unsigned int, struct Writer *, const volatile int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401a68ec`
- `0x1401a9580`

## callees

- `0x1400036a0`
- `0x14000e34c`
- `0x14001b620`
- `0x1400391c4`
- `0x1400c29b8`
- `0x1401a7f28`
- `0x1401a82ac`
- `0x1401ac200`
- `0x1401ae578`
- `0x1401af668`
- `0x1401b9494`
- `0x1401ba178`
- `0x1401bda10`
- `0x140223010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1401ac3a0`
- `KERNEL32!WaitForSingleObject` at `0x1401ac71c`
- `KERNEL32!WaitForSingleObject` at `0x1401ac8bb`
- `KERNEL32!WaitForSingleObject` at `0x1401ac3a0`
- `KERNEL32!WaitForSingleObject` at `0x1401ac71c`
- `KERNEL32!WaitForSingleObject` at `0x1401ac8bb`
- `KERNEL32!GetCurrentThreadId` at `0x1401ac32f`
- `KERNEL32!GetCurrentThreadId` at `0x1401ac3bf`
- `KERNEL32!GetCurrentThreadId` at `0x1401ac953`
- `KERNEL32!GetCurrentThreadId` at `0x1401aca06`
- `KERNEL32!GetCurrentThreadId` at `0x1401acad7`
- `KERNEL32!GetCurrentThreadId` at `0x1401acb56`
- `KERNEL32!GetCurrentThreadId` at `0x1401acba3`
- `KERNEL32!GetCurrentThreadId` at `0x1401acbe3`
- `KERNEL32!GetCurrentThreadId` at `0x1401ac32f`
- `KERNEL32!GetCurrentThreadId` at `0x1401ac3bf`
- `KERNEL32!GetCurrentThreadId` at `0x1401ac953`
- `KERNEL32!GetCurrentThreadId` at `0x1401aca06`
- `KERNEL32!GetCurrentThreadId` at `0x1401acad7`
- `KERNEL32!GetCurrentThreadId` at `0x1401acb56`
- `KERNEL32!GetCurrentThreadId` at `0x1401acba3`
- `KERNEL32!GetCurrentThreadId` at `0x1401acbe3`
- `RPCRT4!RpcAsyncCancelCall` at `0x1401ac6f7`
- `RPCRT4!RpcAsyncCancelCall` at `0x1401ac83f`
- `RPCRT4!RpcAsyncCancelCall` at `0x1401ac6f7`
- `RPCRT4!RpcAsyncCancelCall` at `0x1401ac83f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1401ac922`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1401ac922`

## string_xrefs

- `0x1401ac9d6`: `(Ignored) Failed to complete RPC call after receiving all data. rpcAsyncState:%p Error:%?`
- `0x1401aca89`: `(Ignored) Failed to complete RPC call after receiving all data. rpcAsyncState:%p Error:%?`
- `0x1401ac87a`: `Wait completion rpcAsyncState:%p`

## pseudocode

```c
struct FrsStatus *__fastcall DownstreamTransport::RpcAsyncPipeDownload(
        DownstreamTransport *this,
        struct _RPC_ASYNC_STATE *a2,
        struct ASYNC_pipe_BYTE_PIPE *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        struct Writer *a6,
        const volatile int *a7)
{
  __int64 v7; // rdi
  DownstreamTransport *v8; // r12
  LPCRITICAL_SECTION v9; // rcx
  struct ASYNC_pipe_BYTE_PIPE *v10; // r10
  int v12; // ebx
  unsigned __int8 *v13; // r11
  struct FrsStatus *v14; // r15
  RPC_STATUS v15; // r14d
  const wchar_t *v16; // rdx
  unsigned __int64 v17; // r8
  struct _RPC_ASYNC_STATE *v18; // rax
  struct _RPC_ASYNC_STATE *v19; // r13
  __int64 v20; // rcx
  __int64 (__fastcall *v21)(__int64, unsigned __int8 *, _QWORD, unsigned __int64 *); // rax
  RPC_STATUS v22; // eax
  DWORD CurrentThreadId; // eax
  int v24; // r8d
  DWORD v25; // eax
  DWORD v26; // r12d
  DWORD v27; // eax
  __int64 v28; // rcx
  RPC_ASYNC_EVENT Event; // ecx
  unsigned int v30; // eax
  Dword *v31; // rax
  int v32; // ebx
  int v33; // ebx
  int v34; // ebx
  int v35; // ebx
  int v36; // ebx
  int v37; // ebx
  int v38; // ebx
  int v39; // eax
  Dword *v40; // rax
  const wchar_t **v41; // rcx
  int v42; // eax
  DWORD v43; // eax
  int v44; // r8d
  struct FrsStatus *v45; // rax
  DWORD v46; // eax
  int v47; // r8d
  struct FrsStatus *v48; // rax
  unsigned int v49; // eax
  DWORD v50; // ebx
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rcx
  DWORD v54; // eax
  int v55; // r8d
  DWORD v56; // eax
  __int64 v57; // rcx
  DWORD v58; // eax
  __int64 v59; // rcx
  int v61; // [rsp+30h] [rbp-D0h]
  struct _RPC_ASYNC_STATE *v62; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v63; // [rsp+58h] [rbp-A8h] BYREF
  RPC_STATUS Reply; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v65; // [rsp+68h] [rbp-98h] BYREF
  int v66; // [rsp+70h] [rbp-90h]
  int v67; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v68; // [rsp+78h] [rbp-88h]
  int v69; // [rsp+80h] [rbp-80h]
  struct FrsStatus *v70; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v71; // [rsp+90h] [rbp-70h]
  struct _RPC_ASYNC_STATE *v72; // [rsp+98h] [rbp-68h] BYREF
  const wchar_t *v73; // [rsp+A0h] [rbp-60h] BYREF
  int v74; // [rsp+A8h] [rbp-58h]
  int v75; // [rsp+ACh] [rbp-54h]
  const wchar_t *v76; // [rsp+B0h] [rbp-50h]
  DownstreamTransport *v77; // [rsp+B8h] [rbp-48h]
  struct ASYNC_pipe_BYTE_PIPE *v78; // [rsp+C0h] [rbp-40h]
  struct _RPC_ASYNC_STATE *v79; // [rsp+C8h] [rbp-38h] BYREF
  struct _RPC_ASYNC_STATE *v80; // [rsp+D0h] [rbp-30h] BYREF
  struct _RPC_ASYNC_STATE *v81; // [rsp+D8h] [rbp-28h] BYREF
  const wchar_t *v82; // [rsp+E0h] [rbp-20h] BYREF
  int v83; // [rsp+E8h] [rbp-18h]
  int v84; // [rsp+ECh] [rbp-14h]
  const wchar_t *v85; // [rsp+F0h] [rbp-10h]
  const wchar_t *v86; // [rsp+F8h] [rbp-8h] BYREF
  int v87; // [rsp+100h] [rbp+0h]
  int v88; // [rsp+104h] [rbp+4h]
  const wchar_t *v89; // [rsp+108h] [rbp+8h]
  const wchar_t *v90; // [rsp+110h] [rbp+10h] BYREF
  int v91; // [rsp+118h] [rbp+18h]
  int v92; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v93; // [rsp+120h] [rbp+20h]
  const wchar_t *v94; // [rsp+128h] [rbp+28h] BYREF
  int v95; // [rsp+130h] [rbp+30h]
  int v96; // [rsp+134h] [rbp+34h]
  const wchar_t *v97; // [rsp+138h] [rbp+38h]
  _BYTE v98[48]; // [rsp+140h] [rbp+40h] BYREF

  v7 = 0;
  v8 = this;
  v77 = this;
  v9 = g_DebugLog;
  v10 = a3;
  v78 = a3;
  v71 = a4;
  v12 = 2;
  v70 = a6;
  v13 = a4;
  v63 = 0;
  v14 = 0;
  Reply = 0;
  v15 = 0;
  v16 = L"DownstreamTransport::RpcAsyncPipeDownload";
  v69 = 0;
  v17 = (unsigned __int64)L"DOWN";
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v82 = L"DownstreamTransport::RpcAsyncPipeDownload";
    v85 = L"DOWN";
    v83 = 6067;
    v84 = 5;
    v79 = a2;
    dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v82, L"rpcAsyncState:%p", &v79);
    v9 = g_DebugLog;
    v10 = v78;
    v13 = v71;
  }
  v18 = (struct _RPC_ASYNC_STATE *)((char *)v10 + 24);
  v72 = (struct _RPC_ASYNC_STATE *)((char *)v10 + 24);
  v19 = (struct _RPC_ASYNC_STATE *)((char *)v10 + 24);
  while ( !v14 )
  {
    v19 = v18;
    if ( v12 != 2 )
      break;
    if ( *a7 )
    {
      v9 = g_DebugLog;
      if ( g_DebugLog )
      {
        if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v73 = L"DownstreamTransport::RpcAsyncPipeDownload";
          v74 = 6072;
          v75 = 5;
          v76 = L"DOWN";
          v70 = (struct FrsStatus *)a2;
          dbgobj::DbgPrint<unsigned short,unsigned __int64>(
            &v73,
            L"Cancel before pull following shutdown. rpcAsyncState:%p",
            &v70);
          v9 = g_DebugLog;
        }
LABEL_75:
        if ( v9 && LODWORD(v9[1].LockSemaphore) && SLODWORD(v9[1].OwningThread) >= 5 )
        {
          v65 = L"DownstreamTransport::RpcAsyncPipeDownload";
          v66 = 6186;
          v67 = 5;
          v68 = L"DOWN";
          v72 = a2;
          dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v65, L"Cancel before pull rpcAsyncState:%p", &v72);
        }
      }
      RpcAsyncCancelCall(a2, 1);
      v9 = g_DebugLog;
LABEL_80:
      if ( v9 && LODWORD(v9[1].LockSemaphore) && SLODWORD(v9[1].OwningThread) >= 5 )
      {
        v65 = L"DownstreamTransport::RpcAsyncPipeDownload";
        v66 = 6192;
        v67 = 5;
        v68 = L"DOWN";
        v62 = a2;
        dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v65, L"Wait completion rpcAsyncState:%p", &v62);
      }
      v42 = Settings::GenericDwordSetting::operator()(&Settings::AsyncRpcDownloadMaxWaitInSeconds);
      if ( WaitForSingleObject(a2->u.APC.NotificationRoutine, 1000 * v42) == 258
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v65 = L"DownstreamTransport::RpcAsyncPipeDownload";
        v41 = &v65;
        v66 = 6195;
        v67 = 2;
        v68 = L"DOWN";
LABEL_89:
        v62 = a2;
        dbgobj::DbgPrint<unsigned short,unsigned __int64>(
          v41,
          L"RPC Async pipe event not received on time. rpcAsyncState:%p",
          &v62);
      }
      goto LABEL_90;
    }
    v19 = (struct _RPC_ASYNC_STATE *)((char *)v10 + 24);
    v20 = *((_QWORD *)v10 + 3);
    v21 = *(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, unsigned __int64 *))v10;
    LODWORD(v63) = 0;
    v22 = v21(v20, v13, a5, &v63);
    v15 = v22;
    if ( !v22 )
    {
      v17 = (unsigned int)v63;
      if ( !(_DWORD)v63 )
      {
        v69 = 1;
        v12 = v63 + 5;
        goto LABEL_38;
      }
      v14 = (struct FrsStatus *)WriteBack(v70, v71);
      if ( v14
        || (v14 = BandwidthThrottler::ThrottleBytes((DownstreamTransport *)((char *)v8 + 176), 0, (unsigned int)v63, 0)) != 0 )
      {
        v9 = g_DebugLog;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          v95 = 6107;
          v94 = L"DownstreamTransport::RpcAsyncPipeDownload";
          v96 = 3;
          v97 = L"DOWN";
          v62 = a2;
          dbgobj::DbgPrint<unsigned short,unsigned __int64,FrsStatus>(
            &v94,
            L"Aborting transfer. rpcAsyncState:%p Error:%?",
            &v62,
            v14);
          goto LABEL_45;
        }
      }
      else
      {
LABEL_45:
        v9 = g_DebugLog;
      }
      v12 = 2;
      goto LABEL_47;
    }
    if ( v22 != 997 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = (struct FrsStatus *)LogTranslatedRemoteError(
                                  v15,
                                  v15 == 1237,
                                  v24,
                                  (unsigned int)"DownstreamTransport::RpcAsyncPipeDownload",
                                  6173,
                                  CurrentThreadId,
                                  v61,
                                  0);
      v12 = 10;
LABEL_38:
      v9 = g_DebugLog;
      goto LABEL_47;
    }
    v12 = 3;
    HIDWORD(v63) = 0;
    while ( v12 == 3 )
    {
      if ( *a7 )
      {
        v9 = g_DebugLog;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v91 = 6122;
          v90 = L"DownstreamTransport::RpcAsyncPipeDownload";
          v92 = 5;
          v93 = L"DOWN";
          v81 = a2;
          dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v90, L"cancel after pull rpcAsyncState:%p", &v81);
LABEL_28:
          v9 = g_DebugLog;
        }
LABEL_29:
        v15 = 0;
        v12 = 6;
        goto LABEL_30;
      }
      v25 = WaitForSingleObject(a2->u.APC.NotificationRoutine, 0x3E8u);
      v26 = v25;
      if ( v25 )
      {
        if ( v25 == 258 )
        {
          ++HIDWORD(v63);
        }
        else
        {
          v12 = 6;
          v27 = GetCurrentThreadId();
          v14 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                      v28,
                                      v26,
                                      0,
                                      1,
                                      "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                                      "DownstreamTransport::RpcAsyncPipeDownload",
                                      6154,
                                      v27,
                                      0);
        }
      }
      else
      {
        Event = a2->Event;
        if ( Event )
        {
          if ( Event == RpcReceiveComplete )
            v12 = 2;
        }
        else
        {
          v12 = 9;
        }
      }
      v30 = Settings::GenericDwordSetting::operator()(&Settings::AsyncRpcDownloadMaxWaitInSeconds);
      if ( HIDWORD(v63) >= v30 )
      {
        v31 = Dword::Dword((Dword *)v98, 0x1811u, 10);
        FrsEvent::Log(3221226483LL, L"base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp", v31);
        v9 = g_DebugLog;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v87 = 6162;
          v86 = L"DownstreamTransport::RpcAsyncPipeDownload";
          v88 = 2;
          v89 = L"DOWN";
          v80 = a2;
          dbgobj::DbgPrint<unsigned short,unsigned __int64>(
            &v86,
            L"RPC Async pipe event not received on time. rpcAsyncState:%p",
            &v80);
          goto LABEL_28;
        }
        goto LABEL_29;
      }
    }
    v9 = g_DebugLog;
LABEL_30:
    v8 = v77;
LABEL_47:
    v18 = v72;
    v10 = v78;
    v13 = v71;
  }
  v32 = v12 - 2;
  if ( !v32 )
    goto LABEL_75;
  v33 = v32 - 1;
  if ( !v33 )
    goto LABEL_63;
  v34 = v33 - 1;
  if ( !v34 )
    goto LABEL_75;
  v35 = v34 - 1;
  if ( !v35 )
    goto LABEL_80;
  v36 = v35 - 1;
  if ( v36 )
  {
    v37 = v36 - 1;
    if ( v37 )
    {
      v38 = v37 - 1;
      if ( v38 )
      {
        if ( v38 == 1 )
          goto LABEL_90;
        goto LABEL_91;
      }
LABEL_74:
      (*(void (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, unsigned __int64 *))v10)(
        *(_QWORD *)&v19->Size,
        v71,
        a5,
        &v63);
      v15 = 0;
      goto LABEL_92;
    }
  }
  else
  {
LABEL_63:
    if ( v9 && LODWORD(v9[1].LockSemaphore) && SLODWORD(v9[1].OwningThread) >= 5 )
    {
      v74 = 6207;
      v73 = L"DownstreamTransport::RpcAsyncPipeDownload";
      v75 = 5;
      v76 = L"DOWN";
      v62 = a2;
      dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v73, L"Wait for pull/cancel after pull rpcAsyncState:%p", &v62);
    }
    v15 = RpcAsyncCancelCall(a2, 1);
  }
  v39 = Settings::GenericDwordSetting::operator()(&Settings::AsyncRpcDownloadMaxWaitInSeconds);
  if ( WaitForSingleObject(a2->u.APC.NotificationRoutine, 1000 * v39) == 258 )
  {
    v40 = Dword::Dword((Dword *)v98, 0x1849u, 10);
    FrsEvent::Log(3221226483LL, L"base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp", v40);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v74 = 6218;
      v73 = L"DownstreamTransport::RpcAsyncPipeDownload";
      v76 = L"DOWN";
      v41 = &v73;
      v75 = 2;
      goto LABEL_89;
    }
LABEL_90:
    v15 = RpcAsyncCompleteCall(a2, &Reply);
  }
  else
  {
    if ( a2->Event == RpcCallComplete )
      goto LABEL_90;
    v19 = v72;
    if ( a2->Event == RpcReceiveComplete )
    {
      v10 = v78;
      goto LABEL_74;
    }
  }
LABEL_91:
  if ( !v15 )
  {
LABEL_92:
    if ( v69 )
    {
      if ( Reply )
      {
        v43 = GetCurrentThreadId();
        v45 = (struct FrsStatus *)LogTranslatedRemoteError(
                                    Reply,
                                    Reply == 1237,
                                    v44,
                                    (unsigned int)"DownstreamTransport::RpcAsyncPipeDownload",
                                    6256,
                                    v43,
                                    v61,
                                    0);
        v70 = v45;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          v66 = 6257;
          v65 = L"DownstreamTransport::RpcAsyncPipeDownload";
          v67 = 3;
          v68 = L"DOWN";
          v62 = a2;
          dbgobj::DbgPrint<unsigned short,unsigned __int64,FrsStatus>(
            &v65,
            L"(Ignored) Failed to complete RPC call after receiving all data. rpcAsyncState:%p Error:%?",
            &v62,
            v45);
        }
        CLEAR_ERROR(&v70);
      }
    }
    else
    {
      v15 = Reply;
    }
    goto LABEL_107;
  }
  if ( v69 )
  {
    v46 = GetCurrentThreadId();
    v48 = (struct FrsStatus *)LogTranslatedRemoteError(
                                v15,
                                v15 == 1237,
                                v47,
                                (unsigned int)"DownstreamTransport::RpcAsyncPipeDownload",
                                6266,
                                v46,
                                v61,
                                0);
    v70 = v48;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v66 = 6267;
      v65 = L"DownstreamTransport::RpcAsyncPipeDownload";
      v67 = 3;
      v68 = L"DOWN";
      v62 = a2;
      dbgobj::DbgPrint<unsigned short,unsigned __int64,FrsStatus>(
        &v65,
        L"(Ignored) Failed to complete RPC call after receiving all data. rpcAsyncState:%p Error:%?",
        &v62,
        v48);
    }
    CLEAR_ERROR(&v70);
    v15 = 0;
  }
  else
  {
    LogExtendedErrorInformation_0(v9, v16, v17);
  }
LABEL_107:
  if ( v14 )
    goto LABEL_113;
  v49 = Settings::GenericDwordSetting::operator()(&Settings::AsyncRpcDownloadMaxWaitInSeconds);
  if ( HIDWORD(v63) >= v49 )
  {
    v50 = GetCurrentThreadId();
    v52 = FrsStatusList::PushNewError(
            v51,
            9074,
            0,
            3,
            "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
            "DownstreamTransport::RpcAsyncPipeDownload",
            6280,
            v50,
            0);
    v14 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v53,
                                9027,
                                0,
                                3,
                                "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                                "DownstreamTransport::RpcAsyncPipeDownload",
                                6280,
                                v50,
                                v52);
    if ( v14 )
      goto LABEL_113;
  }
  v54 = GetCurrentThreadId();
  v14 = (struct FrsStatus *)LogTranslatedRemoteError(
                              v15,
                              v15 == 1237,
                              v55,
                              (unsigned int)"DownstreamTransport::RpcAsyncPipeDownload",
                              6284,
                              v54,
                              v61,
                              0);
  if ( v14
    || *a7
    && (v56 = GetCurrentThreadId(),
        (v14 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v57,
                                     9033,
                                     0,
                                     3,
                                     "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                                     "DownstreamTransport::RpcAsyncPipeDownload",
                                     6288,
                                     v56,
                                     0)) != 0) )
  {
LABEL_113:
    v58 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v59,
                                 *((unsigned int *)v14 + 1),
                                 *((unsigned int *)v14 + 2),
                                 *(unsigned int *)v14,
                                 "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                                 "DownstreamTransport::RpcAsyncPipeDownload",
                                 6291,
                                 v58,
                                 v14);
  }
  return (struct FrsStatus *)v7;
}

```

## disassembly

```asm
0x1401ac200  push    rbp
0x1401ac202  push    rbx
0x1401ac203  push    rsi
0x1401ac204  push    rdi
0x1401ac205  push    r12
0x1401ac207  push    r13
0x1401ac209  push    r14
0x1401ac20b  push    r15
0x1401ac20d  lea     rbp, [rsp-88h]
0x1401ac215  sub     rsp, 188h
0x1401ac21c  mov     rax, cs:__security_cookie
0x1401ac223  xor     rax, rsp
0x1401ac226  mov     [rbp+0C0h+var_50], rax
0x1401ac22a  mov     rax, [rbp+0C0h+arg_28]
0x1401ac231  xor     edi, edi
0x1401ac233  mov     r12, rcx
0x1401ac236  mov     [rbp+0C0h+var_108], rcx
0x1401ac23a  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ac241  mov     r10, r8
0x1401ac244  mov     [rbp+0C0h+var_100], r8
0x1401ac248  mov     rsi, rdx
0x1401ac24b  mov     [rbp+0C0h+var_130], r9
0x1401ac24f  lea     ebx, [rdi+2]
0x1401ac252  mov     [rbp+0C0h+var_138], rax
0x1401ac256  mov     r11, r9
0x1401ac259  mov     dword ptr [rsp+1C0h+var_168], edi
0x1401ac25d  mov     r15d, edi
0x1401ac260  mov     [rsp+1C0h+Reply], edi
0x1401ac264  mov     r14d, edi
0x1401ac267  mov     dword ptr [rsp+1C0h+var_168+4], edi
0x1401ac26b  lea     rdx, aDownstreamtran_44; "DownstreamTransport::RpcAsyncPipeDownlo"...
0x1401ac272  mov     [rbp+0C0h+var_140], edi
0x1401ac275  lea     r8, aDown; "DOWN"
0x1401ac27c  test    rcx, rcx
0x1401ac27f  jz      short loc_1401AC2C9
0x1401ac281  cmp     [rcx+40h], edi
0x1401ac284  jz      short loc_1401AC2C9
0x1401ac286  cmp     dword ptr [rcx+38h], 5
0x1401ac28a  jl      short loc_1401AC2C9
0x1401ac28c  mov     [rbp+0C0h+var_E0], rdx
0x1401ac290  lea     rcx, [rbp+0C0h+var_E0]
0x1401ac294  mov     [rbp+0C0h+var_D0], r8
0x1401ac298  lea     rdx, aRpcasyncstateP; "rpcAsyncState:%p"
0x1401ac29f  lea     r8, [rbp+0C0h+var_F8]
0x1401ac2a3  mov     [rbp+0C0h+var_D8], 17B3h
0x1401ac2aa  mov     [rbp+0C0h+var_D4], 5
0x1401ac2b1  mov     [rbp+0C0h+var_F8], rsi
0x1401ac2b5  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x1401ac2ba  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ac2c1  mov     r10, [rbp+0C0h+var_100]
0x1401ac2c5  mov     r11, [rbp+0C0h+var_130]
0x1401ac2c9  lea     rax, [r10+18h]
0x1401ac2cd  mov     [rbp+0C0h+var_128], rax
0x1401ac2d1  mov     r13, rax
0x1401ac2d4  test    r15, r15
0x1401ac2d7  jnz     loc_1401AC660
0x1401ac2dd  mov     r13, rax
0x1401ac2e0  cmp     ebx, 2
0x1401ac2e3  jnz     loc_1401AC660
0x1401ac2e9  mov     rax, [rbp+0C0h+arg_30]
0x1401ac2f0  mov     eax, [rax]
0x1401ac2f2  test    eax, eax
0x1401ac2f4  jnz     loc_1401AC5F5
0x1401ac2fa  mov     r8d, [rbp+0C0h+arg_20]
0x1401ac301  lea     r13, [r10+18h]
0x1401ac305  mov     rcx, [r13+0]
0x1401ac309  lea     r9, [rsp+1C0h+var_168]
0x1401ac30e  mov     rax, [r10]
0x1401ac311  mov     rdx, r11
0x1401ac314  mov     dword ptr [rsp+1C0h+var_168], edi
0x1401ac318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ac31d  mov     r14d, eax
0x1401ac320  test    eax, eax
0x1401ac322  jz      loc_1401AC52B
0x1401ac328  cmp     eax, 3E5h
0x1401ac32d  jz      short loc_1401AC374
0x1401ac32f  call    cs:__imp_GetCurrentThreadId
0x1401ac336  nop     dword ptr [rax+rax+00h]
0x1401ac33b  cmp     r14d, 4D5h
0x1401ac342  mov     [rsp+1C0h+var_188], rdi
0x1401ac347  mov     edx, edi
0x1401ac349  mov     dword ptr [rsp+1C0h+var_198], eax
0x1401ac34d  setz    dl
0x1401ac350  mov     dword ptr [rsp+1C0h+var_1A0], 181Dh
0x1401ac358  lea     r9, aDownstreamtran_1; "DownstreamTransport::RpcAsyncPipeDownlo"...
0x1401ac35f  mov     ecx, r14d
0x1401ac362  call    LogTranslatedRemoteError
0x1401ac367  mov     r15, rax
0x1401ac36a  mov     ebx, 0Ah
0x1401ac36f  jmp     loc_1401AC540
0x1401ac374  mov     ebx, 3
0x1401ac379  mov     dword ptr [rsp+1C0h+var_168+4], edi
0x1401ac37d  cmp     ebx, 3
0x1401ac380  jnz     loc_1401AC522
0x1401ac386  mov     rax, [rbp+0C0h+arg_30]
0x1401ac38d  mov     eax, [rax]
0x1401ac38f  test    eax, eax
0x1401ac391  jnz     loc_1401AC4D2
0x1401ac397  mov     rcx, [rsi+30h]; hHandle
0x1401ac39b  mov     edx, 3E8h; dwMilliseconds
0x1401ac3a0  call    cs:__imp_WaitForSingleObject
0x1401ac3a7  nop     dword ptr [rax+rax+00h]
0x1401ac3ac  mov     r12d, eax
0x1401ac3af  test    eax, eax
0x1401ac3b1  jz      short loc_1401AC40E
0x1401ac3b3  cmp     eax, 102h
0x1401ac3b8  jz      short loc_1401AC408
0x1401ac3ba  mov     ebx, 6
0x1401ac3bf  call    cs:__imp_GetCurrentThreadId
0x1401ac3c6  nop     dword ptr [rax+rax+00h]
0x1401ac3cb  mov     [rsp+1C0h+var_180], rdi
0x1401ac3d0  lea     r9d, [rbx-5]
0x1401ac3d4  mov     dword ptr [rsp+1C0h+var_188], eax
0x1401ac3d8  xor     r8d, r8d
0x1401ac3db  lea     rax, aDownstreamtran_1; "DownstreamTransport::RpcAsyncPipeDownlo"...
0x1401ac3e2  mov     [rsp+1C0h+var_190], 180Ah
0x1401ac3ea  mov     [rsp+1C0h+var_198], rax
0x1401ac3ef  mov     edx, r12d
0x1401ac3f2  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401ac3f9  mov     [rsp+1C0h+var_1A0], rax
0x1401ac3fe  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401ac403  mov     r15, rax
0x1401ac406  jmp     short loc_1401AC429
0x1401ac408  inc     dword ptr [rsp+1C0h+var_168+4]
0x1401ac40c  jmp     short loc_1401AC429
0x1401ac40e  mov     ecx, [rsi+28h]
0x1401ac411  test    ecx, ecx
0x1401ac413  jz      short loc_1401AC424
0x1401ac415  sub     ecx, 1
0x1401ac418  jz      short loc_1401AC429
0x1401ac41a  cmp     ecx, 1
0x1401ac41d  jnz     short loc_1401AC429
0x1401ac41f  lea     ebx, [rcx+1]
0x1401ac422  jmp     short loc_1401AC429
0x1401ac424  mov     ebx, 9
0x1401ac429  lea     rcx, ?AsyncRpcDownloadMaxWaitInSeconds@Settings@@3VCAsyncRpcDownloadMaxWaitInSeconds@1@A; Settings::CAsyncRpcDownloadMaxWaitInSeconds Settings::AsyncRpcDownloadMaxWaitInSeconds
0x1401ac430  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x1401ac435  cmp     dword ptr [rsp+1C0h+var_168+4], eax
0x1401ac439  jb      loc_1401AC37D
0x1401ac43f  mov     edx, 1811h; unsigned int
0x1401ac444  lea     rcx, [rbp+0C0h+var_80]; this
0x1401ac448  mov     r8d, 0Ah; int
0x1401ac44e  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x1401ac453  mov     r8, rax
0x1401ac456  lea     rdx, aBaseFsRemotefs_26; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401ac45d  mov     ecx, 0C00003F3h
0x1401ac462  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum2@@PEBG1@Z; FrsEvent::Log(FrsEventsEnum2,ushort const *,ushort const *)
0x1401ac467  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ac46e  test    rcx, rcx
0x1401ac471  jz      short loc_1401AC4C1
0x1401ac473  cmp     [rcx+40h], edi
0x1401ac476  jz      short loc_1401AC4C1
0x1401ac478  cmp     dword ptr [rcx+38h], 2
0x1401ac47c  jl      short loc_1401AC4C1
0x1401ac47e  lea     rax, aDownstreamtran_44; "DownstreamTransport::RpcAsyncPipeDownlo"...
0x1401ac485  mov     [rbp+0C0h+var_C0], 1812h
0x1401ac48c  mov     [rbp+0C0h+var_C8], rax
0x1401ac490  lea     r8, [rbp+0C0h+var_F0]
0x1401ac494  lea     rax, aDown; "DOWN"
0x1401ac49b  mov     [rbp+0C0h+var_BC], 2
0x1401ac4a2  mov     [rbp+0C0h+var_B8], rax
0x1401ac4a6  lea     rdx, aRpcAsyncPipeEv; "RPC Async pipe event not received on ti"...
0x1401ac4ad  mov     [rbp+0C0h+var_F0], rsi
0x1401ac4b1  lea     rcx, [rbp+0C0h+var_C8]
0x1401ac4b5  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x1401ac4ba  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ac4c1  mov     r14d, edi
0x1401ac4c4  mov     ebx, 6
0x1401ac4c9  mov     r12, [rbp+0C0h+var_108]
0x1401ac4cd  jmp     loc_1401AC5E4
0x1401ac4d2  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ac4d9  test    rcx, rcx
0x1401ac4dc  jz      short loc_1401AC4C1
0x1401ac4de  cmp     [rcx+40h], edi
0x1401ac4e1  jz      short loc_1401AC4C1
0x1401ac4e3  cmp     dword ptr [rcx+38h], 5
0x1401ac4e7  jl      short loc_1401AC4C1
0x1401ac4e9  lea     rax, aDownstreamtran_44; "DownstreamTransport::RpcAsyncPipeDownlo"...
0x1401ac4f0  mov     [rbp+0C0h+var_A8], 17EAh
0x1401ac4f7  mov     [rbp+0C0h+var_B0], rax
0x1401ac4fb  lea     r8, [rbp+0C0h+var_E8]
0x1401ac4ff  lea     rax, aDown; "DOWN"
0x1401ac506  mov     [rbp+0C0h+var_A4], 5
0x1401ac50d  mov     [rbp+0C0h+var_A0], rax
0x1401ac511  lea     rdx, aCancelAfterPul; "cancel after pull rpcAsyncState:%p"
0x1401ac518  mov     [rbp+0C0h+var_E8], rsi
0x1401ac51c  lea     rcx, [rbp+0C0h+var_B0]
0x1401ac520  jmp     short loc_1401AC4B5
0x1401ac522  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ac529  jmp     short loc_1401AC4C9
0x1401ac52b  mov     r8d, dword ptr [rsp+1C0h+var_168]
0x1401ac530  test    r8d, r8d
0x1401ac533  jnz     short loc_1401AC54C
0x1401ac535  mov     [rbp+0C0h+var_140], 1
0x1401ac53c  lea     ebx, [r8+5]
0x1401ac540  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ac547  jmp     loc_1401AC5E4
0x1401ac54c  mov     rdx, [rbp+0C0h+var_130]
0x1401ac550  mov     rcx, [rbp+0C0h+var_138]
0x1401ac554  call    WriteBack
0x1401ac559  mov     r15, rax
0x1401ac55c  test    rax, rax
0x1401ac55f  jnz     short loc_1401AC580
0x1401ac561  mov     r8d, dword ptr [rsp+1C0h+var_168]; unsigned __int64
0x1401ac566  lea     rcx, [r12+0B0h]; this
0x1401ac56e  xor     r9d, r9d; int
0x1401ac571  xor     edx, edx; unsigned __int64
0x1401ac573  call    ?ThrottleBytes@BandwidthThrottler@@QEAAPEAVFrsStatus@@_K0H@Z; BandwidthThrottler::ThrottleBytes(unsigned __int64,unsigned __int64,int)
0x1401ac578  mov     r15, rax
0x1401ac57b  test    rax, rax
0x1401ac57e  jz      short loc_1401AC5D8
0x1401ac580  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ac587  test    rcx, rcx
0x1401ac58a  jz      short loc_1401AC5DF
0x1401ac58c  cmp     [rcx+40h], edi
0x1401ac58f  jz      short loc_1401AC5DF
0x1401ac591  cmp     dword ptr [rcx+38h], 3
0x1401ac595  jl      short loc_1401AC5DF
0x1401ac597  lea     rax, aDownstreamtran_44; "DownstreamTransport::RpcAsyncPipeDownlo"...
0x1401ac59e  mov     [rbp+0C0h+var_90], 17DBh
0x1401ac5a5  mov     [rbp+0C0h+var_98], rax
0x1401ac5a9  lea     r8, [rsp+1C0h+var_170]
0x1401ac5ae  lea     rax, aDown; "DOWN"
0x1401ac5b5  mov     [rbp+0C0h+var_8C], 3
0x1401ac5bc  mov     r9, r15
0x1401ac5bf  mov     [rbp+0C0h+var_88], rax
0x1401ac5c3  lea     rdx, aAbortingTransf; "Aborting transfer. rpcAsyncState:%p Err"...
0x1401ac5ca  mov     [rsp+1C0h+var_170], rsi
0x1401ac5cf  lea     rcx, [rbp+0C0h+var_98]
0x1401ac5d3  call    ??$DbgPrint@G_KVFrsStatus@@@dbgobj@@QEAA_KPEBGAEB_KAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,unsigned __int64,FrsStatus>(ushort const *,unsigned __int64 const &,FrsStatus const &)
0x1401ac5d8  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ac5df  mov     ebx, 2
0x1401ac5e4  mov     rax, [rbp+0C0h+var_128]
0x1401ac5e8  mov     r10, [rbp+0C0h+var_100]
0x1401ac5ec  mov     r11, [rbp+0C0h+var_130]
0x1401ac5f0  jmp     loc_1401AC2D4
0x1401ac5f5  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ac5fc  lea     rbx, aDownstreamtran_44; "DownstreamTransport::RpcAsyncPipeDownlo"...
0x1401ac603  lea     r14, aDown; "DOWN"
0x1401ac60a  test    rcx, rcx
0x1401ac60d  jz      loc_1401AC837
0x1401ac613  cmp     [rcx+40h], edi
0x1401ac616  jz      loc_1401AC7F4
0x1401ac61c  cmp     dword ptr [rcx+38h], 5
0x1401ac620  jl      loc_1401AC7F4
0x1401ac626  lea     r8, [rbp+0C0h+var_138]
0x1401ac62a  mov     [rbp+0C0h+var_120], rbx
0x1401ac62e  lea     rdx, aCancelBeforePu; "Cancel before pull following shutdown. "...
0x1401ac635  mov     [rbp+0C0h+var_118], 17B8h
0x1401ac63c  lea     rcx, [rbp+0C0h+var_120]
0x1401ac640  mov     [rbp+0C0h+var_114], 5
0x1401ac647  mov     [rbp+0C0h+var_110], r14
0x1401ac64b  mov     [rbp+0C0h+var_138], rsi
0x1401ac64f  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x1401ac654  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ac65b  jmp     loc_1401AC7F4
0x1401ac660  sub     ebx, 2
0x1401ac663  jz      loc_1401AC7E6
0x1401ac669  sub     ebx, 1
0x1401ac66c  jz      short loc_1401AC6A1
0x1401ac66e  sub     ebx, 1
0x1401ac671  jz      loc_1401AC7E6
0x1401ac677  sub     ebx, 1
0x1401ac67a  jz      loc_1401AC852
0x1401ac680  sub     ebx, 1
0x1401ac683  jz      short loc_1401AC6A1
0x1401ac685  sub     ebx, 1
0x1401ac688  jz      short loc_1401AC706
0x1401ac68a  sub     ebx, 1
0x1401ac68d  jz      loc_1401AC7C2
0x1401ac693  cmp     ebx, 1
0x1401ac696  jz      loc_1401AC91A
0x1401ac69c  jmp     loc_1401AC931
0x1401ac6a1  test    rcx, rcx
0x1401ac6a4  jz      short loc_1401AC6EF
0x1401ac6a6  cmp     [rcx+40h], edi
0x1401ac6a9  jz      short loc_1401AC6EF
0x1401ac6ab  cmp     dword ptr [rcx+38h], 5
0x1401ac6af  jl      short loc_1401AC6EF
0x1401ac6b1  lea     rax, aDownstreamtran_44; "DownstreamTransport::RpcAsyncPipeDownlo"...
0x1401ac6b8  mov     [rbp+0C0h+var_118], 183Fh
0x1401ac6bf  mov     [rbp+0C0h+var_120], rax
0x1401ac6c3  lea     r8, [rsp+1C0h+var_170]
0x1401ac6c8  lea     rax, aDown; "DOWN"
0x1401ac6cf  mov     [rbp+0C0h+var_114], 5
0x1401ac6d6  lea     rdx, aWaitForPullCan; "Wait for pull/cancel after pull rpcAsyn"...
0x1401ac6dd  mov     [rbp+0C0h+var_110], rax
0x1401ac6e1  lea     rcx, [rbp+0C0h+var_120]
0x1401ac6e5  mov     [rsp+1C0h+var_170], rsi
0x1401ac6ea  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x1401ac6ef  mov     edx, 1; fAbort
0x1401ac6f4  mov     rcx, rsi; pAsync
0x1401ac6f7  call    cs:__imp_RpcAsyncCancelCall
0x1401ac6fe  nop     dword ptr [rax+rax+00h]
0x1401ac703  mov     r14d, eax
0x1401ac706  lea     rcx, ?AsyncRpcDownloadMaxWaitInSeconds@Settings@@3VCAsyncRpcDownloadMaxWaitInSeconds@1@A; Settings::CAsyncRpcDownloadMaxWaitInSeconds Settings::AsyncRpcDownloadMaxWaitInSeconds
0x1401ac70d  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x1401ac712  mov     rcx, [rsi+30h]; hHandle
0x1401ac716  imul    edx, eax, 3E8h; dwMilliseconds
0x1401ac71c  call    cs:__imp_WaitForSingleObject
  ... truncated ...
```
