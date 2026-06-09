# _BitLockerCompatibilityCheck_::_1_::catch$32

- ea: `0x180022242`
- end: `0x18002227b`
- name: `_BitLockerCompatibilityCheck_::_1_::catch$32`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011364`

## pseudocode

```c
__int64 __fastcall BitLockerCompatibilityCheck_::_1_::catch_32(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 52) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 296),
                           (void *)0x56F,
                           (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180022242  mov     [rsp+arg_8], rdx
0x180022247  push    rbp
0x180022248  sub     rsp, 30h
0x18002224c  mov     rbp, rdx
0x18002224f  mov     rcx, [rbp+128h]; this
0x180022256  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18002225d  mov     edx, 56Fh; void *
0x180022262  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180022267  mov     [rbp+34h], eax
0x18002226a  mov     rax, 0
0x180022274  add     rsp, 30h
0x180022278  pop     rbp
0x180022279  retn
```
