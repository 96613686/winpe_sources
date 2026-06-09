# operator delete(void *,unsigned __int64)

- ea: `0x180001804`
- end: `0x180001809`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `45`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001810`
- `0x1800035c4`
- `0x180003990`
- `0x180003c90`
- `0x180003cd0`
- `0x180005f0c`
- `0x180007c00`
- `0x180007c40`
- `0x180008888`
- `0x180009234`
- `0x180009430`
- `0x180009470`
- `0x1800094b0`
- `0x1800094f0`
- `0x18000b240`
- `0x18000bcb8`
- `0x18000ef80`
- `0x18001140c`
- `0x18001145c`
- `0x180011724`
- `0x18001182c`
- `0x180011bc0`
- `0x1800121e8`
- `0x180014b00`
- `0x180014e68`
- `0x1800176b0`
- `0x18001874c`
- `0x180018894`
- `0x180018b30`
- `0x1800193f0`
- `0x18001ac90`
- `0x18001cae4`
- `0x18001ccc0`
- `0x18001ee70`
- `0x1800200f0`
- `0x180020940`
- `0x1800218e0`
- `0x1800252fd`
- `0x18002536b`
- `0x1800255da`
- `0x180025621`
- `0x180025792`
- `0x1800258c8`
- `0x1800259ea`
- `0x180025ad5`

## callees

- `0x180001f00`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180001804  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
