# _Microsoft::HostGuardian::Client::HgService::Stop_::_1_::catch$6

- ea: `0x1800159d8`
- end: `0x180015a0f`
- name: `_Microsoft::HostGuardian::Client::HgService::Stop_::_1_::catch$6`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d84`

## string_xrefs

- `0x1800159ec`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgService::Stop_::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 152),
    (void *)0xCA,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800159d8  mov     [rsp+arg_8], rdx
0x1800159dd  push    rbp
0x1800159de  sub     rsp, 40h
0x1800159e2  mov     rbp, rdx
0x1800159e5  mov     rcx, [rbp+98h]; this
0x1800159ec  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x1800159f3  mov     edx, 0CAh; void *
0x1800159f8  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800159fd  nop
0x1800159fe  mov     rax, 0
0x180015a08  add     rsp, 40h
0x180015a0c  pop     rbp
0x180015a0d  retn
```
