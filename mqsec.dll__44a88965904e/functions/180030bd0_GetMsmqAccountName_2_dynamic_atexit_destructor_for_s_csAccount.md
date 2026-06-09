# __GetMsmqAccountName_::_2_::_dynamic_atexit_destructor_for__s_csAccount__

- ea: `0x180030bd0`
- end: `0x180030be7`
- name: `__GetMsmqAccountName_::_2_::_dynamic_atexit_destructor_for__s_csAccount__`
- size: `23`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180030bdb`
- `KERNEL32!DeleteCriticalSection` at `0x180030bdb`

## pseudocode

```c
void __fastcall _GetMsmqAccountName_::_2_::_dynamic_atexit_destructor_for__s_csAccount__()
{
  DeleteCriticalSection(&stru_180043310);
}

```

## disassembly

```asm
0x180030bd0  sub     rsp, 28h
0x180030bd4  lea     rcx, stru_180043310; lpCriticalSection
0x180030bdb  call    cs:__imp_DeleteCriticalSection
0x180030be1  nop
0x180030be2  add     rsp, 28h
0x180030be6  retn
```
