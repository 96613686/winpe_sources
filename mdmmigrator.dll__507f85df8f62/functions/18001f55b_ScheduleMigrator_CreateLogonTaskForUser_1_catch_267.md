# _ScheduleMigrator::CreateLogonTaskForUser_::_1_::catch$267

- ea: `0x18001f55b`
- end: `0x18001f597`
- name: `_ScheduleMigrator::CreateLogonTaskForUser_::_1_::catch$267`
- size: `60`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800094bc`

## pseudocode

```c
__int64 __fastcall ScheduleMigrator::CreateLogonTaskForUser_::_1_::catch_267(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 152) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 1064),
                            (void *)0x10A,
                            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\schedulemigrator.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18001f55b  mov     [rsp+arg_8], rdx
0x18001f560  push    rbp
0x18001f561  sub     rsp, 50h
0x18001f565  mov     rbp, rdx
0x18001f568  mov     rcx, [rbp+428h]; this
0x18001f56f  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18001f576  mov     edx, 10Ah; void *
0x18001f57b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001f580  mov     [rbp+98h], eax
0x18001f586  mov     rax, 0
0x18001f590  add     rsp, 50h
0x18001f594  pop     rbp
0x18001f595  retn
```
