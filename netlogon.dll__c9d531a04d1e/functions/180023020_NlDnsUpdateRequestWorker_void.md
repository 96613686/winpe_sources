# NlDnsUpdateRequestWorker(void *)

- ea: `0x180023020`
- end: `0x1800237ad`
- name: `?NlDnsUpdateRequestWorker@@YAXPEAX@Z`
- size: `1933`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180007278`
- `0x18000ba1c`
- `0x18000e270`
- `0x18000ed34`
- `0x18000edf4`
- `0x180023020`
- `0x180023f3c`
- `0x180024aa0`
- `0x18003f684`
- `0x180074928`
- `0x180082e88`
- `0x180083094`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180023596`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180023596`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023715`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002375a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023715`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002375a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002310c`
- `ntdll!RtlLeaveCriticalSection` at `0x18002373b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002379e`
- `ntdll!RtlLeaveCriticalSection` at `0x18002310c`
- `ntdll!RtlLeaveCriticalSection` at `0x18002373b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002379e`
- `ntdll!RtlEnterCriticalSection` at `0x1800230cb`
- `ntdll!RtlEnterCriticalSection` at `0x18002372b`
- `ntdll!RtlEnterCriticalSection` at `0x18002378a`
- `ntdll!RtlEnterCriticalSection` at `0x1800230cb`
- `ntdll!RtlEnterCriticalSection` at `0x18002372b`
- `ntdll!RtlEnterCriticalSection` at `0x18002378a`
- `netutils!NetApiBufferFree` at `0x1800231cd`
- `netutils!NetApiBufferFree` at `0x1800236d6`
- `netutils!NetApiBufferFree` at `0x1800236e0`
- `netutils!NetApiBufferFree` at `0x18002374c`
- `netutils!NetApiBufferFree` at `0x1800231cd`
- `netutils!NetApiBufferFree` at `0x1800236d6`
- `netutils!NetApiBufferFree` at `0x1800236e0`
- `netutils!NetApiBufferFree` at `0x18002374c`
- `DNSAPI!DnsReplaceRecordSetUTF8` at `0x1800233a7`
- `DNSAPI!DnsReplaceRecordSetUTF8` at `0x1800233a7`
- `DNSAPI!DnsModifyRecordsInSet_UTF8` at `0x1800233ec`
- `DNSAPI!DnsModifyRecordsInSet_UTF8` at `0x180023477`
- `DNSAPI!DnsModifyRecordsInSet_UTF8` at `0x1800233ec`
- `DNSAPI!DnsModifyRecordsInSet_UTF8` at `0x180023477`
- `WS2_32!GetNameInfoW` at `0x180023579`
- `WS2_32!GetNameInfoW` at `0x180023579`

## string_xrefs

- `0x180023115`: `Processing a Dns update request for %hs. SiteName: %ws, DnsTtl: %ld, DnsNamesCount: %ld\n`
- `0x180023235`: `NlDnsUpdateRequestWorker: %hs: %ws: NetpDcBuildDnsName failed. %ld\n`
- `0x180023408`: `NlDnsUpdateRequestWorker: Registered (success)`
- `0x180023437`: `NlDnsUpdateRequestWorker: Failed to register (%ld)`
- `0x180023493`: `NlDnsUpdateRequestWorker: Deregistered (success)`
- `0x18002349f`: `NlDnsUpdateRequestWorker: Failed to deregister (%ld)`

## pseudocode

