# NetpUpdateLSASecretCreds(int,ushort const *,ushort const *,ulong,uchar const *)

- ea: `0x18002aa50`
- end: `0x18002ae53`
- name: `?NetpUpdateLSASecretCreds@@YAJHPEBG0KPEBE@Z`
- size: `1027`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, const unsigned __int16 *, int, BYTE *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18000e270`
- `0x180029c34`
- `0x180029e00`
- `0x18002a3b0`
- `0x18002aa50`
- `0x18005ffb0`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002add2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002add2`
- `LSASRV!LsarClose` at `0x18002ae14`
- `LSASRV!LsarClose` at `0x18002ae14`
- `LSASRV!LsarCreateSecret` at `0x18002abfe`
- `LSASRV!LsarCreateSecret` at `0x18002abfe`
- `LSASRV!LsarSetSecret` at `0x18002acb1`
- `LSASRV!LsarSetSecret` at `0x18002ad77`
- `LSASRV!LsarSetSecret` at `0x18002acb1`
- `LSASRV!LsarSetSecret` at `0x18002ad77`
- `LSASRV!LsarOpenSecret` at `0x18002aba7`
- `LSASRV!LsarOpenSecret` at `0x18002aba7`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002ab77`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002ab77`
- `ntdll!RtlInitUnicodeString` at `0x18002ab16`
- `ntdll!RtlInitUnicodeString` at `0x18002ab16`
- `ntdll!RtlReleaseResource` at `0x18002adc4`
- `ntdll!RtlReleaseResource` at `0x18002adc4`

## string_xrefs

- `0x18002ac2b`: `LsarOpenSecret failed 0x%08X\n`
- `0x18002aaa1`: `Entering NetpUpdateLSASecretCreds\n`
- `0x18002ab30`: `onecore\ds\netapi\svcdlls\logonsrv\server\groupsvcacct.cxx`
- `0x18002ac0e`: `LsarCreateSecret failed 0x%08X\n`
- `0x18002ae1d`: `Exiting NetpUpdateLSASecretCreds with Status 0x%08X\n`

## pseudocode

