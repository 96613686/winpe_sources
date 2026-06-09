# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x1800081a4`
- end: `0x1800081bd`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005d94`
- `0x18000969c`
- `0x1800106c0`
- `0x180010f30`

## callees

- `0x180003004`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2, a3);
}

```

## disassembly

```asm
0x1800081a4  sub     rsp, 38h
0x1800081a8  mov     rax, [rsp+38h]
0x1800081ad  mov     [rsp+38h+var_10], rax
0x1800081b2  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x1800081b7  nop
0x1800081b8  add     rsp, 38h
0x1800081bc  retn
```
