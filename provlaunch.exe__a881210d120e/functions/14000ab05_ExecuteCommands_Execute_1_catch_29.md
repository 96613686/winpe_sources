# _ExecuteCommands::Execute_::_1_::catch$29

- ea: `0x14000ab05`
- end: `0x14000ab3e`
- name: `_ExecuteCommands::Execute_::_1_::catch$29`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005544`

## pseudocode

```c
__int64 __fastcall ExecuteCommands::Execute_::_1_::catch_29(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 456),
                           (void *)0xC3,
                           (unsigned int)"admin\\prov\\launch\\lib\\execute.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x14000ab05  mov     [rsp+arg_8], rdx
0x14000ab0a  push    rbp
0x14000ab0b  sub     rsp, 50h
0x14000ab0f  mov     rbp, rdx
0x14000ab12  mov     rcx, [rbp+1C8h]; this
0x14000ab19  lea     r8, aAdminProvLaunc_1; "admin\\prov\\launch\\lib\\execute.cpp"
0x14000ab20  mov     edx, 0C3h; void *
0x14000ab25  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x14000ab2a  mov     [rbp+50h], eax
0x14000ab2d  mov     rax, 0
0x14000ab37  add     rsp, 50h
0x14000ab3b  pop     rbp
0x14000ab3c  retn
```
