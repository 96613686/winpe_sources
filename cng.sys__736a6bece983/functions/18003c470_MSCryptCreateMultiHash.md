# MSCryptCreateMultiHash

- ea: `0x18003c470`
- end: `0x18003cd93`
- name: `MSCryptCreateMultiHash`
- size: `2339`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Src, size_t Size, int)`
- caller_count: `6`
- callee_count: `26`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004820`
- `0x18003c430`
- `0x18007dfb4`
- `0x18007ec84`
- `0x180081198`
- `0x180081c48`

## callees

- `0x180005644`
- `0x18000743c`
- `0x180015260`
- `0x1800168c0`
- `0x180017d20`
- `0x18002d228`
- `0x18002e118`
- `0x18002f050`
- `0x180031f0c`
- `0x180032650`
- `0x180032848`
- `0x18003c470`
- `0x18003dac0`
- `0x180040f40`
- `0x180042a6c`
- `0x18004c340`
- `0x18004cc10`
- `0x1800651e0`
- `0x18007d670`
- `0x180087b70`
- `0x180088160`
- `0x180093eb0`
- `0x180094050`
- `0x180098d58`
- `0x18009f780`
- `0x18009fa80`

## string_xrefs

- `0x18003cd6c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptCreateMultiHash(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        void *Src,
        size_t Size,
        unsigned int a8)
{
  unsigned int v8; // r14d
  __int64 v10; // r9
  _DWORD *v11; // rax
  __int64 v12; // rdx
  unsigned int v13; // r8d
  __int64 v14; // r9
  _DWORD *v15; // r15
  unsigned int v16; // ebx
  __int64 v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // esi
  unsigned __int64 v20; // rdx
  BOOL v21; // eax
  void *v22; // r12
  unsigned int v23; // r8d
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  unsigned int i; // ebx
  unsigned int j; // ebx
  unsigned int v29; // r8d
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rbx
  unsigned int k; // ebx
  __int64 v35; // rbx
  unsigned int m; // ebx
  unsigned int n; // ebx
  unsigned int v38; // ecx
  __int64 v39; // rax
  unsigned int ii; // r14d
  __int64 v41; // rbx
  unsigned int jj; // r14d
  __int64 v43; // rbx
  unsigned int kk; // r14d
  __int64 v45; // rbx
  unsigned int mm; // ebx
  unsigned int nn; // ebx
  unsigned int i1; // ebx
  int v49; // eax
  unsigned int i2; // r14d
  __int64 v51; // rbx
  unsigned int i3; // r14d
  __int64 v53; // rbx

  v8 = a8;
  if ( (a8 & 0xFFFFFFDF) != 0 )
  {
    v10 = 957;
LABEL_110:
    v16 = -1073741811;
    v17 = 3221225485LL;
    goto LABEL_111;
  }
  v11 = (_DWORD *)validateMSCryptHashAlgorithm(a1);
  v15 = v11;
  if ( !v11 )
  {
    v16 = -1073741816;
    v10 = 966;
    v17 = 3221225480LL;
LABEL_111:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v10);
    return v16;
  }
  if ( !v12 || !a4 )
  {
    v10 = 974;
    goto LABEL_110;
  }
  if ( !v11[8] && !v11[13] && (Src || (_DWORD)Size) )
  {
    v10 = 986;
    goto LABEL_110;
  }
  v18 = v11[4];
  v19 = 1;
  if ( v13 )
  {
    if ( !v15[11] || v15[13] || v15[2] == 131080 )
    {
      v10 = 1006;
LABEL_23:
      v16 = -1073741637;
      v17 = 3221225659LL;
      goto LABEL_111;
    }
    v20 = (v13 - 1) * (unsigned __int64)(unsigned int)v15[6];
    if ( v20 > 0xFFFFFFFF )
      return (unsigned int)-1073741811;
    v18 = v20 + v15[5];
    if ( v18 < (unsigned int)v20 )
      return (unsigned int)-1073741811;
    v8 = a8 | 0x20;
    v19 = v13;
    a8 |= 0x20u;
  }
  if ( a5 >= v18 )
  {
    *(_DWORD *)v14 = v18;
    *(_DWORD *)(v14 + 4) = 1297303624;
    *(_DWORD *)(v14 + 8) = v15[2];
    *(_DWORD *)(v14 + 12) = v15[3];
    *(_DWORD *)(v14 + 16) = v15[8];
    v21 = v15[10] || (v8 & 0x20) != 0;
    *(_DWORD *)(v14 + 24) = v21;
    v22 = (void *)(v14 + 48);
    *(_DWORD *)(v14 + 28) = v15[13];
    *(_DWORD *)(v14 + 32) = 0;
    *(_DWORD *)(v14 + 36) = v13 != 0;
    *(_BYTE *)(v14 + 40) = *((_BYTE *)v15 + 48);
    *(_DWORD *)(v14 + 44) = v19;
    *(_DWORD *)(v14 + 112) = v15[7];
    memset((void *)(v14 + 48), 0, 0x40u);
    *(_DWORD *)(a4 + 20) = 0;
    switch ( v15[2] )
    {
      case 0x20001:
        v23 = 0;
        v24 = 0;
        do
        {
          v25 = 112 * v24;
          ++v23;
          *(_QWORD *)(v25 + a4 + 144) = 0;
          *(_QWORD *)(v25 + a4 + 152) = 0;
          *(_DWORD *)(v25 + a4 + 128) = 0;
          v26 = v24 + 2;
          ++v24;
          *(_OWORD *)(112 * v26 + a4) = xmmword_1800B0B88;
        }
        while ( v23 < v19 );
        goto LABEL_100;
      case 0x20002:
        for ( i = 0; i < v19; ++i )
          SymCryptSha1Init(a4 + 128 + ((unsigned __int64)i << 7));
        goto LABEL_99;
      case 0x20003:
        for ( j = 0; j < v19; ++j )
          SymCryptWipeAsm(a4 + 128 + 112LL * j, 112);
        goto LABEL_99;
      case 0x20004:
        v29 = 0;
        v30 = 0;
        do
        {
          v31 = 112 * v30;
          ++v29;
          *(_QWORD *)(v31 + a4 + 144) = 0;
          *(_QWORD *)(v31 + a4 + 152) = 0;
          *(_DWORD *)(v31 + a4 + 128) = 0;
          v32 = v30 + 2;
          ++v30;
          *(_OWORD *)(112 * v32 + a4) = xmmword_1800BD760;
        }
        while ( v29 < v19 );
        goto LABEL_100;
      case 0x20005:
        SymCryptParallelSha256Init(a4 + 128, v19);
        goto LABEL_100;
      case 0x20006:
        SymCryptParallelSha384Init(a4 + 128, v19);
        goto LABEL_100;
      case 0x20007:
        SymCryptParallelSha512Init(a4 + 128, v19);
        goto LABEL_100;
      case 0x20008:
        if ( !(unsigned int)SymCryptGcmExpandKey(a4 + 128, SymCryptAesBlockCipher_Fast, Src, (unsigned int)Size)
          && (unsigned int)(Size - 16) <= 0x10
          && (Size & 7) == 0 )
        {
          *(_DWORD *)(a4 + 116) = 0;
          goto LABEL_100;
        }
        v16 = -1073741306;
        v10 = 1161;
        v17 = 3221225990LL;
        goto LABEL_111;
      case 0x20009:
        SymCryptHmacSha1ExpandKey(a4 + 128, Src, (unsigned int)Size);
        v33 = 0;
        do
        {
          SymCryptHmacSha1Init(a4 + 208 + 144 * v33, a4 + 128);
          v33 = (unsigned int)(v33 + 1);
        }
        while ( (unsigned int)v33 < v19 );
        goto LABEL_51;
      case 0x2000A:
        SymCryptHmacMd5ExpandKey(a4 + 128, Src, (unsigned int)Size);
        for ( k = 0; k < v19; ++k )
          SymCryptHmacMd5Init(a4 + 176 + ((unsigned __int64)k << 7), a4 + 128);
        goto LABEL_51;
      case 0x2000B:
        SymCryptHmacSha256ExpandKey(a4 + 128, Src, (unsigned int)Size);
        v35 = 0;
        do
        {
          SymCryptHmacSha256Init(a4 + 208 + 144 * v35, a4 + 128);
          v35 = (unsigned int)(v35 + 1);
        }
        while ( (unsigned int)v35 < v19 );
        goto LABEL_51;
      case 0x2000C:
        SymCryptHmacSha384ExpandKey(a4 + 128, Src, (unsigned int)Size);
        for ( m = 0; m < v19; ++m )
          SymCryptHmacSha512Init(a4 + 272 + 240LL * m, a4 + 128);
        goto LABEL_51;
      case 0x2000D:
        SymCryptHmacSha512ExpandKey(a4 + 128, Src, (unsigned int)Size);
        for ( n = 0; n < v19; ++n )
          SymCryptHmacSha512Init(a4 + 272 + 240LL * n, a4 + 128);
        goto LABEL_51;
      case 0x2000E:
        if ( (unsigned int)SymCryptAesCmacExpandKey(a4 + 128, Src, (unsigned int)Size) )
        {
          v10 = 1261;
          goto LABEL_110;
        }
        v38 = 0;
        do
        {
          v39 = v38++;
          v39 <<= 6;
          *(_QWORD *)(v39 + a4 + 704) = 0;
          *(_QWORD *)(v39 + a4 + 672) = 0;
          *(_QWORD *)(v39 + a4 + 680) = 0;
          *(_QWORD *)(v39 + a4 + 712) = a4 + 128;
        }
        while ( v38 < v19 );
        goto LABEL_100;
      case 0x2000F:
        for ( ii = 0; ii < v19; ++ii )
        {
          v41 = a4 + 240LL * ii;
          *(_DWORD *)(v41 + 328) = 136;
          *(_BYTE *)(v41 + 336) = 6;
          SymCryptWipeAsm(v41 + 128, 200);
          *(_DWORD *)(v41 + 332) = 0;
          *(_BYTE *)(v41 + 337) = 0;
        }
        goto LABEL_99;
      case 0x20010:
        for ( jj = 0; jj < v19; ++jj )
        {
          v43 = a4 + 240LL * jj;
          *(_DWORD *)(v43 + 328) = 104;
          *(_BYTE *)(v43 + 336) = 6;
          SymCryptWipeAsm(v43 + 128, 200);
          *(_DWORD *)(v43 + 332) = 0;
          *(_BYTE *)(v43 + 337) = 0;
        }
        goto LABEL_99;
      case 0x20011:
        for ( kk = 0; kk < v19; ++kk )
        {
          v45 = a4 + 240LL * kk;
          *(_DWORD *)(v45 + 328) = 72;
          *(_BYTE *)(v45 + 336) = 6;
          SymCryptWipeAsm(v45 + 128, 200);
          *(_DWORD *)(v45 + 332) = 0;
          *(_BYTE *)(v45 + 337) = 0;
        }
        goto LABEL_99;
      case 0x20012:
        SymCryptHmacExpandKey(SymCryptSha3_256Algorithm_default, a4 + 128, Src, (unsigned int)Size);
        for ( mm = 0; mm < v19; ++mm )
          SymCryptHmacInit(a4 + 640 + 272LL * mm, a4 + 128);
        goto LABEL_51;
      case 0x20013:
        SymCryptHmacExpandKey(SymCryptSha3_384Algorithm_default, a4 + 128, Src, (unsigned int)Size);
        for ( nn = 0; nn < v19; ++nn )
          SymCryptHmacInit(a4 + 640 + 272LL * nn, a4 + 128);
        goto LABEL_51;
      case 0x20014:
        SymCryptHmacExpandKey(SymCryptSha3_512Algorithm_default, a4 + 128, Src, (unsigned int)Size);
        for ( i1 = 0; i1 < v19; ++i1 )
          SymCryptHmacInit(a4 + 640 + 272LL * i1, a4 + 128);
LABEL_51:
        v22 = (void *)(a4 + 48);
        goto LABEL_99;
      case 0x20015:
      case 0x20016:
        *(_QWORD *)(a4 + 184) = 0;
        *(_DWORD *)(a4 + 192) = 0;
        *(_QWORD *)(a4 + 264) = 0;
        *(_DWORD *)(a4 + 272) = 0;
        *(_DWORD *)(a4 + 280) = 0;
        goto LABEL_100;
      case 0x20017:
        *(_QWORD *)(a4 + 432) = 0;
        *(_DWORD *)(a4 + 440) = 0;
        *(_QWORD *)(a4 + 512) = 0;
        *(_DWORD *)(a4 + 520) = 0;
        v49 = MSCryptCustomBufferUpdate(a4 + 368, Src, (unsigned int)Size);
        v16 = v49;
        if ( v49 >= 0 )
          goto LABEL_93;
        v10 = 1395;
        goto LABEL_90;
      case 0x20018:
        *(_QWORD *)(a4 + 432) = 0;
        *(_DWORD *)(a4 + 440) = 0;
        *(_QWORD *)(a4 + 512) = 0;
        *(_DWORD *)(a4 + 520) = 0;
        v49 = MSCryptCustomBufferUpdate(a4 + 368, Src, (unsigned int)Size);
        v16 = v49;
        if ( v49 < 0 )
        {
          v10 = 1416;
LABEL_90:
          v17 = (unsigned int)v49;
          goto LABEL_111;
        }
LABEL_93:
        *(_DWORD *)(a4 + 528) = 0;
LABEL_100:
        if ( *(_DWORD *)(a4 + 28) )
        {
          if ( (unsigned int)Size <= v15[7] )
          {
            memmove(v22, Src, (unsigned int)Size);
          }
          else
          {
            v49 = MSCryptHashDataInternal(a4, Src);
            v16 = v49;
            if ( v49 < 0 )
            {
              v10 = 1474;
              goto LABEL_90;
            }
            v49 = MSCryptHashResultInternal(a4, (__int64)v22, *(unsigned int *)(a4 + 12), v8);
            v16 = v49;
            if ( v49 < 0 )
            {
              v10 = 1483;
              goto LABEL_90;
            }
          }
        }
        v16 = 0;
        *a2 = a4;
        return v16;
      case 0x20019:
        for ( i2 = 0; i2 < v19; ++i2 )
        {
          v51 = a4 + 240LL * i2;
          *(_DWORD *)(v51 + 328) = 168;
          *(_BYTE *)(v51 + 336) = 31;
          SymCryptWipeAsm(v51 + 128, 200);
          *(_DWORD *)(v51 + 332) = 0;
          *(_BYTE *)(v51 + 337) = 0;
        }
        goto LABEL_99;
      case 0x2001A:
        for ( i3 = 0; i3 < v19; ++i3 )
        {
          v53 = a4 + 240LL * i3;
          *(_DWORD *)(v53 + 328) = 136;
          *(_BYTE *)(v53 + 336) = 31;
          SymCryptWipeAsm(v53 + 128, 200);
          *(_DWORD *)(v53 + 332) = 0;
          *(_BYTE *)(v53 + 337) = 0;
        }
LABEL_99:
        v8 = a8;
        goto LABEL_100;
      default:
        v10 = 1453;
        goto LABEL_23;
    }
  }
  return (unsigned int)-1073741789;
}

```

