# _InstalledPackageNode::Remove_::_1_::catch$10

- ea: `0x180036133`
- end: `0x180036169`
- name: `_InstalledPackageNode::Remove_::_1_::catch$10`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180008d30`

## string_xrefs

- `0x180036144`: `onecoreuap\admin\prov\provcsp\installedpackagenode.cpp`

## pseudocode

```c
__int64 __fastcall InstalledPackageNode::Remove_::_1_::catch_10(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 104) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 88),
                            (void *)0x52,
                            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\installedpackagenode.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180036133  mov     [rsp+arg_8], rdx
0x180036138  push    rbp
0x180036139  sub     rsp, 30h
0x18003613d  mov     rbp, rdx
0x180036140  mov     rcx, [rbp+58h]; this
0x180036144  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\prov\\provcsp\\insta"...
0x18003614b  mov     edx, 52h ; 'R'; void *
0x180036150  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180036155  mov     [rbp+68h], eax
0x180036158  mov     rax, 0
0x180036162  add     rsp, 30h
0x180036166  pop     rbp
0x180036167  retn
```
