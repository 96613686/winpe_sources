# Microsoft::WRL::Details::RaiseException(long,ulong)

- ea: `0x14000ac50`
- end: `0x14000ac61`
- name: `?RaiseException@Details@WRL@Microsoft@@YAXJK@Z`
- size: `17`
- prototype: `void __fastcall(Microsoft::WRL::Details *__hidden this, int, unsigned int)`
- caller_count: `10`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140005bd4`
- `0x1400081c4`
- `0x14000a3c4`
- `0x14000d9b0`
- `0x14000e290`
- `0x140012e10`
- `0x1400135d4`
- `0x140016818`
- `0x14001691c`
- `0x14001920c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000ac5a`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::RaiseException(Microsoft::WRL::Details *this)
{
  RaiseException((DWORD)this, 1u, 0, 0);
}

```

## disassembly

```asm
0x14000ac50  xor     r9d, r9d
0x14000ac53  xor     r8d, r8d
0x14000ac56  lea     edx, [r9+1]
0x14000ac5a  jmp     cs:__imp_RaiseException
```
