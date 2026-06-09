# [thunk]:CCompileProgressNotification::Release`adjustor{8}' (void)

- ea: `0x14000a020`
- end: `0x14000a029`
- name: `?Release@CCompileProgressNotification@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007260`

## pseudocode

```c
__int64 __fastcall CCompileProgressNotification::Release(__int64 a1)
{
  return CCompileProgressNotification::AddRef((CCompileProgressNotification *)(a1 - 8));
}

```

## disassembly

```asm
0x14000a020  sub     rcx, 8; this
0x14000a024  jmp     ?AddRef@CCompileProgressNotification@@UEAAKXZ; CCompileProgressNotification::AddRef(void)
```
