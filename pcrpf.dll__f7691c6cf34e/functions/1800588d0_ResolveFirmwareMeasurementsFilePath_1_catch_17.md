# _ResolveFirmwareMeasurementsFilePath_::_1_::catch$17

- ea: `0x1800588d0`
- end: `0x180058909`
- name: `_ResolveFirmwareMeasurementsFilePath_::_1_::catch$17`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800181dc`

## string_xrefs

- `0x1800588e4`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`

## pseudocode

```c
__int64 __fastcall ResolveFirmwareMeasurementsFilePath_::_1_::catch_17(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 712),
                           (void *)0x4B,
                           (int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800588d0  mov     [rsp+arg_8], rdx
0x1800588d5  push    rbp
0x1800588d6  sub     rsp, 20h
0x1800588da  mov     rbp, rdx
0x1800588dd  mov     rcx, [rbp+2C8h]; this
0x1800588e4  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x1800588eb  mov     edx, 4Bh ; 'K'; void *
0x1800588f0  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800588f5  mov     [rbp+20h], eax
0x1800588f8  mov     rax, 0
0x180058902  add     rsp, 20h
0x180058906  pop     rbp
0x180058907  retn
```
