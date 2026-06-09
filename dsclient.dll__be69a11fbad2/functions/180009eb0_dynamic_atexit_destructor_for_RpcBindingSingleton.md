# _dynamic_atexit_destructor_for__RpcBindingSingleton__

- ea: `0x180009eb0`
- end: `0x180009f03`
- name: `_dynamic_atexit_destructor_for__RpcBindingSingleton__`
- size: `83`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001fa0`
- `0x180009eb0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009ef2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009ed2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009ed2`

## pseudocode

```c
void dynamic_atexit_destructor_for__RpcBindingSingleton__()
{
  BOOL fPending; // [rsp+30h] [rbp+8h] BYREF
  LPVOID Context; // [rsp+38h] [rbp+10h] BYREF

  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&RpcBindingSingleton, 0, &fPending, &Context);
  if ( Context )
    AutoRpcBinding::~AutoRpcBinding((RPC_BINDING_HANDLE *)Context);
  else
    InitOnceComplete(&RpcBindingSingleton, 0, 0);
}

```

## disassembly

```asm
0x180009eb0  sub     rsp, 28h
0x180009eb4  xor     eax, eax
0x180009eb6  lea     r9, [rsp+28h+Context]; lpContext
0x180009ebb  lea     r8, [rsp+28h+fPending]; fPending
0x180009ec0  mov     [rsp+28h+fPending], eax
0x180009ec4  xor     edx, edx; dwFlags
0x180009ec6  mov     [rsp+28h+Context], rax
0x180009ecb  lea     rcx, ?RpcBindingSingleton@@3V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@tlx@@A; lpInitOnce
0x180009ed2  call    cs:__imp_InitOnceBeginInitialize
0x180009ed8  mov     rcx, [rsp+28h+Context]; Binding
0x180009edd  test    rcx, rcx
0x180009ee0  jnz     short loc_180009EF9
0x180009ee2  xor     r8d, r8d
0x180009ee5  lea     rcx, ?RpcBindingSingleton@@3V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@tlx@@A; tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>> RpcBindingSingleton
0x180009eec  xor     edx, edx
0x180009eee  add     rsp, 28h
0x180009ef2  jmp     cs:__imp_InitOnceComplete
0x180009ef9  call    ??1AutoRpcBinding@@QEAA@XZ; AutoRpcBinding::~AutoRpcBinding(void)
0x180009efe  add     rsp, 28h
0x180009f02  retn
```
