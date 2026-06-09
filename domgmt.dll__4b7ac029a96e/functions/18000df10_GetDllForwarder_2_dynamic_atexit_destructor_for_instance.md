# _GetDllForwarder_::_2_::_dynamic_atexit_destructor_for__instance__

- ea: `0x18000df10`
- end: `0x18000df47`
- name: `_GetDllForwarder_::_2_::_dynamic_atexit_destructor_for__instance__`
- size: `55`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000df10`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000df20`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000df20`

## pseudocode

```c
void __fastcall GetDllForwarder_::_2_::_dynamic_atexit_destructor_for__instance__()
{
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( qword_1800188E0 )
    (**(void (__fastcall ***)(__int64, __int64))qword_1800188E0)(qword_1800188E0, 1);
}

```

## disassembly

```asm
0x18000df10  sub     rsp, 28h
0x18000df14  mov     rcx, cs:hLibModule; hLibModule
0x18000df1b  test    rcx, rcx
0x18000df1e  jz      short loc_18000DF26
0x18000df20  call    cs:__imp_FreeLibrary
0x18000df26  mov     rcx, cs:qword_1800188E0
0x18000df2d  test    rcx, rcx
0x18000df30  jz      short loc_18000DF42
0x18000df32  mov     rax, [rcx]
0x18000df35  mov     edx, 1
0x18000df3a  mov     rax, [rax]
0x18000df3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df42  add     rsp, 28h
0x18000df46  retn
```
