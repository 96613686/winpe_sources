# _AsyncEventDispatcher::Dispatch_::_1_::catch$7

- ea: `0x18003f880`
- end: `0x18003f8b6`
- name: `_AsyncEventDispatcher::Dispatch_::_1_::catch$7`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x18001bfbc`

## string_xrefs

- `0x18003f891`: `onecore\net\netprofiles\service\src\public\lib\asynceventdispatcher.cpp`

## pseudocode

```c
__int64 __fastcall AsyncEventDispatcher::Dispatch_::_1_::catch_7(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 104),
                           (void *)0x70,
                           (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\asynceventdispatcher.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18003f880  mov     [rsp+arg_8], rdx
0x18003f885  push    rbp
0x18003f886  sub     rsp, 20h
0x18003f88a  mov     rbp, rdx
0x18003f88d  mov     rcx, [rbp+68h]; this
0x18003f891  lea     r8, aOnecoreNetNetp_9; "onecore\\net\\netprofiles\\service\\src"...
0x18003f898  mov     edx, 70h ; 'p'; void *
0x18003f89d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003f8a2  mov     [rbp+20h], eax
0x18003f8a5  mov     rax, 0
0x18003f8af  add     rsp, 20h
0x18003f8b3  pop     rbp
0x18003f8b4  retn
```
