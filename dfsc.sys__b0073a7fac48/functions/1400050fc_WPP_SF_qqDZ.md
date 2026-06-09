# WPP_SF_qqDZ

- ea: `0x1400050fc`
- end: `0x1400051c7`
- name: `WPP_SF_qqDZ`
- size: `203`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14001c8ac`
- `0x14001cb40`
- `0x14001cee0`
- `0x14001d110`
- `0x14001fb50`

## callees

- `0x1400050fc`
- `0x140005fb0`

## pseudocode

```c
__int64 WPP_SF_qqDZ(__int64 a1, __int64 a2, __int64 a3, ...)
{
  const wchar_t *v3; // rdx
  __int64 v4; // r8
  const wchar_t *v5; // r9
  __int64 v7; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+A8h] [rbp+20h]
  __int64 v9; // [rsp+B0h] [rbp+28h] BYREF
  va_list va1; // [rsp+B0h] [rbp+28h]
  __int64 v11; // [rsp+B8h] [rbp+30h] BYREF
  va_list va2; // [rsp+B8h] [rbp+30h]
  unsigned __int16 *v13; // [rsp+C0h] [rbp+38h]
  va_list va3; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v7 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v9 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v11 = va_arg(va3, _QWORD);
  v13 = va_arg(va3, unsigned __int16 *);
  v3 = v13;
  if ( v13 )
  {
    v4 = *v13;
    if ( *v13 )
    {
      v5 = (const wchar_t *)*((_QWORD *)v13 + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v4 = 8;
  }
  v5 = L"NULL";
LABEL_6:
  if ( !v13 )
    v3 = L"\b";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_55706db06074317498eaf8c01331c814_Traceguids,
           22,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           8,
           (__int64 *)va2,
           4,
           v3,
           2,
           v5,
           v4,
           0);
}

```

## disassembly

```asm
0x1400050fc  mov     [rsp+arg_18], r9
0x140005101  push    rbx
0x140005102  sub     rsp, 80h
0x140005109  mov     rdx, [rsp+88h+arg_30]
0x140005111  xor     r11d, r11d
0x140005114  mov     ebx, 8
0x140005119  test    rdx, rdx
0x14000511c  jz      short loc_14000512E
0x14000511e  movzx   r8d, word ptr [rdx]
0x140005122  cmp     [rdx], r11w
0x140005126  jz      short loc_140005131
0x140005128  mov     r9, [rdx+8]
0x14000512c  jmp     short loc_140005138
0x14000512e  mov     r8, rbx
0x140005131  lea     r9, aNull_0; "NULL"
0x140005138  mov     [rsp+88h+var_18], r11
0x14000513d  lea     rax, asc_1400088CC; "\b"
0x140005144  mov     [rsp+88h+var_20], r8
0x140005149  test    rdx, rdx
0x14000514c  mov     [rsp+88h+var_28], r9
0x140005151  lea     r8, WPP_55706db06074317498eaf8c01331c814_Traceguids
0x140005158  cmovz   rdx, rax
0x14000515c  mov     [rsp+88h+var_30], 2
0x140005165  mov     rax, cs:pfnWppTraceMessage
0x14000516c  mov     r10d, 16h
0x140005172  mov     [rsp+88h+var_38], rdx
0x140005177  mov     r9d, r10d
0x14000517a  mov     [rsp+88h+var_40], 4
0x140005183  lea     rdx, [rsp+88h+arg_28]
0x14000518b  mov     [rsp+88h+var_48], rdx
0x140005190  lea     rdx, [rsp+88h+arg_20]
0x140005198  mov     [rsp+88h+var_50], rbx
0x14000519d  mov     [rsp+88h+var_58], rdx
0x1400051a2  lea     rdx, [rsp+88h+arg_18]
0x1400051aa  mov     [rsp+88h+var_60], rbx
0x1400051af  mov     [rsp+88h+var_68], rdx
0x1400051b4  lea     edx, [r10+15h]
0x1400051b8  call    _guard_dispatch_icall
0x1400051bd  add     rsp, 80h
0x1400051c4  pop     rbx
0x1400051c5  retn
```
