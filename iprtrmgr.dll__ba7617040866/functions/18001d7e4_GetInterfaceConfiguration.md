# GetInterfaceConfiguration

- ea: `0x18001d7e4`
- end: `0x18001e2c9`
- name: `GetInterfaceConfiguration`
- size: `2789`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800263b8`
- `0x18003cce8`

## callees

- `0x18000f5d0`
- `0x180011790`
- `0x180014198`
- `0x1800142d8`
- `0x18001450c`
- `0x180017fc0`
- `0x18001d7e4`
- `0x18001e2d0`
- `0x180040e14`
- `0x18004ec14`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18001db31`
- `ntdll!RtlReleaseResource` at `0x18001db98`
- `ntdll!RtlReleaseResource` at `0x18001db31`
- `ntdll!RtlReleaseResource` at `0x18001db98`
- `ntdll!RtlAcquireResourceShared` at `0x18001d95b`
- `ntdll!RtlAcquireResourceShared` at `0x18001d95b`

## string_xrefs

- `0x18001d8a9`: `Entered: GetInterfaceConfiguration`
- `0x18001db56`: `GetInterfaceConfiguration: There is no more space left to fill in config info even though there are more protocols`
- `0x18001da1e`: `GetInterfaceConfiguration: Info from %ws. Error %d`
- `0x18001dac8`: `GetInterfaceConfiguration: Error %d while adding routing protocol interface info size `
- `0x18001e188`: `GetInterfaceConfiguration: There is no more space left to fill in config info`
- `0x18001dc50`: `GetInterfaceConfiguration: Error %d getting %hs info.`
- `0x18001dd0e`: `GetInterfaceConfiguration2: Error %d while adding routing protocol interface info size `
- `0x18001dd5b`: `GetInterfaceConfiguration: Couldnt Interface route info. Error %d`
- `0x18001e238`: `GetInterfaceConfiguration3: Error %d while adding routing protocol interface route info size `
- `0x18001de39`: `GetInterfaceConfiguration: Error %d getting Interface status`
- `0x18001e226`: `GetInterfaceConfiguration4: Error %d while adding routing protocol interface status info size `
- `0x18001df28`: `GetInterfaceConfiguration: Couldnt Interface router discovery info. Error %d`
- `0x18001e02f`: `GetInterfaceConfiguration2: Error %d while adding routing protocol interface rtrdisc info size `

## pseudocode

