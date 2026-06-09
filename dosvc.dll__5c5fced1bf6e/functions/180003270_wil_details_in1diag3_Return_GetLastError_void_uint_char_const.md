# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180003270`
- end: `0x180003289`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003220`
- `0x18000738c`
- `0x180008138`

## callees

- `0x1800032b4`

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
0x180003270  sub     rsp, 38h
0x180003274  mov     rax, [rsp+38h]
0x180003279  mov     [rsp+38h+var_10], rax
0x18000327e  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180003283  nop
0x180003284  add     rsp, 38h
0x180003288  retn
```
