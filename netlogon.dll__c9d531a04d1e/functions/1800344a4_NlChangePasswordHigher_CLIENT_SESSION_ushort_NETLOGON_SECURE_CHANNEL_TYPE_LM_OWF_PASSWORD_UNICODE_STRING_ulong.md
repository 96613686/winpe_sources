# NlChangePasswordHigher(_CLIENT_SESSION *,ushort *,_NETLOGON_SECURE_CHANNEL_TYPE,_LM_OWF_PASSWORD *,_UNICODE_STRING *,ulong *)

- ea: `0x1800344a4`
- end: `0x180034a38`
- name: `?NlChangePasswordHigher@@YAJPEAU_CLIENT_SESSION@@PEAGW4_NETLOGON_SECURE_CHANNEL_TYPE@@PEAU_LM_OWF_PASSWORD@@PEAU_UNICODE_STRING@@PEAK@Z`
- size: `1428`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, char *, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update`

## callers

- `0x180033a34`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18000e270`
- `0x18000ed34`
- `0x1800344a4`
- `0x180035368`
- `0x18003e71c`
- `0x18003e7dc`
- `0x18003f034`
- `0x18005f358`
- `0x18005f79c`
- `0x18005fce8`
- `0x18005ffb0`
- `0x180060734`
- `0x180060b08`
- `0x18006515c`
- `0x180068458`
- `0x1800688e0`
- `0x180089ab4`

## import_xrefs

- `logoncli!I_NetServerPasswordSet` at `0x1800348be`
- `logoncli!I_NetServerPasswordSet` at `0x1800348be`
- `logoncli!I_NetServerPasswordSet2` at `0x180034763`
- `logoncli!I_NetServerPasswordSet2` at `0x180034763`
- `CRYPTSP!SystemFunction007` at `0x1800347c0`
- `CRYPTSP!SystemFunction007` at `0x1800347c0`

## string_xrefs

