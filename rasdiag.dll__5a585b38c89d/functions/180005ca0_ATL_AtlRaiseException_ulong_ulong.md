# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x180005ca0`
- end: `0x180005cb1`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(DWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002afc`
- `0x1800041b4`
- `0x180004694`
- `0x18000cc0c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180005caa`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x180005ca0  xor     r9d, r9d
0x180005ca3  xor     r8d, r8d
0x180005ca6  lea     edx, [r9+1]
0x180005caa  jmp     cs:__imp_RaiseException
```
