# _Microsoft::HostGuardian::Client::HgServiceController::AddCertificatesToCache_::_1_::catch$5

- ea: `0x180015f3f`
- end: `0x180015f78`
- name: `_Microsoft::HostGuardian::Client::HgServiceController::AddCertificatesToCache_::_1_::catch$5`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009f0c`

## string_xrefs

- `0x180015f53`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServiceController::AddCertificatesToCache_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 216),
                           (void *)0x1AC,
                           (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180015f3f  mov     [rsp+arg_8], rdx
0x180015f44  push    rbp
0x180015f45  sub     rsp, 30h
0x180015f49  mov     rbp, rdx
0x180015f4c  mov     rcx, [rbp+0D8h]; this
0x180015f53  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x180015f5a  mov     edx, 1ACh; void *
0x180015f5f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180015f64  mov     [rbp+30h], eax
0x180015f67  mov     rax, 0
0x180015f71  add     rsp, 30h
0x180015f75  pop     rbp
0x180015f76  retn
```
