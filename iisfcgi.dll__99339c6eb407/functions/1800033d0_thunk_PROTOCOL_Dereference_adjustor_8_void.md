# [thunk]:PROTOCOL::Dereference`adjustor{8}' (void)

- ea: `0x1800033d0`
- end: `0x1800033d9`
- name: `?Dereference@PROTOCOL@@W7EAAXXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800033c0`

## pseudocode

```c
void __fastcall PROTOCOL::Dereference(__int64 a1)
{
  PROTOCOL::Dereference((PROTOCOL *)(a1 - 8));
}

```

## disassembly

```asm
0x1800033d0  sub     rcx, 8; this
0x1800033d4  jmp     ?Dereference@PROTOCOL@@UEAAXXZ; PROTOCOL::Dereference(void)
```
