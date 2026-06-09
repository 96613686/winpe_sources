# MSCryptCreateMultiHash

- ea: `0x180045a00`
- end: `0x18004624e`
- name: `MSCryptCreateMultiHash`
- size: `2126`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Src, size_t Size, int)`
- caller_count: `6`
- callee_count: `31`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000e940`
- `0x1800459c0`
- `0x1800871c4`
- `0x180087e94`
- `0x18008a398`
- `0x18008ae48`

## callees

- `0x180001630`
- `0x180001880`
- `0x180001ad0`
- `0x180001d30`
- `0x1800020d0`
- `0x18000f764`
- `0x18001155c`
- `0x18001b688`
- `0x1800222e0`
- `0x180023940`
- `0x180024da0`
- `0x180037748`
- `0x180038680`
- `0x18003b42c`
- `0x18003bbc0`
- `0x18003bdb8`
- `0x180045a00`
- `0x180046ef0`
- `0x18004a370`
- `0x18004bfbc`
- `0x1800559b0`
- `0x1800564d0`
- `0x18006ea00`
- `0x180086880`
- `0x180090d50`
- `0x180091340`
- `0x18009aa30`
- `0x18009abd0`
- `0x18009f5a8`
- `0x1800a4380`
- `0x1800a45c0`

## string_xrefs

