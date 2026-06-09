# wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)

- ea: `0x1800064d0`
- end: `0x1800064ed`
- name: `?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z`
- size: `29`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020d0`
- `0x180002b70`
- `0x180004b20`
- `0x1800060c0`
- `0x180006354`

## callees

- `0x180009488`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_Win32(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v5; // [rsp+20h] [rbp-28h]
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v6) = (_DWORD)a4;
  return wil::details::ReportFailure_Win32<1>((int)this, (int)a2, a3, (int)a4, v5, retaddr, v6);
}

```

## disassembly

```asm
0x1800064d0  sub     rsp, 48h
0x1800064d4  mov     rax, [rsp+48h]
0x1800064d9  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x1800064de  mov     [rsp+48h+var_20], rax; __int64
0x1800064e3  call    ??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)
0x1800064e8  add     rsp, 48h
0x1800064ec  retn
```
