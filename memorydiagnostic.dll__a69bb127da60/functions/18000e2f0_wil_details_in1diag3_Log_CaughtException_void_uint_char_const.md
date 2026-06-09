# wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)

- ea: `0x18000e2f0`
- end: `0x18000e309`
- name: `?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800209f2`
- `0x180020d22`
- `0x180021130`
- `0x18002143d`
- `0x180021578`
- `0x180021655`
- `0x18002176f`

## callees

- `0x180004ef4`

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
0x18000e2f0  sub     rsp, 48h
0x18000e2f4  mov     rax, [rsp+48h]
0x18000e2f9  mov     [rsp+48h+var_20], rax
0x18000e2fe  call    ??$ReportFailure_CaughtException@$01@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<2>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x18000e303  nop
0x18000e304  add     rsp, 48h
0x18000e308  retn
```
