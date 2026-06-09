# EuCommit

- ea: `0x180012b78`
- end: `0x18001330e`
- name: `EuCommit`
- size: `1942`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800149b4`
- `0x180014b40`
- `0x18001bae4`

## callees

- `0x1800128e4`
- `0x180012b78`
- `0x180013314`
- `0x1800134d0`
- `0x180013660`
- `0x180013858`
- `0x180013b44`
- `0x1800140ec`
- `0x180014198`
- `0x1800146cc`
- `0x18002a81c`
- `0x18003b57c`
- `0x18003b7ac`
- `0x18003bea0`
- `0x18003c860`
- `0x18003ccb8`
- `0x18003ce6c`
- `0x180042bb0`
- `0x1800448e4`
- `0x180048b6c`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `WS2_32!__imp_closesocket` at `0x180013209`
- `WS2_32!__imp_closesocket` at `0x180013235`
- `WS2_32!__imp_closesocket` at `0x180013209`
- `WS2_32!__imp_closesocket` at `0x180013235`
- `WS2_32!__imp_socket` at `0x1800131ec`
- `WS2_32!__imp_socket` at `0x180013218`
- `WS2_32!__imp_socket` at `0x1800131ec`
- `WS2_32!__imp_socket` at `0x180013218`
- `WS2_32!__imp_WSAGetLastError` at `0x180013195`
- `WS2_32!__imp_WSAGetLastError` at `0x180013245`
- `WS2_32!__imp_WSAGetLastError` at `0x180013195`
- `WS2_32!__imp_WSAGetLastError` at `0x180013245`
- `WS2_32!__imp_WSAStartup` at `0x18001318b`
- `WS2_32!__imp_WSAStartup` at `0x18001318b`
- `WS2_32!__imp_WSACleanup` at `0x18001323b`
- `WS2_32!__imp_WSACleanup` at `0x18001323b`
- `RASAPI32!DestroyEntryNode` at `0x180012f98`
- `RASAPI32!DestroyEntryNode` at `0x180012fc6`
- `RASAPI32!DestroyEntryNode` at `0x180012f98`
- `RASAPI32!DestroyEntryNode` at `0x180012fc6`
- `RASAPI32!IsActiveAutoTriggerConnection` at `0x18001302d`
- `RASAPI32!IsActiveAutoTriggerConnection` at `0x18001302d`
- `RASAPI32!WritePhonebookFile` at `0x180012f42`
- `RASAPI32!WritePhonebookFile` at `0x1800130f3`
- `RASAPI32!WritePhonebookFile` at `0x180012f42`
- `RASAPI32!WritePhonebookFile` at `0x1800130f3`
- `RASAPI32!DestroyLinkNode` at `0x180012c83`
- `RASAPI32!DestroyLinkNode` at `0x180012c83`
- `rtutils!TracePrintfExA` at `0x180012ce2`
- `rtutils!TracePrintfExA` at `0x180012d84`
- `rtutils!TracePrintfExA` at `0x1800130ca`
- `rtutils!TracePrintfExA` at `0x1800131b9`
- `rtutils!TracePrintfExA` at `0x180013263`
- `rtutils!TracePrintfExA` at `0x180013296`
- `rtutils!TracePrintfExA` at `0x180012ce2`
- `rtutils!TracePrintfExA` at `0x180012d84`
- `rtutils!TracePrintfExA` at `0x1800130ca`
- `rtutils!TracePrintfExA` at `0x1800131b9`
- `rtutils!TracePrintfExA` at `0x180013263`
- `rtutils!TracePrintfExA` at `0x180013296`

## string_xrefs

- `0x1800130a9`: `EuCommit: g_pRasUpdateAutoTriggerRegKeys failed with error 0x%X `
- `0x18001305e`: `EuCommit: LoadRasmanDll failed with error 0x%X `
- `0x1800130bd`: `EuCommit: IsActiveAutoTriggerConnection failed with error 0x%X `
- `0x180013259`: `WSACleanup. Error: %d\n`

## pseudocode

```c
__int64 __fastcall EuCommit(__int64 a1)
{
  __int64 v1; // rax
  __int64 i; // rbx
  __int64 v4; // rax
  _QWORD *v5; // rdx
  _QWORD *v6; // rbx
  __int64 v7; // rdx
  __int64 *v8; // rcx
  __int64 v9; // rsi
  DWORD v10; // ecx
  __int64 v11; // rsi
  _DWORD *v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  _BYTE *v19; // rax
  __int64 v20; // rcx
  _QWORD *v21; // rbx
  _QWORD *v22; // rsi
  __int64 v23; // rdx
  DWORD v24; // eax
  DWORD v25; // ebp
  __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned int active; // eax
  __int64 (__fastcall *v29)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  unsigned int RasmanDll; // eax
  unsigned int v31; // eax
  int v32; // ebx
  DWORD v33; // ebx
  DWORD v34; // eax
  int Error; // eax
  SOCKET v36; // rax
  SOCKET v37; // rax
  int v38; // eax
  int v39; // eax
  __int64 result; // rax
  int v41; // [rsp+20h] [rbp-208h]
  int v42; // [rsp+40h] [rbp-1E8h] BYREF
  int v43; // [rsp+44h] [rbp-1E4h] BYREF
  int v44; // [rsp+48h] [rbp-1E0h] BYREF
  WSAData WSAData; // [rsp+50h] [rbp-1D8h] BYREF

  v1 = *(_QWORD *)(a1 + 872);
  v44 = 0;
  v42 = 0;
  v43 = 0;
  if ( *(_DWORD *)(v1 + 40) )
  {
    for ( i = **(_QWORD **)(v1 + 32); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)(*(_QWORD *)(i + 16) + 188LL) )
        CopyLinkPhoneNumberInfo(i, *(_QWORD *)(a1 + 328));
    }
  }
  v4 = *(_QWORD *)(a1 + 872);
  if ( *(_DWORD *)(v4 + 272) || *(_DWORD *)(v4 + 372) )
  {
    *(_DWORD *)(v4 + 704) = 0;
  }
  else if ( *(_DWORD *)(v4 + 728) || *(_DWORD *)(v4 + 708) || *(_DWORD *)(v4 + 688) || *(_QWORD *)(v4 + 744) )
  {
    *(_DWORD *)(v4 + 704) = 1;
  }
  if ( *(_DWORD *)(a1 + 324) )
  {
    v5 = **(_QWORD ***)(*(_QWORD *)(a1 + 872) + 32LL);
    if ( v5 )
    {
      do
      {
        v6 = (_QWORD *)v5[1];
        if ( !*(_DWORD *)(v5[2] + 188LL) )
        {
          DtlRemoveNode(*(_QWORD *)(*(_QWORD *)(a1 + 872) + 32LL), v5);
          DestroyLinkNode(v7);
        }
        v5 = v6;
      }
      while ( v6 );
    }
  }
  if ( *(_DWORD *)(a1 + 324) )
  {
    v8 = *(__int64 **)(*(_QWORD *)(a1 + 872) + 32LL);
    if ( *((_DWORD *)v8 + 4) == 1 )
    {
      v9 = *v8;
      if ( *v8 )
      {
        v10 = g_dwTraceId;
        v11 = *(_QWORD *)(v9 + 16);
        if ( g_dwTraceId != -1 )
        {
          TracePrintfExA(g_dwTraceId, 0xCu, "Mult devs, only one selected -- check preferred dev.");
          v10 = g_dwTraceId;
        }
        if ( *(_QWORD *)(a1 + 888) && *(_QWORD *)(a1 + 896) )
        {
          if ( !(unsigned int)CompareStringWrapW(*(PCNZWCH *)(a1 + 888), *(PCNZWCH *)(v11 + 16))
            && !(unsigned int)CompareStringWrapW(*(PCNZWCH *)(a1 + 896), *(PCNZWCH *)v11) )
          {
            v12 = *(_DWORD **)(a1 + 872);
            if ( v12[22] == *(_DWORD *)(v11 + 104)
              && v12[23] == *(_DWORD *)(v11 + 108)
              && v12[24] == *(_DWORD *)(v11 + 112)
              && v12[25] == *(_DWORD *)(v11 + 116)
              && v12[26] == *(_DWORD *)(v11 + 120)
              && v12[27] == *(_DWORD *)(v11 + 124) )
            {
              goto LABEL_40;
            }
          }
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "New device selected as preferred device");
        }
        else if ( v10 != -1 )
        {
          TracePrintfExA(v10, 0xCu, "No preferred device.  Resetting preferred to current.");
        }
        Free0(*(_QWORD *)(*(_QWORD *)(a1 + 872) + 80LL));
        Free0(*(_QWORD *)(*(_QWORD *)(a1 + 872) + 72LL));
        v13 = *(_QWORD *)(a1 + 872);
        *(_QWORD *)(v13 + 80) = StrDup(*(STRSAFE_LPCWSTR *)(v11 + 16));
        v14 = *(_QWORD *)(a1 + 872);
        *(_QWORD *)(v14 + 72) = StrDup(*(STRSAFE_LPCWSTR *)v11);
        *(_DWORD *)(*(_QWORD *)(a1 + 872) + 88LL) = *(_DWORD *)(v11 + 104);
        *(_DWORD *)(*(_QWORD *)(a1 + 872) + 92LL) = *(_DWORD *)(v11 + 108);
        *(_DWORD *)(*(_QWORD *)(a1 + 872) + 96LL) = *(_DWORD *)(v11 + 112);
        *(_DWORD *)(*(_QWORD *)(a1 + 872) + 100LL) = *(_DWORD *)(v11 + 116);
        *(_DWORD *)(*(_QWORD *)(a1 + 872) + 104LL) = *(_DWORD *)(v11 + 120);
        *(_DWORD *)(*(_QWORD *)(a1 + 872) + 108LL) = *(_DWORD *)(v11 + 124);
      }
    }
  }
