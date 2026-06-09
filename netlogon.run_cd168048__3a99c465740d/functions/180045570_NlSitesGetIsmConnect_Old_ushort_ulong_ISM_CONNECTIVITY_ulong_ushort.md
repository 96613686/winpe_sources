# NlSitesGetIsmConnect_Old(ushort *,ulong,_ISM_CONNECTIVITY * *,ulong *,ushort * * *)

- ea: `0x180045570`
- end: `0x180045ac7`
- name: `?NlSitesGetIsmConnect_Old@@YAHPEAGKPEAPEAU_ISM_CONNECTIVITY@@PEAKPEAPEAPEAG@Z`
- size: `1367`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, struct _ISM_CONNECTIVITY **, unsigned int *, unsigned __int16 ***)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020480`
- `0x180045ad0`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x1800110ac`
- `0x180045570`
- `0x180078fd8`
- `0x18008a854`
- `0x18008a878`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004588c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004588c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004583d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004583d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004571e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004571e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180045704`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800457fa`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180045704`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800457fa`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180045869`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180045869`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045665`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800456d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045777`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800457c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045665`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800456d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045777`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800457c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045a4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045a63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045a8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045aa1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045a4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045a63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045a8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045aa1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800459f5`
- `ntdll!RtlLeaveCriticalSection` at `0x1800459f5`
- `ntdll!RtlEnterCriticalSection` at `0x1800458c0`
- `ntdll!RtlEnterCriticalSection` at `0x1800458c0`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x180045616`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x1800456ae`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x180045616`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x1800456ae`

## string_xrefs

- `0x180045647`: `onecore\ds\netapi\svcdlls\logonsrv\server\nlsite.cxx`
- `0x18004568e`: `onecore\ds\netapi\svcdlls\logonsrv\server\nlsite.cxx`
- `0x1800455ca`: `NlSitesGetIsmConnect: Avoided during startup.\n`
- `0x1800455f0`: `NlSitesGetIsmConnect: ISM service not started.\n`
- `0x180045a0e`: `NlSitesGetIsmConnect: Cannot GetConfigurationName 0x%lx.\n`
- `0x180045695`: `IsGetConfigurationNamePresent()`
- `0x1800458cf`: `NlSitesGetIsmConnect: Site link costs for %ld sites:\n`

## pseudocode

```c
__int64 __fastcall NlSitesGetIsmConnect_Old(
        unsigned __int16 *a1,
        int a2,
        struct _ISM_CONNECTIVITY **a3,
        unsigned int *a4,
        unsigned __int16 ***a5)
{
  HLOCAL *v5; // rdi
  unsigned int *v6; // r13
  unsigned __int16 *v8; // r12
  unsigned int *v9; // rbp
  unsigned __int16 ***v10; // r15
  unsigned __int8 v11; // r14
  unsigned __int16 *v12; // rdx
  unsigned int ConfigurationName; // eax
  char *v14; // r9
  unsigned int v15; // esi
  unsigned int v16; // esi
  char *v17; // r9
  int v18; // eax
  __int64 v19; // r8
  unsigned __int16 ***v20; // rax
  unsigned int v21; // eax
  struct _ISM_CONNECTIVITY *v22; // rax
  unsigned int v23; // ecx
  HLOCAL v24; // rax
  unsigned int v25; // r12d
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rcx
  unsigned int v29; // edi
  wchar_t *v30; // rax
  unsigned int v31; // edi
  const char *v32; // r8
  unsigned int v33; // edi
  unsigned __int16 *v34; // rdx
  struct _ISM_CONNECTIVITY *v35; // rdx
  unsigned int v36; // eax
  const char *v37; // r8
  __int64 v38; // rax
  unsigned int i; // esi
  void *v40; // rcx
  SIZE_T uBytes; // [rsp+70h] [rbp+18h] BYREF
  unsigned int *v44; // [rsp+78h] [rbp+20h]

  v44 = a4;
  v5 = (HLOCAL *)a5;
  LODWORD(uBytes) = 0;
  v6 = a4;
  *a3 = 0;
  *a4 = -1;
  v8 = a1;
  v9 = 0;
  v10 = 0;
  if ( v5 )
    *v5 = 0;
  v11 = 1;
  if ( NlGlobalChangeLogNetlogonState != 2 )
  {
    v12 = L"NlSitesGetIsmConnect: Avoided during startup.\n";
LABEL_5:
    NlPrintRoutine(0x8000000u, v12);
    goto LABEL_60;
  }
  if ( (unsigned int)NlWaitForService(L"IsmServ", a2) )
  {
    v12 = L"NlSitesGetIsmConnect: ISM service not started.\n";
    goto LABEL_5;
  }
  LODWORD(uBytes) = 0;
  if ( !(unsigned __int8)IsDsGetServersAndSitesForNetLogonPresent() )
  {
    v15 = -1073741637;
LABEL_58:
    v19 = v15;
    goto LABEL_59;
  }
  ConfigurationName = GetConfigurationName(4, &uBytes);
  v15 = ConfigurationName;
  if ( ConfigurationName != -1073741789 )
  {
    if ( ConfigurationName != -1073741702 && ConfigurationName != -1073741275 )
      NlAssertFailed(
        "Status == STATUS_BUFFER_TOO_SMALL || Status == STATUS_PROCEDURE_NOT_FOUND || Status == STATUS_NOT_FOUND",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\nlsite.cxx",
        0x1A3u,
        v14);
    goto LABEL_58;
  }
  v16 = 0;
  v9 = (unsigned int *)LocalAlloc(0, (unsigned int)uBytes);
  if ( !v9 )
    goto LABEL_60;
  if ( !(unsigned __int8)IsDsGetServersAndSitesForNetLogonPresent() )
    NlAssertFailed(
      "IsGetConfigurationNamePresent()",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\nlsite.cxx",
      0x1B5u,
      v17);
  v18 = GetConfigurationName(4, &uBytes);
  if ( v18 < 0 )
  {
    v19 = (unsigned int)v18;
LABEL_59:
    NlPrintRoutine(0x100u, L"NlSitesGetIsmConnect: Cannot GetConfigurationName 0x%lx.\n", v19);
LABEL_60:
    if ( !v5 )
      goto LABEL_67;
    goto LABEL_61;
  }
  v20 = (unsigned __int16 ***)LocalAlloc(0, 2LL * v9[13] + 82);
  a5 = v20;
  v10 = v20;
  if ( !v20 )
    goto LABEL_60;
  _o_wcscpy_s(v20, v9[13] + 41LL, L"CN=IP,CN=Inter-Site Transports,CN=Sites,");
  _o_wcscat_s(v10, v9[13] + 41LL, v9 + 14);
  v21 = I_ISMGetConnectivity(v10, a3);
  if ( v21 )
  {
    NlPrintRoutine(0x100u, L"NlSitesGetIsmConnect: Cannot I_ISMGetConnectivity %ld.\n", v21);
    goto LABEL_60;
  }
  v22 = *a3;
  if ( !*a3 )
  {
    NlPrintRoutine(0x100u, L"NlSitesGetIsmConnect: I_ISMGetConnectivity returned NULL.\n");
    goto LABEL_60;
  }
  v23 = *(_DWORD *)v22;
  if ( !v5 )
  {
LABEL_31:
    if ( v23 )
    {
      v29 = 0;
      do
      {
        if ( !(unsigned int)_o__wcsnicmp(*(_QWORD *)(*((_QWORD *)v22 + 1) + 8LL * v29), L"CN=", 3) )
        {
          *(_QWORD *)(*((_QWORD *)*a3 + 1) + 8LL * v29) += 6LL;
          v30 = wcschr(*(const wchar_t **)(*((_QWORD *)*a3 + 1) + 8LL * v29), 0x2Cu);
          if ( v30 )
            *v30 = 0;
        }
        if ( !(unsigned int)_o__wcsicmp(v8, *(_QWORD *)(*((_QWORD *)*a3 + 1) + 8LL * v29)) )
          *v6 = v29;
        v22 = *a3;
        ++v29;
      }
      while ( v29 < *(_DWORD *)*a3 );
      v10 = a5;
    }
    v25 = 0;
    goto LABEL_41;
  }
  v24 = LocalAlloc(0x40u, 8LL * v23);
  v25 = 0;
  *v5 = v24;
  if ( v24 )
  {
    v22 = *a3;
    if ( *(_DWORD *)*a3 )
    {
      while ( 1 )
      {
        v26 = *(_QWORD *)(*((_QWORD *)v22 + 1) + 8LL * v16);
        v27 = -1;
        do
          ++v27;
        while ( *(_WORD *)(v26 + 2 * v27) );
        LODWORD(uBytes) = v27 + 1;
        *((_QWORD *)*v5 + v16) = LocalAlloc(0x40u, 2LL * (unsigned int)(v27 + 1));
        v28 = *((_QWORD *)*v5 + v16);
        if ( !v28 )
          goto LABEL_61;
        _o_wcscpy_s(v28, (unsigned int)uBytes, *(_QWORD *)(*((_QWORD *)*a3 + 1) + 8LL * v16));
        v22 = *a3;
        ++v16;
        v23 = *(_DWORD *)*a3;
        if ( v16 >= v23 )
        {
          v8 = a1;
          goto LABEL_31;
        }
      }
    }
LABEL_41:
    RtlEnterCriticalSection(&NlGlobalLogFileCritSect);
    NlPrintRoutine(0x8000000u, L"NlSitesGetIsmConnect: Site link costs for %ld sites:\n", *(unsigned int *)*a3);
    v31 = 0;
    if ( *(_DWORD *)*a3 )
    {
      do
      {
        v32 = ",";
        if ( !v31 )
          v32 = "    ";
        NlPrintRoutine(0x8000000u, L"%hs%5d", v32, v31++);
      }
      while ( v31 < *(_DWORD *)*a3 );
      v6 = v44;
    }
    NlPrintRoutine(0x8000000u, L"\n");
    v33 = 0;
    if ( *(_DWORD *)*a3 )
    {
      do
      {
        v34 = L"*";
        if ( *v6 != v33 )
          v34 = L" ";
        NlPrintRoutine(0x8000000u, v34);
        NlPrintRoutine(0x8000000u, L"(%2d) %ws\n", v33, *(_QWORD *)(*((_QWORD *)*a3 + 1) + 8LL * v33));
        v35 = *a3;
        v36 = *(_DWORD *)*a3;
        if ( v36 )
        {
          do
          {
            v37 = ",";
            v38 = v25 + v33 * v36;
            if ( !v25 )
              v37 = "    ";
            NlPrintRoutine(0x8000000u, L"%hs%5d", v37, *(unsigned int *)(*((_QWORD *)v35 + 2) + 12 * v38));
            v35 = *a3;
            ++v25;
            v36 = *(_DWORD *)*a3;
          }
          while ( v25 < v36 );
          v25 = 0;
        }
        NlPrintRoutine(0x8000000u, L"\n");
        ++v33;
      }
      while ( v33 < *(_DWORD *)*a3 );
      v10 = a5;
    }
    RtlLeaveCriticalSection(&NlGlobalLogFileCritSect);
    goto LABEL_70;
  }
LABEL_61:
  if ( *v5 )
  {
    for ( i = 0; i < *(_DWORD *)*a3; ++i )
    {
      v40 = (void *)*((_QWORD *)*v5 + i);
      if ( v40 )
        LocalFree(v40);
    }
    LocalFree(*v5);
    *v5 = 0;
  }
LABEL_67:
  v11 = 0;
  if ( *a3 )
  {
    I_ISMFree();
    *a3 = 0;
  }
  if ( v9 )
LABEL_70:
    LocalFree(v9);
  if ( v10 )
    LocalFree(v10);
  return v11;
}

