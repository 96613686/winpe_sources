# HashDeviceId(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180031360`
- end: `0x18003175e`
- name: `?HashDeviceId@@YAJPEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1022`
- prototype: `__int64 __fastcall(_WORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800318a4`

## callees

- `0x1800098dc`
- `0x18000b030`
- `0x18000b31c`
- `0x18001eab4`
- `0x180031360`
- `0x180032f58`
- `0x180047010`

## import_xrefs

- `msvcrt!towlower` at `0x18003167e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800314a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031571`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800315f5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031662`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800316c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800316d5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800316f4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031715`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800314a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031571`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800315f5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031662`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800316c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800316d5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800316f4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031715`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180031490`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180031706`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180031490`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180031706`
- `bcrypt!BCryptDestroyHash` at `0x18003155e`
- `bcrypt!BCryptDestroyHash` at `0x1800316e5`
- `bcrypt!BCryptDestroyHash` at `0x18003155e`
- `bcrypt!BCryptDestroyHash` at `0x1800316e5`
- `bcrypt!BCryptFinishHash` at `0x1800315c7`
- `bcrypt!BCryptFinishHash` at `0x1800315c7`
- `bcrypt!BCryptGetProperty` at `0x1800314d9`
- `bcrypt!BCryptGetProperty` at `0x1800314d9`
- `bcrypt!BCryptHashData` at `0x180031589`
- `bcrypt!BCryptHashData` at `0x180031589`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180031461`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180031461`
- `bcrypt!BCryptCreateHash` at `0x180031531`
- `bcrypt!BCryptCreateHash` at `0x180031531`
- `DMCmnUtils!BinaryToHexString` at `0x180031635`
- `DMCmnUtils!BinaryToHexString` at `0x180031635`

## pseudocode

```c
__int64 __fastcall HashDeviceId(_WORD *a1, _QWORD *a2)
{
  _QWORD *v2; // r12
  __int64 v4; // rcx
  _WORD *v5; // rax
  unsigned int v6; // ebx
  unsigned __int64 v7; // rdx
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rcx
  PUCHAR v11; // rdi
  NTSTATUS Property; // eax
  __int64 v13; // rdx
  ULONG v14; // r9d
  PUCHAR v15; // rsi
  NTSTATUS v16; // eax
  __int64 v17; // rdx
  PUCHAR v18; // r15
  NTSTATUS v19; // eax
  _WORD *v20; // r14
  int v21; // eax
  unsigned __int16 *v22; // r13
  _WORD *v23; // rbx
  unsigned __int64 v24; // r8
  __int64 v25; // rdx
  int pcbResult; // [rsp+20h] [rbp-79h]
  int pcbResulta; // [rsp+20h] [rbp-79h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-59h] BYREF
  void *Src[2]; // [rsp+48h] [rbp-51h] BYREF
  __int64 v30; // [rsp+58h] [rbp-41h]
  PUCHAR pbInput[2]; // [rsp+60h] [rbp-39h] BYREF
  __int64 v32; // [rsp+70h] [rbp-29h]
  PUCHAR pbHashObject[2]; // [rsp+78h] [rbp-21h] BYREF
  __int64 v34; // [rsp+88h] [rbp-11h]
  PUCHAR v35[2]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v36; // [rsp+A0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  ULONG pbOutput; // [rsp+100h] [rbp+67h] BYREF
  ULONG v39; // [rsp+108h] [rbp+6Fh] BYREF
  int v40; // [rsp+110h] [rbp+77h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+118h] [rbp+7Fh] BYREF

  v2 = a2;
  if ( a2[3] >= 8u )
    a2 = (_QWORD *)*a2;
  v2[2] = 0;
  *(_WORD *)a2 = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
LABEL_62:
    v25 = 57;
    goto LABEL_63;
  }
  v4 = 0x7FFFFFFF;
  v5 = a1;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  v6 = v4 == 0 ? 0x80070057 : 0;
  v7 = (0x7FFFFFFF - v4) & ((unsigned __int128)-(__int128)(unsigned __int64)v4 >> 64);
  if ( !v4 )
    goto LABEL_62;
  if ( !v7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionutil.cpp",
      (const char *)0x80070057LL,
      pcbResult);
    return 2147942487LL;
  }
  if ( v7 > 0xFFFFFFFF )
  {
    v6 = -2147024362;
    v25 = 61;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionutil.cpp",
      (const char *)v6,
      pcbResult);
    return v6;
  }
  v9 = (unsigned int)v7;
  *(_OWORD *)pbInput = 0;
  v32 = 0;
  std::vector<unsigned char>::_Reallocate(pbInput, (unsigned int)v7);
  v10 = 0;
  v11 = pbInput[0];
  do
  {
    v11[v10] = a1[v10];
    ++v10;
  }
  while ( v10 < v9 );
  phAlgorithm = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"MD5", 0, 0);
  if ( Property < 0 )
  {
    v13 = 73;
LABEL_17:
    v6 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v13,
           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionutil.cpp",
           (const char *)(unsigned int)Property,
           pcbResult);
