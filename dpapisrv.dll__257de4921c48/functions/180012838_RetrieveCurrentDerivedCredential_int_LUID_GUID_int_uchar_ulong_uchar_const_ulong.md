# RetrieveCurrentDerivedCredential(int,_LUID *,_GUID *,int,uchar *,ulong,uchar * const,ulong *)

- ea: `0x180012838`
- end: `0x180012d11`
- name: `?RetrieveCurrentDerivedCredential@@YAKHPEAU_LUID@@PEAU_GUID@@HPEAEKQEAEPEAK@Z`
- size: `1241`
- prototype: `DWORD __fastcall(__int64, struct _LUID *, struct _GUID *, int, unsigned __int8 *, ULONG cbInput, unsigned __int8 *const pbOutput, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004e60`
- `0x180012710`

## callees

- `0x180001184`
- `0x180007f10`
- `0x18000c4a0`
- `0x180011710`
- `0x180012838`
- `0x180013f2c`
- `0x18001467c`
- `0x18001d810`
- `0x180029fcc`
- `0x18003e010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001293b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001293b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001292a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001292a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c22`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001291a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001291a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012c12`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012c12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800128fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800128fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012c35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012c35`
- `ntdll!RtlNtStatusToDosError` at `0x180012c47`
- `ntdll!RtlNtStatusToDosError` at `0x180012c47`
- `CRYPTSP!SystemFunction007` at `0x180012b1f`
- `CRYPTSP!SystemFunction007` at `0x180012b1f`

## string_xrefs

- `0x180012ada`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180012b35`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180012bf4`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
DWORD __fastcall RetrieveCurrentDerivedCredential(
        __int64 a1,
        struct _LUID *a2,
        struct _GUID *a3,
        int a4,
        unsigned __int8 *a5,
        ULONG cbInput,
        unsigned __int8 *const pbOutput,
        unsigned int *a8)
{
  PUCHAR v9; // rdx
  HANDLE CurrentThread; // rax
  DWORD LastError; // r12d
  NTSTATUS v15; // ebx
  __int64 v16; // rsi
  struct _GUID *v17; // rdx
  __int64 v18; // rax
  unsigned int *v19; // rbx
  unsigned int v20; // eax
  unsigned int v21; // ecx
  ULONG v22; // edx
  UCHAR *v23; // rcx
  UCHAR *v24; // rbx
  __int64 v25; // r9
  __int64 v26; // rcx
  UCHAR *v27; // rax
  unsigned int v28; // edi
  __int128 *v29; // rax
  __int64 v30; // rdi
  unsigned __int8 *v31; // r14
  __int64 v32; // rax
  __int64 v33; // r9
  __int64 v34; // rcx
  unsigned __int64 v35; // xmm0_8
  __int64 epi16; // rdx
  _BYTE *v37; // rax
  unsigned int *v38; // rcx
  __int64 v39; // rax
  unsigned int *v40; // [rsp+50h] [rbp-81h] BYREF
  __int64 v41; // [rsp+58h] [rbp-79h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-71h] BYREF
  PUCHAR pbInput; // [rsp+68h] [rbp-69h]
  __int128 v44; // [rsp+70h] [rbp-61h] BYREF
  __int128 v45; // [rsp+80h] [rbp-51h] BYREF
  UCHAR v46[16]; // [rsp+90h] [rbp-41h] BYREF
  int v47; // [rsp+A0h] [rbp-31h]

  v9 = a5;
  v41 = 0;
  pbInput = a5;
  v40 = 0;
  TokenHandle = 0;
  v44 = 0;
  v45 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    WPP_SF__guid_ddd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), a5, a3, a3, a2->LowPart, a2->HighPart, a4);
    v9 = pbInput;
  }
  *a8 = 0;
  if ( !cbInput || !v9 )
    return 87;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    return GetLastError();
  RevertToSelf();
  LastError = 0;
  v15 = -1073741637;
  v16 = 20;
  if ( !*((_QWORD *)g_pDPAPILsasrvIfTable + 13) )
    goto LABEL_51;
  v17 = 0;
  if ( a3 )
  {
    v18 = *(_QWORD *)&a3->Data1;
    if ( !*(_QWORD *)&a3->Data1 )
      v18 = *(_QWORD *)a3->Data4;
    if ( v18 )
      v17 = a3;
  }
  v15 = (*((__int64 (__fastcall **)(struct _LUID *, struct _GUID *, unsigned int **))g_pDPAPILsasrvIfTable + 13))(
          a2,
          v17,
          &v40);
  if ( v15 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        14,
        WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids,
        (unsigned int)v15);
