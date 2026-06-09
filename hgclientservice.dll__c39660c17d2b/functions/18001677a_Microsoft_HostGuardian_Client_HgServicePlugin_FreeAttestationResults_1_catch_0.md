# _Microsoft::HostGuardian::Client::HgServicePlugin::FreeAttestationResults_::_1_::catch$0

- ea: `0x18001677a`
- end: `0x1800167b0`
- name: `_Microsoft::HostGuardian::Client::HgServicePlugin::FreeAttestationResults_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009f0c`

## string_xrefs

- `0x18001678b`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServicePlugin::FreeAttestationResults_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x79,
                           (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001677a  mov     [rsp+arg_8], rdx
0x18001677f  push    rbp
0x180016780  sub     rsp, 30h
0x180016784  mov     rbp, rdx
0x180016787  mov     rcx, [rbp+38h]; this
0x18001678b  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x180016792  mov     edx, 79h ; 'y'; void *
0x180016797  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001679c  mov     [rbp+40h], eax
0x18001679f  mov     rax, 0
0x1800167a9  add     rsp, 30h
0x1800167ad  pop     rbp
0x1800167ae  retn
```
