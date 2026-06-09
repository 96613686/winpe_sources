# StoreFontInCache

- ea: `0x14007eac4`
- end: `0x14007edfe`
- name: `StoreFontInCache`
- size: `826`
- prototype: `void __fastcall(__int64, ULONG)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140030be0`

## callees

- `0x140076ef6`
- `0x14007eac4`
- `0x140092868`
- `0x1400928c0`
- `0x140092964`

## pseudocode

```c
void __fastcall StoreFontInCache(__int64 a1, ULONG a2)
{
  ULONG v2; // esi
  char *v3; // rdi
  _DWORD *v4; // rax
  __int64 v5; // r15
  int v6; // ebx
  _DWORD *v7; // rcx
  size_t v8; // r13
  unsigned int v9; // edx
  __int64 v10; // r12
  unsigned __int64 v11; // rdx
  _DWORD *v12; // rax
  _QWORD *v13; // rdi
  _QWORD *v14; // rsi
  char *v15; // rbx
  const void *v16; // rdx
  const void *v17; // rdx
  __int64 v18; // rcx
  char *v19; // rbx
  const void *v20; // rdx
  char *v21; // rbx
  unsigned int i; // edx
  __int64 v23; // r8
  char *v24; // rbx
  size_t v25; // r9
  __int64 v26; // rax
  unsigned int v27; // edx
  _DWORD *v28; // [rsp+30h] [rbp-38h]

  v2 = a2;
  v3 = 0;
  v4 = 0;
  v28 = 0;
  v5 = *(_QWORD *)(a1 + 8);
  v6 = 0;
  if ( *(_DWORD *)a1 <= 2u && (*(_DWORD *)a1 != 2 || v5 == *(_QWORD *)(a1 + 16)) )
  {
    v7 = *(_DWORD **)(v5 + 32);
    v8 = (unsigned int)(16 * (v7[3] + 1));
    v9 = v7[2];
    if ( v9 <= (unsigned int)(*v7 - v8) >> 2 )
      v9 = (unsigned int)(*v7 - v8) >> 2;
    v10 = v9;
    v11 = v9 * (*(_QWORD *)(v5 + 40) != 0 ? 4LL : 2LL)
        + v8
        + ((*(unsigned int *)(v5 + 104)
          + (((unsigned __int128)-(__int128)*(unsigned __int64 *)(v5 + 384) >> 64) & 0x46C)
          + 1147)
         & 0xFFFFFFFFFFFFFFFCuLL)
        + 8;
    if ( v11 <= 0xFFFFFFFF )
    {
      v12 = EngFntCacheAlloc(v2, v11);
      v3 = (char *)v12;
      if ( v12 )
      {
        v28 = v12;
        *v12 = 16646405;
        v13 = v12 + 2;
        memmove_0(v12 + 2, (const void *)v5, 0x478u);
        v14 = v13;
        v15 = (char *)(v13 + 143);
        v16 = *(const void **)(v5 + 384);
        if ( v16 )
        {
          memmove_0(v13 + 143, v16, 0x46Cu);
          v15 = (char *)v13 + 2276;
          v13[48] = 1;
        }
        v17 = *(const void **)(v5 + 1120);
        if ( v17 )
        {
          memmove_0(v15, v17, 40LL * *(unsigned int *)(v5 + 1112) + 8);
          v18 = *(unsigned int *)(v5 + 1112);
          v19 = &v15[40 * v18 + 8];
          memmove_0(v19, *(const void **)(v5 + 1128), 4LL * (unsigned int)(2 * v18) + 4);
          v15 = &v19[8 * *(_DWORD *)(v5 + 1112) + 4];
          v13[140] = 1;
        }
        v20 = *(const void **)(v5 + 96);
        if ( v20 )
        {
          memmove_0(v15, v20, *(unsigned int *)(v5 + 104));
          v15 += *(unsigned int *)(v5 + 104);
          v13[12] = 1;
        }
        v21 = (char *)((unsigned __int64)(v15 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
        memmove_0(v21, *(const void **)(v5 + 32), v8);
        v13[4] = 1;
        for ( i = 0; ; ++i )
        {
          v23 = *(_QWORD *)(v5 + 32);
          if ( i >= *(_DWORD *)(v23 + 12) )
            break;
          *(_QWORD *)&v21[16 * i + 24] = v13[4] + *(_QWORD *)(v23 + 16LL * i + 24) - v23;
        }
        v24 = &v21[v8];
        v25 = v23 + v8;
        v26 = *(_QWORD *)(v5 + 40);
        v27 = 0;
        if ( v26 )
        {
          while ( v27 < (unsigned int)v10 )
          {
            *(_DWORD *)&v24[4 * v27] = *(_DWORD *)(v25 + 4LL * v27) + (*(_DWORD *)(v26 + v8 + 4LL * v27) << 16);
            ++v27;
          }
          v3 = &v24[4 * v10];
          v14[5] = 1;
        }
        else
        {
          while ( v27 < (unsigned int)v10 )
          {
            *(_WORD *)&v24[2 * v27] = *(_WORD *)(v25 + 4LL * v27);
            ++v27;
          }
          v3 = &v24[2 * v10];
        }
        v14[3] = 0;
        v14[6] = 0;
        v14[7] = 0;
        v14[8] = 0;
        v14[9] = 0;
        v14[10] = 0;
        v14[11] = 0;
        *v14 = 0;
        v14[1] = 0;
        v14[14] = 0;
        v14[17] = 0;
        v14[20] = 0;
        v14[141] = 0;
        v6 = 1;
        v2 = a2;
      }
    }
    v4 = v28;
  }
  if ( v3 )
    EngFntCacheFlush(v4, v6 != 1);
  if ( v6 != 1 )
  {
    if ( v3 )
      EngFntCacheFault(v2, 2u);
  }
}

```

