# FMTInsertCommas(x,x,x,x)

- ea: `0x10030b88`
- end: `0x10030d5a`
- name: `_FMTInsertCommas@16`
- size: `466`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1001c340`
- `0x1002fa03`

## callees

- `0x10006400`
- `0x10030b88`
- `0x10035510`

## pseudocode

```c
__int16 __thiscall FMTInsertCommas(_WORD *this, unsigned int a2, int a3)
{
  unsigned __int16 *v3; // esi
  char *v4; // ebx
  char *v5; // ecx
  int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // ecx
  int v9; // edi
  unsigned __int16 *v10; // edi
  unsigned int v11; // edx
  unsigned __int16 v12; // ax
  unsigned __int16 v13; // cx
  unsigned __int16 *v14; // edx
  bool v15; // cf
  unsigned int v16; // ecx
  unsigned __int16 *v17; // edi
  int i; // ecx
  unsigned int v20; // [esp+8h] [ebp-214h]
  unsigned __int16 *v22; // [esp+14h] [ebp-208h]
  unsigned __int16 v23[256]; // [esp+18h] [ebp-204h] BYREF

  v3 = this;
  v4 = (char *)this;
  v5 = (char *)(this + 1);
  do
  {
    LOWORD(v6) = *(_WORD *)v4;
    v4 += 2;
  }
  while ( (_WORD)v6 );
  v7 = (v4 - v5) >> 1;
  if ( v7 > 0xFF )
    return v6;
  WCSCPY2(v23, v3, 0x100u);
  v8 = a2;
  if ( a3 == 1 )
  {
    if ( a2 < 4 )
    {
      v9 = 4 - a2;
      if ( (int)(4 - a2) <= 0 )
        goto LABEL_7;
LABEL_21:
      v8 = v9 + a2;
      v20 = v9 + a2;
      v6 = v9 + v7 + (v9 + a2 - 1) / 3;
      if ( v6 > 255 )
        return v6;
      v22 = &v23[v9];
      v14 = &v23[wcslen(v23) + v9];
      if ( v14 >= v22 )
      {
        do
        {
          *v14 = v14[-v9];
          --v14;
        }
        while ( v14 >= v22 );
        v3 = this;
      }
      if ( v9 )
      {
        v15 = ((2 * v9) & 2) != 0;
        v16 = (unsigned int)(2 * v9) >> 2;
        memset32(v23, 2293795, v16);
        v17 = &v23[2 * v16];
        for ( i = v15; i; --i )
          *v17++ = 35;
        v8 = v20;
      }
      goto LABEL_7;
    }
    if ( !(a2 % 3) )
    {
      v9 = 1;
      goto LABEL_21;
    }
  }
LABEL_7:
  v6 = v7 + (v8 - 1) / 3;
  if ( v6 <= 255 )
  {
    v10 = v23;
    v11 = v8 % 3;
    if ( !(v8 % 3) )
      v11 = 3;
    for ( ; v8; --v8 )
    {
      if ( !v11 )
      {
        *v3 = 44;
        v11 = 3;
        ++v3;
      }
      v12 = *v10++;
      *v3++ = v12;
      --v11;
    }
    if ( *v10 )
    {
      v13 = *v10;
      do
      {
        ++v10;
        *v3++ = v13;
        v13 = *v10;
      }
      while ( *v10 );
    }
    LOWORD(v6) = 0;
    *v3 = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x10030b88  mov     edi, edi
0x10030b8a  push    ebp
0x10030b8b  mov     ebp, esp
0x10030b8d  sub     esp, 214h
0x10030b93  mov     eax, ___security_cookie
0x10030b98  xor     eax, ebp
0x10030b9a  mov     [ebp+var_4], eax
0x10030b9d  push    ebx
0x10030b9e  push    esi
0x10030b9f  mov     esi, ecx
0x10030ba1  xor     edx, edx
0x10030ba3  mov     ebx, esi
0x10030ba5  mov     [ebp+var_210], esi
0x10030bab  mov     [ebp+var_20C], edx
0x10030bb1  lea     ecx, [ebx+2]
0x10030bb4  mov     ax, [ebx]
0x10030bb7  add     ebx, 2
0x10030bba  cmp     ax, dx
0x10030bbd  jnz     short loc_10030BB4
0x10030bbf  sub     ebx, ecx
0x10030bc1  sar     ebx, 1
0x10030bc3  cmp     ebx, 0FFh
0x10030bc9  ja      loc_10030C79
0x10030bcf  push    edi
0x10030bd0  push    100h
0x10030bd5  mov     edx, esi
0x10030bd7  lea     ecx, [ebp+var_204]
0x10030bdd  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10030be2  cmp     [ebp+arg_4], 1
0x10030be6  mov     ecx, [ebp+arg_0]
0x10030be9  mov     [ebp+var_208], 3
0x10030bf3  jnz     short loc_10030C0A
0x10030bf5  push    4
0x10030bf7  pop     edi
0x10030bf8  cmp     ecx, edi
0x10030bfa  jnb     loc_10030C89
0x10030c00  sub     edi, ecx
0x10030c02  test    edi, edi
0x10030c04  jg      loc_10030C9D
0x10030c0a  push    3
0x10030c0c  pop     edi
0x10030c0d  xor     edx, edx
0x10030c0f  lea     eax, [ecx-1]
0x10030c12  div     edi
0x10030c14  add     eax, ebx
0x10030c16  cmp     eax, 0FFh
0x10030c1b  jg      short loc_10030C78
0x10030c1d  xor     edx, edx
0x10030c1f  lea     edi, [ebp+var_204]
0x10030c25  push    3
0x10030c27  pop     ebx
0x10030c28  mov     eax, ecx
0x10030c2a  div     ebx
0x10030c2c  test    edx, edx
0x10030c2e  cmovz   edx, ebx
0x10030c31  test    ecx, ecx
0x10030c33  jz      short loc_10030C56
0x10030c35  test    edx, edx
0x10030c37  jnz     short loc_10030C44
0x10030c39  push    2Ch ; ','
0x10030c3b  pop     eax
0x10030c3c  mov     [esi], ax
0x10030c3f  mov     edx, ebx
0x10030c41  add     esi, 2
0x10030c44  mov     ax, [edi]
0x10030c47  add     edi, 2
0x10030c4a  mov     [esi], ax
0x10030c4d  add     esi, 2
0x10030c50  dec     edx
0x10030c51  sub     ecx, 1
0x10030c54  jnz     short loc_10030C35
0x10030c56  movzx   eax, word ptr [edi]
0x10030c59  test    ax, ax
0x10030c5c  jz      short loc_10030C73
0x10030c5e  mov     ecx, eax
0x10030c60  lea     edi, [edi+2]
0x10030c63  mov     [esi], cx
0x10030c66  movzx   eax, word ptr [edi]
0x10030c69  add     esi, 2
0x10030c6c  mov     ecx, eax
0x10030c6e  test    ax, ax
0x10030c71  jnz     short loc_10030C60
0x10030c73  xor     eax, eax
0x10030c75  mov     [esi], ax
0x10030c78  pop     edi
0x10030c79  mov     ecx, [ebp+var_4]
0x10030c7c  pop     esi
0x10030c7d  xor     ecx, ebp; StackCookie
0x10030c7f  pop     ebx
0x10030c80  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10030c85  leave
0x10030c86  retn    8
0x10030c89  push    3
0x10030c8b  xor     edx, edx
0x10030c8d  mov     eax, ecx
0x10030c8f  pop     edi
0x10030c90  div     edi
0x10030c92  test    edx, edx
0x10030c94  jnz     loc_10030C0D
0x10030c9a  xor     edi, edi
0x10030c9c  inc     edi
0x10030c9d  add     ecx, edi
0x10030c9f  xor     edx, edx
0x10030ca1  mov     [ebp+var_214], ecx
0x10030ca7  lea     eax, [ecx-1]
0x10030caa  div     [ebp+var_208]
0x10030cb0  add     eax, ebx
0x10030cb2  add     eax, edi
0x10030cb4  cmp     eax, 0FFh
0x10030cb9  jg      short loc_10030C78
0x10030cbb  lea     edx, [ebp+var_204]
0x10030cc1  lea     eax, [edx+2]
0x10030cc4  mov     [ebp+var_208], eax
0x10030cca  mov     ax, [edx]
0x10030ccd  add     edx, 2
0x10030cd0  cmp     ax, word ptr [ebp+var_20C]
0x10030cd7  jnz     short loc_10030CCA
0x10030cd9  sub     edx, [ebp+var_208]
0x10030cdf  lea     eax, [edi+edi]
0x10030ce2  sar     edx, 1
0x10030ce4  mov     [ebp+var_20C], eax
0x10030cea  lea     eax, [ebp+eax+var_204]
0x10030cf1  mov     [ebp+var_208], eax
0x10030cf7  lea     eax, [edx+edi]
0x10030cfa  lea     edx, [ebp+var_204]
0x10030d00  lea     edx, [edx+eax*2]
0x10030d03  cmp     edx, [ebp+var_208]
0x10030d09  jb      short loc_10030D2C
0x10030d0b  mov     esi, [ebp+var_208]
0x10030d11  mov     eax, edx
0x10030d13  sub     eax, [ebp+var_20C]
0x10030d19  mov     ax, [eax]
0x10030d1c  mov     [edx], ax
0x10030d1f  sub     edx, 2
0x10030d22  cmp     edx, esi
0x10030d24  jnb     short loc_10030D11
0x10030d26  mov     esi, [ebp+var_210]
0x10030d2c  push    3
0x10030d2e  test    edi, edi
0x10030d30  jz      loc_10030C0C
0x10030d36  lea     ecx, [edi+edi]
0x10030d39  mov     eax, 230023h
0x10030d3e  shr     ecx, 1
0x10030d40  lea     edi, [ebp+var_204]
0x10030d46  shr     ecx, 1
0x10030d48  rep stosd
0x10030d4a  adc     ecx, ecx
0x10030d4c  rep stosw
0x10030d4f  mov     ecx, [ebp+var_214]
0x10030d55  jmp     loc_10030C0C
```
