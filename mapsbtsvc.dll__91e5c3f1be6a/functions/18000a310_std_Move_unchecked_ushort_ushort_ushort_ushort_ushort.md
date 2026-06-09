# std::_Move_unchecked<ushort *,ushort *>(ushort *,ushort *,ushort *)

- ea: `0x18000a310`
- end: `0x18000a315`
- name: `??$_Move_unchecked@PEAGPEAG@std@@YAPEAGPEAG00@Z`
- size: `5`
- prototype: `__int64 __fastcall(void *Src, __int64, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014102`

## callees

- `0x180009b60`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::_Move_unchecked<unsigned short *,unsigned short *>(void *Src, __int64 a2, void *a3)
{
  return std::_Copy_memmove<unsigned short *,unsigned short *>(Src, a2, a3);
}

```

## disassembly

```asm
0x18000a310  jmp     ??$_Copy_memmove@PEAGPEAG@std@@YAPEAGPEAG00@Z; std::_Copy_memmove<ushort *,ushort *>(ushort *,ushort *,ushort *)
```
