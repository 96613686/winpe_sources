# Nlparse(_NETLOGON_PARAMETERS *,_NETLOGON_PARAMETERS *,uchar)

- ea: `0x180052484`
- end: `0x180052d90`
- name: `?Nlparse@@YAHPEAU_NETLOGON_PARAMETERS@@0E@Z`
- size: `2316`
- prototype: `__int64 __fastcall(struct _NETLOGON_PARAMETERS *, struct _NETLOGON_PARAMETERS *, unsigned __int8)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180052d98`

## callees

- `0x180007518`
- `0x18000c210`
- `0x18000e910`
- `0x18000f3e4`
- `0x180041f80`
- `0x18005103c`
- `0x180051200`
- `0x180051400`
- `0x18005154c`
- `0x180052484`
- `0x18008cfdc`
- `0x18008d224`
- `0x18008e98c`
- `0x18008eb34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180052c37`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180052c37`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180052cea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180052cea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052bef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052cc9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052bef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052cc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052c61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052d11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052c61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052d11`

## string_xrefs

- `0x1800524ef`: `SYSTEM\CurrentControlSet\Services\Netlogon`
- `0x180052cbf`: `SYSTEM\CurrentControlSet\Services\Netlogon`
- `0x180052558`: `Failed to read from Netlogon Parameters register section. Error: %ld\n`
- `0x180052603`: `Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n`
- `0x18005271c`: `Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n`
- `0x1800527df`: `Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n`
- `0x180052885`: `Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n`
- `0x180052a56`: `Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n`
- `0x180052ac5`: `Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n`
- `0x180052939`: `RpcDacl`
- `0x180052969`: `RemoteAccessCheckDacl`
- `0x180052be5`: `SYSTEM\CurrentControlSet\Services\Netlogon\Parameters\CompoundIdentity`
- `0x180052cfa`: `NlParse: Deleted JoinDomain reg key\n`

## pseudocode

