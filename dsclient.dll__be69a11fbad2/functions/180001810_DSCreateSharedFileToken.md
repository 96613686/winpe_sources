# DSCreateSharedFileToken

- ea: `0x180001810`
- end: `0x180001ad8`
- name: `DSCreateSharedFileToken`
- size: `712`
- prototype: `__int64 __fastcall(_WORD *, _DWORD *, unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001810`
- `0x180001ae0`
- `0x180001be0`
- `0x180001e10`
- `0x180002200`
- `0x180002350`
- `0x1800031a8`
- `0x18000384c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800018f4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800019e0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180001a86`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800018f4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800019e0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180001a86`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800018b5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800019a1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180001a47`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800018b5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800019a1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180001a47`

## string_xrefs

- `0x180001aae`: `DSCreateSharedFileToken`
- `0x180001919`: `DSCreateSharedFileToken started.`
- `0x180001a0d`: `DSCreateSharedFileToken finished.`

## pseudocode

```c
__int64 __fastcall DSCreateSharedFileToken(_WORD *a1, _DWORD *a2, unsigned int a3, unsigned int a4, __int64 a5)
{
  __int64 v9; // rcx
  int *v10; // rbx
  int v11; // ebx
  int i; // r12d
  __int64 v13; // rcx
  int *v14; // rdi
  DSLogger *v15; // rdi
  __int64 v17; // [rsp+20h] [rbp-58h]
  BOOL fPending; // [rsp+30h] [rbp-48h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v20[2]; // [rsp+40h] [rbp-38h] BYREF

  if ( a5 && a1 && *a1 && a2 && *a2 <= 2u && a2[1] <= 7u && (unsigned int)(a2[2] - 1) <= 0x13 && a3 <= 1 && a4 <= 1 )
  {
    fPending = 0;
    Context = 0;
    InitOnceBeginInitialize(&DSLoggerSingleton, 0, &fPending, &Context);
    v10 = (int *)Context;
    if ( !Context )
    {
      dword_18000FA50 = McGenEventRegister_EventRegister() == 0;
      v20[0] = 0;
      InitOnceComplete(&DSLoggerSingleton, 0, &dword_18000FA50);
      v10 = &dword_18000FA50;
      tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(v20);
    }
    if ( *v10 && (Microsoft_WindowsPhone_DataSharingEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(v9, DSClientApiStartedEvent, L"DSCreateSharedFileToken started.");
    v11 = 0;
    for ( i = 0; i < 2; ++i )
    {
      if ( (unsigned int)CheckForRpcRetry(v11) )
      {
        v11 = EnsureDSSvcRunning();
        if ( v11 < 0 )
          break;
      }
      v11 = DSCCreateSharedFileToken(a1, a2, a3, a4, a5);
      if ( !(unsigned int)CheckForRpcRetry(v11) )
        break;
    }
    if ( v11 >= 0 )
    {
      fPending = 0;
      Context = 0;
      InitOnceBeginInitialize(&DSLoggerSingleton, 0, &fPending, &Context);
      v14 = (int *)Context;
      if ( !Context )
      {
        dword_18000FA50 = McGenEventRegister_EventRegister() == 0;
        v20[0] = 0;
        InitOnceComplete(&DSLoggerSingleton, 0, &dword_18000FA50);
        v14 = &dword_18000FA50;
        tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(v20);
      }
      if ( *v14 && (Microsoft_WindowsPhone_DataSharingEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(v13, DSClientApiCompletedEvent, L"DSCreateSharedFileToken finished.");
      return (unsigned int)v11;
    }
  }
  else
  {
    v11 = -2147024809;
  }
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&DSLoggerSingleton, 0, &fPending, &Context);
  v15 = (DSLogger *)Context;
  if ( !Context )
  {
    dword_18000FA50 = McGenEventRegister_EventRegister() == 0;
    v20[0] = 0;
    InitOnceComplete(&DSLoggerSingleton, 0, &dword_18000FA50);
    v15 = (DSLogger *)&dword_18000FA50;
    tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(v20);
  }
  LODWORD(v17) = v11;
  DSLogger::LogError(v15, L"DSCreateSharedFileToken", 0x158u, L"hr=0x%x.", v17);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180001810  mov     r11, rsp
0x180001813  mov     [r11+10h], rbx
0x180001817  mov     [r11+18h], rbp
0x18000181b  push    rsi
0x18000181c  push    rdi
0x18000181d  push    r13
0x18000181f  push    r14
0x180001821  push    r15
0x180001823  sub     rsp, 50h
0x180001827  mov     rdi, [rsp+78h+arg_20]
0x18000182f  xor     r13d, r13d
0x180001832  mov     r14d, r9d
0x180001835  mov     r15d, r8d
0x180001838  mov     rsi, rdx
0x18000183b  mov     rbp, rcx
0x18000183e  test    rdi, rdi
0x180001841  jz      loc_180001A25
0x180001847  test    rcx, rcx
0x18000184a  jz      loc_180001A25
0x180001850  cmp     [rcx], r13w
0x180001854  jz      loc_180001A25
0x18000185a  test    rdx, rdx
0x18000185d  jz      loc_180001A25
0x180001863  cmp     dword ptr [rdx], 2
0x180001866  ja      loc_180001A25
0x18000186c  cmp     dword ptr [rdx+4], 7
0x180001870  ja      loc_180001A25
0x180001876  mov     eax, [rdx+8]
0x180001879  dec     eax
0x18000187b  cmp     eax, 13h
0x18000187e  ja      loc_180001A25
0x180001884  cmp     r8d, 1
0x180001888  ja      loc_180001A25
0x18000188e  cmp     r9d, 1
0x180001892  ja      loc_180001A25
0x180001898  lea     r9, [r11-40h]; lpContext
0x18000189c  mov     [r11+8], r12
0x1800018a0  lea     r8, [r11-48h]; fPending
0x1800018a4  mov     [r11-48h], r13d
0x1800018a8  xor     edx, edx; dwFlags
0x1800018aa  mov     [r11-40h], r13
0x1800018ae  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x1800018b5  call    cs:__imp_InitOnceBeginInitialize
0x1800018bb  mov     rbx, [rsp+78h+Context]
0x1800018c0  test    rbx, rbx
0x1800018c3  jnz     short loc_18000190B
0x1800018c5  mov     cs:dword_18000FA50, r13d
0x1800018cc  call    McGenEventRegister_EventRegister
0x1800018d1  test    eax, eax
0x1800018d3  jnz     short loc_1800018DF
0x1800018d5  mov     cs:dword_18000FA50, 1
0x1800018df  lea     r8, dword_18000FA50; lpContext
0x1800018e6  mov     [rsp+78h+var_38], r13
0x1800018eb  xor     edx, edx; dwFlags
0x1800018ed  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x1800018f4  call    cs:__imp_InitOnceComplete
0x1800018fa  lea     rcx, [rsp+78h+var_38]
0x1800018ff  lea     rbx, dword_18000FA50
0x180001906  call    ??1_Initializer@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(void)
0x18000190b  cmp     [rbx], r13d
0x18000190e  jz      short loc_18000192C
0x180001910  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 40h
0x180001917  jz      short loc_18000192C
0x180001919  lea     r8, aDscreateshared_2; "DSCreateSharedFileToken started."
0x180001920  lea     rdx, DSClientApiStartedEvent
0x180001927  call    McTemplateU0z_EventWriteTransfer
0x18000192c  mov     ebx, r13d
0x18000192f  mov     r12d, r13d
0x180001932  mov     ecx, ebx; int
0x180001934  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x180001939  test    eax, eax
0x18000193b  jz      short loc_180001948
0x18000193d  call    ?EnsureDSSvcRunning@@YAJXZ; EnsureDSSvcRunning(void)
0x180001942  mov     ebx, eax
0x180001944  test    eax, eax
0x180001946  js      short loc_180001974
0x180001948  mov     r9d, r14d
0x18000194b  mov     [rsp+78h+var_58], rdi
0x180001950  mov     r8d, r15d
0x180001953  mov     rdx, rsi
0x180001956  mov     rcx, rbp
0x180001959  call    ?DSCCreateSharedFileToken@@YAJPEBGPEBU_DS_SHARE_ACCESS_CONTROL@@W4_DS_TOKEN_LIFETIME_TYPE@@W4_DS_TOKEN_USAGE_TYPE@@PEAPEAG@Z; DSCCreateSharedFileToken(ushort const *,_DS_SHARE_ACCESS_CONTROL const *,_DS_TOKEN_LIFETIME_TYPE,_DS_TOKEN_USAGE_TYPE,ushort * *)
0x18000195e  mov     ecx, eax; int
0x180001960  mov     ebx, eax
0x180001962  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x180001967  test    eax, eax
0x180001969  jz      short loc_180001974
0x18000196b  inc     r12d
0x18000196e  cmp     r12d, 2
0x180001972  jl      short loc_180001932
0x180001974  mov     r12, [rsp+78h+arg_0]
0x18000197c  test    ebx, ebx
0x18000197e  js      loc_180001A2A
0x180001984  lea     r9, [rsp+78h+Context]; lpContext
0x180001989  mov     [rsp+78h+fPending], r13d
0x18000198e  lea     r8, [rsp+78h+fPending]; fPending
0x180001993  mov     [rsp+78h+Context], r13
0x180001998  xor     edx, edx; dwFlags
0x18000199a  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x1800019a1  call    cs:__imp_InitOnceBeginInitialize
0x1800019a7  mov     rdi, [rsp+78h+Context]
0x1800019ac  test    rdi, rdi
0x1800019af  jnz     short loc_1800019F7
0x1800019b1  mov     cs:dword_18000FA50, r13d
0x1800019b8  call    McGenEventRegister_EventRegister
0x1800019bd  test    eax, eax
0x1800019bf  jnz     short loc_1800019CB
0x1800019c1  mov     cs:dword_18000FA50, 1
0x1800019cb  lea     r8, dword_18000FA50; lpContext
0x1800019d2  mov     [rsp+78h+var_38], r13
0x1800019d7  xor     edx, edx; dwFlags
0x1800019d9  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x1800019e0  call    cs:__imp_InitOnceComplete
0x1800019e6  lea     rcx, [rsp+78h+var_38]
0x1800019eb  lea     rdi, dword_18000FA50
0x1800019f2  call    ??1_Initializer@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(void)
0x1800019f7  cmp     [rdi], r13d
0x1800019fa  jz      loc_180001ABD
0x180001a00  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 40h
0x180001a07  jz      loc_180001ABD
0x180001a0d  lea     r8, aDscreateshared_0; "DSCreateSharedFileToken finished."
0x180001a14  lea     rdx, DSClientApiCompletedEvent
0x180001a1b  call    McTemplateU0z_EventWriteTransfer
0x180001a20  jmp     loc_180001ABD
0x180001a25  mov     ebx, 80070057h
0x180001a2a  lea     r9, [rsp+78h+Context]; lpContext
0x180001a2f  mov     [rsp+78h+fPending], r13d
0x180001a34  lea     r8, [rsp+78h+fPending]; fPending
0x180001a39  mov     [rsp+78h+Context], r13
0x180001a3e  xor     edx, edx; dwFlags
0x180001a40  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x180001a47  call    cs:__imp_InitOnceBeginInitialize
0x180001a4d  mov     rdi, [rsp+78h+Context]
0x180001a52  test    rdi, rdi
0x180001a55  jnz     short loc_180001A9D
0x180001a57  mov     cs:dword_18000FA50, r13d
0x180001a5e  call    McGenEventRegister_EventRegister
0x180001a63  test    eax, eax
0x180001a65  jnz     short loc_180001A71
0x180001a67  mov     cs:dword_18000FA50, 1
0x180001a71  lea     r8, dword_18000FA50; lpContext
0x180001a78  mov     [rsp+78h+var_38], r13
0x180001a7d  xor     edx, edx; dwFlags
0x180001a7f  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x180001a86  call    cs:__imp_InitOnceComplete
0x180001a8c  lea     rcx, [rsp+78h+var_38]
0x180001a91  lea     rdi, dword_18000FA50
0x180001a98  call    ??1_Initializer@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(void)
0x180001a9d  lea     r9, aHr0xX; "hr=0x%x."
0x180001aa4  mov     dword ptr [rsp+78h+var_58], ebx
0x180001aa8  mov     r8d, 158h; unsigned int
0x180001aae  lea     rdx, aDscreateshared_1; "DSCreateSharedFileToken"
0x180001ab5  mov     rcx, rdi; this
0x180001ab8  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180001abd  mov     eax, ebx
0x180001abf  lea     r11, [rsp+78h+var_28]
0x180001ac4  mov     rbx, [r11+38h]
0x180001ac8  mov     rbp, [r11+40h]
0x180001acc  mov     rsp, r11
0x180001acf  pop     r15
0x180001ad1  pop     r14
0x180001ad3  pop     r13
0x180001ad5  pop     rdi
0x180001ad6  pop     rsi
0x180001ad7  retn
```
