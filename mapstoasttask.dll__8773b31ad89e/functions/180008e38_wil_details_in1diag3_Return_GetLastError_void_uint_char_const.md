# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180008e38`
- end: `0x180008e51`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008ac0`
- `0x18000914c`

## callees

- `0x180007b34`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v5; // [rsp+20h] [rbp-18h]
  __int64 retaddr; // [rsp+38h] [rbp+0h]

  return wil::details::ReportFailure_GetLastErrorHr<1>((int)this, (int)a2, v5, retaddr);
}

```

## disassembly

```asm
0x180008e38  sub     rsp, 38h
0x180008e3c  mov     rax, [rsp+38h]
0x180008e41  mov     [rsp+38h+var_10], rax; __int64
0x180008e46  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180008e4b  nop
0x180008e4c  add     rsp, 38h
0x180008e50  retn
```
