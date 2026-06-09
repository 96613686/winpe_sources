# RRouterAdminRoutingDomainSetConfigEx

- ea: `0x18000eb60`
- end: `0x18000f40a`
- name: `RRouterAdminRoutingDomainSetConfigEx`
- size: `2218`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x180002598`
- `0x180003258`
- `0x18000ad04`
- `0x18000da10`
- `0x18000dbf4`
- `0x18000df70`
- `0x18000eb60`
- `0x180010e38`
- `0x18001382c`
- `0x180013a68`
- `0x180013b80`
- `0x1800161b8`
- `0x180019eb0`
- `0x180035964`
- `0x180035d10`
- `0x180037820`
- `0x180045d40`
- `0x180045d7c`
- `0x180045da4`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ec15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ec15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f3df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f3df`
- `MPRDDM!DDMAdminUpdateQoSPolicies` at `0x18000f2f5`
- `MPRDDM!DDMAdminUpdateQoSPolicies` at `0x18000f2f5`

## string_xrefs

- `0x18000ecc9`: `RRouterAdminRoutingDomainSetConfigEx: GetRoutingDomainConfiguration failed with error: %d`
- `0x18000ed5b`: `RRouterAdminRoutingDomainSetConfigEx: DimDisableS2SForRoutingDomain failed with error: %d`
- `0x18000edbf`: `RRouterAdminRoutingDomainSetConfigEx: GetDialInAdapterNameForRoutingDomain failed with error: %d`
- `0x18000f247`: `RRouterAdminRoutingDomainSetConfigEx: GetDialInAdapterNameForRoutingDomain failed with error: %d`
- `0x18000edf2`: `RRouterAdminRoutingDomainSetConfigEx: DimDisableVpnForRoutingDomain failed with error: %d`
- `0x18000ee6a`: `RRouterAdminRoutingDomainSetConfigEx: Removing IKEv2 policies for all the S2S interfaces.`
- `0x18000eea3`: `RRouterAdminRoutingDomainSetConfigEx: PlumbRDIkev2Policy failed to remove custom IKEv2 policy. Error: %d`
- `0x18000ef23`: `RRouterAdminRoutingDomainSetConfigEx: Plumbing IKEv2 policies for all the S2S interfaces.`
- `0x18000ef5c`: `RRouterAdminRoutingDomainSetConfigEx: PlumbRDIkev2Policy failed to add custom IKEv2 policy. Error: %d`
- `0x18000efcc`: `RRouterAdminRoutingDomainSetConfigEx: Removing IKEv2 policies of S2S interfaces using PSK auth method.`
- `0x18000f005`: `RRouterAdminRoutingDomainSetConfigEx: PlumbIkev2PskPolicy failed to remove PSK IKEv2 policy. Error: %d`
- `0x18000f0ab`: `RRouterAdminRoutingDomainSetConfigEx: PlumbIkev2PskPolicy failed to remove PSK IKEv2 policy. Error: %d`
- `0x18000f075`: `RRouterAdminRoutingDomainSetConfigEx: Plumbing IKEv2 policies of S2S interfaces using PSK auth method.`
- `0x18000f1a8`: `RRouterAdminRoutingDomainSetConfigEx: DimEnableS2SForRoutingDomain failed with error: %d`
- `0x18000f275`: `RRouterAdminRoutingDomainSetConfigEx: DimEnableVpnForRoutingDomain failed with error: %d`
- `0x18000f2dc`: `RRouterAdminRoutingDomainSetConfigEx: GetRoutingDomainConfiguration for qos policies failed with error: %d`
- `0x18000f317`: `RRouterAdminRoutingDomainSetConfigEx: DDMAdminUpdateQoSPolicies failed with error: %d`

## pseudocode

