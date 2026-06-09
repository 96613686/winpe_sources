# _CellState::FromCellularSnapshot_::_1_::catch$40

- ea: `0x18003df0b`
- end: `0x18003df42`
- name: `_CellState::FromCellularSnapshot_::_1_::catch$40`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180035584`

## string_xrefs

- `0x18003df1f`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`

## pseudocode

```c
__int64 __fastcall CellState::FromCellularSnapshot_::_1_::catch_40(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 440),
    (void *)0x147,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18003df0b  mov     [rsp+arg_8], rdx
0x18003df10  push    rbp
0x18003df11  sub     rsp, 20h
0x18003df15  mov     rbp, rdx
0x18003df18  mov     rcx, [rbp+1B8h]; this
0x18003df1f  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18003df26  mov     edx, 147h; void *
0x18003df2b  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003df30  nop
0x18003df31  mov     rax, 0
0x18003df3b  add     rsp, 20h
0x18003df3f  pop     rbp
0x18003df40  retn
```
