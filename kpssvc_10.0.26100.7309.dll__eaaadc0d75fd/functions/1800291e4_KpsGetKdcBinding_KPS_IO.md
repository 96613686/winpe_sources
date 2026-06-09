# KpsGetKdcBinding(_KPS_IO *)

- ea: `0x1800291e4`
- end: `0x180029c40`
- name: `?KpsGetKdcBinding@@YAKPEAU_KPS_IO@@@Z`
- size: `2652`
- prototype: `__int64 __fastcall(struct _KPS_IO *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800202d0`

## callees

- `0x18001ada8`
- `0x18001ae0c`
- `0x18001ae38`
- `0x18001aecc`
- `0x18001af48`
- `0x180026a08`
- `0x180026d9c`
- `0x180028dc0`
- `0x1800291e4`
- `0x18002a180`
- `0x18002ba2c`
- `0x18002bbdc`
- `0x18002bc7c`
- `0x18002bd30`
- `0x18002c2b4`
- `0x18002dc4c`
- `0x18002dd00`
- `0x180031040`

## import_xrefs

- `WS2_32!GetAddrInfoW` at `0x180029ae6`
- `WS2_32!GetAddrInfoW` at `0x180029ae6`
- `WS2_32!FreeAddrInfoW` at `0x1800292f0`
- `WS2_32!FreeAddrInfoW` at `0x1800292f0`
- `logoncli!DsGetDcNameW` at `0x180029931`
- `logoncli!DsGetDcNameW` at `0x180029931`
- `netutils!NetApiBufferFree` at `0x1800292da`
- `netutils!NetApiBufferFree` at `0x1800292da`
- `ntdll!RtlDuplicateUnicodeString` at `0x180029521`
- `ntdll!RtlDuplicateUnicodeString` at `0x1800295c4`
- `ntdll!RtlDuplicateUnicodeString` at `0x1800296b2`
- `ntdll!RtlDuplicateUnicodeString` at `0x180029a53`
- `ntdll!RtlDuplicateUnicodeString` at `0x180029521`
- `ntdll!RtlDuplicateUnicodeString` at `0x1800295c4`
- `ntdll!RtlDuplicateUnicodeString` at `0x1800296b2`
- `ntdll!RtlDuplicateUnicodeString` at `0x180029a53`
- `ntdll!RtlLeaveCriticalSection` at `0x18002961c`
- `ntdll!RtlLeaveCriticalSection` at `0x18002974c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800297ef`
- `ntdll!RtlLeaveCriticalSection` at `0x180029bda`
- `ntdll!RtlLeaveCriticalSection` at `0x18002961c`
- `ntdll!RtlLeaveCriticalSection` at `0x18002974c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800297ef`
- `ntdll!RtlLeaveCriticalSection` at `0x180029bda`
- `ntdll!RtlEnterCriticalSection` at `0x18002931b`
- `ntdll!RtlEnterCriticalSection` at `0x180029343`
- `ntdll!RtlEnterCriticalSection` at `0x1800296f8`
- `ntdll!RtlEnterCriticalSection` at `0x18002931b`
- `ntdll!RtlEnterCriticalSection` at `0x180029343`
- `ntdll!RtlEnterCriticalSection` at `0x1800296f8`
- `ntdll!RtlInitUnicodeString` at `0x180029a32`
- `ntdll!RtlInitUnicodeString` at `0x180029a32`

## string_xrefs

