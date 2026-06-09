# CmpsMaxCompressedSize

- ea: `0x180011d9c`
- end: `0x180011f25`
- name: `CmpsMaxCompressedSize`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800117c0`

## callees

- `0x180011d9c`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CmpsMaxCompressedSize(int *a1, unsigned __int64 a2)
{
  int v2; // eax
  __int64 *v3; // r8
  __int64 v6; // rcx
  void (__fastcall *v7)(_QWORD, _QWORD); // rsi
  unsigned __int64 v8; // rbx
  __int64 v9; // r9
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rax
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // [rsp+60h] [rbp+8h] BYREF
  __int64 v15; // [rsp+68h] [rbp+10h]

  v2 = *a1;
  v3 = &qword_18001D140;
  v14 = 0;
  if ( (v2 & 0x40000000) == 0 )
    v3 = &qword_18001D020;
  v6 = *((_QWORD *)a1 + 1);
  v7 = (void (__fastcall *)(_QWORD, _QWORD))v3[6 * (v2 & 0x9FFFFFFF)];
  if ( (v2 & 0x40000000) != 0 )
  {
    v8 = a2;
    if ( a2 >= 0x4000000 )
      v8 = 0x4000000;
    if ( ((unsigned int (__fastcall *)(__int64, _QWORD, unsigned __int64, _QWORD, _QWORD, unsigned __int64 *))v7)(
           v6,
           0,
           v8,
           0,
           0,
           &v14) == 111 )
    {
      v8 = v14;
      ((void (__fastcall *)(_QWORD, _QWORD, unsigned __int64, _QWORD, _QWORD, unsigned __int64 *))v7)(
        *((_QWORD *)a1 + 1),
        0,
        v14,
        0,
        0,
        &v14);
    }
    v9 = 32;
  }
  else
  {
    v8 = 1;
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, __int64, unsigned __int64 *))v7)(v6, 0, 0, 0, 1, &v14);
    v9 = 65543;
  }
  v15 = 0;
  v10 = a2 % v8;
  v14 += 8LL;
  v11 = v14 * (a2 / v8);
  if ( !is_mul_ok(v14, a2 / v8) )
    return -1;
  v13 = v9 + v11;
  if ( v9 + v11 < v11 )
    return -1;
  if ( v10 && (v7(*((_QWORD *)a1 + 1), 0), v13 += v14 + 8, v13 < v14 + 8) )
    return -1;
  else
    return v13;
}

```

## disassembly

```asm
0x180011d9c  mov     r11, rsp
0x180011d9f  mov     [r11+18h], rbx
0x180011da3  push    rbp
0x180011da4  push    rsi
0x180011da5  push    rdi
0x180011da6  sub     rsp, 40h
0x180011daa  mov     eax, [rcx]
0x180011dac  lea     r8, qword_18001D140
0x180011db3  bt      eax, 1Eh
0x180011db7  mov     qword ptr [r11+8], 0
0x180011dbf  mov     r9d, eax
0x180011dc2  mov     rdi, rcx
0x180011dc5  lea     rcx, qword_18001D020
0x180011dcc  mov     rbp, rdx
0x180011dcf  cmovnb  r8, rcx
0x180011dd3  mov     ecx, 9FFFFFFFh
0x180011dd8  and     rax, rcx
0x180011ddb  mov     rcx, [rdi+8]
0x180011ddf  lea     rax, [rax+rax*2]
0x180011de3  add     rax, rax
0x180011de6  mov     rsi, [r8+rax*8]
0x180011dea  bt      r9d, 1Eh
0x180011def  jnb     loc_180011E81
0x180011df5  mov     eax, 4000000h
0x180011dfa  mov     rbx, rdx
0x180011dfd  cmp     rdx, rax
0x180011e00  cmovnb  rbx, rax
0x180011e04  lea     rax, [r11+8]
0x180011e08  mov     [r11-30h], rax
0x180011e0c  xor     r9d, r9d
0x180011e0f  mov     rax, rsi
0x180011e12  mov     qword ptr [r11-38h], 0
0x180011e1a  mov     r8, rbx
0x180011e1d  xor     edx, edx
0x180011e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e24  cmp     eax, 6Fh ; 'o'
0x180011e27  jz      loc_180011EC5
0x180011e2d  mov     r9d, 20h ; ' '
0x180011e33  mov     rcx, [rsp+58h+arg_0]
0x180011e38  xor     edx, edx
0x180011e3a  mov     rax, rbp
0x180011e3d  mov     [rsp+58h+arg_8], 0
0x180011e46  div     rbx
0x180011e49  add     rcx, 8
0x180011e4d  mov     r8, rdx
0x180011e50  mov     [rsp+58h+arg_0], rcx
0x180011e55  mul     rcx
0x180011e58  test    rdx, rdx
0x180011e5b  jz      short loc_180011E6E
0x180011e5d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011e61  mov     rbx, [rsp+58h+arg_10]
0x180011e66  add     rsp, 40h
0x180011e6a  pop     rdi
0x180011e6b  pop     rsi
0x180011e6c  pop     rbp
0x180011e6d  retn
0x180011e6e  lea     rbx, [r9+rax]
0x180011e72  cmp     rbx, rax
0x180011e75  jb      short loc_180011E5D
0x180011e77  test    r8, r8
0x180011e7a  jnz     short loc_180011EF6
0x180011e7c  mov     rax, rbx
0x180011e7f  jmp     short loc_180011E61
0x180011e81  lea     rax, [rsp+58h+arg_0]
0x180011e86  mov     ebx, 1
0x180011e8b  mov     [rsp+58h+var_30], rax
0x180011e90  xor     r9d, r9d
0x180011e93  mov     rax, rsi
0x180011e96  mov     [rsp+58h+var_38], rbx
0x180011e9b  xor     r8d, r8d
0x180011e9e  xor     edx, edx
0x180011ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ea5  mov     r9d, 10007h
0x180011eab  jmp     short loc_180011E33
0x180011ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eb2  mov     rax, [rsp+58h+arg_0]
0x180011eb7  add     rax, 8
0x180011ebb  add     rbx, rax
0x180011ebe  cmp     rbx, rax
0x180011ec1  jb      short loc_180011E5D
0x180011ec3  jmp     short loc_180011E7C
0x180011ec5  mov     rbx, [rsp+58h+arg_0]
0x180011eca  lea     rax, [rsp+58h+arg_0]
0x180011ecf  mov     rcx, [rdi+8]
0x180011ed3  xor     r9d, r9d
0x180011ed6  mov     [rsp+58h+var_30], rax
0x180011edb  mov     r8, rbx
0x180011ede  mov     rax, rsi
0x180011ee1  mov     [rsp+58h+var_38], 0
0x180011eea  xor     edx, edx
0x180011eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ef1  jmp     loc_180011E2D
0x180011ef6  mov     rcx, [rdi+8]
0x180011efa  lea     rax, [rsp+58h+arg_0]
0x180011eff  xor     r9d, r9d
0x180011f02  mov     [rsp+58h+var_30], rax
0x180011f07  xor     edx, edx
0x180011f09  mov     rax, rsi
0x180011f0c  test    dword ptr [rdi], 40000000h
0x180011f12  jz      short loc_180011F1B
0x180011f14  mov     [rsp+58h+var_38], rdx
0x180011f19  jmp     short loc_180011EAD
0x180011f1b  mov     [rsp+58h+var_38], r8
0x180011f20  xor     r8d, r8d
0x180011f23  jmp     short loc_180011EAD
```
