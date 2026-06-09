# _BitLockerCompatibilityCheck_::_1_::catch$32

- ea: `0x180020a98`
- end: `0x180020ad1`
- name: `_BitLockerCompatibilityCheck_::_1_::catch$32`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010994`

## pseudocode

```c
__int64 __fastcall BitLockerCompatibilityCheck_::_1_::catch_32(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 52) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 248),
                           (void *)0x510,
                           (int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180020a98  mov     [rsp+arg_8], rdx
0x180020a9d  push    rbp
0x180020a9e  sub     rsp, 30h
0x180020aa2  mov     rbp, rdx
0x180020aa5  mov     rcx, [rbp+0F8h]; this
0x180020aac  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x180020ab3  mov     edx, 510h; void *
0x180020ab8  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180020abd  mov     [rbp+34h], eax
0x180020ac0  mov     rax, 0
0x180020aca  add     rsp, 30h
0x180020ace  pop     rbp
0x180020acf  retn
```