- `0x180029ba0`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
__int64 __fastcall KpsGetKdcBinding(struct _KPS_IO *a1)
{
  unsigned int v1; // esi
  char v2; // r12
  struct _KPS_DOMAIN_HASH_ENTRY *v3; // rdi
  char v4; // r15
  int v5; // ebx
  _QWORD *v7; // rcx
  int v8; // r9d
  struct _UNICODE_STRING *v9; // r13
  struct _KPS_DOMAIN_HASH_ENTRY *v10; // rax
  __int64 v11; // r8
  _QWORD *v12; // rcx
  bool v13; // zf
  const wchar_t *v14; // r12
  __int64 v15; // rbx
  int v16; // r13d
  struct _UNICODE_STRING *v17; // r8
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  int v21; // edx
  int v22; // r8d
  const UNICODE_STRING *v23; // rbx
  __int64 v24; // r8
  int v25; // r13d
  int v26; // esi
  unsigned __int64 v27; // rbx
  const wchar_t *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  _QWORD *v31; // rcx
  int v32; // edx
  ULONG Flags; // r15d
  DWORD DcNameW; // eax
  int v35; // edx
  __int64 v36; // r8
  const wchar_t *v37; // rax
  __int64 v38; // rdx
  const WCHAR *v39; // rdx
  INT AddrInfoW; // eax
  int v41; // edx
  __int64 v42; // r9
  PADDRINFOW v43; // rax
  PDOMAIN_CONTROLLER_INFOW *DomainControllerInfo; // [rsp+30h] [rbp-D8h]
  char v46; // [rsp+48h] [rbp-C0h]
  char v47; // [rsp+49h] [rbp-BFh]
  __int64 v48; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID Buffer; // [rsp+58h] [rbp-B0h] BYREF
  PADDRINFOW pAddrInfo; // [rsp+60h] [rbp-A8h] BYREF
  PADDRINFOW pAddrInfo_8[2]; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD DestinationString[3]; // [rsp+78h] [rbp-90h] BYREF
  ADDRINFOW pHints; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v54[16]; // [rsp+C8h] [rbp-40h] BYREF
  const wchar_t *v55; // [rsp+D8h] [rbp-30h]
  int v56; // [rsp+E0h] [rbp-28h]
  int v57; // [rsp+E4h] [rbp-24h]
  _QWORD *v58; // [rsp+E8h] [rbp-20h]
  __int64 v59; // [rsp+F0h] [rbp-18h]
  __int64 *v60; // [rsp+F8h] [rbp-10h]
  __int64 v61; // [rsp+100h] [rbp-8h]

  Buffer = 0;
  v1 = 0;
  pAddrInfo = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  *(_OWORD *)pAddrInfo_8 = 0;
  *(_OWORD *)&DestinationString[1] = 0;
  memset(&pHints, 0, sizeof(pHints));
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, a1);
    v7 = WPP_GLOBAL_Control;
  }
  v8 = *((_DWORD *)a1 + 33);
  if ( (unsigned int)(v8 - 1) <= 1 )
  {
    v2 = 1;
  }
  else if ( v8 != 3 )
  {
    v1 = 1359;
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
      WPP_SF_dDsd(v7[2]);
    goto LABEL_9;
  }
  v47 = v2;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
  v9 = (struct _UNICODE_STRING *)((char *)a1 + 112);
  v46 = 1;
  v10 = KpsLookupDomainHashEntry(qword_18003ACE8, (struct _UNICODE_STRING *)a1 + 7);
  v3 = v10;
  if ( v10 && (*((_BYTE *)v10 + 28) & 1) != 0 )
  {
    if ( (*((_BYTE *)a1 + 148) & 1) != 0 && (*((_BYTE *)v10 + 48) & 0x10) == 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_26;
      WPP_SF_Z(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
        (char *)a1 + 112);
    }
    v12 = WPP_GLOBAL_Control;
LABEL_26:
    if ( !*((_DWORD *)a1 + 60) )
    {
      v13 = v2 ? *((_WORD *)v3 + 32) == 0 : *((_WORD *)v3 + 40) == 0;
      if ( !v13 )
      {
        if ( !dword_18003A9BC
          || *((_QWORD *)v3 + 11) + (unsigned __int64)(unsigned int)(60000 * dword_18003A9BC) >= (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                                                                                                * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64 )
        {
          v17 = (struct _UNICODE_STRING *)((char *)a1 + 184);
          if ( v2 )
            goto LABEL_50;
          goto LABEL_58;
        }
        v12 = WPP_GLOBAL_Control;
      }
    }
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 8) != 0 )
    {
      v14 = (const wchar_t *)*((_QWORD *)a1 + 15);
      if ( v14 )
      {
        v15 = -1;
        v12 = 0;
        do
          ++v15;
        while ( v14[v15] );
        v16 = 2 * v15 + 2;
      }
      else
      {
        v16 = 10;
        v14 = L"NULL";
      }
      v55 = v14;
      v56 = v16;
      v57 = 0;
      McGenEventWrite_EventWriteTransfer(v12, RediscoverKDC, v11, 2, v54);
      v12 = WPP_GLOBAL_Control;
      v9 = (struct _UNICODE_STRING *)((char *)a1 + 112);
    }
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x10) != 0 )
      WPP_SF_Z(v12[2], 46, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v9);
    v2 = v47;
    if ( v47 )
    {
      if ( *((int *)v3 + 12) < 0 )
      {
LABEL_48:
        v4 = 1;
LABEL_63:
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
        v46 = 0;
        if ( v4 )
        {
          v1 = KpsMitRealmDnsLookup(v9, v2, (struct _KPS_MIT_SERVER_LIST *)pAddrInfo_8);
          if ( v1 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_DZd(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, v1, (__int64)v9, v2);
LABEL_68:
              v2 = 0;
              goto LABEL_9;
            }
            goto LABEL_55;
          }
          v23 = (const UNICODE_STRING *)((char *)pAddrInfo_8[0] + 16 * WORD1(pAddrInfo_8[1]));
          v1 = RtlDuplicateUnicodeString(1u, v23, (PUNICODE_STRING)((char *)a1 + 184));
          if ( v1 )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_55;
            v19 = 50;
            v20 = (__int64)v23;
            goto LABEL_54;
          }
          RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
          if ( v2 )
          {
            KpsFreeMitServerList((struct _KPS_DOMAIN_HASH_ENTRY *)((char *)v3 + 56));
            *(_OWORD *)((char *)v3 + 56) = *(_OWORD *)pAddrInfo_8;
          }
          else
          {
            KpsFreeMitServerList((struct _KPS_DOMAIN_HASH_ENTRY *)((char *)v3 + 72));
            *(_OWORD *)((char *)v3 + 72) = *(_OWORD *)pAddrInfo_8;
          }
          *(_OWORD *)pAddrInfo_8 = 0;
          KpsDereferenceDomainHashEntry(v3);
          v3 = 0;
          RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
        }
        v46 = 0;
        goto LABEL_78;
      }
      v17 = (struct _UNICODE_STRING *)((char *)a1 + 184);
      *((_WORD *)v3 + 33) = (unsigned __int16)(*((_WORD *)v3 + 33) + 1) % *((_WORD *)v3 + 32);
