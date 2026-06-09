# Microsoft::WRL::Details::RaiseException(long,ulong)

- ea: `0x14000a9f0`
- end: `0x14000aa01`
- name: `?RaiseException@Details@WRL@Microsoft@@YAXJK@Z`
- size: `17`
- prototype: `void __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140005b34`
- `0x140007ff8`
- `0x14000a19c`
- `0x14000dd30`
- `0x14001248c`
- `0x140013b84`
- `0x140017a80`
- `0x140017b80`
- `0x14001841c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000a9fa`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::RaiseException(Microsoft::WRL::Details *this)
{
  RaiseException((DWORD)this, 1u, 0, 0);
}

```

## disassembly

```asm
0x14000a9f0  xor     r9d, r9d
0x14000a9f3  xor     r8d, r8d
0x14000a9f6  lea     edx, [r9+1]
0x14000a9fa  jmp     cs:__imp_RaiseException
```
