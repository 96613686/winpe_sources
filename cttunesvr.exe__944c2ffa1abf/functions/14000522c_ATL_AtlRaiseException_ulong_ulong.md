# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x14000522c`
- end: `0x14000523d`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140002c14`
- `0x140002cc0`
- `0x140003abc`
- `0x1400060fc`
- `0x140006488`

## import_xrefs

- `KERNEL32!RaiseException` at `0x140005236`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x14000522c  xor     r9d, r9d
0x14000522f  xor     r8d, r8d
0x140005232  lea     edx, [r9+1]
0x140005236  jmp     cs:__imp_RaiseException
```
