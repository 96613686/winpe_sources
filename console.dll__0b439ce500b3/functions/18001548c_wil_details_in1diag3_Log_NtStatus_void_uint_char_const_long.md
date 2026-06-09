# wil::details::in1diag3::Log_NtStatus(void *,uint,char const *,long)

- ea: `0x18001548c`
- end: `0x1800154bd`
- name: `?Log_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z`
- size: `49`
- prototype: `int(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180017368`

## callees

- `0x180006df8`

## string_xrefs

- `0x1800154a3`: `onecore\windows\core\console\open\src\propslib\delegationconfig.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Log_NtStatus(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-28h]
  wil::details *v7; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  v4 = (unsigned int)a4;
  LODWORD(v7) = (_DWORD)a4;
  wil::details::ReportFailure_NtStatus<2>(
    (int)this,
    261,
    (int)"onecore\\windows\\core\\console\\open\\src\\propslib\\delegationconfig.cpp",
    (int)a4,
    v6,
    retaddr,
    v7);
  return v4;
}

```

## disassembly

```asm
0x18001548c  push    rbx
0x18001548e  sub     rsp, 40h
0x180015492  mov     ebx, r9d
0x180015495  mov     rax, [rsp+48h]
0x18001549a  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x18001549e  mov     [rsp+48h+var_20], rax; __int64
0x1800154a3  lea     r8, aOnecoreWindows; "onecore\\windows\\core\\console\\open\\"...
0x1800154aa  mov     edx, 105h; int
0x1800154af  call    ??$ReportFailure_NtStatus@$01@details@wil@@YAJPEAXIPEBD110J@Z; wil::details::ReportFailure_NtStatus<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x1800154b4  mov     eax, ebx
0x1800154b6  add     rsp, 40h
0x1800154ba  pop     rbx
0x1800154bb  retn
```
