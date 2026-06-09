# _ux::CLauncherMainTaskDialog::SetLauncherEnabled_::_1_::dtor$1

- ea: `0x18001074f`
- end: `0x18001075d`
- name: `_ux::CLauncherMainTaskDialog::SetLauncherEnabled_::_1_::dtor$1`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, service_task`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010756`

## pseudocode

```c
void __fastcall ux::CLauncherMainTaskDialog::SetLauncherEnabled_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 136));
}

```

## disassembly

```asm
0x18001074f  mov     rcx, [rdx+88h]
0x180010756  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