LABEL_40:
  v15 = *(_QWORD *)(a1 + 128);
  if ( *(_DWORD *)(v15 + 180) )
  {
    v16 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 544LL);
    v17 = v16 ? *(_QWORD *)(v16 + 72) : 0LL;
    if ( ((unsigned int (__fastcall *)(__int64, __int64, _QWORD))g_pSetUserPreferences[0])(
           v17,
           v15,
           *(_DWORD *)(a1 + 28) != 0 ? 2 : 0) )
    {
      return 0;
    }
  }
  *(_DWORD *)(*(_QWORD *)(a1 + 872) + 532LL) = 1;
  StringCchCopyWrapW((wchar_t *)(*(_QWORD *)(a1 + 16) + 24LL), 0x101u, *(const wchar_t **)(*(_QWORD *)(a1 + 872) + 8LL));
  EuGetEditFlags(a1, &v42, &v43);
  v18 = *(_QWORD *)(a1 + 872);
  if ( *(_DWORD *)(v18 + 168) == 1 && (*(_DWORD *)(*(_QWORD *)(a1 + 64) + 32LL) & 0x100) == 0 )
  {
    *(_DWORD *)(v18 + 140) = 0;
    v19 = (_BYTE *)(a1 + 1012);
    v20 = 514;
    do
    {
      *v19++ = 0;
      --v20;
    }
    while ( v20 );
    *(_DWORD *)(a1 + 1008) = 1;
  }
  v21 = 0;
  if ( v42 )
  {
    v21 = *(_QWORD **)(a1 + 336);
    DtlRemoveNode(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 16LL), v21);
  }
  v22 = *(_QWORD **)(a1 + 864);
  DtlAddNodeLast(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 16LL), v22);
  v23 = a1 + 344;
  *(_QWORD *)(a1 + 864) = 0;
  if ( !v43 )
    v23 = 0;
  v24 = WritePhonebookFile(*(_QWORD *)(a1 + 64), v23);
  v25 = v24;
  if ( v24 )
  {
    ErrorDlgUtil(*(HWND *)(*(_QWORD *)(a1 + 16) + 4LL), 0x158u, v24, 0, v41, 0x169u, 0xFAu);
    *(_DWORD *)(*(_QWORD *)(a1 + 16) + 540LL) = v25;
    if ( v22 )
    {
      DtlRemoveNode(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 16LL), v22);
      DestroyEntryNode(v22);
    }
    if ( v42 )
      DtlAddNodeLast(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 16LL), v21);
    return 0;
  }
  if ( v21 )
    DestroyEntryNode(v21);
  v26 = 1;
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 16) + 12LL) & 0xB2) == 0 )
    v26 = 4;
  DwSendRasNotification(v26, *(_QWORD *)(a1 + 872), **(_QWORD **)(a1 + 64));
  if ( *(_DWORD *)(a1 + 1564) != *(_DWORD *)(*(_QWORD *)(a1 + 872) + 156LL) )
  {
    v27 = *(_QWORD *)(a1 + 8);
    if ( v27 )
    {
      if ( *(_QWORD *)a1 )
      {
        active = IsActiveAutoTriggerConnection(*(_QWORD *)a1, v27, 0, &v44);
        if ( active || !v44 )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "EuCommit: IsActiveAutoTriggerConnection failed with error 0x%X ", active);
        }
        else
        {
          v29 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_pRasUpdateAutoTriggerRegKeys;
          if ( !g_pRasUpdateAutoTriggerRegKeys )
          {
            RasmanDll = LoadRasmanDll();
            if ( RasmanDll )
            {
              if ( g_dwTraceId != -1 )
                TracePrintfExA(g_dwTraceId, 0xCu, "EuCommit: LoadRasmanDll failed with error 0x%X ", RasmanDll);
              goto LABEL_78;
            }
            v29 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_pRasUpdateAutoTriggerRegKeys;
          }
          v41 = 0;
          v31 = v29(*(_QWORD *)a1, *(_QWORD *)(a1 + 8), *(_QWORD *)(*(_QWORD *)(a1 + 872) + 464LL), 0);
          if ( v31 && g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "EuCommit: g_pRasUpdateAutoTriggerRegKeys failed with error 0x%X ", v31);
        }
      }
    }
  }
