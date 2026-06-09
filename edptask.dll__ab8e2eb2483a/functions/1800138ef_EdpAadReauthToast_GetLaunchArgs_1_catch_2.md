# _EdpAadReauthToast::GetLaunchArgs_::_1_::catch$2

- ea: `0x1800138ef`
- end: `0x180013929`
- name: `_EdpAadReauthToast::GetLaunchArgs_::_1_::catch$2`
- size: `58`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056c4`

## string_xrefs

- `0x180013906`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpAadReauthToast::GetLaunchArgs_::_1_::catch_2(__int64 a1, __int64 a2)
{
  wil::details::in1diag3::Return_Hr(
    *(wil::details::in1diag3 **)(a2 + 104),
    (void *)0x28D,
    (int)"ds\\security\\efs\\edptask\\toast\\edptoast.cpp",
    (const char *)0x8007000ELL);
  return 0;
}

```

## disassembly

```asm
0x1800138ef  mov     [rsp+arg_8], rdx
0x1800138f4  push    rbp; int
0x1800138f5  sub     rsp, 20h
0x1800138f9  mov     rbp, rdx
0x1800138fc  mov     rcx, [rbp+68h]; this
0x180013900  mov     r9d, 8007000Eh; char *
0x180013906  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18001390d  mov     edx, 28Dh; void *
0x180013912  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013917  nop
0x180013918  mov     rax, 0
0x180013922  add     rsp, 20h
0x180013926  pop     rbp
0x180013927  retn
```
