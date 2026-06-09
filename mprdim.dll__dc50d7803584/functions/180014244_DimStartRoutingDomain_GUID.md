# DimStartRoutingDomain(_GUID *)

- ea: `0x180014244`
- end: `0x180014a5d`
- name: `?DimStartRoutingDomain@@YAKPEAU_GUID@@@Z`
- size: `2073`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000e090`
- `0x180014a70`
- `0x180016b80`

## callees

- `0x180001610`
- `0x180008250`
- `0x18000ad04`
- `0x18000df70`
- `0x180013580`
- `0x180013c9c`
- `0x180014244`
- `0x1800161b8`
- `0x180016884`
- `0x180027454`
- `0x18002f5d4`
- `0x180035244`
- `0x180035d10`
- `0x18003653c`
- `0x180036730`
- `0x18003748c`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001483a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001483a`

## string_xrefs

- `0x18001437a`: `DimStartRoutingDomain: Failed to retrieve the compartment ID for routing domain: %d.`
- `0x18001441a`: `DimStartRoutingDomain: GetRoutingDomainConfiguration (RdName) failed: %d.`
- `0x180014557`: `DimStartRoutingDomain: GetRoutingDomainConfiguration (RouterType) failed: %d.`
- `0x1800146ba`: `DimStartRoutingDomain: Error %d occured while loading interfaces from registry.`
- `0x1800147a7`: `Unable to create the interface entry in the registry`
- `0x1800147e3`: `Unable to load the interface from the registry`
- `0x180014887`: `DimStartRoutingDomain: RouterManager::RemoveRoutingDomain (ipv4) failed: %d.`
- `0x1800148fe`: `DimStartRoutingDomain: RouterManager::RemoveRoutingDomain  (ipv6) failed: %d.`
- `0x180014975`: `DimStartRoutingDomain: NotifyDDMForRoutingDomainChange (RD delete) failed: %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DimStartRoutingDomain(struct _GUID *a1)
{
  int v1; // r12d
  unsigned int InterfaceEntry; // esi
  unsigned int RoutingDomainConfiguration; // eax
  const wchar_t *v5; // rdx
  __int64 *v6; // rdx
  __int128 *v7; // r9
  unsigned int v8; // eax
  int v9; // r13d
  unsigned int v10; // eax
  CDimRouterManager *v11; // rcx
  bool v12; // zf
  __int64 *v13; // rdx
  __int128 *v14; // r9
  unsigned int v15; // eax
  unsigned int v16; // eax
  const wchar_t *v17; // rdx
  __int128 *v18; // r9
  char *v19; // r13
  unsigned int Interfaces; // eax
  __int128 *v21; // r9
  unsigned int v22; // eax
  unsigned int v23; // r12d
  unsigned __int16 *v24; // r13
  unsigned __int16 *v25; // r13
  const wchar_t *v26; // r8
  __int128 *v27; // r9
  CDimInterfaceTable *v28; // rcx
  unsigned int v29; // eax
  CDimRouterManager *v30; // rcx
  __int128 *v31; // r9
  unsigned int v32; // eax
  __int128 *v33; // r9
  unsigned int v34; // eax
  CDimInterfaceTable *v35; // rcx
  __int128 *v36; // r9
  unsigned int v37; // eax
  __int128 *v38; // r9
  struct _DIM_COMPARTMENT_INTERFACE *v40; // [rsp+20h] [rbp-E0h]
  NET_IF_COMPARTMENT_ID CompartmentId; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v42; // [rsp+38h] [rbp-C8h] BYREF
  int v43; // [rsp+3Ch] [rbp-C4h] BYREF
  int v44; // [rsp+40h] [rbp-C0h]
  int v45; // [rsp+44h] [rbp-BCh]
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v47; // [rsp+58h] [rbp-A8h]
  __int128 v48; // [rsp+60h] [rbp-A0h] BYREF
  int v49; // [rsp+70h] [rbp-90h] BYREF
  __int128 v50; // [rsp+74h] [rbp-8Ch]
  __int128 v51; // [rsp+84h] [rbp-7Ch]
  int v52; // [rsp+94h] [rbp-6Ch]
  int v53; // [rsp+A0h] [rbp-60h] BYREF
  char v54[2044]; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned __int16 v55[264]; // [rsp+8A0h] [rbp+7A0h] BYREF

  v1 = 0;
  CompartmentId = 0;
  lpMem = 0;
  v42 = 0;
  v43 = 0;
  v53 = 0;
  memset_0(v54, 0, sizeof(v54));
  v49 = 0;
  v52 = 0;
  v50 = 0;
  v51 = 0;
  v48 = 0;
  InterfaceEntry = ReferenceOrDereferenceRoutingDomain(a1, 1);
  if ( InterfaceEntry )
  {
    MarkRoutingDomainAsUnAvailable(a1);
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v53) = 0;
      LOWORD(v49) = 0;
      FormatRRASErrorString(
        &v53,
        L"DimStartRoutingDomain: ReferenceOrDereferenceRoutingDomain (TRUE) failed with error: %d.",
        InterfaceEntry);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
LABEL_101:
        v38 = &v48;
        if ( a1 )
          LODWORD(v38) = (_DWORD)a1;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceError,
          (unsigned int)&v53,
          (_DWORD)v38,
          0,
          (__int64)&v49);
      }
    }
LABEL_104:
    MarkRoutingDomainAsUnAvailable(a1);
    return InterfaceEntry;
  }
  MarkRoutingDomainAsAvailable(a1);
  RoutingDomainConfiguration = GetRoutingDomainConfiguration(a1, (__int64)&CompartmentId);
  if ( RoutingDomainConfiguration )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 1) == 0 )
      goto LABEL_98;
    v5 = L"DimStartRoutingDomain: Failed to retrieve the compartment ID for routing domain: %d.";
    goto LABEL_8;
  }
  v8 = GetRoutingDomainConfiguration(a1, (__int64)v55);
  if ( v8 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_98;
    LOWORD(v53) = 0;
    LOWORD(v49) = 0;
    FormatRRASErrorString(&v53, L"DimStartRoutingDomain: GetRoutingDomainConfiguration (RdName) failed: %d.", v8);
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_98;
    v6 = RasDimParamTraceError;
    goto LABEL_10;
  }
  RoutingDomainConfiguration = AddRoutingDomainToRtrMgr(a1, v55, CompartmentId, 1);
  if ( RoutingDomainConfiguration && RoutingDomainConfiguration != 902 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 1) == 0 )
      goto LABEL_98;
    v5 = L"DimStartRoutingDomain: AddRoutingDomainToRtrMgr(ipv4) failed: %d.";
LABEL_8:
    LOWORD(v53) = 0;
    LOWORD(v49) = 0;
    FormatRRASErrorString(&v53, v5, RoutingDomainConfiguration);
    if ( (Microsoft_Windows_RRASEnableBits & 1) == 0 )
      goto LABEL_98;
    v6 = RasDimParamTraceAdminError;
LABEL_10:
    v7 = &v48;
    if ( a1 )
      LODWORD(v7) = (_DWORD)a1;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (_DWORD)v6,
      (unsigned int)&v53,
      (_DWORD)v7,
      0,
      (__int64)&v49);
    goto LABEL_98;
  }
  v9 = 0;
  v10 = AddRoutingDomainToRtrMgr(a1, v55, CompartmentId, 0);
  if ( v10 && v10 != 902 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 1) == 0 )
      goto LABEL_77;
    LOWORD(v53) = 0;
    LOWORD(v49) = 0;
    FormatRRASErrorString(&v53, L"DimStartRoutingDomain: AddRoutingDomainToRtrMgr(ipv6) failed: %d.", v10);
    v12 = (Microsoft_Windows_RRASEnableBits & 1) == 0;
LABEL_25:
    if ( !v12 )
    {
      v13 = RasDimParamTraceAdminError;
LABEL_27:
      v14 = &v48;
      if ( a1 )
        LODWORD(v14) = (_DWORD)a1;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (_DWORD)v13,
        (unsigned int)&v53,
        (_DWORD)v14,
        0,
        (__int64)&v49);
      goto LABEL_77;
    }
    goto LABEL_77;
  }
  v1 = 1;
  v44 = 1;
  v15 = GetRoutingDomainConfiguration(a1, (__int64)&v43);
  if ( v15 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v53) = 0;
      LOWORD(v49) = 0;
      FormatRRASErrorString(&v53, L"DimStartRoutingDomain: GetRoutingDomainConfiguration (RouterType) failed: %d.", v15);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        v13 = RasDimParamTraceError;
        goto LABEL_27;
      }
    }
LABEL_77:
    v29 = CDimRouterManager::RemoveRoutingDomain(v11, 0x21u, a1);
    v30 = 0;
    if ( v29 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v53) = 0;
        LOWORD(v49) = 0;
        FormatRRASErrorString(
          &v53,
          L"DimStartRoutingDomain: RouterManager::RemoveRoutingDomain (ipv4) failed: %d.",
          v29);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v31 = &v48;
          if ( a1 )
            LODWORD(v31) = (_DWORD)a1;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v53,
            (_DWORD)v31,
            0,
            (__int64)&v49);
        }
      }
    }
    if ( v1 )
    {
      v32 = CDimRouterManager::RemoveRoutingDomain(v30, 0x57u, a1);
      if ( v32 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          LOWORD(v53) = 0;
          LOWORD(v49) = 0;
          FormatRRASErrorString(
            &v53,
            L"DimStartRoutingDomain: RouterManager::RemoveRoutingDomain  (ipv6) failed: %d.",
            v32);
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            v33 = &v48;
            if ( a1 )
              LODWORD(v33) = (_DWORD)a1;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceError,
              (unsigned int)&v53,
              (_DWORD)v33,
              0,
              (__int64)&v49);
          }
        }
      }
    }
    if ( v9 )
    {
      v34 = NotifyDDMForRoutingDomainChange(a1, 2u, 0);
      if ( v34 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          LOWORD(v53) = 0;
          LOWORD(v49) = 0;
          FormatRRASErrorString(
            &v53,
            L"DimStartRoutingDomain: NotifyDDMForRoutingDomainChange (RD delete) failed: %d.",
            v34);
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            v36 = &v48;
            if ( a1 )
              LODWORD(v36) = (_DWORD)a1;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceError,
              (unsigned int)&v53,
              (_DWORD)v36,
              0,
              (__int64)&v49);
          }
        }
      }
      CDimInterfaceTable::RemoveInterfaces(v35, a1);
    }
LABEL_98:
    v37 = ReferenceOrDereferenceRoutingDomain(a1, 0);
    InterfaceEntry = v37;
    if ( v37 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v53) = 0;
        LOWORD(v49) = 0;
        FormatRRASErrorString(
          &v53,
          L"DimStartRoutingDomain: ReferenceOrDereferenceRoutingDomain(FALSE) failed: %d.",
          v37);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          goto LABEL_101;
      }
    }
    goto LABEL_104;
  }
  v16 = NotifyDDMForRoutingDomainChange(a1, 1u, &v43);
  if ( v16 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 1) == 0 )
      goto LABEL_77;
    LOWORD(v53) = 0;
    LOWORD(v49) = 0;
    FormatRRASErrorString(&v53, L"DimStartRoutingDomain: NotifyDDMForRoutingDomain (NEW RD) failed: %d.", v16);
    v12 = (Microsoft_Windows_RRASEnableBits & 1) == 0;
    goto LABEL_25;
  }
  InterfaceEntry = RegisterInterfaceChangeNotifications(a1, 1);
  if ( InterfaceEntry )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      return InterfaceEntry;
    v17 = L"DimStartRoutingDomain: RegisterInterfaceChangeNotifications failed  with error %d.";
    goto LABEL_40;
  }
  InterfaceEntry = DimEnumerateInterfacesFromStack(CompartmentId, &v42, (struct _DIM_COMPARTMENT_INTERFACE **)&lpMem);
  if ( InterfaceEntry )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      return InterfaceEntry;
    v17 = L"DimStartRoutingDomain: Error %d occured while loading interfaces from stack.";
LABEL_40:
    LOWORD(v49) = 0;
    LOWORD(v53) = 0;
    FormatRRASErrorString(&v53, v17, InterfaceEntry);
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      v18 = &v48;
      if ( a1 )
        LODWORD(v18) = (_DWORD)a1;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDimParamTraceError,
        (unsigned int)&v53,
        (_DWORD)v18,
        0,
        (__int64)&v49);
    }
    return InterfaceEntry;
  }
  v19 = (char *)lpMem;
  v45 = 1;
  Interfaces = CDimInterfaceTable::RegLoadInterfaces(
                 g_pCDimInterfaceTable,
                 0,
                 a1,
                 v42,
                 (struct _DIM_COMPARTMENT_INTERFACE *)lpMem);
  InterfaceEntry = Interfaces;
  if ( !Interfaces )
  {
    v22 = CDimInterfaceTable::PlumbRDIkev2Policy(g_pCDimInterfaceTable, a1, 0);
    InterfaceEntry = 0;
    if ( v22 != 2 )
      InterfaceEntry = v22;
    if ( InterfaceEntry )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        goto LABEL_73;
      LOWORD(v53) = 0;
      LOWORD(v49) = 0;
      FormatRRASErrorString(
        &v53,
        L"DimStartRoutingDomain: Error %d occured while plumbing custom IKEv2 policy.",
        InterfaceEntry);
      goto LABEL_50;
    }
    v23 = 0;
    InterfaceEntry = 0;
    while ( 1 )
    {
      if ( v23 >= v42 )
      {
        v1 = v44;
        goto LABEL_73;
      }
      v24 = (unsigned __int16 *)&v19[536 * v23];
      if ( !v24[266] )
      {
        v47 = v24 + 8;
        InterfaceEntry = DimCreateInterfaceEntry(a1, v24 + 8);
        if ( InterfaceEntry )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
            goto LABEL_71;
          v25 = v47;
          v26 = L"Unable to create the interface entry in the registry";
        }
        else
        {
          v40 = (struct _DIM_COMPARTMENT_INTERFACE *)v24;
          v25 = v47;
          InterfaceEntry = CDimInterfaceTable::RegLoadInterfaces(g_pCDimInterfaceTable, v47, a1, 1u, v40);
          if ( !InterfaceEntry || (Microsoft_Windows_RRASEnableBits & 4) == 0 )
            goto LABEL_71;
          v26 = L"Unable to load the interface from the registry";
        }
        LOWORD(v49) = 0;
        v27 = &v48;
        if ( a1 )
          LODWORD(v27) = (_DWORD)a1;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceError,
          (_DWORD)v26,
          (_DWORD)v27,
          (__int64)v25,
          (__int64)&v49);
      }
LABEL_71:
      v19 = (char *)lpMem;
      ++v23;
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
    goto LABEL_73;
  LOWORD(v53) = 0;
  LOWORD(v49) = 0;
  FormatRRASErrorString(
    &v53,
    L"DimStartRoutingDomain: Error %d occured while loading interfaces from registry.",
    Interfaces);
LABEL_50:
  if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
  {
    v21 = &v48;
    if ( a1 )
      LODWORD(v21) = (_DWORD)a1;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDimParamTraceError,
      (unsigned int)&v53,
      (_DWORD)v21,
      0,
      (__int64)&v49);
  }
LABEL_73:
  if ( v19 )
    HeapFree(hHeap, 0, v19);
  if ( InterfaceEntry )
  {
    CDimInterfaceTable::PlumbRDIkev2Policy(g_pCDimInterfaceTable, a1, 1);
    CDimInterfaceTable::DisableDisconnectS2SInterfacesInRd(v28, a1);
    v9 = v45;
    goto LABEL_77;
  }
  return InterfaceEntry;
}

```

