# FsmThisLayerUp

- ea: `0x18000e86c`
- end: `0x18000f32d`
- name: `FsmThisLayerUp`
- size: `2753`
- prototype: ``
- caller_count: `6`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800023a8`
- `0x180004388`
- `0x180009c00`
- `0x18000a0f0`
- `0x18000c854`
- `0x1800149e0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180001e00`
- `0x180003110`
- `0x180003190`
- `0x180003660`
- `0x18000419c`
- `0x18000ba40`
- `0x18000db70`
- `0x18000e86c`
- `0x18000f528`
- `0x18000f7d4`
- `0x18000fa18`
- `0x18000fad4`
- `0x180010cfc`
- `0x180011064`
- `0x180011b08`
- `0x1800126b8`
- `0x180012dcc`
- `0x180013308`
- `0x180013490`
- `0x180013584`
- `0x180013630`
- `0x1800139e0`
- `0x180013bb4`
- `0x180014058`
- `0x18001413c`
- `0x180014514`
- `0x18001a170`
- `0x18002a138`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eebb`
- `rtutils!RouterLogEventA` at `0x18000eda1`
- `rtutils!RouterLogEventA` at `0x18000eda1`

## string_xrefs

- `0x18000e90c`: `FsmThisLayerUp called for protocol = %x, port = %d`
- `0x18000e994`: `FsmThisLayerUp for protocol=%x,port=%d,RetCode=%d`
- `0x18000edce`: `LCP Configured successfully`
- `0x18000ee24`: `Client: LCP Configured successfully for Guid %hs`

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
  __int64 v17; // rcx
  __int64 v18; // rcx
  _DWORD *v19; // rax
  int v20; // ecx
  const wchar_t *v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  _DWORD *v26; // rsi
  int v27; // edx
  __int64 v28; // rcx
  __int64 v29; // rax
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
  __int64 v41; // rdx
  unsigned int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // ecx
  __int64 v46; // rcx
  unsigned int CpIndexFromProtocol; // eax
  __int64 v48; // rcx
  unsigned int v49; // eax
  _DWORD v50[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v51[864]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v52; // [rsp+3A0h] [rbp+2A0h]
  _BYTE v53[224]; // [rsp+3E0h] [rbp+2E0h] BYREF
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
    if ( (byte_18004CF34 & 1) != 0 )
    {
      v6 = *(_QWORD *)(a1 + 16);
      LOWORD(v56) = 0;
      FormatRRASErrorString(
        &v56,
        L"FsmThisLayerUp called for protocol = %x, port = %d",
        *((unsigned int *)CpTable + 44 * v2),
        v6);
      if ( (byte_18004CF34 & 1) != 0 )
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
        if ( byte_18004CF33 < 0 )
        {
          v11 = *(_QWORD *)(a1 + 16);
          LOWORD(v56) = 0;
          FormatRRASErrorString(
            &v56,
            L"FsmThisLayerUp for protocol=%x,port=%d,RetCode=%d",
            *(unsigned int *)((char *)CpTable + v7),
            v11,
            v9);
          if ( byte_18004CF33 < 0 )
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
  else if ( (byte_18004CF34 & 1) != 0 )
  {
    v22 = *(_QWORD *)(a1 + 16);
    LOWORD(v56) = 0;
    FormatRRASErrorString(&v56, L"FsmThisLayerUp called in no auth case, port = %d", v22);
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v56);
  }
  v13 = *(_DWORD *)(a1 + 48);
  if ( !v13 )
  {
    if ( (byte_18004CF34 & 1) != 0 )
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
        if ( (byte_18004CF34 & 1) != 0 )
        {
          LOWORD(v56) = 0;
          FormatRRASErrorString(&v56, L"Client: LCP Configured successfully for Guid %hs", a1 + 1712);
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v56);
        }
        FsmSendIdentification(a1, 4);
      }
    }
    v26 = *(_DWORD **)(a1 + 1472);
    if ( v26[305] || v26[355] )
    {
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasPppTraceInfo,
          L"Authenticating phase started");
      *(_DWORD *)(a1 + 48) = 1;
      v46 = (unsigned int)v26[305];
      if ( (_DWORD)v46 )
      {
        CpIndexFromProtocol = GetCpIndexFromProtocol(v46);
        ApStart(a1, CpIndexFromProtocol, 1);
      }
      v48 = (unsigned int)v26[355];
      if ( (_DWORD)v48 )
      {
        v49 = GetCpIndexFromProtocol(v48);
        ApStart(a1, v49, 0);
      }
      return 1;
    }
    v27 = v26[6];
    if ( (*(_BYTE *)(a1 + 56) & 4) != 0 && (v27 & 0x4000) == 0 && (v27 & 0x400000) == 0 )
    {
      v28 = *(_QWORD *)(a1 + 152);
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
    if ( (byte_18004CF34 & 1) != 0 )
    {
      LOWORD(v56) = 0;
      FormatRRASErrorString(&v56, L"No Auth. Moving onto NCP. Guid %hs", a1 + 1712);
      if ( (byte_18004CF34 & 1) != 0 )
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
    NotifyCaller(a1, 22);
    if ( (*(_BYTE *)(a1 + 56) & 4) != 0 && (byte_18004CF34 & 1) != 0 )
    {
      LOWORD(v56) = 0;
      FormatRRASErrorString(&v56, L"Server: Authentication successful for Guid %hs", a1 + 1712);
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v56);
    }
    v34 = *(_DWORD *)(a1 + 56);
    if ( (v34 & 0x10) != 0 )
    {
      v35 = GetCpIndexFromProtocol(49193);
      if ( (byte_18004CF34 & 1) != 0 )
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
      NotifyCaller(a1, 3);
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
              NotifyCaller(a1, 24);
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
          if ( (byte_18004CF34 & 1) != 0 )
          {
            v40 = *(_QWORD *)(a1 + 16);
            LOWORD(v56) = 0;
            FormatRRASErrorString(&v56, L"Bundle NCPs not done for port %d, wait", v40);
            if ( (byte_18004CF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v56);
          }
          v41 = 24;
LABEL_143:
          NotifyCaller(a1, v41);
          return 1;
        }
LABEL_142:
        v41 = 25;
        goto LABEL_143;
      }
      if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
      {
        v42 = InitializeNCPs(a1, *(unsigned int *)(a1 + 184));
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
      if ( (dword_18004C9EC & 1) == 0 || *(char *)(*(_QWORD *)(a1 + 8) + 52LL) < 0 )
        goto LABEL_142;
      v43 = *(_DWORD *)(a1 + 60);
      if ( (v43 & 0x10000) != 0 && (dword_18004C9EC & 4) != 0 )
        goto LABEL_134;
      v44 = v43 & 0x20000;
      if ( v44 )
      {
        if ( (dword_18004C9EC & 2) != 0 )
          goto LABEL_134;
      }
      if ( (*(_DWORD *)(a1 + 60) & 0x10000) != 0 )
      {
        v45 = dword_18004C9EC | 4;
      }
      else if ( v44 )
      {
        v45 = dword_18004C9EC | 2;
      }
      else
      {
        if ( (dword_18004C9EC & 8) != 0 )
        {
LABEL_134:
          *(_DWORD *)(a1 + 1496) = 937;
          if ( (byte_18004CF34 & 1) != 0 )
          {
            LOWORD(v56) = 0;
            FormatRRASErrorString(&v56, L"User limit reached. Flags: %d", (unsigned int)dword_18004C9EC);
            if ( (byte_18004CF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v56);
          }
          v31 = *(unsigned int *)(a1 + 1496);
          goto LABEL_77;
        }
        v45 = dword_18004C9EC | 8;
      }
      dword_18004C9EC = v45;
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
  v17 = *(unsigned int *)(v16 + 1420);
  if ( (_DWORD)v17 )
  {
    if ( (_DWORD)v2 == (unsigned int)GetCpIndexFromProtocol(v17) )
      return 1;
  }
  v18 = *(unsigned int *)(v16 + 1220);
  if ( (_DWORD)v18 )
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
      if ( (byte_18004CF34 & 1) == 0 )
        goto LABEL_42;
      v21 = L"Server: Ipv4 successful for Guid %hs";
    }
    else
    {
      if ( v20 != 32855 || (byte_18004CF34 & 1) == 0 )
        goto LABEL_42;
      v21 = L"Server: IPv6 successful for Guid %hs";
    }
  }
  else if ( v20 == 32801 )
  {
    if ( (byte_18004CF34 & 1) == 0 )
      goto LABEL_42;
    v21 = L"Client: Ipv4 successful for Guid %hs";
  }
  else
  {
    if ( v20 != 32855 || (byte_18004CF34 & 1) == 0 )
      goto LABEL_42;
    v21 = L"Client: IPv6 successful for Guid %hs";
  }
  LOWORD(v56) = 0;
  FormatRRASErrorString(&v56, v21, a1 + 1712);
  if ( (byte_18004CF34 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v56);
LABEL_42:
  if ( (unsigned int)AreNCPsDone(a1, (unsigned int)v2, v53, v50) )
    return 0;
  if ( v50[0] == 1 )
  {
    RemoveFromTimerQ(*(_DWORD *)(a1 + 64), 0, 0, 0, 3);
    if ( (*(_BYTE *)(a1 + 56) & 4) != 0 )
    {
      NotifyCaller(a1, 19);
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
        if ( (unsigned int)dword_18004CA20 > 2 )
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
      NotifyCaller(a1, 4);
      *(_DWORD *)(a1 + 56) |= 0x80000u;
      NotifyCaller(a1, 0);
      if ( !(*((unsigned int (__fastcall **)(_QWORD, _QWORD, _BYTE *))&xmmword_18004C470 + 1))(
              0,
              *(_QWORD *)(a1 + 16),
              v51) )
        (*((void (__fastcall **)(__int64, __int64, _BYTE *, __int64))&xmmword_18004C410 + 1))(v52, 1, v53, 224);
      goto LABEL_54;
    }
    *(_DWORD *)(a1 + 1496) = 720;
    NotifyCallerOfFailure(a1, 720);
    NotifyCaller(a1, 10);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000e86c  mov     [rsp-8+arg_10], rbx
0x18000e871  mov     [rsp-8+arg_18], rsi
0x18000e876  push    rbp
0x18000e877  push    rdi
0x18000e878  push    r12
0x18000e87a  push    r14
0x18000e87c  push    r15
0x18000e87e  lea     rbp, [rsp-0BF0h]
0x18000e886  sub     rsp, 0CF0h
0x18000e88d  mov     rax, cs:__security_cookie
0x18000e894  xor     rax, rsp
0x18000e897  mov     [rbp+0C10h+var_30], rax
0x18000e89e  mov     r12d, edx
0x18000e8a1  mov     rdi, rcx
0x18000e8a4  xor     edx, edx; Val
0x18000e8a6  lea     rcx, [rbp+0C10h+var_930]; void *
0x18000e8ad  mov     r8d, 0E0h; Size
0x18000e8b3  call    memset_0
0x18000e8b8  mov     edx, r12d
0x18000e8bb  mov     [rsp+0D10h+var_CE0], 0
0x18000e8c3  mov     rcx, rdi
0x18000e8c6  call    GetPointerToCPCB
0x18000e8cb  xor     ecx, ecx
0x18000e8cd  xor     edx, edx; Val
0x18000e8cf  mov     [rbp+0C10h+var_830], ecx
0x18000e8d5  mov     r8d, 7FCh; Size
0x18000e8db  lea     rcx, [rbp+0C10h+var_82C]; void *
0x18000e8e2  mov     r15, rax
0x18000e8e5  call    memset_0
0x18000e8ea  mov     r14d, 4
0x18000e8f0  lea     ebx, [r14-3]
0x18000e8f4  test    r15, r15
0x18000e8f7  jz      loc_18000EB0A
0x18000e8fd  test    cs:byte_18004CF34, bl
0x18000e903  jz      short loc_18000E959
0x18000e905  mov     r8, cs:CpTable
0x18000e90c  lea     rdx, aFsmthislayerup; "FsmThisLayerUp called for protocol = %x"...
0x18000e913  mov     r9, [rdi+10h]
0x18000e917  xor     eax, eax
0x18000e919  imul    rcx, r12, 0B0h
0x18000e920  mov     word ptr [rbp+0C10h+var_830], ax
0x18000e927  mov     r8d, [rcx+r8]
0x18000e92b  lea     rcx, [rbp+0C10h+var_830]
0x18000e932  call    FormatRRASErrorString
0x18000e937  test    cs:byte_18004CF34, bl
0x18000e93d  jz      short loc_18000E959
0x18000e93f  lea     r8, [rbp+0C10h+var_830]
0x18000e946  lea     rdx, RasPppTraceInfo
0x18000e94d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e954  call    McTemplateU0z_EventWriteTransfer
0x18000e959  mov     rax, cs:CpTable
0x18000e960  imul    r14, r12, 0B0h
0x18000e967  mov     rax, [r14+rax+48h]
0x18000e96c  test    rax, rax
0x18000e96f  jz      loc_18000E9FF
0x18000e975  mov     rcx, [r15+10h]
0x18000e979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e97e  mov     esi, eax
0x18000e980  test    eax, eax
0x18000e982  jz      short loc_18000E9FF
0x18000e984  cmp     cs:byte_18004CF33, 0
0x18000e98b  jge     short loc_18000E9DF
0x18000e98d  mov     r8, cs:CpTable
0x18000e994  lea     rdx, aFsmthislayerup_1; "FsmThisLayerUp for protocol=%x,port=%d,"...
0x18000e99b  mov     r9, [rdi+10h]
0x18000e99f  xor     ecx, ecx
0x18000e9a1  mov     word ptr [rbp+0C10h+var_830], cx
0x18000e9a8  lea     rcx, [rbp+0C10h+var_830]
0x18000e9af  mov     dword ptr [rsp+0D10h+plpszSubStringArray], eax
0x18000e9b3  mov     r8d, [r14+r8]
0x18000e9b7  call    FormatRRASErrorString
0x18000e9bc  cmp     cs:byte_18004CF33, 0
0x18000e9c3  jge     short loc_18000E9DF
0x18000e9c5  lea     r8, [rbp+0C10h+var_830]
0x18000e9cc  lea     rdx, RasPppTraceError
0x18000e9d3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e9da  call    McTemplateU0z_EventWriteTransfer
0x18000e9df  cmp     esi, 258h
0x18000e9e5  jz      loc_18000EED1
0x18000e9eb  mov     edx, r12d
0x18000e9ee  mov     [r15+28h], esi
0x18000e9f2  mov     rcx, rdi
0x18000e9f5  call    FsmClose
0x18000e9fa  jmp     loc_18000EED1
0x18000e9ff  test    byte ptr [rdi+38h], 4
0x18000ea03  jnz     short loc_18000EA39
0x18000ea05  mov     rax, cs:CpTable
0x18000ea0c  mov     r8d, [r14+rax]
0x18000ea10  cmp     r8d, 8057h
0x18000ea17  jz      short loc_18000EA22
0x18000ea19  cmp     r8d, 8021h
0x18000ea20  jnz     short loc_18000EA39
0x18000ea22  mov     edx, [r15+8]
0x18000ea26  xor     r9d, r9d
0x18000ea29  mov     ecx, [rdi+40h]
0x18000ea2c  mov     dword ptr [rsp+0D10h+plpszSubStringArray], 8
0x18000ea34  call    RemoveFromTimerQ
0x18000ea39  mov     r14d, 4
0x18000ea3f  mov     ecx, [rdi+30h]
0x18000ea42  test    ecx, ecx
0x18000ea44  jz      loc_18000EDC6
0x18000ea4a  sub     ecx, 1
0x18000ea4d  jz      loc_18000EF54
0x18000ea53  sub     ecx, 1
0x18000ea56  jz      loc_18000F06D
0x18000ea5c  cmp     ecx, 1
0x18000ea5f  jnz     loc_18000F300
0x18000ea65  mov     rsi, [rdi+5C0h]
0x18000ea6c  mov     ecx, [rsi+58Ch]
0x18000ea72  test    ecx, ecx
0x18000ea74  jz      short loc_18000EA84
0x18000ea76  call    GetCpIndexFromProtocol
0x18000ea7b  cmp     r12d, eax
0x18000ea7e  jz      loc_18000F300
0x18000ea84  mov     ecx, [rsi+4C4h]
0x18000ea8a  test    ecx, ecx
0x18000ea8c  jz      short loc_18000EA9C
0x18000ea8e  call    GetCpIndexFromProtocol
0x18000ea93  cmp     r12d, eax
0x18000ea96  jz      loc_18000F300
0x18000ea9c  test    r15, r15
0x18000ea9f  jz      loc_18000EED1
0x18000eaa5  mov     rax, cs:CpTable
0x18000eaac  mov     edx, 8021h
0x18000eab1  imul    rsi, r12, 0B0h
0x18000eab8  mov     dword ptr [r15+38h], 2
0x18000eac0  cmp     [rsi+rax], edx
0x18000eac3  jnz     short loc_18000EADA
0x18000eac5  mov     rcx, rdi
0x18000eac8  call    NotifyIPCPOfProjection
0x18000eacd  test    eax, eax
0x18000eacf  jz      loc_18000EED1
0x18000ead5  mov     edx, 8021h
0x18000eada  mov     rax, cs:CpTable
0x18000eae1  mov     ecx, [rsi+rax]
0x18000eae4  test    [rdi+38h], r14b
0x18000eae8  jz      loc_18000EB7A
0x18000eaee  cmp     ecx, edx
0x18000eaf0  jnz     short loc_18000EB61
0x18000eaf2  test    cs:byte_18004CF34, bl
0x18000eaf8  jz      loc_18000EBCF
0x18000eafe  lea     rdx, aServerIpv4Succ; "Server: Ipv4 successful for Guid %hs"
0x18000eb05  jmp     loc_18000EB91
0x18000eb0a  test    cs:byte_18004CF34, bl
0x18000eb10  jz      loc_18000EA3F
0x18000eb16  mov     r8, [rdi+10h]
0x18000eb1a  lea     rdx, aFsmthislayerup_0; "FsmThisLayerUp called in no auth case, "...
0x18000eb21  xor     eax, eax
0x18000eb23  lea     rcx, [rbp+0C10h+var_830]
0x18000eb2a  mov     word ptr [rbp+0C10h+var_830], ax
0x18000eb31  call    FormatRRASErrorString
0x18000eb36  test    cs:byte_18004CF34, bl
0x18000eb3c  jz      loc_18000EA3F
0x18000eb42  lea     r8, [rbp+0C10h+var_830]
0x18000eb49  lea     rdx, RasPppTraceInfo
0x18000eb50  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000eb57  call    McTemplateU0z_EventWriteTransfer
0x18000eb5c  jmp     loc_18000EA3F
0x18000eb61  cmp     ecx, 8057h
0x18000eb67  jnz     short loc_18000EBCF
0x18000eb69  test    cs:byte_18004CF34, bl
0x18000eb6f  jz      short loc_18000EBCF
0x18000eb71  lea     rdx, aServerIpv6Succ; "Server: IPv6 successful for Guid %hs"
0x18000eb78  jmp     short loc_18000EB91
0x18000eb7a  cmp     ecx, edx
0x18000eb7c  jnz     loc_18000EC2F
0x18000eb82  test    cs:byte_18004CF34, bl
0x18000eb88  jz      short loc_18000EBCF
0x18000eb8a  lea     rdx, aClientIpv4Succ; "Client: Ipv4 successful for Guid %hs"
0x18000eb91  xor     eax, eax
0x18000eb93  lea     r8, [rdi+6B0h]
0x18000eb9a  lea     rcx, [rbp+0C10h+var_830]
0x18000eba1  mov     word ptr [rbp+0C10h+var_830], ax
0x18000eba8  call    FormatRRASErrorString
0x18000ebad  test    cs:byte_18004CF34, bl
0x18000ebb3  jz      short loc_18000EBCF
0x18000ebb5  lea     r8, [rbp+0C10h+var_830]
0x18000ebbc  lea     rdx, RasPppTraceInfo
0x18000ebc3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ebca  call    McTemplateU0z_EventWriteTransfer
0x18000ebcf  lea     r9, [rsp+0D10h+var_CE0]
0x18000ebd4  mov     edx, r12d
0x18000ebd7  lea     r8, [rbp+0C10h+var_930]
0x18000ebde  mov     rcx, rdi
0x18000ebe1  call    AreNCPsDone
0x18000ebe6  test    eax, eax
0x18000ebe8  jnz     loc_18000EED1
0x18000ebee  cmp     [rsp+0D10h+var_CE0], ebx
0x18000ebf2  jnz     loc_18000F300
0x18000ebf8  mov     ecx, [rdi+40h]
0x18000ebfb  xor     r9d, r9d
0x18000ebfe  xor     r8d, r8d
0x18000ec01  mov     dword ptr [rsp+0D10h+plpszSubStringArray], 3
0x18000ec09  xor     edx, edx
0x18000ec0b  call    RemoveFromTimerQ
0x18000ec10  test    [rdi+38h], r14b
0x18000ec14  jz      short loc_18000EC4B
0x18000ec16  lea     r8, [rbp+0C10h+var_930]
0x18000ec1d  mov     edx, 13h
0x18000ec22  mov     rcx, rdi
0x18000ec25  call    NotifyCaller
0x18000ec2a  jmp     loc_18000ED01
0x18000ec2f  cmp     ecx, 8057h
0x18000ec35  jnz     short loc_18000EBCF
0x18000ec37  test    cs:byte_18004CF34, bl
0x18000ec3d  jz      short loc_18000EBCF
0x18000ec3f  lea     rdx, aClientIpv6Succ; "Client: IPv6 successful for Guid %hs"
0x18000ec46  jmp     loc_18000EB91
0x18000ec4b  xor     edx, edx; Val
0x18000ec4d  lea     rcx, [rsp+0D10h+var_CD0]; void *
0x18000ec52  mov     r8d, 398h; Size
0x18000ec58  call    memset_0
0x18000ec5d  mov     esi, 80000h
0x18000ec62  test    [rdi+38h], esi
0x18000ec65  jz      short loc_18000ECA2
0x18000ec67  lea     rdx, [rbp+0C10h+var_930]
0x18000ec6e  call    AreAnyNCPsActive
0x18000ec73  test    eax, eax
0x18000ec75  jnz     short loc_18000ECA2
0x18000ec77  mov     edx, 2D0h
0x18000ec7c  lea     rbx, [rdi+5D8h]
0x18000ec83  mov     rcx, rdi
0x18000ec86  mov     [rbx], edx
0x18000ec88  call    NotifyCallerOfFailure
0x18000ec8d  mov     r8, rbx
0x18000ec90  mov     edx, 0Ah
0x18000ec95  mov     rcx, rdi
0x18000ec98  call    NotifyCaller
0x18000ec9d  jmp     loc_18000EED1
0x18000eca2  lea     r8, [rbp+0C10h+var_930]
0x18000eca9  mov     edx, r14d
0x18000ecac  mov     rcx, rdi
0x18000ecaf  call    NotifyCaller
0x18000ecb4  or      [rdi+38h], esi
0x18000ecb7  xor     r8d, r8d
0x18000ecba  xor     edx, edx
0x18000ecbc  mov     rcx, rdi
0x18000ecbf  call    NotifyCaller
0x18000ecc4  mov     rdx, [rdi+10h]
0x18000ecc8  lea     r8, [rsp+0D10h+var_CD0]
0x18000eccd  mov     rax, qword ptr cs:xmmword_18004C470+8
0x18000ecd4  xor     ecx, ecx
0x18000ecd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecdb  test    eax, eax
0x18000ecdd  jnz     short loc_18000ED01
0x18000ecdf  mov     rcx, [rbp+0C10h+var_970]
0x18000ece6  lea     r8, [rbp+0C10h+var_930]
0x18000eced  mov     rax, qword ptr cs:xmmword_18004C410+8
0x18000ecf4  mov     r9d, 0E0h
0x18000ecfa  mov     edx, ebx
0x18000ecfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed01  mov     rcx, rdi
0x18000ed04  call    StartAutoDisconnectForPort
0x18000ed09  mov     rcx, rdi
0x18000ed0c  call    StartLCPEchoForPort
0x18000ed11  mov     eax, [rdi+38h]
0x18000ed14  test    r14b, al
0x18000ed17  jnz     loc_18000EDAD
0x18000ed1d  mov     esi, 400h
0x18000ed22  test    esi, eax
0x18000ed24  jnz     loc_18000EDAD
0x18000ed2a  cmp     cs:dword_18004CA20, 2
0x18000ed31  lea     rax, [rdi+6B0h]
0x18000ed38  mov     rcx, [rdi+8]
0x18000ed3c  xorps   xmm0, xmm0
0x18000ed3f  mov     [rbp+0C10h+var_850], rax
0x18000ed46  movdqu  [rbp+0C10h+var_840], xmm0
0x18000ed4e  lea     rax, [rcx+1E9h]
0x18000ed55  mov     [rbp+0C10h+var_848], rax
0x18000ed5c  mov     rax, [rcx+0A0h]
0x18000ed63  mov     qword ptr [rbp+0C10h+var_840], rax
0x18000ed6a  lea     rax, [rdi+681h]
0x18000ed71  mov     qword ptr [rbp+0C10h+var_840+8], rax
0x18000ed78  jbe     short loc_18000EDA7
0x18000ed7a  mov     rcx, cs:hLogHandle; hLogHandle
0x18000ed81  lea     rax, [rbp+0C10h+var_850]
0x18000ed88  mov     [rsp+0D10h+dwErrorCode], 0; dwErrorCode
0x18000ed90  mov     r9d, r14d; dwSubStringCount
0x18000ed93  mov     r8d, 4F2Bh; dwMessageId
0x18000ed99  mov     [rsp+0D10h+plpszSubStringArray], rax; plpszSubStringArray
0x18000ed9e  mov     edx, r14d; dwEventType
0x18000eda1  call    cs:__imp_RouterLogEventA
0x18000eda7  or      [rdi+38h], esi
0x18000edaa  mov     eax, [rdi+38h]
0x18000edad  test    al, 2
0x18000edaf  jz      short loc_18000EDB9
0x18000edb1  mov     rcx, rdi
0x18000edb4  call    NotifyCompletionOnBundledPorts
0x18000edb9  mov     rcx, rdi
0x18000edbc  call    MakeStartAccountingCall
0x18000edc1  jmp     loc_18000F300
0x18000edc6  test    cs:byte_18004CF34, bl
0x18000edcc  jz      short loc_18000EDE8
0x18000edce  lea     r8, aLcpConfiguredS; "LCP Configured successfully"
0x18000edd5  lea     rdx, RasPppTraceInfo
0x18000eddc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ede3  call    McTemplateU0z_EventWriteTransfer
0x18000ede8  test    [rdi+38h], r14b
0x18000edec  jnz     short loc_18000EE6B
0x18000edee  mov     rcx, rdi
  ... truncated ...
```
