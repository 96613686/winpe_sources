# WPP_SF_sq

- ea: `0x1400043dc`
- end: `0x140004456`
- name: `WPP_SF_sq`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e200`
- `0x14000e31c`
- `0x140015030`

## callees

- `0x1400043dc`
- `0x140005c30`

## pseudocode

```c
__int64 WPP_SF_sq(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4, ...)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  if ( a4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a4[v5] );
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, const char *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           a4,
           v6,
           va,
           8,
           0);
}

```

## disassembly

```asm
0x1400043dc  sub     rsp, 58h
0x1400043e0  mov     r10, rcx
0x1400043e3  test    r9, r9
0x1400043e6  jz      short loc_1400043FC
0x1400043e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400043ec  inc     rax
0x1400043ef  cmp     byte ptr [r9+rax], 0
0x1400043f4  jnz     short loc_1400043EC
0x1400043f6  lea     rcx, [rax+1]
0x1400043fa  jmp     short loc_140004401
0x1400043fc  mov     ecx, 5
0x140004401  mov     [rsp+58h+var_18], 0
0x14000440a  lea     rax, aNull; "NULL"
0x140004411  test    r9, r9
0x140004414  mov     [rsp+58h+var_20], 8
0x14000441d  lea     r11, [rsp+58h+arg_20]
0x140004425  cmovz   r9, rax
0x140004429  mov     [rsp+58h+var_28], r11
0x14000442e  mov     rax, cs:pfnWppTraceMessage
0x140004435  mov     [rsp+58h+var_30], rcx
0x14000443a  mov     rcx, r10
0x14000443d  mov     [rsp+58h+var_38], r9
0x140004442  movzx   r9d, dx
0x140004446  mov     edx, 2Bh ; '+'
0x14000444b  call    _guard_dispatch_icall
0x140004450  add     rsp, 58h
0x140004454  retn
```
