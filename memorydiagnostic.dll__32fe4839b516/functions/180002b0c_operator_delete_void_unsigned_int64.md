# operator delete(void *,unsigned __int64)

- ea: `0x180002b0c`
- end: `0x180002b11`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `38`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005d4c`
- `0x180005e94`
- `0x180005fdc`
- `0x180007778`
- `0x1800077e4`
- `0x180007858`
- `0x180007d68`
- `0x180007dd0`
- `0x180008930`
- `0x180008960`
- `0x180008990`
- `0x1800089d0`
- `0x180008a10`
- `0x180008a70`
- `0x180008ab0`
- `0x180008b20`
- `0x180008b90`
- `0x18000b3e0`
- `0x1800168e8`
- `0x18001b190`
- `0x18001b250`
- `0x18001b290`
- `0x18001b2d0`
- `0x18001b310`
- `0x18001ba68`
- `0x18001d530`
- `0x18001dd54`
- `0x18001e018`
- `0x18001ead0`
- `0x18001fb4c`
- `0x18001fc48`
- `0x18001fd80`
- `0x18001fedc`
- `0x180020170`
- `0x180020410`
- `0x18002044c`
- `0x1800210d0`
- `0x180022f1b`

## callees

- `0x180003220`

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
0x180002b0c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