LABEL_18:
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    if ( v11 )
      operator delete(v11);
    return v6;
  }
  pbOutput = 0;
  v39 = 4;
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &v39, 0);
  if ( Property < 0 )
  {
    v13 = 79;
    goto LABEL_17;
  }
  *(_OWORD *)pbHashObject = 0;
  v34 = 0;
  v14 = pbOutput;
  if ( pbOutput )
  {
    std::vector<unsigned char>::_Reallocate(pbHashObject, pbOutput);
    v14 = pbOutput;
  }
  v15 = pbHashObject[0];
  phHash = 0;
  v16 = BCryptCreateHash(phAlgorithm, &phHash, pbHashObject[0], v14, 0, 0, 0);
  if ( v16 < 0 )
  {
    v17 = 86;
LABEL_28:
    v6 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v17,
           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionutil.cpp",
           (const char *)(unsigned int)v16,
           pcbResulta);
LABEL_29:
    if ( phHash )
      BCryptDestroyHash(phHash);
    if ( v15 )
      operator delete(v15);
    goto LABEL_18;
  }
  v16 = BCryptHashData(phHash, v11, v9, 0);
  if ( v16 < 0 )
  {
    v17 = 87;
    goto LABEL_28;
  }
  *(_OWORD *)v35 = 0;
  v36 = 0;
  std::vector<unsigned char>::_Reallocate(v35, 16);
  v18 = v35[0];
  v19 = BCryptFinishHash(phHash, v35[0], 0x10u, 0);
  if ( v19 < 0 )
  {
    v6 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x5D,
           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionutil.cpp",
           (const char *)(unsigned int)v19,
           pcbResulta);
LABEL_37:
    if ( v18 )
      operator delete(v18);
    goto LABEL_29;
  }
  v40 = 33;
  *(_OWORD *)Src = 0;
  v30 = 0;
  std::vector<unsigned short>::resize(Src, 33);
  v20 = Src[0];
  v21 = BinaryToHexString(v18, 16, Src[0], &v40);
  v6 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionutil.cpp",
      (const char *)(unsigned int)v21,
      1);
    if ( v20 )
      operator delete(v20);
    goto LABEL_37;
  }
  if ( v20 != Src[1] )
  {
    v22 = v20;
    v23 = v20;
    do
      *v23++ = ((__int64 (__fastcall *)(_QWORD))towlower)(*v22++);
    while ( v22 != Src[1] );
  }
  if ( *v20 )
  {
    v24 = -1;
    do
      ++v24;
    while ( v20[v24] );
  }
  else
  {
    v24 = 0;
  }
  std::wstring::assign(v2, (char *)v20, v24);
  operator delete(v20);
  if ( v18 )
    operator delete(v18);
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v15 )
    operator delete(v15);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v11 )
    operator delete(v11);
  return 0;
}