```c
__int64 __fastcall GetInterfaceConfiguration(__int64 a1, _DWORD *a2, int a3)
{
  unsigned int v3; // edi
  __int64 *v4; // r12
  unsigned int v8; // r13d
  __int128 *v9; // r9
  unsigned int v10; // esi
  int v11; // eax
  void (__fastcall *v12)(__int64, _QWORD, int *, _QWORD, _QWORD, int *); // rax
  int v13; // ecx
  __int64 *v14; // r12
  __int64 *i; // rax
  int v16; // r13d
  int v17; // edx
  unsigned __int64 v18; // rdi
  __int64 *v19; // r14
  int v20; // eax
  unsigned int InterfaceRoutingProtoInfo; // eax
  __int128 *v22; // r9
  unsigned __int64 v23; // rcx
  __int128 *v24; // r9
  __int128 *v25; // r9
  __int128 *v26; // r9
  __int64 j; // r12
  __int64 (__fastcall *v28)(__int64, _DWORD *, int *, unsigned __int64, _DWORD *, int *); // r10
  unsigned int v29; // ecx
  __int128 *v30; // r9
  unsigned __int64 v31; // rcx
  const wchar_t *v32; // rdx
  int v33; // edx
  unsigned int InterfaceRouteInfo; // r12d
  __int128 *v35; // r9
  unsigned __int64 v36; // rcx
  int v37; // edx
  unsigned int InterfaceStatusInfo; // r12d
  __int128 *v39; // r9
  unsigned __int64 v40; // rcx
  int v41; // edx
  unsigned int InterfaceRouterDiscoveryInfo; // r12d
  __int128 *v43; // r9
  int v44; // eax
  int v45; // ecx
  unsigned __int64 v46; // rdx
  unsigned __int64 v47; // rcx
  int OutFilters; // eax
  unsigned __int64 v49; // rdx
  int v50; // eax
  int GlobalFilterOnIf; // eax
  unsigned __int64 v52; // rdx
  int DemandFilters; // eax
  __int128 *v55; // r9
  int v56; // [rsp+40h] [rbp-C0h] BYREF
  int v57; // [rsp+44h] [rbp-BCh] BYREF
  int v58; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v59; // [rsp+4Ch] [rbp-B4h]
  unsigned int v60; // [rsp+50h] [rbp-B0h]
  int v61; // [rsp+54h] [rbp-ACh]
  __int64 *v62; // [rsp+58h] [rbp-A8h]
  __int128 v63; // [rsp+60h] [rbp-A0h] BYREF
  int v64; // [rsp+70h] [rbp-90h] BYREF
  __int128 v65; // [rsp+74h] [rbp-8Ch]
  __int128 v66; // [rsp+84h] [rbp-7Ch]
  int v67; // [rsp+94h] [rbp-6Ch]
  int v68; // [rsp+A0h] [rbp-60h] BYREF
  char v69[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v3 = 0;
  v4 = &g_rgicInfoCbv4;
  v57 = 0;
  v58 = 0;
  v56 = 0;
  v68 = 0;
  v8 = 5;
  if ( *(_DWORD *)(a1 + 516) != 1 )
  {
    v4 = &g_rgicInfoCbv6;
    v8 = 3;
  }
  v62 = v4;
  v59 = v8;
  memset_0(v69, 0, sizeof(v69));
  v64 = 0;
  v67 = 0;
  LOBYTE(v61) = Microsoft_Windows_RRASEnableBits & 0x80;
  v65 = 0;
  v66 = 0;
  v63 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v64) = 0;
    v9 = &v63;
    if ( a1 != -688 )
      LODWORD(v9) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: GetInterfaceConfiguration",
      (_DWORD)v9,
      *(_QWORD *)(a1 + 72),
      (__int64)&v64);
  }
  v10 = 0;
  v11 = (*(_DWORD *)(a1 + 516) != 0) + 3;
  v58 = v11;
  if ( *(_QWORD *)(a1 + 112) )
    v58 = ++v11;
  if ( *(_QWORD *)(a1 + 120) )
    v58 = ++v11;
  if ( *(_QWORD *)(a1 + 128) )
    v58 = v11 + 1;
  do
  {
    v12 = (void (__fastcall *)(__int64, _QWORD, int *, _QWORD, _QWORD, int *))v4[5 * v3 + 1];
    if ( v12 )
    {
      v56 = 0;
      v12(a1, 0, &v58, 0, 0, &v56);
    }
    ++v3;
  }
  while ( v3 < v8 );
  RtlAcquireResourceShared(&stru_18008C4A0, 1u);
  v13 = v58;
  v14 = (__int64 *)(a1 + 56);
  for ( i = *(__int64 **)(a1 + 56); i != v14; i = (__int64 *)*i )
  {
    if ( !*((_DWORD *)i + 4) )
      v58 = ++v13;
  }
  v16 = (_DWORD)a2 + a3;
  v17 = 0;
  *a2 = 1;
  a2[2] = v13;
  v18 = ((unsigned __int64)&a2[4 * v13 + 4] + 3) & 0xFFFFFFFFFFFFFFF8uLL;
  a2[1] = a3;
  v19 = (__int64 *)*v14;
  v20 = v16 - v18;
  v57 = 0;
  v56 = v16 - v18;
  v61 = v16;
  while ( 1 )
  {
    if ( v19 == v14 )
      goto LABEL_46;
    if ( !*((_DWORD *)v19 + 4) )
      break;
LABEL_35:
    v19 = (__int64 *)*v19;
  }
  if ( v20 <= 0 )
  {
    LOBYTE(v60) = Microsoft_Windows_RRASEnableBits & 0x40;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v25 = &v63;
      LOWORD(v64) = 0;
      if ( a1 != -688 )
        LODWORD(v25) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)L"GetInterfaceConfiguration: There is no more space left to fill in config info even though there ar"
                       "e more protocols",
        (_DWORD)v25,
        *(_QWORD *)(a1 + 72),
        (__int64)&v64);
    }
LABEL_46:
    RtlReleaseResource(&stru_18008C4A0);
    if ( v56 <= 0 )
    {
LABEL_47:
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return 234;
      v26 = &v63;
      LOWORD(v64) = 0;
      if ( a1 != -688 )
        LODWORD(v26) = a1 + 688;
LABEL_133:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)L"GetInterfaceConfiguration: There is no more space left to fill in config info",
        (_DWORD)v26,
        *(_QWORD *)(a1 + 72),
        (__int64)&v64);
      return 234;
    }
    for ( j = 0; (unsigned int)j < v59; j = (unsigned int)(j + 1) )
    {
      v28 = (__int64 (__fastcall *)(__int64, _DWORD *, int *, unsigned __int64, _DWORD *, int *))v62[5 * j + 1];
      if ( v28 )
      {
        v60 = v28(a1, &a2[4 * v57 + 3], &v57, v18, a2, &v56);
        v29 = v60;
        if ( v60 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v68) = 0;
            LOWORD(v64) = 0;
            FormatRRASErrorString(&v68, L"GetInterfaceConfiguration: Error %d getting %hs info.", v60, v62[5 * j]);
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v30 = &v63;
              if ( a1 != -688 )
                LODWORD(v30) = a1 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrMgrParamTraceError,
                (unsigned int)&v68,
                (_DWORD)v30,
                *(_QWORD *)(a1 + 72),
                (__int64)&v64);
            }
            v29 = v60;
          }
          if ( v29 != 232 )
            v10 = 234;
        }
        else
        {
          v31 = v18 + v56;
          if ( v31 < v18 )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
              return 534;
            v32 = L"GetInterfaceConfiguration2: Error %d while adding routing protocol interface info size ";
LABEL_148:
            LOWORD(v68) = 0;
            LOWORD(v64) = 0;
            FormatRRASErrorString(&v68, v32, 534);
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v55 = &v63;
              if ( a1 != -688 )
                LODWORD(v55) = a1 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrMgrParamTraceError,
                (unsigned int)&v68,
                (_DWORD)v55,
                *(_QWORD *)(a1 + 72),
                (__int64)&v64);
            }
            return 534;
          }
          v18 = (v31 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        }
        v16 = v61;
        v56 = v61 - v18;
      }
      else
      {
        v16 = v61;
      }
    }
    v33 = 16 * v57++ + 12;
    InterfaceRouteInfo = GetInterfaceRouteInfo(a1, (int)a2 + v33, v18, (_DWORD)a2, (__int64)&v56);
    if ( InterfaceRouteInfo )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v68) = 0;
        LOWORD(v64) = 0;
        FormatRRASErrorString(
          &v68,
          L"GetInterfaceConfiguration: Couldnt Interface route info. Error %d",
          InterfaceRouteInfo);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v35 = &v63;
          if ( a1 != -688 )
            LODWORD(v35) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v68,
            (_DWORD)v35,
            *(_QWORD *)(a1 + 72),
            (__int64)&v64);
        }
      }
      if ( InterfaceRouteInfo != 232 )
        v10 = 234;
    }
    else
    {
      v36 = v18 + v56;
      if ( v36 < v18 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          return 534;
        v32 = L"GetInterfaceConfiguration3: Error %d while adding routing protocol interface route info size ";
        goto LABEL_148;
      }
      v18 = (v36 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    }
    v56 = v16 - v18;
    if ( v16 - (int)v18 <= 0 )
      goto LABEL_47;
    v37 = 16 * v57++ + 12;
    InterfaceStatusInfo = GetInterfaceStatusInfo(a1, (int)a2 + v37, v18, (_DWORD)a2, (__int64)&v56);
    if ( InterfaceStatusInfo )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v68) = 0;
        LOWORD(v64) = 0;
        FormatRRASErrorString(
          &v68,
          L"GetInterfaceConfiguration: Error %d getting Interface status",
          InterfaceStatusInfo);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v39 = &v63;
          if ( a1 != -688 )
            LODWORD(v39) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v68,
            (_DWORD)v39,
            *(_QWORD *)(a1 + 72),
            (__int64)&v64);
        }
      }
      if ( InterfaceStatusInfo != 232 )
        v10 = 234;
    }
    else
    {
      v40 = v18 + v56;
      if ( v40 < v18 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          return 534;
        v32 = L"GetInterfaceConfiguration4: Error %d while adding routing protocol interface status info size ";
        goto LABEL_148;
      }
      v18 = (v40 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    }
    if ( *(_DWORD *)(a1 + 516) )
    {
      v56 = v16 - v18;
      if ( v16 - (int)v18 <= 0 )
        goto LABEL_47;
      v41 = 16 * v57++ + 12;
      InterfaceRouterDiscoveryInfo = GetInterfaceRouterDiscoveryInfo(a1, (int)a2 + v41, v18, (_DWORD)a2, (__int64)&v56);
      if ( InterfaceRouterDiscoveryInfo )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v68) = 0;
          LOWORD(v64) = 0;
          FormatRRASErrorString(
            &v68,
            L"GetInterfaceConfiguration: Couldnt Interface router discovery info. Error %d",
            InterfaceRouterDiscoveryInfo);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v43 = &v63;
            if ( a1 != -688 )
              LODWORD(v43) = a1 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v68,
              (_DWORD)v43,
              *(_QWORD *)(a1 + 72),
              (__int64)&v64);
          }
        }
        if ( InterfaceRouterDiscoveryInfo != 232 )
          v10 = 234;
      }
      else
      {
        v47 = v18 + v56;
        if ( v47 < v18 )
          goto LABEL_108;
        v18 = (v47 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      }
    }
    v56 = v16 - v18;
    if ( v16 - (int)v18 <= 0 )
      goto LABEL_47;
    if ( *(_QWORD *)(a1 + 112) )
    {
      v44 = GetInFilters(a1, &a2[4 * v57 + 3], v18, a2, &v56);
      v45 = v57;
      if ( v44 )
      {
        if ( v44 != 232 )
          v10 = 234;
      }
      else
      {
        v45 = ++v57;
        v46 = v18 + v56;
        if ( v46 < v18 )
          goto LABEL_108;
        v18 = (v46 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      }
      v56 = v16 - v18;
      if ( v16 - (int)v18 <= 0 )
        goto LABEL_47;
    }
    else
    {
      v45 = v57;
    }
    if ( *(_QWORD *)(a1 + 120) )
    {
      OutFilters = GetOutFilters(a1, &a2[4 * v45 + 3], v18, a2, &v56);
      v45 = v57;
      if ( OutFilters )
      {
        if ( OutFilters != 232 )
          v10 = 234;
      }
      else
      {
        v45 = ++v57;
        v49 = v18 + v56;
        if ( v49 < v18 )
          goto LABEL_108;
        v18 = (v49 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      }
      v56 = v16 - v18;
      if ( v16 - (int)v18 <= 0 )
        goto LABEL_47;
    }
    v50 = *(_DWORD *)(a1 + 144);
    if ( (v50 & 0xFFFFFFFA) == 0 && v50 != 1 )
      goto LABEL_135;
    GlobalFilterOnIf = GetGlobalFilterOnIf(a1, (int)a2 + 16 * v45 + 12, v18, (_DWORD)a2, (__int64)&v56);
    v45 = v57;
    if ( GlobalFilterOnIf )
    {
      if ( GlobalFilterOnIf != 232 )
        v10 = 234;
LABEL_129:
      v56 = v16 - v18;
      if ( v16 - (int)v18 <= 0 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          return 234;
        v26 = &v63;
        LOWORD(v64) = 0;
        if ( a1 != -688 )
          LODWORD(v26) = a1 + 688;
        goto LABEL_133;
      }
LABEL_135:
      if ( *(_QWORD *)(a1 + 128) )
      {
        DemandFilters = GetDemandFilters(a1, &a2[4 * v45 + 3], v18, a2, &v56);
        v45 = v57;
        if ( DemandFilters )
        {
          if ( DemandFilters != 232 )
            v10 = 234;
        }
        else
        {
          v45 = ++v57;
          if ( v18 + v56 < v18 )
            goto LABEL_108;
        }
      }
      if ( a2[2] != v45 )
        a2[2] = v45;
      return v10;
    }
    v45 = ++v57;
    v52 = v18 + v56;
    if ( v52 >= v18 )
    {
      v18 = (v52 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      goto LABEL_129;
    }
LABEL_108:
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return 534;
    v32 = L"GetInterfaceConfiguration2: Error %d while adding routing protocol interface rtrdisc info size ";
    goto LABEL_148;
  }
  v57 = v17 + 1;
  InterfaceRoutingProtoInfo = GetInterfaceRoutingProtoInfo(
                                a1,
                                v19[3],
                                (int)a2 + 16 * v17 + 12,
                                v18,
                                (_DWORD)a2,
                                (__int64)&v56);
  if ( InterfaceRoutingProtoInfo )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v68) = 0;
      LOWORD(v64) = 0;
      FormatRRASErrorString(
        &v68,
        L"GetInterfaceConfiguration: Info from %ws. Error %d",
        *(_QWORD *)(v19[3] + 32),
        InterfaceRoutingProtoInfo);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v22 = &v63;
        if ( a1 != -688 )
          LODWORD(v22) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v68,
          (_DWORD)v22,
          *(_QWORD *)(a1 + 72),
          (__int64)&v64);
      }
    }
    v10 = 234;
    goto LABEL_34;
  }
  v23 = v18 + v56;
  if ( v23 >= v18 )
  {
    v18 = (v23 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
LABEL_34:
    v17 = v57;
    v20 = v16 - v18;
    v56 = v16 - v18;
    goto LABEL_35;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v68) = 0;
    LOWORD(v64) = 0;
    FormatRRASErrorString(
      &v68,
      L"GetInterfaceConfiguration: Error %d while adding routing protocol interface info size ",
      534);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v24 = &v63;
      if ( a1 != -688 )
        LODWORD(v24) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v68,
        (_DWORD)v24,
        *(_QWORD *)(a1 + 72),
        (__int64)&v64);
    }
  }
  RtlReleaseResource(&stru_18008C4A0);
  return 534;
}

```

