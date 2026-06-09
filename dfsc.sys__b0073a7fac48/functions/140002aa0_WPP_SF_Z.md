# WPP_SF_Z

- ea: `0x140002aa0`
- end: `0x140002b11`
- name: `WPP_SF_Z`
- size: `113`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x14001338c`
- `0x14001d110`
- `0x14001ef20`
- `0x14001f040`
- `0x14001fb50`
- `0x140022cd8`
- `0x1400239b0`
- `0x14002545c`

## callees

- `0x140002aa0`
- `0x140005fb0`

## pseudocode

```c
__int64 __fastcall WPP_SF_Z(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // r10
  const wchar_t *v5; // r11

  if ( a4 )
  {
    v4 = *a4;
    if ( *a4 )
    {
      v5 = (const wchar_t *)*((_QWORD *)a4 + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v4 = 8;
  }
  v5 = L"NULL";
LABEL_6:
  if ( !a4 )
    a4 = L"\b";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, const wchar_t *, __int64, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           a4,
           2,
           v5,
           v4,
           0);
}

```

## disassembly

```asm
0x140002aa0  push    rbx
0x140002aa2  sub     rsp, 50h
0x140002aa6  xor     ebx, ebx
0x140002aa8  test    r9, r9
0x140002aab  jz      short loc_140002ABD
0x140002aad  movzx   r10d, word ptr [r9]
0x140002ab1  cmp     [r9], bx
0x140002ab5  jz      short loc_140002AC3
0x140002ab7  mov     r11, [r9+8]
0x140002abb  jmp     short loc_140002ACA
0x140002abd  mov     r10d, 8
0x140002ac3  lea     r11, aNull_0; "NULL"
0x140002aca  mov     [rsp+58h+var_18], rbx
0x140002acf  lea     rax, asc_1400088CC; "\b"
0x140002ad6  mov     [rsp+58h+var_20], r10
0x140002adb  test    r9, r9
0x140002ade  mov     [rsp+58h+var_28], r11
0x140002ae3  cmovz   r9, rax
0x140002ae7  mov     [rsp+58h+var_30], 2
0x140002af0  mov     rax, cs:pfnWppTraceMessage
0x140002af7  mov     [rsp+58h+var_38], r9
0x140002afc  movzx   r9d, dx
0x140002b00  mov     edx, 2Bh ; '+'
0x140002b05  call    _guard_dispatch_icall
0x140002b0a  add     rsp, 50h
0x140002b0e  pop     rbx
0x140002b0f  retn
```
