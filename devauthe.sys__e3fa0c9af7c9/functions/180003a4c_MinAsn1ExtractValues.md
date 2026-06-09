# MinAsn1ExtractValues

- ea: `0x180003a4c`
- end: `0x180003cf8`
- name: `MinAsn1ExtractValues`
- size: `684`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800030b4`
- `0x1800031a0`
- `0x180003904`

## callees

- `0x18000397c`
- `0x180003a4c`
- `0x1800067e0`

## pseudocode

```c
__int64 __fastcall MinAsn1ExtractValues(
        _BYTE *a1,
        unsigned int a2,
        unsigned int *a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 v6; // r10
  unsigned int v7; // r13d
  unsigned int *v8; // rax
  __int64 v9; // r11
  unsigned int v10; // r12d
  int v11; // esi
  _BYTE *v12; // rdi
  char v13; // r9
  unsigned int v14; // r15d
  unsigned int v15; // edx
  int v16; // r14d
  bool v17; // r8
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned int v20; // esi
  _BYTE *v22; // rax
  int v23; // eax
  unsigned int v24; // r8d
  _BYTE *v25; // r9
  unsigned int v26; // edx
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // r14d
  int v30; // r14d
  __int64 v31; // rcx
  _BYTE *v32; // rax
  char v33; // [rsp+20h] [rbp-B9h]
  bool v34; // [rsp+21h] [rbp-B8h]
  unsigned int v35; // [rsp+24h] [rbp-B5h]
  unsigned int v36; // [rsp+28h] [rbp-B1h] BYREF
  __int64 v37; // [rsp+30h] [rbp-A9h]
  int v38; // [rsp+38h] [rbp-A1h]
  unsigned int v39; // [rsp+3Ch] [rbp-9Dh]
  unsigned int *v40; // [rsp+40h] [rbp-99h]
  _BYTE *v41; // [rsp+48h] [rbp-91h] BYREF
  __int64 v42; // [rsp+50h] [rbp-89h]
  _QWORD v43[16]; // [rsp+60h] [rbp-79h]

  v6 = a6;
  v7 = 0;
  v42 = a4;
  v8 = a3;
  v40 = a3;
  v9 = a4;
  v37 = a6;
  v10 = a2;
  v11 = (int)a1;
  v12 = a1;
  if ( a2 >= 0x7FFFFFFF )
  {
LABEL_47:
    v20 = v11 - (_DWORD)v12 - 1;
  }
  else
  {
    v13 = 0;
    v14 = 0;
    v39 = *a3;
    v33 = 0;
    if ( v39 )
    {
      while ( 1 )
      {
        v15 = *(_DWORD *)(v9 + 16LL * v7 + 4);
        v38 = *(_DWORD *)(v9 + 16LL * v7);
        v16 = (unsigned __int8)v38;
        v35 = v15;
        v17 = (v38 & 0xC0000000) != 0 && v6 && v15 < a5;
        v34 = v17;
        v36 = 0;
        v41 = 0;
        if ( (unsigned __int8)v38 == 5 )
          break;
        if ( v13 )
          goto LABEL_14;
        if ( !v10 )
        {
          if ( (((unsigned __int8)v38 - 2) & 0xFFFFFFFD) != 0 )
            goto LABEL_46;
          goto LABEL_14;
        }
        v22 = *(_BYTE **)(v9 + 16LL * v7 + 8);
        if ( v22 )
        {
          while ( *v22 )
          {
            if ( *v22 == *v12 )
              goto LABEL_31;
            ++v22;
          }
          if ( (((unsigned __int8)v38 - 2) & 0xFFFFFFFD) != 0 )
          {
LABEL_46:
            v8 = v40;
            goto LABEL_47;
          }
LABEL_14:
          if ( v17 )
          {
            v18 = 2LL * v15;
            *(_QWORD *)(v6 + 8 * v18 + 8) = 0;
            *(_DWORD *)(v6 + 8 * v18) = 0;
          }
          if ( (unsigned int)(v16 - 3) > 1 )
            goto LABEL_20;
          if ( v14 >= 8 )
            goto LABEL_46;
          v19 = 2LL * v14++;
          BYTE4(v43[v19 + 1]) = v13;
          v13 = 1;
          v43[v19] = v12;
          LODWORD(v43[v19 + 1]) = v10;
LABEL_19:
          v33 = v13;
          goto LABEL_20;
        }
LABEL_31:
        v23 = MinAsn1ExtractContent(v12, v10, &v36, &v41);
        if ( v23 <= 0 )
          goto LABEL_46;
        v24 = v36;
        v25 = v41;
        v6 = v37;
        v26 = v36 + v23;
        if ( v34 )
        {
          if ( (v38 & 0x40000000) != 0 )
          {
            v27 = 2LL * v35;
            *(_QWORD *)(v37 + 8 * v27 + 8) = v41;
            *(_DWORD *)(v6 + 8 * v27) = v24;
            if ( *v12 == 3 && v24 )
            {
              *(_QWORD *)(v6 + 16LL * v35 + 8) = v25 + 1;
              *(_DWORD *)(v6 + 16LL * v35) = v24 - 1;
            }
          }
          else if ( v38 < 0 )
          {
            v28 = 2LL * v35;
            *(_QWORD *)(v37 + 8 * v28 + 8) = v12;
            *(_DWORD *)(v6 + 8 * v28) = v26;
          }
        }
        v29 = v16 - 1;
        if ( v29 && (v30 = v29 - 1) != 0 )
        {
          if ( (unsigned int)(v30 - 1) > 1 || v14 >= 8 )
            goto LABEL_46;
          v31 = 2LL * v14;
          v32 = &v12[v26];
          v12 = v25;
          ++v14;
          LODWORD(v43[v31 + 1]) = v10 - v26;
          v10 = v24;
          v43[v31] = v32;
          BYTE4(v43[v31 + 1]) = 0;
        }
        else
        {
          v12 += v26;
          v10 -= v26;
        }
        v13 = v33;
        v9 = v42;
LABEL_20:
        if ( ++v7 >= v39 )
        {
          v8 = v40;
          goto LABEL_22;
        }
      }
      if ( !v14 )
        goto LABEL_46;
      v12 = (_BYTE *)v43[2 * --v14];
      v10 = v43[2 * v14 + 1];
      v13 = BYTE4(v43[2 * v14 + 1]);
      goto LABEL_19;
    }
LABEL_22:
    v20 = (_DWORD)v12 - v11;
  }
  *v8 = v7;
  return v20;
}

