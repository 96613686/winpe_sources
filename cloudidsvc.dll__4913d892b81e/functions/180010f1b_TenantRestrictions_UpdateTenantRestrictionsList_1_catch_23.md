# _TenantRestrictions::UpdateTenantRestrictionsList_::_1_::catch$23

- ea: `0x180010f1b`
- end: `0x180010f54`
- name: `_TenantRestrictions::UpdateTenantRestrictionsList_::_1_::catch$23`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006cd4`

## string_xrefs

- `0x180010f2f`: `onecoreuap\ds\ext\common\ntservice\lib\tenantrestrictions.cpp`

## pseudocode

```c
__int64 __fastcall TenantRestrictions::UpdateTenantRestrictionsList_::_1_::catch_23(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 632),
                           (void *)0xED,
                           (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180010f1b  mov     [rsp+arg_8], rdx
0x180010f20  push    rbp
0x180010f21  sub     rsp, 30h
0x180010f25  mov     rbp, rdx
0x180010f28  mov     rcx, [rbp+278h]; this
0x180010f2f  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x180010f36  mov     edx, 0EDh; void *
0x180010f3b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180010f40  mov     [rbp+30h], eax
0x180010f43  mov     rax, 0
0x180010f4d  add     rsp, 30h
0x180010f51  pop     rbp
0x180010f52  retn
```
