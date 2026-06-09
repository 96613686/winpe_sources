# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x1800079c0`
- end: `0x1800079da`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d62a`
- `0x18000d68d`
- `0x18000d810`
- `0x18000d870`
- `0x18000d8c1`
- `0x18000d912`
- `0x18000d951`

## callees

- `0x18000660c`

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
0x1800079c0  sub     rsp, 48h
0x1800079c4  mov     rax, [rsp+48h]
0x1800079c9  mov     [rsp+48h+var_20], rax
0x1800079ce  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x1800079d3  nop
0x1800079d4  add     rsp, 48h
0x1800079d8  retn
```
