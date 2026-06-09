# PsmAdjustActivationTokenEx

- ea: `0x180003590`
- end: `0x1800035e6`
- name: `PsmAdjustActivationTokenEx`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800038d0`

## pseudocode

```c
__int64 __fastcall PsmAdjustActivationTokenEx(
        void *a1,
        int a2,
        int a3,
        WCHAR *a4,
        wchar_t *a5,
        PackageOrigin a6,
        UUID *a7,
        __int64 *a8,
        HANDLE *a9)
{
  return PsmpAdjustActivationToken(a1, a2, a3, a4, a5, a6, a7, a8, 0, a9);
}

```

## disassembly

```asm
0x180003590  sub     rsp, 58h
0x180003594  mov     rax, [rsp+58h+arg_40]
0x18000359c  mov     [rsp+58h+var_10], rax
0x1800035a1  mov     rax, [rsp+58h+arg_38]
0x1800035a9  mov     [rsp+58h+var_18], 0
0x1800035b2  mov     [rsp+58h+var_20], rax
0x1800035b7  mov     rax, [rsp+58h+arg_30]
0x1800035bf  mov     [rsp+58h+var_28], rax
0x1800035c4  mov     eax, [rsp+58h+arg_28]
0x1800035cb  mov     [rsp+58h+var_30], eax
0x1800035cf  mov     rax, [rsp+58h+arg_20]
0x1800035d7  mov     [rsp+58h+var_38], rax
0x1800035dc  call    PsmpAdjustActivationToken
0x1800035e1  add     rsp, 58h
0x1800035e5  retn
```
