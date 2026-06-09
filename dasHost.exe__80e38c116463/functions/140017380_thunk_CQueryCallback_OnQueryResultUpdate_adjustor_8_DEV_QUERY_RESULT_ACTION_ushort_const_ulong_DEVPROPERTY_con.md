# [thunk]:CQueryCallback::OnQueryResultUpdate`adjustor{8}' (_DEV_QUERY_RESULT_ACTION,ushort const *,ulong,_DEVPROPERTY * const)

- ea: `0x140017380`
- end: `0x140017389`
- name: `?OnQueryResultUpdate@CQueryCallback@@W7EAAJW4_DEV_QUERY_RESULT_ACTION@@PEBGKQEAU_DEVPROPERTY@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, unsigned int, const unsigned __int16 *, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140017000`

## pseudocode

```c
__int64 __fastcall CQueryCallback::OnQueryResultUpdate(
        __int64 a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        __int64 a5)
{
  return CQueryCallback::OnQueryResultUpdate(a1 - 8, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x140017380  sub     rcx, 8
0x140017384  jmp     ?OnQueryResultUpdate@CQueryCallback@@UEAAJW4_DEV_QUERY_RESULT_ACTION@@PEBGKQEAU_DEVPROPERTY@@@Z; CQueryCallback::OnQueryResultUpdate(_DEV_QUERY_RESULT_ACTION,ushort const *,ulong,_DEVPROPERTY * const)
```
