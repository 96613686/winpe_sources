# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x18000b3dc`
- end: `0x18000b3ed`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(DWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180004a90`
- `0x180004ab8`
- `0x180007310`
- `0x18000a3d0`
- `0x18001766c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18000b3e6`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x18000b3dc  xor     r9d, r9d
0x18000b3df  xor     r8d, r8d
0x18000b3e2  lea     edx, [r9+1]
0x18000b3e6  jmp     cs:__imp_RaiseException
```
