# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x180003ae8`
- end: `0x180003af9`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800025a0`
- `0x18000407c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180003af2`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x180003ae8  xor     r9d, r9d
0x180003aeb  xor     r8d, r8d
0x180003aee  lea     edx, [r9+1]
0x180003af2  jmp     cs:__imp_RaiseException
```
