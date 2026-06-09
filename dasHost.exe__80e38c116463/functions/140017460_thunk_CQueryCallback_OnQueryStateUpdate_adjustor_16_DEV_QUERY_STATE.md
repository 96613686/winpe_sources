# [thunk]:CQueryCallback::OnQueryStateUpdate`adjustor{16}' (_DEV_QUERY_STATE)

- ea: `0x140017460`
- end: `0x140017469`
- name: `?OnQueryStateUpdate@CQueryCallback@@WBA@EAAJW4_DEV_QUERY_STATE@@@Z`
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
  return CQueryCallback::OnQueryStateUpdate(a1 - 16, a2);
}

```

## disassembly

```asm
0x140017460  sub     rcx, 10h
0x140017464  jmp     ?OnQueryStateUpdate@CQueryCallback@@UEAAJW4_DEV_QUERY_STATE@@@Z; CQueryCallback::OnQueryStateUpdate(_DEV_QUERY_STATE)
```
