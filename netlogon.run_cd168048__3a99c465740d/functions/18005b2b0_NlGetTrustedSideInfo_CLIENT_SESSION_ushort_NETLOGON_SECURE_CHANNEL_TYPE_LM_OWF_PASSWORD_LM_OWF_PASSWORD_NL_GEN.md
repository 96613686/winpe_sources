# NlGetTrustedSideInfo(_CLIENT_SESSION *,ushort *,_NETLOGON_SECURE_CHANNEL_TYPE,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,_NL_GENERIC_RPC_DATA * *)

- ea: `0x18005b2b0`
- end: `0x18005b680`
- name: `?NlGetTrustedSideInfo@@YAJPEAU_CLIENT_SESSION@@PEAGW4_NETLOGON_SECURE_CHANNEL_TYPE@@PEAU_LM_OWF_PASSWORD@@3PEAPEAU_NL_GENERIC_RPC_DATA@@@Z`
- size: `976`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18005dfe0`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x18000e910`
- `0x180037344`
- `0x180040f18`
- `0x180040fe4`
- `0x18005b2b0`
- `0x1800637d0`
- `0x180063c38`
- `0x180064c90`
- `0x180065048`
- `0x180069c60`
- `0x18006d2b0`
- `0x18006d794`

## import_xrefs

- `logoncli!I_NetServerGetTrustInfo` at `0x18005b451`
- `logoncli!I_NetServerGetTrustInfo` at `0x18005b451`
- `ntdll!RtlLeaveCriticalSection` at `0x18005b4c4`
- `ntdll!RtlLeaveCriticalSection` at `0x18005b4c4`
- `ntdll!RtlEnterCriticalSection` at `0x18005b4a9`
- `ntdll!RtlEnterCriticalSection` at `0x18005b4a9`
- `netutils!NetApiBufferFree` at `0x18005b641`
- `netutils!NetApiBufferFree` at `0x18005b641`

## string_xrefs

