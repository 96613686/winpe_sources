# _CellState::FromCellularSnapshot_::_1_::catch$41

- ea: `0x18003df48`
- end: `0x18003df7f`
- name: `_CellState::FromCellularSnapshot_::_1_::catch$41`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180035584`

## string_xrefs

- `0x18003df5c`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`

## pseudocode

```c
__int64 __fastcall CellState::FromCellularSnapshot_::_1_::catch_41(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 440),
    (void *)0x151,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18003df48  mov     [rsp+arg_8], rdx
0x18003df4d  push    rbp
0x18003df4e  sub     rsp, 20h
0x18003df52  mov     rbp, rdx
0x18003df55  mov     rcx, [rbp+1B8h]; this
0x18003df5c  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18003df63  mov     edx, 151h; void *
0x18003df68  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003df6d  nop
0x18003df6e  mov     rax, 0
0x18003df78  add     rsp, 20h
0x18003df7c  pop     rbp
0x18003df7d  retn
```
