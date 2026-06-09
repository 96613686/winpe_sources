# operator delete(void *,unsigned __int64)

- ea: `0x180001534`
- end: `0x180001539`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `68`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003040`
- `0x180003080`
- `0x180005c34`
- `0x180005d20`
- `0x180005d60`
- `0x180005dd0`
- `0x180005e40`
- `0x180005e80`
- `0x180007700`
- `0x1800078d0`
- `0x180007cb0`
- `0x180007d30`
- `0x180007d70`
- `0x180007db0`
- `0x180007e10`
- `0x180007ea0`
- `0x180007ee0`
- `0x180007f20`
- `0x180007f80`
- `0x180007fe0`
- `0x180008020`
- `0x18000aa00`
- `0x18000f4d0`
- `0x18001003c`
- `0x180010db0`
- `0x180011080`
- `0x1800110c0`
- `0x1800114c0`
- `0x1800119a0`
- `0x180011a10`
- `0x180011c10`
- `0x180012120`
- `0x180012160`
- `0x1800153b0`
- `0x180015560`
- `0x180015694`
- `0x1800160e0`
- `0x1800168f0`
- `0x180017060`
- `0x1800186e8`
- `0x180018750`
- `0x1800187a0`
- `0x1800190e4`
- `0x180019ee0`
- `0x180019f38`
- `0x180019fb0`
- `0x18001a15c`
- `0x18001a274`
- `0x18001a30c`
- `0x18001a49c`

## callees

- `0x180006efc`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x180001534  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
