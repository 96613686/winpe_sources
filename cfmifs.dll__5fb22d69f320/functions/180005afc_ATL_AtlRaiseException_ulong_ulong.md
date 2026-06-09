# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x180005afc`
- end: `0x180005b0d`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000397c`
- `0x1800039a4`
- `0x18000420c`
- `0x180005368`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005b06`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x180005afc  xor     r9d, r9d
0x180005aff  xor     r8d, r8d
0x180005b02  lea     edx, [r9+1]
0x180005b06  jmp     cs:__imp_RaiseException
```
