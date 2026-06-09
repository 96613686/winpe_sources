# _CreateProvCommandResultRecord_::_1_::catch$0

- ea: `0x18000d144`
- end: `0x18000d17a`
- name: `_CreateProvCommandResultRecord_::_1_::catch$0`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007650`

## pseudocode

```c
__int64 __fastcall CreateProvCommandResultRecord_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x3B,
                           (int)"admin\\prov\\launch\\csp\\setvalue.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d144  mov     [rsp+arg_8], rdx
0x18000d149  push    rbp
0x18000d14a  sub     rsp, 20h
0x18000d14e  mov     rbp, rdx
0x18000d151  mov     rcx, [rbp+28h]; this
0x18000d155  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x18000d15c  mov     edx, 3Bh ; ';'; void *
0x18000d161  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d166  mov     [rbp+48h], eax
0x18000d169  mov     rax, 0
0x18000d173  add     rsp, 20h
0x18000d177  pop     rbp
0x18000d178  retn
```
