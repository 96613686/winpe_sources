# operator delete(void *,unsigned __int64)

- ea: `0x180002b14`
- end: `0x180002b19`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `62`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800039e8`
- `0x180005000`
- `0x180005110`
- `0x180005140`
- `0x180005180`
- `0x1800051c0`
- `0x180005210`
- `0x180005250`
- `0x180009808`
- `0x18000af90`
- `0x18000afd0`
- `0x18000b010`
- `0x18000b050`
- `0x18000eb00`
- `0x18000eb40`
- `0x180010d3c`
- `0x180011310`
- `0x180012e04`
- `0x180012fb0`
- `0x180012fe4`
- `0x180013010`
- `0x180013050`
- `0x180015900`
- `0x180015940`
- `0x180017e48`
- `0x1800181d0`
- `0x180018210`
- `0x180019930`
- `0x180019970`
- `0x18001a960`
- `0x18001e330`
- `0x18001e370`
- `0x18001f964`
- `0x18001f994`
- `0x180020aa0`
- `0x180023890`
- `0x1800238b4`
- `0x180023cf0`
- `0x180023d30`
- `0x180023d6c`
- `0x180023db0`
- `0x180023e00`
- `0x180023e70`
- `0x18002fe10`
- `0x18002fe50`
- `0x1800301d0`
- `0x180033780`
- `0x180034de0`
- `0x180035ef9`
- `0x180035f1d`

## callees

- `0x18000aed4`

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
0x180002b14  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
