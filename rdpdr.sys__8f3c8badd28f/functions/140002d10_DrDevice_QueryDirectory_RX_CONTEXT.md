# DrDevice::QueryDirectory(_RX_CONTEXT *)

- ea: `0x140002d10`
- end: `0x140002d16`
- name: `?QueryDirectory@DrDevice@@UEAAJPEAU_RX_CONTEXT@@@Z`
- size: `6`
- prototype: `__int64 __fastcall(DrDevice *__hidden this, struct _RX_CONTEXT *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall DrDevice::QueryDirectory(DrDevice *this, struct _RX_CONTEXT *a2)
{
  return 3221225474LL;
}

```

## disassembly

```asm
0x140002d10  mov     eax, 0C0000002h
0x140002d15  retn
```
