# WPP_SF_S

- ea: `0x140003b2c`
- end: `0x140003b92`
- name: `WPP_SF_S`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14001cf08`
- `0x14001d118`
- `0x1400254c0`
- `0x14002a540`
- `0x14002e078`

## callees

- `0x140003b2c`
- `0x140006560`

## pseudocode

```c
__int64 __fastcall WPP_SF_S(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           a4,
           v5,
           0);
}

```

## disassembly

```asm
0x140003b2c  push    rbx
0x140003b2e  sub     rsp, 40h
0x140003b32  mov     r10, cs:pfnWppTraceMessage
0x140003b39  xor     ebx, ebx
0x140003b3b  test    r9, r9
0x140003b3e  jz      short loc_140003B58
0x140003b40  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003b44  inc     rax
0x140003b47  cmp     [r9+rax*2], bx
0x140003b4c  jnz     short loc_140003B44
0x140003b4e  lea     rax, ds:2[rax*2]
0x140003b56  jmp     short loc_140003B5D
0x140003b58  mov     eax, 0Ah
0x140003b5d  test    r9, r9
0x140003b60  mov     [rsp+48h+var_18], rbx
0x140003b65  mov     [rsp+48h+var_20], rax
0x140003b6a  lea     r11, aNull_0; "NULL"
0x140003b71  cmovz   r9, r11
0x140003b75  mov     rax, r10
0x140003b78  mov     [rsp+48h+var_28], r9
0x140003b7d  movzx   r9d, dx
0x140003b81  mov     edx, 2Bh ; '+'
0x140003b86  call    _guard_dispatch_icall
0x140003b8b  add     rsp, 40h
0x140003b8f  pop     rbx
0x140003b90  retn
```
