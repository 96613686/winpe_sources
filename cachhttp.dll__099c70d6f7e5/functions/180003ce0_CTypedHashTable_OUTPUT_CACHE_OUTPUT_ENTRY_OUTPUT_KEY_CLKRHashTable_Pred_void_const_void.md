# CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_Pred(void const *,void *)

- ea: `0x180003ce0`
- end: `0x180003cec`
- name: `?_Pred@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009010`

## pseudocode

```c
__int64 __fastcall CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_Pred(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, _QWORD))a2)(a1, *(_QWORD *)(a2 + 16));
}

```

## disassembly

```asm
0x180003ce0  mov     rax, [rdx]
0x180003ce3  mov     rdx, [rdx+10h]
0x180003ce7  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
