# GetOpenFileNamePreviewA

- ea: `0x18000efa0`
- end: `0x18000efaa`
- name: `GetOpenFileNamePreviewA`
- size: `10`
- prototype: `BOOL __stdcall(LPOPENFILENAMEA lpofn)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000eb40`

## pseudocode

```c
BOOL __stdcall GetOpenFileNamePreviewA(LPOPENFILENAMEA lpofn)
{
  return GetFileNamePreview((__int64)lpofn, 0, 0);
}

```

## disassembly

```asm
0x18000efa0  xor     r8d, r8d; GetOpenFileNamePreview
0x18000efa3  xor     edx, edx
0x18000efa5  jmp     GetFileNamePreview
```
