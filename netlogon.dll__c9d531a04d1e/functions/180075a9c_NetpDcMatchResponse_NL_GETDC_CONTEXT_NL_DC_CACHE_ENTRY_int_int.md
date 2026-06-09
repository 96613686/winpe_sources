# NetpDcMatchResponse(_NL_GETDC_CONTEXT *,_NL_DC_CACHE_ENTRY *,int,int *)

- ea: `0x180075a9c`
- end: `0x180076b2a`
- name: `?NetpDcMatchResponse@@YAHPEAU_NL_GETDC_CONTEXT@@PEAU_NL_DC_CACHE_ENTRY@@HPEAH@Z`
- size: `4238`
- prototype: `__int64 __fastcall(struct _NL_GETDC_CONTEXT *, struct _NL_DC_CACHE_ENTRY *, int, int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ad34`
- `0x180074f80`

## callees

- `0x180007278`
- `0x18000c3ac`
- `0x18001852c`
- `0x180018690`
- `0x18001a260`
- `0x18001a30c`
- `0x180075a9c`
- `0x180078330`
- `0x1800783f0`
- `0x1800785c8`
- `0x18008315c`
- `0x1800833ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180076095`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800764c2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180076095`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800764c2`
- `netutils!NetpwNameCompare` at `0x180075b82`
- `netutils!NetpwNameCompare` at `0x180075c90`
- `netutils!NetpwNameCompare` at `0x180075db0`
- `netutils!NetpwNameCompare` at `0x18007655d`
- `netutils!NetpwNameCompare` at `0x180075b82`
- `netutils!NetpwNameCompare` at `0x180075c90`
- `netutils!NetpwNameCompare` at `0x180075db0`
- `netutils!NetpwNameCompare` at `0x18007655d`

## string_xrefs