- `0x180046227`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

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
  unsigned int v8; // ebp
  __int64 *v10; // r12
  __int64 v11; // r9
  _DWORD *v12; // rax
  __int64 v13; // rdx
  unsigned int v14; // r8d
  _DWORD *v15; // r14
  unsigned int v16; // edi
  __int64 v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // edi
  unsigned __int64 v20; // rdx
  int v21; // eax
  void *v22; // r15
  unsigned int v23; // r8d
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  unsigned int i; // ebp
  unsigned int j; // ebp
  unsigned int v29; // r8d
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rbp
  unsigned int k; // ebp
  __int64 v35; // rbp
  unsigned int m; // ebp
  unsigned int n; // ebp
  unsigned int v38; // ecx
  __int64 v39; // rax
  unsigned int ii; // ebp
  unsigned int jj; // ebp
  unsigned int kk; // ebp
  unsigned int mm; // ebp
  unsigned int nn; // ebp
  unsigned int i1; // ebp
  int v46; // eax
  unsigned int i2; // ebp
  unsigned int i3; // ebp

  v8 = a8;
  v10 = a2;
  if ( (a8 & 0xFFFFFFDF) != 0 )
  {
    v11 = 957;
LABEL_110:
    v16 = -1073741811;
    v17 = 3221225485LL;
    goto LABEL_111;
  }
  v12 = (_DWORD *)validateMSCryptHashAlgorithm(a1);
  v15 = v12;
  if ( !v12 )
  {
    v16 = -1073741816;
    v11 = 966;
    v17 = 3221225480LL;
LABEL_111:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v11);
    return v16;
  }
  if ( !v13 || !a4 )
  {
    v11 = 974;
    goto LABEL_110;
  }
  if ( !v12[8] && !v12[13] && (Src || (_DWORD)Size) )
  {
    v11 = 986;
    goto LABEL_110;
  }
  v18 = v12[4];
  v19 = 1;
  if ( v14 )
  {
    if ( !v15[11] || v15[13] || v15[2] == 131080 )
    {
      v11 = 1006;
LABEL_23:
      v16 = -1073741637;
      v17 = 3221225659LL;
      goto LABEL_111;
    }
    v20 = (v14 - 1) * (unsigned __int64)(unsigned int)v15[6];
    if ( v20 > 0xFFFFFFFF )
      return (unsigned int)-1073741811;
    v18 = v20 + v15[5];
    if ( v18 < (unsigned int)v20 )
      return (unsigned int)-1073741811;
    v8 = a8 | 0x20;
    v19 = v14;
    a8 |= 0x20u;
  }
  if ( a5 >= v18 )
  {
    *(_DWORD *)a4 = v18;
    *(_DWORD *)(a4 + 4) = 1297303624;
    *(_DWORD *)(a4 + 8) = v15[2];
    *(_DWORD *)(a4 + 12) = v15[3];
    *(_DWORD *)(a4 + 16) = v15[8];
    if ( v15[10] || (v21 = 0, (v8 & 0x20) != 0) )
      v21 = 1;
    *(_DWORD *)(a4 + 24) = v21;
    v22 = (void *)(a4 + 48);
    *(_DWORD *)(a4 + 28) = v15[13];
    *(_DWORD *)(a4 + 32) = 0;
    *(_DWORD *)(a4 + 36) = v14 != 0;
    *(_BYTE *)(a4 + 40) = *((_BYTE *)v15 + 48);
    *(_DWORD *)(a4 + 44) = v19;
    *(_DWORD *)(a4 + 112) = v15[7];
    memset((void *)(a4 + 48), 0, 0x40u);
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
          *(_OWORD *)(112 * v26 + a4) = xmmword_1800B5B88;
        }
        while ( v23 < v19 );
        goto LABEL_100;
      case 0x20002:
        for ( i = 0; i < v19; ++i )
          SymCryptSha1Init(a4 + 128 + ((unsigned __int64)i << 7));
        goto LABEL_98;
      case 0x20003:
        for ( j = 0; j < v19; ++j )
          SymCryptWipeAsm(a4 + 128 + 112LL * j, 112);
        goto LABEL_98;
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
          *(_OWORD *)(112 * v32 + a4) = xmmword_1800C3D30;
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
        v11 = 1161;
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
        goto LABEL_50;
      case 0x2000A:
        SymCryptHmacMd5ExpandKey(a4 + 128, Src, (unsigned int)Size);
        for ( k = 0; k < v19; ++k )
          SymCryptHmacMd5Init(a4 + 176 + ((unsigned __int64)k << 7), a4 + 128);
        goto LABEL_50;
      case 0x2000B:
        SymCryptHmacSha256ExpandKey(a4 + 128, Src, (unsigned int)Size);
        v35 = 0;
        do
        {
          SymCryptHmacSha256Init(a4 + 208 + 144 * v35, a4 + 128);
          v35 = (unsigned int)(v35 + 1);
        }
        while ( (unsigned int)v35 < v19 );
        goto LABEL_50;
      case 0x2000C:
        SymCryptHmacSha384ExpandKey(a4 + 128, Src, (unsigned int)Size);
        for ( m = 0; m < v19; ++m )
          SymCryptHmacSha512Init(a4 + 272 + 240LL * m, a4 + 128);
        goto LABEL_50;
      case 0x2000D:
        SymCryptHmacSha512ExpandKey(a4 + 128, Src, (unsigned int)Size);
        for ( n = 0; n < v19; ++n )
          SymCryptHmacSha512Init(a4 + 272 + 240LL * n, a4 + 128);
        goto LABEL_50;
      case 0x2000E:
        if ( (unsigned int)SymCryptAesCmacExpandKey(a4 + 128, Src, (unsigned int)Size) )
        {
          v11 = 1261;
          goto LABEL_110;
        }
        v38 = 0;
        do
        {
          v39 = v38++;
          v39 <<= 6;
          *(_QWORD *)(a4 + v39 + 704) = 0;
          *(_QWORD *)(a4 + v39 + 672) = 0;
          *(_QWORD *)(a4 + v39 + 680) = 0;
          *(_QWORD *)(a4 + v39 + 712) = a4 + 128;
        }
        while ( v38 < v19 );