LABEL_50:
      v1 = RtlDuplicateUnicodeString(
             1u,
             (PCUNICODE_STRING)(*((_QWORD *)v3 + 7) + 16LL * *((unsigned __int16 *)v3 + 33)),
             v17);
      if ( v1 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_55;
        v19 = 47;
        v20 = *((_QWORD *)v3 + 7) + 16LL * *((unsigned __int16 *)v3 + 33);
        goto LABEL_54;
      }
      goto LABEL_62;
    }
    if ( (*((_DWORD *)v3 + 12) & 0x40000000) != 0 )
      goto LABEL_48;
    v17 = (struct _UNICODE_STRING *)((char *)a1 + 184);
    *((_WORD *)v3 + 41) = (unsigned __int16)(*((_WORD *)v3 + 41) + 1) % *((_WORD *)v3 + 40);
LABEL_58:
    v1 = RtlDuplicateUnicodeString(
           1u,
           (PCUNICODE_STRING)(*((_QWORD *)v3 + 9) + 16LL * *((unsigned __int16 *)v3 + 41)),
           v17);
    if ( v1 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_55;
      v19 = 48;
      v20 = *((_QWORD *)v3 + 9) + 16LL * *((unsigned __int16 *)v3 + 41);
LABEL_54:
      WPP_SF_ZD(v18[2], v19, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v20, v1);
      goto LABEL_55;
    }
LABEL_62:
    KpsDereferenceDomainHashEntry(v3);
    v3 = 0;
    goto LABEL_63;
  }
  if ( !*((_DWORD *)a1 + 60)
    && v10
    && (!dword_18003A9BC
     || *((_QWORD *)v10 + 11) + (unsigned __int64)(unsigned int)(60000 * dword_18003A9BC) >= (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                                                                                            * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64)
    || (v5 = 1, v10) )
  {
    KpsDereferenceDomainHashEntry(v10);
    v3 = 0;
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
  v46 = 0;
  v25 = 10;
  v26 = v5 | *((_DWORD *)a1 + 32) | (((*((_DWORD *)a1 + 37) & 1) << 21) + 1536);
  v27 = -1;
  if ( (v26 & 1) != 0 )
  {
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 8) != 0 )
    {
      v28 = (const wchar_t *)*((_QWORD *)a1 + 15);
      if ( v28 )
      {
        v29 = -1;
        do
          ++v29;
        while ( v28[v29] );
        v30 = (unsigned int)(2 * v29 + 2);
      }
      else
      {
        v30 = 10;
        v28 = L"NULL";
      }
      v55 = v28;
      v56 = v30;
      v57 = 0;
      McGenEventWrite_EventWriteTransfer(v30, RediscoverKDC, v24, 2, v54);
    }
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_98;
    WPP_SF_Z(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
      (char *)a1 + 112);
  }
  v31 = WPP_GLOBAL_Control;
