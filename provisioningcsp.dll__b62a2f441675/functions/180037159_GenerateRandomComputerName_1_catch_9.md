# _GenerateRandomComputerName_::_1_::catch$9

- ea: `0x180037159`
- end: `0x180037192`
- name: `_GenerateRandomComputerName_::_1_::catch$9`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008d30`

## string_xrefs

- `0x18003716d`: `onecoreuap\admin\dm\dmcmnutils\computernameutils\computernameutils.cpp`

## pseudocode

```c
__int64 __fastcall GenerateRandomComputerName_::_1_::catch_9(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 328),
                           (void *)0x35,
                           (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\computernameutils\\computernameutils.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180037159  mov     [rsp+arg_8], rdx
0x18003715e  push    rbp
0x18003715f  sub     rsp, 20h
0x180037163  mov     rbp, rdx
0x180037166  mov     rcx, [rbp+148h]; this
0x18003716d  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\dm\\dmcmnutils\\comp"...
0x180037174  mov     edx, 35h ; '5'; void *
0x180037179  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003717e  mov     [rbp+20h], eax
0x180037181  mov     rax, 0
0x18003718b  add     rsp, 20h
0x18003718f  pop     rbp
0x180037190  retn
```
