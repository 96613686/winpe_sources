# _GetFirmwareResourceRegPath_::_1_::catch$13

- ea: `0x180058813`
- end: `0x18005884c`
- name: `_GetFirmwareResourceRegPath_::_1_::catch$13`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800181dc`

## string_xrefs

- `0x180058827`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`

## pseudocode

```c
__int64 __fastcall GetFirmwareResourceRegPath_::_1_::catch_13(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0x6B,
                           (int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180058813  mov     [rsp+arg_8], rdx
0x180058818  push    rbp
0x180058819  sub     rsp, 30h
0x18005881d  mov     rbp, rdx
0x180058820  mov     rcx, [rbp+88h]; this
0x180058827  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18005882e  mov     edx, 6Bh ; 'k'; void *
0x180058833  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180058838  mov     [rbp+30h], eax
0x18005883b  mov     rax, 0
0x180058845  add     rsp, 30h
0x180058849  pop     rbp
0x18005884a  retn
```
