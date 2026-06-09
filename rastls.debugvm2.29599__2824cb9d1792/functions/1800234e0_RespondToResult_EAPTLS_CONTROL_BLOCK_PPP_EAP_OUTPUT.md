# RespondToResult(_EAPTLS_CONTROL_BLOCK *,_PPP_EAP_OUTPUT *)

- ea: `0x1800234e0`
- end: `0x180023b4f`
- name: `?RespondToResult@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_PPP_EAP_OUTPUT@@@Z`
- size: `1647`
- prototype: `void __fastcall(struct _EAPTLS_CONTROL_BLOCK *, struct _PPP_EAP_OUTPUT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004f508`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18001c680`
- `0x18001dec0`
- `0x1800234e0`
- `0x1800571f0`
- `0x180057b18`
- `0x1800581ac`
- `0x18005a9e4`
- `0x180064cfc`
- `0x18006f3a8`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x180023608`
- `ntdll!WinSqmAddToStream` at `0x180023608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002384a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002384a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800238ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800238ba`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023680`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023680`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002374b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002374b`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x1800237ed`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180023839`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x1800237ed`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180023839`

## pseudocode

```c
void __fastcall RespondToResult(struct _EAPTLS_CONTROL_BLOCK *a1, struct _PPP_EAP_OUTPUT *a2)
{
  int v3; // ecx
  __int64 v5; // rbp
  __int64 v6; // r9
  int v7; // edx
  __int64 v8; // rax
  __int64 v9; // r8
  bool v10; // zf
  _WORD *v11; // rcx
  int v12; // eax
  unsigned int v13; // esi
  const char *v14; // r9
  int v15; // r14d
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v17; // rcx
  DWORD v18; // eax
  int v19; // edx
  struct _GUID v20; // xmm6
  DWORD v21; // edx
  struct _GUID v22; // xmm6
  DWORD v23; // eax
  char *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rdx
  unsigned int v27; // r8d
  _BYTE *i; // rax
  __int64 v29; // rdx
  _WORD *v30; // r9
  __int64 v31; // rdx
  _WORD *v32; // r9
  __int64 v33; // rax
  DWORD v34; // ecx
  unsigned int V0Struct; // eax
  PBYTE pConnectionData; // rcx
  struct _GUID v37; // [rsp+20h] [rbp-38h] BYREF

  v3 = *((_DWORD *)a1 + 1);
  v5 = -1;
  if ( (v3 & 0x4008) == 8 )
  {
    v6 = *((_QWORD *)a1 + 68);
    v37 = 0;
    v7 = 0;
    v8 = -1;
    v9 = v6 + 24LL * *(unsigned int *)(v6 + 12);
    do
      v10 = *(_WORD *)(v9 + 2 * v8++ + 18) == 0;
    while ( !v10 );
    v11 = (_WORD *)(v9 + 18 + 2 * v8);
    if ( (unsigned int)(v6 + *(_DWORD *)(v6 + 4) - (_DWORD)v11) >= 6 && *v11 == 254 )
    {
      v7 = v11[2] & 1;
      if ( (v11[2] & 0xE) != 0 )
        v7 |= 2u;
    }
    if ( (*(_BYTE *)(v6 + 8) & 1) != 0 )
    {
      v12 = 20;
      if ( !*((_DWORD *)a1 + 193) )
        v12 = 4;
      v7 |= v12;
    }
    else if ( g_UseDefaultSCardCert )
    {
      v7 |= 8u;
    }
    v13 = v7 | 0x20;
    if ( *((_DWORD *)a1 + 152) == -1 )
      v13 = v7;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids, v13);
    *(_DWORD *)v37.Data4 = v13;
    v37.Data1 = 1;
    ((void (__fastcall *)(_QWORD, __int64, __int64, struct _GUID *))WinSqmAddToStream)(0, 7452, 1, &v37);
    v3 = *((_DWORD *)a1 + 1);
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v14 = "successful";
    if ( (v3 & 8) == 0 )
      v14 = "unsuccessful";
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v14);
  }
  a2->pUserAttributes = (RAS_AUTH_ATTRIBUTE *)*((_QWORD *)a1 + 67);
  a2->dwAuthResultCode = *((_DWORD *)a1 + 181);
  if ( !*((_QWORD *)a1 + 102) )
    goto LABEL_43;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    v15 = 1;
    if ( !RevertToSelf() && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, LastError);
    }
  }
  else
  {
    v15 = 0;
  }
  if ( !FreeApplicationTicket((struct _NgcTicketContext **)a1 + 102) )
    goto LABEL_32;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
