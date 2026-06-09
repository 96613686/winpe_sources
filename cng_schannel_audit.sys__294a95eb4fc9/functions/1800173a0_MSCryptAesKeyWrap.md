# MSCryptAesKeyWrap

- ea: `0x1800173a0`
- end: `0x1800177e9`
- name: `MSCryptAesKeyWrap`
- size: `1097`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180016d10`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x18000abf0`
- `0x1800173a0`
- `0x1800177f0`
- `0x180017adc`
- `0x18009d820`
- `0x18009da40`

## string_xrefs

- `0x1800175e6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x1800176e8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180017772`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x18001779a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x1800177c7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`

## pseudocode

```c
__int64 __fastcall MSCryptAesKeyWrap(__int64 a1, __int64 a2, void *a3, unsigned int a4, unsigned int *a5)
{
  __int64 v7; // r12
  int Property; // ebx
  __int64 v9; // r15
  __int64 v10; // rdx
  unsigned int v11; // edi
  unsigned int v12; // esi
  void *v13; // r13
  char *p_Src; // rsi
  int v15; // edx
  unsigned int v16; // r15d
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rax
  unsigned int v19; // edi
  unsigned int i; // edx
  int v21; // eax
  __int64 v22; // rcx
  __int128 *v23; // rax
  unsigned __int64 *v24; // rax
  size_t *p_Size; // rax
  size_t v27; // r8
  void *v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rax
  int v31; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v32; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A0h]
  void *v35; // [rsp+68h] [rbp-98h]
  __int64 v36; // [rsp+70h] [rbp-90h]
  __int64 v37; // [rsp+78h] [rbp-88h]
  unsigned __int64 v38; // [rsp+80h] [rbp-80h] BYREF
  __int64 v39; // [rsp+88h] [rbp-78h]
  size_t Size; // [rsp+90h] [rbp-70h] BYREF
  __int128 v41; // [rsp+98h] [rbp-68h] BYREF
  char Src; // [rsp+B0h] [rbp-50h] BYREF

  v34 = a1;
  v35 = a3;
  v36 = a2;
  LODWORD(v33) = 0;
  v32 = 0;
  v31 = 0;
  v7 = 8;
  Property = MSCryptGetProperty(a2, L"BlockLength", &v33, 4, &v31, 0);
  v9 = 16;
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)WPP_GLOBAL_Control,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        (unsigned int)"Status",
        Property,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        173);
    goto LABEL_22;
  }
  if ( v31 != 4 || (_DWORD)v33 != 16 )
  {
    Property = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c", 181);
    goto LABEL_22;
  }
  Property = MSCryptGetProperty(a1, L"KeyLength", &v32, 4, &v31, 0);
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v10,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        (unsigned int)"Status",
        Property,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        195);
    goto LABEL_22;
  }
  v11 = v32 >> 3;
  if ( v31 != 4 || (v11 & 7) != 0 )
  {
    Property = -1073741816;
LABEL_22:
    *a5 = 0;
    goto LABEL_26;
  }
  v12 = v11 + 8;
  if ( !v35 )
  {
    Property = 0;
    goto LABEL_34;
  }
  if ( a4 < v12 )
  {
    Property = -1073741789;
    goto LABEL_34;
  }
  Size = v12;
  if ( v12 > 0x48 )
  {
    v30 = MSCryptAlloc(v12, v10);
    v13 = (void *)v30;
    if ( v30 )
    {
      p_Src = (char *)v30;
      goto LABEL_11;
    }
    Property = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c", 243);
LABEL_34:
    *a5 = v12;
    goto LABEL_26;
  }
  v13 = 0;
  p_Src = &Src;
