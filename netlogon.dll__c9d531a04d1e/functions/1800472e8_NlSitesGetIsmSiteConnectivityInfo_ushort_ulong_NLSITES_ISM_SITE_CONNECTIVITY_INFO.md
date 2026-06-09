# NlSitesGetIsmSiteConnectivityInfo(ushort *,ulong,_NLSITES_ISM_SITE_CONNECTIVITY_INFO * *)

- ea: `0x1800472e8`
- end: `0x180047865`
- name: `?NlSitesGetIsmSiteConnectivityInfo@@YAHPEAGKPEAPEAU_NLSITES_ISM_SITE_CONNECTIVITY_INFO@@@Z`
- size: `1405`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, struct _NLSITES_ISM_SITE_CONNECTIVITY_INFO **)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001f5f0`
- `0x18004786c`

## callees

- `0x180003170`
- `0x18000b790`
- `0x1800109fc`
- `0x180018414`
- `0x18001843c`
- `0x18001847c`
- `0x18001852c`
- `0x18001858c`
- `0x180047070`
- `0x1800472e8`
- `0x18004a5bc`
- `0x18004c93c`
- `0x1800738d0`
- `0x180084724`
- `0x180084740`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047728`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047728`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800476d3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800476d3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004753d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004753d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180047529`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180047529`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800476fb`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800476fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004744e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800474e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800475c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047612`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004744e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800474e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800475c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047612`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047380`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800473a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800473b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047380`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800473a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800473b2`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x180047435`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x1800474a2`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x180047435`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x1800474a2`

## pseudocode

```c
__int64 __fastcall NlSitesGetIsmSiteConnectivityInfo(
        unsigned __int16 *a1,
        int a2,
        struct _NLSITES_ISM_SITE_CONNECTIVITY_INFO **a3)
{
  void *v3; // rdi
  RTL_SRWLOCK *v4; // rsi
  void *v5; // r15
  _QWORD *v6; // r12
  _DWORD *v7; // r14
  ScannerInfoNameMappings *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // r13d
  __int64 i; // rbx
  int ConfigurationName; // eax
  ScannerInfoNameMappings *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  ScannerInfoNameMappings *v18; // rcx
  __int64 v19; // rdx
  HLOCAL v20; // rax
  unsigned int v21; // eax
  unsigned __int64 v22; // rdx
  unsigned int v23; // eax
  unsigned int *v24; // rcx
  __int64 v25; // rdi
  int v26; // r15d
  unsigned int v27; // eax
  __int64 v28; // rax
  wchar_t *v29; // rcx
  int v30; // eax
  unsigned int *v31; // [rsp+30h] [rbp-20h] BYREF
  unsigned int *v32; // [rsp+38h] [rbp-18h]
  HLOCAL v33; // [rsp+40h] [rbp-10h]
  struct CNlIsmSiteNameIndexCache *v34; // [rsp+48h] [rbp-8h] BYREF
  SIZE_T uBytes; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  v4 = 0;
  LODWORD(uBytes) = 0;
  v5 = 0;
  v31 = 0;
  v6 = 0;
  v34 = 0;
  *a3 = 0;
  v7 = 0;
  if ( NlGlobalChangeLogNetlogonState != 2 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      goto LABEL_6;
    v10 = 18;
    goto LABEL_5;
  }
  ConfigurationName = NlWaitForService(L"IsmServ", a2);
  if ( ConfigurationName )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_6;
    v16 = 19;
    goto LABEL_17;
  }
  LODWORD(uBytes) = 0;
  if ( !(unsigned __int8)IsDsGetServersAndSitesForNetLogonPresent() )
  {
    ConfigurationName = -1073741637;
LABEL_79:
    v15 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_6;
    v16 = 20;
LABEL_17:
    v17 = (unsigned int)ConfigurationName;
LABEL_18:
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids, v17);
    goto LABEL_6;
  }
  ConfigurationName = GetConfigurationName(4, &uBytes);
  if ( ConfigurationName != -1073741789 )
    goto LABEL_79;
  v32 = (unsigned int *)LocalAlloc(0x40u, (unsigned int)uBytes);
  v3 = v32;
  if ( !v32 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_6;
    v19 = 21;
    goto LABEL_25;
  }
  ConfigurationName = GetConfigurationName(4, &uBytes);
  if ( ConfigurationName < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_6;
    v16 = 22;
    goto LABEL_17;
  }
  LODWORD(uBytes) = 2 * v32[13] + 82;
  v20 = LocalAlloc(0x40u, (unsigned int)uBytes);
  v33 = v20;
  v5 = v20;
  if ( !v20 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_6;
    v19 = 23;
    goto LABEL_25;
  }
  _o_wcscpy_s(v20, v32[13] + 41LL);
  _o_wcscat_s(v5, v32[13] + 41LL, v32 + 14);
  v21 = I_ISMGetConnectivity(v5, &v31);
  if ( v21 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids, v21, v21);
    goto LABEL_6;
  }
  if ( !v31 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_6;
    v10 = 25;
    goto LABEL_5;
  }
  v7 = LocalAlloc(0x40u, 0x20u);
  if ( !v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_6;
    v10 = 26;
LABEL_5:
    WPP_SF_(*((_QWORD *)v9 + 2), v10, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids);
LABEL_6:
    v11 = 0;
    goto LABEL_7;
  }
  v22 = 8LL * *v31;
  if ( v22 > 0xFFFFFFFF )
  {
    LODWORD(uBytes) = -1;
    v15 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_6;
    v16 = 27;
    v17 = 3221225621LL;
    goto LABEL_18;
  }
  LODWORD(uBytes) = 8 * *v31;
  v6 = LocalAlloc(0x40u, (unsigned int)v22);
  if ( !v6 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_6;
    v19 = 28;
LABEL_25:
    WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids, (unsigned int)uBytes);
    goto LABEL_6;
  }
  v23 = CNlIsmSiteNameIndexCache::StaticCreate(&v34);
  if ( v23 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids, v23);
    v4 = (RTL_SRWLOCK *)v34;
  }
  else
  {
    v24 = v31;
    v25 = 0;
    v4 = (RTL_SRWLOCK *)v34;
    v26 = -1;
    v27 = *v31;
    if ( !*v31 )
    {
LABEL_67:
      v3 = v32;
      v7[2] = v27;
      *(_QWORD *)v7 = v31;
      v31 = 0;
      *((_QWORD *)v7 + 2) = v6;
      v6 = 0;
      *((_QWORD *)v7 + 3) = v4;
      v4 = 0;
      v7[3] = v26;
      v5 = v33;
      *a3 = (struct _NLSITES_ISM_SITE_CONNECTIVITY_INFO *)v7;
      v11 = 1;
      v7 = 0;
      goto LABEL_7;
    }
    while ( 1 )
    {
      v28 = NetpAllocWStrFromWStr(*(void **)(*((_QWORD *)v24 + 1) + 8 * v25));
      v6[v25] = v28;
      if ( !v28 )
        break;
      if ( !(unsigned int)_o__wcsnicmp(*(_QWORD *)(*((_QWORD *)v31 + 1) + 8 * v25), L"CN=", 3) )
      {
        *(_QWORD *)(*((_QWORD *)v31 + 1) + 8 * v25) += 6LL;
        v29 = wcschr(*(const wchar_t **)(*((_QWORD *)v31 + 1) + 8 * v25), 0x2Cu);
        if ( v29 )
          *v29 = 0;
      }
      if ( v26 == -1 && !(unsigned int)_o__wcsicmp(a1) )
        v26 = v25;
      v30 = CNlIsmSiteNameIndexCache::Add(v4, v25, *(unsigned __int16 **)(*((_QWORD *)v31 + 1) + 8 * v25));
      if ( v30 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            (unsigned int)WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids,
            *(_QWORD *)(*((_QWORD *)v31 + 1) + 8 * v25),
            v30);
        goto LABEL_74;
      }
      v24 = v31;
      v25 = (unsigned int)(v25 + 1);
      v27 = *v31;
      if ( (unsigned int)v25 >= *v31 )
        goto LABEL_67;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids, 0);
