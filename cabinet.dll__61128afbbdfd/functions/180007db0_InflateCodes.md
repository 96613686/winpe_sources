# InflateCodes

- ea: `0x180007db0`
- end: `0x18000825e`
- name: `InflateCodes`
- size: `1198`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800058e4`
- `0x180006c2c`
- `0x180007260`

## callees

- `0x180007db0`

## pseudocode

```c
__int64 __fastcall InflateCodes(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, int a6)
{
  __int64 v7; // rbx
  int v10; // esi
  unsigned int v11; // r11d
  unsigned int v12; // r8d
  unsigned int v13; // r13d
  unsigned __int8 *v14; // r9
  __int64 v15; // r10
  int v16; // ecx
  bool v17; // zf
  unsigned int v18; // ebx
  __int64 v19; // r9
  unsigned __int8 v20; // r10
  int v21; // edx
  _BYTE *v22; // r10
  int v23; // r9d
  unsigned int v25; // edi
  __int64 v26; // rbx
  unsigned __int8 v27; // dl
  int v28; // edx
  int v29; // r14d
  unsigned int v30; // ebp
  unsigned int v31; // r11d
  unsigned int v32; // r8d
  unsigned int v33; // ebx
  __int64 v34; // r9
  unsigned __int8 v35; // r10
  int v36; // edx
  unsigned __int8 *v37; // rsi
  __int64 v38; // rdi
  int v39; // ecx
  unsigned int v40; // r11d
  unsigned int v41; // r8d
  unsigned int v42; // ebx
  __int64 v43; // r9
  unsigned __int8 v44; // r10
  int v45; // edx
  int v46; // ecx
  __int64 v47; // rdx
  unsigned int v48; // r10d
  int v49; // ecx
  __int64 v50; // r10
  unsigned int v51; // edi
  __int64 v52; // rbx
  unsigned __int8 v53; // dl
  int v54; // edx
  int v55; // ecx
  __int64 v56; // rdi
  unsigned int v57; // r10d
  __int64 v58; // r9
  unsigned __int8 v59; // dl
  int v60; // edx
  __int16 v62; // [rsp+68h] [rbp+20h]

  v7 = a3;
  if ( a4 <= 0 || !*(_DWORD *)(a1 + 40) )
    return 1;
  _mm_lfence();
  v10 = a5;
  v11 = *(_DWORD *)(a1 + 48);
  v12 = *(_DWORD *)(a1 + 52);
  v13 = (unsigned __int16)word_18001D8B0[a4];
  v62 = word_18001D8B0[a5];
  if ( !a6 || !*(_DWORD *)(a1 + 96) )
  {
    while ( 1 )
    {
LABEL_4:
      if ( v12 < a4 )
      {
        v18 = *(_DWORD *)(a1 + 32);
        do
        {
          v19 = *(unsigned int *)(a1 + 36);
          if ( (unsigned int)v19 >= v18 )
          {
            if ( (_DWORD)v19 != v18 )
              *(_DWORD *)(a1 + 4) = 1;
            v20 = 0;
          }
          else
          {
            v20 = *(_BYTE *)(v19 + *(_QWORD *)(a1 + 8));
            *(_DWORD *)(a1 + 36) = v19 + 1;
          }
          v21 = v20 << v12;
          v12 += 8;
          v11 |= v21;
        }
        while ( v12 < a4 );
        v7 = a3;
      }
      if ( *(_DWORD *)(a1 + 4) )
        return 1;
      v14 = (unsigned __int8 *)(a2 + 16LL * (v11 & v13));
      v15 = *v14;
      if ( (unsigned int)v15 > 0x10 )
      {
        while ( (_DWORD)v15 != 99 )
        {
          v49 = v14[1];
          v50 = (unsigned int)(v15 - 16);
          v11 >>= v49;
          v12 -= v49;
          if ( v12 < (unsigned int)v50 )
          {
            v51 = *(_DWORD *)(a1 + 32);
            do
            {
              v52 = *(unsigned int *)(a1 + 36);
              if ( (unsigned int)v52 >= v51 )
              {
                if ( (_DWORD)v52 != v51 )
                  *(_DWORD *)(a1 + 4) = 1;
                v53 = 0;
              }
              else
              {
                v53 = *(_BYTE *)(v52 + *(_QWORD *)(a1 + 8));
                *(_DWORD *)(a1 + 36) = v52 + 1;
              }
              v54 = v53 << v12;
              v12 += 8;
              v11 |= v54;
            }
            while ( v12 < (unsigned int)v50 );
          }
          if ( *(_DWORD *)(a1 + 4) )
            break;
          v14 = (unsigned __int8 *)(16LL * (v11 & (unsigned __int16)word_18001D8B0[v50]) + *((_QWORD *)v14 + 1));
          v15 = *v14;
          if ( (unsigned int)v15 <= 0x10 )
          {
            v7 = a3;
            goto LABEL_7;
          }
        }
        return 1;
      }
LABEL_7:
      v16 = v14[1];
      v11 >>= v16;
      v12 -= v16;
      if ( (_DWORD)v15 != 16 )
      {
        if ( (_DWORD)v15 == 15 )
          goto LABEL_25;
        if ( v12 < (unsigned int)v15 )
        {
          v25 = *(_DWORD *)(a1 + 32);
          do
          {
            v26 = *(unsigned int *)(a1 + 36);
            if ( (unsigned int)v26 >= v25 )
            {
              if ( (_DWORD)v26 != v25 )
                *(_DWORD *)(a1 + 4) = 1;
              v27 = 0;
            }
            else
            {
              v27 = *(_BYTE *)(v26 + *(_QWORD *)(a1 + 8));
              *(_DWORD *)(a1 + 36) = v26 + 1;
            }
            v28 = v27 << v12;
            v12 += 8;
            v11 |= v28;
          }
          while ( v12 < (unsigned int)v15 );
        }
        if ( !*(_DWORD *)(a1 + 4) && v10 > 0 )
        {
          v29 = *((unsigned __int16 *)v14 + 4);
          v30 = v11 & (unsigned __int16)word_18001D8B0[v15];
          v31 = v11 >> v15;
          v32 = v12 - v15;
          if ( v32 < v10 )
          {
            v33 = *(_DWORD *)(a1 + 32);
            do
            {
              v34 = *(unsigned int *)(a1 + 36);
              if ( (unsigned int)v34 >= v33 )
              {
                if ( (_DWORD)v34 != v33 )
                  *(_DWORD *)(a1 + 4) = 1;
                v35 = 0;
              }
              else
              {
                v35 = *(_BYTE *)(v34 + *(_QWORD *)(a1 + 8));
                *(_DWORD *)(a1 + 36) = v34 + 1;
              }
              v36 = v35 << v32;
              v32 += 8;
              v31 |= v36;
            }
            while ( v32 < v10 );
          }
          if ( !*(_DWORD *)(a1 + 4) )
          {
            v7 = a3;
            v37 = (unsigned __int8 *)(a3 + 16LL * (v31 & (unsigned __int16)v62));
            v38 = *v37;
            if ( (unsigned int)v38 > 0x10 )
            {
              while ( (_DWORD)v38 != 99 )
              {
                v55 = v37[1];
                v56 = (unsigned int)(v38 - 16);
                v31 >>= v55;
                v32 -= v55;
                if ( v32 < (unsigned int)v56 )
                {
                  v57 = *(_DWORD *)(a1 + 32);
                  do
                  {
                    v58 = *(unsigned int *)(a1 + 36);
                    if ( (unsigned int)v58 >= v57 )
                    {
                      if ( (_DWORD)v58 != v57 )
                        *(_DWORD *)(a1 + 4) = 1;
                      v59 = 0;
                    }
                    else
                    {
                      v59 = *(_BYTE *)(v58 + *(_QWORD *)(a1 + 8));
                      *(_DWORD *)(a1 + 36) = v58 + 1;
                    }
                    v60 = v59 << v32;
                    v32 += 8;
                    v31 |= v60;
                  }
                  while ( v32 < (unsigned int)v56 );
                }
                if ( *(_DWORD *)(a1 + 4) || (unsigned int)v56 >= 0x11 )
                  break;
                _mm_lfence();
                v37 = (unsigned __int8 *)(16LL * (v31 & (unsigned __int16)word_18001D8B0[v56]) + *((_QWORD *)v37 + 1));
                v38 = *v37;
                if ( (unsigned int)v38 <= 0x10 )
                  goto LABEL_41;
              }
            }
            else
            {
LABEL_41:
              v39 = v37[1];
              v40 = v31 >> v39;
              v41 = v32 - v39;
              if ( v41 < (unsigned int)v38 )
              {
                v42 = *(_DWORD *)(a1 + 32);
                do
                {
                  v43 = *(unsigned int *)(a1 + 36);
                  if ( (unsigned int)v43 >= v42 )
                  {
                    if ( (_DWORD)v43 != v42 )
                      *(_DWORD *)(a1 + 4) = 1;
                    v44 = 0;
                  }
                  else
                  {
                    v44 = *(_BYTE *)(v43 + *(_QWORD *)(a1 + 8));
                    *(_DWORD *)(a1 + 36) = v43 + 1;
                  }
                  v45 = v44 << v41;
                  v41 += 8;
                  v40 |= v45;
                }
                while ( v41 < (unsigned int)v38 );
                v7 = a3;
              }
              if ( !*(_DWORD *)(a1 + 4) )
              {
                v23 = v29 + v30;
                _mm_lfence();
                v46 = *((unsigned __int16 *)v37 + 4);
                v12 = v41 - v38;
                v47 = *(_QWORD *)(a1 + 16);
                v10 = a5;
                v48 = v46 + (v40 & (unsigned __int16)word_18001D8B0[v38]);
                v11 = v40 >> v38;
                if ( v48 > (int)v47 - *(_DWORD *)(a1 + 24) )
                  v22 = (_BYTE *)(v47 + 0x8000 - v48);
                else
                  v22 = (_BYTE *)(v47 - v48);
                goto LABEL_19;
              }
            }
          }
        }
        return 1;
      }
      if ( *(_DWORD *)(a1 + 40) )
        *(_BYTE *)(*(_QWORD *)(a1 + 16))++ = v14[8];
      v17 = (*(_DWORD *)(a1 + 40))-- == 1;
      if ( v17 )
      {
        *(_DWORD *)(a1 + 96) = 0;
        goto LABEL_24;
      }
    }
  }
  v22 = *(_BYTE **)(a1 + 104);
  v23 = *(_DWORD *)(a1 + 112);
  do
  {
LABEL_19:
    if ( !v23 )
      goto LABEL_4;
    --v23;
    *(_BYTE *)(*(_QWORD *)(a1 + 16))++ = *v22;
    if ( ++v22 == (_BYTE *)(*(_QWORD *)(a1 + 24) + 0x8000LL) )
      v22 = *(_BYTE **)(a1 + 24);
    v17 = (*(_DWORD *)(a1 + 40))-- == 1;
  }
  while ( !v17 );
  *(_DWORD *)(a1 + 96) = 1;
  *(_QWORD *)(a1 + 104) = v22;
  *(_DWORD *)(a1 + 112) = v23;
LABEL_24:
  *(_DWORD *)(a1 + 92) = v10;
  *(_DWORD *)(a1 + 88) = a4;
  *(_QWORD *)(a1 + 80) = v7;
  *(_QWORD *)(a1 + 72) = a2;
  *(_DWORD *)(a1 + 56) = 2;
LABEL_25:
  *(_DWORD *)(a1 + 48) = v11;
  *(_DWORD *)(a1 + 52) = v12;
  return 0;
}