LABEL_11:
  Property = MSCryptGetKeyData(v34, p_Src + 8, v11);
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v15,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        (unsigned int)"Status",
        Property,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        5);
    v16 = v11;
  }
  else
  {
    v16 = v11;
    v17 = (unsigned __int64)v11 >> 3;
    v18 = 0xA6A6A6A6A6A6A6A6uLL;
    v33 = v17;
    v19 = 0;
LABEL_13:
    if ( v19 >= 6 )
    {
      v27 = Size;
      v28 = v35;
      *(_QWORD *)p_Src = v18;
      memmove(v28, p_Src, v27);
      Property = 0;
    }
    else
    {
      for ( i = 0; ; i = v32 + 1 )
      {
        v32 = i;
        v34 = i;
        if ( i >= v17 )
        {
          ++v19;
          goto LABEL_13;
        }
        v38 = v18;
        v37 = 8 * i;
        v39 = *(_QWORD *)&p_Src[v37 + 8];
        v41 = 0;
        v21 = MSCryptEncrypt(
                v36,
                (unsigned __int64)&v38,
                0x10u,
                0,
                (__int64 *)&v41,
                16,
                (unsigned __int64)&v38,
                0x10u,
                &v31,
                0);
        Property = v21;
        if ( v21 < 0 )
          break;
        v18 = v38 ^ _byteswap_uint64(v34 + 1 + v33 * v19);
        *(_QWORD *)&p_Src[v37 + 8] = v39;
        v17 = v33;
      }
      DebugTraceError(
        (unsigned int)v21,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        296);
    }
    v11 = v16;
  }
  *a5 = v11 + 8;
  if ( p_Src )
  {
    v29 = v16 + 8;
    if ( v16 != -8 )
    {
      do
      {
        *p_Src++ = 0;
        --v29;
      }
      while ( v29 );
    }
  }
  if ( v13 )
    MSCryptFree(v13);
  v9 = 16;
