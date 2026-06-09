# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x1400076f4`
- end: `0x14000770d`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e125`
- `0x14000e167`
- `0x14000e243`
- `0x14000e282`
- `0x14000e318`
- `0x14000e357`
- `0x14000e393`
- `0x14000e417`
- `0x14000e4df`
- `0x14000e902`
- `0x14000e941`
- `0x14000eabe`

## callees

- `0x1400023bc`

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
0x1400076f4  sub     rsp, 48h
0x1400076f8  mov     rax, [rsp+48h]
0x1400076fd  mov     [rsp+48h+var_20], rax
0x140007702  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x140007707  nop
0x140007708  add     rsp, 48h
0x14000770c  retn
```
