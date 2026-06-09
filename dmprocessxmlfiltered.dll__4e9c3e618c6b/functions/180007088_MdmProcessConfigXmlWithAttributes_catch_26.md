# MdmProcessConfigXmlWithAttributes$catch$26

- ea: `0x180007088`
- end: `0x1800070b8`
- name: `MdmProcessConfigXmlWithAttributes$catch$26`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800051e4`

## pseudocode

```c
__int64 __fastcall MdmProcessConfigXmlWithAttributes_catch_26(__int64 a1, __int64 a2, unsigned int a3, const char *a4)
{
  *(_DWORD *)(a2 + 208) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 200),
                            (void *)a2,
                            a3,
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180007088  mov     [rsp+arg_8], rdx
0x18000708d  push    rbp
0x18000708e  sub     rsp, 30h
0x180007092  mov     rbp, rdx
0x180007095  mov     rcx, [rbp+0C8h]; this
0x18000709c  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800070a1  mov     [rbp+0D0h], eax
0x1800070a7  mov     rax, 0
0x1800070b1  add     rsp, 30h
0x1800070b5  pop     rbp
0x1800070b6  retn
```
