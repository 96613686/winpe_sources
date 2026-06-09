# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x1800068b4`
- end: `0x1800068cd`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a14`
- `0x18000742c`

## callees

- `0x180002330`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2);
}

```

## disassembly

```asm
0x1800068b4  sub     rsp, 38h
0x1800068b8  mov     rax, [rsp+38h]
0x1800068bd  mov     [rsp+38h+var_10], rax
0x1800068c2  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x1800068c7  nop
0x1800068c8  add     rsp, 38h
0x1800068cc  retn
```