```c
void __fastcall NlDnsUpdateRequestWorker(void *a1)
{
  char *Utf8StrFromWStr; // rsi
  DWORD v2; // r12d
  char *v3; // rbx
  _QWORD *v4; // rcx
  HLOCAL *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r14
  char *v9; // r15
  __int64 v10; // r13
  __int64 v11; // rdi
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // eax
  __int64 v17; // rdi
  DNS_STATUS v18; // eax
  unsigned int v19; // r9d
  unsigned int v20; // edi
  char *v21; // rcx
  struct _NL_DNS_NAME_INFO *v22; // rdx
  unsigned __int16 *v23; // r10
  DNS_STATUS v24; // eax
  const SOCKADDR *v25; // rcx
  unsigned int v26; // eax
  unsigned __int16 *v27; // rcx
  const CHAR *v28; // rcx
  unsigned int v29; // eax
  unsigned __int16 *v30; // rcx
  PVOID pReserved; // [rsp+20h] [rbp-E0h]
  PVOID pReserveda; // [rsp+20h] [rbp-E0h]
  PVOID v33; // [rsp+28h] [rbp-D8h]
  __int64 v34; // [rsp+38h] [rbp-C8h]
  DWORD v35; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v36; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+50h] [rbp-B0h]
  int pExtraInfo; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v39[12]; // [rsp+64h] [rbp-9Ch] BYREF
  int v40; // [rsp+70h] [rbp-90h]
  unsigned int v41; // [rsp+78h] [rbp-88h]
  unsigned __int8 v42[2]; // [rsp+7Ch] [rbp-84h] BYREF
  __int16 v43; // [rsp+7Eh] [rbp-82h] BYREF
  _BYTE v44[6]; // [rsp+80h] [rbp-80h]
  __int128 v45; // [rsp+88h] [rbp-78h]
  DNS_RECORDA pReplaceSet; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD pSockaddr[3]; // [rsp+120h] [rbp+20h] BYREF
  int v48; // [rsp+138h] [rbp+38h]
  unsigned __int16 *v49[2]; // [rsp+140h] [rbp+40h] BYREF
  LPVOID v50[2]; // [rsp+150h] [rbp+50h]
  __int128 v51; // [rsp+160h] [rbp+60h]
  wchar_t Buffer[16]; // [rsp+170h] [rbp+70h] BYREF
  wchar_t v53[16]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR pNodeBuffer[72]; // [rsp+1B0h] [rbp+B0h] BYREF
  CHAR MultiByteStr[256]; // [rsp+240h] [rbp+140h] BYREF

  memset_0(MultiByteStr, 0, sizeof(MultiByteStr));
  Utf8StrFromWStr = 0;
  memset_0(&pReplaceSet, 0, sizeof(pReplaceSet));
  v35 = 0;
  v2 = 0;
  memset_0(&pExtraInfo, 0, 0x60u);
  wcscpy(Buffer, L"<UNAILABLE>");
  wcscpy(v53, L"<UNAILABLE>");
  *(_OWORD *)v49 = 0;
  *(_OWORD *)v50 = 0;
  v51 = 0;
  while ( 1 )
  {
    RtlEnterCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
    v3 = (char *)NlGlobalDnsUpdateRequestList;
    if ( NlGlobalDnsUpdateRequestList == &NlGlobalDnsUpdateRequestList )
      goto LABEL_73;
    v4 = *(_QWORD **)NlGlobalDnsUpdateRequestList;
    if ( *(HLOCAL *)(*(_QWORD *)NlGlobalDnsUpdateRequestList + 8LL) != NlGlobalDnsUpdateRequestList
      || (v5 = (HLOCAL *)*((_QWORD *)NlGlobalDnsUpdateRequestList + 1), *v5 != NlGlobalDnsUpdateRequestList) )
    {
      __fastfail(3u);
    }
    *v5 = v4;
    v4[1] = v5;
    RtlLeaveCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
    LODWORD(v33) = *((_DWORD *)v3 + 18);
    LODWORD(pReserved) = *((_DWORD *)v3 + 16);
    NlPrintRoutine(
      0x20000u,
      L"Processing a Dns update request for %hs. SiteName: %ws, DnsTtl: %ld, DnsNamesCount: %ld\n",
      *((_QWORD *)v3 + 2),
      *((_QWORD *)v3 + 7),
      pReserved,
      v33);
    if ( !dword_1800F1264 )
    {
      v2 |= 0x2000u;
      v35 = v2;
    }
    v6 = 0;
    v37 = 0;
    if ( *((_DWORD *)v3 + 18) )
      break;
LABEL_71:
    LocalFree(v3);
    if ( NlGlobalTerminate )
    {
      RtlEnterCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
LABEL_73:
      NlGlobalDnsUpdateRequestInProgress = 0;
      RtlLeaveCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
      v3 = 0;
      goto LABEL_74;
    }
  }
  while ( 1 )
  {
    v7 = *((_QWORD *)v3 + 10);
    v8 = 5 * v6;
    v9 = 0;
    v10 = *(int *)(v7 + 40 * v6);
    if ( *(_BYTE *)(v7 + 40 * v6 + 32) == 1 )
      break;
    if ( NetpCreateUtf8StrFromWStr(*(LPCWCH *)(v7 + 40 * v6 + 8), MultiByteStr, 255) )
    {
      v11 = v10;
      goto LABEL_29;
    }
    *(_DWORD *)(*((_QWORD *)v3 + 10) + 8 * v8 + 36) = 8;
LABEL_69:
    v6 = (unsigned int)(v37 + 1);
    v37 = v6;
    if ( (unsigned int)v6 >= *((_DWORD *)v3 + 18) )
    {
      v35 = v2;
      goto LABEL_71;
    }
  }
  v36 = 0;
  v11 = v10;
  if ( *((_WORD *)&NlDcDnsNameTypeDesc + 16 * v10 + 12) == 5 )
    v36 = (unsigned __int16 *)(v3 + 40);
  v12 = *(_DWORD *)(v7 + 40 * v6 + 16);
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          if ( v15 == 1 )
          {
            if ( Utf8StrFromWStr )
              NetApiBufferFree(Utf8StrFromWStr);
            Utf8StrFromWStr = NetpCreateUtf8StrFromWStr(*(LPCWCH *)(*((_QWORD *)v3 + 10) + 8 * v8 + 8), 0, 0);
            v9 = Utf8StrFromWStr;
          }
        }
        else
        {
          v9 = NlGlobalUtf8DnsForestNameAlias;
        }
      }
      else
      {
        v9 = NlGlobalUtf8DnsForestName;
      }
    }
    else
    {
      v9 = (char *)*((_QWORD *)v3 + 4);
    }
  }
  else
  {
    v9 = (char *)*((_QWORD *)v3 + 3);
  }
  v16 = NetpDcBuildDnsName((unsigned int)v10, v36, *((_QWORD *)v3 + 7), v9, MultiByteStr);
  if ( v16 )
  {
    LODWORD(pReserveda) = v16;
    *(_DWORD *)(*((_QWORD *)v3 + 10) + 8 * v8 + 36) = v16;
    NlPrintRoutine(
      0x100u,
      L"NlDnsUpdateRequestWorker: %hs: %ws: NetpDcBuildDnsName failed. %ld\n",
      *((_QWORD *)v3 + 2),
      *(&NlDcDnsNameTypeDesc + 4 * v10),
      pReserveda);
    v2 = v35;
    goto LABEL_69;
  }
  v2 = v35;
LABEL_29:
  memset_0(&pReplaceSet, 0, sizeof(pReplaceSet));
  v17 = 32 * v11;
  pReplaceSet.pName = MultiByteStr;
  pReplaceSet.dwTtl = *((_DWORD *)v3 + 16);
  if ( *(_WORD *)((char *)&NlDcDnsNameTypeDesc + v17 + 24) == 5 )
  {
    *(_DWORD *)&pReplaceSet.wType = 524293;
    v2 |= 0x4000u;
    pReplaceSet.Data.AAAA.Ip6Address.IP6Qword[0] = *((_QWORD *)v3 + 2);
    v35 = v2;
  }
  else
  {
    *(_DWORD *)&pReplaceSet.wType = 1048609;
    pReplaceSet.Data.AAAA.Ip6Address.IP6Qword[0] = *((_QWORD *)v3 + 2);
    pReplaceSet.Data.MX.wPreference = *(_WORD *)(*((_QWORD *)v3 + 10) + 8 * v8 + 20);
    pReplaceSet.Data.MX.Pad = *(_WORD *)(*((_QWORD *)v3 + 10) + 8 * v8 + 24);
    pReplaceSet.Data.AAAA.Ip6Address.IP6Word[6] = *(_WORD *)(*((_QWORD *)v3 + 10) + 8 * v8 + 28);
  }
  memset_0(v39, 0, 0x5Cu);
  pExtraInfo = -2147483647;
  v40 = ((unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl'::`2'::impl) != 0)
      + 1;
  if ( *(_BYTE *)(*((_QWORD *)v3 + 10) + 8 * v8 + 32) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl'::`2'::impl) )
    {
      if ( *(_WORD *)((char *)&NlDcDnsNameTypeDesc + v17 + 24) == 5 )
        v18 = DnsReplaceRecordSetUTF8(&pReplaceSet, v2, 0, &pExtraInfo, 0);
      else
        v18 = DnsModifyRecordsInSet_UTF8(&pReplaceSet, 0, v2, 0, &pExtraInfo, 0);
    }
    else if ( *(_WORD *)((char *)&NlDcDnsNameTypeDesc + v17 + 24) == 5 )
    {
      v18 = DnsReplaceRecordSetUTF8(&pReplaceSet, v2, 0, 0, &pExtraInfo);
    }
    else
    {
      v18 = DnsModifyRecordsInSet_UTF8(&pReplaceSet, 0, v2, 0, 0, &pExtraInfo);
    }
    v19 = *((_DWORD *)v3 + 16);
    v20 = v18;
    v21 = (char *)*((_QWORD *)v3 + 2);
    v22 = (struct _NL_DNS_NAME_INFO *)(*((_QWORD *)v3 + 10) + 8 * v8);
    if ( !v18 )
    {
      NlPrintDnsNameInfoRoutine(
        0x4000u,
        v22,
        v9,
        MultiByteStr,
        v21,
        v19,
        L"NlDnsUpdateRequestWorker: Registered (success)");
      goto LABEL_68;
    }
    v23 = L"NlDnsUpdateRequestWorker: Failed to register (%ld)";
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl'::`2'::impl) )
      v24 = DnsModifyRecordsInSet_UTF8(0, &pReplaceSet, v2, 0, &pExtraInfo, 0);
    else
      v24 = DnsModifyRecordsInSet_UTF8(0, &pReplaceSet, v2, 0, 0, &pExtraInfo);
    v19 = *((_DWORD *)v3 + 16);
    v20 = v24;
    v21 = (char *)*((_QWORD *)v3 + 2);
    v22 = (struct _NL_DNS_NAME_INFO *)(*((_QWORD *)v3 + 10) + 8 * v8);
    if ( !v24 )
    {
      NlPrintDnsNameInfoRoutine(
        0x4000u,
        v22,
        v9,
        MultiByteStr,
        v21,
        v19,
        L"NlDnsUpdateRequestWorker: Deregistered (success)");
      goto LABEL_68;
    }
    v23 = L"NlDnsUpdateRequestWorker: Failed to deregister (%ld)";
  }
  LODWORD(v34) = v20;
  NlPrintDnsNameInfoRoutine(0x20000u, v22, v9, MultiByteStr, v21, v19, v23, v34);
  *(_DWORD *)(*((_QWORD *)v3 + 10) + 8 * v8 + 36) = v20;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl'::`2'::impl) )
  {
    if ( *(_DWORD *)v44 )
    {
      NetpIpAddressToWStr(*(unsigned int *)v44, pNodeBuffer);
      goto LABEL_60;
    }
    pSockaddr[0] = 23;
    v25 = (const SOCKADDR *)pSockaddr;
    v48 = 0;
    *(_OWORD *)&pSockaddr[1] = v45;
LABEL_58:
    if ( GetNameInfoW(v25, 28, pNodeBuffer, 0x42u, 0, 0, 2) )
      _o_wcscpy_s(pNodeBuffer, 66);
    goto LABEL_60;
  }
  if ( v43 != 2 )
  {
    v25 = (const SOCKADDR *)&v43;
    goto LABEL_58;
  }
  NetpIpAddressToWStr(*(unsigned int *)&v44[2], pNodeBuffer);
