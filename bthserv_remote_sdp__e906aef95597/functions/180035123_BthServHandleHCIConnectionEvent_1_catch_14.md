# _BthServHandleHCIConnectionEvent_::_1_::catch$14

- ea: `0x180035123`
- end: `0x18003515a`
- name: `_BthServHandleHCIConnectionEvent_::_1_::catch$14`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800105dc`

## string_xrefs

- `0x180035137`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\bthserv.cpp`

## pseudocode

```c
__int64 __fastcall BthServHandleHCIConnectionEvent_::_1_::catch_14(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 200),
    (void *)0x55C,
    (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\bthserv.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180035123  mov     [rsp+arg_8], rdx
0x180035128  push    rbp
0x180035129  sub     rsp, 60h
0x18003512d  mov     rbp, rdx
0x180035130  mov     rcx, [rbp+0C8h]; this
0x180035137  lea     r8, aOnecoreDrivers_9; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x18003513e  mov     edx, 55Ch; void *
0x180035143  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180035148  nop
0x180035149  mov     rax, 0
0x180035153  add     rsp, 60h
0x180035157  pop     rbp
0x180035158  retn
```
