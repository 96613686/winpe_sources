# wil::details::in1diag3::Log_NtStatus(void *,uint,char const *,long)

- ea: `0x180007c5c`
- end: `0x180007c8d`
- name: `?Log_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z`
- size: `49`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000bc38`

## callees

- `0x180004878`

## string_xrefs

- `0x180007c73`: `onecore\base\ngscb\pcrpf\dll\dll.cpp`

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
    55,
    (int)"onecore\\base\\ngscb\\pcrpf\\dll\\dll.cpp",
    (int)a4,
    v6,
    retaddr,
    v7);
  return v4;
}

```

## disassembly

```asm
0x180007c5c  push    rbx
0x180007c5e  sub     rsp, 40h
0x180007c62  mov     ebx, r9d
0x180007c65  mov     rax, [rsp+48h]
0x180007c6a  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x180007c6e  mov     [rsp+48h+var_20], rax; __int64
0x180007c73  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\pcrpf\\dll\\dll.c"...
0x180007c7a  mov     edx, 37h ; '7'; int
0x180007c7f  call    ??$ReportFailure_NtStatus@$01@details@wil@@YAJPEAXIPEBD110J@Z; wil::details::ReportFailure_NtStatus<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x180007c84  mov     eax, ebx
0x180007c86  add     rsp, 40h
0x180007c8a  pop     rbx
0x180007c8b  retn
```
