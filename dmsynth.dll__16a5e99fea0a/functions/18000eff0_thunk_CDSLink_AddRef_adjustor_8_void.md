# [thunk]:CDSLink::AddRef`adjustor{8}' (void)

- ea: `0x18000eff0`
- end: `0x18000eff9`
- name: `?AddRef@CDSLink@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000efd0`

## pseudocode

```c
__int64 __fastcall CDSLink::AddRef(__int64 a1)
{
  return CDSLink::AddRef((CDSLink *)(a1 - 8));
}

```

## disassembly

```asm
0x18000eff0  sub     rcx, 8; this
0x18000eff4  jmp     ?AddRef@CDSLink@@UEAAKXZ; CDSLink::AddRef(void)
```
