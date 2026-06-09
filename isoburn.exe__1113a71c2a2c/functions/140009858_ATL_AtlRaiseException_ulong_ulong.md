# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x140009858`
- end: `0x140009869`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1400045e4`
- `0x14000aac0`
- `0x14000cc84`
- `0x14000d138`
- `0x14000e130`
- `0x14000ee40`

## import_xrefs

- `KERNEL32!RaiseException` at `0x140009862`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x140009858  xor     r9d, r9d
0x14000985b  xor     r8d, r8d
0x14000985e  lea     edx, [r9+1]
0x140009862  jmp     cs:__imp_RaiseException
```
