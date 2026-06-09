# AsyncUnbufferedFileReader::GetNextReadBuffer(void)

- ea: `0x1400aaf34`
- end: `0x1400abe2f`
- name: `?GetNextReadBuffer@AsyncUnbufferedFileReader@@AEAAPEAVFrsStatus@@XZ`
- size: `3835`
- prototype: `struct FrsStatus *__fastcall(AsyncUnbufferedFileReader *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400ad380`

## callees

- `0x1400a88e8`
- `0x1400a8a40`
- `0x1400a8b84`
- `0x1400a8cd4`
- `0x1400a8e18`
- `0x1400aaf34`
- `0x1401b9494`
- `0x1401bda10`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x1400ab221`
- `KERNEL32!GetOverlappedResult` at `0x1400ab915`
- `KERNEL32!GetOverlappedResult` at `0x1400ab221`
- `KERNEL32!GetOverlappedResult` at `0x1400ab915`
- `KERNEL32!ReadFile` at `0x1400ab5bd`
- `KERNEL32!ReadFile` at `0x1400ab5bd`
- `KERNEL32!GetLastError` at `0x1400ab394`
- `KERNEL32!GetLastError` at `0x1400ab5d1`
- `KERNEL32!GetLastError` at `0x1400ab394`
- `KERNEL32!GetLastError` at `0x1400ab5d1`
- `KERNEL32!GetCurrentThreadId` at `0x1400ab334`
- `KERNEL32!GetCurrentThreadId` at `0x1400ab3b7`
- `KERNEL32!GetCurrentThreadId` at `0x1400ab5f4`
- `KERNEL32!GetCurrentThreadId` at `0x1400abdc8`
- `KERNEL32!GetCurrentThreadId` at `0x1400ab334`
- `KERNEL32!GetCurrentThreadId` at `0x1400ab3b7`
- `KERNEL32!GetCurrentThreadId` at `0x1400ab5f4`
- `KERNEL32!GetCurrentThreadId` at `0x1400abdc8`

## string_xrefs

- `0x1400aaffa`: `this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? `
- `0x1400ab0bf`: `this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? `
- `0x1400ab1d3`: `Calling GetOverlappedResult(). overlapped:%p wait:%? this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? `
- `0x1400aaf71`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400ab0f8`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400ab501`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400ab6a5`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400ab764`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400ab853`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400aba11`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400abb05`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400abbe9`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400abca1`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400abce4`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400abd8f`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400ab352`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400ab3d5`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400ab612`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400abde8`: `AsyncUnbufferedFileReader::GetNextReadBuffer`
- `0x1400ab2ec`: `GetOverlappedResult() returned success. overlapped:%p wait:%? bytesRead:%? this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? `
- `0x1400ab7d2`: `GetOverlappedResult() returned ERROR_IO_INCOMPLETE. overlapped:%p wait:%? this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? `
- `0x1400ab8b5`: `GetOverlappedResult() returned ERROR_HANDLE_EOF. overlapped:%p wait:%? bytesRead:%? this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? `
- `0x1400aba72`: `ReadFile() returned ERROR_IO_PENDING. overlapped:%p bytesToRead:%? this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? `
- `0x1400ab562`: `Calling ReadFile(). overlapped:%p bytesToRead:%? this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? `
- `0x1400abb66`: `ReadFile() returned ERROR_HANDLE_EOF. overlapped:%p bytesToRead:%? this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? `
- `0x1400abd6d`: `Reached EOF. this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? `
- `0x1400ab70a`: `Adding I/O in queue. this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? `

## pseudocode