```

## disassembly

```asm
0x180003a4c  push    rbp
0x180003a4e  push    rsi
0x180003a4f  push    rdi
0x180003a50  push    r12
0x180003a52  push    r13
0x180003a54  push    r14
0x180003a56  push    r15
0x180003a58  lea     rbp, [rsp-17h]
0x180003a5d  sub     rsp, 0F0h
0x180003a64  mov     rax, cs:__security_cookie
0x180003a6b  xor     rax, rsp
0x180003a6e  mov     [rbp+47h+var_40], rax
0x180003a72  mov     r10, [rbp+47h+arg_28]
0x180003a76  xor     r13d, r13d
0x180003a79  mov     [rsp+120h+var_D0], r9
0x180003a7e  mov     rax, r8
0x180003a81  mov     [rsp+120h+var_E0], rax
0x180003a86  mov     r11, r9
0x180003a89  mov     [rsp+120h+var_F0], r10
0x180003a8e  mov     r12d, edx
0x180003a91  mov     rsi, rcx
0x180003a94  mov     rdi, rcx
0x180003a97  cmp     edx, 7FFFFFFFh
0x180003a9d  jnb     loc_180003CEF
0x180003aa3  mov     ecx, [r8]
0x180003aa6  xor     r9b, r9b
0x180003aa9  xor     r15d, r15d
0x180003aac  mov     [rsp+120h+var_E4], ecx
0x180003ab0  mov     [rsp+120h+var_100], r9b
0x180003ab5  test    ecx, ecx
0x180003ab7  jz      loc_180003BAF
0x180003abd  mov     eax, r13d
0x180003ac0  add     rax, rax
0x180003ac3  mov     ecx, [r11+rax*8]
0x180003ac7  mov     edx, [r11+rax*8+4]
0x180003acc  mov     [rsp+120h+var_E8], ecx
0x180003ad0  movzx   r14d, cl
0x180003ad4  mov     [rsp+120h+var_FC], edx
0x180003ad8  test    ecx, 0C0000000h
0x180003ade  jz      short loc_180003AEF
0x180003ae0  test    r10, r10
0x180003ae3  jz      short loc_180003AEF
0x180003ae5  cmp     edx, [rbp+47h+arg_20]
0x180003ae8  jnb     short loc_180003AEF
0x180003aea  mov     r8b, 1
0x180003aed  jmp     short loc_180003AF2
0x180003aef  xor     r8b, r8b
0x180003af2  mov     [rsp+120h+var_FF], r8b
0x180003af7  mov     [rsp+120h+var_F8], 0
0x180003aff  mov     [rsp+120h+var_D8], 0
0x180003b08  cmp     r14d, 5
0x180003b0c  jnz     short loc_180003B31
0x180003b0e  test    r15d, r15d
0x180003b11  jz      loc_180003CEA
0x180003b17  dec     r15d
0x180003b1a  mov     eax, r15d
0x180003b1d  add     rax, rax
0x180003b20  mov     rdi, [rbp+rax*8+47h+var_C0]
0x180003b25  mov     r12d, [rbp+rax*8+47h+var_B8]
0x180003b2a  mov     r9b, [rbp+rax*8+47h+var_B4]
0x180003b2f  jmp     short loc_180003B97
0x180003b31  test    r9b, r9b
0x180003b34  jnz     short loc_180003B4E
0x180003b36  test    r12d, r12d
0x180003b39  jnz     loc_180003BD8
0x180003b3f  lea     eax, [r14-2]
0x180003b43  test    eax, 0FFFFFFFDh
0x180003b48  jnz     loc_180003CEA
0x180003b4e  test    r8b, r8b
0x180003b51  jz      short loc_180003B69
0x180003b53  mov     eax, edx
0x180003b55  add     rax, rax
0x180003b58  mov     qword ptr [r10+rax*8+8], 0
0x180003b61  mov     dword ptr [r10+rax*8], 0
0x180003b69  lea     eax, [r14-3]
0x180003b6d  cmp     eax, 1
0x180003b70  ja      short loc_180003B9C
0x180003b72  cmp     r15d, 8
0x180003b76  jnb     loc_180003CEA
0x180003b7c  mov     eax, r15d
0x180003b7f  add     rax, rax
0x180003b82  inc     r15d
0x180003b85  mov     [rbp+rax*8+47h+var_B4], r9b
0x180003b8a  mov     r9b, 1
0x180003b8d  mov     [rbp+rax*8+47h+var_C0], rdi
0x180003b92  mov     [rbp+rax*8+47h+var_B8], r12d
0x180003b97  mov     [rsp+120h+var_100], r9b
0x180003b9c  inc     r13d
0x180003b9f  cmp     r13d, [rsp+120h+var_E4]
0x180003ba4  jb      loc_180003ABD
0x180003baa  mov     rax, [rsp+120h+var_E0]
0x180003baf  sub     edi, esi
0x180003bb1  mov     esi, edi
0x180003bb3  mov     [rax], r13d
0x180003bb6  mov     eax, esi
0x180003bb8  mov     rcx, [rbp+47h+var_40]
0x180003bbc  xor     rcx, rsp; StackCookie
0x180003bbf  call    __security_check_cookie
0x180003bc4  add     rsp, 0F0h
0x180003bcb  pop     r15
0x180003bcd  pop     r14
0x180003bcf  pop     r13
0x180003bd1  pop     r12
0x180003bd3  pop     rdi
0x180003bd4  pop     rsi
0x180003bd5  pop     rbp
0x180003bd6  retn
0x180003bd8  mov     rax, [r11+rax*8+8]
0x180003bdd  test    rax, rax
0x180003be0  jz      short loc_180003C0B
0x180003be2  mov     dl, [rdi]
0x180003be4  jmp     short loc_180003BED
0x180003be6  cmp     cl, dl
0x180003be8  jz      short loc_180003C0B
0x180003bea  inc     rax
0x180003bed  mov     cl, [rax]
0x180003bef  test    cl, cl
0x180003bf1  jnz     short loc_180003BE6
0x180003bf3  lea     eax, [r14-2]
0x180003bf7  test    eax, 0FFFFFFFDh
0x180003bfc  jnz     loc_180003CEA
0x180003c02  mov     edx, [rsp+120h+var_FC]
0x180003c06  jmp     loc_180003B4E
0x180003c0b  lea     r9, [rsp+120h+var_D8]
0x180003c10  mov     edx, r12d
0x180003c13  lea     r8, [rsp+120h+var_F8]
0x180003c18  mov     rcx, rdi
0x180003c1b  call    MinAsn1ExtractContent
0x180003c20  test    eax, eax
0x180003c22  jle     loc_180003CEA
0x180003c28  cmp     [rsp+120h+var_FF], 0
0x180003c2d  mov     r8d, [rsp+120h+var_F8]
0x180003c32  mov     r9, [rsp+120h+var_D8]
0x180003c37  mov     r10, [rsp+120h+var_F0]
0x180003c3c  lea     edx, [r8+rax]
0x180003c40  jz      short loc_180003C8D
0x180003c42  mov     eax, [rsp+120h+var_E8]
0x180003c46  bt      eax, 1Eh
0x180003c4a  jnb     short loc_180003C79
0x180003c4c  mov     ecx, [rsp+120h+var_FC]
0x180003c50  add     rcx, rcx
0x180003c53  mov     [r10+rcx*8+8], r9
0x180003c58  mov     [r10+rcx*8], r8d
0x180003c5c  cmp     byte ptr [rdi], 3
0x180003c5f  jnz     short loc_180003C8D
0x180003c61  test    r8d, r8d
0x180003c64  jz      short loc_180003C8D
0x180003c66  lea     rax, [r9+1]
0x180003c6a  mov     [r10+rcx*8+8], rax
0x180003c6f  lea     eax, [r8-1]
0x180003c73  mov     [r10+rcx*8], eax
0x180003c77  jmp     short loc_180003C8D
0x180003c79  test    eax, eax
0x180003c7b  jns     short loc_180003C8D
0x180003c7d  mov     eax, [rsp+120h+var_FC]
0x180003c81  add     rax, rax
0x180003c84  mov     [r10+rax*8+8], rdi
0x180003c89  mov     [r10+rax*8], edx
0x180003c8d  sub     r14d, 1
0x180003c91  jz      short loc_180003CE0
0x180003c93  sub     r14d, 1
0x180003c97  jz      short loc_180003CE0
0x180003c99  sub     r14d, 1
0x180003c9d  jz      short loc_180003CA5
0x180003c9f  cmp     r14d, 1
0x180003ca3  jnz     short loc_180003CEA
0x180003ca5  cmp     r15d, 8
0x180003ca9  jnb     short loc_180003CEA
0x180003cab  sub     r12d, edx
0x180003cae  mov     ecx, r15d
0x180003cb1  add     rcx, rcx
0x180003cb4  mov     eax, edx
0x180003cb6  add     rax, rdi
0x180003cb9  mov     rdi, r9
0x180003cbc  inc     r15d
0x180003cbf  mov     [rbp+rcx*8+47h+var_B8], r12d
0x180003cc4  mov     r12d, r8d
0x180003cc7  mov     [rbp+rcx*8+47h+var_C0], rax
0x180003ccc  mov     [rbp+rcx*8+47h+var_B4], 0
0x180003cd1  mov     r9b, [rsp+120h+var_100]
0x180003cd6  mov     r11, [rsp+120h+var_D0]
0x180003cdb  jmp     loc_180003B9C
0x180003ce0  mov     eax, edx
0x180003ce2  add     rdi, rax
0x180003ce5  sub     r12d, edx
0x180003ce8  jmp     short loc_180003CD1
0x180003cea  mov     rax, [rsp+120h+var_E0]
0x180003cef  sub     esi, edi
0x180003cf1  dec     esi
0x180003cf3  jmp     loc_180003BB3
```