- `0x180076970`: `NetpDcMatchResponse: %ws: %ws: response not from a DC running web service. 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetpDcMatchResponse(struct _NL_GETDC_CONTEXT *a1, struct _NL_DC_CACHE_ENTRY *a2, int a3, int *a4)
{
  __int64 v5; // rcx
  const unsigned __int16 **v6; // r12
  ScannerInfoNameMappings *v9; // rcx
  int v10; // edx
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // rax
  __int64 v16; // r9
  __int64 v17; // rdx
  unsigned __int8 matched; // r13
  const unsigned __int16 *v19; // rcx
  const unsigned __int16 *v20; // rdx
  ScannerInfoNameMappings *v21; // rcx
  int v22; // edx
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rdx
  const unsigned __int16 *v27; // rcx
  _QWORD *v28; // rcx
  __int64 v29; // rcx
  unsigned int v30; // edx
  int v31; // edx
  int v32; // r8d
  int v33; // r8d
  ScannerInfoNameMappings *v34; // rcx
  int v35; // edx
  int v36; // eax
  __int64 v37; // r8
  ScannerInfoNameMappings *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rcx
  int v42; // eax
  int v43; // eax
  _QWORD *v44; // r15
  __int64 v45; // rcx
  _QWORD *v46; // rsi
  ScannerInfoNameMappings *v47; // rcx
  __int64 v48; // rdx
  int v49; // eax
  __int64 v50; // rcx
  __int64 result; // rax
  __int64 v52; // [rsp+20h] [rbp-68h]
  __int64 v53; // [rsp+28h] [rbp-60h]
  __int64 v54; // [rsp+28h] [rbp-60h]
  char v55; // [rsp+40h] [rbp-48h]

  *a4 = 0;
  v5 = *((_QWORD *)a2 + 9);
  v6 = (const unsigned __int16 **)((char *)a2 + 80);
  if ( *(_OWORD *)((char *)a2 + 72) == 0 )
  {
    if ( !a3 )
      return 0;
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: Neither Netbios nor DNS DC name available\n",
      0,
      *((_QWORD *)a1 + 9));
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v10 = 55;
    goto LABEL_181;
  }
  if ( (*((_DWORD *)a1 + 4) & 0x300) != 0x300 )
  {
    if ( (*((_DWORD *)a1 + 4) & 0x100) != 0 )
    {
      if ( *v6 )
      {
        v14 = (const unsigned __int16 *)*((_QWORD *)a1 + 12);
        if ( v14 )
        {
          if ( (unsigned int)NlEqualDnsName(*v6, v14) )
            goto LABEL_34;
        }
      }
      if ( !a3 )
        return 0;
      NlPrintRoutine(
        0x100u,
        L"NetpDcMatchResponse: Ping response with unmatched DNS host name %ws %ws\n",
        *((_QWORD *)a1 + 12),
        *v6);
      v9 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        return 0;
      v15 = *v6;
      v10 = 57;
    }
    else
    {
      if ( (*((_DWORD *)a1 + 4) & 0x200) == 0 )
        goto LABEL_34;
      if ( v5 )
      {
        v17 = *((_QWORD *)a1 + 12);
        if ( v17 )
        {
          if ( !(unsigned int)NetpwNameCompare(v5, v17, 4) )
            goto LABEL_34;
        }
      }
      if ( !a3 )
        return 0;
      NlPrintRoutine(
        0x100u,
        L"NetpDcMatchResponse: Ping response with unmatched Netbios host name %ws %ws\n",
        *((_QWORD *)a1 + 12),
        *((_QWORD *)a2 + 9));
      v9 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        return 0;
      v15 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
      v10 = 58;
    }
    v16 = *((_QWORD *)a1 + 12);
LABEL_182:
    WPP_SF_SS(
      *((_QWORD *)v9 + 2),
      v10,
      (unsigned int)&WPP_a589336c02da3e383446cd82d3de1477_Traceguids,
      v16,
      (__int64)v15);
    return 0;
  }
  if ( !*v6 || (v11 = (const unsigned __int16 *)*((_QWORD *)a1 + 12)) == 0 || !(unsigned int)NlEqualDnsName(*v6, v11) )
  {
    v12 = *((_QWORD *)a2 + 9);
    if ( !v12 || (v13 = *((_QWORD *)a1 + 12)) == 0 || (unsigned int)NetpwNameCompare(v12, v13, 4) )
    {
      if ( a3 )
      {
        NlPrintRoutine(
          0x100u,
          L"NetpDcMatchResponse: Ping response with unmatched host name %ws %ws %ws\n",
          *((_QWORD *)a1 + 12),
          *v6,
          *((_QWORD *)a2 + 9));
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_SSS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            (unsigned int)&WPP_a589336c02da3e383446cd82d3de1477_Traceguids,
            *((_QWORD *)a1 + 12),
            (__int64)*v6,
            *((_QWORD *)a2 + 9));
      }
      return 0;
    }
  }
LABEL_34:
  matched = 0;
  if ( *((_DWORD *)&NlDcDnsNameTypeDesc + 8 * *((int *)a1 + 2) + 5) != 4 )
  {
    v25 = *((_QWORD *)a2 + 6);
    if ( !v25 || (v26 = *((_QWORD *)a1 + 6)) == 0 || (v55 = 1, (unsigned int)NetpwNameCompare(v25, v26, 6)) )
      v55 = 0;
    if ( *((_QWORD *)a2 + 7) )
    {
      v27 = (const unsigned __int16 *)*((_QWORD *)a1 + 7);
      if ( v27 )
      {
        if ( (*((_DWORD *)a1 + 4) & 0x10000) != 0 )
          matched = NlMatchDnsNamePrefix(v27, *((unsigned __int16 **)a2 + 7));
        else
          matched = NlEqualDnsName(*((const unsigned __int16 **)a2 + 7), *((const unsigned __int16 **)a1 + 7));
      }
    }
    if ( v55 )
    {
      if ( !matched || (*((_BYTE *)a1 + 236) & 2) != 0 )
        goto LABEL_56;
    }
    else if ( !matched )
    {
      if ( *((_DWORD *)a1 + 1) == 5 && !*((_QWORD *)a2 + 6) && !*((_QWORD *)a2 + 7) )
      {
LABEL_56:
        matched = 1;
        goto LABEL_73;
      }
      if ( a3 )
      {
        NlPrintRoutine(
          0x100u,
          L"NetpDcMatchResponse: %ws: Neither Netbios %ws nor DNS %ws domain matches queried name %ws %ws\n",
          *((_QWORD *)a2 + 9),
          *((_QWORD *)a2 + 6),
          *((_QWORD *)a2 + 7),
          *((_QWORD *)a1 + 6),
          *((_QWORD *)a1 + 7));
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_SSSSS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *((_QWORD *)a2 + 6),
            *((_QWORD *)a2 + 7),
            *((_QWORD *)a1 + 6),
            *((_QWORD *)a1 + 7));
      }
      v28 = (_QWORD *)*((_QWORD *)a1 + 13);
      if ( !v28
        || *((_QWORD *)a2 + 4) == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
        && *((_QWORD *)a2 + 5) == *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4
        || *((_QWORD *)a2 + 4) != *v28
        || *((_QWORD *)a2 + 5) != v28[1] )
      {
        return 0;
      }
      if ( a3 )
      {
        NlPrintRoutine(0x100u, L"NetpDcMatchResponse: %ws: But Domain Guid matches\n", *((_QWORD *)a2 + 9));
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            61,
            &WPP_a589336c02da3e383446cd82d3de1477_Traceguids,
            *((_QWORD *)a2 + 9));
      }
    }
    matched = 0;
    goto LABEL_73;
  }
  v19 = (const unsigned __int16 *)*((_QWORD *)a2 + 29);
  if ( !v19 || (v20 = (const unsigned __int16 *)*((_QWORD *)a1 + 7)) == 0 || !(unsigned int)NlEqualDnsName(v19, v20) )
  {
    if ( !a3 )
      return 0;
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: asking for GC and tree name doesn't match request %ws %ws\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a2 + 29),
      *((_QWORD *)a1 + 7));
    v21 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v22 = 59;
    v23 = *((_QWORD *)a2 + 9);
    v54 = *((_QWORD *)a1 + 7);
    v24 = *((_QWORD *)a2 + 29);
    goto LABEL_160;
  }
LABEL_73:
  v29 = *((_QWORD *)a1 + 3);
  if ( v29 )
  {
    if ( *((_DWORD *)a2 + 7) == 12 && (*((_DWORD *)a2 + 66) & 0x11) == 1 )
    {
      if ( a3 )
      {
        NlPrintRoutine(
          0x200u,
          L"NetpDcMatchResponse: %ws: %ws: response for wrong account '%ws' s.b. '%ws' (but message from NT 4 PDC so use it).\n",
          *((_QWORD *)a2 + 9),
          *((_QWORD *)a1 + 9),
          *((_QWORD *)a2 + 8),
          *((_QWORD *)a1 + 3));
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_SSSS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            62,
            (unsigned int)&WPP_a589336c02da3e383446cd82d3de1477_Traceguids,
            *((_QWORD *)a2 + 9),
            *((_QWORD *)a1 + 9),
            *((_QWORD *)a2 + 8),
            *((_QWORD *)a1 + 3));
      }
    }
    else if ( !*((_QWORD *)a2 + 8) || (unsigned int)_o__wcsicmp(v29) )
    {
      if ( a3 )
      {
        NlPrintRoutine(
          0x100u,
          L"NetpDcMatchResponse: %ws: %ws: response for wrong account '%ws' s.b. '%ws'\n",
          *((_QWORD *)a2 + 9),
          *((_QWORD *)a1 + 9),
          *((_QWORD *)a2 + 8),
          *((_QWORD *)a1 + 3));
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_SSSS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            63,
            (unsigned int)&WPP_a589336c02da3e383446cd82d3de1477_Traceguids,
            *((_QWORD *)a2 + 9),
            *((_QWORD *)a1 + 9),
            *((_QWORD *)a2 + 8),
            *((_QWORD *)a1 + 3));
      }
      return 0;
    }
  }
  v30 = *((_DWORD *)a1 + 1);
  if ( v30 <= 2 )
    goto LABEL_109;
  if ( v30 == 3 )
  {
    if ( (*((_DWORD *)a2 + 66) & 4) != 0 )
      goto LABEL_109;
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: Responder is not a GC server. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 66;
    goto LABEL_237;
  }
  if ( v30 == 4 )
  {
    if ( (*((_BYTE *)a2 + 264) & 0x14) == 0x14 )
      goto LABEL_109;
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: Responder is not a GC server. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 65;
LABEL_237:
    WPP_SF_SSL(*((_QWORD *)v34 + 2), v35, v33, *((_QWORD *)a2 + 9), *((_QWORD *)a1 + 9), *((_DWORD *)a2 + 66));
    return 0;
  }
  if ( v30 != 5 )
  {
    if ( a3 )
    {
      LODWORD(v53) = *((_DWORD *)a2 + 66);
      LODWORD(v52) = *((_DWORD *)a1 + 1);
      NlPrintRoutine(
        0x100u,
        L"NetpDcMatchResponse: %ws: %ws: invalid query type 0x%lx 0x%lx\n",
        *((_QWORD *)a2 + 9),
        *((_QWORD *)a1 + 9),
        v52,
        v53);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_SSLL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v31,
          v32,
          *((_QWORD *)a2 + 9),
          *((_QWORD *)a1 + 9),
          *((_DWORD *)a1 + 1),
          *((_DWORD *)a2 + 66));
    }
    return 0;
  }
  if ( (*((_DWORD *)a2 + 66) & 1) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: Responder is not the PDC. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 64;
    goto LABEL_237;
  }
LABEL_109:
  if ( (*((_DWORD *)&NlDcDnsNameTypeDesc + 8 * *((int *)a1 + 2) + 5) & 0x400) == 0
    && (*((_DWORD *)a2 + 66) & 0x400) != 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from real domain DC. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 68;
    goto LABEL_237;
  }
  v36 = *((_DWORD *)a1 + 3);
  if ( (v36 & 0x10) != 0 && (*((_DWORD *)a2 + 66) & 0x10) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from DS server. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 69;
    goto LABEL_237;
  }
  if ( (v36 & 0x2800) != 0 && (*((_DWORD *)a2 + 66) & 0x40) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a Time Server. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 70;
    goto LABEL_237;
  }
  if ( (v36 & 0x1000) != 0 && (*((_DWORD *)a2 + 66) & 0x100) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: Responder is not a writable server. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 71;
    goto LABEL_237;
  }
  if ( (v36 & 0x8000) != 0 && (*((_DWORD *)a2 + 66) & 8) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: Responder is not a LDAP server. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 72;
    goto LABEL_237;
  }
  if ( v36 < 0 )
  {
    v37 = *((_QWORD *)a2 + 9);
    if ( !v37 || !*((_QWORD *)a2 + 6) )
    {
      if ( !a3 )
        return 0;
      NlPrintRoutine(
        0x100u,
        L"NetpDcMatchResponse: %ws: %ws: Netbios server or domain name needed and missing.\n",
        v37,
        *((_QWORD *)a1 + 9));
      v9 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        return 0;
      v10 = 73;
      goto LABEL_181;
    }
  }
  if ( (*((_DWORD *)a1 + 3) & 0x40000000) != 0 && (!*((_QWORD *)a2 + 10) || !*((_QWORD *)a2 + 7)) )
  {
    if ( !a3 )
      return 0;
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: Dns server or domain name needed and missing.\n",
      *((_QWORD *)a1 + 9));
    v38 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v39 = 74;
    goto LABEL_168;
  }
  if ( *((_BYTE *)a1 + 227) )
  {
    v40 = *((_QWORD *)a2 + 30);
    if ( !v40 || (unsigned int)_o__wcsicmp(v40) )
    {
      if ( !a3 )
        return 0;
      NlPrintRoutine(
        0x100u,
        L"NetpDcMatchResponse: %ws: Responder is in site '%ws' but site '%ws' asked for.\n",
        *((_QWORD *)a1 + 9),
        *((_QWORD *)a2 + 30),
        *((_QWORD *)a1 + 5));
      v21 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        return 0;
      v22 = 75;
      v23 = *((_QWORD *)a1 + 9);
      v54 = *((_QWORD *)a1 + 5);
      v24 = *((_QWORD *)a2 + 30);
LABEL_160:
      WPP_SF_SSS(
        *((_QWORD *)v21 + 2),
        v22,
        (unsigned int)&WPP_a589336c02da3e383446cd82d3de1477_Traceguids,
        v23,
        v24,
        v54);
      return 0;
    }
  }
  if ( (*((_DWORD *)a1 + 3) & 0x4000) != 0 )
  {
    v41 = *((_QWORD *)a2 + 9);
    if ( v41 )
    {
      if ( !(unsigned int)NetpwNameCompare(v41, *((_QWORD *)a1 + 10), 4) )
      {
        if ( !a3 )
          return 0;
        NlPrintRoutine(
          0x200u,
          L"NetpDcMatchResponse: %ws: response is from ourself and caller asked for AVOID_SELF.\n",
          *((_QWORD *)a1 + 9));
        v38 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          return 0;
        v39 = 76;
LABEL_168:
        WPP_SF_S(*((_QWORD *)v38 + 2), v39, &WPP_a589336c02da3e383446cd82d3de1477_Traceguids, *((_QWORD *)a1 + 9));
        return 0;
      }
    }
  }
  v42 = *((_DWORD *)a1 + 3);
  if ( (v42 & 0x400) != 0 && (*((_DWORD *)a2 + 66) & 0x20) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from KDC. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 77;
    goto LABEL_237;
  }
  if ( (v42 & 0x200) != 0 && !*((_DWORD *)a2 + 24) )
  {
    if ( !a3 )
      return 0;
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from IP transport\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9));
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v10 = 78;
LABEL_181:
    v15 = (const unsigned __int16 *)*((_QWORD *)a1 + 9);
    v16 = *((_QWORD *)a2 + 9);
    goto LABEL_182;
  }
  if ( (v42 & 0x80000) != 0 && (*((_DWORD *)a2 + 66) & 0x1800) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a WS2008 DC. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 79;
    goto LABEL_237;
  }
  if ( (v42 & 0x200000) != 0 && (*((_DWORD *)a2 + 66) & 0x4000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a WS2012 DC. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 80;
    goto LABEL_237;
  }
  if ( (v42 & 0x400000) != 0 && (*((_DWORD *)a2 + 66) & 0x8000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a WS2012R2 DC. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 81;
    goto LABEL_237;
  }
  if ( (v42 & 0x800000) != 0 && (*((_DWORD *)a2 + 66) & 0x10000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a WS2016 dc. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 82;
    goto LABEL_237;
  }
  if ( (v42 & 0x1000000) != 0 && (*((_DWORD *)a2 + 66) & 0x20000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a DC with key list request support. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 83;
    goto LABEL_237;
  }
  if ( (v42 & 0x4000000) != 0 && (*((_DWORD *)a2 + 66) & 0x80000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a WS2022 dc. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 84;
    goto LABEL_237;
  }
  if ( (v42 & 0x2000000) != 0 && (*((_DWORD *)a2 + 66) & 0x40000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a WS2025 dc. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 85;
    goto LABEL_237;
  }
  if ( (v42 & 0x8000000) != 0 && (*((_DWORD *)a2 + 66) & 0x100000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a WS2028 dc. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 86;
    goto LABEL_237;
  }
  if ( (*((_DWORD *)a1 + 3) & 0x100000) != 0 && (*((_DWORD *)a2 + 66) & 0x2000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v52) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a DC running web service. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v52);
    v34 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v35 = 87;
    goto LABEL_237;
  }
  if ( (*((_BYTE *)a1 + 12) & 0x20) != 0 )
  {
    v43 = *((_DWORD *)a2 + 66);
    if ( (v43 & 0x10) == 0 )
    {
      v44 = (_QWORD *)((char *)a1 + 216);
      v45 = *((_QWORD *)a1 + 27);
      if ( v45 )
      {
        if ( *(char *)(v45 + 264) < 0 || (v43 & 0x80u) == 0 )
          return 0;
        NetpDcDerefCacheEntry((struct _NL_DC_CACHE_ENTRY *)v45);
        *v44 = 0;
        v46 = (_QWORD *)((char *)a1 + 216);
      }
      else
      {
        v46 = (_QWORD *)((char *)a1 + 216);
      }
      if ( !a3 )
        goto LABEL_262;
      NlPrintRoutine(
        0x200u,
        L"NetpDcMatchResponse: %ws: non-DS server responded when DS preferred\n",
        *((_QWORD *)a1 + 9));
      v47 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v48 = 88;
LABEL_260:
          WPP_SF_S(*((_QWORD *)v47 + 2), v48, &WPP_a589336c02da3e383446cd82d3de1477_Traceguids, *((_QWORD *)a1 + 9));
          goto LABEL_262;
        }
        goto LABEL_262;
      }
      goto LABEL_261;
    }
  }
  if ( (*((_DWORD *)a1 + 3) & 0x2000) != 0 )
  {
    v49 = *((_DWORD *)a2 + 66);
    if ( (v49 & 0x200) == 0 )
    {
      v44 = (_QWORD *)((char *)a1 + 216);
      v50 = *((_QWORD *)a1 + 27);
      if ( v50 )
      {
        if ( *(char *)(v50 + 264) < 0 || (v49 & 0x80u) == 0 )
          return 0;
        NetpDcDerefCacheEntry((struct _NL_DC_CACHE_ENTRY *)v50);
        *v44 = 0;
        v46 = (_QWORD *)((char *)a1 + 216);
      }
      else
      {
        v46 = (_QWORD *)((char *)a1 + 216);
      }
      if ( !a3 )
        goto LABEL_262;
      NlPrintRoutine(
        0x200u,
        L"NetpDcMatchResponse: %ws: non-good time server responded when one preferred\n",
        *((_QWORD *)a1 + 9));
      v47 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v48 = 89;
          goto LABEL_260;
        }
LABEL_262:
        ++*((_DWORD *)a2 + 4);
        *((_BYTE *)a1 + 224) = matched;
        *v46 = a2;
        return 0;
      }
LABEL_261:
      v46 = v44;
      goto LABEL_262;
    }
  }
  result = 1;
  *a4 = matched;
  return result;
}

```

