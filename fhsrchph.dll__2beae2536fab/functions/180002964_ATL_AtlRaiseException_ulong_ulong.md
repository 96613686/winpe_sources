# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x180002964`
- end: `0x180002975`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(DWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002114`
- `0x180003ed0`
- `0x180004d4c`
- `0x18000795c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18000296e`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x180002964  xor     r9d, r9d
0x180002967  xor     r8d, r8d
0x18000296a  lea     edx, [r9+1]
0x18000296e  jmp     cs:__imp_RaiseException
```
