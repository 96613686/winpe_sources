# NetpDcMatchResponse(_NL_GETDC_CONTEXT *,_NL_DC_CACHE_ENTRY *,int,int *)

- ea: `0x18007b50c`
- end: `0x18007c5c2`
- name: `?NetpDcMatchResponse@@YAHPEAU_NL_GETDC_CONTEXT@@PEAU_NL_DC_CACHE_ENTRY@@HPEAH@Z`
- size: `4278`
- prototype: `__int64 __fastcall(struct _NL_GETDC_CONTEXT *, struct _NL_DC_CACHE_ENTRY *, int, int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b394`
- `0x18007a9a4`

## callees

- `0x180007518`
- `0x18000ca88`
- `0x18001906c`
- `0x1800191e4`
- `0x18001af4c`
- `0x18001b000`
- `0x18007b50c`
- `0x18007de00`
- `0x18007dec8`
- `0x18007e0b0`
- `0x1800892fc`
- `0x18008957c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007bb1a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007bf4d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007bb1a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007bf4d`
- `netutils!NetpwNameCompare` at `0x18007b5f2`
- `netutils!NetpwNameCompare` at `0x18007b706`
- `netutils!NetpwNameCompare` at `0x18007b82f`
- `netutils!NetpwNameCompare` at `0x18007bfee`
- `netutils!NetpwNameCompare` at `0x18007b5f2`
- `netutils!NetpwNameCompare` at `0x18007b706`
- `netutils!NetpwNameCompare` at `0x18007b82f`
- `netutils!NetpwNameCompare` at `0x18007bfee`

## string_xrefs

