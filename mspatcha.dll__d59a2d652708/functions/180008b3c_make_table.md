# make_table

- ea: `0x180008b3c`
- end: `0x180008dab`
- name: `make_table`
- size: `623`
- prototype: `__int64 __fastcall(int, int, int, int, void *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007c94`
- `0x1800087b0`

## callees

- `0x180001400`
- `0x180001cae`
- `0x180008b3c`

## pseudocode

```c
__int64 __fastcall make_table(__int64 a1, int a2, __int64 a3, unsigned __int8 a4, char *a5, __int64 a6)
{
  __int64 v6; // r15
  __int64 v7; // r9
  unsigned int v9; // ecx
  __int64 v10; // rax
  unsigned int v11; // edx
  __int64 v12; // rdi
  unsigned int v14; // edi
  char v15; // bl
  __int64 v16; // rdx
  char v17; // cl
  __int64 v18; // rax
  int v19; // edx
  __int64 v20; // rdx
  int v21; // r8d
  int v22; // r11d
  __int64 v23; // rdx
  unsigned int v24; // r10d
  unsigned __int64 v25; // rdi
  unsigned int v26; // r9d
  __int64 v27; // rcx
  char *v28; // rdi
  char v29; // dl
  unsigned __int64 v30; // rax
  int v31; // edi
  char *v32; // r9
  __int16 v33; // ax
  __int64 v34; // rcx
  __int64 v35; // rax
  int v37; // [rsp+30h] [rbp-99h]
  __int128 v38; // [rsp+34h] [rbp-95h]
  __int128 v39; // [rsp+44h] [rbp-85h]
  __int128 v40; // [rsp+54h] [rbp-75h]
  __int128 v41; // [rsp+64h] [rbp-65h]
  _DWORD v43[16]; // [rsp+84h] [rbp-45h]
  int Val; // [rsp+C4h] [rbp-5h]

  v6 = a4;
  v7 = a3;
  v9 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  if ( a2 )
  {
    while ( *(_BYTE *)(v9 + a3) <= 0x10u )
    {
      v10 = *(unsigned __int8 *)(v9++ + a3);
      ++*(&v37 + v10);
      if ( v9 >= a2 )
        goto LABEL_4;
    }
    return 0;
  }
LABEL_4:
  v43[0] = 0;
  v11 = 1;
  do
  {
    v12 = v11 + 1;
    v43[v12 - 1] = v43[v11 - 1] + (*(&v37 + v11) << (16 - v11));
    ++v11;
  }
  while ( (unsigned int)v12 <= 0x10 );
  if ( Val == 0x10000 )
  {
    v14 = 1;
    v15 = 16 - v6;
    if ( !(_DWORD)v6 )
      goto LABEL_13;
    do
    {
      v16 = v14;
      v43[v14 - 1] = (unsigned int)v43[v14 - 1] >> v15;
      v17 = v6 - v14++;
      *(&v37 + v16) = 1 << v17;
    }
    while ( v14 <= (unsigned int)v6 );
    while ( v14 <= 0x10 )
    {
LABEL_13:
      v18 = v14;
      v19 = 1 << (16 - v14++);
      *(&v37 + v18) = v19;
    }
    v20 = (unsigned int)(v43[v6] >> v15);
    if ( (_DWORD)v20 != 0x10000 )
    {
      memset_0(&a5[2 * v20], 0, 2LL * (unsigned int)((1 << v6) - v20));
      v7 = a3;
    }
    if ( a2 > 0 )
    {
      v21 = 0;
      v22 = a2;
      do
      {
        v23 = *(unsigned __int8 *)((unsigned int)v21 + v7);
        if ( (_BYTE)v23 )
        {
          v24 = *(&v37 + v23);
          v25 = (unsigned int)v43[v23 - 1];
          v26 = v24 + v25;
          if ( (unsigned __int8)v23 > (unsigned __int8)v6 )
          {
            v43[v23 - 1] = v26;
            v29 = v23 - v6;
            v30 = v25 >> v15;
            v31 = (_DWORD)v25 << v6;
            v32 = &a5[2 * v30];
            do
            {
              v33 = *(_WORD *)v32;
              if ( !*(_WORD *)v32 )
              {
                v34 = 2 * v22;
                v33 = -(__int16)v22++;
                *(_DWORD *)(a6 + 2 * v34) = 0;
                *(_WORD *)v32 = v33;
              }
              if ( (v31 & 0x8000u) == 0 )
                v35 = -2 * v33;
              else
                v35 = 1 - 2 * v33;
              LOWORD(v31) = 2 * v31;
              v32 = (char *)(a6 + 2 * v35);
              --v29;
            }
            while ( v29 );
            *(_WORD *)v32 = v21;
          }
          else
          {
            if ( v26 > 1 << v6 )
              return 0;
            if ( (unsigned int)v25 < v26 )
            {
              v27 = v24;
              v28 = &a5[2 * v25];
              while ( v27 )
              {
                *(_WORD *)v28 = v21;
                v28 += 2;
                --v27;
              }
            }
            v43[v23 - 1] = v26;
          }
          v7 = a3;
        }
        ++v21;
      }
      while ( v21 < a2 );
    }
    return 1;
  }
  if ( !Val )
  {
    memset_0(a5, 0, 2 * (1LL << v6));
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180008b3c  mov     [rsp-8+arg_0], rbx
0x180008b41  push    rbp
0x180008b42  push    rsi
0x180008b43  push    rdi
0x180008b44  push    r12
0x180008b46  push    r13
0x180008b48  push    r14
0x180008b4a  push    r15
0x180008b4c  lea     rbp, [rsp-17h]
0x180008b51  sub     rsp, 0E0h
0x180008b58  mov     rax, cs:__security_cookie
0x180008b5f  xor     rax, rsp
0x180008b62  mov     [rbp+47h+var_40], rax
0x180008b66  mov     r12, [rbp+47h+arg_20]
0x180008b6a  xorps   xmm0, xmm0
0x180008b6d  mov     r13, [rbp+47h+arg_28]
0x180008b71  xor     r10d, r10d
0x180008b74  movzx   r15d, r9b
0x180008b78  mov     r9, r8
0x180008b7b  mov     [rsp+110h+var_F0], r8
0x180008b80  mov     esi, edx
0x180008b82  mov     ecx, r10d
0x180008b85  lea     r11d, [r10+10h]
0x180008b89  movups  [rsp+110h+var_DC], xmm0
0x180008b8e  movups  [rsp+110h+var_CC], xmm0
0x180008b93  movups  [rbp+47h+var_BC], xmm0
0x180008b97  movups  [rbp+47h+var_AC], xmm0
0x180008b9b  test    edx, edx
0x180008b9d  jz      short loc_180008BBA
0x180008b9f  mov     eax, ecx
0x180008ba1  cmp     [rax+r8], r11b
0x180008ba5  ja      loc_180008DA4
0x180008bab  movzx   eax, byte ptr [rax+r8]
0x180008bb0  inc     ecx
0x180008bb2  inc     [rsp+rax*4+110h+var_E0]
0x180008bb6  cmp     ecx, esi
0x180008bb8  jb      short loc_180008B9F
0x180008bba  mov     [rbp+47h+var_8C], r10d
0x180008bbe  mov     edx, 1
0x180008bc3  lea     edi, [rdx+1]
0x180008bc6  mov     eax, edx
0x180008bc8  mov     ecx, r11d
0x180008bcb  sub     ecx, edx
0x180008bcd  mov     edx, [rsp+rax*4+110h+var_E0]
0x180008bd1  shl     edx, cl
0x180008bd3  add     edx, [rbp+rax*4+47h+var_90]
0x180008bd7  mov     [rbp+rdi*4+47h+var_90], edx
0x180008bdb  mov     edx, edi
0x180008bdd  cmp     edi, r11d
0x180008be0  jbe     short loc_180008BC3
0x180008be2  mov     edx, [rbp+47h+Val]; Val
0x180008be5  cmp     edx, 10000h
0x180008beb  jz      short loc_180008C36
0x180008bed  test    edx, edx
0x180008bef  jnz     loc_180008DA4
0x180008bf5  mov     ecx, r15d
0x180008bf8  lea     r8d, [rdx+1]
0x180008bfc  shl     r8, cl
0x180008bff  mov     rcx, r12; void *
0x180008c02  add     r8, r8; Size
0x180008c05  call    memset_0
0x180008c0a  mov     eax, 1
0x180008c0f  mov     rcx, [rbp+47h+var_40]
0x180008c13  xor     rcx, rsp; StackCookie
0x180008c16  call    __security_check_cookie
0x180008c1b  mov     rbx, [rsp+110h+arg_0]
0x180008c23  add     rsp, 0E0h
0x180008c2a  pop     r15
0x180008c2c  pop     r14
0x180008c2e  pop     r13
0x180008c30  pop     r12
0x180008c32  pop     rdi
0x180008c33  pop     rsi
0x180008c34  pop     rbp
0x180008c35  retn
0x180008c36  mov     ebx, r11d
0x180008c39  mov     edi, 1
0x180008c3e  sub     bl, r15b
0x180008c41  cmp     r15d, edi
0x180008c44  jb      short loc_180008C6C
0x180008c46  movzx   r8d, bl
0x180008c4a  mov     edx, edi
0x180008c4c  mov     ecx, r8d
0x180008c4f  mov     eax, 1
0x180008c54  shr     [rbp+rdx*4+47h+var_90], cl
0x180008c58  mov     ecx, r15d
0x180008c5b  sub     ecx, edi
0x180008c5d  inc     edi
0x180008c5f  shl     eax, cl
0x180008c61  mov     [rsp+rdx*4+110h+var_E0], eax
0x180008c65  cmp     edi, r15d
0x180008c68  jbe     short loc_180008C4A
0x180008c6a  jmp     short loc_180008C80
0x180008c6c  mov     eax, edi
0x180008c6e  mov     ecx, r11d
0x180008c71  sub     ecx, edi
0x180008c73  mov     edx, 1
0x180008c78  shl     edx, cl
0x180008c7a  inc     edi
0x180008c7c  mov     [rsp+rax*4+110h+var_E0], edx
0x180008c80  cmp     edi, r11d
0x180008c83  jbe     short loc_180008C6C
0x180008c85  mov     edx, [rbp+r15*4+47h+var_8C]
0x180008c8a  mov     cl, bl
0x180008c8c  shr     edx, cl
0x180008c8e  cmp     edx, 10000h
0x180008c94  jz      short loc_180008CBB
0x180008c96  mov     ecx, r15d
0x180008c99  mov     r8d, 1
0x180008c9f  shl     r8d, cl
0x180008ca2  lea     rcx, [r12+rdx*2]; void *
0x180008ca6  sub     r8d, edx
0x180008ca9  xor     edx, edx; Val
0x180008cab  add     r8, r8; Size
0x180008cae  call    memset_0
0x180008cb3  mov     r9, [rsp+110h+var_F0]
0x180008cb8  xor     r10d, r10d
0x180008cbb  test    esi, esi
0x180008cbd  jle     loc_180008C0A
0x180008cc3  mov     r8d, r10d
0x180008cc6  movzx   ebx, bl
0x180008cc9  mov     r11d, esi
0x180008ccc  mov     eax, r8d
0x180008ccf  movzx   edx, byte ptr [rax+r9]
0x180008cd4  test    dl, dl
0x180008cd6  jz      loc_180008D93
0x180008cdc  mov     r10d, [rsp+rdx*4+110h+var_E0]
0x180008ce1  mov     edi, [rbp+rdx*4+47h+var_90]
0x180008ce5  lea     r9d, [r10+rdi]
0x180008ce9  cmp     dl, r15b
0x180008cec  ja      short loc_180008D1E
0x180008cee  mov     ecx, r15d
0x180008cf1  mov     eax, 1
0x180008cf6  shl     eax, cl
0x180008cf8  cmp     r9d, eax
0x180008cfb  ja      loc_180008DA4
0x180008d01  cmp     edi, r9d
0x180008d04  jnb     short loc_180008D14
0x180008d06  mov     ecx, r10d
0x180008d09  movsx   rax, r8w
0x180008d0d  lea     rdi, [r12+rdi*2]
0x180008d11  rep stosw
0x180008d14  mov     [rbp+rdx*4+47h+var_90], r9d
0x180008d19  xor     r10d, r10d
0x180008d1c  jmp     short loc_180008D8E
0x180008d1e  mov     rax, rdi
0x180008d21  mov     [rbp+rdx*4+47h+var_90], r9d
0x180008d26  mov     rcx, rbx
0x180008d29  sub     dl, r15b
0x180008d2c  shr     rax, cl
0x180008d2f  mov     ecx, r15d
0x180008d32  shl     edi, cl
0x180008d34  xor     r10d, r10d
0x180008d37  lea     r9, [r12+rax*2]
0x180008d3b  movzx   eax, word ptr [r9]
0x180008d3f  test    ax, ax
0x180008d42  jnz     short loc_180008D5E
0x180008d44  lea     eax, [r11+r11]
0x180008d48  movsxd  rcx, eax
0x180008d4b  movzx   eax, r11w
0x180008d4f  neg     ax
0x180008d52  inc     r11d
0x180008d55  mov     [r13+rcx*2+0], r10d
0x180008d5a  mov     [r9], ax
0x180008d5e  cwde
0x180008d5f  test    di, di
0x180008d62  jns     short loc_180008D72
0x180008d64  add     eax, eax
0x180008d66  mov     ecx, 1
0x180008d6b  sub     ecx, eax
0x180008d6d  movsxd  rax, ecx
0x180008d70  jmp     short loc_180008D78
0x180008d72  neg     eax
0x180008d74  add     eax, eax
0x180008d76  cdqe
0x180008d78  lea     r9, ds:0[rax*2]
0x180008d80  add     edi, edi
0x180008d82  add     r9, r13
0x180008d85  add     dl, 0FFh
0x180008d88  jnz     short loc_180008D3B
0x180008d8a  mov     [r9], r8w
0x180008d8e  mov     r9, [rsp+110h+var_F0]
0x180008d93  inc     r8d
0x180008d96  cmp     r8d, esi
0x180008d99  jl      loc_180008CCC
0x180008d9f  jmp     loc_180008C0A
0x180008da4  xor     eax, eax
0x180008da6  jmp     loc_180008C0F
```
