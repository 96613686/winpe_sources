# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180005514`
- end: `0x180005536`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `34`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a34`
- `0x18000615c`
- `0x1800088dc`
- `0x18000b34c`
- `0x18000b658`
- `0x180010b08`

## callees

- `0x1800025e4`

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
0x180005514  sub     rsp, 48h
0x180005518  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x180005521  mov     rax, [rsp+48h]
0x180005526  mov     [rsp+48h+var_20], rax
0x18000552b  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180005530  nop
0x180005531  add     rsp, 48h
0x180005535  retn
```
