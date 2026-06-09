# RtlpCombineAcls

- ea: `0x18003bf30`
- end: `0x18003c694`
- name: `RtlpCombineAcls`
- size: `1892`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003c720`
- `0x1800de220`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x18003bf30`
- `0x18003c6a0`
- `0x180164280`

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
0x18003bf30  mov     [rsp+arg_10], rbx
0x18003bf35  mov     [rsp+arg_18], rbp
0x18003bf3a  push    rsi
0x18003bf3b  push    rdi
0x18003bf3c  push    r12
0x18003bf3e  push    r13
0x18003bf40  push    r14
0x18003bf42  sub     rsp, 40h
0x18003bf46  mov     rbp, r9
0x18003bf49  mov     rsi, r8
0x18003bf4c  mov     rdi, rdx
0x18003bf4f  mov     rbx, rcx
0x18003bf52  test    rcx, rcx
0x18003bf55  jnz     short loc_18003BFAA
0x18003bf57  test    rdx, rdx
0x18003bf5a  jnz     short loc_18003BFAA
0x18003bf5c  test    r8, r8
0x18003bf5f  jnz     short loc_18003BFAA
0x18003bf61  test    r9, r9
0x18003bf64  jnz     short loc_18003BFAA
0x18003bf66  mov     r13, [rsp+68h+arg_20]
0x18003bf6e  mov     r12, [rsp+68h+arg_28]
0x18003bf76  test    r13, r13
0x18003bf79  jnz     short loc_18003BFBA
0x18003bf7b  test    r12, r12
0x18003bf7e  jnz     short loc_18003BFBA
0x18003bf80  mov     rax, [rsp+68h+arg_30]
0x18003bf88  xor     r14d, r14d
0x18003bf8b  mov     [rax], r14
0x18003bf8e  xor     eax, eax
0x18003bf90  lea     r11, [rsp+68h+var_28]
0x18003bf95  mov     rbx, [r11+40h]
0x18003bf99  mov     rbp, [r11+48h]
0x18003bf9d  mov     rsp, r11
0x18003bfa0  pop     r14
0x18003bfa2  pop     r13
0x18003bfa4  pop     r12
0x18003bfa6  pop     rdi
0x18003bfa7  pop     rsi
0x18003bfa8  retn
0x18003bfaa  mov     r12, [rsp+68h+arg_28]
0x18003bfb2  mov     r13, [rsp+68h+arg_20]
0x18003bfba  mov     r10, [rsp+68h+arg_38]
0x18003bfc2  xor     r14d, r14d
0x18003bfc5  mov     [rsp+68h+arg_8], r15
0x18003bfca  mov     r11d, 2
0x18003bfd0  mov     [rsp+68h+var_40], r14
0x18003bfd5  mov     edx, 8
0x18003bfda  mov     [rsp+68h+arg_0], r11d
0x18003bfdf  lea     r15, cs:180000000h
0x18003bfe6  test    rbx, rbx
0x18003bfe9  jnz     loc_18003C482
0x18003bfef  test    rdi, rdi
0x18003bff2  jz      short loc_18003C03D
0x18003bff4  mov     r9d, r14d
0x18003bff7  lea     rcx, [rdi+8]
0x18003bffb  movzx   eax, word ptr [rdi+4]
0x18003bfff  cmp     r9d, eax
0x18003c002  jnb     short loc_18003C03D
0x18003c004  cmp     byte ptr [rcx], 11h
0x18003c007  jnz     short loc_18003C031
0x18003c009  movzx   r8d, word ptr [rcx+2]
0x18003c00e  add     r8d, edx
0x18003c011  cmp     r8d, edx
0x18003c014  jb      short loc_18003C068
0x18003c016  mov     edx, r8d
0x18003c019  test    r10, r10
0x18003c01c  jz      short loc_18003C022
0x18003c01e  or      dword ptr [r10], 10h
0x18003c022  movzx   eax, byte ptr [rdi]
0x18003c025  cmp     eax, r11d
0x18003c028  jbe     short loc_18003C031
0x18003c02a  mov     r11d, eax
0x18003c02d  mov     [rsp+68h+arg_0], eax
0x18003c031  movzx   eax, word ptr [rcx+2]
0x18003c035  inc     r9d
0x18003c038  add     rcx, rax
0x18003c03b  jmp     short loc_18003BFFB
0x18003c03d  test    r13, r13
0x18003c040  jnz     loc_18003C4CE
0x18003c046  test    r12, r12
0x18003c049  jnz     loc_18003C456
0x18003c04f  test    rsi, rsi
0x18003c052  jnz     loc_18003C404
0x18003c058  test    rbp, rbp
0x18003c05b  jnz     loc_18003C42D
0x18003c061  lea     eax, [rdx+3]
0x18003c064  cmp     eax, edx
0x18003c066  jnb     short loc_18003C08B
0x18003c068  mov     r15d, 0C0000095h
0x18003c06e  mov     rax, [rsp+68h+arg_30]
0x18003c076  mov     rdx, [rsp+68h+var_40]
0x18003c07b  mov     [rax], rdx
0x18003c07e  mov     eax, r15d
0x18003c081  mov     r15, [rsp+68h+arg_8]
0x18003c086  jmp     loc_18003BF90
0x18003c08b  mov     rcx, gs:60h
0x18003c094  and     eax, 0FFFFFFFCh
0x18003c097  mov     edx, cs:NtdllBaseTag
0x18003c09d  mov     r8d, eax
0x18003c0a0  add     edx, 140000h
0x18003c0a6  mov     r15d, eax
0x18003c0a9  mov     rcx, [rcx+30h]
0x18003c0ad  call    RtlAllocateHeap_0
0x18003c0b2  mov     [rsp+68h+var_40], rax
0x18003c0b7  test    rax, rax
0x18003c0ba  jz      loc_18003C5F9
0x18003c0c0  mov     r8d, [rsp+68h+arg_0]
0x18003c0c5  mov     edx, r15d
0x18003c0c8  mov     rcx, rax
0x18003c0cb  call    RtlCreateAcl
0x18003c0d0  mov     [rsp+68h+arg_0], eax
0x18003c0d4  mov     r15d, eax
0x18003c0d7  test    eax, eax
0x18003c0d9  js      loc_18003C228
0x18003c0df  mov     rax, [rsp+68h+var_40]
0x18003c0e4  mov     ecx, r14d
0x18003c0e7  movzx   r9d, word ptr [rax+2]
0x18003c0ec  lea     rdx, [rax+8]
0x18003c0f0  movzx   r8d, word ptr [rax+4]
0x18003c0f5  add     r9, rax
0x18003c0f8  cmp     ecx, r8d
0x18003c0fb  jnb     short loc_18003C111
0x18003c0fd  cmp     rdx, r9
0x18003c100  jnb     loc_18003C222
0x18003c106  movzx   eax, word ptr [rdx+2]
0x18003c10a  inc     ecx
0x18003c10c  add     rdx, rax
0x18003c10f  jmp     short loc_18003C0F8
0x18003c111  mov     [rsp+68h+var_38], r14
0x18003c116  cmp     rdx, r9
0x18003c119  ja      short loc_18003C120
0x18003c11b  mov     [rsp+68h+var_38], rdx
0x18003c120  test    rbx, rbx
0x18003c123  jnz     loc_18003C373
0x18003c129  test    rdi, rdi
0x18003c12c  jz      short loc_18003C1A7
0x18003c12e  lea     rbx, [rdi+8]
0x18003c132  mov     ecx, r14d
0x18003c135  mov     [rsp+68h+var_48], ecx
0x18003c139  cmp     r14w, [rdi+4]
0x18003c13e  jnb     short loc_18003C1A7
0x18003c140  mov     r12, [rsp+68h+var_40]
0x18003c145  mov     r15, [rsp+68h+var_38]
0x18003c14a  cmp     byte ptr [rbx], 11h
0x18003c14d  lea     rax, [rbx+2]
0x18003c151  mov     [rsp+68h+var_38], rax
0x18003c156  jnz     short loc_18003C181
0x18003c158  movzx   r8d, word ptr [rax]; Size
0x18003c15c  mov     rdx, rbx; Src
0x18003c15f  mov     rcx, r15; void *
0x18003c162  call    memmove
0x18003c167  inc     word ptr [r12+4]
0x18003c16d  mov     rax, [rsp+68h+var_38]
0x18003c172  mov     ecx, [rsp+68h+var_48]
0x18003c176  movzx   eax, word ptr [rax]
0x18003c179  add     r15, rax
0x18003c17c  mov     rax, [rsp+68h+var_38]
0x18003c181  movzx   eax, word ptr [rax]
0x18003c184  inc     ecx
0x18003c186  add     rbx, rax
0x18003c189  mov     [rsp+68h+var_48], ecx
0x18003c18d  movzx   eax, word ptr [rdi+4]
0x18003c191  cmp     ecx, eax
0x18003c193  jb      short loc_18003C14A
0x18003c195  mov     r12, [rsp+68h+arg_28]
0x18003c19d  mov     [rsp+68h+var_38], r15
0x18003c1a2  mov     r15d, [rsp+68h+arg_0]
0x18003c1a7  mov     rbx, [rsp+68h+var_38]
0x18003c1ac  test    r13, r13
0x18003c1af  jnz     loc_18003C303
0x18003c1b5  test    r12, r12
0x18003c1b8  jnz     loc_18003C2A0
0x18003c1be  test    rsi, rsi
0x18003c1c1  jnz     loc_18003C24B
0x18003c1c7  test    rbp, rbp
0x18003c1ca  jz      loc_18003C06E
0x18003c1d0  lea     rdi, [rbp+8]
0x18003c1d4  cmp     r14w, [rbp+4]
0x18003c1d9  jnb     loc_18003C06E
0x18003c1df  mov     r15, [rsp+68h+var_40]
0x18003c1e4  cmp     byte ptr [rdi], 13h
0x18003c1e7  jnz     short loc_18003C205
0x18003c1e9  movzx   r8d, word ptr [rdi+2]; Size
0x18003c1ee  mov     rdx, rdi; Src
0x18003c1f1  mov     rcx, rbx; void *
0x18003c1f4  call    memmove
0x18003c1f9  inc     word ptr [r15+4]
0x18003c1fe  movzx   eax, word ptr [rdi+2]
0x18003c202  add     rbx, rax
0x18003c205  movzx   eax, word ptr [rdi+2]
0x18003c209  inc     r14d
0x18003c20c  add     rdi, rax
0x18003c20f  movzx   eax, word ptr [rbp+4]
0x18003c213  cmp     r14d, eax
0x18003c216  jb      short loc_18003C1E4
0x18003c218  mov     r15d, [rsp+68h+arg_0]
0x18003c21d  jmp     loc_18003C06E
0x18003c222  mov     r15d, 0C000007Dh
0x18003c228  mov     rcx, gs:60h
0x18003c231  xor     edx, edx
0x18003c233  mov     r8, [rsp+68h+var_40]
0x18003c238  mov     rcx, [rcx+30h]
0x18003c23c  call    RtlFreeHeap_0
0x18003c241  mov     [rsp+68h+var_40], r14
0x18003c246  jmp     loc_18003C06E
0x18003c24b  lea     rdi, [rsi+8]
0x18003c24f  mov     r12d, r14d
0x18003c252  cmp     r14w, [rsi+4]
0x18003c257  jnb     loc_18003C1C7
0x18003c25d  mov     r15, [rsp+68h+var_40]
0x18003c262  cmp     byte ptr [rdi], 12h
0x18003c265  jnz     short loc_18003C283
0x18003c267  movzx   r8d, word ptr [rdi+2]; Size
0x18003c26c  mov     rdx, rdi; Src
0x18003c26f  mov     rcx, rbx; void *
0x18003c272  call    memmove
0x18003c277  inc     word ptr [r15+4]
0x18003c27c  movzx   eax, word ptr [rdi+2]
0x18003c280  add     rbx, rax
0x18003c283  movzx   eax, word ptr [rdi+2]
0x18003c287  inc     r12d
0x18003c28a  add     rdi, rax
0x18003c28d  movzx   eax, word ptr [rsi+4]
0x18003c291  cmp     r12d, eax
0x18003c294  jb      short loc_18003C262
0x18003c296  mov     r15d, [rsp+68h+arg_0]
0x18003c29b  jmp     loc_18003C1C7
0x18003c2a0  lea     rdi, [r12+8]
0x18003c2a5  mov     ecx, r14d
0x18003c2a8  mov     [rsp+68h+var_48], ecx
0x18003c2ac  cmp     r14w, [r12+4]
0x18003c2b2  jnb     loc_18003C1BE
0x18003c2b8  mov     r15, [rsp+68h+var_40]
0x18003c2bd  cmp     byte ptr [rdi], 15h
0x18003c2c0  jnz     short loc_18003C2E2
0x18003c2c2  movzx   r8d, word ptr [rdi+2]; Size
0x18003c2c7  mov     rdx, rdi; Src
0x18003c2ca  mov     rcx, rbx; void *
0x18003c2cd  call    memmove
0x18003c2d2  inc     word ptr [r15+4]
0x18003c2d7  movzx   eax, word ptr [rdi+2]
0x18003c2db  mov     ecx, [rsp+68h+var_48]
0x18003c2df  add     rbx, rax
0x18003c2e2  movzx   eax, word ptr [rdi+2]
0x18003c2e6  inc     ecx
0x18003c2e8  add     rdi, rax
0x18003c2eb  mov     [rsp+68h+var_48], ecx
0x18003c2ef  movzx   eax, word ptr [r12+4]
0x18003c2f5  cmp     ecx, eax
0x18003c2f7  jb      short loc_18003C2BD
0x18003c2f9  mov     r15d, [rsp+68h+arg_0]
0x18003c2fe  jmp     loc_18003C1BE
0x18003c303  lea     rdi, [r13+8]
0x18003c307  mov     ecx, r14d
0x18003c30a  mov     [rsp+68h+var_48], ecx
0x18003c30e  cmp     r14w, [r13+4]
0x18003c313  jnb     loc_18003C1B5
0x18003c319  mov     r15, [rsp+68h+var_40]
0x18003c31e  cmp     byte ptr [rdi], 14h
0x18003c321  lea     rax, [rdi+2]
0x18003c325  mov     [rsp+68h+var_38], rax
0x18003c32a  jnz     short loc_18003C354
0x18003c32c  movzx   r8d, word ptr [rax]; Size
0x18003c330  mov     rdx, rdi; Src
0x18003c333  mov     rcx, rbx; void *
0x18003c336  call    memmove
0x18003c33b  inc     word ptr [r15+4]
0x18003c340  mov     rax, [rsp+68h+var_38]
0x18003c345  mov     ecx, [rsp+68h+var_48]
0x18003c349  movzx   eax, word ptr [rax]
0x18003c34c  add     rbx, rax
0x18003c34f  mov     rax, [rsp+68h+var_38]
0x18003c354  movzx   eax, word ptr [rax]
0x18003c357  inc     ecx
0x18003c359  add     rdi, rax
0x18003c35c  mov     [rsp+68h+var_48], ecx
0x18003c360  movzx   eax, word ptr [r13+4]
0x18003c365  cmp     ecx, eax
0x18003c367  jb      short loc_18003C31E
0x18003c369  mov     r15d, [rsp+68h+arg_0]
0x18003c36e  jmp     loc_18003C1B5
0x18003c373  mov     edx, r14d
0x18003c376  mov     [rsp+68h+var_48], edx
0x18003c37a  cmp     r14w, [rbx+4]
0x18003c37f  jnb     loc_18003C129
0x18003c385  mov     r15, [rsp+68h+var_40]
0x18003c38a  lea     r12, [rbx+8]
0x18003c38e  mov     r13, [rsp+68h+var_38]
0x18003c393  lea     r14, cs:180000000h
0x18003c39a  movzx   eax, byte ptr [r12]
0x18003c39f  cmp     eax, 10h
0x18003c3a2  jnz     loc_18003C604
0x18003c3a8  movzx   r8d, word ptr [r12+2]; jumptable 000000018003C61D cases 2,3,7,8,13-15
0x18003c3ae  mov     rdx, r12; Src
0x18003c3b1  mov     rcx, r13; void *
0x18003c3b4  call    memmove
0x18003c3b9  inc     word ptr [r15+4]
0x18003c3be  movzx   eax, word ptr [r12+2]
0x18003c3c4  mov     edx, [rsp+68h+var_48]
  ... truncated ...
```
