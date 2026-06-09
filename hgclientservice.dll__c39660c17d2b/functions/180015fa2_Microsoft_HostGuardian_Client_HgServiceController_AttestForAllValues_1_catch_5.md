# _Microsoft::HostGuardian::Client::HgServiceController::AttestForAllValues_::_1_::catch$5

- ea: `0x180015fa2`
- end: `0x180015fe0`
- name: `_Microsoft::HostGuardian::Client::HgServiceController::AttestForAllValues_::_1_::catch$5`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d84`
- `0x1800062c4`

## string_xrefs

- `0x180015fb6`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServiceController::AttestForAllValues_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  void *v5; // rdx
  wil *v6; // rcx
  unsigned int v7; // r8d

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 264),
    (void *)0x1DB,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
    a4);
  *(_DWORD *)(a2 + 96) = wil::ResultFromCaughtException(v6, v5, v7);
  return 0;
}

```

## disassembly

```asm
0x180015fa2  mov     [rsp+arg_8], rdx
0x180015fa7  push    rbp
0x180015fa8  sub     rsp, 40h
0x180015fac  mov     rbp, rdx
0x180015faf  mov     rcx, [rbp+108h]; this
0x180015fb6  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x180015fbd  mov     edx, 1DBh; void *
0x180015fc2  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180015fc7  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180015fcc  mov     [rbp+60h], eax
0x180015fcf  mov     rax, 0
0x180015fd9  add     rsp, 40h
0x180015fdd  pop     rbp
0x180015fde  retn
```
