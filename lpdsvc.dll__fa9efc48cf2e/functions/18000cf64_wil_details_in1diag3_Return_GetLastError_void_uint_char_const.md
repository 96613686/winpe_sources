# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x18000cf64`
- end: `0x18000cf7c`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `24`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c520`
- `0x18000d36c`

## callees

- `0x18000ac70`

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
0x18000cf64  sub     rsp, 38h
0x18000cf68  mov     rax, [rsp+38h]
0x18000cf6d  mov     [rsp+38h+var_10], rax
0x18000cf72  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x18000cf77  add     rsp, 38h
0x18000cf7b  retn
```
