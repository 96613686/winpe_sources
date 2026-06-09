# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x180006a14`
- end: `0x180006a2d`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `56`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d218`
- `0x18000d25f`
- `0x18000d2a6`
- `0x18000d2ed`
- `0x18000d322`
- `0x18000d357`
- `0x18000d38c`
- `0x18000d3c1`
- `0x18000d3f6`
- `0x18000d42b`
- `0x18000d460`
- `0x18000d495`
- `0x18000d4ca`
- `0x18000d825`
- `0x18000d85a`
- `0x18000d88f`
- `0x18000d8c4`
- `0x18000d8f9`
- `0x18000d952`
- `0x18000d98d`
- `0x18000d9c2`
- `0x18000d9f7`
- `0x18000da2c`
- `0x18000da61`
- `0x18000da96`
- `0x18000dacb`
- `0x18000db00`
- `0x18000db35`
- `0x18000db6a`
- `0x18000db9f`
- `0x18000dbd4`
- `0x18000dc09`
- `0x18000dc3e`
- `0x18000dc73`
- `0x18000dca8`
- `0x18000dcdd`
- `0x18000dd12`
- `0x18000dd47`
- `0x18000dd7c`
- `0x18000ddb1`
- `0x18000dde6`
- `0x18000de1b`
- `0x18000de50`
- `0x18000de85`
- `0x18000deba`
- `0x18000df01`
- `0x18000df36`
- `0x18000df6b`
- `0x18000dfa0`
- `0x18000dfd5`

## callees

- `0x1800030e4`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_CaughtException(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  return wil::details::ReportFailure_CaughtException<1>((__int64)this, (unsigned int)a2);
}

```

## disassembly

```asm
0x180006a14  sub     rsp, 48h
0x180006a18  mov     rax, [rsp+48h]
0x180006a1d  mov     [rsp+48h+var_20], rax
0x180006a22  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x180006a27  nop
0x180006a28  add     rsp, 48h
0x180006a2c  retn
```
