# MSCryptAesKeyWrap

- ea: `0x180021480`
- end: `0x1800218c9`
- name: `MSCryptAesKeyWrap`
- size: `1097`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180020df0`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x180014d10`
- `0x180021480`
- `0x1800218d0`
- `0x180021c0c`
- `0x1800a4260`
- `0x1800a45c0`

## string_xrefs

- `0x1800216c6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x1800217c8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180021852`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x18002187a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x1800218a7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`

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
0x180021480  mov     [rsp-8+arg_18], rbx
0x180021485  push    rbp
0x180021486  push    rsi
0x180021487  push    rdi
0x180021488  push    r12
0x18002148a  push    r13
0x18002148c  push    r14
0x18002148e  push    r15
0x180021490  lea     rbp, [rsp-10h]
0x180021495  sub     rsp, 110h
0x18002149c  mov     rax, cs:__security_cookie
0x1800214a3  xor     rax, rsp
0x1800214a6  mov     [rbp+40h+var_40], rax
0x1800214aa  mov     r14, [rbp+40h+arg_20]
0x1800214ae  xor     esi, esi
0x1800214b0  mov     rdi, rcx
0x1800214b3  mov     [rsp+140h+var_E0], rcx
0x1800214b8  mov     rax, rdx
0x1800214bb  mov     [rsp+140h+var_D8], r8
0x1800214c0  lea     rcx, [rsp+140h+var_F0]
0x1800214c5  mov     [rsp+140h+var_D0], rdx
0x1800214ca  mov     r13d, r9d
0x1800214cd  mov     dword ptr [rsp+140h+var_118], esi
0x1800214d1  mov     [rsp+140h+var_120], rcx
0x1800214d6  lea     r9d, [rsi+4]
0x1800214da  lea     r8, [rsp+140h+var_E8]
0x1800214df  mov     dword ptr [rsp+140h+var_E8], esi
0x1800214e3  lea     rdx, aBlocklength; "BlockLength"
0x1800214ea  mov     [rsp+140h+var_EC], esi
0x1800214ee  mov     rcx, rax
0x1800214f1  mov     [rsp+140h+var_F0], esi
0x1800214f5  call    MSCryptGetProperty
0x1800214fa  lea     r12d, [rsi+8]
0x1800214fe  mov     ebx, eax
0x180021500  lea     r15d, [rsi+10h]
0x180021504  test    eax, eax
0x180021506  js      loc_18002169F
0x18002150c  cmp     [rsp+140h+var_F0], 4
0x180021511  jnz     loc_1800218A1
0x180021517  cmp     dword ptr [rsp+140h+var_E8], r15d
0x18002151c  jnz     loc_1800218A1
0x180021522  lea     rax, [rsp+140h+var_F0]
0x180021527  mov     dword ptr [rsp+140h+var_118], esi
0x18002152b  lea     r9d, [rsi+4]
0x18002152f  mov     [rsp+140h+var_120], rax
0x180021534  lea     r8, [rsp+140h+var_EC]
0x180021539  mov     rcx, rdi
0x18002153c  lea     rdx, aKeylength; "KeyLength"
0x180021543  call    MSCryptGetProperty
0x180021548  mov     ebx, eax
0x18002154a  test    eax, eax
0x18002154c  js      loc_1800217F1
0x180021552  mov     edi, [rsp+140h+var_EC]
0x180021556  shr     edi, 3
0x180021559  cmp     [rsp+140h+var_F0], 4
0x18002155e  jnz     loc_180021824
0x180021564  test    dil, 7
0x180021568  jnz     loc_180021824
0x18002156e  cmp     [rsp+140h+var_D8], 0
0x180021574  lea     esi, [rdi+8]
0x180021577  jz      loc_180021755
0x18002157d  cmp     r13d, esi
0x180021580  jb      loc_18002182E
0x180021586  mov     eax, esi
0x180021588  mov     [rbp+40h+Size], rax
0x18002158c  cmp     esi, 48h ; 'H'
0x18002158f  ja      loc_180021838
0x180021595  xor     r13d, r13d
0x180021598  lea     rsi, [rbp+40h+Src]
0x18002159c  mov     rcx, [rsp+140h+var_E0]
0x1800215a1  lea     rdx, [rsi+8]
0x1800215a5  mov     r8d, edi
0x1800215a8  call    MSCryptGetKeyData
0x1800215ad  mov     ebx, eax
0x1800215af  test    eax, eax
0x1800215b1  js      loc_1800217AA
0x1800215b7  mov     ecx, edi
0x1800215b9  mov     r15d, edi
0x1800215bc  shr     rcx, 3
0x1800215c0  mov     rax, 0A6A6A6A6A6A6A6A6h
0x1800215ca  mov     [rsp+140h+var_E8], rcx
0x1800215cf  xor     edi, edi
0x1800215d1  cmp     edi, 6
0x1800215d4  jnb     loc_18002175E
0x1800215da  xor     edx, edx
0x1800215dc  mov     r8d, edx
0x1800215df  mov     [rsp+140h+var_EC], edx
0x1800215e3  mov     [rsp+140h+var_E0], r8
0x1800215e8  cmp     r8, rcx
0x1800215eb  jnb     loc_180021698
0x1800215f1  mov     [rbp+40h+var_C0], rax
0x1800215f5  lea     rcx, [rbp+40h+var_C0]
0x1800215f9  mov     [rsp+140h+var_F8], 0
0x180021601  lea     eax, ds:0[rdx*8]
0x180021608  mov     [rsp+140h+var_C8], rax
0x18002160d  lea     rdx, [rbp+40h+var_C0]
0x180021611  mov     rax, [rax+rsi+8]
0x180021616  xorps   xmm0, xmm0
0x180021619  mov     [rbp+40h+var_B8], rax
0x18002161d  xor     r9d, r9d
0x180021620  lea     rax, [rsp+140h+var_F0]
0x180021625  mov     [rsp+140h+var_100], rax
0x18002162a  mov     eax, 10h
0x18002162f  mov     [rsp+140h+var_108], eax
0x180021633  mov     r8d, eax
0x180021636  mov     [rsp+140h+var_110], rcx
0x18002163b  lea     rcx, [rbp+40h+var_A8]
0x18002163f  mov     dword ptr [rsp+140h+var_118], eax
0x180021643  mov     [rsp+140h+var_120], rcx
0x180021648  mov     rcx, [rsp+140h+var_D0]
0x18002164d  movups  [rbp+40h+var_A8], xmm0
0x180021651  call    MSCryptEncrypt
0x180021656  mov     ebx, eax
0x180021658  test    eax, eax
0x18002165a  js      loc_180021874
0x180021660  mov     rdx, [rsp+140h+var_C8]
0x180021665  mov     rcx, [rsp+140h+var_E0]
0x18002166a  inc     rcx
0x18002166d  mov     eax, edi
0x18002166f  imul    rax, [rsp+140h+var_E8]
0x180021675  add     rax, rcx
0x180021678  mov     rcx, [rbp+40h+var_B8]
0x18002167c  bswap   rax
0x18002167f  xor     rax, [rbp+40h+var_C0]
0x180021683  mov     [rdx+rsi+8], rcx
0x180021688  mov     edx, [rsp+140h+var_EC]
0x18002168c  mov     rcx, [rsp+140h+var_E8]
0x180021691  inc     edx
0x180021693  jmp     loc_1800215DC
0x180021698  inc     edi
0x18002169a  jmp     loc_1800215D1
0x18002169f  mov     rdx, cs:WPP_GLOBAL_Control
0x1800216a6  lea     rax, WPP_GLOBAL_Control
0x1800216ad  cmp     rdx, rax
0x1800216b0  jz      short loc_1800216E2
0x1800216b2  mov     ecx, [rdx+2Ch]
0x1800216b5  test    cl, 1
0x1800216b8  jz      short loc_1800216E2
0x1800216ba  mov     rcx, [rdx+18h]
0x1800216be  mov     dword ptr [rsp+140h+var_110], 0ADh
0x1800216c6  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800216cd  mov     [rsp+140h+var_118], r8
0x1800216d2  lea     r9, aStatus; "Status"
0x1800216d9  mov     dword ptr [rsp+140h+var_120], ebx
0x1800216dd  call    WPP_SF_sDsd
0x1800216e2  mov     [r14], esi
0x1800216e5  jmp     short loc_1800216F8
0x1800216e7  xor     esi, esi
0x1800216e9  test    r13, r13
0x1800216ec  jnz     loc_180021894
0x1800216f2  mov     r15d, 10h
0x1800216f8  mov     rcx, r15
0x1800216fb  lea     rax, [rbp+40h+var_A8]
0x1800216ff  mov     [rax], sil
0x180021702  inc     rax
0x180021705  sub     rcx, 1
0x180021709  jnz     short loc_1800216FF
0x18002170b  lea     rax, [rbp+40h+var_C0]
0x18002170f  mov     [rax], sil
0x180021712  inc     rax
0x180021715  sub     r15, 1
0x180021719  jnz     short loc_18002170F
0x18002171b  lea     rax, [rbp+40h+Size]
0x18002171f  mov     [rax], sil
0x180021722  inc     rax
0x180021725  sub     r12, 1
0x180021729  jnz     short loc_18002171F
0x18002172b  mov     eax, ebx
0x18002172d  mov     rcx, [rbp+40h+var_40]
0x180021731  xor     rcx, rsp; StackCookie
0x180021734  call    __security_check_cookie
0x180021739  mov     rbx, [rsp+140h+arg_18]
0x180021741  add     rsp, 110h
0x180021748  pop     r15
0x18002174a  pop     r14
0x18002174c  pop     r13
0x18002174e  pop     r12
0x180021750  pop     rdi
0x180021751  pop     rsi
0x180021752  pop     rbp
0x180021753  retn
0x180021755  xor     ebx, ebx
0x180021757  mov     [r14], esi
0x18002175a  xor     esi, esi
0x18002175c  jmp     short loc_1800216F8
0x18002175e  mov     r8, [rbp+40h+Size]; Size
0x180021762  mov     rdx, rsi; Src
0x180021765  mov     rcx, [rsp+140h+var_D8]; void *
0x18002176a  mov     [rsi], rax
0x18002176d  call    memmove
0x180021772  xor     ebx, ebx
0x180021774  mov     edi, r15d
0x180021777  mov     eax, r12d
0x18002177a  mov     ecx, r12d
0x18002177d  add     eax, edi
0x18002177f  mov     [r14], eax
0x180021782  test    rsi, rsi
0x180021785  jz      loc_1800216E7
0x18002178b  lea     eax, [r15+rcx]
0x18002178f  mov     ecx, eax
0x180021791  test    eax, eax
0x180021793  jz      loc_1800216E7
0x180021799  mov     byte ptr [rsi], 0
0x18002179c  inc     rsi
0x18002179f  sub     rcx, 1
0x1800217a3  jnz     short loc_180021799
0x1800217a5  jmp     loc_1800216E7
0x1800217aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800217b1  lea     rax, WPP_GLOBAL_Control
0x1800217b8  cmp     rcx, rax
0x1800217bb  jz      short loc_1800217EC
0x1800217bd  mov     eax, [rcx+2Ch]
0x1800217c0  test    al, 1
0x1800217c2  jz      short loc_1800217EC
0x1800217c4  mov     rcx, [rcx+18h]
0x1800217c8  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800217cf  mov     dword ptr [rsp+140h+var_110], 105h
0x1800217d7  lea     r9, aStatus; "Status"
0x1800217de  mov     [rsp+140h+var_118], r8
0x1800217e3  mov     dword ptr [rsp+140h+var_120], ebx
0x1800217e7  call    WPP_SF_sDsd
0x1800217ec  mov     r15d, edi
0x1800217ef  jmp     short loc_180021777
0x1800217f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800217f8  lea     rax, WPP_GLOBAL_Control
0x1800217ff  cmp     rcx, rax
0x180021802  jz      loc_1800216E2
0x180021808  mov     eax, [rcx+2Ch]
0x18002180b  test    al, 1
0x18002180d  jz      loc_1800216E2
0x180021813  mov     rcx, [rcx+18h]
0x180021817  mov     dword ptr [rsp+140h+var_110], 0C3h
0x18002181f  jmp     loc_1800216C6
0x180021824  mov     ebx, 0C0000008h
0x180021829  jmp     loc_1800216E2
0x18002182e  mov     ebx, 0C0000023h
0x180021833  jmp     loc_180021757
0x180021838  mov     rcx, rax
0x18002183b  call    MSCryptAlloc
0x180021840  mov     r13, rax
0x180021843  test    rax, rax
0x180021846  jnz     loc_1800A6870
0x18002184c  mov     r9d, 0F3h
0x180021852  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021859  lea     rdx, aStatus; "Status"
0x180021860  mov     ecx, 0C0000017h
0x180021865  mov     ebx, 0C0000017h
0x18002186a  call    DebugTraceError
0x18002186f  jmp     loc_180021757
0x180021874  mov     r9d, 128h
0x18002187a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021881  lea     rdx, aStatus; "Status"
0x180021888  mov     ecx, eax
0x18002188a  call    DebugTraceError
0x18002188f  jmp     loc_180021774
0x180021894  mov     rcx, r13; P
0x180021897  call    MSCryptFree
0x18002189c  jmp     loc_1800216F2
0x1800218a1  mov     r9d, 0B5h
0x1800218a7  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800218ae  lea     rdx, aStatus; "Status"
0x1800218b5  mov     ecx, 0C0000008h
0x1800218ba  mov     ebx, 0C0000008h
0x1800218bf  call    DebugTraceError
0x1800218c4  jmp     loc_1800216E2
0x1800a6870  mov     rsi, rax
0x1800a6873  jmp     loc_18002159C
```
