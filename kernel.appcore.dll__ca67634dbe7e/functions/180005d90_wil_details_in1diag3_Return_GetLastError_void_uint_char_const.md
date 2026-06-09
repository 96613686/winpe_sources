# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180005d90`
- end: `0x180005da8`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `24`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b70`
- `0x180003350`

## callees

- `0x180005560`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2);
}

```

## disassembly

```asm
0x180005d90  sub     rsp, 38h
0x180005d94  mov     rax, [rsp+38h]
0x180005d99  mov     [rsp+38h+var_10], rax
0x180005d9e  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180005da3  add     rsp, 38h
0x180005da7  retn
```
