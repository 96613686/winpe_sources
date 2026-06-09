# WPP_SF_sD

- ea: `0x14001db18`
- end: `0x14001db92`
- name: `WPP_SF_sD`
- size: `122`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a950`
- `0x14001b3e0`
- `0x140025be0`
- `0x140027d74`
- `0x140027eec`
- `0x140028870`
- `0x140028ac8`
- `0x1400293c4`
- `0x140029b24`
- `0x14002d428`
- `0x14002e330`
- `0x14002e5a8`

## callees

- `0x14001db18`
- `0x14003abe0`

## pseudocode

```c
__int64 WPP_SF_sD(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4, ...)
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
           4,
           0);
}

```

## disassembly

```asm
0x14001db18  sub     rsp, 58h
0x14001db1c  mov     r10, rcx
0x14001db1f  test    r9, r9
0x14001db22  jz      short loc_14001DB38
0x14001db24  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001db28  inc     rax
0x14001db2b  cmp     byte ptr [r9+rax], 0
0x14001db30  jnz     short loc_14001DB28
0x14001db32  lea     rcx, [rax+1]
0x14001db36  jmp     short loc_14001DB3D
0x14001db38  mov     ecx, 5
0x14001db3d  mov     [rsp+58h+var_18], 0
0x14001db46  lea     rax, aNull; "NULL"
0x14001db4d  test    r9, r9
0x14001db50  mov     [rsp+58h+var_20], 4
0x14001db59  lea     r11, [rsp+58h+arg_20]
0x14001db61  cmovz   r9, rax
0x14001db65  mov     [rsp+58h+var_28], r11
0x14001db6a  mov     rax, cs:pfnWppTraceMessage
0x14001db71  mov     [rsp+58h+var_30], rcx
0x14001db76  mov     rcx, r10
0x14001db79  mov     [rsp+58h+var_38], r9
0x14001db7e  movzx   r9d, dx
0x14001db82  mov     edx, 2Bh ; '+'
0x14001db87  call    _guard_dispatch_icall
0x14001db8c  add     rsp, 58h
0x14001db90  retn
```
