# _GetLanguagePacksToUninstall_::_1_::catch$0

- ea: `0x140010620`
- end: `0x140010656`
- name: `_GetLanguagePacksToUninstall_::_1_::catch$0`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14000a8d4`

## pseudocode

```c
__int64 __fastcall GetLanguagePacksToUninstall_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0xB3,
                           (int)"shell\\osshell\\cpls\\lpksetup\\utils\\languagepackcleanuputils.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x140010620  mov     [rsp+arg_8], rdx
0x140010625  push    rbp
0x140010626  sub     rsp, 20h
0x14001062a  mov     rbp, rdx
0x14001062d  mov     rcx, [rbp+38h]; this
0x140010631  lea     r8, aShellOsshellCp; "shell\\osshell\\cpls\\lpksetup\\utils\\"...
0x140010638  mov     edx, 0B3h; void *
0x14001063d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140010642  mov     [rbp+50h], eax
0x140010645  mov     rax, 0
0x14001064f  add     rsp, 20h
0x140010653  pop     rbp
0x140010654  retn
```
