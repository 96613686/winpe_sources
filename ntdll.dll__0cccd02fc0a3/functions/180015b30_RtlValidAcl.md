# RtlValidAcl

- ea: `0x180015b30`
- end: `0x180015cd0`
- name: `RtlValidAcl`
- size: `416`
- prototype: ``
- caller_count: `18`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012eb0`
- `0x180013ed0`
- `0x180014450`
- `0x180014cf0`
- `0x180015490`
- `0x1800155b0`
- `0x1800b34e0`
- `0x1800b42b0`
- `0x1800d1770`
- `0x1800db870`
- `0x1800de100`
- `0x1800e9000`
- `0x180122b74`
- `0x18013d080`
- `0x18013d320`
- `0x18013d480`
- `0x18013d800`
- `0x18013d9a0`

## callees

- `0x180015b30`
- `0x18010df28`
- `0x18011fdc0`
- `0x180120a4c`
- `0x180120b4c`

## pseudocode

```c
char __fastcall RtlValidAcl(__int64 a1)
{
  _WORD *v2; // r14
  unsigned __int8 *v3; // rdi
  unsigned int v4; // esi
  int v5; // r12d
  int v6; // r13d
  unsigned __int64 v7; // rdx
  unsigned __int16 *v8; // r15
  unsigned __int64 v9; // rcx
  unsigned int v10; // edx
  __int64 v11; // rax
  char result; // al

  if ( (unsigned __int8)(*(_BYTE *)a1 - 2) <= 2u )
  {
    v2 = (_WORD *)(a1 + 2);
    if ( ((a1 + 3) & 0xFFFFFFFFFFFFFFFEuLL) != a1 + 2 )
      return 0;
    if ( *v2 < 8u )
      return 0;
    v3 = (unsigned __int8 *)(a1 + 8);
    v4 = 0;
    v5 = 1730063;
    v6 = 104928;
    while ( 1 )
    {
      if ( v4 >= *(unsigned __int16 *)(a1 + 4) )
        return 1;
      v7 = a1 + (unsigned __int16)*v2;
      if ( (unsigned __int64)(v3 + 4) > v7 )
        return 0;
      v8 = (unsigned __int16 *)(v3 + 2);
      if ( (unsigned __int8 *)((unsigned __int64)(v3 + 3) & 0xFFFFFFFFFFFFFFFEuLL) != v3 + 2 )
        return 0;
      v9 = *v8;
      if ( (unsigned __int64)&v3[v9] > v7 )
        return 0;
      v10 = *v3;
      if ( (unsigned __int8)v10 <= 0x14u && _bittest(&v5, v10) )
      {
        if ( ((v9 + 3) & 0xFFFFFFFFFFFFFFFCuLL) != v9 )
          return 0;
        if ( (unsigned int)v9 < 0x10 )
          return 0;
        if ( v3[8] != 1 )
          return 0;
        v11 = v3[9];
        if ( (unsigned __int8)v11 > 0xFu || v9 < 4 * v11 + 16 )
          return 0;
      }
      else if ( (_BYTE)v10 == 4 )
      {
        if ( *(_BYTE *)a1 < 3u )
          return 0;
        result = RtlpValidCompoundAce(v3);
        if ( !result )
          return result;
      }
      else if ( (unsigned __int8)v10 <= 0x10u && _bittest(&v6, v10) )
      {
        if ( *(_BYTE *)a1 < 4u )
          return 0;
        result = RtlpValidObjectAce(v3);
        if ( !result )
          return result;
      }
      else if ( (_BYTE)v10 == 18 )
      {
        result = RtlpValidAttributeAce(v3);
        if ( !result )
          return result;
      }
      else if ( (_BYTE)v10 == 21 )
      {
        result = RtlpValidAccessFilterAce(v3);
        if ( !result )
          return result;
      }
      else if ( (unsigned int)v9 < 4 )
      {
        return 0;
      }
      v3 += *v8;
      ++v4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180015b30  push    rbx
0x180015b32  push    rsi
0x180015b33  push    rdi
0x180015b34  push    r12
0x180015b36  push    r13
0x180015b38  push    r14
0x180015b3a  push    r15
0x180015b3c  sub     rsp, 30h
0x180015b40  mov     rbx, rcx
0x180015b43  movzx   eax, byte ptr [rcx]
0x180015b46  sub     al, 2
0x180015b48  cmp     al, 2
0x180015b4a  ja      loc_180015CB9
0x180015b50  lea     r14, [rcx+2]
0x180015b54  lea     rax, [r14+1]
0x180015b58  and     rax, 0FFFFFFFFFFFFFFFEh
0x180015b5c  cmp     rax, r14
0x180015b5f  jnz     loc_180015C80
0x180015b65  cmp     word ptr [r14], 8
0x180015b6a  jb      loc_180015C7C
0x180015b70  lea     rdi, [rcx+8]
0x180015b74  mov     [rsp+68h+var_40], rdi
0x180015b79  xor     esi, esi
0x180015b7b  mov     r12d, 1A660Fh
0x180015b81  mov     r13d, 199E0h
0x180015b87  mov     [rsp+68h+var_48], esi
0x180015b8b  movzx   eax, word ptr [rbx+4]
0x180015b8f  cmp     esi, eax
0x180015b91  jnb     loc_180015C1B
0x180015b97  movzx   edx, word ptr [r14]
0x180015b9b  add     rdx, rbx
0x180015b9e  lea     rax, [rdi+4]
0x180015ba2  cmp     rax, rdx
0x180015ba5  ja      loc_180015C74
0x180015bab  lea     r15, [rdi+2]
0x180015baf  lea     rax, [rdi+3]
0x180015bb3  and     rax, 0FFFFFFFFFFFFFFFEh
0x180015bb7  cmp     rax, r15
0x180015bba  jnz     loc_180015C78
0x180015bc0  movzx   ecx, word ptr [r15]
0x180015bc4  lea     rax, [rcx+rdi]
0x180015bc8  cmp     rax, rdx
0x180015bcb  ja      short loc_180015C29
0x180015bcd  movzx   edx, byte ptr [rdi]
0x180015bd0  cmp     dl, 14h
0x180015bd3  ja      short loc_180015C30
0x180015bd5  bt      r12d, edx
0x180015bd9  jnb     short loc_180015C30
0x180015bdb  lea     rax, [rcx+3]
0x180015bdf  and     rax, 0FFFFFFFFFFFFFFFCh
0x180015be3  cmp     rax, rcx
0x180015be6  jnz     short loc_180015C22
0x180015be8  cmp     ecx, 10h
0x180015beb  jb      short loc_180015C22
0x180015bed  cmp     byte ptr [rdi+8], 1
0x180015bf1  jnz     short loc_180015C22
0x180015bf3  movzx   eax, byte ptr [rdi+9]
0x180015bf7  cmp     al, 0Fh
0x180015bf9  ja      short loc_180015C22
0x180015bfb  lea     rax, ds:10h[rax*4]
0x180015c03  cmp     rcx, rax
0x180015c06  jb      short loc_180015C22
0x180015c08  movzx   eax, word ptr [r15]
0x180015c0c  add     rdi, rax
0x180015c0f  mov     [rsp+68h+var_40], rdi
0x180015c14  inc     esi
0x180015c16  jmp     loc_180015B87
0x180015c1b  mov     al, 1
0x180015c1d  jmp     loc_180015CBF
0x180015c22  xor     al, al
0x180015c24  jmp     loc_180015CBF
0x180015c29  xor     al, al
0x180015c2b  jmp     loc_180015CBF
0x180015c30  cmp     dl, 4
0x180015c33  jz      short loc_180015C61
0x180015c35  cmp     dl, 10h
0x180015c38  ja      short loc_180015C49
0x180015c3a  bt      r13d, edx
0x180015c3e  jnb     short loc_180015C49
0x180015c40  cmp     byte ptr [rbx], 4
0x180015c43  jnb     short loc_180015C84
0x180015c45  xor     al, al
0x180015c47  jmp     short loc_180015CBF
0x180015c49  cmp     dl, 12h
0x180015c4c  jz      short loc_180015C9A
0x180015c4e  cmp     dl, 15h
0x180015c51  jnz     short loc_180015CAC
0x180015c53  mov     rcx, rdi
0x180015c56  call    RtlpValidAccessFilterAce
0x180015c5b  test    al, al
0x180015c5d  jnz     short loc_180015C08
0x180015c5f  jmp     short loc_180015CBF
0x180015c61  cmp     byte ptr [rbx], 3
0x180015c64  jb      short loc_180015C96
0x180015c66  mov     rcx, rdi
0x180015c69  call    RtlpValidCompoundAce
0x180015c6e  test    al, al
0x180015c70  jnz     short loc_180015C08
0x180015c72  jmp     short loc_180015CBF
0x180015c74  xor     al, al
0x180015c76  jmp     short loc_180015CBF
0x180015c78  xor     al, al
0x180015c7a  jmp     short loc_180015CBF
0x180015c7c  xor     al, al
0x180015c7e  jmp     short loc_180015CBF
0x180015c80  xor     al, al
0x180015c82  jmp     short loc_180015CBF
0x180015c84  mov     rcx, rdi
0x180015c87  call    RtlpValidObjectAce
0x180015c8c  test    al, al
0x180015c8e  jnz     loc_180015C08
0x180015c94  jmp     short loc_180015CBF
0x180015c96  xor     al, al
0x180015c98  jmp     short loc_180015CBF
0x180015c9a  mov     rcx, rdi
0x180015c9d  call    RtlpValidAttributeAce
0x180015ca2  test    al, al
0x180015ca4  jnz     loc_180015C08
0x180015caa  jmp     short loc_180015CBF
0x180015cac  cmp     ecx, 4
0x180015caf  jnb     loc_180015C08
0x180015cb5  xor     al, al
0x180015cb7  jmp     short loc_180015CBF
0x180015cb9  xor     al, al
0x180015cbb  jmp     short loc_180015CBF
0x180015cbd  xor     al, al
0x180015cbf  add     rsp, 30h
0x180015cc3  pop     r15
0x180015cc5  pop     r14
0x180015cc7  pop     r13
0x180015cc9  pop     r12
0x180015ccb  pop     rdi
0x180015ccc  pop     rsi
0x180015ccd  pop     rbx
0x180015cce  retn
```
