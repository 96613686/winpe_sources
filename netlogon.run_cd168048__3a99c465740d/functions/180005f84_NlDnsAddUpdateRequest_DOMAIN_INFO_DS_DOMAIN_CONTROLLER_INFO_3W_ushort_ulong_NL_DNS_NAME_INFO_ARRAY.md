# NlDnsAddUpdateRequest(_DOMAIN_INFO *,DS_DOMAIN_CONTROLLER_INFO_3W *,ushort *,ulong,_NL_DNS_NAME_INFO_ARRAY *)

- ea: `0x180005f84`
- end: `0x1800067f5`
- name: `?NlDnsAddUpdateRequest@@YAKPEAU_DOMAIN_INFO@@PEAUDS_DOMAIN_CONTROLLER_INFO_3W@@PEAGKPEAU_NL_DNS_NAME_INFO_ARRAY@@@Z`
- size: `2161`
- prototype: `unsigned int __fastcall(struct _DOMAIN_INFO *, struct DS_DOMAIN_CONTROLLER_INFO_3W *, unsigned __int16 *, unsigned int, struct _NL_DNS_NAME_INFO_ARRAY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800338b0`

## callees

- `0x180005f84`
- `0x180007518`
- `0x180007e90`
- `0x1800090c0`
- `0x18000c130`
- `0x18000dd00`
- `0x1800110ac`
- `0x1800892fc`
- `0x180090204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006029`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006029`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000659c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006658`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000659c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006658`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000625f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800064c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000625f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800064c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067d5`
- `ntdll!RtlLeaveCriticalSection` at `0x180006739`
- `ntdll!RtlLeaveCriticalSection` at `0x180006739`
- `ntdll!RtlEnterCriticalSection` at `0x1800066b4`
- `ntdll!RtlEnterCriticalSection` at `0x1800066b4`
- `netutils!NetApiBufferFree` at `0x1800067c1`
- `netutils!NetApiBufferFree` at `0x1800067c1`
- `DNSAPI!DnsValidateName_W` at `0x1800060ce`
- `DNSAPI!DnsValidateName_W` at `0x1800060ce`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsCanRODCHostNdncForNetLogon` at `0x1800062a9`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsCanRODCHostNdncForNetLogon` at `0x1800062a9`

## string_xrefs

- `0x18000675d`: `NlDnsAddUpdateRequest: Integer overflow in size calculation at line %d\n`
- `0x1800062d5`: `onecore\ds\netapi\svcdlls\logonsrv\server\dns.cxx`
- `0x180005fd9`: `NlDnsAddUpdateRequest: DnsHostName: %ws, SiteName: %ws, DnsTtl: %ld\n`
- `0x180006169`: `NlDnsAddUpdateRequest: DnsHostName: %ws. Invalid site name %ws.\n`
- `0x1800062ec`: `NlDnsAddUpdateRequest: DnsHostName: %ws. Invalid Ndnc domain name %ws.\n`
- `0x18000671c`: `NlDnsAddUpdateRequest: %ws: Cann't queue DNS Update Request work item\n`

## pseudocode