```c
__int64 __fastcall RRouterAdminRoutingDomainSetConfigEx(__int64 a1, __int64 a2)
{
  unsigned int DialInAdapterNameForRoutingDomain; // ebx
  bool v5; // zf
  int v6; // r13d
  int v7; // r12d
  __int64 v8; // rcx
  unsigned int RoutingDomainConfiguration; // eax
  const wchar_t *v10; // rdx
  __int128 *v11; // r9
  char v12; // al
  unsigned int v13; // eax
  __int128 *v14; // r9
  unsigned int v15; // eax
  __int128 *v16; // r9
  __int128 *v17; // r9
  unsigned int v18; // eax
  __int128 *v19; // r9
  __int128 *v20; // r9
  unsigned int v21; // eax
  __int128 *v22; // r9
  __int128 *v23; // r9
  __int128 *v24; // r9
  unsigned int i; // r12d
  __int64 v26; // rdx
  __int64 v27; // rax
  char v28; // cl
  char v29; // al
  const wchar_t *v30; // rdx
  __int128 *v31; // r9
  unsigned int v32; // edx
  unsigned int v33; // [rsp+30h] [rbp-D0h] BYREF
  int v34; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v35; // [rsp+38h] [rbp-C8h] BYREF
  int v36; // [rsp+40h] [rbp-C0h]
  int v37; // [rsp+44h] [rbp-BCh]
  _QWORD v38[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v39; // [rsp+58h] [rbp-A8h]
  int v40; // [rsp+5Ch] [rbp-A4h]
  __int64 v41; // [rsp+60h] [rbp-A0h]
  __int128 v42; // [rsp+68h] [rbp-98h] BYREF
  GUID ActivityId; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44[4]; // [rsp+88h] [rbp-78h] BYREF
  int v45; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v46; // [rsp+ACh] [rbp-54h]
  __int128 v47; // [rsp+BCh] [rbp-44h]
  int v48; // [rsp+CCh] [rbp-34h]
  int v49; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v50[2044]; // [rsp+D4h] [rbp-2Ch] BYREF
  unsigned __int16 Destination; // [rsp+8D0h] [rbp+7D0h] BYREF
  _BYTE v52[510]; // [rsp+8D2h] [rbp+7D2h] BYREF

  LODWORD(v35) = 0;
  memset(v44, 0, 28);
  v33 = 0;
  v34 = 0;
  v49 = 0;
  ActivityId = 0;
  v42 = 0;
  memset_0(v50, 0, sizeof(v50));
  v45 = 0;
  v46 = 0;
  v48 = 0;
  v47 = 0;
  if ( !(unsigned int)IsLRPC() )
    return 5;
  if ( !a2 )
    return 87;
  if ( *(_BYTE *)a2 != 1 )
    return 50;
  DialInAdapterNameForRoutingDomain = 0;
  EnterCriticalSection(&CriticalSection);
  v5 = *(_BYTE *)a2 == 1;
  v33 = *(_DWORD *)(a2 + 540);
  if ( v5 )
  {
    v6 = *(_DWORD *)(a2 + 652);
    v37 = SetActivityId((LPGUID)(a2 + 524));
    v7 = v37;
    DialInAdapterNameForRoutingDomain = IsRoutingDomainAvailable((struct _GUID *)(a2 + 524), &v34);
    if ( !DialInAdapterNameForRoutingDomain )
    {
      if ( !v34 )
      {
        DialInAdapterNameForRoutingDomain = 4317;
        goto LABEL_128;
      }
      v34 = 0;
      v36 = v6 & 0x8000;
      if ( (v6 & 0x8000) != 0 )
      {
        HIDWORD(v35) = 4;
        RoutingDomainConfiguration = GetRoutingDomainConfiguration((struct _GUID *)(a2 + 524), (__int64)&v35);
        DialInAdapterNameForRoutingDomain = RoutingDomainConfiguration;
        if ( RoutingDomainConfiguration )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
            goto LABEL_128;
          v10 = L"RRouterAdminRoutingDomainSetConfigEx: GetRoutingDomainConfiguration failed with error: %d";
          goto LABEL_15;
        }
        v12 = v33;
        v34 = 1;
        if ( (v33 & 0x24) == 0 && (v35 & 0x24) != 0 )
        {
          RoutingDomainConfiguration = DimDisableS2SForRoutingDomain((struct _GUID *)(a2 + 524), v33);
          DialInAdapterNameForRoutingDomain = RoutingDomainConfiguration;
          if ( RoutingDomainConfiguration )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
              goto LABEL_128;
            v10 = L"RRouterAdminRoutingDomainSetConfigEx: DimDisableS2SForRoutingDomain failed with error: %d";
LABEL_15:
            LOWORD(v45) = 0;
            LOWORD(v49) = 0;
            FormatRRASErrorString(&v49, v10, RoutingDomainConfiguration);
            if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
              goto LABEL_128;
LABEL_16:
            v11 = &v42;
            if ( a2 != -524 )
              LODWORD(v11) = a2 + 524;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceError,
              (unsigned int)&v49,
              (_DWORD)v11,
              0,
              (__int64)&v45);
            goto LABEL_128;
          }
          v12 = v33;
          v34 = 0;
        }
        if ( (v12 & 9) == 0 && (v35 & 9) != 0 )
        {
          Destination = 0;
          memset_0(v52, 0, sizeof(v52));
          RoutingDomainConfiguration = GetDialInAdapterNameForRoutingDomain((struct _GUID *)(a2 + 524), &Destination);
          DialInAdapterNameForRoutingDomain = RoutingDomainConfiguration;
          if ( RoutingDomainConfiguration )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
              goto LABEL_128;
            v10 = L"RRouterAdminRoutingDomainSetConfigEx: GetDialInAdapterNameForRoutingDomain failed with error: %d";
            goto LABEL_15;
          }
          RoutingDomainConfiguration = DimDisableVpnForRoutingDomain((struct _GUID *)(a2 + 524), &Destination, v33);
          DialInAdapterNameForRoutingDomain = RoutingDomainConfiguration;
          if ( RoutingDomainConfiguration )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
              goto LABEL_128;
            v10 = L"RRouterAdminRoutingDomainSetConfigEx: DimDisableVpnForRoutingDomain failed with error: %d";
            goto LABEL_15;
          }
          v34 = 0;
        }
      }
      *(_DWORD *)(a2 + 652) &= 0xFFFFFF4F;
      v13 = SetRoutingDomainConfigObject(v8, a2);
      *(_DWORD *)(a2 + 652) = v6;
      DialInAdapterNameForRoutingDomain = v13;
      if ( v13 )
        goto LABEL_128;
      if ( (v6 & 8) != 0 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
        {
          LOWORD(v45) = 0;
          v14 = &v42;
          if ( a2 != -524 )
            LODWORD(v14) = a2 + 524;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceInfo,
            (unsigned int)L"RRouterAdminRoutingDomainSetConfigEx: Removing IKEv2 policies for all the S2S interfaces.",
            (_DWORD)v14,
            0,
            (__int64)&v45);
        }
        v15 = CDimInterfaceTable::PlumbRDIkev2Policy(g_pCDimInterfaceTable, (struct _GUID *)(a2 + 524), 1);
        if ( v15 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            LOWORD(v49) = 0;
            LOWORD(v45) = 0;
            FormatRRASErrorString(
              &v49,
              L"RRouterAdminRoutingDomainSetConfigEx: PlumbRDIkev2Policy failed to remove custom IKEv2 policy. Error: %d",
              v15);
            if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
            {
              v16 = &v42;
              if ( a2 != -524 )
                LODWORD(v16) = a2 + 524;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDimParamTraceError,
                (unsigned int)&v49,
                (_DWORD)v16,
                0,
                (__int64)&v45);
            }
          }
        }
        if ( (unsigned int)IsCustomIkev2PolicyConfiguredForRoutingDomain((struct _GUID *)(a2 + 524)) )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
          {
            LOWORD(v45) = 0;
            v17 = &v42;
            if ( a2 != -524 )
              LODWORD(v17) = a2 + 524;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceInfo,
              (unsigned int)L"RRouterAdminRoutingDomainSetConfigEx: Plumbing IKEv2 policies for all the S2S interfaces.",
              (_DWORD)v17,
              0,
              (__int64)&v45);
          }
          v18 = CDimInterfaceTable::PlumbRDIkev2Policy(g_pCDimInterfaceTable, (struct _GUID *)(a2 + 524), 0);
          if ( v18 )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
            {
              LOWORD(v49) = 0;
              LOWORD(v45) = 0;
              FormatRRASErrorString(
                &v49,
                L"RRouterAdminRoutingDomainSetConfigEx: PlumbRDIkev2Policy failed to add custom IKEv2 policy. Error: %d",
                v18);
              if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
              {
                v19 = &v42;
                if ( a2 != -524 )
                  LODWORD(v19) = a2 + 524;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasDimParamTraceError,
                  (unsigned int)&v49,
                  (_DWORD)v19,
                  0,
                  (__int64)&v45);
              }
            }
          }
        }
        if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
        {
          LOWORD(v45) = 0;
          v20 = &v42;
          if ( a2 != -524 )
            LODWORD(v20) = a2 + 524;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceInfo,
            (unsigned int)L"RRouterAdminRoutingDomainSetConfigEx: Removing IKEv2 policies of S2S interfaces using PSK auth method.",
            (_DWORD)v20,
            0,
            (__int64)&v45);
        }
        v21 = CDimInterfaceTable::PlumbIkev2PskPolicy(g_pCDimInterfaceTable, (const struct _GUID *)(a2 + 524), 1);
        if ( v21 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            LOWORD(v49) = 0;
            LOWORD(v45) = 0;
            FormatRRASErrorString(
              &v49,
              L"RRouterAdminRoutingDomainSetConfigEx: PlumbIkev2PskPolicy failed to remove PSK IKEv2 policy. Error: %d",
              v21);
            if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
            {
              v22 = &v42;
              if ( a2 != -524 )
                LODWORD(v22) = a2 + 524;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDimParamTraceError,
                (unsigned int)&v49,
                (_DWORD)v22,
                0,
                (__int64)&v45);
            }
          }
        }
        if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
        {
          LOWORD(v45) = 0;
          v23 = &v42;
          if ( a2 != -524 )
            LODWORD(v23) = a2 + 524;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceInfo,
            (unsigned int)L"RRouterAdminRoutingDomainSetConfigEx: Plumbing IKEv2 policies of S2S interfaces using PSK auth method.",
            (_DWORD)v23,
            0,
            (__int64)&v45);
        }
        DialInAdapterNameForRoutingDomain = CDimInterfaceTable::PlumbIkev2PskPolicy(
                                              g_pCDimInterfaceTable,
                                              (const struct _GUID *)(a2 + 524),
                                              0);
        if ( DialInAdapterNameForRoutingDomain )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            LOWORD(v49) = 0;
            LOWORD(v45) = 0;
            FormatRRASErrorString(
              &v49,
              L"RRouterAdminRoutingDomainSetConfigEx: PlumbIkev2PskPolicy failed to remove PSK IKEv2 policy. Error: %d",
              DialInAdapterNameForRoutingDomain);
            if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
            {
              v24 = &v42;
              if ( a2 != -524 )
                LODWORD(v24) = a2 + 524;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDimParamTraceError,
                (unsigned int)&v49,
                (_DWORD)v24,
                0,
                (__int64)&v45);
            }
          }
          DialInAdapterNameForRoutingDomain = 0;
        }
      }
      if ( (*(_BYTE *)(a2 + 652) & 0xB0) != 0 )
      {
        for ( i = 0; i < *(_DWORD *)(a2 + 808); ++i )
        {
          v26 = *(_QWORD *)(a2 + 816);
          v38[0] = 0;
          v38[1] = 0;
          v39 = 0;
          v40 = *(_DWORD *)(v26 + 16LL * i + 4);
          v27 = *(_QWORD *)(v26 + 16LL * i + 8);
          LODWORD(v26) = *(_DWORD *)(v26 + 16LL * i);
          v41 = v27;
          DialInAdapterNameForRoutingDomain = RRouterInterfaceTransportSetGlobalInfoInternal(
                                                (void *)(2LL * i),
                                                v26,
                                                (struct _DIM_INTERFACE_CONTAINER *)v38,
                                                (struct _GUID *)(a2 + 524));
          if ( DialInAdapterNameForRoutingDomain )
            goto LABEL_128;
        }
        v7 = v37;
      }
      if ( v36 )
      {
        v28 = v33;
        v29 = v35;
        if ( (v33 & 0x24) != 0 && (v35 & 0x24) == 0 )
        {
          DialInAdapterNameForRoutingDomain = DimEnableS2SForRoutingDomain((struct _GUID *)(a2 + 524));
          if ( DialInAdapterNameForRoutingDomain )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
              goto LABEL_128;
            v30 = L"RRouterAdminRoutingDomainSetConfigEx: DimEnableS2SForRoutingDomain failed with error: %d";
            goto LABEL_90;
          }
          v29 = v35;
          v28 = v33;
        }
        if ( (v28 & 9) != 0 && (v29 & 1) == 0 && (v29 & 8) == 0 )
        {
          Destination = 0;
          memset_0(v52, 0, sizeof(v52));
          DialInAdapterNameForRoutingDomain = GetDialInAdapterNameForRoutingDomain(
                                                (struct _GUID *)(a2 + 524),
                                                &Destination);
          if ( DialInAdapterNameForRoutingDomain )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
              goto LABEL_128;
            v30 = L"RRouterAdminRoutingDomainSetConfigEx: GetDialInAdapterNameForRoutingDomain failed with error: %d";
LABEL_90:
            LOWORD(v45) = 0;
            LOWORD(v49) = 0;
            FormatRRASErrorString(&v49, v30, DialInAdapterNameForRoutingDomain);
            if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
              goto LABEL_128;
            goto LABEL_16;
          }
          DialInAdapterNameForRoutingDomain = DimEnableVpnForRoutingDomain((struct _GUID *)(a2 + 524), &Destination);
          if ( DialInAdapterNameForRoutingDomain )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
              goto LABEL_128;
            v30 = L"RRouterAdminRoutingDomainSetConfigEx: DimEnableVpnForRoutingDomain failed with error: %d";
            goto LABEL_90;
          }
        }
      }
      if ( (v6 & 0x4000) != 0 )
        NotifyDDMForRoutingDomainChange((struct _GUID *)(a2 + 524), 8u, 0);
      if ( (v6 & 0x2000) != 0 )
      {
        v36 = 28;
        DialInAdapterNameForRoutingDomain = GetRoutingDomainConfiguration((struct _GUID *)(a2 + 524), (__int64)v44);
        if ( DialInAdapterNameForRoutingDomain )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
            goto LABEL_128;
          v30 = L"RRouterAdminRoutingDomainSetConfigEx: GetRoutingDomainConfiguration for qos policies failed with error: %d";
          goto LABEL_90;
        }
        if ( (gbldwDIMComponentsLoaded & 4) == 0 )
        {
          DialInAdapterNameForRoutingDomain = 903;
LABEL_112:
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            LOWORD(v49) = 0;
            LOWORD(v45) = 0;
            FormatRRASErrorString(
              &v49,
              L"RRouterAdminRoutingDomainSetConfigEx: DDMAdminUpdateQoSPolicies failed with error: %d",
              DialInAdapterNameForRoutingDomain);
            if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
            {
              v31 = &v42;
              if ( a2 != -524 )
                LODWORD(v31) = a2 + 524;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDimParamTraceError,
                (unsigned int)&v49,
                (_DWORD)v31,
                0,
                (__int64)&v45);
            }
          }
LABEL_126:
          if ( v7 )
            ReSetActivityId(&ActivityId);
          goto LABEL_128;
        }
        DialInAdapterNameForRoutingDomain = DDMAdminUpdateQoSPolicies(v44);
        if ( DialInAdapterNameForRoutingDomain )
          goto LABEL_112;
      }
      if ( (v6 & 3) != 0 )
      {
        if ( (v6 & 1) != 0 )
          NotifyDDMForRoutingDomainChange((struct _GUID *)(a2 + 524), 3u, 0);
        if ( (v6 & 2) != 0 )
        {
          v32 = 6;
          if ( *(_DWORD *)(a2 + 688) )
            v32 = 4;
          NotifyDDMForRoutingDomainChange((struct _GUID *)(a2 + 524), v32, 0);
        }
      }
      if ( v34 )
        NotifyDDMForRoutingDomainChange((struct _GUID *)(a2 + 524), 7u, &v33);
      goto LABEL_126;
    }
  }
LABEL_128:
  LeaveCriticalSection(&CriticalSection);
  return DialInAdapterNameForRoutingDomain;
}

```