LABEL_78:
  if ( (unsigned int)EuRouterInterfaceIsNew(a1) )
  {
    v32 = EuRouterInterfaceCreate();
    if ( v32 )
    {
      WritePhonebookFile(*(_QWORD *)(a1 + 64), *(_QWORD *)(a1 + 16) + 24LL);
LABEL_81:
      *(_DWORD *)(*(_QWORD *)(a1 + 16) + 540LL) = v32;
      return 0;
    }
  }
  if ( !*(_DWORD *)(a1 + 28) )
  {
    v33 = EuCredentialsCommitRasIPSec(a1);
    if ( v33 )
      goto LABEL_108;
    v34 = EuCredentialsCommitRasGlobal(a1);
    goto LABEL_89;
  }
  v33 = EuCredentialsCommitRouterIPSec(a1);
  if ( v33 )
    goto LABEL_108;
  if ( (unsigned int)EuRouterInterfaceIsNew(a1) && *(_QWORD *)(a1 + 912) )
  {
    v34 = EuCredentialsCommitRouterStandard();
LABEL_89:
    v33 = v34;
    if ( !v34 )
      goto LABEL_90;
LABEL_108:
    ErrorDlgUtil(*(HWND *)(*(_QWORD *)(a1 + 16) + 4LL), 0x64Du, v33, 0, v41, 0x169u, 0xFAu);
    *(_DWORD *)(*(_QWORD *)(a1 + 16) + 540LL) = v33;
    return 0;
  }
