# RespondToResult(_EAPTLS_CONTROL_BLOCK *,_PPP_EAP_OUTPUT *)

- ea: `0x180025ff0`
- end: `0x1800266a0`
- name: `?RespondToResult@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_PPP_EAP_OUTPUT@@@Z`
- size: `1712`
- prototype: `void __fastcall(struct _EAPTLS_CONTROL_BLOCK *, struct _PPP_EAP_OUTPUT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180052198`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18001e0c0`
- `0x18001fa30`
- `0x180025ff0`
- `0x18005a3a0`
- `0x18005ad10`
- `0x18005b3dc`
- `0x18005dde8`
- `0x180068880`
- `0x180073fa0`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x180026118`
- `ntdll!WinSqmAddToStream` at `0x180026118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800261af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026332`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002638a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800261af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026332`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002638a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026400`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026400`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180026196`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180026196`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002626d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002626d`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18002631b`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180026373`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18002631b`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180026373`

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
    WinSqmAddToStream(0, 7452, 1, &v37);
    v3 = *((_DWORD *)a1 + 1);
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v14 = "successful";
    if ( (v3 & 8) == 0 )
      v14 = "unsuccessful";
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v14);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, LastError);
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v18);
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
        WPP_SF_(*((_QWORD *)v17 + 2), 235, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
        WPP_SF_(*((_QWORD *)v17 + 2), 236, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 240, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, V0Struct);
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
0x180025ff0  push    rbx
0x180025ff2  push    rdi
0x180025ff3  sub     rsp, 48h
0x180025ff7  mov     [rsp+58h+arg_0], rbp
0x180025ffc  mov     rbx, rcx
0x180025fff  mov     ecx, [rcx+4]
0x180026002  mov     rdi, rdx
0x180026005  mov     [rsp+58h+arg_8], rsi
0x18002600a  mov     eax, ecx
0x18002600c  mov     [rsp+58h+arg_10], r13
0x180026011  and     eax, 4008h
0x180026016  mov     [rsp+58h+var_18], r15
0x18002601b  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180026022  lea     r15, WPP_GLOBAL_Control
0x180026029  mov     r13d, 0FFFFFFFFh
0x18002602f  cmp     eax, 8
0x180026032  jnz     loc_180026127
0x180026038  mov     r9, [rbx+220h]
0x18002603f  xorps   xmm0, xmm0
0x180026042  movups  xmmword ptr [rsp+58h+var_38.Data1], xmm0
0x180026047  xor     edx, edx
0x180026049  mov     eax, [r9+0Ch]
0x18002604d  lea     rcx, [rax+rax*2]
0x180026051  mov     rax, rbp
0x180026054  lea     r8, [r9+rcx*8]
0x180026058  nop     dword ptr [rax+rax+00000000h]
0x180026060  cmp     [r8+rax*2+12h], dx
0x180026066  lea     rax, [rax+1]
0x18002606a  jnz     short loc_180026060
0x18002606c  lea     rcx, [r8+12h]
0x180026070  lea     rcx, [rcx+rax*2]
0x180026074  mov     eax, [r9+4]
0x180026078  sub     eax, ecx
0x18002607a  add     eax, r9d
0x18002607d  cmp     eax, 6
0x180026080  jb      short loc_18002609C
0x180026082  mov     eax, 0FEh
0x180026087  cmp     [rcx], ax
0x18002608a  jnz     short loc_18002609C
0x18002608c  movzx   eax, word ptr [rcx+4]
0x180026090  mov     edx, eax
0x180026092  and     edx, 1
0x180026095  test    al, 0Eh
0x180026097  jz      short loc_18002609C
0x180026099  or      edx, 2
0x18002609c  test    byte ptr [r9+8], 1
0x1800260a1  jz      short loc_1800260BB
0x1800260a3  cmp     dword ptr [rbx+304h], 0
0x1800260aa  mov     eax, 14h
0x1800260af  mov     ecx, 4
0x1800260b4  cmovz   eax, ecx
0x1800260b7  or      edx, eax
0x1800260b9  jmp     short loc_1800260C7
0x1800260bb  cmp     cs:?g_UseDefaultSCardCert@@3HA, 0; int g_UseDefaultSCardCert
0x1800260c2  jz      short loc_1800260C7
0x1800260c4  or      edx, 8
0x1800260c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800260ce  mov     esi, edx
0x1800260d0  or      esi, 20h
0x1800260d3  cmp     [rbx+260h], r13d
0x1800260da  cmovz   esi, edx
0x1800260dd  cmp     rcx, r15
0x1800260e0  jz      short loc_1800260FA
0x1800260e2  mov     rcx, [rcx+10h]
0x1800260e6  lea     r8, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x1800260ed  mov     edx, 53h ; 'S'
0x1800260f2  mov     r9d, esi
0x1800260f5  call    WPP_SF_d
0x1800260fa  lea     r9, [rsp+58h+var_38]
0x1800260ff  mov     dword ptr [rsp+58h+var_38.Data4], esi
0x180026103  mov     edx, 1D1Ch
0x180026108  mov     [rsp+58h+var_38.Data1], 1
0x180026110  xor     ecx, ecx
0x180026112  mov     r8d, 1
0x180026118  call    cs:__imp_WinSqmAddToStream
0x18002611f  nop     dword ptr [rax+rax+00h]
0x180026124  mov     ecx, [rbx+4]
0x180026127  mov     rax, cs:WPP_GLOBAL_Control
0x18002612e  cmp     rax, r15
0x180026131  jz      short loc_18002615D
0x180026133  test    cl, 8
0x180026136  lea     r9, aSuccessful; "successful"
0x18002613d  lea     rcx, aUnsuccessful; "unsuccessful"
0x180026144  mov     edx, 0E6h
0x180026149  cmovz   r9, rcx
0x18002614d  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180026154  mov     rcx, [rax+10h]
0x180026158  call    WPP_SF_s
0x18002615d  mov     rax, [rbx+218h]
0x180026164  mov     [rdi+10h], rax
0x180026168  mov     eax, [rbx+2D4h]
0x18002616e  mov     [rdi+8], eax
0x180026171  cmp     qword ptr [rbx+330h], 0
0x180026179  jz      loc_1800262B4
0x18002617f  mov     eax, gs:179Ch
0x180026187  mov     [rsp+58h+arg_18], r14
0x18002618c  test    eax, eax
0x18002618e  jz      short loc_1800261DC
0x180026190  mov     r14d, 1
0x180026196  call    cs:__imp_RevertToSelf
0x18002619d  nop     dword ptr [rax+rax+00h]
0x1800261a2  test    eax, eax
0x1800261a4  jnz     short loc_1800261DF
0x1800261a6  cmp     cs:WPP_GLOBAL_Control, r15
0x1800261ad  jz      short loc_1800261DF
0x1800261af  call    cs:__imp_GetLastError
0x1800261b6  nop     dword ptr [rax+rax+00h]
0x1800261bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261c2  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800261c9  mov     edx, 0E7h
0x1800261ce  mov     r9d, eax
0x1800261d1  mov     rcx, [rcx+10h]
0x1800261d5  call    WPP_SF_d
0x1800261da  jmp     short loc_1800261DF
0x1800261dc  xor     r14d, r14d
0x1800261df  lea     rcx, [rbx+330h]; struct _NgcTicketContext **
0x1800261e6  call    ?FreeApplicationTicket@@YAKPEAPEAU_NgcTicketContext@@@Z; FreeApplicationTicket(_NgcTicketContext * *)
0x1800261eb  test    eax, eax
0x1800261ed  jz      short loc_180026210
0x1800261ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261f6  cmp     rcx, r15
0x1800261f9  jz      short loc_180026217
0x1800261fb  mov     rcx, [rcx+10h]
0x1800261ff  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180026206  mov     edx, 0E8h
0x18002620b  call    WPP_SF_
0x180026210  mov     rcx, cs:WPP_GLOBAL_Control
0x180026217  test    byte ptr [rbx+4], 8
0x18002621b  jnz     short loc_18002625F
0x18002621d  cmp     qword ptr [rbx+320h], 0
0x180026225  jz      short loc_18002625F
0x180026227  lea     rcx, [rbx+320h]; struct _NgcTicketContext **
0x18002622e  call    ?FreeApplicationTicket@@YAKPEAPEAU_NgcTicketContext@@@Z; FreeApplicationTicket(_NgcTicketContext * *)
0x180026233  test    eax, eax
0x180026235  jz      short loc_180026258
0x180026237  mov     rcx, cs:WPP_GLOBAL_Control
0x18002623e  cmp     rcx, r15
0x180026241  jz      short loc_18002625F
0x180026243  mov     rcx, [rcx+10h]
0x180026247  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18002624e  mov     edx, 0E9h
0x180026253  call    WPP_SF_
0x180026258  mov     rcx, cs:WPP_GLOBAL_Control
0x18002625f  test    r14d, r14d
0x180026262  mov     r14, [rsp+58h+arg_18]
0x180026267  jz      short loc_1800262BB
0x180026269  mov     rcx, [rbx+8]; hToken
0x18002626d  call    cs:__imp_ImpersonateLoggedOnUser
0x180026274  nop     dword ptr [rax+rax+00h]
0x180026279  test    eax, eax
0x18002627b  jnz     short loc_1800262B4
0x18002627d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026284  cmp     rcx, r15
0x180026287  jz      short loc_1800262BB
0x180026289  call    cs:__imp_GetLastError
0x180026290  nop     dword ptr [rax+rax+00h]
0x180026295  mov     rcx, cs:WPP_GLOBAL_Control
0x18002629c  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800262a3  mov     edx, 0EAh
0x1800262a8  mov     r9d, eax
0x1800262ab  mov     rcx, [rcx+10h]
0x1800262af  call    WPP_SF_d
0x1800262b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262bb  mov     edx, [rbx+4]
0x1800262be  mov     eax, edx
0x1800262c0  and     eax, 44000h
0x1800262c5  cmp     eax, 40000h
0x1800262ca  jnz     loc_1800264E2
0x1800262d0  cmp     cs:hObject, 0
0x1800262d8  movaps  [rsp+58h+var_28], xmm6
0x1800262dd  jz      loc_1800263D3
0x1800262e3  cmp     rcx, r15
0x1800262e6  jz      short loc_1800262FD
0x1800262e8  mov     rcx, [rcx+10h]
0x1800262ec  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800262f3  mov     edx, 0EBh
0x1800262f8  call    WPP_SF_
0x1800262fd  call    ?WaitForThread@CWorkerThreadState@@QEAAKXZ; CWorkerThreadState::WaitForThread(void)
0x180026302  test    byte ptr [rbx+4], 8
0x180026306  jnz     loc_180026464
0x18002630c  xor     r8d, r8d; Flags
0x18002630f  lea     rcx, TargetName; "*Session"
0x180026316  mov     edx, 2; Type
0x18002631b  call    cs:__imp_CredDeleteW
0x180026322  nop     dword ptr [rax+rax+00h]
0x180026327  test    eax, eax
0x180026329  jnz     short loc_180026347
0x18002632b  movups  xmm6, xmmword ptr [rbx+30Ch]
0x180026332  call    cs:__imp_GetLastError
0x180026339  nop     dword ptr [rax+rax+00h]
0x18002633e  mov     edx, eax
0x180026340  movaps  xmmword ptr [rsp+58h+var_38.Data1], xmm6
0x180026345  jmp     short loc_180026355
0x180026347  movups  xmm0, xmmword ptr [rbx+30Ch]
0x18002634e  xor     edx, edx; unsigned int
0x180026350  movaps  xmmword ptr [rsp+58h+var_38.Data1], xmm0
0x180026355  lea     r8, [rsp+58h+var_38]; struct _GUID
0x18002635a  mov     ecx, 2; unsigned int
0x18002635f  call    ?WriteCredentialUnPlumbingEvent@@YAXKKU_GUID@@@Z; WriteCredentialUnPlumbingEvent(ulong,ulong,_GUID)
0x180026364  xor     r8d, r8d; Flags
0x180026367  lea     rcx, TargetName; "*Session"
0x18002636e  mov     edx, 3; Type
0x180026373  call    cs:__imp_CredDeleteW
0x18002637a  nop     dword ptr [rax+rax+00h]
0x18002637f  test    eax, eax
0x180026381  jnz     short loc_1800263B1
0x180026383  movups  xmm6, xmmword ptr [rbx+30Ch]
0x18002638a  call    cs:__imp_GetLastError
0x180026391  nop     dword ptr [rax+rax+00h]
0x180026396  lea     r8, [rsp+58h+var_38]; struct _GUID
0x18002639b  movaps  xmmword ptr [rsp+58h+var_38.Data1], xmm6
0x1800263a0  mov     edx, eax; unsigned int
0x1800263a2  mov     ecx, 3; unsigned int
0x1800263a7  call    ?WriteCredentialUnPlumbingEvent@@YAXKKU_GUID@@@Z; WriteCredentialUnPlumbingEvent(ulong,ulong,_GUID)
0x1800263ac  jmp     loc_180026464
0x1800263b1  movups  xmm0, xmmword ptr [rbx+30Ch]
0x1800263b8  lea     r8, [rsp+58h+var_38]; struct _GUID
0x1800263bd  xor     edx, edx; unsigned int
0x1800263bf  mov     ecx, 3; unsigned int
0x1800263c4  movaps  xmmword ptr [rsp+58h+var_38.Data1], xmm0
0x1800263c9  call    ?WriteCredentialUnPlumbingEvent@@YAXKKU_GUID@@@Z; WriteCredentialUnPlumbingEvent(ulong,ulong,_GUID)
0x1800263ce  jmp     loc_180026464
0x1800263d3  test    dl, 8
0x1800263d6  jz      loc_180026464
0x1800263dc  cmp     rcx, r15
0x1800263df  jz      short loc_1800263F6
0x1800263e1  mov     rcx, [rcx+10h]
0x1800263e5  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800263ec  mov     edx, 0ECh
0x1800263f1  call    WPP_SF_
0x1800263f6  mov     edx, 28h ; '('; uBytes
0x1800263fb  mov     ecx, 40h ; '@'; uFlags
0x180026400  call    cs:__imp_LocalAlloc
0x180026407  nop     dword ptr [rax+rax+00h]
0x18002640c  mov     rcx, rax; Parameter
0x18002640f  test    rax, rax
0x180026412  jnz     short loc_180026437
0x180026414  mov     rcx, cs:WPP_GLOBAL_Control
0x18002641b  cmp     rcx, r15
0x18002641e  jz      short loc_180026464
0x180026420  mov     rcx, [rcx+10h]
0x180026424  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18002642b  mov     edx, 0EDh
0x180026430  call    WPP_SF_
0x180026435  jmp     short loc_180026464
0x180026437  mov     rax, [rbx+8]
0x18002643b  mov     [rcx], rax
0x18002643e  mov     rax, [rbx+238h]
0x180026445  mov     [rcx+8], rax
0x180026449  mov     rax, [rbx+220h]
0x180026450  mov     [rcx+10h], rax
0x180026454  movups  xmm0, xmmword ptr [rbx+30Ch]
0x18002645b  movups  xmmword ptr [rcx+18h], xmm0
0x18002645f  call    ?SaveCertCredsThread@@YAKPEAX@Z; SaveCertCredsThread(void *)
0x180026464  mov     rcx, [rbx+238h]
0x18002646b  xor     eax, eax
0x18002646d  movaps  xmm6, [rsp+58h+var_28]
0x180026472  mov     [rcx+40h], ax
0x180026476  mov     rcx, [rbx+238h]
0x18002647d  mov     [rcx+42h], ax
0x180026481  xor     ecx, ecx
0x180026483  mov     rdx, [rbx+238h]
0x18002648a  mov     r8d, [rdx+8]
0x18002648e  cmp     r8d, 48h ; 'H'
0x180026492  jbe     short loc_1800264BA
0x180026494  mov     rax, [rdx+28h]
0x180026498  nop     dword ptr [rax+rax+00000000h]
0x1800264a0  cmp     [rax+rbp*2+2], cx
0x1800264a5  lea     rbp, [rbp+1]
0x1800264a9  jnz     short loc_1800264A0
0x1800264ab  lea     eax, ds:0[rbp*2]
0x1800264b2  mov     ecx, r8d
0x1800264b5  sub     ecx, eax
0x1800264b7  sub     ecx, 4Ah ; 'J'
0x1800264ba  mov     rax, [rdx+38h]
0x1800264be  test    rcx, rcx
0x1800264c1  jz      short loc_1800264D0
0x1800264c3  mov     byte ptr [rax], 0
0x1800264c6  lea     rax, [rax+1]
0x1800264ca  sub     rcx, 1
0x1800264ce  jnz     short loc_1800264C3
0x1800264d0  mov     rax, [rbx+238h]
0x1800264d7  and     dword ptr [rax+0Ch], 0FFFFFFFBh
0x1800264db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800264e2  test    byte ptr [rbx+4], 2
0x1800264e6  mov     rbp, [rsp+58h+arg_0]
0x1800264eb  jnz     short loc_1800264FB
0x1800264ed  mov     dword ptr [rdi+3Ch], 1
0x1800264f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800264fb  test    byte ptr [rbx+4], 8
0x1800264ff  jz      loc_18002662D
0x180026505  mov     rdx, [rbx+238h]
0x18002650c  test    rdx, rdx
0x18002650f  jz      loc_18002662D
0x180026515  mov     r9, [rdx+28h]
0x180026519  test    r9, r9
0x18002651c  jz      short loc_180026536
0x18002651e  cmp     r9, r13
0x180026521  jz      short loc_180026536
0x180026523  movzx   eax, word ptr [r9]
  ... truncated ...
```