- `0x18007c407`: `NetpDcMatchResponse: %ws: %ws: response not from a DC running web service. 0x%lx\n`

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
  __int64 v33; // rdx
  int v34; // r8d
  ScannerInfoNameMappings *v35; // rcx
  int v36; // edx
  int v37; // eax
  __int64 v38; // r8
  ScannerInfoNameMappings *v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rcx
  int v43; // eax
  int v44; // eax
  _QWORD *v45; // r15
  __int64 v46; // rcx
  _QWORD *v47; // rsi
  ScannerInfoNameMappings *v48; // rcx
  __int64 v49; // rdx
  int v50; // eax
  __int64 v51; // rcx
  __int64 result; // rax
  __int64 v53; // [rsp+20h] [rbp-68h]
  __int64 v54; // [rsp+28h] [rbp-60h]
  __int64 v55; // [rsp+28h] [rbp-60h]
  char v56; // [rsp+40h] [rbp-48h]

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
      (unsigned int)&WPP_11c6771b9160306a006e43c886fcea6e_Traceguids,
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
            (unsigned int)&WPP_11c6771b9160306a006e43c886fcea6e_Traceguids,
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
    if ( !v25 || (v26 = *((_QWORD *)a1 + 6)) == 0 || (v56 = 1, (unsigned int)NetpwNameCompare(v25, v26, 6)) )
      v56 = 0;
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
    if ( v56 )
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
            &WPP_11c6771b9160306a006e43c886fcea6e_Traceguids,
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
    v55 = *((_QWORD *)a1 + 7);
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
            (unsigned int)&WPP_11c6771b9160306a006e43c886fcea6e_Traceguids,
            *((_QWORD *)a2 + 9),
            *((_QWORD *)a1 + 9),
            *((_QWORD *)a2 + 8),
            *((_QWORD *)a1 + 3));
      }
    }
    else
    {
      v33 = *((_QWORD *)a2 + 8);
      if ( !v33 || (unsigned int)_o__wcsicmp(v29, v33) )
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
              (unsigned int)&WPP_11c6771b9160306a006e43c886fcea6e_Traceguids,
              *((_QWORD *)a2 + 9),
              *((_QWORD *)a1 + 9),
              *((_QWORD *)a2 + 8),
              *((_QWORD *)a1 + 3));
        }
        return 0;
      }
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
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: Responder is not a GC server. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 66;
    goto LABEL_237;
  }
  if ( v30 == 4 )
  {
    if ( (*((_BYTE *)a2 + 264) & 0x14) == 0x14 )
      goto LABEL_109;
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: Responder is not a GC server. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 65;
LABEL_237:
    WPP_SF_SSL(*((_QWORD *)v35 + 2), v36, v34, *((_QWORD *)a2 + 9), *((_QWORD *)a1 + 9), *((_DWORD *)a2 + 66));
    return 0;
  }
  if ( v30 != 5 )
  {
    if ( a3 )
    {
      LODWORD(v54) = *((_DWORD *)a2 + 66);
      LODWORD(v53) = *((_DWORD *)a1 + 1);
      NlPrintRoutine(
        0x100u,
        L"NetpDcMatchResponse: %ws: %ws: invalid query type 0x%lx 0x%lx\n",
        *((_QWORD *)a2 + 9),
        *((_QWORD *)a1 + 9),
        v53,
        v54);
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
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: Responder is not the PDC. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 64;
    goto LABEL_237;
  }
LABEL_109:
  if ( (*((_DWORD *)&NlDcDnsNameTypeDesc + 8 * *((int *)a1 + 2) + 5) & 0x400) == 0
    && (*((_DWORD *)a2 + 66) & 0x400) != 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from real domain DC. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 68;
    goto LABEL_237;
  }
  v37 = *((_DWORD *)a1 + 3);
  if ( (v37 & 0x10) != 0 && (*((_DWORD *)a2 + 66) & 0x10) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from DS server. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 69;
    goto LABEL_237;
  }
  if ( (v37 & 0x2800) != 0 && (*((_DWORD *)a2 + 66) & 0x40) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a Time Server. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 70;
    goto LABEL_237;
  }
  if ( (v37 & 0x1000) != 0 && (*((_DWORD *)a2 + 66) & 0x100) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: Responder is not a writable server. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 71;
    goto LABEL_237;
  }
  if ( (v37 & 0x8000) != 0 && (*((_DWORD *)a2 + 66) & 8) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: Responder is not a LDAP server. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 72;
    goto LABEL_237;
  }
  if ( v37 < 0 )
  {
    v38 = *((_QWORD *)a2 + 9);
    if ( !v38 || !*((_QWORD *)a2 + 6) )
    {
      if ( !a3 )
        return 0;
      NlPrintRoutine(
        0x100u,
        L"NetpDcMatchResponse: %ws: %ws: Netbios server or domain name needed and missing.\n",
        v38,
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
    v39 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v40 = 74;
    goto LABEL_168;
  }
  if ( *((_BYTE *)a1 + 227) )
  {
    v41 = *((_QWORD *)a2 + 30);
    if ( !v41 || (unsigned int)_o__wcsicmp(v41, *((_QWORD *)a1 + 5)) )
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
      v55 = *((_QWORD *)a1 + 5);
      v24 = *((_QWORD *)a2 + 30);
LABEL_160:
      WPP_SF_SSS(
        *((_QWORD *)v21 + 2),
        v22,
        (unsigned int)&WPP_11c6771b9160306a006e43c886fcea6e_Traceguids,
        v23,
        v24,
        v55);
      return 0;
    }
  }
  if ( (*((_DWORD *)a1 + 3) & 0x4000) != 0 )
  {
    v42 = *((_QWORD *)a2 + 9);
    if ( v42 )
    {
      if ( !(unsigned int)NetpwNameCompare(v42, *((_QWORD *)a1 + 10), 4) )
      {
        if ( !a3 )
          return 0;
        NlPrintRoutine(
          0x200u,
          L"NetpDcMatchResponse: %ws: response is from ourself and caller asked for AVOID_SELF.\n",
          *((_QWORD *)a1 + 9));
        v39 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          return 0;
        v40 = 76;
LABEL_168:
        WPP_SF_S(*((_QWORD *)v39 + 2), v40, &WPP_11c6771b9160306a006e43c886fcea6e_Traceguids, *((_QWORD *)a1 + 9));
        return 0;
      }
    }
  }
  v43 = *((_DWORD *)a1 + 3);
  if ( (v43 & 0x400) != 0 && (*((_DWORD *)a2 + 66) & 0x20) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from KDC. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 77;
    goto LABEL_237;
  }
  if ( (v43 & 0x200) != 0 && !*((_DWORD *)a2 + 24) )
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
  if ( (v43 & 0x80000) != 0 && (*((_DWORD *)a2 + 66) & 0x1800) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a WS2008 DC. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 79;
    goto LABEL_237;
  }
  if ( (v43 & 0x200000) != 0 && (*((_DWORD *)a2 + 66) & 0x4000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a WS2012 DC. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 80;
    goto LABEL_237;
  }
  if ( (v43 & 0x400000) != 0 && (*((_DWORD *)a2 + 66) & 0x8000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a WS2012R2 DC. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 81;
    goto LABEL_237;
  }
  if ( (v43 & 0x800000) != 0 && (*((_DWORD *)a2 + 66) & 0x10000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a WS2016 dc. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 82;
    goto LABEL_237;
  }
  if ( (v43 & 0x1000000) != 0 && (*((_DWORD *)a2 + 66) & 0x20000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a DC with key list request support. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 83;
    goto LABEL_237;
  }
  if ( (v43 & 0x4000000) != 0 && (*((_DWORD *)a2 + 66) & 0x80000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a WS2022 dc. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 84;
    goto LABEL_237;
  }
  if ( (v43 & 0x2000000) != 0 && (*((_DWORD *)a2 + 66) & 0x40000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a WS2025 dc. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 85;
    goto LABEL_237;
  }
  if ( (v43 & 0x8000000) != 0 && (*((_DWORD *)a2 + 66) & 0x100000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a WS2028 dc. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 86;
    goto LABEL_237;
  }
  if ( (*((_DWORD *)a1 + 3) & 0x100000) != 0 && (*((_DWORD *)a2 + 66) & 0x2000) == 0 )
  {
    if ( !a3 )
      return 0;
    LODWORD(v53) = *((_DWORD *)a2 + 66);
    NlPrintRoutine(
      0x100u,
      L"NetpDcMatchResponse: %ws: %ws: response not from a DC running web service. 0x%lx\n",
      *((_QWORD *)a2 + 9),
      *((_QWORD *)a1 + 9),
      v53);
    v35 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    v36 = 87;
    goto LABEL_237;
  }
  if ( (*((_BYTE *)a1 + 12) & 0x20) != 0 )
  {
    v44 = *((_DWORD *)a2 + 66);
    if ( (v44 & 0x10) == 0 )
    {
      v45 = (_QWORD *)((char *)a1 + 216);
      v46 = *((_QWORD *)a1 + 27);
      if ( v46 )
      {
        if ( *(char *)(v46 + 264) < 0 || (v44 & 0x80u) == 0 )
          return 0;
        NetpDcDerefCacheEntry((struct _NL_DC_CACHE_ENTRY *)v46);
        *v45 = 0;
        v47 = (_QWORD *)((char *)a1 + 216);
      }
      else
      {
        v47 = (_QWORD *)((char *)a1 + 216);
      }
      if ( !a3 )
        goto LABEL_262;
      NlPrintRoutine(
        0x200u,
        L"NetpDcMatchResponse: %ws: non-DS server responded when DS preferred\n",
        *((_QWORD *)a1 + 9));
      v48 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v49 = 88;
LABEL_260:
          WPP_SF_S(*((_QWORD *)v48 + 2), v49, &WPP_11c6771b9160306a006e43c886fcea6e_Traceguids, *((_QWORD *)a1 + 9));
          goto LABEL_262;
        }
        goto LABEL_262;
      }
      goto LABEL_261;
    }
  }
  if ( (*((_DWORD *)a1 + 3) & 0x2000) != 0 )
  {
    v50 = *((_DWORD *)a2 + 66);
    if ( (v50 & 0x200) == 0 )
    {
      v45 = (_QWORD *)((char *)a1 + 216);
      v51 = *((_QWORD *)a1 + 27);
      if ( v51 )
      {
        if ( *(char *)(v51 + 264) < 0 || (v50 & 0x80u) == 0 )
          return 0;
        NetpDcDerefCacheEntry((struct _NL_DC_CACHE_ENTRY *)v51);
        *v45 = 0;
        v47 = (_QWORD *)((char *)a1 + 216);
      }
      else
      {
        v47 = (_QWORD *)((char *)a1 + 216);
      }
      if ( !a3 )
        goto LABEL_262;
      NlPrintRoutine(
        0x200u,
        L"NetpDcMatchResponse: %ws: non-good time server responded when one preferred\n",
        *((_QWORD *)a1 + 9));
      v48 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v49 = 89;
          goto LABEL_260;
        }
LABEL_262:
        ++*((_DWORD *)a2 + 4);
        *((_BYTE *)a1 + 224) = matched;
        *v47 = a2;
        return 0;
      }
LABEL_261:
      v47 = v45;
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
0x18007b50c  mov     [rsp+arg_0], rbx
0x18007b511  mov     [rsp+arg_18], r9
0x18007b516  push    rbp
0x18007b517  push    rsi
0x18007b518  push    rdi
0x18007b519  push    r12
0x18007b51b  push    r13
0x18007b51d  push    r14
0x18007b51f  push    r15
0x18007b521  sub     rsp, 50h
0x18007b525  mov     rdi, rcx
0x18007b528  mov     dword ptr [r9], 0
0x18007b52f  mov     rcx, [rdx+48h]
0x18007b533  lea     r12, [rdx+50h]
0x18007b537  mov     ebp, r8d
0x18007b53a  mov     rbx, rdx
0x18007b53d  test    rcx, rcx
0x18007b540  jnz     short loc_18007B59D
0x18007b542  cmp     [r12], rcx
0x18007b546  jnz     short loc_18007B59D
0x18007b548  test    r8d, r8d
0x18007b54b  jz      loc_18007C592
0x18007b551  mov     r9, [rdi+48h]
0x18007b555  lea     rdx, aNetpdcmatchres_13; "NetpDcMatchResponse: %ws: %ws: Neither "...
0x18007b55c  xor     r8d, r8d
0x18007b55f  mov     ecx, 100h; unsigned int
0x18007b564  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007b569  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b570  mov     r14d, 4
0x18007b576  test    [rcx+1Ch], r14b
0x18007b57a  jz      loc_18007C592
0x18007b580  mov     sil, 2
0x18007b583  cmp     [rcx+19h], sil
0x18007b587  jb      loc_18007C592
0x18007b58d  lea     edx, [r14+33h]
0x18007b591  lea     r8, WPP_11c6771b9160306a006e43c886fcea6e_Traceguids
0x18007b598  jmp     loc_18007C0FA
0x18007b59d  mov     eax, [rdi+10h]
0x18007b5a0  mov     edx, 300h
0x18007b5a5  and     eax, edx
0x18007b5a7  mov     r14d, 4
0x18007b5ad  mov     r15d, 100h
0x18007b5b3  cmp     eax, edx
0x18007b5b5  jnz     loc_18007B66E
0x18007b5bb  mov     rcx, [r12]; unsigned __int16 *
0x18007b5bf  test    rcx, rcx
0x18007b5c2  jz      short loc_18007B5DA
0x18007b5c4  mov     rdx, [rdi+60h]; unsigned __int16 *
0x18007b5c8  test    rdx, rdx
0x18007b5cb  jz      short loc_18007B5DA
0x18007b5cd  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x18007b5d2  test    eax, eax
0x18007b5d4  jnz     loc_18007B761
0x18007b5da  mov     rcx, [rbx+48h]
0x18007b5de  test    rcx, rcx
0x18007b5e1  jz      short loc_18007B606
0x18007b5e3  mov     rdx, [rdi+60h]
0x18007b5e7  test    rdx, rdx
0x18007b5ea  jz      short loc_18007B606
0x18007b5ec  xor     r9d, r9d
0x18007b5ef  mov     r8d, r14d
0x18007b5f2  call    cs:__imp_NetpwNameCompare
0x18007b5f9  nop     dword ptr [rax+rax+00h]
0x18007b5fe  test    eax, eax
0x18007b600  jz      loc_18007B761
0x18007b606  test    ebp, ebp
0x18007b608  jz      loc_18007C592
0x18007b60e  mov     rax, [rbx+48h]
0x18007b612  lea     rdx, aNetpdcmatchres_1; "NetpDcMatchResponse: Ping response with"...
0x18007b619  mov     r9, [r12]
0x18007b61d  mov     ecx, r15d; unsigned int
0x18007b620  mov     r8, [rdi+60h]
0x18007b624  mov     [rsp+88h+var_68], rax
0x18007b629  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007b62e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b635  test    [rcx+1Ch], r14b
0x18007b639  jz      loc_18007C592
0x18007b63f  mov     sil, 2
0x18007b642  cmp     [rcx+19h], sil
0x18007b646  jb      loc_18007C592
0x18007b64c  mov     rax, [rbx+48h]
0x18007b650  lea     r8, WPP_11c6771b9160306a006e43c886fcea6e_Traceguids
0x18007b657  mov     r9, [rdi+60h]
0x18007b65b  mov     edx, 38h ; '8'
0x18007b660  mov     [rsp+88h+var_60], rax
0x18007b665  mov     rax, [r12]
0x18007b669  jmp     loc_18007BFBF
0x18007b66e  test    [rdi+10h], r15d
0x18007b672  jz      short loc_18007B6E9
0x18007b674  mov     rcx, [r12]; unsigned __int16 *
0x18007b678  test    rcx, rcx
0x18007b67b  jz      short loc_18007B693
0x18007b67d  mov     rdx, [rdi+60h]; unsigned __int16 *
0x18007b681  test    rdx, rdx
0x18007b684  jz      short loc_18007B693
0x18007b686  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x18007b68b  test    eax, eax
0x18007b68d  jnz     loc_18007B761
0x18007b693  test    ebp, ebp
0x18007b695  jz      loc_18007C592
0x18007b69b  mov     r9, [r12]
0x18007b69f  lea     rdx, aNetpdcmatchres_32; "NetpDcMatchResponse: Ping response with"...
0x18007b6a6  mov     r8, [rdi+60h]
0x18007b6aa  mov     ecx, r15d; unsigned int
0x18007b6ad  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007b6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b6b9  test    [rcx+1Ch], r14b
0x18007b6bd  jz      loc_18007C592
0x18007b6c3  mov     sil, 2
0x18007b6c6  cmp     [rcx+19h], sil
0x18007b6ca  jb      loc_18007C592
0x18007b6d0  mov     rax, [r12]
0x18007b6d4  mov     edx, 39h ; '9'
0x18007b6d9  mov     r9, [rdi+60h]
0x18007b6dd  lea     r8, WPP_11c6771b9160306a006e43c886fcea6e_Traceguids
0x18007b6e4  jmp     loc_18007C102
0x18007b6e9  test    dword ptr [rdi+10h], 200h
0x18007b6f0  jz      short loc_18007B761
0x18007b6f2  test    rcx, rcx
0x18007b6f5  jz      short loc_18007B716
0x18007b6f7  mov     rdx, [rdi+60h]
0x18007b6fb  test    rdx, rdx
0x18007b6fe  jz      short loc_18007B716
0x18007b700  xor     r9d, r9d
0x18007b703  mov     r8d, r14d
0x18007b706  call    cs:__imp_NetpwNameCompare
0x18007b70d  nop     dword ptr [rax+rax+00h]
0x18007b712  test    eax, eax
0x18007b714  jz      short loc_18007B761
0x18007b716  test    ebp, ebp
0x18007b718  jz      loc_18007C592
0x18007b71e  mov     r9, [rbx+48h]
0x18007b722  lea     rdx, aNetpdcmatchres_21; "NetpDcMatchResponse: Ping response with"...
0x18007b729  mov     r8, [rdi+60h]
0x18007b72d  mov     ecx, r15d; unsigned int
0x18007b730  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007b735  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b73c  test    [rcx+1Ch], r14b
0x18007b740  jz      loc_18007C592
0x18007b746  mov     sil, 2
0x18007b749  cmp     [rcx+19h], sil
0x18007b74d  jb      loc_18007C592
0x18007b753  mov     rax, [rbx+48h]
0x18007b757  mov     edx, 3Ah ; ':'
0x18007b75c  jmp     loc_18007B6D9
0x18007b761  movsxd  rax, dword ptr [rdi+8]
0x18007b765  lea     rcx, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A; _NL_DNS_NAME_TYPE_DESC near * NlDcDnsNameTypeDesc
0x18007b76c  xor     r13b, r13b
0x18007b76f  shl     rax, 5
0x18007b773  mov     [rsp+88h+arg_8], r13b
0x18007b77b  lea     r12, WPP_11c6771b9160306a006e43c886fcea6e_Traceguids
0x18007b782  mov     sil, 2
0x18007b785  cmp     [rax+rcx+14h], r14d
0x18007b78a  jnz     loc_18007B816
0x18007b790  mov     rcx, [rbx+0E8h]; unsigned __int16 *
0x18007b797  test    rcx, rcx
0x18007b79a  jz      short loc_18007B7B2
0x18007b79c  mov     rdx, [rdi+38h]; unsigned __int16 *
0x18007b7a0  test    rdx, rdx
0x18007b7a3  jz      short loc_18007B7B2
0x18007b7a5  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x18007b7aa  test    eax, eax
0x18007b7ac  jnz     loc_18007B9CE
0x18007b7b2  test    ebp, ebp
0x18007b7b4  jz      loc_18007C592
0x18007b7ba  mov     rax, [rdi+38h]
0x18007b7be  lea     rdx, aNetpdcmatchres_10; "NetpDcMatchResponse: %ws: asking for GC"...
0x18007b7c5  mov     r9, [rbx+0E8h]
0x18007b7cc  mov     ecx, r15d; unsigned int
0x18007b7cf  mov     r8, [rbx+48h]
0x18007b7d3  mov     [rsp+88h+var_68], rax
0x18007b7d8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007b7dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b7e4  test    [rcx+1Ch], r14b
0x18007b7e8  jz      loc_18007C592
0x18007b7ee  cmp     [rcx+19h], sil
0x18007b7f2  jb      loc_18007C592
0x18007b7f8  mov     rax, [rdi+38h]
0x18007b7fc  mov     edx, 3Bh ; ';'
0x18007b801  mov     r9, [rbx+48h]
0x18007b805  mov     [rsp+88h+var_60], rax
0x18007b80a  mov     rax, [rbx+0E8h]
0x18007b811  jmp     loc_18007BFBC
0x18007b816  mov     rcx, [rbx+30h]
0x18007b81a  test    rcx, rcx
0x18007b81d  jz      short loc_18007B844
0x18007b81f  mov     rdx, [rdi+30h]
0x18007b823  test    rdx, rdx
0x18007b826  jz      short loc_18007B844
0x18007b828  xor     r9d, r9d
0x18007b82b  lea     r8d, [r9+6]
0x18007b82f  call    cs:__imp_NetpwNameCompare
0x18007b836  nop     dword ptr [rax+rax+00h]
0x18007b83b  mov     [rsp+88h+var_48], 1
0x18007b840  test    eax, eax
0x18007b842  jz      short loc_18007B849
0x18007b844  mov     [rsp+88h+var_48], r13b
0x18007b849  mov     rax, [rbx+38h]
0x18007b84d  test    rax, rax
0x18007b850  jz      short loc_18007B87F
0x18007b852  mov     rcx, [rdi+38h]; unsigned __int16 *
0x18007b856  test    rcx, rcx
0x18007b859  jz      short loc_18007B87F
0x18007b85b  test    dword ptr [rdi+10h], 10000h
0x18007b862  jnz     short loc_18007B874
0x18007b864  mov     rdx, rcx; unsigned __int16 *
0x18007b867  mov     rcx, rax; unsigned __int16 *
0x18007b86a  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x18007b86f  mov     r13d, eax
0x18007b872  jmp     short loc_18007B87F
0x18007b874  mov     rdx, rax; unsigned __int16 *
0x18007b877  call    ?NlMatchDnsNamePrefix@@YAHPEBGPEAG@Z; NlMatchDnsNamePrefix(ushort const *,ushort *)
0x18007b87c  mov     r13b, al
0x18007b87f  cmp     [rsp+88h+var_48], 0
0x18007b884  jnz     loc_18007B9B0
0x18007b88a  test    r13b, r13b
0x18007b88d  jnz     loc_18007B9C6
0x18007b893  cmp     dword ptr [rdi+4], 5
0x18007b897  jnz     short loc_18007B8AF
0x18007b899  cmp     qword ptr [rbx+30h], 0
0x18007b89e  jnz     short loc_18007B8AF
0x18007b8a0  cmp     qword ptr [rbx+38h], 0
0x18007b8a5  jnz     short loc_18007B8AF
0x18007b8a7  mov     r13b, 1
0x18007b8aa  jmp     loc_18007B9CE
0x18007b8af  test    ebp, ebp
0x18007b8b1  jz      short loc_18007B929
0x18007b8b3  mov     rax, [rdi+38h]
0x18007b8b7  lea     rdx, aNetpdcmatchres_14; "NetpDcMatchResponse: %ws: Neither Netbi"...
0x18007b8be  mov     r9, [rbx+30h]
0x18007b8c2  mov     ecx, r15d; unsigned int
0x18007b8c5  mov     r8, [rbx+48h]
0x18007b8c9  mov     [rsp+88h+var_58], rax
0x18007b8ce  mov     rax, [rdi+30h]
0x18007b8d2  mov     [rsp+88h+var_60], rax
0x18007b8d7  mov     rax, [rbx+38h]
0x18007b8db  mov     [rsp+88h+var_68], rax
0x18007b8e0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007b8e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b8ec  test    [rcx+1Ch], r14b
0x18007b8f0  jz      short loc_18007B929
0x18007b8f2  cmp     [rcx+19h], sil
0x18007b8f6  jb      short loc_18007B929
0x18007b8f8  mov     rax, [rdi+38h]
0x18007b8fc  mov     r9, [rbx+48h]
0x18007b900  mov     rcx, [rcx+10h]; LoggerHandle
0x18007b904  mov     [rsp+88h+var_50], rax; __int64
0x18007b909  mov     rax, [rdi+30h]
0x18007b90d  mov     [rsp+88h+var_58], rax; __int64
0x18007b912  mov     rax, [rbx+38h]
0x18007b916  mov     [rsp+88h+var_60], rax; __int64
0x18007b91b  mov     rax, [rbx+30h]
0x18007b91f  mov     [rsp+88h+var_68], rax; __int64
0x18007b924  call    WPP_SF_SSSSS
0x18007b929  mov     rcx, [rdi+68h]
0x18007b92d  test    rcx, rcx
0x18007b930  jz      loc_18007C592
0x18007b936  mov     rax, [rbx+20h]
0x18007b93a  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18007b941  jnz     short loc_18007B954
0x18007b943  mov     rax, [rbx+28h]
0x18007b947  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18007b94e  jz      loc_18007C592
0x18007b954  mov     rax, [rbx+20h]
0x18007b958  cmp     rax, [rcx]
0x18007b95b  jnz     loc_18007C592
0x18007b961  mov     rax, [rbx+28h]
0x18007b965  cmp     rax, [rcx+8]
0x18007b969  jnz     loc_18007C592
0x18007b96f  test    ebp, ebp
0x18007b971  jz      short loc_18007B9C6
0x18007b973  mov     r8, [rbx+48h]
0x18007b977  lea     rdx, aNetpdcmatchres_29; "NetpDcMatchResponse: %ws: But Domain Gu"...
0x18007b97e  mov     ecx, r15d; unsigned int
0x18007b981  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007b986  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b98d  test    [rcx+1Ch], r14b
0x18007b991  jz      short loc_18007B9C6
0x18007b993  cmp     [rcx+19h], sil
0x18007b997  jb      short loc_18007B9C6
0x18007b999  mov     r9, [rbx+48h]
0x18007b99d  mov     edx, 3Dh ; '='
0x18007b9a2  mov     rcx, [rcx+10h]
0x18007b9a6  mov     r8, r12
0x18007b9a9  call    WPP_SF_S
0x18007b9ae  jmp     short loc_18007B9C6
0x18007b9b0  test    r13b, r13b
0x18007b9b3  jz      loc_18007B8A7
0x18007b9b9  test    [rdi+0ECh], sil
0x18007b9c0  jnz     loc_18007B8A7
0x18007b9c6  mov     r13b, [rsp+88h+arg_8]
0x18007b9ce  mov     rcx, [rdi+18h]
0x18007b9d2  test    rcx, rcx
0x18007b9d5  jz      loc_18007BA63
0x18007b9db  cmp     dword ptr [rbx+1Ch], 0Ch
0x18007b9df  jnz     loc_18007BB11
0x18007b9e5  mov     eax, [rbx+108h]
0x18007b9eb  and     al, 11h
0x18007b9ed  cmp     al, 1
0x18007b9ef  jnz     loc_18007BB11
  ... truncated ...
```
