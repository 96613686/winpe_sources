# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x180007650`
- end: `0x180007669`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cf64`
- `0x18000cfc7`
- `0x18000d144`
- `0x18000d1a4`
- `0x18000d1f5`
- `0x18000d246`
- `0x18000d285`

## callees

- `0x18000630c`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_CaughtException(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_CaughtException<1>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x180007650  sub     rsp, 48h
0x180007654  mov     rax, [rsp+48h]
0x180007659  mov     [rsp+48h+var_20], rax
0x18000765e  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x180007663  nop
0x180007664  add     rsp, 48h
0x180007668  retn
```
