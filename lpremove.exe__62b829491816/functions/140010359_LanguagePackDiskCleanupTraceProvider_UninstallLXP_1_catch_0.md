# _LanguagePackDiskCleanupTraceProvider::UninstallLXP__::_1_::catch$0

- ea: `0x140010359`
- end: `0x14001038d`
- name: `_LanguagePackDiskCleanupTraceProvider::UninstallLXP__::_1_::catch$0`
- size: `52`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140008a28`

## pseudocode

```c
__int64 __fastcall LanguagePackDiskCleanupTraceProvider::UninstallLXP__::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 120),
    (void *)0x2F,
    (unsigned int)"shell\\osshell\\cpls\\lpksetup\\utils\\LanguagePackDiskCleanupTraceLogging.h",
    a4);
  return 0;
}

```

## disassembly

```asm
0x140010359  mov     [rsp+arg_8], rdx
0x14001035e  push    rbp
0x14001035f  sub     rsp, 30h
0x140010363  mov     rbp, rdx
0x140010366  mov     rcx, [rbp+78h]; this
0x14001036a  lea     r8, aShellOsshellCp_1; "shell\\osshell\\cpls\\lpksetup\\utils\\"...
0x140010371  mov     edx, 2Fh ; '/'; void *
0x140010376  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x14001037b  nop
0x14001037c  mov     rax, 0
0x140010386  add     rsp, 30h
0x14001038a  pop     rbp
0x14001038b  retn
```
