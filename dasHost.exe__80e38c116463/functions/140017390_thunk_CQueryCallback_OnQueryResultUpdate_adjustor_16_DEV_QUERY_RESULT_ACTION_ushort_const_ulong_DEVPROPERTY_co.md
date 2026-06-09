# [thunk]:CQueryCallback::OnQueryResultUpdate`adjustor{16}' (_DEV_QUERY_RESULT_ACTION,ushort const *,ulong,_DEVPROPERTY * const)

- ea: `0x140017390`
- end: `0x140017399`
- name: `?OnQueryResultUpdate@CQueryCallback@@WBA@EAAJW4_DEV_QUERY_RESULT_ACTION@@PEBGKQEAU_DEVPROPERTY@@@Z`
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
  return CQueryCallback::OnQueryResultUpdate(a1 - 16, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x140017390  sub     rcx, 10h
0x140017394  jmp     ?OnQueryResultUpdate@CQueryCallback@@UEAAJW4_DEV_QUERY_RESULT_ACTION@@PEBGKQEAU_DEVPROPERTY@@@Z; CQueryCallback::OnQueryResultUpdate(_DEV_QUERY_RESULT_ACTION,ushort const *,ulong,_DEVPROPERTY * const)
```
