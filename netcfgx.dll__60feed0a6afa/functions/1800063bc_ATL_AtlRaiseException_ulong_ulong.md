# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x1800063bc`
- end: `0x1800063cd`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003ed8`
- `0x18000498c`
- `0x180005c4c`
- `0x180007e08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800063c6`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x1800063bc  xor     r9d, r9d
0x1800063bf  xor     r8d, r8d
0x1800063c2  lea     edx, [r9+1]
0x1800063c6  jmp     cs:__imp_RaiseException
```