LABEL_51:
    v33 = 305;
    v34 = (unsigned int)v15;
    goto LABEL_52;
  }
  v19 = v40;
  v20 = v40[3];
  if ( v20 > 0xFFFF || (v21 = v40[2], v21 > *v40) || v21 + v20 > *v40 )
  {
    v15 = -1073741811;
    v33 = 271;
    v34 = 3221225485LL;
LABEL_52:
    DebugTraceError(v34, "ntstatus", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v33);
    goto LABEL_53;
  }
  *a8 = v40[1];
  v22 = *((unsigned __int16 *)v19 + 6);
  LOWORD(v44) = v22;
  WORD1(v44) = v22;
  v23 = (UCHAR *)v19 + v19[2];
  *((_QWORD *)&v44 + 1) = v23;
  if ( a3 && (*((_QWORD *)v19 + 2) || *((_QWORD *)v19 + 3)) )
    *a3 = *((struct _GUID *)v19 + 1);
  *(_OWORD *)v46 = 0;
  v47 = 0;
  v45 = 0;
  if ( (v19[1] & 4) != 0 )
  {
    if ( a4 )
      v24 = (UCHAR *)(v19 + 8);
    else
      v24 = (UCHAR *)(v19 + 13);
    if ( !*(_QWORD *)v24
      && *((_QWORD *)v24 + 1) == _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0]
      && *((_DWORD *)v24 + 4) == (_DWORD)v41
      && (unsigned int)dword_18004C260 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
    {
      LODWORD(v41) = a4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (int)&dword_18004C260,
        (int)byte_180044AD9,
        0,
        v25,
        (__int64)&v41);
    }
    goto LABEL_38;
  }
  if ( a4 )
  {
    if ( (unsigned int)FMyPrimitiveSHA(v23, v22, v46) )
    {
      v24 = v46;
LABEL_38:
      v28 = 20;
      goto LABEL_44;
    }
    v15 = -1073283059;
    DebugTraceError(3221684237LL, "ntstatus", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", 354);
    v26 = 20;
    v27 = v46;
    do
    {
      *v27++ = 0;
      --v26;
    }
    while ( v26 );
  }
  else
  {
    if ( (int)SystemFunction007(&v44, &v45) >= 0 )
    {
      v24 = (UCHAR *)&v45;
      v28 = 16;
LABEL_44:
      v31 = pbOutput;
      DeriveWithHMAC_SHA1(v24, v28, pbInput, cbInput, pbOutput);
      v32 = v28;
      do
      {
        *v24++ = 0;
        --v32;
      }
      while ( v32 );
      v15 = 0;
      goto LABEL_54;
    }
    v15 = -1073283059;
    DebugTraceError(3221684237LL, "ntstatus", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", 374);
    v29 = &v45;
    v30 = 16;
    do
    {
      *(_BYTE *)v29 = 0;
      v29 = (__int128 *)((char *)v29 + 1);
      --v30;
    }
    while ( v30 );
  }
LABEL_53:
  v31 = pbOutput;
LABEL_54:
  if ( !SetThreadToken(0, TokenHandle) )
    LastError = GetLastError();
  CloseHandle(TokenHandle);
  if ( v15 < 0 )
    LastError = RtlNtStatusToDosError(v15);
  v35 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v35 )
  {
    epi16 = (unsigned int)_mm_extract_epi16((__m128i)0LL, 1);
    v37 = (_BYTE *)v35;
    if ( (_DWORD)epi16 )
    {
      do
      {
        *v37++ = 0;
        --epi16;
      }
      while ( epi16 );
    }
    (*((void (**)(void))g_pDPAPILsasrvIfTable + 3))();
  }
  v38 = v40;
  if ( v40 )
  {
    v39 = *v40;
    if ( *v40 )
    {
      do
      {
        *(_BYTE *)v38 = 0;
        v38 = (unsigned int *)((char *)v38 + 1);
        --v39;
      }
      while ( v39 );
    }
    (*((void (**)(void))g_pDPAPILsasrvIfTable + 3))();
  }
  if ( LastError )
  {
    do
    {
      *v31++ = 0;
      --v16;
    }
    while ( v16 );
  }
  return LastError;
}

