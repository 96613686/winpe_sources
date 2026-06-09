# NlGetTrustedSideInfo(_CLIENT_SESSION *,ushort *,_NETLOGON_SECURE_CHANNEL_TYPE,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,_NL_GENERIC_RPC_DATA * *)

- ea: `0x180057434`
- end: `0x1800577eb`
- name: `?NlGetTrustedSideInfo@@YAJPEAU_CLIENT_SESSION@@PEAGW4_NETLOGON_SECURE_CHANNEL_TYPE@@PEAU_LM_OWF_PASSWORD@@3PEAPEAU_NL_GENERIC_RPC_DATA@@@Z`
- size: `951`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180059e9c`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18000e270`
- `0x180035368`
- `0x18003e71c`
- `0x18003e7dc`
- `0x180057434`
- `0x18005f358`
- `0x18005f79c`
- `0x180060734`
- `0x180060adc`
- `0x18006515c`
- `0x180068458`
- `0x1800688e0`

## import_xrefs

- `logoncli!I_NetServerGetTrustInfo` at `0x1800575d5`
- `logoncli!I_NetServerGetTrustInfo` at `0x1800575d5`
- `ntdll!RtlLeaveCriticalSection` at `0x18005763c`
- `ntdll!RtlLeaveCriticalSection` at `0x18005763c`
- `ntdll!RtlEnterCriticalSection` at `0x180057627`
- `ntdll!RtlEnterCriticalSection` at `0x180057627`
- `netutils!NetApiBufferFree` at `0x1800577b3`
- `netutils!NetApiBufferFree` at `0x1800577b3`

## string_xrefs