LABEL_98:
  LODWORD(v48) = 0;
  v13 = !_BitScanReverse((unsigned int *)&v32, v26 & 0x2E80010);
  if ( v13 )
  {
    Flags = v26;
    if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 0x10) != 0 )
      WPP_SF_(v31[2], 52, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids);
  }
  else
  {
    Flags = v26 & 0xFD17FFEF | (1 << v32);
  }
  DcNameW = DsGetDcNameW(0, *((LPCWSTR *)a1 + 15), 0, 0, Flags, (PDOMAIN_CONTROLLER_INFOW *)&Buffer);
  v1 = DcNameW;
  if ( DcNameW )
  {
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 2) != 0 )
    {
      LODWORD(v48) = DcNameW;
      v37 = (const wchar_t *)*((_QWORD *)a1 + 15);
      LODWORD(DestinationString[0]) = Flags;
      if ( v37 )
      {
        do
          ++v27;
        while ( v37[v27] );
        v25 = 2 * v27 + 2;
      }
      else
      {
        v37 = L"NULL";
      }
      v55 = v37;
      v56 = v25;
      v57 = 0;
      v58 = DestinationString;
      v60 = &v48;
      v59 = 4;
      v61 = 4;
      McGenEventWrite_EventWriteTransfer(0, "g", v36, 4, v54);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DDsd(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, v36, Flags, v1);
    goto LABEL_55;
  }
  v38 = *((_QWORD *)Buffer + 1);
  do
    ++v27;
  while ( *(_WORD *)(v38 + 2 * v27) );
  if ( v27 < 2 || *(_WORD *)v38 != 92 || *(_WORD *)(v38 + 2) != 92 )
  {
    v1 = 87;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LODWORD(DomainControllerInfo) = 1013;
      WPP_SF_Dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
        87,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
        DomainControllerInfo);
    }
    v2 = 0;
    goto LABEL_9;
  }
  RtlInitUnicodeString((PUNICODE_STRING)&DestinationString[1], (PCWSTR)(v38 + 4));
  v1 = RtlDuplicateUnicodeString(1u, (PCUNICODE_STRING)&DestinationString[1], (PUNICODE_STRING)((char *)a1 + 184));
  if ( v1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_ZD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
        &DestinationString[1],
        v1);
      goto LABEL_68;
    }
LABEL_55:
    v2 = v46;
    goto LABEL_9;
  }
LABEL_78:
  v2 = 0;
  pHints.ai_family = 0;
  pHints.ai_socktype = 1;
  if ( *((_WORD *)a1 + 92) )
    *(_WORD *)(*((_QWORD *)a1 + 24) + 2 * ((unsigned __int64)*((unsigned __int16 *)a1 + 92) >> 1)) = 0;
  else
    *((_QWORD *)a1 + 24) = 0;
  v39 = L"88";
  if ( !v47 )
    v39 = L"464";
  AddrInfoW = GetAddrInfoW(*((PCWSTR *)a1 + 24), v39, &pHints, &pAddrInfo);
  if ( AddrInfoW )
  {
    v1 = AddrInfoW;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_DZsd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a1 + 184);
      goto LABEL_9;
    }
    goto LABEL_55;
  }
  if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 8) != 0 )
  {
    if ( Buffer )
      v42 = *(_QWORD *)Buffer;
    else
      LODWORD(v42) = 0;
    McTemplateU0zzz_EventWriteTransfer(*((_QWORD *)a1 + 24), v41, *((_QWORD *)a1 + 15), v42, *((_QWORD *)a1 + 24));
  }
  v43 = pAddrInfo;
  *((_QWORD *)a1 + 25) = pAddrInfo;
  *((_QWORD *)a1 + 26) = v43;
  pAddrInfo = 0;
LABEL_9:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( pAddrInfo )
    FreeAddrInfoW(pAddrInfo);
  KpsFreeMitServerList((struct _KPS_MIT_SERVER_LIST *)pAddrInfo_8);
  if ( v3 )
  {
    if ( !v2 )
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
    KpsDereferenceDomainHashEntry(v3);
    goto LABEL_140;
  }
  if ( v2 )
