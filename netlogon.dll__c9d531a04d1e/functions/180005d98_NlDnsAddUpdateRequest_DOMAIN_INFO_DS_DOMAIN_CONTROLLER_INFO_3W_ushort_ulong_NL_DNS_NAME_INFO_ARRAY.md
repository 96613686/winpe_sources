# NlDnsAddUpdateRequest(_DOMAIN_INFO *,DS_DOMAIN_CONTROLLER_INFO_3W *,ushort *,ulong,_NL_DNS_NAME_INFO_ARRAY *)

- ea: `0x180005d98`
- end: `0x1800065c0`
- name: `?NlDnsAddUpdateRequest@@YAKPEAU_DOMAIN_INFO@@PEAUDS_DOMAIN_CONTROLLER_INFO_3W@@PEAGKPEAU_NL_DNS_NAME_INFO_ARRAY@@@Z`
- size: `2088`
- prototype: `unsigned int __fastcall(struct _DOMAIN_INFO *, struct DS_DOMAIN_CONTROLLER_INFO_3W *, unsigned __int16 *, unsigned int, struct _NL_DNS_NAME_INFO_ARRAY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180031ae0`

## callees

- `0x180005d98`
- `0x180007278`
- `0x180007b50`
- `0x180008ba0`
- `0x18000ba1c`
- `0x18000d710`
- `0x1800109fc`
- `0x18008315c`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180005e3d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180005e3d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006392`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006448`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006392`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006448`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006067`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800062c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006067`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800062c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000657e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800065a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000657e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800065a7`
- `ntdll!RtlLeaveCriticalSection` at `0x18000651d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000651d`
- `ntdll!RtlEnterCriticalSection` at `0x18000649e`
- `ntdll!RtlEnterCriticalSection` at `0x18000649e`
- `netutils!NetApiBufferFree` at `0x180006599`
- `netutils!NetApiBufferFree` at `0x180006599`
- `DNSAPI!DnsValidateName_W` at `0x180005edc`
- `DNSAPI!DnsValidateName_W` at `0x180005edc`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsCanRODCHostNdncForNetLogon` at `0x1800060ab`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsCanRODCHostNdncForNetLogon` at `0x1800060ab`

## string_xrefs

- `0x18000653b`: `NlDnsAddUpdateRequest: Integer overflow in size calculation at line %d\n`
- `0x1800060d1`: `onecore\ds\netapi\svcdlls\logonsrv\server\dns.cxx`
- `0x180005ded`: `NlDnsAddUpdateRequest: DnsHostName: %ws, SiteName: %ws, DnsTtl: %ld\n`
- `0x180005f71`: `NlDnsAddUpdateRequest: DnsHostName: %ws. Invalid site name %ws.\n`
- `0x1800060e8`: `NlDnsAddUpdateRequest: DnsHostName: %ws. Invalid Ndnc domain name %ws.\n`
- `0x180006500`: `NlDnsAddUpdateRequest: %ws: Cann't queue DNS Update Request work item\n`

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
    v10 = (unsigned int)_o__wcsicmp(a2->SiteName) == 0;
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
          v31 = 6588;
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
                6732,
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
                v31 = 6745;
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
      v31 = 6685;
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
    v31 = 6809;
    goto LABEL_120;
  }
  v50 = 40LL * v11;
  if ( v50 > 0xFFFFFFFF )
  {
    v31 = 6817;
    goto LABEL_120;
  }
  v51 = v50 + v49;
  if ( (unsigned int)v50 + v49 < v49 )
  {
    v31 = 6824;
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
    _o_wcscpy_s(v56, v60 >> 1);
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
          _o_wcscpy_s(v56, (unsigned __int64)v57 >> 1);
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
  v69 = (_QWORD *)qword_1800F0B58;
  if ( *(HLOCAL **)qword_1800F0B58 != &NlGlobalDnsUpdateRequestList )
    goto LABEL_125;
  *(_QWORD *)v12 = &NlGlobalDnsUpdateRequestList;
  v70 = NlGlobalDnsUpdateRequestInProgress == 0;
  v13 = 0;
  *((_QWORD *)v12 + 1) = v69;
  *v69 = v12;
  qword_1800F0B58 = (__int64)v12;
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
0x180005d98  mov     rax, rsp
0x180005d9b  mov     [rax+20h], r9d
0x180005d9f  mov     [rax+18h], r8
0x180005da3  mov     [rax+10h], rdx
0x180005da7  mov     [rax+8], rcx
0x180005dab  push    rbp
0x180005dac  push    rbx
0x180005dad  push    rsi
0x180005dae  push    rdi
0x180005daf  push    r12
0x180005db1  push    r13
0x180005db3  push    r14
0x180005db5  push    r15
0x180005db7  mov     rbp, rsp
0x180005dba  sub     rsp, 68h
0x180005dbe  xor     ecx, ecx
0x180005dc0  xorps   xmm0, xmm0
0x180005dc3  cmp     cs:?NlGlobalTerminate@@3HA, ecx; int NlGlobalTerminate
0x180005dc9  mov     rdi, r8
0x180005dcc  mov     rbx, rdx
0x180005dcf  mov     [rbp+var_2C], ecx
0x180005dd2  movups  xmmword ptr [rbp+hMem], xmm0
0x180005dd6  jz      short loc_180005DE2
0x180005dd8  mov     eax, 3E3h
0x180005ddd  jmp     loc_1800065AF
0x180005de2  mov     r8, [rdx+8]
0x180005de6  mov     r12d, ecx
0x180005de9  movzx   r13d, cl
0x180005ded  lea     rdx, aNldnsaddupdate; "NlDnsAddUpdateRequest: DnsHostName: %ws"...
0x180005df4  mov     [rbp+var_38], cl
0x180005df7  mov     esi, ecx
0x180005df9  mov     [rbp+var_30], ecx
0x180005dfc  mov     r14, rcx
0x180005dff  mov     [rbp+var_34], ecx
0x180005e02  mov     [rbp+Src], rcx
0x180005e06  mov     ecx, 20000h; unsigned int
0x180005e0b  mov     [rsp+68h+var_48], r9d
0x180005e10  mov     r9, rdi
0x180005e13  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180005e18  lea     rax, [rbp+hMem]
0x180005e1c  xor     r10d, r10d
0x180005e1f  mov     [rbp+hMem+8], rax
0x180005e23  lea     rax, [rbp+hMem]
0x180005e27  mov     [rbp+hMem], rax
0x180005e2b  mov     r15d, 1
0x180005e31  test    rdi, rdi
0x180005e34  jz      short loc_180005E4C
0x180005e36  mov     rcx, [rbx+10h]
0x180005e3a  mov     rdx, rdi
0x180005e3d  call    cs:__imp__o__wcsicmp
0x180005e43  xor     r10d, r10d
0x180005e46  test    eax, eax
0x180005e48  cmovz   r13d, r15d
0x180005e4c  mov     r15, [rbp+arg_20]
0x180005e50  mov     ebx, 57h ; 'W'
0x180005e55  mov     eax, r10d
0x180005e58  lea     r9d, [rbx-52h]
0x180005e5c  lea     r11, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A; _NL_DNS_NAME_TYPE_DESC near * NlDcDnsNameTypeDesc
0x180005e63  mov     [rbp+var_28], eax
0x180005e66  cmp     eax, [r15]
0x180005e69  jnb     loc_1800061D4
0x180005e6f  mov     rcx, [r15+8]
0x180005e73  lea     rdi, [rax+rax*4]
0x180005e77  cmp     dword ptr [rcx+rdi*8], 28h ; '('
0x180005e7b  jnb     loc_1800061A6
0x180005e81  mov     eax, [rcx+rdi*8+10h]
0x180005e85  cmp     eax, 6
0x180005e88  jnb     loc_1800061A6
0x180005e8e  mov     r8d, [rcx+rdi*8]
0x180005e92  shl     r8, 5
0x180005e96  lea     rdx, [r8+r11]
0x180005e9a  cmp     [r8+r11+1Ah], r10b
0x180005e9f  jnz     short loc_180005EB5
0x180005ea1  cmp     [rdx+18h], r9w
0x180005ea6  jz      short loc_180005EB5
0x180005ea8  mov     dword ptr [rcx+rdi*8+24h], 32h ; '2'
0x180005eb0  jmp     loc_1800061AA
0x180005eb5  cmp     [rcx+rdi*8+20h], r10b
0x180005eba  jnz     loc_180005F40
0x180005ec0  cmp     eax, r9d
0x180005ec3  jnz     loc_1800061A6
0x180005ec9  mov     rax, [rcx+rdi*8+8]
0x180005ece  test    rax, rax
0x180005ed1  jz      loc_1800061A6
0x180005ed7  xor     edx, edx; Format
0x180005ed9  mov     rcx, rax; pszName
0x180005edc  call    cs:__imp_DnsValidateName_W
0x180005ee2  xor     r10d, r10d
0x180005ee5  test    eax, eax
0x180005ee7  jz      short loc_180005F03
0x180005ee9  cmp     eax, 2554h
0x180005eee  jz      short loc_180005F03
0x180005ef0  mov     rax, [r15+8]
0x180005ef4  mov     [rax+rdi*8+24h], ebx
0x180005ef8  mov     r9d, 5
0x180005efe  jmp     loc_1800061AA
0x180005f03  mov     rdx, [r15+8]
0x180005f07  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005f0b  mov     rcx, [rdx+rdi*8+8]
0x180005f10  inc     rax
0x180005f13  cmp     [rcx+rax*2], r10w
0x180005f18  jnz     short loc_180005F10
0x180005f1a  lea     ecx, [rax+1]
0x180005f1d  lea     ecx, [r12+rcx*2]
0x180005f21  cmp     ecx, r12d
0x180005f24  jb      loc_1800061B4
0x180005f2a  mov     r12d, ecx
0x180005f2d  mov     [rbp+var_30], ecx
0x180005f30  mov     [rdx+rdi*8+24h], r10d
0x180005f35  mov     r9d, 5
0x180005f3b  jmp     loc_18000619F
0x180005f40  cmp     [rdx+18h], r9w
0x180005f45  jnz     short loc_180005F62
0x180005f47  add     eax, 0FFFFFFFEh
0x180005f4a  cmp     eax, 1
0x180005f4d  ja      loc_1800061A6
0x180005f53  inc     esi
0x180005f55  mov     [rcx+rdi*8+24h], r10d
0x180005f5a  mov     [rbp+var_34], esi
0x180005f5d  jmp     loc_1800061AA
0x180005f62  test    r13b, r13b
0x180005f65  jnz     short loc_180005FA3
0x180005f67  cmp     [rbp+var_38], r10b
0x180005f6b  jnz     short loc_180005F95
0x180005f6d  mov     rax, [rbp+arg_8]
0x180005f71  lea     rdx, aNldnsaddupdate_1; "NlDnsAddUpdateRequest: DnsHostName: %ws"...
0x180005f78  mov     r9, [rbp+arg_10]
0x180005f7c  mov     ecx, 100h; unsigned int
0x180005f81  mov     r8, [rax+8]
0x180005f85  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180005f8a  xor     r10d, r10d
0x180005f8d  mov     [rbp+var_38], 1
0x180005f91  lea     r9d, [r10+5]
0x180005f95  mov     rax, [r15+8]
0x180005f99  mov     [rax+rdi*8+24h], r9d
0x180005f9e  jmp     loc_1800061AA
0x180005fa3  test    eax, eax
0x180005fa5  jz      loc_180006193
0x180005fab  sub     eax, 1
0x180005fae  jz      loc_180006193
0x180005fb4  sub     eax, 1
0x180005fb7  jz      loc_180006177
0x180005fbd  sub     eax, 1
0x180005fc0  jz      loc_180006177
0x180005fc6  cmp     eax, 1
0x180005fc9  jnz     loc_1800061A6
0x180005fcf  cmp     [rcx+rdi*8+8], r10
0x180005fd4  jz      loc_1800061A6
0x180005fda  test    dword ptr [r8+r11+14h], 400h
0x180005fe3  jz      loc_1800061A6
0x180005fe9  mov     rsi, [rbp+hMem]
0x180005fed  lea     rax, [rbp+hMem]
0x180005ff1  cmp     rsi, rax
0x180005ff4  jz      short loc_18000605F
0x180005ff6  mov     rdx, [r15+8]
0x180005ffa  mov     rcx, [rsi+10h]; unsigned __int16 *
0x180005ffe  mov     rdx, [rdx+rdi*8+8]; unsigned __int16 *
0x180006003  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x180006008  xor     r10d, r10d
0x18000600b  test    eax, eax
0x18000600d  jnz     short loc_180006014
0x18000600f  mov     rsi, [rsi]
0x180006012  jmp     short loc_180005FED
0x180006014  cmp     byte ptr [rsi+18h], 1
0x180006018  mov     rcx, [r15+8]
0x18000601c  jnz     short loc_18000604C
0x18000601e  mov     rdx, [rcx+rdi*8+8]
0x180006023  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006027  inc     rax
0x18000602a  cmp     [rdx+rax*2], r10w
0x18000602f  jnz     short loc_180006027
0x180006031  lea     edx, [rax+1]
0x180006034  lea     edx, [r12+rdx*2]
0x180006038  cmp     edx, r12d
0x18000603b  jnb     loc_18000615F
0x180006041  mov     r8d, 1A1Dh
0x180006047  jmp     loc_18000653B
0x18000604c  mov     esi, [rbp+var_34]
0x18000604f  mov     r9d, 5
0x180006055  mov     [rcx+rdi*8+24h], r9d
0x18000605a  jmp     loc_1800061AA
0x18000605f  mov     edx, 20h ; ' '; uBytes
0x180006064  lea     ecx, [rdx+20h]; uFlags
0x180006067  call    cs:__imp_LocalAlloc
0x18000606d  xor     r10d, r10d
0x180006070  mov     rsi, rax
0x180006073  test    rax, rax
0x180006076  jz      loc_1800061CA
0x18000607c  mov     rax, [r15+8]
0x180006080  mov     rcx, [rax+rdi*8+8]
0x180006085  mov     [rsi+10h], rcx
0x180006089  mov     [rbp+var_2C], r10d
0x18000608d  call    IsDsGetServersAndSitesForNetLogonPresent
0x180006092  test    al, al
0x180006094  jz      short loc_1800060C2
0x180006096  mov     rcx, [r15+8]
0x18000609a  lea     r8, [rbp+var_2C]
0x18000609e  mov     rax, [rbp+arg_8]
0x1800060a2  mov     rcx, [rcx+rdi*8+8]
0x1800060a7  mov     rdx, [rax+8]
0x1800060ab  call    cs:__imp_DsCanRODCHostNdncForNetLogon
0x1800060b1  xor     r10d, r10d
0x1800060b4  test    eax, eax
0x1800060b6  jnz     short loc_1800060C2
0x1800060b8  cmp     [rbp+var_2C], 1
0x1800060bc  jnz     short loc_1800060C2
0x1800060be  mov     al, 1
0x1800060c0  jmp     short loc_18000610C
0x1800060c2  call    IsDsGetServersAndSitesForNetLogonPresent
0x1800060c7  test    al, al
0x1800060c9  jnz     short loc_1800060E4
0x1800060cb  mov     r8d, 1A4Ch; unsigned int
0x1800060d1  lea     rdx, aOnecoreDsNetap_10; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800060d8  lea     rcx, aIsdscanrodchos; "IsDsCanRODCHostNdncForNetLogonPresent()"
0x1800060df  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800060e4  mov     r9, [r15+8]
0x1800060e8  lea     rdx, aNldnsaddupdate_3; "NlDnsAddUpdateRequest: DnsHostName: %ws"...
0x1800060ef  mov     rax, [rbp+arg_8]
0x1800060f3  mov     ecx, 100h; unsigned int
0x1800060f8  mov     r9, [r9+rdi*8+8]
0x1800060fd  mov     r8, [rax+8]
0x180006101  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180006106  xor     r10d, r10d
0x180006109  mov     al, r10b
0x18000610c  mov     [rsi+18h], al
0x18000610f  lea     rcx, [rbp+hMem]
0x180006113  mov     rax, [rbp+hMem+8]
0x180006117  cmp     [rax], rcx
0x18000611a  jnz     loc_180006586
0x180006120  mov     [rsi+8], rax
0x180006124  lea     rcx, [rbp+hMem]
0x180006128  mov     [rsi], rcx
0x18000612b  mov     [rax], rsi
0x18000612e  mov     rcx, [r15+8]
0x180006132  mov     [rbp+hMem+8], rsi
0x180006136  cmp     byte ptr [rsi+18h], 1
0x18000613a  jnz     loc_18000604C
0x180006140  mov     rdx, [rcx+rdi*8+8]
0x180006145  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006149  inc     rax
0x18000614c  cmp     [rdx+rax*2], r10w
0x180006151  jnz     short loc_180006149
0x180006153  lea     edx, [rax+1]
0x180006156  lea     edx, [r12+rdx*2]
0x18000615a  cmp     edx, r12d
0x18000615d  jb      short loc_1800061BF
0x18000615f  mov     esi, [rbp+var_34]
0x180006162  mov     r12d, edx
0x180006165  inc     esi
0x180006167  mov     [rbp+var_30], edx
0x18000616a  mov     [rbp+var_34], esi
0x18000616d  mov     [rcx+rdi*8+24h], r10d
0x180006172  jmp     loc_180005EF8
0x180006177  mov     al, [r8+r11+1Bh]
0x18000617c  test    al, al
0x18000617e  jz      short loc_180006185
0x180006180  inc     esi
0x180006182  mov     [rbp+var_34], esi
0x180006185  neg     al
0x180006187  sbb     eax, eax
0x180006189  not     eax
0x18000618b  and     eax, ebx
0x18000618d  mov     [rcx+rdi*8+24h], eax
0x180006191  jmp     short loc_1800061AA
0x180006193  cmp     [r8+r11+1Bh], r10b
0x180006198  jnz     short loc_1800061A6
0x18000619a  mov     [rcx+rdi*8+24h], r10d
0x18000619f  inc     esi
0x1800061a1  mov     [rbp+var_34], esi
0x1800061a4  jmp     short loc_1800061AA
0x1800061a6  mov     [rcx+rdi*8+24h], ebx
0x1800061aa  mov     eax, [rbp+var_28]
0x1800061ad  inc     eax
0x1800061af  jmp     loc_180005E5C
0x1800061b4  mov     r8d, 19BCh
0x1800061ba  jmp     loc_18000653B
0x1800061bf  mov     r8d, 1A59h
0x1800061c5  jmp     loc_18000653B
0x1800061ca  mov     ebx, 8
0x1800061cf  jmp     loc_180006558
0x1800061d4  test    esi, esi
0x1800061d6  jz      loc_180006558
0x1800061dc  mov     rax, [rbp+arg_8]
0x1800061e0  xor     r8d, r8d; int
0x1800061e3  xor     edx, edx; lpMultiByteStr
0x1800061e5  mov     rcx, [rax+8]; lpWideCharStr
0x1800061e9  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x1800061ee  xor     r10d, r10d
0x1800061f1  mov     [rbp+Src], rax
0x1800061f5  mov     r8, rax
0x1800061f8  test    rax, rax
0x1800061fb  jz      short loc_1800061CA
0x1800061fd  mov     edx, r10d
0x180006200  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006204  mov     [rbp+var_28], edx
0x180006207  mov     rax, rdi
0x18000620a  mov     r13d, r10d
0x18000620d  mov     r12d, r10d
0x180006210  inc     rax
0x180006213  cmp     [r8+rax], r10b
  ... truncated ...
```
