# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x140011a14`
- end: `0x140011a45`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `49`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140010ac0`

## callees

- `0x14000453c`

## string_xrefs

- `0x140011a33`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    (int)a2,
    (int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x140011a14  sub     rsp, 48h
0x140011a18  mov     rax, [rsp+48h]
0x140011a1d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140011a22  mov     [rsp+48h+var_20], rax; __int64
0x140011a27  mov     [rsp+48h+var_28], 0; __int64
0x140011a30  xor     r9d, r9d; int
0x140011a33  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140011a3a  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140011a3f  nop
0x140011a40  add     rsp, 48h
0x140011a44  retn
```
