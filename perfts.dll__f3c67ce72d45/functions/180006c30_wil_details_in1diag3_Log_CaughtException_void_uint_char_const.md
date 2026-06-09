# wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)

- ea: `0x180006c30`
- end: `0x180006c49`
- name: `?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009e08`
- `0x180009e48`
- `0x180009e7e`

## callees

- `0x180003c74`

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
0x180006c30  sub     rsp, 48h
0x180006c34  mov     rax, [rsp+48h]
0x180006c39  mov     [rsp+48h+var_20], rax
0x180006c3e  call    ??$ReportFailure_CaughtException@$01@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<2>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x180006c43  nop
0x180006c44  add     rsp, 48h
0x180006c48  retn
```
