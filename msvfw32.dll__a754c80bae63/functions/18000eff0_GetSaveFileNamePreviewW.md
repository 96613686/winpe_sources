# GetSaveFileNamePreviewW

- ea: `0x18000eff0`
- end: `0x18000effd`
- name: `GetSaveFileNamePreviewW`
- size: `13`
- prototype: `BOOL __stdcall(LPOPENFILENAMEW lpofn)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000eb40`

## pseudocode

```c
BOOL __stdcall GetSaveFileNamePreviewW(LPOPENFILENAMEW lpofn)
{
  return GetFileNamePreview((__int64)lpofn, 1, (size_t *)1);
}

```

## disassembly

```asm
0x18000eff0  mov     edx, 1
0x18000eff5  mov     r8d, edx
0x18000eff8  jmp     GetFileNamePreview
```
