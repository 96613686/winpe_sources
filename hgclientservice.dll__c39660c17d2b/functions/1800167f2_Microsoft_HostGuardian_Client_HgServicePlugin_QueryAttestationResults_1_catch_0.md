# _Microsoft::HostGuardian::Client::HgServicePlugin::QueryAttestationResults_::_1_::catch$0

- ea: `0x1800167f2`
- end: `0x180016828`
- name: `_Microsoft::HostGuardian::Client::HgServicePlugin::QueryAttestationResults_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009f0c`

## string_xrefs

- `0x180016803`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServicePlugin::QueryAttestationResults_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x51,
                           (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800167f2  mov     [rsp+arg_8], rdx
0x1800167f7  push    rbp
0x1800167f8  sub     rsp, 50h
0x1800167fc  mov     rbp, rdx
0x1800167ff  mov     rcx, [rbp+58h]; this
0x180016803  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x18001680a  mov     edx, 51h ; 'Q'; void *
0x18001680f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180016814  mov     [rbp+60h], eax
0x180016817  mov     rax, 0
0x180016821  add     rsp, 50h
0x180016825  pop     rbp
0x180016826  retn
```
