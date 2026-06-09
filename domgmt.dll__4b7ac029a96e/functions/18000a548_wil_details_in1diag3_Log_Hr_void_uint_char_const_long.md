# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18000a548`
- end: `0x18000a57d`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `53`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000ae80`

## callees

- `0x180003220`

## string_xrefs

- `0x18000a567`: `onecore\enduser\deliveryoptimization\management\dllmain.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (__int64)this,
    37,
    (__int64)"onecore\\enduser\\deliveryoptimization\\management\\dllmain.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x18000a548  sub     rsp, 48h
0x18000a54c  mov     rax, [rsp+48h]
0x18000a551  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000a556  mov     [rsp+48h+var_20], rax; __int64
0x18000a55b  mov     [rsp+48h+var_28], 0; __int64
0x18000a564  xor     r9d, r9d; int
0x18000a567  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\deliveryoptimization"...
0x18000a56e  lea     edx, [r9+25h]; int
0x18000a572  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a577  nop
0x18000a578  add     rsp, 48h
0x18000a57c  retn
```
