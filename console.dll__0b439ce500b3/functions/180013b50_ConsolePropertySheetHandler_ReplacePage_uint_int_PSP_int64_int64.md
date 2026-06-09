# ConsolePropertySheetHandler::ReplacePage(uint,int (*)(_PSP *,__int64),__int64)

- ea: `0x180013b50`
- end: `0x180013b56`
- name: `?ReplacePage@ConsolePropertySheetHandler@@UEAAJIP6AHPEAU_PSP@@_J@Z1@Z`
- size: `6`
- prototype: `__int64 __fastcall(ConsolePropertySheetHandler *__hidden this, unsigned int, int (*)(struct _PSP *, __int64), __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall ConsolePropertySheetHandler::ReplacePage(
        ConsolePropertySheetHandler *this,
        __int64 a2,
        int (*a3)(struct _PSP *, __int64))
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180013b50  mov     eax, 80004001h
0x180013b55  retn
```
