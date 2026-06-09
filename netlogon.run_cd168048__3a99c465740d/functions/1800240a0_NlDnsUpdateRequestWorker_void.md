# NlDnsUpdateRequestWorker(void *)

- ea: `0x1800240a0`
- end: `0x1800247bc`
- name: `?NlDnsUpdateRequestWorker@@YAXPEAX@Z`
- size: `1820`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180007518`
- `0x18000c130`
- `0x18000e910`
- `0x18000f3e4`
- `0x18000f4a4`
- `0x1800240a0`
- `0x180024fc8`
- `0x180041fbc`
- `0x18007a320`
- `0x180088fe8`
- `0x180089228`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180024588`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180024588`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800246f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024756`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800246f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024756`
- `ntdll!RtlLeaveCriticalSection` at `0x18002419a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002472b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800247a7`
- `ntdll!RtlLeaveCriticalSection` at `0x18002419a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002472b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800247a7`
- `ntdll!RtlEnterCriticalSection` at `0x18002414f`
- `ntdll!RtlEnterCriticalSection` at `0x180024711`
- `ntdll!RtlEnterCriticalSection` at `0x18002478d`
- `ntdll!RtlEnterCriticalSection` at `0x18002414f`
- `ntdll!RtlEnterCriticalSection` at `0x180024711`
- `ntdll!RtlEnterCriticalSection` at `0x18002478d`
- `netutils!NetApiBufferFree` at `0x18002425e`
- `netutils!NetApiBufferFree` at `0x1800246b5`
- `netutils!NetApiBufferFree` at `0x1800246c5`
- `netutils!NetApiBufferFree` at `0x180024742`
- `netutils!NetApiBufferFree` at `0x18002425e`
- `netutils!NetApiBufferFree` at `0x1800246b5`
- `netutils!NetApiBufferFree` at `0x1800246c5`
- `netutils!NetApiBufferFree` at `0x180024742`
- `DNSAPI!DnsReplaceRecordSetUTF8` at `0x180024417`
- `DNSAPI!DnsReplaceRecordSetUTF8` at `0x180024417`
- `DNSAPI!DnsModifyRecordsInSet_UTF8` at `0x180024434`
- `DNSAPI!DnsModifyRecordsInSet_UTF8` at `0x1800244a6`
- `DNSAPI!DnsModifyRecordsInSet_UTF8` at `0x180024434`
- `DNSAPI!DnsModifyRecordsInSet_UTF8` at `0x1800244a6`
- `WS2_32!GetNameInfoW` at `0x180024567`
- `WS2_32!GetNameInfoW` at `0x180024567`

## string_xrefs

- `0x1800241a9`: `Processing a Dns update request for %hs. SiteName: %ws, DnsTtl: %ld, DnsNamesCount: %ld\n`
- `0x1800242cc`: `NlDnsUpdateRequestWorker: %hs: %ws: NetpDcBuildDnsName failed. %ld\n`
- `0x18002445d`: `NlDnsUpdateRequestWorker: Registered (success)`
- `0x180024485`: `NlDnsUpdateRequestWorker: Failed to register (%ld)`
- `0x1800244cf`: `NlDnsUpdateRequestWorker: Deregistered (success)`
- `0x1800244d8`: `NlDnsUpdateRequestWorker: Failed to deregister (%ld)`

## pseudocode

```c
void __fastcall NlDnsUpdateRequestWorker(void *a1)
{
  char *Utf8StrFromWStr; // r13
  DWORD v2; // r15d
  char *v3; // rbx
  _QWORD *v4; // rcx
  HLOCAL *v5; // rax
  __int64 i; // rax
  __int64 v7; // rcx
  __int64 v8; // rdi
  char *v9; // r14
  __int64 v10; // r12
  __int64 v11; // rsi
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // eax
  __int64 v17; // rsi
  DNS_STATUS v18; // eax
  unsigned int v19; // r8d
  char *v20; // rcx
  unsigned int v21; // esi
  struct _NL_DNS_NAME_INFO *v22; // rdx
  unsigned __int16 *v23; // r10
  DNS_STATUS v24; // eax
  bool v25; // zf
  unsigned __int16 *v26; // rcx
  const CHAR *v27; // rcx
  unsigned int v28; // eax
  unsigned __int16 *v29; // rcx
  unsigned __int16 *v30; // rdx
  PVOID pReserved; // [rsp+20h] [rbp-E0h]
  PVOID pReserveda; // [rsp+20h] [rbp-E0h]
  PVOID v33; // [rsp+28h] [rbp-D8h]
  __int64 v34; // [rsp+38h] [rbp-C8h]
  DWORD v35; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v36; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+50h] [rbp-B0h]
  _DWORD v38[7]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 v39[2]; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v40; // [rsp+80h] [rbp-80h]
  __int128 v41; // [rsp+88h] [rbp-78h]
  DNS_RECORDA pReplaceSet; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE pSockaddr[24]; // [rsp+120h] [rbp+20h] BYREF
  int v44; // [rsp+138h] [rbp+38h]
  unsigned __int16 *v45[2]; // [rsp+140h] [rbp+40h] BYREF
  LPVOID v46[2]; // [rsp+150h] [rbp+50h]
  __int128 v47; // [rsp+160h] [rbp+60h]
  wchar_t Buffer[16]; // [rsp+170h] [rbp+70h] BYREF
  wchar_t v49[16]; // [rsp+190h] [rbp+90h] BYREF
  CHAR MultiByteStr[256]; // [rsp+1B0h] [rbp+B0h] BYREF
  WCHAR pNodeBuffer[72]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset_0(MultiByteStr, 0, sizeof(MultiByteStr));
  Utf8StrFromWStr = 0;
  memset_0(&pReplaceSet, 0, sizeof(pReplaceSet));
  v35 = 0;
  v2 = 0;
  memset_0(v38, 0, 0x60u);
  wcscpy(Buffer, L"<UNAILABLE>");
  wcscpy(v49, L"<UNAILABLE>");
  *(_OWORD *)v45 = 0;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  while ( 2 )
  {
    RtlEnterCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
    v3 = (char *)NlGlobalDnsUpdateRequestList;
    if ( NlGlobalDnsUpdateRequestList == &NlGlobalDnsUpdateRequestList )
      goto LABEL_59;
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
    if ( !dword_1800F8264 )
    {
      v2 |= 0x2000u;
      v35 = v2;
    }
    for ( i = 0; ; i = (unsigned int)(v37 + 1) )
    {
      v37 = i;
      if ( (unsigned int)i >= *((_DWORD *)v3 + 18) )
        break;
      v7 = *((_QWORD *)v3 + 10);
      v8 = 5 * i;
      v9 = 0;
      v10 = *(int *)(v7 + 40 * i);
      if ( *(_BYTE *)(v7 + 40 * i + 32) == 1 )
      {
        v36 = 0;
        v11 = v10;
        if ( *((_WORD *)&NlDcDnsNameTypeDesc + 16 * v10 + 12) == 5 )
          v36 = (unsigned __int16 *)(v3 + 40);
        v12 = *(_DWORD *)(v7 + 40 * i + 16);
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
          continue;
        }
        v2 = v35;
      }
      else
      {
        if ( !NetpCreateUtf8StrFromWStr(*(LPCWCH *)(v7 + 40 * i + 8), MultiByteStr, 255) )
        {
          *(_DWORD *)(*((_QWORD *)v3 + 10) + 8 * v8 + 36) = 8;
          continue;
        }
        v11 = v10;
      }
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
      memset_0(v38, 0, 0x60u);
      v38[0] = -2147483647;
      v38[4] = 1;
      if ( *(_BYTE *)(*((_QWORD *)v3 + 10) + 8 * v8 + 32) )
      {
        if ( *(_WORD *)((char *)&NlDcDnsNameTypeDesc + v17 + 24) == 5 )
          v18 = DnsReplaceRecordSetUTF8(&pReplaceSet, v2, 0, 0, v38);
        else
          v18 = DnsModifyRecordsInSet_UTF8(&pReplaceSet, 0, v2, 0, 0, v38);
        v19 = *((_DWORD *)v3 + 16);
        v20 = (char *)*((_QWORD *)v3 + 2);
        v21 = v18;
        v22 = (struct _NL_DNS_NAME_INFO *)(*((_QWORD *)v3 + 10) + 8 * v8);
        if ( !v18 )
        {
          NlPrintDnsNameInfoRoutine(
            0x4000u,
            v22,
            v9,
            MultiByteStr,
            v20,
            v19,
            L"NlDnsUpdateRequestWorker: Registered (success)");
          goto LABEL_55;
        }
        v23 = L"NlDnsUpdateRequestWorker: Failed to register (%ld)";
      }
      else
      {
        v24 = DnsModifyRecordsInSet_UTF8(0, &pReplaceSet, v2, 0, 0, v38);
        v19 = *((_DWORD *)v3 + 16);
        v20 = (char *)*((_QWORD *)v3 + 2);
        v21 = v24;
        v22 = (struct _NL_DNS_NAME_INFO *)(*((_QWORD *)v3 + 10) + 8 * v8);
        if ( !v24 )
        {
          NlPrintDnsNameInfoRoutine(
            0x4000u,
            v22,
            v9,
            MultiByteStr,
            v20,
            v19,
            L"NlDnsUpdateRequestWorker: Deregistered (success)");
          goto LABEL_55;
        }
        v23 = L"NlDnsUpdateRequestWorker: Failed to deregister (%ld)";
      }
      LODWORD(v34) = v21;
      NlPrintDnsNameInfoRoutine(0x20000u, v22, v9, MultiByteStr, v20, v19, v23, v34);
      *(_DWORD *)(*((_QWORD *)v3 + 10) + 8 * v8 + 36) = v21;
      if ( v40 )
      {
        NetpIpAddressToWStr(v40, pNodeBuffer);
      }
      else
      {
        *(_DWORD *)&pSockaddr[2] = 0;
        *(_WORD *)&pSockaddr[6] = 0;
        v44 = 0;
        *(_WORD *)pSockaddr = 23;
        *(_OWORD *)&pSockaddr[8] = v41;
        if ( GetNameInfoW((const SOCKADDR *)pSockaddr, 28, pNodeBuffer, 0x42u, 0, 0, 2) )
          _o_wcscpy_s(pNodeBuffer, 66, L"<UNAVAILABLE>");
      }
      swprintf_s(Buffer, 0xEu, L"%lu", *(unsigned __int16 *)v39);
      swprintf_s(v49, 0xEu, L"%lu", v38[6]);
      v36 = 0;
      v25 = NetpAllocWStrFromUtf8StrAsRequired(MultiByteStr, 0xFFFFFFFF, 0, 0, &v36) == 0;
      v26 = 0;
      if ( v25 )
        v26 = v36;
      v45[0] = v26;
      v27 = (const CHAR *)*((_QWORD *)v3 + 2);
      v36 = 0;
      v28 = NetpAllocWStrFromUtf8StrAsRequired(v27, 0xFFFFFFFF, 0, 0, &v36);
      v29 = v45[0];
      v30 = 0;
      if ( !v28 )
        v30 = v36;
      v46[0] = v30;
      if ( v45[0] && v30 )
      {
        v45[1] = (unsigned __int16 *)v21;
        v46[1] = pNodeBuffer;
        *(_QWORD *)&v47 = Buffer;
        *((_QWORD *)&v47 + 1) = v49;
        NlpWriteEventlogEx(
          5812 - (*(_BYTE *)(*((_QWORD *)v3 + 10) + 8 * v8 + 32) != 0),
          1u,
          0x40000000u,
          1u,
          v45,
          6u,
          v39,
          2u);
        v29 = v45[0];
      }
      NetApiBufferFree(v29);
      NetApiBufferFree(v46[0]);
LABEL_55:
      if ( NlGlobalTerminate )
      {
        RtlEnterCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
        NlGlobalDnsUpdateRequestInProgress = 0;
        RtlLeaveCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
        goto LABEL_60;
      }
    }
    LocalFree(v3);
    if ( !NlGlobalTerminate )
      continue;
    break;
  }
  RtlEnterCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
