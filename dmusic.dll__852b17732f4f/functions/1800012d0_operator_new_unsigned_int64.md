# operator new[](unsigned __int64)

- ea: `0x1800012d0`
- end: `0x1800012d5`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `35`
- callee_count: `1`
- tags: ``

## callers

- `0x180009b30`
- `0x18000b918`
- `0x18000c5f8`
- `0x18000cd90`
- `0x18000db7c`
- `0x18000dbf0`
- `0x18000f5d0`
- `0x18000f6a4`
- `0x1800127d0`
- `0x180013050`
- `0x1800140a4`
- `0x1800141a0`
- `0x1800142f8`
- `0x180014530`
- `0x180014834`
- `0x180014bb8`
- `0x180015820`
- `0x180017fb4`
- `0x180018324`
- `0x1800186a4`
- `0x180018aa8`
- `0x180019460`
- `0x180019bc8`
- `0x18001bdc0`
- `0x18001c048`
- `0x18001c7f0`
- `0x18001ced8`
- `0x18001e0c8`
- `0x18001f51c`
- `0x18001f9ac`
- `0x18001fb6c`
- `0x18001ff90`
- `0x180020148`
- `0x180020220`
- `0x180020ff8`

## callees

- `0x180016204`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](unsigned __int64 a1)
{
  return operator new(a1);
}

```

## disassembly

```asm
0x1800012d0  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
