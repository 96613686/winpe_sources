# DSGetSharedFileName

- ea: `0x1800015a0`
- end: `0x1800017fc`
- name: `DSGetSharedFileName`
- size: `604`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800015a0`
- `0x180001ae0`
- `0x180001b20`
- `0x180001e10`
- `0x180002200`
- `0x180002350`
- `0x1800031a8`
- `0x18000384c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180001633`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000170f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800017b5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180001633`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000170f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800017b5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800015f4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800016d0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180001776`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800015f4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800016d0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180001776`

## pseudocode

```c
__int64 __fastcall DSGetSharedFileName(unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 v4; // rcx
  int *v5; // rbx
  int v6; // ebx
  int i; // ebp
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rcx
  int *v13; // rdi
  DSLogger *v14; // rdi
  _QWORD v16[5]; // [rsp+30h] [rbp-28h] BYREF
  BOOL fPending; // [rsp+70h] [rbp+18h] BYREF
  LPVOID Context; // [rsp+78h] [rbp+20h] BYREF

  if ( a1 && *a1 && a2 )
  {
    fPending = 0;
    Context = 0;
    InitOnceBeginInitialize(&DSLoggerSingleton, 0, &fPending, &Context);
    v5 = (int *)Context;
    if ( !Context )
    {
      dword_18000FA50 = McGenEventRegister_EventRegister() == 0;
      v16[0] = 0;
      InitOnceComplete(&DSLoggerSingleton, 0, &dword_18000FA50);
      v5 = &dword_18000FA50;
      tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(v16);
    }
    if ( *v5 && (Microsoft_WindowsPhone_DataSharingEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(v4, DSClientApiStartedEvent, L"DSGetSharedFileName started.");
    v6 = 0;
    for ( i = 0; i < 2; ++i )
    {
      if ( (unsigned int)CheckForRpcRetry(v6) )
      {
        v6 = EnsureDSSvcRunning(v9, v8, v10, v11);
        if ( v6 < 0 )
          break;
      }
      v6 = DSCGetSharedFileName(a1, a2);
      if ( !(unsigned int)CheckForRpcRetry(v6) )
        break;
    }
    if ( v6 >= 0 )
    {
      fPending = 0;
      Context = 0;
      InitOnceBeginInitialize(&DSLoggerSingleton, 0, &fPending, &Context);
      v13 = (int *)Context;
      if ( !Context )
      {
        dword_18000FA50 = McGenEventRegister_EventRegister() == 0;
        v16[0] = 0;
        InitOnceComplete(&DSLoggerSingleton, 0, &dword_18000FA50);
        v13 = &dword_18000FA50;
        tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(v16);
      }
      if ( *v13 && (Microsoft_WindowsPhone_DataSharingEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(v12, DSClientApiCompletedEvent, L"DSGetSharedFileName finished.");
      return (unsigned int)v6;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&DSLoggerSingleton, 0, &fPending, &Context);
  v14 = (DSLogger *)Context;
  if ( !Context )
  {
    dword_18000FA50 = McGenEventRegister_EventRegister() == 0;
    v16[0] = 0;
    InitOnceComplete(&DSLoggerSingleton, 0, &dword_18000FA50);
    v14 = (DSLogger *)&dword_18000FA50;
    tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(v16);
  }
  DSLogger::LogError(v14, L"DSGetSharedFileName", 0x172u, L"hr=0x%x.", v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800015a0  mov     [rsp+arg_8], rbx
0x1800015a5  push    rsi
0x1800015a6  push    rdi
0x1800015a7  push    r14
0x1800015a9  sub     rsp, 40h
0x1800015ad  xor     r14d, r14d
0x1800015b0  mov     rsi, rdx
0x1800015b3  mov     rdi, rcx
0x1800015b6  test    rcx, rcx
0x1800015b9  jz      loc_180001754
0x1800015bf  cmp     [rcx], r14w
0x1800015c3  jz      loc_180001754
0x1800015c9  test    rdx, rdx
0x1800015cc  jz      loc_180001754
0x1800015d2  lea     r9, [rsp+58h+Context]; lpContext
0x1800015d7  mov     [rsp+58h+arg_0], rbp
0x1800015dc  lea     r8, [rsp+58h+fPending]; fPending
0x1800015e1  mov     [rsp+58h+fPending], r14d
0x1800015e6  xor     edx, edx; dwFlags
0x1800015e8  mov     [rsp+58h+Context], r14
0x1800015ed  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x1800015f4  call    cs:__imp_InitOnceBeginInitialize
0x1800015fa  mov     rbx, [rsp+58h+Context]
0x1800015ff  test    rbx, rbx
0x180001602  jnz     short loc_18000164A
0x180001604  mov     cs:dword_18000FA50, r14d
0x18000160b  call    McGenEventRegister_EventRegister
0x180001610  test    eax, eax
0x180001612  jnz     short loc_18000161E
0x180001614  mov     cs:dword_18000FA50, 1
0x18000161e  lea     r8, dword_18000FA50; lpContext
0x180001625  mov     [rsp+58h+var_28], r14
0x18000162a  xor     edx, edx; dwFlags
0x18000162c  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x180001633  call    cs:__imp_InitOnceComplete
0x180001639  lea     rcx, [rsp+58h+var_28]
0x18000163e  lea     rbx, dword_18000FA50
0x180001645  call    ??1_Initializer@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(void)
0x18000164a  cmp     [rbx], r14d
0x18000164d  jz      short loc_18000166B
0x18000164f  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 40h
0x180001656  jz      short loc_18000166B
0x180001658  lea     r8, aDsgetsharedfil_0; "DSGetSharedFileName started."
0x18000165f  lea     rdx, DSClientApiStartedEvent
0x180001666  call    McTemplateU0z_EventWriteTransfer
0x18000166b  mov     ebx, r14d
0x18000166e  mov     ebp, r14d
0x180001671  mov     ecx, ebx; int
0x180001673  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x180001678  test    eax, eax
0x18000167a  jz      short loc_180001687
0x18000167c  call    ?EnsureDSSvcRunning@@YAJXZ; EnsureDSSvcRunning(void)
0x180001681  mov     ebx, eax
0x180001683  test    eax, eax
0x180001685  js      short loc_1800016A6
0x180001687  mov     rdx, rsi; unsigned __int16 **
0x18000168a  mov     rcx, rdi; unsigned __int16 *
0x18000168d  call    ?DSCGetSharedFileName@@YAJPEBGPEAPEAG@Z; DSCGetSharedFileName(ushort const *,ushort * *)
0x180001692  mov     ecx, eax; int
0x180001694  mov     ebx, eax
0x180001696  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x18000169b  test    eax, eax
0x18000169d  jz      short loc_1800016A6
0x18000169f  inc     ebp
0x1800016a1  cmp     ebp, 2
0x1800016a4  jl      short loc_180001671
0x1800016a6  mov     rbp, [rsp+58h+arg_0]
0x1800016ab  test    ebx, ebx
0x1800016ad  js      loc_180001759
0x1800016b3  lea     r9, [rsp+58h+Context]; lpContext
0x1800016b8  mov     [rsp+58h+fPending], r14d
0x1800016bd  lea     r8, [rsp+58h+fPending]; fPending
0x1800016c2  mov     [rsp+58h+Context], r14
0x1800016c7  xor     edx, edx; dwFlags
0x1800016c9  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x1800016d0  call    cs:__imp_InitOnceBeginInitialize
0x1800016d6  mov     rdi, [rsp+58h+Context]
0x1800016db  test    rdi, rdi
0x1800016de  jnz     short loc_180001726
0x1800016e0  mov     cs:dword_18000FA50, r14d
0x1800016e7  call    McGenEventRegister_EventRegister
0x1800016ec  test    eax, eax
0x1800016ee  jnz     short loc_1800016FA
0x1800016f0  mov     cs:dword_18000FA50, 1
0x1800016fa  lea     r8, dword_18000FA50; lpContext
0x180001701  mov     [rsp+58h+var_28], r14
0x180001706  xor     edx, edx; dwFlags
0x180001708  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x18000170f  call    cs:__imp_InitOnceComplete
0x180001715  lea     rcx, [rsp+58h+var_28]
0x18000171a  lea     rdi, dword_18000FA50
0x180001721  call    ??1_Initializer@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(void)
0x180001726  cmp     [rdi], r14d
0x180001729  jz      loc_1800017EC
0x18000172f  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 40h
0x180001736  jz      loc_1800017EC
0x18000173c  lea     r8, aDsgetsharedfil_2; "DSGetSharedFileName finished."
0x180001743  lea     rdx, DSClientApiCompletedEvent
0x18000174a  call    McTemplateU0z_EventWriteTransfer
0x18000174f  jmp     loc_1800017EC
0x180001754  mov     ebx, 80070057h
0x180001759  lea     r9, [rsp+58h+Context]; lpContext
0x18000175e  mov     [rsp+58h+fPending], r14d
0x180001763  lea     r8, [rsp+58h+fPending]; fPending
0x180001768  mov     [rsp+58h+Context], r14
0x18000176d  xor     edx, edx; dwFlags
0x18000176f  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x180001776  call    cs:__imp_InitOnceBeginInitialize
0x18000177c  mov     rdi, [rsp+58h+Context]
0x180001781  test    rdi, rdi
0x180001784  jnz     short loc_1800017CC
0x180001786  mov     cs:dword_18000FA50, r14d
0x18000178d  call    McGenEventRegister_EventRegister
0x180001792  test    eax, eax
0x180001794  jnz     short loc_1800017A0
0x180001796  mov     cs:dword_18000FA50, 1
0x1800017a0  lea     r8, dword_18000FA50; lpContext
0x1800017a7  mov     [rsp+58h+var_28], r14
0x1800017ac  xor     edx, edx; dwFlags
0x1800017ae  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x1800017b5  call    cs:__imp_InitOnceComplete
0x1800017bb  lea     rcx, [rsp+58h+var_28]
0x1800017c0  lea     rdi, dword_18000FA50
0x1800017c7  call    ??1_Initializer@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(void)
0x1800017cc  lea     r9, aHr0xX; "hr=0x%x."
0x1800017d3  mov     [rsp+58h+var_38], ebx
0x1800017d7  mov     r8d, 172h; unsigned int
0x1800017dd  lea     rdx, aDsgetsharedfil_1; "DSGetSharedFileName"
0x1800017e4  mov     rcx, rdi; this
0x1800017e7  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800017ec  mov     eax, ebx
0x1800017ee  mov     rbx, [rsp+58h+arg_8]
0x1800017f3  add     rsp, 40h
0x1800017f7  pop     r14
0x1800017f9  pop     rdi
0x1800017fa  pop     rsi
0x1800017fb  retn
```
