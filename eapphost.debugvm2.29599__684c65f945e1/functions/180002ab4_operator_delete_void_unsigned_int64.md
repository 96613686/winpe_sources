# operator delete(void *,unsigned __int64)

- ea: `0x180002ab4`
- end: `0x180002ab9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `62`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003948`
- `0x180004ec0`
- `0x180004fc4`
- `0x180005000`
- `0x180005040`
- `0x180005080`
- `0x1800050d0`
- `0x180005110`
- `0x180009430`
- `0x18000ab00`
- `0x18000ab40`
- `0x18000ab80`
- `0x18000abc0`
- `0x18000e520`
- `0x18000e560`
- `0x1800105f4`
- `0x180010c60`
- `0x180012674`
- `0x180012820`
- `0x180012854`
- `0x180012880`
- `0x1800128c0`
- `0x1800150c0`
- `0x180015100`
- `0x18001755c`
- `0x1800178b0`
- `0x1800178f0`
- `0x180018f70`
- `0x180018fb0`
- `0x180019f80`
- `0x18001d840`
- `0x18001d880`
- `0x18001ee34`
- `0x18001ee64`
- `0x18001ff20`
- `0x180022c58`
- `0x180022c7c`
- `0x180023080`
- `0x1800230c0`
- `0x1800230fc`
- `0x180023140`
- `0x180023190`
- `0x1800231f0`
- `0x18002ed10`
- `0x18002ed50`
- `0x18002f0b0`
- `0x180032450`
- `0x180033a30`
- `0x180034b39`
- `0x180034b5c`

## callees

- `0x18000aa48`

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
0x180002ab4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
