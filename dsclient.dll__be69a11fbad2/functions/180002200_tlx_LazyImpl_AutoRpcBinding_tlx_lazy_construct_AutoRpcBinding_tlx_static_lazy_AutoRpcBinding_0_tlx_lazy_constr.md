# tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(void)

- ea: `0x180002200`
- end: `0x180002218`
- name: `??1_Initializer@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAA@XZ`
- size: `24`
- prototype: `BOOL __fastcall(union _RTL_RUN_ONCE **)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001200`
- `0x180001290`
- `0x1800015a0`
- `0x180001810`
- `0x180002060`
- `0x180002220`

## callees

- `0x180002200`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180002210`

## pseudocode

```c
BOOL __fastcall tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(
        union _RTL_RUN_ONCE **a1)
{
  union _RTL_RUN_ONCE *v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return InitOnceComplete(v1, 4u, 0);
  return result;
}

```

## disassembly

```asm
0x180002200  mov     rcx, [rcx]
0x180002203  test    rcx, rcx
0x180002206  jz      short locret_180002217
0x180002208  xor     r8d, r8d
0x18000220b  mov     edx, 4
0x180002210  jmp     cs:__imp_InitOnceComplete
0x180002217  retn
```
