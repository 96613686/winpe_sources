# lldpReferenceClient

- ea: `0x14000628c`
- end: `0x140006291`
- name: `lldpReferenceClient`
- size: `5`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x14000ef10`
- `0x14000efd0`
- `0x14000fd1c`

## pseudocode

```c
void __fastcall lldpReferenceClient(__int64 a1)
{
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
}

```

## disassembly

```asm
0x14000628c  lock inc dword ptr [rcx+10h]
0x140006290  retn
```
