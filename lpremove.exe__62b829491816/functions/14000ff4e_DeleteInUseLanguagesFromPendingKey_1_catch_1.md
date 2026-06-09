# _DeleteInUseLanguagesFromPendingKey_::_1_::catch$1

- ea: `0x14000ff4e`
- end: `0x14000ff84`
- name: `_DeleteInUseLanguagesFromPendingKey_::_1_::catch$1`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14000a8d4`

## string_xrefs

- `0x14000ff5f`: `shell\osshell\cpls\lpksetup\lpremove\launchlpksetup.cpp`

## pseudocode

```c
__int64 __fastcall DeleteInUseLanguagesFromPendingKey_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 88) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x192,
                           (int)"shell\\osshell\\cpls\\lpksetup\\lpremove\\launchlpksetup.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x14000ff4e  mov     [rsp+arg_8], rdx
0x14000ff53  push    rbp
0x14000ff54  sub     rsp, 20h
0x14000ff58  mov     rbp, rdx
0x14000ff5b  mov     rcx, [rbp+48h]; this
0x14000ff5f  lea     r8, aShellOsshellCp_0; "shell\\osshell\\cpls\\lpksetup\\lpremov"...
0x14000ff66  mov     edx, 192h; void *
0x14000ff6b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x14000ff70  mov     [rbp+58h], eax
0x14000ff73  mov     rax, 0
0x14000ff7d  add     rsp, 20h
0x14000ff81  pop     rbp
0x14000ff82  retn
```
