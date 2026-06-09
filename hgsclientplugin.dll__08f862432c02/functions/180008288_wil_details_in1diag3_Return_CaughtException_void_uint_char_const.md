# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x180008288`
- end: `0x1800082a1`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000adb2`
- `0x18000ade7`
- `0x18000ae1c`
- `0x18000ae51`
- `0x18000ae86`
- `0x18000aef7`
- `0x18000af53`
- `0x18000af8b`
- `0x18000afc0`

## callees

- `0x180007080`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_CaughtException(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v5; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  return wil::details::ReportFailure_CaughtException<1>((int)this, (int)a2, a3, (__int64)a4, v5, retaddr);
}

```

## disassembly

```asm
0x180008288  sub     rsp, 48h
0x18000828c  mov     rax, [rsp+48h]
0x180008291  mov     [rsp+48h+var_20], rax
0x180008296  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x18000829b  nop
0x18000829c  add     rsp, 48h
0x1800082a0  retn
```
