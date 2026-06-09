# wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)

- ea: `0x18000c0bc`
- end: `0x18000c0d5`
- name: `?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bbe0`
- `0x18000bd5c`
- `0x18000bef4`
- `0x18000c08c`

## callees

- `0x18000bb44`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_Win32(
        wil::details::in1diag3 *this,
        __int64 a2,
        __int64 a3,
        const char *a4,
        unsigned int a5)
{
  int v5; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Win32<0>((__int64)this, a2, a3, (__int64)a4, v5, retaddr, (int)a4);
}

```

## disassembly

```asm
0x18000c0bc  sub     rsp, 48h
0x18000c0c0  mov     rax, [rsp+48h]
0x18000c0c5  mov     [rsp+48h+var_18], r9d
0x18000c0ca  mov     [rsp+48h+var_20], rax
0x18000c0cf  call    ??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)
```
