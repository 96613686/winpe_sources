# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180005944`
- end: `0x18000595d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d44`
- `0x1800063cc`
- `0x180009140`
- `0x18000c1cc`
- `0x18000c950`

## callees

- `0x180003118`

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
0x180005944  sub     rsp, 38h
0x180005948  mov     rax, [rsp+38h]
0x18000594d  mov     [rsp+38h+var_10], rax
0x180005952  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180005957  nop
0x180005958  add     rsp, 38h
0x18000595c  retn
```