- `0x18003454e`: `ClientSession->CsFlags & CS_WRITER`
- `0x180034525`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180034547`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x18003461d`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180034644`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180034703`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x18003485e`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x18003495b`: `NlChangePasswordHigher: denying access after status: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NlChangePasswordHigher(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        char *a4,
        unsigned __int16 *a5,
        int *a6)
{
  unsigned __int16 *v6; // r15
  struct _LM_OWF_PASSWORD *v7; // rsi
  __int64 v8; // r14
  int started; // ebx
  __int64 v11; // r12
  struct _NETLOGON_SESSION_KEY *v12; // r13
  __int128 v13; // xmm0
  int v14; // eax
  char *v15; // r9
  int v16; // edx
  _DWORD *v17; // rcx
  struct _CLIENT_API *v18; // r14
  unsigned int v19; // esi
  __int64 v20; // r15
  char *v21; // r9
  __int64 v22; // rcx
  __int64 v23; // r9
  int v24; // eax
  unsigned __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rcx
  __int128 *v28; // rax
  unsigned int v29; // esi
  __int64 v30; // r15
  char *v31; // r9
  __int64 v32; // rcx
  __int64 v33; // r9
  int v34; // eax
  unsigned __int64 v35; // rax
  __int128 *v36; // rax
  struct _CLIENT_API *v38; // [rsp+20h] [rbp-E0h]
  char v39; // [rsp+40h] [rbp-C0h]
  struct _LM_OWF_PASSWORD *v42; // [rsp+60h] [rbp-A0h]
  __int64 v43; // [rsp+68h] [rbp-98h] BYREF
  int v44; // [rsp+70h] [rbp-90h]
  struct _CYPHER_BLOCK v45; // [rsp+78h] [rbp-88h] BYREF
  int v46; // [rsp+80h] [rbp-80h]
  __int128 v47; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v48; // [rsp+98h] [rbp-68h]
  __int128 v49; // [rsp+A0h] [rbp-60h] BYREF
  struct _ENCRYPTED_LM_OWF_PASSWORD v50; // [rsp+B0h] [rbp-50h] BYREF
  BYTE pbBuffer[500]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v52[12]; // [rsp+2B4h] [rbp+1B4h] BYREF
  int v53; // [rsp+2C0h] [rbp+1C0h] BYREF

  v6 = a5;
  v7 = (struct _LM_OWF_PASSWORD *)a4;
  v8 = a2;
  v42 = (struct _LM_OWF_PASSWORD *)a4;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v39 = 1;
  if ( !*(_DWORD *)(a1 + 328) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
      6040,
      a4);
  if ( (*(_BYTE *)(a1 + 292) & 8) == 0 )
    NlAssertFailed(
      "ClientSession->CsFlags & CS_WRITER",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
      6041,
      a4);
  started = NlEnsureSessionAuthenticated((struct _CLIENT_SESSION *)a1, 0);
  v11 = 16;
  if ( started >= 0 )
  {
    v12 = (struct _NETLOGON_SESSION_KEY *)(a1 + 440);
    while ( 1 )
    {
      v13 = *(_OWORD *)v12;
      v48 = *(_DWORD *)(a1 + 316);
      v47 = v13;
      v14 = NlBuildAuthenticator((struct _CYPHER_BLOCK *)(a1 + 432), v12, (struct _NETLOGON_AUTHENTICATOR *)&v43, v48);
      started = v14;
      if ( v14 < 0 )
        break;
      if ( v6 && (v48 & 0x20000) != 0 )
      {
        memset_0(pbBuffer, 0, 0x204u);
        memcpy_0((char *)&v53 - *v6, *((const void **)v6 + 1), *v6);
        v53 = *v6;
        if ( a3 - 3 <= 1 )
        {
          if ( !a6 )
            NlAssertFailed(
              "ClearPasswordVersionNumber != NULL",
              "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
              6122,
              v15);
          if ( *v6 == 500 )
            NlAssertFailed(
              "NL_MAX_PASSWORD_LENGTH * sizeof(WCHAR) - NewClearPassword->Length - sizeof(PasswordVersion) > 0",
              "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
              6125,
              v15);
          v16 = *a6;
          v17 = &v52[-*v6];
          *v17 = 0;
          v17[1] = v16;
          v17[2] = 35854696;
        }
        if ( !NlGenerateRandomBits(pbBuffer, 500 - *v6) )
          NlPrintRoutine(0x100u, L"Can't NlGenerateRandomBits for clear password prefix\n");
        NlEncrypt(pbBuffer, 0x204u, (struct _SESSION_INFO *)&v47);
        v18 = (struct _CLIENT_API *)(a1 + 680);
        v19 = 0;
        started = -1073610748;
        v20 = 0x4000000080001LL;
        do
        {
          started = NlStartApiClientSession(
                      (struct _CLIENT_SESSION *)a1,
                      1u,
                      v19,
                      started,
                      (struct _CLIENT_API *)(a1 + 680));
          if ( started >= 0 )
          {
            v22 = *(_QWORD *)(a1 + 504);
            if ( !v22 )
            {
              NlAssertFailed(
                "ClientSession->CsUncServerName != NULL",
                "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
                6165,
                v21);
              v22 = *(_QWORD *)(a1 + 504);
            }
            if ( (*(_DWORD *)(a1 + 292) & 0x40000) != 0 )
              v23 = *(_QWORD *)(a1 + 216);
            else
              v23 = *(_QWORD *)(*(_QWORD *)(a1 + 272) + 264LL);
            v24 = I_NetServerPasswordSet2(v22, a2, a3, v23, &v43, &v45, pbBuffer);
            started = v24;
            if ( v24 < 0 )
              NlPrintRpcDebug("I_NetServerPasswordSet2", v24);
          }
          v25 = (unsigned int)(started + 1073610748);
          if ( (unsigned int)v25 > 0x32 )
            break;
          if ( !_bittest64(&v20, v25) )
            break;
          ++v19;
        }
        while ( v19 < 2 );
      }
      else
      {
        v50 = 0;
        v49 = 0;
        if ( !v7 )
        {
          v26 = SystemFunction007(v6, &v49);
          started = v26;
          if ( v26 < 0 )
          {
            NlPrintCsRoutine(
              0x100u,
              (struct _CLIENT_SESSION *)a1,
              L"NlChangePasswordHigher: Cannot RtlCalculateNtOwfPassword %lX\n",
              (unsigned int)v26);
            goto LABEL_61;
          }
          v7 = (struct _LM_OWF_PASSWORD *)&v49;
          v42 = (struct _LM_OWF_PASSWORD *)&v49;
        }
        started = NlpEncryptNtOwf(*(_DWORD *)(a1 + 316), v7, (struct _LM_OWF_PASSWORD *)v12, &v50);
        v27 = 16;
        v28 = &v49;
        do
        {
          *(_BYTE *)v28 = 0;
          v28 = (__int128 *)((char *)v28 + 1);
          --v27;
        }
        while ( v27 );
        if ( started < 0 )
        {
          NlPrintCsRoutine(
            0x100u,
            (struct _CLIENT_SESSION *)a1,
            L"NlChangePasswordHigher: Cannot NlpEncryptNtOwf %lX\n",
            (unsigned int)started);
          goto LABEL_61;
        }
        v18 = (struct _CLIENT_API *)(a1 + 680);
        started = -1073610748;
        v29 = 0;
        v30 = 0x4000000080001LL;
        do
        {
          started = NlStartApiClientSession(
                      (struct _CLIENT_SESSION *)a1,
                      1u,
                      v29,
                      started,
                      (struct _CLIENT_API *)(a1 + 680));
          if ( started >= 0 )
          {
            v32 = *(_QWORD *)(a1 + 504);
            if ( !v32 )
            {
              NlAssertFailed(
                "ClientSession->CsUncServerName != NULL",
                "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
                6241,
                v31);
              v32 = *(_QWORD *)(a1 + 504);
            }
            if ( (*(_DWORD *)(a1 + 292) & 0x40000) != 0 )
              v33 = *(_QWORD *)(a1 + 216);
            else
              v33 = *(_QWORD *)(*(_QWORD *)(a1 + 272) + 264LL);
            v34 = I_NetServerPasswordSet(v32, a2, a3, v33, &v43, &v45, &v50);
            started = v34;
            if ( v34 < 0 )
              NlPrintRpcDebug("I_NetServerPasswordSet", v34);
          }
          v35 = (unsigned int)(started + 1073610748);
          if ( (unsigned int)v35 > 0x32 )
            break;
          if ( !_bittest64(&v30, v35) )
            break;
          ++v29;
        }
        while ( v29 < 2 );
      }
      NlFinishApiClientSession((struct _CLIENT_SESSION *)a1, 1u, 1u, v18);
      v6 = a5;
      v12 = (struct _NETLOGON_SESSION_KEY *)(a1 + 440);
      v11 = 16;
      if ( !NlpDidDcFail(started)
        && (!(unsigned int)NlCheckRpcAuthIsNetlogon((struct _CLIENT_SESSION *)a1)
         || (unsigned int)NlUpdateSeed((PUCHAR)(a1 + 432), &v45, (PUCHAR)(a1 + 440), *(_DWORD *)(a1 + 316))) )
      {
        goto LABEL_61;
      }
      NlPrintCsRoutine(
        0x100u,
        (struct _CLIENT_SESSION *)a1,
        L"NlChangePasswordHigher: denying access after status: 0x%lx\n",
        (unsigned int)started);
      if ( started >= 0 )
        started = -1073741790;
      NlSetStatusClientSession((struct _CLIENT_SESSION *)a1, started);
      if ( !v39 )
        goto LABEL_61;
      v39 = 0;
      started = NlEnsureSessionAuthenticated((struct _CLIENT_SESSION *)a1, 0);
      if ( started < 0 )
        goto LABEL_61;
      v7 = v42;
    }
    NlPrintRoutine(
      0x100u,
      L"NlChangePasswordHigher: NlBuildAuthenticator failed with status: 0x%lx\n",
      (unsigned int)v14);
LABEL_61:
    v8 = a2;
  }
  v36 = &v47;
  do
  {
    *(_BYTE *)v36 = 0;
    v36 = (__int128 *)((char *)v36 + 1);
    --v11;
  }
  while ( v11 );
  if ( started < 0 )
  {
    LODWORD(v38) = started;
    NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, L"NlChangePasswordHigher: %ws: failed %lX\n", v8, v38);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800344a4  push    rbp
0x1800344a6  push    rbx
0x1800344a7  push    rsi
0x1800344a8  push    rdi
0x1800344a9  push    r12
0x1800344ab  push    r13
0x1800344ad  push    r14
0x1800344af  push    r15
0x1800344b1  lea     rbp, [rsp-1E8h]
0x1800344b9  sub     rsp, 2E8h
0x1800344c0  mov     rax, cs:__security_cookie
0x1800344c7  xor     rax, rsp
0x1800344ca  mov     [rbp+220h+var_50], rax
0x1800344d1  mov     r15, [rbp+220h+arg_20]
0x1800344d8  xor     eax, eax
0x1800344da  xorps   xmm0, xmm0
0x1800344dd  mov     rsi, r9
0x1800344e0  mov     r14, rdx
0x1800344e3  mov     [rsp+320h+var_2C0], r9
0x1800344e8  mov     rdi, rcx
0x1800344eb  mov     [rsp+320h+var_2D0], r8d
0x1800344f0  mov     [rsp+320h+var_2D8], rdx
0x1800344f5  mov     [rsp+320h+var_2C8], r15
0x1800344fa  mov     [rsp+320h+var_2B8], rax
0x1800344ff  mov     [rsp+320h+var_2B0], eax
0x180034503  mov     qword ptr [rsp+320h+var_2A8.data], rax
0x180034508  mov     [rbp+220h+var_2A0], eax
0x18003450b  movups  [rbp+220h+var_298], xmm0
0x18003450f  mov     [rbp+220h+var_288], eax
0x180034512  mov     [rsp+320h+var_2E0], 1
0x180034517  cmp     [rcx+148h], eax
0x18003451d  ja      short loc_180034538
0x18003451f  mov     r8d, 1798h; unsigned int
0x180034525  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18003452c  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x180034533  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180034538  test    byte ptr [rdi+124h], 8
0x18003453f  jnz     short loc_18003455A
0x180034541  mov     r8d, 1799h; unsigned int
0x180034547  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18003454e  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x180034555  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18003455a  xor     edx, edx; unsigned int
0x18003455c  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18003455f  call    ?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z; NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)
0x180034564  mov     ebx, eax
0x180034566  mov     r12d, 10h
0x18003456c  test    eax, eax
0x18003456e  js      loc_1800349E4
0x180034574  lea     r13, [rdi+1B8h]
0x18003457b  mov     r14d, 100h
0x180034581  lea     rax, [rdi+1B0h]
0x180034588  movups  xmm0, xmmword ptr [r13+0]
0x18003458d  mov     r9d, [rdi+13Ch]; unsigned int
0x180034594  lea     r8, [rsp+320h+var_2B8]; struct _NETLOGON_AUTHENTICATOR *
0x180034599  mov     rdx, r13; struct _NETLOGON_SESSION_KEY *
0x18003459c  mov     [rbp+220h+var_288], r9d
0x1800345a0  mov     rcx, rax; struct _CYPHER_BLOCK *
0x1800345a3  movdqu  [rbp+220h+var_298], xmm0
0x1800345a8  call    ?NlBuildAuthenticator@@YAJPEAU_CYPHER_BLOCK@@PEAU_NETLOGON_SESSION_KEY@@PEAU_NETLOGON_AUTHENTICATOR@@K@Z; NlBuildAuthenticator(_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,_NETLOGON_AUTHENTICATOR *,ulong)
0x1800345ad  mov     ebx, eax
0x1800345af  test    eax, eax
0x1800345b1  js      loc_1800349CD
0x1800345b7  test    r15, r15
0x1800345ba  jz      loc_1800347A6
0x1800345c0  test    [rbp+220h+var_288], 20000h
0x1800345c7  jz      loc_1800347A6
0x1800345cd  xor     edx, edx; Val
0x1800345cf  lea     rcx, [rbp+220h+pbBuffer]; void *
0x1800345d3  mov     r8d, 204h; Size
0x1800345d9  call    memset_0
0x1800345de  movzx   r8d, word ptr [r15]; Size
0x1800345e2  lea     rcx, [rbp+220h+var_60]
0x1800345e9  mov     rdx, [r15+8]; Src
0x1800345ed  sub     rcx, r8; void *
0x1800345f0  call    memcpy_0
0x1800345f5  movzx   eax, word ptr [r15]
0x1800345f9  mov     [rbp+220h+var_60], eax
0x1800345ff  mov     eax, [rsp+320h+var_2D0]
0x180034603  add     eax, 0FFFFFFFDh
0x180034606  cmp     eax, 1
0x180034609  ja      short loc_180034677
0x18003460b  mov     rbx, [rbp+220h+arg_28]
0x180034612  test    rbx, rbx
0x180034615  jnz     short loc_180034630
0x180034617  mov     r8d, 17EAh; unsigned int
0x18003461d  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180034624  lea     rcx, aClearpasswordv; "ClearPasswordVersionNumber != NULL"
0x18003462b  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180034630  movzx   ecx, word ptr [r15]
0x180034634  mov     eax, 1F4h
0x180034639  cmp     rax, rcx
0x18003463c  jnz     short loc_180034657
0x18003463e  mov     r8d, 17EDh; unsigned int
0x180034644  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18003464b  lea     rcx, aNlMaxPasswordL; "NL_MAX_PASSWORD_LENGTH * sizeof(WCHAR) "...
0x180034652  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180034657  movzx   eax, word ptr [r15]
0x18003465b  lea     rcx, [rbp+220h+var_6C]
0x180034662  mov     edx, [rbx]
0x180034664  sub     rcx, rax
0x180034667  mov     dword ptr [rcx], 0
0x18003466d  mov     [rcx+4], edx
0x180034670  mov     dword ptr [rcx+8], 2231968h
0x180034677  movzx   eax, word ptr [r15]
0x18003467b  lea     rcx, [rbp+220h+pbBuffer]; pbBuffer
0x18003467f  mov     edx, 1F4h
0x180034684  sub     edx, eax; unsigned int
0x180034686  call    ?NlGenerateRandomBits@@YAEPEAEK@Z; NlGenerateRandomBits(uchar *,ulong)
0x18003468b  test    al, al
0x18003468d  jnz     short loc_18003469E
0x18003468f  lea     rdx, aCanTNlgenerate_0; "Can't NlGenerateRandomBits for clear pa"...
0x180034696  mov     ecx, r14d; unsigned int
0x180034699  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003469e  lea     r8, [rbp+220h+var_298]; struct _SESSION_INFO *
0x1800346a2  mov     edx, 204h; unsigned int
0x1800346a7  lea     rcx, [rbp+220h+pbBuffer]; void *
0x1800346ab  call    ?NlEncrypt@@YAXPEAXKPEAU_SESSION_INFO@@@Z; NlEncrypt(void *,ulong,_SESSION_INFO *)
0x1800346b0  mov     r13, [rsp+320h+var_2D8]
0x1800346b5  lea     r14, [rdi+2A8h]
0x1800346bc  mov     r12d, [rsp+320h+var_2D0]
0x1800346c1  xor     esi, esi
0x1800346c3  mov     ebx, 0C0020004h
0x1800346c8  mov     r15, 4000000080001h
0x1800346d2  mov     r9d, ebx; int
0x1800346d5  mov     [rsp+320h+var_300], r14; struct _CLIENT_API *
0x1800346da  mov     r8d, esi; unsigned int
0x1800346dd  mov     dl, 1; unsigned __int8
0x1800346df  mov     rcx, rdi; struct _CLIENT_SESSION *
0x1800346e2  call    ?NlStartApiClientSession@@YAJPEAU_CLIENT_SESSION@@EKJPEAU_CLIENT_API@@@Z; NlStartApiClientSession(_CLIENT_SESSION *,uchar,ulong,long,_CLIENT_API *)
0x1800346e7  mov     ebx, eax
0x1800346e9  test    eax, eax
0x1800346eb  js      loc_18003477D
0x1800346f1  mov     rcx, [rdi+1F8h]
0x1800346f8  test    rcx, rcx
0x1800346fb  jnz     short loc_18003471D
0x1800346fd  mov     r8d, 1815h; unsigned int
0x180034703  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18003470a  lea     rcx, aClientsessionC_2; "ClientSession->CsUncServerName != NULL"
0x180034711  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180034716  mov     rcx, [rdi+1F8h]
0x18003471d  test    dword ptr [rdi+124h], 40000h
0x180034727  jz      short loc_180034732
0x180034729  mov     r9, [rdi+0D8h]
0x180034730  jmp     short loc_180034740
0x180034732  mov     rax, [rdi+110h]
0x180034739  mov     r9, [rax+108h]
0x180034740  lea     rax, [rbp+220h+pbBuffer]
0x180034744  mov     r8d, r12d
0x180034747  mov     [rsp+320h+var_2F0], rax
0x18003474c  mov     rdx, r13
0x18003474f  lea     rax, [rsp+320h+var_2A8]
0x180034754  mov     [rsp+320h+var_2F8], rax
0x180034759  lea     rax, [rsp+320h+var_2B8]
0x18003475e  mov     [rsp+320h+var_300], rax
0x180034763  call    cs:__imp_I_NetServerPasswordSet2
0x180034769  mov     ebx, eax
0x18003476b  test    eax, eax
0x18003476d  jns     short loc_18003477D
0x18003476f  mov     edx, eax; int
0x180034771  lea     rcx, aINetserverpass; "I_NetServerPasswordSet2"
0x180034778  call    ?NlPrintRpcDebug@@YAXPEBDJ@Z; NlPrintRpcDebug(char const *,long)
0x18003477d  lea     eax, [rbx+3FFDFFFCh]
0x180034783  cmp     eax, 32h ; '2'
0x180034786  ja      loc_1800348F4
0x18003478c  bt      r15, rax
0x180034790  jnb     loc_1800348F4
0x180034796  inc     esi
0x180034798  cmp     esi, 2
0x18003479b  jb      loc_1800346D2
0x1800347a1  jmp     loc_1800348F4
0x1800347a6  xorps   xmm0, xmm0
0x1800347a9  xorps   xmm1, xmm1
0x1800347ac  movups  xmmword ptr [rbp+220h+var_270.data.data], xmm0
0x1800347b0  movups  [rbp+220h+var_280], xmm1
0x1800347b4  test    rsi, rsi
0x1800347b7  jnz     short loc_1800347D9
0x1800347b9  lea     rdx, [rbp+220h+var_280]
0x1800347bd  mov     rcx, r15
0x1800347c0  call    cs:__imp_SystemFunction007
0x1800347c6  mov     ebx, eax
0x1800347c8  test    eax, eax
0x1800347ca  js      loc_1800349AA
0x1800347d0  lea     rsi, [rbp+220h+var_280]
0x1800347d4  mov     [rsp+320h+var_2C0], rsi
0x1800347d9  mov     ecx, [rdi+13Ch]; unsigned int
0x1800347df  lea     r9, [rbp+220h+var_270]; struct _ENCRYPTED_LM_OWF_PASSWORD *
0x1800347e3  mov     r8, r13; struct _LM_OWF_PASSWORD *
0x1800347e6  mov     rdx, rsi; struct _LM_OWF_PASSWORD *
0x1800347e9  call    ?NlpEncryptNtOwf@@YAJKPEAU_LM_OWF_PASSWORD@@0PEAU_ENCRYPTED_LM_OWF_PASSWORD@@@Z; NlpEncryptNtOwf(ulong,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,_ENCRYPTED_LM_OWF_PASSWORD *)
0x1800347ee  mov     ebx, eax
0x1800347f0  mov     rcx, r12
0x1800347f3  lea     rax, [rbp+220h+var_280]
0x1800347f7  mov     byte ptr [rax], 0
0x1800347fa  inc     rax
0x1800347fd  sub     rcx, 1
0x180034801  jnz     short loc_1800347F7
0x180034803  test    ebx, ebx
0x180034805  js      loc_1800349C1
0x18003480b  mov     r13, [rsp+320h+var_2D8]
0x180034810  lea     r14, [rdi+2A8h]
0x180034817  mov     r12d, [rsp+320h+var_2D0]
0x18003481c  mov     ebx, 0C0020004h
0x180034821  xor     esi, esi
0x180034823  mov     r15, 4000000080001h
0x18003482d  mov     r9d, ebx; int
0x180034830  mov     [rsp+320h+var_300], r14; struct _CLIENT_API *
0x180034835  mov     r8d, esi; unsigned int
0x180034838  mov     dl, 1; unsigned __int8
0x18003483a  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18003483d  call    ?NlStartApiClientSession@@YAJPEAU_CLIENT_SESSION@@EKJPEAU_CLIENT_API@@@Z; NlStartApiClientSession(_CLIENT_SESSION *,uchar,ulong,long,_CLIENT_API *)
0x180034842  mov     ebx, eax
0x180034844  test    eax, eax
0x180034846  js      loc_1800348D8
0x18003484c  mov     rcx, [rdi+1F8h]
0x180034853  test    rcx, rcx
0x180034856  jnz     short loc_180034878
0x180034858  mov     r8d, 1861h; unsigned int
0x18003485e  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180034865  lea     rcx, aClientsessionC_2; "ClientSession->CsUncServerName != NULL"
0x18003486c  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180034871  mov     rcx, [rdi+1F8h]
0x180034878  test    dword ptr [rdi+124h], 40000h
0x180034882  jz      short loc_18003488D
0x180034884  mov     r9, [rdi+0D8h]
0x18003488b  jmp     short loc_18003489B
0x18003488d  mov     rax, [rdi+110h]
0x180034894  mov     r9, [rax+108h]
0x18003489b  lea     rax, [rbp+220h+var_270]
0x18003489f  mov     r8d, r12d
0x1800348a2  mov     [rsp+320h+var_2F0], rax
0x1800348a7  mov     rdx, r13
0x1800348aa  lea     rax, [rsp+320h+var_2A8]
0x1800348af  mov     [rsp+320h+var_2F8], rax
0x1800348b4  lea     rax, [rsp+320h+var_2B8]
0x1800348b9  mov     [rsp+320h+var_300], rax
0x1800348be  call    cs:__imp_I_NetServerPasswordSet
0x1800348c4  mov     ebx, eax
0x1800348c6  test    eax, eax
0x1800348c8  jns     short loc_1800348D8
0x1800348ca  mov     edx, eax; int
0x1800348cc  lea     rcx, aINetserverpass_0; "I_NetServerPasswordSet"
0x1800348d3  call    ?NlPrintRpcDebug@@YAXPEBDJ@Z; NlPrintRpcDebug(char const *,long)
0x1800348d8  lea     eax, [rbx+3FFDFFFCh]
0x1800348de  cmp     eax, 32h ; '2'
0x1800348e1  ja      short loc_1800348F4
0x1800348e3  bt      r15, rax
0x1800348e7  jnb     short loc_1800348F4
0x1800348e9  inc     esi
0x1800348eb  cmp     esi, 2
0x1800348ee  jb      loc_18003482D
0x1800348f4  mov     r8b, 1; unsigned __int8
0x1800348f7  mov     r9, r14; struct _CLIENT_API *
0x1800348fa  mov     dl, r8b; unsigned __int8
0x1800348fd  mov     rcx, rdi; struct _CLIENT_SESSION *
0x180034900  call    ?NlFinishApiClientSession@@YAEPEAU_CLIENT_SESSION@@EEPEAU_CLIENT_API@@@Z; NlFinishApiClientSession(_CLIENT_SESSION *,uchar,uchar,_CLIENT_API *)
0x180034905  mov     r15, [rsp+320h+var_2C8]
0x18003490a  lea     r13, [rdi+1B8h]
0x180034911  mov     ecx, ebx; int
0x180034913  mov     r12d, 10h
0x180034919  call    ?NlpDidDcFail@@YAEJ@Z; NlpDidDcFail(long)
0x18003491e  test    al, al
0x180034920  jnz     short loc_180034955
0x180034922  mov     rcx, rdi; struct _CLIENT_SESSION *
0x180034925  call    ?NlCheckRpcAuthIsNetlogon@@YAHPEAU_CLIENT_SESSION@@@Z; NlCheckRpcAuthIsNetlogon(_CLIENT_SESSION *)
0x18003492a  test    eax, eax
0x18003492c  jz      loc_1800349DF
0x180034932  mov     r9d, [rdi+13Ch]; unsigned int
0x180034939  lea     rdx, [rsp+320h+var_2A8]; struct _CYPHER_BLOCK *
0x18003493e  mov     r8, r13; pbSecret
0x180034941  lea     rcx, [rdi+1B0h]; pbInput
0x180034948  call    ?NlUpdateSeed@@YAHPEAU_CYPHER_BLOCK@@0PEAU_NETLOGON_SESSION_KEY@@K@Z; NlUpdateSeed(_CYPHER_BLOCK *,_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,ulong)
0x18003494d  test    eax, eax
0x18003494f  jnz     loc_1800349DF
0x180034955  mov     r14d, 100h
0x18003495b  lea     r8, aNlchangepasswo_22; "NlChangePasswordHigher: denying access "...
0x180034962  mov     ecx, r14d; unsigned int
0x180034965  mov     r9d, ebx
0x180034968  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18003496b  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180034970  mov     eax, 0C0000022h
0x180034975  test    ebx, ebx
0x180034977  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18003497a  cmovns  ebx, eax
0x18003497d  mov     edx, ebx; int
0x18003497f  call    ?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z; NlSetStatusClientSession(_CLIENT_SESSION *,long)
0x180034984  cmp     [rsp+320h+var_2E0], 0
0x180034989  jz      short loc_1800349DF
0x18003498b  xor     edx, edx; unsigned int
0x18003498d  mov     [rsp+320h+var_2E0], 0
0x180034992  mov     rcx, rdi; struct _CLIENT_SESSION *
0x180034995  call    ?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z; NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)
0x18003499a  mov     ebx, eax
0x18003499c  test    eax, eax
0x18003499e  js      short loc_1800349DF
0x1800349a0  mov     rsi, [rsp+320h+var_2C0]
0x1800349a5  jmp     loc_180034581
0x1800349aa  mov     r9d, eax
0x1800349ad  lea     r8, aNlchangepasswo_21; "NlChangePasswordHigher: Cannot RtlCalcu"...
0x1800349b4  mov     rdx, rdi; struct _CLIENT_SESSION *
  ... truncated ...
```
