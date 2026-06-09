# CacheCreateThread(ulong (*)(void *),void *,ulong *)

- ea: `0x180027cfc`
- end: `0x180027f03`
- name: `?CacheCreateThread@@YAJP6AKPEAX@Z0PEAK@Z`
- size: `519`
- prototype: `HRESULT __fastcall(unsigned int (__fastcall *fn)(void *), void *param, unsigned int *pdwThreadID)`
- caller_count: `10`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001186c`
- `0x180027668`
- `0x1800279bc`
- `0x180027ca4`
- `0x1800655d8`
- `0x1800922b4`
- `0x1800eda64`
- `0x1801b1db0`
- `0x1801b1dd0`
- `0x1801b98f0`

## callees

- `0x180006250`
- `0x180006390`
- `0x180027cfc`
- `0x18005cde8`
- `0x18005ce60`
- `0x18008db2c`
- `0x18011fba4`
- `0x180132318`
- `0x1801393a0`
- `0x18015b904`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027e50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027e50`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027dbc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027dbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027dad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027dad`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180027e42`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180027e42`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027d82`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027d82`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027dfe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027dfe`

## string_xrefs

- `0x180027d34`: `onecore\com\combase\dcomrem\threads.cxx`
- `0x180027eb0`: `onecore\com\combase\dcomrem\threads.cxx`
- `0x180027e9c`: `CacheCreateThread`

## pseudocode

```c
HRESULT __fastcall CacheCreateThread(
        unsigned int (__fastcall *fn)(void *),
        void *param,
        unsigned int *pdwThreadID,
        const char *a4)
{
  HRESULT result; // eax
  CRpcThread *v8; // rdi
  signed int v9; // ebx
  HANDLE ProcessHeap; // rax
  CRpcThread *v11; // rax
  CRpcThread *v12; // rdi
  unsigned int v13; // edx
  CThreadStack *v14; // rcx
  const wchar_t *NewThreadStackCommitSize; // rsi
  unsigned int v16; // edx
  HANDLE v17; // rax
  signed int LastError; // eax
  DWORD v19; // eax
  signed __int32 v20[8]; // [rsp+0h] [rbp-58h] BYREF
  unsigned int dwThrdId; // [rsp+60h] [rbp+8h] BYREF
  void *hThread; // [rsp+78h] [rbp+20h] BYREF

  if ( !fn )
    return -2147024809;
  dwThrdId = 0;
  COleStaticMutexSem::Request(&CRpcThreadCache::_mxs, "onecore\\com\\combase\\dcomrem\\threads.cxx", 0x1D0u, a4);
  v8 = CRpcThreadCache::_pFreeList;
  if ( CRpcThreadCache::_pFreeList )
  {
    v9 = 0;
    CRpcThreadCache::_pFreeList = CRpcThreadCache::_pFreeList->_pNext;
    COleStaticMutexSem::Release(&CRpcThreadCache::_mxs);
    dwThrdId = v8->_dwThreadID;
    v8->_fn = fn;
    v8->_param = param;
    _InterlockedOr(v20, 0);
    SetEvent(v8->_hWakeup);
    goto LABEL_20;
  }
  COleStaticMutexSem::Release(&CRpcThreadCache::_mxs);
  hThread = 0;
  result = SuspendImpersonate(&hThread);
  if ( result < 0 )
    return result;
  ProcessHeap = GetProcessHeap();
  v11 = (CRpcThread *)HeapAlloc(ProcessHeap, 0, 0x38u);
  v12 = v11;
  if ( v11 )
  {
    v11->_fDone = 0;
    v11->_fn = fn;
    v11->_param = param;
    v11->_pNext = 0;
    v11->_dwThreadID = 0;
    v11->_hInstOle32 = 0;
    v11->_hWakeup = CreateEventW(0, 0, 0, 0);
    NewThreadStackCommitSize = (const wchar_t *)CThreadStack::GetNewThreadStackCommitSize(v14, v13);
    v9 = CRpcThread::Init(v12);
    if ( v9 < 0 )
      goto LABEL_17;
    v17 = CreateThread(0, (SIZE_T)NewThreadStackCommitSize, CRpcThreadCache::RpcWorkerThreadEntry, v12, 0, &dwThrdId);
    if ( v17 )
    {
      CloseHandle(v17);
      goto LABEL_19;
    }
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    {
      v19 = GetLastError();
      ComTraceMessageT<unsigned __int64,unsigned long>(
        "onecore\\com\\combase\\dcomrem\\threads.cxx",
        "CacheCreateThread",
        518,
        ERRORS,
        L"%I64u %!WINERROR!",
        NewThreadStackCommitSize,
        v19);
    }
    if ( v9 < 0 )
LABEL_17:
      CRpcThread::`scalar deleting destructor'(v12, v16);
  }
  else
  {
    v9 = -2147024882;
  }
