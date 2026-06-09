# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x18000dc34`
- end: `0x18000dc4d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x1800017e4`
- `0x180001d3c`
- `0x180002650`
- `0x180002ac0`
- `0x180002bb0`
- `0x180002ea8`
- `0x180003914`
- `0x180003e20`
- `0x180006ad0`
- `0x180006de0`
- `0x18000a914`
- `0x18000b9c4`
- `0x18000da48`
- `0x180016400`
- `0x180016d14`

## callees

- `0x180001514`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x18000dc34  sub     rsp, 38h
0x18000dc38  mov     rax, [rsp+38h]
0x18000dc3d  mov     [rsp+38h+var_10], rax
0x18000dc42  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x18000dc47  nop
0x18000dc48  add     rsp, 38h
0x18000dc4c  retn
```
