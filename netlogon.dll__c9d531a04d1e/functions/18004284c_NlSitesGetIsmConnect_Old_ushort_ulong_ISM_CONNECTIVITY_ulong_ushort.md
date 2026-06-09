# NlSitesGetIsmConnect_Old(ushort *,ulong,_ISM_CONNECTIVITY * *,ulong *,ushort * * *)

- ea: `0x18004284c`
- end: `0x180042d2b`
- name: `?NlSitesGetIsmConnect_Old@@YAHPEAGKPEAPEAU_ISM_CONNECTIVITY@@PEAKPEAPEAPEAG@Z`
- size: `1247`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, struct _ISM_CONNECTIVITY **, unsigned int *, unsigned __int16 ***)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f5f0`
- `0x180042d34`

## callees

- `0x180007278`
- `0x18000d710`
- `0x1800109fc`
- `0x18004284c`
- `0x1800738d0`
- `0x180084724`
- `0x180084740`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180042b22`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180042b22`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180042adf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180042adf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800429dc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800429dc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800429c8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180042aa6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800429c8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180042aa6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180042b05`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180042b05`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004293b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004299d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042a2f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042a7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004293b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004299d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042a2f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042a7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042cc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042cda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042cfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042d0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042cc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042cda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042cfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042d0c`
- `ntdll!RtlLeaveCriticalSection` at `0x180042c7b`
- `ntdll!RtlLeaveCriticalSection` at `0x180042c7b`
- `ntdll!RtlEnterCriticalSection` at `0x180042b4c`
- `ntdll!RtlEnterCriticalSection` at `0x180042b4c`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x1800428f2`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x18004297e`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x1800428f2`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x18004297e`

## string_xrefs

