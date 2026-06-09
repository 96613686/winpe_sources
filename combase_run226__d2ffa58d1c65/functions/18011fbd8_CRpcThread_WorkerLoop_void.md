# CRpcThread::WorkerLoop(void)

- ea: `0x18011fbd8`
- end: `0x18011fe33`
- name: `?WorkerLoop@CRpcThread@@QEAAXXZ`
- size: `603`
- prototype: `void __fastcall(CRpcThread *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18011fb10`

## callees

- `0x180006250`
- `0x180006390`
- `0x180087660`
- `0x18008db2c`
- `0x18011c178`
- `0x18011fbd8`
- `0x18013b6cc`
- `0x180144e80`
- `0x180145958`
- `0x18014d5b0`
- `0x180255010`

## import_xrefs

- `ntdll!RtlCheckForOrphanedCriticalSections` at `0x18011fc32`
- `ntdll!RtlCheckForOrphanedCriticalSections` at `0x18011fc32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fcb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fdb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fcb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fdb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011fe08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011fe08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011fc29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011fc29`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18011fcaa`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18011fcaa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18011fd60`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18011fd60`

## string_xrefs

- `0x18011fcf5`: `CRpcThread::WorkerLoop`
- `0x18011fdc9`: `CRpcThread::WorkerLoop`
- `0x18011fd04`: `onecore\com\combase\dcomrem\threads.cxx`
- `0x18011fddd`: `onecore\com\combase\dcomrem\threads.cxx`

## pseudocode

```c
void __fastcall CRpcThread::WorkerLoop(CRpcThread *this)
{
  _DWORD *ReservedForOle; // rcx
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  HANDLE WaitableTimer; // rsi
  char v6; // bp
  signed int LastError; // eax
  HRESULT v8; // edx
  CRpcThread *v9; // rcx
  unsigned int v10; // edi
  CRpcThreadCache *v11; // rcx
  DWORD v12; // eax
  signed __int32 v13[8]; // [rsp+0h] [rbp-58h] BYREF
  unsigned int dwRet; // [rsp+60h] [rbp+8h] BYREF

  if ( this->_fDone )
    return;
  do
  {
    ReservedForOle = NtCurrentTeb()->ReservedForOle;
    if ( ReservedForOle )
      ReservedForOle[78] = 0;
    this->_fn(this->_param);
    CurrentThread = GetCurrentThread();
    RtlCheckForOrphanedCriticalSections(CurrentThread);
    this->_fn = 0;
    this->_param = 0;
    _InterlockedOr(v13, 0);
    if ( !this->_hWakeup )
      break;
    COleStaticMutexSem::Request(&CRpcThreadCache::_mxs, "Unknown File", 0, v4);
    this->_pNext = CRpcThreadCache::_pFreeList;
    CRpcThreadCache::_pFreeList = this;
    COleStaticMutexSem::Release(&CRpcThreadCache::_mxs);
    WaitableTimer = 0;
    dwRet = 0;
    v6 = 0;
    while ( 1 )
    {
      if ( WaitableTimer || (WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x100002u)) != 0 )
      {
        if ( WaitCoalesced(WaitableTimer, 1u, &this->_hWakeup, 0x7530u, 0x7530u, 1, &dwRet) < 0 )
          v6 = 1;
        if ( !v6 )
        {
          v10 = dwRet;
          goto LABEL_20;
        }
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          ComTraceMessageT<long>(
            "onecore\\com\\combase\\dcomrem\\threads.cxx",
            "CRpcThread::WorkerLoop",
            321,
            ERRORS,
            L"%!HRESULT!",
            v8);
        v6 = 1;
      }
      v10 = WaitForSingleObjectEx(this->_hWakeup, 0x7530u, 1);
      dwRet = v10;
LABEL_20:
      if ( !v10 )
        break;
      if ( v10 != 192 && !CRpcThread::IsIOPending(v9) )
      {
        if ( v10 != 258
          && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS)) )
        {
          v12 = GetLastError();
          ComTraceMessageT<unsigned long,unsigned long>(
            "onecore\\com\\combase\\dcomrem\\threads.cxx",
            "CRpcThread::WorkerLoop",
            362,
            ERRORS,
            L"%x %!WINERROR!",
            v10,
            v12);
        }
        CRpcThreadCache::RemoveFromFreeList(v11, this);
        if ( this->_fDone )
          break;
      }
    }
    if ( WaitableTimer )
      CloseHandle(WaitableTimer);
    ApiTelemetryLogger::FireEvent(MutexAbandoned);
  }
  while ( !this->_fDone );
}

