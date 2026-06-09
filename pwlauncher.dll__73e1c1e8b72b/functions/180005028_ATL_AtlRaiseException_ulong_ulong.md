# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x180005028`
- end: `0x180005039`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(DWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800025c0`
- `0x180003774`
- `0x180003cc4`
- `0x18000d7e4`
- `0x18000d8a4`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180005032`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x180005028  xor     r9d, r9d
0x18000502b  xor     r8d, r8d
0x18000502e  lea     edx, [r9+1]
0x180005032  jmp     cs:__imp_RaiseException
```
