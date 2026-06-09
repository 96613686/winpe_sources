# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x140004d34`
- end: `0x140004d4c`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `24`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003cf0`
- `0x140005298`

## callees

- `0x140001fb4`

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
0x140004d34  sub     rsp, 38h
0x140004d38  mov     rax, [rsp+38h]
0x140004d3d  mov     [rsp+38h+var_10], rax
0x140004d42  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x140004d47  add     rsp, 38h
0x140004d4b  retn
```
