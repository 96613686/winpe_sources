# _GenerateSerialNumberComputerName_::_1_::catch$19

- ea: `0x1800371bc`
- end: `0x1800371f5`
- name: `_GenerateSerialNumberComputerName_::_1_::catch$19`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008d30`

## string_xrefs

- `0x1800371d0`: `onecoreuap\admin\dm\dmcmnutils\computernameutils\computernameutils.cpp`

## pseudocode

```c
__int64 __fastcall GenerateSerialNumberComputerName_::_1_::catch_19(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 376),
                           (void *)0x6C,
                           (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\computernameutils\\computernameutils.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800371bc  mov     [rsp+arg_8], rdx
0x1800371c1  push    rbp
0x1800371c2  sub     rsp, 20h
0x1800371c6  mov     rbp, rdx
0x1800371c9  mov     rcx, [rbp+178h]; this
0x1800371d0  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\dm\\dmcmnutils\\comp"...
0x1800371d7  mov     edx, 6Ch ; 'l'; void *
0x1800371dc  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800371e1  mov     [rbp+20h], eax
0x1800371e4  mov     rax, 0
0x1800371ee  add     rsp, 20h
0x1800371f2  pop     rbp
0x1800371f3  retn
```
