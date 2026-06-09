# vFontFileCache(_TTC_FONTFILE *,ulong,ulong)

- ea: `0x140092168`
- end: `0x14009244a`
- name: `?vFontFileCache@@YAXPEAU_TTC_FONTFILE@@KK@Z`
- size: `738`
- prototype: `void(struct _TTC_FONTFILE *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140007104`

## callees

- `0x140076eea`
- `0x140092168`
- `0x140092868`
- `0x1400928c0`
- `0x140092964`

## pseudocode

```c
void __fastcall vFontFileCache(struct _TTC_FONTFILE *a1, ULONG a2, int a3)
{
  unsigned int v5; // r9d
  __int64 i; // r10
  unsigned int v7; // ebx
  ULONG v8; // edx
  unsigned int v9; // r15d
  _DWORD *v10; // rax
  _DWORD *v11; // rsi
  int v12; // r12d
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 j; // r15
  _OWORD *v16; // rcx
  _OWORD *v17; // rax
  __int64 v18; // r8
  int v19; // [rsp+20h] [rbp-68h]
  __int64 v20; // [rsp+28h] [rbp-60h]
  __int64 v21; // [rsp+38h] [rbp-50h]
  _DWORD *v23; // [rsp+A8h] [rbp+20h]

  if ( a2 )
  {
    v5 = 0;
    for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 3); i = (unsigned int)(i + 1) )
    {
      if ( *((_DWORD *)a1 + 4 * (unsigned int)i + 11) == 1 )
      {
        if ( v5 + ((*(_DWORD *)(*((_QWORD *)a1 + 2 * i + 6) + 440LL) + 7) & 0xFFFFFFF8) + 328 < v5 )
          return;
        v5 += ((*(_DWORD *)(*((_QWORD *)a1 + 2 * i + 6) + 440LL) + 7) & 0xFFFFFFF8) + 328;
      }
    }
    v7 = (4 * *((_DWORD *)a1 + 2) + 23) & 0xFFFFFFF8;
    v8 = v7 + v5;
    if ( v7 + v5 >= v5 )
    {
      v9 = 0;
      if ( (*(_DWORD *)(*((_QWORD *)a1 + 6) + 388LL) & 0x100) != 0 )
      {
        if ( v8 + ((**((_DWORD **)a1 + 4) + 7) & 0xFFFFFFF8) < v8 )
          return;
        v9 = v7 + v5;
        v8 += (**((_DWORD **)a1 + 4) + 7) & 0xFFFFFFF8;
      }
      v10 = EngFntCacheAlloc(a2, v8);
      v11 = v10;
      if ( v10 )
      {
        v12 = 0;
        v13 = 0;
        v19 = 0;
        *v10 = 1416914532;
        v10[1] = a3;
        v10[2] = *((_DWORD *)a1 + 2);
        v10[3] = v9;
        v14 = (__int64)v10 + v7;
        v20 = v14;
        for ( j = 0; (unsigned int)j < *((_DWORD *)a1 + 3); j = (unsigned int)(j + 1) )
        {
          if ( *((_DWORD *)a1 + 4 * (unsigned int)j + 11) == 1 )
          {
            v21 = *((_QWORD *)a1 + 2 * j + 6);
            v23 = (_DWORD *)v14;
            v11[v13 + 4] = v14 - (_DWORD)v11;
            v16 = (_OWORD *)(v14 + 4);
            v17 = (_OWORD *)(v21 + 112);
            v18 = 2;
            do
            {
              *v16 = *v17;
              v16[1] = v17[1];
              v16[2] = v17[2];
              v16[3] = v17[3];
              v16[4] = v17[4];
              v16[5] = v17[5];
              v16[6] = v17[6];
              v16[7] = v17[7];
              v16 += 8;
              v17 += 8;
              --v18;
            }
            while ( v18 );
            *v16 = *v17;
            v16[1] = v17[1];
            v16[2] = v17[2];
            v16[3] = v17[3];
            *((_DWORD *)v16 + 16) = *((_DWORD *)v17 + 16);
            memcpy_0((void *)(v14 + 328), (const void *)(v21 + 440), *(unsigned int *)(v21 + 440));
            v14 = ((*(_DWORD *)(v21 + 440) + 7) & 0xFFFFFFF8) + v20 + 328;
            v20 = v14;
            if ( *(_DWORD *)(v21 + 372) == 2 )
            {
              if ( *(unsigned int (__fastcall **)(struct _TT_FONTFILE *, unsigned int))(v21 + 8) == SearchMortTable )
                *v23 = 2;
              else
                *v23 = *(_QWORD *)(v21 + 8) == (_QWORD)SearchGsubTable;
            }
            else
            {
              *v23 = 0;
            }
            v13 = (unsigned int)++v19;
          }
        }
        if ( v11[3] )
          memcpy_0((char *)v11 + (unsigned int)v11[3], *((const void **)a1 + 4), **((unsigned int **)a1 + 4));
        if ( !(unsigned int)EngFntCacheFlush(v11, 0) )
          v12 = 1;
        if ( v12 )
          EngFntCacheFault(a2, 2u);
      }
    }
  }
}

```