LABEL_32:
    v17 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)a1 + 4) & 8) == 0 && *((_QWORD *)a1 + 100) )
  {
    if ( FreeApplicationTicket((struct _NgcTicketContext **)a1 + 100) )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_39;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
    }
    v17 = WPP_GLOBAL_Control;
  }
LABEL_39:
  if ( !v15 )
    goto LABEL_44;
  if ( !ImpersonateLoggedOnUser(*((HANDLE *)a1 + 1)) )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_44;
    v18 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v18);
  }
LABEL_43:
  v17 = WPP_GLOBAL_Control;
LABEL_44:
  v19 = *((_DWORD *)a1 + 1);
  if ( (v19 & 0x44000) == 0x40000 )
  {
    if ( hObject )
    {
      if ( v17 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)v17 + 2), 235, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      CWorkerThreadState::WaitForThread(v17);
      if ( (*((_BYTE *)a1 + 4) & 8) == 0 )
      {
        if ( CredDeleteW(L"*Session", 2u, 0) )
        {
          v21 = 0;
          v37 = *(struct _GUID *)((char *)a1 + 780);
        }
        else
        {
          v20 = *(struct _GUID *)((char *)a1 + 780);
          v21 = GetLastError();
          v37 = v20;
        }
        WriteCredentialUnPlumbingEvent(2u, v21, &v37);
        if ( CredDeleteW(L"*Session", 3u, 0) )
        {
          v37 = *(struct _GUID *)((char *)a1 + 780);
          WriteCredentialUnPlumbingEvent(3u, 0, &v37);
        }
        else
        {
          v22 = *(struct _GUID *)((char *)a1 + 780);
          v23 = GetLastError();
          v37 = v22;
          WriteCredentialUnPlumbingEvent(3u, v23, &v37);
        }
      }
    }
    else if ( (v19 & 8) != 0 )
    {
      if ( v17 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)v17 + 2), 236, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      v24 = (char *)LocalAlloc(0x40u, 0x28u);
      if ( v24 )
      {
        *(_QWORD *)v24 = *((_QWORD *)a1 + 1);
        *((_QWORD *)v24 + 1) = *((_QWORD *)a1 + 71);
        *((_QWORD *)v24 + 2) = *((_QWORD *)a1 + 68);
        *(_OWORD *)(v24 + 24) = *(_OWORD *)((char *)a1 + 780);
        SaveCertCredsThread(v24);
      }
      else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      }
    }
    *(_WORD *)(*((_QWORD *)a1 + 71) + 64LL) = 0;
    *(_WORD *)(*((_QWORD *)a1 + 71) + 66LL) = 0;
    v25 = 0;
    v26 = *((_QWORD *)a1 + 71);
    v27 = *(_DWORD *)(v26 + 8);
    if ( v27 > 0x48 )
    {
      do
        v10 = *(_WORD *)(*(_QWORD *)(v26 + 40) + 2 * v5++ + 2) == 0;
      while ( !v10 );
      v25 = v27 - 2 * (_DWORD)v5 - 74;
    }
    for ( i = *(_BYTE **)(v26 + 56); v25; --v25 )
      *i++ = 0;
    *(_DWORD *)(*((_QWORD *)a1 + 71) + 12LL) &= ~4u;
    v17 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)a1 + 4) & 2) == 0 )
  {
    a2->fSaveUserData = 1;
    v17 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)a1 + 4) & 8) == 0 || (v29 = *((_QWORD *)a1 + 71)) == 0 )
  {
    a2->pUserData = 0;
    a2->dwSizeOfUserData = 0;
    goto LABEL_95;
  }
  v30 = *(_WORD **)(v29 + 40);
  if ( !v30 || v30 == (_WORD *)0xFFFFFFFFLL )
  {
    if ( v17 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_78;
    WPP_SF_q(*((_QWORD *)v17 + 2), 238);
  }
  else
  {
    *(_QWORD *)(v29 + 40) = (unsigned int)-(*v30 != 0);
  }
  v17 = WPP_GLOBAL_Control;
LABEL_78:
  v31 = *((_QWORD *)a1 + 71);
  v32 = *(_WORD **)(v31 + 56);
  if ( !v32 || v32 == (_WORD *)0xFFFFFFFFLL )
  {
    if ( v17 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_q(*((_QWORD *)v17 + 2), 239);
  }
  else
  {
    *(_QWORD *)(v31 + 56) = (unsigned int)-(*v32 != 0);
  }
  v33 = *((_QWORD *)a1 + 71);
  a2->pUserData = (PBYTE)v33;
  if ( v33 )
    v34 = *(_DWORD *)(v33 + 8);
  else
    v34 = 0;
  a2->dwSizeOfUserData = v34;
  if ( *((_QWORD *)a1 + 69) )
  {
    a2->fSaveConnectionData = 1;
    V0Struct = ConnPropGetV0Struct(
                 *((struct _EAPTLS_CONN_PROPERTIES_V1 **)a1 + 69),
                 (struct _EAPTLS_CONN_PROPERTIES **)&a2->pConnectionData);
    if ( V0Struct )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 240, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, V0Struct);
    }
    else
    {
      pConnectionData = a2->pConnectionData;
      a2->dwSizeOfConnectionData = *((_DWORD *)pConnectionData + 1);
      *((_QWORD *)a1 + 70) = pConnectionData;
    }
  }
  if ( (*((_DWORD *)a1 + 1) & 0x40000) != 0 )
  {
    a2->fSaveToCredMan = 1;
    a2->pNgcKerbTicket = (NgcTicketContext *)*((_QWORD *)a1 + 100);
  }
  else
  {
    a2->fSaveToCredMan = 0;
    a2->pNgcKerbTicket = 0;
  }
