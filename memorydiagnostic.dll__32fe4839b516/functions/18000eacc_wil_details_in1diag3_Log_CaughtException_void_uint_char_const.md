# wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)

- ea: `0x18000eacc`
- end: `0x18000eae6`
- name: `?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18002219c`
- `0x18002264e`
- `0x180022a66`
- `0x180022e03`
- `0x180022f3f`
- `0x180023023`
- `0x18002314b`

## callees

- `0x1800049c4`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Log_CaughtException(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_CaughtException<2>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x18000eacc  sub     rsp, 48h
0x18000ead0  mov     rax, [rsp+48h]
0x18000ead5  mov     [rsp+48h+var_20], rax
0x18000eada  call    ??$ReportFailure_CaughtException@$01@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<2>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x18000eadf  nop
0x18000eae0  add     rsp, 48h
0x18000eae4  retn
```
