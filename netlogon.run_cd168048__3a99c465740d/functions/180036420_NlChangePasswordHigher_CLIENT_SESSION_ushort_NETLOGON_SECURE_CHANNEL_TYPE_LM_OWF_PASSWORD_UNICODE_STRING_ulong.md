# NlChangePasswordHigher(_CLIENT_SESSION *,ushort *,_NETLOGON_SECURE_CHANNEL_TYPE,_LM_OWF_PASSWORD *,_UNICODE_STRING *,ulong *)

- ea: `0x180036420`
- end: `0x1800369c7`
- name: `?NlChangePasswordHigher@@YAJPEAU_CLIENT_SESSION@@PEAGW4_NETLOGON_SECURE_CHANNEL_TYPE@@PEAU_LM_OWF_PASSWORD@@PEAU_UNICODE_STRING@@PEAK@Z`
- size: `1447`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update`

## callers

- `0x180035924`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x18000e910`
- `0x18000f3e4`
- `0x180036420`
- `0x180037344`
- `0x180040f18`
- `0x180040fe4`
- `0x180041924`
- `0x1800637d0`
- `0x180063c38`
- `0x1800641c8`
- `0x1800644a0`
- `0x180064c90`
- `0x18006507c`
- `0x180069c60`
- `0x18006d2b0`
- `0x18006d794`
- `0x180090204`

## import_xrefs

- `logoncli!I_NetServerPasswordSet` at `0x180036846`
- `logoncli!I_NetServerPasswordSet` at `0x180036846`
- `logoncli!I_NetServerPasswordSet2` at `0x1800366df`
- `logoncli!I_NetServerPasswordSet2` at `0x1800366df`
- `CRYPTSP!SystemFunction007` at `0x180036742`
- `CRYPTSP!SystemFunction007` at `0x180036742`

## string_xrefs

