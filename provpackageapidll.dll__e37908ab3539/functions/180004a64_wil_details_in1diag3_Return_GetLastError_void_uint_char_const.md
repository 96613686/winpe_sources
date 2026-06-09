# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180004a64`
- end: `0x180004a7d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ff4`
- `0x18000555c`
- `0x18001176c`
- `0x180013040`
- `0x180013400`

## callees

- `0x18000241c`

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
0x180004a64  sub     rsp, 38h
0x180004a68  mov     rax, [rsp+38h]
0x180004a6d  mov     [rsp+38h+var_10], rax
0x180004a72  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180004a77  nop
0x180004a78  add     rsp, 38h
0x180004a7c  retn
```
