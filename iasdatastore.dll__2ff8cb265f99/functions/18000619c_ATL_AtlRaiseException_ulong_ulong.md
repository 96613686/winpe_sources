# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x18000619c`
- end: `0x1800061ad`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800039cc`
- `0x18000466c`
- `0x1800059dc`
- `0x180007238`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800061a6`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x18000619c  xor     r9d, r9d
0x18000619f  xor     r8d, r8d
0x1800061a2  lea     edx, [r9+1]
0x1800061a6  jmp     cs:__imp_RaiseException
```
