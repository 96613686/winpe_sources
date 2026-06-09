# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180005204`
- end: `0x18000521d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800045e4`
- `0x180005c6c`

## callees

- `0x180002768`

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
0x180005204  sub     rsp, 38h
0x180005208  mov     rax, [rsp+38h]
0x18000520d  mov     [rsp+38h+var_10], rax
0x180005212  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180005217  nop
0x180005218  add     rsp, 38h
0x18000521c  retn
```