## disassembly

```asm
0x180014244  push    rbp
0x180014246  push    rbx
0x180014247  push    rsi
0x180014248  push    rdi
0x180014249  push    r12
0x18001424b  push    r13
0x18001424d  push    r14
0x18001424f  push    r15
0x180014251  lea     rbp, [rsp-9C8h]
0x180014259  sub     rsp, 0AC8h
0x180014260  mov     rax, cs:__security_cookie
0x180014267  xor     rax, rsp
0x18001426a  mov     [rbp+0A00h+var_50], rax
0x180014271  xor     r12d, r12d
0x180014274  mov     rbx, rcx
0x180014277  lea     rcx, [rbp+0A00h+var_A5C]; void *
0x18001427b  mov     [rsp+0B00h+CompartmentId], r12d
0x180014280  xor     edx, edx; Val
0x180014282  mov     [rsp+0B00h+lpMem], r12
0x180014287  mov     r8d, 7FCh; Size
0x18001428d  mov     [rsp+0B00h+var_AC8], r12d
0x180014292  mov     [rsp+0B00h+var_AD0], r12d
0x180014297  mov     dword ptr [rsp+0B00h+var_AC4], r12d
0x18001429c  mov     [rbp+0A00h+var_A60], r12d
0x1800142a0  call    memset_0
0x1800142a5  xorps   xmm0, xmm0
0x1800142a8  mov     [rsp+0B00h+var_A90], r12d
0x1800142ad  xor     eax, eax
0x1800142af  lea     r13d, [r12+1]
0x1800142b4  mov     edx, r13d; int
0x1800142b7  mov     [rbp+0A00h+var_A6C], eax
0x1800142ba  mov     rcx, rbx; struct _GUID *
0x1800142bd  movups  [rsp+0B00h+var_A8C], xmm0
0x1800142c2  movups  [rbp+0A00h+var_A7C], xmm0
0x1800142c6  movups  [rsp+0B00h+var_AA0], xmm0
0x1800142cb  call    ReferenceOrDereferenceRoutingDomain
0x1800142d0  mov     esi, eax
0x1800142d2  mov     rcx, rbx; struct _GUID *
0x1800142d5  test    eax, eax
0x1800142d7  jz      short loc_18001432E
0x1800142d9  call    MarkRoutingDomainAsUnAvailable
0x1800142de  lea     edi, [r12+4]
0x1800142e3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x1800142ea  jz      loc_180014A30
0x1800142f0  mov     r8d, esi
0x1800142f3  mov     word ptr [rbp+0A00h+var_A60], r12w
0x1800142f8  lea     rdx, aDimstartroutin_12; "DimStartRoutingDomain: ReferenceOrDeref"...
0x1800142ff  mov     word ptr [rsp+0B00h+var_A90], r12w
0x180014305  lea     rcx, [rbp+0A00h+var_A60]
0x180014309  call    FormatRRASErrorString
0x18001430e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180014315  jz      loc_180014A30
0x18001431b  lea     rdx, RasDimParamTraceError
0x180014322  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014329  jmp     loc_180014A0C
0x18001432e  call    MarkRoutingDomainAsAvailable
0x180014333  lea     rax, [rsp+0B00h+CompartmentId]
0x180014338  mov     edi, 4
0x18001433d  lea     r9, [rsp+0B00h+var_AD0]
0x180014342  mov     [rsp+0B00h+var_AE0], rax; __int64
0x180014347  xor     r8d, r8d
0x18001434a  mov     [rsp+0B00h+var_AD0], edi
0x18001434e  mov     edx, 100h
0x180014353  mov     rcx, rbx; struct _GUID *
0x180014356  call    GetRoutingDomainConfiguration
0x18001435b  lea     r15, RasDimParamTraceError
0x180014362  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014369  test    eax, eax
0x18001436b  jz      short loc_1800143D8
0x18001436d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180014374  jz      loc_1800149C6
0x18001437a  lea     rdx, aDimstartroutin_7; "DimStartRoutingDomain: Failed to retrie"...
0x180014381  mov     r8d, eax
0x180014384  mov     word ptr [rbp+0A00h+var_A60], r12w
0x180014389  lea     rcx, [rbp+0A00h+var_A60]
0x18001438d  mov     word ptr [rsp+0B00h+var_A90], r12w
0x180014393  call    FormatRRASErrorString
0x180014398  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18001439f  jz      loc_1800149C6
0x1800143a5  lea     rdx, RasDimParamTraceAdminError
0x1800143ac  test    rbx, rbx
0x1800143af  lea     rax, [rsp+0B00h+var_A90]
0x1800143b4  mov     [rsp+0B00h+var_AD8], rax
0x1800143b9  lea     r9, [rsp+0B00h+var_AA0]
0x1800143be  cmovnz  r9, rbx
0x1800143c2  mov     [rsp+0B00h+var_AE0], r12
0x1800143c7  lea     r8, [rbp+0A00h+var_A60]
0x1800143cb  mov     rcx, r14
0x1800143ce  call    McTemplateU0zjzz_EventWriteTransfer
0x1800143d3  jmp     loc_1800149C6
0x1800143d8  lea     rax, [rbp+0A00h+var_260]
0x1800143df  mov     [rsp+0B00h+var_AD0], 202h
0x1800143e7  lea     r9, [rsp+0B00h+var_AD0]
0x1800143ec  mov     [rsp+0B00h+var_AE0], rax; __int64
0x1800143f1  xor     r8d, r8d
0x1800143f4  mov     edx, 400h
0x1800143f9  mov     rcx, rbx; struct _GUID *
0x1800143fc  call    GetRoutingDomainConfiguration
0x180014401  test    eax, eax
0x180014403  jz      short loc_180014445
0x180014405  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18001440c  jz      loc_1800149C6
0x180014412  mov     r8d, eax
0x180014415  mov     word ptr [rbp+0A00h+var_A60], r12w
0x18001441a  lea     rdx, aDimstartroutin_10; "DimStartRoutingDomain: GetRoutingDomain"...
0x180014421  mov     word ptr [rsp+0B00h+var_A90], r12w
0x180014427  lea     rcx, [rbp+0A00h+var_A60]
0x18001442b  call    FormatRRASErrorString
0x180014430  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180014437  jz      loc_1800149C6
0x18001443d  mov     rdx, r15
0x180014440  jmp     loc_1800143AC
0x180014445  mov     r8d, [rsp+0B00h+CompartmentId]; unsigned int
0x18001444a  lea     rdx, [rbp+0A00h+var_260]; unsigned __int16 *
0x180014451  mov     r9d, r13d; int
0x180014454  mov     rcx, rbx; struct _GUID *
0x180014457  call    ?AddRoutingDomainToRtrMgr@@YAKPEAU_GUID@@PEAGIH@Z; AddRoutingDomainToRtrMgr(_GUID *,ushort *,uint,int)
0x18001445c  mov     esi, 386h
0x180014461  test    eax, eax
0x180014463  jz      short loc_180014482
0x180014465  cmp     eax, esi
0x180014467  jz      short loc_180014482
0x180014469  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180014470  jz      loc_1800149C6
0x180014476  lea     rdx, aDimstartroutin_2; "DimStartRoutingDomain: AddRoutingDomain"...
0x18001447d  jmp     loc_180014381
0x180014482  mov     r8d, [rsp+0B00h+CompartmentId]; unsigned int
0x180014487  lea     rdx, [rbp+0A00h+var_260]; unsigned __int16 *
0x18001448e  xor     r9d, r9d; int
0x180014491  mov     rcx, rbx; struct _GUID *
0x180014494  mov     r13d, r12d
0x180014497  call    ?AddRoutingDomainToRtrMgr@@YAKPEAU_GUID@@PEAGIH@Z; AddRoutingDomainToRtrMgr(_GUID *,ushort *,uint,int)
0x18001449c  mov     r8d, eax
0x18001449f  test    eax, eax
0x1800144a1  jz      short loc_18001450F
0x1800144a3  cmp     eax, esi
0x1800144a5  jz      short loc_18001450F
0x1800144a7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x1800144ae  jz      loc_180014867
0x1800144b4  xor     esi, esi
0x1800144b6  lea     rdx, aDimstartroutin_4; "DimStartRoutingDomain: AddRoutingDomain"...
0x1800144bd  lea     rcx, [rbp+0A00h+var_A60]
0x1800144c1  mov     word ptr [rbp+0A00h+var_A60], si
0x1800144c5  mov     word ptr [rsp+0B00h+var_A90], si
0x1800144ca  call    FormatRRASErrorString
0x1800144cf  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x1800144d6  jz      loc_180014867
0x1800144dc  lea     rdx, RasDimParamTraceAdminError
0x1800144e3  test    rbx, rbx
0x1800144e6  lea     rax, [rsp+0B00h+var_A90]
0x1800144eb  mov     [rsp+0B00h+var_AD8], rax
0x1800144f0  lea     r9, [rsp+0B00h+var_AA0]
0x1800144f5  cmovnz  r9, rbx
0x1800144f9  mov     [rsp+0B00h+var_AE0], rsi
0x1800144fe  lea     r8, [rbp+0A00h+var_A60]
0x180014502  mov     rcx, r14
0x180014505  call    McTemplateU0zjzz_EventWriteTransfer
0x18001450a  jmp     loc_180014867
0x18001450f  lea     rax, [rsp+0B00h+var_AC4]
0x180014514  mov     [rsp+0B00h+var_AD0], edi
0x180014518  mov     r12d, 1
0x18001451e  mov     [rsp+0B00h+var_AE0], rax; __int64
0x180014523  lea     r9, [rsp+0B00h+var_AD0]
0x180014528  mov     dword ptr [rsp+0B00h+var_AC4+4], r12d
0x18001452d  xor     r8d, r8d
0x180014530  mov     edx, 8000h
0x180014535  mov     rcx, rbx; struct _GUID *
0x180014538  call    GetRoutingDomainConfiguration
0x18001453d  xor     esi, esi
0x18001453f  test    eax, eax
0x180014541  jz      short loc_180014581
0x180014543  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18001454a  jz      loc_180014867
0x180014550  mov     r8d, eax
0x180014553  mov     word ptr [rbp+0A00h+var_A60], si
0x180014557  lea     rdx, aDimstartroutin_8; "DimStartRoutingDomain: GetRoutingDomain"...
0x18001455e  mov     word ptr [rsp+0B00h+var_A90], si
0x180014563  lea     rcx, [rbp+0A00h+var_A60]
0x180014567  call    FormatRRASErrorString
0x18001456c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180014573  jz      loc_180014867
0x180014579  mov     rdx, r15
0x18001457c  jmp     loc_1800144E3
0x180014581  lea     r8, [rsp+0B00h+var_AC4]; void *
0x180014586  mov     edx, r12d; unsigned int
0x180014589  mov     rcx, rbx; struct _GUID *
0x18001458c  call    ?NotifyDDMForRoutingDomainChange@@YAKPEAU_GUID@@KPEAX@Z; NotifyDDMForRoutingDomainChange(_GUID *,ulong,void *)
0x180014591  test    eax, eax
0x180014593  jz      short loc_1800145CA
0x180014595  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18001459c  jz      loc_180014867
0x1800145a2  mov     r8d, eax
0x1800145a5  mov     word ptr [rbp+0A00h+var_A60], si
0x1800145a9  lea     rdx, aDimstartroutin_5; "DimStartRoutingDomain: NotifyDDMForRout"...
0x1800145b0  mov     word ptr [rsp+0B00h+var_A90], si
0x1800145b5  lea     rcx, [rbp+0A00h+var_A60]
0x1800145b9  call    FormatRRASErrorString
0x1800145be  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800145c5  jmp     loc_1800144D6
0x1800145ca  mov     edx, r12d; int
0x1800145cd  mov     rcx, rbx; struct _GUID *
0x1800145d0  call    ?RegisterInterfaceChangeNotifications@@YAKPEAU_GUID@@H@Z; RegisterInterfaceChangeNotifications(_GUID *,int)
0x1800145d5  mov     esi, eax
0x1800145d7  test    eax, eax
0x1800145d9  jz      short loc_180014642
0x1800145db  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x1800145e2  jz      loc_180014A38
0x1800145e8  lea     rdx, aDimstartroutin_9; "DimStartRoutingDomain: RegisterInterfac"...
0x1800145ef  mov     r8d, esi
0x1800145f2  mov     word ptr [rsp+0B00h+var_A90], r13w
0x1800145f8  lea     rcx, [rbp+0A00h+var_A60]
0x1800145fc  mov     word ptr [rbp+0A00h+var_A60], r13w
0x180014601  call    FormatRRASErrorString
0x180014606  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18001460d  jz      loc_180014A38
0x180014613  test    rbx, rbx
0x180014616  lea     rax, [rsp+0B00h+var_A90]
0x18001461b  mov     [rsp+0B00h+var_AD8], rax
0x180014620  lea     r9, [rsp+0B00h+var_AA0]
0x180014625  cmovnz  r9, rbx
0x180014629  mov     [rsp+0B00h+var_AE0], r13
0x18001462e  lea     r8, [rbp+0A00h+var_A60]
0x180014632  mov     rdx, r15
0x180014635  mov     rcx, r14
0x180014638  call    McTemplateU0zjzz_EventWriteTransfer
0x18001463d  jmp     loc_180014A38
0x180014642  mov     ecx, [rsp+0B00h+CompartmentId]; CompartmentId
0x180014646  lea     r8, [rsp+0B00h+lpMem]; struct _DIM_COMPARTMENT_INTERFACE **
0x18001464b  lea     rdx, [rsp+0B00h+var_AC8]; unsigned int *
0x180014650  call    ?DimEnumerateInterfacesFromStack@@YAKIPEAKPEAPEAU_DIM_COMPARTMENT_INTERFACE@@@Z; DimEnumerateInterfacesFromStack(uint,ulong *,_DIM_COMPARTMENT_INTERFACE * *)
0x180014655  mov     esi, eax
0x180014657  test    eax, eax
0x180014659  jz      short loc_180014674
0x18001465b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180014662  jz      loc_180014A38
0x180014668  lea     rdx, aDimstartroutin; "DimStartRoutingDomain: Error %d occured"...
0x18001466f  jmp     loc_1800145EF
0x180014674  mov     r13, [rsp+0B00h+lpMem]
0x180014679  mov     r8, rbx; struct _GUID *
0x18001467c  mov     r9d, [rsp+0B00h+var_AC8]; unsigned int
0x180014681  xor     edx, edx; unsigned __int16 *
0x180014683  mov     rcx, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; this
0x18001468a  mov     [rsp+0B00h+var_AE0], r13; struct _DIM_COMPARTMENT_INTERFACE *
0x18001468f  mov     [rsp+0B00h+var_ABC], r12d
0x180014694  call    ?RegLoadInterfaces@CDimInterfaceTable@@QEAAKPEAGPEAU_GUID@@KPEAU_DIM_COMPARTMENT_INTERFACE@@@Z; CDimInterfaceTable::RegLoadInterfaces(ushort *,_GUID *,ulong,_DIM_COMPARTMENT_INTERFACE *)
0x180014699  xor     edx, edx
0x18001469b  mov     esi, eax
0x18001469d  test    eax, eax
0x18001469f  jz      short loc_18001470A
0x1800146a1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x1800146a8  jz      loc_180014829
0x1800146ae  mov     word ptr [rbp+0A00h+var_A60], dx
0x1800146b2  mov     r8d, eax
0x1800146b5  mov     word ptr [rsp+0B00h+var_A90], dx
0x1800146ba  lea     rdx, aDimstartroutin_13; "DimStartRoutingDomain: Error %d occured"...
0x1800146c1  lea     rcx, [rbp+0A00h+var_A60]
0x1800146c5  call    FormatRRASErrorString
0x1800146ca  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x1800146d1  jz      loc_180014829
0x1800146d7  test    rbx, rbx
0x1800146da  lea     rax, [rsp+0B00h+var_A90]
0x1800146df  mov     [rsp+0B00h+var_AD8], rax
0x1800146e4  lea     r9, [rsp+0B00h+var_AA0]
0x1800146e9  cmovnz  r9, rbx
0x1800146ed  mov     [rsp+0B00h+var_AE0], 0
0x1800146f6  lea     r8, [rbp+0A00h+var_A60]
0x1800146fa  mov     rdx, r15
0x1800146fd  mov     rcx, r14
0x180014700  call    McTemplateU0zjzz_EventWriteTransfer
0x180014705  jmp     loc_180014829
0x18001470a  mov     rcx, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; this
0x180014711  xor     r8d, r8d; bool
0x180014714  mov     rdx, rbx; struct _GUID *
0x180014717  call    ?PlumbRDIkev2Policy@CDimInterfaceTable@@QEAAKPEAU_GUID@@_N@Z; CDimInterfaceTable::PlumbRDIkev2Policy(_GUID *,bool)
0x18001471c  xor     edx, edx
0x18001471e  cmp     eax, 2
0x180014721  mov     esi, edx
0x180014723  cmovnz  esi, eax
0x180014726  test    esi, esi
0x180014728  jz      short loc_18001474F
0x18001472a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180014731  jz      loc_180014829
0x180014737  mov     word ptr [rbp+0A00h+var_A60], dx
0x18001473b  mov     r8d, esi
0x18001473e  mov     word ptr [rsp+0B00h+var_A90], dx
0x180014743  lea     rdx, aDimstartroutin_3; "DimStartRoutingDomain: Error %d occured"...
0x18001474a  jmp     loc_1800146C1
0x18001474f  mov     r12d, edx
0x180014752  mov     esi, edx
0x180014754  cmp     r12d, [rsp+0B00h+var_AC8]
0x180014759  jnb     loc_180014824
0x18001475f  mov     eax, r12d
0x180014762  imul    rcx, rax, 218h
0x180014769  add     r13, rcx
0x18001476c  cmp     [r13+214h], dx
0x180014774  jnz     loc_180014817
0x18001477a  lea     rax, [r13+10h]
0x18001477e  mov     r9, r13
0x180014781  mov     rdx, rax; unsigned __int16 *
0x180014784  mov     [rsp+0B00h+var_AA8], rax
  ... truncated ...
```
