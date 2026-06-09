# DllGetSimpleObjectByIDEx

- ea: `0x180002af0`
- end: `0x180002b19`
- name: `DllGetSimpleObjectByIDEx`
- size: `41`
- prototype: `__int64 __fastcall(int, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002a818`
- `0x18002c9cc`
- `0x18002cf48`
- `0x18002d78c`

## callees

- `0x180002740`
- `0x180002970`
- `0x180002af0`

## pseudocode

```c
__int64 __fastcall DllGetSimpleObjectByIDEx(int a1, const struct _GUID *a2, void **a3)
{
  if ( !a3 || *a3 )
    return 2147942487LL;
  if ( a1 == 1 )
    return ReallyGetSimpleTableDispenser(a2, a3);
  return DllGetSimpleObjectByID(a1, a2, a3);
}

```

## disassembly

```asm
0x180002af0  mov     rax, rdx
0x180002af3  test    r8, r8
0x180002af6  jz      short loc_180002B13
0x180002af8  cmp     qword ptr [r8], 0
0x180002afc  jnz     short loc_180002B13
0x180002afe  cmp     ecx, 1
0x180002b01  jnz     short loc_180002B0E
0x180002b03  mov     rdx, r8; void **
0x180002b06  mov     rcx, rax; struct _GUID *
0x180002b09  jmp     ?ReallyGetSimpleTableDispenser@@YAJAEBU_GUID@@PEAPEAX@Z; ReallyGetSimpleTableDispenser(_GUID const &,void * *)
0x180002b0e  jmp     DllGetSimpleObjectByID
0x180002b13  mov     eax, 80070057h
0x180002b18  retn
```
