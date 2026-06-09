# Nlparse(_NETLOGON_PARAMETERS *,_NETLOGON_PARAMETERS *,uchar)

- ea: `0x18004ed98`
- end: `0x18004f67f`
- name: `?Nlparse@@YAHPEAU_NETLOGON_PARAMETERS@@0E@Z`
- size: `2279`
- prototype: `__int64 __fastcall(struct _NETLOGON_PARAMETERS *, struct _NETLOGON_PARAMETERS *, unsigned __int8)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004f688`

## callees

- `0x180007278`
- `0x18000bb90`
- `0x18000e270`
- `0x18000ed34`
- `0x18003f648`
- `0x18004da08`
- `0x18004dbc8`
- `0x18004dd9c`
- `0x18004dee4`
- `0x18004ed98`
- `0x180086bf4`
- `0x180086e30`
- `0x180088394`
- `0x180088514`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004f545`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004f545`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18004f5e6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18004f5e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f503`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f5cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f503`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f5cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f569`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f607`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f569`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f607`

## string_xrefs

- `0x18004ee03`: `SYSTEM\CurrentControlSet\Services\Netlogon`
- `0x18004f5c1`: `SYSTEM\CurrentControlSet\Services\Netlogon`
- `0x18004ee6c`: `Failed to read from Netlogon Parameters register section. Error: %ld\n`
- `0x18004ef17`: `Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n`
- `0x18004f030`: `Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n`
- `0x18004f0f3`: `Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n`
- `0x18004f199`: `Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n`
- `0x18004f36a`: `Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n`
- `0x18004f3d9`: `Failed to read a parameter %ws from Netlogon %ws register section. Error: %ld\n`
- `0x18004f24d`: `RpcDacl`
- `0x18004f27d`: `RemoteAccessCheckDacl`
- `0x18004f4f9`: `SYSTEM\CurrentControlSet\Services\Netlogon\Parameters\CompoundIdentity`
- `0x18004f5f0`: `NlParse: Deleted JoinDomain reg key\n`

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
    v12 = HIDWORD(qword_1800EEAF8[v11 + 1]);
    v13 = (unsigned int *)((char *)a1 + v12);
    if ( a2 )
      v14 = *(_DWORD *)((char *)a2 + v12);
    else
      v14 = qword_1800EEAF8[v11];
    v15 = NlParseOne(
            v8,
            v9,
            *(unsigned __int16 **)((char *)&ParseTable + v11 * 8),
            v14,
            HIDWORD(qword_1800EEAF8[v11]),
            qword_1800EEAF8[v11 + 1],
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
    v19 = (unsigned int)dword_1800EE7DC[v18 / 4];
    v20 = (char *)a1 + v19;
    if ( a2 )
      v21 = *(unsigned int *)((char *)a2 + v19);
    else
      v21 = *(unsigned int *)&byte_1800EE7D8[v18];
    *(_DWORD *)v55 = NetpGetConfigBool(
                       v8,
                       *(struct _unnamed_type_BoolParseTable_ near **)((char *)&BoolParseTable + v18),
                       v21,
                       v20);
    if ( *(_DWORD *)v55 )
    {
      v22 = (unsigned int)dword_1800EE7DC[v18 / 4];
      if ( a2 )
      {
        *(_DWORD *)((char *)a1 + v22) = *(_DWORD *)((char *)a2 + v22);
        v23 = &NlGlobalGroupPolicyString;
      }
      else
      {
        *(_DWORD *)((char *)a1 + v22) = *(_DWORD *)&byte_1800EE7D8[v18];
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
0x18004ed98  mov     [rsp-8+arg_10], rbx
0x18004ed9d  push    rbp
0x18004ed9e  push    rsi
0x18004ed9f  push    rdi
0x18004eda0  push    r12
0x18004eda2  push    r13
0x18004eda4  push    r14
0x18004eda6  push    r15
0x18004eda8  lea     rbp, [rsp-27h]
0x18004edad  sub     rsp, 0B0h
0x18004edb4  mov     rax, cs:__security_cookie
0x18004edbb  xor     rax, rsp
0x18004edbe  mov     [rbp+57h+var_40], rax
0x18004edc2  xor     eax, eax
0x18004edc4  mov     [rbp+57h+var_7C], r8b
0x18004edc8  mov     rbx, rdx
0x18004edcb  mov     [rbp+57h+var_48], rax
0x18004edcf  xorps   xmm0, xmm0
0x18004edd2  mov     [rbp+57h+hKey], rax
0x18004edd6  xor     edx, edx; Val
0x18004edd8  mov     [rbp+57h+var_70], rax
0x18004eddc  mov     r8d, 220h; Size
0x18004ede2  mov     [rbp+57h+var_60], rax
0x18004ede6  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x18004edea  mov     rdi, rcx
0x18004eded  mov     dword ptr [rbp+57h+var_80], 0
0x18004edf4  call    memset_0
0x18004edf9  lea     rax, aSoftwarePolici; "Software\\Policies\\Microsoft\\Netlogon"
0x18004ee00  test    rbx, rbx
0x18004ee03  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x18004ee0a  cmovnz  rdx, rax
0x18004ee0e  lea     rcx, [rbp+57h+hKey]
0x18004ee12  call    NetpOpenConfigDataWithPathEx
0x18004ee17  mov     dword ptr [rbp+57h+var_80], eax
0x18004ee1a  test    eax, eax
0x18004ee1c  jz      short loc_18004EE84
0x18004ee1e  test    rbx, rbx
0x18004ee21  jnz     short loc_18004EE7D
0x18004ee23  lea     rcx, aParameters; "Parameters"
0x18004ee2a  mov     eax, eax
0x18004ee2c  mov     [rbp+57h+var_48], rax
0x18004ee30  lea     r9, [rbp+57h+var_58]; unsigned __int16 **
0x18004ee34  lea     rax, [rbp+57h+var_80]
0x18004ee38  mov     [rbp+57h+var_58], rcx
0x18004ee3c  mov     [rbp+57h+var_58+8], rcx
0x18004ee40  lea     edx, [rbx+2]; unsigned int
0x18004ee43  mov     dword ptr [rsp+0E0h+lpcbMaxClassLen], 4; unsigned int
0x18004ee4b  mov     ecx, 16ABh; unsigned int
0x18004ee50  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; unsigned __int8 *
0x18004ee55  mov     r8d, 40000000h; unsigned int
0x18004ee5b  mov     dword ptr [rsp+0E0h+phkResult], 3; unsigned int
0x18004ee63  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18004ee68  mov     r8d, dword ptr [rbp+57h+var_80]
0x18004ee6c  lea     rdx, aFailedToReadFr; "Failed to read from Netlogon Parameters"...
0x18004ee73  mov     ecx, 100h; unsigned int
0x18004ee78  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004ee7d  xor     esi, esi
0x18004ee7f  jmp     loc_18004F656
0x18004ee84  mov     r12, [rbp+57h+hKey]
0x18004ee88  xor     eax, eax
0x18004ee8a  test    rbx, rbx
0x18004ee8d  mov     r14d, 100h
0x18004ee93  setnz   al
0x18004ee96  xor     r13d, r13d
0x18004ee99  mov     [rbp+57h+cValues], eax
0x18004ee9c  xor     r15d, r15d
0x18004ee9f  lea     esi, [r13+1]
0x18004eea3  lea     r10, __ImageBase
0x18004eeaa  mov     r9d, [r15+r10+0EEB04h]
0x18004eeb2  mov     edx, [r15+r10+0EEB00h]
0x18004eeba  mov     r8d, [r15+r10+0EEAFCh]
0x18004eec2  lea     rcx, [r9+rdi]
0x18004eec6  test    rbx, rbx
0x18004eec9  jnz     short loc_18004EED5
0x18004eecb  mov     r9d, [r15+r10+0EEAF8h]
0x18004eed3  jmp     short loc_18004EED9
0x18004eed5  mov     r9d, [r9+rbx]; unsigned int
0x18004eed9  mov     [rsp+0E0h+lpcbMaxClassLen], rcx; unsigned int *
0x18004eede  mov     rcx, r12; void *
0x18004eee1  mov     dword ptr [rsp+0E0h+lpcbMaxSubKeyLen], edx; unsigned int
0x18004eee5  mov     edx, eax; int
0x18004eee7  mov     dword ptr [rsp+0E0h+phkResult], r8d; unsigned int
0x18004eeec  mov     r8, [r15+r10+0EEAF0h]; unsigned __int16 *
0x18004eef4  call    ?NlParseOne@@YAKPEAXHPEAGKKKPEAK@Z; NlParseOne(void *,int,ushort *,ulong,ulong,ulong,ulong *)
0x18004eef9  mov     dword ptr [rbp+57h+var_80], eax
0x18004eefc  test    eax, eax
0x18004eefe  jz      loc_18004EF8C
0x18004ef04  mov     dword ptr [rsp+0E0h+phkResult], eax
0x18004ef08  lea     r8, __ImageBase
0x18004ef0f  mov     r8, [r15+r8+0EEAF0h]
0x18004ef17  lea     rdx, aFailedToReadAP; "Failed to read a parameter %ws from Net"...
0x18004ef1e  lea     rcx, ?NlGlobalParametersString@@3PAGA; ushort near * NlGlobalParametersString
0x18004ef25  test    rbx, rbx
0x18004ef28  jz      short loc_18004EF31
0x18004ef2a  lea     rcx, ?NlGlobalGroupPolicyString@@3PAGA; ushort near * NlGlobalGroupPolicyString
0x18004ef31  mov     [rbp+57h+var_58], rcx
0x18004ef35  mov     r9, rcx
0x18004ef38  mov     ecx, r14d; unsigned int
0x18004ef3b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004ef40  mov     dword ptr [rsp+0E0h+lpcbMaxClassLen], 4; unsigned int
0x18004ef48  lea     rax, __ImageBase
0x18004ef4f  mov     rax, [r15+rax+0EEAF0h]
0x18004ef57  lea     r9, [rbp+57h+var_58]; unsigned __int16 **
0x18004ef5b  mov     [rbp+57h+var_58+8], rax
0x18004ef5f  mov     edx, 2; unsigned int
0x18004ef64  mov     eax, dword ptr [rbp+57h+var_80]
0x18004ef67  mov     ecx, 16ABh; unsigned int
0x18004ef6c  mov     [rbp+57h+var_48], rax
0x18004ef70  mov     r8d, 40000000h; unsigned int
0x18004ef76  lea     rax, [rbp+57h+var_80]
0x18004ef7a  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; unsigned __int8 *
0x18004ef7f  mov     dword ptr [rsp+0E0h+phkResult], 3; unsigned int
0x18004ef87  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18004ef8c  mov     eax, [rbp+57h+cValues]
0x18004ef8f  add     r13, rsi
0x18004ef92  add     r15, 20h ; ' '
0x18004ef96  cmp     r13, 37h ; '7'
0x18004ef9a  jnz     loc_18004EEA3
0x18004efa0  mov     [rbp+57h+hKey], 0
0x18004efa8  xor     r15d, r15d
0x18004efab  lea     rax, __ImageBase
0x18004efb2  mov     r8d, [r15+rax+0EE7DCh]
0x18004efba  lea     r13, rva byte_1800EE7D8[rax]
0x18004efc1  lea     r9, [r8+rdi]
0x18004efc5  test    rbx, rbx
0x18004efc8  jnz     short loc_18004EFD1
0x18004efca  mov     r8d, [r13+r15+0]
0x18004efcf  jmp     short loc_18004EFD5
0x18004efd1  mov     r8d, [r8+rbx]
0x18004efd5  mov     rdx, [r15+rax+0EE7D0h]
0x18004efdd  mov     rcx, r12
0x18004efe0  call    NetpGetConfigBool
0x18004efe5  mov     dword ptr [rbp+57h+var_80], eax
0x18004efe8  test    eax, eax
0x18004efea  jz      loc_18004F093
0x18004eff0  lea     rdx, __ImageBase
0x18004eff7  mov     ecx, [r15+rdx+0EE7DCh]
0x18004efff  test    rbx, rbx
0x18004f002  jnz     short loc_18004F015
0x18004f004  mov     eax, [r13+r15+0]
0x18004f009  mov     [rcx+rdi], eax
0x18004f00c  lea     rcx, ?NlGlobalParametersString@@3PAGA; ushort near * NlGlobalParametersString
0x18004f013  jmp     short loc_18004F022
0x18004f015  mov     eax, [rcx+rbx]
0x18004f018  mov     [rcx+rdi], eax
0x18004f01b  lea     rcx, ?NlGlobalGroupPolicyString@@3PAGA; ushort near * NlGlobalGroupPolicyString
0x18004f022  mov     r8, [r15+rdx+0EE7D0h]
0x18004f02a  mov     r9, rcx
0x18004f02d  mov     eax, dword ptr [rbp+57h+var_80]
0x18004f030  lea     rdx, aFailedToReadAP; "Failed to read a parameter %ws from Net"...
0x18004f037  mov     [rbp+57h+var_58], rcx
0x18004f03b  mov     ecx, r14d; unsigned int
0x18004f03e  mov     dword ptr [rsp+0E0h+phkResult], eax
0x18004f042  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004f047  mov     dword ptr [rsp+0E0h+lpcbMaxClassLen], 4; unsigned int
0x18004f04f  lea     rax, __ImageBase
0x18004f056  mov     rax, [r15+rax+0EE7D0h]
0x18004f05e  lea     r9, [rbp+57h+var_58]; unsigned __int16 **
0x18004f062  mov     [rbp+57h+var_58+8], rax
0x18004f066  mov     edx, 2; unsigned int
0x18004f06b  mov     eax, dword ptr [rbp+57h+var_80]
0x18004f06e  mov     ecx, 16ABh; unsigned int
0x18004f073  mov     [rbp+57h+var_48], rax
0x18004f077  mov     r8d, 40000000h; unsigned int
0x18004f07d  lea     rax, [rbp+57h+var_80]
0x18004f081  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; unsigned __int8 *
0x18004f086  mov     dword ptr [rsp+0E0h+phkResult], 3; unsigned int
0x18004f08e  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18004f093  mov     rax, [rbp+57h+hKey]
0x18004f097  add     r15, 18h
0x18004f09b  add     rax, rsi
0x18004f09e  mov     [rbp+57h+hKey], rax
0x18004f0a2  cmp     rax, 21h ; '!'
0x18004f0a6  jnz     loc_18004EFAB
0x18004f0ac  xor     r13d, r13d
0x18004f0af  lea     r15, [rdi+0E0h]
0x18004f0b6  lea     r8, aSysvolSysvol; "SYSVOL\\SYSVOL"
0x18004f0bd  test    rbx, rbx
0x18004f0c0  jz      short loc_18004F0C9
0x18004f0c2  mov     r8, [rbx+0E0h]; unsigned __int16 *
0x18004f0c9  mov     r9, r15; unsigned __int16 **
0x18004f0cc  lea     rdx, aSysvol_0; "SysVol"
0x18004f0d3  mov     rcx, r12; void *
0x18004f0d6  call    ?NlParseOnePath@@YAKPEAXPEAG1PEAPEAG@Z; NlParseOnePath(void *,ushort *,ushort *,ushort * *)
0x18004f0db  mov     dword ptr [rbp+57h+var_80], eax
0x18004f0de  test    eax, eax
0x18004f0e0  jz      short loc_18004F159
0x18004f0e2  mov     [r15], r13
0x18004f0e5  lea     r15, aSysvol_0; "SysVol"
0x18004f0ec  mov     dword ptr [rsp+0E0h+phkResult], eax
0x18004f0f0  mov     r8, r15
0x18004f0f3  lea     rdx, aFailedToReadAP; "Failed to read a parameter %ws from Net"...
0x18004f0fa  lea     rcx, ?NlGlobalParametersString@@3PAGA; ushort near * NlGlobalParametersString
0x18004f101  test    rbx, rbx
0x18004f104  jz      short loc_18004F10D
0x18004f106  lea     rcx, ?NlGlobalGroupPolicyString@@3PAGA; ushort near * NlGlobalGroupPolicyString
0x18004f10d  mov     [rbp+57h+var_58], rcx
0x18004f111  mov     r9, rcx
0x18004f114  mov     ecx, r14d; unsigned int
0x18004f117  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004f11c  mov     eax, dword ptr [rbp+57h+var_80]
0x18004f11f  lea     r9, [rbp+57h+var_58]; unsigned __int16 **
0x18004f123  mov     [rbp+57h+var_48], rax
0x18004f127  mov     edx, 2; unsigned int
0x18004f12c  lea     rax, [rbp+57h+var_80]
0x18004f130  mov     dword ptr [rsp+0E0h+lpcbMaxClassLen], 4; unsigned int
0x18004f138  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; unsigned __int8 *
0x18004f13d  mov     ecx, 16ABh; unsigned int
0x18004f142  mov     r8d, 40000000h; unsigned int
0x18004f148  mov     dword ptr [rsp+0E0h+phkResult], 3; unsigned int
0x18004f150  mov     [rbp+57h+var_58+8], r15
0x18004f154  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18004f159  lea     r15, [rdi+0E8h]
0x18004f160  mov     r8, r13
0x18004f163  test    rbx, rbx
0x18004f166  jz      short loc_18004F16F
0x18004f168  mov     r8, [rbx+0E8h]; unsigned __int16 *
0x18004f16f  mov     r9, r15; unsigned __int16 **
0x18004f172  lea     rdx, aScripts; "Scripts"
0x18004f179  mov     rcx, r12; void *
0x18004f17c  call    ?NlParseOnePath@@YAKPEAXPEAG1PEAPEAG@Z; NlParseOnePath(void *,ushort *,ushort *,ushort * *)
0x18004f181  mov     dword ptr [rbp+57h+var_80], eax
0x18004f184  test    eax, eax
0x18004f186  jz      short loc_18004F1FF
0x18004f188  mov     [r15], r13
0x18004f18b  lea     r15, aScripts; "Scripts"
0x18004f192  mov     dword ptr [rsp+0E0h+phkResult], eax
0x18004f196  mov     r8, r15
0x18004f199  lea     rdx, aFailedToReadAP; "Failed to read a parameter %ws from Net"...
0x18004f1a0  lea     rcx, ?NlGlobalParametersString@@3PAGA; ushort near * NlGlobalParametersString
0x18004f1a7  test    rbx, rbx
0x18004f1aa  jz      short loc_18004F1B3
0x18004f1ac  lea     rcx, ?NlGlobalGroupPolicyString@@3PAGA; ushort near * NlGlobalGroupPolicyString
0x18004f1b3  mov     [rbp+57h+var_58], rcx
0x18004f1b7  mov     r9, rcx
0x18004f1ba  mov     ecx, r14d; unsigned int
0x18004f1bd  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004f1c2  mov     eax, dword ptr [rbp+57h+var_80]
0x18004f1c5  lea     r9, [rbp+57h+var_58]; unsigned __int16 **
0x18004f1c9  mov     [rbp+57h+var_48], rax
0x18004f1cd  mov     edx, 2; unsigned int
0x18004f1d2  lea     rax, [rbp+57h+var_80]
0x18004f1d6  mov     dword ptr [rsp+0E0h+lpcbMaxClassLen], 4; unsigned int
0x18004f1de  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; unsigned __int8 *
0x18004f1e3  mov     ecx, 16ABh; unsigned int
0x18004f1e8  mov     r8d, 40000000h; unsigned int
0x18004f1ee  mov     dword ptr [rsp+0E0h+phkResult], 3; unsigned int
0x18004f1f6  mov     [rbp+57h+var_58+8], r15
0x18004f1fa  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18004f1ff  lea     rax, [rdi+0D0h]
0x18004f206  mov     r9, r13
0x18004f209  test    rbx, rbx
0x18004f20c  jz      short loc_18004F215
0x18004f20e  lea     r9, [rbx+0D0h]; unsigned __int16 **
0x18004f215  mov     r8d, esi; int
0x18004f218  mov     [rsp+0E0h+phkResult], rax; LPVOID *
0x18004f21d  lea     rdx, aDcallowedntlms; "DCAllowedNTLMServers"
0x18004f224  mov     rcx, r12; void *
0x18004f227  call    ?NlParseTStr@@YAKPEAXPEAGHPEAPEAG2@Z; NlParseTStr(void *,ushort *,int,ushort * *,ushort * *)
0x18004f22c  mov     dword ptr [rbp+57h+var_80], eax
0x18004f22f  lea     rax, [rdi+1B8h]
0x18004f236  mov     r9, r13
0x18004f239  test    rbx, rbx
0x18004f23c  jz      short loc_18004F245
0x18004f23e  lea     r9, [rbx+1B8h]; unsigned __int16 **
0x18004f245  xor     r8d, r8d; int
0x18004f248  mov     [rsp+0E0h+phkResult], rax; LPVOID *
0x18004f24d  lea     rdx, aRpcdacl; "RpcDacl"
0x18004f254  mov     rcx, r12; void *
0x18004f257  call    ?NlParseTStr@@YAKPEAXPEAGHPEAPEAG2@Z; NlParseTStr(void *,ushort *,int,ushort * *,ushort * *)
0x18004f25c  mov     dword ptr [rbp+57h+var_80], eax
0x18004f25f  lea     rax, [rdi+1C0h]
0x18004f266  mov     r9, r13
0x18004f269  test    rbx, rbx
0x18004f26c  jz      short loc_18004F275
0x18004f26e  lea     r9, [rbx+1C0h]; unsigned __int16 **
0x18004f275  xor     r8d, r8d; int
0x18004f278  mov     [rsp+0E0h+phkResult], rax; LPVOID *
0x18004f27d  lea     rdx, aRemoteaccessch_1; "RemoteAccessCheckDacl"
0x18004f284  mov     rcx, r12; void *
0x18004f287  call    ?NlParseTStr@@YAKPEAXPEAGHPEAPEAG2@Z; NlParseTStr(void *,ushort *,int,ushort * *,ushort * *)
0x18004f28c  mov     dword ptr [rbp+57h+var_80], eax
0x18004f28f  lea     r15, [rdi+130h]
0x18004f296  mov     r9, r13
0x18004f299  test    rbx, rbx
0x18004f29c  jz      short loc_18004F2A5
0x18004f29e  lea     r9, [rbx+130h]; unsigned __int16 **
0x18004f2a5  xor     r8d, r8d; int
0x18004f2a8  mov     [rsp+0E0h+phkResult], r15; LPVOID *
0x18004f2ad  lea     rdx, aVulnerablechan_1; "VulnerableChannelAllowList"
0x18004f2b4  mov     rcx, r12; void *
0x18004f2b7  call    ?NlParseTStr@@YAKPEAXPEAGHPEAPEAG2@Z; NlParseTStr(void *,ushort *,int,ushort * *,ushort * *)
0x18004f2bc  mov     r8, [r15]
0x18004f2bf  mov     ecx, esi; unsigned int
0x18004f2c1  mov     dword ptr [rbp+57h+var_80], eax
0x18004f2c4  test    r8, r8
0x18004f2c7  jz      short loc_18004F2D7
0x18004f2c9  lea     rdx, aVulnerablechan_2; "   VulnerableChannelAllowList = \"%ws\""...
0x18004f2d0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004f2d5  jmp     short loc_18004F2E3
  ... truncated ...
```
