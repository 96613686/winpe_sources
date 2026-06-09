# [thunk]:CCompileProgressNotification::Release`adjustor{16}' (void)

- ea: `0x14000a030`
- end: `0x14000a039`
- name: `?Release@CCompileProgressNotification@@WBA@EAAKXZ`
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
  return CCompileProgressNotification::AddRef((CCompileProgressNotification *)(a1 - 16));
}

```

## disassembly

```asm
0x14000a030  sub     rcx, 10h; this
0x14000a034  jmp     ?AddRef@CCompileProgressNotification@@UEAAKXZ; CCompileProgressNotification::AddRef(void)
```