```

## disassembly

```asm
0x180031360  push    rbp
0x180031362  push    rbx
0x180031363  push    rsi
0x180031364  push    rdi
0x180031365  push    r12
0x180031367  push    r13
0x180031369  push    r14
0x18003136b  push    r15
0x18003136d  lea     rbp, [rsp-1Fh]
0x180031372  sub     rsp, 0B8h
0x180031379  mov     r12, rdx
0x18003137c  mov     rsi, rcx
0x18003137f  cmp     qword ptr [rdx+18h], 8
0x180031384  jb      short loc_180031389
0x180031386  mov     rdx, [rdx]
0x180031389  xor     r13d, r13d
0x18003138c  mov     [r12+10h], r13
0x180031391  mov     [rdx], r13w
0x180031395  test    rsi, rsi
0x180031398  jz      loc_18003172B
0x18003139e  mov     r8d, 7FFFFFFFh
0x1800313a4  mov     ecx, r8d
0x1800313a7  mov     rax, rsi
0x1800313aa  cmp     [rax], r13w
0x1800313ae  jz      short loc_1800313BA
0x1800313b0  add     rax, 2
0x1800313b4  sub     rcx, 1
0x1800313b8  jnz     short loc_1800313AA
0x1800313ba  mov     rax, rcx
0x1800313bd  neg     rax
0x1800313c0  sbb     ebx, ebx
0x1800313c2  not     ebx
0x1800313c4  mov     edi, 80070057h
0x1800313c9  and     ebx, edi
0x1800313cb  mov     rax, rcx
0x1800313ce  sub     r8, rcx
0x1800313d1  neg     rax
0x1800313d4  sbb     rdx, rdx
0x1800313d7  and     rdx, r8
0x1800313da  test    rcx, rcx
0x1800313dd  jz      loc_180031730
0x1800313e3  test    rdx, rdx
0x1800313e6  jnz     short loc_180031407
0x1800313e8  mov     rcx, [rbp+5Fh]; this
0x1800313ec  mov     r9d, edi; char *
0x1800313ef  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800313f6  mov     edx, 3Ah ; ':'; void *
0x1800313fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031400  mov     eax, edi
0x180031402  jmp     loc_18003174A
0x180031407  mov     eax, 0FFFFFFFFh
0x18003140c  cmp     rdx, rax
0x18003140f  ja      loc_18003171F
0x180031415  mov     ebx, edx
0x180031417  xorps   xmm0, xmm0
0x18003141a  movdqu  xmmword ptr [rbp+57h+pbInput], xmm0
0x18003141f  mov     [rbp+57h+var_80], r13
0x180031423  test    edx, edx
0x180031425  jz      short loc_180031432
0x180031427  mov     edx, ebx
0x180031429  lea     rcx, [rbp+57h+pbInput]
0x18003142d  call    ?_Reallocate@?$vector@EV?$allocator@E@std@@@std@@IEAAX_K@Z; std::vector<uchar>::_Reallocate(unsigned __int64)
0x180031432  mov     rcx, r13
0x180031435  mov     rdi, [rbp+57h+pbInput]
0x180031439  test    rbx, rbx
0x18003143c  jz      short loc_18003144C
0x18003143e  mov     al, [rsi+rcx*2]
0x180031441  mov     [rdi+rcx], al
0x180031444  inc     rcx
0x180031447  cmp     rcx, rbx
0x18003144a  jb      short loc_18003143E
0x18003144c  mov     [rbp+57h+phAlgorithm], r13
0x180031450  xor     r9d, r9d; dwFlags
0x180031453  xor     r8d, r8d; pszImplementation
0x180031456  lea     rdx, pszAlgId; "MD5"
0x18003145d  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x180031461  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180031467  test    eax, eax
0x180031469  jns     short loc_1800314AE
0x18003146b  mov     edx, 49h ; 'I'; void *
0x180031470  mov     r9d, eax; char *
0x180031473  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18003147a  mov     rcx, [rbp+5Fh]; this
0x18003147e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180031483  mov     ebx, eax
0x180031485  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180031489  test    rcx, rcx
0x18003148c  jz      short loc_180031497
0x18003148e  xor     edx, edx; dwFlags
0x180031490  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180031496  nop
0x180031497  test    rdi, rdi
0x18003149a  jz      loc_180031748
0x1800314a0  mov     rcx, rdi
0x1800314a3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800314a9  jmp     loc_180031748
0x1800314ae  mov     [rbp+57h+pbOutput], r13d
0x1800314b2  mov     r9d, 4; cbOutput
0x1800314b8  mov     [rbp+57h+arg_8], r9d
0x1800314bc  mov     [rsp+0F0h+dwFlags], r13d; dwFlags
0x1800314c1  lea     rax, [rbp+57h+arg_8]
0x1800314c5  mov     [rsp+0F0h+pcbResult], rax; pcbResult
0x1800314ca  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x1800314ce  lea     rdx, pszProperty; "ObjectLength"
0x1800314d5  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x1800314d9  call    cs:__imp_BCryptGetProperty
0x1800314df  test    eax, eax
0x1800314e1  jns     short loc_1800314EA
0x1800314e3  mov     edx, 4Fh ; 'O'
0x1800314e8  jmp     short loc_180031470
0x1800314ea  xorps   xmm0, xmm0
0x1800314ed  movdqu  xmmword ptr [rbp+57h+pbHashObject], xmm0
0x1800314f2  mov     [rbp+57h+var_68], r13
0x1800314f6  mov     r9d, [rbp+57h+pbOutput]
0x1800314fa  mov     edx, r9d
0x1800314fd  test    r9d, r9d
0x180031500  jz      short loc_18003150F
0x180031502  lea     rcx, [rbp+57h+pbHashObject]
0x180031506  call    ?_Reallocate@?$vector@EV?$allocator@E@std@@@std@@IEAAX_K@Z; std::vector<uchar>::_Reallocate(unsigned __int64)
0x18003150b  mov     r9d, [rbp+57h+pbOutput]; cbHashObject
0x18003150f  mov     rsi, [rbp+57h+pbHashObject]
0x180031513  mov     [rbp+57h+phHash], r13
0x180031517  mov     [rsp+0F0h+var_C0], r13d; dwFlags
0x18003151c  mov     [rsp+0F0h+dwFlags], r13d; cbSecret
0x180031521  mov     [rsp+0F0h+pcbResult], r13; int
0x180031526  mov     r8, rsi; pbHashObject
0x180031529  lea     rdx, [rbp+57h+phHash]; phHash
0x18003152d  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180031531  call    cs:__imp_BCryptCreateHash
0x180031537  test    eax, eax
0x180031539  jns     short loc_18003157C
0x18003153b  mov     edx, 56h ; 'V'; void *
0x180031540  mov     r9d, eax; char *
0x180031543  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18003154a  mov     rcx, [rbp+5Fh]; this
0x18003154e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180031553  mov     ebx, eax
0x180031555  mov     rcx, [rbp+57h+phHash]; hHash
0x180031559  test    rcx, rcx
0x18003155c  jz      short loc_180031565
0x18003155e  call    cs:__imp_BCryptDestroyHash
0x180031564  nop
0x180031565  test    rsi, rsi
0x180031568  jz      loc_180031485
0x18003156e  mov     rcx, rsi
0x180031571  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180031577  jmp     loc_180031485
0x18003157c  xor     r9d, r9d; dwFlags
0x18003157f  mov     r8d, ebx; cbInput
0x180031582  mov     rdx, rdi; pbInput
0x180031585  mov     rcx, [rbp+57h+phHash]; hHash
0x180031589  call    cs:__imp_BCryptHashData
0x18003158f  test    eax, eax
0x180031591  jns     short loc_18003159A
0x180031593  mov     edx, 57h ; 'W'
0x180031598  jmp     short loc_180031540
0x18003159a  xorps   xmm0, xmm0
0x18003159d  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x1800315a2  mov     [rbp+57h+var_50], r13
0x1800315a6  mov     ebx, 10h
0x1800315ab  mov     edx, ebx
0x1800315ad  lea     rcx, [rbp+57h+var_60]
0x1800315b1  call    ?_Reallocate@?$vector@EV?$allocator@E@std@@@std@@IEAAX_K@Z; std::vector<uchar>::_Reallocate(unsigned __int64)
0x1800315b6  xor     r9d, r9d; dwFlags
0x1800315b9  mov     r8d, ebx; cbOutput
0x1800315bc  mov     r15, [rbp+57h+var_60]
0x1800315c0  mov     rdx, r15; pbOutput
0x1800315c3  mov     rcx, [rbp+57h+phHash]; hHash
0x1800315c7  call    cs:__imp_BCryptFinishHash
0x1800315cd  test    eax, eax
0x1800315cf  jns     short loc_180031600
0x1800315d1  mov     rcx, [rbp+5Fh]; this
0x1800315d5  mov     r9d, eax; char *
0x1800315d8  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800315df  lea     edx, [rbx+4Dh]; void *
0x1800315e2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800315e7  mov     ebx, eax
0x1800315e9  test    r15, r15
0x1800315ec  jz      loc_180031555
0x1800315f2  mov     rcx, r15
0x1800315f5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800315fb  jmp     loc_180031555
0x180031600  mov     edx, 21h ; '!'
0x180031605  mov     [rbp+57h+arg_10], edx
0x180031608  xorps   xmm0, xmm0
0x18003160b  movdqu  xmmword ptr [rbp+57h+Src], xmm0
0x180031610  mov     [rbp+57h+var_98], r13
0x180031614  lea     rcx, [rbp+57h+Src]
0x180031618  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003161d  mov     dword ptr [rsp+0F0h+pcbResult], 1; int
0x180031625  lea     r9, [rbp+57h+arg_10]
0x180031629  mov     r14, [rbp+57h+Src]
0x18003162d  mov     r8, r14
0x180031630  mov     edx, ebx
0x180031632  mov     rcx, r15
0x180031635  call    cs:__imp_BinaryToHexString
0x18003163b  mov     ebx, eax
0x18003163d  test    eax, eax
0x18003163f  jns     short loc_18003166D
0x180031641  mov     rcx, [rbp+5Fh]; this
0x180031645  mov     r9d, eax; char *
0x180031648  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18003164f  mov     edx, 63h ; 'c'; void *
0x180031654  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031659  nop
0x18003165a  test    r14, r14
0x18003165d  jz      short loc_1800315E9
0x18003165f  mov     rcx, r14
0x180031662  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180031668  jmp     loc_1800315E9
0x18003166d  cmp     r14, [rbp+57h+Src+8]
0x180031671  jz      short loc_18003169E
0x180031673  mov     r13, r14
0x180031676  mov     rbx, r14
0x180031679  movzx   ecx, word ptr [r13+0]
0x18003167e  mov     rax, cs:__imp_towlower
0x180031685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003168a  mov     [rbx], ax
0x18003168d  lea     rbx, [rbx+2]
0x180031691  add     r13, 2
0x180031695  cmp     r13, [rbp+57h+Src+8]
0x180031699  jnz     short loc_180031679
0x18003169b  xor     r13d, r13d
0x18003169e  cmp     [r14], r13w
0x1800316a2  jnz     short loc_1800316A9
0x1800316a4  mov     r8, r13
0x1800316a7  jmp     short loc_1800316B7
0x1800316a9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800316ad  inc     r8
0x1800316b0  cmp     [r14+r8*2], r13w
0x1800316b5  jnz     short loc_1800316AD
0x1800316b7  mov     rdx, r14; Src
0x1800316ba  mov     rcx, r12; void *
0x1800316bd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800316c2  nop
0x1800316c3  mov     rcx, r14
0x1800316c6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800316cc  nop
0x1800316cd  test    r15, r15
0x1800316d0  jz      short loc_1800316DC
0x1800316d2  mov     rcx, r15
0x1800316d5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800316db  nop
0x1800316dc  mov     rcx, [rbp+57h+phHash]; hHash
0x1800316e0  test    rcx, rcx
0x1800316e3  jz      short loc_1800316EC
0x1800316e5  call    cs:__imp_BCryptDestroyHash
0x1800316eb  nop
0x1800316ec  test    rsi, rsi
0x1800316ef  jz      short loc_1800316FB
0x1800316f1  mov     rcx, rsi
0x1800316f4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800316fa  nop
0x1800316fb  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800316ff  test    rcx, rcx
0x180031702  jz      short loc_18003170D
0x180031704  xor     edx, edx; dwFlags
0x180031706  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18003170c  nop
0x18003170d  test    rdi, rdi
0x180031710  jz      short loc_18003171B
0x180031712  mov     rcx, rdi
0x180031715  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003171b  xor     eax, eax
0x18003171d  jmp     short loc_18003174A
0x18003171f  mov     ebx, 80070216h
0x180031724  mov     edx, 3Dh ; '='
0x180031729  jmp     short loc_180031735
0x18003172b  mov     ebx, 80070057h
0x180031730  mov     edx, 39h ; '9'; void *
0x180031735  mov     r9d, ebx; char *
0x180031738  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18003173f  mov     rcx, [rbp+5Fh]; this
0x180031743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031748  mov     eax, ebx
0x18003174a  add     rsp, 0B8h
0x180031751  pop     r15
0x180031753  pop     r14
0x180031755  pop     r13
0x180031757  pop     r12
0x180031759  pop     rdi
0x18003175a  pop     rsi
0x18003175b  pop     rbx
0x18003175c  pop     rbp
0x18003175d  retn
```
