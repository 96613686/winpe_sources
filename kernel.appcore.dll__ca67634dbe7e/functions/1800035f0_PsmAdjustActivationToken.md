# PsmAdjustActivationToken

- ea: `0x1800035f0`
- end: `0x180003634`
- name: `PsmAdjustActivationToken`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800038d0`

## pseudocode

```c
__int64 __fastcall PsmAdjustActivationToken(
        void *a1,
        int a2,
        int a3,
        WCHAR *a4,
        wchar_t *a5,
        PackageOrigin a6,
        HANDLE *a7)
{
  return PsmpAdjustActivationToken(a1, a2, a3, a4, a5, a6, 0, 0, 0, a7);
}

```

## disassembly

```asm
0x1800035f0  sub     rsp, 58h
0x1800035f4  mov     rax, [rsp+58h+arg_30]
0x1800035fc  mov     [rsp+58h+var_10], rax
0x180003601  xor     eax, eax
0x180003603  mov     [rsp+58h+var_18], rax
0x180003608  mov     [rsp+58h+var_20], rax
0x18000360d  mov     [rsp+58h+var_28], rax
0x180003612  mov     eax, [rsp+58h+arg_28]
0x180003619  mov     [rsp+58h+var_30], eax
0x18000361d  mov     rax, [rsp+58h+arg_20]
0x180003625  mov     [rsp+58h+var_38], rax
0x18000362a  call    PsmpAdjustActivationToken
0x18000362f  add     rsp, 58h
0x180003633  retn
```
