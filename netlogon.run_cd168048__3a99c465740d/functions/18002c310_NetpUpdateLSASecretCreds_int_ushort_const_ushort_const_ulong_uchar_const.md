# NetpUpdateLSASecretCreds(int,ushort const *,ushort const *,ulong,uchar const *)

- ea: `0x18002c310`
- end: `0x18002c750`
- name: `?NetpUpdateLSASecretCreds@@YAJHPEBG0KPEBE@Z`
- size: `1088`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, const unsigned __int8 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x18000e910`
- `0x18002b388`
- `0x18002b590`
- `0x18002bbe0`
- `0x18002c310`
- `0x1800644a0`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c449`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c449`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c6c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c6c2`
- `LSASRV!LsarClose` at `0x18002c70a`
- `LSASRV!LsarClose` at `0x18002c70a`
- `LSASRV!LsarCreateSecret` at `0x18002c4d6`
- `LSASRV!LsarCreateSecret` at `0x18002c4d6`
- `LSASRV!LsarSetSecret` at `0x18002c58f`
- `LSASRV!LsarSetSecret` at `0x18002c65b`
- `LSASRV!LsarSetSecret` at `0x18002c58f`
- `LSASRV!LsarSetSecret` at `0x18002c65b`
- `LSASRV!LsarOpenSecret` at `0x18002c479`
- `LSASRV!LsarOpenSecret` at `0x18002c479`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002c43d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002c43d`
- `ntdll!RtlInitUnicodeString` at `0x18002c3d6`
- `ntdll!RtlInitUnicodeString` at `0x18002c3d6`
- `ntdll!RtlReleaseResource` at `0x18002c6ae`
- `ntdll!RtlReleaseResource` at `0x18002c6ae`

## string_xrefs

- `0x18002c509`: `LsarOpenSecret failed 0x%08X\n`
- `0x18002c361`: `Entering NetpUpdateLSASecretCreds\n`
- `0x18002c3f6`: `onecore\ds\netapi\svcdlls\logonsrv\server\groupsvcacct.cxx`
- `0x18002c4ec`: `LsarCreateSecret failed 0x%08X\n`
- `0x18002c719`: `Exiting NetpUpdateLSASecretCreds with Status 0x%08X\n`

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
    dword_1800F7D10 = GetCurrentThreadId();
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
    dword_1800F7D10 = -1;
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
0x18002c310  push    rbp
0x18002c312  push    rbx
0x18002c313  push    rsi
0x18002c314  push    rdi
0x18002c315  push    r12
0x18002c317  push    r13
0x18002c319  push    r14
0x18002c31b  push    r15
0x18002c31d  lea     rbp, [rsp-0A8h]
0x18002c325  sub     rsp, 1A8h
0x18002c32c  mov     rax, cs:__security_cookie
0x18002c333  xor     rax, rsp
0x18002c336  mov     [rbp+0E0h+var_50], rax
0x18002c33d  mov     r12, [rbp+0E0h+arg_20]
0x18002c344  xor     eax, eax
0x18002c346  xorps   xmm0, xmm0
0x18002c349  mov     [rbp+0E0h+var_158], rdx
0x18002c34d  mov     rbx, rdx
0x18002c350  mov     [rbp+0E0h+var_160], r8
0x18002c354  mov     edi, ecx
0x18002c356  mov     dword ptr [rsp+1E0h+var_170+4], eax
0x18002c35a  lea     ecx, [rax+40h]; unsigned int
0x18002c35d  mov     [rsp+1E0h+var_1B0], eax
0x18002c361  lea     rdx, aEnteringNetpup; "Entering NetpUpdateLSASecretCreds\n"
0x18002c368  mov     [rsp+1E0h+var_1A8], rax
0x18002c36d  mov     r15d, r9d
0x18002c370  mov     [rsp+1E0h+SourceString], rax
0x18002c375  mov     r13, r8
0x18002c378  mov     [rsp+1E0h+var_188], rax
0x18002c37d  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x18002c381  mov     r14d, eax
0x18002c384  mov     esi, eax
0x18002c386  movups  [rsp+1E0h+var_180], xmm0
0x18002c38b  movups  [rsp+1E0h+var_198], xmm0
0x18002c390  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002c395  lea     r9, [rsp+1E0h+SourceString]; unsigned __int16 **
0x18002c39a  mov     r8, r13; unsigned __int16 *
0x18002c39d  mov     rdx, rbx; unsigned __int16 *
0x18002c3a0  mov     ecx, edi; int
0x18002c3a2  call    ?NetpGetSecretName@@YAJHPEBG0PEAPEAG@Z; NetpGetSecretName(int,ushort const *,ushort const *,ushort * *)
0x18002c3a7  mov     r13, [rsp+1E0h+SourceString]
0x18002c3ac  mov     ebx, eax
0x18002c3ae  test    eax, eax
0x18002c3b0  jns     short loc_18002C3CB
0x18002c3b2  mov     r8d, eax
0x18002c3b5  lea     rdx, aNetpgetsecretn; "NetpGetSecretName failed 0x%08X\n"
0x18002c3bc  mov     ecx, 40h ; '@'; unsigned int
0x18002c3c1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002c3c6  jmp     loc_18002C6BA
0x18002c3cb  mov     rdx, r13; SourceString
0x18002c3ce  mov     dword ptr [rsp+1E0h+SourceString], esi
0x18002c3d2  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x18002c3d6  call    cs:__imp_RtlInitUnicodeString
0x18002c3dd  nop     dword ptr [rax+rax+00h]
0x18002c3e2  test    edi, edi
0x18002c3e4  jz      short loc_18002C463
0x18002c3e6  test    r12, r12
0x18002c3e9  jnz     short loc_18002C3F0
0x18002c3eb  test    r15d, r15d
0x18002c3ee  jz      short loc_18002C409
0x18002c3f0  mov     r8d, 1BFh; unsigned int
0x18002c3f6  lea     rdx, aOnecoreDsNetap_22; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18002c3fd  lea     rcx, aNullPbdata0Cbd; "NULL == pbData && 0 == cbData"
0x18002c404  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18002c409  mov     r15d, 0F0h
0x18002c40f  lea     rcx, [rbp+0E0h+pbBuffer]; pbBuffer
0x18002c413  mov     edx, r15d; unsigned int
0x18002c416  call    ?NlGenerateRandomBits@@YAEPEAEK@Z; NlGenerateRandomBits(uchar *,ulong)
0x18002c41b  test    al, al
0x18002c41d  jnz     short loc_18002C430
0x18002c41f  mov     ebx, 0C00000E5h
0x18002c424  lea     rdx, aNlgeneraterand; "NlGenerateRandomBits failed 0x%08X\n"
0x18002c42b  mov     r8d, ebx
0x18002c42e  jmp     short loc_18002C3BC
0x18002c430  mov     dl, 1; Wait
0x18002c432  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x18002c439  lea     r12, [rbp+0E0h+pbBuffer]
0x18002c43d  call    cs:__imp_RtlAcquireResourceExclusive
0x18002c444  nop     dword ptr [rax+rax+00h]
0x18002c449  call    cs:__imp_GetCurrentThreadId
0x18002c450  nop     dword ptr [rax+rax+00h]
0x18002c455  mov     cs:dword_1800F7D10, eax
0x18002c45b  mov     dword ptr [rsp+1E0h+SourceString], 1
0x18002c463  mov     rcx, cs:?NlGlobalLsaPolicyHandle@@3PEAXEA; void * NlGlobalLsaPolicyHandle
0x18002c46a  lea     r9, [rsp+1E0h+var_1A8]
0x18002c46f  mov     r8d, 3
0x18002c475  lea     rdx, [rbp+0E0h+DestinationString]
0x18002c479  call    cs:__imp_LsarOpenSecret
0x18002c480  nop     dword ptr [rax+rax+00h]
0x18002c485  mov     ebx, eax
0x18002c487  cmp     eax, 0C0000034h
0x18002c48c  jnz     short loc_18002C505
0x18002c48e  mov     r9, [rbp+0E0h+var_160]
0x18002c492  lea     rax, aGmsa; "GMSA"
0x18002c499  test    edi, edi
0x18002c49b  lea     r8, aDpapi; "DPAPI"
0x18002c4a2  lea     rdx, aWsSecretNotFou; "%ws Secret not found for %ws\\%ws\n"
0x18002c4a9  mov     ecx, 40h ; '@'; unsigned int
0x18002c4ae  cmovz   r8, rax
0x18002c4b2  mov     rax, [rbp+0E0h+var_158]
0x18002c4b6  mov     [rsp+1E0h+var_1C0], rax
0x18002c4bb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002c4c0  mov     rcx, cs:?NlGlobalLsaPolicyHandle@@3PEAXEA; void * NlGlobalLsaPolicyHandle
0x18002c4c7  lea     r9, [rsp+1E0h+var_1A8]
0x18002c4cc  mov     r8d, 0F0003h
0x18002c4d2  lea     rdx, [rbp+0E0h+DestinationString]
0x18002c4d6  call    cs:__imp_LsarCreateSecret
0x18002c4dd  nop     dword ptr [rax+rax+00h]
0x18002c4e2  mov     ebx, eax
0x18002c4e4  test    eax, eax
0x18002c4e6  jns     loc_18002C56F
0x18002c4ec  lea     rdx, aLsarcreatesecr; "LsarCreateSecret failed 0x%08X\n"
0x18002c4f3  mov     r8d, eax
0x18002c4f6  mov     ecx, 40h ; '@'; unsigned int
0x18002c4fb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002c500  jmp     loc_18002C696
0x18002c505  test    eax, eax
0x18002c507  jns     short loc_18002C512
0x18002c509  lea     rdx, aLsaropensecret; "LsarOpenSecret failed 0x%08X\n"
0x18002c510  jmp     short loc_18002C4F3
0x18002c512  test    edi, edi
0x18002c514  jz      short loc_18002C56F
0x18002c516  mov     rcx, [rsp+1E0h+var_1A8]; void *
0x18002c51b  lea     rax, [rsp+1E0h+var_188]
0x18002c520  mov     [rsp+1E0h+var_1B8], rax; unsigned __int8 **
0x18002c525  xor     r9d, r9d; unsigned __int16 *
0x18002c528  lea     rax, [rsp+1E0h+var_1B0]
0x18002c52d  xor     r8d, r8d; unsigned __int16 *
0x18002c530  mov     edx, edi; int
0x18002c532  mov     [rsp+1E0h+var_1C0], rax; unsigned int *
0x18002c537  call    ?NetpFetchLSASecretCredsEx@@YAJPEAXHPEBG1PEAKPEAPEAE@Z; NetpFetchLSASecretCredsEx(void *,int,ushort const *,ushort const *,ulong *,uchar * *)
0x18002c53c  mov     ebx, eax
0x18002c53e  test    eax, eax
0x18002c540  jns     short loc_18002C565
0x18002c542  mov     r8d, eax
0x18002c545  lea     rdx, aNetpfetchdpapi; "NetpFetchDPAPICreds failed 0x%08X\n"
0x18002c54c  mov     ecx, 40h ; '@'; unsigned int
0x18002c551  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002c556  mov     r14d, [rsp+1E0h+var_1B0]
0x18002c55b  mov     rsi, [rsp+1E0h+var_188]
0x18002c560  jmp     loc_18002C696
0x18002c565  mov     r14d, [rsp+1E0h+var_1B0]
0x18002c56a  mov     rsi, [rsp+1E0h+var_188]
0x18002c56f  mov     rcx, [rsp+1E0h+var_1A8]
0x18002c574  lea     rdx, [rsp+1E0h+var_198]
0x18002c579  movzx   r15d, r15w
0x18002c57d  xor     r8d, r8d
0x18002c580  mov     dword ptr [rsp+1E0h+var_198+4], r15d
0x18002c585  mov     dword ptr [rsp+1E0h+var_198], r15d
0x18002c58a  mov     qword ptr [rsp+1E0h+var_198+8], r12
0x18002c58f  call    cs:__imp_LsarSetSecret
0x18002c596  nop     dword ptr [rax+rax+00h]
0x18002c59b  mov     ebx, eax
0x18002c59d  test    eax, eax
0x18002c59f  jns     short loc_18002C5AD
0x18002c5a1  lea     rdx, aLsarsetsecretF; "LsarSetSecret failed 0x%08X\n"
0x18002c5a8  jmp     loc_18002C4F3
0x18002c5ad  test    edi, edi
0x18002c5af  jz      loc_18002C694
0x18002c5b5  test    rsi, rsi
0x18002c5b8  jz      loc_18002C694
0x18002c5be  mov     rax, cs:?g_pLsaFunctions@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pLsaFunctions
0x18002c5c5  lea     r9, [rsp+1E0h+var_180]
0x18002c5ca  mov     rdx, [rbp+0E0h+var_160]
0x18002c5ce  lea     r8, [rsp+1E0h+var_170]
0x18002c5d3  mov     rcx, [rbp+0E0h+var_158]
0x18002c5d7  mov     word ptr [rsp+1E0h+var_170+2], r14w
0x18002c5dd  mov     rax, [rax+78h]
0x18002c5e1  mov     word ptr [rsp+1E0h+var_170], r14w
0x18002c5e7  mov     qword ptr [rsp+1E0h+var_170+8], rsi
0x18002c5ec  movaps  xmm1, [rsp+1E0h+var_170]
0x18002c5f1  mov     word ptr [rsp+1E0h+var_180+2], r15w
0x18002c5f7  mov     word ptr [rsp+1E0h+var_180], r15w
0x18002c5fd  mov     qword ptr [rsp+1E0h+var_180+8], r12
0x18002c602  movaps  xmm0, [rsp+1E0h+var_180]
0x18002c607  movdqa  [rsp+1E0h+var_180], xmm0
0x18002c60d  movdqa  [rsp+1E0h+var_170], xmm1
0x18002c613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c618  mov     ebx, eax
0x18002c61a  test    eax, eax
0x18002c61c  jns     short loc_18002C694
0x18002c61e  mov     r8d, eax
0x18002c621  lea     rdx, aLsaidpapipassw; "LsaIDPAPIPasswordChangeForGMSA failed 0"...
0x18002c628  mov     ecx, 40h ; '@'; unsigned int
0x18002c62d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002c632  mov     rcx, [rsp+1E0h+var_1A8]
0x18002c637  lea     rdx, [rsp+1E0h+var_198]
0x18002c63c  movzx   eax, r14w
0x18002c640  xor     edi, edi
0x18002c642  cmp     ebx, 0C000005Fh
0x18002c648  mov     dword ptr [rsp+1E0h+var_198+4], eax
0x18002c64c  mov     dword ptr [rsp+1E0h+var_198], eax
0x18002c650  cmovnz  edi, ebx
0x18002c653  mov     qword ptr [rsp+1E0h+var_198+8], rsi
0x18002c658  xor     r8d, r8d
0x18002c65b  call    cs:__imp_LsarSetSecret
0x18002c662  nop     dword ptr [rax+rax+00h]
0x18002c667  mov     ebx, eax
0x18002c669  test    eax, eax
0x18002c66b  jns     short loc_18002C690
0x18002c66d  mov     r8d, eax
0x18002c670  lea     rdx, aLsarsetsecretF; "LsarSetSecret failed 0x%08X\n"
0x18002c677  mov     ecx, 40h ; '@'; unsigned int
0x18002c67c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002c681  mov     ecx, ebx; int
0x18002c683  call    ?IsFatalStatus@@YAHJ@Z; IsFatalStatus(long)
0x18002c688  test    eax, eax
0x18002c68a  jz      short loc_18002C690
0x18002c68c  test    edi, edi
0x18002c68e  jns     short loc_18002C696
0x18002c690  mov     ebx, edi
0x18002c692  jmp     short loc_18002C696
0x18002c694  xor     ebx, ebx
0x18002c696  cmp     dword ptr [rsp+1E0h+SourceString], 0
0x18002c69b  jz      short loc_18002C6BA
0x18002c69d  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x18002c6a4  mov     cs:dword_1800F7D10, 0FFFFFFFFh
0x18002c6ae  call    cs:__imp_RtlReleaseResource
0x18002c6b5  nop     dword ptr [rax+rax+00h]
0x18002c6ba  test    r13, r13
0x18002c6bd  jz      short loc_18002C6CE
0x18002c6bf  mov     rcx, r13; hMem
0x18002c6c2  call    cs:__imp_LocalFree
0x18002c6c9  nop     dword ptr [rax+rax+00h]
0x18002c6ce  test    rsi, rsi
0x18002c6d1  jz      short loc_18002C6FD
0x18002c6d3  mov     ecx, r14d
0x18002c6d6  mov     rax, rsi
0x18002c6d9  test    r14d, r14d
0x18002c6dc  jz      short loc_18002C6EA
0x18002c6de  mov     byte ptr [rax], 0
0x18002c6e1  inc     rax
0x18002c6e4  sub     rcx, 1
0x18002c6e8  jnz     short loc_18002C6DE
0x18002c6ea  mov     rax, cs:?g_pLsaFunctions@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pLsaFunctions
0x18002c6f1  mov     rcx, rsi
0x18002c6f4  mov     rax, [rax+18h]
0x18002c6f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6fd  cmp     [rsp+1E0h+var_1A8], 0
0x18002c703  jz      short loc_18002C716
0x18002c705  lea     rcx, [rsp+1E0h+var_1A8]
0x18002c70a  call    cs:__imp_LsarClose
0x18002c711  nop     dword ptr [rax+rax+00h]
0x18002c716  mov     r8d, ebx
0x18002c719  lea     rdx, aExitingNetpupd; "Exiting NetpUpdateLSASecretCreds with S"...
0x18002c720  mov     ecx, 40h ; '@'; unsigned int
0x18002c725  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002c72a  mov     eax, ebx
0x18002c72c  mov     rcx, [rbp+0E0h+var_50]
0x18002c733  xor     rcx, rsp; StackCookie
0x18002c736  call    __security_check_cookie
0x18002c73b  add     rsp, 1A8h
0x18002c742  pop     r15
0x18002c744  pop     r14
0x18002c746  pop     r13
0x18002c748  pop     r12
0x18002c74a  pop     rdi
0x18002c74b  pop     rsi
0x18002c74c  pop     rbx
0x18002c74d  pop     rbp
0x18002c74e  retn
```
