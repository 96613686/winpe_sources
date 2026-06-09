# _CreateProvCommandResultRecord_::_1_::catch$0

- ea: `0x18000d810`
- end: `0x18000d846`
- name: `_CreateProvCommandResultRecord_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800079c0`

## pseudocode

```c
__int64 __fastcall CreateProvCommandResultRecord_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x3B,
                           (unsigned int)"admin\\prov\\launch\\csp\\setvalue.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d810  mov     [rsp+arg_8], rdx
0x18000d815  push    rbp
0x18000d816  sub     rsp, 20h
0x18000d81a  mov     rbp, rdx
0x18000d81d  mov     rcx, [rbp+28h]; this
0x18000d821  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x18000d828  mov     edx, 3Bh ; ';'; void *
0x18000d82d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d832  mov     [rbp+48h], eax
0x18000d835  mov     rax, 0
0x18000d83f  add     rsp, 20h
0x18000d843  pop     rbp
0x18000d844  retn
```
