# _InstalledPackageNode::RuntimeClassInitialize_::_1_::catch$4

- ea: `0x180036193`
- end: `0x1800361cc`
- name: `_InstalledPackageNode::RuntimeClassInitialize_::_1_::catch$4`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180008d30`

## string_xrefs

- `0x1800361a7`: `onecoreuap\admin\prov\provcsp\installedpackagenode.cpp`

## pseudocode

```c
__int64 __fastcall InstalledPackageNode::RuntimeClassInitialize_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 168),
                           (void *)0x3F,
                           (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\installedpackagenode.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180036193  mov     [rsp+arg_8], rdx
0x180036198  push    rbp
0x180036199  sub     rsp, 20h
0x18003619d  mov     rbp, rdx
0x1800361a0  mov     rcx, [rbp+0A8h]; this
0x1800361a7  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\prov\\provcsp\\insta"...
0x1800361ae  mov     edx, 3Fh ; '?'; void *
0x1800361b3  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800361b8  mov     [rbp+20h], eax
0x1800361bb  mov     rax, 0
0x1800361c5  add     rsp, 20h
0x1800361c9  pop     rbp
0x1800361ca  retn
```
