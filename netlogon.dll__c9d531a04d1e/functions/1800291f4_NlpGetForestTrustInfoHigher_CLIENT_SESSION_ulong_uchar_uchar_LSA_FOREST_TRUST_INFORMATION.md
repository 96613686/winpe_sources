# NlpGetForestTrustInfoHigher(_CLIENT_SESSION *,ulong,uchar,uchar,_LSA_FOREST_TRUST_INFORMATION * *)

- ea: `0x1800291f4`
- end: `0x180029591`
- name: `?NlpGetForestTrustInfoHigher@@YAJPEAU_CLIENT_SESSION@@KEEPEAPEAU_LSA_FOREST_TRUST_INFORMATION@@@Z`
- size: `925`
- prototype: `__int64 __usercall@<rax>(struct _CLIENT_SESSION *@<rcx>, unsigned int@<edx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, struct _LSA_FOREST_TRUST_INFORMATION **)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x180029680`
- `0x1800378d4`
- `0x18006e960`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18000e270`
- `0x1800291f4`
- `0x180029598`
- `0x180035368`
- `0x18003e71c`
- `0x18003e7dc`
- `0x18003f034`
- `0x18005f358`
- `0x18005f79c`
- `0x180060734`
- `0x18006515c`
- `0x180068458`
- `0x1800688e0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180029510`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180029510`
- `logoncli!I_NetGetForestTrustInformation` at `0x1800293ac`
- `logoncli!I_NetGetForestTrustInformation` at `0x1800293ac`
- `ntdll!RtlLeaveCriticalSection` at `0x180029504`
- `ntdll!RtlLeaveCriticalSection` at `0x180029520`
- `ntdll!RtlLeaveCriticalSection` at `0x180029504`
- `ntdll!RtlLeaveCriticalSection` at `0x180029520`
- `ntdll!RtlEnterCriticalSection` at `0x1800294d0`
- `ntdll!RtlEnterCriticalSection` at `0x1800294d0`

## string_xrefs

