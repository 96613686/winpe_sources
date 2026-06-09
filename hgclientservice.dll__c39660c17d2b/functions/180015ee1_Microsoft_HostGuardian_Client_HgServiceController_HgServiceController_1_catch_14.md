# _Microsoft::HostGuardian::Client::HgServiceController::_HgServiceController_::_1_::catch$14

- ea: `0x180015ee1`
- end: `0x180015f15`
- name: `_Microsoft::HostGuardian::Client::HgServiceController::_HgServiceController_::_1_::catch$14`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d84`

## string_xrefs

- `0x180015ef2`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServiceController::_HgServiceController_::_1_::catch_14(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 120),
    (void *)0x1E,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180015ee1  mov     [rsp+arg_8], rdx
0x180015ee6  push    rbp
0x180015ee7  sub     rsp, 30h
0x180015eeb  mov     rbp, rdx
0x180015eee  mov     rcx, [rbp+78h]; this
0x180015ef2  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x180015ef9  mov     edx, 1Eh; void *
0x180015efe  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180015f03  nop
0x180015f04  mov     rax, 0
0x180015f0e  add     rsp, 30h
0x180015f12  pop     rbp
0x180015f13  retn
```
