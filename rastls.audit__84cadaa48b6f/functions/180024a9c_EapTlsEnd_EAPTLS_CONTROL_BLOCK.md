# EapTlsEnd(_EAPTLS_CONTROL_BLOCK *)

- ea: `0x180024a9c`
- end: `0x18002503a`
- name: `?EapTlsEnd@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@@Z`
- size: `1438`
- prototype: `unsigned int __fastcall(struct _EAPTLS_CONTROL_BLOCK *)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025d78`
- `0x18005cea0`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180010140`
- `0x180018f50`
- `0x180024a9c`
- `0x180033a58`
- `0x180038270`
- `0x180038e64`
- `0x18004ddec`
- `0x1800507e0`
- `0x1800542a0`
- `0x18005b3dc`
- `0x18005b790`
- `0x18005b944`
- `0x18005fcb8`
- `0x180068880`
- `0x180073fa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024f8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024f8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024faa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024f29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024f29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024da5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024dbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024dd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024e22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024e3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024fbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024da5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024dbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024dd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024e22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024e3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024fbd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180024b64`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180024b64`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180024c12`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180024c12`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180024ebd`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180024f12`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180024ebd`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180024f12`
- `SspiCli!DeleteSecurityContext` at `0x180024ca6`
- `SspiCli!DeleteSecurityContext` at `0x180024ca6`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
      WPP_SF_S(v4, 51, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v5);
    }
    if ( *((_QWORD *)a1 + 102) )
    {
      if ( NtCurrentTeb()->IsImpersonating )
      {
        v6 = 1;
        if ( !RevertToSelf() && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, LastError);
        }
      }
      else
      {
        v6 = 0;
      }
      if ( FreeApplicationTicket((struct _NgcTicketContext **)a1 + 102)
        && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
      }
      if ( (*((_BYTE *)a1 + 4) & 8) == 0
        && *((_QWORD *)a1 + 100)
        && FreeApplicationTicket((struct _NgcTicketContext **)a1 + 100)
        && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
      }
      if ( v6
        && !ImpersonateLoggedOnUser(*((HANDLE *)a1 + 1))
        && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v8 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v8);
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
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v10);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
      CWorkerThreadState::WaitForThread(v23);
    }
    if ( (*((_DWORD *)a1 + 1) & 0x44008) == 0x40000 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
0x180024a9c  push    rbp
0x180024a9e  push    rbx
0x180024a9f  push    rsi
0x180024aa0  push    rdi
0x180024aa1  push    r12
0x180024aa3  push    r13
0x180024aa5  push    r14
0x180024aa7  push    r15
0x180024aa9  mov     rbp, rsp
0x180024aac  sub     rsp, 68h
0x180024ab0  movaps  [rsp+68h+var_18], xmm6
0x180024ab5  mov     rax, cs:__security_cookie
0x180024abc  xor     rax, rsp
0x180024abf  mov     [rbp+var_28], rax
0x180024ac3  mov     rbx, rcx
0x180024ac6  mov     rcx, cs:WPP_GLOBAL_Control
0x180024acd  lea     r12, WPP_GLOBAL_Control
0x180024ad4  lea     r13, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180024adb  cmp     rcx, r12
0x180024ade  jz      short loc_180024AF8
0x180024ae0  mov     rcx, [rcx+10h]
0x180024ae4  mov     edx, 32h ; '2'
0x180024ae9  mov     r8, r13
0x180024aec  call    WPP_SF_
0x180024af1  mov     rcx, cs:WPP_GLOBAL_Control
0x180024af8  xor     r15d, r15d
0x180024afb  mov     edi, 11h
0x180024b00  test    rbx, rbx
0x180024b03  jz      loc_180024FF6
0x180024b09  mov     edi, [rbx+4]
0x180024b0c  and     edi, 4000h
0x180024b12  or      edi, 22000h
0x180024b18  shr     edi, 0Dh
0x180024b1b  cmp     rcx, r12
0x180024b1e  jz      short loc_180024B42
0x180024b20  mov     rcx, [rcx+10h]
0x180024b24  lea     rax, [rbx+10h]
0x180024b28  test    rax, rax
0x180024b2b  lea     r9, String
0x180024b32  lea     edx, [r15+33h]
0x180024b36  mov     r8, r13
0x180024b39  cmovnz  r9, rax
0x180024b3d  call    WPP_SF_S
0x180024b42  lea     rsi, [rbx+330h]
0x180024b49  cmp     [rsi], r15
0x180024b4c  jz      loc_180024C52
0x180024b52  mov     eax, gs:179Ch
0x180024b5a  test    eax, eax
0x180024b5c  jz      short loc_180024BA5
0x180024b5e  mov     r14d, 1
0x180024b64  call    cs:__imp_RevertToSelf
0x180024b6b  nop     dword ptr [rax+rax+00h]
0x180024b70  test    eax, eax
0x180024b72  jnz     short loc_180024BA8
0x180024b74  cmp     cs:WPP_GLOBAL_Control, r12
0x180024b7b  jz      short loc_180024BA8
0x180024b7d  call    cs:__imp_GetLastError
0x180024b84  nop     dword ptr [rax+rax+00h]
0x180024b89  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b90  lea     edx, [r14+33h]
0x180024b94  mov     r9d, eax
0x180024b97  mov     r8, r13
0x180024b9a  mov     rcx, [rcx+10h]
0x180024b9e  call    WPP_SF_d
0x180024ba3  jmp     short loc_180024BA8
0x180024ba5  mov     r14d, r15d
0x180024ba8  mov     rcx, rsi; struct _NgcTicketContext **
0x180024bab  call    ?FreeApplicationTicket@@YAKPEAPEAU_NgcTicketContext@@@Z; FreeApplicationTicket(_NgcTicketContext * *)
0x180024bb0  test    eax, eax
0x180024bb2  jz      short loc_180024BD1
0x180024bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180024bbb  cmp     rcx, r12
0x180024bbe  jz      short loc_180024BD1
0x180024bc0  mov     rcx, [rcx+10h]
0x180024bc4  mov     edx, 35h ; '5'
0x180024bc9  mov     r8, r13
0x180024bcc  call    WPP_SF_
0x180024bd1  test    byte ptr [rbx+4], 8
0x180024bd5  jnz     short loc_180024C09
0x180024bd7  lea     rcx, [rbx+320h]; struct _NgcTicketContext **
0x180024bde  cmp     [rcx], r15
0x180024be1  jz      short loc_180024C09
0x180024be3  call    ?FreeApplicationTicket@@YAKPEAPEAU_NgcTicketContext@@@Z; FreeApplicationTicket(_NgcTicketContext * *)
0x180024be8  test    eax, eax
0x180024bea  jz      short loc_180024C09
0x180024bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180024bf3  cmp     rcx, r12
0x180024bf6  jz      short loc_180024C09
0x180024bf8  mov     rcx, [rcx+10h]
0x180024bfc  mov     edx, 36h ; '6'
0x180024c01  mov     r8, r13
0x180024c04  call    WPP_SF_
0x180024c09  test    r14d, r14d
0x180024c0c  jz      short loc_180024C52
0x180024c0e  mov     rcx, [rbx+8]; hToken
0x180024c12  call    cs:__imp_ImpersonateLoggedOnUser
0x180024c19  nop     dword ptr [rax+rax+00h]
0x180024c1e  test    eax, eax
0x180024c20  jnz     short loc_180024C52
0x180024c22  cmp     cs:WPP_GLOBAL_Control, r12
0x180024c29  jz      short loc_180024C52
0x180024c2b  call    cs:__imp_GetLastError
0x180024c32  nop     dword ptr [rax+rax+00h]
0x180024c37  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c3e  mov     edx, 37h ; '7'
0x180024c43  mov     r9d, eax
0x180024c46  mov     r8, r13
0x180024c49  mov     rcx, [rcx+10h]
0x180024c4d  call    WPP_SF_d
0x180024c52  cmp     [rbx+250h], r15
0x180024c59  jz      short loc_180024C62
0x180024c5b  mov     [rbx+250h], r15
0x180024c62  mov     eax, [rbx+4]
0x180024c65  bt      eax, 14h
0x180024c69  jnb     short loc_180024C80
0x180024c6b  shr     eax, 3
0x180024c6e  and     eax, 1
0x180024c71  mov     ecx, eax; int
0x180024c73  call    ?SQMPeapConnectWithoutCA@@YAXH@Z; SQMPeapConnectWithoutCA(int)
0x180024c78  btr     dword ptr [rbx+4], 14h
0x180024c7d  mov     eax, [rbx+4]
0x180024c80  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x180024c83  test    al, 8
0x180024c85  jz      short loc_180024C8E
0x180024c87  call    ?WriteTlsAuthSuccessEvent@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@@Z; WriteTlsAuthSuccessEvent(_EAPTLS_CONTROL_BLOCK *)
0x180024c8c  jmp     short loc_180024C99
0x180024c8e  mov     edx, [rbx+2D4h]; unsigned int
0x180024c94  call    ?WriteTlsAuthFailEvent@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@K@Z; WriteTlsAuthFailEvent(_EAPTLS_CONTROL_BLOCK *,ulong)
0x180024c99  test    byte ptr [rbx+4], 40h
0x180024c9d  jnz     short loc_180024CD6
0x180024c9f  lea     rcx, [rbx+288h]; phContext
0x180024ca6  call    cs:__imp_DeleteSecurityContext
0x180024cad  nop     dword ptr [rax+rax+00h]
0x180024cb2  test    eax, eax
0x180024cb4  jz      short loc_180024CD6
0x180024cb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180024cbd  cmp     rcx, r12
0x180024cc0  jz      short loc_180024CD6
0x180024cc2  mov     rcx, [rcx+10h]
0x180024cc6  mov     edx, 38h ; '8'
0x180024ccb  mov     r9d, eax
0x180024cce  mov     r8, r13
0x180024cd1  call    WPP_SF_d
0x180024cd6  test    byte ptr [rbx+4], 20h
0x180024cda  jnz     short loc_180024CE6
0x180024cdc  xorps   xmm0, xmm0
0x180024cdf  movups  xmmword ptr [rbx+268h], xmm0
0x180024ce6  or      dword ptr [rbx+4], 60h
0x180024cea  mov     rcx, [rbx+218h]; hMem
0x180024cf1  test    rcx, rcx
0x180024cf4  jz      short loc_180024CFB
0x180024cf6  call    RasAuthAttributeDestroy
0x180024cfb  mov     rcx, [rbx+280h]; hMem
0x180024d02  call    cs:__imp_LocalFree
0x180024d09  nop     dword ptr [rax+rax+00h]
0x180024d0e  mov     rcx, [rbx+238h]; hMem
0x180024d15  mov     [rbx+280h], r15
0x180024d1c  mov     [rbx+278h], r15d
0x180024d23  call    cs:__imp_LocalFree
0x180024d2a  nop     dword ptr [rax+rax+00h]
0x180024d2f  mov     rcx, [rbx+220h]; hMem
0x180024d36  mov     [rbx+238h], r15
0x180024d3d  call    cs:__imp_LocalFree
0x180024d44  nop     dword ptr [rax+rax+00h]
0x180024d49  mov     rcx, [rbx+228h]; hMem
0x180024d50  mov     [rbx+220h], r15
0x180024d57  call    cs:__imp_LocalFree
0x180024d5e  nop     dword ptr [rax+rax+00h]
0x180024d63  mov     rcx, [rbx+230h]; hMem
0x180024d6a  mov     [rbx+228h], r15
0x180024d71  call    cs:__imp_LocalFree
0x180024d78  nop     dword ptr [rax+rax+00h]
0x180024d7d  mov     rcx, [rbx+240h]; hMem
0x180024d84  mov     [rbx+230h], r15
0x180024d8b  call    cs:__imp_LocalFree
0x180024d92  nop     dword ptr [rax+rax+00h]
0x180024d97  mov     rcx, [rbx+2A0h]; hMem
0x180024d9e  mov     [rbx+240h], r15
0x180024da5  call    cs:__imp_LocalFree
0x180024dac  nop     dword ptr [rax+rax+00h]
0x180024db1  mov     rcx, [rbx+2B8h]; hMem
0x180024db8  mov     [rbx+2A0h], r15
0x180024dbf  call    cs:__imp_LocalFree
0x180024dc6  nop     dword ptr [rax+rax+00h]
0x180024dcb  mov     rcx, [rbx+2E8h]; hMem
0x180024dd2  mov     [rbx+2B8h], r15
0x180024dd9  call    cs:__imp_LocalFree
0x180024de0  nop     dword ptr [rax+rax+00h]
0x180024de5  mov     rcx, [rbx+2D8h]
0x180024dec  mov     [rbx+2E8h], r15
0x180024df3  test    rcx, rcx
0x180024df6  jz      short loc_180024E52
0x180024df8  mov     rcx, [rcx]; void *
0x180024dfb  test    rcx, rcx
0x180024dfe  jz      short loc_180024E38
0x180024e00  or      r8, 0FFFFFFFFFFFFFFFFh
0x180024e04  inc     r8
0x180024e07  cmp     [rcx+r8*2], r15w
0x180024e0c  jnz     short loc_180024E04
0x180024e0e  add     r8, r8; Size
0x180024e11  xor     edx, edx; Val
0x180024e13  call    memset_0
0x180024e18  mov     rcx, [rbx+2D8h]
0x180024e1f  mov     rcx, [rcx]; hMem
0x180024e22  call    cs:__imp_LocalFree
0x180024e29  nop     dword ptr [rax+rax+00h]
0x180024e2e  mov     rax, [rbx+2D8h]
0x180024e35  mov     [rax], r15
0x180024e38  mov     rcx, [rbx+2D8h]; hMem
0x180024e3f  call    cs:__imp_LocalFree
0x180024e46  nop     dword ptr [rax+rax+00h]
0x180024e4b  mov     [rbx+2D8h], r15
0x180024e52  cmp     cs:hObject, r15
0x180024e59  jz      short loc_180024E7D
0x180024e5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e62  cmp     rcx, r12
0x180024e65  jz      short loc_180024E78
0x180024e67  mov     rcx, [rcx+10h]
0x180024e6b  mov     edx, 39h ; '9'
0x180024e70  mov     r8, r13
0x180024e73  call    WPP_SF_
0x180024e78  call    ?WaitForThread@CWorkerThreadState@@QEAAKXZ; CWorkerThreadState::WaitForThread(void)
0x180024e7d  mov     eax, [rbx+4]
0x180024e80  and     eax, 44008h
0x180024e85  cmp     eax, 40000h
0x180024e8a  jnz     loc_180024F57
0x180024e90  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e97  cmp     rcx, r12
0x180024e9a  jz      short loc_180024EAD
0x180024e9c  mov     rcx, [rcx+10h]
0x180024ea0  mov     edx, 3Ah ; ':'
0x180024ea5  mov     r8, r13
0x180024ea8  call    WPP_SF_
0x180024ead  xor     r8d, r8d; Flags
0x180024eb0  lea     rcx, TargetName; "*Session"
0x180024eb7  lea     esi, [r8+2]
0x180024ebb  mov     edx, esi; Type
0x180024ebd  call    cs:__imp_CredDeleteW
0x180024ec4  nop     dword ptr [rax+rax+00h]
0x180024ec9  test    eax, eax
0x180024ecb  jnz     short loc_180024EE9
0x180024ecd  movups  xmm6, xmmword ptr [rbx+30Ch]
0x180024ed4  call    cs:__imp_GetLastError
0x180024edb  nop     dword ptr [rax+rax+00h]
0x180024ee0  mov     edx, eax
0x180024ee2  movdqu  xmmword ptr [rbp+var_48], xmm6
0x180024ee7  jmp     short loc_180024EF7
0x180024ee9  movups  xmm0, xmmword ptr [rbx+30Ch]
0x180024ef0  xor     edx, edx; unsigned int
0x180024ef2  movdqu  xmmword ptr [rbp+var_48], xmm0
0x180024ef7  lea     r8, [rbp+var_48]; struct _GUID
0x180024efb  mov     ecx, esi; unsigned int
0x180024efd  call    ?WriteCredentialUnPlumbingEvent@@YAXKKU_GUID@@@Z; WriteCredentialUnPlumbingEvent(ulong,ulong,_GUID)
0x180024f02  xor     r8d, r8d; Flags
0x180024f05  lea     rcx, TargetName; "*Session"
0x180024f0c  lea     esi, [r8+3]
0x180024f10  mov     edx, esi; Type
0x180024f12  call    cs:__imp_CredDeleteW
0x180024f19  nop     dword ptr [rax+rax+00h]
0x180024f1e  test    eax, eax
0x180024f20  jnz     short loc_180024F3E
0x180024f22  movups  xmm6, xmmword ptr [rbx+30Ch]
0x180024f29  call    cs:__imp_GetLastError
0x180024f30  nop     dword ptr [rax+rax+00h]
0x180024f35  mov     edx, eax
0x180024f37  movdqu  xmmword ptr [rbp+var_48], xmm6
0x180024f3c  jmp     short loc_180024F4C
0x180024f3e  movups  xmm0, xmmword ptr [rbx+30Ch]
0x180024f45  xor     edx, edx; unsigned int
0x180024f47  movdqu  xmmword ptr [rbp+var_48], xmm0
0x180024f4c  lea     r8, [rbp+var_48]; struct _GUID
0x180024f50  mov     ecx, esi; unsigned int
0x180024f52  call    ?WriteCredentialUnPlumbingEvent@@YAXKKU_GUID@@@Z; WriteCredentialUnPlumbingEvent(ulong,ulong,_GUID)
0x180024f57  cmp     [rbx+2D4h], r15d
0x180024f5e  jnz     short loc_180024F65
0x180024f60  cmp     dword ptr [rbx], 7
0x180024f63  jnz     short loc_180024FB6
0x180024f65  test    byte ptr [rbx+4], 1
0x180024f69  jnz     short loc_180024FB6
0x180024f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f72  cmp     rcx, r12
0x180024f75  jz      short loc_180024F88
0x180024f77  mov     rcx, [rcx+10h]
0x180024f7b  mov     edx, 3Bh ; ';'
0x180024f80  mov     r8, r13
0x180024f83  call    WPP_SF_
0x180024f88  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180024f8f  call    cs:__imp_EnterCriticalSection
0x180024f96  nop     dword ptr [rax+rax+00h]
0x180024f9b  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x180024f9e  call    ?FreeCachedCredentials@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@@Z; FreeCachedCredentials(_EAPTLS_CONTROL_BLOCK *)
0x180024fa3  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180024faa  call    cs:__imp_LeaveCriticalSection
0x180024fb1  nop     dword ptr [rax+rax+00h]
0x180024fb6  mov     rcx, [rbx+2F8h]; hMem
0x180024fbd  call    cs:__imp_LocalFree
0x180024fc4  nop     dword ptr [rax+rax+00h]
0x180024fc9  mov     eax, [rbx+4]
0x180024fcc  test    eax, 4001h
0x180024fd1  jnz     short loc_180024FEE
  ... truncated ...
```