LABEL_90:
  EuInternetSettingsCommitDefault(a1);
  if ( *(_DWORD *)(a1 + 28) )
  {
    memset_0(&WSAData, 0, sizeof(WSAData));
    if ( WSAStartup(0x202u, &WSAData) )
    {
      Error = WSAGetLastError();
      v32 = Error;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "WSAStartup. Error: %d\n", Error);
      goto LABEL_81;
    }
    *(_QWORD *)(*(_QWORD *)(a1 + 16) + 552LL) |= ~*(_DWORD *)(*(_QWORD *)(a1 + 872) + 236LL) & 0xCLL;
    v36 = socket(2, 2, 0);
    if ( v36 == -1 )
      *(_QWORD *)(*(_QWORD *)(a1 + 16) + 552LL) &= ~4uLL;
    else
      closesocket(v36);
    v37 = socket(23, 2, 0);
    if ( v37 == -1 )
      *(_QWORD *)(*(_QWORD *)(a1 + 16) + 552LL) &= ~8uLL;
    else
      closesocket(v37);
    if ( WSACleanup() )
    {
      v38 = WSAGetLastError();
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "WSACleanup. Error: %d\n", v38);
    }
  }
  if ( *(_DWORD *)(a1 + 1528) )
  {
    v39 = EuClearCustomPolicy(a1);
    if ( v39 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "EuClearCustomPolicy. Error: %d\n", v39);
    }
  }
  result = 1;
  *(_DWORD *)(*(_QWORD *)(a1 + 16) + 540LL) = 0;
  return result;
}