LABEL_99:
        v8 = a8;
        goto LABEL_100;
      case 0x2000F:
        for ( ii = 0; ii < v19; ++ii )
          SymCryptSha3_256Init((void *)(a4 + 128 + 240LL * ii));
        goto LABEL_98;
      case 0x20010:
        for ( jj = 0; jj < v19; ++jj )
          SymCryptSha3_384Init((void *)(a4 + 128 + 240LL * jj));
        goto LABEL_98;
      case 0x20011:
        for ( kk = 0; kk < v19; ++kk )
          SymCryptSha3_512Init((void *)(a4 + 128 + 240LL * kk));
        goto LABEL_98;
      case 0x20012:
        SymCryptHmacExpandKey(&SymCryptSha3_256Algorithm_default, a4 + 128, Src, (unsigned int)Size);
        for ( mm = 0; mm < v19; ++mm )
          SymCryptHmacInit(a4 + 640 + 272LL * mm, a4 + 128);
        goto LABEL_50;
      case 0x20013:
        SymCryptHmacExpandKey(&SymCryptSha3_384Algorithm_default, a4 + 128, Src, (unsigned int)Size);
        for ( nn = 0; nn < v19; ++nn )
          SymCryptHmacInit(a4 + 640 + 272LL * nn, a4 + 128);
        goto LABEL_50;
      case 0x20014:
        SymCryptHmacExpandKey(&SymCryptSha3_512Algorithm_default, a4 + 128, Src, (unsigned int)Size);
        for ( i1 = 0; i1 < v19; ++i1 )
          SymCryptHmacInit(a4 + 640 + 272LL * i1, a4 + 128);
LABEL_50:
        v10 = a2;
        goto LABEL_98;
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
        v46 = MSCryptCustomBufferUpdate(a4 + 368, Src, (unsigned int)Size);
        v16 = v46;
        if ( v46 >= 0 )
          goto LABEL_92;
        v11 = 1395;
        goto LABEL_89;
      case 0x20018:
        *(_QWORD *)(a4 + 432) = 0;
        *(_DWORD *)(a4 + 440) = 0;
        *(_QWORD *)(a4 + 512) = 0;
        *(_DWORD *)(a4 + 520) = 0;
        v46 = MSCryptCustomBufferUpdate(a4 + 368, Src, (unsigned int)Size);
        v16 = v46;
        if ( v46 < 0 )
        {
          v11 = 1416;
LABEL_89:
          v17 = (unsigned int)v46;
          goto LABEL_111;
        }
LABEL_92:
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
            v46 = MSCryptHashDataInternal(a4, Src);
            v16 = v46;
            if ( v46 < 0 )
            {
              v11 = 1474;
              goto LABEL_89;
            }
            v46 = MSCryptHashResultInternal(a4, (__int64)v22, *(_DWORD *)(a4 + 12), v8);
            v16 = v46;
            if ( v46 < 0 )
            {
              v11 = 1483;
              goto LABEL_89;
            }
          }
        }
        *v10 = a4;
        return 0;
      case 0x20019:
        for ( i2 = 0; i2 < v19; ++i2 )
          SymCryptShake128Init((void *)(a4 + 128 + 240LL * i2));
        goto LABEL_98;
      case 0x2001A:
        for ( i3 = 0; i3 < v19; ++i3 )
          SymCryptShake256Init((void *)(a4 + 128 + 240LL * i3));
LABEL_98:
        v22 = (void *)(a4 + 48);
        goto LABEL_99;
      default:
        v11 = 1453;
        goto LABEL_23;
    }
  }
  return (unsigned int)-1073741789;
}

