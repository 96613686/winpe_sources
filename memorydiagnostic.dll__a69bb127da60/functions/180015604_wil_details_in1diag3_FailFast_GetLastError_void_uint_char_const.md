# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180015604`
- end: `0x180015618`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180006fd8`
- `0x1800075d8`
- `0x1800076a4`
- `0x180007aa0`
- `0x180007b10`
- `0x180008cc8`
- `0x180009098`
- `0x18000a294`
- `0x18000a630`
- `0x18000fe8c`
- `0x18000ffa0`
- `0x1800132f0`
- `0x1800139d0`
- `0x180014030`
- `0x1800143d0`
- `0x180014570`
- `0x1800221a0`

## callees

- `0x180005124`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>(this, a2, a3, a4, v4, retaddr);
}

```

## disassembly

```asm
0x180015604  sub     rsp, 38h
0x180015608  mov     rax, [rsp+38h]
0x18001560d  mov     [rsp+38h+var_10], rax
0x180015612  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