```c
__int64 __fastcall Nlparse(struct _NETLOGON_PARAMETERS *a1, struct _NETLOGON_PARAMETERS *a2, char a3)
{
  const wchar_t *v5; // rdx
  unsigned int v6; // eax
  unsigned int v7; // esi
  HKEY v8; // r12
  DWORD v9; // eax
  __int64 v10; // r13
  __int64 v11; // r15
  __int64 v12; // r9
  unsigned int *v13; // rcx
  unsigned int v14; // r9d
  unsigned int v15; // eax
  __int64 v16; // r8
  unsigned __int16 *v17; // rcx
  unsigned __int64 v18; // r15
  __int64 v19; // r8
  char *v20; // r9
  __int64 v21; // r8
  __int64 v22; // rcx
  unsigned __int16 *v23; // rcx
  __int64 v24; // r8
  unsigned __int16 *v25; // r8
  unsigned int v26; // eax
  unsigned __int16 *v27; // rcx
  unsigned __int16 *v28; // r8
  unsigned int v29; // eax
  unsigned __int16 *v30; // rcx
  unsigned __int16 **v31; // r9
  unsigned __int16 **v32; // r9
  unsigned __int16 **v33; // r9
  unsigned __int16 **v34; // r9
  unsigned int v35; // eax
  __int64 v36; // r8
  unsigned __int16 **v37; // r9
  unsigned int v38; // eax
  unsigned int v39; // eax
  WCHAR *v40; // r9
  const unsigned __int16 *v41; // r8
  __int64 v42; // rbx
  unsigned __int16 **v43; // r9
  unsigned int v44; // eax
  unsigned __int16 **v45; // r9
  unsigned __int16 **v46; // r9
  unsigned __int16 **v47; // r9
  int v48; // eax
  __int64 v49; // rdx
  __int64 v50; // r8
  int v51; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-69h]
  PHKEY phkResulta; // [rsp+20h] [rbp-69h]
  unsigned __int8 v55[4]; // [rsp+60h] [rbp-29h] BYREF
  char v56; // [rsp+64h] [rbp-25h]
  HKEY hKey; // [rsp+68h] [rbp-21h] BYREF
  __int64 v58; // [rsp+70h] [rbp-19h]
  DWORD cValues; // [rsp+78h] [rbp-11h] BYREF
  __int64 v60; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int16 *v61[2]; // [rsp+88h] [rbp-1h] BYREF
  __int64 v62; // [rsp+98h] [rbp+Fh]

  v56 = a3;
  v62 = 0;
  hKey = 0;
  v58 = 0;
  v60 = 0;
  *(_OWORD *)v61 = 0;
  *(_DWORD *)v55 = 0;
  memset_0(a1, 0, 0x220u);
  v5 = L"SYSTEM\\CurrentControlSet\\Services\\Netlogon";
  if ( a2 )
    v5 = L"Software\\Policies\\Microsoft\\Netlogon";
  v6 = NetpOpenConfigDataWithPathEx(&hKey, v5);
  *(_DWORD *)v55 = v6;
  if ( v6 )
  {
    if ( !a2 )
    {
      v62 = v6;
      v61[0] = L"Parameters";
      v61[1] = L"Parameters";
      NlpWriteEventlog(0x16ABu, 2u, 0x40000000u, v61, 3u, v55, 4u);
      NlPrintRoutine(
        0x100u,
        L"Failed to read from Netlogon Parameters register section. Error: %ld\n",
        *(unsigned int *)v55);
    }
    return 0;
  }
  v8 = hKey;
  v9 = a2 != 0;
  v10 = 0;
  cValues = v9;
  v11 = 0;
  v7 = 1;
  do
  {
    v12 = HIDWORD(qword_1800F5AF8[v11 + 1]);
    v13 = (unsigned int *)((char *)a1 + v12);
    if ( a2 )
      v14 = *(_DWORD *)((char *)a2 + v12);
    else
      v14 = qword_1800F5AF8[v11];
    v15 = NlParseOne(
            v8,
            v9,
            *(unsigned __int16 **)((char *)&ParseTable + v11 * 8),
            v14,
            HIDWORD(qword_1800F5AF8[v11]),
            qword_1800F5AF8[v11 + 1],
            v13);
    *(_DWORD *)v55 = v15;
    if ( v15 )
    {
      LODWORD(phkResult) = v15;
      v16 = *(__int64 *)((char *)&ParseTable + v11 * 8);
      v17 = &NlGlobalParametersString;
      if ( a2 )
        v17 = &NlGlobalGroupPolicyString;
      v61[0] = v17;
      NlPrintRoutine(
        0x100u,
        L"Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n",
        v16,
        v17,
        phkResult);
      v61[1] = *(unsigned __int16 **)((char *)&ParseTable + v11 * 8);
      v62 = *(unsigned int *)v55;
      NlpWriteEventlog(0x16ABu, 2u, 0x40000000u, v61, 3u, v55, 4u);
    }
    v9 = cValues;
    ++v10;
    v11 += 4;
  }
  while ( v10 != 55 );
  hKey = 0;
  v18 = 0;
  do
  {
    v19 = (unsigned int)dword_1800F57DC[v18 / 4];
    v20 = (char *)a1 + v19;
    if ( a2 )
      v21 = *(unsigned int *)((char *)a2 + v19);
    else
      v21 = *(unsigned int *)&byte_1800F57D8[v18];
    *(_DWORD *)v55 = NetpGetConfigBool(
                       v8,
                       *(struct _unnamed_type_BoolParseTable_ near **)((char *)&BoolParseTable + v18),
                       v21,
                       v20);
    if ( *(_DWORD *)v55 )
    {
      v22 = (unsigned int)dword_1800F57DC[v18 / 4];
      if ( a2 )
      {
        *(_DWORD *)((char *)a1 + v22) = *(_DWORD *)((char *)a2 + v22);
        v23 = &NlGlobalGroupPolicyString;
      }
      else
      {
        *(_DWORD *)((char *)a1 + v22) = *(_DWORD *)&byte_1800F57D8[v18];
        v23 = &NlGlobalParametersString;
      }
      v24 = *(__int64 *)((char *)&BoolParseTable + v18);
      v61[0] = v23;
      LODWORD(phkResult) = *(_DWORD *)v55;
      NlPrintRoutine(
        0x100u,
        L"Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n",
        v24,
        v23,
        phkResult);
      v61[1] = *(unsigned __int16 **)((char *)&BoolParseTable + v18);
      v62 = *(unsigned int *)v55;
      NlpWriteEventlog(0x16ABu, 2u, 0x40000000u, v61, 3u, v55, 4u);
    }
    v18 += 24LL;
    hKey = (HKEY)((char *)hKey + 1);
  }
  while ( hKey != (HKEY)33 );
  v25 = L"SYSVOL\\SYSVOL";
  if ( a2 )
    v25 = (unsigned __int16 *)*((_QWORD *)a2 + 28);
  v26 = NlParseOnePath(v8, L"SysVol", v25, (unsigned __int16 **)a1 + 28);
  *(_DWORD *)v55 = v26;
  if ( v26 )
  {
    *((_QWORD *)a1 + 28) = 0;
    LODWORD(phkResult) = v26;
    v27 = &NlGlobalParametersString;
    if ( a2 )
      v27 = &NlGlobalGroupPolicyString;
    v61[0] = v27;
    NlPrintRoutine(
      0x100u,
      L"Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n",
      L"SysVol",
      v27,
      phkResult);
    v62 = *(unsigned int *)v55;
    v61[1] = L"SysVol";
    NlpWriteEventlog(0x16ABu, 2u, 0x40000000u, v61, 3u, v55, 4u);
  }
  v28 = 0;
  if ( a2 )
    v28 = (unsigned __int16 *)*((_QWORD *)a2 + 29);
  v29 = NlParseOnePath(v8, L"Scripts", v28, (unsigned __int16 **)a1 + 29);
  *(_DWORD *)v55 = v29;
  if ( v29 )
  {
    *((_QWORD *)a1 + 29) = 0;
    LODWORD(phkResult) = v29;
    v30 = &NlGlobalParametersString;
    if ( a2 )
      v30 = &NlGlobalGroupPolicyString;
    v61[0] = v30;
    NlPrintRoutine(
      0x100u,
      L"Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n",
      L"Scripts",
      v30,
      phkResult);
    v62 = *(unsigned int *)v55;
    v61[1] = L"Scripts";
    NlpWriteEventlog(0x16ABu, 2u, 0x40000000u, v61, 3u, v55, 4u);
  }
  v31 = 0;
  if ( a2 )
    v31 = (unsigned __int16 **)((char *)a2 + 208);
  *(_DWORD *)v55 = NlParseTStr(v8, L"DCAllowedNTLMServers", 1, v31, (LPVOID *)a1 + 26);
  v32 = 0;
  if ( a2 )
    v32 = (unsigned __int16 **)((char *)a2 + 440);
  *(_DWORD *)v55 = NlParseTStr(v8, L"RpcDacl", 0, v32, (LPVOID *)a1 + 55);
  v33 = 0;
  if ( a2 )
    v33 = (unsigned __int16 **)((char *)a2 + 448);
  *(_DWORD *)v55 = NlParseTStr(v8, L"RemoteAccessCheckDacl", 0, v33, (LPVOID *)a1 + 56);
  v34 = 0;
  if ( a2 )
    v34 = (unsigned __int16 **)((char *)a2 + 304);
  v35 = NlParseTStr(v8, L"VulnerableChannelAllowList", 0, v34, (LPVOID *)a1 + 38);
  v36 = *((_QWORD *)a1 + 38);
  *(_DWORD *)v55 = v35;
  if ( v36 )
    NlPrintRoutine(1u, L"   VulnerableChannelAllowList = \"%ws\"\n");
  else
    NlPrintRoutine(1u, L"   VulnerableChannelAllowList is empty\n");
  v37 = 0;
  if ( a2 )
    v37 = (unsigned __int16 **)((char *)a2 + 240);
  v38 = NlParseTStr(v8, L"SiteName", 0, v37, (LPVOID *)a1 + 30);
  *(_DWORD *)v55 = v38;
  *((_DWORD *)a1 + 62) = v38 == 0;
  if ( a2 )
  {
    if ( v38 )
      *((_DWORD *)a1 + 62) = *((_DWORD *)a2 + 62);
    v43 = (unsigned __int16 **)((char *)a2 + 256);
LABEL_61:
    v44 = NlParseTStr(v8, L"SiteCoverage", 1, v43, (LPVOID *)a1 + 32);
    *(_DWORD *)v55 = v44;
    if ( v44 && v44 != 2147 )
    {
      v41 = L"SiteCoverage";
      goto LABEL_64;
    }
    v45 = 0;
    if ( a2 )
      v45 = (unsigned __int16 **)((char *)a2 + 264);
    v44 = NlParseTStr(v8, L"GcSiteCoverage", 1, v45, (LPVOID *)a1 + 33);
    *(_DWORD *)v55 = v44;
    if ( v44 && v44 != 2147 )
    {
      v41 = L"GcSiteCoverage";
      goto LABEL_64;
    }
    v46 = 0;
    if ( a2 )
      v46 = (unsigned __int16 **)((char *)a2 + 272);
    v44 = NlParseTStr(v8, L"NdncSiteCoverage", 1, v46, (LPVOID *)a1 + 34);
    *(_DWORD *)v55 = v44;
    if ( v44 && v44 != 2147 )
    {
      v41 = L"NdncSiteCoverage";
      goto LABEL_64;
    }
    v47 = 0;
    if ( a2 )
      v47 = (unsigned __int16 **)((char *)a2 + 288);
    v44 = NlParseTStr(v8, L"DnsAvoidRegisterRecords", 1, v47, (LPVOID *)a1 + 36);
    *(_DWORD *)v55 = v44;
    if ( v44 && v44 != 2147 )
    {
      v41 = L"DnsAvoidRegisterRecords";
LABEL_64:
      LODWORD(phkResulta) = v44;
      v40 = &NlGlobalParametersString;
      if ( a2 )
        v40 = &NlGlobalGroupPolicyString;
      goto LABEL_56;
    }
    NlParseRecompute(a1);
    if ( a2 )
    {
      *((_DWORD *)a1 + 104) = *((_DWORD *)a2 + 104);
    }
    else
    {
      hKey = 0;
      cValues = 0;
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\Netlogon\\Parameters\\CompoundIdentity",
             0,
             0x20019u,
             &hKey) )
      {
        *((_DWORD *)a1 + 104) = 0;
      }
      else
      {
        if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0) || (v48 = 1, !cValues) )
          v48 = 0;
        *((_DWORD *)a1 + 104) = v48;
        if ( hKey )
          RegCloseKey(hKey);
      }
    }
    if ( v56 && !a2 && (*((_DWORD *)a1 + 31) == 1 || !NlGlobalMemberWorkstation) )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\Netlogon", 0, 0x10000u, &hKey) )
      {
        if ( !RegDeleteKeyExW(hKey, L"JoinDomain", 0, 0) )
          NlPrintRoutine(1u, L"NlParse: Deleted JoinDomain reg key\n");
        if ( hKey )
          RegCloseKey(hKey);
      }
      v51 = NetpOpenConfigDataEx(&v60, v49, v50, 0);
      v42 = v60;
      if ( v51 )
        goto LABEL_102;
      v58 = v60;
      NetpDeleteConfigKeyword(v60, L"DcLocatorIsDoneWithJoinDomainEntry");
    }
    v42 = v58;
LABEL_102:
    *(_DWORD *)v55 = 0;
    goto LABEL_103;
  }
  if ( v38 != 2147
    || (v39 = NlParseTStr(v8, L"DynamicSiteName", 0, 0, (LPVOID *)a1 + 30), (*(_DWORD *)v55 = v39) == 0)
    || v39 == 2147 )
  {
    v43 = 0;
    goto LABEL_61;
  }
  LODWORD(phkResulta) = v39;
  v40 = &NlGlobalParametersString;
  v41 = L"DynamicSiteName";
LABEL_56:
  NlPrintRoutine(
    0x100u,
    L"Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n",
    v41,
    v40,
    phkResulta);
  v42 = v58;
  v7 = 0;
LABEL_103:
  if ( v8 )
    NetpCloseConfigData(v8);
  if ( v42 )
    NetpCloseConfigData(v42);
  return v7;
}

```

