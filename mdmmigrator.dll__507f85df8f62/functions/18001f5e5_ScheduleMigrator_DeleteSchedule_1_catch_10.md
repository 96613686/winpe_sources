# _ScheduleMigrator::DeleteSchedule_::_1_::catch$10

- ea: `0x18001f5e5`
- end: `0x18001f61e`
- name: `_ScheduleMigrator::DeleteSchedule_::_1_::catch$10`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800094bc`

## pseudocode

```c
__int64 __fastcall ScheduleMigrator::DeleteSchedule_::_1_::catch_10(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 216),
                           (void *)0x8E,
                           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\schedulemigrator.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001f5e5  mov     [rsp+arg_8], rdx
0x18001f5ea  push    rbp
0x18001f5eb  sub     rsp, 30h
0x18001f5ef  mov     rbp, rdx
0x18001f5f2  mov     rcx, [rbp+0D8h]; this
0x18001f5f9  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18001f600  mov     edx, 8Eh; void *
0x18001f605  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001f60a  mov     [rbp+30h], eax
0x18001f60d  mov     rax, 0
0x18001f617  add     rsp, 30h
0x18001f61b  pop     rbp
0x18001f61c  retn
```