- `0x180029253`: `onecore\ds\netapi\svcdlls\logonsrv\server\ftinfo.cxx`
- `0x180029275`: `onecore\ds\netapi\svcdlls\logonsrv\server\ftinfo.cxx`
- `0x180029358`: `onecore\ds\netapi\svcdlls\logonsrv\server\ftinfo.cxx`
- `0x18002927c`: `ClientSession->CsFlags & CS_WRITER`
- `0x180029450`: `NlpDidDcFail: denying access after status: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NlpGetForestTrustInfoHigher(
        struct _CLIENT_SESSION *a1,
        char a2,
        char a3,
        char *a4,
        struct _LSA_FOREST_TRUST_INFORMATION **a5)
{
  char v5; // r15
  int v8; // ebp
  int started; // ebx
  char v10; // r14
  unsigned int v11; // r9d
  int v12; // eax
  DWORD i; // esi
  char *v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rdx
  int ForestTrustInformation; // eax
  unsigned __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r8
  char *v21; // r9
  __int64 v24; // [rsp+40h] [rbp-68h] BYREF
  int v25; // [rsp+48h] [rbp-60h]
  struct _CYPHER_BLOCK v26; // [rsp+50h] [rbp-58h] BYREF
  int v27; // [rsp+58h] [rbp-50h]

  v5 = (char)a4;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  if ( !*((_DWORD *)a1 + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ftinfo.cxx",
      197,
      a4);
  if ( (*((_BYTE *)a1 + 292) & 8) == 0 )
    NlAssertFailed(
      "ClientSession->CsFlags & CS_WRITER",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ftinfo.cxx",
      198,
      a4);
  v8 = a2 & 1;
  if ( v8 && *(_DWORD *)(*((_QWORD *)a1 + 34) + 588LL) != 1 )
  {
    started = -1073741433;
LABEL_47:
    NlPrintCsRoutine(0x100u, a1, L"NlpGetForestTrustInfoHigher: failed %lX\n", (unsigned int)started);
    return (unsigned int)started;
  }
  if ( (*((_DWORD *)a1 + 74) & 8) == 0 )
  {
    NlPrintCsRoutine(0x100u, a1, L"NlpGetForestTrustInfoHigher: trust isn't marked as cross forest trust: 0x%lX\n");
    started = -1073741601;
    goto LABEL_47;
  }
  v10 = 1;
  if ( !v5 )
    goto LABEL_35;
  while ( 1 )
  {
    v11 = *((_DWORD *)a1 + 79);
    if ( (v11 & 0x80000) == 0 )
    {
      NlPrintCsRoutine(0x100u, a1, L"NlpGetForestTrustInfoHigher: remote DC doesn't support this function.\n");
      started = -1073741637;
      goto LABEL_47;
    }
    v12 = NlBuildAuthenticator(
            (struct _CYPHER_BLOCK *)a1 + 54,
            (struct _CLIENT_SESSION *)((char *)a1 + 440),
            (struct _NETLOGON_AUTHENTICATOR *)&v24,
            v11);
    started = v12;
    if ( v12 < 0 )
    {
      NlPrintRoutine(
        0x100u,
        L"NlpGetForestTrustInfoHigher: NlBuildAuthenticator failed with status: 0x%lx\n",
        (unsigned int)v12);
      goto LABEL_47;
    }
    started = -1073610748;
    for ( i = 0; i < 2; ++i )
    {
      started = NlStartApiClientSession(a1, 1, i, started, (struct _CLIENT_SESSION *)((char *)a1 + 680));
      if ( started >= 0 )
      {
        v15 = *((_QWORD *)a1 + 63);
        if ( !v15 )
        {
          NlAssertFailed(
            "ClientSession->CsUncServerName != NULL",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ftinfo.cxx",
            272,
            v14);
          v15 = *((_QWORD *)a1 + 63);
        }
        if ( (*((_DWORD *)a1 + 73) & 0x40000) != 0 )
          v16 = *((_QWORD *)a1 + 27);
        else
          v16 = *(_QWORD *)(*((_QWORD *)a1 + 34) + 264LL);
        ForestTrustInformation = I_NetGetForestTrustInformation(v15, v16, &v24, &v26, 0, a5);
        started = ForestTrustInformation;
        if ( ForestTrustInformation < 0 )
          NlPrintRpcDebug("I_NetGetForestTrustInformation", ForestTrustInformation);
      }
      v18 = (unsigned int)(started + 1073610748);
      if ( (unsigned int)v18 > 0x32 )
        break;
      v19 = 0x4000000080001LL;
      if ( !_bittest64(&v19, v18) )
        break;
    }
    if ( !NlFinishApiClientSession(a1, 1, 1, (struct _CLIENT_SESSION *)((char *)a1 + 680)) && started >= 0 )
    {
      started = *((_DWORD *)a1 + 72);
      if ( started >= 0 )
        return (unsigned int)started;
      goto LABEL_47;
    }
    if ( !NlpDidDcFail(started)
      && (!(unsigned int)NlCheckRpcAuthIsNetlogon(a1)
       || (unsigned int)NlUpdateSeed((PUCHAR)a1 + 432, &v26, (PUCHAR)a1 + 440, *((_DWORD *)a1 + 79))) )
    {
      break;
    }
    NlPrintCsRoutine(0x100u, a1, L"NlpDidDcFail: denying access after status: 0x%lx\n", (unsigned int)started);
    if ( started >= 0 )
      started = -1073741790;
    NlSetStatusClientSession(a1, started, v20, v21);
    if ( !v10 )
      goto LABEL_47;
    if ( v5 )
      break;
    v10 = 0;
LABEL_35:
    started = NlEnsureSessionAuthenticated(a1, 0);
    if ( started < 0 )
      goto LABEL_47;
  }
  if ( started < 0 )
    goto LABEL_47;
  if ( v8 )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
    started = NlpUpdateFtinfo(*((struct _DOMAIN_INFO **)a1 + 34), *((unsigned __int16 **)a1 + 20), a3, *a5);
    if ( started < 0 )
    {
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
      goto LABEL_47;
    }
    GetSystemTimeAsFileTime((LPFILETIME)a1 + 6);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
  }
  return 0;
}

```

## disassembly

