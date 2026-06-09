# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x14000a8d4`
- end: `0x14000a8ed`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ff4e`
- `0x1400103ed`
- `0x1400105e1`
- `0x140010620`

## callees

- `0x1400036d8`

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
0x14000a8d4  sub     rsp, 48h
0x14000a8d8  mov     rax, [rsp+48h]
0x14000a8dd  mov     [rsp+48h+var_20], rax
0x14000a8e2  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x14000a8e7  nop
0x14000a8e8  add     rsp, 48h
0x14000a8ec  retn
```
