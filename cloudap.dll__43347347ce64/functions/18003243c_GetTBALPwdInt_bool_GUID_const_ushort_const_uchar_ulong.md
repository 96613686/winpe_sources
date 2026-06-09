# GetTBALPwdInt(bool,_GUID const *,ushort const *,uchar * *,ulong *)

- ea: `0x18003243c`
- end: `0x1800327b8`
- name: `?GetTBALPwdInt@@YAJ_NPEBU_GUID@@PEBGPEAPEAEPEAK@Z`
- size: `892`
- prototype: `int(bool, const struct _GUID *, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800322e4`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18002d71c`
- `0x18003243c`
- `0x180043340`
- `0x18005b110`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032797`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032797`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032789`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032789`
- `ntdll!RtlInitUnicodeString` at `0x1800324fc`
- `ntdll!RtlInitUnicodeString` at `0x1800324fc`
- `LSASRV!LsarClose` at `0x18003272e`
- `LSASRV!LsarClose` at `0x18003272e`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x18003275d`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x18003275d`
- `LSASRV!LsarQuerySecret` at `0x18003256a`
- `LSASRV!LsarQuerySecret` at `0x18003256a`
- `LSASRV!LsarOpenSecret` at `0x180032517`
- `LSASRV!LsarOpenSecret` at `0x180032517`
- `ext-ms-win-cloudap-tbal-l1-1-0!TbalUnsealBuffer` at `0x180032609`
- `ext-ms-win-cloudap-tbal-l1-1-0!TbalUnsealBuffer` at `0x180032609`

## string_xrefs

- `0x1800324b0`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x180032523`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18003257d`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x180032615`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x180032677`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x1800326c7`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18003253e`: `LsarOpenSecret`

## pseudocode

```c
__int64 __fastcall GetTBALPwdInt(
        bool a1,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  unsigned int *v5; // rsi
  char v7; // r15
  unsigned int LSASecretName; // eax
  PCWSTR v9; // rdi
  unsigned int v10; // ebx
  const char *v11; // r9
  const char *v12; // rax
  bool v13; // zf
  const char *v14; // r9
  const char *v15; // r9
  const char *v16; // rax
  bool v17; // zf
  const char *v18; // r9
  __int64 v19; // rcx
  unsigned __int8 *v20; // rax
  const char *v21; // r9
  const char *v22; // r9
  _BYTE *v23; // rax
  __int64 v24; // rdx
  _BYTE *v25; // rdi
  __int64 v26; // rax
  HANDLE ProcessHeap; // rax
  bool v29[8]; // [rsp+20h] [rbp-50h]
  bool v30[8]; // [rsp+20h] [rbp-50h]
  unsigned int *v31; // [rsp+40h] [rbp-30h] BYREF
  void *Src; // [rsp+48h] [rbp-28h] BYREF
  __int64 v33; // [rsp+50h] [rbp-20h] BYREF
  PCWSTR SourceString; // [rsp+58h] [rbp-18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  size_t Size; // [rsp+B8h] [rbp+48h] BYREF

  v5 = a5;
  *a4 = 0;
  LODWORD(Size) = 0;
  *v5 = 0;
  v31 = 0;
  v33 = 0;
  SourceString = 0;
  Src = 0;
  v7 = 0;
  DestinationString = 0;
  LSASecretName = GetLSASecretName(a2, a3, (unsigned __int16 **)&SourceString, 0, a1);
  v9 = SourceString;
  v10 = LSASecretName;
  if ( LSASecretName )
  {
    v11 = "";
    while ( 1 )
    {
      v12 = v11--;
      v13 = *v11 == 92;
      if ( *v11 == 92 )
        break;
      if ( v11 <= "onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp" )
      {
        v13 = *v11 == 92;
        break;
      }
    }
    if ( v13 )
      v11 = v12;
    *(_DWORD *)v29 = 421;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v11, *(_QWORD *)v29, "GetLSASecretName", &Class);
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    v10 = LsarOpenSecret(g_LsaPolicyHandle, &DestinationString, 2, &v33);
    if ( v10 )
    {
      v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
      *(_DWORD *)v29 = 429;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v14, *(_QWORD *)v29, "LsarOpenSecret", &Class);
      goto LABEL_32;
    }
    v10 = LsarQuerySecret(v33, &v31, 0, 0, 0);
    if ( v10 )
    {
      v15 = "";
      while ( 1 )
      {
        v16 = v15--;
        v17 = *v15 == 92;
        if ( *v15 == 92 )
          break;
        if ( v15 <= "onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp" )
        {
          v17 = *v15 == 92;
          break;
        }
      }
      if ( v17 )
        v15 = v16;
      *(_DWORD *)v30 = 437;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v15, *(_QWORD *)v30, "LsarQuerySecret", &Class);
    }
    else if ( v31 && *((_QWORD *)v31 + 1) && *v31 )
    {
      if ( !(unsigned __int8)IsTbalSealBufferPresent() || IsHyperVGuestOS() )
      {
        Src = (void *)*((_QWORD *)v31 + 1);
        v19 = *v31;
        LODWORD(Size) = *v31;
      }
      else
      {
        v7 = 1;
        v10 = TbalUnsealBuffer(*((_QWORD *)v31 + 1), *v31, &Src, &Size);
        if ( v10 )
        {
          v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
          *(_DWORD *)v30 = 453;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v18, *(_QWORD *)v30, "TbalUnsealBuffer", &Class);
          goto LABEL_32;
        }
        v19 = (unsigned int)Size;
      }
      v20 = (unsigned __int8 *)((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(v19);
      *a4 = v20;
      if ( v20 )
      {
        memcpy_0(v20, Src, (unsigned int)Size);
        v10 = 0;
        *v5 = Size;
      }
      else
      {
        v10 = -1073741801;
        v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
        *(_DWORD *)v30 = 465;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v21, *(_QWORD *)v30, "AllocateLsaHeap", &Class);
      }
    }
    else
    {
      v10 = -1073740943;
      v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
      *(_DWORD *)v30 = 444;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221226353LL, v22, *(_QWORD *)v30, "No TBAL Secret", &Class);
    }
  }
