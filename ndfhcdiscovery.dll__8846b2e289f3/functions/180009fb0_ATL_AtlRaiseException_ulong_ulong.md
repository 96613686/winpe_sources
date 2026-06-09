# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x180009fb0`
- end: `0x180009fc1`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180006914`
- `0x1800086fc`
- `0x1800123e8`
- `0x18001311c`
- `0x180013200`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180009fba`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x180009fb0  xor     r9d, r9d
0x180009fb3  xor     r8d, r8d
0x180009fb6  lea     edx, [r9+1]
0x180009fba  jmp     cs:__imp_RaiseException
```
