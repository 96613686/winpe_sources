# _CloudIdSvcModule::ServiceStarted_::_1_::catch$1

- ea: `0x180010bb8`
- end: `0x180010bf1`
- name: `_CloudIdSvcModule::ServiceStarted_::_1_::catch$1`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006cd4`

## string_xrefs

- `0x180010bcc`: `onecoreuap\ds\ext\common\ntservice\svc\cloudidsvc.cpp`

## pseudocode

```c
__int64 __fastcall CloudIdSvcModule::ServiceStarted_::_1_::catch_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 376),
                           (void *)0x38,
                           (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\svc\\cloudidsvc.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180010bb8  mov     [rsp+arg_8], rdx
0x180010bbd  push    rbp
0x180010bbe  sub     rsp, 30h
0x180010bc2  mov     rbp, rdx
0x180010bc5  mov     rcx, [rbp+178h]; this
0x180010bcc  lea     r8, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x180010bd3  mov     edx, 38h ; '8'; void *
0x180010bd8  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180010bdd  mov     [rbp+30h], eax
0x180010be0  mov     rax, 0
0x180010bea  add     rsp, 30h
0x180010bee  pop     rbp
0x180010bef  retn
```