```c
__int64 __fastcall NlDnsAddUpdateRequest(
        struct _DOMAIN_INFO *a1,
        struct DS_DOMAIN_CONTROLLER_INFO_3W *a2,
        unsigned __int16 *a3,
        int a4,
        struct _NL_DNS_NAME_INFO_ARRAY *a5)
{
  LPWSTR DnsHostName; // r8
  unsigned int v9; // r12d
  bool v10; // r13
  unsigned int v11; // esi
  char *v12; // r14
  unsigned int v13; // ebx
  __int64 i; // rax
  __int64 v15; // rcx
  __int64 v16; // rdi
  unsigned int v17; // eax
  __int64 v18; // r8
  char *v19; // rdx
  DNS_STATUS v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rax
  unsigned int v23; // ecx
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  const unsigned __int16 *j; // rsi
  __int64 v28; // rcx
  __int64 v29; // rax
  unsigned int v30; // edx
  __int64 v31; // r8
  HLOCAL *v32; // rax
  HLOCAL *v33; // rsi
  char v34; // al
  char *v35; // r9
  HLOCAL **v36; // rax
  __int64 v37; // rax
  char v38; // al
  unsigned int v39; // edx
  __int64 v40; // rax
  unsigned int v41; // r13d
  unsigned int v42; // r12d
  size_t v43; // rbx
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rax
  unsigned int v49; // r8d
  unsigned __int64 v50; // rdx
  unsigned int v51; // r15d
  char *v52; // rax
  void *v53; // rdx
  unsigned int v54; // esi
  char *v55; // rdi
  char *v56; // rdi
  unsigned int v57; // esi
  struct DS_DOMAIN_CONTROLLER_INFO_3W *v58; // r12
  __int64 v59; // r15
  unsigned __int64 v60; // rdx
  unsigned int v61; // ebx
  int v62; // r15d
  __int64 v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rcx
  unsigned int v68; // ecx
  _QWORD *v69; // rax
  bool v70; // zf
  HLOCAL v71; // rcx
  _QWORD *v72; // rax
  HLOCAL *v73; // rdx
  char v74; // [rsp+30h] [rbp-38h]
  int v75; // [rsp+34h] [rbp-34h]
  unsigned int v76; // [rsp+38h] [rbp-30h]
  int v77; // [rsp+3Ch] [rbp-2Ch] BYREF
  unsigned int v78; // [rsp+40h] [rbp-28h]
  void *Src; // [rsp+48h] [rbp-20h]
  HLOCAL hMem[3]; // [rsp+50h] [rbp-18h] BYREF

  v77 = 0;
  *(_OWORD *)hMem = 0;
  if ( NlGlobalTerminate )
    return 995;
  DnsHostName = a2->DnsHostName;
  v9 = 0;
  v10 = 0;
  v74 = 0;
  v11 = 0;
  v76 = 0;
  v12 = 0;
  v75 = 0;
  Src = 0;
  NlPrintRoutine(
    0x20000u,
    L"NlDnsAddUpdateRequest: DnsHostName: %ws, SiteName: %ws, DnsTtl: %ld\n",
    DnsHostName,
    a3,
    a4);
  hMem[1] = hMem;
  hMem[0] = hMem;
  if ( a3 )
    v10 = (unsigned int)_o__wcsicmp(a2->SiteName, a3) == 0;
  v13 = 87;
  for ( i = 0; ; i = v78 + 1 )
  {
    v78 = i;
    if ( (unsigned int)i >= *(_DWORD *)a5 )
      break;
    v15 = *((_QWORD *)a5 + 1);
    v16 = 5 * i;
    if ( *(_DWORD *)(v15 + 40 * i) >= 0x28u )
      goto LABEL_66;
    v17 = *(_DWORD *)(v15 + 40 * i + 16);
    if ( v17 >= 6 )
      goto LABEL_66;
    v18 = 32LL * *(unsigned int *)(v15 + 8 * v16);
    v19 = (char *)&NlDcDnsNameTypeDesc + v18;
    if ( !*((_BYTE *)&NlDcDnsNameTypeDesc + v18 + 26) && *((_WORD *)v19 + 12) != 5 )
    {
      *(_DWORD *)(v15 + 8 * v16 + 36) = 50;
      continue;
    }
    if ( !*(_BYTE *)(v15 + 8 * v16 + 32) )
    {
      if ( v17 == 5 && *(_QWORD *)(v15 + 8 * v16 + 8) )
      {
        v20 = DnsValidateName_W(*(PCWSTR *)(v15 + 8 * v16 + 8), DnsNameDomain);
        if ( v20 && v20 != 9556 )
        {
          *(_DWORD *)(*((_QWORD *)a5 + 1) + 8 * v16 + 36) = 87;
          continue;
        }
        v21 = *((_QWORD *)a5 + 1);
        v22 = -1;
        do
          ++v22;
        while ( *(_WORD *)(*(_QWORD *)(v21 + 8 * v16 + 8) + 2 * v22) );
        v23 = v9 + 2 * (v22 + 1);
        if ( v23 < v9 )
        {
          v31 = 6448;
          goto LABEL_120;
        }
        v9 += 2 * (v22 + 1);
        v76 = v23;
        *(_DWORD *)(v21 + 8 * v16 + 36) = 0;
        goto LABEL_65;
      }
      goto LABEL_66;
    }
    if ( *((_WORD *)v19 + 12) == 5 )
    {
      if ( v17 - 2 <= 1 )
      {
        ++v11;
        *(_DWORD *)(v15 + 8 * v16 + 36) = 0;
        v75 = v11;
        continue;
      }
      goto LABEL_66;
    }
    if ( !v10 )
    {
      if ( !v74 )
      {
        NlPrintRoutine(
          0x100u,
          L"NlDnsAddUpdateRequest: DnsHostName: %ws. Invalid site name %ws.\n",
          a2->DnsHostName,
          a3);
        v74 = 1;
      }
      *(_DWORD *)(*((_QWORD *)a5 + 1) + 8 * v16 + 36) = 5;
      continue;
    }
    if ( !v17 || (v24 = v17 - 1) == 0 )
    {
      if ( !*((_BYTE *)&NlDcDnsNameTypeDesc + v18 + 27) )
      {
        *(_DWORD *)(v15 + 8 * v16 + 36) = 0;
LABEL_65:
        v75 = ++v11;
        continue;
      }
LABEL_66:
      *(_DWORD *)(v15 + 8 * v16 + 36) = 87;
      continue;
    }
    v25 = v24 - 1;
    if ( !v25 || (v26 = v25 - 1) == 0 )
    {
      v38 = *((_BYTE *)&NlDcDnsNameTypeDesc + v18 + 27);
      if ( v38 )
        v75 = ++v11;
      *(_DWORD *)(v15 + 8 * v16 + 36) = v38 == 0 ? 0x57 : 0;
      continue;
    }
    if ( v26 != 1
      || !*(_QWORD *)(v15 + 8 * v16 + 8)
      || (*(_DWORD *)((_BYTE *)&NlDcDnsNameTypeDesc + v18 + 20) & 0x400) == 0 )
    {
      goto LABEL_66;
    }
    for ( j = (const unsigned __int16 *)hMem[0]; ; j = *(const unsigned __int16 **)j )
    {
      if ( j == (const unsigned __int16 *)hMem )
      {
        v32 = (HLOCAL *)LocalAlloc(0x40u, 0x20u);
        v33 = v32;
        if ( v32 )
        {
          v32[2] = *(HLOCAL *)(*((_QWORD *)a5 + 1) + 8 * v16 + 8);
          v77 = 0;
          if ( (unsigned __int8)IsDsGetServersAndSitesForNetLogonPresent()
            && !(unsigned int)DsCanRODCHostNdncForNetLogon(
                                *(_QWORD *)(*((_QWORD *)a5 + 1) + 8 * v16 + 8),
                                a2->DnsHostName,
                                &v77)
            && v77 == 1 )
          {
            v34 = 1;
          }
          else
          {
            if ( !(unsigned __int8)IsDsGetServersAndSitesForNetLogonPresent() )
              NlAssertFailed(
                "IsDsCanRODCHostNdncForNetLogonPresent()",
                "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\dns.cxx",
                0x19C0u,
                v35);
            NlPrintRoutine(
              0x100u,
              L"NlDnsAddUpdateRequest: DnsHostName: %ws. Invalid Ndnc domain name %ws.\n",
              a2->DnsHostName,
              *(_QWORD *)(*((_QWORD *)a5 + 1) + 8 * v16 + 8));
            v34 = 0;
          }
          *((_BYTE *)v33 + 24) = v34;
          v36 = (HLOCAL **)hMem[1];
          if ( *(HLOCAL **)hMem[1] == hMem )
          {
            v33[1] = hMem[1];
            *v33 = hMem;
            *v36 = v33;
            v28 = *((_QWORD *)a5 + 1);
            hMem[1] = v33;
            if ( *((_BYTE *)v33 + 24) == 1 )
            {
              v37 = -1;
              do
                ++v37;
              while ( *(_WORD *)(*(_QWORD *)(v28 + 8 * v16 + 8) + 2 * v37) );
              v30 = v9 + 2 * (v37 + 1);
              if ( v30 < v9 )
              {
                v31 = 6605;
                goto LABEL_120;
              }
              goto LABEL_59;
            }
LABEL_45:
            v11 = v75;
            *(_DWORD *)(v28 + 8 * v16 + 36) = 5;
            goto LABEL_67;
          }
LABEL_125:
          __fastfail(3u);
        }
LABEL_70:
        v13 = 8;
        goto LABEL_121;
      }
      if ( (unsigned int)NlEqualDnsName(
                           *((const unsigned __int16 **)j + 2),
                           *(const unsigned __int16 **)(*((_QWORD *)a5 + 1) + 8 * v16 + 8)) )
        break;
    }
    v28 = *((_QWORD *)a5 + 1);
    if ( *((_BYTE *)j + 24) != 1 )
      goto LABEL_45;
    v29 = -1;
    do
      ++v29;
    while ( *(_WORD *)(*(_QWORD *)(v28 + 8 * v16 + 8) + 2 * v29) );
    v30 = v9 + 2 * (v29 + 1);
    if ( v30 < v9 )
    {
      v31 = 6545;
LABEL_120:
      NlPrintRoutine(0x100u, L"NlDnsAddUpdateRequest: Integer overflow in size calculation at line %d\n", v31);
      v13 = NetpNtStatusToApiStatus(-1073741675);
      goto LABEL_121;
    }
LABEL_59:
    v9 = v30;
    v11 = v75 + 1;
    v76 = v30;
    ++v75;
    *(_DWORD *)(v28 + 8 * v16 + 36) = 0;
LABEL_67:
    ;
  }
  if ( !v11 )
    goto LABEL_121;
  Src = NetpCreateUtf8StrFromWStr(a2->DnsHostName, 0, 0);
  if ( !Src )
    goto LABEL_70;
  v39 = 0;
  v78 = 0;
  v40 = -1;
  v41 = 0;
  v42 = 0;
  do
    ++v40;
  while ( *((_BYTE *)Src + v40) );
  v43 = (unsigned int)(v40 + 1);
  v44 = *((_QWORD *)a1 + 19);
  if ( v44 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *(_BYTE *)(v44 + v45) );
    v41 = v45 + 1;
  }
  v46 = *((_QWORD *)a1 + 20);
  if ( v46 )
  {
    v47 = -1;
    do
      ++v47;
    while ( *(_BYTE *)(v46 + v47) );
    v42 = v47 + 1;
  }
  if ( a3 )
  {
    v48 = -1;
    do
      ++v48;
    while ( a3[v48] );
    v39 = 2 * v48 + 2;
    v78 = v39;
  }
  v49 = v41 + v42 + v43 + v39 + v76 + 88;
  if ( v49 < v76 )
  {
    v31 = 6669;
    goto LABEL_120;
  }
  v50 = 40LL * v11;
  if ( v50 > 0xFFFFFFFF )
  {
    v31 = 6677;
    goto LABEL_120;
  }
  v51 = v50 + v49;
  if ( (unsigned int)v50 + v49 < v49 )
  {
    v31 = 6684;
    goto LABEL_120;
  }
  v52 = (char *)LocalAlloc(0x40u, v51);
  v12 = v52;
  if ( !v52 )
    goto LABEL_70;
  v53 = Src;
  *((_QWORD *)v52 + 10) = v52 + 88;
  v54 = 40 * v11;
  v55 = &v52[v54 + 88];
  *((_QWORD *)v52 + 2) = v55;
  memcpy_0(v55, v53, v43);
  v56 = &v55[v43];
  v57 = v51 - v54 - v43 - 88;
  if ( *((_QWORD *)a1 + 19) )
  {
    *((_QWORD *)v12 + 3) = v56;
    memcpy_0(v56, *((const void **)a1 + 19), v41);
    v56 += v41;
    v57 -= v41;
  }
  if ( *((_QWORD *)a1 + 20) )
  {
    *((_QWORD *)v12 + 4) = v56;
    memcpy_0(v56, *((const void **)a1 + 20), v42);
    v56 += v42;
    v57 -= v42;
  }
  v58 = a2;
  *(GUID *)(v12 + 40) = a2->NtdsDsaObjectGuid;
  if ( a3 )
  {
    v59 = v78;
    v60 = v78;
    *((_QWORD *)v12 + 7) = v56;
    _o_wcscpy_s(v56, v60 >> 1, a3);
    v56 += v59;
    v57 -= v59;
  }
  v61 = 0;
  *((_DWORD *)v12 + 16) = a4;
  if ( *(_DWORD *)a5 )
  {
    v62 = v75;
    do
    {
      if ( !v62 )
        break;
      v63 = *((_QWORD *)a5 + 1);
      if ( !*(_DWORD *)(v63 + 40LL * v61 + 36) )
      {
        v64 = 5LL * *((unsigned int *)v12 + 18);
        v65 = *((_QWORD *)v12 + 10);
        *(_OWORD *)(v65 + 8 * v64) = *(_OWORD *)(v63 + 40LL * v61);
        *(_OWORD *)(v65 + 8 * v64 + 16) = *(_OWORD *)(v63 + 40LL * v61 + 16);
        *(_QWORD *)(v65 + 8 * v64 + 32) = *(_QWORD *)(v63 + 40LL * v61 + 32);
        v66 = *((_QWORD *)v12 + 10);
        if ( (unsigned int)(*(_DWORD *)(*((_QWORD *)a5 + 1) + 40LL * v61 + 16) - 4) <= 1 )
        {
          *(_QWORD *)(v66 + 40LL * *((unsigned int *)v12 + 18) + 8) = v56;
          _o_wcscpy_s(v56, (unsigned __int64)v57 >> 1, *(_QWORD *)(*((_QWORD *)a5 + 1) + 40LL * v61 + 8));
          v67 = -1;
          do
            ++v67;
          while ( *(_WORD *)&v56[2 * v67] );
          v68 = 2 * v67 + 2;
          v56 += v68;
          v57 -= v68;
        }
        else
        {
          *(_QWORD *)(v66 + 40LL * *((unsigned int *)v12 + 18) + 8) = 0;
        }
        --v62;
        ++*((_DWORD *)v12 + 18);
      }
      ++v61;
    }
    while ( v61 < *(_DWORD *)a5 );
    v58 = a2;
  }
  if ( NlGlobalTerminate )
  {
    v13 = 995;
    goto LABEL_121;
  }
  RtlEnterCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
  v69 = (_QWORD *)qword_1800F7B58;
  if ( *(HLOCAL **)qword_1800F7B58 != &NlGlobalDnsUpdateRequestList )
    goto LABEL_125;
  *(_QWORD *)v12 = &NlGlobalDnsUpdateRequestList;
  v70 = NlGlobalDnsUpdateRequestInProgress == 0;
  v13 = 0;
  *((_QWORD *)v12 + 1) = v69;
  *v69 = v12;
  qword_1800F7B58 = (__int64)v12;
  v12 = 0;
  if ( v70 )
  {
    if ( (unsigned int)NlQueueWorkItem((struct _WORKER_ITEM *)&NlGlobalDnsUpdateRequestWorkItem, 1, 0) )
    {
      NlGlobalDnsUpdateRequestInProgress = 1;
    }
    else
    {
      NlPrintRoutine(
        0x100u,
        L"NlDnsAddUpdateRequest: %ws: Cann't queue DNS Update Request work item\n",
        v58->DnsHostName);
      v13 = 31;
    }
  }
  RtlLeaveCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
LABEL_121:
  while ( 1 )
  {
    v71 = hMem[0];
    if ( hMem[0] == hMem )
      break;
    v72 = *(_QWORD **)hMem[0];
    if ( *(HLOCAL *)(*(_QWORD *)hMem[0] + 8LL) != hMem[0] )
      goto LABEL_125;
    v73 = (HLOCAL *)*((_QWORD *)hMem[0] + 1);
    if ( *v73 != hMem[0] )
      goto LABEL_125;
    *v73 = v72;
    v72[1] = v73;
    LocalFree(v71);
  }
  if ( Src )
    NetApiBufferFree(Src);
  if ( v12 )
    LocalFree(v12);
  return v13;
}

```