```c
__int64 __fastcall NetpUpdateLSASecretCreds(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        BYTE *a5)
{
  BYTE *v5; // r12
  unsigned int v10; // r14d
  unsigned __int8 *v11; // rsi
  int SecretName; // eax
  WCHAR *v13; // r13
  unsigned int v14; // ebx
  const WCHAR *v15; // rdx
  char *v16; // r9
  int v17; // eax
  const wchar_t *v18; // r8
  int v19; // eax
  int LSASecretCreds; // eax
  int v21; // eax
  __int64 (__fastcall *v22)(const unsigned __int16 *, const unsigned __int16 *, _WORD *, __int128 *); // rax
  int v23; // eax
  int v24; // ebx
  int v25; // edi
  int v26; // eax
  __int64 v27; // rcx
  unsigned __int8 *v28; // rax
  unsigned int v30; // [rsp+30h] [rbp-D0h] BYREF
  void *v31; // [rsp+38h] [rbp-C8h] BYREF
  PCWSTR SourceString; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v33; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int8 *v34; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v35; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v36[2]; // [rsp+70h] [rbp-90h] BYREF
  int v37; // [rsp+74h] [rbp-8Ch]
  unsigned __int8 *v38; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v39; // [rsp+80h] [rbp-80h]
  const unsigned __int16 *v40; // [rsp+88h] [rbp-78h]
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  BYTE pbBuffer[240]; // [rsp+A0h] [rbp-60h] BYREF

  v5 = a5;
  v40 = a2;
  v39 = a3;
  v37 = 0;
  v30 = 0;
  v31 = 0;
  SourceString = 0;
  v34 = 0;
  DestinationString = 0;
  v10 = 0;
  v11 = 0;
  v35 = 0;
  v33 = 0;
  NlPrintRoutine(0x40u, L"Entering NetpUpdateLSASecretCreds\n");
  SecretName = NetpGetSecretName(a1, a2, a3, (unsigned __int16 **)&SourceString);
  v13 = (WCHAR *)SourceString;
  v14 = SecretName;
  if ( SecretName < 0 )
  {
    NlPrintRoutine(0x40u, L"NetpGetSecretName failed 0x%08X\n", (unsigned int)SecretName);
    goto LABEL_37;
  }
  v15 = SourceString;
  LODWORD(SourceString) = 0;
  RtlInitUnicodeString(&DestinationString, v15);
  if ( a1 )
  {
    if ( a5 || a4 )
      NlAssertFailed(
        "NULL == pbData && 0 == cbData",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\groupsvcacct.cxx",
        0x1BFu,
        v16);
    LOWORD(a4) = 240;
    if ( !NlGenerateRandomBits(pbBuffer, 0xF0u) )
    {
      v14 = -1073741595;
      NlPrintRoutine(0x40u, L"NlGenerateRandomBits failed 0x%08X\n", 3221225701LL);
      goto LABEL_37;
    }
    v5 = pbBuffer;
    RtlAcquireResourceExclusive(&NlGlobalGMSADPAPILock, 1u);
    dword_1800F0D10 = GetCurrentThreadId();
    LODWORD(SourceString) = 1;
  }
  v17 = LsarOpenSecret(NlGlobalLsaPolicyHandle, &DestinationString, 3, &v31);
  v14 = v17;
  if ( v17 != -1073741772 )
  {
    if ( v17 < 0 )
    {
      NlPrintRoutine(0x40u, L"LsarOpenSecret failed 0x%08X\n", (unsigned int)v17);
      goto LABEL_35;
    }
    if ( a1 )
    {
      LSASecretCreds = NetpFetchLSASecretCredsEx(v31, a1, 0, 0, &v30, &v34);
      v14 = LSASecretCreds;
      if ( LSASecretCreds < 0 )
      {
        NlPrintRoutine(0x40u, L"NetpFetchDPAPICreds failed 0x%08X\n", (unsigned int)LSASecretCreds);
        v10 = v30;
        v11 = v34;
        goto LABEL_35;
      }
      v10 = v30;
      v11 = v34;
    }
LABEL_23:
    a4 = (unsigned __int16)a4;
    DWORD1(v33) = a4;
    LODWORD(v33) = (unsigned __int16)a4;
    *((_QWORD *)&v33 + 1) = v5;
    v21 = LsarSetSecret(v31, &v33, 0);
    v14 = v21;
    if ( v21 >= 0 )
    {
      if ( !a1 )
        goto LABEL_34;
      if ( !v11 )
        goto LABEL_34;
      v36[1] = v10;
      v22 = (__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, _WORD *, __int128 *))*((_QWORD *)g_pLsaFunctions + 15);
      v36[0] = v10;
      v38 = v11;
      WORD1(v35) = a4;
      LOWORD(v35) = a4;
      *((_QWORD *)&v35 + 1) = v5;
      v23 = v22(v40, v39, v36, &v35);
      v24 = v23;
      if ( v23 < 0 )
      {
        NlPrintRoutine(0x40u, L"LsaIDPAPIPasswordChangeForGMSA failed 0x%08X\n", (unsigned int)v23);
        v25 = 0;
        DWORD1(v33) = (unsigned __int16)v10;
        LODWORD(v33) = (unsigned __int16)v10;
        if ( v24 != -1073741729 )
          v25 = v24;
        *((_QWORD *)&v33 + 1) = v11;
        v26 = LsarSetSecret(v31, &v33, 0);
        v14 = v26;
        if ( v26 >= 0
          || (NlPrintRoutine(0x40u, L"LsarSetSecret failed 0x%08X\n", (unsigned int)v26),
              !(unsigned int)IsFatalStatus(v14))
          || v25 < 0 )
        {
          v14 = v25;
        }
      }
      else
      {
LABEL_34:
        v14 = 0;
      }
    }
    else
    {
      NlPrintRoutine(0x40u, L"LsarSetSecret failed 0x%08X\n", (unsigned int)v21);
    }
    goto LABEL_35;
  }
  v18 = L"DPAPI";
  if ( !a1 )
    v18 = L"GMSA";
  NlPrintRoutine(0x40u, L"%ws Secret not found for %ws\\%ws\n", v18, v39, v40);
  v19 = LsarCreateSecret(NlGlobalLsaPolicyHandle, &DestinationString, 983043, &v31);
  v14 = v19;
  if ( v19 >= 0 )
    goto LABEL_23;
  NlPrintRoutine(0x40u, L"LsarCreateSecret failed 0x%08X\n", (unsigned int)v19);
LABEL_35:
  if ( (_DWORD)SourceString )
  {
    dword_1800F0D10 = -1;
    RtlReleaseResource(&NlGlobalGMSADPAPILock);
  }
LABEL_37:
  if ( v13 )
    LocalFree(v13);
  if ( v11 )
  {
    v27 = v10;
    v28 = v11;
    if ( v10 )
    {
      do
      {
        *v28++ = 0;
        --v27;
      }
      while ( v27 );
    }
    (*((void (__fastcall **)(unsigned __int8 *))g_pLsaFunctions + 3))(v11);
  }
  if ( v31 )
    LsarClose(&v31);
  NlPrintRoutine(0x40u, L"Exiting NetpUpdateLSASecretCreds with Status 0x%08X\n", v14);
  return v14;
}

```

