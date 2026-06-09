# Microsoft::WRL::Details::RaiseException(long,ulong)

- ea: `0x180004adc`
- end: `0x180004aed`
- name: `?RaiseException@Details@WRL@Microsoft@@YAXJK@Z`
- size: `17`
- prototype: `void __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002ed4`
- `0x1800053e0`
- `0x18000574c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004ae6`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::RaiseException(Microsoft::WRL::Details *this)
{
  RaiseException((DWORD)this, 1u, 0, 0);
}

```

## disassembly

```asm
0x180004adc  xor     r9d, r9d
0x180004adf  xor     r8d, r8d
0x180004ae2  lea     edx, [r9+1]
0x180004ae6  jmp     cs:__imp_RaiseException
```