- `0x18004291d`: `onecore\ds\netapi\svcdlls\logonsrv\server\nlsite.cxx`
- `0x18004295e`: `onecore\ds\netapi\svcdlls\logonsrv\server\nlsite.cxx`
- `0x1800428a6`: `NlSitesGetIsmConnect: Avoided during startup.\n`
- `0x1800428cc`: `NlSitesGetIsmConnect: ISM service not started.\n`
- `0x180042c8b`: `NlSitesGetIsmConnect: Cannot GetConfigurationName 0x%lx.\n`
- `0x180042965`: `IsGetConfigurationNamePresent()`
- `0x180042b55`: `NlSitesGetIsmConnect: Site link costs for %ld sites:\n`

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
        419,
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
      437,
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
  _o_wcscpy_s(v20, v9[13] + 41LL);
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
        if ( !(unsigned int)_o__wcsicmp(v8) )
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
        _o_wcscpy_s(v28, (unsigned int)uBytes);
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
0x18004284c  mov     rax, rsp
0x18004284f  mov     [rax+10h], rbx
0x180042853  mov     [rax+20h], r9
0x180042857  mov     [rax+8], rcx
0x18004285b  push    rbp
0x18004285c  push    rsi
0x18004285d  push    rdi
0x18004285e  push    r12
0x180042860  push    r13
0x180042862  push    r14
0x180042864  push    r15
0x180042866  sub     rsp, 20h
0x18004286a  mov     rdi, [rsp+58h+arg_20]
0x180042872  xor     esi, esi
0x180042874  mov     [rax+18h], esi
0x180042877  mov     r13, r9
0x18004287a  mov     [r8], rsi
0x18004287d  mov     rbx, r8
0x180042880  mov     dword ptr [r9], 0FFFFFFFFh
0x180042887  mov     r12, rcx
0x18004288a  mov     ebp, esi
0x18004288c  mov     r15d, esi
0x18004288f  test    rdi, rdi
0x180042892  jz      short loc_180042897
0x180042894  mov     [rdi], rsi
0x180042897  cmp     cs:?NlGlobalChangeLogNetlogonState@@3W4_CHANGELOG_NETLOGON_STATE@@A, 2; _CHANGELOG_NETLOGON_STATE NlGlobalChangeLogNetlogonState
0x18004289e  mov     r14d, 1
0x1800428a4  jz      short loc_1800428BC
0x1800428a6  lea     rdx, aNlsitesgetismc_1; "NlSitesGetIsmConnect: Avoided during st"...
0x1800428ad  mov     ecx, 8000000h; unsigned int
0x1800428b2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800428b7  jmp     loc_180042C9C
0x1800428bc  lea     rcx, aIsmserv; "IsmServ"
0x1800428c3  call    ?NlWaitForService@@YAJPEAGKE@Z; NlWaitForService(ushort *,ulong,uchar)
0x1800428c8  test    eax, eax
0x1800428ca  jz      short loc_1800428D5
0x1800428cc  lea     rdx, aNlsitesgetismc_4; "NlSitesGetIsmConnect: ISM service not s"...
0x1800428d3  jmp     short loc_1800428AD
0x1800428d5  mov     dword ptr [rsp+58h+uBytes], esi
0x1800428d9  call    IsDsGetServersAndSitesForNetLogonPresent
0x1800428de  test    al, al
0x1800428e0  jz      loc_180042C83
0x1800428e6  xor     r8d, r8d
0x1800428e9  lea     rdx, [rsp+58h+uBytes]
0x1800428ee  lea     ecx, [r8+4]
0x1800428f2  call    cs:__imp_GetConfigurationName
0x1800428f8  mov     esi, eax
0x1800428fa  cmp     eax, 0C0000023h
0x1800428ff  jz      short loc_180042935
0x180042901  cmp     eax, 0C000007Ah
0x180042906  jz      loc_180042C88
0x18004290c  cmp     eax, 0C0000225h
0x180042911  jz      loc_180042C88
0x180042917  mov     r8d, 1A3h; unsigned int
0x18004291d  lea     rdx, aOnecoreDsNetap_18; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180042924  lea     rcx, aStatusStatusBu; "Status == STATUS_BUFFER_TOO_SMALL || St"...
0x18004292b  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180042930  jmp     loc_180042C88
0x180042935  mov     edx, dword ptr [rsp+58h+uBytes]; uBytes
0x180042939  xor     ecx, ecx; uFlags
0x18004293b  call    cs:__imp_LocalAlloc
0x180042941  xor     esi, esi
0x180042943  mov     rbp, rax
0x180042946  test    rax, rax
0x180042949  jz      loc_180042C9C
0x18004294f  call    IsDsGetServersAndSitesForNetLogonPresent
0x180042954  test    al, al
0x180042956  jnz     short loc_180042971
0x180042958  mov     r8d, 1B5h; unsigned int
0x18004295e  lea     rdx, aOnecoreDsNetap_18; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180042965  lea     rcx, aIsgetconfigura; "IsGetConfigurationNamePresent()"
0x18004296c  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180042971  mov     r8, rbp
0x180042974  lea     rdx, [rsp+58h+uBytes]
0x180042979  mov     ecx, 4
0x18004297e  call    cs:__imp_GetConfigurationName
0x180042984  test    eax, eax
0x180042986  jns     short loc_180042990
0x180042988  mov     r8d, eax
0x18004298b  jmp     loc_180042C8B
0x180042990  mov     edx, [rbp+34h]
0x180042993  xor     ecx, ecx; uFlags
0x180042995  lea     rdx, ds:52h[rdx*2]; uBytes
0x18004299d  call    cs:__imp_LocalAlloc
0x1800429a3  mov     [rsp+58h+arg_20], rax
0x1800429ab  mov     r15, rax
0x1800429ae  test    rax, rax
0x1800429b1  jz      loc_180042C9C
0x1800429b7  mov     edx, [rbp+34h]
0x1800429ba  lea     r8, aCnIpCnInterSit; "CN=IP,CN=Inter-Site Transports,CN=Sites"...
0x1800429c1  add     rdx, 29h ; ')'
0x1800429c5  mov     rcx, rax
0x1800429c8  call    cs:__imp__o_wcscpy_s
0x1800429ce  mov     edx, [rbp+34h]
0x1800429d1  lea     r8, [rbp+38h]
0x1800429d5  add     rdx, 29h ; ')'
0x1800429d9  mov     rcx, r15
0x1800429dc  call    cs:__imp__o_wcscat_s
0x1800429e2  mov     rdx, rbx
0x1800429e5  mov     rcx, r15
0x1800429e8  call    I_ISMGetConnectivity
0x1800429ed  test    eax, eax
0x1800429ef  jz      short loc_180042A00
0x1800429f1  mov     r8d, eax
0x1800429f4  lea     rdx, aNlsitesgetismc_0; "NlSitesGetIsmConnect: Cannot I_ISMGetCo"...
0x1800429fb  jmp     loc_180042C92
0x180042a00  mov     rax, [rbx]
0x180042a03  test    rax, rax
0x180042a06  jnz     short loc_180042A19
0x180042a08  lea     rdx, aNlsitesgetismc_3; "NlSitesGetIsmConnect: I_ISMGetConnectiv"...
0x180042a0f  mov     ecx, 100h
0x180042a14  jmp     loc_1800428B2
0x180042a19  mov     ecx, [rax]
0x180042a1b  test    rdi, rdi
0x180042a1e  jz      loc_180042ABF
0x180042a24  mov     edx, ecx
0x180042a26  mov     ecx, 40h ; '@'; uFlags
0x180042a2b  shl     rdx, 3; uBytes
0x180042a2f  call    cs:__imp_LocalAlloc
0x180042a35  xor     r12d, r12d
0x180042a38  mov     [rdi], rax
0x180042a3b  test    rax, rax
0x180042a3e  jz      loc_180042CA9
0x180042a44  mov     rax, [rbx]
0x180042a47  cmp     [rax], r12d
0x180042a4a  jbe     loc_180042B45
0x180042a50  mov     rax, [rax+8]
0x180042a54  mov     r12d, esi
0x180042a57  mov     rcx, [rax+r12*8]
0x180042a5b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042a5f  xor     edx, edx
0x180042a61  inc     rax
0x180042a64  cmp     [rcx+rax*2], dx
0x180042a68  jnz     short loc_180042A61
0x180042a6a  inc     eax
0x180042a6c  mov     ecx, 40h ; '@'; uFlags
0x180042a71  mov     edx, eax
0x180042a73  add     rdx, rdx; uBytes
0x180042a76  mov     dword ptr [rsp+58h+uBytes], eax
0x180042a7a  call    cs:__imp_LocalAlloc
0x180042a80  mov     rcx, [rdi]
0x180042a83  mov     [rcx+r12*8], rax
0x180042a87  mov     rax, [rdi]
0x180042a8a  mov     rcx, [rax+r12*8]
0x180042a8e  test    rcx, rcx
0x180042a91  jz      loc_180042CA6
0x180042a97  mov     rax, [rbx]
0x180042a9a  mov     edx, dword ptr [rsp+58h+uBytes]
0x180042a9e  mov     r8, [rax+8]
0x180042aa2  mov     r8, [r8+r12*8]
0x180042aa6  call    cs:__imp__o_wcscpy_s
0x180042aac  mov     rax, [rbx]
0x180042aaf  add     esi, r14d
0x180042ab2  mov     ecx, [rax]
0x180042ab4  cmp     esi, ecx
0x180042ab6  jb      short loc_180042A50
0x180042ab8  mov     r12, [rsp+58h+arg_0]
0x180042abd  xor     esi, esi
0x180042abf  test    ecx, ecx
0x180042ac1  jz      short loc_180042B42
0x180042ac3  mov     edi, esi
0x180042ac5  xor     r15d, r15d
0x180042ac8  mov     rcx, [rax+8]
0x180042acc  lea     rdx, aCn_0; "CN="
0x180042ad3  mov     esi, edi
0x180042ad5  mov     r8d, 3
0x180042adb  mov     rcx, [rcx+rsi*8]
0x180042adf  call    cs:__imp__o__wcsnicmp
0x180042ae5  test    eax, eax
0x180042ae7  jnz     short loc_180042B14
0x180042ae9  mov     rax, [rbx]
0x180042aec  mov     edx, 2Ch ; ','; Ch
0x180042af1  mov     rcx, [rax+8]
0x180042af5  add     qword ptr [rcx+rsi*8], 6
0x180042afa  mov     rax, [rbx]
0x180042afd  mov     rcx, [rax+8]
0x180042b01  mov     rcx, [rcx+rsi*8]; Str
0x180042b05  call    cs:__imp_wcschr
0x180042b0b  test    rax, rax
0x180042b0e  jz      short loc_180042B14
0x180042b10  mov     [rax], r15w
0x180042b14  mov     rax, [rbx]
0x180042b17  mov     rcx, r12
0x180042b1a  mov     rdx, [rax+8]
0x180042b1e  mov     rdx, [rdx+rsi*8]
0x180042b22  call    cs:__imp__o__wcsicmp
0x180042b28  test    eax, eax
0x180042b2a  jnz     short loc_180042B30
0x180042b2c  mov     [r13+0], edi
0x180042b30  mov     rax, [rbx]
0x180042b33  add     edi, r14d
0x180042b36  cmp     edi, [rax]
0x180042b38  jb      short loc_180042AC8
0x180042b3a  mov     r15, [rsp+58h+arg_20]
0x180042b42  xor     r12d, r12d
0x180042b45  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180042b4c  call    cs:__imp_RtlEnterCriticalSection
0x180042b52  mov     r8, [rbx]
0x180042b55  lea     rdx, aNlsitesgetismc_2; "NlSitesGetIsmConnect: Site link costs f"...
0x180042b5c  mov     esi, 8000000h
0x180042b61  mov     ecx, esi; unsigned int
0x180042b63  mov     r8d, [r8]
0x180042b66  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042b6b  mov     rax, [rbx]
0x180042b6e  mov     edi, r12d
0x180042b71  cmp     [rax], r12d
0x180042b74  jbe     short loc_180042BAA
0x180042b76  lea     r13, asc_1800B0C8C; "    "
0x180042b7d  test    edi, edi
0x180042b7f  lea     r8, asc_1800B3898; ","
0x180042b86  mov     r9d, edi
0x180042b89  lea     rdx, aHs5d; "%hs%5d"
0x180042b90  cmovz   r8, r13
0x180042b94  mov     ecx, esi; unsigned int
0x180042b96  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042b9b  mov     rax, [rbx]
0x180042b9e  add     edi, r14d
0x180042ba1  cmp     edi, [rax]
0x180042ba3  jb      short loc_180042B7D
0x180042ba5  mov     r13, [rsp+58h+arg_18]
0x180042baa  lea     rdx, asc_180096388; "\n"
0x180042bb1  mov     ecx, esi; unsigned int
0x180042bb3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042bb8  mov     rax, [rbx]
0x180042bbb  mov     edi, r12d
0x180042bbe  cmp     [rax], r12d
0x180042bc1  jbe     loc_180042C74
0x180042bc7  lea     r15, asc_1800B0C8C; "    "
0x180042bce  cmp     [r13+0], edi
0x180042bd2  lea     rax, asc_180099DA4; " "
0x180042bd9  lea     rdx, asc_1800B0CA8; "*"
0x180042be0  mov     ecx, esi; unsigned int
0x180042be2  cmovnz  rdx, rax; unsigned __int16 *
0x180042be6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042beb  mov     rax, [rbx]
0x180042bee  lea     rdx, a2dWs; "(%2d) %ws\n"
0x180042bf5  mov     ecx, edi
0x180042bf7  mov     r8d, edi
0x180042bfa  mov     r9, [rax+8]
0x180042bfe  mov     r9, [r9+rcx*8]
0x180042c02  mov     ecx, esi; unsigned int
0x180042c04  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042c09  mov     rdx, [rbx]
0x180042c0c  mov     eax, [rdx]
0x180042c0e  test    eax, eax
0x180042c10  jz      short loc_180042C50
0x180042c12  mov     r9, [rdx+10h]
0x180042c16  lea     r8, asc_1800B3898; ","
0x180042c1d  imul    eax, edi
0x180042c20  lea     rdx, aHs5d; "%hs%5d"
0x180042c27  add     eax, r12d
0x180042c2a  test    r12d, r12d
0x180042c2d  cmovz   r8, r15
0x180042c31  lea     rcx, [rax+rax*2]
0x180042c35  mov     r9d, [r9+rcx*4]
0x180042c39  mov     ecx, esi; unsigned int
0x180042c3b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042c40  mov     rdx, [rbx]
0x180042c43  add     r12d, r14d
0x180042c46  mov     eax, [rdx]
0x180042c48  cmp     r12d, eax
0x180042c4b  jb      short loc_180042C12
0x180042c4d  xor     r12d, r12d
0x180042c50  lea     rdx, asc_180096388; "\n"
0x180042c57  mov     ecx, esi; unsigned int
0x180042c59  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042c5e  mov     rax, [rbx]
0x180042c61  add     edi, r14d
0x180042c64  cmp     edi, [rax]
0x180042c66  jb      loc_180042BCE
0x180042c6c  mov     r15, [rsp+58h+arg_20]
0x180042c74  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180042c7b  call    cs:__imp_RtlLeaveCriticalSection
0x180042c81  jmp     short loc_180042CFB
0x180042c83  mov     esi, 0C00000BBh
0x180042c88  mov     r8d, esi
0x180042c8b  lea     rdx, aNlsitesgetismc; "NlSitesGetIsmConnect: Cannot GetConfigu"...
0x180042c92  mov     ecx, 100h; unsigned int
0x180042c97  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042c9c  xor     r12d, r12d
0x180042c9f  test    rdi, rdi
0x180042ca2  jz      short loc_180042CE3
0x180042ca4  jmp     short loc_180042CA9
0x180042ca6  xor     r12d, r12d
0x180042ca9  cmp     [rdi], r12
0x180042cac  jz      short loc_180042CE3
0x180042cae  mov     rax, [rbx]
0x180042cb1  mov     esi, r12d
0x180042cb4  cmp     [rax], r12d
0x180042cb7  jbe     short loc_180042CD7
0x180042cb9  mov     rax, [rdi]
0x180042cbc  mov     ecx, esi
0x180042cbe  mov     rcx, [rax+rcx*8]; hMem
0x180042cc2  test    rcx, rcx
0x180042cc5  jz      short loc_180042CCD
0x180042cc7  call    cs:__imp_LocalFree
0x180042ccd  mov     rax, [rbx]
0x180042cd0  add     esi, r14d
0x180042cd3  cmp     esi, [rax]
0x180042cd5  jb      short loc_180042CB9
  ... truncated ...
```
