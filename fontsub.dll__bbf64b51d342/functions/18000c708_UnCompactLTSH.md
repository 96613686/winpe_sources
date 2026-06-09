# UnCompactLTSH

- ea: `0x18000c708`
- end: `0x18000c86b`
- name: `UnCompactLTSH`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000c874`

## callees

- `0x18000c708`
- `0x18001a348`
- `0x18001a3bc`
- `0x18001a76c`
- `0x18001a808`

## pseudocode

```c
__int16 __fastcall UnCompactLTSH(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        __int64 a7,
        _DWORD *a8)
{
  unsigned __int16 v8; // si
  __int16 result; // ax
  unsigned __int16 v13; // di
  unsigned int v14; // r14d
  char v15[4]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 v16; // [rsp+34h] [rbp-Ch] BYREF
  _WORD v17[2]; // [rsp+38h] [rbp-8h] BYREF
  int v18; // [rsp+3Ch] [rbp-4h] BYREF

  v8 = 0;
  v16 = 0;
  v17[0] = 0;
  v18 = 0;
  v15[0] = 0;
  *a8 = 0;
  result = ReadGeneric(a1, (__int64)&v18, 4u, (unsigned __int8 *)&LTSH_CONTROL, a3, &v16);
  if ( !result )
  {
    if ( a6 == HIWORD(v18) )
    {
      HIWORD(v18) = a5;
      result = WriteGeneric((__int64)a2, (__int64)&v18, 4u, (unsigned __int8 *)&LTSH_CONTROL, a4, v17);
      if ( !result )
      {
        v13 = 0;
        v14 = v16 + a3;
        *a8 += v17[0];
        while ( v8 < a5 )
        {
          if ( v13 < a6 && v8 == *(_WORD *)(a7 + 2LL * v13) )
          {
            result = ReadByte(a1, (__int64)v15, v14);
            if ( result )
              return result;
            result = WriteByte(a2, v15[0], a4 + *a8);
            if ( result )
              return result;
            ++v14;
            ++v13;
          }
          else
          {
            result = WriteByte(a2, 1, *a8 + a4);
            if ( result )
              return result;
          }
          ++*a8;
          ++v8;
        }
        return 0;
      }
    }
    else
    {
      return 1087;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c708  mov     r11, rsp
0x18000c70b  mov     [r11+18h], rbx
0x18000c70f  mov     [r11+10h], rdx
0x18000c713  mov     [r11+8], rcx
0x18000c717  push    rbp
0x18000c718  push    rsi
0x18000c719  push    rdi
0x18000c71a  push    r12
0x18000c71c  push    r13
0x18000c71e  push    r14
0x18000c720  push    r15
0x18000c722  mov     rbp, rsp
0x18000c725  sub     rsp, 40h
0x18000c729  mov     rbx, [rbp+arg_38]
0x18000c72d  lea     rax, [rbp+var_C]
0x18000c731  xor     esi, esi
0x18000c733  mov     [r11-50h], rax
0x18000c737  mov     r14d, r8d
0x18000c73a  mov     [rbp+var_C], si
0x18000c73e  mov     r13d, r9d
0x18000c741  mov     [rbp+var_8], si
0x18000c745  mov     rdi, rdx
0x18000c748  mov     [rbp+var_4], esi
0x18000c74b  lea     r8d, [rsi+4]
0x18000c74f  mov     [rbp+var_10], sil
0x18000c753  lea     r9, LTSH_CONTROL
0x18000c75a  mov     [rbx], esi
0x18000c75c  lea     rdx, [rbp+var_4]
0x18000c760  mov     [r11-58h], r14d
0x18000c764  call    ReadGeneric
0x18000c769  test    ax, ax
0x18000c76c  jnz     loc_18000C853
0x18000c772  movzx   r15d, [rbp+arg_28]
0x18000c777  cmp     r15w, word ptr [rbp+var_4+2]
0x18000c77c  jz      short loc_18000C788
0x18000c77e  mov     eax, 43Fh
0x18000c783  jmp     loc_18000C853
0x18000c788  movzx   r12d, [rbp+arg_20]
0x18000c78d  lea     rax, [rbp+var_8]
0x18000c791  mov     [rsp+40h+var_18], rax
0x18000c796  lea     r9, LTSH_CONTROL
0x18000c79d  mov     r8d, 4
0x18000c7a3  mov     [rsp+40h+var_20], r13d
0x18000c7a8  lea     rdx, [rbp+var_4]
0x18000c7ac  mov     word ptr [rbp+var_4+2], r12w
0x18000c7b1  mov     rcx, rdi
0x18000c7b4  call    WriteGeneric
0x18000c7b9  test    ax, ax
0x18000c7bc  jnz     loc_18000C853
0x18000c7c2  movzx   eax, [rbp+var_C]
0x18000c7c6  mov     edi, esi
0x18000c7c8  add     r14d, eax
0x18000c7cb  mov     r9d, 1
0x18000c7d1  movzx   eax, [rbp+var_8]
0x18000c7d5  add     [rbx], eax
0x18000c7d7  mov     ecx, [rbx]
0x18000c7d9  cmp     si, r12w
0x18000c7dd  jnb     short loc_18000C851
0x18000c7df  cmp     di, r15w
0x18000c7e3  jnb     short loc_18000C82D
0x18000c7e5  mov     rdx, [rbp+arg_30]
0x18000c7e9  movzx   eax, di
0x18000c7ec  cmp     si, [rdx+rax*2]
0x18000c7f0  jnz     short loc_18000C82D
0x18000c7f2  mov     rcx, [rbp+arg_0]
0x18000c7f6  lea     rdx, [rbp+var_10]
0x18000c7fa  mov     r8d, r14d
0x18000c7fd  call    ReadByte
0x18000c802  test    ax, ax
0x18000c805  jnz     short loc_18000C853
0x18000c807  mov     r8d, [rbx]
0x18000c80a  mov     dl, [rbp+var_10]
0x18000c80d  add     r8d, r13d
0x18000c810  mov     rcx, [rbp+arg_8]
0x18000c814  call    WriteByte
0x18000c819  test    ax, ax
0x18000c81c  jnz     short loc_18000C853
0x18000c81e  mov     r9d, 1
0x18000c824  add     r14d, r9d
0x18000c827  add     di, r9w
0x18000c82b  jmp     short loc_18000C848
0x18000c82d  lea     r8d, [rcx+r13]
0x18000c831  mov     dl, r9b
0x18000c834  mov     rcx, [rbp+arg_8]
0x18000c838  call    WriteByte
0x18000c83d  test    ax, ax
0x18000c840  jnz     short loc_18000C853
0x18000c842  mov     r9d, 1
0x18000c848  add     [rbx], r9d
0x18000c84b  add     si, r9w
0x18000c84f  jmp     short loc_18000C7D7
0x18000c851  xor     eax, eax
0x18000c853  mov     rbx, [rsp+40h+arg_10]
0x18000c85b  add     rsp, 40h
0x18000c85f  pop     r15
0x18000c861  pop     r14
0x18000c863  pop     r13
0x18000c865  pop     r12
0x18000c867  pop     rdi
0x18000c868  pop     rsi
0x18000c869  pop     rbp
0x18000c86a  retn
```