LABEL_95:
  if ( (*((_DWORD *)a1 + 1) & 0x4001) == 0 )
  {
    *((_BYTE *)a1 + 889) = (*((_DWORD *)a1 + 1) & 8) != 0;
    if ( !*((_BYTE *)a1 + 890) )
    {
      EapHostTelemetry::TlsBasedMethodCompletion("EAP-TLS", *((unsigned __int8 *)a1 + 888), *((unsigned int *)a1 + 221));
      *((_BYTE *)a1 + 890) = 1;
    }
  }
  a2->Action = EAPACTION_Done;
}

```

## disassembly

```asm
0x1800234e0  push    rbx
0x1800234e2  push    rdi
0x1800234e3  sub     rsp, 48h
0x1800234e7  mov     [rsp+58h+arg_0], rbp
0x1800234ec  mov     rbx, rcx
0x1800234ef  mov     ecx, [rcx+4]
0x1800234f2  mov     rdi, rdx
0x1800234f5  mov     [rsp+58h+arg_8], rsi
0x1800234fa  mov     eax, ecx
0x1800234fc  mov     [rsp+58h+arg_10], r13
0x180023501  and     eax, 4008h
0x180023506  mov     [rsp+58h+var_18], r15
0x18002350b  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180023512  lea     r15, WPP_GLOBAL_Control
0x180023519  mov     r13d, 0FFFFFFFFh
0x18002351f  cmp     eax, 8
0x180023522  jnz     loc_180023611
0x180023528  mov     r9, [rbx+220h]
0x18002352f  xorps   xmm0, xmm0
0x180023532  movups  xmmword ptr [rsp+58h+var_38.Data1], xmm0
0x180023537  xor     edx, edx
0x180023539  mov     eax, [r9+0Ch]
0x18002353d  lea     rcx, [rax+rax*2]
0x180023541  mov     rax, rbp
0x180023544  lea     r8, [r9+rcx*8]
0x180023548  nop     dword ptr [rax+rax+00000000h]
0x180023550  cmp     [r8+rax*2+12h], dx
0x180023556  lea     rax, [rax+1]
0x18002355a  jnz     short loc_180023550
0x18002355c  lea     rcx, [r8+12h]
0x180023560  lea     rcx, [rcx+rax*2]
0x180023564  mov     eax, [r9+4]
0x180023568  sub     eax, ecx
0x18002356a  add     eax, r9d
0x18002356d  cmp     eax, 6
0x180023570  jb      short loc_18002358C
0x180023572  mov     eax, 0FEh
0x180023577  cmp     [rcx], ax
0x18002357a  jnz     short loc_18002358C
0x18002357c  movzx   eax, word ptr [rcx+4]
0x180023580  mov     edx, eax
0x180023582  and     edx, 1
0x180023585  test    al, 0Eh
0x180023587  jz      short loc_18002358C
0x180023589  or      edx, 2
0x18002358c  test    byte ptr [r9+8], 1
0x180023591  jz      short loc_1800235AB
0x180023593  cmp     dword ptr [rbx+304h], 0
0x18002359a  mov     eax, 14h
0x18002359f  mov     ecx, 4
0x1800235a4  cmovz   eax, ecx
0x1800235a7  or      edx, eax
0x1800235a9  jmp     short loc_1800235B7
0x1800235ab  cmp     cs:?g_UseDefaultSCardCert@@3HA, 0; int g_UseDefaultSCardCert
0x1800235b2  jz      short loc_1800235B7
0x1800235b4  or      edx, 8
0x1800235b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235be  mov     esi, edx
0x1800235c0  or      esi, 20h
0x1800235c3  cmp     [rbx+260h], r13d
0x1800235ca  cmovz   esi, edx
0x1800235cd  cmp     rcx, r15
0x1800235d0  jz      short loc_1800235EA
0x1800235d2  mov     rcx, [rcx+10h]
0x1800235d6  lea     r8, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x1800235dd  mov     edx, 53h ; 'S'
0x1800235e2  mov     r9d, esi
0x1800235e5  call    WPP_SF_d
0x1800235ea  lea     r9, [rsp+58h+var_38]
0x1800235ef  mov     dword ptr [rsp+58h+var_38.Data4], esi
0x1800235f3  mov     edx, 1D1Ch
0x1800235f8  mov     [rsp+58h+var_38.Data1], 1
0x180023600  xor     ecx, ecx
0x180023602  mov     r8d, 1
0x180023608  call    cs:__imp_WinSqmAddToStream
0x18002360e  mov     ecx, [rbx+4]
0x180023611  mov     rax, cs:WPP_GLOBAL_Control
0x180023618  cmp     rax, r15
0x18002361b  jz      short loc_180023647
0x18002361d  test    cl, 8
0x180023620  lea     r9, aSuccessful; "successful"
0x180023627  lea     rcx, aUnsuccessful; "unsuccessful"
0x18002362e  mov     edx, 0E6h
0x180023633  cmovz   r9, rcx
0x180023637  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18002363e  mov     rcx, [rax+10h]
0x180023642  call    WPP_SF_s
0x180023647  mov     rax, [rbx+218h]
0x18002364e  mov     [rdi+10h], rax
0x180023652  mov     eax, [rbx+2D4h]
0x180023658  mov     [rdi+8], eax
0x18002365b  cmp     qword ptr [rbx+330h], 0
0x180023663  jz      loc_180023786
0x180023669  mov     eax, gs:179Ch
0x180023671  mov     [rsp+58h+arg_18], r14
0x180023676  test    eax, eax
0x180023678  jz      short loc_1800236BA
0x18002367a  mov     r14d, 1
0x180023680  call    cs:__imp_RevertToSelf
0x180023686  test    eax, eax
0x180023688  jnz     short loc_1800236BD
0x18002368a  cmp     cs:WPP_GLOBAL_Control, r15
0x180023691  jz      short loc_1800236BD
0x180023693  call    cs:__imp_GetLastError
0x180023699  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236a0  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x1800236a7  mov     edx, 0E7h
0x1800236ac  mov     r9d, eax
0x1800236af  mov     rcx, [rcx+10h]
0x1800236b3  call    WPP_SF_d
0x1800236b8  jmp     short loc_1800236BD
0x1800236ba  xor     r14d, r14d
0x1800236bd  lea     rcx, [rbx+330h]; struct _NgcTicketContext **
0x1800236c4  call    ?FreeApplicationTicket@@YAKPEAPEAU_NgcTicketContext@@@Z; FreeApplicationTicket(_NgcTicketContext * *)
0x1800236c9  test    eax, eax
0x1800236cb  jz      short loc_1800236EE
0x1800236cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236d4  cmp     rcx, r15
0x1800236d7  jz      short loc_1800236F5
0x1800236d9  mov     rcx, [rcx+10h]
0x1800236dd  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x1800236e4  mov     edx, 0E8h
0x1800236e9  call    WPP_SF_
0x1800236ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236f5  test    byte ptr [rbx+4], 8
0x1800236f9  jnz     short loc_18002373D
0x1800236fb  cmp     qword ptr [rbx+320h], 0
0x180023703  jz      short loc_18002373D
0x180023705  lea     rcx, [rbx+320h]; struct _NgcTicketContext **
0x18002370c  call    ?FreeApplicationTicket@@YAKPEAPEAU_NgcTicketContext@@@Z; FreeApplicationTicket(_NgcTicketContext * *)
0x180023711  test    eax, eax
0x180023713  jz      short loc_180023736
0x180023715  mov     rcx, cs:WPP_GLOBAL_Control
0x18002371c  cmp     rcx, r15
0x18002371f  jz      short loc_18002373D
0x180023721  mov     rcx, [rcx+10h]
0x180023725  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18002372c  mov     edx, 0E9h
0x180023731  call    WPP_SF_
0x180023736  mov     rcx, cs:WPP_GLOBAL_Control
0x18002373d  test    r14d, r14d
0x180023740  mov     r14, [rsp+58h+arg_18]
0x180023745  jz      short loc_18002378D
0x180023747  mov     rcx, [rbx+8]; hToken
0x18002374b  call    cs:__imp_ImpersonateLoggedOnUser
0x180023751  test    eax, eax
0x180023753  jnz     short loc_180023786
0x180023755  mov     rcx, cs:WPP_GLOBAL_Control
0x18002375c  cmp     rcx, r15
0x18002375f  jz      short loc_18002378D
0x180023761  call    cs:__imp_GetLastError
0x180023767  mov     rcx, cs:WPP_GLOBAL_Control
0x18002376e  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180023775  mov     edx, 0EAh
0x18002377a  mov     r9d, eax
0x18002377d  mov     rcx, [rcx+10h]
0x180023781  call    WPP_SF_d
0x180023786  mov     rcx, cs:WPP_GLOBAL_Control
0x18002378d  mov     edx, [rbx+4]
0x180023790  mov     eax, edx
0x180023792  and     eax, 44000h
0x180023797  cmp     eax, 40000h
0x18002379c  jnz     loc_180023992
0x1800237a2  cmp     cs:hObject, 0
0x1800237aa  movaps  [rsp+58h+var_28], xmm6
0x1800237af  jz      loc_18002388D
0x1800237b5  cmp     rcx, r15
0x1800237b8  jz      short loc_1800237CF
0x1800237ba  mov     rcx, [rcx+10h]
0x1800237be  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x1800237c5  mov     edx, 0EBh
0x1800237ca  call    WPP_SF_
0x1800237cf  call    ?WaitForThread@CWorkerThreadState@@QEAAKXZ; CWorkerThreadState::WaitForThread(void)
0x1800237d4  test    byte ptr [rbx+4], 8
0x1800237d8  jnz     loc_180023918
0x1800237de  xor     r8d, r8d; Flags
0x1800237e1  lea     rcx, TargetName; "*Session"
0x1800237e8  mov     edx, 2; Type
0x1800237ed  call    cs:__imp_CredDeleteW
0x1800237f3  test    eax, eax
0x1800237f5  jnz     short loc_18002380D
0x1800237f7  movups  xmm6, xmmword ptr [rbx+30Ch]
0x1800237fe  call    cs:__imp_GetLastError
0x180023804  mov     edx, eax
0x180023806  movaps  xmmword ptr [rsp+58h+var_38.Data1], xmm6
0x18002380b  jmp     short loc_18002381B
0x18002380d  movups  xmm0, xmmword ptr [rbx+30Ch]
0x180023814  xor     edx, edx; unsigned int
0x180023816  movaps  xmmword ptr [rsp+58h+var_38.Data1], xmm0
0x18002381b  lea     r8, [rsp+58h+var_38]; struct _GUID
0x180023820  mov     ecx, 2; unsigned int
0x180023825  call    ?WriteCredentialUnPlumbingEvent@@YAXKKU_GUID@@@Z; WriteCredentialUnPlumbingEvent(ulong,ulong,_GUID)
0x18002382a  xor     r8d, r8d; Flags
0x18002382d  lea     rcx, TargetName; "*Session"
0x180023834  mov     edx, 3; Type
0x180023839  call    cs:__imp_CredDeleteW
0x18002383f  test    eax, eax
0x180023841  jnz     short loc_18002386B
0x180023843  movups  xmm6, xmmword ptr [rbx+30Ch]
0x18002384a  call    cs:__imp_GetLastError
0x180023850  lea     r8, [rsp+58h+var_38]; struct _GUID
0x180023855  movaps  xmmword ptr [rsp+58h+var_38.Data1], xmm6
0x18002385a  mov     edx, eax; unsigned int
0x18002385c  mov     ecx, 3; unsigned int
0x180023861  call    ?WriteCredentialUnPlumbingEvent@@YAXKKU_GUID@@@Z; WriteCredentialUnPlumbingEvent(ulong,ulong,_GUID)
0x180023866  jmp     loc_180023918
0x18002386b  movups  xmm0, xmmword ptr [rbx+30Ch]
0x180023872  lea     r8, [rsp+58h+var_38]; struct _GUID
0x180023877  xor     edx, edx; unsigned int
0x180023879  mov     ecx, 3; unsigned int
0x18002387e  movaps  xmmword ptr [rsp+58h+var_38.Data1], xmm0
0x180023883  call    ?WriteCredentialUnPlumbingEvent@@YAXKKU_GUID@@@Z; WriteCredentialUnPlumbingEvent(ulong,ulong,_GUID)
0x180023888  jmp     loc_180023918
0x18002388d  test    dl, 8
0x180023890  jz      loc_180023918
0x180023896  cmp     rcx, r15
0x180023899  jz      short loc_1800238B0
0x18002389b  mov     rcx, [rcx+10h]
0x18002389f  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x1800238a6  mov     edx, 0ECh
0x1800238ab  call    WPP_SF_
0x1800238b0  mov     edx, 28h ; '('; uBytes
0x1800238b5  mov     ecx, 40h ; '@'; uFlags
0x1800238ba  call    cs:__imp_LocalAlloc
0x1800238c0  mov     rcx, rax; Parameter
0x1800238c3  test    rax, rax
0x1800238c6  jnz     short loc_1800238EB
0x1800238c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238cf  cmp     rcx, r15
0x1800238d2  jz      short loc_180023918
0x1800238d4  mov     rcx, [rcx+10h]
0x1800238d8  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x1800238df  mov     edx, 0EDh
0x1800238e4  call    WPP_SF_
0x1800238e9  jmp     short loc_180023918
0x1800238eb  mov     rax, [rbx+8]
0x1800238ef  mov     [rcx], rax
0x1800238f2  mov     rax, [rbx+238h]
0x1800238f9  mov     [rcx+8], rax
0x1800238fd  mov     rax, [rbx+220h]
0x180023904  mov     [rcx+10h], rax
0x180023908  movups  xmm0, xmmword ptr [rbx+30Ch]
0x18002390f  movups  xmmword ptr [rcx+18h], xmm0
0x180023913  call    ?SaveCertCredsThread@@YAKPEAX@Z; SaveCertCredsThread(void *)
0x180023918  mov     rcx, [rbx+238h]
0x18002391f  xor     eax, eax
0x180023921  movaps  xmm6, [rsp+58h+var_28]
0x180023926  mov     [rcx+40h], ax
0x18002392a  mov     rcx, [rbx+238h]
0x180023931  mov     [rcx+42h], ax
0x180023935  xor     ecx, ecx
0x180023937  mov     rdx, [rbx+238h]
0x18002393e  mov     r8d, [rdx+8]
0x180023942  cmp     r8d, 48h ; 'H'
0x180023946  jbe     short loc_18002396A
0x180023948  mov     rax, [rdx+28h]
0x18002394c  nop     dword ptr [rax+00h]
0x180023950  cmp     [rax+rbp*2+2], cx
0x180023955  lea     rbp, [rbp+1]
0x180023959  jnz     short loc_180023950
0x18002395b  lea     eax, ds:0[rbp*2]
0x180023962  mov     ecx, r8d
0x180023965  sub     ecx, eax
0x180023967  sub     ecx, 4Ah ; 'J'
0x18002396a  mov     rax, [rdx+38h]
0x18002396e  test    rcx, rcx
0x180023971  jz      short loc_180023980
0x180023973  mov     byte ptr [rax], 0
0x180023976  lea     rax, [rax+1]
0x18002397a  sub     rcx, 1
0x18002397e  jnz     short loc_180023973
0x180023980  mov     rax, [rbx+238h]
0x180023987  and     dword ptr [rax+0Ch], 0FFFFFFFBh
0x18002398b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023992  test    byte ptr [rbx+4], 2
0x180023996  mov     rbp, [rsp+58h+arg_0]
0x18002399b  jnz     short loc_1800239AB
0x18002399d  mov     dword ptr [rdi+3Ch], 1
0x1800239a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239ab  test    byte ptr [rbx+4], 8
0x1800239af  jz      loc_180023ADD
0x1800239b5  mov     rdx, [rbx+238h]
0x1800239bc  test    rdx, rdx
0x1800239bf  jz      loc_180023ADD
0x1800239c5  mov     r9, [rdx+28h]
0x1800239c9  test    r9, r9
0x1800239cc  jz      short loc_1800239E6
0x1800239ce  cmp     r9, r13
0x1800239d1  jz      short loc_1800239E6
0x1800239d3  movzx   eax, word ptr [r9]
0x1800239d7  neg     ax
0x1800239da  sbb     rcx, rcx
0x1800239dd  and     rcx, r13
0x1800239e0  mov     [rdx+28h], rcx
0x1800239e4  jmp     short loc_1800239F9
0x1800239e6  cmp     rcx, r15
0x1800239e9  jz      short loc_180023A00
0x1800239eb  mov     rcx, [rcx+10h]
0x1800239ef  mov     edx, 0EEh
0x1800239f4  call    WPP_SF_q
  ... truncated ...
```
