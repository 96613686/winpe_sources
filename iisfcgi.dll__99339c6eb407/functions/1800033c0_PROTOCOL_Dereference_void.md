# PROTOCOL::Dereference(void)

- ea: `0x1800033c0`
- end: `0x1800033c9`
- name: `?Dereference@PROTOCOL@@UEAAXXZ`
- size: `9`
- prototype: `void __fastcall(PROTOCOL *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800033d0`

## callees

- `0x1800033e0`

## pseudocode

```c
void __fastcall PROTOCOL::Dereference(PROTOCOL *this)
{
  PROTOCOL::DereferenceProtocol((PROTOCOL *)((char *)this - 8));
}

```

## disassembly

```asm
0x1800033c0  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x1800033c4  jmp     ?DereferenceProtocol@PROTOCOL@@QEAAXXZ; PROTOCOL::DereferenceProtocol(void)
```
