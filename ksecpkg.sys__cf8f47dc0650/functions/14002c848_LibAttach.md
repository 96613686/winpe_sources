# LibAttach

- ea: `0x14002c848`
- end: `0x14002c86b`
- name: `LibAttach`
- size: `35`
- prototype: ``
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x1400209a0`
- `0x140020c10`
- `0x140021db0`
- `0x1400263c0`
- `0x140026a00`
- `0x140026ad0`
- `0x140026ba0`
- `0x140026c70`
- `0x1400290b0`
- `0x140029690`
- `0x140029780`
- `0x140029870`

## callees

- `0x14000e3d8`
- `0x14000e488`
- `0x14000e544`
- `0x14002c95c`

## pseudocode

```c
_BOOL8 LibAttach()
{
  LoadCSystems();
  LoadCheckSums();
  LoadRngs();
  return (int)LoadCNG() >= 0;
}

```

## disassembly

```asm
0x14002c848  sub     rsp, 28h
0x14002c84c  call    LoadCSystems
0x14002c851  call    LoadCheckSums
0x14002c856  call    LoadRngs
0x14002c85b  call    LoadCNG
0x14002c860  not     eax
0x14002c862  shr     eax, 1Fh
0x14002c865  add     rsp, 28h
0x14002c869  retn
```