LABEL_59:
  NlGlobalDnsUpdateRequestInProgress = 0;
  RtlLeaveCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
  v3 = 0;
LABEL_60:
  if ( Utf8StrFromWStr )
    NetApiBufferFree(Utf8StrFromWStr);
  if ( v3 )
    LocalFree(v3);
}

```

## disassembly

```asm
0x1800240a0  push    rbp
0x1800240a2  push    rbx
0x1800240a3  push    rsi
0x1800240a4  push    rdi
0x1800240a5  push    r12
0x1800240a7  push    r13
0x1800240a9  push    r14
0x1800240ab  push    r15
0x1800240ad  lea     rbp, [rsp-258h]
0x1800240b5  sub     rsp, 358h
0x1800240bc  mov     rax, cs:__security_cookie
0x1800240c3  xor     rax, rsp
0x1800240c6  mov     [rbp+290h+var_50], rax
0x1800240cd  xor     edx, edx; Val
0x1800240cf  lea     rcx, [rbp+290h+MultiByteStr]; void *
0x1800240d6  mov     r8d, 100h; Size
0x1800240dc  call    memset_0
0x1800240e1  xor     r12d, r12d
0x1800240e4  lea     rcx, [rbp+290h+pReplaceSet]; void *
0x1800240e8  xor     edx, edx; Val
0x1800240ea  mov     r13d, r12d
0x1800240ed  lea     r8d, [r12+58h]; Size
0x1800240f2  call    memset_0
0x1800240f7  xor     edx, edx; Val
0x1800240f9  mov     [rsp+390h+var_350], r12d
0x1800240fe  lea     r8d, [r12+60h]; Size
0x180024103  mov     r15d, r12d
0x180024106  lea     rcx, [rsp+390h+var_330]; void *
0x18002410b  call    memset_0
0x180024110  movups  xmm0, xmmword ptr cs:aUnavailable+0Ch; "ILABLE>"
0x180024117  lea     esi, [r12+8]
0x18002411c  movups  xmm1, xmmword ptr cs:aUnavailable; "<UNAVAILABLE>"
0x180024123  movups  xmmword ptr [rbp+290h+Buffer], xmm1
0x180024127  movups  xmmword ptr [rbp+290h+var_200], xmm1
0x18002412e  movups  xmmword ptr [rbp+290h+Buffer+0Ch], xmm0
0x180024132  movups  xmmword ptr [rbp+290h+var_200+0Ch], xmm0
0x180024139  xorps   xmm0, xmm0
0x18002413c  movups  xmmword ptr [rbp+290h+var_250], xmm0
0x180024140  movups  xmmword ptr [rbp+290h+var_240], xmm0
0x180024144  movups  [rbp+290h+var_230], xmm0
0x180024148  lea     rcx, ?NlGlobalDnsUpdateRequestCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18002414f  call    cs:__imp_RtlEnterCriticalSection
0x180024156  nop     dword ptr [rax+rax+00h]
0x18002415b  mov     rbx, cs:?NlGlobalDnsUpdateRequestList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalDnsUpdateRequestList
0x180024162  lea     rax, ?NlGlobalDnsUpdateRequestList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalDnsUpdateRequestList
0x180024169  cmp     rbx, rax
0x18002416c  jz      loc_18002471D
0x180024172  mov     rcx, [rbx]
0x180024175  cmp     [rcx+8], rbx
0x180024179  jnz     loc_1800247B5
0x18002417f  mov     rax, [rbx+8]
0x180024183  cmp     [rax], rbx
0x180024186  jnz     loc_1800247B5
0x18002418c  mov     [rax], rcx
0x18002418f  mov     [rcx+8], rax
0x180024193  lea     rcx, ?NlGlobalDnsUpdateRequestCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18002419a  call    cs:__imp_RtlLeaveCriticalSection
0x1800241a1  nop     dword ptr [rax+rax+00h]
0x1800241a6  mov     eax, [rbx+48h]
0x1800241a9  lea     rdx, aProcessingADns; "Processing a Dns update request for %hs"...
0x1800241b0  mov     r9, [rbx+38h]
0x1800241b4  mov     ecx, 20000h; unsigned int
0x1800241b9  mov     r8, [rbx+10h]
0x1800241bd  mov     dword ptr [rsp+390h+var_368], eax
0x1800241c1  mov     eax, [rbx+40h]
0x1800241c4  mov     dword ptr [rsp+390h+pReserved], eax
0x1800241c8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800241cd  cmp     cs:dword_1800F8264, r12d
0x1800241d4  jnz     short loc_1800241E0
0x1800241d6  bts     r15d, 0Dh
0x1800241db  mov     [rsp+390h+var_350], r15d
0x1800241e0  mov     eax, r12d
0x1800241e3  mov     [rsp+390h+var_340], eax
0x1800241e7  cmp     eax, [rbx+48h]
0x1800241ea  jnb     loc_1800246EE
0x1800241f0  mov     rcx, [rbx+50h]
0x1800241f4  lea     rdi, [rax+rax*4]
0x1800241f8  mov     r14, r12
0x1800241fb  cmp     byte ptr [rcx+rdi*8+20h], 1
0x180024200  movsxd  r12, dword ptr [rcx+rdi*8]
0x180024204  jnz     loc_1800242FE
0x18002420a  mov     r15, r12
0x18002420d  mov     [rsp+390h+var_348], 0
0x180024216  shl     r15, 5
0x18002421a  lea     rdx, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A; _NL_DNS_NAME_TYPE_DESC near * NlDcDnsNameTypeDesc
0x180024221  mov     eax, 5
0x180024226  mov     rsi, r12
0x180024229  cmp     [r15+rdx+18h], ax
0x18002422f  jnz     short loc_18002423A
0x180024231  lea     rax, [rbx+28h]
0x180024235  mov     [rsp+390h+var_348], rax
0x18002423a  mov     edx, [rcx+rdi*8+10h]
0x18002423e  test    edx, edx
0x180024240  jz      short loc_18002429D
0x180024242  sub     edx, 1
0x180024245  jz      short loc_180024297
0x180024247  sub     edx, 1
0x18002424a  jz      short loc_18002428E
0x18002424c  sub     edx, 1
0x18002424f  jz      short loc_180024285
0x180024251  cmp     edx, 1
0x180024254  jnz     short loc_1800242A1
0x180024256  test    r13, r13
0x180024259  jz      short loc_18002426A
0x18002425b  mov     rcx, r13; Buffer
0x18002425e  call    cs:__imp_NetApiBufferFree
0x180024265  nop     dword ptr [rax+rax+00h]
0x18002426a  mov     rcx, [rbx+50h]
0x18002426e  xor     r8d, r8d; int
0x180024271  xor     edx, edx; lpMultiByteStr
0x180024273  mov     rcx, [rcx+rdi*8+8]; lpWideCharStr
0x180024278  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x18002427d  mov     r13, rax
0x180024280  mov     r14, rax
0x180024283  jmp     short loc_1800242A1
0x180024285  mov     r14, cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA; char * NlGlobalUtf8DnsForestNameAlias
0x18002428c  jmp     short loc_1800242A1
0x18002428e  mov     r14, cs:?NlGlobalUtf8DnsForestName@@3PEADEA; char * NlGlobalUtf8DnsForestName
0x180024295  jmp     short loc_1800242A1
0x180024297  mov     r14, [rbx+20h]
0x18002429b  jmp     short loc_1800242A1
0x18002429d  mov     r14, [rbx+18h]
0x1800242a1  mov     r8, [rbx+38h]
0x1800242a5  lea     rax, [rbp+290h+MultiByteStr]
0x1800242ac  mov     rdx, [rsp+390h+var_348]
0x1800242b1  mov     r9, r14
0x1800242b4  mov     ecx, r12d
0x1800242b7  mov     [rsp+390h+pReserved], rax
0x1800242bc  call    ?NetpDcBuildDnsName@@YAKW4_NL_DNS_NAME_TYPE@@PEAU_GUID@@PEBGPEBDQEAD@Z; NetpDcBuildDnsName(_NL_DNS_NAME_TYPE,_GUID *,ushort const *,char const *,char * const)
0x1800242c1  xor     r12d, r12d
0x1800242c4  test    eax, eax
0x1800242c6  jz      short loc_180024332
0x1800242c8  mov     rcx, [rbx+50h]
0x1800242cc  lea     rdx, aNldnsupdatereq_0; "NlDnsUpdateRequestWorker: %hs: %ws: Net"...
0x1800242d3  mov     dword ptr [rsp+390h+pReserved], eax
0x1800242d7  mov     [rcx+rdi*8+24h], eax
0x1800242db  lea     rax, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A; _NL_DNS_NAME_TYPE_DESC near * NlDcDnsNameTypeDesc
0x1800242e2  mov     r9, [r15+rax]
0x1800242e6  mov     ecx, 100h; unsigned int
0x1800242eb  mov     r8, [rbx+10h]
0x1800242ef  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800242f4  mov     r15d, [rsp+390h+var_350]
0x1800242f9  jmp     loc_1800246DE
0x1800242fe  mov     rcx, [rcx+rdi*8+8]; lpWideCharStr
0x180024303  lea     rdx, [rbp+290h+MultiByteStr]; lpMultiByteStr
0x18002430a  mov     r8d, 0FFh; int
0x180024310  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x180024315  test    rax, rax
0x180024318  jnz     short loc_18002432A
0x18002431a  mov     rax, [rbx+50h]
0x18002431e  xor     r12d, r12d
0x180024321  mov     [rax+rdi*8+24h], esi
0x180024325  jmp     loc_1800246E3
0x18002432a  mov     rsi, r12
0x18002432d  xor     r12d, r12d
0x180024330  jmp     short loc_180024337
0x180024332  mov     r15d, [rsp+390h+var_350]
0x180024337  xor     edx, edx; Val
0x180024339  lea     rcx, [rbp+290h+pReplaceSet]; void *
0x18002433d  lea     r8d, [rdx+58h]; Size
0x180024341  call    memset_0
0x180024346  lea     rax, [rbp+290h+MultiByteStr]
0x18002434d  shl     rsi, 5
0x180024351  mov     [rbp+290h+pReplaceSet.pName], rax
0x180024355  lea     rcx, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A; _NL_DNS_NAME_TYPE_DESC near * NlDcDnsNameTypeDesc
0x18002435c  mov     eax, [rbx+40h]
0x18002435f  mov     [rbp+290h+pReplaceSet.dwTtl], eax
0x180024362  mov     eax, 5
0x180024367  cmp     [rsi+rcx+18h], ax
0x18002436c  jnz     short loc_180024389
0x18002436e  mov     dword ptr [rbp+290h+pReplaceSet.wType], 80005h
0x180024375  bts     r15d, 0Eh
0x18002437a  mov     rax, [rbx+10h]
0x18002437e  mov     qword ptr [rbp+290h+pReplaceSet.Data], rax
0x180024382  mov     [rsp+390h+var_350], r15d
0x180024387  jmp     short loc_1800243BF
0x180024389  mov     dword ptr [rbp+290h+pReplaceSet.wType], 100021h
0x180024390  mov     rax, [rbx+10h]
0x180024394  mov     qword ptr [rbp+290h+pReplaceSet.Data], rax
0x180024398  mov     rax, [rbx+50h]
0x18002439c  movzx   ecx, word ptr [rax+rdi*8+14h]
0x1800243a1  mov     word ptr [rbp+290h+pReplaceSet.Data+8], cx
0x1800243a5  mov     rax, [rbx+50h]
0x1800243a9  movzx   ecx, word ptr [rax+rdi*8+18h]
0x1800243ae  mov     word ptr [rbp+290h+pReplaceSet.Data+0Ah], cx
0x1800243b2  mov     rax, [rbx+50h]
0x1800243b6  movzx   ecx, word ptr [rax+rdi*8+1Ch]
0x1800243bb  mov     word ptr [rbp+290h+pReplaceSet.Data+0Ch], cx
0x1800243bf  xor     edx, edx; Val
0x1800243c1  lea     rcx, [rsp+390h+var_330]; void *
0x1800243c6  lea     r8d, [rdx+60h]; Size
0x1800243ca  call    memset_0
0x1800243cf  mov     [rsp+390h+var_330], 80000001h
0x1800243d7  xor     r9d, r9d; hCredentials
0x1800243da  mov     [rsp+390h+var_320], 1
0x1800243e2  mov     rax, [rbx+50h]
0x1800243e6  cmp     [rax+rdi*8+20h], r12b
0x1800243eb  jz      loc_18002448E
0x1800243f1  lea     eax, [r9+5]
0x1800243f5  lea     rcx, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A; _NL_DNS_NAME_TYPE_DESC near * NlDcDnsNameTypeDesc
0x1800243fc  cmp     [rsi+rcx+18h], ax
0x180024401  lea     rax, [rsp+390h+var_330]
0x180024406  lea     rcx, [rbp+290h+pReplaceSet]; pAddRecords
0x18002440a  jnz     short loc_180024425
0x18002440c  xor     r8d, r8d; hContext
0x18002440f  mov     [rsp+390h+pReserved], rax; pReserved
0x180024414  mov     edx, r15d; Options
0x180024417  call    cs:__imp_DnsReplaceRecordSetUTF8
0x18002441e  nop     dword ptr [rax+rax+00h]
0x180024423  jmp     short loc_180024440
0x180024425  mov     [rsp+390h+var_368], rax; pReserved
0x18002442a  mov     r8d, r15d; Options
0x18002442d  xor     edx, edx; pDeleteRecords
0x18002442f  mov     [rsp+390h+pReserved], r12; pExtraList
0x180024434  call    cs:__imp_DnsModifyRecordsInSet_UTF8
0x18002443b  nop     dword ptr [rax+rax+00h]
0x180024440  mov     r8d, [rbx+40h]
0x180024444  lea     r9, [rbp+290h+MultiByteStr]; char *
0x18002444b  mov     rcx, [rbx+10h]
0x18002444f  mov     esi, eax
0x180024451  mov     rax, [rbx+50h]
0x180024455  lea     rdx, [rax+rdi*8]; struct _NL_DNS_NAME_INFO *
0x180024459  test    esi, esi
0x18002445b  jnz     short loc_180024485
0x18002445d  lea     rax, aNldnsupdatereq_2; "NlDnsUpdateRequestWorker: Registered (s"...
0x180024464  mov     qword ptr [rsp+390h+Flags], rax; unsigned __int16 *
0x180024469  mov     dword ptr [rsp+390h+var_368], r8d; unsigned int
0x18002446e  mov     r8, r14; char *
0x180024471  mov     [rsp+390h+pReserved], rcx; char *
0x180024476  mov     ecx, 4000h; unsigned int
0x18002447b  call    ?NlPrintDnsNameInfoRoutine@@YAXKPEAU_NL_DNS_NAME_INFO@@PEAD11KPEAGZZ; NlPrintDnsNameInfoRoutine(ulong,_NL_DNS_NAME_INFO *,char *,char *,char *,ulong,ushort *,...)
0x180024480  jmp     loc_1800246D1
0x180024485  lea     r10, aNldnsupdatereq; "NlDnsUpdateRequestWorker: Failed to reg"...
0x18002448c  jmp     short loc_1800244DF
0x18002448e  lea     rax, [rsp+390h+var_330]
0x180024493  mov     r8d, r15d; Options
0x180024496  mov     [rsp+390h+var_368], rax; pReserved
0x18002449b  lea     rdx, [rbp+290h+pReplaceSet]; pDeleteRecords
0x18002449f  xor     ecx, ecx; pAddRecords
0x1800244a1  mov     [rsp+390h+pReserved], r12; pExtraList
0x1800244a6  call    cs:__imp_DnsModifyRecordsInSet_UTF8
0x1800244ad  nop     dword ptr [rax+rax+00h]
0x1800244b2  mov     r8d, [rbx+40h]
0x1800244b6  lea     r9, [rbp+290h+MultiByteStr]; char *
0x1800244bd  mov     rcx, [rbx+10h]
0x1800244c1  mov     esi, eax
0x1800244c3  mov     rax, [rbx+50h]
0x1800244c7  lea     rdx, [rax+rdi*8]; struct _NL_DNS_NAME_INFO *
0x1800244cb  test    esi, esi
0x1800244cd  jnz     short loc_1800244D8
0x1800244cf  lea     rax, aNldnsupdatereq_1; "NlDnsUpdateRequestWorker: Deregistered "...
0x1800244d6  jmp     short loc_180024464
0x1800244d8  lea     r10, aNldnsupdatereq_3; "NlDnsUpdateRequestWorker: Failed to der"...
0x1800244df  mov     dword ptr [rsp+390h+var_358], esi
0x1800244e3  mov     eax, 20000h
0x1800244e8  mov     qword ptr [rsp+390h+Flags], r10; unsigned __int16 *
0x1800244ed  mov     r11d, esi
0x1800244f0  mov     dword ptr [rsp+390h+var_368], r8d; unsigned int
0x1800244f5  mov     r8, r14; char *
0x1800244f8  mov     [rsp+390h+pReserved], rcx; char *
0x1800244fd  mov     ecx, eax; unsigned int
0x1800244ff  call    ?NlPrintDnsNameInfoRoutine@@YAXKPEAU_NL_DNS_NAME_INFO@@PEAD11KPEAGZZ; NlPrintDnsNameInfoRoutine(ulong,_NL_DNS_NAME_INFO *,char *,char *,char *,ulong,ushort *,...)
0x180024504  mov     rax, [rbx+50h]
0x180024508  mov     [rax+rdi*8+24h], esi
0x18002450c  mov     ecx, [rbp+290h+var_310]; unsigned int
0x18002450f  test    ecx, ecx
0x180024511  jz      short loc_180024521
0x180024513  lea     rdx, [rbp+290h+pNodeBuffer]; unsigned __int16 *
0x18002451a  call    ?NetpIpAddressToWStr@@YAXKQEAG@Z; NetpIpAddressToWStr(ulong,ushort * const)
0x18002451f  jmp     short loc_180024594
0x180024521  movups  xmm0, [rbp+290h+var_308]
0x180024525  mov     eax, 17h
0x18002452a  mov     [rsp+390h+Flags], 2; Flags
0x180024532  mov     dword ptr [rsp+390h+var_368], r12d; ServiceBufferSize
0x180024537  lea     r8, [rbp+290h+pNodeBuffer]; pNodeBuffer
0x18002453e  lea     rcx, [rbp+290h+pSockaddr]; pSockaddr
0x180024542  mov     dword ptr [rbp+290h+pSockaddr+2], r12d
0x180024546  mov     word ptr [rbp+290h+pSockaddr+6], r12w
0x18002454b  lea     r14d, [rax+2Bh]
0x18002454f  mov     [rbp+290h+var_258], r12d
0x180024553  mov     r9d, r14d; NodeBufferSize
0x180024556  mov     word ptr [rbp+290h+pSockaddr], ax
0x18002455a  lea     edx, [rax+5]; SockaddrLength
0x18002455d  mov     [rsp+390h+pReserved], r12; pServiceBuffer
0x180024562  movdqu  xmmword ptr [rbp+290h+pSockaddr+8], xmm0
0x180024567  call    cs:__imp_GetNameInfoW
0x18002456e  nop     dword ptr [rax+rax+00h]
0x180024573  test    eax, eax
0x180024575  jz      short loc_180024594
0x180024577  lea     r8, aUnavailable; "<UNAVAILABLE>"
0x18002457e  mov     edx, r14d
0x180024581  lea     rcx, [rbp+290h+pNodeBuffer]
0x180024588  call    cs:__imp__o_wcscpy_s
0x18002458f  nop     dword ptr [rax+rax+00h]
0x180024594  movzx   r9d, word ptr [rsp+390h+var_314]
0x18002459a  lea     r8, aLu_0; "%lu"
0x1800245a1  mov     r14d, 0Eh
0x1800245a7  lea     rcx, [rbp+290h+Buffer]; Buffer
0x1800245ab  mov     edx, r14d; BufferCount
0x1800245ae  call    swprintf_s
  ... truncated ...
```
