# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x140008afc`
- end: `0x140008b0d`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140005b3c`
- `0x140006968`
- `0x140007110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140008b06`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x140008afc  xor     r9d, r9d
0x140008aff  xor     r8d, r8d
0x140008b02  lea     edx, [r9+1]
0x140008b06  jmp     cs:__imp_RaiseException
```
