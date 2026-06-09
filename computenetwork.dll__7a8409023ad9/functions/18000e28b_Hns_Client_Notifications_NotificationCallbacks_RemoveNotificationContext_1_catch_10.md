# _Hns::Client::Notifications::NotificationCallbacks::RemoveNotificationContext_::_1_::catch$10

- ea: `0x18000e28b`
- end: `0x18000e2d3`
- name: `_Hns::Client::Notifications::NotificationCallbacks::RemoveNotificationContext_::_1_::catch$10`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006864`
- `0x18000a3c8`

## string_xrefs

- `0x18000e2b0`: `onecore\vm\dv\net\hns\computenetwork\src\notificationcallbacks.cpp`

## pseudocode

```c
__int64 __fastcall Hns::Client::Notifications::NotificationCallbacks::RemoveNotificationContext_::_1_::catch_10(
        wil *a1,
        __int64 a2)
{
  unsigned int v3; // eax
  const char *v5; // [rsp+28h] [rbp-10h]

  v3 = wil::ResultFromCaughtException(a1);
  wil::details::in1diag3::Log_HrMsg(
    *(wil::details::in1diag3 **)(a2 + 120),
    (void *)0xB9,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\notificationcallbacks.cpp",
    (const char *)v3,
    (int)"Unregister notification failed",
    v5);
  return 0;
}

```

## disassembly

```asm
0x18000e28b  mov     [rsp+arg_8], rdx
0x18000e290  push    rbp
0x18000e291  sub     rsp, 30h
0x18000e295  mov     rbp, rdx
0x18000e298  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18000e29d  mov     rcx, [rbp+78h]; this
0x18000e2a1  lea     rdx, aUnregisterNoti; "Unregister notification failed"
0x18000e2a8  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18000e2ad  mov     r9d, eax; char *
0x18000e2b0  lea     r8, aOnecoreVmDvNet_1; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x18000e2b7  mov     edx, 0B9h; void *
0x18000e2bc  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000e2c1  nop
0x18000e2c2  mov     rax, 0
0x18000e2cc  add     rsp, 30h
0x18000e2d0  pop     rbp
0x18000e2d1  retn
```