- `0x18005755d`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x180057703`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x180057736`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005774e`: `NlGetTrustedSideInfo: NlBuildAuthenticator failed with status: 0x%lx\n`
- `0x180057699`: `NlGetTrustedSideInfo: denying access after status: 0x%lx\n`
- `0x180057796`: `NlGetTrustedSideInfo: %ws: failed %lX\n`

## pseudocode

```c
__int64 __fastcall NlGetTrustedSideInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct _LM_OWF_PASSWORD *a4,
        struct _LM_OWF_PASSWORD *a5,
        LPVOID *a6)
{
  LPVOID *v6; // r14
  bool v8; // zf
  char v10; // r15
  __int64 v11; // rbx
  int started; // edi
  _LM_OWF_PASSWORD v13; // xmm0
  int v14; // eax
  DWORD v15; // r14d
  char *v16; // r9
  __int64 v17; // rcx
  __int64 v18; // r9
  int TrustInfo; // eax
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r8
  char *v23; // r9
  char *v24; // r9
  char *v25; // r9
  __int64 v26; // rcx
  _LM_OWF_PASSWORD *v27; // rax
  struct _CLIENT_API *v28; // [rsp+20h] [rbp-A9h]
  char v29; // [rsp+50h] [rbp-79h]
  LPVOID Buffer; // [rsp+60h] [rbp-69h] BYREF
  struct _LM_OWF_PASSWORD *v31; // [rsp+68h] [rbp-61h]
  struct _LM_OWF_PASSWORD *v32; // [rsp+70h] [rbp-59h]
  char v33; // [rsp+78h] [rbp-51h] BYREF
  __int64 v34; // [rsp+79h] [rbp-50h]
  __int16 v35; // [rsp+81h] [rbp-48h]
  char v36; // [rsp+83h] [rbp-46h]
  _BYTE v37[9]; // [rsp+88h] [rbp-41h] BYREF
  __int16 v38; // [rsp+91h] [rbp-38h]
  char v39; // [rsp+93h] [rbp-36h]
  _LM_OWF_PASSWORD v40; // [rsp+98h] [rbp-31h] BYREF
  unsigned int v41; // [rsp+A8h] [rbp-21h]
  _ENCRYPTED_LM_OWF_PASSWORD v42; // [rsp+B0h] [rbp-19h] BYREF
  struct _ENCRYPTED_LM_OWF_PASSWORD v43; // [rsp+C0h] [rbp-9h] BYREF

  v6 = a6;
  v32 = a5;
  v31 = a4;
  v8 = (*(_DWORD *)(a1 + 408) & 0x200) == 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  memset(v37, 0, sizeof(v37));
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  Buffer = 0;
  v43 = 0;
  if ( !v8 )
    return 3221225659LL;
  v10 = 0;
  v11 = 0;
  started = NlEnsureSessionAuthenticated((struct _CLIENT_SESSION *)a1, 0);
  if ( started < 0 )
    goto LABEL_37;
  v29 = 1;
  while ( 2 )
  {
    v13 = *(_LM_OWF_PASSWORD *)(a1 + 440);
    v11 = *(_QWORD *)(a1 + 432);
    v41 = *(_DWORD *)(a1 + 316);
    v40 = v13;
    v14 = NlBuildAuthenticator(
            (struct _CYPHER_BLOCK *)(a1 + 432),
            (struct _NETLOGON_SESSION_KEY *)(a1 + 440),
            (struct _NETLOGON_AUTHENTICATOR *)&v33,
            v41);
    started = v14;
    if ( v14 < 0 )
    {
      NlPrintRoutine(
        0x100u,
        L"NlGetTrustedSideInfo: NlBuildAuthenticator failed with status: 0x%lx\n",
        (unsigned int)v14);
      break;
    }
    started = -1073610748;
    v15 = 0;
    while ( 1 )
    {
      started = NlStartApiClientSession((struct _CLIENT_SESSION *)a1, 1, v15, started, (struct _CLIENT_API *)(a1 + 680));
      if ( started >= 0 )
        break;
LABEL_16:
      v20 = (unsigned int)(started + 1073610748);
      if ( (unsigned int)v20 <= 0x32 )
      {
        v21 = 0x4000000080001LL;
        if ( _bittest64(&v21, v20) )
        {
          if ( ++v15 < 2 )
            continue;
        }
      }
      goto LABEL_21;
    }
    v17 = *(_QWORD *)(a1 + 504);
    if ( !v17 )
    {
      NlAssertFailed(
        "ClientSession->CsUncServerName != NULL",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx",
        4669,
        v16);
      v17 = *(_QWORD *)(a1 + 504);
    }
    if ( (*(_DWORD *)(a1 + 292) & 0x40000) != 0 )
      v18 = *(_QWORD *)(a1 + 216);
    else
      v18 = *(_QWORD *)(*(_QWORD *)(a1 + 272) + 264LL);
    TrustInfo = I_NetServerGetTrustInfo(
                  v17,
                  *(_QWORD *)(a1 + 200),
                  *(unsigned int *)(a1 + 280),
                  v18,
                  &v33,
                  v37,
                  &v42,
                  &v43,
                  &Buffer);
    started = TrustInfo;
    if ( TrustInfo != -1073610706 )
    {
      if ( TrustInfo < 0 )
        NlPrintRpcDebug("I_NetServerGetTrustInfo", TrustInfo);
      goto LABEL_16;
    }
    RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
    *(_DWORD *)(a1 + 408) |= 0x200u;
    RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
    started = 0;
    v10 = 1;
LABEL_21:
    NlFinishApiClientSession((struct _CLIENT_SESSION *)a1, 1u, 1u, (struct _CLIENT_API *)(a1 + 680));
    if ( !v10 )
    {
      if ( started == -1073741790
        || (unsigned int)NlCheckRpcAuthIsNetlogon((struct _CLIENT_SESSION *)a1)
        && !(unsigned int)NlUpdateSeed(
                            (PUCHAR)(a1 + 432),
                            (struct _CYPHER_BLOCK *)v37,
                            (PUCHAR)(a1 + 440),
                            *(_DWORD *)(a1 + 316)) )
      {
        NlPrintCsRoutine(
          0x100u,
          (struct _CLIENT_SESSION *)a1,
          L"NlGetTrustedSideInfo: denying access after status: 0x%lx\n",
          (unsigned int)started);
        if ( started >= 0 )
          started = -1073741790;
        NlSetStatusClientSession((struct _CLIENT_SESSION *)a1, started, v22, v23);
        if ( !v29 )
          break;
        v29 = 0;
        started = NlEnsureSessionAuthenticated((struct _CLIENT_SESSION *)a1, 0);
        if ( started < 0 )
          break;
        continue;
      }
      if ( started >= 0 )
      {
        if ( (int)NlpDecryptNtOwf(v41, &v42, &v40, v31) < 0 )
          NlAssertFailed("NT_SUCCESS(Status)", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx", 4767, v24);
        started = NlpDecryptNtOwf(v41, &v43, &v40, v32);
        if ( started < 0 )
          NlAssertFailed("NT_SUCCESS(Status)", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx", 4774, v25);
      }
    }
    break;
  }
  v6 = a6;
LABEL_37:
  v26 = 16;
  v27 = &v40;
  do
  {
    v27->data[0].data[0] = 0;
    v27 = (_LM_OWF_PASSWORD *)((char *)v27 + 1);
    --v26;
  }
  while ( v26 );
  if ( v10 )
  {
    *(_QWORD *)(a1 + 432) = v11;
    started = -1073741637;
LABEL_42:
    LODWORD(v28) = started;
    NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, L"NlGetTrustedSideInfo: %ws: failed %lX\n", 0, v28);
    if ( Buffer )
      NetApiBufferFree(Buffer);
  }
  else
  {
    if ( started < 0 )
      goto LABEL_42;
    *v6 = Buffer;
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180057434  mov     [rsp-8+arg_8], rbx
0x180057439  push    rbp
0x18005743a  push    rsi
0x18005743b  push    rdi
0x18005743c  push    r12
0x18005743e  push    r13
0x180057440  push    r14
0x180057442  push    r15
0x180057444  lea     rbp, [rsp-17h]
0x180057449  sub     rsp, 0E0h
0x180057450  mov     rax, cs:__security_cookie
0x180057457  xor     rax, rsp
0x18005745a  mov     [rbp+47h+var_40], rax
0x18005745e  mov     rax, [rbp+47h+arg_20]
0x180057462  xorps   xmm0, xmm0
0x180057465  mov     r14, [rbp+47h+arg_28]
0x180057469  xorps   xmm1, xmm1
0x18005746c  mov     [rbp+47h+var_A0], rax
0x180057470  mov     rsi, rcx
0x180057473  xor     eax, eax
0x180057475  mov     [rbp+47h+var_A8], r9
0x180057479  test    dword ptr [rcx+198h], 200h
0x180057483  mov     [rbp+47h+var_B8], r14
0x180057487  mov     [rbp+47h+var_98], 0
0x18005748b  mov     [rbp+47h+var_97], rax
0x18005748f  mov     [rbp+47h+var_8F], ax
0x180057493  mov     [rbp+47h+var_8D], al
0x180057496  mov     [rbp+47h+var_88], al
0x180057499  mov     qword ptr [rbp+47h+var_88+1], rax
0x18005749d  mov     [rbp+47h+var_7F], ax
0x1800574a1  mov     [rbp+47h+var_7D], al
0x1800574a4  movups  xmmword ptr [rbp+47h+var_78.data.data], xmm0
0x1800574a8  mov     [rbp+47h+var_68], eax
0x1800574ab  movups  xmmword ptr [rbp+47h+var_60.data.data], xmm0
0x1800574af  mov     [rbp+47h+Buffer], rax
0x1800574b3  movups  xmmword ptr [rbp+47h+var_50.data.data], xmm1
0x1800574b7  jz      short loc_1800574C3
0x1800574b9  mov     eax, 0C00000BBh
0x1800574be  jmp     loc_1800577C4
0x1800574c3  xor     edx, edx; unsigned int
0x1800574c5  xor     r15b, r15b
0x1800574c8  xor     ebx, ebx
0x1800574ca  call    ?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z; NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)
0x1800574cf  mov     edi, eax
0x1800574d1  test    eax, eax
0x1800574d3  js      loc_180057763
0x1800574d9  mov     [rbp+47h+var_C0], 1
0x1800574dd  lea     r12, [rsi+1B8h]
0x1800574e4  lea     r13, [rsi+1B0h]
0x1800574eb  movups  xmm0, xmmword ptr [r12]
0x1800574f0  mov     r9d, [rsi+13Ch]; unsigned int
0x1800574f7  lea     r8, [rbp+47h+var_98]; struct _NETLOGON_AUTHENTICATOR *
0x1800574fb  mov     rbx, [r13+0]
0x1800574ff  mov     rdx, r12; struct _NETLOGON_SESSION_KEY *
0x180057502  mov     rcx, r13; struct _CYPHER_BLOCK *
0x180057505  mov     [rbp+47h+var_68], r9d
0x180057509  movdqu  xmmword ptr [rbp+47h+var_78.data.data], xmm0
0x18005750e  call    ?NlBuildAuthenticator@@YAJPEAU_CYPHER_BLOCK@@PEAU_NETLOGON_SESSION_KEY@@PEAU_NETLOGON_AUTHENTICATOR@@K@Z; NlBuildAuthenticator(_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,_NETLOGON_AUTHENTICATOR *,ulong)
0x180057513  mov     edi, eax
0x180057515  test    eax, eax
0x180057517  js      loc_18005774B
0x18005751d  mov     edi, 0C0020004h
0x180057522  xor     r14d, r14d
0x180057525  lea     rax, [rsi+2A8h]
0x18005752c  mov     r9d, edi; int
0x18005752f  mov     r8d, r14d; unsigned int
0x180057532  mov     [rsp+110h+var_F0], rax; struct _CLIENT_API *
0x180057537  mov     dl, 1; unsigned __int8
0x180057539  mov     rcx, rsi; struct _CLIENT_SESSION *
0x18005753c  call    ?NlStartApiClientSession@@YAJPEAU_CLIENT_SESSION@@EKJPEAU_CLIENT_API@@@Z; NlStartApiClientSession(_CLIENT_SESSION *,uchar,ulong,long,_CLIENT_API *)
0x180057541  mov     edi, eax
0x180057543  test    eax, eax
0x180057545  js      loc_1800575F6
0x18005754b  mov     rcx, [rsi+1F8h]
0x180057552  test    rcx, rcx
0x180057555  jnz     short loc_180057577
0x180057557  mov     r8d, 123Dh; unsigned int
0x18005755d  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180057564  lea     rcx, aClientsessionC_2; "ClientSession->CsUncServerName != NULL"
0x18005756b  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180057570  mov     rcx, [rsi+1F8h]
0x180057577  test    dword ptr [rsi+124h], 40000h
0x180057581  jz      short loc_18005758C
0x180057583  mov     r9, [rsi+0D8h]
0x18005758a  jmp     short loc_18005759A
0x18005758c  mov     rax, [rsi+110h]
0x180057593  mov     r9, [rax+108h]
0x18005759a  mov     r8d, [rsi+118h]
0x1800575a1  lea     rax, [rbp+47h+Buffer]
0x1800575a5  mov     rdx, [rsi+0C8h]
0x1800575ac  mov     [rsp+110h+var_D0], rax
0x1800575b1  lea     rax, [rbp+47h+var_50]
0x1800575b5  mov     [rsp+110h+var_D8], rax
0x1800575ba  lea     rax, [rbp+47h+var_60]
0x1800575be  mov     [rsp+110h+var_E0], rax
0x1800575c3  lea     rax, [rbp+47h+var_88]
0x1800575c7  mov     [rsp+110h+var_E8], rax
0x1800575cc  lea     rax, [rbp+47h+var_98]
0x1800575d0  mov     [rsp+110h+var_F0], rax
0x1800575d5  call    cs:__imp_I_NetServerGetTrustInfo
0x1800575db  mov     edi, eax
0x1800575dd  cmp     eax, 0C002002Eh
0x1800575e2  jz      short loc_180057620
0x1800575e4  test    eax, eax
0x1800575e6  jns     short loc_1800575F6
0x1800575e8  mov     edx, eax; int
0x1800575ea  lea     rcx, aINetservergett; "I_NetServerGetTrustInfo"
0x1800575f1  call    ?NlPrintRpcDebug@@YAXPEBDJ@Z; NlPrintRpcDebug(char const *,long)
0x1800575f6  lea     eax, [rdi+3FFDFFFCh]
0x1800575fc  cmp     eax, 32h ; '2'
0x1800575ff  ja      short loc_180057647
0x180057601  mov     rcx, 4000000080001h
0x18005760b  bt      rcx, rax
0x18005760f  jnb     short loc_180057647
0x180057611  inc     r14d
0x180057614  cmp     r14d, 2
0x180057618  jb      loc_180057525
0x18005761e  jmp     short loc_180057647
0x180057620  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180057627  call    cs:__imp_RtlEnterCriticalSection
0x18005762d  bts     dword ptr [rsi+198h], 9
0x180057635  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18005763c  call    cs:__imp_RtlLeaveCriticalSection
0x180057642  xor     edi, edi
0x180057644  mov     r15b, 1
0x180057647  mov     r8b, 1; unsigned __int8
0x18005764a  lea     r9, [rsi+2A8h]; struct _CLIENT_API *
0x180057651  mov     dl, r8b; unsigned __int8
0x180057654  mov     rcx, rsi; struct _CLIENT_SESSION *
0x180057657  call    ?NlFinishApiClientSession@@YAEPEAU_CLIENT_SESSION@@EEPEAU_CLIENT_API@@@Z; NlFinishApiClientSession(_CLIENT_SESSION *,uchar,uchar,_CLIENT_API *)
0x18005765c  test    r15b, r15b
0x18005765f  jnz     loc_18005775F
0x180057665  mov     r14d, 0C0000022h
0x18005766b  cmp     edi, r14d
0x18005766e  jz      short loc_180057696
0x180057670  mov     rcx, rsi; struct _CLIENT_SESSION *
0x180057673  call    ?NlCheckRpcAuthIsNetlogon@@YAHPEAU_CLIENT_SESSION@@@Z; NlCheckRpcAuthIsNetlogon(_CLIENT_SESSION *)
0x180057678  test    eax, eax
0x18005767a  jz      short loc_1800576E1
0x18005767c  mov     r9d, [rsi+13Ch]; unsigned int
0x180057683  lea     rdx, [rbp+47h+var_88]; struct _CYPHER_BLOCK *
0x180057687  mov     r8, r12; pbSecret
0x18005768a  mov     rcx, r13; pbInput
0x18005768d  call    ?NlUpdateSeed@@YAHPEAU_CYPHER_BLOCK@@0PEAU_NETLOGON_SESSION_KEY@@K@Z; NlUpdateSeed(_CYPHER_BLOCK *,_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,ulong)
0x180057692  test    eax, eax
0x180057694  jnz     short loc_1800576E1
0x180057696  mov     r9d, edi
0x180057699  lea     r8, aNlgettrustedsi_0; "NlGetTrustedSideInfo: denying access af"...
0x1800576a0  mov     rdx, rsi; struct _CLIENT_SESSION *
0x1800576a3  mov     ecx, 100h; unsigned int
0x1800576a8  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800576ad  test    edi, edi
0x1800576af  mov     rcx, rsi; struct _CLIENT_SESSION *
0x1800576b2  cmovns  edi, r14d
0x1800576b6  mov     edx, edi; int
0x1800576b8  call    ?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z; NlSetStatusClientSession(_CLIENT_SESSION *,long)
0x1800576bd  cmp     [rbp+47h+var_C0], 0
0x1800576c1  jz      loc_18005775F
0x1800576c7  xor     edx, edx; unsigned int
0x1800576c9  mov     [rbp+47h+var_C0], 0
0x1800576cd  mov     rcx, rsi; struct _CLIENT_SESSION *
0x1800576d0  call    ?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z; NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)
0x1800576d5  mov     edi, eax
0x1800576d7  test    eax, eax
0x1800576d9  jns     loc_1800574EB
0x1800576df  jmp     short loc_18005775F
0x1800576e1  test    edi, edi
0x1800576e3  js      short loc_18005775F
0x1800576e5  mov     r9, [rbp+47h+var_A8]; struct _LM_OWF_PASSWORD *
0x1800576e9  lea     r8, [rbp+47h+var_78]; struct _LM_OWF_PASSWORD *
0x1800576ed  mov     ecx, [rbp+47h+var_68]; unsigned int
0x1800576f0  lea     rdx, [rbp+47h+var_60]; struct _ENCRYPTED_LM_OWF_PASSWORD *
0x1800576f4  call    ?NlpDecryptNtOwf@@YAJKPEAU_ENCRYPTED_LM_OWF_PASSWORD@@PEAU_LM_OWF_PASSWORD@@1@Z; NlpDecryptNtOwf(ulong,_ENCRYPTED_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *)
0x1800576f9  test    eax, eax
0x1800576fb  jns     short loc_180057716
0x1800576fd  mov     r8d, 129Fh; unsigned int
0x180057703  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005770a  lea     rcx, aNtSuccessStatu_4; "NT_SUCCESS(Status)"
0x180057711  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180057716  mov     r9, [rbp+47h+var_A0]; struct _LM_OWF_PASSWORD *
0x18005771a  lea     r8, [rbp+47h+var_78]; struct _LM_OWF_PASSWORD *
0x18005771e  mov     ecx, [rbp+47h+var_68]; unsigned int
0x180057721  lea     rdx, [rbp+47h+var_50]; struct _ENCRYPTED_LM_OWF_PASSWORD *
0x180057725  call    ?NlpDecryptNtOwf@@YAJKPEAU_ENCRYPTED_LM_OWF_PASSWORD@@PEAU_LM_OWF_PASSWORD@@1@Z; NlpDecryptNtOwf(ulong,_ENCRYPTED_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *)
0x18005772a  mov     edi, eax
0x18005772c  test    eax, eax
0x18005772e  jns     short loc_18005775F
0x180057730  mov     r8d, 12A6h; unsigned int
0x180057736  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005773d  lea     rcx, aNtSuccessStatu_4; "NT_SUCCESS(Status)"
0x180057744  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180057749  jmp     short loc_18005775F
0x18005774b  mov     r8d, eax
0x18005774e  lea     rdx, aNlgettrustedsi; "NlGetTrustedSideInfo: NlBuildAuthentica"...
0x180057755  mov     ecx, 100h; unsigned int
0x18005775a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005775f  mov     r14, [rbp+47h+var_B8]
0x180057763  mov     ecx, 10h
0x180057768  lea     rax, [rbp+47h+var_78]
0x18005776c  mov     byte ptr [rax], 0
0x18005776f  inc     rax
0x180057772  sub     rcx, 1
0x180057776  jnz     short loc_18005776C
0x180057778  test    r15b, r15b
0x18005777b  jz      short loc_18005778B
0x18005777d  mov     [rsi+1B0h], rbx
0x180057784  mov     edi, 0C00000BBh
0x180057789  jmp     short loc_18005778F
0x18005778b  test    edi, edi
0x18005778d  jns     short loc_1800577BB
0x18005778f  xor     r9d, r9d
0x180057792  mov     dword ptr [rsp+110h+var_F0], edi
0x180057796  lea     r8, aNlgettrustedsi_1; "NlGetTrustedSideInfo: %ws: failed %lX\n"
0x18005779d  mov     rdx, rsi; struct _CLIENT_SESSION *
0x1800577a0  mov     ecx, 100h; unsigned int
0x1800577a5  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800577aa  mov     rcx, [rbp+47h+Buffer]; Buffer
0x1800577ae  test    rcx, rcx
0x1800577b1  jz      short loc_1800577C2
0x1800577b3  call    cs:__imp_NetApiBufferFree
0x1800577b9  jmp     short loc_1800577C2
0x1800577bb  mov     rcx, [rbp+47h+Buffer]
0x1800577bf  mov     [r14], rcx
0x1800577c2  mov     eax, edi
0x1800577c4  mov     rcx, [rbp+47h+var_40]
0x1800577c8  xor     rcx, rsp; StackCookie
0x1800577cb  call    __security_check_cookie
0x1800577d0  mov     rbx, [rsp+110h+arg_8]
0x1800577d8  add     rsp, 0E0h
0x1800577df  pop     r15
0x1800577e1  pop     r14
0x1800577e3  pop     r13
0x1800577e5  pop     r12
0x1800577e7  pop     rdi
0x1800577e8  pop     rsi
0x1800577e9  pop     rbp
0x1800577ea  retn
```