## disassembly

```asm
0x180052484  mov     [rsp-8+arg_10], rbx
0x180052489  push    rbp
0x18005248a  push    rsi
0x18005248b  push    rdi
0x18005248c  push    r12
0x18005248e  push    r13
0x180052490  push    r14
0x180052492  push    r15
0x180052494  lea     rbp, [rsp-27h]
0x180052499  sub     rsp, 0B0h
0x1800524a0  mov     rax, cs:__security_cookie
0x1800524a7  xor     rax, rsp
0x1800524aa  mov     [rbp+57h+var_40], rax
0x1800524ae  xor     eax, eax
0x1800524b0  mov     [rbp+57h+var_7C], r8b
0x1800524b4  mov     rbx, rdx
0x1800524b7  mov     [rbp+57h+var_48], rax
0x1800524bb  xorps   xmm0, xmm0
0x1800524be  mov     [rbp+57h+hKey], rax
0x1800524c2  xor     edx, edx; Val
0x1800524c4  mov     [rbp+57h+var_70], rax
0x1800524c8  mov     r8d, 220h; Size
0x1800524ce  mov     [rbp+57h+var_60], rax
0x1800524d2  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x1800524d6  mov     rdi, rcx
0x1800524d9  mov     dword ptr [rbp+57h+var_80], 0
0x1800524e0  call    memset_0
0x1800524e5  lea     rax, aSoftwarePolici; "Software\\Policies\\Microsoft\\Netlogon"
0x1800524ec  test    rbx, rbx
0x1800524ef  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x1800524f6  cmovnz  rdx, rax
0x1800524fa  lea     rcx, [rbp+57h+hKey]
0x1800524fe  call    NetpOpenConfigDataWithPathEx
0x180052503  mov     dword ptr [rbp+57h+var_80], eax
0x180052506  test    eax, eax
0x180052508  jz      short loc_180052570
0x18005250a  test    rbx, rbx
0x18005250d  jnz     short loc_180052569
0x18005250f  lea     rcx, aParameters; "Parameters"
0x180052516  mov     eax, eax
0x180052518  mov     [rbp+57h+var_48], rax
0x18005251c  lea     r9, [rbp+57h+var_58]; unsigned __int16 **
0x180052520  lea     rax, [rbp+57h+var_80]
0x180052524  mov     [rbp+57h+var_58], rcx
0x180052528  mov     [rbp+57h+var_58+8], rcx
0x18005252c  lea     edx, [rbx+2]; unsigned int
0x18005252f  mov     dword ptr [rsp+0E0h+lpcbMaxClassLen], 4; unsigned int
0x180052537  mov     ecx, 16ABh; unsigned int
0x18005253c  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; unsigned __int8 *
0x180052541  mov     r8d, 40000000h; unsigned int
0x180052547  mov     dword ptr [rsp+0E0h+phkResult], 3; unsigned int
0x18005254f  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x180052554  mov     r8d, dword ptr [rbp+57h+var_80]
0x180052558  lea     rdx, aFailedToReadFr; "Failed to read from Netlogon Parameters"...
0x18005255f  mov     ecx, 100h; unsigned int
0x180052564  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180052569  xor     esi, esi
0x18005256b  jmp     loc_180052D66
0x180052570  mov     r12, [rbp+57h+hKey]
0x180052574  xor     eax, eax
0x180052576  test    rbx, rbx
0x180052579  mov     r14d, 100h
0x18005257f  setnz   al
0x180052582  xor     r13d, r13d
0x180052585  mov     [rbp+57h+cValues], eax
0x180052588  xor     r15d, r15d
0x18005258b  lea     esi, [r13+1]
0x18005258f  lea     r10, __ImageBase
0x180052596  mov     r9d, [r15+r10+0F5B04h]
0x18005259e  mov     edx, [r15+r10+0F5B00h]
0x1800525a6  mov     r8d, [r15+r10+0F5AFCh]
0x1800525ae  lea     rcx, [r9+rdi]
0x1800525b2  test    rbx, rbx
0x1800525b5  jnz     short loc_1800525C1
0x1800525b7  mov     r9d, [r15+r10+0F5AF8h]
0x1800525bf  jmp     short loc_1800525C5
0x1800525c1  mov     r9d, [r9+rbx]; unsigned int
0x1800525c5  mov     [rsp+0E0h+lpcbMaxClassLen], rcx; unsigned int *
0x1800525ca  mov     rcx, r12; void *
0x1800525cd  mov     dword ptr [rsp+0E0h+lpcbMaxSubKeyLen], edx; unsigned int
0x1800525d1  mov     edx, eax; int
0x1800525d3  mov     dword ptr [rsp+0E0h+phkResult], r8d; unsigned int
0x1800525d8  mov     r8, [r15+r10+0F5AF0h]; unsigned __int16 *
0x1800525e0  call    ?NlParseOne@@YAKPEAXHPEAGKKKPEAK@Z; NlParseOne(void *,int,ushort *,ulong,ulong,ulong,ulong *)
0x1800525e5  mov     dword ptr [rbp+57h+var_80], eax
0x1800525e8  test    eax, eax
0x1800525ea  jz      loc_180052678
0x1800525f0  mov     dword ptr [rsp+0E0h+phkResult], eax
0x1800525f4  lea     r8, __ImageBase
0x1800525fb  mov     r8, [r15+r8+0F5AF0h]
0x180052603  lea     rdx, aFailedToReadAP; "Failed to read a parameter %ws from Net"...
0x18005260a  lea     rcx, ?NlGlobalParametersString@@3PAGA; ushort near * NlGlobalParametersString
0x180052611  test    rbx, rbx
0x180052614  jz      short loc_18005261D
0x180052616  lea     rcx, ?NlGlobalGroupPolicyString@@3PAGA; ushort near * NlGlobalGroupPolicyString
0x18005261d  mov     [rbp+57h+var_58], rcx
0x180052621  mov     r9, rcx
0x180052624  mov     ecx, r14d; unsigned int
0x180052627  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005262c  mov     dword ptr [rsp+0E0h+lpcbMaxClassLen], 4; unsigned int
0x180052634  lea     rax, __ImageBase
0x18005263b  mov     rax, [r15+rax+0F5AF0h]
0x180052643  lea     r9, [rbp+57h+var_58]; unsigned __int16 **
0x180052647  mov     [rbp+57h+var_58+8], rax
0x18005264b  mov     edx, 2; unsigned int
0x180052650  mov     eax, dword ptr [rbp+57h+var_80]
0x180052653  mov     ecx, 16ABh; unsigned int
0x180052658  mov     [rbp+57h+var_48], rax
0x18005265c  mov     r8d, 40000000h; unsigned int
0x180052662  lea     rax, [rbp+57h+var_80]
0x180052666  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; unsigned __int8 *
0x18005266b  mov     dword ptr [rsp+0E0h+phkResult], 3; unsigned int
0x180052673  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x180052678  mov     eax, [rbp+57h+cValues]
0x18005267b  add     r13, rsi
0x18005267e  add     r15, 20h ; ' '
0x180052682  cmp     r13, 37h ; '7'
0x180052686  jnz     loc_18005258F
0x18005268c  mov     [rbp+57h+hKey], 0
0x180052694  xor     r15d, r15d
0x180052697  lea     rax, __ImageBase
0x18005269e  mov     r8d, [r15+rax+0F57DCh]
0x1800526a6  lea     r13, rva byte_1800F57D8[rax]
0x1800526ad  lea     r9, [r8+rdi]
0x1800526b1  test    rbx, rbx
0x1800526b4  jnz     short loc_1800526BD
0x1800526b6  mov     r8d, [r13+r15+0]
0x1800526bb  jmp     short loc_1800526C1
0x1800526bd  mov     r8d, [r8+rbx]
0x1800526c1  mov     rdx, [r15+rax+0F57D0h]
0x1800526c9  mov     rcx, r12
0x1800526cc  call    NetpGetConfigBool
0x1800526d1  mov     dword ptr [rbp+57h+var_80], eax
0x1800526d4  test    eax, eax
0x1800526d6  jz      loc_18005277F
0x1800526dc  lea     rdx, __ImageBase
0x1800526e3  mov     ecx, [r15+rdx+0F57DCh]
0x1800526eb  test    rbx, rbx
0x1800526ee  jnz     short loc_180052701
0x1800526f0  mov     eax, [r13+r15+0]
0x1800526f5  mov     [rcx+rdi], eax
0x1800526f8  lea     rcx, ?NlGlobalParametersString@@3PAGA; ushort near * NlGlobalParametersString
0x1800526ff  jmp     short loc_18005270E
0x180052701  mov     eax, [rcx+rbx]
0x180052704  mov     [rcx+rdi], eax
0x180052707  lea     rcx, ?NlGlobalGroupPolicyString@@3PAGA; ushort near * NlGlobalGroupPolicyString
0x18005270e  mov     r8, [r15+rdx+0F57D0h]
0x180052716  mov     r9, rcx
0x180052719  mov     eax, dword ptr [rbp+57h+var_80]
0x18005271c  lea     rdx, aFailedToReadAP; "Failed to read a parameter %ws from Net"...
0x180052723  mov     [rbp+57h+var_58], rcx
0x180052727  mov     ecx, r14d; unsigned int
0x18005272a  mov     dword ptr [rsp+0E0h+phkResult], eax
0x18005272e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180052733  mov     dword ptr [rsp+0E0h+lpcbMaxClassLen], 4; unsigned int
0x18005273b  lea     rax, __ImageBase
0x180052742  mov     rax, [r15+rax+0F57D0h]
0x18005274a  lea     r9, [rbp+57h+var_58]; unsigned __int16 **
0x18005274e  mov     [rbp+57h+var_58+8], rax
0x180052752  mov     edx, 2; unsigned int
0x180052757  mov     eax, dword ptr [rbp+57h+var_80]
0x18005275a  mov     ecx, 16ABh; unsigned int
0x18005275f  mov     [rbp+57h+var_48], rax
0x180052763  mov     r8d, 40000000h; unsigned int
0x180052769  lea     rax, [rbp+57h+var_80]
0x18005276d  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; unsigned __int8 *
0x180052772  mov     dword ptr [rsp+0E0h+phkResult], 3; unsigned int
0x18005277a  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18005277f  mov     rax, [rbp+57h+hKey]
0x180052783  add     r15, 18h
0x180052787  add     rax, rsi
0x18005278a  mov     [rbp+57h+hKey], rax
0x18005278e  cmp     rax, 21h ; '!'
0x180052792  jnz     loc_180052697
0x180052798  xor     r13d, r13d
0x18005279b  lea     r15, [rdi+0E0h]
0x1800527a2  lea     r8, aSysvolSysvol; "SYSVOL\\SYSVOL"
0x1800527a9  test    rbx, rbx
0x1800527ac  jz      short loc_1800527B5
0x1800527ae  mov     r8, [rbx+0E0h]; unsigned __int16 *
0x1800527b5  mov     r9, r15; unsigned __int16 **
0x1800527b8  lea     rdx, aSysvol_0; "SysVol"
0x1800527bf  mov     rcx, r12; void *
0x1800527c2  call    ?NlParseOnePath@@YAKPEAXPEAG1PEAPEAG@Z; NlParseOnePath(void *,ushort *,ushort *,ushort * *)
0x1800527c7  mov     dword ptr [rbp+57h+var_80], eax
0x1800527ca  test    eax, eax
0x1800527cc  jz      short loc_180052845
0x1800527ce  mov     [r15], r13
0x1800527d1  lea     r15, aSysvol_0; "SysVol"
0x1800527d8  mov     dword ptr [rsp+0E0h+phkResult], eax
0x1800527dc  mov     r8, r15
0x1800527df  lea     rdx, aFailedToReadAP; "Failed to read a parameter %ws from Net"...
0x1800527e6  lea     rcx, ?NlGlobalParametersString@@3PAGA; ushort near * NlGlobalParametersString
0x1800527ed  test    rbx, rbx
0x1800527f0  jz      short loc_1800527F9
0x1800527f2  lea     rcx, ?NlGlobalGroupPolicyString@@3PAGA; ushort near * NlGlobalGroupPolicyString
0x1800527f9  mov     [rbp+57h+var_58], rcx
0x1800527fd  mov     r9, rcx
0x180052800  mov     ecx, r14d; unsigned int
0x180052803  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180052808  mov     eax, dword ptr [rbp+57h+var_80]
0x18005280b  lea     r9, [rbp+57h+var_58]; unsigned __int16 **
0x18005280f  mov     [rbp+57h+var_48], rax
0x180052813  mov     edx, 2; unsigned int
0x180052818  lea     rax, [rbp+57h+var_80]
0x18005281c  mov     dword ptr [rsp+0E0h+lpcbMaxClassLen], 4; unsigned int
0x180052824  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; unsigned __int8 *
0x180052829  mov     ecx, 16ABh; unsigned int
0x18005282e  mov     r8d, 40000000h; unsigned int
0x180052834  mov     dword ptr [rsp+0E0h+phkResult], 3; unsigned int
0x18005283c  mov     [rbp+57h+var_58+8], r15
0x180052840  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x180052845  lea     r15, [rdi+0E8h]
0x18005284c  mov     r8, r13
0x18005284f  test    rbx, rbx
0x180052852  jz      short loc_18005285B
0x180052854  mov     r8, [rbx+0E8h]; unsigned __int16 *
0x18005285b  mov     r9, r15; unsigned __int16 **
0x18005285e  lea     rdx, aScripts; "Scripts"
0x180052865  mov     rcx, r12; void *
0x180052868  call    ?NlParseOnePath@@YAKPEAXPEAG1PEAPEAG@Z; NlParseOnePath(void *,ushort *,ushort *,ushort * *)
0x18005286d  mov     dword ptr [rbp+57h+var_80], eax
0x180052870  test    eax, eax
0x180052872  jz      short loc_1800528EB
0x180052874  mov     [r15], r13
0x180052877  lea     r15, aScripts; "Scripts"
0x18005287e  mov     dword ptr [rsp+0E0h+phkResult], eax
0x180052882  mov     r8, r15
0x180052885  lea     rdx, aFailedToReadAP; "Failed to read a parameter %ws from Net"...
0x18005288c  lea     rcx, ?NlGlobalParametersString@@3PAGA; ushort near * NlGlobalParametersString
0x180052893  test    rbx, rbx
0x180052896  jz      short loc_18005289F
0x180052898  lea     rcx, ?NlGlobalGroupPolicyString@@3PAGA; ushort near * NlGlobalGroupPolicyString
0x18005289f  mov     [rbp+57h+var_58], rcx
0x1800528a3  mov     r9, rcx
0x1800528a6  mov     ecx, r14d; unsigned int
0x1800528a9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800528ae  mov     eax, dword ptr [rbp+57h+var_80]
0x1800528b1  lea     r9, [rbp+57h+var_58]; unsigned __int16 **
0x1800528b5  mov     [rbp+57h+var_48], rax
0x1800528b9  mov     edx, 2; unsigned int
0x1800528be  lea     rax, [rbp+57h+var_80]
0x1800528c2  mov     dword ptr [rsp+0E0h+lpcbMaxClassLen], 4; unsigned int
0x1800528ca  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; unsigned __int8 *
0x1800528cf  mov     ecx, 16ABh; unsigned int
0x1800528d4  mov     r8d, 40000000h; unsigned int
0x1800528da  mov     dword ptr [rsp+0E0h+phkResult], 3; unsigned int
0x1800528e2  mov     [rbp+57h+var_58+8], r15
0x1800528e6  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x1800528eb  lea     rax, [rdi+0D0h]
0x1800528f2  mov     r9, r13
0x1800528f5  test    rbx, rbx
0x1800528f8  jz      short loc_180052901
0x1800528fa  lea     r9, [rbx+0D0h]; unsigned __int16 **
0x180052901  mov     r8d, esi; int
0x180052904  mov     [rsp+0E0h+phkResult], rax; LPVOID *
0x180052909  lea     rdx, aDcallowedntlms; "DCAllowedNTLMServers"
0x180052910  mov     rcx, r12; void *
0x180052913  call    ?NlParseTStr@@YAKPEAXPEAGHPEAPEAG2@Z; NlParseTStr(void *,ushort *,int,ushort * *,ushort * *)
0x180052918  mov     dword ptr [rbp+57h+var_80], eax
0x18005291b  lea     rax, [rdi+1B8h]
0x180052922  mov     r9, r13
0x180052925  test    rbx, rbx
0x180052928  jz      short loc_180052931
0x18005292a  lea     r9, [rbx+1B8h]; unsigned __int16 **
0x180052931  xor     r8d, r8d; int
0x180052934  mov     [rsp+0E0h+phkResult], rax; LPVOID *
0x180052939  lea     rdx, aRpcdacl; "RpcDacl"
0x180052940  mov     rcx, r12; void *
0x180052943  call    ?NlParseTStr@@YAKPEAXPEAGHPEAPEAG2@Z; NlParseTStr(void *,ushort *,int,ushort * *,ushort * *)
0x180052948  mov     dword ptr [rbp+57h+var_80], eax
0x18005294b  lea     rax, [rdi+1C0h]
0x180052952  mov     r9, r13
0x180052955  test    rbx, rbx
0x180052958  jz      short loc_180052961
0x18005295a  lea     r9, [rbx+1C0h]; unsigned __int16 **
0x180052961  xor     r8d, r8d; int
0x180052964  mov     [rsp+0E0h+phkResult], rax; LPVOID *
0x180052969  lea     rdx, aRemoteaccessch_1; "RemoteAccessCheckDacl"
0x180052970  mov     rcx, r12; void *
0x180052973  call    ?NlParseTStr@@YAKPEAXPEAGHPEAPEAG2@Z; NlParseTStr(void *,ushort *,int,ushort * *,ushort * *)
0x180052978  mov     dword ptr [rbp+57h+var_80], eax
0x18005297b  lea     r15, [rdi+130h]
0x180052982  mov     r9, r13
0x180052985  test    rbx, rbx
0x180052988  jz      short loc_180052991
0x18005298a  lea     r9, [rbx+130h]; unsigned __int16 **
0x180052991  xor     r8d, r8d; int
0x180052994  mov     [rsp+0E0h+phkResult], r15; LPVOID *
0x180052999  lea     rdx, aVulnerablechan_1; "VulnerableChannelAllowList"
0x1800529a0  mov     rcx, r12; void *
0x1800529a3  call    ?NlParseTStr@@YAKPEAXPEAGHPEAPEAG2@Z; NlParseTStr(void *,ushort *,int,ushort * *,ushort * *)
0x1800529a8  mov     r8, [r15]
0x1800529ab  mov     ecx, esi; unsigned int
0x1800529ad  mov     dword ptr [rbp+57h+var_80], eax
0x1800529b0  test    r8, r8
0x1800529b3  jz      short loc_1800529C3
0x1800529b5  lea     rdx, aVulnerablechan_2; "   VulnerableChannelAllowList = \"%ws\""...
0x1800529bc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800529c1  jmp     short loc_1800529CF
  ... truncated ...
```
