# _AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::catch$24

- ea: `0x140011b5a`
- end: `0x140011b8b`
- name: `_AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::catch$24`
- size: `49`
- prototype: `__int64 __fastcall(__int64, wil::details::in1diag3 **, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14000a260`

## pseudocode

```c
__int64 __fastcall AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::catch_24(
        __int64 a1,
        wil::details::in1diag3 **a2,
        unsigned int a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(a2[131], a2, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x140011b5a  mov     [rsp+arg_8], rdx
0x140011b5f  push    rbp
0x140011b60  sub     rsp, 90h
0x140011b67  mov     rbp, rdx
0x140011b6a  mov     rcx, [rbp+418h]; this
0x140011b71  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140011b76  nop
0x140011b77  mov     rax, 0
0x140011b81  add     rsp, 90h
0x140011b88  pop     rbp
0x140011b89  retn
```
