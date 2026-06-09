# tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)

- ea: `0x180001200`
- end: `0x180001283`
- name: `?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ`
- size: `131`
- prototype: `int *__fastcall(__int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001290`
- `0x180002060`
- `0x1800031d0`
- `0x1800032a0`
- `0x180003380`
- `0x180003460`
- `0x180003518`

## callees

- `0x180001200`
- `0x180001e10`
- `0x180002200`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180001266`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180001266`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180001228`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180001228`

## pseudocode

```c
int *__fastcall tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
        __int64 a1)
{
  int *result; // rax
  union _RTL_RUN_ONCE *fPending; // [rsp+30h] [rbp+8h] BYREF
  LPVOID Context; // [rsp+38h] [rbp+10h] BYREF

  HIDWORD(fPending) = HIDWORD(a1);
  LODWORD(fPending) = 0;
  Context = 0;
  InitOnceBeginInitialize(&DSLoggerSingleton, 0, (PBOOL)&fPending, &Context);
  result = (int *)Context;
  if ( !Context )
  {
    dword_18000FA50 = McGenEventRegister_EventRegister() == 0;
    fPending = 0;
    InitOnceComplete(&DSLoggerSingleton, 0, &dword_18000FA50);
    tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(&fPending);
    return &dword_18000FA50;
  }
  return result;
}

```

## disassembly

```asm
0x180001200  mov     [rsp+fPending], rcx
0x180001205  push    rbx
0x180001206  sub     rsp, 20h
0x18000120a  xor     ebx, ebx
0x18000120c  lea     r9, [rsp+28h+Context]; lpContext
0x180001211  lea     r8, [rsp+28h+fPending]; fPending
0x180001216  mov     dword ptr [rsp+28h+fPending], ebx
0x18000121a  xor     edx, edx; dwFlags
0x18000121c  mov     [rsp+28h+Context], rbx
0x180001221  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x180001228  call    cs:__imp_InitOnceBeginInitialize
0x18000122e  mov     rax, [rsp+28h+Context]
0x180001233  test    rax, rax
0x180001236  jnz     short loc_18000127D
0x180001238  mov     cs:dword_18000FA50, ebx
0x18000123e  call    McGenEventRegister_EventRegister
0x180001243  test    eax, eax
0x180001245  jnz     short loc_180001251
0x180001247  mov     cs:dword_18000FA50, 1
0x180001251  lea     r8, dword_18000FA50; lpContext
0x180001258  mov     [rsp+28h+fPending], rbx
0x18000125d  xor     edx, edx; dwFlags
0x18000125f  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x180001266  call    cs:__imp_InitOnceComplete
0x18000126c  lea     rcx, [rsp+28h+fPending]
0x180001271  call    ??1_Initializer@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(void)
0x180001276  lea     rax, dword_18000FA50
0x18000127d  add     rsp, 20h
0x180001281  pop     rbx
0x180001282  retn
```
