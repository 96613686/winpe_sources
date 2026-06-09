# MSCryptAesKeyWrap

- ea: `0x180014450`
- end: `0x180014899`
- name: `MSCryptAesKeyWrap`
- size: `1097`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180013dc0`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x18000abf0`
- `0x180014450`
- `0x1800148a0`
- `0x180014b8c`
- `0x18009f650`
- `0x18009f780`

## string_xrefs

- `0x180014696`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180014798`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180014822`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x18001484a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180014877`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`

## pseudocode

```c
__int64 __fastcall MSCryptAesKeyWrap(__int64 a1, __int64 a2, void *a3, unsigned int a4, unsigned int *a5)
{
  __int64 v7; // r12
  int Property; // ebx
  __int64 v9; // r15
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // edi
  unsigned int v14; // esi
  void *v15; // r13
  char *p_Src; // rsi
  int v17; // edx
  unsigned int v18; // r15d
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  unsigned int v21; // edi
  unsigned int i; // edx
  int v23; // eax
  __int64 v24; // rcx
  __int128 *v25; // rax
  unsigned __int64 *v26; // rax
  size_t *p_Size; // rax
  size_t v29; // r8
  void *v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rax
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v34; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h]
  void *v37; // [rsp+68h] [rbp-98h]
  __int64 v38; // [rsp+70h] [rbp-90h]
  __int64 v39; // [rsp+78h] [rbp-88h]
  unsigned __int64 v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+88h] [rbp-78h]
  size_t Size; // [rsp+90h] [rbp-70h] BYREF
  __int128 v43; // [rsp+98h] [rbp-68h] BYREF
  char Src; // [rsp+B0h] [rbp-50h] BYREF

  v36 = a1;
  v37 = a3;
  v38 = a2;
  LODWORD(v35) = 0;
  v34 = 0;
  v33 = 0;
  v7 = 8;
  Property = MSCryptGetProperty(a2, L"BlockLength", &v35, 4, &v33, 0);
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
  if ( v33 != 4 || (_DWORD)v35 != 16 )
  {
    Property = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c", 181);
    goto LABEL_22;
  }
  Property = MSCryptGetProperty(a1, L"KeyLength", &v34, 4, &v33, 0);
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
  v13 = v34 >> 3;
  if ( v33 != 4 || (v13 & 7) != 0 )
  {
    Property = -1073741816;
LABEL_22:
    *a5 = 0;
    goto LABEL_26;
  }
  v14 = v13 + 8;
  if ( !v37 )
  {
    Property = 0;
    goto LABEL_34;
  }
  if ( a4 < v14 )
  {
    Property = -1073741789;
    goto LABEL_34;
  }
  Size = v14;
  if ( v14 > 0x48 )
  {
    v32 = MSCryptAlloc(v14, v10, v11, v12);
    v15 = (void *)v32;
    if ( v32 )
    {
      p_Src = (char *)v32;
      goto LABEL_11;
    }
    Property = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c", 243);
LABEL_34:
    *a5 = v14;
    goto LABEL_26;
  }
  v15 = 0;
  p_Src = &Src;
LABEL_11:
  Property = MSCryptGetKeyData(v36, p_Src + 8, v13);
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v17,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        (unsigned int)"Status",
        Property,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        5);
    v18 = v13;
  }
  else
  {
    v18 = v13;
    v19 = (unsigned __int64)v13 >> 3;
    v20 = 0xA6A6A6A6A6A6A6A6uLL;
    v35 = v19;
    v21 = 0;
LABEL_13:
    if ( v21 >= 6 )
    {
      v29 = Size;
      v30 = v37;
      *(_QWORD *)p_Src = v20;
      memmove(v30, p_Src, v29);
      Property = 0;
    }
    else
    {
      for ( i = 0; ; i = v34 + 1 )
      {
        v34 = i;
        v36 = i;
        if ( i >= v19 )
        {
          ++v21;
          goto LABEL_13;
        }
        v40 = v20;
        v39 = 8 * i;
        v41 = *(_QWORD *)&p_Src[v39 + 8];
        v43 = 0;
        v23 = MSCryptEncrypt(
                v38,
                (unsigned __int64)&v40,
                0x10u,
                0,
                (__int64 *)&v43,
                0x10u,
                (unsigned __int64)&v40,
                0x10u,
                &v33,
                0);
        Property = v23;
        if ( v23 < 0 )
          break;
        v20 = v40 ^ _byteswap_uint64(v36 + 1 + v35 * v21);
        *(_QWORD *)&p_Src[v39 + 8] = v41;
        v19 = v35;
      }
      DebugTraceError(
        (unsigned int)v23,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        296);
    }
    v13 = v18;
  }
  *a5 = v13 + 8;
  if ( p_Src )
  {
    v31 = v18 + 8;
    if ( v18 != -8 )
    {
      do
      {
        *p_Src++ = 0;
        --v31;
      }
      while ( v31 );
    }
  }
  if ( v15 )
    MSCryptFree(v15);
  v9 = 16;
LABEL_26:
  v24 = 16;
  v25 = &v43;
  do
  {
    *(_BYTE *)v25 = 0;
    v25 = (__int128 *)((char *)v25 + 1);
    --v24;
  }
  while ( v24 );
  v26 = &v40;
  do
  {
    *(_BYTE *)v26 = 0;
    v26 = (unsigned __int64 *)((char *)v26 + 1);
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
0x180014450  mov     [rsp-8+arg_18], rbx
0x180014455  push    rbp
0x180014456  push    rsi
0x180014457  push    rdi
0x180014458  push    r12
0x18001445a  push    r13
0x18001445c  push    r14
0x18001445e  push    r15
0x180014460  lea     rbp, [rsp-10h]
0x180014465  sub     rsp, 110h
0x18001446c  mov     rax, cs:__security_cookie
0x180014473  xor     rax, rsp
0x180014476  mov     [rbp+40h+var_40], rax
0x18001447a  mov     r14, [rbp+40h+arg_20]
0x18001447e  xor     esi, esi
0x180014480  mov     rdi, rcx
0x180014483  mov     [rsp+140h+var_E0], rcx
0x180014488  mov     rax, rdx
0x18001448b  mov     [rsp+140h+var_D8], r8
0x180014490  lea     rcx, [rsp+140h+var_F0]
0x180014495  mov     [rsp+140h+var_D0], rdx
0x18001449a  mov     r13d, r9d
0x18001449d  mov     dword ptr [rsp+140h+var_118], esi
0x1800144a1  mov     [rsp+140h+var_120], rcx
0x1800144a6  lea     r9d, [rsi+4]
0x1800144aa  lea     r8, [rsp+140h+var_E8]
0x1800144af  mov     dword ptr [rsp+140h+var_E8], esi
0x1800144b3  lea     rdx, aBlocklength; "BlockLength"
0x1800144ba  mov     [rsp+140h+var_EC], esi
0x1800144be  mov     rcx, rax
0x1800144c1  mov     [rsp+140h+var_F0], esi
0x1800144c5  call    MSCryptGetProperty
0x1800144ca  lea     r12d, [rsi+8]
0x1800144ce  mov     ebx, eax
0x1800144d0  lea     r15d, [rsi+10h]
0x1800144d4  test    eax, eax
0x1800144d6  js      loc_18001466F
0x1800144dc  cmp     [rsp+140h+var_F0], 4
0x1800144e1  jnz     loc_180014871
0x1800144e7  cmp     dword ptr [rsp+140h+var_E8], r15d
0x1800144ec  jnz     loc_180014871
0x1800144f2  lea     rax, [rsp+140h+var_F0]
0x1800144f7  mov     dword ptr [rsp+140h+var_118], esi
0x1800144fb  lea     r9d, [rsi+4]
0x1800144ff  mov     [rsp+140h+var_120], rax
0x180014504  lea     r8, [rsp+140h+var_EC]
0x180014509  mov     rcx, rdi
0x18001450c  lea     rdx, aKeylength; "KeyLength"
0x180014513  call    MSCryptGetProperty
0x180014518  mov     ebx, eax
0x18001451a  test    eax, eax
0x18001451c  js      loc_1800147C1
0x180014522  mov     edi, [rsp+140h+var_EC]
0x180014526  shr     edi, 3
0x180014529  cmp     [rsp+140h+var_F0], 4
0x18001452e  jnz     loc_1800147F4
0x180014534  test    dil, 7
0x180014538  jnz     loc_1800147F4
0x18001453e  cmp     [rsp+140h+var_D8], 0
0x180014544  lea     esi, [rdi+8]
0x180014547  jz      loc_180014725
0x18001454d  cmp     r13d, esi
0x180014550  jb      loc_1800147FE
0x180014556  mov     eax, esi
0x180014558  mov     [rbp+40h+Size], rax
0x18001455c  cmp     esi, 48h ; 'H'
0x18001455f  ja      loc_180014808
0x180014565  xor     r13d, r13d
0x180014568  lea     rsi, [rbp+40h+Src]
0x18001456c  mov     rcx, [rsp+140h+var_E0]
0x180014571  lea     rdx, [rsi+8]
0x180014575  mov     r8d, edi
0x180014578  call    MSCryptGetKeyData
0x18001457d  mov     ebx, eax
0x18001457f  test    eax, eax
0x180014581  js      loc_18001477A
0x180014587  mov     ecx, edi
0x180014589  mov     r15d, edi
0x18001458c  shr     rcx, 3
0x180014590  mov     rax, 0A6A6A6A6A6A6A6A6h
0x18001459a  mov     [rsp+140h+var_E8], rcx
0x18001459f  xor     edi, edi
0x1800145a1  cmp     edi, 6
0x1800145a4  jnb     loc_18001472E
0x1800145aa  xor     edx, edx
0x1800145ac  mov     r8d, edx
0x1800145af  mov     [rsp+140h+var_EC], edx
0x1800145b3  mov     [rsp+140h+var_E0], r8
0x1800145b8  cmp     r8, rcx
0x1800145bb  jnb     loc_180014668
0x1800145c1  mov     [rbp+40h+var_C0], rax
0x1800145c5  lea     rcx, [rbp+40h+var_C0]
0x1800145c9  mov     [rsp+140h+var_F8], 0
0x1800145d1  lea     eax, ds:0[rdx*8]
0x1800145d8  mov     [rsp+140h+var_C8], rax
0x1800145dd  lea     rdx, [rbp+40h+var_C0]
0x1800145e1  mov     rax, [rax+rsi+8]
0x1800145e6  xorps   xmm0, xmm0
0x1800145e9  mov     [rbp+40h+var_B8], rax
0x1800145ed  xor     r9d, r9d
0x1800145f0  lea     rax, [rsp+140h+var_F0]
0x1800145f5  mov     [rsp+140h+var_100], rax
0x1800145fa  mov     eax, 10h
0x1800145ff  mov     [rsp+140h+var_108], eax
0x180014603  mov     r8d, eax
0x180014606  mov     [rsp+140h+var_110], rcx
0x18001460b  lea     rcx, [rbp+40h+var_A8]
0x18001460f  mov     dword ptr [rsp+140h+var_118], eax
0x180014613  mov     [rsp+140h+var_120], rcx
0x180014618  mov     rcx, [rsp+140h+var_D0]
0x18001461d  movups  [rbp+40h+var_A8], xmm0
0x180014621  call    MSCryptEncrypt
0x180014626  mov     ebx, eax
0x180014628  test    eax, eax
0x18001462a  js      loc_180014844
0x180014630  mov     rdx, [rsp+140h+var_C8]
0x180014635  mov     rcx, [rsp+140h+var_E0]
0x18001463a  inc     rcx
0x18001463d  mov     eax, edi
0x18001463f  imul    rax, [rsp+140h+var_E8]
0x180014645  add     rax, rcx
0x180014648  mov     rcx, [rbp+40h+var_B8]
0x18001464c  bswap   rax
0x18001464f  xor     rax, [rbp+40h+var_C0]
0x180014653  mov     [rdx+rsi+8], rcx
0x180014658  mov     edx, [rsp+140h+var_EC]
0x18001465c  mov     rcx, [rsp+140h+var_E8]
0x180014661  inc     edx
0x180014663  jmp     loc_1800145AC
0x180014668  inc     edi
0x18001466a  jmp     loc_1800145A1
0x18001466f  mov     rdx, cs:WPP_GLOBAL_Control
0x180014676  lea     rax, WPP_GLOBAL_Control
0x18001467d  cmp     rdx, rax
0x180014680  jz      short loc_1800146B2
0x180014682  mov     ecx, [rdx+2Ch]
0x180014685  test    cl, 1
0x180014688  jz      short loc_1800146B2
0x18001468a  mov     rcx, [rdx+18h]
0x18001468e  mov     dword ptr [rsp+140h+var_110], 0ADh
0x180014696  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001469d  mov     [rsp+140h+var_118], r8
0x1800146a2  lea     r9, aStatus; "Status"
0x1800146a9  mov     dword ptr [rsp+140h+var_120], ebx
0x1800146ad  call    WPP_SF_sDsd
0x1800146b2  mov     [r14], esi
0x1800146b5  jmp     short loc_1800146C8
0x1800146b7  xor     esi, esi
0x1800146b9  test    r13, r13
0x1800146bc  jnz     loc_180014864
0x1800146c2  mov     r15d, 10h
0x1800146c8  mov     rcx, r15
0x1800146cb  lea     rax, [rbp+40h+var_A8]
0x1800146cf  mov     [rax], sil
0x1800146d2  inc     rax
0x1800146d5  sub     rcx, 1
0x1800146d9  jnz     short loc_1800146CF
0x1800146db  lea     rax, [rbp+40h+var_C0]
0x1800146df  mov     [rax], sil
0x1800146e2  inc     rax
0x1800146e5  sub     r15, 1
0x1800146e9  jnz     short loc_1800146DF
0x1800146eb  lea     rax, [rbp+40h+Size]
0x1800146ef  mov     [rax], sil
0x1800146f2  inc     rax
0x1800146f5  sub     r12, 1
0x1800146f9  jnz     short loc_1800146EF
0x1800146fb  mov     eax, ebx
0x1800146fd  mov     rcx, [rbp+40h+var_40]
0x180014701  xor     rcx, rsp; StackCookie
0x180014704  call    __security_check_cookie
0x180014709  mov     rbx, [rsp+140h+arg_18]
0x180014711  add     rsp, 110h
0x180014718  pop     r15
0x18001471a  pop     r14
0x18001471c  pop     r13
0x18001471e  pop     r12
0x180014720  pop     rdi
0x180014721  pop     rsi
0x180014722  pop     rbp
0x180014723  retn
0x180014725  xor     ebx, ebx
0x180014727  mov     [r14], esi
0x18001472a  xor     esi, esi
0x18001472c  jmp     short loc_1800146C8
0x18001472e  mov     r8, [rbp+40h+Size]; Size
0x180014732  mov     rdx, rsi; Src
0x180014735  mov     rcx, [rsp+140h+var_D8]; void *
0x18001473a  mov     [rsi], rax
0x18001473d  call    memmove
0x180014742  xor     ebx, ebx
0x180014744  mov     edi, r15d
0x180014747  mov     eax, r12d
0x18001474a  mov     ecx, r12d
0x18001474d  add     eax, edi
0x18001474f  mov     [r14], eax
0x180014752  test    rsi, rsi
0x180014755  jz      loc_1800146B7
0x18001475b  lea     eax, [r15+rcx]
0x18001475f  mov     ecx, eax
0x180014761  test    eax, eax
0x180014763  jz      loc_1800146B7
0x180014769  mov     byte ptr [rsi], 0
0x18001476c  inc     rsi
0x18001476f  sub     rcx, 1
0x180014773  jnz     short loc_180014769
0x180014775  jmp     loc_1800146B7
0x18001477a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014781  lea     rax, WPP_GLOBAL_Control
0x180014788  cmp     rcx, rax
0x18001478b  jz      short loc_1800147BC
0x18001478d  mov     eax, [rcx+2Ch]
0x180014790  test    al, 1
0x180014792  jz      short loc_1800147BC
0x180014794  mov     rcx, [rcx+18h]
0x180014798  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001479f  mov     dword ptr [rsp+140h+var_110], 105h
0x1800147a7  lea     r9, aStatus; "Status"
0x1800147ae  mov     [rsp+140h+var_118], r8
0x1800147b3  mov     dword ptr [rsp+140h+var_120], ebx
0x1800147b7  call    WPP_SF_sDsd
0x1800147bc  mov     r15d, edi
0x1800147bf  jmp     short loc_180014747
0x1800147c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147c8  lea     rax, WPP_GLOBAL_Control
0x1800147cf  cmp     rcx, rax
0x1800147d2  jz      loc_1800146B2
0x1800147d8  mov     eax, [rcx+2Ch]
0x1800147db  test    al, 1
0x1800147dd  jz      loc_1800146B2
0x1800147e3  mov     rcx, [rcx+18h]
0x1800147e7  mov     dword ptr [rsp+140h+var_110], 0C3h
0x1800147ef  jmp     loc_180014696
0x1800147f4  mov     ebx, 0C0000008h
0x1800147f9  jmp     loc_1800146B2
0x1800147fe  mov     ebx, 0C0000023h
0x180014803  jmp     loc_180014727
0x180014808  mov     rcx, rax
0x18001480b  call    MSCryptAlloc
0x180014810  mov     r13, rax
0x180014813  test    rax, rax
0x180014816  jnz     loc_1800A1688
0x18001481c  mov     r9d, 0F3h
0x180014822  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014829  lea     rdx, aStatus; "Status"
0x180014830  mov     ecx, 0C0000017h
0x180014835  mov     ebx, 0C0000017h
0x18001483a  call    DebugTraceError
0x18001483f  jmp     loc_180014727
0x180014844  mov     r9d, 128h
0x18001484a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014851  lea     rdx, aStatus; "Status"
0x180014858  mov     ecx, eax
0x18001485a  call    DebugTraceError
0x18001485f  jmp     loc_180014744
0x180014864  mov     rcx, r13; P
0x180014867  call    MSCryptFree
0x18001486c  jmp     loc_1800146C2
0x180014871  mov     r9d, 0B5h
0x180014877  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001487e  lea     rdx, aStatus; "Status"
0x180014885  mov     ecx, 0C0000008h
0x18001488a  mov     ebx, 0C0000008h
0x18001488f  call    DebugTraceError
0x180014894  jmp     loc_1800146B2
0x1800a1688  mov     rsi, rax
0x1800a168b  jmp     loc_18001456C
```