LABEL_32:
  if ( v9 )
    ((void (__fastcall *)(PCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v9);
  if ( v33 )
    LsarClose(&v33);
  if ( v31 )
  {
    v23 = (_BYTE *)*((_QWORD *)v31 + 1);
    if ( v23 )
    {
      v24 = *v31;
      if ( *v31 )
      {
        do
        {
          *v23++ = 0;
          --v24;
        }
        while ( v24 );
      }
    }
    LsaIFree_LSAPR_CR_CIPHER_VALUE();
  }
  if ( v7 )
  {
    v25 = Src;
    if ( Src )
    {
      v26 = (unsigned int)Size;
      if ( (_DWORD)Size )
      {
        do
        {
          *v25++ = 0;
          --v26;
        }
        while ( v26 );
        v25 = Src;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v25);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18003243c  mov     [rsp-28h+arg_0], rbx
0x180032441  mov     [rsp-28h+arg_8], rsi
0x180032446  push    rbp
0x180032447  push    rdi
0x180032448  push    r12
0x18003244a  push    r14
0x18003244c  push    r15
0x18003244e  mov     rbp, rsp
0x180032451  sub     rsp, 70h
0x180032455  mov     rsi, [rbp+arg_20]
0x180032459  xor     r12d, r12d
0x18003245c  mov     rax, r8
0x18003245f  mov     [r9], r12
0x180032462  mov     r10, rdx
0x180032465  mov     [rsp+70h+var_50], cl; bool
0x180032469  mov     r14, r9
0x18003246c  mov     dword ptr [rbp+Size], r12d
0x180032470  xorps   xmm0, xmm0
0x180032473  mov     [rsi], r12d
0x180032476  xor     r9d, r9d; bool
0x180032479  mov     [rbp+var_30], r12
0x18003247d  lea     r8, [rbp+SourceString]; unsigned __int16 **
0x180032481  mov     [rbp+var_20], r12
0x180032485  mov     rdx, rax; unsigned __int16 *
0x180032488  mov     [rbp+SourceString], r12
0x18003248c  mov     rcx, r10; Uuid
0x18003248f  mov     [rbp+Src], r12
0x180032493  mov     r15b, r12b
0x180032496  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003249a  call    ?GetLSASecretName@@YAJPEBU_GUID@@PEBGPEAPEAG_N3@Z; GetLSASecretName(_GUID const *,ushort const *,ushort * *,bool,bool)
0x18003249f  mov     rdi, [rbp+SourceString]
0x1800324a3  mov     ebx, eax
0x1800324a5  test    eax, eax
0x1800324a7  jz      short loc_1800324F5
0x1800324a9  lea     r9, aOnecoreDsExtCl_8+23h; ""
0x1800324b0  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x1800324b7  mov     rax, r9
0x1800324ba  dec     r9
0x1800324bd  cmp     byte ptr [r9], 5Ch ; '\'
0x1800324c1  jz      short loc_1800324CC
0x1800324c3  cmp     r9, rcx
0x1800324c6  ja      short loc_1800324B7
0x1800324c8  cmp     byte ptr [r9], 5Ch ; '\'
0x1800324cc  cmovz   r9, rax
0x1800324d0  lea     rax, Class
0x1800324d7  mov     [rsp+70h+var_40], rax
0x1800324dc  lea     rax, aGetlsasecretna; "GetLSASecretName"
0x1800324e3  mov     [rsp+70h+var_48], rax
0x1800324e8  mov     dword ptr [rsp+70h+var_50], 1A5h
0x1800324f0  jmp     loc_1800326FB
0x1800324f5  mov     rdx, rdi; SourceString
0x1800324f8  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800324fc  call    cs:__imp_RtlInitUnicodeString
0x180032502  mov     rcx, cs:?g_LsaPolicyHandle@@3PEAXEA; void * g_LsaPolicyHandle
0x180032509  lea     r9, [rbp+var_20]
0x18003250d  mov     r8d, 2
0x180032513  lea     rdx, [rbp+DestinationString]
0x180032517  call    cs:__imp_LsarOpenSecret
0x18003251d  mov     ebx, eax
0x18003251f  test    eax, eax
0x180032521  jz      short loc_180032557
0x180032523  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18003252a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003252f  mov     r9, rax
0x180032532  lea     rax, Class
0x180032539  mov     [rsp+70h+var_40], rax
0x18003253e  lea     rax, aLsaropensecret_0; "LsarOpenSecret"
0x180032545  mov     [rsp+70h+var_48], rax
0x18003254a  mov     dword ptr [rsp+70h+var_50], 1ADh
0x180032552  jmp     loc_1800326FB
0x180032557  mov     rcx, [rbp+var_20]
0x18003255b  lea     rdx, [rbp+var_30]
0x18003255f  xor     r9d, r9d
0x180032562  mov     qword ptr [rsp+70h+var_50], r12
0x180032567  xor     r8d, r8d
0x18003256a  call    cs:__imp_LsarQuerySecret
0x180032570  mov     ebx, eax
0x180032572  test    eax, eax
0x180032574  jz      short loc_1800325C2
0x180032576  lea     r9, aOnecoreDsExtCl_8+23h; ""
0x18003257d  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x180032584  mov     rax, r9
0x180032587  dec     r9
0x18003258a  cmp     byte ptr [r9], 5Ch ; '\'
0x18003258e  jz      short loc_180032599
0x180032590  cmp     r9, rcx
0x180032593  ja      short loc_180032584
0x180032595  cmp     byte ptr [r9], 5Ch ; '\'
0x180032599  cmovz   r9, rax
0x18003259d  lea     rax, Class
0x1800325a4  mov     [rsp+70h+var_40], rax
0x1800325a9  lea     rax, aLsarquerysecre; "LsarQuerySecret"
0x1800325b0  mov     [rsp+70h+var_48], rax
0x1800325b5  mov     dword ptr [rsp+70h+var_50], 1B5h
0x1800325bd  jmp     loc_1800326FB
0x1800325c2  mov     rax, [rbp+var_30]
0x1800325c6  test    rax, rax
0x1800325c9  jz      loc_1800326C7
0x1800325cf  cmp     [rax+8], r12
0x1800325d3  jz      loc_1800326C7
0x1800325d9  cmp     [rax], r12d
0x1800325dc  jz      loc_1800326C7
0x1800325e2  call    IsTbalSealBufferPresent
0x1800325e7  test    al, al
0x1800325e9  jz      short loc_18003264E
0x1800325eb  call    ?IsHyperVGuestOS@@YA_NXZ; IsHyperVGuestOS(void)
0x1800325f0  test    al, al
0x1800325f2  jnz     short loc_18003264E
0x1800325f4  mov     rcx, [rbp+var_30]
0x1800325f8  lea     r9, [rbp+Size]
0x1800325fc  lea     r8, [rbp+Src]
0x180032600  mov     r15b, 1
0x180032603  mov     edx, [rcx]
0x180032605  mov     rcx, [rcx+8]
0x180032609  call    cs:__imp_TbalUnsealBuffer
0x18003260f  mov     ebx, eax
0x180032611  test    eax, eax
0x180032613  jz      short loc_180032649
0x180032615  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18003261c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180032621  mov     r9, rax
0x180032624  lea     rax, Class
0x18003262b  mov     [rsp+70h+var_40], rax
0x180032630  lea     rax, aTbalunsealbuff_0; "TbalUnsealBuffer"
0x180032637  mov     [rsp+70h+var_48], rax
0x18003263c  mov     dword ptr [rsp+70h+var_50], 1C5h
0x180032644  jmp     loc_1800326FB
0x180032649  mov     ecx, dword ptr [rbp+Size]
0x18003264c  jmp     short loc_18003265F
0x18003264e  mov     rcx, [rbp+var_30]
0x180032652  mov     rax, [rcx+8]
0x180032656  mov     [rbp+Src], rax
0x18003265a  mov     ecx, [rcx]
0x18003265c  mov     dword ptr [rbp+Size], ecx
0x18003265f  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180032666  mov     rax, [rax+28h]
0x18003266a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003266f  mov     [r14], rax
0x180032672  test    rax, rax
0x180032675  jnz     short loc_1800326AD
0x180032677  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18003267e  mov     ebx, 0C0000017h
0x180032683  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180032688  mov     r9, rax
0x18003268b  lea     rax, Class
0x180032692  mov     [rsp+70h+var_40], rax
0x180032697  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18003269e  mov     [rsp+70h+var_48], rax
0x1800326a3  mov     dword ptr [rsp+70h+var_50], 1D1h
0x1800326ab  jmp     short loc_1800326FB
0x1800326ad  mov     r8d, dword ptr [rbp+Size]; Size
0x1800326b1  mov     rcx, rax; void *
0x1800326b4  mov     rdx, [rbp+Src]; Src
0x1800326b8  call    memcpy_0
0x1800326bd  mov     eax, dword ptr [rbp+Size]
0x1800326c0  mov     ebx, r12d
0x1800326c3  mov     [rsi], eax
0x1800326c5  jmp     short loc_18003270C
0x1800326c7  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x1800326ce  mov     ebx, 0C0000371h
0x1800326d3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800326d8  mov     r9, rax
0x1800326db  lea     rax, Class
0x1800326e2  mov     [rsp+70h+var_40], rax
0x1800326e7  lea     rax, aNoTbalSecret; "No TBAL Secret"
0x1800326ee  mov     [rsp+70h+var_48], rax
0x1800326f3  mov     dword ptr [rsp+70h+var_50], 1BCh
0x1800326fb  mov     r8d, ebx
0x1800326fe  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180032705  xor     ecx, ecx
0x180032707  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003270c  test    rdi, rdi
0x18003270f  jz      short loc_180032724
0x180032711  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180032718  mov     rcx, rdi
0x18003271b  mov     rax, [rax+30h]
0x18003271f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032724  cmp     [rbp+var_20], r12
0x180032728  jz      short loc_180032734
0x18003272a  lea     rcx, [rbp+var_20]
0x18003272e  call    cs:__imp_LsarClose
0x180032734  mov     rcx, [rbp+var_30]
0x180032738  test    rcx, rcx
0x18003273b  jz      short loc_180032763
0x18003273d  mov     rax, [rcx+8]
0x180032741  test    rax, rax
0x180032744  jz      short loc_18003275D
0x180032746  mov     edx, [rcx]
0x180032748  test    rdx, rdx
0x18003274b  jz      short loc_18003275D
0x18003274d  mov     [rax], r12b
0x180032750  inc     rax
0x180032753  sub     rdx, 1
0x180032757  jnz     short loc_18003274D
0x180032759  mov     rcx, [rbp+var_30]
0x18003275d  call    cs:__imp_LsaIFree_LSAPR_CR_CIPHER_VALUE
0x180032763  test    r15b, r15b
0x180032766  jz      short loc_18003279D
0x180032768  mov     rdi, [rbp+Src]
0x18003276c  test    rdi, rdi
0x18003276f  jz      short loc_18003279D
0x180032771  mov     eax, dword ptr [rbp+Size]
0x180032774  test    rax, rax
0x180032777  jz      short loc_180032789
0x180032779  mov     [rdi], r12b
0x18003277c  inc     rdi
0x18003277f  sub     rax, 1
0x180032783  jnz     short loc_180032779
0x180032785  mov     rdi, [rbp+Src]
0x180032789  call    cs:__imp_GetProcessHeap
0x18003278f  mov     r8, rdi; lpMem
0x180032792  xor     edx, edx; dwFlags
0x180032794  mov     rcx, rax; hHeap
0x180032797  call    cs:__imp_HeapFree
0x18003279d  lea     r11, [rsp+70h+var_s0]
0x1800327a2  mov     eax, ebx
0x1800327a4  mov     rbx, [r11+30h]
0x1800327a8  mov     rsi, [r11+38h]
0x1800327ac  mov     rsp, r11
0x1800327af  pop     r15
0x1800327b1  pop     r14
0x1800327b3  pop     r12
0x1800327b5  pop     rdi
0x1800327b6  pop     rbp
0x1800327b7  retn
```