```

## disassembly

```asm
0x18011fbd8  mov     [rsp+arg_8], rbx
0x18011fbdd  mov     [rsp+arg_10], rbp
0x18011fbe2  push    rsi
0x18011fbe3  push    rdi
0x18011fbe4  push    r15
0x18011fbe6  sub     rsp, 40h
0x18011fbea  cmp     dword ptr [this+8], 0
0x18011fbee  mov     rbx, this
0x18011fbf1  jnz     loc_18011FE20
0x18011fbf7  mov     r15d, 1
0x18011fbfd  mov     rax, gs:30h
0x18011fc06  mov     this, [rax+1758h]
0x18011fc0d  test    this, this
0x18011fc10  jz      short loc_18011FC1C
0x18011fc12  mov     dword ptr [this+138h], 0
0x18011fc1c  mov     this, [rbx+18h]
0x18011fc20  mov     rax, [rbx+10h]
0x18011fc24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fc29  call    cs:__imp_GetCurrentThread
0x18011fc2f  mov     this, rax; ThreadHandle
0x18011fc32  call    cs:__imp_RtlCheckForOrphanedCriticalSections
0x18011fc38  mov     qword ptr [rbx+10h], 0
0x18011fc40  mov     qword ptr [rbx+18h], 0
0x18011fc48  lock or [rsp+58h+var_58], 0
0x18011fc4d  cmp     qword ptr [rbx], 0
0x18011fc51  jz      loc_18011FE20
0x18011fc57  xor     r8d, r8d; dwLine
0x18011fc5a  lea     rdx, aUnknownFile; "Unknown File"
0x18011fc61  lea     this, ?_mxs@CRpcThreadCache@@0VCOleStaticMutexSem@@A; this
0x18011fc68  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x18011fc6d  mov     rax, cs:?_pFreeList@CRpcThreadCache@@0PEAVCRpcThread@@EA; CRpcThread * CRpcThreadCache::_pFreeList
0x18011fc74  lea     this, ?_mxs@CRpcThreadCache@@0VCOleStaticMutexSem@@A; this
0x18011fc7b  mov     [rbx+20h], rax
0x18011fc7f  mov     cs:?_pFreeList@CRpcThreadCache@@0PEAVCRpcThread@@EA, rbx; CRpcThread * CRpcThreadCache::_pFreeList
0x18011fc86  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x18011fc8b  xor     esi, esi
0x18011fc8d  mov     [rsp+58h+dwRet], 0
0x18011fc95  xor     bpl, bpl
0x18011fc98  test    rsi, rsi
0x18011fc9b  jnz     short loc_18011FD1B
0x18011fc9d  mov     r9d, 100002h; dwDesiredAccess
0x18011fca3  xor     r8d, r8d; dwFlags
0x18011fca6  xor     edx, edx; lpTimerName
0x18011fca8  xor     ecx, ecx; lpTimerAttributes
0x18011fcaa  call    cs:__imp_CreateWaitableTimerExW
0x18011fcb0  mov     rsi, rax
0x18011fcb3  test    rax, rax
0x18011fcb6  jnz     short loc_18011FD1B
0x18011fcb8  call    cs:__imp_GetLastError
0x18011fcbe  mov     edx, eax
0x18011fcc0  test    eax, eax
0x18011fcc2  jle     short loc_18011FCCD
0x18011fcc4  movzx   edx, ax
0x18011fcc7  or      edx, 80070000h
0x18011fccd  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18011fcd3  test    eax, eax
0x18011fcd5  jnz     short loc_18011FCEA
0x18011fcd7  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18011fcdd  jz      short loc_18011FD16
0x18011fcdf  xor     ecx, ecx; level
0x18011fce1  call    IsWppLevelEnabled
0x18011fce6  test    al, al
0x18011fce8  jz      short loc_18011FD16
0x18011fcea  mov     [rsp+58h+alertable], edx; <args_0>
0x18011fcee  lea     rax, aHresult; "%!HRESULT!"
0x18011fcf5  lea     rdx, aCrpcthreadWork; "CRpcThread::WorkerLoop"
0x18011fcfc  mov     [rsp+58h+format], rax; format
0x18011fd01  xor     r9d, r9d; level
0x18011fd04  lea     this, aOnecoreComComb_79; "onecore\\com\\combase\\dcomrem\\threads"...
0x18011fd0b  mov     r8d, 141h; line
0x18011fd11  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18011fd16  mov     bpl, r15b
0x18011fd19  jmp     short loc_18011FD55
0x18011fd1b  lea     rax, [rsp+58h+dwRet]
0x18011fd20  mov     r9d, 7530h; delayInMs
0x18011fd26  mov     [rsp+58h+waitResult], rax; waitResult
0x18011fd2b  mov     r8, rbx; pHandles
0x18011fd2e  mov     [rsp+58h+alertable], r15d; alertable
0x18011fd33  mov     edx, r15d; cHandlesOuter
0x18011fd36  mov     this, rsi; timer
0x18011fd39  mov     dword ptr [rsp+58h+format], 7530h; tolerableDelayInMs
0x18011fd41  call    ?WaitCoalesced@@YAJPEAXIPEBQEAXKKHPEAK@Z; WaitCoalesced(void *,uint,void * const *,ulong,ulong,int,ulong *)
0x18011fd46  test    eax, eax
0x18011fd48  movzx   ebp, bpl
0x18011fd4c  cmovs   ebp, r15d
0x18011fd50  test    bpl, bpl
0x18011fd53  jz      short loc_18011FD6E
0x18011fd55  mov     this, [rbx]; hHandle
0x18011fd58  mov     r8d, r15d; bAlertable
0x18011fd5b  mov     edx, 7530h; dwMilliseconds
0x18011fd60  call    cs:__imp_WaitForSingleObjectEx
0x18011fd66  mov     edi, eax
0x18011fd68  mov     [rsp+58h+dwRet], eax
0x18011fd6c  jmp     short loc_18011FD72
0x18011fd6e  mov     edi, [rsp+58h+dwRet]
0x18011fd72  test    edi, edi
0x18011fd74  jz      loc_18011FE00
0x18011fd7a  cmp     edi, 0C0h
0x18011fd80  jz      loc_18011FC98
0x18011fd86  call    ?IsIOPending@CRpcThread@@QEAAHXZ; CRpcThread::IsIOPending(void)
0x18011fd8b  test    eax, eax
0x18011fd8d  jnz     loc_18011FC98
0x18011fd93  cmp     edi, 102h
0x18011fd99  jz      short loc_18011FDEE
0x18011fd9b  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18011fda1  test    eax, eax
0x18011fda3  jnz     short loc_18011FDB8
0x18011fda5  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18011fdab  jz      short loc_18011FDEE
0x18011fdad  xor     ecx, ecx; level
0x18011fdaf  call    IsWppLevelEnabled
0x18011fdb4  test    al, al
0x18011fdb6  jz      short loc_18011FDEE
0x18011fdb8  call    cs:__imp_GetLastError
0x18011fdbe  mov     dword ptr [rsp+58h+waitResult], eax; <args_1>
0x18011fdc2  xor     r9d, r9d; level
0x18011fdc5  mov     [rsp+58h+alertable], edi; <args_0>
0x18011fdc9  lea     rdx, aCrpcthreadWork; "CRpcThread::WorkerLoop"
0x18011fdd0  lea     rax, aXWinerror; "%x %!WINERROR!"
0x18011fdd7  mov     r8d, 16Ah; line
0x18011fddd  lea     this, aOnecoreComComb_79; "onecore\\com\\combase\\dcomrem\\threads"...
0x18011fde4  mov     [rsp+58h+format], rax; format
0x18011fde9  call    ??$ComTraceMessageT@KK@@YAXPEBD0HW4TraceLevel@@PEBGKK@Z; ComTraceMessageT<ulong,ulong>(char const *,char const *,int,TraceLevel,ushort const *,ulong,ulong)
0x18011fdee  mov     rdx, rbx; pThrd
0x18011fdf1  call    ?RemoveFromFreeList@CRpcThreadCache@@QEAAXPEAVCRpcThread@@@Z; CRpcThreadCache::RemoveFromFreeList(CRpcThread *)
0x18011fdf6  cmp     dword ptr [rbx+8], 0
0x18011fdfa  jz      loc_18011FC98
0x18011fe00  test    rsi, rsi
0x18011fe03  jz      short loc_18011FE0E
0x18011fe05  mov     this, rsi; hObject
0x18011fe08  call    cs:__imp_CloseHandle
0x18011fe0e  mov     ecx, r15d; eventRequestType
0x18011fe11  call    ?FireEvent@ApiTelemetryLogger@@YAJW4EventRequestType@1@@Z; ApiTelemetryLogger::FireEvent(ApiTelemetryLogger::EventRequestType)
0x18011fe16  cmp     dword ptr [rbx+8], 0
0x18011fe1a  jz      loc_18011FBFD
0x18011fe20  mov     rbx, [rsp+58h+arg_8]
0x18011fe25  mov     rbp, [rsp+58h+arg_10]
0x18011fe2a  add     rsp, 40h
0x18011fe2e  pop     r15
0x18011fe30  pop     rdi
0x18011fe31  pop     rsi
0x18011fe32  retn
```
