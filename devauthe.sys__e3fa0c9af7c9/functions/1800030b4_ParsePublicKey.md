# _ParsePublicKey

- ea: `0x1800030b4`
- end: `0x180003198`
- name: `_ParsePublicKey`
- size: `228`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002ef4`
- `0x18000325c`

## callees

- `0x1800030b4`
- `0x180003a4c`
- `0x1800067e0`

## pseudocode

```c
__int64 __fastcall ParsePublicKey(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  int Values; // eax
  int v7; // eax
  __int64 result; // rax
  _DWORD v9[4]; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v10[16]; // [rsp+40h] [rbp-49h] BYREF
  int v11; // [rsp+50h] [rbp-39h]
  int v12; // [rsp+70h] [rbp-19h]
  __int64 v13; // [rsp+78h] [rbp-11h]
  _BYTE v14[16]; // [rsp+80h] [rbp-9h] BYREF
  int v15; // [rsp+90h] [rbp+7h]
  int v16; // [rsp+A0h] [rbp+17h]
  _BYTE *v17; // [rsp+A8h] [rbp+1Fh]

  v9[0] = 3;
  Values = MinAsn1ExtractValues(
             *(_QWORD *)(a1 + 8),
             *(_DWORD *)a1,
             (unsigned int)v9,
             (unsigned int)&qword_180009050,
             4,
             (__int64)v10);
  if ( Values > 0 )
    Values = v11;
  if ( Values != *(_DWORD *)a1 )
    return 0;
  v9[0] = 3;
  v7 = MinAsn1ExtractValues(v13, v12, (unsigned int)v9, (unsigned int)&qword_1800090B0, 4, (__int64)v14);
  if ( v7 > 0 )
    v7 = v15;
  if ( v7 != v12 || v16 != 257 || *v17 )
    return 0;
  *a2 = v17 + 1;
  result = 1;
  *a3 = 256;
  return result;
}

```

## disassembly

```asm
0x1800030b4  mov     [rsp-8+arg_18], rbx
0x1800030b9  push    rbp
0x1800030ba  push    rsi
0x1800030bb  push    rdi
0x1800030bc  lea     rbp, [rsp-47h]
0x1800030c1  sub     rsp, 0D0h
0x1800030c8  mov     rax, cs:__security_cookie
0x1800030cf  xor     rax, rsp
0x1800030d2  mov     [rbp+57h+var_20], rax
0x1800030d6  mov     rdi, rdx
0x1800030d9  mov     [rbp+57h+var_B0], 3
0x1800030e0  mov     edx, [rcx]
0x1800030e2  lea     rax, [rbp+57h+var_A0]
0x1800030e6  mov     rsi, r8
0x1800030e9  mov     [rsp+0E0h+var_B8], rax
0x1800030ee  mov     rbx, rcx
0x1800030f1  mov     [rsp+0E0h+var_C0], 4
0x1800030f9  mov     rcx, [rcx+8]
0x1800030fd  lea     r9, qword_180009050
0x180003104  lea     r8, [rbp+57h+var_B0]
0x180003108  call    MinAsn1ExtractValues
0x18000310d  test    eax, eax
0x18000310f  cmovg   eax, [rbp+57h+var_90]
0x180003113  cmp     eax, [rbx]
0x180003115  jnz     short loc_180003176
0x180003117  mov     edx, [rbp+57h+var_70]
0x18000311a  lea     rax, [rbp+57h+var_60]
0x18000311e  mov     rcx, [rbp+57h+var_68]
0x180003122  lea     r9, qword_1800090B0
0x180003129  mov     [rsp+0E0h+var_B8], rax
0x18000312e  lea     r8, [rbp+57h+var_B0]
0x180003132  mov     [rsp+0E0h+var_C0], 4
0x18000313a  mov     [rbp+57h+var_B0], 3
0x180003141  call    MinAsn1ExtractValues
0x180003146  test    eax, eax
0x180003148  cmovg   eax, [rbp+57h+var_50]
0x18000314c  cmp     eax, [rbp+57h+var_70]
0x18000314f  jnz     short loc_180003176
0x180003151  cmp     [rbp+57h+var_40], 101h
0x180003158  jnz     short loc_180003176
0x18000315a  mov     rax, [rbp+57h+var_38]
0x18000315e  cmp     byte ptr [rax], 0
0x180003161  jnz     short loc_180003176
0x180003163  inc     rax
0x180003166  mov     [rdi], rax
0x180003169  mov     eax, 1
0x18000316e  mov     dword ptr [rsi], 100h
0x180003174  jmp     short loc_180003178
0x180003176  xor     eax, eax
0x180003178  mov     rcx, [rbp+57h+var_20]
0x18000317c  xor     rcx, rsp; StackCookie
0x18000317f  call    __security_check_cookie
0x180003184  mov     rbx, [rsp+0E0h+arg_18]
0x18000318c  add     rsp, 0D0h
0x180003193  pop     rdi
0x180003194  pop     rsi
0x180003195  pop     rbp
0x180003196  retn
```
