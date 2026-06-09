# _Microsoft::HostGuardian::Client::VsmCaAgent::CaTrustletMonitorThread_::_1_::catch$13

- ea: `0x18001661e`
- end: `0x180016652`
- name: `_Microsoft::HostGuardian::Client::VsmCaAgent::CaTrustletMonitorThread_::_1_::catch$13`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d84`

## string_xrefs

- `0x18001662f`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::VsmCaAgent::CaTrustletMonitorThread_::_1_::catch_13(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 120),
    (void *)0x195,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18001661e  mov     [rsp+arg_8], rdx
0x180016623  push    rbp
0x180016624  sub     rsp, 30h
0x180016628  mov     rbp, rdx
0x18001662b  mov     rcx, [rbp+78h]; this
0x18001662f  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180016636  mov     edx, 195h; void *
0x18001663b  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180016640  nop
0x180016641  mov     rax, 0
0x18001664b  add     rsp, 30h
0x18001664f  pop     rbp
0x180016650  retn
```
