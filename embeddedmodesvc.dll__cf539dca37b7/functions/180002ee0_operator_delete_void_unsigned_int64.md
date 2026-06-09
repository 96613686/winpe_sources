# operator delete(void *,unsigned __int64)

- ea: `0x180002ee0`
- end: `0x180002ee5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `24`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800045a0`
- `0x1800045e0`
- `0x180007130`
- `0x180007170`
- `0x1800071b0`
- `0x180009564`
- `0x180009f7c`
- `0x18000b130`
- `0x18000b160`
- `0x18000b190`
- `0x18000b1e0`
- `0x18000b220`
- `0x18000b260`
- `0x18000b2a0`
- `0x18000b2e0`
- `0x18000b320`
- `0x18000b360`
- `0x18000b3a0`
- `0x18001053c`
- `0x180017e28`
- `0x180017e4c`
- `0x18001821c`
- `0x18001839c`
- `0x180018e96`

## callees

- `0x180002f84`

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
0x180002ee0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