## disassembly

```asm
0x180005f84  mov     rax, rsp
0x180005f87  mov     [rax+20h], r9d
0x180005f8b  mov     [rax+18h], r8
0x180005f8f  mov     [rax+10h], rdx
0x180005f93  mov     [rax+8], rcx
0x180005f97  push    rbp
0x180005f98  push    rbx
0x180005f99  push    rsi
0x180005f9a  push    rdi
0x180005f9b  push    r12
0x180005f9d  push    r13
0x180005f9f  push    r14
0x180005fa1  push    r15
0x180005fa3  mov     rbp, rsp
0x180005fa6  sub     rsp, 68h
0x180005faa  xor     ecx, ecx
0x180005fac  xorps   xmm0, xmm0
0x180005faf  cmp     cs:?NlGlobalTerminate@@3HA, ecx; int NlGlobalTerminate
0x180005fb5  mov     rdi, r8
0x180005fb8  mov     rbx, rdx
0x180005fbb  mov     [rbp+var_2C], ecx
0x180005fbe  movups  xmmword ptr [rbp+hMem], xmm0
0x180005fc2  jz      short loc_180005FCE
0x180005fc4  mov     eax, 3E3h
0x180005fc9  jmp     loc_1800067E3
0x180005fce  mov     r8, [rdx+8]
0x180005fd2  mov     r12d, ecx
0x180005fd5  movzx   r13d, cl
0x180005fd9  lea     rdx, aNldnsaddupdate; "NlDnsAddUpdateRequest: DnsHostName: %ws"...
0x180005fe0  mov     [rbp+var_38], cl
0x180005fe3  mov     esi, ecx
0x180005fe5  mov     [rbp+var_30], ecx
0x180005fe8  mov     r14, rcx
0x180005feb  mov     [rbp+var_34], ecx
0x180005fee  mov     [rbp+Src], rcx
0x180005ff2  mov     ecx, 20000h; unsigned int
0x180005ff7  mov     [rsp+68h+var_48], r9d
0x180005ffc  mov     r9, rdi
0x180005fff  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180006004  lea     rax, [rbp+hMem]
0x180006008  xor     r10d, r10d
0x18000600b  mov     [rbp+hMem+8], rax
0x18000600f  lea     rax, [rbp+hMem]
0x180006013  mov     [rbp+hMem], rax
0x180006017  mov     r15d, 1
0x18000601d  test    rdi, rdi
0x180006020  jz      short loc_18000603E
0x180006022  mov     rcx, [rbx+10h]
0x180006026  mov     rdx, rdi
0x180006029  call    cs:__imp__o__wcsicmp
0x180006030  nop     dword ptr [rax+rax+00h]
0x180006035  xor     r10d, r10d
0x180006038  test    eax, eax
0x18000603a  cmovz   r13d, r15d
0x18000603e  mov     r15, [rbp+arg_20]
0x180006042  mov     ebx, 57h ; 'W'
0x180006047  mov     eax, r10d
0x18000604a  lea     r9d, [rbx-52h]
0x18000604e  lea     r11, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A; _NL_DNS_NAME_TYPE_DESC near * NlDcDnsNameTypeDesc
0x180006055  mov     [rbp+var_28], eax
0x180006058  cmp     eax, [r15]
0x18000605b  jnb     loc_1800063D8
0x180006061  mov     rcx, [r15+8]
0x180006065  lea     rdi, [rax+rax*4]
0x180006069  cmp     dword ptr [rcx+rdi*8], 28h ; '('
0x18000606d  jnb     loc_1800063AA
0x180006073  mov     eax, [rcx+rdi*8+10h]
0x180006077  cmp     eax, 6
0x18000607a  jnb     loc_1800063AA
0x180006080  mov     r8d, [rcx+rdi*8]
0x180006084  shl     r8, 5
0x180006088  lea     rdx, [r8+r11]
0x18000608c  cmp     [r8+r11+1Ah], r10b
0x180006091  jnz     short loc_1800060A7
0x180006093  cmp     [rdx+18h], r9w
0x180006098  jz      short loc_1800060A7
0x18000609a  mov     dword ptr [rcx+rdi*8+24h], 32h ; '2'
0x1800060a2  jmp     loc_1800063AE
0x1800060a7  cmp     [rcx+rdi*8+20h], r10b
0x1800060ac  jnz     loc_180006138
0x1800060b2  cmp     eax, r9d
0x1800060b5  jnz     loc_1800063AA
0x1800060bb  mov     rax, [rcx+rdi*8+8]
0x1800060c0  test    rax, rax
0x1800060c3  jz      loc_1800063AA
0x1800060c9  xor     edx, edx; Format
0x1800060cb  mov     rcx, rax; pszName
0x1800060ce  call    cs:__imp_DnsValidateName_W
0x1800060d5  nop     dword ptr [rax+rax+00h]
0x1800060da  xor     r10d, r10d
0x1800060dd  test    eax, eax
0x1800060df  jz      short loc_1800060FB
0x1800060e1  cmp     eax, 2554h
0x1800060e6  jz      short loc_1800060FB
0x1800060e8  mov     rax, [r15+8]
0x1800060ec  mov     [rax+rdi*8+24h], ebx
0x1800060f0  mov     r9d, 5
0x1800060f6  jmp     loc_1800063AE
0x1800060fb  mov     rdx, [r15+8]
0x1800060ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006103  mov     rcx, [rdx+rdi*8+8]
0x180006108  inc     rax
0x18000610b  cmp     [rcx+rax*2], r10w
0x180006110  jnz     short loc_180006108
0x180006112  lea     ecx, [rax+1]
0x180006115  lea     ecx, [r12+rcx*2]
0x180006119  cmp     ecx, r12d
0x18000611c  jb      loc_1800063B8
0x180006122  mov     r12d, ecx
0x180006125  mov     [rbp+var_30], ecx
0x180006128  mov     [rdx+rdi*8+24h], r10d
0x18000612d  mov     r9d, 5
0x180006133  jmp     loc_1800063A3
0x180006138  cmp     [rdx+18h], r9w
0x18000613d  jnz     short loc_18000615A
0x18000613f  add     eax, 0FFFFFFFEh
0x180006142  cmp     eax, 1
0x180006145  ja      loc_1800063AA
0x18000614b  inc     esi
0x18000614d  mov     [rcx+rdi*8+24h], r10d
0x180006152  mov     [rbp+var_34], esi
0x180006155  jmp     loc_1800063AE
0x18000615a  test    r13b, r13b
0x18000615d  jnz     short loc_18000619B
0x18000615f  cmp     [rbp+var_38], r10b
0x180006163  jnz     short loc_18000618D
0x180006165  mov     rax, [rbp+arg_8]
0x180006169  lea     rdx, aNldnsaddupdate_1; "NlDnsAddUpdateRequest: DnsHostName: %ws"...
0x180006170  mov     r9, [rbp+arg_10]
0x180006174  mov     ecx, 100h; unsigned int
0x180006179  mov     r8, [rax+8]
0x18000617d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180006182  xor     r10d, r10d
0x180006185  mov     [rbp+var_38], 1
0x180006189  lea     r9d, [r10+5]
0x18000618d  mov     rax, [r15+8]
0x180006191  mov     [rax+rdi*8+24h], r9d
0x180006196  jmp     loc_1800063AE
0x18000619b  test    eax, eax
0x18000619d  jz      loc_180006397
0x1800061a3  sub     eax, 1
0x1800061a6  jz      loc_180006397
0x1800061ac  sub     eax, 1
0x1800061af  jz      loc_18000637B
0x1800061b5  sub     eax, 1
0x1800061b8  jz      loc_18000637B
0x1800061be  cmp     eax, 1
0x1800061c1  jnz     loc_1800063AA
0x1800061c7  cmp     [rcx+rdi*8+8], r10
0x1800061cc  jz      loc_1800063AA
0x1800061d2  test    dword ptr [r8+r11+14h], 400h
0x1800061db  jz      loc_1800063AA
0x1800061e1  mov     rsi, [rbp+hMem]
0x1800061e5  lea     rax, [rbp+hMem]
0x1800061e9  cmp     rsi, rax
0x1800061ec  jz      short loc_180006257
0x1800061ee  mov     rdx, [r15+8]
0x1800061f2  mov     rcx, [rsi+10h]; unsigned __int16 *
0x1800061f6  mov     rdx, [rdx+rdi*8+8]; unsigned __int16 *
0x1800061fb  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x180006200  xor     r10d, r10d
0x180006203  test    eax, eax
0x180006205  jnz     short loc_18000620C
0x180006207  mov     rsi, [rsi]
0x18000620a  jmp     short loc_1800061E5
0x18000620c  cmp     byte ptr [rsi+18h], 1
0x180006210  mov     rcx, [r15+8]
0x180006214  jnz     short loc_180006244
0x180006216  mov     rdx, [rcx+rdi*8+8]
0x18000621b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000621f  inc     rax
0x180006222  cmp     [rdx+rax*2], r10w
0x180006227  jnz     short loc_18000621F
0x180006229  lea     edx, [rax+1]
0x18000622c  lea     edx, [r12+rdx*2]
0x180006230  cmp     edx, r12d
0x180006233  jnb     loc_180006363
0x180006239  mov     r8d, 1991h
0x18000623f  jmp     loc_18000675D
0x180006244  mov     esi, [rbp+var_34]
0x180006247  mov     r9d, 5
0x18000624d  mov     [rcx+rdi*8+24h], r9d
0x180006252  jmp     loc_1800063AE
0x180006257  mov     edx, 20h ; ' '; uBytes
0x18000625c  lea     ecx, [rdx+20h]; uFlags
0x18000625f  call    cs:__imp_LocalAlloc
0x180006266  nop     dword ptr [rax+rax+00h]
0x18000626b  xor     r10d, r10d
0x18000626e  mov     rsi, rax
0x180006271  test    rax, rax
0x180006274  jz      loc_1800063CE
0x18000627a  mov     rax, [r15+8]
0x18000627e  mov     rcx, [rax+rdi*8+8]
0x180006283  mov     [rsi+10h], rcx
0x180006287  mov     [rbp+var_2C], r10d
0x18000628b  call    IsDsGetServersAndSitesForNetLogonPresent
0x180006290  test    al, al
0x180006292  jz      short loc_1800062C6
0x180006294  mov     rcx, [r15+8]
0x180006298  lea     r8, [rbp+var_2C]
0x18000629c  mov     rax, [rbp+arg_8]
0x1800062a0  mov     rcx, [rcx+rdi*8+8]
0x1800062a5  mov     rdx, [rax+8]
0x1800062a9  call    cs:__imp_DsCanRODCHostNdncForNetLogon
0x1800062b0  nop     dword ptr [rax+rax+00h]
0x1800062b5  xor     r10d, r10d
0x1800062b8  test    eax, eax
0x1800062ba  jnz     short loc_1800062C6
0x1800062bc  cmp     [rbp+var_2C], 1
0x1800062c0  jnz     short loc_1800062C6
0x1800062c2  mov     al, 1
0x1800062c4  jmp     short loc_180006310
0x1800062c6  call    IsDsGetServersAndSitesForNetLogonPresent
0x1800062cb  test    al, al
0x1800062cd  jnz     short loc_1800062E8
0x1800062cf  mov     r8d, 19C0h; unsigned int
0x1800062d5  lea     rdx, aOnecoreDsNetap_10; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800062dc  lea     rcx, aIsdscanrodchos; "IsDsCanRODCHostNdncForNetLogonPresent()"
0x1800062e3  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800062e8  mov     r9, [r15+8]
0x1800062ec  lea     rdx, aNldnsaddupdate_3; "NlDnsAddUpdateRequest: DnsHostName: %ws"...
0x1800062f3  mov     rax, [rbp+arg_8]
0x1800062f7  mov     ecx, 100h; unsigned int
0x1800062fc  mov     r9, [r9+rdi*8+8]
0x180006301  mov     r8, [rax+8]
0x180006305  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000630a  xor     r10d, r10d
0x18000630d  mov     al, r10b
0x180006310  mov     [rsi+18h], al
0x180006313  lea     rcx, [rbp+hMem]
0x180006317  mov     rax, [rbp+hMem+8]
0x18000631b  cmp     [rax], rcx
0x18000631e  jnz     loc_1800067AE
0x180006324  mov     [rsi+8], rax
0x180006328  lea     rcx, [rbp+hMem]
0x18000632c  mov     [rsi], rcx
0x18000632f  mov     [rax], rsi
0x180006332  mov     rcx, [r15+8]
0x180006336  mov     [rbp+hMem+8], rsi
0x18000633a  cmp     byte ptr [rsi+18h], 1
0x18000633e  jnz     loc_180006244
0x180006344  mov     rdx, [rcx+rdi*8+8]
0x180006349  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000634d  inc     rax
0x180006350  cmp     [rdx+rax*2], r10w
0x180006355  jnz     short loc_18000634D
0x180006357  lea     edx, [rax+1]
0x18000635a  lea     edx, [r12+rdx*2]
0x18000635e  cmp     edx, r12d
0x180006361  jb      short loc_1800063C3
0x180006363  mov     esi, [rbp+var_34]
0x180006366  mov     r12d, edx
0x180006369  inc     esi
0x18000636b  mov     [rbp+var_30], edx
0x18000636e  mov     [rbp+var_34], esi
0x180006371  mov     [rcx+rdi*8+24h], r10d
0x180006376  jmp     loc_1800060F0
0x18000637b  mov     al, [r8+r11+1Bh]
0x180006380  test    al, al
0x180006382  jz      short loc_180006389
0x180006384  inc     esi
0x180006386  mov     [rbp+var_34], esi
0x180006389  neg     al
0x18000638b  sbb     eax, eax
0x18000638d  not     eax
0x18000638f  and     eax, ebx
0x180006391  mov     [rcx+rdi*8+24h], eax
0x180006395  jmp     short loc_1800063AE
0x180006397  cmp     [r8+r11+1Bh], r10b
0x18000639c  jnz     short loc_1800063AA
0x18000639e  mov     [rcx+rdi*8+24h], r10d
0x1800063a3  inc     esi
0x1800063a5  mov     [rbp+var_34], esi
0x1800063a8  jmp     short loc_1800063AE
0x1800063aa  mov     [rcx+rdi*8+24h], ebx
0x1800063ae  mov     eax, [rbp+var_28]
0x1800063b1  inc     eax
0x1800063b3  jmp     loc_18000604E
0x1800063b8  mov     r8d, 1930h
0x1800063be  jmp     loc_18000675D
0x1800063c3  mov     r8d, 19CDh
0x1800063c9  jmp     loc_18000675D
0x1800063ce  mov     ebx, 8
0x1800063d3  jmp     loc_18000677A
0x1800063d8  test    esi, esi
0x1800063da  jz      loc_18000677A
0x1800063e0  mov     rax, [rbp+arg_8]
0x1800063e4  xor     r8d, r8d; int
0x1800063e7  xor     edx, edx; lpMultiByteStr
0x1800063e9  mov     rcx, [rax+8]; lpWideCharStr
0x1800063ed  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x1800063f2  xor     r10d, r10d
0x1800063f5  mov     [rbp+Src], rax
0x1800063f9  mov     r8, rax
0x1800063fc  test    rax, rax
0x1800063ff  jz      short loc_1800063CE
0x180006401  mov     edx, r10d
0x180006404  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006408  mov     [rbp+var_28], edx
0x18000640b  mov     rax, rdi
  ... truncated ...
```
