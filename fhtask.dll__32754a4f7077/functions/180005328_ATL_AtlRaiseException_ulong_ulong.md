# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x180005328`
- end: `0x180005339`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(DWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800030dc`
- `0x180003cec`
- `0x180005340`
- `0x180009678`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180005332`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x180005328  xor     r9d, r9d
0x18000532b  xor     r8d, r8d
0x18000532e  lea     edx, [r9+1]
0x180005332  jmp     cs:__imp_RaiseException
```
