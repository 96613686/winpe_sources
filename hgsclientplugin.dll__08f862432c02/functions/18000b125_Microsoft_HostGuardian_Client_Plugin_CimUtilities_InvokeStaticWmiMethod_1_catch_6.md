# _Microsoft::HostGuardian::Client::Plugin::CimUtilities::InvokeStaticWmiMethod_::_1_::catch$6

- ea: `0x18000b125`
- end: `0x18000b150`
- name: `_Microsoft::HostGuardian::Client::Plugin::CimUtilities::InvokeStaticWmiMethod_::_1_::catch$6`
- size: `43`
- prototype: `__int64 __fastcall(__int64, wil::details::in1diag3 **, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a380`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Plugin::CimUtilities::InvokeStaticWmiMethod_::_1_::catch_6(
        __int64 a1,
        wil::details::in1diag3 **a2,
        unsigned int a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(a2[33], a2, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x18000b125  mov     [rsp+arg_8], rdx
0x18000b12a  push    rbp
0x18000b12b  sub     rsp, 60h
0x18000b12f  mov     rbp, rdx
0x18000b132  mov     rcx, [rbp+108h]; this
0x18000b139  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18000b13e  nop
0x18000b13f  mov     rax, 0
0x18000b149  add     rsp, 60h
0x18000b14d  pop     rbp
0x18000b14e  retn
```
