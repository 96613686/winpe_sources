# RtlpCombineAcls

- ea: `0x1800b0c30`
- end: `0x1800b1394`
- name: `RtlpCombineAcls`
- size: `1892`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b1420`
- `0x1800de100`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x1800b0c30`
- `0x1800b13a0`
- `0x180163a80`

## pseudocode

```c
__int64 __fastcall RtlpCombineAcls(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        unsigned __int64 a5,
        unsigned __int64 a6,
        __int64 *a7,
        _DWORD *a8)
{
  unsigned __int8 *v12; // r13
  unsigned __int8 *v13; // r12
  unsigned int v15; // r14d
  unsigned int v16; // r11d
  unsigned int v17; // edx
  unsigned int v18; // r9d
  unsigned __int8 *v19; // rcx
  unsigned int v20; // r15d
  __int64 v21; // r15
  __int64 Heap_0; // rax
  unsigned int v23; // ecx
  unsigned __int16 *v24; // rdx
  unsigned __int64 v25; // r9
  unsigned __int16 *v26; // rbx
  unsigned int v27; // ecx
  char *v28; // r15
  unsigned __int16 *v29; // rax
  char *v30; // rbx
  unsigned __int16 *v31; // rdi
  unsigned __int16 *v32; // rdi
  unsigned int v33; // r12d
  unsigned __int16 *v34; // rdi
  unsigned int v35; // ecx
  unsigned __int16 *v36; // rdi
  unsigned int v37; // ecx
  unsigned __int16 *v38; // rax
  unsigned int v39; // edx
  unsigned __int16 *v40; // r12
  char *v41; // r13
  unsigned int v42; // ecx
  unsigned __int8 *v43; // r8
  unsigned int v44; // ecx
  unsigned __int8 *v45; // r8
  unsigned int v46; // ecx
  unsigned __int8 *v47; // r8
  unsigned int v48; // r9d
  unsigned __int8 *v49; // r8
  unsigned int v50; // ecx
  unsigned __int8 *v51; // r8
  unsigned int v52; // [rsp+20h] [rbp-48h]
  unsigned int v53; // [rsp+20h] [rbp-48h]
  unsigned int v54; // [rsp+20h] [rbp-48h]
  unsigned int v55; // [rsp+20h] [rbp-48h]
  __int64 v56; // [rsp+28h] [rbp-40h]
  unsigned __int16 *v57; // [rsp+30h] [rbp-38h]
  unsigned int v58; // [rsp+70h] [rbp+8h]
  int Acl; // [rsp+70h] [rbp+8h]

  if ( a1 || a2 || a3 || a4 )
  {
    v13 = (unsigned __int8 *)a6;
    v12 = (unsigned __int8 *)a5;
  }
  else
  {
    v12 = (unsigned __int8 *)a5;
    v13 = (unsigned __int8 *)a6;
    if ( __PAIR128__(a6, a5) == 0 )
    {
      *a7 = 0;
      return 0;
    }
  }
  v15 = 0;
  v16 = 2;
  v56 = 0;
  v17 = 8;
  v58 = 2;
  if ( a1 )
  {
    v48 = 0;
    v49 = a1 + 8;
    while ( v48 < *((unsigned __int16 *)a1 + 2) )
    {
      if ( *v49 != 16 )
      {
        switch ( *v49 )
        {
          case 2u:
          case 3u:
          case 7u:
          case 8u:
          case 0xDu:
          case 0xEu:
          case 0xFu:
            break;
          default:
            goto LABEL_104;
        }
      }
      if ( v17 + *((unsigned __int16 *)v49 + 1) < v17 )
        goto LABEL_24;
      v17 += *((unsigned __int16 *)v49 + 1);
      if ( a8 )
        *a8 |= 8u;
      if ( *a1 > v16 )
      {
        v16 = *a1;
        v58 = v16;
      }
LABEL_104:
      ++v48;
      v49 += *((unsigned __int16 *)v49 + 1);
    }
  }
  if ( a2 )
  {
    v18 = 0;
    v19 = a2 + 8;
    while ( v18 < *((unsigned __int16 *)a2 + 2) )
    {
      if ( *v19 == 17 )
      {
        if ( v17 + *((unsigned __int16 *)v19 + 1) < v17 )
          goto LABEL_24;
        v17 += *((unsigned __int16 *)v19 + 1);
        if ( a8 )
          *a8 |= 0x10u;
        if ( *a2 > v16 )
        {
          v16 = *a2;
          v58 = v16;
        }
      }
      ++v18;
      v19 += *((unsigned __int16 *)v19 + 1);
    }
  }
  if ( v12 )
  {
    v50 = 0;
    v51 = v12 + 8;
    while ( v50 < *((unsigned __int16 *)v12 + 2) )
    {
      if ( *v51 == 20 )
      {
        if ( v17 + *((unsigned __int16 *)v51 + 1) < v17 )
          goto LABEL_24;
        v17 += *((unsigned __int16 *)v51 + 1);
        if ( a8 )
          *a8 |= 0x80u;
        if ( *v12 > v16 )
        {
          v16 = *v12;
          v58 = v16;
        }
      }
      ++v50;
      v51 += *((unsigned __int16 *)v51 + 1);
    }
  }
  if ( v13 )
  {
    v46 = 0;
    v47 = v13 + 8;
    while ( v46 < *((unsigned __int16 *)v13 + 2) )
    {
      if ( *v47 == 21 )
      {
        if ( v17 + *((unsigned __int16 *)v47 + 1) < v17 )
          goto LABEL_24;
        v17 += *((unsigned __int16 *)v47 + 1);
        if ( a8 )
          *a8 |= 0x100u;
        if ( *v13 > v16 )
        {
          v16 = *v13;
          v58 = v16;
        }
      }
      ++v46;
      v47 += *((unsigned __int16 *)v47 + 1);
    }
  }
  if ( a3 )
  {
    v42 = 0;
    v43 = a3 + 8;
    while ( v42 < *((unsigned __int16 *)a3 + 2) )
    {
      if ( *v43 == 18 )
      {
        if ( v17 + *((unsigned __int16 *)v43 + 1) < v17 )
          goto LABEL_24;
        v17 += *((unsigned __int16 *)v43 + 1);
        if ( a8 )
          *a8 |= 0x20u;
        if ( *a3 > v16 )
        {
          v16 = *a3;
          v58 = v16;
        }
      }
      ++v42;
      v43 += *((unsigned __int16 *)v43 + 1);
    }
  }
  if ( a4 )
  {
    v44 = 0;
    v45 = a4 + 8;
    while ( v44 < *((unsigned __int16 *)a4 + 2) )
    {
      if ( *v45 == 19 )
      {
        if ( v17 + *((unsigned __int16 *)v45 + 1) < v17 )
          goto LABEL_24;
        v17 += *((unsigned __int16 *)v45 + 1);
        if ( a8 )
          *a8 |= 0x40u;
        if ( *a4 > v16 )
        {
          v16 = *a4;
          v58 = v16;
        }
      }
      ++v44;
      v45 += *((unsigned __int16 *)v45 + 1);
    }
  }
  if ( v17 + 3 >= v17 )
  {
    v21 = (v17 + 3) & 0xFFFFFFFC;
    Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, (unsigned int)(NtdllBaseTag + 1310720), v21);
    v56 = Heap_0;
    if ( Heap_0 )
    {
      Acl = RtlCreateAcl(Heap_0, (unsigned int)v21, v58);
      v20 = Acl;
      if ( Acl < 0 )
      {
LABEL_52:
        RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v56);
        v56 = 0;
      }
      else
      {
        v23 = 0;
        v24 = (unsigned __int16 *)(v56 + 8);
        v25 = v56 + *(unsigned __int16 *)(v56 + 2);
        while ( v23 < *(unsigned __int16 *)(v56 + 4) )
        {
          if ( (unsigned __int64)v24 >= v25 )
          {
            v20 = -1073741699;
            goto LABEL_52;
          }
          ++v23;
          v24 = (unsigned __int16 *)((char *)v24 + v24[1]);
        }
        v57 = 0;
        if ( (unsigned __int64)v24 <= v25 )
          v57 = v24;
        if ( a1 )
        {
          v39 = 0;
          v55 = 0;
          if ( *((_WORD *)a1 + 2) )
          {
            v40 = (unsigned __int16 *)(a1 + 8);
            v41 = (char *)v57;
            do
            {
              if ( *(_BYTE *)v40 == 16 )
              {
LABEL_71:
                memmove(v41, v40, v40[1]);
                ++*(_WORD *)(v56 + 4);
                v39 = v55;
                v41 += v40[1];
              }
              else
              {
                switch ( *(_BYTE *)v40 )
                {
                  case 2:
                  case 3:
                  case 7:
                  case 8:
                  case 0xD:
                  case 0xE:
                  case 0xF:
                    goto LABEL_71;
                  default:
                    break;
                }
              }
              ++v39;
              v40 = (unsigned __int16 *)((char *)v40 + v40[1]);
              v55 = v39;
            }
            while ( v39 < *((unsigned __int16 *)a1 + 2) );
            v20 = Acl;
            v15 = 0;
            v13 = (unsigned __int8 *)a6;
            v57 = (unsigned __int16 *)v41;
            v12 = (unsigned __int8 *)a5;
          }
        }
        if ( a2 )
        {
          v26 = (unsigned __int16 *)(a2 + 8);
          v27 = 0;
          v52 = 0;
          if ( *((_WORD *)a2 + 2) )
          {
            v28 = (char *)v57;
            do
            {
              v29 = v26 + 1;
              if ( *(_BYTE *)v26 == 17 )
              {
                memmove(v28, v26, *v29);
                ++*(_WORD *)(v56 + 4);
                v27 = v52;
                v28 += v26[1];
                v29 = v26 + 1;
              }
              ++v27;
              v26 = (unsigned __int16 *)((char *)v26 + *v29);
              v52 = v27;
            }
            while ( v27 < *((unsigned __int16 *)a2 + 2) );
            v13 = (unsigned __int8 *)a6;
            v57 = (unsigned __int16 *)v28;
            v20 = Acl;
          }
        }
        v30 = (char *)v57;
        if ( v12 )
        {
          v36 = (unsigned __int16 *)(v12 + 8);
          v37 = 0;
          v54 = 0;
          if ( *((_WORD *)v12 + 2) )
          {
            do
            {
              v38 = v36 + 1;
              if ( *(_BYTE *)v36 == 20 )
              {
                memmove(v30, v36, *v38);
                ++*(_WORD *)(v56 + 4);
                v37 = v54;
                v30 += v36[1];
                v38 = v36 + 1;
              }
              ++v37;
              v36 = (unsigned __int16 *)((char *)v36 + *v38);
              v54 = v37;
            }
            while ( v37 < *((unsigned __int16 *)v12 + 2) );
            v20 = Acl;
          }
        }
        if ( v13 )
        {
          v34 = (unsigned __int16 *)(v13 + 8);
          v35 = 0;
          v53 = 0;
          if ( *((_WORD *)v13 + 2) )
          {
            do
            {
              if ( *(_BYTE *)v34 == 21 )
              {
                memmove(v30, v34, v34[1]);
                ++*(_WORD *)(v56 + 4);
                v35 = v53;
                v30 += v34[1];
              }
              ++v35;
              v34 = (unsigned __int16 *)((char *)v34 + v34[1]);
              v53 = v35;
            }
            while ( v35 < *((unsigned __int16 *)v13 + 2) );
            v20 = Acl;
          }
        }
        if ( a3 )
        {
          v32 = (unsigned __int16 *)(a3 + 8);
          v33 = 0;
          if ( *((_WORD *)a3 + 2) )
          {
            do
            {
              if ( *(_BYTE *)v32 == 18 )
              {
                memmove(v30, v32, v32[1]);
                ++*(_WORD *)(v56 + 4);
                v30 += v32[1];
              }
              ++v33;
              v32 = (unsigned __int16 *)((char *)v32 + v32[1]);
            }
            while ( v33 < *((unsigned __int16 *)a3 + 2) );
            v20 = Acl;
          }
        }
        if ( a4 )
        {
          v31 = (unsigned __int16 *)(a4 + 8);
          if ( *((_WORD *)a4 + 2) )
          {
            do
            {
              if ( *(_BYTE *)v31 == 19 )
              {
                memmove(v30, v31, v31[1]);
                ++*(_WORD *)(v56 + 4);
                v30 += v31[1];
              }
              ++v15;
              v31 = (unsigned __int16 *)((char *)v31 + v31[1]);
            }
            while ( v15 < *((unsigned __int16 *)a4 + 2) );
            v20 = Acl;
          }
        }
      }
    }
    else
    {
      v20 = -1073741801;
    }
  }
  else
  {
LABEL_24:
    v20 = -1073741675;
  }
  *a7 = v56;
  return v20;
}

```

