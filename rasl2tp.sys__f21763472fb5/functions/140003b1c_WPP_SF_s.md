# WPP_SF_s

- ea: `0x140003b1c`
- end: `0x140003b80`
- name: `WPP_SF_s`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400040b0`
- `0x140013edc`
- `0x1400154b8`

## callees

- `0x140003b1c`
- `0x140004830`

## pseudocode

```c
__int64 __fastcall WPP_SF_s(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4)
{
  __int64 v5; // rax
  __int64 v6; // rcx

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
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, const char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           a4,
           v6,
           0);
}

```

## disassembly

```asm
0x140003b1c  sub     rsp, 48h
0x140003b20  mov     r10, rcx
0x140003b23  test    r9, r9
0x140003b26  jz      short loc_140003B3C
0x140003b28  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003b2c  inc     rax
0x140003b2f  cmp     byte ptr [r9+rax], 0
0x140003b34  jnz     short loc_140003B2C
0x140003b36  lea     rcx, [rax+1]
0x140003b3a  jmp     short loc_140003B41
0x140003b3c  mov     ecx, 5
0x140003b41  test    r9, r9
0x140003b44  mov     [rsp+48h+var_18], 0
0x140003b4d  mov     [rsp+48h+var_20], rcx
0x140003b52  lea     rax, aNull; "NULL"
0x140003b59  cmovz   r9, rax
0x140003b5d  mov     rcx, r10
0x140003b60  mov     rax, cs:pfnWppTraceMessage
0x140003b67  mov     [rsp+48h+var_28], r9
0x140003b6c  movzx   r9d, dx
0x140003b70  mov     edx, 2Bh ; '+'
0x140003b75  call    _guard_dispatch_icall
0x140003b7a  add     rsp, 48h
0x140003b7e  retn
```
