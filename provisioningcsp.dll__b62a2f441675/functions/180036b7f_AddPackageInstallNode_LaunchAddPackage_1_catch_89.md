# _AddPackageInstallNode::LaunchAddPackage_::_1_::catch$89

- ea: `0x180036b7f`
- end: `0x180036bb8`
- name: `_AddPackageInstallNode::LaunchAddPackage_::_1_::catch$89`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180008d30`

## string_xrefs

- `0x180036b93`: `onecoreuap\admin\prov\provcsp\addpackageinstallnode.cpp`

## pseudocode

```c
__int64 __fastcall AddPackageInstallNode::LaunchAddPackage_::_1_::catch_89(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 392),
                           (void *)0x93,
                           (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180036b7f  mov     [rsp+arg_8], rdx
0x180036b84  push    rbp
0x180036b85  sub     rsp, 40h
0x180036b89  mov     rbp, rdx
0x180036b8c  mov     rcx, [rbp+188h]; this
0x180036b93  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\provcsp\\addpa"...
0x180036b9a  mov     edx, 93h; void *
0x180036b9f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180036ba4  mov     [rbp+60h], eax
0x180036ba7  mov     rax, 0
0x180036bb1  add     rsp, 40h
0x180036bb5  pop     rbp
0x180036bb6  retn
```
