# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x1800127fc`
- end: `0x18001280d`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(DWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f2a4`
- `0x18001098c`
- `0x180011f80`
- `0x180013678`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180012806`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x1800127fc  xor     r9d, r9d
0x1800127ff  xor     r8d, r8d
0x180012802  lea     edx, [r9+1]
0x180012806  jmp     cs:__imp_RaiseException
```
