# _PwrshPlugInMediator::LoadPowerShell_::_1_::dtor$8

- ea: `0x180009b09`
- end: `0x180009b17`
- name: `_PwrshPlugInMediator::LoadPowerShell_::_1_::dtor$8`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, loader_planting`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009b10`

## pseudocode

```c
void __fastcall PwrshPlugInMediator::LoadPowerShell_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x180009b09  mov     rcx, [rdx+40h]
0x180009b10  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