LABEL_26:
  v22 = 16;
  v23 = &v41;
  do
  {
    *(_BYTE *)v23 = 0;
    v23 = (__int128 *)((char *)v23 + 1);
    --v22;
  }
  while ( v22 );
  v24 = &v38;
  do
  {
    *(_BYTE *)v24 = 0;
    v24 = (unsigned __int64 *)((char *)v24 + 1);
    --v9;
  }
  while ( v9 );
  p_Size = &Size;
  do
  {
    *(_BYTE *)p_Size = 0;
    p_Size = (size_t *)((char *)p_Size + 1);
    --v7;
  }
  while ( v7 );
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1800173a0  mov     [rsp-8+arg_18], rbx
0x1800173a5  push    rbp
0x1800173a6  push    rsi
0x1800173a7  push    rdi
0x1800173a8  push    r12
0x1800173aa  push    r13
0x1800173ac  push    r14
0x1800173ae  push    r15
0x1800173b0  lea     rbp, [rsp-10h]
0x1800173b5  sub     rsp, 110h
0x1800173bc  mov     rax, cs:__security_cookie
0x1800173c3  xor     rax, rsp
0x1800173c6  mov     [rbp+40h+var_40], rax
0x1800173ca  mov     r14, [rbp+40h+arg_20]
0x1800173ce  xor     esi, esi
0x1800173d0  mov     rdi, rcx
0x1800173d3  mov     [rsp+140h+var_E0], rcx
0x1800173d8  mov     rax, rdx
0x1800173db  mov     [rsp+140h+var_D8], r8
0x1800173e0  lea     rcx, [rsp+140h+var_F0]
0x1800173e5  mov     [rsp+140h+var_D0], rdx
0x1800173ea  mov     r13d, r9d
0x1800173ed  mov     dword ptr [rsp+140h+var_118], esi
0x1800173f1  mov     [rsp+140h+var_120], rcx
0x1800173f6  lea     r9d, [rsi+4]
0x1800173fa  lea     r8, [rsp+140h+var_E8]
0x1800173ff  mov     dword ptr [rsp+140h+var_E8], esi
0x180017403  lea     rdx, aBlocklength; "BlockLength"
0x18001740a  mov     [rsp+140h+var_EC], esi
0x18001740e  mov     rcx, rax
0x180017411  mov     [rsp+140h+var_F0], esi
0x180017415  call    MSCryptGetProperty
0x18001741a  lea     r12d, [rsi+8]
0x18001741e  mov     ebx, eax
0x180017420  lea     r15d, [rsi+10h]
0x180017424  test    eax, eax
0x180017426  js      loc_1800175BF
0x18001742c  cmp     [rsp+140h+var_F0], 4
0x180017431  jnz     loc_1800177C1
0x180017437  cmp     dword ptr [rsp+140h+var_E8], r15d
0x18001743c  jnz     loc_1800177C1
0x180017442  lea     rax, [rsp+140h+var_F0]
0x180017447  mov     dword ptr [rsp+140h+var_118], esi
0x18001744b  lea     r9d, [rsi+4]
0x18001744f  mov     [rsp+140h+var_120], rax
0x180017454  lea     r8, [rsp+140h+var_EC]
0x180017459  mov     rcx, rdi
0x18001745c  lea     rdx, aKeylength; "KeyLength"
0x180017463  call    MSCryptGetProperty
0x180017468  mov     ebx, eax
0x18001746a  test    eax, eax
0x18001746c  js      loc_180017711
0x180017472  mov     edi, [rsp+140h+var_EC]
0x180017476  shr     edi, 3
0x180017479  cmp     [rsp+140h+var_F0], 4
0x18001747e  jnz     loc_180017744
0x180017484  test    dil, 7
0x180017488  jnz     loc_180017744
0x18001748e  cmp     [rsp+140h+var_D8], 0
0x180017494  lea     esi, [rdi+8]
0x180017497  jz      loc_180017675
0x18001749d  cmp     r13d, esi
0x1800174a0  jb      loc_18001774E
0x1800174a6  mov     eax, esi
0x1800174a8  mov     [rbp+40h+Size], rax
0x1800174ac  cmp     esi, 48h ; 'H'
0x1800174af  ja      loc_180017758
0x1800174b5  xor     r13d, r13d
0x1800174b8  lea     rsi, [rbp+40h+Src]
0x1800174bc  mov     rcx, [rsp+140h+var_E0]
0x1800174c1  lea     rdx, [rsi+8]
0x1800174c5  mov     r8d, edi
0x1800174c8  call    MSCryptGetKeyData
0x1800174cd  mov     ebx, eax
0x1800174cf  test    eax, eax
0x1800174d1  js      loc_1800176CA
0x1800174d7  mov     ecx, edi
0x1800174d9  mov     r15d, edi
0x1800174dc  shr     rcx, 3
0x1800174e0  mov     rax, 0A6A6A6A6A6A6A6A6h
0x1800174ea  mov     [rsp+140h+var_E8], rcx
0x1800174ef  xor     edi, edi
0x1800174f1  cmp     edi, 6
0x1800174f4  jnb     loc_18001767E
0x1800174fa  xor     edx, edx
0x1800174fc  mov     r8d, edx
0x1800174ff  mov     [rsp+140h+var_EC], edx
0x180017503  mov     [rsp+140h+var_E0], r8
0x180017508  cmp     r8, rcx
0x18001750b  jnb     loc_1800175B8
0x180017511  mov     [rbp+40h+var_C0], rax
0x180017515  lea     rcx, [rbp+40h+var_C0]
0x180017519  mov     [rsp+140h+var_F8], 0
0x180017521  lea     eax, ds:0[rdx*8]
0x180017528  mov     [rsp+140h+var_C8], rax
0x18001752d  lea     rdx, [rbp+40h+var_C0]
0x180017531  mov     rax, [rax+rsi+8]
0x180017536  xorps   xmm0, xmm0
0x180017539  mov     [rbp+40h+var_B8], rax
0x18001753d  xor     r9d, r9d
0x180017540  lea     rax, [rsp+140h+var_F0]
0x180017545  mov     [rsp+140h+var_100], rax
0x18001754a  mov     eax, 10h
0x18001754f  mov     [rsp+140h+var_108], eax
0x180017553  mov     r8d, eax
0x180017556  mov     [rsp+140h+var_110], rcx
0x18001755b  lea     rcx, [rbp+40h+var_A8]
0x18001755f  mov     dword ptr [rsp+140h+var_118], eax
0x180017563  mov     [rsp+140h+var_120], rcx
0x180017568  mov     rcx, [rsp+140h+var_D0]
0x18001756d  movups  [rbp+40h+var_A8], xmm0
0x180017571  call    MSCryptEncrypt
0x180017576  mov     ebx, eax
0x180017578  test    eax, eax
0x18001757a  js      loc_180017794
0x180017580  mov     rdx, [rsp+140h+var_C8]
0x180017585  mov     rcx, [rsp+140h+var_E0]
0x18001758a  inc     rcx
0x18001758d  mov     eax, edi
0x18001758f  imul    rax, [rsp+140h+var_E8]
0x180017595  add     rax, rcx
0x180017598  mov     rcx, [rbp+40h+var_B8]
0x18001759c  bswap   rax
0x18001759f  xor     rax, [rbp+40h+var_C0]
0x1800175a3  mov     [rdx+rsi+8], rcx
0x1800175a8  mov     edx, [rsp+140h+var_EC]
0x1800175ac  mov     rcx, [rsp+140h+var_E8]
0x1800175b1  inc     edx
0x1800175b3  jmp     loc_1800174FC
0x1800175b8  inc     edi
0x1800175ba  jmp     loc_1800174F1
0x1800175bf  mov     rdx, cs:WPP_GLOBAL_Control
0x1800175c6  lea     rax, WPP_GLOBAL_Control
0x1800175cd  cmp     rdx, rax
0x1800175d0  jz      short loc_180017602
0x1800175d2  mov     ecx, [rdx+2Ch]
0x1800175d5  test    cl, 1
0x1800175d8  jz      short loc_180017602
0x1800175da  mov     rcx, [rdx+18h]
0x1800175de  mov     dword ptr [rsp+140h+var_110], 0ADh
0x1800175e6  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800175ed  mov     [rsp+140h+var_118], r8
0x1800175f2  lea     r9, aStatus; "Status"
0x1800175f9  mov     dword ptr [rsp+140h+var_120], ebx
0x1800175fd  call    WPP_SF_sDsd
0x180017602  mov     [r14], esi
0x180017605  jmp     short loc_180017618
0x180017607  xor     esi, esi
0x180017609  test    r13, r13
0x18001760c  jnz     loc_1800177B4
0x180017612  mov     r15d, 10h
0x180017618  mov     rcx, r15
0x18001761b  lea     rax, [rbp+40h+var_A8]
0x18001761f  mov     [rax], sil
0x180017622  inc     rax
0x180017625  sub     rcx, 1
0x180017629  jnz     short loc_18001761F
0x18001762b  lea     rax, [rbp+40h+var_C0]
0x18001762f  mov     [rax], sil
0x180017632  inc     rax
0x180017635  sub     r15, 1
0x180017639  jnz     short loc_18001762F
0x18001763b  lea     rax, [rbp+40h+Size]
0x18001763f  mov     [rax], sil
0x180017642  inc     rax
0x180017645  sub     r12, 1
0x180017649  jnz     short loc_18001763F
0x18001764b  mov     eax, ebx
0x18001764d  mov     rcx, [rbp+40h+var_40]
0x180017651  xor     rcx, rsp; StackCookie
0x180017654  call    __security_check_cookie
0x180017659  mov     rbx, [rsp+140h+arg_18]
0x180017661  add     rsp, 110h
0x180017668  pop     r15
0x18001766a  pop     r14
0x18001766c  pop     r13
0x18001766e  pop     r12
0x180017670  pop     rdi
0x180017671  pop     rsi
0x180017672  pop     rbp
0x180017673  retn
0x180017675  xor     ebx, ebx
0x180017677  mov     [r14], esi
0x18001767a  xor     esi, esi
0x18001767c  jmp     short loc_180017618
0x18001767e  mov     r8, [rbp+40h+Size]; Size
0x180017682  mov     rdx, rsi; Src
0x180017685  mov     rcx, [rsp+140h+var_D8]; void *
0x18001768a  mov     [rsi], rax
0x18001768d  call    memmove
0x180017692  xor     ebx, ebx
0x180017694  mov     edi, r15d
0x180017697  mov     eax, r12d
0x18001769a  mov     ecx, r12d
0x18001769d  add     eax, edi
0x18001769f  mov     [r14], eax
0x1800176a2  test    rsi, rsi
0x1800176a5  jz      loc_180017607
0x1800176ab  lea     eax, [r15+rcx]
0x1800176af  mov     ecx, eax
0x1800176b1  test    eax, eax
0x1800176b3  jz      loc_180017607
0x1800176b9  mov     byte ptr [rsi], 0
0x1800176bc  inc     rsi
0x1800176bf  sub     rcx, 1
0x1800176c3  jnz     short loc_1800176B9
0x1800176c5  jmp     loc_180017607
0x1800176ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800176d1  lea     rax, WPP_GLOBAL_Control
0x1800176d8  cmp     rcx, rax
0x1800176db  jz      short loc_18001770C
0x1800176dd  mov     eax, [rcx+2Ch]
0x1800176e0  test    al, 1
0x1800176e2  jz      short loc_18001770C
0x1800176e4  mov     rcx, [rcx+18h]
0x1800176e8  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800176ef  mov     dword ptr [rsp+140h+var_110], 105h
0x1800176f7  lea     r9, aStatus; "Status"
0x1800176fe  mov     [rsp+140h+var_118], r8
0x180017703  mov     dword ptr [rsp+140h+var_120], ebx
0x180017707  call    WPP_SF_sDsd
0x18001770c  mov     r15d, edi
0x18001770f  jmp     short loc_180017697
0x180017711  mov     rcx, cs:WPP_GLOBAL_Control
0x180017718  lea     rax, WPP_GLOBAL_Control
0x18001771f  cmp     rcx, rax
0x180017722  jz      loc_180017602
0x180017728  mov     eax, [rcx+2Ch]
0x18001772b  test    al, 1
0x18001772d  jz      loc_180017602
0x180017733  mov     rcx, [rcx+18h]
0x180017737  mov     dword ptr [rsp+140h+var_110], 0C3h
0x18001773f  jmp     loc_1800175E6
0x180017744  mov     ebx, 0C0000008h
0x180017749  jmp     loc_180017602
0x18001774e  mov     ebx, 0C0000023h
0x180017753  jmp     loc_180017677
0x180017758  mov     rcx, rax
0x18001775b  call    MSCryptAlloc
0x180017760  mov     r13, rax
0x180017763  test    rax, rax
0x180017766  jnz     loc_18009FAD2
0x18001776c  mov     r9d, 0F3h
0x180017772  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017779  lea     rdx, aStatus; "Status"
0x180017780  mov     ecx, 0C0000017h
0x180017785  mov     ebx, 0C0000017h
0x18001778a  call    DebugTraceError
0x18001778f  jmp     loc_180017677
0x180017794  mov     r9d, 128h
0x18001779a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800177a1  lea     rdx, aStatus; "Status"
0x1800177a8  mov     ecx, eax
0x1800177aa  call    DebugTraceError
0x1800177af  jmp     loc_180017694
0x1800177b4  mov     rcx, r13; P
0x1800177b7  call    MSCryptFree
0x1800177bc  jmp     loc_180017612
0x1800177c1  mov     r9d, 0B5h
0x1800177c7  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800177ce  lea     rdx, aStatus; "Status"
0x1800177d5  mov     ecx, 0C0000008h
0x1800177da  mov     ebx, 0C0000008h
0x1800177df  call    DebugTraceError
0x1800177e4  jmp     loc_180017602
0x18009fad2  mov     rsi, rax
0x18009fad5  jmp     loc_1800174BC
```
