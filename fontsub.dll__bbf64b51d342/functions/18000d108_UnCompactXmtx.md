# UnCompactXmtx

- ea: `0x18000d108`
- end: `0x18000d36c`
- name: `UnCompactXmtx`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000c874`

## callees

- `0x18000d108`
- `0x18001a3bc`
- `0x18001a680`
- `0x18001a808`
- `0x18001aadc`

## pseudocode

```c
__int16 __fastcall UnCompactXmtx(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        int a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        __int64 a7,
        unsigned __int16 *a8,
        int *a9)
{
  int *v9; // rdi
  _QWORD *v10; // r11
  int v11; // r10d
  __int64 v12; // r9
  unsigned __int16 v14; // r15
  unsigned __int16 v15; // bx
  unsigned __int16 v16; // si
  int v17; // ecx
  __int16 result; // ax
  int v19; // r10d
  _WORD v20[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 v21; // [rsp+34h] [rbp-Ch] BYREF
  __int16 v22[2]; // [rsp+38h] [rbp-8h] BYREF
  int v23; // [rsp+3Ch] [rbp-4h] BYREF

  v9 = a9;
  v10 = a2;
  v11 = a4;
  v12 = a1;
  v20[0] = 0;
  *a9 = 0;
  v21 = 0;
  v14 = 0;
  v22[0] = 0;
  v15 = 0;
  v23 = 0;
  v16 = 0;
  LODWORD(a9) = 0;
  v17 = 0;
  while ( v16 < a5 )
  {
    if ( v15 >= *a8 )
    {
      if ( v15 < a6 && v16 == *(_WORD *)(a7 + 2LL * v15) )
      {
        result = ReadWord(v12, (__int64)v22, a3);
        if ( result )
          return result;
        result = WriteWord(a2, v22[0], v19 + *v9);
        if ( result )
          return result;
        a3 += 2;
        ++v15;
        goto LABEL_23;
      }
      if ( a6 != *a8 || v15 != a6 )
      {
        result = WriteWord(v10, 0, v17 + v11);
        if ( result )
          return result;
LABEL_23:
        *v9 += 2;
        goto LABEL_24;
      }
      result = WriteGeneric((__int64)v10, (__int64)&a9, 4u, (unsigned __int8 *)LONGXMETRIC_CONTROL, v17 + v11, v20);
      if ( result )
        return result;
      *v9 += v20[0];
      ++v14;
      ++v15;
    }
    else
    {
      if ( v15 < a6 && v16 == *(_WORD *)(a7 + 2LL * v15) )
      {
        result = ReadGeneric(a1, (__int64)&v23, 4u, (unsigned __int8 *)LONGXMETRIC_CONTROL, a3, &v21);
        if ( result )
          return result;
        result = WriteGeneric((__int64)a2, (__int64)&v23, 4u, (unsigned __int8 *)LONGXMETRIC_CONTROL, *v9 + a4, v20);
        if ( result )
          return result;
        a3 += v21;
        if ( v15 == *a8 - 1 )
          v14 = v16 + 1;
        ++v15;
      }
      else
      {
        result = WriteGeneric((__int64)v10, (__int64)&a9, 4u, (unsigned __int8 *)LONGXMETRIC_CONTROL, v17 + v11, v20);
        if ( result )
          return result;
      }
      *v9 += v20[0];
    }
LABEL_24:
    v17 = *v9;
    ++v16;
    v11 = a4;
    v10 = a2;
    v12 = a1;
  }
  *a8 = v14;
  return 0;
}

```

## disassembly

```asm
0x18000d108  mov     rax, rsp
0x18000d10b  mov     [rax+18h], rbx
0x18000d10f  mov     [rax+20h], r9d
0x18000d113  mov     [rax+10h], rdx
0x18000d117  mov     [rax+8], rcx
0x18000d11b  push    rbp
0x18000d11c  push    rsi
0x18000d11d  push    rdi
0x18000d11e  push    r12
0x18000d120  push    r13
0x18000d122  push    r14
0x18000d124  push    r15
0x18000d126  mov     rbp, rsp
0x18000d129  sub     rsp, 40h
0x18000d12d  mov     rdi, [rbp+arg_40]
0x18000d134  mov     r11, rdx
0x18000d137  mov     r13, [rbp+arg_38]
0x18000d13b  xor     edx, edx
0x18000d13d  movzx   r12d, [rbp+arg_28]
0x18000d142  mov     r10d, r9d
0x18000d145  mov     r9, rcx
0x18000d148  mov     [rbp+var_10], dx
0x18000d14c  mov     [rdi], edx
0x18000d14e  mov     r14d, r8d
0x18000d151  mov     [rbp+var_C], dx
0x18000d155  mov     r15d, edx
0x18000d158  mov     [rbp+var_8], dx
0x18000d15c  mov     ebx, edx
0x18000d15e  mov     [rbp+var_4], edx
0x18000d161  mov     esi, edx
0x18000d163  mov     dword ptr [rbp+arg_40], edx
0x18000d169  mov     ecx, edx
0x18000d16b  cmp     si, [rbp+arg_20]
0x18000d16f  jnb     loc_18000D34D
0x18000d175  cmp     bx, [r13+0]
0x18000d17a  jnb     loc_18000D26E
0x18000d180  cmp     bx, r12w
0x18000d184  jnb     loc_18000D227
0x18000d18a  mov     rdx, [rbp+arg_30]
0x18000d18e  movzx   eax, bx
0x18000d191  cmp     si, [rdx+rax*2]
0x18000d195  jnz     loc_18000D227
0x18000d19b  mov     rcx, [rbp+arg_0]
0x18000d19f  lea     rax, [rbp+var_C]
0x18000d1a3  mov     [rsp+40h+var_18], rax
0x18000d1a8  lea     r9, LONGXMETRIC_CONTROL
0x18000d1af  mov     r8d, 4
0x18000d1b5  mov     [rsp+40h+var_20], r14d
0x18000d1ba  lea     rdx, [rbp+var_4]
0x18000d1be  call    ReadGeneric
0x18000d1c3  test    ax, ax
0x18000d1c6  jnz     loc_18000D354
0x18000d1cc  mov     ecx, [rbp+arg_18]
0x18000d1cf  lea     rax, [rbp+var_10]
0x18000d1d3  add     ecx, [rdi]
0x18000d1d5  lea     r9, LONGXMETRIC_CONTROL
0x18000d1dc  mov     [rsp+40h+var_18], rax
0x18000d1e1  lea     rdx, [rbp+var_4]
0x18000d1e5  mov     [rsp+40h+var_20], ecx
0x18000d1e9  mov     r8d, 4
0x18000d1ef  mov     rcx, [rbp+arg_8]
0x18000d1f3  call    WriteGeneric
0x18000d1f8  xor     edx, edx
0x18000d1fa  test    ax, ax
0x18000d1fd  jnz     loc_18000D354
0x18000d203  movzx   eax, [rbp+var_C]
0x18000d207  lea     r8d, [rdx+1]
0x18000d20b  movzx   ecx, word ptr [r13+0]
0x18000d210  add     r14d, eax
0x18000d213  movzx   eax, bx
0x18000d216  sub     ecx, r8d
0x18000d219  cmp     eax, ecx
0x18000d21b  jnz     short loc_18000D221
0x18000d21d  lea     r15d, [r8+rsi]
0x18000d221  add     bx, r8w
0x18000d225  jmp     short loc_18000D263
0x18000d227  lea     eax, [rcx+r10]
0x18000d22b  mov     r8d, 4
0x18000d231  lea     rcx, [rbp+var_10]
0x18000d235  mov     [rsp+40h+var_18], rcx
0x18000d23a  lea     r9, LONGXMETRIC_CONTROL
0x18000d241  mov     rcx, r11
0x18000d244  mov     [rsp+40h+var_20], eax
0x18000d248  lea     rdx, [rbp+arg_40]
0x18000d24f  call    WriteGeneric
0x18000d254  xor     edx, edx
0x18000d256  test    ax, ax
0x18000d259  jnz     loc_18000D354
0x18000d25f  lea     r8d, [rdx+1]
0x18000d263  movzx   eax, [rbp+var_10]
0x18000d267  add     [rdi], eax
0x18000d269  jmp     loc_18000D336
0x18000d26e  cmp     bx, r12w
0x18000d272  jnb     short loc_18000D2C5
0x18000d274  mov     rdx, [rbp+arg_30]
0x18000d278  movzx   eax, bx
0x18000d27b  cmp     si, [rdx+rax*2]
0x18000d27f  jnz     short loc_18000D2C5
0x18000d281  mov     r8d, r14d
0x18000d284  lea     rdx, [rbp+var_8]
0x18000d288  mov     rcx, r9
0x18000d28b  call    ReadWord
0x18000d290  test    ax, ax
0x18000d293  jnz     loc_18000D354
0x18000d299  mov     r8d, [rdi]
0x18000d29c  movzx   edx, [rbp+var_8]
0x18000d2a0  add     r8d, r10d
0x18000d2a3  mov     rcx, [rbp+arg_8]
0x18000d2a7  call    WriteWord
0x18000d2ac  xor     edx, edx
0x18000d2ae  test    ax, ax
0x18000d2b1  jnz     loc_18000D354
0x18000d2b7  add     r14d, 2
0x18000d2bb  lea     r8d, [rdx+1]
0x18000d2bf  add     bx, r8w
0x18000d2c3  jmp     short loc_18000D333
0x18000d2c5  cmp     r12w, [r13+0]
0x18000d2ca  jnz     short loc_18000D31A
0x18000d2cc  cmp     bx, r12w
0x18000d2d0  jnz     short loc_18000D31A
0x18000d2d2  lea     eax, [rcx+r10]
0x18000d2d6  mov     r8d, 4
0x18000d2dc  lea     rcx, [rbp+var_10]
0x18000d2e0  mov     [rsp+40h+var_18], rcx
0x18000d2e5  lea     r9, LONGXMETRIC_CONTROL
0x18000d2ec  mov     rcx, r11
0x18000d2ef  mov     [rsp+40h+var_20], eax
0x18000d2f3  lea     rdx, [rbp+arg_40]
0x18000d2fa  call    WriteGeneric
0x18000d2ff  xor     edx, edx
0x18000d301  test    ax, ax
0x18000d304  jnz     short loc_18000D354
0x18000d306  movzx   eax, [rbp+var_10]
0x18000d30a  lea     r8d, [rdx+1]
0x18000d30e  add     [rdi], eax
0x18000d310  add     r15w, r8w
0x18000d314  add     bx, r8w
0x18000d318  jmp     short loc_18000D336
0x18000d31a  lea     r8d, [rcx+r10]
0x18000d31e  xor     edx, edx
0x18000d320  mov     rcx, r11
0x18000d323  call    WriteWord
0x18000d328  xor     edx, edx
0x18000d32a  test    ax, ax
0x18000d32d  jnz     short loc_18000D354
0x18000d32f  lea     r8d, [rdx+1]
0x18000d333  add     dword ptr [rdi], 2
0x18000d336  mov     ecx, [rdi]
0x18000d338  add     si, r8w
0x18000d33c  mov     r10d, [rbp+arg_18]
0x18000d340  mov     r11, [rbp+arg_8]
0x18000d344  mov     r9, [rbp+arg_0]
0x18000d348  jmp     loc_18000D16B
0x18000d34d  mov     [r13+0], r15w
0x18000d352  mov     eax, edx
0x18000d354  mov     rbx, [rsp+40h+arg_10]
0x18000d35c  add     rsp, 40h
0x18000d360  pop     r15
0x18000d362  pop     r14
0x18000d364  pop     r13
0x18000d366  pop     r12
0x18000d368  pop     rdi
0x18000d369  pop     rsi
0x18000d36a  pop     rbp
0x18000d36b  retn
```
