# _CommandLineHandler_::_1_::catch$0

- ea: `0x14000e282`
- end: `0x14000e2b8`
- name: `_CommandLineHandler_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400076f4`

## pseudocode

```c
__int64 __fastcall CommandLineHandler_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x49,
                           (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x14000e282  mov     [rsp+arg_8], rdx
0x14000e287  push    rbp
0x14000e288  sub     rsp, 20h
0x14000e28c  mov     rbp, rdx
0x14000e28f  mov     rcx, [rbp+28h]; this
0x14000e293  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x14000e29a  mov     edx, 49h ; 'I'; void *
0x14000e29f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x14000e2a4  mov     [rbp+38h], eax
0x14000e2a7  mov     rax, 0
0x14000e2b1  add     rsp, 20h
0x14000e2b5  pop     rbp
0x14000e2b6  retn
```
