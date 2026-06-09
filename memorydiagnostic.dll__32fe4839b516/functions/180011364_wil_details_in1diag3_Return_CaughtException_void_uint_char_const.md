# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x180011364`
- end: `0x18001137e`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180022242`
- `0x180022281`
- `0x1800222f3`
- `0x180022341`
- `0x180022380`
- `0x18002260c`
- `0x180022688`
- `0x180022a2a`
- `0x180022bf6`
- `0x180022c35`
- `0x180022ccb`
- `0x180022d40`
- `0x180022db5`
- `0x180022e3d`
- `0x180022e79`
- `0x180022ed9`
- `0x1800236e4`

## callees

- `0x18000487c`

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
0x180011364  sub     rsp, 48h
0x180011368  mov     rax, [rsp+48h]
0x18001136d  mov     [rsp+48h+var_20], rax
0x180011372  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x180011377  nop
0x180011378  add     rsp, 48h
0x18001137c  retn
```
