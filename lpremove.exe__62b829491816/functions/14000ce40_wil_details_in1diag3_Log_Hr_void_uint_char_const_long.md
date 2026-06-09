# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x14000ce40`
- end: `0x14000ce71`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `49`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140003260`
- `0x14000c36c`
- `0x14000d8b8`

## callees

- `0x140003b10`

## string_xrefs

- `0x14000ce5f`: `shell\osshell\cpls\lpksetup\lpremove\launchlpksetup.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (__int64)this,
    (int)a2,
    (__int64)"shell\\osshell\\cpls\\lpksetup\\lpremove\\launchlpksetup.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x14000ce40  sub     rsp, 48h
0x14000ce44  mov     rax, [rsp+48h]
0x14000ce49  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x14000ce4e  mov     [rsp+48h+var_20], rax; __int64
0x14000ce53  mov     [rsp+48h+var_28], 0; __int64
0x14000ce5c  xor     r9d, r9d; int
0x14000ce5f  lea     r8, aShellOsshellCp_0; "shell\\osshell\\cpls\\lpksetup\\lpremov"...
0x14000ce66  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000ce6b  nop
0x14000ce6c  add     rsp, 48h
0x14000ce70  retn
```
