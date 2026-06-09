# _Microsoft::HostGuardian::Client::HgServicePlugin::UnwrapKeyProtector_::_1_::catch$0

- ea: `0x18001682e`
- end: `0x180016864`
- name: `_Microsoft::HostGuardian::Client::HgServicePlugin::UnwrapKeyProtector_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009f0c`

## string_xrefs

- `0x18001683f`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServicePlugin::UnwrapKeyProtector_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x8B,
                           (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001682e  mov     [rsp+arg_8], rdx
0x180016833  push    rbp
0x180016834  sub     rsp, 40h
0x180016838  mov     rbp, rdx
0x18001683b  mov     rcx, [rbp+58h]; this
0x18001683f  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x180016846  mov     edx, 8Bh; void *
0x18001684b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180016850  mov     [rbp+60h], eax
0x180016853  mov     rax, 0
0x18001685d  add     rsp, 40h
0x180016861  pop     rbp
0x180016862  retn
```
