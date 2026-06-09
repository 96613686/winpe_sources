# OpenLagPerfData(ushort *)

- ea: `0x180003bc0`
- end: `0x180003bc5`
- name: `?OpenLagPerfData@@YAKPEAG@Z`
- size: `5`
- prototype: `unsigned int __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007668`

## pseudocode

```c
// attributes: thunk
BOOL __fastcall OpenLagPerfData(unsigned __int16 *a1)
{
  return LagCounterManager::PerfOpenDataCallback(a1);
}

```

## disassembly

```asm
0x180003bc0  jmp     ?PerfOpenDataCallback@LagCounterManager@@SAKPEAG@Z; LagCounterManager::PerfOpenDataCallback(ushort *)
```