## disassembly

```asm
0x18003c470  mov     [rsp+arg_8], rdx
0x18003c475  push    rbx
0x18003c476  push    rbp
0x18003c477  push    rsi
0x18003c478  push    rdi
0x18003c479  push    r12
0x18003c47b  push    r13
0x18003c47d  push    r14
0x18003c47f  push    r15
0x18003c481  sub     rsp, 28h
0x18003c485  mov     r14d, [rsp+68h+arg_38]
0x18003c48d  mov     rdi, r9
0x18003c490  test    r14d, 0FFFFFFDFh
0x18003c497  jz      short loc_18003C4A4
0x18003c499  mov     r9d, 3BDh
0x18003c49f  jmp     loc_18003CD62
0x18003c4a4  call    validateMSCryptHashAlgorithm
0x18003c4a9  mov     r15, rax
0x18003c4ac  test    rax, rax
0x18003c4af  jnz     short loc_18003C4C6
0x18003c4b1  mov     ebx, 0C0000008h
0x18003c4b6  mov     r9d, 3C6h
0x18003c4bc  mov     ecx, 0C0000008h
0x18003c4c1  jmp     loc_18003CD6C
0x18003c4c6  test    rdx, rdx
0x18003c4c9  jz      loc_18003CD5C
0x18003c4cf  test    rdi, rdi
0x18003c4d2  jz      loc_18003CD5C
0x18003c4d8  cmp     dword ptr [rax+20h], 0
0x18003c4dc  mov     ebp, dword ptr [rsp+68h+Size]
0x18003c4e3  mov     r13, [rsp+68h+Src]
0x18003c4eb  jnz     short loc_18003C507
0x18003c4ed  cmp     dword ptr [rax+34h], 0
0x18003c4f1  jnz     short loc_18003C507
0x18003c4f3  test    r13, r13
0x18003c4f6  jnz     short loc_18003C4FC
0x18003c4f8  test    ebp, ebp
0x18003c4fa  jz      short loc_18003C507
0x18003c4fc  mov     r9d, 3DAh
0x18003c502  jmp     loc_18003CD62
0x18003c507  mov     eax, [rax+10h]
0x18003c50a  mov     ebx, 1
0x18003c50f  mov     esi, ebx
0x18003c511  test    r8d, r8d
0x18003c514  jz      short loc_18003C55D
0x18003c516  cmp     dword ptr [r15+2Ch], 0
0x18003c51b  jz      short loc_18003C57A
0x18003c51d  cmp     dword ptr [r15+34h], 0
0x18003c522  jnz     short loc_18003C57A
0x18003c524  cmp     dword ptr [r15+8], 20008h
0x18003c52c  jz      short loc_18003C57A
0x18003c52e  mov     edx, [r15+18h]
0x18003c532  lea     ecx, [r8-1]
0x18003c536  imul    rdx, rcx
0x18003c53a  mov     eax, 0FFFFFFFFh
0x18003c53f  cmp     rdx, rax
0x18003c542  ja      short loc_18003C570
0x18003c544  mov     eax, [r15+14h]
0x18003c548  add     eax, edx
0x18003c54a  cmp     eax, edx
0x18003c54c  jb      short loc_18003C570
0x18003c54e  or      r14d, 20h
0x18003c552  mov     esi, r8d
0x18003c555  mov     [rsp+68h+arg_38], r14d
0x18003c55d  cmp     [rsp+68h+arg_20], eax
0x18003c564  jnb     short loc_18003C58F
0x18003c566  mov     ebx, 0C0000023h
0x18003c56b  jmp     loc_18003CD7F
0x18003c570  mov     ebx, 0C000000Dh
0x18003c575  jmp     loc_18003CD7F
0x18003c57a  mov     r9d, 3EEh
0x18003c580  mov     ebx, 0C00000BBh
0x18003c585  mov     ecx, 0C00000BBh
0x18003c58a  jmp     loc_18003CD6C
0x18003c58f  mov     [r9], eax
0x18003c592  mov     dword ptr [r9+4], 4D534848h
0x18003c59a  mov     eax, [r15+8]
0x18003c59e  mov     [r9+8], eax
0x18003c5a2  mov     eax, [r15+0Ch]
0x18003c5a6  mov     [r9+0Ch], eax
0x18003c5aa  mov     eax, [r15+20h]
0x18003c5ae  mov     [r9+10h], eax
0x18003c5b2  cmp     dword ptr [r15+28h], 0
0x18003c5b7  jnz     short loc_18003C5C3
0x18003c5b9  test    r14b, 20h
0x18003c5bd  jnz     short loc_18003C5C3
0x18003c5bf  xor     eax, eax
0x18003c5c1  jmp     short loc_18003C5C5
0x18003c5c3  mov     eax, ebx
0x18003c5c5  mov     [r9+18h], eax
0x18003c5c9  lea     r12, [r9+30h]
0x18003c5cd  mov     eax, [r15+34h]
0x18003c5d1  mov     rcx, r12; void *
0x18003c5d4  mov     [r9+1Ch], eax
0x18003c5d8  xor     eax, eax
0x18003c5da  test    r8d, r8d
0x18003c5dd  mov     dword ptr [r9+20h], 0
0x18003c5e5  setnz   al
0x18003c5e8  xor     edx, edx; Val
0x18003c5ea  mov     [r9+24h], eax
0x18003c5ee  mov     al, [r15+30h]
0x18003c5f2  mov     [r9+28h], al
0x18003c5f6  mov     [r9+2Ch], esi
0x18003c5fa  lea     r8d, [rdx+40h]; Size
0x18003c5fe  mov     eax, [r15+1Ch]
0x18003c602  mov     [r9+70h], eax
0x18003c606  call    memset
0x18003c60b  mov     dword ptr [rdi+14h], 0
0x18003c612  mov     eax, [r15+8]
0x18003c616  add     eax, 0FFFDFFFFh; switch 26 cases
0x18003c61b  cmp     eax, 19h
0x18003c61e  ja      def_18003C635; jumptable 000000018003C635 default case
0x18003c624  lea     rcx, cs:180000000h
0x18003c62b  mov     eax, ds:(jpt_18003C635 - 180000000h)[rcx+rax*4]
0x18003c632  add     rax, rcx
0x18003c635  jmp     rax; switch jump
0x18003c63b  xor     r8d, r8d; jumptable 000000018003C635 case 131073
0x18003c63e  test    esi, esi
0x18003c640  jz      loc_18003CCEC
0x18003c646  xor     edx, edx
0x18003c648  imul    rax, rdx, 70h ; 'p'
0x18003c64c  add     r8d, ebx
0x18003c64f  mov     qword ptr [rax+rdi+90h], 0
0x18003c65b  mov     qword ptr [rax+rdi+98h], 0
0x18003c667  mov     dword ptr [rax+rdi+80h], 0
0x18003c672  lea     rax, [rdx+2]
0x18003c676  movups  xmm0, cs:xmmword_1800B0B88
0x18003c67d  add     rdx, rbx
0x18003c680  imul    rcx, rax, 70h ; 'p'
0x18003c684  movdqu  xmmword ptr [rcx+rdi], xmm0
0x18003c689  cmp     r8d, esi
0x18003c68c  jb      short loc_18003C648
0x18003c68e  jmp     loc_18003CCEC
0x18003c693  xor     ebx, ebx; jumptable 000000018003C635 case 131074
0x18003c695  test    esi, esi
0x18003c697  jz      loc_18003CCEC
0x18003c69d  lea     r14, [rdi+80h]
0x18003c6a4  mov     ecx, ebx
0x18003c6a6  shl     rcx, 7
0x18003c6aa  add     rcx, r14
0x18003c6ad  call    SymCryptSha1Init
0x18003c6b2  inc     ebx
0x18003c6b4  cmp     ebx, esi
0x18003c6b6  jb      short loc_18003C6A4
0x18003c6b8  jmp     loc_18003CCE4
0x18003c6bd  xor     ebx, ebx; jumptable 000000018003C635 case 131075
0x18003c6bf  test    esi, esi
0x18003c6c1  jz      loc_18003CCEC
0x18003c6c7  lea     r14, [rdi+80h]
0x18003c6ce  mov     eax, ebx
0x18003c6d0  mov     edx, 70h ; 'p'
0x18003c6d5  imul    rcx, rax, 70h ; 'p'
0x18003c6d9  add     rcx, r14
0x18003c6dc  call    SymCryptWipeAsm
0x18003c6e1  inc     ebx
0x18003c6e3  cmp     ebx, esi
0x18003c6e5  jb      short loc_18003C6CE
0x18003c6e7  jmp     loc_18003CCE4
0x18003c6ec  xor     r8d, r8d; jumptable 000000018003C635 case 131076
0x18003c6ef  test    esi, esi
0x18003c6f1  jz      loc_18003CCEC
0x18003c6f7  xor     edx, edx
0x18003c6f9  imul    rax, rdx, 70h ; 'p'
0x18003c6fd  add     r8d, ebx
0x18003c700  mov     qword ptr [rax+rdi+90h], 0
0x18003c70c  mov     qword ptr [rax+rdi+98h], 0
0x18003c718  mov     dword ptr [rax+rdi+80h], 0
0x18003c723  lea     rax, [rdx+2]
0x18003c727  movups  xmm0, cs:xmmword_1800BD760
0x18003c72e  add     rdx, rbx
0x18003c731  imul    rcx, rax, 70h ; 'p'
0x18003c735  movdqu  xmmword ptr [rcx+rdi], xmm0
0x18003c73a  cmp     r8d, esi
0x18003c73d  jb      short loc_18003C6F9
0x18003c73f  jmp     loc_18003CCEC
0x18003c744  mov     edx, esi; jumptable 000000018003C635 case 131077
0x18003c746  lea     rcx, [rdi+80h]
0x18003c74d  call    SymCryptParallelSha256Init
0x18003c752  jmp     loc_18003CCEC
0x18003c757  mov     edx, esi; jumptable 000000018003C635 case 131078
0x18003c759  lea     rcx, [rdi+80h]
0x18003c760  call    SymCryptParallelSha384Init
0x18003c765  jmp     loc_18003CCEC
0x18003c76a  mov     edx, esi; jumptable 000000018003C635 case 131079
0x18003c76c  lea     rcx, [rdi+80h]
0x18003c773  call    SymCryptParallelSha512Init
0x18003c778  jmp     loc_18003CCEC
0x18003c77d  mov     r9, rbp; jumptable 000000018003C635 case 131080
0x18003c780  lea     rcx, [rdi+80h]
0x18003c787  mov     r8, r13
0x18003c78a  lea     rdx, SymCryptAesBlockCipher_Fast
0x18003c791  call    SymCryptGcmExpandKey
0x18003c796  test    eax, eax
0x18003c798  jnz     short loc_18003C7B4
0x18003c79a  lea     eax, [rbp-10h]
0x18003c79d  cmp     eax, 10h
0x18003c7a0  ja      short loc_18003C7B4
0x18003c7a2  test    bpl, 7
0x18003c7a6  jnz     short loc_18003C7B4
0x18003c7a8  mov     dword ptr [rdi+74h], 0
0x18003c7af  jmp     loc_18003CCEC
0x18003c7b4  mov     ebx, 0C0000206h
0x18003c7b9  mov     r9d, 489h
0x18003c7bf  mov     ecx, 0C0000206h
0x18003c7c4  jmp     loc_18003CD6C
0x18003c7c9  lea     r14, [rdi+80h]; jumptable 000000018003C635 case 131081
0x18003c7d0  mov     r8, rbp
0x18003c7d3  mov     rcx, r14
0x18003c7d6  mov     rdx, r13
0x18003c7d9  call    SymCryptHmacSha1ExpandKey
0x18003c7de  xor     ebx, ebx
0x18003c7e0  test    esi, esi
0x18003c7e2  jz      loc_18003CCE4
0x18003c7e8  lea     r12, [rdi+0D0h]
0x18003c7ef  lea     rcx, [rbx+rbx*8]
0x18003c7f3  mov     rdx, r14
0x18003c7f6  shl     rcx, 4
0x18003c7fa  add     rcx, r12
0x18003c7fd  call    SymCryptHmacSha1Init
0x18003c802  inc     ebx
0x18003c804  cmp     ebx, esi
0x18003c806  jb      short loc_18003C7EF
0x18003c808  lea     r12, [rdi+30h]
0x18003c80c  jmp     loc_18003CCE4
0x18003c811  lea     r14, [rdi+80h]; jumptable 000000018003C635 case 131082
0x18003c818  mov     r8, rbp
0x18003c81b  mov     rcx, r14
0x18003c81e  mov     rdx, r13
0x18003c821  call    SymCryptHmacMd5ExpandKey
0x18003c826  xor     ebx, ebx
0x18003c828  test    esi, esi
0x18003c82a  jz      loc_18003CCE4
0x18003c830  lea     r12, [rdi+0B0h]
0x18003c837  mov     ecx, ebx
0x18003c839  mov     rdx, r14
0x18003c83c  shl     rcx, 7
0x18003c840  add     rcx, r12
0x18003c843  call    SymCryptHmacMd5Init
0x18003c848  inc     ebx
0x18003c84a  cmp     ebx, esi
0x18003c84c  jb      short loc_18003C837
0x18003c84e  jmp     short loc_18003C808
0x18003c850  lea     r14, [rdi+80h]; jumptable 000000018003C635 case 131083
0x18003c857  mov     r8, rbp
0x18003c85a  mov     rcx, r14
0x18003c85d  mov     rdx, r13
0x18003c860  call    SymCryptHmacSha256ExpandKey
0x18003c865  xor     ebx, ebx
0x18003c867  test    esi, esi
0x18003c869  jz      loc_18003CCE4
0x18003c86f  lea     r12, [rdi+0D0h]
0x18003c876  lea     rcx, [rbx+rbx*8]
0x18003c87a  mov     rdx, r14
0x18003c87d  shl     rcx, 4
0x18003c881  add     rcx, r12
0x18003c884  call    SymCryptHmacSha256Init
0x18003c889  inc     ebx
0x18003c88b  cmp     ebx, esi
0x18003c88d  jb      short loc_18003C876
0x18003c88f  jmp     loc_18003C808
0x18003c894  lea     r14, [rdi+80h]; jumptable 000000018003C635 case 131084
0x18003c89b  mov     r8, rbp
0x18003c89e  mov     rcx, r14
0x18003c8a1  mov     rdx, r13
0x18003c8a4  call    SymCryptHmacSha384ExpandKey
0x18003c8a9  xor     ebx, ebx
0x18003c8ab  test    esi, esi
0x18003c8ad  jz      loc_18003CCE4
0x18003c8b3  lea     r12, [rdi+110h]
0x18003c8ba  mov     eax, ebx
0x18003c8bc  mov     rdx, r14
0x18003c8bf  imul    rcx, rax, 0F0h
0x18003c8c6  add     rcx, r12
0x18003c8c9  call    SymCryptHmacSha512Init
0x18003c8ce  inc     ebx
0x18003c8d0  cmp     ebx, esi
0x18003c8d2  jb      short loc_18003C8BA
0x18003c8d4  jmp     loc_18003C808
0x18003c8d9  lea     r14, [rdi+80h]; jumptable 000000018003C635 case 131085
0x18003c8e0  mov     r8, rbp
0x18003c8e3  mov     rcx, r14
0x18003c8e6  mov     rdx, r13
0x18003c8e9  call    SymCryptHmacSha512ExpandKey
0x18003c8ee  xor     ebx, ebx
0x18003c8f0  test    esi, esi
0x18003c8f2  jz      loc_18003CCE4
0x18003c8f8  lea     r12, [rdi+110h]
0x18003c8ff  mov     eax, ebx
0x18003c901  mov     rdx, r14
0x18003c904  imul    rcx, rax, 0F0h
0x18003c90b  add     rcx, r12
0x18003c90e  call    SymCryptHmacSha512Init
0x18003c913  inc     ebx
0x18003c915  cmp     ebx, esi
0x18003c917  jb      short loc_18003C8FF
0x18003c919  jmp     loc_18003C808
0x18003c91e  lea     rbx, [rdi+80h]; jumptable 000000018003C635 case 131086
0x18003c925  mov     r8, rbp
0x18003c928  mov     rcx, rbx
0x18003c92b  mov     rdx, r13
  ... truncated ...
```