```

## disassembly

```asm
0x180007db0  mov     [rsp+arg_0], rbx
0x180007db5  mov     [rsp+arg_10], r8
0x180007dba  push    rbp
0x180007dbb  push    rsi
0x180007dbc  push    rdi
0x180007dbd  push    r12
0x180007dbf  push    r13
0x180007dc1  push    r14
0x180007dc3  push    r15
0x180007dc5  sub     rsp, 10h
0x180007dc9  movsxd  r15, r9d
0x180007dcc  mov     rbx, r8
0x180007dcf  mov     r12, rdx
0x180007dd2  mov     rax, rcx
0x180007dd5  test    r9d, r9d
0x180007dd8  jle     loc_1800081C0
0x180007dde  cmp     dword ptr [rcx+28h], 0
0x180007de2  jbe     loc_1800081C0
0x180007de8  lfence
0x180007deb  cmp     [rsp+48h+arg_28], 0
0x180007df0  lea     rdi, word_18001D8B0
0x180007df7  movsxd  rsi, [rsp+48h+arg_20]
0x180007dfc  mov     r11d, [rcx+30h]
0x180007e00  mov     r8d, [rcx+34h]
0x180007e04  movzx   r13d, word ptr [rdi+r15*2]
0x180007e09  movzx   ecx, word ptr [rdi+rsi*2]
0x180007e0d  mov     [rsp+48h+arg_18], cx
0x180007e12  jnz     loc_180007EC0
0x180007e18  cmp     r8d, r15d
0x180007e1b  jb      short loc_180007E81
0x180007e1d  cmp     dword ptr [rax+4], 0
0x180007e21  jnz     loc_1800081C0
0x180007e27  mov     r9, r13
0x180007e2a  mov     ecx, r11d
0x180007e2d  and     r9, rcx
0x180007e30  shl     r9, 4
0x180007e34  add     r9, r12
0x180007e37  movzx   r10d, byte ptr [r9]
0x180007e3b  cmp     r10d, 10h
0x180007e3f  ja      loc_180008130
0x180007e45  movzx   ecx, byte ptr [r9+1]
0x180007e4a  shr     r11d, cl
0x180007e4d  sub     r8d, ecx
0x180007e50  cmp     r10d, 10h
0x180007e54  jnz     loc_180007F4B
0x180007e5a  cmp     dword ptr [rax+28h], 0
0x180007e5e  jbe     short loc_180007E6F
0x180007e60  mov     rdx, [rax+10h]
0x180007e64  movzx   ecx, byte ptr [r9+8]
0x180007e69  mov     [rdx], cl
0x180007e6b  inc     qword ptr [rax+10h]
0x180007e6f  add     dword ptr [rax+28h], 0FFFFFFFFh
0x180007e73  jnz     short loc_180007E18
0x180007e75  mov     dword ptr [rax+60h], 0
0x180007e7c  jmp     loc_180007F16
0x180007e81  mov     ebx, [rax+20h]
0x180007e84  mov     r9d, [rax+24h]
0x180007e88  cmp     r9d, ebx
0x180007e8b  jnb     loc_1800080D7
0x180007e91  mov     rcx, [rax+8]
0x180007e95  movzx   r10d, byte ptr [r9+rcx]
0x180007e9a  lea     ecx, [r9+1]
0x180007e9e  mov     [rax+24h], ecx
0x180007ea1  mov     ecx, r8d
0x180007ea4  movzx   edx, r10b
0x180007ea8  shl     edx, cl
0x180007eaa  add     r8d, 8
0x180007eae  or      r11d, edx
0x180007eb1  cmp     r8d, r15d
0x180007eb4  jb      short loc_180007E84
0x180007eb6  mov     rbx, [rsp+48h+arg_10]
0x180007ebb  jmp     loc_180007E1D
0x180007ec0  cmp     dword ptr [rax+60h], 0
0x180007ec4  jz      loc_180007E18
0x180007eca  mov     r10, [rax+68h]
0x180007ece  mov     r9d, [rax+70h]
0x180007ed2  test    r9d, r9d
0x180007ed5  jz      loc_180007E18
0x180007edb  movzx   ecx, byte ptr [r10]
0x180007edf  dec     r9d
0x180007ee2  mov     rdx, [rax+10h]
0x180007ee6  mov     [rdx], cl
0x180007ee8  inc     qword ptr [rax+10h]
0x180007eec  mov     rdx, [rax+18h]
0x180007ef0  inc     r10
0x180007ef3  lea     rcx, [rdx+8000h]
0x180007efa  cmp     r10, rcx
0x180007efd  cmovz   r10, rdx
0x180007f01  sub     dword ptr [rax+28h], 1
0x180007f05  jnz     short loc_180007ED2
0x180007f07  mov     dword ptr [rax+60h], 1
0x180007f0e  mov     [rax+68h], r10
0x180007f12  mov     [rax+70h], r9d
0x180007f16  mov     [rax+5Ch], esi
0x180007f19  mov     [rax+58h], r15d
0x180007f1d  mov     [rax+50h], rbx
0x180007f21  mov     [rax+48h], r12
0x180007f25  mov     dword ptr [rax+38h], 2
0x180007f2c  mov     [rax+30h], r11d
0x180007f30  mov     [rax+34h], r8d
0x180007f34  xor     eax, eax
0x180007f36  mov     rbx, [rsp+48h+arg_0]
0x180007f3b  add     rsp, 10h
0x180007f3f  pop     r15
0x180007f41  pop     r14
0x180007f43  pop     r13
0x180007f45  pop     r12
0x180007f47  pop     rdi
0x180007f48  pop     rsi
0x180007f49  pop     rbp
0x180007f4a  retn
0x180007f4b  cmp     r10d, 0Fh
0x180007f4f  jz      short loc_180007F2C
0x180007f51  cmp     r8d, r10d
0x180007f54  jnb     short loc_180007F94
0x180007f56  mov     edi, [rax+20h]
0x180007f59  nop     dword ptr [rax+00000000h]
0x180007f60  mov     ebx, [rax+24h]
0x180007f63  cmp     ebx, edi
0x180007f65  jnb     loc_1800080E8
0x180007f6b  mov     rcx, [rax+8]
0x180007f6f  movzx   edx, byte ptr [rbx+rcx]
0x180007f73  lea     ecx, [rbx+1]
0x180007f76  mov     [rax+24h], ecx
0x180007f79  mov     ecx, r8d
0x180007f7c  movzx   edx, dl
0x180007f7f  shl     edx, cl
0x180007f81  add     r8d, 8
0x180007f85  or      r11d, edx
0x180007f88  cmp     r8d, r10d
0x180007f8b  jb      short loc_180007F60
0x180007f8d  lea     rdi, word_18001D8B0
0x180007f94  cmp     dword ptr [rax+4], 0
0x180007f98  jnz     loc_1800081C0
0x180007f9e  test    esi, esi
0x180007fa0  jle     loc_1800081C0
0x180007fa6  movzx   ebp, word ptr [rdi+r10*2]
0x180007fab  mov     ecx, r10d
0x180007fae  movzx   r14d, word ptr [r9+8]
0x180007fb3  and     ebp, r11d
0x180007fb6  shr     r11d, cl
0x180007fb9  sub     r8d, r10d
0x180007fbc  cmp     r8d, esi
0x180007fbf  jnb     short loc_180008002
0x180007fc1  mov     ebx, [rax+20h]
0x180007fc4  nop     dword ptr [rax+00h]
0x180007fc8  nop     dword ptr [rax+rax+00000000h]
0x180007fd0  mov     r9d, [rax+24h]
0x180007fd4  cmp     r9d, ebx
0x180007fd7  jnb     loc_1800080F8
0x180007fdd  mov     rcx, [rax+8]
0x180007fe1  movzx   r10d, byte ptr [r9+rcx]
0x180007fe6  lea     ecx, [r9+1]
0x180007fea  mov     [rax+24h], ecx
0x180007fed  mov     ecx, r8d
0x180007ff0  movzx   edx, r10b
0x180007ff4  shl     edx, cl
0x180007ff6  add     r8d, 8
0x180007ffa  or      r11d, edx
0x180007ffd  cmp     r8d, esi
0x180008000  jb      short loc_180007FD0
0x180008002  cmp     dword ptr [rax+4], 0
0x180008006  jnz     loc_1800081C0
0x18000800c  movzx   esi, [rsp+48h+arg_18]
0x180008011  mov     rbx, [rsp+48h+arg_10]
0x180008016  mov     ecx, r11d
0x180008019  and     rsi, rcx
0x18000801c  shl     rsi, 4
0x180008020  add     rsi, rbx
0x180008023  movzx   edi, byte ptr [rsi]
0x180008026  cmp     edi, 10h
0x180008029  ja      loc_1800081D0
0x18000802f  movzx   ecx, byte ptr [rsi+1]
0x180008033  shr     r11d, cl
0x180008036  sub     r8d, ecx
0x180008039  cmp     r8d, edi
0x18000803c  jnb     short loc_180008078
0x18000803e  mov     ebx, [rax+20h]
0x180008041  mov     r9d, [rax+24h]
0x180008045  cmp     r9d, ebx
0x180008048  jnb     loc_180008109
0x18000804e  mov     rcx, [rax+8]
0x180008052  movzx   r10d, byte ptr [r9+rcx]
0x180008057  lea     ecx, [r9+1]
0x18000805b  mov     [rax+24h], ecx
0x18000805e  mov     ecx, r8d
0x180008061  movzx   edx, r10b
0x180008065  shl     edx, cl
0x180008067  add     r8d, 8
0x18000806b  or      r11d, edx
0x18000806e  cmp     r8d, edi
0x180008071  jb      short loc_180008041
0x180008073  mov     rbx, [rsp+48h+arg_10]
0x180008078  cmp     dword ptr [rax+4], 0
0x18000807c  jnz     loc_1800081C0
0x180008082  cmp     edi, 11h
0x180008085  jnb     loc_1800081C0
0x18000808b  lea     r9d, [r14+rbp]
0x18000808f  lfence
0x180008092  movzx   ecx, word ptr [rsi+8]
0x180008096  lea     rdx, word_18001D8B0
0x18000809d  movzx   r10d, word ptr [rdx+rdi*2]
0x1800080a2  sub     r8d, edi
0x1800080a5  mov     rdx, [rax+10h]
0x1800080a9  and     r10d, r11d
0x1800080ac  mov     esi, [rsp+48h+arg_20]
0x1800080b0  add     r10d, ecx
0x1800080b3  mov     ecx, edi
0x1800080b5  lea     rdi, word_18001D8B0
0x1800080bc  shr     r11d, cl
0x1800080bf  mov     ecx, edx
0x1800080c1  sub     ecx, [rax+18h]
0x1800080c4  cmp     r10d, ecx
0x1800080c7  ja      short loc_18000811A
0x1800080c9  mov     ecx, r10d
0x1800080cc  mov     r10, rdx
0x1800080cf  sub     r10, rcx
0x1800080d2  jmp     loc_180007ED2
0x1800080d7  jz      short loc_1800080E0
0x1800080d9  mov     dword ptr [rax+4], 1
0x1800080e0  xor     r10b, r10b
0x1800080e3  jmp     loc_180007EA1
0x1800080e8  jz      short loc_1800080F1
0x1800080ea  mov     dword ptr [rax+4], 1
0x1800080f1  xor     dl, dl
0x1800080f3  jmp     loc_180007F79
0x1800080f8  jz      short loc_180008101
0x1800080fa  mov     dword ptr [rax+4], 1
0x180008101  xor     r10b, r10b
0x180008104  jmp     loc_180007FED
0x180008109  jz      short loc_180008112
0x18000810b  mov     dword ptr [rax+4], 1
0x180008112  xor     r10b, r10b
0x180008115  jmp     loc_18000805E
0x18000811a  mov     ecx, 8000h
0x18000811f  sub     ecx, r10d
0x180008122  mov     r10d, ecx
0x180008125  add     r10, rdx
0x180008128  jmp     loc_180007ED2
0x180008130  cmp     r10d, 63h ; 'c'
0x180008134  jz      loc_1800081C0
0x18000813a  movzx   ecx, byte ptr [r9+1]
0x18000813f  add     r10d, 0FFFFFFF0h
0x180008143  shr     r11d, cl
0x180008146  sub     r8d, ecx
0x180008149  cmp     r8d, r10d
0x18000814c  jb      short loc_18000817E
0x18000814e  cmp     dword ptr [rax+4], 0
0x180008152  jnz     short loc_1800081C0
0x180008154  movzx   edx, word ptr [rdi+r10*2]
0x180008159  mov     r9, [r9+8]
0x18000815d  mov     ecx, r11d
0x180008160  and     rdx, rcx
0x180008163  shl     rdx, 4
0x180008167  add     r9, rdx
0x18000816a  movzx   r10d, byte ptr [r9]
0x18000816e  cmp     r10d, 10h
0x180008172  ja      short loc_180008130
0x180008174  mov     rbx, [rsp+48h+arg_10]
0x180008179  jmp     loc_180007E45
0x18000817e  mov     edi, [rax+20h]
0x180008181  mov     ebx, [rax+24h]
0x180008184  cmp     ebx, edi
0x180008186  jnb     short loc_1800081B3
0x180008188  mov     rcx, [rax+8]
0x18000818c  movzx   edx, byte ptr [rbx+rcx]
0x180008190  lea     ecx, [rbx+1]
0x180008193  mov     [rax+24h], ecx
0x180008196  mov     ecx, r8d
0x180008199  movzx   edx, dl
0x18000819c  shl     edx, cl
0x18000819e  add     r8d, 8
0x1800081a2  or      r11d, edx
0x1800081a5  cmp     r8d, r10d
0x1800081a8  jb      short loc_180008181
0x1800081aa  lea     rdi, word_18001D8B0
0x1800081b1  jmp     short loc_18000814E
0x1800081b3  jz      short loc_1800081BC
0x1800081b5  mov     dword ptr [rax+4], 1
0x1800081bc  xor     dl, dl
0x1800081be  jmp     short loc_180008196
0x1800081c0  mov     eax, 1
0x1800081c5  jmp     loc_180007F36
0x1800081d0  cmp     edi, 63h ; 'c'
0x1800081d3  jz      short loc_1800081C0
0x1800081d5  movzx   ecx, byte ptr [rsi+1]
0x1800081d9  add     edi, 0FFFFFFF0h
0x1800081dc  shr     r11d, cl
0x1800081df  sub     r8d, ecx
0x1800081e2  cmp     r8d, edi
0x1800081e5  jb      short loc_18000821E
0x1800081e7  cmp     dword ptr [rax+4], 0
0x1800081eb  jnz     short loc_1800081C0
0x1800081ed  cmp     edi, 11h
0x1800081f0  jnb     short loc_1800081C0
0x1800081f2  lfence
0x1800081f5  mov     rsi, [rsi+8]
0x1800081f9  lea     rdx, word_18001D8B0
0x180008200  movzx   edx, word ptr [rdx+rdi*2]
0x180008204  mov     ecx, r11d
  ... truncated ...
```