```

## disassembly

```asm
0x180012b78  mov     [rsp+arg_8], rbx
0x180012b7d  mov     [rsp+arg_10], rbp
0x180012b82  push    rsi
0x180012b83  push    rdi
0x180012b84  push    r12
0x180012b86  push    r13
0x180012b88  push    r15
0x180012b8a  sub     rsp, 200h
0x180012b91  mov     rax, cs:__security_cookie
0x180012b98  xor     rax, rsp
0x180012b9b  mov     [rsp+228h+var_38], rax
0x180012ba3  mov     rax, [rcx+368h]
0x180012baa  xor     r15d, r15d
0x180012bad  mov     [rsp+228h+var_1E0], r15d
0x180012bb2  mov     rdi, rcx
0x180012bb5  mov     [rsp+228h+var_1E8], r15d
0x180012bba  mov     [rsp+228h+var_1E4], r15d
0x180012bbf  cmp     [rax+28h], r15d
0x180012bc3  jz      short loc_180012BF3
0x180012bc5  mov     rax, [rax+20h]
0x180012bc9  mov     rbx, [rax]
0x180012bcc  jmp     short loc_180012BEE
0x180012bce  mov     rax, [rbx+10h]
0x180012bd2  cmp     [rax+0BCh], r15d
0x180012bd9  jz      short loc_180012BEA
0x180012bdb  mov     rdx, [rdi+148h]
0x180012be2  mov     rcx, rbx
0x180012be5  call    CopyLinkPhoneNumberInfo
0x180012bea  mov     rbx, [rbx+8]
0x180012bee  test    rbx, rbx
0x180012bf1  jnz     short loc_180012BCE
0x180012bf3  mov     rax, [rdi+368h]
0x180012bfa  cmp     [rax+110h], r15d
0x180012c01  jnz     short loc_180012C3C
0x180012c03  cmp     [rax+174h], r15d
0x180012c0a  jnz     short loc_180012C3C
0x180012c0c  cmp     [rax+2D8h], r15d
0x180012c13  ja      short loc_180012C30
0x180012c15  cmp     [rax+2C4h], r15d
0x180012c1c  ja      short loc_180012C30
0x180012c1e  cmp     [rax+2B0h], r15d
0x180012c25  ja      short loc_180012C30
0x180012c27  cmp     [rax+2E8h], r15
0x180012c2e  jz      short loc_180012C43
0x180012c30  mov     dword ptr [rax+2C0h], 1
0x180012c3a  jmp     short loc_180012C43
0x180012c3c  mov     [rax+2C0h], r15d
0x180012c43  cmp     [rdi+144h], r15d
0x180012c4a  jz      short loc_180012C91
0x180012c4c  mov     rax, [rdi+368h]
0x180012c53  mov     rcx, [rax+20h]
0x180012c57  mov     rdx, [rcx]
0x180012c5a  test    rdx, rdx
0x180012c5d  jz      short loc_180012C91
0x180012c5f  mov     rax, [rdx+10h]
0x180012c63  mov     rbx, [rdx+8]
0x180012c67  cmp     [rax+0BCh], r15d
0x180012c6e  jnz     short loc_180012C89
0x180012c70  mov     rcx, [rdi+368h]
0x180012c77  mov     rcx, [rcx+20h]
0x180012c7b  call    DtlRemoveNode
0x180012c80  mov     rcx, rdx
0x180012c83  call    cs:__imp_DestroyLinkNode
0x180012c89  mov     rdx, rbx
0x180012c8c  test    rbx, rbx
0x180012c8f  jnz     short loc_180012C5F
0x180012c91  or      r12d, 0FFFFFFFFh
0x180012c95  mov     r13d, 0Ch
0x180012c9b  cmp     [rdi+144h], r15d
0x180012ca2  jz      loc_180012E1F
0x180012ca8  mov     rax, [rdi+368h]
0x180012caf  mov     rcx, [rax+20h]
0x180012cb3  cmp     dword ptr [rcx+10h], 1
0x180012cb7  jnz     loc_180012E1F
0x180012cbd  mov     rsi, [rcx]
0x180012cc0  test    rsi, rsi
0x180012cc3  jz      loc_180012E1F
0x180012cc9  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180012ccf  mov     rsi, [rsi+10h]
0x180012cd3  cmp     ecx, r12d
0x180012cd6  jz      short loc_180012CEE
0x180012cd8  lea     r8, aMultDevsOnlyOn; "Mult devs, only one selected -- check p"...
0x180012cdf  mov     edx, r13d; dwFlags
0x180012ce2  call    cs:__imp_TracePrintfExA
0x180012ce8  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180012cee  mov     rax, [rdi+378h]
0x180012cf5  test    rax, rax
0x180012cf8  jz      short loc_180012D75
0x180012cfa  cmp     [rdi+380h], r15
0x180012d01  jz      short loc_180012D75
0x180012d03  mov     rdx, [rsi+10h]; lpString2
0x180012d07  mov     rcx, rax; lpString1
0x180012d0a  call    CompareStringWrapW
0x180012d0f  test    eax, eax
0x180012d11  jnz     short loc_180012D61
0x180012d13  mov     rdx, [rsi]; lpString2
0x180012d16  mov     rcx, [rdi+380h]; lpString1
0x180012d1d  call    CompareStringWrapW
0x180012d22  test    eax, eax
0x180012d24  jnz     short loc_180012D61
0x180012d26  mov     rcx, [rdi+368h]
0x180012d2d  mov     eax, [rsi+68h]
0x180012d30  cmp     [rcx+58h], eax
0x180012d33  jnz     short loc_180012D61
0x180012d35  mov     eax, [rsi+6Ch]
0x180012d38  cmp     [rcx+5Ch], eax
0x180012d3b  jnz     short loc_180012D61
0x180012d3d  mov     eax, [rsi+70h]
0x180012d40  cmp     [rcx+60h], eax
0x180012d43  jnz     short loc_180012D61
0x180012d45  mov     eax, [rsi+74h]
0x180012d48  cmp     [rcx+64h], eax
0x180012d4b  jnz     short loc_180012D61
0x180012d4d  mov     eax, [rsi+78h]
0x180012d50  cmp     [rcx+68h], eax
0x180012d53  jnz     short loc_180012D61
0x180012d55  mov     eax, [rsi+7Ch]
0x180012d58  cmp     [rcx+6Ch], eax
0x180012d5b  jz      loc_180012E1F
0x180012d61  mov     ecx, cs:g_dwTraceId
0x180012d67  cmp     ecx, r12d
0x180012d6a  jz      short loc_180012D8A
0x180012d6c  lea     r8, aNewDeviceSelec; "New device selected as preferred device"
0x180012d73  jmp     short loc_180012D81
0x180012d75  cmp     ecx, r12d
0x180012d78  jz      short loc_180012D8A
0x180012d7a  lea     r8, aNoPreferredDev; "No preferred device.  Resetting preferr"...
0x180012d81  mov     edx, r13d; dwFlags
0x180012d84  call    cs:__imp_TracePrintfExA
0x180012d8a  mov     rcx, [rdi+368h]
0x180012d91  mov     rcx, [rcx+50h]
0x180012d95  call    Free0
0x180012d9a  mov     rcx, [rdi+368h]
0x180012da1  mov     rcx, [rcx+48h]
0x180012da5  call    Free0
0x180012daa  mov     rcx, [rsi+10h]; pszSrc
0x180012dae  mov     rbx, [rdi+368h]
0x180012db5  call    StrDup
0x180012dba  mov     [rbx+50h], rax
0x180012dbe  mov     rcx, [rsi]; pszSrc
0x180012dc1  mov     rbx, [rdi+368h]
0x180012dc8  call    StrDup
0x180012dcd  mov     [rbx+48h], rax
0x180012dd1  mov     rcx, [rdi+368h]
0x180012dd8  mov     eax, [rsi+68h]
0x180012ddb  mov     [rcx+58h], eax
0x180012dde  mov     rcx, [rdi+368h]
0x180012de5  mov     eax, [rsi+6Ch]
0x180012de8  mov     [rcx+5Ch], eax
0x180012deb  mov     rcx, [rdi+368h]
0x180012df2  mov     eax, [rsi+70h]
0x180012df5  mov     [rcx+60h], eax
0x180012df8  mov     rcx, [rdi+368h]
0x180012dff  mov     eax, [rsi+74h]
0x180012e02  mov     [rcx+64h], eax
0x180012e05  mov     rcx, [rdi+368h]
0x180012e0c  mov     eax, [rsi+78h]
0x180012e0f  mov     [rcx+68h], eax
0x180012e12  mov     rcx, [rdi+368h]
0x180012e19  mov     eax, [rsi+7Ch]
0x180012e1c  mov     [rcx+6Ch], eax
0x180012e1f  mov     rdx, [rdi+80h]
0x180012e26  cmp     [rdx+0B4h], r15d
0x180012e2d  jz      short loc_180012E68
0x180012e2f  mov     rax, [rdi+10h]
0x180012e33  mov     rcx, [rax+220h]
0x180012e3a  mov     eax, [rdi+1Ch]
0x180012e3d  neg     eax
0x180012e3f  sbb     r8d, r8d
0x180012e42  and     r8d, 2
0x180012e46  test    rcx, rcx
0x180012e49  jz      short loc_180012E51
0x180012e4b  mov     rcx, [rcx+48h]
0x180012e4f  jmp     short loc_180012E54
0x180012e51  mov     rcx, r15
0x180012e54  mov     rax, cs:g_pSetUserPreferences
0x180012e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e60  test    eax, eax
0x180012e62  jnz     loc_1800132E0
0x180012e68  mov     rax, [rdi+368h]
0x180012e6f  mov     edx, 101h
0x180012e74  mov     dword ptr [rax+214h], 1
0x180012e7e  mov     r8, [rdi+368h]
0x180012e85  mov     rcx, [rdi+10h]
0x180012e89  add     rcx, 18h
0x180012e8d  mov     r8, [r8+8]
0x180012e91  call    StringCchCopyWrapW
0x180012e96  lea     r8, [rsp+228h+var_1E4]
0x180012e9b  mov     rcx, rdi
0x180012e9e  lea     rdx, [rsp+228h+var_1E8]
0x180012ea3  call    EuGetEditFlags
0x180012ea8  mov     rcx, [rdi+368h]
0x180012eaf  cmp     dword ptr [rcx+0A8h], 1
0x180012eb6  jnz     short loc_180012EEE
0x180012eb8  mov     rax, [rdi+40h]
0x180012ebc  test    dword ptr [rax+20h], 100h
0x180012ec3  jnz     short loc_180012EEE
0x180012ec5  mov     [rcx+8Ch], r15d
0x180012ecc  lea     rax, [rdi+3F4h]
0x180012ed3  mov     ecx, 202h
0x180012ed8  mov     [rax], r15b
0x180012edb  inc     rax
0x180012ede  sub     rcx, 1
0x180012ee2  jnz     short loc_180012ED8
0x180012ee4  mov     dword ptr [rdi+3F0h], 1
0x180012eee  mov     rbx, r15
0x180012ef1  cmp     [rsp+228h+var_1E8], r15d
0x180012ef6  jz      short loc_180012F0F
0x180012ef8  mov     rcx, [rdi+40h]
0x180012efc  mov     rbx, [rdi+150h]
0x180012f03  mov     rdx, rbx
0x180012f06  mov     rcx, [rcx+10h]
0x180012f0a  call    DtlRemoveNode
0x180012f0f  mov     rcx, [rdi+40h]
0x180012f13  mov     rsi, [rdi+360h]
0x180012f1a  mov     rdx, rsi
0x180012f1d  mov     rcx, [rcx+10h]
0x180012f21  call    DtlAddNodeLast
0x180012f26  lea     rdx, [rdi+158h]
0x180012f2d  mov     [rdi+360h], r15
0x180012f34  cmp     [rsp+228h+var_1E4], r15d
0x180012f39  jnz     short loc_180012F3E
0x180012f3b  mov     rdx, r15
0x180012f3e  mov     rcx, [rdi+40h]
0x180012f42  call    cs:__imp_WritePhonebookFile
0x180012f48  mov     ebp, eax
0x180012f4a  test    eax, eax
0x180012f4c  jz      short loc_180012FBE
0x180012f4e  mov     rcx, [rdi+10h]
0x180012f52  xor     r9d, r9d
0x180012f55  mov     [rsp+228h+var_1F8], 0FAh; UINT
0x180012f5d  mov     r8d, eax; dwMessageId
0x180012f60  mov     edx, 158h; uID
0x180012f65  mov     [rsp+228h+var_200], 169h; UINT
0x180012f6d  mov     rcx, [rcx+4]; hWnd
0x180012f71  call    ErrorDlgUtil
0x180012f76  mov     rdx, [rdi+10h]
0x180012f7a  mov     [rdx+21Ch], ebp
0x180012f80  test    rsi, rsi
0x180012f83  jz      short loc_180012F9E
0x180012f85  mov     rcx, [rdi+40h]
0x180012f89  mov     rdx, rsi
0x180012f8c  mov     rcx, [rcx+10h]
0x180012f90  call    DtlRemoveNode
0x180012f95  mov     rcx, rsi
0x180012f98  call    cs:__imp_DestroyEntryNode
0x180012f9e  cmp     [rsp+228h+var_1E8], r15d
0x180012fa3  jz      loc_1800132E0
0x180012fa9  mov     rcx, [rdi+40h]
0x180012fad  mov     rdx, rbx
0x180012fb0  mov     rcx, [rcx+10h]
0x180012fb4  call    DtlAddNodeLast
0x180012fb9  jmp     loc_1800132E0
0x180012fbe  test    rbx, rbx
0x180012fc1  jz      short loc_180012FCC
0x180012fc3  mov     rcx, rbx
0x180012fc6  call    cs:__imp_DestroyEntryNode
0x180012fcc  mov     rax, [rdi+40h]
0x180012fd0  mov     ecx, 1
0x180012fd5  mov     rdx, [rdi+368h]
0x180012fdc  mov     r8, [rax]
0x180012fdf  mov     rax, [rdi+10h]
0x180012fe3  test    byte ptr [rax+0Ch], 0B2h
0x180012fe7  jnz     short loc_180012FEE
0x180012fe9  mov     ecx, 4
0x180012fee  call    DwSendRasNotification
0x180012ff3  mov     rax, [rdi+368h]
0x180012ffa  mov     ecx, [rax+9Ch]
0x180013000  cmp     [rdi+61Ch], ecx
0x180013006  jz      loc_1800130D0
0x18001300c  mov     rdx, [rdi+8]
0x180013010  test    rdx, rdx
0x180013013  jz      loc_1800130D0
0x180013019  mov     rcx, [rdi]
0x18001301c  test    rcx, rcx
0x18001301f  jz      loc_1800130D0
0x180013025  lea     r9, [rsp+228h+var_1E0]
0x18001302a  xor     r8d, r8d
0x18001302d  call    cs:__imp_IsActiveAutoTriggerConnection
0x180013033  test    eax, eax
0x180013035  jnz     short loc_1800130B2
0x180013037  cmp     [rsp+228h+var_1E0], r15d
0x18001303c  jz      short loc_1800130B2
0x18001303e  mov     rax, cs:g_pRasUpdateAutoTriggerRegKeys
0x180013045  test    rax, rax
0x180013048  jnz     short loc_18001306E
0x18001304a  call    LoadRasmanDll
0x18001304f  test    eax, eax
0x180013051  jz      short loc_180013067
0x180013053  mov     ecx, cs:g_dwTraceId
0x180013059  cmp     ecx, r12d
0x18001305c  jz      short loc_1800130D0
0x18001305e  lea     r8, aEucommitLoadra; "EuCommit: LoadRasmanDll failed with err"...
0x180013065  jmp     short loc_1800130C4
0x180013067  mov     rax, cs:g_pRasUpdateAutoTriggerRegKeys
0x18001306e  mov     r8, [rdi+368h]
0x180013075  xor     r9d, r9d
0x180013078  mov     rdx, [rdi+8]
0x18001307c  mov     rcx, [rdi]
0x18001307f  mov     [rsp+228h+var_1F8], r15d
  ... truncated ...
```