```

## disassembly

```asm
0x180045a00  mov     [rsp+arg_8], rdx
0x180045a05  push    rbx
0x180045a06  push    rbp
0x180045a07  push    rsi
0x180045a08  push    rdi
0x180045a09  push    r12
0x180045a0b  push    r13
0x180045a0d  push    r14
0x180045a0f  push    r15
0x180045a11  sub     rsp, 28h
0x180045a15  mov     ebp, [rsp+68h+arg_38]
0x180045a1c  mov     rbx, r9
0x180045a1f  mov     r12, rdx
0x180045a22  test    ebp, 0FFFFFFDFh
0x180045a28  jz      short loc_180045A35
0x180045a2a  mov     r9d, 3BDh
0x180045a30  jmp     loc_18004621D
0x180045a35  call    validateMSCryptHashAlgorithm
0x180045a3a  xor     r9d, r9d
0x180045a3d  mov     r14, rax
0x180045a40  test    rax, rax
0x180045a43  jnz     short loc_180045A5A
0x180045a45  mov     edi, 0C0000008h
0x180045a4a  mov     r9d, 3C6h
0x180045a50  mov     ecx, 0C0000008h
0x180045a55  jmp     loc_180046227
0x180045a5a  test    rdx, rdx
0x180045a5d  jz      loc_180046217
0x180045a63  test    rbx, rbx
0x180045a66  jz      loc_180046217
0x180045a6c  mov     esi, dword ptr [rsp+68h+Size]
0x180045a73  mov     r13, [rsp+68h+Src]
0x180045a7b  cmp     [rax+20h], r9d
0x180045a7f  jnz     short loc_180045A9B
0x180045a81  cmp     [rax+34h], r9d
0x180045a85  jnz     short loc_180045A9B
0x180045a87  test    r13, r13
0x180045a8a  jnz     short loc_180045A90
0x180045a8c  test    esi, esi
0x180045a8e  jz      short loc_180045A9B
0x180045a90  mov     r9d, 3DAh
0x180045a96  jmp     loc_18004621D
0x180045a9b  mov     eax, [rax+10h]
0x180045a9e  mov     edi, 1
0x180045aa3  test    r8d, r8d
0x180045aa6  jz      short loc_180045AEB
0x180045aa8  cmp     [r14+2Ch], r9d
0x180045aac  jz      short loc_180045B08
0x180045aae  cmp     [r14+34h], r9d
0x180045ab2  jnz     short loc_180045B08
0x180045ab4  cmp     dword ptr [r14+8], 20008h
0x180045abc  jz      short loc_180045B08
0x180045abe  mov     edx, [r14+18h]
0x180045ac2  lea     ecx, [r8-1]
0x180045ac6  imul    rdx, rcx
0x180045aca  mov     eax, 0FFFFFFFFh
0x180045acf  cmp     rdx, rax
0x180045ad2  ja      short loc_180045AFE
0x180045ad4  mov     eax, [r14+14h]
0x180045ad8  add     eax, edx
0x180045ada  cmp     eax, edx
0x180045adc  jb      short loc_180045AFE
0x180045ade  or      ebp, 20h
0x180045ae1  mov     edi, r8d
0x180045ae4  mov     [rsp+68h+arg_38], ebp
0x180045aeb  cmp     [rsp+68h+arg_20], eax
0x180045af2  jnb     short loc_180045B1D
0x180045af4  mov     edi, 0C0000023h
0x180045af9  jmp     loc_18004623A
0x180045afe  mov     edi, 0C000000Dh
0x180045b03  jmp     loc_18004623A
0x180045b08  mov     r9d, 3EEh
0x180045b0e  mov     edi, 0C00000BBh
0x180045b13  mov     ecx, 0C00000BBh
0x180045b18  jmp     loc_180046227
0x180045b1d  mov     [rbx], eax
0x180045b1f  mov     dword ptr [rbx+4], 4D534848h
0x180045b26  mov     eax, [r14+8]
0x180045b2a  mov     [rbx+8], eax
0x180045b2d  mov     eax, [r14+0Ch]
0x180045b31  mov     [rbx+0Ch], eax
0x180045b34  mov     eax, [r14+20h]
0x180045b38  mov     [rbx+10h], eax
0x180045b3b  cmp     [r14+28h], r9d
0x180045b3f  jnz     short loc_180045B4A
0x180045b41  mov     eax, r9d
0x180045b44  test    bpl, 20h
0x180045b48  jz      short loc_180045B4F
0x180045b4a  mov     eax, 1
0x180045b4f  mov     [rbx+18h], eax
0x180045b52  lea     r15, [rbx+30h]
0x180045b56  mov     eax, [r14+34h]
0x180045b5a  test    r8d, r8d
0x180045b5d  mov     [rbx+1Ch], eax
0x180045b60  mov     rcx, r15; void *
0x180045b63  mov     eax, r9d
0x180045b66  mov     [rbx+20h], r9d
0x180045b6a  setnz   al
0x180045b6d  xor     edx, edx; Val
0x180045b6f  mov     [rbx+24h], eax
0x180045b72  mov     al, [r14+30h]
0x180045b76  mov     [rbx+28h], al
0x180045b79  mov     [rbx+2Ch], edi
0x180045b7c  lea     r8d, [rdx+40h]; Size
0x180045b80  mov     eax, [r14+1Ch]
0x180045b84  mov     [rbx+70h], eax
0x180045b87  call    memset
0x180045b8c  mov     dword ptr [rbx+14h], 0
0x180045b93  mov     eax, [r14+8]
0x180045b97  add     eax, 0FFFDFFFFh; switch 26 cases
0x180045b9c  cmp     eax, 19h
0x180045b9f  ja      def_180045BB6; jumptable 0000000180045BB6 default case
0x180045ba5  lea     rcx, cs:180000000h
0x180045bac  mov     eax, ds:(jpt_180045BB6 - 180000000h)[rcx+rax*4]
0x180045bb3  add     rax, rcx
0x180045bb6  jmp     rax; switch jump
0x180045bbc  xor     r8d, r8d; jumptable 0000000180045BB6 case 131073
0x180045bbf  test    edi, edi
0x180045bc1  jz      loc_1800461AB
0x180045bc7  xor     edx, edx
0x180045bc9  imul    rax, rdx, 70h ; 'p'
0x180045bcd  inc     r8d
0x180045bd0  mov     qword ptr [rax+rbx+90h], 0
0x180045bdc  mov     qword ptr [rax+rbx+98h], 0
0x180045be8  mov     dword ptr [rax+rbx+80h], 0
0x180045bf3  lea     rax, [rdx+2]
0x180045bf7  movups  xmm0, cs:xmmword_1800B5B88
0x180045bfe  inc     rdx
0x180045c01  imul    rcx, rax, 70h ; 'p'
0x180045c05  movdqu  xmmword ptr [rcx+rbx], xmm0
0x180045c0a  cmp     r8d, edi
0x180045c0d  jb      short loc_180045BC9
0x180045c0f  jmp     loc_1800461AB
0x180045c14  xor     ebp, ebp; jumptable 0000000180045BB6 case 131074
0x180045c16  test    edi, edi
0x180045c18  jz      loc_1800461A4
0x180045c1e  lea     r15, [rbx+80h]
0x180045c25  mov     ecx, ebp
0x180045c27  shl     rcx, 7
0x180045c2b  add     rcx, r15
0x180045c2e  call    SymCryptSha1Init
0x180045c33  inc     ebp
0x180045c35  cmp     ebp, edi
0x180045c37  jb      short loc_180045C25
0x180045c39  jmp     loc_1800461A0
0x180045c3e  xor     ebp, ebp; jumptable 0000000180045BB6 case 131075
0x180045c40  test    edi, edi
0x180045c42  jz      loc_1800461A4
0x180045c48  lea     r15, [rbx+80h]
0x180045c4f  mov     eax, ebp
0x180045c51  mov     edx, 70h ; 'p'
0x180045c56  imul    rcx, rax, 70h ; 'p'
0x180045c5a  add     rcx, r15
0x180045c5d  call    SymCryptWipeAsm
0x180045c62  inc     ebp
0x180045c64  cmp     ebp, edi
0x180045c66  jb      short loc_180045C4F
0x180045c68  jmp     loc_1800461A0
0x180045c6d  xor     r8d, r8d; jumptable 0000000180045BB6 case 131076
0x180045c70  test    edi, edi
0x180045c72  jz      loc_1800461AB
0x180045c78  xor     edx, edx
0x180045c7a  imul    rax, rdx, 70h ; 'p'
0x180045c7e  inc     r8d
0x180045c81  mov     qword ptr [rax+rbx+90h], 0
0x180045c8d  mov     qword ptr [rax+rbx+98h], 0
0x180045c99  mov     dword ptr [rax+rbx+80h], 0
0x180045ca4  lea     rax, [rdx+2]
0x180045ca8  movups  xmm0, cs:xmmword_1800C3D30
0x180045caf  inc     rdx
0x180045cb2  imul    rcx, rax, 70h ; 'p'
0x180045cb6  movdqu  xmmword ptr [rcx+rbx], xmm0
0x180045cbb  cmp     r8d, edi
0x180045cbe  jb      short loc_180045C7A
0x180045cc0  jmp     loc_1800461AB
0x180045cc5  mov     edx, edi; jumptable 0000000180045BB6 case 131077
0x180045cc7  lea     rcx, [rbx+80h]
0x180045cce  call    SymCryptParallelSha256Init
0x180045cd3  jmp     loc_1800461AB
0x180045cd8  mov     edx, edi; jumptable 0000000180045BB6 case 131078
0x180045cda  lea     rcx, [rbx+80h]
0x180045ce1  call    SymCryptParallelSha384Init
0x180045ce6  jmp     loc_1800461AB
0x180045ceb  mov     edx, edi; jumptable 0000000180045BB6 case 131079
0x180045ced  lea     rcx, [rbx+80h]
0x180045cf4  call    SymCryptParallelSha512Init
0x180045cf9  jmp     loc_1800461AB
0x180045cfe  mov     r9, rsi; jumptable 0000000180045BB6 case 131080
0x180045d01  lea     rcx, [rbx+80h]
0x180045d08  mov     r8, r13
0x180045d0b  lea     rdx, SymCryptAesBlockCipher_Fast
0x180045d12  call    SymCryptGcmExpandKey
0x180045d17  test    eax, eax
0x180045d19  jnz     short loc_180045D35
0x180045d1b  lea     eax, [rsi-10h]
0x180045d1e  cmp     eax, 10h
0x180045d21  ja      short loc_180045D35
0x180045d23  test    sil, 7
0x180045d27  jnz     short loc_180045D35
0x180045d29  mov     dword ptr [rbx+74h], 0
0x180045d30  jmp     loc_1800461AB
0x180045d35  mov     edi, 0C0000206h
0x180045d3a  mov     r9d, 489h
0x180045d40  mov     ecx, 0C0000206h
0x180045d45  jmp     loc_180046227
0x180045d4a  lea     r15, [rbx+80h]; jumptable 0000000180045BB6 case 131081
0x180045d51  mov     r8, rsi
0x180045d54  mov     rcx, r15
0x180045d57  mov     rdx, r13
0x180045d5a  call    SymCryptHmacSha1ExpandKey
0x180045d5f  xor     ebp, ebp
0x180045d61  test    edi, edi
0x180045d63  jz      loc_1800461A0
0x180045d69  lea     r12, [rbx+0D0h]
0x180045d70  lea     rcx, ds:0[rbp*8]
0x180045d78  mov     rdx, r15
0x180045d7b  add     rcx, rbp
0x180045d7e  shl     rcx, 4
0x180045d82  add     rcx, r12
0x180045d85  call    SymCryptHmacSha1Init
0x180045d8a  inc     ebp
0x180045d8c  cmp     ebp, edi
0x180045d8e  jb      short loc_180045D70
0x180045d90  mov     r12, [rsp+68h+arg_8]
0x180045d95  jmp     loc_1800461A0
0x180045d9a  lea     r15, [rbx+80h]; jumptable 0000000180045BB6 case 131082
0x180045da1  mov     r8, rsi
0x180045da4  mov     rcx, r15
0x180045da7  mov     rdx, r13
0x180045daa  call    SymCryptHmacMd5ExpandKey
0x180045daf  xor     ebp, ebp
0x180045db1  test    edi, edi
0x180045db3  jz      loc_1800461A0
0x180045db9  lea     r12, [rbx+0B0h]
0x180045dc0  mov     ecx, ebp
0x180045dc2  mov     rdx, r15
0x180045dc5  shl     rcx, 7
0x180045dc9  add     rcx, r12
0x180045dcc  call    SymCryptHmacMd5Init
0x180045dd1  inc     ebp
0x180045dd3  cmp     ebp, edi
0x180045dd5  jb      short loc_180045DC0
0x180045dd7  jmp     short loc_180045D90
0x180045dd9  lea     r15, [rbx+80h]; jumptable 0000000180045BB6 case 131083
0x180045de0  mov     r8, rsi
0x180045de3  mov     rcx, r15
0x180045de6  mov     rdx, r13
0x180045de9  call    SymCryptHmacSha256ExpandKey
0x180045dee  xor     ebp, ebp
0x180045df0  test    edi, edi
0x180045df2  jz      loc_1800461A0
0x180045df8  lea     r12, [rbx+0D0h]
0x180045dff  lea     rcx, ds:0[rbp*8]
0x180045e07  mov     rdx, r15
0x180045e0a  add     rcx, rbp
0x180045e0d  shl     rcx, 4
0x180045e11  add     rcx, r12
0x180045e14  call    SymCryptHmacSha256Init
0x180045e19  inc     ebp
0x180045e1b  cmp     ebp, edi
0x180045e1d  jb      short loc_180045DFF
0x180045e1f  jmp     loc_180045D90
0x180045e24  lea     r15, [rbx+80h]; jumptable 0000000180045BB6 case 131084
0x180045e2b  mov     r8, rsi
0x180045e2e  mov     rcx, r15
0x180045e31  mov     rdx, r13
0x180045e34  call    SymCryptHmacSha384ExpandKey
0x180045e39  xor     ebp, ebp
0x180045e3b  test    edi, edi
0x180045e3d  jz      loc_1800461A0
0x180045e43  lea     r12, [rbx+110h]
0x180045e4a  mov     eax, ebp
0x180045e4c  mov     rdx, r15
0x180045e4f  imul    rcx, rax, 0F0h
0x180045e56  add     rcx, r12
0x180045e59  call    SymCryptHmacSha512Init
0x180045e5e  inc     ebp
0x180045e60  cmp     ebp, edi
0x180045e62  jb      short loc_180045E4A
0x180045e64  jmp     loc_180045D90
0x180045e69  lea     r15, [rbx+80h]; jumptable 0000000180045BB6 case 131085
0x180045e70  mov     r8, rsi
0x180045e73  mov     rcx, r15
0x180045e76  mov     rdx, r13
0x180045e79  call    SymCryptHmacSha512ExpandKey
0x180045e7e  xor     ebp, ebp
0x180045e80  test    edi, edi
0x180045e82  jz      loc_1800461A0
0x180045e88  lea     r12, [rbx+110h]
0x180045e8f  mov     eax, ebp
0x180045e91  mov     rdx, r15
0x180045e94  imul    rcx, rax, 0F0h
0x180045e9b  add     rcx, r12
0x180045e9e  call    SymCryptHmacSha512Init
0x180045ea3  inc     ebp
0x180045ea5  cmp     ebp, edi
0x180045ea7  jb      short loc_180045E8F
0x180045ea9  jmp     loc_180045D90
0x180045eae  lea     rbp, [rbx+80h]; jumptable 0000000180045BB6 case 131086
0x180045eb5  mov     r8, rsi
  ... truncated ...
```
