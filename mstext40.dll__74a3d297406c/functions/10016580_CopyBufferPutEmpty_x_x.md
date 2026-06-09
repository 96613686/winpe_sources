# CopyBufferPutEmpty(x,x)

- ea: `0x10016580`
- end: `0x10016592`
- name: `_CopyBufferPutEmpty@8`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10015cb0`

## callees

- `0x10016a10`

## pseudocode

```c
int __stdcall CopyBufferPutEmpty(int a1, int a2)
{
  RemoveCopyItem(a1, a2);
  return 0;
}

```

## disassembly

```asm
0x10016580  push    [esp+arg_4]
0x10016584  push    [esp+4+arg_0]
0x10016588  call    RemoveCopyItem
0x1001658d  xor     eax, eax
0x1001658f  retn    8
```
