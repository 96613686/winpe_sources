# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x140006cc4`
- end: `0x140006cdd`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140005264`
- `0x140007bac`
- `0x140011cc8`
- `0x140012748`
- `0x1400138ac`

## callees

- `0x1400024b8`

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
0x140006cc4  sub     rsp, 38h
0x140006cc8  mov     rax, [rsp+38h]
0x140006ccd  mov     [rsp+38h+var_10], rax
0x140006cd2  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x140006cd7  nop
0x140006cd8  add     rsp, 38h
0x140006cdc  retn
```
