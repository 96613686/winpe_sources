# PsmAdjustActivationTokenWithDynamicId

- ea: `0x180007e60`
- end: `0x180007eb0`
- name: `PsmAdjustActivationTokenWithDynamicId`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800038d0`

## pseudocode

```c
__int64 __fastcall PsmAdjustActivationTokenWithDynamicId(
        void *a1,
        int a2,
        int a3,
        WCHAR *a4,
        wchar_t *a5,
        PackageOrigin a6,
        UUID *a7,
        HANDLE *a8)
{
  return PsmpAdjustActivationToken(a1, a2, a3, a4, a5, a6, a7, 0, 0, a8);
}

```

## disassembly

```asm
0x180007e60  mov     r11, rsp
0x180007e63  sub     rsp, 58h
0x180007e67  mov     rax, [rsp+58h+arg_38]
0x180007e6f  mov     [r11-10h], rax
0x180007e73  mov     rax, [rsp+58h+arg_30]
0x180007e7b  mov     qword ptr [r11-18h], 0
0x180007e83  mov     qword ptr [r11-20h], 0
0x180007e8b  mov     [r11-28h], rax
0x180007e8f  mov     eax, [rsp+58h+arg_28]
0x180007e96  mov     [rsp+58h+var_30], eax
0x180007e9a  mov     rax, [rsp+58h+arg_20]
0x180007ea2  mov     [r11-38h], rax
0x180007ea6  call    PsmpAdjustActivationToken
0x180007eab  add     rsp, 58h
0x180007eaf  retn
```
