# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x1800029a4`
- end: `0x1800029b5`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(DWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800021a8`
- `0x1800027c0`
- `0x18000410c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800029ae`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x1800029a4  xor     r9d, r9d
0x1800029a7  xor     r8d, r8d
0x1800029aa  lea     edx, [r9+1]
0x1800029ae  jmp     cs:__imp_RaiseException
```