```

## disassembly

```asm
0x180012838  mov     rax, rsp
0x18001283b  mov     [rax+8], rbx
0x18001283f  push    rbp
0x180012840  push    rsi
0x180012841  push    rdi
0x180012842  push    r12
0x180012844  push    r13
0x180012846  push    r14
0x180012848  push    r15
0x18001284a  lea     rbp, [rax-3Fh]
0x18001284e  sub     rsp, 0D0h
0x180012855  movaps  xmmword ptr [rax-48h], xmm6
0x180012859  movaps  xmmword ptr [rax-58h], xmm7
0x18001285d  mov     rax, cs:__security_cookie
0x180012864  xor     rax, rsp
0x180012867  mov     [rbp+37h+var_60], rax
0x18001286b  mov     rax, [rbp+37h+arg_30]
0x18001286f  xor     esi, esi
0x180012871  mov     r13, [rbp+37h+arg_38]
0x180012875  xorps   xmm0, xmm0
0x180012878  mov     [rsp+100h+var_C0], rax
0x18001287d  mov     r15, rdx
0x180012880  mov     rdx, [rbp+37h+arg_20]
0x180012884  xor     eax, eax
0x180012886  mov     [rbp+37h+var_B0], rax
0x18001288a  mov     r14d, r9d
0x18001288d  mov     rdi, r8
0x180012890  mov     [rbp+37h+pbInput], rdx
0x180012894  mov     [rsp+100h+var_B8], rsi
0x180012899  xorps   xmm7, xmm7
0x18001289c  mov     [rbp+37h+TokenHandle], rsi
0x1800128a0  xorps   xmm6, xmm6
0x1800128a3  movups  [rbp+37h+var_98], xmm0
0x1800128a7  movups  [rbp+37h+var_88], xmm0
0x1800128ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128b2  lea     rax, WPP_GLOBAL_Control
0x1800128b9  cmp     rcx, rax
0x1800128bc  jz      short loc_1800128E8
0x1800128be  test    byte ptr [rcx+1Ch], 4
0x1800128c2  jz      short loc_1800128E8
0x1800128c4  mov     eax, [r15+4]
0x1800128c8  mov     rcx, [rcx+10h]
0x1800128cc  mov     [rsp+100h+var_D0], r9d
0x1800128d1  mov     r9, r8
0x1800128d4  mov     [rsp+100h+var_D8], eax
0x1800128d8  mov     eax, [r15]
0x1800128db  mov     dword ptr [rsp+100h+pbOutput], eax
0x1800128df  call    WPP_SF__guid_ddd
0x1800128e4  mov     rdx, [rbp+37h+pbInput]
0x1800128e8  mov     [r13+0], esi
0x1800128ec  cmp     [rbp+37h+cbInput], esi
0x1800128ef  jz      loc_180012CDA
0x1800128f5  test    rdx, rdx
0x1800128f8  jz      loc_180012CDA
0x1800128fe  call    cs:__imp_GetCurrentThread
0x180012905  nop     dword ptr [rax+rax+00h]
0x18001290a  mov     edx, 4; DesiredAccess
0x18001290f  lea     r9, [rbp+37h+TokenHandle]; TokenHandle
0x180012913  mov     rcx, rax; ThreadHandle
0x180012916  lea     r8d, [rdx-3]; OpenAsSelf
0x18001291a  call    cs:__imp_OpenThreadToken
0x180012921  nop     dword ptr [rax+rax+00h]
0x180012926  test    eax, eax
0x180012928  jnz     short loc_18001293B
0x18001292a  call    cs:__imp_GetLastError
0x180012931  nop     dword ptr [rax+rax+00h]
0x180012936  jmp     loc_180012CDF
0x18001293b  call    cs:__imp_RevertToSelf
0x180012942  nop     dword ptr [rax+rax+00h]
0x180012947  mov     rax, cs:?g_pDPAPILsasrvIfTable@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pDPAPILsasrvIfTable
0x18001294e  mov     r12d, esi
0x180012951  mov     ebx, 0C00000BBh
0x180012956  mov     esi, 14h
0x18001295b  mov     r9, [rax+68h]
0x18001295f  test    r9, r9
0x180012962  jz      loc_180012BE9
0x180012968  xor     edx, edx
0x18001296a  test    rdi, rdi
0x18001296d  jz      short loc_18001298D
0x18001296f  mov     rax, [rdi]
0x180012972  sub     rax, cs:qword_180042E10
0x180012979  jnz     short loc_180012986
0x18001297b  mov     rax, [rdi+8]
0x18001297f  sub     rax, cs:qword_180042E18
0x180012986  test    rax, rax
0x180012989  cmovnz  rdx, rdi
0x18001298d  lea     r8, [rsp+100h+var_B8]
0x180012992  mov     rcx, r15
0x180012995  mov     rax, r9
0x180012998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001299d  xor     r15d, r15d
0x1800129a0  mov     ebx, eax
0x1800129a2  test    eax, eax
0x1800129a4  js      loc_180012BB6
0x1800129aa  mov     rbx, [rsp+100h+var_B8]
0x1800129af  mov     eax, [rbx+0Ch]
0x1800129b2  cmp     eax, 0FFFFh
0x1800129b7  ja      loc_180012BA4
0x1800129bd  mov     ecx, [rbx+8]
0x1800129c0  cmp     ecx, [rbx]
0x1800129c2  ja      loc_180012BA4
0x1800129c8  add     eax, ecx
0x1800129ca  cmp     eax, [rbx]
0x1800129cc  ja      loc_180012BA4
0x1800129d2  mov     eax, [rbx+4]
0x1800129d5  mov     [r13+0], eax
0x1800129d9  movzx   edx, word ptr [rbx+0Ch]; cbInput
0x1800129dd  mov     word ptr [rbp+37h+var_98], dx
0x1800129e1  mov     word ptr [rbp+37h+var_98+2], dx
0x1800129e5  mov     ecx, [rbx+8]
0x1800129e8  add     rcx, rbx; pbInput
0x1800129eb  mov     qword ptr [rbp+37h+var_98+8], rcx
0x1800129ef  test    rdi, rdi
0x1800129f2  jz      short loc_180012A16
0x1800129f4  mov     rax, cs:qword_180042E10
0x1800129fb  cmp     rax, [rbx+10h]
0x1800129ff  jnz     short loc_180012A0E
0x180012a01  mov     rax, cs:qword_180042E18
0x180012a08  cmp     rax, [rbx+18h]
0x180012a0c  jz      short loc_180012A16
0x180012a0e  movups  xmm0, xmmword ptr [rbx+10h]
0x180012a12  movdqu  xmmword ptr [rdi], xmm0
0x180012a16  xor     eax, eax
0x180012a18  xorps   xmm0, xmm0
0x180012a1b  movups  xmmword ptr [rbp+37h+var_78], xmm0
0x180012a1f  mov     [rbp+37h+var_68], eax
0x180012a22  movups  [rbp+37h+var_88], xmm0
0x180012a26  mov     eax, [rbx+4]
0x180012a29  test    al, 4
0x180012a2b  jz      loc_180012ABD
0x180012a31  test    r14d, r14d
0x180012a34  jz      short loc_180012A3C
0x180012a36  add     rbx, 20h ; ' '
0x180012a3a  jmp     short loc_180012A40
0x180012a3c  add     rbx, 34h ; '4'
0x180012a40  movq    rax, xmm6
0x180012a45  cmp     [rbx], rax
0x180012a48  jnz     loc_180012B13
0x180012a4e  psrldq  xmm6, 8
0x180012a53  movq    rax, xmm6
0x180012a58  cmp     [rbx+8], rax
0x180012a5c  jnz     loc_180012B13
0x180012a62  mov     rax, [rbp+37h+var_B0]
0x180012a66  cmp     [rbx+10h], eax
0x180012a69  jnz     loc_180012B13
0x180012a6f  mov     eax, cs:dword_18004C260
0x180012a75  cmp     eax, 5
0x180012a78  jbe     loc_180012B13
0x180012a7e  mov     rdx, 400000000000h
0x180012a88  lea     rcx, dword_18004C260
0x180012a8f  call    _tlgKeywordOn
0x180012a94  test    al, al
0x180012a96  jz      short loc_180012B13
0x180012a98  lea     rax, [rbp+37h+var_B0]
0x180012a9c  mov     dword ptr [rbp+37h+var_B0], r14d
0x180012aa0  xor     r8d, r8d
0x180012aa3  mov     [rsp+100h+pbOutput], rax
0x180012aa8  lea     rdx, byte_180044AD9
0x180012aaf  lea     rcx, dword_18004C260
0x180012ab6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180012abb  jmp     short loc_180012B13
0x180012abd  test    r14d, r14d
0x180012ac0  jz      short loc_180012B17
0x180012ac2  lea     rax, [rbp+37h+var_78]
0x180012ac6  mov     [rsp+100h+pbOutput], rax; PUCHAR
0x180012acb  call    FMyPrimitiveSHA
0x180012ad0  test    eax, eax
0x180012ad2  jnz     short loc_180012B0F
0x180012ad4  mov     r9d, 162h
0x180012ada  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180012ae1  lea     rdx, aNtstatus_0; "ntstatus"
0x180012ae8  mov     ecx, 0C007000Dh
0x180012aed  mov     ebx, 0C007000Dh
0x180012af2  call    DebugTraceError
0x180012af7  mov     rcx, rsi
0x180012afa  lea     rax, [rbp+37h+var_78]
0x180012afe  mov     [rax], r15b
0x180012b01  inc     rax
0x180012b04  sub     rcx, 1
0x180012b08  jnz     short loc_180012AFE
0x180012b0a  jmp     loc_180012C07
0x180012b0f  lea     rbx, [rbp+37h+var_78]
0x180012b13  mov     edi, esi
0x180012b15  jmp     short loc_180012B75
0x180012b17  lea     rdx, [rbp+37h+var_88]
0x180012b1b  lea     rcx, [rbp+37h+var_98]
0x180012b1f  call    cs:__imp_SystemFunction007
0x180012b26  nop     dword ptr [rax+rax+00h]
0x180012b2b  test    eax, eax
0x180012b2d  jns     short loc_180012B6C
0x180012b2f  mov     r9d, 176h
0x180012b35  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180012b3c  lea     rdx, aNtstatus_0; "ntstatus"
0x180012b43  mov     ecx, 0C007000Dh
0x180012b48  mov     ebx, 0C007000Dh
0x180012b4d  call    DebugTraceError
0x180012b52  lea     rax, [rbp+37h+var_88]
0x180012b56  mov     edi, 10h
0x180012b5b  mov     [rax], r15b
0x180012b5e  inc     rax
0x180012b61  sub     rdi, 1
0x180012b65  jnz     short loc_180012B5B
0x180012b67  jmp     loc_180012C07
0x180012b6c  lea     rbx, [rbp+37h+var_88]
0x180012b70  mov     edi, 10h
0x180012b75  mov     r14, [rsp+100h+var_C0]
0x180012b7a  mov     edx, edi; Size
0x180012b7c  mov     r9d, [rbp+37h+cbInput]; cbInput
0x180012b80  mov     rcx, rbx; Src
0x180012b83  mov     r8, [rbp+37h+pbInput]; pbInput
0x180012b87  mov     [rsp+100h+pbOutput], r14; pbOutput
0x180012b8c  call    DeriveWithHMAC_SHA1
0x180012b91  mov     eax, edi
0x180012b93  mov     [rbx], r15b
0x180012b96  inc     rbx
0x180012b99  sub     rax, 1
0x180012b9d  jnz     short loc_180012B93
0x180012b9f  mov     ebx, r15d
0x180012ba2  jmp     short loc_180012C0C
0x180012ba4  mov     ebx, 0C000000Dh
0x180012ba9  mov     r9d, 10Fh
0x180012baf  mov     ecx, 0C000000Dh
0x180012bb4  jmp     short loc_180012BF4
0x180012bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bbd  lea     rax, WPP_GLOBAL_Control
0x180012bc4  cmp     rcx, rax
0x180012bc7  jz      short loc_180012BEC
0x180012bc9  test    byte ptr [rcx+1Ch], 8
0x180012bcd  jz      short loc_180012BEC
0x180012bcf  mov     rcx, [rcx+10h]
0x180012bd3  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x180012bda  mov     edx, 0Eh
0x180012bdf  mov     r9d, ebx
0x180012be2  call    WPP_SF_d
0x180012be7  jmp     short loc_180012BEC
0x180012be9  xor     r15d, r15d
0x180012bec  mov     r9d, 131h
0x180012bf2  mov     ecx, ebx
0x180012bf4  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180012bfb  lea     rdx, aNtstatus_0; "ntstatus"
0x180012c02  call    DebugTraceError
0x180012c07  mov     r14, [rsp+100h+var_C0]
0x180012c0c  mov     rdx, [rbp+37h+TokenHandle]; Token
0x180012c10  xor     ecx, ecx; Thread
0x180012c12  call    cs:__imp_SetThreadToken
0x180012c19  nop     dword ptr [rax+rax+00h]
0x180012c1e  test    eax, eax
0x180012c20  jnz     short loc_180012C31
0x180012c22  call    cs:__imp_GetLastError
0x180012c29  nop     dword ptr [rax+rax+00h]
0x180012c2e  mov     r12d, eax
0x180012c31  mov     rcx, [rbp+37h+TokenHandle]; hObject
0x180012c35  call    cs:__imp_CloseHandle
0x180012c3c  nop     dword ptr [rax+rax+00h]
0x180012c41  test    ebx, ebx
0x180012c43  jns     short loc_180012C56
0x180012c45  mov     ecx, ebx; Status
0x180012c47  call    cs:__imp_RtlNtStatusToDosError
0x180012c4e  nop     dword ptr [rax+rax+00h]
0x180012c53  mov     r12d, eax
0x180012c56  movdqa  xmm0, xmm7
0x180012c5a  psrldq  xmm0, 8
0x180012c5f  movq    rcx, xmm0
0x180012c64  test    rcx, rcx
0x180012c67  jz      short loc_180012C92
0x180012c69  pextrw  edx, xmm7, 1
0x180012c6e  mov     rax, rcx
0x180012c71  test    rdx, rdx
0x180012c74  jz      short loc_180012C82
0x180012c76  mov     [rax], r15b
0x180012c79  inc     rax
0x180012c7c  sub     rdx, 1
0x180012c80  jnz     short loc_180012C76
0x180012c82  mov     rax, cs:?g_pDPAPILsasrvIfTable@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pDPAPILsasrvIfTable
0x180012c89  mov     rax, [rax+18h]
0x180012c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c92  mov     rcx, [rsp+100h+var_B8]
0x180012c97  test    rcx, rcx
0x180012c9a  jz      short loc_180012CC4
0x180012c9c  mov     eax, [rcx]
0x180012c9e  test    rax, rax
0x180012ca1  jz      short loc_180012CB4
0x180012ca3  mov     [rcx], r15b
0x180012ca6  inc     rcx
0x180012ca9  sub     rax, 1
0x180012cad  jnz     short loc_180012CA3
0x180012caf  mov     rcx, [rsp+100h+var_B8]
0x180012cb4  mov     rax, cs:?g_pDPAPILsasrvIfTable@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pDPAPILsasrvIfTable
0x180012cbb  mov     rax, [rax+18h]
0x180012cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cc4  test    r12d, r12d
0x180012cc7  jz      short loc_180012CD5
0x180012cc9  mov     [r14], r15b
0x180012ccc  inc     r14
0x180012ccf  sub     rsi, 1
0x180012cd3  jnz     short loc_180012CC9
0x180012cd5  mov     eax, r12d
0x180012cd8  jmp     short loc_180012CDF
0x180012cda  mov     eax, 57h ; 'W'
0x180012cdf  mov     rcx, [rbp+37h+var_60]
  ... truncated ...
```
