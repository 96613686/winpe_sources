# tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get(void)

- ea: `0x180002220`
- end: `0x1800022a3`
- name: `?get@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAAAEAVAutoRpcBinding@@XZ`
- size: `131`
- prototype: `__int64 *__fastcall(__int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001400`
- `0x180001500`
- `0x180001b20`
- `0x180001be0`
- `0x1800039c0`
- `0x180003a7c`
- `0x180003b38`
- `0x180003c20`

## callees

- `0x180002200`
- `0x180002220`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180002286`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180002286`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180002248`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180002248`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000226b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000226b`

## pseudocode

```c
__int64 *__fastcall tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get(
        __int64 a1)
{
  __int64 *result; // rax
  union _RTL_RUN_ONCE *fPending; // [rsp+30h] [rbp+8h] BYREF
  LPVOID Context; // [rsp+38h] [rbp+10h] BYREF

  HIDWORD(fPending) = HIDWORD(a1);
  LODWORD(fPending) = 0;
  Context = 0;
  InitOnceBeginInitialize(&RpcBindingSingleton, 0, (PBOOL)&fPending, &Context);
  result = (__int64 *)Context;
  if ( !Context )
  {
    qword_18000FB70 = 0;
    InitializeCriticalSectionEx(&CriticalSection, 0, 0);
    fPending = 0;
    InitOnceComplete(&RpcBindingSingleton, 0, &qword_18000FB70);
    tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(&fPending);
    return &qword_18000FB70;
  }
  return result;
}

```

## disassembly

```asm
0x180002220  mov     [rsp+fPending], rcx
0x180002225  push    rbx
0x180002226  sub     rsp, 20h
0x18000222a  xor     ebx, ebx
0x18000222c  lea     r9, [rsp+28h+Context]; lpContext
0x180002231  lea     r8, [rsp+28h+fPending]; fPending
0x180002236  mov     dword ptr [rsp+28h+fPending], ebx
0x18000223a  xor     edx, edx; dwFlags
0x18000223c  mov     [rsp+28h+Context], rbx
0x180002241  lea     rcx, ?RpcBindingSingleton@@3V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@tlx@@A; lpInitOnce
0x180002248  call    cs:__imp_InitOnceBeginInitialize
0x18000224e  mov     rax, [rsp+28h+Context]
0x180002253  test    rax, rax
0x180002256  jnz     short loc_18000229D
0x180002258  xor     r8d, r8d; Flags
0x18000225b  mov     cs:qword_18000FB70, rbx
0x180002262  xor     edx, edx; dwSpinCount
0x180002264  lea     rcx, CriticalSection; lpCriticalSection
0x18000226b  call    cs:__imp_InitializeCriticalSectionEx
0x180002271  lea     r8, qword_18000FB70; lpContext
0x180002278  mov     [rsp+28h+fPending], rbx
0x18000227d  xor     edx, edx; dwFlags
0x18000227f  lea     rcx, ?RpcBindingSingleton@@3V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@tlx@@A; lpInitOnce
0x180002286  call    cs:__imp_InitOnceComplete
0x18000228c  lea     rcx, [rsp+28h+fPending]
0x180002291  call    ??1_Initializer@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(void)
0x180002296  lea     rax, qword_18000FB70
0x18000229d  add     rsp, 20h
0x1800022a1  pop     rbx
0x1800022a2  retn
```