```asm
0x1800291f4  mov     [rsp+arg_8], rbx
0x1800291f9  push    rbp
0x1800291fa  push    rsi
0x1800291fb  push    rdi
0x1800291fc  push    r12
0x1800291fe  push    r13
0x180029200  push    r14
0x180029202  push    r15
0x180029204  sub     rsp, 70h
0x180029208  mov     rax, cs:__security_cookie
0x18002920f  xor     rax, rsp
0x180029212  mov     [rsp+0A8h+var_48], rax
0x180029217  mov     rax, [rsp+0A8h+arg_20]
0x18002921f  mov     r15b, r9b
0x180029222  mov     [rsp+0A8h+var_70], rax
0x180029227  mov     ebp, edx
0x180029229  xor     eax, eax
0x18002922b  mov     [rsp+0A8h+var_78], r8b
0x180029230  mov     rdi, rcx
0x180029233  mov     [rsp+0A8h+var_68], rax
0x180029238  mov     [rsp+0A8h+var_60], eax
0x18002923c  mov     qword ptr [rsp+0A8h+var_58.data], rax
0x180029241  mov     [rsp+0A8h+var_50], eax
0x180029245  cmp     [rcx+148h], eax
0x18002924b  ja      short loc_180029266
0x18002924d  mov     r8d, 0C5h; unsigned int
0x180029253  lea     rdx, aOnecoreDsNetap_5; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18002925a  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x180029261  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180029266  test    byte ptr [rdi+124h], 8
0x18002926d  jnz     short loc_180029288
0x18002926f  mov     r8d, 0C6h; unsigned int
0x180029275  lea     rdx, aOnecoreDsNetap_5; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18002927c  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x180029283  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180029288  mov     esi, 100h
0x18002928d  and     ebp, 1
0x180029290  jz      short loc_1800292AC
0x180029292  mov     rax, [rdi+110h]
0x180029299  cmp     dword ptr [rax+24Ch], 1
0x1800292a0  jz      short loc_1800292AC
0x1800292a2  mov     ebx, 0C0000187h
0x1800292a7  jmp     loc_180029553
0x1800292ac  mov     r9d, [rdi+128h]
0x1800292b3  test    r9b, 8
0x1800292b7  jnz     short loc_1800292D4
0x1800292b9  lea     r8, aNlpgetforesttr_2; "NlpGetForestTrustInfoHigher: trust isn'"...
0x1800292c0  mov     rdx, rdi; struct _CLIENT_SESSION *
0x1800292c3  mov     ecx, esi; unsigned int
0x1800292c5  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800292ca  mov     ebx, 0C00000DFh
0x1800292cf  jmp     loc_180029553
0x1800292d4  mov     r14b, 1
0x1800292d7  test    r15b, r15b
0x1800292da  jz      loc_180029489
0x1800292e0  mov     r9d, [rdi+13Ch]; unsigned int
0x1800292e7  bt      r9d, 13h
0x1800292ec  jnb     loc_18002953D
0x1800292f2  lea     rdx, [rdi+1B8h]; struct _NETLOGON_SESSION_KEY *
0x1800292f9  lea     rcx, [rdi+1B0h]; struct _CYPHER_BLOCK *
0x180029300  lea     r8, [rsp+0A8h+var_68]; struct _NETLOGON_AUTHENTICATOR *
0x180029305  call    ?NlBuildAuthenticator@@YAJPEAU_CYPHER_BLOCK@@PEAU_NETLOGON_SESSION_KEY@@PEAU_NETLOGON_AUTHENTICATOR@@K@Z; NlBuildAuthenticator(_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,_NETLOGON_AUTHENTICATOR *,ulong)
0x18002930a  mov     ebx, eax
0x18002930c  test    eax, eax
0x18002930e  js      loc_18002952A
0x180029314  mov     r12, [rsp+0A8h+var_70]
0x180029319  lea     r13, [rdi+2A8h]
0x180029320  mov     ebx, 0C0020004h
0x180029325  xor     esi, esi
0x180029327  mov     r9d, ebx; int
0x18002932a  mov     [rsp+0A8h+var_88], r13; struct _CLIENT_API *
0x18002932f  mov     r8d, esi; unsigned int
0x180029332  mov     dl, 1; unsigned __int8
0x180029334  mov     rcx, rdi; struct _CLIENT_SESSION *
0x180029337  call    ?NlStartApiClientSession@@YAJPEAU_CLIENT_SESSION@@EKJPEAU_CLIENT_API@@@Z; NlStartApiClientSession(_CLIENT_SESSION *,uchar,ulong,long,_CLIENT_API *)
0x18002933c  mov     ebx, eax
0x18002933e  test    eax, eax
0x180029340  js      loc_1800293C6
0x180029346  mov     rcx, [rdi+1F8h]
0x18002934d  test    rcx, rcx
0x180029350  jnz     short loc_180029372
0x180029352  mov     r8d, 110h; unsigned int
0x180029358  lea     rdx, aOnecoreDsNetap_5; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18002935f  lea     rcx, aClientsessionC_2; "ClientSession->CsUncServerName != NULL"
0x180029366  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18002936b  mov     rcx, [rdi+1F8h]
0x180029372  test    dword ptr [rdi+124h], 40000h
0x18002937c  jz      short loc_180029387
0x18002937e  mov     rdx, [rdi+0D8h]
0x180029385  jmp     short loc_180029395
0x180029387  mov     rax, [rdi+110h]
0x18002938e  mov     rdx, [rax+108h]
0x180029395  mov     [rsp+0A8h+var_80], r12
0x18002939a  lea     r9, [rsp+0A8h+var_58]
0x18002939f  lea     r8, [rsp+0A8h+var_68]
0x1800293a4  mov     dword ptr [rsp+0A8h+var_88], 0
0x1800293ac  call    cs:__imp_I_NetGetForestTrustInformation
0x1800293b2  mov     ebx, eax
0x1800293b4  test    eax, eax
0x1800293b6  jns     short loc_1800293C6
0x1800293b8  mov     edx, eax; int
0x1800293ba  lea     rcx, aINetgetforestt; "I_NetGetForestTrustInformation"
0x1800293c1  call    ?NlPrintRpcDebug@@YAXPEBDJ@Z; NlPrintRpcDebug(char const *,long)
0x1800293c6  lea     eax, [rbx+3FFDFFFCh]
0x1800293cc  cmp     eax, 32h ; '2'
0x1800293cf  ja      short loc_1800293EC
0x1800293d1  mov     rcx, 4000000080001h
0x1800293db  bt      rcx, rax
0x1800293df  jnb     short loc_1800293EC
0x1800293e1  inc     esi
0x1800293e3  cmp     esi, 2
0x1800293e6  jb      loc_180029327
0x1800293ec  mov     r8b, 1; unsigned __int8
0x1800293ef  lea     r9, [rdi+2A8h]; struct _CLIENT_API *
0x1800293f6  mov     dl, r8b; unsigned __int8
0x1800293f9  mov     rcx, rdi; struct _CLIENT_SESSION *
0x1800293fc  call    ?NlFinishApiClientSession@@YAEPEAU_CLIENT_SESSION@@EEPEAU_CLIENT_API@@@Z; NlFinishApiClientSession(_CLIENT_SESSION *,uchar,uchar,_CLIENT_API *)
0x180029401  test    al, al
0x180029403  jnz     short loc_18002940D
0x180029405  test    ebx, ebx
0x180029407  jns     loc_1800294A2
0x18002940d  mov     ecx, ebx; int
0x18002940f  call    ?NlpDidDcFail@@YAEJ@Z; NlpDidDcFail(long)
0x180029414  test    al, al
0x180029416  jnz     short loc_18002944B
0x180029418  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18002941b  call    ?NlCheckRpcAuthIsNetlogon@@YAHPEAU_CLIENT_SESSION@@@Z; NlCheckRpcAuthIsNetlogon(_CLIENT_SESSION *)
0x180029420  test    eax, eax
0x180029422  jz      loc_1800294B5
0x180029428  mov     r9d, [rdi+13Ch]; unsigned int
0x18002942f  lea     r8, [rdi+1B8h]; pbSecret
0x180029436  lea     rdx, [rsp+0A8h+var_58]; struct _CYPHER_BLOCK *
0x18002943b  lea     rcx, [rdi+1B0h]; pbInput
0x180029442  call    ?NlUpdateSeed@@YAHPEAU_CYPHER_BLOCK@@0PEAU_NETLOGON_SESSION_KEY@@K@Z; NlUpdateSeed(_CYPHER_BLOCK *,_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,ulong)
0x180029447  test    eax, eax
0x180029449  jnz     short loc_1800294B5
0x18002944b  mov     esi, 100h
0x180029450  lea     r8, aNlpdiddcfailDe; "NlpDidDcFail: denying access after stat"...
0x180029457  mov     ecx, esi; unsigned int
0x180029459  mov     r9d, ebx
0x18002945c  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18002945f  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180029464  mov     eax, 0C0000022h
0x180029469  test    ebx, ebx
0x18002946b  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18002946e  cmovns  ebx, eax
0x180029471  mov     edx, ebx; int
0x180029473  call    ?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z; NlSetStatusClientSession(_CLIENT_SESSION *,long)
0x180029478  test    r14b, r14b
0x18002947b  jz      loc_180029553
0x180029481  test    r15b, r15b
0x180029484  jnz     short loc_1800294B5
0x180029486  xor     r14b, r14b
0x180029489  xor     edx, edx; unsigned int
0x18002948b  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18002948e  call    ?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z; NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)
0x180029493  mov     ebx, eax
0x180029495  test    eax, eax
0x180029497  jns     loc_1800292E0
0x18002949d  jmp     loc_180029553
0x1800294a2  mov     ebx, [rdi+120h]
0x1800294a8  test    ebx, ebx
0x1800294aa  jns     loc_18002956A
0x1800294b0  jmp     loc_180029553
0x1800294b5  test    ebx, ebx
0x1800294b7  js      loc_180029553
0x1800294bd  test    ebp, ebp
0x1800294bf  jz      short loc_180029526
0x1800294c1  mov     rcx, [rdi+110h]
0x1800294c8  mov     esi, 190h
0x1800294cd  add     rcx, rsi; CriticalSection
0x1800294d0  call    cs:__imp_RtlEnterCriticalSection
0x1800294d6  mov     r8b, [rsp+0A8h+var_78]; unsigned __int8
0x1800294db  mov     rax, r12
0x1800294de  mov     rdx, [rdi+0A0h]; unsigned __int16 *
0x1800294e5  mov     rcx, [rdi+110h]; struct _DOMAIN_INFO *
0x1800294ec  mov     r9, [rax]; struct _LSA_FOREST_TRUST_INFORMATION *
0x1800294ef  call    ?NlpUpdateFtinfo@@YAJPEAU_DOMAIN_INFO@@PEAGEPEAU_LSA_FOREST_TRUST_INFORMATION@@@Z; NlpUpdateFtinfo(_DOMAIN_INFO *,ushort *,uchar,_LSA_FOREST_TRUST_INFORMATION *)
0x1800294f4  mov     ebx, eax
0x1800294f6  test    eax, eax
0x1800294f8  jns     short loc_18002950C
0x1800294fa  mov     rcx, [rdi+110h]
0x180029501  add     rcx, rsi; CriticalSection
0x180029504  call    cs:__imp_RtlLeaveCriticalSection
0x18002950a  jmp     short loc_180029553
0x18002950c  lea     rcx, [rdi+30h]; lpSystemTimeAsFileTime
0x180029510  call    cs:__imp_GetSystemTimeAsFileTime
0x180029516  mov     rcx, [rdi+110h]
0x18002951d  add     rcx, rsi; CriticalSection
0x180029520  call    cs:__imp_RtlLeaveCriticalSection
0x180029526  xor     ebx, ebx
0x180029528  jmp     short loc_18002956A
0x18002952a  mov     r8d, eax
0x18002952d  lea     rdx, aNlpgetforesttr; "NlpGetForestTrustInfoHigher: NlBuildAut"...
0x180029534  mov     ecx, esi; unsigned int
0x180029536  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002953b  jmp     short loc_180029553
0x18002953d  lea     r8, aNlpgetforesttr_0; "NlpGetForestTrustInfoHigher: remote DC "...
0x180029544  mov     rdx, rdi; struct _CLIENT_SESSION *
0x180029547  mov     ecx, esi; unsigned int
0x180029549  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18002954e  mov     ebx, 0C00000BBh
0x180029553  mov     r9d, ebx
0x180029556  lea     r8, aNlpgetforesttr_3; "NlpGetForestTrustInfoHigher: failed %lX"...
0x18002955d  mov     rdx, rdi; struct _CLIENT_SESSION *
0x180029560  mov     ecx, 100h; unsigned int
0x180029565  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18002956a  mov     eax, ebx
0x18002956c  mov     rcx, [rsp+0A8h+var_48]
0x180029571  xor     rcx, rsp; StackCookie
0x180029574  call    __security_check_cookie
0x180029579  mov     rbx, [rsp+0A8h+arg_8]
0x180029581  add     rsp, 70h
0x180029585  pop     r15
0x180029587  pop     r14
0x180029589  pop     r13
0x18002958b  pop     r12
0x18002958d  pop     rdi
0x18002958e  pop     rsi
0x18002958f  pop     rbp
0x180029590  retn
```