```c
struct FrsStatus *__fastcall AsyncUnbufferedFileReader::GetNextReadBuffer(AsyncUnbufferedFileReader *this)
{
  __int64 v1; // rsi
  int v3; // eax
  __int64 v5; // rcx
  unsigned int v6; // eax
  unsigned int *v7; // r15
  _DWORD *v8; // r14
  _DWORD *v9; // r12
  unsigned int *v10; // r15
  unsigned int v11; // eax
  unsigned int v12; // edx
  DWORD v13; // eax
  __int64 v14; // rcx
  int v15; // r13d
  DWORD LastError; // eax
  DWORD v17; // r14d
  DWORD v18; // eax
  __int64 v19; // rcx
  unsigned int v20; // r14d
  unsigned int v21; // r13d
  __int64 v22; // r12
  char *v23; // rax
  _QWORD *v24; // r15
  _DWORD *v25; // rbx
  unsigned int *v26; // r14
  __int64 v27; // rax
  unsigned __int64 v28; // r8
  DWORD v29; // eax
  DWORD v30; // r14d
  DWORD v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rdx
  bool v34; // zf
  __int64 v35; // rcx
  unsigned int v36; // eax
  DWORD CurrentThreadId; // eax
  __int64 v38; // rcx
  BOOL bWait; // [rsp+70h] [rbp-19h] BYREF
  __int64 v40; // [rsp+78h] [rbp-11h]
  AsyncUnbufferedFileReader *v41; // [rsp+80h] [rbp-9h] BYREF
  AsyncUnbufferedFileReader *v42; // [rsp+88h] [rbp-1h] BYREF
  const wchar_t *v43; // [rsp+90h] [rbp+7h] BYREF
  int v44; // [rsp+98h] [rbp+Fh]
  int v45; // [rsp+9Ch] [rbp+13h]
  const wchar_t *v46; // [rsp+A0h] [rbp+17h]
  AsyncUnbufferedFileReader *v47; // [rsp+F8h] [rbp+6Fh] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+100h] [rbp+77h] BYREF
  DWORD nNumberOfBytesToRead; // [rsp+108h] [rbp+7Fh] BYREF

  v1 = 0;
  v40 = 0;
  NumberOfBytesTransferred = 0;
  nNumberOfBytesToRead = 0;
  LODWORD(v47) = 0;
  bWait = 0;
  if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugAsyncIo)
    && g_DebugLog
    && LODWORD(g_DebugLog[1].LockSemaphore)
    && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v43 = L"AsyncUnbufferedFileReader::GetNextReadBuffer";
    v44 = 2076;
    v45 = 5;
    v46 = L"ASYN";
    v41 = this;
    dbgobj::DbgPrint<unsigned short,unsigned __int64,enum AsyncUnbufferedFileReader::State,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,int>(
      (unsigned int)&v43,
      (unsigned int)L"this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? cur"
                     "rentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? ",
      (unsigned int)&v41,
      (_DWORD)this + 144,
      (__int64)this + 96,
      (__int64)this + 100,
      (__int64)this + 104,
      (__int64)this + 108,
      (__int64)this + 88,
      (__int64)this + 92,
      (__int64)this + 160);
  }
  if ( *((_QWORD *)this + 2) )
  {
    v3 = *((_DWORD *)this + 23);
    if ( !v3 )
      return 0;
    v5 = *((unsigned int *)this + 24);
    *((_DWORD *)this + 23) = v3 - 1;
    *(_DWORD *)(*((_QWORD *)this + 19) + 4 * v5) = 0;
    v6 = *((_DWORD *)this + 24) + 1;
    *((_DWORD *)this + 27) = 0;
    *((_DWORD *)this + 24) = v6 % *((_DWORD *)this + 15);
    if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugAsyncIo)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v43 = L"AsyncUnbufferedFileReader::GetNextReadBuffer";
      v44 = 2097;
      v45 = 5;
      v46 = L"ASYN";
      v41 = this;
      dbgobj::DbgPrint<unsigned short,unsigned __int64,enum AsyncUnbufferedFileReader::State,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,int>(
        (unsigned int)&v43,
        (unsigned int)L"this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? c"
                       "urrentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? ",
        (unsigned int)&v41,
        (_DWORD)this + 144,
        (__int64)this + 96,
        (__int64)this + 100,
        (__int64)this + 104,
        (__int64)this + 108,
        (__int64)this + 88,
        (__int64)this + 92,
        (__int64)this + 160);
    }
  }
  v7 = 0;
  while ( 2 )
  {
    while ( 2 )
    {
      if ( v7 )
      {
        CurrentThreadId = GetCurrentThreadId();
        return (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v38,
                                     v7[1],
                                     v7[2],
                                     *v7,
                                     "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                                     "AsyncUnbufferedFileReader::GetNextReadBuffer",
                                     2372,
                                     CurrentThreadId,
                                     v7);
      }
      v8 = (_DWORD *)((char *)this + 60);
      while ( 1 )
      {
        if ( v7 )
          goto LABEL_36;
        v9 = (_DWORD *)((char *)this + 88);
        if ( !*((_DWORD *)this + 22) )
          goto LABEL_81;
        NumberOfBytesTransferred = 0;
        bWait = *((_DWORD *)this + 23) == 0;
        if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugAsyncIo)
          && g_DebugLog
          && LODWORD(g_DebugLog[1].LockSemaphore)
          && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v43 = L"AsyncUnbufferedFileReader::GetNextReadBuffer";
          v44 = 2117;
          v46 = L"ASYN";
          v42 = (AsyncUnbufferedFileReader *)(*((_QWORD *)this + 10) + 32LL * *((unsigned int *)this + 25));
          v45 = 5;
          v41 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64,int,unsigned __int64,enum AsyncUnbufferedFileReader::State,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,int>(
            (unsigned int)&v43,
            (unsigned int)L"Calling GetOverlappedResult(). overlapped:%p wait:%? this:%p state:%? currentCacheBufferIndex:"
                           "%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? nu"
                           "mIoBuffers:%? asyncEof:%? ",
            (unsigned int)&v42,
            (unsigned int)&bWait,
            (__int64)&v41,
            (__int64)this + 144,
            (__int64)this + 96,
            (__int64)this + 100,
            (__int64)this + 104,
            (__int64)this + 108,
            (__int64)this + 88,
            (__int64)this + 92,
            (__int64)this + 160);
        }
        v10 = (unsigned int *)((char *)this + 100);
        if ( !GetOverlappedResult(
                *((HANDLE *)this + 4),
                (LPOVERLAPPED)(*((_QWORD *)this + 10) + 32LL * *((unsigned int *)this + 25)),
                &NumberOfBytesTransferred,
                bWait) )
          break;
        v8 = (_DWORD *)((char *)this + 60);
        *(_DWORD *)(*((_QWORD *)this + 19) + 4LL * *v10) = NumberOfBytesTransferred;
        v11 = *v10;
        --*v9;
        v12 = (v11 + 1) % *((_DWORD *)this + 15);
        ++*((_DWORD *)this + 23);
        *v10 = v12;
        if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugAsyncIo)
          && g_DebugLog
          && LODWORD(g_DebugLog[1].LockSemaphore)
          && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v43 = L"AsyncUnbufferedFileReader::GetNextReadBuffer";
          v46 = L"ASYN";
          v41 = (AsyncUnbufferedFileReader *)(*((_QWORD *)this + 10) + 32LL * *v10);
          v44 = 2134;
          v45 = 5;
          v42 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64,int,unsigned long,unsigned __int64,enum AsyncUnbufferedFileReader::State,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,int>(
            (unsigned int)&v43,
            (unsigned int)L"GetOverlappedResult() returned success. overlapped:%p wait:%? bytesRead:%? this:%p state:%? cu"
                           "rrentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSi"
                           "ze:%? queueDepth:%? numIoBuffers:%? asyncEof:%? ",
            (unsigned int)&v41,
            (unsigned int)&bWait,
            (__int64)&NumberOfBytesTransferred,
            (__int64)&v42,
            (__int64)this + 144,
            (__int64)this + 96,
            (__int64)this + 100,
            (__int64)this + 104,
            (__int64)this + 108,
            (__int64)this + 88,
            (__int64)this + 92,
            (__int64)this + 160);
        }
        if ( NumberOfBytesTransferred )
        {
          v7 = (unsigned int *)v40;
        }
        else
        {
          v13 = GetCurrentThreadId();
          v7 = (unsigned int *)FrsStatusList::PushNewError(
                                 v14,
                                 995,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                                 "AsyncUnbufferedFileReader::GetNextReadBuffer",
                                 2147,
                                 v13,
                                 0);
          v40 = (__int64)v7;
        }
      }
      v15 = 0;
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError == 38 )
      {
        *((_DWORD *)this + 40) = 1;
        if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugAsyncIo)
          && g_DebugLog
          && LODWORD(g_DebugLog[1].LockSemaphore)
          && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v43 = L"AsyncUnbufferedFileReader::GetNextReadBuffer";
          v46 = L"ASYN";
          v42 = (AsyncUnbufferedFileReader *)(*((_QWORD *)this + 10) + 32LL * *v10);
          v44 = 2162;
          v45 = 5;
          v47 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64,int,unsigned long,unsigned __int64,enum AsyncUnbufferedFileReader::State,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,int>(
            (unsigned int)&v43,
            (unsigned int)L"GetOverlappedResult() returned ERROR_HANDLE_EOF. overlapped:%p wait:%? bytesRead:%? this:%p st"
                           "ate:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? curren"
                           "tBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? ",
            (unsigned int)&v42,
            (unsigned int)&bWait,
            (__int64)&NumberOfBytesTransferred,
            (__int64)&v47,
            (__int64)this + 144,
            (__int64)this + 96,
            (__int64)this + 100,
            (__int64)this + 104,
            (__int64)this + 108,
            (__int64)this + 88,
            (__int64)this + 92,
            (__int64)this + 160);
        }
        v8 = (_DWORD *)((char *)this + 60);
        if ( !*v9 )
          goto LABEL_80;
        v33 = *v10;
        do
        {
          LODWORD(v47) = 0;
          if ( v15 )
            GetOverlappedResult(
              *((HANDLE *)this + 4),
              (LPOVERLAPPED)(*((_QWORD *)this + 10) + 32 * v33),
              (LPDWORD)&v47,
              1);
          HIDWORD(v33) = 0;
          v15 = 1;
          *(_DWORD *)(*((_QWORD *)this + 19) + 4LL * *v10) = 0;
          LODWORD(v33) = (*v10 + 1) % *((_DWORD *)this + 15);
          v34 = (*v9)-- == 1;
          *v10 = v33;
        }
        while ( !v34 );
      }
      else
      {
        if ( LastError != 996 )
        {
          v18 = GetCurrentThreadId();
          v40 = FrsStatusList::PushNewError(
                  v19,
                  v17,
                  0,
                  1,
                  "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                  "AsyncUnbufferedFileReader::GetNextReadBuffer",
                  2207,
                  v18,
                  0);
          v7 = (unsigned int *)v40;
          v8 = (_DWORD *)((char *)this + 60);
          if ( v40 )
          {
LABEL_36:
            v20 = (unsigned int)v47;
            goto LABEL_37;
          }
          goto LABEL_81;
        }
        if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugAsyncIo)
          && g_DebugLog
          && LODWORD(g_DebugLog[1].LockSemaphore)
          && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v44 = 2197;
          v43 = L"AsyncUnbufferedFileReader::GetNextReadBuffer";
          v45 = 5;
          v46 = L"ASYN";
          v42 = (AsyncUnbufferedFileReader *)(*((_QWORD *)this + 10) + 32LL * *v10);
          v47 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64,int,unsigned __int64,enum AsyncUnbufferedFileReader::State,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,int>(
            (unsigned int)&v43,
            (unsigned int)L"GetOverlappedResult() returned ERROR_IO_INCOMPLETE. overlapped:%p wait:%? this:%p state:%? cur"
                           "rentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSiz"
                           "e:%? queueDepth:%? numIoBuffers:%? asyncEof:%? ",
            (unsigned int)&v42,
            (unsigned int)&bWait,
            (__int64)&v47,
            (__int64)this + 144,
            (__int64)this + 96,
            (__int64)this + 100,
            (__int64)this + 104,
            (__int64)this + 108,
            (__int64)this + 88,
            (__int64)this + 92,
            (__int64)this + 160);
        }
        ++*((_DWORD *)this + 33);
      }
      v8 = (_DWORD *)((char *)this + 60);
LABEL_80:
      v7 = (unsigned int *)v40;
LABEL_81:
      if ( *((_DWORD *)this + 40) )
      {
        v20 = 0;
        LODWORD(v47) = 0;
        v21 = 0;
        break;
      }
      if ( *((_QWORD *)this + 2) > (unsigned __int64)(unsigned int)(*v8 * *((_DWORD *)this + 16)) && !*v9 )
        ++*((_DWORD *)this + 30);
      v20 = *v8 - *((_DWORD *)this + 23) - *v9;
      v35 = *((_QWORD *)this + 24);
      LODWORD(v47) = v20;
      if ( v35 && v20 >= (unsigned __int64)(v35 - *((_QWORD *)this + 25)) )
      {
        v20 = *((_DWORD *)this + 48) - *((_DWORD *)this + 50);
        LODWORD(v47) = v20;
      }
LABEL_37:
      v21 = 0;
      if ( v7 )
        continue;
      break;
    }
    v22 = v40;
    v23 = (char *)this + 192;
    v24 = (_QWORD *)((char *)this + 192);
    v25 = (_DWORD *)((char *)this + 160);
    while ( !*v25 )
    {
      v24 = v23;
      if ( v21 >= v20 )
        break;
      v26 = (unsigned int *)((char *)this + 104);
      v24 = (_QWORD *)((char *)this + 192);
      *(_QWORD *)(32LL * *((unsigned int *)this + 26) + *((_QWORD *)this + 10) + 16) = *((_QWORD *)this + 14);
      v27 = *((_QWORD *)this + 24);
      v28 = *((unsigned int *)this + 16);
      nNumberOfBytesToRead = *((_DWORD *)this + 16);
      if ( v27
        && *((_QWORD *)this + 25) == v27 - 1
        && v28 >= *((_QWORD *)this + 22) + *((_QWORD *)this + 21) - *((_QWORD *)this + 14) )
      {
        nNumberOfBytesToRead = *((_DWORD *)this + 44) + *((_DWORD *)this + 42) - *((_DWORD *)this + 28);
      }
      if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugAsyncIo)
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v43 = L"AsyncUnbufferedFileReader::GetNextReadBuffer";
        v46 = L"ASYN";
        v41 = (AsyncUnbufferedFileReader *)(*((_QWORD *)this + 10) + 32LL * *v26);
        v44 = 2277;
        v45 = 5;
        v42 = this;
        dbgobj::DbgPrint<unsigned short,unsigned __int64,unsigned long,unsigned __int64,enum AsyncUnbufferedFileReader::State,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,int>(
          (unsigned int)&v43,
          (unsigned int)L"Calling ReadFile(). overlapped:%p bytesToRead:%? this:%p state:%? currentCacheBufferIndex:%? cur"
                         "rentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffe"
                         "rs:%? asyncEof:%? ",
          (unsigned int)&v41,
          (unsigned int)&nNumberOfBytesToRead,
          (__int64)&v42,
          (__int64)this + 144,
          (__int64)this + 96,
          (__int64)this + 100,
          (__int64)this + 104,
          (__int64)this + 108,
          (__int64)this + 88,
          (__int64)this + 92,
          (__int64)this + 160);
      }
      if ( ReadFile(
             *((HANDLE *)this + 4),
             *(LPVOID *)(*((_QWORD *)this + 9) + 8LL * *v26),
             nNumberOfBytesToRead,
             &NumberOfBytesTransferred,
             (LPOVERLAPPED)(*((_QWORD *)this + 10) + 32LL * *v26)) )
      {
        ++*((_DWORD *)this + 32);
        ++*((_QWORD *)this + 25);
        if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugAsyncIo)
          && g_DebugLog
          && LODWORD(g_DebugLog[1].LockSemaphore)
          && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v43 = L"AsyncUnbufferedFileReader::GetNextReadBuffer";
          v46 = L"ASYN";
          v41 = (AsyncUnbufferedFileReader *)(*((_QWORD *)this + 10) + 32LL * *v26);
          v44 = 2323;
          v45 = 5;
          v42 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64,unsigned long,unsigned long,unsigned __int64,enum AsyncUnbufferedFileReader::State,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,int>(
            (unsigned int)&v43,
            (_DWORD)this + 100,
            (unsigned int)&v41,
            (unsigned int)&nNumberOfBytesToRead,
            (__int64)&NumberOfBytesTransferred,
            (__int64)&v42,
            (__int64)this + 144,
            (__int64)this + 96,
            (__int64)this + 100,
            (__int64)this + 104,
            (__int64)this + 108,
            (__int64)this + 88,
            (__int64)this + 92,
            (__int64)this + 160);
        }
        goto LABEL_55;
      }
      v29 = GetLastError();
      v30 = v29;
      if ( v29 == 38 )
      {
        *v25 = 1;
        LODWORD(v47) = 0;
        if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugAsyncIo)
          && g_DebugLog
          && LODWORD(g_DebugLog[1].LockSemaphore) )
        {
          v26 = (unsigned int *)((char *)this + 104);
          if ( SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
          {
            v43 = L"AsyncUnbufferedFileReader::GetNextReadBuffer";
            v46 = L"ASYN";
            v41 = (AsyncUnbufferedFileReader *)(*((_QWORD *)this + 10) + 32LL * *v26);
            v44 = 2306;
            v45 = 5;
            v42 = this;
            dbgobj::DbgPrint<unsigned short,unsigned __int64,unsigned long,unsigned __int64,enum AsyncUnbufferedFileReader::State,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,int>(
              (unsigned int)&v43,
              (unsigned int)L"ReadFile() returned ERROR_HANDLE_EOF. overlapped:%p bytesToRead:%? this:%p state:%? currentC"
                             "acheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%"
                             "? queueDepth:%? numIoBuffers:%? asyncEof:%? ",
              (unsigned int)&v41,
              (unsigned int)&nNumberOfBytesToRead,
              (__int64)&v42,
              (__int64)this + 144,
              (__int64)this + 96,
              (__int64)this + 100,
              (__int64)this + 104,
              (__int64)this + 108,
              (__int64)this + 88,
              (__int64)this + 92,
              (__int64)this + 160);
          }
          goto LABEL_55;
        }
      }
      else
      {
        if ( v29 == 997 )
        {
          if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugAsyncIo)
            && g_DebugLog
            && LODWORD(g_DebugLog[1].LockSemaphore) )
          {
            v26 = (unsigned int *)((char *)this + 104);
            if ( SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
            {
              v43 = L"AsyncUnbufferedFileReader::GetNextReadBuffer";
              v46 = L"ASYN";
              v41 = (AsyncUnbufferedFileReader *)(*((_QWORD *)this + 10) + 32LL * *v26);
              v44 = 2292;
              v45 = 5;
              v42 = this;
              dbgobj::DbgPrint<unsigned short,unsigned __int64,unsigned long,unsigned __int64,enum AsyncUnbufferedFileReader::State,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,int>(
                (unsigned int)&v43,
                (unsigned int)L"ReadFile() returned ERROR_IO_PENDING. overlapped:%p bytesToRead:%? this:%p state:%? curren"
                               "tCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSi"
                               "ze:%? queueDepth:%? numIoBuffers:%? asyncEof:%? ",
                (unsigned int)&v41,
                (unsigned int)&nNumberOfBytesToRead,
                (__int64)&v42,
                (__int64)this + 144,
                (__int64)this + 96,
                (__int64)this + 100,
                (__int64)this + 104,
                (__int64)this + 108,
                (__int64)this + 88,
                (__int64)this + 92,
                (__int64)this + 160);
            }
          }
          else
          {
            v26 = (unsigned int *)((char *)this + 104);
          }
          ++*((_DWORD *)this + 31);
          ++*((_QWORD *)this + 25);
          goto LABEL_55;
        }
        v31 = GetCurrentThreadId();
        v22 = FrsStatusList::PushNewError(
                v32,
                v30,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                "AsyncUnbufferedFileReader::GetNextReadBuffer",
                2314,
                v31,
                0);
      }
      v26 = (unsigned int *)((char *)this + 104);
LABEL_55:
      if ( v22
        || *v25
        || (*((_QWORD *)this + 14) += nNumberOfBytesToRead,
            *v26 = (*v26 + 1) % *((_DWORD *)this + 15),
            ++*((_DWORD *)this + 22),
            !(unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugAsyncIo))
        || !g_DebugLog )
      {
        v20 = (unsigned int)v47;
        v23 = (char *)this + 192;
        ++v21;
        if ( v22 )
          break;
      }
      else
      {
        if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v43 = L"AsyncUnbufferedFileReader::GetNextReadBuffer";
          v46 = L"ASYN";
          v44 = 2337;
          v45 = 5;
          v42 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64,enum AsyncUnbufferedFileReader::State,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,int>(
            (unsigned int)&v43,
            (unsigned int)L"Adding I/O in queue. this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? "
                           "currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? ",
            (unsigned int)&v42,
            (_DWORD)this + 144,
            (__int64)this + 96,
            (__int64)this + 100,
            (__int64)this + 104,
            (__int64)this + 108,
            (__int64)this + 88,
            (__int64)this + 92,
            (__int64)this + 160);
        }
        v20 = (unsigned int)v47;
        v23 = (char *)this + 192;
        ++v21;
      }
    }
    v40 = v22;
    if ( v22 )
      goto LABEL_120;
    if ( !*v25 )
    {
      if ( *v24 )
      {
        if ( *((_QWORD *)this + 25) == *v24 )
        {
          *v25 = 1;
          if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugAsyncIo) )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
            {
              v46 = L"ASYN";
              v43 = L"AsyncUnbufferedFileReader::GetNextReadBuffer";
              v44 = 2350;
              v45 = 5;
              v42 = this;
              dbgobj::DbgPrint<unsigned short,unsigned __int64,enum AsyncUnbufferedFileReader::State,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,int>(
                (unsigned int)&v43,
                (unsigned int)L"Reached EOF. this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? curr"
                               "entIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? ",
                (unsigned int)&v42,
                (_DWORD)this + 144,
                (__int64)this + 96,
                (__int64)this + 100,
                (__int64)this + 104,
                (__int64)this + 108,
                (__int64)this + 88,
                (__int64)this + 92,
                (__int64)this + 160);
            }
          }
        }
      }
    }
    if ( !*((_DWORD *)this + 23) )
    {
      v7 = 0;
      if ( !*((_DWORD *)this + 22) )
      {
        if ( *v25 )
          return (struct FrsStatus *)v1;
LABEL_120:
        v7 = (unsigned int *)v22;
      }
      continue;
    }
    break;
  }
  v36 = *((_DWORD *)this + 34);
  if ( v36 <= *((_DWORD *)this + 24) )
    v36 = *((_DWORD *)this + 24);
  *((_DWORD *)this + 34) = v36;
  return (struct FrsStatus *)v1;
}

```

