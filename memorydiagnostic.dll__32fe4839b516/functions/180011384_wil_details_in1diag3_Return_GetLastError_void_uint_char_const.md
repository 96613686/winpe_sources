# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180011384`
- end: `0x18001139e`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180009504`
- `0x18000b3e0`
- `0x18000dbc8`
- `0x18000e790`
- `0x1800152b8`
- `0x180020c20`

## callees

- `0x180004cf8`

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
0x180011384  sub     rsp, 38h
0x180011388  mov     rax, [rsp+38h]
0x18001138d  mov     [rsp+38h+var_10], rax
0x180011392  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180011397  nop
0x180011398  add     rsp, 38h
0x18001139c  retn
```