- `0x1800364ca`: `ClientSession->CsFlags & CS_WRITER`
- `0x1800364a1`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x1800364c3`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180036599`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x1800365c0`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x18003667f`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x1800367e6`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x1800368e9`: `NlChangePasswordHigher: denying access after status: 0x%lx\n`

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
  DWORD v19; // esi
  __int64 v20; // r15
  char *v21; // r9
  __int64 v22; // rcx
  __int64 v23; // r9
  int v24; // eax
  unsigned __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rcx
  __int128 *v28; // rax
  DWORD v29; // esi
  __int64 v30; // r15
  char *v31; // r9
  __int64 v32; // rcx
  __int64 v33; // r9
  int v34; // eax
  unsigned __int64 v35; // rax
  __int64 v36; // r8
  char *v37; // r9
  __int128 *v38; // rax
  struct _CLIENT_API *v40; // [rsp+20h] [rbp-E0h]
  char v41; // [rsp+40h] [rbp-C0h]
  struct _LM_OWF_PASSWORD *v44; // [rsp+60h] [rbp-A0h]
  __int64 v45; // [rsp+68h] [rbp-98h] BYREF
  int v46; // [rsp+70h] [rbp-90h]
  struct _CYPHER_BLOCK v47; // [rsp+78h] [rbp-88h] BYREF
  int v48; // [rsp+80h] [rbp-80h]
  __int128 v49; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v50; // [rsp+98h] [rbp-68h]
  __int128 v51; // [rsp+A0h] [rbp-60h] BYREF
  struct _ENCRYPTED_LM_OWF_PASSWORD v52; // [rsp+B0h] [rbp-50h] BYREF
  BYTE pbBuffer[500]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v54[12]; // [rsp+2B4h] [rbp+1B4h] BYREF
  int v55; // [rsp+2C0h] [rbp+1C0h] BYREF

  v6 = a5;
  v7 = (struct _LM_OWF_PASSWORD *)a4;
  v8 = a2;
  v44 = (struct _LM_OWF_PASSWORD *)a4;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v41 = 1;
  if ( !*(_DWORD *)(a1 + 328) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
      0x17A1u,
      a4);
  if ( (*(_BYTE *)(a1 + 292) & 8) == 0 )
    NlAssertFailed(
      "ClientSession->CsFlags & CS_WRITER",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
      0x17A2u,
      a4);
  started = NlEnsureSessionAuthenticated((struct _CLIENT_SESSION *)a1, 0);
  v11 = 16;
  if ( started >= 0 )
  {
    v12 = (struct _NETLOGON_SESSION_KEY *)(a1 + 440);
    while ( 1 )
    {
      v13 = *(_OWORD *)v12;
      v50 = *(_DWORD *)(a1 + 316);
      v49 = v13;
      v14 = NlBuildAuthenticator((struct _CYPHER_BLOCK *)(a1 + 432), v12, (struct _NETLOGON_AUTHENTICATOR *)&v45, v50);
      started = v14;
      if ( v14 < 0 )
        break;
      if ( v6 && (v50 & 0x20000) != 0 )
      {
        memset_0(pbBuffer, 0, 0x204u);
        memcpy_0((char *)&v55 - *v6, *((const void **)v6 + 1), *v6);
        v55 = *v6;
        if ( a3 - 3 <= 1 )
        {
          if ( !a6 )
            NlAssertFailed(
              "ClearPasswordVersionNumber != NULL",
              "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
              0x17F3u,
              v15);
          if ( *v6 == 500 )
            NlAssertFailed(
              "NL_MAX_PASSWORD_LENGTH * sizeof(WCHAR) - NewClearPassword->Length - sizeof(PasswordVersion) > 0",
              "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
              0x17F6u,
              v15);
          v16 = *a6;
          v17 = &v54[-*v6];
          *v17 = 0;
          v17[1] = v16;
          v17[2] = 35854696;
        }
        if ( !NlGenerateRandomBits(pbBuffer, 500 - *v6) )
          NlPrintRoutine(0x100u, L"Can't NlGenerateRandomBits for clear password prefix\n");
        NlEncrypt(pbBuffer, 0x204u, (struct _SESSION_INFO *)&v49);
        v18 = (struct _CLIENT_API *)(a1 + 680);
        v19 = 0;
        started = -1073610748;
        v20 = 0x4000000080001LL;
        do
        {
          started = NlStartApiClientSession(
                      (struct _CLIENT_SESSION *)a1,
                      1,
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
                0x181Eu,
                v21);
              v22 = *(_QWORD *)(a1 + 504);
            }
            if ( (*(_DWORD *)(a1 + 292) & 0x40000) != 0 )
              v23 = *(_QWORD *)(a1 + 216);
            else
              v23 = *(_QWORD *)(*(_QWORD *)(a1 + 272) + 264LL);
            v24 = I_NetServerPasswordSet2(v22, a2, a3, v23, &v45, &v47, pbBuffer);
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
        v52 = 0;
        v51 = 0;
        if ( !v7 )
        {
          v26 = SystemFunction007(v6, &v51);
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
          v7 = (struct _LM_OWF_PASSWORD *)&v51;
          v44 = (struct _LM_OWF_PASSWORD *)&v51;
        }
        started = NlpEncryptNtOwf(*(_DWORD *)(a1 + 316), v7, (struct _LM_OWF_PASSWORD *)v12, &v52);
        v27 = 16;
        v28 = &v51;
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
                      1,
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
                0x186Au,
                v31);
              v32 = *(_QWORD *)(a1 + 504);
            }
            if ( (*(_DWORD *)(a1 + 292) & 0x40000) != 0 )
              v33 = *(_QWORD *)(a1 + 216);
            else
              v33 = *(_QWORD *)(*(_QWORD *)(a1 + 272) + 264LL);
            v34 = I_NetServerPasswordSet(v32, a2, a3, v33, &v45, &v47, &v52);
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
         || (unsigned int)NlUpdateSeed((PUCHAR)(a1 + 432), &v47, (PUCHAR)(a1 + 440), *(_DWORD *)(a1 + 316))) )
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
      NlSetStatusClientSession((struct _CLIENT_SESSION *)a1, started, v36, v37);
      if ( !v41 )
        goto LABEL_61;
      v41 = 0;
      started = NlEnsureSessionAuthenticated((struct _CLIENT_SESSION *)a1, 0);
      if ( started < 0 )
        goto LABEL_61;
      v7 = v44;
    }
    NlPrintRoutine(
      0x100u,
      L"NlChangePasswordHigher: NlBuildAuthenticator failed with status: 0x%lx\n",
      (unsigned int)v14);
