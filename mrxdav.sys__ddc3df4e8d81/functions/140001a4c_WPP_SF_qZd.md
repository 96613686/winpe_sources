# WPP_SF_qZd

- ea: `0x140001a4c`
- end: `0x140001af5`
- name: `WPP_SF_qZd`
- size: `169`
- prototype: `__int64(__int64, unsigned __int16, __int64, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140010620`
- `0x1400130e0`
- `0x14001dec0`
- `0x140020090`

## callees

- `0x140001a4c`
- `0x140006880`

## pseudocode

```c
__int64 WPP_SF_qZd(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  const wchar_t *v3; // r9
  __int64 v4; // r10
  const wchar_t *v5; // r11
  __int64 v7; // [rsp+98h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+20h]
  unsigned __int16 *v9; // [rsp+A0h] [rbp+28h]
  va_list va1; // [rsp+A8h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v7 = va_arg(va1, _QWORD);
  v9 = va_arg(va1, unsigned __int16 *);
  v3 = v9;
  if ( v9 )
  {
    v4 = *v9;
    if ( *v9 )
    {
      v5 = (const wchar_t *)*((_QWORD *)v9 + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v4 = 8;
  }
  v5 = L"NULL";
LABEL_6:
  if ( !v9 )
    v3 = L"\b";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           v3,
           2,
           v5,
           v4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x140001a4c  mov     [rsp+arg_18], r9
0x140001a51  push    rbx
0x140001a52  sub     rsp, 70h
0x140001a56  mov     r9, [rsp+78h+arg_20]
0x140001a5e  xor     ebx, ebx
0x140001a60  test    r9, r9
0x140001a63  jz      short loc_140001A75
0x140001a65  movzx   r10d, word ptr [r9]
0x140001a69  cmp     [r9], bx
0x140001a6d  jz      short loc_140001A7B
0x140001a6f  mov     r11, [r9+8]
0x140001a73  jmp     short loc_140001A82
0x140001a75  mov     r10d, 8
0x140001a7b  lea     r11, aNull_0; "NULL"
0x140001a82  mov     [rsp+78h+var_18], rbx
0x140001a87  lea     rax, asc_140009230; "\b"
0x140001a8e  mov     [rsp+78h+var_20], 4
0x140001a97  lea     rbx, [rsp+78h+arg_28]
0x140001a9f  mov     [rsp+78h+var_28], rbx
0x140001aa4  test    r9, r9
0x140001aa7  mov     [rsp+78h+var_30], r10
0x140001aac  mov     [rsp+78h+var_38], r11
0x140001ab1  cmovz   r9, rax
0x140001ab5  mov     rax, cs:pfnWppTraceMessage
0x140001abc  mov     [rsp+78h+var_40], 2
0x140001ac5  mov     [rsp+78h+var_48], r9
0x140001aca  lea     r9, [rsp+78h+arg_18]
0x140001ad2  mov     [rsp+78h+var_50], 8
0x140001adb  mov     [rsp+78h+var_58], r9
0x140001ae0  movzx   r9d, dx
0x140001ae4  mov     edx, 2Bh ; '+'
0x140001ae9  call    _guard_dispatch_icall
0x140001aee  add     rsp, 70h
0x140001af2  pop     rbx
0x140001af3  retn
```
