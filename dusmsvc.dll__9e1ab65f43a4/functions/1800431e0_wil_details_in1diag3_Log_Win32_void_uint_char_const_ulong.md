# wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)

- ea: `0x1800431e0`
- end: `0x18004320b`
- name: `?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z`
- size: `43`
- prototype: `unsigned int(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180043278`
- `0x1800432bc`
- `0x180043788`
- `0x1800439f8`

## callees

- `0x180031154`

## string_xrefs

- `0x1800431f7`: `onecore\net\netprofiles\service\src\l2manager\clientlib\pluginclient.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Log_Win32(
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
  wil::details::ReportFailure_Win32<2>(
    (int)this,
    (int)a2,
    (int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\pluginclient.cpp",
    (int)a4,
    v6,
    retaddr,
    v7);
  return v4;
}

```

## disassembly

```asm
0x1800431e0  push    rbx
0x1800431e2  sub     rsp, 40h
0x1800431e6  mov     ebx, r9d
0x1800431e9  mov     rax, [rsp+48h]
0x1800431ee  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x1800431f2  mov     [rsp+48h+var_20], rax; __int64
0x1800431f7  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x1800431fe  call    ??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)
0x180043203  mov     eax, ebx
0x180043205  add     rsp, 40h
0x180043209  pop     rbx
0x18004320a  retn
```