LABEL_60:
  swprintf_s(Buffer, 0xEu, L"%lu", *(unsigned __int16 *)v42);
  swprintf_s(v53, 0xEu, L"%lu", v41);
  v36 = 0;
  v26 = NetpAllocWStrFromUtf8StrAsRequired(MultiByteStr, 0xFFFFFFFF, 0, 0, &v36);
  v27 = 0;
  if ( !v26 )
    v27 = v36;
  v49[0] = v27;
  v28 = (const CHAR *)*((_QWORD *)v3 + 2);
  v36 = 0;
  v29 = NetpAllocWStrFromUtf8StrAsRequired(v28, 0xFFFFFFFF, 0, 0, &v36);
  v30 = 0;
  if ( !v29 )
    v30 = v36;
  v50[0] = v30;
  if ( v49[0] && v30 )
  {
    v49[1] = (unsigned __int16 *)v20;
    v50[1] = pNodeBuffer;
    *(_QWORD *)&v51 = Buffer;
    *((_QWORD *)&v51 + 1) = v53;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl'::`2'::impl);
    NlpWriteEventlogEx(
      5812 - (*(_BYTE *)(*((_QWORD *)v3 + 10) + 8 * v8 + 32) != 0),
      1u,
      0x40000000u,
      1u,
      v49,
      6u,
      v42,
      2u);
  }
  NetApiBufferFree(v49[0]);
  NetApiBufferFree(v50[0]);
