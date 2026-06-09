# _Microsoft::HostGuardian::Client::HgServicePlugin::EncryptWithKeyProtector_::_1_::catch$0

- ea: `0x18001673e`
- end: `0x180016774`
- name: `_Microsoft::HostGuardian::Client::HgServicePlugin::EncryptWithKeyProtector_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009f0c`

## string_xrefs

- `0x18001674f`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServicePlugin::EncryptWithKeyProtector_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 112) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 104),
                            (void *)0x9F,
                            (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18001673e  mov     [rsp+arg_8], rdx
0x180016743  push    rbp
0x180016744  sub     rsp, 40h
0x180016748  mov     rbp, rdx
0x18001674b  mov     rcx, [rbp+68h]; this
0x18001674f  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x180016756  mov     edx, 9Fh; void *
0x18001675b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180016760  mov     [rbp+70h], eax
0x180016763  mov     rax, 0
0x18001676d  add     rsp, 40h
0x180016771  pop     rbp
0x180016772  retn
```
