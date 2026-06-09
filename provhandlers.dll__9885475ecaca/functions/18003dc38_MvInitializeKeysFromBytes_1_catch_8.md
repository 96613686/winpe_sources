# _MvInitializeKeysFromBytes_::_1_::catch$8

- ea: `0x18003dc38`
- end: `0x18003dc71`
- name: `_MvInitializeKeysFromBytes_::_1_::catch$8`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001190c`

## string_xrefs

- `0x18003dc49`: `onecoreuap\admin\prov\multivariant\common\src\mvprovisiondatahelper.cpp`

## pseudocode

```c
__int64 __fastcall MvInitializeKeysFromBytes_::_1_::catch_8(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 144) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 120),
                            (void *)0x116,
                            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvprovisiondatahelper.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18003dc38  mov     [rsp+arg_8], rdx
0x18003dc3d  push    rbp
0x18003dc3e  sub     rsp, 30h
0x18003dc42  mov     rbp, rdx
0x18003dc45  mov     rcx, [rbp+78h]; this
0x18003dc49  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18003dc50  mov     edx, 116h; void *
0x18003dc55  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003dc5a  mov     [rbp+90h], eax
0x18003dc60  mov     rax, 0
0x18003dc6a  add     rsp, 30h
0x18003dc6e  pop     rbp
0x18003dc6f  retn
```
