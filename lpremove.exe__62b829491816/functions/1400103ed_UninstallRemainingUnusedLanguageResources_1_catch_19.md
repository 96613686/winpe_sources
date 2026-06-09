# _UninstallRemainingUnusedLanguageResources_::_1_::catch$19

- ea: `0x1400103ed`
- end: `0x140010426`
- name: `_UninstallRemainingUnusedLanguageResources_::_1_::catch$19`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14000a8d4`

## string_xrefs

- `0x140010401`: `shell\osshell\cpls\lpksetup\lpremove\launchlpksetup.cpp`

## pseudocode

```c
__int64 __fastcall UninstallRemainingUnusedLanguageResources_::_1_::catch_19(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 264),
                           (void *)0x1E6,
                           (int)"shell\\osshell\\cpls\\lpksetup\\lpremove\\launchlpksetup.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1400103ed  mov     [rsp+arg_8], rdx
0x1400103f2  push    rbp
0x1400103f3  sub     rsp, 30h
0x1400103f7  mov     rbp, rdx
0x1400103fa  mov     rcx, [rbp+108h]; this
0x140010401  lea     r8, aShellOsshellCp_0; "shell\\osshell\\cpls\\lpksetup\\lpremov"...
0x140010408  mov     edx, 1E6h; void *
0x14001040d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140010412  mov     [rbp+30h], eax
0x140010415  mov     rax, 0
0x14001041f  add     rsp, 30h
0x140010423  pop     rbp
0x140010424  retn
```