## disassembly

```asm
0x18002aa50  push    rbp
0x18002aa52  push    rbx
0x18002aa53  push    rsi
0x18002aa54  push    rdi
0x18002aa55  push    r12
0x18002aa57  push    r13
0x18002aa59  push    r14
0x18002aa5b  push    r15
0x18002aa5d  lea     rbp, [rsp-0A8h]
0x18002aa65  sub     rsp, 1A8h
0x18002aa6c  mov     rax, cs:__security_cookie
0x18002aa73  xor     rax, rsp
0x18002aa76  mov     [rbp+0E0h+var_50], rax
0x18002aa7d  mov     r12, [rbp+0E0h+arg_20]
0x18002aa84  xor     eax, eax
0x18002aa86  xorps   xmm0, xmm0
0x18002aa89  mov     [rbp+0E0h+var_158], rdx
0x18002aa8d  mov     rbx, rdx
0x18002aa90  mov     [rbp+0E0h+var_160], r8
0x18002aa94  mov     edi, ecx
0x18002aa96  mov     dword ptr [rsp+1E0h+var_170+4], eax
0x18002aa9a  lea     ecx, [rax+40h]; unsigned int
0x18002aa9d  mov     [rsp+1E0h+var_1B0], eax
0x18002aaa1  lea     rdx, aEnteringNetpup; "Entering NetpUpdateLSASecretCreds\n"
0x18002aaa8  mov     [rsp+1E0h+var_1A8], rax
0x18002aaad  mov     r15d, r9d
0x18002aab0  mov     [rsp+1E0h+SourceString], rax
0x18002aab5  mov     r13, r8
0x18002aab8  mov     [rsp+1E0h+var_188], rax
0x18002aabd  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x18002aac1  mov     r14d, eax
0x18002aac4  mov     esi, eax
0x18002aac6  movups  [rsp+1E0h+var_180], xmm0
0x18002aacb  movups  [rsp+1E0h+var_198], xmm0
0x18002aad0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002aad5  lea     r9, [rsp+1E0h+SourceString]; unsigned __int16 **
0x18002aada  mov     r8, r13; unsigned __int16 *
0x18002aadd  mov     rdx, rbx; unsigned __int16 *
0x18002aae0  mov     ecx, edi; int
0x18002aae2  call    ?NetpGetSecretName@@YAJHPEBG0PEAPEAG@Z; NetpGetSecretName(int,ushort const *,ushort const *,ushort * *)
0x18002aae7  mov     r13, [rsp+1E0h+SourceString]
0x18002aaec  mov     ebx, eax
0x18002aaee  test    eax, eax
0x18002aaf0  jns     short loc_18002AB0B
0x18002aaf2  mov     r8d, eax
0x18002aaf5  lea     rdx, aNetpgetsecretn; "NetpGetSecretName failed 0x%08X\n"
0x18002aafc  mov     ecx, 40h ; '@'; unsigned int
0x18002ab01  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002ab06  jmp     loc_18002ADCA
0x18002ab0b  mov     rdx, r13; SourceString
0x18002ab0e  mov     dword ptr [rsp+1E0h+SourceString], esi
0x18002ab12  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x18002ab16  call    cs:__imp_RtlInitUnicodeString
0x18002ab1c  test    edi, edi
0x18002ab1e  jz      short loc_18002AB91
0x18002ab20  test    r12, r12
0x18002ab23  jnz     short loc_18002AB2A
0x18002ab25  test    r15d, r15d
0x18002ab28  jz      short loc_18002AB43
0x18002ab2a  mov     r8d, 1BFh; unsigned int
0x18002ab30  lea     rdx, aOnecoreDsNetap_22; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18002ab37  lea     rcx, aNullPbdata0Cbd; "NULL == pbData && 0 == cbData"
0x18002ab3e  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18002ab43  mov     r15d, 0F0h
0x18002ab49  lea     rcx, [rbp+0E0h+pbBuffer]; pbBuffer
0x18002ab4d  mov     edx, r15d; unsigned int
0x18002ab50  call    ?NlGenerateRandomBits@@YAEPEAEK@Z; NlGenerateRandomBits(uchar *,ulong)
0x18002ab55  test    al, al
0x18002ab57  jnz     short loc_18002AB6A
0x18002ab59  mov     ebx, 0C00000E5h
0x18002ab5e  lea     rdx, aNlgeneraterand; "NlGenerateRandomBits failed 0x%08X\n"
0x18002ab65  mov     r8d, ebx
0x18002ab68  jmp     short loc_18002AAFC
0x18002ab6a  mov     dl, 1; Wait
0x18002ab6c  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x18002ab73  lea     r12, [rbp+0E0h+pbBuffer]
0x18002ab77  call    cs:__imp_RtlAcquireResourceExclusive
0x18002ab7d  call    cs:__imp_GetCurrentThreadId
0x18002ab83  mov     cs:dword_1800F0D10, eax
0x18002ab89  mov     dword ptr [rsp+1E0h+SourceString], 1
0x18002ab91  mov     rcx, cs:?NlGlobalLsaPolicyHandle@@3PEAXEA; void * NlGlobalLsaPolicyHandle
0x18002ab98  lea     r9, [rsp+1E0h+var_1A8]
0x18002ab9d  mov     r8d, 3
0x18002aba3  lea     rdx, [rbp+0E0h+DestinationString]
0x18002aba7  call    cs:__imp_LsarOpenSecret
0x18002abad  mov     ebx, eax
0x18002abaf  cmp     eax, 0C0000034h
0x18002abb4  jnz     short loc_18002AC27
0x18002abb6  mov     r9, [rbp+0E0h+var_160]
0x18002abba  lea     rax, aGmsa; "GMSA"
0x18002abc1  test    edi, edi
0x18002abc3  lea     r8, aDpapi; "DPAPI"
0x18002abca  lea     rdx, aWsSecretNotFou; "%ws Secret not found for %ws\\%ws\n"
0x18002abd1  mov     ecx, 40h ; '@'; unsigned int
0x18002abd6  cmovz   r8, rax
0x18002abda  mov     rax, [rbp+0E0h+var_158]
0x18002abde  mov     [rsp+1E0h+var_1C0], rax
0x18002abe3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002abe8  mov     rcx, cs:?NlGlobalLsaPolicyHandle@@3PEAXEA; void * NlGlobalLsaPolicyHandle
0x18002abef  lea     r9, [rsp+1E0h+var_1A8]
0x18002abf4  mov     r8d, 0F0003h
0x18002abfa  lea     rdx, [rbp+0E0h+DestinationString]
0x18002abfe  call    cs:__imp_LsarCreateSecret
0x18002ac04  mov     ebx, eax
0x18002ac06  test    eax, eax
0x18002ac08  jns     loc_18002AC91
0x18002ac0e  lea     rdx, aLsarcreatesecr; "LsarCreateSecret failed 0x%08X\n"
0x18002ac15  mov     r8d, eax
0x18002ac18  mov     ecx, 40h ; '@'; unsigned int
0x18002ac1d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002ac22  jmp     loc_18002ADAC
0x18002ac27  test    eax, eax
0x18002ac29  jns     short loc_18002AC34
0x18002ac2b  lea     rdx, aLsaropensecret; "LsarOpenSecret failed 0x%08X\n"
0x18002ac32  jmp     short loc_18002AC15
0x18002ac34  test    edi, edi
0x18002ac36  jz      short loc_18002AC91
0x18002ac38  mov     rcx, [rsp+1E0h+var_1A8]; void *
0x18002ac3d  lea     rax, [rsp+1E0h+var_188]
0x18002ac42  mov     [rsp+1E0h+var_1B8], rax; unsigned __int8 **
0x18002ac47  xor     r9d, r9d; unsigned __int16 *
0x18002ac4a  lea     rax, [rsp+1E0h+var_1B0]
0x18002ac4f  xor     r8d, r8d; unsigned __int16 *
0x18002ac52  mov     edx, edi; int
0x18002ac54  mov     [rsp+1E0h+var_1C0], rax; unsigned int *
0x18002ac59  call    ?NetpFetchLSASecretCredsEx@@YAJPEAXHPEBG1PEAKPEAPEAE@Z; NetpFetchLSASecretCredsEx(void *,int,ushort const *,ushort const *,ulong *,uchar * *)
0x18002ac5e  mov     ebx, eax
0x18002ac60  test    eax, eax
0x18002ac62  jns     short loc_18002AC87
0x18002ac64  mov     r8d, eax
0x18002ac67  lea     rdx, aNetpfetchdpapi; "NetpFetchDPAPICreds failed 0x%08X\n"
0x18002ac6e  mov     ecx, 40h ; '@'; unsigned int
0x18002ac73  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002ac78  mov     r14d, [rsp+1E0h+var_1B0]
0x18002ac7d  mov     rsi, [rsp+1E0h+var_188]
0x18002ac82  jmp     loc_18002ADAC
0x18002ac87  mov     r14d, [rsp+1E0h+var_1B0]
0x18002ac8c  mov     rsi, [rsp+1E0h+var_188]
0x18002ac91  mov     rcx, [rsp+1E0h+var_1A8]
0x18002ac96  lea     rdx, [rsp+1E0h+var_198]
0x18002ac9b  movzx   r15d, r15w
0x18002ac9f  xor     r8d, r8d
0x18002aca2  mov     dword ptr [rsp+1E0h+var_198+4], r15d
0x18002aca7  mov     dword ptr [rsp+1E0h+var_198], r15d
0x18002acac  mov     qword ptr [rsp+1E0h+var_198+8], r12
0x18002acb1  call    cs:__imp_LsarSetSecret
0x18002acb7  mov     ebx, eax
0x18002acb9  test    eax, eax
0x18002acbb  jns     short loc_18002ACC9
0x18002acbd  lea     rdx, aLsarsetsecretF; "LsarSetSecret failed 0x%08X\n"
0x18002acc4  jmp     loc_18002AC15
0x18002acc9  test    edi, edi
0x18002accb  jz      loc_18002ADAA
0x18002acd1  test    rsi, rsi
0x18002acd4  jz      loc_18002ADAA
0x18002acda  mov     rax, cs:?g_pLsaFunctions@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pLsaFunctions
0x18002ace1  lea     r9, [rsp+1E0h+var_180]
0x18002ace6  mov     rdx, [rbp+0E0h+var_160]
0x18002acea  lea     r8, [rsp+1E0h+var_170]
0x18002acef  mov     rcx, [rbp+0E0h+var_158]
0x18002acf3  mov     word ptr [rsp+1E0h+var_170+2], r14w
0x18002acf9  mov     rax, [rax+78h]
0x18002acfd  mov     word ptr [rsp+1E0h+var_170], r14w
0x18002ad03  mov     qword ptr [rsp+1E0h+var_170+8], rsi
0x18002ad08  movaps  xmm1, [rsp+1E0h+var_170]
0x18002ad0d  mov     word ptr [rsp+1E0h+var_180+2], r15w
0x18002ad13  mov     word ptr [rsp+1E0h+var_180], r15w
0x18002ad19  mov     qword ptr [rsp+1E0h+var_180+8], r12
0x18002ad1e  movaps  xmm0, [rsp+1E0h+var_180]
0x18002ad23  movdqa  [rsp+1E0h+var_180], xmm0
0x18002ad29  movdqa  [rsp+1E0h+var_170], xmm1
0x18002ad2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad34  mov     ebx, eax
0x18002ad36  test    eax, eax
0x18002ad38  jns     short loc_18002ADAA
0x18002ad3a  mov     r8d, eax
0x18002ad3d  lea     rdx, aLsaidpapipassw; "LsaIDPAPIPasswordChangeForGMSA failed 0"...
0x18002ad44  mov     ecx, 40h ; '@'; unsigned int
0x18002ad49  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002ad4e  mov     rcx, [rsp+1E0h+var_1A8]
0x18002ad53  lea     rdx, [rsp+1E0h+var_198]
0x18002ad58  movzx   eax, r14w
0x18002ad5c  xor     edi, edi
0x18002ad5e  cmp     ebx, 0C000005Fh
0x18002ad64  mov     dword ptr [rsp+1E0h+var_198+4], eax
0x18002ad68  mov     dword ptr [rsp+1E0h+var_198], eax
0x18002ad6c  cmovnz  edi, ebx
0x18002ad6f  mov     qword ptr [rsp+1E0h+var_198+8], rsi
0x18002ad74  xor     r8d, r8d
0x18002ad77  call    cs:__imp_LsarSetSecret
0x18002ad7d  mov     ebx, eax
0x18002ad7f  test    eax, eax
0x18002ad81  jns     short loc_18002ADA6
0x18002ad83  mov     r8d, eax
0x18002ad86  lea     rdx, aLsarsetsecretF; "LsarSetSecret failed 0x%08X\n"
0x18002ad8d  mov     ecx, 40h ; '@'; unsigned int
0x18002ad92  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002ad97  mov     ecx, ebx; int
0x18002ad99  call    ?IsFatalStatus@@YAHJ@Z; IsFatalStatus(long)
0x18002ad9e  test    eax, eax
0x18002ada0  jz      short loc_18002ADA6
0x18002ada2  test    edi, edi
0x18002ada4  jns     short loc_18002ADAC
0x18002ada6  mov     ebx, edi
0x18002ada8  jmp     short loc_18002ADAC
0x18002adaa  xor     ebx, ebx
0x18002adac  cmp     dword ptr [rsp+1E0h+SourceString], 0
0x18002adb1  jz      short loc_18002ADCA
0x18002adb3  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x18002adba  mov     cs:dword_1800F0D10, 0FFFFFFFFh
0x18002adc4  call    cs:__imp_RtlReleaseResource
0x18002adca  test    r13, r13
0x18002adcd  jz      short loc_18002ADD8
0x18002adcf  mov     rcx, r13; hMem
0x18002add2  call    cs:__imp_LocalFree
0x18002add8  test    rsi, rsi
0x18002addb  jz      short loc_18002AE07
0x18002addd  mov     ecx, r14d
0x18002ade0  mov     rax, rsi
0x18002ade3  test    r14d, r14d
0x18002ade6  jz      short loc_18002ADF4
0x18002ade8  mov     byte ptr [rax], 0
0x18002adeb  inc     rax
0x18002adee  sub     rcx, 1
0x18002adf2  jnz     short loc_18002ADE8
0x18002adf4  mov     rax, cs:?g_pLsaFunctions@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pLsaFunctions
0x18002adfb  mov     rcx, rsi
0x18002adfe  mov     rax, [rax+18h]
0x18002ae02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae07  cmp     [rsp+1E0h+var_1A8], 0
0x18002ae0d  jz      short loc_18002AE1A
0x18002ae0f  lea     rcx, [rsp+1E0h+var_1A8]
0x18002ae14  call    cs:__imp_LsarClose
0x18002ae1a  mov     r8d, ebx
0x18002ae1d  lea     rdx, aExitingNetpupd; "Exiting NetpUpdateLSASecretCreds with S"...
0x18002ae24  mov     ecx, 40h ; '@'; unsigned int
0x18002ae29  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002ae2e  mov     eax, ebx
0x18002ae30  mov     rcx, [rbp+0E0h+var_50]
0x18002ae37  xor     rcx, rsp; StackCookie
0x18002ae3a  call    __security_check_cookie
0x18002ae3f  add     rsp, 1A8h
0x18002ae46  pop     r15
0x18002ae48  pop     r14
0x18002ae4a  pop     r13
0x18002ae4c  pop     r12
0x18002ae4e  pop     rdi
0x18002ae4f  pop     rsi
0x18002ae50  pop     rbx
0x18002ae51  pop     rbp
0x18002ae52  retn
```
