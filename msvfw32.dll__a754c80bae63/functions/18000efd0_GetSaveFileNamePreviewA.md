# GetSaveFileNamePreviewA

- ea: `0x18000efd0`
- end: `0x18000efdc`
- name: `GetSaveFileNamePreviewA`
- size: `12`
- prototype: `BOOL __stdcall(LPOPENFILENAMEA lpofn)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000eb40`

## pseudocode

```c
BOOL __stdcall GetSaveFileNamePreviewA(LPOPENFILENAMEA lpofn)
{
  return GetFileNamePreview((__int64)lpofn, 1, 0);
}

```

## disassembly

```asm
0x18000efd0  xor     r8d, r8d
0x18000efd3  lea     edx, [r8+1]
0x18000efd7  jmp     GetFileNamePreview
```
