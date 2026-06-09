# _Microsoft::HostGuardian::Client::HgServicePlugin::FreeBlobData_::_1_::catch$0

- ea: `0x1800167b6`
- end: `0x1800167ec`
- name: `_Microsoft::HostGuardian::Client::HgServicePlugin::FreeBlobData_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009f0c`

## string_xrefs

- `0x1800167c7`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServicePlugin::FreeBlobData_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0xB5,
                           (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800167b6  mov     [rsp+arg_8], rdx
0x1800167bb  push    rbp
0x1800167bc  sub     rsp, 20h
0x1800167c0  mov     rbp, rdx
0x1800167c3  mov     rcx, [rbp+38h]; this
0x1800167c7  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x1800167ce  mov     edx, 0B5h; void *
0x1800167d3  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800167d8  mov     [rbp+40h], eax
0x1800167db  mov     rax, 0
0x1800167e5  add     rsp, 20h
0x1800167e9  pop     rbp
0x1800167ea  retn
```
