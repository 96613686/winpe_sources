# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x18000b604`
- end: `0x18000b61d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a58c`
- `0x18000b9d0`

## callees

- `0x18000902c`

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
0x18000b604  sub     rsp, 38h
0x18000b608  mov     rax, [rsp+38h]
0x18000b60d  mov     [rsp+38h+var_10], rax
0x18000b612  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x18000b617  add     rsp, 38h
0x18000b61b  retn
```
