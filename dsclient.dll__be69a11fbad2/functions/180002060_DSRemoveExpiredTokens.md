# DSRemoveExpiredTokens

- ea: `0x180002060`
- end: `0x1800021f7`
- name: `DSRemoveExpiredTokens`
- size: `407`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001200`
- `0x180001500`
- `0x180001ae0`
- `0x180001e10`
- `0x180002060`
- `0x180002200`
- `0x180002350`
- `0x1800031a8`
- `0x18000384c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800020c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800021b6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800020c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800021b6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180002086`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180002178`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180002086`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180002178`

## string_xrefs

- `0x1800020e8`: `DSRemoveExpiredTokens started.`
- `0x1800021da`: `DSRemoveExpiredTokens finished.`
- `0x180002148`: `DSRemoveExpiredTokens`

## pseudocode

```c
__int64 DSRemoveExpiredTokens()
{
  __int64 v0; // rcx
  int *v1; // rbx
  int v2; // ebx
  int i; // edi
  DSLogger *v4; // rax
  __int64 v5; // rcx
  int *v6; // rdi
  BOOL fPending; // [rsp+50h] [rbp+8h] BYREF
  LPVOID Context; // [rsp+58h] [rbp+10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&DSLoggerSingleton, 0, &fPending, &Context);
  v1 = (int *)Context;
  if ( !Context )
  {
    dword_18000FA50 = McGenEventRegister_EventRegister() == 0;
    v10 = 0;
    InitOnceComplete(&DSLoggerSingleton, 0, &dword_18000FA50);
    v1 = &dword_18000FA50;
    tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(&v10);
  }
  if ( *v1 && (Microsoft_WindowsPhone_DataSharingEnableBits & 0x40) != 0 )
    McTemplateU0z_EventWriteTransfer(v0, DSClientApiStartedEvent, L"DSRemoveExpiredTokens started.");
  v2 = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( (unsigned int)CheckForRpcRetry(v2) )
    {
      v2 = EnsureDSSvcRunning();
      if ( v2 < 0 )
        break;
    }
    v2 = DSCRemoveExpiredTokens();
    if ( !(unsigned int)CheckForRpcRetry(v2) )
      break;
  }
  if ( v2 >= 0 )
  {
    fPending = 0;
    Context = 0;
    InitOnceBeginInitialize(&DSLoggerSingleton, 0, &fPending, &Context);
    v6 = (int *)Context;
    if ( !Context )
    {
      dword_18000FA50 = McGenEventRegister_EventRegister() == 0;
      v10 = 0;
      InitOnceComplete(&DSLoggerSingleton, 0, &dword_18000FA50);
      v6 = &dword_18000FA50;
      tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(&v10);
    }
    if ( *v6 && (Microsoft_WindowsPhone_DataSharingEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(v5, DSClientApiCompletedEvent, L"DSRemoveExpiredTokens finished.");
  }
  else
  {
    v4 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    DSLogger::LogError(v4, L"DSRemoveExpiredTokens", 0x20Fu, L"hr=0x%x.", v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180002060  push    rbx
0x180002062  push    rsi
0x180002063  push    rdi
0x180002064  sub     rsp, 30h
0x180002068  xor     esi, esi
0x18000206a  lea     r9, [rsp+48h+Context]; lpContext
0x18000206f  lea     r8, [rsp+48h+fPending]; fPending
0x180002074  mov     [rsp+48h+fPending], esi
0x180002078  xor     edx, edx; dwFlags
0x18000207a  mov     [rsp+48h+Context], rsi
0x18000207f  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x180002086  call    cs:__imp_InitOnceBeginInitialize
0x18000208c  mov     rbx, [rsp+48h+Context]
0x180002091  test    rbx, rbx
0x180002094  jnz     short loc_1800020DB
0x180002096  mov     cs:dword_18000FA50, esi
0x18000209c  call    McGenEventRegister_EventRegister
0x1800020a1  test    eax, eax
0x1800020a3  jnz     short loc_1800020AF
0x1800020a5  mov     cs:dword_18000FA50, 1
0x1800020af  lea     r8, dword_18000FA50; lpContext
0x1800020b6  mov     [rsp+48h+arg_10], rsi
0x1800020bb  xor     edx, edx; dwFlags
0x1800020bd  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x1800020c4  call    cs:__imp_InitOnceComplete
0x1800020ca  lea     rcx, [rsp+48h+arg_10]
0x1800020cf  lea     rbx, dword_18000FA50
0x1800020d6  call    ??1_Initializer@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(void)
0x1800020db  cmp     [rbx], esi
0x1800020dd  jz      short loc_1800020FB
0x1800020df  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 40h
0x1800020e6  jz      short loc_1800020FB
0x1800020e8  lea     r8, aDsremoveexpire_2; "DSRemoveExpiredTokens started."
0x1800020ef  lea     rdx, DSClientApiStartedEvent
0x1800020f6  call    McTemplateU0z_EventWriteTransfer
0x1800020fb  mov     ebx, esi
0x1800020fd  mov     edi, esi
0x1800020ff  mov     ecx, ebx; int
0x180002101  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x180002106  test    eax, eax
0x180002108  jz      short loc_180002115
0x18000210a  call    ?EnsureDSSvcRunning@@YAJXZ; EnsureDSSvcRunning(void)
0x18000210f  mov     ebx, eax
0x180002111  test    eax, eax
0x180002113  js      short loc_18000212E
0x180002115  call    ?DSCRemoveExpiredTokens@@YAJXZ; DSCRemoveExpiredTokens(void)
0x18000211a  mov     ecx, eax; int
0x18000211c  mov     ebx, eax
0x18000211e  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x180002123  test    eax, eax
0x180002125  jz      short loc_18000212E
0x180002127  inc     edi
0x180002129  cmp     edi, 2
0x18000212c  jl      short loc_1800020FF
0x18000212e  test    ebx, ebx
0x180002130  jns     short loc_18000215C
0x180002132  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180002137  lea     r9, aHr0xX; "hr=0x%x."
0x18000213e  mov     [rsp+48h+var_28], ebx
0x180002142  mov     r8d, 20Fh; unsigned int
0x180002148  lea     rdx, aDsremoveexpire_1; "DSRemoveExpiredTokens"
0x18000214f  mov     rcx, rax; this
0x180002152  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180002157  jmp     loc_1800021ED
0x18000215c  lea     r9, [rsp+48h+Context]; lpContext
0x180002161  mov     [rsp+48h+fPending], esi
0x180002165  lea     r8, [rsp+48h+fPending]; fPending
0x18000216a  mov     [rsp+48h+Context], rsi
0x18000216f  xor     edx, edx; dwFlags
0x180002171  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x180002178  call    cs:__imp_InitOnceBeginInitialize
0x18000217e  mov     rdi, [rsp+48h+Context]
0x180002183  test    rdi, rdi
0x180002186  jnz     short loc_1800021CD
0x180002188  mov     cs:dword_18000FA50, esi
0x18000218e  call    McGenEventRegister_EventRegister
0x180002193  test    eax, eax
0x180002195  jnz     short loc_1800021A1
0x180002197  mov     cs:dword_18000FA50, 1
0x1800021a1  lea     r8, dword_18000FA50; lpContext
0x1800021a8  mov     [rsp+48h+arg_10], rsi
0x1800021ad  xor     edx, edx; dwFlags
0x1800021af  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x1800021b6  call    cs:__imp_InitOnceComplete
0x1800021bc  lea     rcx, [rsp+48h+arg_10]
0x1800021c1  lea     rdi, dword_18000FA50
0x1800021c8  call    ??1_Initializer@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(void)
0x1800021cd  cmp     [rdi], esi
0x1800021cf  jz      short loc_1800021ED
0x1800021d1  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 40h
0x1800021d8  jz      short loc_1800021ED
0x1800021da  lea     r8, aDsremoveexpire_0; "DSRemoveExpiredTokens finished."
0x1800021e1  lea     rdx, DSClientApiCompletedEvent
0x1800021e8  call    McTemplateU0z_EventWriteTransfer
0x1800021ed  mov     eax, ebx
0x1800021ef  add     rsp, 30h
0x1800021f3  pop     rdi
0x1800021f4  pop     rsi
0x1800021f5  pop     rbx
0x1800021f6  retn
```
