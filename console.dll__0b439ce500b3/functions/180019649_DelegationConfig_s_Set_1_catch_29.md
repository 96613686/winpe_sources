# _DelegationConfig::s_Set_::_1_::catch$29

- ea: `0x180019649`
- end: `0x180019678`
- name: `_DelegationConfig::s_Set_::_1_::catch$29`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180015680`

## pseudocode

```c
__int64 __fastcall DelegationConfig::s_Set_::_1_::catch_29(__int64 a1, __int64 a2, unsigned int a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x133,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180019649  mov     [rsp+arg_8], rdx
0x18001964e  push    rbp
0x18001964f  sub     rsp, 30h
0x180019653  mov     rbp, rdx
0x180019656  mov     rcx, [rbp+58h]; this
0x18001965a  mov     edx, 133h; void *
0x18001965f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180019664  mov     [rbp+30h], eax
0x180019667  mov     rax, 0
0x180019671  add     rsp, 30h
0x180019675  pop     rbp
0x180019676  retn
```
