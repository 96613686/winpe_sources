# MSCryptCreateMultiHash

- ea: `0x18003b970`
- end: `0x18003c293`
- name: `MSCryptCreateMultiHash`
- size: `2339`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Src, size_t Size, int)`
- caller_count: `6`
- callee_count: `26`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004820`
- `0x18003b930`
- `0x18007cfc4`
- `0x18007dc94`
- `0x1800801a8`
- `0x180080c58`

## callees

- `0x180005644`
- `0x18000743c`
- `0x1800115d0`
- `0x1800181b0`
- `0x180019810`
- `0x18001ac70`
- `0x18002d618`
- `0x18002e550`
- `0x18003140c`
- `0x180031b50`
- `0x180031d48`
- `0x18003b970`
- `0x18003cf30`
- `0x1800403b0`
- `0x180041fdc`
- `0x18004b8b0`
- `0x18004c3d0`
- `0x180064860`
- `0x18007c680`
- `0x180086b60`
- `0x180087150`
- `0x180092450`
- `0x1800925f0`
- `0x1800972f8`
- `0x18009da40`
- `0x18009dd40`

## string_xrefs

- `0x18003c26c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

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
          *(_OWORD *)(112 * v26 + a4) = xmmword_1800AE788;
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
          *(_OWORD *)(112 * v32 + a4) = xmmword_1800BB1A0;
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
0x18003b970  mov     [rsp+arg_8], rdx
0x18003b975  push    rbx
0x18003b976  push    rbp
0x18003b977  push    rsi
0x18003b978  push    rdi
0x18003b979  push    r12
0x18003b97b  push    r13
0x18003b97d  push    r14
0x18003b97f  push    r15
0x18003b981  sub     rsp, 28h
0x18003b985  mov     r14d, [rsp+68h+arg_38]
0x18003b98d  mov     rdi, r9
0x18003b990  test    r14d, 0FFFFFFDFh
0x18003b997  jz      short loc_18003B9A4
0x18003b999  mov     r9d, 3BDh
0x18003b99f  jmp     loc_18003C262
0x18003b9a4  call    validateMSCryptHashAlgorithm
0x18003b9a9  mov     r15, rax
0x18003b9ac  test    rax, rax
0x18003b9af  jnz     short loc_18003B9C6
0x18003b9b1  mov     ebx, 0C0000008h
0x18003b9b6  mov     r9d, 3C6h
0x18003b9bc  mov     ecx, 0C0000008h
0x18003b9c1  jmp     loc_18003C26C
0x18003b9c6  test    rdx, rdx
0x18003b9c9  jz      loc_18003C25C
0x18003b9cf  test    rdi, rdi
0x18003b9d2  jz      loc_18003C25C
0x18003b9d8  cmp     dword ptr [rax+20h], 0
0x18003b9dc  mov     ebp, dword ptr [rsp+68h+Size]
0x18003b9e3  mov     r13, [rsp+68h+Src]
0x18003b9eb  jnz     short loc_18003BA07
0x18003b9ed  cmp     dword ptr [rax+34h], 0
0x18003b9f1  jnz     short loc_18003BA07
0x18003b9f3  test    r13, r13
0x18003b9f6  jnz     short loc_18003B9FC
0x18003b9f8  test    ebp, ebp
0x18003b9fa  jz      short loc_18003BA07
0x18003b9fc  mov     r9d, 3DAh
0x18003ba02  jmp     loc_18003C262
0x18003ba07  mov     eax, [rax+10h]
0x18003ba0a  mov     ebx, 1
0x18003ba0f  mov     esi, ebx
0x18003ba11  test    r8d, r8d
0x18003ba14  jz      short loc_18003BA5D
0x18003ba16  cmp     dword ptr [r15+2Ch], 0
0x18003ba1b  jz      short loc_18003BA7A
0x18003ba1d  cmp     dword ptr [r15+34h], 0
0x18003ba22  jnz     short loc_18003BA7A
0x18003ba24  cmp     dword ptr [r15+8], 20008h
0x18003ba2c  jz      short loc_18003BA7A
0x18003ba2e  mov     edx, [r15+18h]
0x18003ba32  lea     ecx, [r8-1]
0x18003ba36  imul    rdx, rcx
0x18003ba3a  mov     eax, 0FFFFFFFFh
0x18003ba3f  cmp     rdx, rax
0x18003ba42  ja      short loc_18003BA70
0x18003ba44  mov     eax, [r15+14h]
0x18003ba48  add     eax, edx
0x18003ba4a  cmp     eax, edx
0x18003ba4c  jb      short loc_18003BA70
0x18003ba4e  or      r14d, 20h
0x18003ba52  mov     esi, r8d
0x18003ba55  mov     [rsp+68h+arg_38], r14d
0x18003ba5d  cmp     [rsp+68h+arg_20], eax
0x18003ba64  jnb     short loc_18003BA8F
0x18003ba66  mov     ebx, 0C0000023h
0x18003ba6b  jmp     loc_18003C27F
0x18003ba70  mov     ebx, 0C000000Dh
0x18003ba75  jmp     loc_18003C27F
0x18003ba7a  mov     r9d, 3EEh
0x18003ba80  mov     ebx, 0C00000BBh
0x18003ba85  mov     ecx, 0C00000BBh
0x18003ba8a  jmp     loc_18003C26C
0x18003ba8f  mov     [r9], eax
0x18003ba92  mov     dword ptr [r9+4], 4D534848h
0x18003ba9a  mov     eax, [r15+8]
0x18003ba9e  mov     [r9+8], eax
0x18003baa2  mov     eax, [r15+0Ch]
0x18003baa6  mov     [r9+0Ch], eax
0x18003baaa  mov     eax, [r15+20h]
0x18003baae  mov     [r9+10h], eax
0x18003bab2  cmp     dword ptr [r15+28h], 0
0x18003bab7  jnz     short loc_18003BAC3
0x18003bab9  test    r14b, 20h
0x18003babd  jnz     short loc_18003BAC3
0x18003babf  xor     eax, eax
0x18003bac1  jmp     short loc_18003BAC5
0x18003bac3  mov     eax, ebx
0x18003bac5  mov     [r9+18h], eax
0x18003bac9  lea     r12, [r9+30h]
0x18003bacd  mov     eax, [r15+34h]
0x18003bad1  mov     rcx, r12; void *
0x18003bad4  mov     [r9+1Ch], eax
0x18003bad8  xor     eax, eax
0x18003bada  test    r8d, r8d
0x18003badd  mov     dword ptr [r9+20h], 0
0x18003bae5  setnz   al
0x18003bae8  xor     edx, edx; Val
0x18003baea  mov     [r9+24h], eax
0x18003baee  mov     al, [r15+30h]
0x18003baf2  mov     [r9+28h], al
0x18003baf6  mov     [r9+2Ch], esi
0x18003bafa  lea     r8d, [rdx+40h]; Size
0x18003bafe  mov     eax, [r15+1Ch]
0x18003bb02  mov     [r9+70h], eax
0x18003bb06  call    memset
0x18003bb0b  mov     dword ptr [rdi+14h], 0
0x18003bb12  mov     eax, [r15+8]
0x18003bb16  add     eax, 0FFFDFFFFh; switch 26 cases
0x18003bb1b  cmp     eax, 19h
0x18003bb1e  ja      def_18003BB35; jumptable 000000018003BB35 default case
0x18003bb24  lea     rcx, cs:180000000h
0x18003bb2b  mov     eax, ds:(jpt_18003BB35 - 180000000h)[rcx+rax*4]
0x18003bb32  add     rax, rcx
0x18003bb35  jmp     rax; switch jump
0x18003bb3b  xor     r8d, r8d; jumptable 000000018003BB35 case 131073
0x18003bb3e  test    esi, esi
0x18003bb40  jz      loc_18003C1EC
0x18003bb46  xor     edx, edx
0x18003bb48  imul    rax, rdx, 70h ; 'p'
0x18003bb4c  add     r8d, ebx
0x18003bb4f  mov     qword ptr [rax+rdi+90h], 0
0x18003bb5b  mov     qword ptr [rax+rdi+98h], 0
0x18003bb67  mov     dword ptr [rax+rdi+80h], 0
0x18003bb72  lea     rax, [rdx+2]
0x18003bb76  movups  xmm0, cs:xmmword_1800AE788
0x18003bb7d  add     rdx, rbx
0x18003bb80  imul    rcx, rax, 70h ; 'p'
0x18003bb84  movdqu  xmmword ptr [rcx+rdi], xmm0
0x18003bb89  cmp     r8d, esi
0x18003bb8c  jb      short loc_18003BB48
0x18003bb8e  jmp     loc_18003C1EC
0x18003bb93  xor     ebx, ebx; jumptable 000000018003BB35 case 131074
0x18003bb95  test    esi, esi
0x18003bb97  jz      loc_18003C1EC
0x18003bb9d  lea     r14, [rdi+80h]
0x18003bba4  mov     ecx, ebx
0x18003bba6  shl     rcx, 7
0x18003bbaa  add     rcx, r14
0x18003bbad  call    SymCryptSha1Init
0x18003bbb2  inc     ebx
0x18003bbb4  cmp     ebx, esi
0x18003bbb6  jb      short loc_18003BBA4
0x18003bbb8  jmp     loc_18003C1E4
0x18003bbbd  xor     ebx, ebx; jumptable 000000018003BB35 case 131075
0x18003bbbf  test    esi, esi
0x18003bbc1  jz      loc_18003C1EC
0x18003bbc7  lea     r14, [rdi+80h]
0x18003bbce  mov     eax, ebx
0x18003bbd0  mov     edx, 70h ; 'p'
0x18003bbd5  imul    rcx, rax, 70h ; 'p'
0x18003bbd9  add     rcx, r14
0x18003bbdc  call    SymCryptWipeAsm
0x18003bbe1  inc     ebx
0x18003bbe3  cmp     ebx, esi
0x18003bbe5  jb      short loc_18003BBCE
0x18003bbe7  jmp     loc_18003C1E4
0x18003bbec  xor     r8d, r8d; jumptable 000000018003BB35 case 131076
0x18003bbef  test    esi, esi
0x18003bbf1  jz      loc_18003C1EC
0x18003bbf7  xor     edx, edx
0x18003bbf9  imul    rax, rdx, 70h ; 'p'
0x18003bbfd  add     r8d, ebx
0x18003bc00  mov     qword ptr [rax+rdi+90h], 0
0x18003bc0c  mov     qword ptr [rax+rdi+98h], 0
0x18003bc18  mov     dword ptr [rax+rdi+80h], 0
0x18003bc23  lea     rax, [rdx+2]
0x18003bc27  movups  xmm0, cs:xmmword_1800BB1A0
0x18003bc2e  add     rdx, rbx
0x18003bc31  imul    rcx, rax, 70h ; 'p'
0x18003bc35  movdqu  xmmword ptr [rcx+rdi], xmm0
0x18003bc3a  cmp     r8d, esi
0x18003bc3d  jb      short loc_18003BBF9
0x18003bc3f  jmp     loc_18003C1EC
0x18003bc44  mov     edx, esi; jumptable 000000018003BB35 case 131077
0x18003bc46  lea     rcx, [rdi+80h]
0x18003bc4d  call    SymCryptParallelSha256Init
0x18003bc52  jmp     loc_18003C1EC
0x18003bc57  mov     edx, esi; jumptable 000000018003BB35 case 131078
0x18003bc59  lea     rcx, [rdi+80h]
0x18003bc60  call    SymCryptParallelSha384Init
0x18003bc65  jmp     loc_18003C1EC
0x18003bc6a  mov     edx, esi; jumptable 000000018003BB35 case 131079
0x18003bc6c  lea     rcx, [rdi+80h]
0x18003bc73  call    SymCryptParallelSha512Init
0x18003bc78  jmp     loc_18003C1EC
0x18003bc7d  mov     r9, rbp; jumptable 000000018003BB35 case 131080
0x18003bc80  lea     rcx, [rdi+80h]
0x18003bc87  mov     r8, r13
0x18003bc8a  lea     rdx, SymCryptAesBlockCipher_Fast
0x18003bc91  call    SymCryptGcmExpandKey
0x18003bc96  test    eax, eax
0x18003bc98  jnz     short loc_18003BCB4
0x18003bc9a  lea     eax, [rbp-10h]
0x18003bc9d  cmp     eax, 10h
0x18003bca0  ja      short loc_18003BCB4
0x18003bca2  test    bpl, 7
0x18003bca6  jnz     short loc_18003BCB4
0x18003bca8  mov     dword ptr [rdi+74h], 0
0x18003bcaf  jmp     loc_18003C1EC
0x18003bcb4  mov     ebx, 0C0000206h
0x18003bcb9  mov     r9d, 489h
0x18003bcbf  mov     ecx, 0C0000206h
0x18003bcc4  jmp     loc_18003C26C
0x18003bcc9  lea     r14, [rdi+80h]; jumptable 000000018003BB35 case 131081
0x18003bcd0  mov     r8, rbp
0x18003bcd3  mov     rcx, r14
0x18003bcd6  mov     rdx, r13
0x18003bcd9  call    SymCryptHmacSha1ExpandKey
0x18003bcde  xor     ebx, ebx
0x18003bce0  test    esi, esi
0x18003bce2  jz      loc_18003C1E4
0x18003bce8  lea     r12, [rdi+0D0h]
0x18003bcef  lea     rcx, [rbx+rbx*8]
0x18003bcf3  mov     rdx, r14
0x18003bcf6  shl     rcx, 4
0x18003bcfa  add     rcx, r12
0x18003bcfd  call    SymCryptHmacSha1Init
0x18003bd02  inc     ebx
0x18003bd04  cmp     ebx, esi
0x18003bd06  jb      short loc_18003BCEF
0x18003bd08  lea     r12, [rdi+30h]
0x18003bd0c  jmp     loc_18003C1E4
0x18003bd11  lea     r14, [rdi+80h]; jumptable 000000018003BB35 case 131082
0x18003bd18  mov     r8, rbp
0x18003bd1b  mov     rcx, r14
0x18003bd1e  mov     rdx, r13
0x18003bd21  call    SymCryptHmacMd5ExpandKey
0x18003bd26  xor     ebx, ebx
0x18003bd28  test    esi, esi
0x18003bd2a  jz      loc_18003C1E4
0x18003bd30  lea     r12, [rdi+0B0h]
0x18003bd37  mov     ecx, ebx
0x18003bd39  mov     rdx, r14
0x18003bd3c  shl     rcx, 7
0x18003bd40  add     rcx, r12
0x18003bd43  call    SymCryptHmacMd5Init
0x18003bd48  inc     ebx
0x18003bd4a  cmp     ebx, esi
0x18003bd4c  jb      short loc_18003BD37
0x18003bd4e  jmp     short loc_18003BD08
0x18003bd50  lea     r14, [rdi+80h]; jumptable 000000018003BB35 case 131083
0x18003bd57  mov     r8, rbp
0x18003bd5a  mov     rcx, r14
0x18003bd5d  mov     rdx, r13
0x18003bd60  call    SymCryptHmacSha256ExpandKey
0x18003bd65  xor     ebx, ebx
0x18003bd67  test    esi, esi
0x18003bd69  jz      loc_18003C1E4
0x18003bd6f  lea     r12, [rdi+0D0h]
0x18003bd76  lea     rcx, [rbx+rbx*8]
0x18003bd7a  mov     rdx, r14
0x18003bd7d  shl     rcx, 4
0x18003bd81  add     rcx, r12
0x18003bd84  call    SymCryptHmacSha256Init
0x18003bd89  inc     ebx
0x18003bd8b  cmp     ebx, esi
0x18003bd8d  jb      short loc_18003BD76
0x18003bd8f  jmp     loc_18003BD08
0x18003bd94  lea     r14, [rdi+80h]; jumptable 000000018003BB35 case 131084
0x18003bd9b  mov     r8, rbp
0x18003bd9e  mov     rcx, r14
0x18003bda1  mov     rdx, r13
0x18003bda4  call    SymCryptHmacSha384ExpandKey
0x18003bda9  xor     ebx, ebx
0x18003bdab  test    esi, esi
0x18003bdad  jz      loc_18003C1E4
0x18003bdb3  lea     r12, [rdi+110h]
0x18003bdba  mov     eax, ebx
0x18003bdbc  mov     rdx, r14
0x18003bdbf  imul    rcx, rax, 0F0h
0x18003bdc6  add     rcx, r12
0x18003bdc9  call    SymCryptHmacSha512Init
0x18003bdce  inc     ebx
0x18003bdd0  cmp     ebx, esi
0x18003bdd2  jb      short loc_18003BDBA
0x18003bdd4  jmp     loc_18003BD08
0x18003bdd9  lea     r14, [rdi+80h]; jumptable 000000018003BB35 case 131085
0x18003bde0  mov     r8, rbp
0x18003bde3  mov     rcx, r14
0x18003bde6  mov     rdx, r13
0x18003bde9  call    SymCryptHmacSha512ExpandKey
0x18003bdee  xor     ebx, ebx
0x18003bdf0  test    esi, esi
0x18003bdf2  jz      loc_18003C1E4
0x18003bdf8  lea     r12, [rdi+110h]
0x18003bdff  mov     eax, ebx
0x18003be01  mov     rdx, r14
0x18003be04  imul    rcx, rax, 0F0h
0x18003be0b  add     rcx, r12
0x18003be0e  call    SymCryptHmacSha512Init
0x18003be13  inc     ebx
0x18003be15  cmp     ebx, esi
0x18003be17  jb      short loc_18003BDFF
0x18003be19  jmp     loc_18003BD08
0x18003be1e  lea     rbx, [rdi+80h]; jumptable 000000018003BB35 case 131086
0x18003be25  mov     r8, rbp
0x18003be28  mov     rcx, rbx
0x18003be2b  mov     rdx, r13
  ... truncated ...
```