## disassembly

```asm
0x180075a9c  mov     [rsp+arg_0], rbx
0x180075aa1  mov     [rsp+arg_18], r9
0x180075aa6  push    rbp
0x180075aa7  push    rsi
0x180075aa8  push    rdi
0x180075aa9  push    r12
0x180075aab  push    r13
0x180075aad  push    r14
0x180075aaf  push    r15
0x180075ab1  sub     rsp, 50h
0x180075ab5  mov     rdi, rcx
0x180075ab8  mov     dword ptr [r9], 0
0x180075abf  mov     rcx, [rdx+48h]
0x180075ac3  lea     r12, [rdx+50h]
0x180075ac7  mov     ebp, r8d
0x180075aca  mov     rbx, rdx
0x180075acd  test    rcx, rcx
0x180075ad0  jnz     short loc_180075B2D
0x180075ad2  cmp     [r12], rcx
0x180075ad6  jnz     short loc_180075B2D
0x180075ad8  test    r8d, r8d
0x180075adb  jz      loc_180076AFB
0x180075ae1  mov     r9, [rdi+48h]
0x180075ae5  lea     rdx, aNetpdcmatchres_13; "NetpDcMatchResponse: %ws: %ws: Neither "...
0x180075aec  xor     r8d, r8d
0x180075aef  mov     ecx, 100h; unsigned int
0x180075af4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180075af9  mov     rcx, cs:WPP_GLOBAL_Control
0x180075b00  mov     r14d, 4
0x180075b06  test    [rcx+1Ch], r14b
0x180075b0a  jz      loc_180076AFB
0x180075b10  mov     sil, 2
0x180075b13  cmp     [rcx+19h], sil
0x180075b17  jb      loc_180076AFB
0x180075b1d  lea     edx, [r14+33h]
0x180075b21  lea     r8, WPP_a589336c02da3e383446cd82d3de1477_Traceguids
0x180075b28  jmp     loc_180076663
0x180075b2d  mov     eax, [rdi+10h]
0x180075b30  mov     edx, 300h
0x180075b35  and     eax, edx
0x180075b37  mov     r14d, 4
0x180075b3d  mov     r15d, 100h
0x180075b43  cmp     eax, edx
0x180075b45  jnz     loc_180075BF8
0x180075b4b  mov     rcx, [r12]; unsigned __int16 *
0x180075b4f  test    rcx, rcx
0x180075b52  jz      short loc_180075B6A
0x180075b54  mov     rdx, [rdi+60h]; unsigned __int16 *
0x180075b58  test    rdx, rdx
0x180075b5b  jz      short loc_180075B6A
0x180075b5d  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x180075b62  test    eax, eax
0x180075b64  jnz     loc_180075CE2
0x180075b6a  mov     rcx, [rbx+48h]
0x180075b6e  test    rcx, rcx
0x180075b71  jz      short loc_180075B90
0x180075b73  mov     rdx, [rdi+60h]
0x180075b77  test    rdx, rdx
0x180075b7a  jz      short loc_180075B90
0x180075b7c  xor     r9d, r9d
0x180075b7f  mov     r8d, r14d
0x180075b82  call    cs:__imp_NetpwNameCompare
0x180075b88  test    eax, eax
0x180075b8a  jz      loc_180075CE2
0x180075b90  test    ebp, ebp
0x180075b92  jz      loc_180076AFB
0x180075b98  mov     rax, [rbx+48h]
0x180075b9c  lea     rdx, aNetpdcmatchres_1; "NetpDcMatchResponse: Ping response with"...
0x180075ba3  mov     r9, [r12]
0x180075ba7  mov     ecx, r15d; unsigned int
0x180075baa  mov     r8, [rdi+60h]
0x180075bae  mov     [rsp+88h+var_68], rax
0x180075bb3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180075bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180075bbf  test    [rcx+1Ch], r14b
0x180075bc3  jz      loc_180076AFB
0x180075bc9  mov     sil, 2
0x180075bcc  cmp     [rcx+19h], sil
0x180075bd0  jb      loc_180076AFB
0x180075bd6  mov     rax, [rbx+48h]
0x180075bda  lea     r8, WPP_a589336c02da3e383446cd82d3de1477_Traceguids
0x180075be1  mov     r9, [rdi+60h]
0x180075be5  mov     edx, 38h ; '8'
0x180075bea  mov     [rsp+88h+var_60], rax
0x180075bef  mov     rax, [r12]
0x180075bf3  jmp     loc_18007652E
0x180075bf8  test    [rdi+10h], r15d
0x180075bfc  jz      short loc_180075C73
0x180075bfe  mov     rcx, [r12]; unsigned __int16 *
0x180075c02  test    rcx, rcx
0x180075c05  jz      short loc_180075C1D
0x180075c07  mov     rdx, [rdi+60h]; unsigned __int16 *
0x180075c0b  test    rdx, rdx
0x180075c0e  jz      short loc_180075C1D
0x180075c10  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x180075c15  test    eax, eax
0x180075c17  jnz     loc_180075CE2
0x180075c1d  test    ebp, ebp
0x180075c1f  jz      loc_180076AFB
0x180075c25  mov     r9, [r12]
0x180075c29  lea     rdx, aNetpdcmatchres_32; "NetpDcMatchResponse: Ping response with"...
0x180075c30  mov     r8, [rdi+60h]
0x180075c34  mov     ecx, r15d; unsigned int
0x180075c37  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180075c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180075c43  test    [rcx+1Ch], r14b
0x180075c47  jz      loc_180076AFB
0x180075c4d  mov     sil, 2
0x180075c50  cmp     [rcx+19h], sil
0x180075c54  jb      loc_180076AFB
0x180075c5a  mov     rax, [r12]
0x180075c5e  mov     edx, 39h ; '9'
0x180075c63  mov     r9, [rdi+60h]
0x180075c67  lea     r8, WPP_a589336c02da3e383446cd82d3de1477_Traceguids
0x180075c6e  jmp     loc_18007666B
0x180075c73  test    dword ptr [rdi+10h], 200h
0x180075c7a  jz      short loc_180075CE2
0x180075c7c  test    rcx, rcx
0x180075c7f  jz      short loc_180075C9A
0x180075c81  mov     rdx, [rdi+60h]
0x180075c85  test    rdx, rdx
0x180075c88  jz      short loc_180075C9A
0x180075c8a  xor     r9d, r9d
0x180075c8d  mov     r8d, r14d
0x180075c90  call    cs:__imp_NetpwNameCompare
0x180075c96  test    eax, eax
0x180075c98  jz      short loc_180075CE2
0x180075c9a  test    ebp, ebp
0x180075c9c  jz      loc_180076AFB
0x180075ca2  mov     r9, [rbx+48h]
0x180075ca6  lea     rdx, aNetpdcmatchres_21; "NetpDcMatchResponse: Ping response with"...
0x180075cad  mov     r8, [rdi+60h]
0x180075cb1  mov     ecx, r15d; unsigned int
0x180075cb4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180075cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180075cc0  test    [rcx+1Ch], r14b
0x180075cc4  jz      loc_180076AFB
0x180075cca  mov     sil, 2
0x180075ccd  cmp     [rcx+19h], sil
0x180075cd1  jb      loc_180076AFB
0x180075cd7  mov     rax, [rbx+48h]
0x180075cdb  mov     edx, 3Ah ; ':'
0x180075ce0  jmp     short loc_180075C63
0x180075ce2  movsxd  rax, dword ptr [rdi+8]
0x180075ce6  lea     rcx, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A; _NL_DNS_NAME_TYPE_DESC near * NlDcDnsNameTypeDesc
0x180075ced  xor     r13b, r13b
0x180075cf0  shl     rax, 5
0x180075cf4  mov     [rsp+88h+arg_8], r13b
0x180075cfc  lea     r12, WPP_a589336c02da3e383446cd82d3de1477_Traceguids
0x180075d03  mov     sil, 2
0x180075d06  cmp     [rax+rcx+14h], r14d
0x180075d0b  jnz     loc_180075D97
0x180075d11  mov     rcx, [rbx+0E8h]; unsigned __int16 *
0x180075d18  test    rcx, rcx
0x180075d1b  jz      short loc_180075D33
0x180075d1d  mov     rdx, [rdi+38h]; unsigned __int16 *
0x180075d21  test    rdx, rdx
0x180075d24  jz      short loc_180075D33
0x180075d26  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x180075d2b  test    eax, eax
0x180075d2d  jnz     loc_180075F49
0x180075d33  test    ebp, ebp
0x180075d35  jz      loc_180076AFB
0x180075d3b  mov     rax, [rdi+38h]
0x180075d3f  lea     rdx, aNetpdcmatchres_10; "NetpDcMatchResponse: %ws: asking for GC"...
0x180075d46  mov     r9, [rbx+0E8h]
0x180075d4d  mov     ecx, r15d; unsigned int
0x180075d50  mov     r8, [rbx+48h]
0x180075d54  mov     [rsp+88h+var_68], rax
0x180075d59  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180075d5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180075d65  test    [rcx+1Ch], r14b
0x180075d69  jz      loc_180076AFB
0x180075d6f  cmp     [rcx+19h], sil
0x180075d73  jb      loc_180076AFB
0x180075d79  mov     rax, [rdi+38h]
0x180075d7d  mov     edx, 3Bh ; ';'
0x180075d82  mov     r9, [rbx+48h]
0x180075d86  mov     [rsp+88h+var_60], rax
0x180075d8b  mov     rax, [rbx+0E8h]
0x180075d92  jmp     loc_18007652B
0x180075d97  mov     rcx, [rbx+30h]
0x180075d9b  test    rcx, rcx
0x180075d9e  jz      short loc_180075DBF
0x180075da0  mov     rdx, [rdi+30h]
0x180075da4  test    rdx, rdx
0x180075da7  jz      short loc_180075DBF
0x180075da9  xor     r9d, r9d
0x180075dac  lea     r8d, [r9+6]
0x180075db0  call    cs:__imp_NetpwNameCompare
0x180075db6  mov     [rsp+88h+var_48], 1
0x180075dbb  test    eax, eax
0x180075dbd  jz      short loc_180075DC4
0x180075dbf  mov     [rsp+88h+var_48], r13b
0x180075dc4  mov     rax, [rbx+38h]
0x180075dc8  test    rax, rax
0x180075dcb  jz      short loc_180075DFA
0x180075dcd  mov     rcx, [rdi+38h]; unsigned __int16 *
0x180075dd1  test    rcx, rcx
0x180075dd4  jz      short loc_180075DFA
0x180075dd6  test    dword ptr [rdi+10h], 10000h
0x180075ddd  jnz     short loc_180075DEF
0x180075ddf  mov     rdx, rcx; unsigned __int16 *
0x180075de2  mov     rcx, rax; unsigned __int16 *
0x180075de5  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x180075dea  mov     r13d, eax
0x180075ded  jmp     short loc_180075DFA
0x180075def  mov     rdx, rax; unsigned __int16 *
0x180075df2  call    ?NlMatchDnsNamePrefix@@YAHPEBGPEAG@Z; NlMatchDnsNamePrefix(ushort const *,ushort *)
0x180075df7  mov     r13b, al
0x180075dfa  cmp     [rsp+88h+var_48], 0
0x180075dff  jnz     loc_180075F2B
0x180075e05  test    r13b, r13b
0x180075e08  jnz     loc_180075F41
0x180075e0e  cmp     dword ptr [rdi+4], 5
0x180075e12  jnz     short loc_180075E2A
0x180075e14  cmp     qword ptr [rbx+30h], 0
0x180075e19  jnz     short loc_180075E2A
0x180075e1b  cmp     qword ptr [rbx+38h], 0
0x180075e20  jnz     short loc_180075E2A
0x180075e22  mov     r13b, 1
0x180075e25  jmp     loc_180075F49
0x180075e2a  test    ebp, ebp
0x180075e2c  jz      short loc_180075EA4
0x180075e2e  mov     rax, [rdi+38h]
0x180075e32  lea     rdx, aNetpdcmatchres_14; "NetpDcMatchResponse: %ws: Neither Netbi"...
0x180075e39  mov     r9, [rbx+30h]
0x180075e3d  mov     ecx, r15d; unsigned int
0x180075e40  mov     r8, [rbx+48h]
0x180075e44  mov     [rsp+88h+var_58], rax
0x180075e49  mov     rax, [rdi+30h]
0x180075e4d  mov     [rsp+88h+var_60], rax
0x180075e52  mov     rax, [rbx+38h]
0x180075e56  mov     [rsp+88h+var_68], rax
0x180075e5b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180075e60  mov     rcx, cs:WPP_GLOBAL_Control
0x180075e67  test    [rcx+1Ch], r14b
0x180075e6b  jz      short loc_180075EA4
0x180075e6d  cmp     [rcx+19h], sil
0x180075e71  jb      short loc_180075EA4
0x180075e73  mov     rax, [rdi+38h]
0x180075e77  mov     r9, [rbx+48h]
0x180075e7b  mov     rcx, [rcx+10h]; LoggerHandle
0x180075e7f  mov     [rsp+88h+var_50], rax; __int64
0x180075e84  mov     rax, [rdi+30h]
0x180075e88  mov     [rsp+88h+var_58], rax; __int64
0x180075e8d  mov     rax, [rbx+38h]
0x180075e91  mov     [rsp+88h+var_60], rax; __int64
0x180075e96  mov     rax, [rbx+30h]
0x180075e9a  mov     [rsp+88h+var_68], rax; __int64
0x180075e9f  call    WPP_SF_SSSSS
0x180075ea4  mov     rcx, [rdi+68h]
0x180075ea8  test    rcx, rcx
0x180075eab  jz      loc_180076AFB
0x180075eb1  mov     rax, [rbx+20h]
0x180075eb5  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180075ebc  jnz     short loc_180075ECF
0x180075ebe  mov     rax, [rbx+28h]
0x180075ec2  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180075ec9  jz      loc_180076AFB
0x180075ecf  mov     rax, [rbx+20h]
0x180075ed3  cmp     rax, [rcx]
0x180075ed6  jnz     loc_180076AFB
0x180075edc  mov     rax, [rbx+28h]
0x180075ee0  cmp     rax, [rcx+8]
0x180075ee4  jnz     loc_180076AFB
0x180075eea  test    ebp, ebp
0x180075eec  jz      short loc_180075F41
0x180075eee  mov     r8, [rbx+48h]
0x180075ef2  lea     rdx, aNetpdcmatchres_29; "NetpDcMatchResponse: %ws: But Domain Gu"...
0x180075ef9  mov     ecx, r15d; unsigned int
0x180075efc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180075f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180075f08  test    [rcx+1Ch], r14b
0x180075f0c  jz      short loc_180075F41
0x180075f0e  cmp     [rcx+19h], sil
0x180075f12  jb      short loc_180075F41
0x180075f14  mov     r9, [rbx+48h]
0x180075f18  mov     edx, 3Dh ; '='
0x180075f1d  mov     rcx, [rcx+10h]
0x180075f21  mov     r8, r12
0x180075f24  call    WPP_SF_S
0x180075f29  jmp     short loc_180075F41
0x180075f2b  test    r13b, r13b
0x180075f2e  jz      loc_180075E22
0x180075f34  test    [rdi+0ECh], sil
0x180075f3b  jnz     loc_180075E22
0x180075f41  mov     r13b, [rsp+88h+arg_8]
0x180075f49  mov     rcx, [rdi+18h]
0x180075f4d  test    rcx, rcx
0x180075f50  jz      loc_180075FDE
0x180075f56  cmp     dword ptr [rbx+1Ch], 0Ch
0x180075f5a  jnz     loc_18007608C
0x180075f60  mov     eax, [rbx+108h]
0x180075f66  and     al, 11h
0x180075f68  cmp     al, 1
0x180075f6a  jnz     loc_18007608C
0x180075f70  test    ebp, ebp
0x180075f72  jz      short loc_180075FDE
0x180075f74  mov     rax, [rbx+40h]
  ... truncated ...
```