LABEL_140:
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x1800291e4  mov     rax, rsp
0x1800291e7  mov     [rax+10h], rbx
0x1800291eb  mov     [rax+18h], rsi
0x1800291ef  mov     [rax+20h], rdi
0x1800291f3  push    rbp
0x1800291f4  push    r12
0x1800291f6  push    r13
0x1800291f8  push    r14
0x1800291fa  push    r15
0x1800291fc  lea     rbp, [rax-38h]
0x180029200  sub     rsp, 110h
0x180029207  mov     rax, cs:__security_cookie
0x18002920e  xor     rax, rsp
0x180029211  mov     [rbp+30h+var_30], rax
0x180029215  xor     r13d, r13d
0x180029218  xorps   xmm1, xmm1
0x18002921b  xorps   xmm0, xmm0
0x18002921e  mov     [rsp+130h+Buffer], r13
0x180029223  mov     esi, r13d
0x180029226  mov     [rsp+130h+pAddrInfo], r13
0x18002922b  mov     r12b, r13b
0x18002922e  mov     edi, r13d
0x180029231  mov     r15b, r13b
0x180029234  mov     ebx, r13d
0x180029237  movups  xmmword ptr [rsp+130h+pAddrInfo+8], xmm0
0x18002923c  mov     r14, rcx
0x18002923f  movups  xmmword ptr [rsp+130h+DestinationString+8], xmm0
0x180029244  movups  xmmword ptr [rbp+30h+pHints.ai_flags], xmm1
0x180029248  movups  xmmword ptr [rbp+30h+pHints.ai_addrlen], xmm1
0x18002924c  movups  xmmword ptr [rbp+30h+pHints.ai_addr], xmm1
0x180029250  mov     rcx, cs:WPP_GLOBAL_Control
0x180029257  lea     r8, WPP_GLOBAL_Control
0x18002925e  cmp     rcx, r8
0x180029261  jz      short loc_18002928E
0x180029263  test    byte ptr [rcx+1Ch], 20h
0x180029267  jz      short loc_18002928E
0x180029269  mov     rcx, [rcx+10h]
0x18002926d  lea     edx, [r13+2Bh]
0x180029271  mov     r9, r14
0x180029274  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002927b  call    WPP_SF_q
0x180029280  mov     rcx, cs:WPP_GLOBAL_Control
0x180029287  lea     r8, WPP_GLOBAL_Control
0x18002928e  mov     r9d, [r14+84h]
0x180029295  mov     edx, 1
0x18002929a  lea     eax, [r9-1]
0x18002929e  cmp     eax, edx
0x1800292a0  jbe     loc_180029334
0x1800292a6  cmp     r9d, 3
0x1800292aa  jz      loc_180029337
0x1800292b0  mov     esi, 54Fh
0x1800292b5  cmp     rcx, r8
0x1800292b8  jz      short loc_1800292C9
0x1800292ba  test    byte ptr [rcx+1Ch], 8
0x1800292be  jz      short loc_1800292C9
0x1800292c0  mov     rcx, [rcx+10h]
0x1800292c4  call    WPP_SF_dDsd
0x1800292c9  lea     rbx, WPP_GLOBAL_Control
0x1800292d0  mov     rcx, [rsp+130h+Buffer]; Buffer
0x1800292d5  test    rcx, rcx
0x1800292d8  jz      short loc_1800292E6
0x1800292da  call    cs:__imp_NetApiBufferFree
0x1800292e1  nop     dword ptr [rax+rax+00h]
0x1800292e6  mov     rcx, [rsp+130h+pAddrInfo]; pAddrInfo
0x1800292eb  test    rcx, rcx
0x1800292ee  jz      short loc_1800292FC
0x1800292f0  call    cs:__imp_FreeAddrInfoW
0x1800292f7  nop     dword ptr [rax+rax+00h]
0x1800292fc  lea     rcx, [rsp+130h+pAddrInfo+8]; struct _KPS_MIT_SERVER_LIST *
0x180029301  call    ?KpsFreeMitServerList@@YAXPEAU_KPS_MIT_SERVER_LIST@@@Z; KpsFreeMitServerList(_KPS_MIT_SERVER_LIST *)
0x180029306  test    rdi, rdi
0x180029309  jz      loc_180029BCE
0x18002930f  test    r12b, r12b
0x180029312  jnz     short loc_180029327
0x180029314  lea     rcx, ?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A+8; CriticalSection
0x18002931b  call    cs:__imp_RtlEnterCriticalSection
0x180029322  nop     dword ptr [rax+rax+00h]
0x180029327  mov     rcx, rdi; lpMem
0x18002932a  call    ?KpsDereferenceDomainHashEntry@@YAXPEAU_KPS_DOMAIN_HASH_ENTRY@@@Z; KpsDereferenceDomainHashEntry(_KPS_DOMAIN_HASH_ENTRY *)
0x18002932f  jmp     loc_180029BD3
0x180029334  mov     r12b, dl
0x180029337  lea     rcx, ?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A+8; CriticalSection
0x18002933e  mov     [rsp+130h+var_F0+1], r12b
0x180029343  call    cs:__imp_RtlEnterCriticalSection
0x18002934a  nop     dword ptr [rax+rax+00h]
0x18002934f  mov     rcx, cs:qword_18003ACE8; struct _RTL_DYNAMIC_HASH_TABLE *
0x180029356  lea     r13, [r14+70h]
0x18002935a  mov     rdx, r13; struct _UNICODE_STRING *
0x18002935d  mov     [rsp+130h+var_F0], 1
0x180029362  call    ?KpsLookupDomainHashEntry@@YAPEAU_KPS_DOMAIN_HASH_ENTRY@@PEAU_RTL_DYNAMIC_HASH_TABLE@@PEAU_UNICODE_STRING@@@Z; KpsLookupDomainHashEntry(_RTL_DYNAMIC_HASH_TABLE *,_UNICODE_STRING *)
0x180029367  mov     rdi, rax
0x18002936a  mov     r9d, 1
0x180029370  test    rax, rax
0x180029373  jz      loc_18002978E
0x180029379  test    [rax+1Ch], r9b
0x18002937d  jz      loc_18002978E
0x180029383  test    [r14+94h], r9b
0x18002938a  jz      short loc_1800293C8
0x18002938c  test    byte ptr [rax+30h], 10h
0x180029390  jnz     short loc_1800293C8
0x180029392  mov     rcx, cs:WPP_GLOBAL_Control
0x180029399  lea     rax, WPP_GLOBAL_Control
0x1800293a0  cmp     rcx, rax
0x1800293a3  jz      short loc_1800293CF
0x1800293a5  test    byte ptr [rcx+1Ch], 2
0x1800293a9  jz      short loc_1800293CF
0x1800293ab  mov     rcx, [rcx+10h]
0x1800293af  lea     edx, [r9+2Ch]
0x1800293b3  mov     r9, r13
0x1800293b6  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x1800293bd  call    WPP_SF_Z
0x1800293c2  mov     r9d, 1
0x1800293c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800293cf  cmp     [r14+0F0h], ebx
0x1800293d6  jnz     short loc_180029425
0x1800293d8  test    r12b, r12b
0x1800293db  jz      short loc_1800293E3
0x1800293dd  cmp     [rdi+40h], bx
0x1800293e1  jmp     short loc_1800293E7
0x1800293e3  cmp     [rdi+50h], bx
0x1800293e7  jz      short loc_180029425
0x1800293e9  cmp     cs:dword_18003A9BC, ebx
0x1800293ef  jz      short loc_180029453
0x1800293f1  mov     ecx, ds:7FFE0004h
0x1800293f8  mov     eax, 7FFE0320h
0x1800293fd  shl     rcx, 20h
0x180029401  mov     rax, [rax]
0x180029404  shl     rax, 8
0x180029408  mul     rcx
0x18002940b  imul    ecx, cs:dword_18003A9BC, 0EA60h
0x180029415  add     rcx, [rdi+58h]
0x180029419  cmp     rcx, rdx
0x18002941c  jnb     short loc_180029453
0x18002941e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029425  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 8
0x18002942c  jz      short loc_1800294A6
0x18002942e  mov     r12, [r14+78h]
0x180029432  test    r12, r12
0x180029435  jz      short loc_180029468
0x180029437  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002943b  xor     ecx, ecx
0x18002943d  inc     rbx
0x180029440  cmp     [r12+rbx*2], cx
0x180029445  jnz     short loc_18002943D
0x180029447  lea     r13d, ds:2[rbx*2]
0x18002944f  xor     ebx, ebx
0x180029451  jmp     short loc_180029475
0x180029453  lea     r8, [r14+0B8h]
0x18002945a  test    r12b, r12b
0x18002945d  jz      loc_1800295B5
0x180029463  jmp     loc_180029512
0x180029468  mov     r13d, 0Ah
0x18002946e  lea     r12, aNull_0; "NULL"
0x180029475  lea     rax, [rbp+30h+var_70]
0x180029479  mov     [rbp+30h+var_60], r12
0x18002947d  mov     r9d, 2
0x180029483  mov     qword ptr [rsp+130h+Flags], rax
0x180029488  lea     rdx, RediscoverKDC
0x18002948f  mov     [rbp+30h+var_58], r13d
0x180029493  mov     [rbp+30h+var_54], ebx
0x180029496  call    McGenEventWrite_EventWriteTransfer
0x18002949b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800294a2  lea     r13, [r14+70h]
0x1800294a6  lea     rax, WPP_GLOBAL_Control
0x1800294ad  cmp     rcx, rax
0x1800294b0  jz      short loc_1800294D0
0x1800294b2  test    byte ptr [rcx+1Ch], 10h
0x1800294b6  jz      short loc_1800294D0
0x1800294b8  mov     rcx, [rcx+10h]
0x1800294bc  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x1800294c3  mov     edx, 2Eh ; '.'
0x1800294c8  mov     r9, r13
0x1800294cb  call    WPP_SF_Z
0x1800294d0  mov     r12b, [rsp+130h+var_F0+1]
0x1800294d5  test    r12b, r12b
0x1800294d8  jz      loc_180029584
0x1800294de  cmp     [rdi+30h], ebx
0x1800294e1  jge     short loc_1800294EE
0x1800294e3  mov     r15d, 1
0x1800294e9  jmp     loc_180029615
0x1800294ee  movzx   eax, word ptr [rdi+42h]
0x1800294f2  lea     r8, [r14+0B8h]; DestinationString
0x1800294f9  movzx   ecx, word ptr [rdi+40h]
0x1800294fd  mov     r9d, 1
0x180029503  add     ax, r9w
0x180029507  xor     edx, edx
0x180029509  movzx   eax, ax
0x18002950c  div     ecx
0x18002950e  mov     [rdi+42h], dx
0x180029512  movzx   edx, word ptr [rdi+42h]
0x180029516  mov     ecx, r9d; Flags
0x180029519  shl     rdx, 4
0x18002951d  add     rdx, [rdi+38h]; SourceString
0x180029521  call    cs:__imp_RtlDuplicateUnicodeString
0x180029528  nop     dword ptr [rax+rax+00h]
0x18002952d  mov     esi, eax
0x18002952f  test    eax, eax
0x180029531  jz      loc_18002960A
0x180029537  mov     rcx, cs:WPP_GLOBAL_Control
0x18002953e  lea     rax, WPP_GLOBAL_Control
0x180029545  cmp     rcx, rax
0x180029548  jz      short loc_18002957A
0x18002954a  mov     edx, 1
0x18002954f  test    [rcx+1Ch], dl
0x180029552  jz      short loc_18002957A
0x180029554  movzx   r9d, word ptr [rdi+42h]
0x180029559  mov     edx, 2Fh ; '/'
0x18002955e  shl     r9, 4
0x180029562  add     r9, [rdi+38h]
0x180029566  mov     rcx, [rcx+10h]
0x18002956a  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180029571  mov     [rsp+130h+Flags], esi
0x180029575  call    WPP_SF_ZD
0x18002957a  mov     r12b, [rsp+130h+var_F0]
0x18002957f  jmp     loc_1800292C9
0x180029584  test    dword ptr [rdi+30h], 40000000h
0x18002958b  jnz     loc_1800294E3
0x180029591  movzx   eax, word ptr [rdi+52h]
0x180029595  lea     r8, [r14+0B8h]; DestinationString
0x18002959c  movzx   ecx, word ptr [rdi+50h]
0x1800295a0  mov     r9d, 1
0x1800295a6  add     ax, r9w
0x1800295aa  xor     edx, edx
0x1800295ac  movzx   eax, ax
0x1800295af  div     ecx
0x1800295b1  mov     [rdi+52h], dx
0x1800295b5  movzx   edx, word ptr [rdi+52h]
0x1800295b9  mov     ecx, r9d; Flags
0x1800295bc  shl     rdx, 4
0x1800295c0  add     rdx, [rdi+48h]; SourceString
0x1800295c4  call    cs:__imp_RtlDuplicateUnicodeString
0x1800295cb  nop     dword ptr [rax+rax+00h]
0x1800295d0  mov     esi, eax
0x1800295d2  test    eax, eax
0x1800295d4  jz      short loc_18002960A
0x1800295d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800295dd  lea     rax, WPP_GLOBAL_Control
0x1800295e4  cmp     rcx, rax
0x1800295e7  jz      short loc_18002957A
0x1800295e9  mov     edx, 1
0x1800295ee  test    [rcx+1Ch], dl
0x1800295f1  jz      short loc_18002957A
0x1800295f3  movzx   r9d, word ptr [rdi+52h]
0x1800295f8  mov     edx, 30h ; '0'
0x1800295fd  shl     r9, 4
0x180029601  add     r9, [rdi+48h]
0x180029605  jmp     loc_180029566
0x18002960a  mov     rcx, rdi; lpMem
0x18002960d  call    ?KpsDereferenceDomainHashEntry@@YAXPEAU_KPS_DOMAIN_HASH_ENTRY@@@Z; KpsDereferenceDomainHashEntry(_KPS_DOMAIN_HASH_ENTRY *)
0x180029612  mov     rdi, rbx
0x180029615  lea     rcx, ?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A+8; CriticalSection
0x18002961c  call    cs:__imp_RtlLeaveCriticalSection
0x180029623  nop     dword ptr [rax+rax+00h]
0x180029628  mov     [rsp+130h+var_F0], bl
0x18002962c  test    r15b, r15b
0x18002962f  jz      loc_18002975A
0x180029635  lea     r8, [rsp+130h+pAddrInfo+8]; struct _KPS_MIT_SERVER_LIST *
0x18002963a  mov     dl, r12b; unsigned __int8
0x18002963d  mov     rcx, r13; struct _UNICODE_STRING *
0x180029640  call    ?KpsMitRealmDnsLookup@@YAKPEAU_UNICODE_STRING@@EPEAU_KPS_MIT_SERVER_LIST@@@Z; KpsMitRealmDnsLookup(_UNICODE_STRING *,uchar,_KPS_MIT_SERVER_LIST *)
0x180029645  mov     esi, eax
0x180029647  test    eax, eax
0x180029649  jz      short loc_180029691
0x18002964b  mov     rcx, cs:WPP_GLOBAL_Control
0x180029652  lea     rax, WPP_GLOBAL_Control
0x180029659  cmp     rcx, rax
0x18002965c  jz      loc_18002957A
0x180029662  mov     eax, 1
0x180029667  test    [rcx+1Ch], al
0x18002966a  jz      loc_18002957A
0x180029670  mov     rcx, [rcx+10h]
0x180029674  mov     r9d, esi
0x180029677  movzx   eax, r12b
0x18002967b  mov     dword ptr [rsp+130h+DomainControllerInfo], eax
0x18002967f  mov     qword ptr [rsp+130h+Flags], r13
0x180029684  call    WPP_SF_DZd
0x180029689  mov     r12b, bl
0x18002968c  jmp     loc_1800292C9
0x180029691  movzx   ebx, word ptr [rsp+130h+var_C8+2]
0x180029696  lea     r8, [r14+0B8h]; DestinationString
0x18002969d  shl     rbx, 4
0x1800296a1  mov     r15d, 1
0x1800296a7  add     rbx, [rsp+130h+pAddrInfo+8]
0x1800296ac  mov     ecx, r15d; Flags
0x1800296af  mov     rdx, rbx; SourceString
0x1800296b2  call    cs:__imp_RtlDuplicateUnicodeString
0x1800296b9  nop     dword ptr [rax+rax+00h]
0x1800296be  mov     esi, eax
0x1800296c0  test    eax, eax
0x1800296c2  jz      short loc_1800296F1
0x1800296c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800296cb  lea     rax, WPP_GLOBAL_Control
0x1800296d2  cmp     rcx, rax
0x1800296d5  jz      loc_18002957A
0x1800296db  test    [rcx+1Ch], r15b
0x1800296df  jz      loc_18002957A
0x1800296e5  lea     edx, [r15+31h]
0x1800296e9  mov     r9, rbx
0x1800296ec  jmp     loc_180029566
0x1800296f1  lea     rcx, ?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A+8; CriticalSection
  ... truncated ...
```