LABEL_74:
    v3 = v32;
    v5 = v33;
  }
  v11 = 0;
LABEL_7:
  NlSitesFreeIsmSiteConnectivityInfo(v7);
  if ( v6 )
  {
    for ( i = 0; (unsigned int)i < *v31; i = (unsigned int)(i + 1) )
      LocalFree((HLOCAL)v6[i]);
  }
  if ( v4 )
    NLRefcountableObject::ReleaseReference((NLRefcountableObject *)v4);
  I_ISMFree(v31);
  LocalFree(v5);
  LocalFree(v3);
  return v11;
}

```

## disassembly

```asm
0x1800472e8  mov     [rsp-38h+arg_8], rbx
0x1800472ed  mov     [rsp-38h+arg_0], rcx
0x1800472f2  push    rbp
0x1800472f3  push    rsi
0x1800472f4  push    rdi
0x1800472f5  push    r12
0x1800472f7  push    r13
0x1800472f9  push    r14
0x1800472fb  push    r15
0x1800472fd  mov     rbp, rsp
0x180047300  sub     rsp, 50h
0x180047304  xor     edi, edi
0x180047306  mov     [rbp+arg_10], 0
0x18004730d  xor     esi, esi
0x18004730f  mov     dword ptr [rbp+uBytes], 0
0x180047316  xor     r15d, r15d
0x180047319  mov     [rbp+var_20], rdi
0x18004731d  xor     r12d, r12d
0x180047320  mov     [rbp+var_8], rsi
0x180047324  lea     ebx, [rdi+2]
0x180047327  mov     [r8], rsi
0x18004732a  xor     r14d, r14d
0x18004732d  mov     r13, r8
0x180047330  cmp     cs:?NlGlobalChangeLogNetlogonState@@3W4_CHANGELOG_NETLOGON_STATE@@A, ebx; _CHANGELOG_NETLOGON_STATE NlGlobalChangeLogNetlogonState
0x180047336  jz      loc_1800473D3
0x18004733c  mov     rcx, cs:WPP_GLOBAL_Control
0x180047343  test    byte ptr [rcx+1Ch], 20h
0x180047347  jz      short loc_180047362
0x180047349  cmp     byte ptr [rcx+19h], 4
0x18004734d  jb      short loc_180047362
0x18004734f  lea     edx, [rdi+12h]
0x180047352  mov     rcx, [rcx+10h]
0x180047356  lea     r8, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids
0x18004735d  call    WPP_SF_
0x180047362  mov     r13d, esi
0x180047365  mov     rcx, r14; hMem
0x180047368  call    ?NlSitesFreeIsmSiteConnectivityInfo@@YAXPEAU_NLSITES_ISM_SITE_CONNECTIVITY_INFO@@@Z; NlSitesFreeIsmSiteConnectivityInfo(_NLSITES_ISM_SITE_CONNECTIVITY_INFO *)
0x18004736d  test    r12, r12
0x180047370  jz      short loc_180047390
0x180047372  mov     rax, [rbp+var_20]
0x180047376  xor     ebx, ebx
0x180047378  cmp     [rax], ebx
0x18004737a  jbe     short loc_180047390
0x18004737c  mov     rcx, [r12+rbx*8]; hMem
0x180047380  call    cs:__imp_LocalFree
0x180047386  mov     rax, [rbp+var_20]
0x18004738a  inc     ebx
0x18004738c  cmp     ebx, [rax]
0x18004738e  jb      short loc_18004737C
0x180047390  test    rsi, rsi
0x180047393  jz      short loc_18004739D
0x180047395  mov     rcx, rsi; this
0x180047398  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x18004739d  mov     rcx, [rbp+var_20]
0x1800473a1  call    I_ISMFree
0x1800473a6  mov     rcx, r15; hMem
0x1800473a9  call    cs:__imp_LocalFree
0x1800473af  mov     rcx, rdi; hMem
0x1800473b2  call    cs:__imp_LocalFree
0x1800473b8  mov     rbx, [rsp+50h+arg_8]
0x1800473c0  mov     eax, r13d
0x1800473c3  add     rsp, 50h
0x1800473c7  pop     r15
0x1800473c9  pop     r14
0x1800473cb  pop     r13
0x1800473cd  pop     r12
0x1800473cf  pop     rdi
0x1800473d0  pop     rsi
0x1800473d1  pop     rbp
0x1800473d2  retn
0x1800473d3  lea     rcx, aIsmserv; "IsmServ"
0x1800473da  call    ?NlWaitForService@@YAJPEAGKE@Z; NlWaitForService(ushort *,ulong,uchar)
0x1800473df  test    eax, eax
0x1800473e1  jz      short loc_18004741A
0x1800473e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800473ea  test    byte ptr [rcx+1Ch], 20h
0x1800473ee  jz      loc_180047362
0x1800473f4  cmp     [rcx+19h], bl
0x1800473f7  jb      loc_180047362
0x1800473fd  mov     edx, 13h
0x180047402  mov     r9d, eax
0x180047405  mov     rcx, [rcx+10h]
0x180047409  lea     r8, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids
0x180047410  call    WPP_SF_d
0x180047415  jmp     loc_180047362
0x18004741a  mov     dword ptr [rbp+uBytes], esi
0x18004741d  call    IsDsGetServersAndSitesForNetLogonPresent
0x180047422  test    al, al
0x180047424  jz      loc_18004783C
0x18004742a  xor     r8d, r8d
0x18004742d  lea     rdx, [rbp+uBytes]
0x180047431  lea     ecx, [r8+4]
0x180047435  call    cs:__imp_GetConfigurationName
0x18004743b  cmp     eax, 0C0000023h
0x180047440  jnz     loc_180047841
0x180047446  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180047449  mov     ecx, 40h ; '@'; uFlags
0x18004744e  call    cs:__imp_LocalAlloc
0x180047454  mov     [rbp+var_18], rax
0x180047458  mov     rdi, rax
0x18004745b  test    rax, rax
0x18004745e  jnz     short loc_180047496
0x180047460  mov     rcx, cs:WPP_GLOBAL_Control
0x180047467  test    byte ptr [rcx+1Ch], 20h
0x18004746b  jz      loc_180047362
0x180047471  cmp     [rcx+19h], bl
0x180047474  jb      loc_180047362
0x18004747a  lea     edx, [rax+15h]
0x18004747d  mov     r9d, dword ptr [rbp+uBytes]
0x180047481  lea     r8, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids
0x180047488  mov     rcx, [rcx+10h]
0x18004748c  call    WPP_SF_d
0x180047491  jmp     loc_180047362
0x180047496  mov     r8, rdi
0x180047499  lea     rdx, [rbp+uBytes]
0x18004749d  mov     ecx, 4
0x1800474a2  call    cs:__imp_GetConfigurationName
0x1800474a8  test    eax, eax
0x1800474aa  jns     short loc_1800474D0
0x1800474ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800474b3  test    byte ptr [rcx+1Ch], 20h
0x1800474b7  jz      loc_180047362
0x1800474bd  cmp     [rcx+19h], bl
0x1800474c0  jb      loc_180047362
0x1800474c6  mov     edx, 16h
0x1800474cb  jmp     loc_180047402
0x1800474d0  mov     eax, [rdi+34h]
0x1800474d3  mov     ecx, 40h ; '@'; uFlags
0x1800474d8  lea     eax, ds:52h[rax*2]
0x1800474df  mov     edx, eax; uBytes
0x1800474e1  mov     dword ptr [rbp+uBytes], eax
0x1800474e4  call    cs:__imp_LocalAlloc
0x1800474ea  mov     [rbp+var_10], rax
0x1800474ee  mov     r15, rax
0x1800474f1  test    rax, rax
0x1800474f4  jnz     short loc_180047518
0x1800474f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800474fd  test    byte ptr [rcx+1Ch], 20h
0x180047501  jz      loc_180047362
0x180047507  cmp     [rcx+19h], bl
0x18004750a  jb      loc_180047362
0x180047510  lea     edx, [rax+17h]
0x180047513  jmp     loc_18004747D
0x180047518  mov     edx, [rdi+34h]
0x18004751b  lea     r8, aCnIpCnInterSit; "CN=IP,CN=Inter-Site Transports,CN=Sites"...
0x180047522  add     rdx, 29h ; ')'
0x180047526  mov     rcx, r15
0x180047529  call    cs:__imp__o_wcscpy_s
0x18004752f  mov     edx, [rdi+34h]
0x180047532  lea     r8, [rdi+38h]
0x180047536  add     rdx, 29h ; ')'
0x18004753a  mov     rcx, r15
0x18004753d  call    cs:__imp__o_wcscat_s
0x180047543  lea     rdx, [rbp+var_20]
0x180047547  mov     rcx, r15
0x18004754a  call    I_ISMGetConnectivity
0x18004754f  test    eax, eax
0x180047551  jz      short loc_18004758E
0x180047553  mov     rcx, cs:WPP_GLOBAL_Control
0x18004755a  test    byte ptr [rcx+1Ch], 20h
0x18004755e  jz      loc_180047362
0x180047564  cmp     [rcx+19h], bl
0x180047567  jb      loc_180047362
0x18004756d  mov     rcx, [rcx+10h]
0x180047571  lea     r8, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids
0x180047578  mov     edx, 18h
0x18004757d  mov     [rsp+50h+var_30], eax
0x180047581  mov     r9d, eax
0x180047584  call    WPP_SF_Dd
0x180047589  jmp     loc_180047362
0x18004758e  cmp     [rbp+var_20], rsi
0x180047592  jnz     short loc_1800475B8
0x180047594  mov     rcx, cs:WPP_GLOBAL_Control
0x18004759b  test    byte ptr [rcx+1Ch], 20h
0x18004759f  jz      loc_180047362
0x1800475a5  cmp     [rcx+19h], bl
0x1800475a8  jb      loc_180047362
0x1800475ae  mov     edx, 19h
0x1800475b3  jmp     loc_180047352
0x1800475b8  mov     edx, 20h ; ' '; uBytes
0x1800475bd  lea     ecx, [rdx+20h]; uFlags
0x1800475c0  call    cs:__imp_LocalAlloc
0x1800475c6  mov     r14, rax
0x1800475c9  test    rax, rax
0x1800475cc  jnz     short loc_1800475F0
0x1800475ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800475d5  test    byte ptr [rcx+1Ch], 20h
0x1800475d9  jz      loc_180047362
0x1800475df  cmp     [rcx+19h], bl
0x1800475e2  jb      loc_180047362
0x1800475e8  lea     edx, [rax+1Ah]
0x1800475eb  jmp     loc_180047352
0x1800475f0  mov     rax, [rbp+var_20]
0x1800475f4  mov     edx, [rax]
0x1800475f6  mov     eax, 0FFFFFFFFh
0x1800475fb  shl     rdx, 3
0x1800475ff  cmp     rdx, rax
0x180047602  ja      loc_18004780F
0x180047608  mov     edx, edx; uBytes
0x18004760a  mov     ecx, 40h ; '@'; uFlags
0x18004760f  mov     dword ptr [rbp+uBytes], edx
0x180047612  call    cs:__imp_LocalAlloc
0x180047618  mov     r12, rax
0x18004761b  test    rax, rax
0x18004761e  jnz     short loc_180047642
0x180047620  mov     rcx, cs:WPP_GLOBAL_Control
0x180047627  test    byte ptr [rcx+1Ch], 20h
0x18004762b  jz      loc_180047362
0x180047631  cmp     [rcx+19h], bl
0x180047634  jb      loc_180047362
0x18004763a  lea     edx, [rax+1Ch]
0x18004763d  jmp     loc_18004747D
0x180047642  lea     rcx, [rbp+var_8]; struct CNlIsmSiteNameIndexCache **
0x180047646  call    ?StaticCreate@CNlIsmSiteNameIndexCache@@SAKPEAPEAV1@@Z; CNlIsmSiteNameIndexCache::StaticCreate(CNlIsmSiteNameIndexCache * *)
0x18004764b  test    eax, eax
0x18004764d  jz      short loc_180047686
0x18004764f  mov     rcx, cs:WPP_GLOBAL_Control
0x180047656  test    byte ptr [rcx+1Ch], 20h
0x18004765a  jz      short loc_180047679
0x18004765c  cmp     [rcx+19h], bl
0x18004765f  jb      short loc_180047679
0x180047661  mov     rcx, [rcx+10h]
0x180047665  lea     r8, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids
0x18004766c  mov     edx, 1Dh
0x180047671  mov     r9d, eax
0x180047674  call    WPP_SF_d
0x180047679  mov     rsi, [rbp+var_8]
0x18004767d  mov     r13d, [rbp+arg_10]
0x180047681  jmp     loc_180047365
0x180047686  mov     rcx, [rbp+var_20]
0x18004768a  xor     edi, edi
0x18004768c  mov     rsi, [rbp+var_8]
0x180047690  mov     r15d, 0FFFFFFFFh
0x180047696  mov     eax, [rcx]
0x180047698  test    eax, eax
0x18004769a  jz      loc_180047761
0x1800476a0  mov     rcx, [rcx+8]
0x1800476a4  mov     rcx, [rcx+rdi*8]; Src
0x1800476a8  call    NetpAllocWStrFromWStr
0x1800476ad  mov     [r12+rdi*8], rax
0x1800476b1  test    rax, rax
0x1800476b4  jz      loc_1800477D8
0x1800476ba  mov     rax, [rbp+var_20]
0x1800476be  lea     rdx, aCn_0; "CN="
0x1800476c5  mov     r8d, 3
0x1800476cb  mov     rcx, [rax+8]
0x1800476cf  mov     rcx, [rcx+rdi*8]
0x1800476d3  call    cs:__imp__o__wcsnicmp
0x1800476d9  test    eax, eax
0x1800476db  jnz     short loc_18004770E
0x1800476dd  mov     rax, [rbp+var_20]
0x1800476e1  mov     edx, 2Ch ; ','; Ch
0x1800476e6  mov     rcx, [rax+8]
0x1800476ea  add     qword ptr [rcx+rdi*8], 6
0x1800476ef  mov     rax, [rbp+var_20]
0x1800476f3  mov     rcx, [rax+8]
0x1800476f7  mov     rcx, [rcx+rdi*8]; Str
0x1800476fb  call    cs:__imp_wcschr
0x180047701  mov     rcx, rax
0x180047704  test    rax, rax
0x180047707  jz      short loc_18004770E
0x180047709  xor     eax, eax
0x18004770b  mov     [rcx], ax
0x18004770e  mov     eax, 0FFFFFFFFh
0x180047713  cmp     r15d, eax
0x180047716  jnz     short loc_180047734
0x180047718  mov     rax, [rbp+var_20]
0x18004771c  mov     rcx, [rbp+arg_0]
0x180047720  mov     rdx, [rax+8]
0x180047724  mov     rdx, [rdx+rdi*8]
0x180047728  call    cs:__imp__o__wcsicmp
0x18004772e  test    eax, eax
0x180047730  cmovz   r15d, edi
0x180047734  mov     rax, [rbp+var_20]
0x180047738  mov     edx, edi; unsigned int
0x18004773a  mov     rcx, rsi; this
0x18004773d  mov     r8, [rax+8]
0x180047741  mov     r8, [r8+rdi*8]; unsigned __int16 *
0x180047745  call    ?Add@CNlIsmSiteNameIndexCache@@QEAAKKPEAG@Z; CNlIsmSiteNameIndexCache::Add(ulong,ushort *)
0x18004774a  mov     r8d, eax
0x18004774d  test    eax, eax
0x18004774f  jnz     short loc_18004779E
0x180047751  mov     rcx, [rbp+var_20]
0x180047755  inc     edi
0x180047757  mov     eax, [rcx]
0x180047759  cmp     edi, eax
0x18004775b  jb      loc_1800476A0
0x180047761  mov     rdi, [rbp+var_18]
0x180047765  mov     [r14+8], eax
0x180047769  mov     rax, [rbp+var_20]
0x18004776d  mov     [r14], rax
0x180047770  mov     [rbp+var_20], 0
0x180047778  mov     [r14+10h], r12
0x18004777c  xor     r12d, r12d
0x18004777f  mov     [r14+18h], rsi
0x180047783  xor     esi, esi
0x180047785  mov     [r14+0Ch], r15d
0x180047789  mov     r15, [rbp+var_10]
0x18004778d  mov     [r13+0], r14
0x180047791  lea     r13d, [r12+1]
  ... truncated ...
```
