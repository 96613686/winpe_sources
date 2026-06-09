# GetOpenFileNamePreviewW

- ea: `0x18000efb0`
- end: `0x18000efbb`
- name: `GetOpenFileNamePreviewW`
- size: `11`
- prototype: `BOOL __stdcall(LPOPENFILENAMEW lpofn)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000eb40`

## pseudocode

```c
BOOL __stdcall GetOpenFileNamePreviewW(LPOPENFILENAMEW lpofn)
{
  return GetFileNamePreview((__int64)lpofn, 0, (size_t *)1);
}

```

## disassembly

```asm
0x18000efb0  xor     edx, edx
0x18000efb2  lea     r8d, [rdx+1]
0x18000efb6  jmp     GetFileNamePreview
```
