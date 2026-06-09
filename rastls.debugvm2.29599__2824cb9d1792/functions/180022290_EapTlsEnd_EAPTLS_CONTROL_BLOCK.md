# EapTlsEnd(_EAPTLS_CONTROL_BLOCK *)

- ea: `0x180022290`
- end: `0x1800227a3`
- name: `?EapTlsEnd@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@@Z`
- size: `1299`
- prototype: `unsigned int __fastcall(struct _EAPTLS_CONTROL_BLOCK *)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800232b0`
- `0x180059b40`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18000f350`
- `0x180017780`
- `0x180022290`
- `0x180031468`
- `0x180035680`
- `0x180036254`
- `0x18004b4ec`
- `0x18004dcd8`
- `0x180051510`
- `0x1800581ac`
- `0x180058558`
- `0x180058708`
- `0x18005c6cc`
- `0x180064cfc`
- `0x18006f3a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002270b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002270b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022720`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002236b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002240d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002236b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002240d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800224d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800224f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022507`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002251b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002252f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022543`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022557`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002256b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002257f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800225c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800225d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002272d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800224d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800224f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022507`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002251b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002252f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022543`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022557`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002256b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002257f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800225c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800225d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002272d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022358`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022358`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800223fa`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800223fa`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180022651`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18002269a`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180022651`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18002269a`
- `SspiCli!DeleteSecurityContext` at `0x180022482`
- `SspiCli!DeleteSecurityContext` at `0x180022482`

## pseudocode

```c
__int64 __fastcall EapTlsEnd(struct _EAPTLS_CONTROL_BLOCK *a1)
{
  struct _EAPTLS_CONTROL_BLOCK *v2; // rcx
  unsigned int v3; // edi
  __int64 v4; // rcx
  const WCHAR *v5; // r9
  int v6; // r14d
  DWORD LastError; // eax
  DWORD v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void **v20; // rcx
  _WORD *v21; // rcx
  __int64 v22; // r8
  CWorkerThreadState *v23; // rcx
  __int128 v24; // xmm6
  DWORD v25; // edx
  __int128 v26; // xmm6
  DWORD v27; // edx
  unsigned int v28; // edx
  _BYTE v30[20]; // [rsp+20h] [rbp-48h] BYREF
  int v31; // [rsp+34h] [rbp-34h]

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 17;
  if ( a1 )
  {
    v3 = (*((_DWORD *)a1 + 1) & 0x4000 | 0x22000u) >> 13;
    if ( v2 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v4 = *((_QWORD *)v2 + 2);
      v5 = &String;
      if ( a1 != (struct _EAPTLS_CONTROL_BLOCK *)-16LL )
        v5 = (const WCHAR *)((char *)a1 + 16);
      WPP_SF_S(v4, 51, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v5);
    }
    if ( *((_QWORD *)a1 + 102) )
    {
      if ( NtCurrentTeb()->IsImpersonating )
      {
        v6 = 1;
        if ( !RevertToSelf() && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, LastError);
        }
      }
      else
      {
        v6 = 0;
      }
      if ( FreeApplicationTicket((struct _NgcTicketContext **)a1 + 102)
        && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      }
      if ( (*((_BYTE *)a1 + 4) & 8) == 0
        && *((_QWORD *)a1 + 100)
        && FreeApplicationTicket((struct _NgcTicketContext **)a1 + 100)
        && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      }
      if ( v6
        && !ImpersonateLoggedOnUser(*((HANDLE *)a1 + 1))
        && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v8 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v8);
      }
    }
    if ( *((_QWORD *)a1 + 74) )
      *((_QWORD *)a1 + 74) = 0;
    v9 = *((_DWORD *)a1 + 1);
    if ( (v9 & 0x100000) != 0 )
    {
      SQMPeapConnectWithoutCA((v9 >> 3) & 1);
      *((_DWORD *)a1 + 1) &= ~0x100000u;
      v9 = *((_DWORD *)a1 + 1);
    }
    if ( (v9 & 8) != 0 )
      WriteTlsAuthSuccessEvent(a1);
    else
      WriteTlsAuthFailEvent(a1, *((_DWORD *)a1 + 181));
    if ( (*((_BYTE *)a1 + 4) & 0x40) == 0 )
    {
      v10 = DeleteSecurityContext((PCtxtHandle)((char *)a1 + 648));
      if ( v10 )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v10);
      }
    }
    if ( (*((_BYTE *)a1 + 4) & 0x20) == 0 )
      *(_OWORD *)((char *)a1 + 616) = 0;
    *((_DWORD *)a1 + 1) |= 0x60u;
    v11 = (void *)*((_QWORD *)a1 + 67);
    if ( v11 )
      RasAuthAttributeDestroy(v11);
    LocalFree(*((HLOCAL *)a1 + 80));
    v12 = (void *)*((_QWORD *)a1 + 71);
    *((_QWORD *)a1 + 80) = 0;
    *((_DWORD *)a1 + 158) = 0;
    LocalFree(v12);
    v13 = (void *)*((_QWORD *)a1 + 68);
    *((_QWORD *)a1 + 71) = 0;
    LocalFree(v13);
    v14 = (void *)*((_QWORD *)a1 + 69);
    *((_QWORD *)a1 + 68) = 0;
    LocalFree(v14);
    v15 = (void *)*((_QWORD *)a1 + 70);
    *((_QWORD *)a1 + 69) = 0;
    LocalFree(v15);
    v16 = (void *)*((_QWORD *)a1 + 72);
    *((_QWORD *)a1 + 70) = 0;
    LocalFree(v16);
    v17 = (void *)*((_QWORD *)a1 + 84);
    *((_QWORD *)a1 + 72) = 0;
    LocalFree(v17);
    v18 = (void *)*((_QWORD *)a1 + 87);
    *((_QWORD *)a1 + 84) = 0;
    LocalFree(v18);
    v19 = (void *)*((_QWORD *)a1 + 93);
    *((_QWORD *)a1 + 87) = 0;
    LocalFree(v19);
    v20 = (void **)*((_QWORD *)a1 + 91);
    *((_QWORD *)a1 + 93) = 0;
    if ( v20 )
    {
      v21 = *v20;
      if ( v21 )
      {
        v22 = -1;
        do
          ++v22;
        while ( v21[v22] );
        memset_0(v21, 0, 2 * v22);
        LocalFree(**((HLOCAL **)a1 + 91));
        **((_QWORD **)a1 + 91) = 0;
      }
      LocalFree(*((HLOCAL *)a1 + 91));
      *((_QWORD *)a1 + 91) = 0;
    }
    if ( hObject )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      CWorkerThreadState::WaitForThread(v23);
    }
    if ( (*((_DWORD *)a1 + 1) & 0x44008) == 0x40000 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      if ( CredDeleteW(L"*Session", 2u, 0) )
      {
        v25 = 0;
        *(_OWORD *)v30 = *(_OWORD *)((char *)a1 + 780);
      }
      else
      {
        v24 = *(_OWORD *)((char *)a1 + 780);
        v25 = GetLastError();
        *(_OWORD *)v30 = v24;
      }
      WriteCredentialUnPlumbingEvent(2u, v25, (struct _GUID *)v30);
      if ( CredDeleteW(L"*Session", 3u, 0) )
      {
        v27 = 0;
        *(_OWORD *)v30 = *(_OWORD *)((char *)a1 + 780);
      }
      else
      {
        v26 = *(_OWORD *)((char *)a1 + 780);
        v27 = GetLastError();
        *(_OWORD *)v30 = v26;
      }
      WriteCredentialUnPlumbingEvent(3u, v27, (struct _GUID *)v30);
    }
    if ( (*((_DWORD *)a1 + 181) || *(_DWORD *)a1 == 7) && (*((_BYTE *)a1 + 4) & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      EnterCriticalSection(&g_csProtectCachedCredentials);
      FreeCachedCredentials(a1);
      LeaveCriticalSection(&g_csProtectCachedCredentials);
    }
    LocalFree(*((HLOCAL *)a1 + 95));
    if ( (*((_DWORD *)a1 + 1) & 0x4001) == 0 )
    {
      *((_BYTE *)a1 + 889) = (*((_DWORD *)a1 + 1) & 8) != 0;
      EapMethodWithTlsTelemetry::TryWriteTelemetry((struct _EAPTLS_CONTROL_BLOCK *)((char *)a1 + 884), "EAP-TLS");
    }
    _EAPTLS_CONTROL_BLOCK::`scalar deleting destructor'(a1, v28);
  }
  *(_DWORD *)v30 = v3;
  v31 = 1;
  *(GUID *)&v30[4] = GUID_NULL;
  NetworkingTriageScenario::GetConnected::EAPTlsEndEvent((const struct NetworkingTriageScenario::GetConnected::RequiredFields *)v30);
  return 0;
}

```

## disassembly

```asm
0x180022290  push    rbp
0x180022292  push    rbx
0x180022293  push    rsi
0x180022294  push    rdi
0x180022295  push    r12
0x180022297  push    r13
0x180022299  push    r14
0x18002229b  push    r15
0x18002229d  mov     rbp, rsp
0x1800222a0  sub     rsp, 68h
0x1800222a4  movaps  [rsp+68h+var_18], xmm6
0x1800222a9  mov     rax, cs:__security_cookie
0x1800222b0  xor     rax, rsp
0x1800222b3  mov     [rbp+var_28], rax
0x1800222b7  mov     rbx, rcx
0x1800222ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222c1  lea     r12, WPP_GLOBAL_Control
0x1800222c8  lea     r13, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x1800222cf  cmp     rcx, r12
0x1800222d2  jz      short loc_1800222EC
0x1800222d4  mov     rcx, [rcx+10h]
0x1800222d8  mov     edx, 32h ; '2'
0x1800222dd  mov     r8, r13
0x1800222e0  call    WPP_SF_
0x1800222e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222ec  xor     r15d, r15d
0x1800222ef  mov     edi, 11h
0x1800222f4  test    rbx, rbx
0x1800222f7  jz      loc_180022760
0x1800222fd  mov     edi, [rbx+4]
0x180022300  and     edi, 4000h
0x180022306  or      edi, 22000h
0x18002230c  shr     edi, 0Dh
0x18002230f  cmp     rcx, r12
0x180022312  jz      short loc_180022336
0x180022314  mov     rcx, [rcx+10h]
0x180022318  lea     rax, [rbx+10h]
0x18002231c  test    rax, rax
0x18002231f  lea     r9, String
0x180022326  lea     edx, [r15+33h]
0x18002232a  mov     r8, r13
0x18002232d  cmovnz  r9, rax
0x180022331  call    WPP_SF_S
0x180022336  lea     rsi, [rbx+330h]
0x18002233d  cmp     [rsi], r15
0x180022340  jz      loc_18002242E
0x180022346  mov     eax, gs:179Ch
0x18002234e  test    eax, eax
0x180022350  jz      short loc_18002238D
0x180022352  mov     r14d, 1
0x180022358  call    cs:__imp_RevertToSelf
0x18002235e  test    eax, eax
0x180022360  jnz     short loc_180022390
0x180022362  cmp     cs:WPP_GLOBAL_Control, r12
0x180022369  jz      short loc_180022390
0x18002236b  call    cs:__imp_GetLastError
0x180022371  mov     rcx, cs:WPP_GLOBAL_Control
0x180022378  lea     edx, [r14+33h]
0x18002237c  mov     r9d, eax
0x18002237f  mov     r8, r13
0x180022382  mov     rcx, [rcx+10h]
0x180022386  call    WPP_SF_d
0x18002238b  jmp     short loc_180022390
0x18002238d  mov     r14d, r15d
0x180022390  mov     rcx, rsi; struct _NgcTicketContext **
0x180022393  call    ?FreeApplicationTicket@@YAKPEAPEAU_NgcTicketContext@@@Z; FreeApplicationTicket(_NgcTicketContext * *)
0x180022398  test    eax, eax
0x18002239a  jz      short loc_1800223B9
0x18002239c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223a3  cmp     rcx, r12
0x1800223a6  jz      short loc_1800223B9
0x1800223a8  mov     rcx, [rcx+10h]
0x1800223ac  mov     edx, 35h ; '5'
0x1800223b1  mov     r8, r13
0x1800223b4  call    WPP_SF_
0x1800223b9  test    byte ptr [rbx+4], 8
0x1800223bd  jnz     short loc_1800223F1
0x1800223bf  lea     rcx, [rbx+320h]; struct _NgcTicketContext **
0x1800223c6  cmp     [rcx], r15
0x1800223c9  jz      short loc_1800223F1
0x1800223cb  call    ?FreeApplicationTicket@@YAKPEAPEAU_NgcTicketContext@@@Z; FreeApplicationTicket(_NgcTicketContext * *)
0x1800223d0  test    eax, eax
0x1800223d2  jz      short loc_1800223F1
0x1800223d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223db  cmp     rcx, r12
0x1800223de  jz      short loc_1800223F1
0x1800223e0  mov     rcx, [rcx+10h]
0x1800223e4  mov     edx, 36h ; '6'
0x1800223e9  mov     r8, r13
0x1800223ec  call    WPP_SF_
0x1800223f1  test    r14d, r14d
0x1800223f4  jz      short loc_18002242E
0x1800223f6  mov     rcx, [rbx+8]; hToken
0x1800223fa  call    cs:__imp_ImpersonateLoggedOnUser
0x180022400  test    eax, eax
0x180022402  jnz     short loc_18002242E
0x180022404  cmp     cs:WPP_GLOBAL_Control, r12
0x18002240b  jz      short loc_18002242E
0x18002240d  call    cs:__imp_GetLastError
0x180022413  mov     rcx, cs:WPP_GLOBAL_Control
0x18002241a  mov     edx, 37h ; '7'
0x18002241f  mov     r9d, eax
0x180022422  mov     r8, r13
0x180022425  mov     rcx, [rcx+10h]
0x180022429  call    WPP_SF_d
0x18002242e  cmp     [rbx+250h], r15
0x180022435  jz      short loc_18002243E
0x180022437  mov     [rbx+250h], r15
0x18002243e  mov     eax, [rbx+4]
0x180022441  bt      eax, 14h
0x180022445  jnb     short loc_18002245C
0x180022447  shr     eax, 3
0x18002244a  and     eax, 1
0x18002244d  mov     ecx, eax; int
0x18002244f  call    ?SQMPeapConnectWithoutCA@@YAXH@Z; SQMPeapConnectWithoutCA(int)
0x180022454  btr     dword ptr [rbx+4], 14h
0x180022459  mov     eax, [rbx+4]
0x18002245c  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x18002245f  test    al, 8
0x180022461  jz      short loc_18002246A
0x180022463  call    ?WriteTlsAuthSuccessEvent@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@@Z; WriteTlsAuthSuccessEvent(_EAPTLS_CONTROL_BLOCK *)
0x180022468  jmp     short loc_180022475
0x18002246a  mov     edx, [rbx+2D4h]; unsigned int
0x180022470  call    ?WriteTlsAuthFailEvent@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@K@Z; WriteTlsAuthFailEvent(_EAPTLS_CONTROL_BLOCK *,ulong)
0x180022475  test    byte ptr [rbx+4], 40h
0x180022479  jnz     short loc_1800224AC
0x18002247b  lea     rcx, [rbx+288h]; phContext
0x180022482  call    cs:__imp_DeleteSecurityContext
0x180022488  test    eax, eax
0x18002248a  jz      short loc_1800224AC
0x18002248c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022493  cmp     rcx, r12
0x180022496  jz      short loc_1800224AC
0x180022498  mov     rcx, [rcx+10h]
0x18002249c  mov     edx, 38h ; '8'
0x1800224a1  mov     r9d, eax
0x1800224a4  mov     r8, r13
0x1800224a7  call    WPP_SF_d
0x1800224ac  test    byte ptr [rbx+4], 20h
0x1800224b0  jnz     short loc_1800224BC
0x1800224b2  xorps   xmm0, xmm0
0x1800224b5  movups  xmmword ptr [rbx+268h], xmm0
0x1800224bc  or      dword ptr [rbx+4], 60h
0x1800224c0  mov     rcx, [rbx+218h]; hMem
0x1800224c7  test    rcx, rcx
0x1800224ca  jz      short loc_1800224D1
0x1800224cc  call    RasAuthAttributeDestroy
0x1800224d1  mov     rcx, [rbx+280h]; hMem
0x1800224d8  call    cs:__imp_LocalFree
0x1800224de  mov     rcx, [rbx+238h]; hMem
0x1800224e5  mov     [rbx+280h], r15
0x1800224ec  mov     [rbx+278h], r15d
0x1800224f3  call    cs:__imp_LocalFree
0x1800224f9  mov     rcx, [rbx+220h]; hMem
0x180022500  mov     [rbx+238h], r15
0x180022507  call    cs:__imp_LocalFree
0x18002250d  mov     rcx, [rbx+228h]; hMem
0x180022514  mov     [rbx+220h], r15
0x18002251b  call    cs:__imp_LocalFree
0x180022521  mov     rcx, [rbx+230h]; hMem
0x180022528  mov     [rbx+228h], r15
0x18002252f  call    cs:__imp_LocalFree
0x180022535  mov     rcx, [rbx+240h]; hMem
0x18002253c  mov     [rbx+230h], r15
0x180022543  call    cs:__imp_LocalFree
0x180022549  mov     rcx, [rbx+2A0h]; hMem
0x180022550  mov     [rbx+240h], r15
0x180022557  call    cs:__imp_LocalFree
0x18002255d  mov     rcx, [rbx+2B8h]; hMem
0x180022564  mov     [rbx+2A0h], r15
0x18002256b  call    cs:__imp_LocalFree
0x180022571  mov     rcx, [rbx+2E8h]; hMem
0x180022578  mov     [rbx+2B8h], r15
0x18002257f  call    cs:__imp_LocalFree
0x180022585  mov     rcx, [rbx+2D8h]
0x18002258c  mov     [rbx+2E8h], r15
0x180022593  test    rcx, rcx
0x180022596  jz      short loc_1800225E6
0x180022598  mov     rcx, [rcx]; void *
0x18002259b  test    rcx, rcx
0x18002259e  jz      short loc_1800225D2
0x1800225a0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800225a4  inc     r8
0x1800225a7  cmp     [rcx+r8*2], r15w
0x1800225ac  jnz     short loc_1800225A4
0x1800225ae  add     r8, r8; Size
0x1800225b1  xor     edx, edx; Val
0x1800225b3  call    memset_0
0x1800225b8  mov     rcx, [rbx+2D8h]
0x1800225bf  mov     rcx, [rcx]; hMem
0x1800225c2  call    cs:__imp_LocalFree
0x1800225c8  mov     rax, [rbx+2D8h]
0x1800225cf  mov     [rax], r15
0x1800225d2  mov     rcx, [rbx+2D8h]; hMem
0x1800225d9  call    cs:__imp_LocalFree
0x1800225df  mov     [rbx+2D8h], r15
0x1800225e6  cmp     cs:hObject, r15
0x1800225ed  jz      short loc_180022611
0x1800225ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225f6  cmp     rcx, r12
0x1800225f9  jz      short loc_18002260C
0x1800225fb  mov     rcx, [rcx+10h]
0x1800225ff  mov     edx, 39h ; '9'
0x180022604  mov     r8, r13
0x180022607  call    WPP_SF_
0x18002260c  call    ?WaitForThread@CWorkerThreadState@@QEAAKXZ; CWorkerThreadState::WaitForThread(void)
0x180022611  mov     eax, [rbx+4]
0x180022614  and     eax, 44008h
0x180022619  cmp     eax, 40000h
0x18002261e  jnz     loc_1800226D3
0x180022624  mov     rcx, cs:WPP_GLOBAL_Control
0x18002262b  cmp     rcx, r12
0x18002262e  jz      short loc_180022641
0x180022630  mov     rcx, [rcx+10h]
0x180022634  mov     edx, 3Ah ; ':'
0x180022639  mov     r8, r13
0x18002263c  call    WPP_SF_
0x180022641  xor     r8d, r8d; Flags
0x180022644  lea     rcx, TargetName; "*Session"
0x18002264b  lea     esi, [r8+2]
0x18002264f  mov     edx, esi; Type
0x180022651  call    cs:__imp_CredDeleteW
0x180022657  test    eax, eax
0x180022659  jnz     short loc_180022671
0x18002265b  movups  xmm6, xmmword ptr [rbx+30Ch]
0x180022662  call    cs:__imp_GetLastError
0x180022668  mov     edx, eax
0x18002266a  movdqu  xmmword ptr [rbp+var_48], xmm6
0x18002266f  jmp     short loc_18002267F
0x180022671  movups  xmm0, xmmword ptr [rbx+30Ch]
0x180022678  xor     edx, edx; unsigned int
0x18002267a  movdqu  xmmword ptr [rbp+var_48], xmm0
0x18002267f  lea     r8, [rbp+var_48]; struct _GUID
0x180022683  mov     ecx, esi; unsigned int
0x180022685  call    ?WriteCredentialUnPlumbingEvent@@YAXKKU_GUID@@@Z; WriteCredentialUnPlumbingEvent(ulong,ulong,_GUID)
0x18002268a  xor     r8d, r8d; Flags
0x18002268d  lea     rcx, TargetName; "*Session"
0x180022694  lea     esi, [r8+3]
0x180022698  mov     edx, esi; Type
0x18002269a  call    cs:__imp_CredDeleteW
0x1800226a0  test    eax, eax
0x1800226a2  jnz     short loc_1800226BA
0x1800226a4  movups  xmm6, xmmword ptr [rbx+30Ch]
0x1800226ab  call    cs:__imp_GetLastError
0x1800226b1  mov     edx, eax
0x1800226b3  movdqu  xmmword ptr [rbp+var_48], xmm6
0x1800226b8  jmp     short loc_1800226C8
0x1800226ba  movups  xmm0, xmmword ptr [rbx+30Ch]
0x1800226c1  xor     edx, edx; unsigned int
0x1800226c3  movdqu  xmmword ptr [rbp+var_48], xmm0
0x1800226c8  lea     r8, [rbp+var_48]; struct _GUID
0x1800226cc  mov     ecx, esi; unsigned int
0x1800226ce  call    ?WriteCredentialUnPlumbingEvent@@YAXKKU_GUID@@@Z; WriteCredentialUnPlumbingEvent(ulong,ulong,_GUID)
0x1800226d3  cmp     [rbx+2D4h], r15d
0x1800226da  jnz     short loc_1800226E1
0x1800226dc  cmp     dword ptr [rbx], 7
0x1800226df  jnz     short loc_180022726
0x1800226e1  test    byte ptr [rbx+4], 1
0x1800226e5  jnz     short loc_180022726
0x1800226e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800226ee  cmp     rcx, r12
0x1800226f1  jz      short loc_180022704
0x1800226f3  mov     rcx, [rcx+10h]
0x1800226f7  mov     edx, 3Bh ; ';'
0x1800226fc  mov     r8, r13
0x1800226ff  call    WPP_SF_
0x180022704  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002270b  call    cs:__imp_EnterCriticalSection
0x180022711  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x180022714  call    ?FreeCachedCredentials@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@@Z; FreeCachedCredentials(_EAPTLS_CONTROL_BLOCK *)
0x180022719  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180022720  call    cs:__imp_LeaveCriticalSection
0x180022726  mov     rcx, [rbx+2F8h]; hMem
0x18002272d  call    cs:__imp_LocalFree
0x180022733  mov     eax, [rbx+4]
0x180022736  test    eax, 4001h
0x18002273b  jnz     short loc_180022758
0x18002273d  shr     eax, 3
0x180022740  lea     rcx, [rbx+374h]; this
0x180022747  and     al, 1
0x180022749  lea     rdx, aEapTls; "EAP-TLS"
0x180022750  mov     [rcx+5], al
0x180022753  call    ?TryWriteTelemetry@EapMethodWithTlsTelemetry@@QEAAXQEBD@Z; EapMethodWithTlsTelemetry::TryWriteTelemetry(char const * const)
0x180022758  mov     rcx, rbx; this
0x18002275b  call    ??_G_EAPTLS_CONTROL_BLOCK@@QEAAPEAXI@Z; _EAPTLS_CONTROL_BLOCK::`scalar deleting destructor'(uint)
0x180022760  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180022767  lea     rcx, [rbp+var_48]; struct NetworkingTriageScenario::GetConnected::RequiredFields *
0x18002276b  mov     dword ptr [rbp+var_48], edi
0x18002276e  mov     [rbp+var_34], 1
0x180022775  movdqu  xmmword ptr [rbp+var_48+4], xmm0
0x18002277a  call    ?EAPTlsEndEvent@GetConnected@NetworkingTriageScenario@@SAXAEBURequiredFields@12@@Z; NetworkingTriageScenario::GetConnected::EAPTlsEndEvent(NetworkingTriageScenario::GetConnected::RequiredFields const &)
0x18002277f  xor     eax, eax
0x180022781  mov     rcx, [rbp+var_28]
0x180022785  xor     rcx, rsp; StackCookie
0x180022788  call    __security_check_cookie
0x18002278d  movaps  xmm6, [rsp+68h+var_18]
0x180022792  add     rsp, 68h
0x180022796  pop     r15
0x180022798  pop     r14
0x18002279a  pop     r13
  ... truncated ...
```
