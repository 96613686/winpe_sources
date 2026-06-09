# NlSitesGetIsmSiteConnectivityInfo(ushort *,ulong,_NLSITES_ISM_SITE_CONNECTIVITY_INFO * *)

- ea: `0x18004a450`
- end: `0x18004aa22`
- name: `?NlSitesGetIsmSiteConnectivityInfo@@YAHPEAGKPEAPEAU_NLSITES_ISM_SITE_CONNECTIVITY_INFO@@@Z`
- size: `1490`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, struct _NLSITES_ISM_SITE_CONNECTIVITY_INFO **)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180020480`
- `0x18004aa28`

## callees

- `0x180003250`
- `0x18000b790`
- `0x1800110ac`
- `0x180018f38`
- `0x180018f68`
- `0x180018fac`
- `0x18001906c`
- `0x1800190d4`
- `0x18004a1b0`
- `0x18004a450`
- `0x18004d75c`
- `0x18004fe48`
- `0x180078fd8`
- `0x18008a854`
- `0x18008a878`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004a8df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004a8df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004a87e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004a87e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004a6d6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004a6d6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004a6bc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004a6bc`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004a8ac`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004a8ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a5cf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a671`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a75f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a7b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a5cf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a671`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a75f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a7b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a4e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a517`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a526`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a4e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a517`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a526`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x18004a5b0`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x18004a629`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x18004a5b0`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationName` at `0x18004a629`

## pseudocode

```c
__int64 __fastcall NlSitesGetIsmSiteConnectivityInfo(
        unsigned __int16 *a1,
        int a2,
        struct _NLSITES_ISM_SITE_CONNECTIVITY_INFO **a3)
{
  void *v3; // rdi
  CNlIsmSiteNameIndexCache *v4; // rsi
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
  unsigned int v30; // eax
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
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids, v17);
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
  _o_wcscpy_s(v20, v32[13] + 41LL, L"CN=IP,CN=Inter-Site Transports,CN=Sites,");
  _o_wcscat_s(v5, v32[13] + 41LL, v32 + 14);
  v21 = I_ISMGetConnectivity(v5, &v31);
  if ( v21 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids, v21, v21);
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
    WPP_SF_(*((_QWORD *)v9 + 2), v10, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids);
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
    WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids, (unsigned int)uBytes);
    goto LABEL_6;
  }
  v23 = CNlIsmSiteNameIndexCache::StaticCreate(&v34);
  if ( v23 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids, v23);
    v4 = v34;
  }
  else
  {
    v24 = v31;
    v25 = 0;
    v4 = v34;
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
      if ( v26 == -1 && !(unsigned int)_o__wcsicmp(a1, *(_QWORD *)(*((_QWORD *)v31 + 1) + 8 * v25)) )
        v26 = v25;
      v30 = CNlIsmSiteNameIndexCache::Add(v4, v25, *(unsigned __int16 **)(*((_QWORD *)v31 + 1) + 8 * v25));
      if ( v30 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            (unsigned int)WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids,
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
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids, 0);
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
    NLRefcountableObject::ReleaseReference(v4);
  I_ISMFree(v31);
  LocalFree(v5);
  LocalFree(v3);
  return v11;
}

