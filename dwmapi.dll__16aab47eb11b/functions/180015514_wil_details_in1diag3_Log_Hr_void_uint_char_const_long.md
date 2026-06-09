# wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)

- ea: `0x180015514`
- end: `0x180015550`
- name: `?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z`
- size: `60`
- prototype: `int(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007ae0`
- `0x18000b05c`

## callees

- `0x180004ff4`

## string_xrefs

- `0x18001551f`: `onecoreuap\windows\DWM\common\shared\lpcshared.h`

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
    328,
    (int)"onecoreuap\\windows\\DWM\\common\\shared\\lpcshared.h",
    0,
    0,
    retaddr,
    v6);
  return v4;
}

```

## disassembly

```asm
0x180015514  push    rbx
0x180015516  sub     rsp, 40h
0x18001551a  mov     rax, [rsp+48h]
0x18001551f  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\DWM\\common\\share"...
0x180015526  mov     ebx, r9d
0x180015529  mov     edx, 148h; int
0x18001552e  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x180015532  xor     r9d, r9d; int
0x180015535  mov     [rsp+48h+var_20], rax; __int64
0x18001553a  mov     [rsp+48h+var_28], 0; __int64
0x180015543  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180015548  mov     eax, ebx
0x18001554a  add     rsp, 40h
0x18001554e  pop     rbx
0x18001554f  retn
```