## disassembly

```asm
0x18001d7e4  mov     [rsp-8+arg_18], rbx
0x18001d7e9  push    rbp
0x18001d7ea  push    rsi
0x18001d7eb  push    rdi
0x18001d7ec  push    r12
0x18001d7ee  push    r13
0x18001d7f0  push    r14
0x18001d7f2  push    r15
0x18001d7f4  lea     rbp, [rsp-7B0h]
0x18001d7fc  sub     rsp, 8B0h
0x18001d803  mov     rax, cs:__security_cookie
0x18001d80a  xor     rax, rsp
0x18001d80d  mov     [rbp+7E0h+var_40], rax
0x18001d814  xor     edi, edi
0x18001d816  lea     r12, g_rgicInfoCbv4
0x18001d81d  mov     rbx, rcx
0x18001d820  mov     [rsp+8E0h+var_89C], edi
0x18001d824  lea     rcx, g_rgicInfoCbv6
0x18001d82b  mov     [rsp+8E0h+var_898], edi
0x18001d82f  mov     r14d, r8d
0x18001d832  mov     [rsp+8E0h+var_8A0], edi
0x18001d836  mov     r15, rdx
0x18001d839  mov     [rbp+7E0h+var_840], edi
0x18001d83c  cmp     dword ptr [rbx+204h], 1
0x18001d843  lea     r13d, [rdi+5]
0x18001d847  mov     r8d, 7FCh; Size
0x18001d84d  cmovnz  r12, rcx
0x18001d851  lea     ecx, [rdi+3]
0x18001d854  cmovnz  r13d, ecx
0x18001d858  mov     [rsp+8E0h+var_888], r12
0x18001d85d  xor     edx, edx; Val
0x18001d85f  mov     [rsp+8E0h+var_894], r13d
0x18001d864  lea     rcx, [rbp+7E0h+var_83C]; void *
0x18001d868  call    memset_0
0x18001d86d  xor     eax, eax
0x18001d86f  mov     [rsp+8E0h+var_870], edi
0x18001d873  xorps   xmm0, xmm0
0x18001d876  mov     [rbp+7E0h+var_84C], eax
0x18001d879  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x18001d87f  and     al, 80h
0x18001d881  mov     byte ptr [rsp+8E0h+var_88C], al
0x18001d885  movups  [rsp+8E0h+var_86C], xmm0
0x18001d88a  movups  [rbp+7E0h+var_85C], xmm0
0x18001d88e  movups  [rsp+8E0h+var_880], xmm0
0x18001d893  jz      short loc_18001D8DA
0x18001d895  lea     rax, [rbx+2B0h]
0x18001d89c  mov     word ptr [rsp+8E0h+var_870], di
0x18001d8a1  test    rax, rax
0x18001d8a4  lea     r9, [rsp+8E0h+var_880]
0x18001d8a9  lea     r8, aEnteredGetinte_0; "Entered: GetInterfaceConfiguration"
0x18001d8b0  cmovnz  r9, rax
0x18001d8b4  lea     rdx, RasRtrmgrParamTraceInfo
0x18001d8bb  lea     rax, [rsp+8E0h+var_870]
0x18001d8c0  mov     [rsp+8E0h+var_8B8], rax
0x18001d8c5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001d8cc  mov     rax, [rbx+48h]
0x18001d8d0  mov     [rsp+8E0h+var_8C0], rax
0x18001d8d5  call    McTemplateU0zjzz_EventWriteTransfer
0x18001d8da  mov     eax, [rbx+204h]
0x18001d8e0  mov     esi, edi
0x18001d8e2  neg     eax
0x18001d8e4  sbb     eax, eax
0x18001d8e6  neg     eax
0x18001d8e8  add     eax, 3
0x18001d8eb  mov     [rsp+8E0h+var_898], eax
0x18001d8ef  cmp     [rbx+70h], rdi
0x18001d8f3  jz      short loc_18001D8FB
0x18001d8f5  inc     eax
0x18001d8f7  mov     [rsp+8E0h+var_898], eax
0x18001d8fb  cmp     [rbx+78h], rdi
0x18001d8ff  jz      short loc_18001D907
0x18001d901  inc     eax
0x18001d903  mov     [rsp+8E0h+var_898], eax
0x18001d907  cmp     [rbx+80h], rdi
0x18001d90e  jz      short loc_18001D916
0x18001d910  inc     eax
0x18001d912  mov     [rsp+8E0h+var_898], eax
0x18001d916  mov     eax, edi
0x18001d918  lea     rcx, [rax+rax*4]
0x18001d91c  mov     rax, [r12+rcx*8+8]
0x18001d921  test    rax, rax
0x18001d924  jz      short loc_18001D94B
0x18001d926  lea     rcx, [rsp+8E0h+var_8A0]
0x18001d92b  mov     [rsp+8E0h+var_8A0], esi
0x18001d92f  mov     [rsp+8E0h+var_8B8], rcx
0x18001d934  lea     r8, [rsp+8E0h+var_898]
0x18001d939  mov     rcx, rbx
0x18001d93c  mov     [rsp+8E0h+var_8C0], rsi
0x18001d941  xor     r9d, r9d
0x18001d944  xor     edx, edx
0x18001d946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d94b  inc     edi
0x18001d94d  cmp     edi, r13d
0x18001d950  jb      short loc_18001D916
0x18001d952  mov     dl, 1; Wait
0x18001d954  lea     rcx, stru_18008C4A0; Resource
0x18001d95b  call    cs:__imp_RtlAcquireResourceShared
0x18001d961  mov     ecx, [rsp+8E0h+var_898]
0x18001d965  lea     r12, [rbx+38h]
0x18001d969  mov     rax, [r12]
0x18001d96d  cmp     rax, r12
0x18001d970  jz      short loc_18001D982
0x18001d972  cmp     [rax+10h], esi
0x18001d975  jnz     short loc_18001D97D
0x18001d977  inc     ecx
0x18001d979  mov     [rsp+8E0h+var_898], ecx
0x18001d97d  mov     rax, [rax]
0x18001d980  jmp     short loc_18001D96D
0x18001d982  lea     r13d, [r15+r14]
0x18001d986  mov     edi, ecx
0x18001d988  shl     rdi, 4
0x18001d98c  xor     edx, edx
0x18001d98e  add     rdi, 13h
0x18001d992  mov     dword ptr [r15], 1
0x18001d999  add     rdi, r15
0x18001d99c  mov     [r15+8], ecx
0x18001d9a0  and     rdi, 0FFFFFFFFFFFFFFF8h
0x18001d9a4  mov     [r15+4], r14d
0x18001d9a8  mov     r14, [r12]
0x18001d9ac  mov     eax, r13d
0x18001d9af  sub     eax, edi
0x18001d9b1  mov     [rsp+8E0h+var_89C], edx
0x18001d9b5  mov     [rsp+8E0h+var_8A0], eax
0x18001d9b9  mov     [rsp+8E0h+var_88C], r13d
0x18001d9be  cmp     r14, r12
0x18001d9c1  jz      loc_18001DB91
0x18001d9c7  cmp     dword ptr [r14+10h], 0
0x18001d9cc  jnz     loc_18001DAAF
0x18001d9d2  test    eax, eax
0x18001d9d4  jle     loc_18001DB3C
0x18001d9da  mov     r8d, edx
0x18001d9dd  lea     rax, [rsp+8E0h+var_8A0]
0x18001d9e2  shl     r8, 4
0x18001d9e6  inc     edx
0x18001d9e8  add     r8, 0Ch
0x18001d9ec  mov     [rsp+8E0h+var_89C], edx
0x18001d9f0  mov     rdx, [r14+18h]
0x18001d9f4  add     r8, r15
0x18001d9f7  mov     [rsp+8E0h+var_8B8], rax
0x18001d9fc  mov     r9, rdi
0x18001d9ff  mov     rcx, rbx
0x18001da02  mov     [rsp+8E0h+var_8C0], r15
0x18001da07  call    GetInterfaceRoutingProtoInfo
0x18001da0c  mov     r9d, eax
0x18001da0f  test    eax, eax
0x18001da11  jz      short loc_18001DA8C
0x18001da13  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001da1a  jz      short loc_18001DA85
0x18001da1c  xor     eax, eax
0x18001da1e  lea     rdx, aGetinterfaceco_9; "GetInterfaceConfiguration: Info from %w"...
0x18001da25  mov     word ptr [rbp+7E0h+var_840], ax
0x18001da29  lea     rcx, [rbp+7E0h+var_840]
0x18001da2d  mov     word ptr [rsp+8E0h+var_870], ax
0x18001da32  mov     r8, [r14+18h]
0x18001da36  mov     r8, [r8+20h]
0x18001da3a  call    FormatRRASErrorString
0x18001da3f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001da46  jz      short loc_18001DA85
0x18001da48  lea     rax, [rbx+2B0h]
0x18001da4f  test    rax, rax
0x18001da52  lea     r9, [rsp+8E0h+var_880]
0x18001da57  lea     r8, [rbp+7E0h+var_840]
0x18001da5b  cmovnz  r9, rax
0x18001da5f  lea     rdx, RasRtrMgrParamTraceError
0x18001da66  lea     rax, [rsp+8E0h+var_870]
0x18001da6b  mov     [rsp+8E0h+var_8B8], rax
0x18001da70  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001da77  mov     rax, [rbx+48h]
0x18001da7b  mov     [rsp+8E0h+var_8C0], rax
0x18001da80  call    McTemplateU0zjzz_EventWriteTransfer
0x18001da85  mov     esi, 0EAh
0x18001da8a  jmp     short loc_18001DAA2
0x18001da8c  movsxd  r9, [rsp+8E0h+var_8A0]
0x18001da91  lea     rcx, [rdi+r9]
0x18001da95  cmp     rcx, rdi
0x18001da98  jb      short loc_18001DAB7
0x18001da9a  lea     rdi, [rcx+7]
0x18001da9e  and     rdi, 0FFFFFFFFFFFFFFF8h
0x18001daa2  mov     edx, [rsp+8E0h+var_89C]
0x18001daa6  mov     eax, r13d
0x18001daa9  sub     eax, edi
0x18001daab  mov     [rsp+8E0h+var_8A0], eax
0x18001daaf  mov     r14, [r14]
0x18001dab2  jmp     loc_18001D9BE
0x18001dab7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001dabe  mov     r14d, 216h
0x18001dac4  jz      short loc_18001DB2A
0x18001dac6  xor     eax, eax
0x18001dac8  lea     rdx, aGetinterfaceco_5; "GetInterfaceConfiguration: Error %d whi"...
0x18001dacf  mov     r8d, r14d
0x18001dad2  mov     word ptr [rbp+7E0h+var_840], ax
0x18001dad6  lea     rcx, [rbp+7E0h+var_840]
0x18001dada  mov     word ptr [rsp+8E0h+var_870], ax
0x18001dadf  call    FormatRRASErrorString
0x18001dae4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001daeb  jz      short loc_18001DB2A
0x18001daed  lea     rax, [rbx+2B0h]
0x18001daf4  test    rax, rax
0x18001daf7  lea     r9, [rsp+8E0h+var_880]
0x18001dafc  lea     r8, [rbp+7E0h+var_840]
0x18001db00  cmovnz  r9, rax
0x18001db04  lea     rdx, RasRtrMgrParamTraceError
0x18001db0b  lea     rax, [rsp+8E0h+var_870]
0x18001db10  mov     [rsp+8E0h+var_8B8], rax
0x18001db15  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001db1c  mov     rax, [rbx+48h]
0x18001db20  mov     [rsp+8E0h+var_8C0], rax
0x18001db25  call    McTemplateU0zjzz_EventWriteTransfer
0x18001db2a  lea     rcx, stru_18008C4A0; Resource
0x18001db31  call    cs:__imp_RtlReleaseResource
0x18001db37  jmp     loc_18001E29C
0x18001db3c  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x18001db42  and     al, 40h
0x18001db44  mov     byte ptr [rsp+8E0h+var_890], al
0x18001db48  jz      short loc_18001DB91
0x18001db4a  xor     eax, eax
0x18001db4c  lea     r9, [rsp+8E0h+var_880]
0x18001db51  mov     word ptr [rsp+8E0h+var_870], ax
0x18001db56  lea     r8, aGetinterfaceco_6; "GetInterfaceConfiguration: There is no "...
0x18001db5d  lea     rax, [rbx+2B0h]
0x18001db64  test    rax, rax
0x18001db67  lea     rdx, RasRtrMgrParamTraceError
0x18001db6e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001db75  cmovnz  r9, rax
0x18001db79  lea     rax, [rsp+8E0h+var_870]
0x18001db7e  mov     [rsp+8E0h+var_8B8], rax
0x18001db83  mov     rax, [rbx+48h]
0x18001db87  mov     [rsp+8E0h+var_8C0], rax
0x18001db8c  call    McTemplateU0zjzz_EventWriteTransfer
0x18001db91  lea     rcx, stru_18008C4A0; Resource
0x18001db98  call    cs:__imp_RtlReleaseResource
0x18001db9e  cmp     [rsp+8E0h+var_8A0], 0
0x18001dba3  jg      short loc_18001DBDB
0x18001dba5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001dbac  jz      loc_18001E1A7
0x18001dbb2  xor     eax, eax
0x18001dbb4  lea     r9, [rsp+8E0h+var_880]
0x18001dbb9  mov     word ptr [rsp+8E0h+var_870], ax
0x18001dbbe  lea     rax, [rbx+2B0h]
0x18001dbc5  test    rax, rax
0x18001dbc8  cmovnz  r9, rax
0x18001dbcc  lea     rax, [rsp+8E0h+var_870]
0x18001dbd1  mov     [rsp+8E0h+var_8B8], rax
0x18001dbd6  jmp     loc_18001E184
0x18001dbdb  xor     r12d, r12d
0x18001dbde  mov     r14d, 216h
0x18001dbe4  cmp     r12d, [rsp+8E0h+var_894]
0x18001dbe9  jnb     loc_18001DD1A
0x18001dbef  mov     rax, [rsp+8E0h+var_888]
0x18001dbf4  lea     r13, [r12+r12*4]
0x18001dbf8  mov     r10, [rax+r13*8+8]
0x18001dbfd  test    r10, r10
0x18001dc00  jz      loc_18001DCF4
0x18001dc06  mov     edx, [rsp+8E0h+var_89C]
0x18001dc0a  lea     rax, [rsp+8E0h+var_8A0]
0x18001dc0f  shl     rdx, 4
0x18001dc13  lea     r8, [rsp+8E0h+var_89C]
0x18001dc18  mov     [rsp+8E0h+var_8B8], rax
0x18001dc1d  add     rdx, 0Ch
0x18001dc21  add     rdx, r15
0x18001dc24  mov     [rsp+8E0h+var_8C0], r15
0x18001dc29  mov     r9, rdi
0x18001dc2c  mov     rcx, rbx
0x18001dc2f  mov     rax, r10
0x18001dc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc37  mov     [rsp+8E0h+var_890], eax
0x18001dc3b  mov     ecx, eax
0x18001dc3d  test    eax, eax
0x18001dc3f  jz      loc_18001DCCE
0x18001dc45  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001dc4c  jz      short loc_18001DCBF
0x18001dc4e  xor     eax, eax
0x18001dc50  lea     rdx, aGetinterfaceco_10; "GetInterfaceConfiguration: Error %d get"...
0x18001dc57  mov     word ptr [rbp+7E0h+var_840], ax
0x18001dc5b  mov     r8d, ecx
0x18001dc5e  mov     word ptr [rsp+8E0h+var_870], ax
0x18001dc63  lea     rcx, [rbp+7E0h+var_840]
0x18001dc67  mov     rax, [rsp+8E0h+var_888]
0x18001dc6c  mov     r9, [rax+r13*8]
0x18001dc70  call    FormatRRASErrorString
0x18001dc75  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001dc7c  jz      short loc_18001DCBB
0x18001dc7e  lea     rax, [rbx+2B0h]
0x18001dc85  test    rax, rax
0x18001dc88  lea     r9, [rsp+8E0h+var_880]
0x18001dc8d  lea     r8, [rbp+7E0h+var_840]
0x18001dc91  cmovnz  r9, rax
0x18001dc95  lea     rdx, RasRtrMgrParamTraceError
0x18001dc9c  lea     rax, [rsp+8E0h+var_870]
0x18001dca1  mov     [rsp+8E0h+var_8B8], rax
0x18001dca6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001dcad  mov     rax, [rbx+48h]
0x18001dcb1  mov     [rsp+8E0h+var_8C0], rax
0x18001dcb6  call    McTemplateU0zjzz_EventWriteTransfer
0x18001dcbb  mov     ecx, [rsp+8E0h+var_890]
0x18001dcbf  cmp     ecx, 0E8h
0x18001dcc5  jz      short loc_18001DCE4
0x18001dcc7  mov     esi, 0EAh
0x18001dccc  jmp     short loc_18001DCE4
0x18001dcce  movsxd  r9, [rsp+8E0h+var_8A0]
  ... truncated ...
```