LABEL_61:
    v8 = a2;
  }
  v38 = &v49;
  do
  {
    *(_BYTE *)v38 = 0;
    v38 = (__int128 *)((char *)v38 + 1);
    --v11;
  }
  while ( v11 );
  if ( started < 0 )
  {
    LODWORD(v40) = started;
    NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, L"NlChangePasswordHigher: %ws: failed %lX\n", v8, v40);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180036420  push    rbp
0x180036422  push    rbx
0x180036423  push    rsi
0x180036424  push    rdi
0x180036425  push    r12
0x180036427  push    r13
0x180036429  push    r14
0x18003642b  push    r15
0x18003642d  lea     rbp, [rsp-1E8h]
0x180036435  sub     rsp, 2E8h
0x18003643c  mov     rax, cs:__security_cookie
0x180036443  xor     rax, rsp
0x180036446  mov     [rbp+220h+var_50], rax
0x18003644d  mov     r15, [rbp+220h+arg_20]
0x180036454  xor     eax, eax
0x180036456  xorps   xmm0, xmm0
0x180036459  mov     rsi, r9
0x18003645c  mov     r14, rdx
0x18003645f  mov     [rsp+320h+var_2C0], r9
0x180036464  mov     rdi, rcx
0x180036467  mov     [rsp+320h+var_2D0], r8d
0x18003646c  mov     [rsp+320h+var_2D8], rdx
0x180036471  mov     [rsp+320h+var_2C8], r15
0x180036476  mov     [rsp+320h+var_2B8], rax
0x18003647b  mov     [rsp+320h+var_2B0], eax
0x18003647f  mov     qword ptr [rsp+320h+var_2A8.data], rax
0x180036484  mov     [rbp+220h+var_2A0], eax
0x180036487  movups  [rbp+220h+var_298], xmm0
0x18003648b  mov     [rbp+220h+var_288], eax
0x18003648e  mov     [rsp+320h+var_2E0], 1
0x180036493  cmp     [rcx+148h], eax
0x180036499  ja      short loc_1800364B4
0x18003649b  mov     r8d, 17A1h; unsigned int
0x1800364a1  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800364a8  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x1800364af  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800364b4  test    byte ptr [rdi+124h], 8
0x1800364bb  jnz     short loc_1800364D6
0x1800364bd  mov     r8d, 17A2h; unsigned int
0x1800364c3  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800364ca  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x1800364d1  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800364d6  xor     edx, edx; unsigned int
0x1800364d8  mov     rcx, rdi; struct _CLIENT_SESSION *
0x1800364db  call    ?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z; NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)
0x1800364e0  mov     ebx, eax
0x1800364e2  mov     r12d, 10h
0x1800364e8  test    eax, eax
0x1800364ea  js      loc_180036972
0x1800364f0  lea     r13, [rdi+1B8h]
0x1800364f7  mov     r14d, 100h
0x1800364fd  lea     rax, [rdi+1B0h]
0x180036504  movups  xmm0, xmmword ptr [r13+0]
0x180036509  mov     r9d, [rdi+13Ch]; unsigned int
0x180036510  lea     r8, [rsp+320h+var_2B8]; struct _NETLOGON_AUTHENTICATOR *
0x180036515  mov     rdx, r13; struct _NETLOGON_SESSION_KEY *
0x180036518  mov     [rbp+220h+var_288], r9d
0x18003651c  mov     rcx, rax; struct _CYPHER_BLOCK *
0x18003651f  movdqu  [rbp+220h+var_298], xmm0
0x180036524  call    ?NlBuildAuthenticator@@YAJPEAU_CYPHER_BLOCK@@PEAU_NETLOGON_SESSION_KEY@@PEAU_NETLOGON_AUTHENTICATOR@@K@Z; NlBuildAuthenticator(_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,_NETLOGON_AUTHENTICATOR *,ulong)
0x180036529  mov     ebx, eax
0x18003652b  test    eax, eax
0x18003652d  js      loc_18003695B
0x180036533  test    r15, r15
0x180036536  jz      loc_180036728
0x18003653c  test    [rbp+220h+var_288], 20000h
0x180036543  jz      loc_180036728
0x180036549  xor     edx, edx; Val
0x18003654b  lea     rcx, [rbp+220h+pbBuffer]; void *
0x18003654f  mov     r8d, 204h; Size
0x180036555  call    memset_0
0x18003655a  movzx   r8d, word ptr [r15]; Size
0x18003655e  lea     rcx, [rbp+220h+var_60]
0x180036565  mov     rdx, [r15+8]; Src
0x180036569  sub     rcx, r8; void *
0x18003656c  call    memcpy_0
0x180036571  movzx   eax, word ptr [r15]
0x180036575  mov     [rbp+220h+var_60], eax
0x18003657b  mov     eax, [rsp+320h+var_2D0]
0x18003657f  add     eax, 0FFFFFFFDh
0x180036582  cmp     eax, 1
0x180036585  ja      short loc_1800365F3
0x180036587  mov     rbx, [rbp+220h+arg_28]
0x18003658e  test    rbx, rbx
0x180036591  jnz     short loc_1800365AC
0x180036593  mov     r8d, 17F3h; unsigned int
0x180036599  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800365a0  lea     rcx, aClearpasswordv; "ClearPasswordVersionNumber != NULL"
0x1800365a7  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800365ac  movzx   ecx, word ptr [r15]
0x1800365b0  mov     eax, 1F4h
0x1800365b5  cmp     rax, rcx
0x1800365b8  jnz     short loc_1800365D3
0x1800365ba  mov     r8d, 17F6h; unsigned int
0x1800365c0  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800365c7  lea     rcx, aNlMaxPasswordL; "NL_MAX_PASSWORD_LENGTH * sizeof(WCHAR) "...
0x1800365ce  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800365d3  movzx   eax, word ptr [r15]
0x1800365d7  lea     rcx, [rbp+220h+var_6C]
0x1800365de  mov     edx, [rbx]
0x1800365e0  sub     rcx, rax
0x1800365e3  mov     dword ptr [rcx], 0
0x1800365e9  mov     [rcx+4], edx
0x1800365ec  mov     dword ptr [rcx+8], 2231968h
0x1800365f3  movzx   eax, word ptr [r15]
0x1800365f7  lea     rcx, [rbp+220h+pbBuffer]; pbBuffer
0x1800365fb  mov     edx, 1F4h
0x180036600  sub     edx, eax; unsigned int
0x180036602  call    ?NlGenerateRandomBits@@YAEPEAEK@Z; NlGenerateRandomBits(uchar *,ulong)
0x180036607  test    al, al
0x180036609  jnz     short loc_18003661A
0x18003660b  lea     rdx, aCanTNlgenerate_0; "Can't NlGenerateRandomBits for clear pa"...
0x180036612  mov     ecx, r14d; unsigned int
0x180036615  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003661a  lea     r8, [rbp+220h+var_298]; struct _SESSION_INFO *
0x18003661e  mov     edx, 204h; unsigned int
0x180036623  lea     rcx, [rbp+220h+pbBuffer]; void *
0x180036627  call    ?NlEncrypt@@YAXPEAXKPEAU_SESSION_INFO@@@Z; NlEncrypt(void *,ulong,_SESSION_INFO *)
0x18003662c  mov     r13, [rsp+320h+var_2D8]
0x180036631  lea     r14, [rdi+2A8h]
0x180036638  mov     r12d, [rsp+320h+var_2D0]
0x18003663d  xor     esi, esi
0x18003663f  mov     ebx, 0C0020004h
0x180036644  mov     r15, 4000000080001h
0x18003664e  mov     r9d, ebx; int
0x180036651  mov     [rsp+320h+var_300], r14; struct _CLIENT_API *
0x180036656  mov     r8d, esi; unsigned int
0x180036659  mov     dl, 1; unsigned __int8
0x18003665b  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18003665e  call    ?NlStartApiClientSession@@YAJPEAU_CLIENT_SESSION@@EKJPEAU_CLIENT_API@@@Z; NlStartApiClientSession(_CLIENT_SESSION *,uchar,ulong,long,_CLIENT_API *)
0x180036663  mov     ebx, eax
0x180036665  test    eax, eax
0x180036667  js      loc_1800366FF
0x18003666d  mov     rcx, [rdi+1F8h]
0x180036674  test    rcx, rcx
0x180036677  jnz     short loc_180036699
0x180036679  mov     r8d, 181Eh; unsigned int
0x18003667f  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180036686  lea     rcx, aClientsessionC_2; "ClientSession->CsUncServerName != NULL"
0x18003668d  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180036692  mov     rcx, [rdi+1F8h]
0x180036699  test    dword ptr [rdi+124h], 40000h
0x1800366a3  jz      short loc_1800366AE
0x1800366a5  mov     r9, [rdi+0D8h]
0x1800366ac  jmp     short loc_1800366BC
0x1800366ae  mov     rax, [rdi+110h]
0x1800366b5  mov     r9, [rax+108h]
0x1800366bc  lea     rax, [rbp+220h+pbBuffer]
0x1800366c0  mov     r8d, r12d
0x1800366c3  mov     [rsp+320h+var_2F0], rax
0x1800366c8  mov     rdx, r13
0x1800366cb  lea     rax, [rsp+320h+var_2A8]
0x1800366d0  mov     [rsp+320h+var_2F8], rax
0x1800366d5  lea     rax, [rsp+320h+var_2B8]
0x1800366da  mov     [rsp+320h+var_300], rax
0x1800366df  call    cs:__imp_I_NetServerPasswordSet2
0x1800366e6  nop     dword ptr [rax+rax+00h]
0x1800366eb  mov     ebx, eax
0x1800366ed  test    eax, eax
0x1800366ef  jns     short loc_1800366FF
0x1800366f1  mov     edx, eax; int
0x1800366f3  lea     rcx, aINetserverpass; "I_NetServerPasswordSet2"
0x1800366fa  call    ?NlPrintRpcDebug@@YAXPEBDJ@Z; NlPrintRpcDebug(char const *,long)
0x1800366ff  lea     eax, [rbx+3FFDFFFCh]
0x180036705  cmp     eax, 32h ; '2'
0x180036708  ja      loc_180036882
0x18003670e  bt      r15, rax
0x180036712  jnb     loc_180036882
0x180036718  inc     esi
0x18003671a  cmp     esi, 2
0x18003671d  jb      loc_18003664E
0x180036723  jmp     loc_180036882
0x180036728  xorps   xmm0, xmm0
0x18003672b  xorps   xmm1, xmm1
0x18003672e  movups  xmmword ptr [rbp+220h+var_270.data.data], xmm0
0x180036732  movups  [rbp+220h+var_280], xmm1
0x180036736  test    rsi, rsi
0x180036739  jnz     short loc_180036761
0x18003673b  lea     rdx, [rbp+220h+var_280]
0x18003673f  mov     rcx, r15
0x180036742  call    cs:__imp_SystemFunction007
0x180036749  nop     dword ptr [rax+rax+00h]
0x18003674e  mov     ebx, eax
0x180036750  test    eax, eax
0x180036752  js      loc_180036938
0x180036758  lea     rsi, [rbp+220h+var_280]
0x18003675c  mov     [rsp+320h+var_2C0], rsi
0x180036761  mov     ecx, [rdi+13Ch]; unsigned int
0x180036767  lea     r9, [rbp+220h+var_270]; struct _ENCRYPTED_LM_OWF_PASSWORD *
0x18003676b  mov     r8, r13; struct _LM_OWF_PASSWORD *
0x18003676e  mov     rdx, rsi; struct _LM_OWF_PASSWORD *
0x180036771  call    ?NlpEncryptNtOwf@@YAJKPEAU_LM_OWF_PASSWORD@@0PEAU_ENCRYPTED_LM_OWF_PASSWORD@@@Z; NlpEncryptNtOwf(ulong,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,_ENCRYPTED_LM_OWF_PASSWORD *)
0x180036776  mov     ebx, eax
0x180036778  mov     rcx, r12
0x18003677b  lea     rax, [rbp+220h+var_280]
0x18003677f  mov     byte ptr [rax], 0
0x180036782  inc     rax
0x180036785  sub     rcx, 1
0x180036789  jnz     short loc_18003677F
0x18003678b  test    ebx, ebx
0x18003678d  js      loc_18003694F
0x180036793  mov     r13, [rsp+320h+var_2D8]
0x180036798  lea     r14, [rdi+2A8h]
0x18003679f  mov     r12d, [rsp+320h+var_2D0]
0x1800367a4  mov     ebx, 0C0020004h
0x1800367a9  xor     esi, esi
0x1800367ab  mov     r15, 4000000080001h
0x1800367b5  mov     r9d, ebx; int
0x1800367b8  mov     [rsp+320h+var_300], r14; struct _CLIENT_API *
0x1800367bd  mov     r8d, esi; unsigned int
0x1800367c0  mov     dl, 1; unsigned __int8
0x1800367c2  mov     rcx, rdi; struct _CLIENT_SESSION *
0x1800367c5  call    ?NlStartApiClientSession@@YAJPEAU_CLIENT_SESSION@@EKJPEAU_CLIENT_API@@@Z; NlStartApiClientSession(_CLIENT_SESSION *,uchar,ulong,long,_CLIENT_API *)
0x1800367ca  mov     ebx, eax
0x1800367cc  test    eax, eax
0x1800367ce  js      loc_180036866
0x1800367d4  mov     rcx, [rdi+1F8h]
0x1800367db  test    rcx, rcx
0x1800367de  jnz     short loc_180036800
0x1800367e0  mov     r8d, 186Ah; unsigned int
0x1800367e6  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800367ed  lea     rcx, aClientsessionC_2; "ClientSession->CsUncServerName != NULL"
0x1800367f4  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800367f9  mov     rcx, [rdi+1F8h]
0x180036800  test    dword ptr [rdi+124h], 40000h
0x18003680a  jz      short loc_180036815
0x18003680c  mov     r9, [rdi+0D8h]
0x180036813  jmp     short loc_180036823
0x180036815  mov     rax, [rdi+110h]
0x18003681c  mov     r9, [rax+108h]
0x180036823  lea     rax, [rbp+220h+var_270]
0x180036827  mov     r8d, r12d
0x18003682a  mov     [rsp+320h+var_2F0], rax
0x18003682f  mov     rdx, r13
0x180036832  lea     rax, [rsp+320h+var_2A8]
0x180036837  mov     [rsp+320h+var_2F8], rax
0x18003683c  lea     rax, [rsp+320h+var_2B8]
0x180036841  mov     [rsp+320h+var_300], rax
0x180036846  call    cs:__imp_I_NetServerPasswordSet
0x18003684d  nop     dword ptr [rax+rax+00h]
0x180036852  mov     ebx, eax
0x180036854  test    eax, eax
0x180036856  jns     short loc_180036866
0x180036858  mov     edx, eax; int
0x18003685a  lea     rcx, aINetserverpass_0; "I_NetServerPasswordSet"
0x180036861  call    ?NlPrintRpcDebug@@YAXPEBDJ@Z; NlPrintRpcDebug(char const *,long)
0x180036866  lea     eax, [rbx+3FFDFFFCh]
0x18003686c  cmp     eax, 32h ; '2'
0x18003686f  ja      short loc_180036882
0x180036871  bt      r15, rax
0x180036875  jnb     short loc_180036882
0x180036877  inc     esi
0x180036879  cmp     esi, 2
0x18003687c  jb      loc_1800367B5
0x180036882  mov     r8b, 1; unsigned __int8
0x180036885  mov     r9, r14; struct _CLIENT_API *
0x180036888  mov     dl, r8b; unsigned __int8
0x18003688b  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18003688e  call    ?NlFinishApiClientSession@@YAEPEAU_CLIENT_SESSION@@EEPEAU_CLIENT_API@@@Z; NlFinishApiClientSession(_CLIENT_SESSION *,uchar,uchar,_CLIENT_API *)
0x180036893  mov     r15, [rsp+320h+var_2C8]
0x180036898  lea     r13, [rdi+1B8h]
0x18003689f  mov     ecx, ebx; int
0x1800368a1  mov     r12d, 10h
0x1800368a7  call    ?NlpDidDcFail@@YAEJ@Z; NlpDidDcFail(long)
0x1800368ac  test    al, al
0x1800368ae  jnz     short loc_1800368E3
0x1800368b0  mov     rcx, rdi; struct _CLIENT_SESSION *
0x1800368b3  call    ?NlCheckRpcAuthIsNetlogon@@YAHPEAU_CLIENT_SESSION@@@Z; NlCheckRpcAuthIsNetlogon(_CLIENT_SESSION *)
0x1800368b8  test    eax, eax
0x1800368ba  jz      loc_18003696D
0x1800368c0  mov     r9d, [rdi+13Ch]; unsigned int
0x1800368c7  lea     rdx, [rsp+320h+var_2A8]; struct _CYPHER_BLOCK *
0x1800368cc  mov     r8, r13; pbSecret
0x1800368cf  lea     rcx, [rdi+1B0h]; pbInput
0x1800368d6  call    ?NlUpdateSeed@@YAHPEAU_CYPHER_BLOCK@@0PEAU_NETLOGON_SESSION_KEY@@K@Z; NlUpdateSeed(_CYPHER_BLOCK *,_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,ulong)
0x1800368db  test    eax, eax
0x1800368dd  jnz     loc_18003696D
0x1800368e3  mov     r14d, 100h
0x1800368e9  lea     r8, aNlchangepasswo_22; "NlChangePasswordHigher: denying access "...
0x1800368f0  mov     ecx, r14d; unsigned int
0x1800368f3  mov     r9d, ebx
0x1800368f6  mov     rdx, rdi; struct _CLIENT_SESSION *
0x1800368f9  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800368fe  mov     eax, 0C0000022h
0x180036903  test    ebx, ebx
0x180036905  mov     rcx, rdi; struct _CLIENT_SESSION *
0x180036908  cmovns  ebx, eax
0x18003690b  mov     edx, ebx; int
0x18003690d  call    ?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z; NlSetStatusClientSession(_CLIENT_SESSION *,long)
0x180036912  cmp     [rsp+320h+var_2E0], 0
0x180036917  jz      short loc_18003696D
0x180036919  xor     edx, edx; unsigned int
0x18003691b  mov     [rsp+320h+var_2E0], 0
0x180036920  mov     rcx, rdi; struct _CLIENT_SESSION *
0x180036923  call    ?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z; NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)
0x180036928  mov     ebx, eax
0x18003692a  test    eax, eax
0x18003692c  js      short loc_18003696D
0x18003692e  mov     rsi, [rsp+320h+var_2C0]
0x180036933  jmp     loc_1800364FD
  ... truncated ...
```