## disassembly

```asm
0x14007eac4  mov     rax, rsp
0x14007eac7  mov     [rax+8], rbx
0x14007eacb  mov     [rax+18h], rsi
0x14007eacf  mov     [rax+10h], edx
0x14007ead2  push    rdi
0x14007ead3  push    r12
0x14007ead5  push    r13
0x14007ead7  push    r14
0x14007ead9  push    r15
0x14007eadb  sub     rsp, 40h
0x14007eadf  mov     esi, edx
0x14007eae1  xor     r10d, r10d
0x14007eae4  mov     edi, r10d
0x14007eae7  mov     [rax-40h], r10
0x14007eaeb  mov     eax, r10d
0x14007eaee  mov     [rsp+68h+var_38], rax
0x14007eaf3  mov     r15, [rcx+8]
0x14007eaf7  mov     ebx, r10d
0x14007eafa  mov     [rsp+68h+var_44], ebx
0x14007eafe  cmp     dword ptr [rcx], 2
0x14007eb01  ja      loc_14007EDAB
0x14007eb07  jnz     short loc_14007EB13
0x14007eb09  cmp     r15, [rcx+10h]
0x14007eb0d  jnz     loc_14007EDAB
0x14007eb13  mov     rcx, [r15+20h]
0x14007eb17  mov     r13d, [rcx+0Ch]
0x14007eb1b  mov     r14d, 1
0x14007eb21  add     r13d, r14d
0x14007eb24  shl     r13d, 4
0x14007eb28  mov     edx, [rcx+8]
0x14007eb2b  mov     eax, [rcx]
0x14007eb2d  sub     eax, r13d
0x14007eb30  shr     eax, 2
0x14007eb33  cmp     edx, eax
0x14007eb35  cmovbe  edx, eax
0x14007eb38  mov     r12d, edx
0x14007eb3b  mov     rax, [r15+180h]
0x14007eb42  neg     rax
0x14007eb45  sbb     rdx, rdx
0x14007eb48  and     edx, 46Ch
0x14007eb4e  add     rdx, 47Bh
0x14007eb55  mov     eax, [r15+68h]
0x14007eb59  add     rdx, rax
0x14007eb5c  and     rdx, 0FFFFFFFFFFFFFFFCh
0x14007eb60  mov     rax, [r15+28h]
0x14007eb64  neg     rax
0x14007eb67  sbb     rcx, rcx
0x14007eb6a  and     ecx, 2
0x14007eb6d  add     rcx, 2
0x14007eb71  imul    rcx, r12
0x14007eb75  add     rdx, 8
0x14007eb79  add     rdx, r13
0x14007eb7c  add     rdx, rcx; ulSize
0x14007eb7f  mov     eax, 0FFFFFFFFh
0x14007eb84  cmp     rdx, rax
0x14007eb87  ja      loc_14007EDB3
0x14007eb8d  mov     ecx, esi; FastCheckSum
0x14007eb8f  call    EngFntCacheAlloc
0x14007eb94  mov     rdi, rax
0x14007eb97  mov     [rsp+68h+var_40], rax
0x14007eb9c  xor     r10d, r10d
0x14007eb9f  test    rax, rax
0x14007eba2  jz      loc_14007EDB3
0x14007eba8  mov     [rsp+68h+var_38], rax
0x14007ebad  mov     dword ptr [rax], 0FE0105h
0x14007ebb3  add     rdi, 8
0x14007ebb7  mov     [rsp+68h+var_40], rdi
0x14007ebbc  mov     r8d, 478h; Size
0x14007ebc2  mov     rdx, r15; Src
0x14007ebc5  mov     rcx, rdi; void *
0x14007ebc8  call    memmove_0
0x14007ebcd  mov     rsi, rdi
0x14007ebd0  lea     rbx, [rdi+478h]
0x14007ebd7  mov     [rsp+68h+var_40], rbx
0x14007ebdc  mov     rdx, [r15+180h]; Src
0x14007ebe3  test    rdx, rdx
0x14007ebe6  jz      short loc_14007EC09
0x14007ebe8  mov     r8d, 46Ch; Size
0x14007ebee  mov     rcx, rbx; void *
0x14007ebf1  call    memmove_0
0x14007ebf6  add     rbx, 46Ch
0x14007ebfd  mov     [rsp+68h+var_40], rbx
0x14007ec02  mov     [rdi+180h], r14
0x14007ec09  mov     rdx, [r15+460h]; Src
0x14007ec10  test    rdx, rdx
0x14007ec13  jz      short loc_14007EC7F
0x14007ec15  mov     eax, [r15+458h]
0x14007ec1c  lea     r8, [rax+rax*4]
0x14007ec20  lea     r8, ds:8[r8*8]; Size
0x14007ec28  mov     rcx, rbx; void *
0x14007ec2b  call    memmove_0
0x14007ec30  mov     ecx, [r15+458h]
0x14007ec37  lea     rax, [rcx+rcx*4]
0x14007ec3b  lea     rbx, [rbx+rax*8]
0x14007ec3f  add     rbx, 8
0x14007ec43  mov     [rsp+68h+var_40], rbx
0x14007ec48  lea     eax, [rcx+rcx]
0x14007ec4b  lea     r8, ds:4[rax*4]; Size
0x14007ec53  mov     rdx, [r15+468h]; Src
0x14007ec5a  mov     rcx, rbx; void *
0x14007ec5d  call    memmove_0
0x14007ec62  mov     eax, [r15+458h]
0x14007ec69  add     eax, eax
0x14007ec6b  lea     rbx, [rbx+rax*4]
0x14007ec6f  add     rbx, 4
0x14007ec73  mov     [rsp+68h+var_40], rbx
0x14007ec78  mov     [rdi+460h], r14
0x14007ec7f  mov     rdx, [r15+60h]; Src
0x14007ec83  test    rdx, rdx
0x14007ec86  jz      short loc_14007ECA4
0x14007ec88  mov     r8d, [r15+68h]; Size
0x14007ec8c  mov     rcx, rbx; void *
0x14007ec8f  call    memmove_0
0x14007ec94  mov     eax, [r15+68h]
0x14007ec98  add     rbx, rax
0x14007ec9b  mov     [rsp+68h+var_40], rbx
0x14007eca0  mov     [rdi+60h], r14
0x14007eca4  add     rbx, 3
0x14007eca8  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14007ecac  mov     [rsp+68h+var_40], rbx
0x14007ecb1  mov     r8, r13; Size
0x14007ecb4  mov     rdx, [r15+20h]; Src
0x14007ecb8  mov     rcx, rbx; void *
0x14007ecbb  call    memmove_0
0x14007ecc0  mov     [rdi+20h], r14
0x14007ecc4  xor     r10d, r10d
0x14007ecc7  mov     edx, r10d
0x14007ecca  mov     [rsp+68h+var_48], edx
0x14007ecce  mov     r8, [r15+20h]
0x14007ecd2  cmp     edx, [r8+0Ch]
0x14007ecd6  jnb     short loc_14007ECF3
0x14007ecd8  mov     ecx, edx
0x14007ecda  add     rcx, rcx
0x14007ecdd  mov     rax, [r8+rcx*8+18h]
0x14007ece2  sub     rax, r8
0x14007ece5  add     rax, [rdi+20h]
0x14007ece9  mov     [rbx+rcx*8+18h], rax
0x14007ecee  add     edx, r14d
0x14007ecf1  jmp     short loc_14007ECCA
0x14007ecf3  add     rbx, r13
0x14007ecf6  mov     [rsp+68h+var_40], rbx
0x14007ecfb  lea     r9, [r8+r13]
0x14007ecff  mov     rax, [r15+28h]
0x14007ed03  mov     edx, r10d
0x14007ed06  mov     [rsp+68h+var_48], edx
0x14007ed0a  test    rax, rax
0x14007ed0d  jz      short loc_14007ED40
0x14007ed0f  lea     r8, [rax+r13]
0x14007ed13  cmp     edx, r12d
0x14007ed16  jnb     short loc_14007ED31
0x14007ed18  mov     ecx, edx
0x14007ed1a  mov     eax, [r8+rcx*4]
0x14007ed1e  shl     eax, 10h
0x14007ed21  add     eax, [r9+rcx*4]
0x14007ed25  mov     [rbx+rcx*4], eax
0x14007ed28  add     edx, r14d
0x14007ed2b  mov     [rsp+68h+var_48], edx
0x14007ed2f  jmp     short loc_14007ED13
0x14007ed31  lea     rdi, [rbx+r12*4]
0x14007ed35  mov     [rsp+68h+var_40], rdi
0x14007ed3a  mov     [rsi+28h], r14
0x14007ed3e  jmp     short loc_14007ED62
0x14007ed40  cmp     edx, r12d
0x14007ed43  jnb     short loc_14007ED59
0x14007ed45  mov     ecx, edx
0x14007ed47  movzx   eax, word ptr [r9+rcx*4]
0x14007ed4c  mov     [rbx+rcx*2], ax
0x14007ed50  add     edx, r14d
0x14007ed53  mov     [rsp+68h+var_48], edx
0x14007ed57  jmp     short loc_14007ED40
0x14007ed59  lea     rdi, [rbx+r12*2]
0x14007ed5d  mov     [rsp+68h+var_40], rdi
0x14007ed62  mov     [rsi+18h], r10
0x14007ed66  mov     [rsi+30h], r10
0x14007ed6a  mov     [rsi+38h], r10
0x14007ed6e  mov     [rsi+40h], r10
0x14007ed72  mov     [rsi+48h], r10
0x14007ed76  mov     [rsi+50h], r10
0x14007ed7a  mov     [rsi+58h], r10
0x14007ed7e  mov     [rsi], r10
0x14007ed81  mov     [rsi+8], r10
0x14007ed85  mov     [rsi+70h], r10
0x14007ed89  mov     [rsi+88h], r10
0x14007ed90  mov     [rsi+0A0h], r10
0x14007ed97  mov     [rsi+468h], r10
0x14007ed9e  mov     ebx, r14d
0x14007eda1  mov     [rsp+68h+var_44], ebx
0x14007eda5  mov     esi, [rsp+68h+arg_8]
0x14007eda9  jmp     short loc_14007EDB3
0x14007edab  mov     r14d, 1
0x14007edb1  jmp     short loc_14007EDB8
0x14007edb3  mov     rax, [rsp+68h+var_38]
0x14007edb8  test    rdi, rdi
0x14007edbb  jz      short loc_14007EDCE
0x14007edbd  mov     edx, r10d
0x14007edc0  cmp     ebx, r14d
0x14007edc3  setnz   dl
0x14007edc6  mov     rcx, rax
0x14007edc9  call    EngFntCacheFlush
0x14007edce  cmp     ebx, r14d
0x14007edd1  jz      short loc_14007EDE4
0x14007edd3  test    rdi, rdi
0x14007edd6  jz      short loc_14007EDE4
0x14007edd8  mov     edx, 2; iFaultMode
0x14007eddd  mov     ecx, esi; ulFastCheckSum
0x14007eddf  call    EngFntCacheFault
0x14007ede4  lea     r11, [rsp+68h+var_28]
0x14007ede9  mov     rbx, [r11+30h]
0x14007eded  mov     rsi, [r11+40h]
0x14007edf1  mov     rsp, r11
0x14007edf4  pop     r15
0x14007edf6  pop     r14
0x14007edf8  pop     r13
0x14007edfa  pop     r12
0x14007edfc  pop     rdi
0x14007edfd  retn
0x140097886  push    rbx
0x140097888  push    rbp
0x140097889  sub     rsp, 28h
0x14009788d  mov     rbp, rdx
0x140097890  mov     rbx, [rbp+28h]
0x140097894  test    rbx, rbx
0x140097897  jz      short loc_1400978AC
0x140097899  xor     edx, edx
0x14009789b  cmp     dword ptr [rbp+24h], 1
0x14009789f  setnz   dl
0x1400978a2  mov     rcx, [rbp+30h]
0x1400978a6  call    EngFntCacheFlush
0x1400978ab  nop
0x1400978ac  cmp     dword ptr [rbp+24h], 1
0x1400978b0  jz      short loc_1400978C5
0x1400978b2  test    rbx, rbx
0x1400978b5  jz      short loc_1400978C5
0x1400978b7  mov     edx, 2; iFaultMode
0x1400978bc  mov     ecx, [rbp+78h]; ulFastCheckSum
0x1400978bf  call    EngFntCacheFault
0x1400978c4  nop
0x1400978c5  add     rsp, 28h
0x1400978c9  pop     rbp
0x1400978ca  pop     rbx
0x1400978cb  retn
```