```

## disassembly

```asm
0x18004a450  mov     [rsp-38h+arg_8], rbx
0x18004a455  mov     [rsp-38h+arg_0], rcx
0x18004a45a  push    rbp
0x18004a45b  push    rsi
0x18004a45c  push    rdi
0x18004a45d  push    r12
0x18004a45f  push    r13
0x18004a461  push    r14
0x18004a463  push    r15
0x18004a465  mov     rbp, rsp
0x18004a468  sub     rsp, 50h
0x18004a46c  xor     edi, edi
0x18004a46e  mov     [rbp+arg_10], 0
0x18004a475  xor     esi, esi
0x18004a477  mov     dword ptr [rbp+uBytes], 0
0x18004a47e  xor     r15d, r15d
0x18004a481  mov     [rbp+var_20], rdi
0x18004a485  xor     r12d, r12d
0x18004a488  mov     [rbp+var_8], rsi
0x18004a48c  lea     ebx, [rdi+2]
0x18004a48f  mov     [r8], rsi
0x18004a492  xor     r14d, r14d
0x18004a495  mov     r13, r8
0x18004a498  cmp     cs:?NlGlobalChangeLogNetlogonState@@3W4_CHANGELOG_NETLOGON_STATE@@A, ebx; _CHANGELOG_NETLOGON_STATE NlGlobalChangeLogNetlogonState
0x18004a49e  jz      loc_18004A54E
0x18004a4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a4ab  test    byte ptr [rcx+1Ch], 20h
0x18004a4af  jz      short loc_18004A4CA
0x18004a4b1  cmp     byte ptr [rcx+19h], 4
0x18004a4b5  jb      short loc_18004A4CA
0x18004a4b7  lea     edx, [rdi+12h]
0x18004a4ba  mov     rcx, [rcx+10h]
0x18004a4be  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x18004a4c5  call    WPP_SF_
0x18004a4ca  mov     r13d, esi
0x18004a4cd  mov     rcx, r14; hMem
0x18004a4d0  call    ?NlSitesFreeIsmSiteConnectivityInfo@@YAXPEAU_NLSITES_ISM_SITE_CONNECTIVITY_INFO@@@Z; NlSitesFreeIsmSiteConnectivityInfo(_NLSITES_ISM_SITE_CONNECTIVITY_INFO *)
0x18004a4d5  test    r12, r12
0x18004a4d8  jz      short loc_18004A4FE
0x18004a4da  mov     rax, [rbp+var_20]
0x18004a4de  xor     ebx, ebx
0x18004a4e0  cmp     [rax], ebx
0x18004a4e2  jbe     short loc_18004A4FE
0x18004a4e4  mov     rcx, [r12+rbx*8]; hMem
0x18004a4e8  call    cs:__imp_LocalFree
0x18004a4ef  nop     dword ptr [rax+rax+00h]
0x18004a4f4  mov     rax, [rbp+var_20]
0x18004a4f8  inc     ebx
0x18004a4fa  cmp     ebx, [rax]
0x18004a4fc  jb      short loc_18004A4E4
0x18004a4fe  test    rsi, rsi
0x18004a501  jz      short loc_18004A50B
0x18004a503  mov     rcx, rsi; this
0x18004a506  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x18004a50b  mov     rcx, [rbp+var_20]
0x18004a50f  call    I_ISMFree
0x18004a514  mov     rcx, r15; hMem
0x18004a517  call    cs:__imp_LocalFree
0x18004a51e  nop     dword ptr [rax+rax+00h]
0x18004a523  mov     rcx, rdi; hMem
0x18004a526  call    cs:__imp_LocalFree
0x18004a52d  nop     dword ptr [rax+rax+00h]
0x18004a532  mov     rbx, [rsp+50h+arg_8]
0x18004a53a  mov     eax, r13d
0x18004a53d  add     rsp, 50h
0x18004a541  pop     r15
0x18004a543  pop     r14
0x18004a545  pop     r13
0x18004a547  pop     r12
0x18004a549  pop     rdi
0x18004a54a  pop     rsi
0x18004a54b  pop     rbp
0x18004a54c  retn
0x18004a54e  lea     rcx, aIsmserv; "IsmServ"
0x18004a555  call    ?NlWaitForService@@YAJPEAGKE@Z; NlWaitForService(ushort *,ulong,uchar)
0x18004a55a  test    eax, eax
0x18004a55c  jz      short loc_18004A595
0x18004a55e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a565  test    byte ptr [rcx+1Ch], 20h
0x18004a569  jz      loc_18004A4CA
0x18004a56f  cmp     [rcx+19h], bl
0x18004a572  jb      loc_18004A4CA
0x18004a578  mov     edx, 13h
0x18004a57d  mov     r9d, eax
0x18004a580  mov     rcx, [rcx+10h]
0x18004a584  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x18004a58b  call    WPP_SF_d
0x18004a590  jmp     loc_18004A4CA
0x18004a595  mov     dword ptr [rbp+uBytes], esi
0x18004a598  call    IsDsGetServersAndSitesForNetLogonPresent
0x18004a59d  test    al, al
0x18004a59f  jz      loc_18004A9F9
0x18004a5a5  xor     r8d, r8d
0x18004a5a8  lea     rdx, [rbp+uBytes]
0x18004a5ac  lea     ecx, [r8+4]
0x18004a5b0  call    cs:__imp_GetConfigurationName
0x18004a5b7  nop     dword ptr [rax+rax+00h]
0x18004a5bc  cmp     eax, 0C0000023h
0x18004a5c1  jnz     loc_18004A9FE
0x18004a5c7  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x18004a5ca  mov     ecx, 40h ; '@'; uFlags
0x18004a5cf  call    cs:__imp_LocalAlloc
0x18004a5d6  nop     dword ptr [rax+rax+00h]
0x18004a5db  mov     [rbp+var_18], rax
0x18004a5df  mov     rdi, rax
0x18004a5e2  test    rax, rax
0x18004a5e5  jnz     short loc_18004A61D
0x18004a5e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a5ee  test    byte ptr [rcx+1Ch], 20h
0x18004a5f2  jz      loc_18004A4CA
0x18004a5f8  cmp     [rcx+19h], bl
0x18004a5fb  jb      loc_18004A4CA
0x18004a601  lea     edx, [rax+15h]
0x18004a604  mov     r9d, dword ptr [rbp+uBytes]
0x18004a608  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x18004a60f  mov     rcx, [rcx+10h]
0x18004a613  call    WPP_SF_d
0x18004a618  jmp     loc_18004A4CA
0x18004a61d  mov     r8, rdi
0x18004a620  lea     rdx, [rbp+uBytes]
0x18004a624  mov     ecx, 4
0x18004a629  call    cs:__imp_GetConfigurationName
0x18004a630  nop     dword ptr [rax+rax+00h]
0x18004a635  test    eax, eax
0x18004a637  jns     short loc_18004A65D
0x18004a639  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a640  test    byte ptr [rcx+1Ch], 20h
0x18004a644  jz      loc_18004A4CA
0x18004a64a  cmp     [rcx+19h], bl
0x18004a64d  jb      loc_18004A4CA
0x18004a653  mov     edx, 16h
0x18004a658  jmp     loc_18004A57D
0x18004a65d  mov     eax, [rdi+34h]
0x18004a660  mov     ecx, 40h ; '@'; uFlags
0x18004a665  lea     eax, ds:52h[rax*2]
0x18004a66c  mov     edx, eax; uBytes
0x18004a66e  mov     dword ptr [rbp+uBytes], eax
0x18004a671  call    cs:__imp_LocalAlloc
0x18004a678  nop     dword ptr [rax+rax+00h]
0x18004a67d  mov     [rbp+var_10], rax
0x18004a681  mov     r15, rax
0x18004a684  test    rax, rax
0x18004a687  jnz     short loc_18004A6AB
0x18004a689  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a690  test    byte ptr [rcx+1Ch], 20h
0x18004a694  jz      loc_18004A4CA
0x18004a69a  cmp     [rcx+19h], bl
0x18004a69d  jb      loc_18004A4CA
0x18004a6a3  lea     edx, [rax+17h]
0x18004a6a6  jmp     loc_18004A604
0x18004a6ab  mov     edx, [rdi+34h]
0x18004a6ae  lea     r8, aCnIpCnInterSit; "CN=IP,CN=Inter-Site Transports,CN=Sites"...
0x18004a6b5  add     rdx, 29h ; ')'
0x18004a6b9  mov     rcx, r15
0x18004a6bc  call    cs:__imp__o_wcscpy_s
0x18004a6c3  nop     dword ptr [rax+rax+00h]
0x18004a6c8  mov     edx, [rdi+34h]
0x18004a6cb  lea     r8, [rdi+38h]
0x18004a6cf  add     rdx, 29h ; ')'
0x18004a6d3  mov     rcx, r15
0x18004a6d6  call    cs:__imp__o_wcscat_s
0x18004a6dd  nop     dword ptr [rax+rax+00h]
0x18004a6e2  lea     rdx, [rbp+var_20]
0x18004a6e6  mov     rcx, r15
0x18004a6e9  call    I_ISMGetConnectivity
0x18004a6ee  test    eax, eax
0x18004a6f0  jz      short loc_18004A72D
0x18004a6f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a6f9  test    byte ptr [rcx+1Ch], 20h
0x18004a6fd  jz      loc_18004A4CA
0x18004a703  cmp     [rcx+19h], bl
0x18004a706  jb      loc_18004A4CA
0x18004a70c  mov     rcx, [rcx+10h]
0x18004a710  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x18004a717  mov     edx, 18h
0x18004a71c  mov     [rsp+50h+var_30], eax
0x18004a720  mov     r9d, eax
0x18004a723  call    WPP_SF_Dd
0x18004a728  jmp     loc_18004A4CA
0x18004a72d  cmp     [rbp+var_20], rsi
0x18004a731  jnz     short loc_18004A757
0x18004a733  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a73a  test    byte ptr [rcx+1Ch], 20h
0x18004a73e  jz      loc_18004A4CA
0x18004a744  cmp     [rcx+19h], bl
0x18004a747  jb      loc_18004A4CA
0x18004a74d  mov     edx, 19h
0x18004a752  jmp     loc_18004A4BA
0x18004a757  mov     edx, 20h ; ' '; uBytes
0x18004a75c  lea     ecx, [rdx+20h]; uFlags
0x18004a75f  call    cs:__imp_LocalAlloc
0x18004a766  nop     dword ptr [rax+rax+00h]
0x18004a76b  mov     r14, rax
0x18004a76e  test    rax, rax
0x18004a771  jnz     short loc_18004A795
0x18004a773  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a77a  test    byte ptr [rcx+1Ch], 20h
0x18004a77e  jz      loc_18004A4CA
0x18004a784  cmp     [rcx+19h], bl
0x18004a787  jb      loc_18004A4CA
0x18004a78d  lea     edx, [rax+1Ah]
0x18004a790  jmp     loc_18004A4BA
0x18004a795  mov     rax, [rbp+var_20]
0x18004a799  mov     edx, [rax]
0x18004a79b  mov     eax, 0FFFFFFFFh
0x18004a7a0  shl     rdx, 3
0x18004a7a4  cmp     rdx, rax
0x18004a7a7  ja      loc_18004A9CC
0x18004a7ad  mov     edx, edx; uBytes
0x18004a7af  mov     ecx, 40h ; '@'; uFlags
0x18004a7b4  mov     dword ptr [rbp+uBytes], edx
0x18004a7b7  call    cs:__imp_LocalAlloc
0x18004a7be  nop     dword ptr [rax+rax+00h]
0x18004a7c3  mov     r12, rax
0x18004a7c6  test    rax, rax
0x18004a7c9  jnz     short loc_18004A7ED
0x18004a7cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a7d2  test    byte ptr [rcx+1Ch], 20h
0x18004a7d6  jz      loc_18004A4CA
0x18004a7dc  cmp     [rcx+19h], bl
0x18004a7df  jb      loc_18004A4CA
0x18004a7e5  lea     edx, [rax+1Ch]
0x18004a7e8  jmp     loc_18004A604
0x18004a7ed  lea     rcx, [rbp+var_8]; struct CNlIsmSiteNameIndexCache **
0x18004a7f1  call    ?StaticCreate@CNlIsmSiteNameIndexCache@@SAKPEAPEAV1@@Z; CNlIsmSiteNameIndexCache::StaticCreate(CNlIsmSiteNameIndexCache * *)
0x18004a7f6  test    eax, eax
0x18004a7f8  jz      short loc_18004A831
0x18004a7fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a801  test    byte ptr [rcx+1Ch], 20h
0x18004a805  jz      short loc_18004A824
0x18004a807  cmp     [rcx+19h], bl
0x18004a80a  jb      short loc_18004A824
0x18004a80c  mov     rcx, [rcx+10h]
0x18004a810  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x18004a817  mov     edx, 1Dh
0x18004a81c  mov     r9d, eax
0x18004a81f  call    WPP_SF_d
0x18004a824  mov     rsi, [rbp+var_8]
0x18004a828  mov     r13d, [rbp+arg_10]
0x18004a82c  jmp     loc_18004A4CD
0x18004a831  mov     rcx, [rbp+var_20]
0x18004a835  xor     edi, edi
0x18004a837  mov     rsi, [rbp+var_8]
0x18004a83b  mov     r15d, 0FFFFFFFFh
0x18004a841  mov     eax, [rcx]
0x18004a843  test    eax, eax
0x18004a845  jz      loc_18004A91E
0x18004a84b  mov     rcx, [rcx+8]
0x18004a84f  mov     rcx, [rcx+rdi*8]; Src
0x18004a853  call    NetpAllocWStrFromWStr
0x18004a858  mov     [r12+rdi*8], rax
0x18004a85c  test    rax, rax
0x18004a85f  jz      loc_18004A995
0x18004a865  mov     rax, [rbp+var_20]
0x18004a869  lea     rdx, aCn_0; "CN="
0x18004a870  mov     r8d, 3
0x18004a876  mov     rcx, [rax+8]
0x18004a87a  mov     rcx, [rcx+rdi*8]
0x18004a87e  call    cs:__imp__o__wcsnicmp
0x18004a885  nop     dword ptr [rax+rax+00h]
0x18004a88a  test    eax, eax
0x18004a88c  jnz     short loc_18004A8C5
0x18004a88e  mov     rax, [rbp+var_20]
0x18004a892  mov     edx, 2Ch ; ','; Ch
0x18004a897  mov     rcx, [rax+8]
0x18004a89b  add     qword ptr [rcx+rdi*8], 6
0x18004a8a0  mov     rax, [rbp+var_20]
0x18004a8a4  mov     rcx, [rax+8]
0x18004a8a8  mov     rcx, [rcx+rdi*8]; Str
0x18004a8ac  call    cs:__imp_wcschr
0x18004a8b3  nop     dword ptr [rax+rax+00h]
0x18004a8b8  mov     rcx, rax
0x18004a8bb  test    rax, rax
0x18004a8be  jz      short loc_18004A8C5
0x18004a8c0  xor     eax, eax
0x18004a8c2  mov     [rcx], ax
0x18004a8c5  mov     eax, 0FFFFFFFFh
0x18004a8ca  cmp     r15d, eax
0x18004a8cd  jnz     short loc_18004A8F1
0x18004a8cf  mov     rax, [rbp+var_20]
0x18004a8d3  mov     rcx, [rbp+arg_0]
0x18004a8d7  mov     rdx, [rax+8]
0x18004a8db  mov     rdx, [rdx+rdi*8]
0x18004a8df  call    cs:__imp__o__wcsicmp
0x18004a8e6  nop     dword ptr [rax+rax+00h]
0x18004a8eb  test    eax, eax
0x18004a8ed  cmovz   r15d, edi
0x18004a8f1  mov     rax, [rbp+var_20]
0x18004a8f5  mov     edx, edi; unsigned int
0x18004a8f7  mov     rcx, rsi; this
0x18004a8fa  mov     r8, [rax+8]
0x18004a8fe  mov     r8, [r8+rdi*8]; unsigned __int16 *
0x18004a902  call    ?Add@CNlIsmSiteNameIndexCache@@QEAAKKPEAG@Z; CNlIsmSiteNameIndexCache::Add(ulong,ushort *)
0x18004a907  mov     r8d, eax
0x18004a90a  test    eax, eax
0x18004a90c  jnz     short loc_18004A95B
0x18004a90e  mov     rcx, [rbp+var_20]
0x18004a912  inc     edi
0x18004a914  mov     eax, [rcx]
0x18004a916  cmp     edi, eax
  ... truncated ...
```
