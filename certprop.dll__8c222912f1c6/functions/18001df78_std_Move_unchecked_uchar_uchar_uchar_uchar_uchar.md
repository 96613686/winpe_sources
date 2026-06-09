# std::_Move_unchecked<uchar *,uchar *>(uchar *,uchar *,uchar *)

- ea: `0x18001df78`
- end: `0x18001df7d`
- name: `??$_Move_unchecked@PEAEPEAE@std@@YAPEAEPEAE00@Z`
- size: `5`
- prototype: `__int64 __fastcall(void *Src, __int64, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180024fe6`

## callees

- `0x18000e708`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::_Move_unchecked<unsigned char *,unsigned char *>(void *Src, __int64 a2, void *a3)
{
  return std::_Copy_memmove<unsigned char *,unsigned char *>(Src, a2, a3);
}

```

## disassembly

```asm
0x18001df78  jmp     ??$_Copy_memmove@PEAEPEAE@std@@YAPEAEPEAE00@Z; std::_Copy_memmove<uchar *,uchar *>(uchar *,uchar *,uchar *)
```
