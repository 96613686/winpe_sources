# FsmThisLayerUp

- ea: `0x18000ecac`
- end: `0x18000f77a`
- name: `FsmThisLayerUp`
- size: `2766`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `6`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800023c0`
- `0x18000442c`
- `0x180009fd0`
- `0x18000a4c0`
- `0x18000cc7c`
- `0x180015100`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180001e0c`
- `0x180003170`
- `0x1800031f4`
- `0x1800036f8`
- `0x18000423c`
- `0x18000be68`
- `0x18000dfac`
- `0x18000ecac`
- `0x18000f984`
- `0x18000fc50`
- `0x18000fec0`
- `0x18000ff7c`
- `0x180011230`
- `0x1800115d0`
- `0x180012104`
- `0x180012d54`
- `0x18001348c`
- `0x1800139cc`
- `0x180013b54`
- `0x180013c48`
- `0x180013cf4`
- `0x1800140a4`
- `0x18001427c`
- `0x180014724`
- `0x180014808`
- `0x180014bfc`
- `0x18001ab0c`
- `0x18002b0dc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f301`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f301`
- `rtutils!RouterLogEventA` at `0x18000f1e1`
- `rtutils!RouterLogEventA` at `0x18000f1e1`

## string_xrefs

- `0x18000ed4c`: `FsmThisLayerUp called for protocol = %x, port = %d`
- `0x18000edd4`: `FsmThisLayerUp for protocol=%x,port=%d,RetCode=%d`
- `0x18000f214`: `LCP Configured successfully`
- `0x18000f26a`: `Client: LCP Configured successfully for Guid %hs`

## pseudocode

```c
__int64 __fastcall FsmThisLayerUp(__int64 a1, unsigned int a2)
{
  __int64 v2; // r12
  __int64 PointerToCPCB; // rax
  __int64 v5; // r15
  __int64 v6; // r9
  __int64 v7; // r14
  __int64 (__fastcall *v8)(_QWORD); // rax
  int v9; // eax
  int v10; // esi
  __int64 v11; // r9
  int v12; // r8d
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  __int64 v16; // rsi
  int v17; // ecx
  int v18; // ecx
  _DWORD *v19; // rax
  int v20; // ecx
  const wchar_t *v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  _DWORD *v26; // rsi
  int v27; // edx
  _DWORD *v28; // rcx
  _DWORD *v29; // rax
  DWORD LastError; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  int v34; // eax
  unsigned int v35; // esi
  __int64 v36; // rax
  int BundleNCPState; // eax
  int v38; // eax
  int v39; // eax
  __int64 v40; // r8
  unsigned int v41; // edx
  unsigned int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // ecx
  int v46; // ecx
  unsigned int CpIndexFromProtocol; // eax
  int v48; // ecx
  unsigned int v49; // eax
  _DWORD v50[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v51[864]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v52; // [rsp+3A0h] [rbp+2A0h]
  unsigned int v53[56]; // [rsp+3E0h] [rbp+2E0h] BYREF
  LPSTR plpszSubStringArray[2]; // [rsp+4C0h] [rbp+3C0h] BYREF
  __int128 v55; // [rsp+4D0h] [rbp+3D0h]
  int v56; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v57[2044]; // [rsp+4E4h] [rbp+3E4h] BYREF

  v2 = a2;
  memset_0(v53, 0, sizeof(v53));
  v50[0] = 0;
  PointerToCPCB = GetPointerToCPCB(a1, (unsigned int)v2);
  v56 = 0;
  v5 = PointerToCPCB;
  memset_0(v57, 0, sizeof(v57));
  if ( v5 )
  {
    if ( (byte_18004DF34 & 1) != 0 )
    {
      v6 = *(_QWORD *)(a1 + 16);
      LOWORD(v56) = 0;
      FormatRRASErrorString(
        (wchar_t *)&v56,
        L"FsmThisLayerUp called for protocol = %x, port = %d",
        *((unsigned int *)CpTable + 44 * v2),
        v6);
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v56);
    }
    v7 = 176 * v2;
    v8 = (__int64 (__fastcall *)(_QWORD))*((_QWORD *)CpTable + 22 * v2 + 9);
    if ( v8 )
    {
      v9 = v8(*(_QWORD *)(v5 + 16));
      v10 = v9;
      if ( v9 )
      {
        if ( byte_18004DF33 < 0 )
        {
          v11 = *(_QWORD *)(a1 + 16);
          LOWORD(v56) = 0;
          FormatRRASErrorString(
            (wchar_t *)&v56,
            L"FsmThisLayerUp for protocol=%x,port=%d,RetCode=%d",
            *(unsigned int *)((char *)CpTable + v7),
            v11,
            v9);
          if ( byte_18004DF33 < 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v56);
        }
        if ( v10 != 600 )
        {
          *(_DWORD *)(v5 + 40) = v10;
          FsmClose(a1, (unsigned int)v2);
        }
        return 0;
      }
    }
    if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
    {
      v12 = *(_DWORD *)((char *)CpTable + v7);
      if ( v12 == 32855 || v12 == 32801 )
        RemoveFromTimerQ(*(_DWORD *)(a1 + 64), *(_DWORD *)(v5 + 8), v12, 0, 8);
    }
  }
  else if ( (byte_18004DF34 & 1) != 0 )
  {
    v22 = *(_QWORD *)(a1 + 16);
    LOWORD(v56) = 0;
    FormatRRASErrorString((wchar_t *)&v56, L"FsmThisLayerUp called in no auth case, port = %d", v22);
    if ( (byte_18004DF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v56);
  }
  v13 = *(_DWORD *)(a1 + 48);
  if ( !v13 )
  {
    if ( (byte_18004DF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasPppTraceInfo,
        L"LCP Configured successfully");
    if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
    {
      AdjustHTokenImpersonateUser(a1);
      if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
      {
        FsmSendIdentification(a1, 1);
        FsmSendIdentification(a1, 2);
        if ( (byte_18004DF34 & 1) != 0 )
        {
          LOWORD(v56) = 0;
          FormatRRASErrorString((wchar_t *)&v56, L"Client: LCP Configured successfully for Guid %hs", a1 + 1712);
          if ( (byte_18004DF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v56);
        }
        FsmSendIdentification(a1, 4);
      }
    }
    v26 = *(_DWORD **)(a1 + 1472);
    if ( v26[305] || v26[355] )
    {
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasPppTraceInfo,
          L"Authenticating phase started");
      *(_DWORD *)(a1 + 48) = 1;
      v46 = v26[305];
      if ( v46 )
      {
        CpIndexFromProtocol = GetCpIndexFromProtocol(v46);
        ApStart(a1, CpIndexFromProtocol, 1);
      }
      v48 = v26[355];
      if ( v48 )
      {
        v49 = GetCpIndexFromProtocol(v48);
        ApStart(a1, v49, 0);
      }
      return 1;
    }
    v27 = v26[6];
    if ( (*(_BYTE *)(a1 + 56) & 4) != 0 && (v27 & 0x4000) == 0 && (v27 & 0x400000) == 0 )
    {
      v28 = *(_DWORD **)(a1 + 152);
      *(_DWORD *)(a1 + 48) = 1;
      v29 = RasAuthAttributeCopy(v28);
      if ( v29 )
      {
        LastError = RasAuthenticateClient(*(_QWORD *)(a1 + 16), v29);
        if ( !LastError )
          return 1;
      }
      else
      {
        LastError = GetLastError();
      }
      goto LABEL_76;
    }
    if ( (byte_18004DF34 & 1) != 0 )
    {
      LOWORD(v56) = 0;
      FormatRRASErrorString((wchar_t *)&v56, L"No Auth. Moving onto NCP. Guid %hs", a1 + 1712);
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v56);
    }
    if ( (v26[6] & 0x4000) != 0 && *(_WORD *)(a1 + 60) == 14 )
      SetNoMppeKeys(*(_QWORD *)(a1 + 16));
    goto LABEL_88;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
LABEL_88:
    if ( *(_DWORD *)(a1 + 1372) && *(_DWORD *)(a1 + 1328) != 9 || *(_DWORD *)(a1 + 1436) && *(_DWORD *)(a1 + 1392) != 9 )
      return 1;
    NotifyCaller(a1, 0x16u, 0);
    if ( (*(_BYTE *)(a1 + 56) & 4) != 0 && (byte_18004DF34 & 1) != 0 )
    {
      LOWORD(v56) = 0;
      FormatRRASErrorString((wchar_t *)&v56, L"Server: Authentication successful for Guid %hs", a1 + 1712);
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v56);
    }
    v34 = *(_DWORD *)(a1 + 56);
    if ( (v34 & 0x10) != 0 )
    {
      v35 = GetCpIndexFromProtocol(49193);
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasPppTraceInfo,
          L"Callback phase started");
      *(_DWORD *)(a1 + 48) = 2;
      v36 = GetPointerToCPCB(a1, v35);
      if ( !v36 )
        return 0;
      *(_DWORD *)(v36 + 44) = 1;
      CbStart(a1, v35);
      return 1;
    }
    if ( (v34 & 0xC) == 4 && (*(_BYTE *)(a1 + 112) & 2) != 0 )
    {
      *(_DWORD *)(a1 + 1496) = 649;
      NotifyCallerOfFailure(a1, 649);
      *(_DWORD *)(a1 + 56) |= 0x2000u;
      return 1;
    }
LABEL_104:
    if ( (*(_BYTE *)(a1 + 56) & 0x10) != 0 && *((_DWORD *)CpTable + 44 * v2) != 49193 )
      return 1;
    if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
      NotifyCaller(a1, 3u, 0);
    if ( (*(_DWORD *)(a1 + 56) & 3) != 1 || (LastError = TryToBundleWithAnotherLink(a1)) == 0 )
    {
      if ( (*(_BYTE *)(a1 + 56) & 2) != 0 )
      {
        BundleNCPState = QueryBundleNCPState(a1);
        if ( BundleNCPState )
        {
          v38 = BundleNCPState - 1;
          if ( v38 )
          {
            v39 = v38 - 1;
            if ( !v39 )
            {
              *(_DWORD *)(a1 + 48) = 3;
              NotifyCaller(a1, 0x18u, 0);
              NotifyCallerOfBundledProjection(a1);
              RemoveFromTimerQ(*(_DWORD *)(a1 + 64), 0, 0, 0, 3);
              StartAutoDisconnectForPort(a1);
              StartLCPEchoForPort(a1);
LABEL_61:
              MakeStartAccountingCall(a1);
              return 1;
            }
            if ( v39 != 1 )
              return 1;
            v31 = 720;
            *(_DWORD *)(a1 + 48) = 3;
            *(_DWORD *)(a1 + 1496) = 720;
            goto LABEL_77;
          }
          *(_DWORD *)(a1 + 48) = 3;
          if ( (byte_18004DF34 & 1) != 0 )
          {
            v40 = *(_QWORD *)(a1 + 16);
            LOWORD(v56) = 0;
            FormatRRASErrorString((wchar_t *)&v56, L"Bundle NCPs not done for port %d, wait", v40);
            if ( (byte_18004DF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v56);
          }
          v41 = 24;
LABEL_143:
          NotifyCaller(a1, v41, 0);
          return 1;
        }
LABEL_142:
        v41 = 25;
        goto LABEL_143;
      }
      if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
      {
        v42 = InitializeNCPs(a1, *(_DWORD *)(a1 + 184));
        v32 = a1;
        if ( !v42 )
        {
          StartNegotiatingNCPs(a1);
          return 1;
        }
        *(_DWORD *)(a1 + 1496) = v42;
        v31 = v42;
        goto LABEL_78;
      }
      if ( (dword_18004D9EC & 1) == 0 || *(char *)(*(_QWORD *)(a1 + 8) + 52LL) < 0 )
        goto LABEL_142;
      v43 = *(_DWORD *)(a1 + 60);
      if ( (v43 & 0x10000) != 0 && (dword_18004D9EC & 4) != 0 )
        goto LABEL_134;
      v44 = v43 & 0x20000;
      if ( v44 )
      {
        if ( (dword_18004D9EC & 2) != 0 )
          goto LABEL_134;
      }
      if ( (*(_DWORD *)(a1 + 60) & 0x10000) != 0 )
      {
        v45 = dword_18004D9EC | 4;
      }
      else if ( v44 )
      {
        v45 = dword_18004D9EC | 2;
      }
      else
      {
        if ( (dword_18004D9EC & 8) != 0 )
        {
LABEL_134:
          *(_DWORD *)(a1 + 1496) = 937;
          if ( (byte_18004DF34 & 1) != 0 )
          {
            LOWORD(v56) = 0;
            FormatRRASErrorString((wchar_t *)&v56, L"User limit reached. Flags: %d", (unsigned int)dword_18004D9EC);
            if ( (byte_18004DF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v56);
          }
          v31 = *(unsigned int *)(a1 + 1496);
          goto LABEL_77;
        }
        v45 = dword_18004D9EC | 8;
      }
      dword_18004D9EC = v45;
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x80u;
      goto LABEL_142;
    }
LABEL_76:
    *(_DWORD *)(a1 + 1496) = LastError;
    v31 = LastError;
LABEL_77:
    v32 = a1;
LABEL_78:
    NotifyCallerOfFailure(v32, v31);
    return 0;
  }
  v15 = v14 - 1;
  if ( !v15 )
    goto LABEL_104;
  if ( v15 != 1 )
    return 1;
  v16 = *(_QWORD *)(a1 + 1472);
  v17 = *(_DWORD *)(v16 + 1420);
  if ( v17 )
  {
    if ( (_DWORD)v2 == (unsigned int)GetCpIndexFromProtocol(v17) )
      return 1;
  }
  v18 = *(_DWORD *)(v16 + 1220);
  if ( v18 )
  {
    if ( (_DWORD)v2 == (unsigned int)GetCpIndexFromProtocol(v18) )
      return 1;
  }
  if ( !v5 )
    return 0;
  v19 = CpTable;
  *(_DWORD *)(v5 + 56) = 2;
  if ( v19[44 * v2] == 32801 && !(unsigned int)NotifyIPCPOfProjection(a1) )
    return 0;
  v20 = *((_DWORD *)CpTable + 44 * v2);
  if ( (*(_BYTE *)(a1 + 56) & 4) != 0 )
  {
    if ( v20 == 32801 )
    {
      if ( (byte_18004DF34 & 1) == 0 )
        goto LABEL_42;
      v21 = L"Server: Ipv4 successful for Guid %hs";
    }
    else
    {
      if ( v20 != 32855 || (byte_18004DF34 & 1) == 0 )
        goto LABEL_42;
      v21 = L"Server: IPv6 successful for Guid %hs";
    }
  }
  else if ( v20 == 32801 )
  {
    if ( (byte_18004DF34 & 1) == 0 )
      goto LABEL_42;
    v21 = L"Client: Ipv4 successful for Guid %hs";
  }
  else
  {
    if ( v20 != 32855 || (byte_18004DF34 & 1) == 0 )
      goto LABEL_42;
    v21 = L"Client: IPv6 successful for Guid %hs";
  }
  LOWORD(v56) = 0;
  FormatRRASErrorString((wchar_t *)&v56, v21, a1 + 1712);
  if ( (byte_18004DF34 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v56);
LABEL_42:
  if ( (unsigned int)AreNCPsDone(a1, (unsigned int)v2, v53, v50) )
    return 0;
  if ( v50[0] == 1 )
  {
    RemoveFromTimerQ(*(_DWORD *)(a1 + 64), 0, 0, 0, 3);
    if ( (*(_BYTE *)(a1 + 56) & 4) != 0 )
    {
      NotifyCaller(a1, 0x13u, v53);
LABEL_54:
      StartAutoDisconnectForPort(a1);
      StartLCPEchoForPort(a1);
      v24 = *(_DWORD *)(a1 + 56);
      if ( (v24 & 4) == 0 && (v24 & 0x400) == 0 )
      {
        v25 = *(_QWORD *)(a1 + 8);
        plpszSubStringArray[0] = (LPSTR)(a1 + 1712);
        v55 = 0;
        plpszSubStringArray[1] = (LPSTR)(v25 + 489);
        *(_QWORD *)&v55 = *(_QWORD *)(v25 + 160);
        *((_QWORD *)&v55 + 1) = a1 + 1665;
        if ( (unsigned int)dword_18004DA20 > 2 )
          RouterLogEventA(hLogHandle, 4u, 0x4F2Bu, 4u, plpszSubStringArray, 0);
        *(_DWORD *)(a1 + 56) |= 0x400u;
        v24 = *(_DWORD *)(a1 + 56);
      }
      if ( (v24 & 2) != 0 )
        NotifyCompletionOnBundledPorts(a1);
      goto LABEL_61;
    }
    memset_0(v51, 0, 0x398u);
    if ( (*(_DWORD *)(a1 + 56) & 0x80000) == 0 || (unsigned int)AreAnyNCPsActive(v23, v53) )
    {
      NotifyCaller(a1, 4u, v53);
      *(_DWORD *)(a1 + 56) |= 0x80000u;
      NotifyCaller(a1, 0, 0);
      if ( !(*((unsigned int (__fastcall **)(_QWORD, _QWORD, _BYTE *))&xmmword_18004D470 + 1))(
              0,
              *(_QWORD *)(a1 + 16),
              v51) )
        (*((void (__fastcall **)(__int64, __int64, unsigned int *, __int64))&xmmword_18004D410 + 1))(v52, 1, v53, 224);
      goto LABEL_54;
    }
    *(_DWORD *)(a1 + 1496) = 720;
    NotifyCallerOfFailure(a1, 720);
    NotifyCaller(a1, 0xAu, (unsigned int *)(a1 + 1496));
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000ecac  mov     [rsp-8+arg_10], rbx
0x18000ecb1  mov     [rsp-8+arg_18], rsi
0x18000ecb6  push    rbp
0x18000ecb7  push    rdi
0x18000ecb8  push    r12
0x18000ecba  push    r14
0x18000ecbc  push    r15
0x18000ecbe  lea     rbp, [rsp-0BF0h]
0x18000ecc6  sub     rsp, 0CF0h
0x18000eccd  mov     rax, cs:__security_cookie
0x18000ecd4  xor     rax, rsp
0x18000ecd7  mov     [rbp+0C10h+var_30], rax
0x18000ecde  mov     r12d, edx
0x18000ece1  mov     rdi, rcx
0x18000ece4  xor     edx, edx; Val
0x18000ece6  lea     rcx, [rbp+0C10h+var_930]; void *
0x18000eced  mov     r8d, 0E0h; Size
0x18000ecf3  call    memset_0
0x18000ecf8  mov     edx, r12d
0x18000ecfb  mov     [rsp+0D10h+var_CE0], 0
0x18000ed03  mov     rcx, rdi
0x18000ed06  call    GetPointerToCPCB
0x18000ed0b  xor     ecx, ecx
0x18000ed0d  xor     edx, edx; Val
0x18000ed0f  mov     [rbp+0C10h+var_830], ecx
0x18000ed15  mov     r8d, 7FCh; Size
0x18000ed1b  lea     rcx, [rbp+0C10h+var_82C]; void *
0x18000ed22  mov     r15, rax
0x18000ed25  call    memset_0
0x18000ed2a  mov     r14d, 4
0x18000ed30  lea     ebx, [r14-3]
0x18000ed34  test    r15, r15
0x18000ed37  jz      loc_18000EF4A
0x18000ed3d  test    cs:byte_18004DF34, bl
0x18000ed43  jz      short loc_18000ED99
0x18000ed45  mov     r8, cs:CpTable
0x18000ed4c  lea     rdx, aFsmthislayerup; "FsmThisLayerUp called for protocol = %x"...
0x18000ed53  mov     r9, [rdi+10h]
0x18000ed57  xor     eax, eax
0x18000ed59  imul    rcx, r12, 0B0h
0x18000ed60  mov     word ptr [rbp+0C10h+var_830], ax
0x18000ed67  mov     r8d, [rcx+r8]
0x18000ed6b  lea     rcx, [rbp+0C10h+var_830]
0x18000ed72  call    FormatRRASErrorString
0x18000ed77  test    cs:byte_18004DF34, bl
0x18000ed7d  jz      short loc_18000ED99
0x18000ed7f  lea     r8, [rbp+0C10h+var_830]
0x18000ed86  lea     rdx, RasPppTraceInfo
0x18000ed8d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ed94  call    McTemplateU0z_EventWriteTransfer
0x18000ed99  mov     rax, cs:CpTable
0x18000eda0  imul    r14, r12, 0B0h
0x18000eda7  mov     rax, [r14+rax+48h]
0x18000edac  test    rax, rax
0x18000edaf  jz      loc_18000EE3F
0x18000edb5  mov     rcx, [r15+10h]
0x18000edb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edbe  mov     esi, eax
0x18000edc0  test    eax, eax
0x18000edc2  jz      short loc_18000EE3F
0x18000edc4  cmp     cs:byte_18004DF33, 0
0x18000edcb  jge     short loc_18000EE1F
0x18000edcd  mov     r8, cs:CpTable
0x18000edd4  lea     rdx, aFsmthislayerup_1; "FsmThisLayerUp for protocol=%x,port=%d,"...
0x18000eddb  mov     r9, [rdi+10h]
0x18000eddf  xor     ecx, ecx
0x18000ede1  mov     word ptr [rbp+0C10h+var_830], cx
0x18000ede8  lea     rcx, [rbp+0C10h+var_830]
0x18000edef  mov     dword ptr [rsp+0D10h+plpszSubStringArray], eax
0x18000edf3  mov     r8d, [r14+r8]
0x18000edf7  call    FormatRRASErrorString
0x18000edfc  cmp     cs:byte_18004DF33, 0
0x18000ee03  jge     short loc_18000EE1F
0x18000ee05  lea     r8, [rbp+0C10h+var_830]
0x18000ee0c  lea     rdx, RasPppTraceError
0x18000ee13  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ee1a  call    McTemplateU0z_EventWriteTransfer
0x18000ee1f  cmp     esi, 258h
0x18000ee25  jz      loc_18000F31D
0x18000ee2b  mov     edx, r12d
0x18000ee2e  mov     [r15+28h], esi
0x18000ee32  mov     rcx, rdi
0x18000ee35  call    FsmClose
0x18000ee3a  jmp     loc_18000F31D
0x18000ee3f  test    byte ptr [rdi+38h], 4
0x18000ee43  jnz     short loc_18000EE79
0x18000ee45  mov     rax, cs:CpTable
0x18000ee4c  mov     r8d, [r14+rax]
0x18000ee50  cmp     r8d, 8057h
0x18000ee57  jz      short loc_18000EE62
0x18000ee59  cmp     r8d, 8021h
0x18000ee60  jnz     short loc_18000EE79
0x18000ee62  mov     edx, [r15+8]
0x18000ee66  xor     r9d, r9d
0x18000ee69  mov     ecx, [rdi+40h]
0x18000ee6c  mov     dword ptr [rsp+0D10h+plpszSubStringArray], 8
0x18000ee74  call    RemoveFromTimerQ
0x18000ee79  mov     r14d, 4
0x18000ee7f  mov     ecx, [rdi+30h]
0x18000ee82  test    ecx, ecx
0x18000ee84  jz      loc_18000F20C
0x18000ee8a  sub     ecx, 1
0x18000ee8d  jz      loc_18000F3A0
0x18000ee93  sub     ecx, 1
0x18000ee96  jz      loc_18000F4B9
0x18000ee9c  cmp     ecx, 1
0x18000ee9f  jnz     loc_18000F74C
0x18000eea5  mov     rsi, [rdi+5C0h]
0x18000eeac  mov     ecx, [rsi+58Ch]
0x18000eeb2  test    ecx, ecx
0x18000eeb4  jz      short loc_18000EEC4
0x18000eeb6  call    GetCpIndexFromProtocol
0x18000eebb  cmp     r12d, eax
0x18000eebe  jz      loc_18000F74C
0x18000eec4  mov     ecx, [rsi+4C4h]
0x18000eeca  test    ecx, ecx
0x18000eecc  jz      short loc_18000EEDC
0x18000eece  call    GetCpIndexFromProtocol
0x18000eed3  cmp     r12d, eax
0x18000eed6  jz      loc_18000F74C
0x18000eedc  test    r15, r15
0x18000eedf  jz      loc_18000F31D
0x18000eee5  mov     rax, cs:CpTable
0x18000eeec  mov     edx, 8021h
0x18000eef1  imul    rsi, r12, 0B0h
0x18000eef8  mov     dword ptr [r15+38h], 2
0x18000ef00  cmp     [rsi+rax], edx
0x18000ef03  jnz     short loc_18000EF1A
0x18000ef05  mov     rcx, rdi
0x18000ef08  call    NotifyIPCPOfProjection
0x18000ef0d  test    eax, eax
0x18000ef0f  jz      loc_18000F31D
0x18000ef15  mov     edx, 8021h
0x18000ef1a  mov     rax, cs:CpTable
0x18000ef21  mov     ecx, [rsi+rax]
0x18000ef24  test    [rdi+38h], r14b
0x18000ef28  jz      loc_18000EFBA
0x18000ef2e  cmp     ecx, edx
0x18000ef30  jnz     short loc_18000EFA1
0x18000ef32  test    cs:byte_18004DF34, bl
0x18000ef38  jz      loc_18000F00F
0x18000ef3e  lea     rdx, aServerIpv4Succ; "Server: Ipv4 successful for Guid %hs"
0x18000ef45  jmp     loc_18000EFD1
0x18000ef4a  test    cs:byte_18004DF34, bl
0x18000ef50  jz      loc_18000EE7F
0x18000ef56  mov     r8, [rdi+10h]
0x18000ef5a  lea     rdx, aFsmthislayerup_0; "FsmThisLayerUp called in no auth case, "...
0x18000ef61  xor     eax, eax
0x18000ef63  lea     rcx, [rbp+0C10h+var_830]
0x18000ef6a  mov     word ptr [rbp+0C10h+var_830], ax
0x18000ef71  call    FormatRRASErrorString
0x18000ef76  test    cs:byte_18004DF34, bl
0x18000ef7c  jz      loc_18000EE7F
0x18000ef82  lea     r8, [rbp+0C10h+var_830]
0x18000ef89  lea     rdx, RasPppTraceInfo
0x18000ef90  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ef97  call    McTemplateU0z_EventWriteTransfer
0x18000ef9c  jmp     loc_18000EE7F
0x18000efa1  cmp     ecx, 8057h
0x18000efa7  jnz     short loc_18000F00F
0x18000efa9  test    cs:byte_18004DF34, bl
0x18000efaf  jz      short loc_18000F00F
0x18000efb1  lea     rdx, aServerIpv6Succ; "Server: IPv6 successful for Guid %hs"
0x18000efb8  jmp     short loc_18000EFD1
0x18000efba  cmp     ecx, edx
0x18000efbc  jnz     loc_18000F06F
0x18000efc2  test    cs:byte_18004DF34, bl
0x18000efc8  jz      short loc_18000F00F
0x18000efca  lea     rdx, aClientIpv4Succ; "Client: Ipv4 successful for Guid %hs"
0x18000efd1  xor     eax, eax
0x18000efd3  lea     r8, [rdi+6B0h]
0x18000efda  lea     rcx, [rbp+0C10h+var_830]
0x18000efe1  mov     word ptr [rbp+0C10h+var_830], ax
0x18000efe8  call    FormatRRASErrorString
0x18000efed  test    cs:byte_18004DF34, bl
0x18000eff3  jz      short loc_18000F00F
0x18000eff5  lea     r8, [rbp+0C10h+var_830]
0x18000effc  lea     rdx, RasPppTraceInfo
0x18000f003  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f00a  call    McTemplateU0z_EventWriteTransfer
0x18000f00f  lea     r9, [rsp+0D10h+var_CE0]
0x18000f014  mov     edx, r12d
0x18000f017  lea     r8, [rbp+0C10h+var_930]
0x18000f01e  mov     rcx, rdi
0x18000f021  call    AreNCPsDone
0x18000f026  test    eax, eax
0x18000f028  jnz     loc_18000F31D
0x18000f02e  cmp     [rsp+0D10h+var_CE0], ebx
0x18000f032  jnz     loc_18000F74C
0x18000f038  mov     ecx, [rdi+40h]
0x18000f03b  xor     r9d, r9d
0x18000f03e  xor     r8d, r8d
0x18000f041  mov     dword ptr [rsp+0D10h+plpszSubStringArray], 3
0x18000f049  xor     edx, edx
0x18000f04b  call    RemoveFromTimerQ
0x18000f050  test    [rdi+38h], r14b
0x18000f054  jz      short loc_18000F08B
0x18000f056  lea     r8, [rbp+0C10h+var_930]
0x18000f05d  mov     edx, 13h
0x18000f062  mov     rcx, rdi
0x18000f065  call    NotifyCaller
0x18000f06a  jmp     loc_18000F141
0x18000f06f  cmp     ecx, 8057h
0x18000f075  jnz     short loc_18000F00F
0x18000f077  test    cs:byte_18004DF34, bl
0x18000f07d  jz      short loc_18000F00F
0x18000f07f  lea     rdx, aClientIpv6Succ; "Client: IPv6 successful for Guid %hs"
0x18000f086  jmp     loc_18000EFD1
0x18000f08b  xor     edx, edx; Val
0x18000f08d  lea     rcx, [rsp+0D10h+var_CD0]; void *
0x18000f092  mov     r8d, 398h; Size
0x18000f098  call    memset_0
0x18000f09d  mov     esi, 80000h
0x18000f0a2  test    [rdi+38h], esi
0x18000f0a5  jz      short loc_18000F0E2
0x18000f0a7  lea     rdx, [rbp+0C10h+var_930]
0x18000f0ae  call    AreAnyNCPsActive
0x18000f0b3  test    eax, eax
0x18000f0b5  jnz     short loc_18000F0E2
0x18000f0b7  mov     edx, 2D0h
0x18000f0bc  lea     rbx, [rdi+5D8h]
0x18000f0c3  mov     rcx, rdi
0x18000f0c6  mov     [rbx], edx
0x18000f0c8  call    NotifyCallerOfFailure
0x18000f0cd  mov     r8, rbx
0x18000f0d0  mov     edx, 0Ah
0x18000f0d5  mov     rcx, rdi
0x18000f0d8  call    NotifyCaller
0x18000f0dd  jmp     loc_18000F31D
0x18000f0e2  lea     r8, [rbp+0C10h+var_930]
0x18000f0e9  mov     edx, r14d
0x18000f0ec  mov     rcx, rdi
0x18000f0ef  call    NotifyCaller
0x18000f0f4  or      [rdi+38h], esi
0x18000f0f7  xor     r8d, r8d
0x18000f0fa  xor     edx, edx
0x18000f0fc  mov     rcx, rdi
0x18000f0ff  call    NotifyCaller
0x18000f104  mov     rdx, [rdi+10h]
0x18000f108  lea     r8, [rsp+0D10h+var_CD0]
0x18000f10d  mov     rax, qword ptr cs:xmmword_18004D470+8
0x18000f114  xor     ecx, ecx
0x18000f116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f11b  test    eax, eax
0x18000f11d  jnz     short loc_18000F141
0x18000f11f  mov     rcx, [rbp+0C10h+var_970]
0x18000f126  lea     r8, [rbp+0C10h+var_930]
0x18000f12d  mov     rax, qword ptr cs:xmmword_18004D410+8
0x18000f134  mov     r9d, 0E0h
0x18000f13a  mov     edx, ebx
0x18000f13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f141  mov     rcx, rdi
0x18000f144  call    StartAutoDisconnectForPort
0x18000f149  mov     rcx, rdi
0x18000f14c  call    StartLCPEchoForPort
0x18000f151  mov     eax, [rdi+38h]
0x18000f154  test    r14b, al
0x18000f157  jnz     loc_18000F1F3
0x18000f15d  mov     esi, 400h
0x18000f162  test    esi, eax
0x18000f164  jnz     loc_18000F1F3
0x18000f16a  cmp     cs:dword_18004DA20, 2
0x18000f171  lea     rax, [rdi+6B0h]
0x18000f178  mov     rcx, [rdi+8]
0x18000f17c  xorps   xmm0, xmm0
0x18000f17f  mov     [rbp+0C10h+var_850], rax
0x18000f186  movdqu  [rbp+0C10h+var_840], xmm0
0x18000f18e  lea     rax, [rcx+1E9h]
0x18000f195  mov     [rbp+0C10h+var_848], rax
0x18000f19c  mov     rax, [rcx+0A0h]
0x18000f1a3  mov     qword ptr [rbp+0C10h+var_840], rax
0x18000f1aa  lea     rax, [rdi+681h]
0x18000f1b1  mov     qword ptr [rbp+0C10h+var_840+8], rax
0x18000f1b8  jbe     short loc_18000F1ED
0x18000f1ba  mov     rcx, cs:hLogHandle; hLogHandle
0x18000f1c1  lea     rax, [rbp+0C10h+var_850]
0x18000f1c8  mov     [rsp+0D10h+dwErrorCode], 0; dwErrorCode
0x18000f1d0  mov     r9d, r14d; dwSubStringCount
0x18000f1d3  mov     r8d, 4F2Bh; dwMessageId
0x18000f1d9  mov     [rsp+0D10h+plpszSubStringArray], rax; plpszSubStringArray
0x18000f1de  mov     edx, r14d; dwEventType
0x18000f1e1  call    cs:__imp_RouterLogEventA
0x18000f1e8  nop     dword ptr [rax+rax+00h]
0x18000f1ed  or      [rdi+38h], esi
0x18000f1f0  mov     eax, [rdi+38h]
0x18000f1f3  test    al, 2
0x18000f1f5  jz      short loc_18000F1FF
0x18000f1f7  mov     rcx, rdi
0x18000f1fa  call    NotifyCompletionOnBundledPorts
0x18000f1ff  mov     rcx, rdi
0x18000f202  call    MakeStartAccountingCall
0x18000f207  jmp     loc_18000F74C
0x18000f20c  test    cs:byte_18004DF34, bl
0x18000f212  jz      short loc_18000F22E
0x18000f214  lea     r8, aLcpConfiguredS; "LCP Configured successfully"
0x18000f21b  lea     rdx, RasPppTraceInfo
0x18000f222  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f229  call    McTemplateU0z_EventWriteTransfer
0x18000f22e  test    [rdi+38h], r14b
0x18000f232  jnz     short loc_18000F2B1
  ... truncated ...
```