LABEL_68:
  if ( !NlGlobalTerminate )
    goto LABEL_69;
  RtlEnterCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
  NlGlobalDnsUpdateRequestInProgress = 0;
  RtlLeaveCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
LABEL_74:
  if ( Utf8StrFromWStr )
    NetApiBufferFree(Utf8StrFromWStr);
  if ( v3 )
    LocalFree(v3);
}

```

## disassembly

```asm
0x180023020  push    rbp
0x180023022  push    rbx
0x180023023  push    rsi
0x180023024  push    rdi
0x180023025  push    r12
0x180023027  push    r13
0x180023029  push    r14
0x18002302b  push    r15
0x18002302d  lea     rbp, [rsp-258h]
0x180023035  sub     rsp, 358h
0x18002303c  mov     rax, cs:__security_cookie
0x180023043  xor     rax, rsp
0x180023046  mov     [rbp+290h+var_50], rax
0x18002304d  xor     edx, edx; Val
0x18002304f  lea     rcx, [rbp+290h+MultiByteStr]; void *
0x180023056  mov     r8d, 100h; Size
0x18002305c  call    memset_0
0x180023061  xor     r13d, r13d
0x180023064  lea     rcx, [rbp+290h+pReplaceSet]; void *
0x180023068  xor     edx, edx; Val
0x18002306a  mov     esi, r13d
0x18002306d  lea     r8d, [r13+58h]; Size
0x180023071  call    memset_0
0x180023076  xor     edx, edx; Val
0x180023078  mov     [rsp+390h+var_350], r13d
0x18002307d  lea     r8d, [r13+60h]; Size
0x180023081  mov     r12d, r13d
0x180023084  lea     rcx, [rsp+390h+pExtraInfo]; void *
0x180023089  call    memset_0
0x18002308e  movups  xmm0, xmmword ptr cs:aUnavailable+0Ch; "ILABLE>"
0x180023095  lea     rdi, ?NlGlobalDnsUpdateRequestCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlGlobalDnsUpdateRequestCritSect
0x18002309c  movups  xmm1, xmmword ptr cs:aUnavailable; "<UNAVAILABLE>"
0x1800230a3  movups  xmmword ptr [rbp+290h+Buffer], xmm1
0x1800230a7  movups  xmmword ptr [rbp+290h+var_200], xmm1
0x1800230ae  movups  xmmword ptr [rbp+290h+Buffer+0Ch], xmm0
0x1800230b2  movups  xmmword ptr [rbp+290h+var_200+0Ch], xmm0
0x1800230b9  xorps   xmm0, xmm0
0x1800230bc  movups  xmmword ptr [rbp+290h+var_250], xmm0
0x1800230c0  movups  xmmword ptr [rbp+290h+var_240], xmm0
0x1800230c4  movups  [rbp+290h+var_230], xmm0
0x1800230c8  mov     rcx, rdi; CriticalSection
0x1800230cb  call    cs:__imp_RtlEnterCriticalSection
0x1800230d1  mov     rbx, cs:?NlGlobalDnsUpdateRequestList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalDnsUpdateRequestList
0x1800230d8  lea     rax, ?NlGlobalDnsUpdateRequestList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalDnsUpdateRequestList
0x1800230df  cmp     rbx, rax
0x1800230e2  jz      loc_180023731
0x1800230e8  mov     rcx, [rbx]
0x1800230eb  cmp     [rcx+8], rbx
0x1800230ef  jnz     loc_1800237A6
0x1800230f5  mov     rax, [rbx+8]
0x1800230f9  cmp     [rax], rbx
0x1800230fc  jnz     loc_1800237A6
0x180023102  mov     [rax], rcx
0x180023105  mov     [rcx+8], rax
0x180023109  mov     rcx, rdi; CriticalSection
0x18002310c  call    cs:__imp_RtlLeaveCriticalSection
0x180023112  mov     eax, [rbx+48h]
0x180023115  lea     rdx, aProcessingADns; "Processing a Dns update request for %hs"...
0x18002311c  mov     r9, [rbx+38h]
0x180023120  mov     ecx, 20000h; unsigned int
0x180023125  mov     r8, [rbx+10h]
0x180023129  mov     dword ptr [rsp+390h+var_368], eax
0x18002312d  mov     eax, [rbx+40h]
0x180023130  mov     dword ptr [rsp+390h+pReserved], eax
0x180023134  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180023139  cmp     cs:dword_1800F1264, r13d
0x180023140  jnz     short loc_18002314C
0x180023142  bts     r12d, 0Dh
0x180023147  mov     [rsp+390h+var_350], r12d
0x18002314c  mov     eax, r13d
0x18002314f  mov     [rsp+390h+var_340], eax
0x180023153  cmp     [rbx+48h], r13d
0x180023157  jbe     loc_180023712
0x18002315d  mov     rcx, [rbx+50h]
0x180023161  lea     r14, [rax+rax*4]
0x180023165  mov     r15, r13
0x180023168  cmp     byte ptr [rcx+r14*8+20h], 1
0x18002316e  movsxd  r13, dword ptr [rcx+r14*8]
0x180023172  jnz     loc_180023268
0x180023178  mov     r12, r13
0x18002317b  mov     [rsp+390h+var_348], 0
0x180023184  shl     r12, 5
0x180023188  lea     rdx, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A; _NL_DNS_NAME_TYPE_DESC near * NlDcDnsNameTypeDesc
0x18002318f  mov     eax, 5
0x180023194  mov     rdi, r13
0x180023197  cmp     [r12+rdx+18h], ax
0x18002319d  jnz     short loc_1800231A8
0x18002319f  lea     rax, [rbx+28h]
0x1800231a3  mov     [rsp+390h+var_348], rax
0x1800231a8  mov     edx, [rcx+r14*8+10h]
0x1800231ad  test    edx, edx
0x1800231af  jz      short loc_180023206
0x1800231b1  sub     edx, 1
0x1800231b4  jz      short loc_180023200
0x1800231b6  sub     edx, 1
0x1800231b9  jz      short loc_1800231F7
0x1800231bb  sub     edx, 1
0x1800231be  jz      short loc_1800231EE
0x1800231c0  cmp     edx, 1
0x1800231c3  jnz     short loc_18002320A
0x1800231c5  test    rsi, rsi
0x1800231c8  jz      short loc_1800231D3
0x1800231ca  mov     rcx, rsi; Buffer
0x1800231cd  call    cs:__imp_NetApiBufferFree
0x1800231d3  mov     rcx, [rbx+50h]
0x1800231d7  xor     r8d, r8d; int
0x1800231da  xor     edx, edx; lpMultiByteStr
0x1800231dc  mov     rcx, [rcx+r14*8+8]; lpWideCharStr
0x1800231e1  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x1800231e6  mov     rsi, rax
0x1800231e9  mov     r15, rax
0x1800231ec  jmp     short loc_18002320A
0x1800231ee  mov     r15, cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA; char * NlGlobalUtf8DnsForestNameAlias
0x1800231f5  jmp     short loc_18002320A
0x1800231f7  mov     r15, cs:?NlGlobalUtf8DnsForestName@@3PEADEA; char * NlGlobalUtf8DnsForestName
0x1800231fe  jmp     short loc_18002320A
0x180023200  mov     r15, [rbx+20h]
0x180023204  jmp     short loc_18002320A
0x180023206  mov     r15, [rbx+18h]
0x18002320a  mov     r8, [rbx+38h]
0x18002320e  lea     rax, [rbp+290h+MultiByteStr]
0x180023215  mov     rdx, [rsp+390h+var_348]
0x18002321a  mov     r9, r15
0x18002321d  mov     ecx, r13d
0x180023220  mov     [rsp+390h+pReserved], rax
0x180023225  call    ?NetpDcBuildDnsName@@YAKW4_NL_DNS_NAME_TYPE@@PEAU_GUID@@PEBGPEBDQEAD@Z; NetpDcBuildDnsName(_NL_DNS_NAME_TYPE,_GUID *,ushort const *,char const *,char * const)
0x18002322a  xor     r13d, r13d
0x18002322d  test    eax, eax
0x18002322f  jz      short loc_1800232A1
0x180023231  mov     rcx, [rbx+50h]
0x180023235  lea     rdx, aNldnsupdatereq_0; "NlDnsUpdateRequestWorker: %hs: %ws: Net"...
0x18002323c  mov     dword ptr [rsp+390h+pReserved], eax
0x180023240  mov     [rcx+r14*8+24h], eax
0x180023245  lea     rax, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A; _NL_DNS_NAME_TYPE_DESC near * NlDcDnsNameTypeDesc
0x18002324c  mov     r9, [r12+rax]
0x180023250  mov     ecx, 100h; unsigned int
0x180023255  mov     r8, [rbx+10h]
0x180023259  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002325e  mov     r12d, [rsp+390h+var_350]
0x180023263  jmp     loc_1800236F3
0x180023268  mov     rcx, [rcx+r14*8+8]; lpWideCharStr
0x18002326d  lea     rdx, [rbp+290h+MultiByteStr]; lpMultiByteStr
0x180023274  mov     r8d, 0FFh; int
0x18002327a  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x18002327f  test    rax, rax
0x180023282  jnz     short loc_180023299
0x180023284  mov     rax, [rbx+50h]
0x180023288  xor     r13d, r13d
0x18002328b  mov     dword ptr [rax+r14*8+24h], 8
0x180023294  jmp     loc_1800236F3
0x180023299  mov     rdi, r13
0x18002329c  xor     r13d, r13d
0x18002329f  jmp     short loc_1800232A6
0x1800232a1  mov     r12d, [rsp+390h+var_350]
0x1800232a6  xor     edx, edx; Val
0x1800232a8  lea     rcx, [rbp+290h+pReplaceSet]; void *
0x1800232ac  lea     r8d, [rdx+58h]; Size
0x1800232b0  call    memset_0
0x1800232b5  lea     rax, [rbp+290h+MultiByteStr]
0x1800232bc  shl     rdi, 5
0x1800232c0  mov     [rbp+290h+pReplaceSet.pName], rax
0x1800232c4  lea     rcx, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A; _NL_DNS_NAME_TYPE_DESC near * NlDcDnsNameTypeDesc
0x1800232cb  mov     eax, [rbx+40h]
0x1800232ce  mov     [rbp+290h+pReplaceSet.dwTtl], eax
0x1800232d1  mov     eax, 5
0x1800232d6  cmp     [rdi+rcx+18h], ax
0x1800232db  jnz     short loc_1800232F8
0x1800232dd  mov     dword ptr [rbp+290h+pReplaceSet.wType], 80005h
0x1800232e4  bts     r12d, 0Eh
0x1800232e9  mov     rax, [rbx+10h]
0x1800232ed  mov     qword ptr [rbp+290h+pReplaceSet.Data], rax
0x1800232f1  mov     [rsp+390h+var_350], r12d
0x1800232f6  jmp     short loc_180023331
0x1800232f8  mov     dword ptr [rbp+290h+pReplaceSet.wType], 100021h
0x1800232ff  mov     rax, [rbx+10h]
0x180023303  mov     qword ptr [rbp+290h+pReplaceSet.Data], rax
0x180023307  mov     rax, [rbx+50h]
0x18002330b  movzx   ecx, word ptr [rax+r14*8+14h]
0x180023311  mov     word ptr [rbp+290h+pReplaceSet.Data+8], cx
0x180023315  mov     rax, [rbx+50h]
0x180023319  movzx   ecx, word ptr [rax+r14*8+18h]
0x18002331f  mov     word ptr [rbp+290h+pReplaceSet.Data+0Ah], cx
0x180023323  mov     rax, [rbx+50h]
0x180023327  movzx   ecx, word ptr [rax+r14*8+1Ch]
0x18002332d  mov     word ptr [rbp+290h+pReplaceSet.Data+0Ch], cx
0x180023331  xor     edx, edx; Val
0x180023333  lea     rcx, [rsp+390h+var_32C]; void *
0x180023338  lea     r8d, [rdx+5Ch]; Size
0x18002333c  call    memset_0
0x180023341  mov     [rsp+390h+pExtraInfo], 80000001h
0x180023349  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_6086_9425@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_6086_9425@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425> `wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl(void)'::`2'::impl
0x180023350  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_6086_9425@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(void)
0x180023355  neg     al
0x180023357  sbb     ecx, ecx
0x180023359  neg     ecx
0x18002335b  inc     ecx
0x18002335d  mov     [rsp+390h+var_320], ecx
0x180023361  mov     rax, [rbx+50h]
0x180023365  cmp     [rax+r14*8+20h], r13b
0x18002336a  jz      loc_180023440
0x180023370  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_6086_9425@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_6086_9425@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425> `wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl(void)'::`2'::impl
0x180023377  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_6086_9425@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(void)
0x18002337c  test    al, al
0x18002337e  lea     rcx, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A; _NL_DNS_NAME_TYPE_DESC near * NlDcDnsNameTypeDesc
0x180023385  mov     eax, 5
0x18002338a  jz      short loc_1800233C0
0x18002338c  cmp     [rdi+rcx+18h], ax
0x180023391  lea     rcx, [rbp+290h+pReplaceSet]; pReplaceSet
0x180023395  jnz     short loc_1800233AF
0x180023397  mov     [rsp+390h+pReserved], r13; pReserved
0x18002339c  lea     r9, [rsp+390h+pExtraInfo]; pExtraInfo
0x1800233a1  xor     r8d, r8d; hContext
0x1800233a4  mov     edx, r12d; Options
0x1800233a7  call    cs:__imp_DnsReplaceRecordSetUTF8
0x1800233ad  jmp     short loc_1800233F2
0x1800233af  lea     rax, [rsp+390h+pExtraInfo]
0x1800233b4  mov     [rsp+390h+var_368], r13
0x1800233b9  mov     [rsp+390h+pReserved], rax
0x1800233be  jmp     short loc_1800233E4
0x1800233c0  cmp     [rdi+rcx+18h], ax
0x1800233c5  lea     rax, [rsp+390h+pExtraInfo]
0x1800233ca  lea     rcx, [rbp+290h+pReplaceSet]; pAddRecords
0x1800233ce  jnz     short loc_1800233DA
0x1800233d0  mov     [rsp+390h+pReserved], rax
0x1800233d5  xor     r9d, r9d
0x1800233d8  jmp     short loc_1800233A1
0x1800233da  mov     [rsp+390h+var_368], rax; pReserved
0x1800233df  mov     [rsp+390h+pReserved], r13; pExtraList
0x1800233e4  xor     r9d, r9d; hCredentials
0x1800233e7  mov     r8d, r12d; Options
0x1800233ea  xor     edx, edx; pDeleteRecords
0x1800233ec  call    cs:__imp_DnsModifyRecordsInSet_UTF8
0x1800233f2  mov     r9d, [rbx+40h]
0x1800233f6  mov     edi, eax
0x1800233f8  mov     rax, [rbx+50h]
0x1800233fc  mov     rcx, [rbx+10h]
0x180023400  lea     rdx, [rax+r14*8]; struct _NL_DNS_NAME_INFO *
0x180023404  test    edi, edi
0x180023406  jnz     short loc_180023437
0x180023408  lea     rax, aNldnsupdatereq_2; "NlDnsUpdateRequestWorker: Registered (s"...
0x18002340f  mov     qword ptr [rsp+390h+Flags], rax; unsigned __int16 *
0x180023414  mov     r8, r15; char *
0x180023417  mov     dword ptr [rsp+390h+var_368], r9d; unsigned int
0x18002341c  lea     r9, [rbp+290h+MultiByteStr]; char *
0x180023423  mov     [rsp+390h+pReserved], rcx; char *
0x180023428  mov     ecx, 4000h; unsigned int
0x18002342d  call    ?NlPrintDnsNameInfoRoutine@@YAXKPEAU_NL_DNS_NAME_INFO@@PEAD11KPEAGZZ; NlPrintDnsNameInfoRoutine(ulong,_NL_DNS_NAME_INFO *,char *,char *,char *,ulong,ushort *,...)
0x180023432  jmp     loc_1800236E6
0x180023437  lea     r10, aNldnsupdatereq; "NlDnsUpdateRequestWorker: Failed to reg"...
0x18002343e  jmp     short loc_1800234A6
0x180023440  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_6086_9425@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_6086_9425@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425> `wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl(void)'::`2'::impl
0x180023447  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_6086_9425@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(void)
0x18002344c  xor     r9d, r9d; hCredentials
0x18002344f  lea     rdx, [rbp+290h+pReplaceSet]; pDeleteRecords
0x180023453  xor     ecx, ecx; pAddRecords
0x180023455  mov     r8d, r12d; Options
0x180023458  test    al, al
0x18002345a  lea     rax, [rsp+390h+pExtraInfo]
0x18002345f  jz      short loc_18002346D
0x180023461  mov     [rsp+390h+var_368], r13
0x180023466  mov     [rsp+390h+pReserved], rax
0x18002346b  jmp     short loc_180023477
0x18002346d  mov     [rsp+390h+var_368], rax; pReserved
0x180023472  mov     [rsp+390h+pReserved], r13; pExtraList
0x180023477  call    cs:__imp_DnsModifyRecordsInSet_UTF8
0x18002347d  mov     r9d, [rbx+40h]
0x180023481  mov     edi, eax
0x180023483  mov     rax, [rbx+50h]
0x180023487  mov     rcx, [rbx+10h]
0x18002348b  lea     rdx, [rax+r14*8]; struct _NL_DNS_NAME_INFO *
0x18002348f  test    edi, edi
0x180023491  jnz     short loc_18002349F
0x180023493  lea     rax, aNldnsupdatereq_1; "NlDnsUpdateRequestWorker: Deregistered "...
0x18002349a  jmp     loc_18002340F
0x18002349f  lea     r10, aNldnsupdatereq_3; "NlDnsUpdateRequestWorker: Failed to der"...
0x1800234a6  mov     dword ptr [rsp+390h+var_358], edi
0x1800234aa  lea     r8, [rbp+290h+MultiByteStr]
0x1800234b1  mov     qword ptr [rsp+390h+Flags], r10; unsigned __int16 *
0x1800234b6  mov     eax, 20000h
0x1800234bb  mov     dword ptr [rsp+390h+var_368], r9d; unsigned int
0x1800234c0  mov     r11d, edi
0x1800234c3  mov     [rsp+390h+pReserved], rcx; char *
0x1800234c8  mov     r9, r8; char *
0x1800234cb  mov     r8, r15; char *
0x1800234ce  mov     ecx, eax; unsigned int
0x1800234d0  call    ?NlPrintDnsNameInfoRoutine@@YAXKPEAU_NL_DNS_NAME_INFO@@PEAD11KPEAGZZ; NlPrintDnsNameInfoRoutine(ulong,_NL_DNS_NAME_INFO *,char *,char *,char *,ulong,ushort *,...)
0x1800234d5  mov     rax, [rbx+50h]
0x1800234d9  mov     [rax+r14*8+24h], edi
0x1800234de  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_6086_9425@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_6086_9425@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425> `wil::Feature<__WilFeatureTraits_Feature_6086_9425>::GetImpl(void)'::`2'::impl
0x1800234e5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_6086_9425@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_6086_9425>::__private_IsEnabled(void)
0x1800234ea  test    al, al
0x1800234ec  jz      short loc_180023517
0x1800234ee  mov     r15d, 2
0x1800234f4  cmp     [rsp+390h+var_312], r15w
0x1800234fa  jnz     short loc_180023510
0x1800234fc  mov     ecx, [rbp+290h+var_30E]; unsigned int
0x1800234ff  lea     rdx, [rbp+290h+pNodeBuffer]; unsigned __int16 *
0x180023506  call    ?NetpIpAddressToWStr@@YAXKQEAG@Z; NetpIpAddressToWStr(ulong,ushort * const)
0x18002350b  jmp     loc_18002359C
0x180023510  lea     rcx, [rsp+390h+var_312]
  ... truncated ...
```