## disassembly

```asm
0x140092168  test    edx, edx
0x14009216a  jz      locret_140092449
0x140092170  mov     [rsp+arg_10], r8d
0x140092175  mov     [rsp+arg_8], edx
0x140092179  push    rbx
0x14009217a  push    rsi
0x14009217b  push    rdi
0x14009217c  push    r12
0x14009217e  push    r13
0x140092180  push    r14
0x140092182  push    r15
0x140092184  sub     rsp, 50h
0x140092188  mov     r13d, edx
0x14009218b  mov     rdi, rcx
0x14009218e  xor     r9d, r9d
0x140092191  xor     r10d, r10d
0x140092194  lea     r14d, [r9+1]
0x140092198  mov     r8d, 0FFFFFFF8h
0x14009219e  cmp     r10d, [rcx+0Ch]
0x1400921a2  jnb     short loc_1400921E1
0x1400921a4  mov     eax, r10d
0x1400921a7  add     rax, rax
0x1400921aa  cmp     [rcx+rax*8+2Ch], r14d
0x1400921af  jnz     short loc_1400921DC
0x1400921b1  lea     rax, [r10+3]
0x1400921b5  add     rax, rax
0x1400921b8  mov     rax, [rcx+rax*8]
0x1400921bc  mov     eax, [rax+1B8h]
0x1400921c2  add     eax, 7
0x1400921c5  and     eax, r8d
0x1400921c8  add     eax, 148h
0x1400921cd  add     eax, r9d
0x1400921d0  cmp     eax, r9d
0x1400921d3  jb      loc_14009243A
0x1400921d9  mov     r9d, eax
0x1400921dc  add     r10d, r14d
0x1400921df  jmp     short loc_14009219E
0x1400921e1  mov     eax, [rcx+8]
0x1400921e4  lea     ebx, ds:17h[rax*4]
0x1400921eb  and     ebx, r8d
0x1400921ee  lea     edx, [rbx+r9]
0x1400921f2  cmp     edx, r9d
0x1400921f5  jb      loc_14009243A
0x1400921fb  xor     r15d, r15d
0x1400921fe  mov     rax, [rcx+30h]
0x140092202  test    dword ptr [rax+184h], 100h
0x14009220c  jz      short loc_140092229
0x14009220e  mov     rax, [rcx+20h]
0x140092212  mov     eax, [rax]
0x140092214  add     eax, 7
0x140092217  and     eax, r8d
0x14009221a  add     eax, edx
0x14009221c  cmp     eax, edx
0x14009221e  jb      loc_14009243A
0x140092224  mov     r15d, edx
0x140092227  mov     edx, eax; ulSize
0x140092229  mov     ecx, r13d; FastCheckSum
0x14009222c  call    EngFntCacheAlloc
0x140092231  mov     rsi, rax
0x140092234  mov     [rsp+88h+var_48], rax
0x140092239  test    rax, rax
0x14009223c  jz      loc_14009243A
0x140092242  xor     r12d, r12d
0x140092245  xor     r8d, r8d
0x140092248  mov     [rsp+88h+var_68], r8d
0x14009224d  mov     dword ptr [rax], 54746664h
0x140092253  mov     eax, [rsp+88h+arg_10]
0x14009225a  mov     [rsi+4], eax
0x14009225d  mov     eax, [rdi+8]
0x140092260  mov     [rsi+8], eax
0x140092263  mov     [rsi+0Ch], r15d
0x140092267  mov     edx, ebx
0x140092269  add     rdx, rsi
0x14009226c  mov     [rsp+88h+var_60], rdx
0x140092271  mov     [rsp+88h+var_58], rdx
0x140092276  xor     r15d, r15d
0x140092279  mov     [rsp+88h+var_64], r15d
0x14009227e  cmp     r15d, [rdi+0Ch]
0x140092282  jnb     loc_1400923E7
0x140092288  mov     eax, r15d
0x14009228b  add     rax, rax
0x14009228e  cmp     [rdi+rax*8+2Ch], r14d
0x140092293  jnz     loc_1400923DF
0x140092299  lea     rax, [r15+3]
0x14009229d  add     rax, rax
0x1400922a0  mov     r9, [rdi+rax*8]
0x1400922a4  mov     [rsp+88h+var_50], r9
0x1400922a9  mov     [rsp+88h+arg_18], rdx
0x1400922b1  mov     ecx, edx
0x1400922b3  sub     ecx, esi
0x1400922b5  mov     [rsi+r8*4+10h], ecx
0x1400922ba  lea     rcx, [rdx+4]
0x1400922be  lea     rax, [r9+70h]
0x1400922c2  mov     r8d, 2
0x1400922c8  movups  xmm0, xmmword ptr [rax]
0x1400922cb  movups  xmmword ptr [rcx], xmm0
0x1400922ce  movups  xmm1, xmmword ptr [rax+10h]
0x1400922d2  movups  xmmword ptr [rcx+10h], xmm1
0x1400922d6  movups  xmm0, xmmword ptr [rax+20h]
0x1400922da  movups  xmmword ptr [rcx+20h], xmm0
0x1400922de  movups  xmm1, xmmword ptr [rax+30h]
0x1400922e2  movups  xmmword ptr [rcx+30h], xmm1
0x1400922e6  movups  xmm0, xmmword ptr [rax+40h]
0x1400922ea  movups  xmmword ptr [rcx+40h], xmm0
0x1400922ee  movups  xmm1, xmmword ptr [rax+50h]
0x1400922f2  movups  xmmword ptr [rcx+50h], xmm1
0x1400922f6  movups  xmm0, xmmword ptr [rax+60h]
0x1400922fa  movups  xmmword ptr [rcx+60h], xmm0
0x1400922fe  movups  xmm1, xmmword ptr [rax+70h]
0x140092302  movups  xmmword ptr [rcx+70h], xmm1
0x140092306  lea     rcx, [rcx+80h]
0x14009230d  lea     rax, [rax+80h]
0x140092314  sub     r8, 1
0x140092318  jnz     short loc_1400922C8
0x14009231a  movups  xmm0, xmmword ptr [rax]
0x14009231d  movups  xmmword ptr [rcx], xmm0
0x140092320  movups  xmm1, xmmword ptr [rax+10h]
0x140092324  movups  xmmword ptr [rcx+10h], xmm1
0x140092328  movups  xmm0, xmmword ptr [rax+20h]
0x14009232c  movups  xmmword ptr [rcx+20h], xmm0
0x140092330  movups  xmm1, xmmword ptr [rax+30h]
0x140092334  movups  xmmword ptr [rcx+30h], xmm1
0x140092338  mov     eax, [rax+40h]
0x14009233b  mov     [rcx+40h], eax
0x14009233e  lea     rbx, [r9+1B8h]
0x140092345  mov     r8d, [rbx]; Size
0x140092348  lea     rcx, [rdx+148h]; void *
0x14009234f  mov     rdx, rbx; Src
0x140092352  call    memcpy_0
0x140092357  mov     eax, [rbx]
0x140092359  add     eax, 7
0x14009235c  mov     ecx, 0FFFFFFF8h
0x140092361  and     rax, rcx
0x140092364  mov     rdx, [rsp+88h+var_60]
0x140092369  add     rdx, 148h
0x140092370  add     rdx, rax
0x140092373  mov     [rsp+88h+var_60], rdx
0x140092378  mov     [rsp+88h+var_58], rdx
0x14009237d  mov     rcx, [rsp+88h+var_50]
0x140092382  cmp     dword ptr [rcx+174h], 2
0x140092389  jnz     short loc_1400923C4
0x14009238b  lea     rax, ?SearchMortTable@@YAKPEAU_TT_FONTFILE@@K@Z; SearchMortTable(_TT_FONTFILE *,ulong)
0x140092392  cmp     [rcx+8], rax
0x140092396  jnz     short loc_1400923A8
0x140092398  mov     rcx, [rsp+88h+arg_18]
0x1400923a0  mov     dword ptr [rcx], 2
0x1400923a6  jmp     short loc_1400923D2
0x1400923a8  xor     eax, eax
0x1400923aa  lea     r8, ?SearchGsubTable@@YAKPEAU_TT_FONTFILE@@K@Z; SearchGsubTable(_TT_FONTFILE *,ulong)
0x1400923b1  cmp     [rcx+8], r8
0x1400923b5  setz    al
0x1400923b8  mov     rcx, [rsp+88h+arg_18]
0x1400923c0  mov     [rcx], eax
0x1400923c2  jmp     short loc_1400923D2
0x1400923c4  mov     rcx, [rsp+88h+arg_18]
0x1400923cc  mov     dword ptr [rcx], 0
0x1400923d2  mov     r8d, [rsp+88h+var_68]
0x1400923d7  add     r8d, r14d
0x1400923da  mov     [rsp+88h+var_68], r8d
0x1400923df  add     r15d, r14d
0x1400923e2  jmp     loc_140092279
0x1400923e7  cmp     dword ptr [rsi+0Ch], 0
0x1400923eb  jz      short loc_1400923FF
0x1400923ed  mov     rdx, [rdi+20h]; Src
0x1400923f1  mov     r8d, [rdx]; Size
0x1400923f4  mov     ecx, [rsi+0Ch]
0x1400923f7  add     rcx, rsi; void *
0x1400923fa  call    memcpy_0
0x1400923ff  jmp     short loc_140092417
0x140092401  mov     r12d, 1
0x140092407  mov     r14d, r12d
0x14009240a  mov     r13d, [rsp+88h+arg_8]
0x140092412  mov     rsi, [rsp+88h+var_48]
0x140092417  mov     edx, r12d
0x14009241a  mov     rcx, rsi
0x14009241d  call    EngFntCacheFlush
0x140092422  test    eax, eax
0x140092424  cmovz   r12d, r14d
0x140092428  test    r12d, r12d
0x14009242b  jz      short loc_14009243A
0x14009242d  mov     edx, 2; iFaultMode
0x140092432  mov     ecx, r13d; ulFastCheckSum
0x140092435  call    EngFntCacheFault
0x14009243a  add     rsp, 50h
0x14009243e  pop     r15
0x140092440  pop     r14
0x140092442  pop     r13
0x140092444  pop     r12
0x140092446  pop     rdi
0x140092447  pop     rsi
0x140092448  pop     rbx
0x140092449  retn
```
