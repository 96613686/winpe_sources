# _CloudIdSvcModule::ServiceStopped_::_1_::catch$1

- ea: `0x180010bf7`
- end: `0x180010c22`
- name: `_CloudIdSvcModule::ServiceStopped_::_1_::catch$1`
- size: `43`
- prototype: `__int64 __fastcall(__int64, wil::details::in1diag3 **, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006580`

## pseudocode

```c
__int64 __fastcall CloudIdSvcModule::ServiceStopped_::_1_::catch_1(
        __int64 a1,
        wil::details::in1diag3 **a2,
        unsigned int a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(a2[39], a2, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x180010bf7  mov     [rsp+arg_8], rdx
0x180010bfc  push    rbp
0x180010bfd  sub     rsp, 20h
0x180010c01  mov     rbp, rdx
0x180010c04  mov     rcx, [rbp+138h]; this
0x180010c0b  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180010c10  nop
0x180010c11  mov     rax, 0
0x180010c1b  add     rsp, 20h
0x180010c1f  pop     rbp
0x180010c20  retn
```
