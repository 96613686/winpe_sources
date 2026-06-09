# DummyCtrlHandler(ulong)

- ea: `0x140001930`
- end: `0x140001933`
- name: `?DummyCtrlHandler@@YAXK@Z`
- size: `3`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
void __fastcall DummyCtrlHandler(DWORD dwControl)
{
  ;
}

```

## disassembly

```asm
0x140001930  retn    0
```
