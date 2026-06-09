# WPP_SF_qddds

- ea: `0x1400439bc`
- end: `0x140043a6d`
- name: `WPP_SF_qddds`
- size: `177`
- prototype: ``
- caller_count: `76`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010f0`
- `0x140001ee4`
- `0x1400021d0`
- `0x140002b00`
- `0x140002cb0`
- `0x1400031bc`
- `0x140003d04`
- `0x140004038`
- `0x140004920`
- `0x14000508c`
- `0x140006e2c`
- `0x140007354`
- `0x140007a08`
- `0x140007df8`
- `0x140007ed8`
- `0x140008160`
- `0x14000889c`
- `0x140008a74`
- `0x140009600`
- `0x140009844`
- `0x140009e1c`
- `0x140009ee0`
- `0x14000c570`
- `0x14000cca0`
- `0x14000d310`
- `0x14000d594`
- `0x14000e408`
- `0x14000ebe0`
- `0x14000efd4`
- `0x140010680`
- `0x140010988`
- `0x140010c90`
- `0x140011998`
- `0x14001212c`
- `0x140012a10`
- `0x140013184`
- `0x1400133c0`
- `0x140014df8`
- `0x140015818`
- `0x140017214`
- `0x140017a3c`
- `0x140017d80`
- `0x140018ea0`
- `0x140019870`
- `0x140019a10`
- `0x14001b7d0`
- `0x14001c600`
- `0x14001d0b4`
- `0x14001d580`
- `0x14001e8f4`

## callees

- `0x140030bc8`
- `0x1400439bc`

## pseudocode

```c
void WPP_SF_qddds(__int64 a1, USHORT a2, ULONGLONG a3, ...)
{
  const char *v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // [rsp+98h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+20h]
  __int64 v8; // [rsp+A0h] [rbp+28h] BYREF
  va_list va1; // [rsp+A0h] [rbp+28h]
  __int64 v10; // [rsp+A8h] [rbp+30h] BYREF
  va_list va2; // [rsp+A8h] [rbp+30h]
  __int64 v12; // [rsp+B0h] [rbp+38h] BYREF
  va_list va3; // [rsp+B0h] [rbp+38h]
  const char *v14; // [rsp+B8h] [rbp+40h]
  va_list va4; // [rsp+C0h] [rbp+48h] BYREF

  va_start(va4, a3);
  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v6 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v8 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v10 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v12 = va_arg(va4, _QWORD);
  v14 = va_arg(va4, const char *);
  v3 = v14;
  if ( v14 )
  {
    v4 = -1;
    do
      ++v4;
    while ( v14[v4] );
    v5 = v4 + 1;
  }
  else
  {
    v5 = 5;
  }
  if ( !v14 )
    v3 = "NULL";
  FastWppTraceMessage(1294, a2, a3, va, 8, va1, 4, va2, 4, va3, 4, v3, v5, 0);
}

```

## disassembly

```asm
0x1400439bc  mov     [rsp+arg_18], r9
0x1400439c1  sub     rsp, 78h
0x1400439c5  mov     rcx, [rsp+78h+arg_38]
0x1400439cd  test    rcx, rcx
0x1400439d0  jz      short loc_1400439E4
0x1400439d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400439d6  inc     rax
0x1400439d9  cmp     byte ptr [rcx+rax], 0
0x1400439dd  jnz     short loc_1400439D6
0x1400439df  inc     rax
0x1400439e2  jmp     short loc_1400439E9
0x1400439e4  mov     eax, 5
0x1400439e9  mov     [rsp+78h+var_10], 0
0x1400439f2  lea     r9, aNull; "NULL"
0x1400439f9  mov     [rsp+78h+var_18], rax
0x1400439fe  test    rcx, rcx
0x140043a01  lea     rax, [rsp+78h+arg_30]
0x140043a09  movzx   edx, dx
0x140043a0c  cmovz   rcx, r9
0x140043a10  mov     r10d, 50Eh
0x140043a16  mov     [rsp+78h+var_20], rcx
0x140043a1b  lea     r9, [rsp+78h+arg_18]
0x140043a23  mov     ecx, 4
0x140043a28  mov     [rsp+78h+var_28], rcx
0x140043a2d  mov     [rsp+78h+var_30], rax
0x140043a32  lea     rax, [rsp+78h+arg_28]
0x140043a3a  mov     [rsp+78h+var_38], rcx
0x140043a3f  mov     [rsp+78h+var_40], rax
0x140043a44  lea     rax, [rsp+78h+arg_20]
0x140043a4c  mov     [rsp+78h+var_48], rcx
0x140043a51  mov     ecx, r10d
0x140043a54  mov     [rsp+78h+var_50], rax
0x140043a59  mov     [rsp+78h+var_58], 8
0x140043a62  call    FastWppTraceMessage
0x140043a67  add     rsp, 78h
0x140043a6b  retn
```
