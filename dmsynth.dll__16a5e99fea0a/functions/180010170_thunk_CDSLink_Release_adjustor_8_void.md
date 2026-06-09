# [thunk]:CDSLink::Release`adjustor{8}' (void)

- ea: `0x180010170`
- end: `0x180010179`
- name: `?Release@CDSLink@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180010140`

## pseudocode

```c
__int64 __fastcall CDSLink::Release(__int64 a1)
{
  return CDSLink::Release((CDSLink *)(a1 - 8));
}

```

## disassembly

```asm
0x180010170  sub     rcx, 8; this
0x180010174  jmp     ?Release@CDSLink@@UEAAKXZ; CDSLink::Release(void)
```