- `0x18005b3d9`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005b591`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005b5c4`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005b5dc`: `NlGetTrustedSideInfo: NlBuildAuthenticator failed with status: 0x%lx\n`
- `0x18005b527`: `NlGetTrustedSideInfo: denying access after status: 0x%lx\n`
- `0x18005b624`: `NlGetTrustedSideInfo: %ws: failed %lX\n`

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
        0x123Fu,
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
          NlAssertFailed(
            "NT_SUCCESS(Status)",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx",
            0x12A1u,
            v24);
        started = NlpDecryptNtOwf(v41, &v43, &v40, v32);
        if ( started < 0 )
          NlAssertFailed(
            "NT_SUCCESS(Status)",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx",
            0x12A8u,
            v25);
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
0x18005b2b0  mov     [rsp-8+arg_8], rbx
0x18005b2b5  push    rbp
0x18005b2b6  push    rsi
0x18005b2b7  push    rdi
0x18005b2b8  push    r12
0x18005b2ba  push    r13
0x18005b2bc  push    r14
0x18005b2be  push    r15
0x18005b2c0  lea     rbp, [rsp-17h]
0x18005b2c5  sub     rsp, 0E0h
0x18005b2cc  mov     rax, cs:__security_cookie
0x18005b2d3  xor     rax, rsp
0x18005b2d6  mov     [rbp+47h+var_40], rax
0x18005b2da  mov     rax, [rbp+47h+arg_20]
0x18005b2de  xorps   xmm0, xmm0
0x18005b2e1  mov     r14, [rbp+47h+arg_28]
0x18005b2e5  xorps   xmm1, xmm1
0x18005b2e8  mov     [rbp+47h+var_A0], rax
0x18005b2ec  mov     rsi, rcx
0x18005b2ef  xor     eax, eax
0x18005b2f1  mov     [rbp+47h+var_A8], r9
0x18005b2f5  test    dword ptr [rcx+198h], 200h
0x18005b2ff  mov     [rbp+47h+var_B8], r14
0x18005b303  mov     [rbp+47h+var_98], 0
0x18005b307  mov     [rbp+47h+var_97], rax
0x18005b30b  mov     [rbp+47h+var_8F], ax
0x18005b30f  mov     [rbp+47h+var_8D], al
0x18005b312  mov     [rbp+47h+var_88], al
0x18005b315  mov     qword ptr [rbp+47h+var_88+1], rax
0x18005b319  mov     [rbp+47h+var_7F], ax
0x18005b31d  mov     [rbp+47h+var_7D], al
0x18005b320  movups  xmmword ptr [rbp+47h+var_78.data.data], xmm0
0x18005b324  mov     [rbp+47h+var_68], eax
0x18005b327  movups  xmmword ptr [rbp+47h+var_60.data.data], xmm0
0x18005b32b  mov     [rbp+47h+Buffer], rax
0x18005b32f  movups  xmmword ptr [rbp+47h+var_50.data.data], xmm1
0x18005b333  jz      short loc_18005B33F
0x18005b335  mov     eax, 0C00000BBh
0x18005b33a  jmp     loc_18005B658
0x18005b33f  xor     edx, edx; unsigned int
0x18005b341  xor     r15b, r15b
0x18005b344  xor     ebx, ebx
0x18005b346  call    ?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z; NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)
0x18005b34b  mov     edi, eax
0x18005b34d  test    eax, eax
0x18005b34f  js      loc_18005B5F1
0x18005b355  mov     [rbp+47h+var_C0], 1
0x18005b359  lea     r12, [rsi+1B8h]
0x18005b360  lea     r13, [rsi+1B0h]
0x18005b367  movups  xmm0, xmmword ptr [r12]
0x18005b36c  mov     r9d, [rsi+13Ch]; unsigned int
0x18005b373  lea     r8, [rbp+47h+var_98]; struct _NETLOGON_AUTHENTICATOR *
0x18005b377  mov     rbx, [r13+0]
0x18005b37b  mov     rdx, r12; struct _NETLOGON_SESSION_KEY *
0x18005b37e  mov     rcx, r13; struct _CYPHER_BLOCK *
0x18005b381  mov     [rbp+47h+var_68], r9d
0x18005b385  movdqu  xmmword ptr [rbp+47h+var_78.data.data], xmm0
0x18005b38a  call    ?NlBuildAuthenticator@@YAJPEAU_CYPHER_BLOCK@@PEAU_NETLOGON_SESSION_KEY@@PEAU_NETLOGON_AUTHENTICATOR@@K@Z; NlBuildAuthenticator(_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,_NETLOGON_AUTHENTICATOR *,ulong)
0x18005b38f  mov     edi, eax
0x18005b391  test    eax, eax
0x18005b393  js      loc_18005B5D9
0x18005b399  mov     edi, 0C0020004h
0x18005b39e  xor     r14d, r14d
0x18005b3a1  lea     rax, [rsi+2A8h]
0x18005b3a8  mov     r9d, edi; int
0x18005b3ab  mov     r8d, r14d; unsigned int
0x18005b3ae  mov     [rsp+110h+var_F0], rax; struct _CLIENT_API *
0x18005b3b3  mov     dl, 1; unsigned __int8
0x18005b3b5  mov     rcx, rsi; struct _CLIENT_SESSION *
0x18005b3b8  call    ?NlStartApiClientSession@@YAJPEAU_CLIENT_SESSION@@EKJPEAU_CLIENT_API@@@Z; NlStartApiClientSession(_CLIENT_SESSION *,uchar,ulong,long,_CLIENT_API *)
0x18005b3bd  mov     edi, eax
0x18005b3bf  test    eax, eax
0x18005b3c1  js      loc_18005B478
0x18005b3c7  mov     rcx, [rsi+1F8h]
0x18005b3ce  test    rcx, rcx
0x18005b3d1  jnz     short loc_18005B3F3
0x18005b3d3  mov     r8d, 123Fh; unsigned int
0x18005b3d9  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005b3e0  lea     rcx, aClientsessionC_2; "ClientSession->CsUncServerName != NULL"
0x18005b3e7  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18005b3ec  mov     rcx, [rsi+1F8h]
0x18005b3f3  test    dword ptr [rsi+124h], 40000h
0x18005b3fd  jz      short loc_18005B408
0x18005b3ff  mov     r9, [rsi+0D8h]
0x18005b406  jmp     short loc_18005B416
0x18005b408  mov     rax, [rsi+110h]
0x18005b40f  mov     r9, [rax+108h]
0x18005b416  mov     r8d, [rsi+118h]
0x18005b41d  lea     rax, [rbp+47h+Buffer]
0x18005b421  mov     rdx, [rsi+0C8h]
0x18005b428  mov     [rsp+110h+var_D0], rax
0x18005b42d  lea     rax, [rbp+47h+var_50]
0x18005b431  mov     [rsp+110h+var_D8], rax
0x18005b436  lea     rax, [rbp+47h+var_60]
0x18005b43a  mov     [rsp+110h+var_E0], rax
0x18005b43f  lea     rax, [rbp+47h+var_88]
0x18005b443  mov     [rsp+110h+var_E8], rax
0x18005b448  lea     rax, [rbp+47h+var_98]
0x18005b44c  mov     [rsp+110h+var_F0], rax
0x18005b451  call    cs:__imp_I_NetServerGetTrustInfo
0x18005b458  nop     dword ptr [rax+rax+00h]
0x18005b45d  mov     edi, eax
0x18005b45f  cmp     eax, 0C002002Eh
0x18005b464  jz      short loc_18005B4A2
0x18005b466  test    eax, eax
0x18005b468  jns     short loc_18005B478
0x18005b46a  mov     edx, eax; int
0x18005b46c  lea     rcx, aINetservergett; "I_NetServerGetTrustInfo"
0x18005b473  call    ?NlPrintRpcDebug@@YAXPEBDJ@Z; NlPrintRpcDebug(char const *,long)
0x18005b478  lea     eax, [rdi+3FFDFFFCh]
0x18005b47e  cmp     eax, 32h ; '2'
0x18005b481  ja      short loc_18005B4D5
0x18005b483  mov     rcx, 4000000080001h
0x18005b48d  bt      rcx, rax
0x18005b491  jnb     short loc_18005B4D5
0x18005b493  inc     r14d
0x18005b496  cmp     r14d, 2
0x18005b49a  jb      loc_18005B3A1
0x18005b4a0  jmp     short loc_18005B4D5
0x18005b4a2  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18005b4a9  call    cs:__imp_RtlEnterCriticalSection
0x18005b4b0  nop     dword ptr [rax+rax+00h]
0x18005b4b5  bts     dword ptr [rsi+198h], 9
0x18005b4bd  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18005b4c4  call    cs:__imp_RtlLeaveCriticalSection
0x18005b4cb  nop     dword ptr [rax+rax+00h]
0x18005b4d0  xor     edi, edi
0x18005b4d2  mov     r15b, 1
0x18005b4d5  mov     r8b, 1; unsigned __int8
0x18005b4d8  lea     r9, [rsi+2A8h]; struct _CLIENT_API *
0x18005b4df  mov     dl, r8b; unsigned __int8
0x18005b4e2  mov     rcx, rsi; struct _CLIENT_SESSION *
0x18005b4e5  call    ?NlFinishApiClientSession@@YAEPEAU_CLIENT_SESSION@@EEPEAU_CLIENT_API@@@Z; NlFinishApiClientSession(_CLIENT_SESSION *,uchar,uchar,_CLIENT_API *)
0x18005b4ea  test    r15b, r15b
0x18005b4ed  jnz     loc_18005B5ED
0x18005b4f3  mov     r14d, 0C0000022h
0x18005b4f9  cmp     edi, r14d
0x18005b4fc  jz      short loc_18005B524
0x18005b4fe  mov     rcx, rsi; struct _CLIENT_SESSION *
0x18005b501  call    ?NlCheckRpcAuthIsNetlogon@@YAHPEAU_CLIENT_SESSION@@@Z; NlCheckRpcAuthIsNetlogon(_CLIENT_SESSION *)
0x18005b506  test    eax, eax
0x18005b508  jz      short loc_18005B56F
0x18005b50a  mov     r9d, [rsi+13Ch]; unsigned int
0x18005b511  lea     rdx, [rbp+47h+var_88]; struct _CYPHER_BLOCK *
0x18005b515  mov     r8, r12; pbSecret
0x18005b518  mov     rcx, r13; pbInput
0x18005b51b  call    ?NlUpdateSeed@@YAHPEAU_CYPHER_BLOCK@@0PEAU_NETLOGON_SESSION_KEY@@K@Z; NlUpdateSeed(_CYPHER_BLOCK *,_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,ulong)
0x18005b520  test    eax, eax
0x18005b522  jnz     short loc_18005B56F
0x18005b524  mov     r9d, edi
0x18005b527  lea     r8, aNlgettrustedsi_0; "NlGetTrustedSideInfo: denying access af"...
0x18005b52e  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18005b531  mov     ecx, 100h; unsigned int
0x18005b536  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18005b53b  test    edi, edi
0x18005b53d  mov     rcx, rsi; struct _CLIENT_SESSION *
0x18005b540  cmovns  edi, r14d
0x18005b544  mov     edx, edi; int
0x18005b546  call    ?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z; NlSetStatusClientSession(_CLIENT_SESSION *,long)
0x18005b54b  cmp     [rbp+47h+var_C0], 0
0x18005b54f  jz      loc_18005B5ED
0x18005b555  xor     edx, edx; unsigned int
0x18005b557  mov     [rbp+47h+var_C0], 0
0x18005b55b  mov     rcx, rsi; struct _CLIENT_SESSION *
0x18005b55e  call    ?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z; NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)
0x18005b563  mov     edi, eax
0x18005b565  test    eax, eax
0x18005b567  jns     loc_18005B367
0x18005b56d  jmp     short loc_18005B5ED
0x18005b56f  test    edi, edi
0x18005b571  js      short loc_18005B5ED
0x18005b573  mov     r9, [rbp+47h+var_A8]; struct _LM_OWF_PASSWORD *
0x18005b577  lea     r8, [rbp+47h+var_78]; struct _LM_OWF_PASSWORD *
0x18005b57b  mov     ecx, [rbp+47h+var_68]; unsigned int
0x18005b57e  lea     rdx, [rbp+47h+var_60]; struct _ENCRYPTED_LM_OWF_PASSWORD *
0x18005b582  call    ?NlpDecryptNtOwf@@YAJKPEAU_ENCRYPTED_LM_OWF_PASSWORD@@PEAU_LM_OWF_PASSWORD@@1@Z; NlpDecryptNtOwf(ulong,_ENCRYPTED_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *)
0x18005b587  test    eax, eax
0x18005b589  jns     short loc_18005B5A4
0x18005b58b  mov     r8d, 12A1h; unsigned int
0x18005b591  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005b598  lea     rcx, aNtSuccessStatu_4; "NT_SUCCESS(Status)"
0x18005b59f  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18005b5a4  mov     r9, [rbp+47h+var_A0]; struct _LM_OWF_PASSWORD *
0x18005b5a8  lea     r8, [rbp+47h+var_78]; struct _LM_OWF_PASSWORD *
0x18005b5ac  mov     ecx, [rbp+47h+var_68]; unsigned int
0x18005b5af  lea     rdx, [rbp+47h+var_50]; struct _ENCRYPTED_LM_OWF_PASSWORD *
0x18005b5b3  call    ?NlpDecryptNtOwf@@YAJKPEAU_ENCRYPTED_LM_OWF_PASSWORD@@PEAU_LM_OWF_PASSWORD@@1@Z; NlpDecryptNtOwf(ulong,_ENCRYPTED_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *)
0x18005b5b8  mov     edi, eax
0x18005b5ba  test    eax, eax
0x18005b5bc  jns     short loc_18005B5ED
0x18005b5be  mov     r8d, 12A8h; unsigned int
0x18005b5c4  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005b5cb  lea     rcx, aNtSuccessStatu_4; "NT_SUCCESS(Status)"
0x18005b5d2  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18005b5d7  jmp     short loc_18005B5ED
0x18005b5d9  mov     r8d, eax
0x18005b5dc  lea     rdx, aNlgettrustedsi; "NlGetTrustedSideInfo: NlBuildAuthentica"...
0x18005b5e3  mov     ecx, 100h; unsigned int
0x18005b5e8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005b5ed  mov     r14, [rbp+47h+var_B8]
0x18005b5f1  mov     ecx, 10h
0x18005b5f6  lea     rax, [rbp+47h+var_78]
0x18005b5fa  mov     byte ptr [rax], 0
0x18005b5fd  inc     rax
0x18005b600  sub     rcx, 1
0x18005b604  jnz     short loc_18005B5FA
0x18005b606  test    r15b, r15b
0x18005b609  jz      short loc_18005B619
0x18005b60b  mov     [rsi+1B0h], rbx
0x18005b612  mov     edi, 0C00000BBh
0x18005b617  jmp     short loc_18005B61D
0x18005b619  test    edi, edi
0x18005b61b  jns     short loc_18005B64F
0x18005b61d  xor     r9d, r9d
0x18005b620  mov     dword ptr [rsp+110h+var_F0], edi
0x18005b624  lea     r8, aNlgettrustedsi_1; "NlGetTrustedSideInfo: %ws: failed %lX\n"
0x18005b62b  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18005b62e  mov     ecx, 100h; unsigned int
0x18005b633  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18005b638  mov     rcx, [rbp+47h+Buffer]; Buffer
0x18005b63c  test    rcx, rcx
0x18005b63f  jz      short loc_18005B656
0x18005b641  call    cs:__imp_NetApiBufferFree
0x18005b648  nop     dword ptr [rax+rax+00h]
0x18005b64d  jmp     short loc_18005B656
0x18005b64f  mov     rcx, [rbp+47h+Buffer]
0x18005b653  mov     [r14], rcx
0x18005b656  mov     eax, edi
0x18005b658  mov     rcx, [rbp+47h+var_40]
0x18005b65c  xor     rcx, rsp; StackCookie
0x18005b65f  call    __security_check_cookie
0x18005b664  mov     rbx, [rsp+110h+arg_8]
0x18005b66c  add     rsp, 0E0h
0x18005b673  pop     r15
0x18005b675  pop     r14
0x18005b677  pop     r13
0x18005b679  pop     r12
0x18005b67b  pop     rdi
0x18005b67c  pop     rsi
0x18005b67d  pop     rbp
0x18005b67e  retn
```
