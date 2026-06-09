# [thunk]:CQueryCallback::OnQueryStateUpdate`adjustor{8}' (_DEV_QUERY_STATE)

- ea: `0x140017450`
- end: `0x140017459`
- name: `?OnQueryStateUpdate@CQueryCallback@@W7EAAJW4_DEV_QUERY_STATE@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1400173a0`

## pseudocode

```c
__int64 __fastcall CQueryCallback::OnQueryStateUpdate(__int64 a1, unsigned int a2)
{
  return CQueryCallback::OnQueryStateUpdate(a1 - 8, a2);
}

```

## disassembly

```asm
0x140017450  sub     rcx, 8
0x140017454  jmp     ?OnQueryStateUpdate@CQueryCallback@@UEAAJW4_DEV_QUERY_STATE@@@Z; CQueryCallback::OnQueryStateUpdate(_DEV_QUERY_STATE)
```
