# WPP_SF_qZ

- ea: `0x140002ac4`
- end: `0x140002b57`
- name: `WPP_SF_qZ`
- size: `147`
- prototype: `__int64(__int64, unsigned __int16, __int64, ...)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x140002be4`
- `0x1400128a0`
- `0x1400130e0`
- `0x140014e00`
- `0x140017310`
- `0x1400189a0`
- `0x1400193d0`
- `0x1400195b0`
- `0x14001ac20`
- `0x14001af40`
- `0x140020660`
- `0x140022a80`
- `0x1400234b0`
- `0x140023950`

## callees

- `0x140002ac4`
- `0x140006880`

## pseudocode

```c
__int64 WPP_SF_qZ(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  const wchar_t *v3; // r9
  __int64 v4; // r10
  const wchar_t *v5; // r11
  __int64 v7; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  unsigned __int16 *v9; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

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
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
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
           0);
}

```

## disassembly

```asm
0x140002ac4  mov     [rsp+arg_18], r9
0x140002ac9  push    rbx
0x140002aca  sub     rsp, 60h
0x140002ace  mov     r9, [rsp+68h+arg_20]
0x140002ad6  xor     ebx, ebx
0x140002ad8  test    r9, r9
0x140002adb  jz      short loc_140002AED
0x140002add  movzx   r10d, word ptr [r9]
0x140002ae1  cmp     [r9], bx
0x140002ae5  jz      short loc_140002AF3
0x140002ae7  mov     r11, [r9+8]
0x140002aeb  jmp     short loc_140002AFA
0x140002aed  mov     r10d, 8
0x140002af3  lea     r11, aNull_0; "NULL"
0x140002afa  mov     [rsp+68h+var_18], rbx
0x140002aff  lea     rax, asc_140009230; "\b"
0x140002b06  mov     [rsp+68h+var_20], r10
0x140002b0b  test    r9, r9
0x140002b0e  mov     [rsp+68h+var_28], r11
0x140002b13  cmovz   r9, rax
0x140002b17  mov     [rsp+68h+var_30], 2
0x140002b20  mov     rax, cs:pfnWppTraceMessage
0x140002b27  mov     [rsp+68h+var_38], r9
0x140002b2c  lea     r9, [rsp+68h+arg_18]
0x140002b34  mov     [rsp+68h+var_40], 8
0x140002b3d  mov     [rsp+68h+var_48], r9
0x140002b42  movzx   r9d, dx
0x140002b46  mov     edx, 2Bh ; '+'
0x140002b4b  call    _guard_dispatch_icall
0x140002b50  add     rsp, 60h
0x140002b54  pop     rbx
0x140002b55  retn
```