## disassembly

```asm
0x1800b0c30  mov     [rsp+arg_10], rbx
0x1800b0c35  mov     [rsp+arg_18], rbp
0x1800b0c3a  push    rsi
0x1800b0c3b  push    rdi
0x1800b0c3c  push    r12
0x1800b0c3e  push    r13
0x1800b0c40  push    r14
0x1800b0c42  sub     rsp, 40h
0x1800b0c46  mov     rbp, r9
0x1800b0c49  mov     rsi, r8
0x1800b0c4c  mov     rdi, rdx
0x1800b0c4f  mov     rbx, rcx
0x1800b0c52  test    rcx, rcx
0x1800b0c55  jnz     short loc_1800B0CAA
0x1800b0c57  test    rdx, rdx
0x1800b0c5a  jnz     short loc_1800B0CAA
0x1800b0c5c  test    r8, r8
0x1800b0c5f  jnz     short loc_1800B0CAA
0x1800b0c61  test    r9, r9
0x1800b0c64  jnz     short loc_1800B0CAA
0x1800b0c66  mov     r13, [rsp+68h+arg_20]
0x1800b0c6e  mov     r12, [rsp+68h+arg_28]
0x1800b0c76  test    r13, r13
0x1800b0c79  jnz     short loc_1800B0CBA
0x1800b0c7b  test    r12, r12
0x1800b0c7e  jnz     short loc_1800B0CBA
0x1800b0c80  mov     rax, [rsp+68h+arg_30]
0x1800b0c88  xor     r14d, r14d
0x1800b0c8b  mov     [rax], r14
0x1800b0c8e  xor     eax, eax
0x1800b0c90  lea     r11, [rsp+68h+var_28]
0x1800b0c95  mov     rbx, [r11+40h]
0x1800b0c99  mov     rbp, [r11+48h]
0x1800b0c9d  mov     rsp, r11
0x1800b0ca0  pop     r14
0x1800b0ca2  pop     r13
0x1800b0ca4  pop     r12
0x1800b0ca6  pop     rdi
0x1800b0ca7  pop     rsi
0x1800b0ca8  retn
0x1800b0caa  mov     r12, [rsp+68h+arg_28]
0x1800b0cb2  mov     r13, [rsp+68h+arg_20]
0x1800b0cba  mov     r10, [rsp+68h+arg_38]
0x1800b0cc2  xor     r14d, r14d
0x1800b0cc5  mov     [rsp+68h+arg_8], r15
0x1800b0cca  mov     r11d, 2
0x1800b0cd0  mov     [rsp+68h+var_40], r14
0x1800b0cd5  mov     edx, 8
0x1800b0cda  mov     [rsp+68h+arg_0], r11d
0x1800b0cdf  lea     r15, cs:180000000h
0x1800b0ce6  test    rbx, rbx
0x1800b0ce9  jnz     loc_1800B1182
0x1800b0cef  test    rdi, rdi
0x1800b0cf2  jz      short loc_1800B0D3D
0x1800b0cf4  mov     r9d, r14d
0x1800b0cf7  lea     rcx, [rdi+8]
0x1800b0cfb  movzx   eax, word ptr [rdi+4]
0x1800b0cff  cmp     r9d, eax
0x1800b0d02  jnb     short loc_1800B0D3D
0x1800b0d04  cmp     byte ptr [rcx], 11h
0x1800b0d07  jnz     short loc_1800B0D31
0x1800b0d09  movzx   r8d, word ptr [rcx+2]
0x1800b0d0e  add     r8d, edx
0x1800b0d11  cmp     r8d, edx
0x1800b0d14  jb      short loc_1800B0D68
0x1800b0d16  mov     edx, r8d
0x1800b0d19  test    r10, r10
0x1800b0d1c  jz      short loc_1800B0D22
0x1800b0d1e  or      dword ptr [r10], 10h
0x1800b0d22  movzx   eax, byte ptr [rdi]
0x1800b0d25  cmp     eax, r11d
0x1800b0d28  jbe     short loc_1800B0D31
0x1800b0d2a  mov     r11d, eax
0x1800b0d2d  mov     [rsp+68h+arg_0], eax
0x1800b0d31  movzx   eax, word ptr [rcx+2]
0x1800b0d35  inc     r9d
0x1800b0d38  add     rcx, rax
0x1800b0d3b  jmp     short loc_1800B0CFB
0x1800b0d3d  test    r13, r13
0x1800b0d40  jnz     loc_1800B11CE
0x1800b0d46  test    r12, r12
0x1800b0d49  jnz     loc_1800B1156
0x1800b0d4f  test    rsi, rsi
0x1800b0d52  jnz     loc_1800B1104
0x1800b0d58  test    rbp, rbp
0x1800b0d5b  jnz     loc_1800B112D
0x1800b0d61  lea     eax, [rdx+3]
0x1800b0d64  cmp     eax, edx
0x1800b0d66  jnb     short loc_1800B0D8B
0x1800b0d68  mov     r15d, 0C0000095h
0x1800b0d6e  mov     rax, [rsp+68h+arg_30]
0x1800b0d76  mov     rdx, [rsp+68h+var_40]
0x1800b0d7b  mov     [rax], rdx
0x1800b0d7e  mov     eax, r15d
0x1800b0d81  mov     r15, [rsp+68h+arg_8]
0x1800b0d86  jmp     loc_1800B0C90
0x1800b0d8b  mov     rcx, gs:60h
0x1800b0d94  and     eax, 0FFFFFFFCh
0x1800b0d97  mov     edx, cs:NtdllBaseTag
0x1800b0d9d  mov     r8d, eax
0x1800b0da0  add     edx, 140000h
0x1800b0da6  mov     r15d, eax
0x1800b0da9  mov     rcx, [rcx+30h]
0x1800b0dad  call    RtlAllocateHeap_0
0x1800b0db2  mov     [rsp+68h+var_40], rax
0x1800b0db7  test    rax, rax
0x1800b0dba  jz      loc_1800B12F9
0x1800b0dc0  mov     r8d, [rsp+68h+arg_0]
0x1800b0dc5  mov     edx, r15d
0x1800b0dc8  mov     rcx, rax
0x1800b0dcb  call    RtlCreateAcl
0x1800b0dd0  mov     [rsp+68h+arg_0], eax
0x1800b0dd4  mov     r15d, eax
0x1800b0dd7  test    eax, eax
0x1800b0dd9  js      loc_1800B0F28
0x1800b0ddf  mov     rax, [rsp+68h+var_40]
0x1800b0de4  mov     ecx, r14d
0x1800b0de7  movzx   r9d, word ptr [rax+2]
0x1800b0dec  lea     rdx, [rax+8]
0x1800b0df0  movzx   r8d, word ptr [rax+4]
0x1800b0df5  add     r9, rax
0x1800b0df8  cmp     ecx, r8d
0x1800b0dfb  jnb     short loc_1800B0E11
0x1800b0dfd  cmp     rdx, r9
0x1800b0e00  jnb     loc_1800B0F22
0x1800b0e06  movzx   eax, word ptr [rdx+2]
0x1800b0e0a  inc     ecx
0x1800b0e0c  add     rdx, rax
0x1800b0e0f  jmp     short loc_1800B0DF8
0x1800b0e11  mov     [rsp+68h+var_38], r14
0x1800b0e16  cmp     rdx, r9
0x1800b0e19  ja      short loc_1800B0E20
0x1800b0e1b  mov     [rsp+68h+var_38], rdx
0x1800b0e20  test    rbx, rbx
0x1800b0e23  jnz     loc_1800B1073
0x1800b0e29  test    rdi, rdi
0x1800b0e2c  jz      short loc_1800B0EA7
0x1800b0e2e  lea     rbx, [rdi+8]
0x1800b0e32  mov     ecx, r14d
0x1800b0e35  mov     [rsp+68h+var_48], ecx
0x1800b0e39  cmp     r14w, [rdi+4]
0x1800b0e3e  jnb     short loc_1800B0EA7
0x1800b0e40  mov     r12, [rsp+68h+var_40]
0x1800b0e45  mov     r15, [rsp+68h+var_38]
0x1800b0e4a  cmp     byte ptr [rbx], 11h
0x1800b0e4d  lea     rax, [rbx+2]
0x1800b0e51  mov     [rsp+68h+var_38], rax
0x1800b0e56  jnz     short loc_1800B0E81
0x1800b0e58  movzx   r8d, word ptr [rax]; Size
0x1800b0e5c  mov     rdx, rbx; Src
0x1800b0e5f  mov     rcx, r15; void *
0x1800b0e62  call    memmove
0x1800b0e67  inc     word ptr [r12+4]
0x1800b0e6d  mov     rax, [rsp+68h+var_38]
0x1800b0e72  mov     ecx, [rsp+68h+var_48]
0x1800b0e76  movzx   eax, word ptr [rax]
0x1800b0e79  add     r15, rax
0x1800b0e7c  mov     rax, [rsp+68h+var_38]
0x1800b0e81  movzx   eax, word ptr [rax]
0x1800b0e84  inc     ecx
0x1800b0e86  add     rbx, rax
0x1800b0e89  mov     [rsp+68h+var_48], ecx
0x1800b0e8d  movzx   eax, word ptr [rdi+4]
0x1800b0e91  cmp     ecx, eax
0x1800b0e93  jb      short loc_1800B0E4A
0x1800b0e95  mov     r12, [rsp+68h+arg_28]
0x1800b0e9d  mov     [rsp+68h+var_38], r15
0x1800b0ea2  mov     r15d, [rsp+68h+arg_0]
0x1800b0ea7  mov     rbx, [rsp+68h+var_38]
0x1800b0eac  test    r13, r13
0x1800b0eaf  jnz     loc_1800B1003
0x1800b0eb5  test    r12, r12
0x1800b0eb8  jnz     loc_1800B0FA0
0x1800b0ebe  test    rsi, rsi
0x1800b0ec1  jnz     loc_1800B0F4B
0x1800b0ec7  test    rbp, rbp
0x1800b0eca  jz      loc_1800B0D6E
0x1800b0ed0  lea     rdi, [rbp+8]
0x1800b0ed4  cmp     r14w, [rbp+4]
0x1800b0ed9  jnb     loc_1800B0D6E
0x1800b0edf  mov     r15, [rsp+68h+var_40]
0x1800b0ee4  cmp     byte ptr [rdi], 13h
0x1800b0ee7  jnz     short loc_1800B0F05
0x1800b0ee9  movzx   r8d, word ptr [rdi+2]; Size
0x1800b0eee  mov     rdx, rdi; Src
0x1800b0ef1  mov     rcx, rbx; void *
0x1800b0ef4  call    memmove
0x1800b0ef9  inc     word ptr [r15+4]
0x1800b0efe  movzx   eax, word ptr [rdi+2]
0x1800b0f02  add     rbx, rax
0x1800b0f05  movzx   eax, word ptr [rdi+2]
0x1800b0f09  inc     r14d
0x1800b0f0c  add     rdi, rax
0x1800b0f0f  movzx   eax, word ptr [rbp+4]
0x1800b0f13  cmp     r14d, eax
0x1800b0f16  jb      short loc_1800B0EE4
0x1800b0f18  mov     r15d, [rsp+68h+arg_0]
0x1800b0f1d  jmp     loc_1800B0D6E
0x1800b0f22  mov     r15d, 0C000007Dh
0x1800b0f28  mov     rcx, gs:60h
0x1800b0f31  xor     edx, edx
0x1800b0f33  mov     r8, [rsp+68h+var_40]
0x1800b0f38  mov     rcx, [rcx+30h]
0x1800b0f3c  call    RtlFreeHeap_0
0x1800b0f41  mov     [rsp+68h+var_40], r14
0x1800b0f46  jmp     loc_1800B0D6E
0x1800b0f4b  lea     rdi, [rsi+8]
0x1800b0f4f  mov     r12d, r14d
0x1800b0f52  cmp     r14w, [rsi+4]
0x1800b0f57  jnb     loc_1800B0EC7
0x1800b0f5d  mov     r15, [rsp+68h+var_40]
0x1800b0f62  cmp     byte ptr [rdi], 12h
0x1800b0f65  jnz     short loc_1800B0F83
0x1800b0f67  movzx   r8d, word ptr [rdi+2]; Size
0x1800b0f6c  mov     rdx, rdi; Src
0x1800b0f6f  mov     rcx, rbx; void *
0x1800b0f72  call    memmove
0x1800b0f77  inc     word ptr [r15+4]
0x1800b0f7c  movzx   eax, word ptr [rdi+2]
0x1800b0f80  add     rbx, rax
0x1800b0f83  movzx   eax, word ptr [rdi+2]
0x1800b0f87  inc     r12d
0x1800b0f8a  add     rdi, rax
0x1800b0f8d  movzx   eax, word ptr [rsi+4]
0x1800b0f91  cmp     r12d, eax
0x1800b0f94  jb      short loc_1800B0F62
0x1800b0f96  mov     r15d, [rsp+68h+arg_0]
0x1800b0f9b  jmp     loc_1800B0EC7
0x1800b0fa0  lea     rdi, [r12+8]
0x1800b0fa5  mov     ecx, r14d
0x1800b0fa8  mov     [rsp+68h+var_48], ecx
0x1800b0fac  cmp     r14w, [r12+4]
0x1800b0fb2  jnb     loc_1800B0EBE
0x1800b0fb8  mov     r15, [rsp+68h+var_40]
0x1800b0fbd  cmp     byte ptr [rdi], 15h
0x1800b0fc0  jnz     short loc_1800B0FE2
0x1800b0fc2  movzx   r8d, word ptr [rdi+2]; Size
0x1800b0fc7  mov     rdx, rdi; Src
0x1800b0fca  mov     rcx, rbx; void *
0x1800b0fcd  call    memmove
0x1800b0fd2  inc     word ptr [r15+4]
0x1800b0fd7  movzx   eax, word ptr [rdi+2]
0x1800b0fdb  mov     ecx, [rsp+68h+var_48]
0x1800b0fdf  add     rbx, rax
0x1800b0fe2  movzx   eax, word ptr [rdi+2]
0x1800b0fe6  inc     ecx
0x1800b0fe8  add     rdi, rax
0x1800b0feb  mov     [rsp+68h+var_48], ecx
0x1800b0fef  movzx   eax, word ptr [r12+4]
0x1800b0ff5  cmp     ecx, eax
0x1800b0ff7  jb      short loc_1800B0FBD
0x1800b0ff9  mov     r15d, [rsp+68h+arg_0]
0x1800b0ffe  jmp     loc_1800B0EBE
0x1800b1003  lea     rdi, [r13+8]
0x1800b1007  mov     ecx, r14d
0x1800b100a  mov     [rsp+68h+var_48], ecx
0x1800b100e  cmp     r14w, [r13+4]
0x1800b1013  jnb     loc_1800B0EB5
0x1800b1019  mov     r15, [rsp+68h+var_40]
0x1800b101e  cmp     byte ptr [rdi], 14h
0x1800b1021  lea     rax, [rdi+2]
0x1800b1025  mov     [rsp+68h+var_38], rax
0x1800b102a  jnz     short loc_1800B1054
0x1800b102c  movzx   r8d, word ptr [rax]; Size
0x1800b1030  mov     rdx, rdi; Src
0x1800b1033  mov     rcx, rbx; void *
0x1800b1036  call    memmove
0x1800b103b  inc     word ptr [r15+4]
0x1800b1040  mov     rax, [rsp+68h+var_38]
0x1800b1045  mov     ecx, [rsp+68h+var_48]
0x1800b1049  movzx   eax, word ptr [rax]
0x1800b104c  add     rbx, rax
0x1800b104f  mov     rax, [rsp+68h+var_38]
0x1800b1054  movzx   eax, word ptr [rax]
0x1800b1057  inc     ecx
0x1800b1059  add     rdi, rax
0x1800b105c  mov     [rsp+68h+var_48], ecx
0x1800b1060  movzx   eax, word ptr [r13+4]
0x1800b1065  cmp     ecx, eax
0x1800b1067  jb      short loc_1800B101E
0x1800b1069  mov     r15d, [rsp+68h+arg_0]
0x1800b106e  jmp     loc_1800B0EB5
0x1800b1073  mov     edx, r14d
0x1800b1076  mov     [rsp+68h+var_48], edx
0x1800b107a  cmp     r14w, [rbx+4]
0x1800b107f  jnb     loc_1800B0E29
0x1800b1085  mov     r15, [rsp+68h+var_40]
0x1800b108a  lea     r12, [rbx+8]
0x1800b108e  mov     r13, [rsp+68h+var_38]
0x1800b1093  lea     r14, cs:180000000h
0x1800b109a  movzx   eax, byte ptr [r12]
0x1800b109f  cmp     eax, 10h
0x1800b10a2  jnz     loc_1800B1304
0x1800b10a8  movzx   r8d, word ptr [r12+2]; jumptable 00000001800B131D cases 2,3,7,8,13-15
0x1800b10ae  mov     rdx, r12; Src
0x1800b10b1  mov     rcx, r13; void *
0x1800b10b4  call    memmove
0x1800b10b9  inc     word ptr [r15+4]
0x1800b10be  movzx   eax, word ptr [r12+2]
0x1800b10c4  mov     edx, [rsp+68h+var_48]
  ... truncated ...
```