```

## disassembly

```asm
0x180045570  mov     rax, rsp
0x180045573  mov     [rax+10h], rbx
0x180045577  mov     [rax+20h], r9
0x18004557b  mov     [rax+8], rcx
0x18004557f  push    rbp
0x180045580  push    rsi
0x180045581  push    rdi
0x180045582  push    r12
0x180045584  push    r13
0x180045586  push    r14
0x180045588  push    r15
0x18004558a  sub     rsp, 20h
0x18004558e  mov     rdi, [rsp+58h+arg_20]
0x180045596  xor     esi, esi
0x180045598  mov     [rax+18h], esi
0x18004559b  mov     r13, r9
0x18004559e  mov     [r8], rsi
0x1800455a1  mov     rbx, r8
0x1800455a4  mov     dword ptr [r9], 0FFFFFFFFh
0x1800455ab  mov     r12, rcx
0x1800455ae  mov     ebp, esi
0x1800455b0  mov     r15d, esi
0x1800455b3  test    rdi, rdi
0x1800455b6  jz      short loc_1800455BB
0x1800455b8  mov     [rdi], rsi
0x1800455bb  cmp     cs:?NlGlobalChangeLogNetlogonState@@3W4_CHANGELOG_NETLOGON_STATE@@A, 2; _CHANGELOG_NETLOGON_STATE NlGlobalChangeLogNetlogonState
0x1800455c2  mov     r14d, 1
0x1800455c8  jz      short loc_1800455E0
0x1800455ca  lea     rdx, aNlsitesgetismc_1; "NlSitesGetIsmConnect: Avoided during st"...
0x1800455d1  mov     ecx, 8000000h; unsigned int
0x1800455d6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800455db  jmp     loc_180045A1F
0x1800455e0  lea     rcx, aIsmserv; "IsmServ"
0x1800455e7  call    ?NlWaitForService@@YAJPEAGKE@Z; NlWaitForService(ushort *,ulong,uchar)
0x1800455ec  test    eax, eax
0x1800455ee  jz      short loc_1800455F9
0x1800455f0  lea     rdx, aNlsitesgetismc_4; "NlSitesGetIsmConnect: ISM service not s"...
0x1800455f7  jmp     short loc_1800455D1
0x1800455f9  mov     dword ptr [rsp+58h+uBytes], esi
0x1800455fd  call    IsDsGetServersAndSitesForNetLogonPresent
0x180045602  test    al, al
0x180045604  jz      loc_180045A06
0x18004560a  xor     r8d, r8d
0x18004560d  lea     rdx, [rsp+58h+uBytes]
0x180045612  lea     ecx, [r8+4]
0x180045616  call    cs:__imp_GetConfigurationName
0x18004561d  nop     dword ptr [rax+rax+00h]
0x180045622  mov     esi, eax
0x180045624  cmp     eax, 0C0000023h
0x180045629  jz      short loc_18004565F
0x18004562b  cmp     eax, 0C000007Ah
0x180045630  jz      loc_180045A0B
0x180045636  cmp     eax, 0C0000225h
0x18004563b  jz      loc_180045A0B
0x180045641  mov     r8d, 1A3h; unsigned int
0x180045647  lea     rdx, aOnecoreDsNetap_18; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18004564e  lea     rcx, aStatusStatusBu; "Status == STATUS_BUFFER_TOO_SMALL || St"...
0x180045655  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18004565a  jmp     loc_180045A0B
0x18004565f  mov     edx, dword ptr [rsp+58h+uBytes]; uBytes
0x180045663  xor     ecx, ecx; uFlags
0x180045665  call    cs:__imp_LocalAlloc
0x18004566c  nop     dword ptr [rax+rax+00h]
0x180045671  xor     esi, esi
0x180045673  mov     rbp, rax
0x180045676  test    rax, rax
0x180045679  jz      loc_180045A1F
0x18004567f  call    IsDsGetServersAndSitesForNetLogonPresent
0x180045684  test    al, al
0x180045686  jnz     short loc_1800456A1
0x180045688  mov     r8d, 1B5h; unsigned int
0x18004568e  lea     rdx, aOnecoreDsNetap_18; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180045695  lea     rcx, aIsgetconfigura; "IsGetConfigurationNamePresent()"
0x18004569c  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800456a1  mov     r8, rbp
0x1800456a4  lea     rdx, [rsp+58h+uBytes]
0x1800456a9  mov     ecx, 4
0x1800456ae  call    cs:__imp_GetConfigurationName
0x1800456b5  nop     dword ptr [rax+rax+00h]
0x1800456ba  test    eax, eax
0x1800456bc  jns     short loc_1800456C6
0x1800456be  mov     r8d, eax
0x1800456c1  jmp     loc_180045A0E
0x1800456c6  mov     edx, [rbp+34h]
0x1800456c9  xor     ecx, ecx; uFlags
0x1800456cb  lea     rdx, ds:52h[rdx*2]; uBytes
0x1800456d3  call    cs:__imp_LocalAlloc
0x1800456da  nop     dword ptr [rax+rax+00h]
0x1800456df  mov     [rsp+58h+arg_20], rax
0x1800456e7  mov     r15, rax
0x1800456ea  test    rax, rax
0x1800456ed  jz      loc_180045A1F
0x1800456f3  mov     edx, [rbp+34h]
0x1800456f6  lea     r8, aCnIpCnInterSit; "CN=IP,CN=Inter-Site Transports,CN=Sites"...
0x1800456fd  add     rdx, 29h ; ')'
0x180045701  mov     rcx, rax
0x180045704  call    cs:__imp__o_wcscpy_s
0x18004570b  nop     dword ptr [rax+rax+00h]
0x180045710  mov     edx, [rbp+34h]
0x180045713  lea     r8, [rbp+38h]
0x180045717  add     rdx, 29h ; ')'
0x18004571b  mov     rcx, r15
0x18004571e  call    cs:__imp__o_wcscat_s
0x180045725  nop     dword ptr [rax+rax+00h]
0x18004572a  mov     rdx, rbx
0x18004572d  mov     rcx, r15
0x180045730  call    I_ISMGetConnectivity
0x180045735  test    eax, eax
0x180045737  jz      short loc_180045748
0x180045739  mov     r8d, eax
0x18004573c  lea     rdx, aNlsitesgetismc_0; "NlSitesGetIsmConnect: Cannot I_ISMGetCo"...
0x180045743  jmp     loc_180045A15
0x180045748  mov     rax, [rbx]
0x18004574b  test    rax, rax
0x18004574e  jnz     short loc_180045761
0x180045750  lea     rdx, aNlsitesgetismc_3; "NlSitesGetIsmConnect: I_ISMGetConnectiv"...
0x180045757  mov     ecx, 100h
0x18004575c  jmp     loc_1800455D6
0x180045761  mov     ecx, [rax]
0x180045763  test    rdi, rdi
0x180045766  jz      loc_180045819
0x18004576c  mov     edx, ecx
0x18004576e  mov     ecx, 40h ; '@'; uFlags
0x180045773  shl     rdx, 3; uBytes
0x180045777  call    cs:__imp_LocalAlloc
0x18004577e  nop     dword ptr [rax+rax+00h]
0x180045783  xor     r12d, r12d
0x180045786  mov     [rdi], rax
0x180045789  test    rax, rax
0x18004578c  jz      loc_180045A2C
0x180045792  mov     rax, [rbx]
0x180045795  cmp     [rax], r12d
0x180045798  jbe     loc_1800458B9
0x18004579e  mov     rax, [rax+8]
0x1800457a2  mov     r12d, esi
0x1800457a5  mov     rcx, [rax+r12*8]
0x1800457a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800457ad  xor     edx, edx
0x1800457af  inc     rax
0x1800457b2  cmp     [rcx+rax*2], dx
0x1800457b6  jnz     short loc_1800457AF
0x1800457b8  inc     eax
0x1800457ba  mov     ecx, 40h ; '@'; uFlags
0x1800457bf  mov     edx, eax
0x1800457c1  add     rdx, rdx; uBytes
0x1800457c4  mov     dword ptr [rsp+58h+uBytes], eax
0x1800457c8  call    cs:__imp_LocalAlloc
0x1800457cf  nop     dword ptr [rax+rax+00h]
0x1800457d4  mov     rcx, [rdi]
0x1800457d7  mov     [rcx+r12*8], rax
0x1800457db  mov     rax, [rdi]
0x1800457de  mov     rcx, [rax+r12*8]
0x1800457e2  test    rcx, rcx
0x1800457e5  jz      loc_180045A29
0x1800457eb  mov     rax, [rbx]
0x1800457ee  mov     edx, dword ptr [rsp+58h+uBytes]
0x1800457f2  mov     r8, [rax+8]
0x1800457f6  mov     r8, [r8+r12*8]
0x1800457fa  call    cs:__imp__o_wcscpy_s
0x180045801  nop     dword ptr [rax+rax+00h]
0x180045806  mov     rax, [rbx]
0x180045809  add     esi, r14d
0x18004580c  mov     ecx, [rax]
0x18004580e  cmp     esi, ecx
0x180045810  jb      short loc_18004579E
0x180045812  mov     r12, [rsp+58h+arg_0]
0x180045817  xor     esi, esi
0x180045819  test    ecx, ecx
0x18004581b  jz      loc_1800458B6
0x180045821  mov     edi, esi
0x180045823  xor     r15d, r15d
0x180045826  mov     rcx, [rax+8]
0x18004582a  lea     rdx, aCn_0; "CN="
0x180045831  mov     esi, edi
0x180045833  mov     r8d, 3
0x180045839  mov     rcx, [rcx+rsi*8]
0x18004583d  call    cs:__imp__o__wcsnicmp
0x180045844  nop     dword ptr [rax+rax+00h]
0x180045849  test    eax, eax
0x18004584b  jnz     short loc_18004587E
0x18004584d  mov     rax, [rbx]
0x180045850  mov     edx, 2Ch ; ','; Ch
0x180045855  mov     rcx, [rax+8]
0x180045859  add     qword ptr [rcx+rsi*8], 6
0x18004585e  mov     rax, [rbx]
0x180045861  mov     rcx, [rax+8]
0x180045865  mov     rcx, [rcx+rsi*8]; Str
0x180045869  call    cs:__imp_wcschr
0x180045870  nop     dword ptr [rax+rax+00h]
0x180045875  test    rax, rax
0x180045878  jz      short loc_18004587E
0x18004587a  mov     [rax], r15w
0x18004587e  mov     rax, [rbx]
0x180045881  mov     rcx, r12
0x180045884  mov     rdx, [rax+8]
0x180045888  mov     rdx, [rdx+rsi*8]
0x18004588c  call    cs:__imp__o__wcsicmp
0x180045893  nop     dword ptr [rax+rax+00h]
0x180045898  test    eax, eax
0x18004589a  jnz     short loc_1800458A0
0x18004589c  mov     [r13+0], edi
0x1800458a0  mov     rax, [rbx]
0x1800458a3  add     edi, r14d
0x1800458a6  cmp     edi, [rax]
0x1800458a8  jb      loc_180045826
0x1800458ae  mov     r15, [rsp+58h+arg_20]
0x1800458b6  xor     r12d, r12d
0x1800458b9  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800458c0  call    cs:__imp_RtlEnterCriticalSection
0x1800458c7  nop     dword ptr [rax+rax+00h]
0x1800458cc  mov     r8, [rbx]
0x1800458cf  lea     rdx, aNlsitesgetismc_2; "NlSitesGetIsmConnect: Site link costs f"...
0x1800458d6  mov     esi, 8000000h
0x1800458db  mov     ecx, esi; unsigned int
0x1800458dd  mov     r8d, [r8]
0x1800458e0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800458e5  mov     rax, [rbx]
0x1800458e8  mov     edi, r12d
0x1800458eb  cmp     [rax], r12d
0x1800458ee  jbe     short loc_180045924
0x1800458f0  lea     r13, asc_1800B7C9C; "    "
0x1800458f7  test    edi, edi
0x1800458f9  lea     r8, asc_1800BA8A8; ","
0x180045900  mov     r9d, edi
0x180045903  lea     rdx, aHs5d; "%hs%5d"
0x18004590a  cmovz   r8, r13
0x18004590e  mov     ecx, esi; unsigned int
0x180045910  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180045915  mov     rax, [rbx]
0x180045918  add     edi, r14d
0x18004591b  cmp     edi, [rax]
0x18004591d  jb      short loc_1800458F7
0x18004591f  mov     r13, [rsp+58h+arg_18]
0x180045924  lea     rdx, asc_18009D398; "\n"
0x18004592b  mov     ecx, esi; unsigned int
0x18004592d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180045932  mov     rax, [rbx]
0x180045935  mov     edi, r12d
0x180045938  cmp     [rax], r12d
0x18004593b  jbe     loc_1800459EE
0x180045941  lea     r15, asc_1800B7C9C; "    "
0x180045948  cmp     [r13+0], edi
0x18004594c  lea     rax, asc_1800A0DB4; " "
0x180045953  lea     rdx, asc_1800B7CB8; "*"
0x18004595a  mov     ecx, esi; unsigned int
0x18004595c  cmovnz  rdx, rax; unsigned __int16 *
0x180045960  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180045965  mov     rax, [rbx]
0x180045968  lea     rdx, a2dWs; "(%2d) %ws\n"
0x18004596f  mov     ecx, edi
0x180045971  mov     r8d, edi
0x180045974  mov     r9, [rax+8]
0x180045978  mov     r9, [r9+rcx*8]
0x18004597c  mov     ecx, esi; unsigned int
0x18004597e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180045983  mov     rdx, [rbx]
0x180045986  mov     eax, [rdx]
0x180045988  test    eax, eax
0x18004598a  jz      short loc_1800459CA
0x18004598c  mov     r9, [rdx+10h]
0x180045990  lea     r8, asc_1800BA8A8; ","
0x180045997  imul    eax, edi
0x18004599a  lea     rdx, aHs5d; "%hs%5d"
0x1800459a1  add     eax, r12d
0x1800459a4  test    r12d, r12d
0x1800459a7  cmovz   r8, r15
0x1800459ab  lea     rcx, [rax+rax*2]
0x1800459af  mov     r9d, [r9+rcx*4]
0x1800459b3  mov     ecx, esi; unsigned int
0x1800459b5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800459ba  mov     rdx, [rbx]
0x1800459bd  add     r12d, r14d
0x1800459c0  mov     eax, [rdx]
0x1800459c2  cmp     r12d, eax
0x1800459c5  jb      short loc_18004598C
0x1800459c7  xor     r12d, r12d
0x1800459ca  lea     rdx, asc_18009D398; "\n"
0x1800459d1  mov     ecx, esi; unsigned int
0x1800459d3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800459d8  mov     rax, [rbx]
0x1800459db  add     edi, r14d
0x1800459de  cmp     edi, [rax]
0x1800459e0  jb      loc_180045948
0x1800459e6  mov     r15, [rsp+58h+arg_20]
0x1800459ee  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800459f5  call    cs:__imp_RtlLeaveCriticalSection
0x1800459fc  nop     dword ptr [rax+rax+00h]
0x180045a01  jmp     loc_180045A8A
0x180045a06  mov     esi, 0C00000BBh
0x180045a0b  mov     r8d, esi
0x180045a0e  lea     rdx, aNlsitesgetismc; "NlSitesGetIsmConnect: Cannot GetConfigu"...
0x180045a15  mov     ecx, 100h; unsigned int
0x180045a1a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180045a1f  xor     r12d, r12d
0x180045a22  test    rdi, rdi
0x180045a25  jz      short loc_180045A72
0x180045a27  jmp     short loc_180045A2C
0x180045a29  xor     r12d, r12d
0x180045a2c  cmp     [rdi], r12
0x180045a2f  jz      short loc_180045A72
  ... truncated ...
```
