# _Microsoft::HostGuardian::Client::HgService::ControlHandlerCallback_::_1_::catch$0

- ea: `0x18001598a`
- end: `0x1800159c0`
- name: `_Microsoft::HostGuardian::Client::HgService::ControlHandlerCallback_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009f0c`

## string_xrefs

- `0x18001599b`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgService::ControlHandlerCallback_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x8D,
                           (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001598a  mov     [rsp+arg_8], rdx
0x18001598f  push    rbp
0x180015990  sub     rsp, 20h
0x180015994  mov     rbp, rdx
0x180015997  mov     rcx, [rbp+28h]; this
0x18001599b  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x1800159a2  mov     edx, 8Dh; void *
0x1800159a7  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800159ac  mov     [rbp+48h], eax
0x1800159af  mov     rax, 0
0x1800159b9  add     rsp, 20h
0x1800159bd  pop     rbp
0x1800159be  retn
```