LABEL_19:
  ResumeImpersonate(hThread);
  if ( v9 >= 0 )
  {
LABEL_20:
    if ( pdwThreadID )
      *pdwThreadID = dwThrdId;
  }
  return v9;
}

```

## disassembly

```asm
0x180027cfc  mov     [rsp+arg_8], rbx
0x180027d01  mov     [rsp+arg_10], rbp
0x180027d06  push    rsi
0x180027d07  push    rdi
0x180027d08  push    r14
0x180027d0a  sub     rsp, 40h
0x180027d0e  mov     r14, pdwThreadID
0x180027d11  mov     rbp, param
0x180027d14  mov     rsi, fn
0x180027d17  test    fn, fn
0x180027d1a  jnz     short loc_180027D26
0x180027d1c  mov     eax, 80070057h
0x180027d21  jmp     loc_180027EF0
0x180027d26  mov     r8d, 1D0h; dwLine
0x180027d2c  mov     [rsp+58h+dwThrdId], 0
0x180027d34  lea     param, aOnecoreComComb_79; "onecore\\com\\combase\\dcomrem\\threads"...
0x180027d3b  lea     fn, ?_mxs@CRpcThreadCache@@0VCOleStaticMutexSem@@A; this
0x180027d42  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x180027d47  mov     rdi, cs:?_pFreeList@CRpcThreadCache@@0PEAVCRpcThread@@EA; CRpcThread * CRpcThreadCache::_pFreeList
0x180027d4e  lea     fn, ?_mxs@CRpcThreadCache@@0VCOleStaticMutexSem@@A; this
0x180027d55  test    rdi, rdi
0x180027d58  jz      short loc_180027D8D
0x180027d5a  mov     rax, [rdi+20h]
0x180027d5e  xor     ebx, ebx
0x180027d60  mov     cs:?_pFreeList@CRpcThreadCache@@0PEAVCRpcThread@@EA, rax; CRpcThread * CRpcThreadCache::_pFreeList
0x180027d67  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x180027d6c  mov     eax, [rdi+28h]
0x180027d6f  mov     [rsp+58h+dwThrdId], eax
0x180027d73  mov     [rdi+10h], rsi
0x180027d77  mov     [rdi+18h], rbp
0x180027d7b  lock or [rsp+58h+var_58], ebx
0x180027d7f  mov     fn, [rdi]; hEvent
0x180027d82  call    cs:__imp_SetEvent
0x180027d88  jmp     loc_180027EE2
0x180027d8d  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x180027d92  lea     fn, [rsp+58h+hThread]; pHandle
0x180027d97  mov     [rsp+58h+hThread], 0
0x180027da0  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x180027da5  test    eax, eax
0x180027da7  js      loc_180027EF0
0x180027dad  call    cs:__imp_GetProcessHeap
0x180027db3  xor     edx, edx; dwFlags
0x180027db5  mov     fn, rax; hHeap
0x180027db8  lea     r8d, [param+38h]; dwBytes
0x180027dbc  call    cs:__imp_HeapAlloc
0x180027dc2  mov     rdi, rax
0x180027dc5  test    rax, rax
0x180027dc8  jz      loc_180027ECF
0x180027dce  xor     r9d, r9d; lpName
0x180027dd1  mov     dword ptr [rax+8], 0
0x180027dd8  xor     r8d, r8d; bInitialState
0x180027ddb  mov     [rax+10h], rsi
0x180027ddf  xor     edx, edx; bManualReset
0x180027de1  mov     [rax+18h], rbp
0x180027de5  xor     ecx, ecx; lpEventAttributes
0x180027de7  mov     qword ptr [rax+20h], 0
0x180027def  mov     dword ptr [rax+28h], 0
0x180027df6  mov     qword ptr [rax+30h], 0
0x180027dfe  call    cs:__imp_CreateEventW
0x180027e04  mov     [rdi], rax
0x180027e07  call    ?GetNewThreadStackCommitSize@CThreadStack@@QEAA_KK@Z; CThreadStack::GetNewThreadStackCommitSize(ulong)
0x180027e0c  mov     fn, rdi; this
0x180027e0f  mov     rsi, rax
0x180027e12  call    ?Init@CRpcThread@@QEAAJXZ; CRpcThread::Init(void)
0x180027e17  mov     ebx, eax
0x180027e19  test    eax, eax
0x180027e1b  js      loc_180027EC5
0x180027e21  lea     rax, [rsp+58h+dwThrdId]
0x180027e26  mov     r9, rdi; lpParameter
0x180027e29  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180027e2e  lea     pdwThreadID, ?RpcWorkerThreadEntry@CRpcThreadCache@@CAKPEAX@Z; lpStartAddress
0x180027e35  mov     param, rsi; dwStackSize
0x180027e38  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180027e40  xor     ecx, ecx; lpThreadAttributes
0x180027e42  call    cs:__imp_CreateThread
0x180027e48  test    rax, rax
0x180027e4b  jz      short loc_180027E58
0x180027e4d  mov     fn, rax; hObject
0x180027e50  call    cs:__imp_CloseHandle
0x180027e56  jmp     short loc_180027ED4
0x180027e58  call    cs:__imp_GetLastError
0x180027e5e  mov     ebx, eax
0x180027e60  test    eax, eax
0x180027e62  jle     short loc_180027E6D
0x180027e64  movzx   ebx, ax
0x180027e67  or      ebx, 80070000h
0x180027e6d  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180027e73  test    eax, eax
0x180027e75  jnz     short loc_180027E8A
0x180027e77  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180027e7d  jz      short loc_180027EC1
0x180027e7f  xor     ecx, ecx; level
0x180027e81  call    IsWppLevelEnabled
0x180027e86  test    al, al
0x180027e88  jz      short loc_180027EC1
0x180027e8a  call    cs:__imp_GetLastError
0x180027e90  mov     [rsp+58h+var_28], eax; <args_1>
0x180027e94  xor     r9d, r9d; level
0x180027e97  mov     [rsp+58h+lpThreadId], rsi; <args_0>
0x180027e9c  lea     param, aCachecreatethr; "CacheCreateThread"
0x180027ea3  lea     rax, aI64uWinerror; "%I64u %!WINERROR!"
0x180027eaa  mov     r8d, 206h; line
0x180027eb0  lea     fn, aOnecoreComComb_79; "onecore\\com\\combase\\dcomrem\\threads"...
0x180027eb7  mov     qword ptr [rsp+58h+dwCreationFlags], rax; format
0x180027ebc  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x180027ec1  test    ebx, ebx
0x180027ec3  jns     short loc_180027ED4
0x180027ec5  mov     fn, rdi; this
0x180027ec8  call    ??_GCRpcThread@@QEAAPEAXI@Z; CRpcThread::`scalar deleting destructor'(uint)
0x180027ecd  jmp     short loc_180027ED4
0x180027ecf  mov     ebx, 8007000Eh
0x180027ed4  mov     fn, [rsp+58h+hThread]; hToken
0x180027ed9  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x180027ede  test    ebx, ebx
0x180027ee0  js      short loc_180027EEE
0x180027ee2  test    r14, r14
0x180027ee5  jz      short loc_180027EEE
0x180027ee7  mov     eax, [rsp+58h+dwThrdId]
0x180027eeb  mov     [r14], eax
0x180027eee  mov     eax, ebx
0x180027ef0  mov     rbx, [rsp+58h+arg_8]
0x180027ef5  mov     rbp, [rsp+58h+arg_10]
0x180027efa  add     rsp, 40h
0x180027efe  pop     r14
0x180027f00  pop     rdi
0x180027f01  pop     rsi
0x180027f02  retn
```
