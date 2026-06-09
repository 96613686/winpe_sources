# _InitializeTenantRestrictionsUpdates_::_1_::catch$1

- ea: `0x180010dbf`
- end: `0x180010df5`
- name: `_InitializeTenantRestrictionsUpdates_::_1_::catch$1`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006cd4`

## string_xrefs

- `0x180010dd0`: `onecoreuap\ds\ext\common\ntservice\lib\tenantrestrictions.cpp`

## pseudocode

```c
__int64 __fastcall InitializeTenantRestrictionsUpdates_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x2A,
                           (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180010dbf  mov     [rsp+arg_8], rdx
0x180010dc4  push    rbp
0x180010dc5  sub     rsp, 40h
0x180010dc9  mov     rbp, rdx
0x180010dcc  mov     rcx, [rbp+48h]; this
0x180010dd0  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x180010dd7  mov     edx, 2Ah ; '*'; void *
0x180010ddc  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180010de1  mov     [rbp+50h], eax
0x180010de4  mov     rax, 0
0x180010dee  add     rsp, 40h
0x180010df2  pop     rbp
0x180010df3  retn
```
