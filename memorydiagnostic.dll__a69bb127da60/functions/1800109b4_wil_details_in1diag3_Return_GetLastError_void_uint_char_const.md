# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x1800109b4`
- end: `0x1800109cd`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800094d4`
- `0x18000b238`
- `0x18000d448`
- `0x18000dcdc`
- `0x180014570`
- `0x18001f6ec`

## callees

- `0x18000521c`

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
0x1800109b4  sub     rsp, 38h
0x1800109b8  mov     rax, [rsp+38h]
0x1800109bd  mov     [rsp+38h+var_10], rax
0x1800109c2  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x1800109c7  nop
0x1800109c8  add     rsp, 38h
0x1800109cc  retn
```
