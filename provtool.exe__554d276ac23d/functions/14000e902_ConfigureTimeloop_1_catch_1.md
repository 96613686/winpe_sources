# _ConfigureTimeloop_::_1_::catch$1

- ea: `0x14000e902`
- end: `0x14000e93b`
- name: `_ConfigureTimeloop_::_1_::catch$1`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1400076f4`

## pseudocode

```c
__int64 __fastcall ConfigureTimeloop_::_1_::catch_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 808),
                           (void *)0x5B,
                           (unsigned int)"onecoreuap\\admin\\prov\\provtool\\timeloop.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x14000e902  mov     [rsp+arg_8], rdx
0x14000e907  push    rbp
0x14000e908  sub     rsp, 50h
0x14000e90c  mov     rbp, rdx
0x14000e90f  mov     rcx, [rbp+328h]; this
0x14000e916  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\provtool\\time"...
0x14000e91d  mov     edx, 5Bh ; '['; void *
0x14000e922  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x14000e927  mov     [rbp+50h], eax
0x14000e92a  mov     rax, 0
0x14000e934  add     rsp, 50h
0x14000e938  pop     rbp
0x14000e939  retn
```
