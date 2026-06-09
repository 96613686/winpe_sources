# wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)

- ea: `0x18000eb14`
- end: `0x18000eb4e`
- name: `?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z`
- size: `58`
- prototype: `int(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800085b0`

## callees

- `0x180004e1c`

## string_xrefs

- `0x18000eb34`: `onecore\internal\sdk\inc\wil\opensource\wil\result.h`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  unsigned int v4; // ebx
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  v4 = (unsigned int)a4;
  LODWORD(v6) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    958,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result.h",
    0,
    0,
    retaddr,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000eb14  push    rbx
0x18000eb16  sub     rsp, 40h
0x18000eb1a  mov     ebx, r9d
0x18000eb1d  mov     rax, [rsp+48h]
0x18000eb22  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x18000eb26  mov     [rsp+48h+var_20], rax; __int64
0x18000eb2b  and     [rsp+48h+var_28], 0
0x18000eb31  xor     r9d, r9d; int
0x18000eb34  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000eb3b  mov     edx, 3BEh; int
0x18000eb40  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x18000eb45  mov     eax, ebx
0x18000eb47  add     rsp, 40h
0x18000eb4b  pop     rbx
0x18000eb4c  retn
```