## disassembly

```asm
0x1400aaf34  mov     [rsp-8+arg_0], rbx
0x1400aaf39  push    rbp
0x1400aaf3a  push    rsi
0x1400aaf3b  push    rdi
0x1400aaf3c  push    r12
0x1400aaf3e  push    r13
0x1400aaf40  push    r14
0x1400aaf42  push    r15
0x1400aaf44  lea     rbp, [rsp-27h]
0x1400aaf49  sub     rsp, 0B0h
0x1400aaf50  xor     esi, esi
0x1400aaf52  mov     rdi, rcx
0x1400aaf55  lea     rcx, ?DebugAsyncIo@Settings@@3VCDebugAsyncIo@1@A; Settings::CDebugAsyncIo Settings::DebugAsyncIo
0x1400aaf5c  mov     [rbp+57h+var_68], rsi
0x1400aaf60  mov     [rbp+57h+NumberOfBytesTransferred], esi
0x1400aaf63  mov     [rbp+57h+nNumberOfBytesToRead], esi
0x1400aaf66  mov     dword ptr [rbp+57h+arg_8], esi
0x1400aaf69  mov     [rbp+57h+bWait], esi
0x1400aaf6c  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x1400aaf71  lea     r13, aAsyncunbuffere_25; "AsyncUnbufferedFileReader::GetNextReadB"...
0x1400aaf78  lea     r12, aAsyn; "ASYN"
0x1400aaf7f  test    eax, eax
0x1400aaf81  jz      loc_1400AB019
0x1400aaf87  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400aaf8e  test    rax, rax
0x1400aaf91  jz      loc_1400AB019
0x1400aaf97  cmp     [rax+40h], esi
0x1400aaf9a  jz      short loc_1400AB019
0x1400aaf9c  cmp     dword ptr [rax+38h], 5
0x1400aafa0  jl      short loc_1400AB019
0x1400aafa2  lea     rax, [rdi+0A0h]
0x1400aafa9  mov     [rbp+57h+var_50], r13
0x1400aafad  mov     [rsp+0E0h+var_90], rax
0x1400aafb2  lea     rcx, [rdi+5Ch]
0x1400aafb6  mov     [rsp+0E0h+var_98], rcx
0x1400aafbb  lea     rdx, [rdi+58h]
0x1400aafbf  mov     [rsp+0E0h+var_A0], rdx
0x1400aafc4  lea     r8, [rdi+6Ch]
0x1400aafc8  mov     [rsp+0E0h+var_A8], r8
0x1400aafcd  lea     r10, [rdi+68h]
0x1400aafd1  mov     [rsp+0E0h+var_B0], r10
0x1400aafd6  lea     r11, [rdi+64h]
0x1400aafda  mov     [rsp+0E0h+var_B8], r11
0x1400aafdf  lea     rbx, [rdi+60h]
0x1400aafe3  lea     r9, [rdi+90h]
0x1400aafea  mov     [rsp+0E0h+lpOverlapped], rbx
0x1400aafef  lea     r8, [rbp+57h+var_60]
0x1400aaff3  mov     [rbp+57h+var_48], 81Ch
0x1400aaffa  lea     rdx, aThisPStateCurr_0; "this:%p state:%? currentCacheBufferInde"...
0x1400ab001  mov     [rbp+57h+var_44], 5
0x1400ab008  lea     rcx, [rbp+57h+var_50]
0x1400ab00c  mov     [rbp+57h+var_40], r12
0x1400ab010  mov     [rbp+57h+var_60], rdi
0x1400ab014  call    ??$DbgPrint@G_KW4State@AsyncUnbufferedFileReader@@KKKKKKH@dbgobj@@QEAA_KPEBGAEB_KAEBW4State@AsyncUnbufferedFileReader@@AEBK33333AEBH@Z; dbgobj::DbgPrint<ushort,unsigned __int64,AsyncUnbufferedFileReader::State,ulong,ulong,ulong,ulong,ulong,ulong,int>(ushort const *,unsigned __int64 const &,AsyncUnbufferedFileReader::State const &,ulong const &,ulong const &,ulong const &,ulong const &,ulong const &,ulong const &,int const &)
0x1400ab019  cmp     [rdi+10h], rsi
0x1400ab01d  jbe     loc_1400AB0F3
0x1400ab023  lea     rbx, [rdi+5Ch]
0x1400ab027  mov     eax, [rbx]
0x1400ab029  test    eax, eax
0x1400ab02b  jnz     short loc_1400AB034
0x1400ab02d  xor     eax, eax
0x1400ab02f  jmp     loc_1400ABE13
0x1400ab034  dec     eax
0x1400ab036  lea     r14, [rdi+60h]
0x1400ab03a  mov     ecx, [r14]
0x1400ab03d  lea     r15, [rdi+6Ch]
0x1400ab041  mov     [rbx], eax
0x1400ab043  xor     edx, edx
0x1400ab045  mov     rax, [rdi+98h]
0x1400ab04c  mov     [rax+rcx*4], esi
0x1400ab04f  lea     rcx, ?DebugAsyncIo@Settings@@3VCDebugAsyncIo@1@A; Settings::CDebugAsyncIo Settings::DebugAsyncIo
0x1400ab056  mov     eax, [r14]
0x1400ab059  inc     eax
0x1400ab05b  mov     [r15], esi
0x1400ab05e  div     dword ptr [rdi+3Ch]
0x1400ab061  mov     [r14], edx
0x1400ab064  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x1400ab069  test    eax, eax
0x1400ab06b  jz      loc_1400AB0F3
0x1400ab071  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400ab078  test    rax, rax
0x1400ab07b  jz      short loc_1400AB0F3
0x1400ab07d  cmp     [rax+40h], esi
0x1400ab080  jz      short loc_1400AB0F3
0x1400ab082  cmp     dword ptr [rax+38h], 5
0x1400ab086  jl      short loc_1400AB0F3
0x1400ab088  lea     rax, [rdi+0A0h]
0x1400ab08f  mov     [rbp+57h+var_50], r13
0x1400ab093  mov     [rsp+0E0h+var_90], rax
0x1400ab098  lea     rcx, [rdi+58h]
0x1400ab09c  mov     [rsp+0E0h+var_98], rbx
0x1400ab0a1  lea     r8, [rdi+68h]
0x1400ab0a5  mov     [rsp+0E0h+var_A0], rcx
0x1400ab0aa  lea     r10, [rdi+64h]
0x1400ab0ae  mov     [rsp+0E0h+var_A8], r15
0x1400ab0b3  lea     r9, [rdi+90h]
0x1400ab0ba  mov     [rsp+0E0h+var_B0], r8
0x1400ab0bf  lea     rdx, aThisPStateCurr_0; "this:%p state:%? currentCacheBufferInde"...
0x1400ab0c6  mov     [rsp+0E0h+var_B8], r10
0x1400ab0cb  lea     r8, [rbp+57h+var_60]
0x1400ab0cf  lea     rcx, [rbp+57h+var_50]
0x1400ab0d3  mov     [rsp+0E0h+lpOverlapped], r14
0x1400ab0d8  mov     [rbp+57h+var_48], 831h
0x1400ab0df  mov     [rbp+57h+var_44], 5
0x1400ab0e6  mov     [rbp+57h+var_40], r12
0x1400ab0ea  mov     [rbp+57h+var_60], rdi
0x1400ab0ee  call    ??$DbgPrint@G_KW4State@AsyncUnbufferedFileReader@@KKKKKKH@dbgobj@@QEAA_KPEBGAEB_KAEBW4State@AsyncUnbufferedFileReader@@AEBK33333AEBH@Z; dbgobj::DbgPrint<ushort,unsigned __int64,AsyncUnbufferedFileReader::State,ulong,ulong,ulong,ulong,ulong,ulong,int>(ushort const *,unsigned __int64 const &,AsyncUnbufferedFileReader::State const &,ulong const &,ulong const &,ulong const &,ulong const &,ulong const &,ulong const &,int const &)
0x1400ab0f3  mov     r15, rsi
0x1400ab0f6  jmp     short loc_1400AB0FF
0x1400ab0f8  lea     r13, aAsyncunbuffere_25; "AsyncUnbufferedFileReader::GetNextReadB"...
0x1400ab0ff  test    r15, r15
0x1400ab102  jnz     loc_1400ABDC8
0x1400ab108  lea     r14, [rdi+3Ch]
0x1400ab10c  lea     rbx, [rdi+5Ch]
0x1400ab110  test    r15, r15
0x1400ab113  jnz     loc_1400AB411
0x1400ab119  lea     r12, [rdi+58h]
0x1400ab11d  cmp     [r12], esi
0x1400ab121  jbe     loc_1400AB950
0x1400ab127  mov     eax, esi
0x1400ab129  mov     [rbp+57h+NumberOfBytesTransferred], esi
0x1400ab12c  lea     rbx, [rdi+5Ch]
0x1400ab130  cmp     [rbx], esi
0x1400ab132  lea     rcx, ?DebugAsyncIo@Settings@@3VCDebugAsyncIo@1@A; Settings::CDebugAsyncIo Settings::DebugAsyncIo
0x1400ab139  setz    al
0x1400ab13c  mov     [rbp+57h+bWait], eax
0x1400ab13f  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x1400ab144  test    eax, eax
0x1400ab146  jz      loc_1400AB206
0x1400ab14c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400ab153  test    rax, rax
0x1400ab156  jz      loc_1400AB206
0x1400ab15c  cmp     [rax+40h], esi
0x1400ab15f  jz      loc_1400AB206
0x1400ab165  cmp     dword ptr [rax+38h], 5
0x1400ab169  jl      loc_1400AB206
0x1400ab16f  lea     r10, [rdi+64h]
0x1400ab173  mov     [rbp+57h+var_50], r13
0x1400ab177  lea     rax, aAsyn; "ASYN"
0x1400ab17e  mov     [rbp+57h+var_48], 845h
0x1400ab185  mov     [rbp+57h+var_40], rax
0x1400ab189  lea     rcx, [rdi+6Ch]
0x1400ab18d  mov     eax, [r10]
0x1400ab190  lea     rdx, [rdi+68h]
0x1400ab194  shl     rax, 5
0x1400ab198  lea     r8, [rdi+60h]
0x1400ab19c  add     rax, [rdi+50h]
0x1400ab1a0  lea     r9, [rdi+90h]
0x1400ab1a7  mov     [rbp+57h+var_58], rax
0x1400ab1ab  lea     rax, [rdi+0A0h]
0x1400ab1b2  mov     [rsp+0E0h+var_80], rax
0x1400ab1b7  lea     rax, [rbp+57h+var_60]
0x1400ab1bb  mov     [rsp+0E0h+var_88], rbx
0x1400ab1c0  mov     [rsp+0E0h+var_90], r12
0x1400ab1c5  mov     [rsp+0E0h+var_98], rcx
0x1400ab1ca  lea     rcx, [rbp+57h+var_50]
0x1400ab1ce  mov     [rsp+0E0h+var_A0], rdx
0x1400ab1d3  lea     rdx, aCallingGetover; "Calling GetOverlappedResult(). overlapp"...
0x1400ab1da  mov     [rsp+0E0h+var_A8], r10
0x1400ab1df  mov     [rsp+0E0h+var_B0], r8
0x1400ab1e4  lea     r8, [rbp+57h+var_58]
0x1400ab1e8  mov     [rsp+0E0h+var_B8], r9
0x1400ab1ed  lea     r9, [rbp+57h+bWait]
0x1400ab1f1  mov     [rbp+57h+var_44], 5
0x1400ab1f8  mov     [rbp+57h+var_60], rdi
0x1400ab1fc  mov     [rsp+0E0h+lpOverlapped], rax
0x1400ab201  call    ??$DbgPrint@G_KH_KW4State@AsyncUnbufferedFileReader@@KKKKKKH@dbgobj@@QEAA_KPEBGAEB_KAEBH1AEBW4State@AsyncUnbufferedFileReader@@AEBK444442@Z; dbgobj::DbgPrint<ushort,unsigned __int64,int,unsigned __int64,AsyncUnbufferedFileReader::State,ulong,ulong,ulong,ulong,ulong,ulong,int>(ushort const *,unsigned __int64 const &,int const &,unsigned __int64 const &,AsyncUnbufferedFileReader::State const &,ulong const &,ulong const &,ulong const &,ulong const &,ulong const &,ulong const &,int const &)
0x1400ab206  mov     r9d, [rbp+57h+bWait]; bWait
0x1400ab20a  lea     r15, [rdi+64h]
0x1400ab20e  mov     edx, [r15]
0x1400ab211  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1400ab215  mov     rcx, [rdi+20h]; hFile
0x1400ab219  shl     rdx, 5
0x1400ab21d  add     rdx, [rdi+50h]; lpOverlapped
0x1400ab221  call    cs:__imp_GetOverlappedResult
0x1400ab228  nop     dword ptr [rax+rax+00h]
0x1400ab22d  test    eax, eax
0x1400ab22f  jz      loc_1400AB391
0x1400ab235  mov     edx, [r15]
0x1400ab238  lea     r14, [rdi+3Ch]
0x1400ab23c  mov     rcx, [rdi+98h]
0x1400ab243  mov     eax, [rbp+57h+NumberOfBytesTransferred]
0x1400ab246  mov     [rcx+rdx*4], eax
0x1400ab249  xor     edx, edx
0x1400ab24b  mov     eax, [r15]
0x1400ab24e  lea     rcx, ?DebugAsyncIo@Settings@@3VCDebugAsyncIo@1@A; Settings::CDebugAsyncIo Settings::DebugAsyncIo
0x1400ab255  dec     dword ptr [r12]
0x1400ab259  inc     eax
0x1400ab25b  div     dword ptr [r14]
0x1400ab25e  inc     dword ptr [rbx]
0x1400ab260  mov     [r15], edx
0x1400ab263  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x1400ab268  test    eax, eax
0x1400ab26a  jz      loc_1400AB32F
0x1400ab270  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400ab277  test    rax, rax
0x1400ab27a  jz      loc_1400AB32F
0x1400ab280  cmp     [rax+40h], esi
0x1400ab283  jz      loc_1400AB32F
0x1400ab289  cmp     dword ptr [rax+38h], 5
0x1400ab28d  jl      loc_1400AB32F
0x1400ab293  lea     rax, aAsyn; "ASYN"
0x1400ab29a  mov     [rbp+57h+var_50], r13
0x1400ab29e  mov     [rbp+57h+var_40], rax
0x1400ab2a2  lea     rcx, [rdi+6Ch]
0x1400ab2a6  mov     eax, [r15]
0x1400ab2a9  lea     rdx, [rdi+68h]
0x1400ab2ad  shl     rax, 5
0x1400ab2b1  lea     r8, [rdi+60h]
0x1400ab2b5  add     rax, [rdi+50h]
0x1400ab2b9  lea     r9, [rdi+90h]
0x1400ab2c0  mov     [rbp+57h+var_60], rax
0x1400ab2c4  lea     rax, [rdi+0A0h]
0x1400ab2cb  mov     [rsp+0E0h+var_78], rax
0x1400ab2d0  lea     rax, [rbp+57h+var_58]
0x1400ab2d4  mov     [rsp+0E0h+var_80], rbx
0x1400ab2d9  mov     [rsp+0E0h+var_88], r12
0x1400ab2de  mov     [rsp+0E0h+var_90], rcx
0x1400ab2e3  lea     rcx, [rbp+57h+var_50]
0x1400ab2e7  mov     [rsp+0E0h+var_98], rdx
0x1400ab2ec  lea     rdx, aGetoverlappedr_0; "GetOverlappedResult() returned success."...
0x1400ab2f3  mov     [rsp+0E0h+var_A0], r15
0x1400ab2f8  mov     [rsp+0E0h+var_A8], r8
0x1400ab2fd  lea     r8, [rbp+57h+var_60]
0x1400ab301  mov     [rsp+0E0h+var_B0], r9
0x1400ab306  lea     r9, [rbp+57h+bWait]
0x1400ab30a  mov     [rsp+0E0h+var_B8], rax
0x1400ab30f  lea     rax, [rbp+57h+NumberOfBytesTransferred]
0x1400ab313  mov     [rsp+0E0h+lpOverlapped], rax
0x1400ab318  mov     [rbp+57h+var_48], 856h
0x1400ab31f  mov     [rbp+57h+var_44], 5
0x1400ab326  mov     [rbp+57h+var_58], rdi
0x1400ab32a  call    ??$DbgPrint@G_KHK_KW4State@AsyncUnbufferedFileReader@@KKKKKKH@dbgobj@@QEAA_KPEBGAEB_KAEBHAEBK1AEBW4State@AsyncUnbufferedFileReader@@3333332@Z; dbgobj::DbgPrint<ushort,unsigned __int64,int,ulong,unsigned __int64,AsyncUnbufferedFileReader::State,ulong,ulong,ulong,ulong,ulong,ulong,int>(ushort const *,unsigned __int64 const &,int const &,ulong const &,unsigned __int64 const &,AsyncUnbufferedFileReader::State const &,ulong const &,ulong const &,ulong const &,ulong const &,ulong const &,ulong const &,int const &)
0x1400ab32f  cmp     [rbp+57h+NumberOfBytesTransferred], esi
0x1400ab332  jnz     short loc_1400AB388
0x1400ab334  call    cs:__imp_GetCurrentThreadId
0x1400ab33b  nop     dword ptr [rax+rax+00h]
0x1400ab340  mov     [rsp+0E0h+var_A0], rsi
0x1400ab345  mov     r9d, 1
0x1400ab34b  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1400ab34f  xor     r8d, r8d
0x1400ab352  lea     rax, aAsyncunbuffere_29; "AsyncUnbufferedFileReader::GetNextReadB"...
0x1400ab359  mov     dword ptr [rsp+0E0h+var_B0], 863h
0x1400ab361  mov     [rsp+0E0h+var_B8], rax
0x1400ab366  mov     edx, 3E3h
0x1400ab36b  lea     rax, aBaseFsRemotefs_14; "base\\fs\\remotefs\\frs\\src\\fs\\async"...
0x1400ab372  mov     [rsp+0E0h+lpOverlapped], rax
0x1400ab377  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400ab37c  mov     r15, rax
0x1400ab37f  mov     [rbp+57h+var_68], rax
0x1400ab383  jmp     loc_1400AB110
0x1400ab388  mov     r15, [rbp+57h+var_68]
0x1400ab38c  jmp     loc_1400AB110
0x1400ab391  mov     r13d, esi
0x1400ab394  call    cs:__imp_GetLastError
0x1400ab39b  nop     dword ptr [rax+rax+00h]
0x1400ab3a0  mov     r14d, eax
0x1400ab3a3  cmp     eax, 26h ; '&'
0x1400ab3a6  jz      loc_1400AB809
0x1400ab3ac  cmp     eax, 3E4h
0x1400ab3b1  jz      loc_1400AB72D
0x1400ab3b7  call    cs:__imp_GetCurrentThreadId
0x1400ab3be  nop     dword ptr [rax+rax+00h]
0x1400ab3c3  mov     [rsp+0E0h+var_A0], rsi
0x1400ab3c8  mov     r9d, 1
0x1400ab3ce  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1400ab3d2  xor     r8d, r8d
0x1400ab3d5  lea     rax, aAsyncunbuffere_29; "AsyncUnbufferedFileReader::GetNextReadB"...
0x1400ab3dc  mov     dword ptr [rsp+0E0h+var_B0], 89Fh
0x1400ab3e4  mov     [rsp+0E0h+var_B8], rax
0x1400ab3e9  mov     edx, r14d
0x1400ab3ec  lea     rax, aBaseFsRemotefs_14; "base\\fs\\remotefs\\frs\\src\\fs\\async"...
0x1400ab3f3  mov     [rsp+0E0h+lpOverlapped], rax
0x1400ab3f8  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400ab3fd  mov     [rbp+57h+var_68], rax
0x1400ab401  mov     r15, rax
0x1400ab404  lea     r14, [rdi+3Ch]
0x1400ab408  test    rax, rax
0x1400ab40b  jz      loc_1400AB950
0x1400ab411  mov     r14d, dword ptr [rbp+57h+arg_8]
0x1400ab415  mov     r13d, esi
0x1400ab418  test    r15, r15
0x1400ab41b  jnz     loc_1400AB0F8
0x1400ab421  mov     r12, [rbp+57h+var_68]
0x1400ab425  lea     rax, [rdi+0C0h]
0x1400ab42c  mov     r15, rax
0x1400ab42f  lea     rbx, [rdi+0A0h]
0x1400ab436  cmp     [rbx], esi
0x1400ab438  jnz     loc_1400ABC9D
0x1400ab43e  mov     r15, rax
0x1400ab441  cmp     r13d, r14d
0x1400ab444  jnb     loc_1400ABC9D
0x1400ab44a  mov     rcx, [rdi+50h]
0x1400ab44e  lea     r14, [rdi+68h]
0x1400ab452  mov     edx, [r14]
0x1400ab455  lea     r15, [rdi+0C0h]
0x1400ab45c  mov     eax, [rdi+70h]
0x1400ab45f  shl     rdx, 5
0x1400ab463  mov     [rdx+rcx+10h], eax
0x1400ab467  mov     ecx, [r14]
  ... truncated ...
```