## disassembly

```asm
0x18000eb60  push    rbp
0x18000eb62  push    rbx
0x18000eb63  push    rsi
0x18000eb64  push    rdi
0x18000eb65  push    r12
0x18000eb67  push    r13
0x18000eb69  push    r14
0x18000eb6b  push    r15
0x18000eb6d  lea     rbp, [rsp-9E8h]
0x18000eb75  sub     rsp, 0AE8h
0x18000eb7c  mov     rax, cs:__security_cookie
0x18000eb83  xor     rax, rsp
0x18000eb86  mov     [rbp+0A20h+var_50], rax
0x18000eb8d  xorps   xmm0, xmm0
0x18000eb90  lea     rcx, [rbp+0A20h+var_A4C]; void *
0x18000eb94  xor     esi, esi
0x18000eb96  mov     r15, rdx
0x18000eb99  xorps   xmm1, xmm1
0x18000eb9c  mov     dword ptr [rsp+0B20h+var_AE8], esi
0x18000eba0  movups  xmmword ptr [rbp+0A20h+var_A98], xmm0
0x18000eba4  xor     edx, edx; Val
0x18000eba6  mov     [rsp+0B20h+var_AF0], esi
0x18000ebaa  mov     r8d, 7FCh; Size
0x18000ebb0  mov     [rsp+0B20h+var_AEC], esi
0x18000ebb4  movups  xmmword ptr [rbp+0A20h+var_A98+0Ch], xmm0
0x18000ebb8  mov     [rbp+0A20h+var_A50], esi
0x18000ebbb  movups  xmmword ptr [rsp+0B20h+ActivityId.Data1], xmm0
0x18000ebc0  movups  [rsp+0B20h+var_AB8], xmm1
0x18000ebc5  call    memset_0
0x18000ebca  xorps   xmm0, xmm0
0x18000ebcd  mov     [rbp+0A20h+var_A78], esi
0x18000ebd0  xor     eax, eax
0x18000ebd2  movups  [rbp+0A20h+var_A74], xmm0
0x18000ebd6  mov     [rbp+0A20h+var_A54], eax
0x18000ebd9  movups  [rbp+0A20h+var_A64], xmm0
0x18000ebdd  call    ?IsLRPC@@YAHXZ; IsLRPC(void)
0x18000ebe2  test    eax, eax
0x18000ebe4  jnz     short loc_18000EBEE
0x18000ebe6  lea     eax, [rsi+5]
0x18000ebe9  jmp     loc_18000F3E7
0x18000ebee  test    r15, r15
0x18000ebf1  jnz     short loc_18000EBFC
0x18000ebf3  lea     eax, [r15+57h]
0x18000ebf7  jmp     loc_18000F3E7
0x18000ebfc  cmp     byte ptr [r15], 1
0x18000ec00  jz      short loc_18000EC0C
0x18000ec02  mov     eax, 32h ; '2'
0x18000ec07  jmp     loc_18000F3E7
0x18000ec0c  lea     rcx, CriticalSection; lpCriticalSection
0x18000ec13  mov     ebx, esi
0x18000ec15  call    cs:__imp_EnterCriticalSection
0x18000ec1b  cmp     byte ptr [r15], 1
0x18000ec1f  mov     eax, [r15+21Ch]
0x18000ec26  mov     [rsp+0B20h+var_AF0], eax
0x18000ec2a  jnz     loc_18000F3D8
0x18000ec30  mov     r13d, [r15+28Ch]
0x18000ec37  lea     rdi, [r15+20Ch]
0x18000ec3e  mov     rcx, rdi; ActivityId
0x18000ec41  lea     rdx, [rsp+0B20h+ActivityId]
0x18000ec46  call    SetActivityId
0x18000ec4b  lea     rdx, [rsp+0B20h+var_AEC]; int *
0x18000ec50  mov     [rsp+0B20h+var_ADC], eax
0x18000ec54  mov     rcx, rdi; struct _GUID *
0x18000ec57  mov     r12d, eax
0x18000ec5a  call    ?IsRoutingDomainAvailable@@YAKPEAU_GUID@@PEAH@Z; IsRoutingDomainAvailable(_GUID *,int *)
0x18000ec5f  mov     ebx, eax
0x18000ec61  test    eax, eax
0x18000ec63  jnz     loc_18000F3D8
0x18000ec69  cmp     [rsp+0B20h+var_AEC], esi
0x18000ec6d  jnz     short loc_18000EC79
0x18000ec6f  mov     ebx, 10DDh
0x18000ec74  jmp     loc_18000F3D8
0x18000ec79  mov     eax, r13d
0x18000ec7c  mov     [rsp+0B20h+var_AEC], esi
0x18000ec80  mov     edx, 8000h
0x18000ec85  mov     r14d, 4
0x18000ec8b  and     eax, edx
0x18000ec8d  mov     [rsp+0B20h+var_AE0], eax
0x18000ec91  jz      loc_18000EE02
0x18000ec97  lea     rax, [rsp+0B20h+var_AE8]
0x18000ec9c  mov     dword ptr [rsp+0B20h+var_AE8+4], r14d
0x18000eca1  lea     r9, [rsp+0B20h+var_AE8+4]
0x18000eca6  mov     [rsp+0B20h+var_B00], rax; __int64
0x18000ecab  xor     r8d, r8d
0x18000ecae  mov     rcx, rdi; struct _GUID *
0x18000ecb1  call    GetRoutingDomainConfiguration
0x18000ecb6  mov     ebx, eax
0x18000ecb8  test    eax, eax
0x18000ecba  jz      short loc_18000ED27
0x18000ecbc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000ecc3  jz      loc_18000F3D8
0x18000ecc9  lea     rdx, aRrouteradminro_4; "RRouterAdminRoutingDomainSetConfigEx: G"...
0x18000ecd0  mov     r8d, eax
0x18000ecd3  mov     word ptr [rbp+0A20h+var_A78], si
0x18000ecd7  lea     rcx, [rbp+0A20h+var_A50]
0x18000ecdb  mov     word ptr [rbp+0A20h+var_A50], si
0x18000ecdf  call    FormatRRASErrorString
0x18000ece4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000eceb  jz      loc_18000F3D8
0x18000ecf1  lea     rax, [rbp+0A20h+var_A78]
0x18000ecf5  mov     [rsp+0B20h+var_AF8], rax
0x18000ecfa  lea     rdx, RasDimParamTraceError
0x18000ed01  mov     [rsp+0B20h+var_B00], rsi
0x18000ed06  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ed0d  test    rdi, rdi
0x18000ed10  lea     r9, [rsp+0B20h+var_AB8]
0x18000ed15  lea     r8, [rbp+0A20h+var_A50]
0x18000ed19  cmovnz  r9, rdi
0x18000ed1d  call    McTemplateU0zjzz_EventWriteTransfer
0x18000ed22  jmp     loc_18000F3D8
0x18000ed27  mov     eax, [rsp+0B20h+var_AF0]
0x18000ed2b  mov     [rsp+0B20h+var_AEC], 1
0x18000ed33  test    al, 24h
0x18000ed35  jnz     short loc_18000ED6F
0x18000ed37  test    byte ptr [rsp+0B20h+var_AE8], 24h
0x18000ed3c  jz      short loc_18000ED6F
0x18000ed3e  mov     edx, eax; unsigned int
0x18000ed40  mov     rcx, rdi; struct _GUID *
0x18000ed43  call    ?DimDisableS2SForRoutingDomain@@YAKPEAU_GUID@@K@Z; DimDisableS2SForRoutingDomain(_GUID *,ulong)
0x18000ed48  mov     ebx, eax
0x18000ed4a  test    eax, eax
0x18000ed4c  jz      short loc_18000ED67
0x18000ed4e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000ed55  jz      loc_18000F3D8
0x18000ed5b  lea     rdx, aRrouteradminro_11; "RRouterAdminRoutingDomainSetConfigEx: D"...
0x18000ed62  jmp     loc_18000ECD0
0x18000ed67  mov     eax, [rsp+0B20h+var_AF0]
0x18000ed6b  mov     [rsp+0B20h+var_AEC], esi
0x18000ed6f  test    al, 9
0x18000ed71  jnz     loc_18000EE02
0x18000ed77  test    byte ptr [rsp+0B20h+var_AE8], 9
0x18000ed7c  jz      loc_18000EE02
0x18000ed82  xor     edx, edx; Val
0x18000ed84  mov     [rbp+0A20h+Destination], si
0x18000ed8b  mov     r8d, 1FEh; Size
0x18000ed91  lea     rcx, [rbp+0A20h+var_24E]; void *
0x18000ed98  call    memset_0
0x18000ed9d  lea     rdx, [rbp+0A20h+Destination]; Destination
0x18000eda4  mov     rcx, rdi; struct _GUID *
0x18000eda7  call    GetDialInAdapterNameForRoutingDomain
0x18000edac  mov     ebx, eax
0x18000edae  test    eax, eax
0x18000edb0  jz      short loc_18000EDCB
0x18000edb2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000edb9  jz      loc_18000F3D8
0x18000edbf  lea     rdx, aRrouteradminro_8; "RRouterAdminRoutingDomainSetConfigEx: G"...
0x18000edc6  jmp     loc_18000ECD0
0x18000edcb  mov     r8d, [rsp+0B20h+var_AF0]; unsigned int
0x18000edd0  lea     rdx, [rbp+0A20h+Destination]; unsigned __int16 *
0x18000edd7  mov     rcx, rdi; struct _GUID *
0x18000edda  call    ?DimDisableVpnForRoutingDomain@@YAKPEAU_GUID@@PEAGK@Z; DimDisableVpnForRoutingDomain(_GUID *,ushort *,ulong)
0x18000eddf  mov     ebx, eax
0x18000ede1  test    eax, eax
0x18000ede3  jz      short loc_18000EDFE
0x18000ede5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000edec  jz      loc_18000F3D8
0x18000edf2  lea     rdx, aRrouteradminro_10; "RRouterAdminRoutingDomainSetConfigEx: D"...
0x18000edf9  jmp     loc_18000ECD0
0x18000edfe  mov     [rsp+0B20h+var_AEC], esi
0x18000ee02  and     dword ptr [r15+28Ch], 0FFFFFF4Fh
0x18000ee0d  mov     rdx, r15
0x18000ee10  call    SetRoutingDomainConfigObject
0x18000ee15  mov     [r15+28Ch], r13d
0x18000ee1c  mov     ebx, eax
0x18000ee1e  test    eax, eax
0x18000ee20  jnz     loc_18000F3D8
0x18000ee26  lea     r14, RasDimParamTraceError
0x18000ee2d  lea     rsi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ee34  test    r13b, 8
0x18000ee38  jz      loc_18000F0FE
0x18000ee3e  xor     ebx, ebx
0x18000ee40  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18000ee47  jz      short loc_18000EE7D
0x18000ee49  test    rdi, rdi
0x18000ee4c  mov     word ptr [rbp+0A20h+var_A78], bx
0x18000ee50  lea     rax, [rbp+0A20h+var_A78]
0x18000ee54  mov     rcx, rsi
0x18000ee57  mov     [rsp+0B20h+var_AF8], rax
0x18000ee5c  lea     r9, [rsp+0B20h+var_AB8]
0x18000ee61  cmovnz  r9, rdi
0x18000ee65  mov     [rsp+0B20h+var_B00], rbx
0x18000ee6a  lea     r8, aRrouteradminro_7; "RRouterAdminRoutingDomainSetConfigEx: R"...
0x18000ee71  lea     rdx, RasDimParamTraceInfo
0x18000ee78  call    McTemplateU0zjzz_EventWriteTransfer
0x18000ee7d  mov     rcx, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; this
0x18000ee84  mov     r8b, 1; bool
0x18000ee87  mov     rdx, rdi; struct _GUID *
0x18000ee8a  call    ?PlumbRDIkev2Policy@CDimInterfaceTable@@QEAAKPEAU_GUID@@_N@Z; CDimInterfaceTable::PlumbRDIkev2Policy(_GUID *,bool)
0x18000ee8f  test    eax, eax
0x18000ee91  jz      short loc_18000EEE9
0x18000ee93  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000ee9a  jz      short loc_18000EEE9
0x18000ee9c  mov     r8d, eax
0x18000ee9f  mov     word ptr [rbp+0A20h+var_A50], bx
0x18000eea3  lea     rdx, aRrouteradminro_12; "RRouterAdminRoutingDomainSetConfigEx: P"...
0x18000eeaa  mov     word ptr [rbp+0A20h+var_A78], bx
0x18000eeae  lea     rcx, [rbp+0A20h+var_A50]
0x18000eeb2  call    FormatRRASErrorString
0x18000eeb7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000eebe  jz      short loc_18000EEE9
0x18000eec0  test    rdi, rdi
0x18000eec3  lea     rax, [rbp+0A20h+var_A78]
0x18000eec7  mov     [rsp+0B20h+var_AF8], rax
0x18000eecc  lea     r9, [rsp+0B20h+var_AB8]
0x18000eed1  cmovnz  r9, rdi
0x18000eed5  mov     [rsp+0B20h+var_B00], rbx
0x18000eeda  lea     r8, [rbp+0A20h+var_A50]
0x18000eede  mov     rdx, r14
0x18000eee1  mov     rcx, rsi
0x18000eee4  call    McTemplateU0zjzz_EventWriteTransfer
0x18000eee9  mov     rcx, rdi; struct _GUID *
0x18000eeec  call    ?IsCustomIkev2PolicyConfiguredForRoutingDomain@@YAHPEAU_GUID@@@Z; IsCustomIkev2PolicyConfiguredForRoutingDomain(_GUID *)
0x18000eef1  test    eax, eax
0x18000eef3  jz      loc_18000EFA2
0x18000eef9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18000ef00  jz      short loc_18000EF36
0x18000ef02  test    rdi, rdi
0x18000ef05  mov     word ptr [rbp+0A20h+var_A78], bx
0x18000ef09  lea     rax, [rbp+0A20h+var_A78]
0x18000ef0d  mov     rcx, rsi
0x18000ef10  mov     [rsp+0B20h+var_AF8], rax
0x18000ef15  lea     r9, [rsp+0B20h+var_AB8]
0x18000ef1a  cmovnz  r9, rdi
0x18000ef1e  mov     [rsp+0B20h+var_B00], rbx
0x18000ef23  lea     r8, aRrouteradminro_0; "RRouterAdminRoutingDomainSetConfigEx: P"...
0x18000ef2a  lea     rdx, RasDimParamTraceInfo
0x18000ef31  call    McTemplateU0zjzz_EventWriteTransfer
0x18000ef36  mov     rcx, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; this
0x18000ef3d  xor     r8d, r8d; bool
0x18000ef40  mov     rdx, rdi; struct _GUID *
0x18000ef43  call    ?PlumbRDIkev2Policy@CDimInterfaceTable@@QEAAKPEAU_GUID@@_N@Z; CDimInterfaceTable::PlumbRDIkev2Policy(_GUID *,bool)
0x18000ef48  test    eax, eax
0x18000ef4a  jz      short loc_18000EFA2
0x18000ef4c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000ef53  jz      short loc_18000EFA2
0x18000ef55  mov     r8d, eax
0x18000ef58  mov     word ptr [rbp+0A20h+var_A50], bx
0x18000ef5c  lea     rdx, aRrouteradminro_3; "RRouterAdminRoutingDomainSetConfigEx: P"...
0x18000ef63  mov     word ptr [rbp+0A20h+var_A78], bx
0x18000ef67  lea     rcx, [rbp+0A20h+var_A50]
0x18000ef6b  call    FormatRRASErrorString
0x18000ef70  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000ef77  jz      short loc_18000EFA2
0x18000ef79  test    rdi, rdi
0x18000ef7c  lea     rax, [rbp+0A20h+var_A78]
0x18000ef80  mov     [rsp+0B20h+var_AF8], rax
0x18000ef85  lea     r9, [rsp+0B20h+var_AB8]
0x18000ef8a  cmovnz  r9, rdi
0x18000ef8e  mov     [rsp+0B20h+var_B00], rbx
0x18000ef93  lea     r8, [rbp+0A20h+var_A50]
0x18000ef97  mov     rdx, r14
0x18000ef9a  mov     rcx, rsi
0x18000ef9d  call    McTemplateU0zjzz_EventWriteTransfer
0x18000efa2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18000efa9  jz      short loc_18000EFDF
0x18000efab  test    rdi, rdi
0x18000efae  mov     word ptr [rbp+0A20h+var_A78], bx
0x18000efb2  lea     rax, [rbp+0A20h+var_A78]
0x18000efb6  mov     rcx, rsi
0x18000efb9  mov     [rsp+0B20h+var_AF8], rax
0x18000efbe  lea     r9, [rsp+0B20h+var_AB8]
0x18000efc3  cmovnz  r9, rdi
0x18000efc7  mov     [rsp+0B20h+var_B00], rbx
0x18000efcc  lea     r8, aRrouteradminro_1; "RRouterAdminRoutingDomainSetConfigEx: R"...
0x18000efd3  lea     rdx, RasDimParamTraceInfo
0x18000efda  call    McTemplateU0zjzz_EventWriteTransfer
0x18000efdf  mov     rcx, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; this
0x18000efe6  mov     r8b, 1; bool
0x18000efe9  mov     rdx, rdi; struct _GUID *
0x18000efec  call    ?PlumbIkev2PskPolicy@CDimInterfaceTable@@QEAAKAEBU_GUID@@_N@Z; CDimInterfaceTable::PlumbIkev2PskPolicy(_GUID const &,bool)
0x18000eff1  test    eax, eax
0x18000eff3  jz      short loc_18000F04B
0x18000eff5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000effc  jz      short loc_18000F04B
0x18000effe  mov     r8d, eax
0x18000f001  mov     word ptr [rbp+0A20h+var_A50], bx
0x18000f005  lea     rdx, aRrouteradminro_9; "RRouterAdminRoutingDomainSetConfigEx: P"...
0x18000f00c  mov     word ptr [rbp+0A20h+var_A78], bx
0x18000f010  lea     rcx, [rbp+0A20h+var_A50]
0x18000f014  call    FormatRRASErrorString
0x18000f019  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000f020  jz      short loc_18000F04B
0x18000f022  test    rdi, rdi
0x18000f025  lea     rax, [rbp+0A20h+var_A78]
0x18000f029  mov     [rsp+0B20h+var_AF8], rax
0x18000f02e  lea     r9, [rsp+0B20h+var_AB8]
0x18000f033  cmovnz  r9, rdi
0x18000f037  mov     [rsp+0B20h+var_B00], rbx
0x18000f03c  lea     r8, [rbp+0A20h+var_A50]
0x18000f040  mov     rdx, r14
0x18000f043  mov     rcx, rsi
0x18000f046  call    McTemplateU0zjzz_EventWriteTransfer
0x18000f04b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18000f052  jz      short loc_18000F088
0x18000f054  test    rdi, rdi
0x18000f057  mov     word ptr [rbp+0A20h+var_A78], bx
0x18000f05b  lea     rax, [rbp+0A20h+var_A78]
0x18000f05f  mov     rcx, rsi
0x18000f062  mov     [rsp+0B20h+var_AF8], rax
0x18000f067  lea     r9, [rsp+0B20h+var_AB8]
  ... truncated ...
```
