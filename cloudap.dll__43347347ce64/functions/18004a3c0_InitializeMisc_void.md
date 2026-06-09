# InitializeMisc(void)

- ea: `0x18004a3c0`
- end: `0x18004a525`
- name: `?InitializeMisc@@YAJXZ`
- size: `357`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004b1e0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18004a3c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a3f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a3f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a470`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a3ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a466`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a3ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a466`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18004a3d2`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18004a3d2`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x18004a4bd`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x18004a4bd`

## string_xrefs

- `0x18004a40c`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a485`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a4c9`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a427`: `ConvertStringSecurityDescriptorToSecurityDescriptor`
- `0x18004a4a0`: `ConvertStringSecurityDescriptorToSecurityDescriptor`
- `0x18004a4e4`: `LsaIOpenPolicyTrusted`

## pseudocode

```c
__int64 InitializeMisc(void)
{
  signed int v0; // eax
  unsigned int v1; // ebx
  const char *v2; // r9
  signed int LastError; // eax
  const char *v4; // r9
  const char *v5; // r9
  int v7; // [rsp+20h] [rbp-28h]
  int v8; // [rsp+20h] [rbp-28h]
  int v9; // [rsp+20h] [rbp-28h]

  RtlGetDeviceFamilyInfoEnum(0, &g_ulPlatformId, 0);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:SYD:P(A;;GR;;;AU)(A;;GA;;;SY)", 1u, &g_pSystemSD, 0) )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:SYD:P(A;;GA;;;SY)", 1u, &g_pSystemOnlySD, 0) )
    {
      v1 = LsaIOpenPolicyTrusted(&g_LsaPolicyHandle);
      if ( v1 )
      {
        v5 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v9 = 411;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v1, v5, v9, "LsaIOpenPolicyTrusted", &Class);
      }
      else
      {
        g_bAutoProvisionTBAL = ((g_ulPlatformId - 14) & 0xFFFFFFFD) == 0;
        return 0;
      }
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0xC0070000;
      v4 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      v8 = 407;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        v1,
        v4,
        v8,
        "ConvertStringSecurityDescriptorToSecurityDescriptor",
        &Class);
    }
  }
  else
  {
    v0 = GetLastError();
    v1 = v0;
    if ( v0 > 0 )
      v1 = (unsigned __int16)v0 | 0xC0070000;
    v2 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    v7 = 396;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v1, v2, v7, "ConvertStringSecurityDescriptorToSecurityDescriptor", &Class);
  }
  return v1;
}

```

## disassembly

```asm
0x18004a3c0  push    rbx
0x18004a3c2  sub     rsp, 40h
0x18004a3c6  xor     r8d, r8d
0x18004a3c9  lea     rdx, ?g_ulPlatformId@@3KA; ulong g_ulPlatformId
0x18004a3d0  xor     ecx, ecx
0x18004a3d2  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18004a3d8  xor     r9d, r9d; SecurityDescriptorSize
0x18004a3db  lea     r8, ?g_pSystemSD@@3PEAXEA; SecurityDescriptor
0x18004a3e2  lea     rcx, StringSecurityDescriptor; "O:SYD:P(A;;GR;;;AU)(A;;GA;;;SY)"
0x18004a3e9  lea     edx, [r9+1]; StringSDRevision
0x18004a3ed  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004a3f3  test    eax, eax
0x18004a3f5  jnz     short loc_18004A451
0x18004a3f7  call    cs:__imp_GetLastError
0x18004a3fd  mov     ebx, eax
0x18004a3ff  test    eax, eax
0x18004a401  jle     short loc_18004A40C
0x18004a403  movzx   ebx, ax
0x18004a406  or      ebx, 0C0070000h
0x18004a40c  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a413  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a418  mov     r9, rax
0x18004a41b  lea     rax, Class
0x18004a422  mov     [rsp+48h+var_18], rax
0x18004a427  lea     rax, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x18004a42e  mov     [rsp+48h+var_20], rax
0x18004a433  mov     [rsp+48h+var_28], 18Ch
0x18004a43b  mov     r8d, ebx
0x18004a43e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004a445  xor     ecx, ecx
0x18004a447  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004a44c  jmp     loc_18004A51D
0x18004a451  xor     r9d, r9d; SecurityDescriptorSize
0x18004a454  lea     r8, ?g_pSystemOnlySD@@3PEAXEA; SecurityDescriptor
0x18004a45b  lea     rcx, aOSydPAGaSy; "O:SYD:P(A;;GA;;;SY)"
0x18004a462  lea     edx, [r9+1]; StringSDRevision
0x18004a466  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004a46c  test    eax, eax
0x18004a46e  jnz     short loc_18004A4B6
0x18004a470  call    cs:__imp_GetLastError
0x18004a476  mov     ebx, eax
0x18004a478  test    eax, eax
0x18004a47a  jle     short loc_18004A485
0x18004a47c  movzx   ebx, ax
0x18004a47f  or      ebx, 0C0070000h
0x18004a485  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a48c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a491  mov     r9, rax
0x18004a494  lea     rax, Class
0x18004a49b  mov     [rsp+48h+var_18], rax
0x18004a4a0  lea     rax, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x18004a4a7  mov     [rsp+48h+var_20], rax
0x18004a4ac  mov     [rsp+48h+var_28], 197h
0x18004a4b4  jmp     short loc_18004A43B
0x18004a4b6  lea     rcx, ?g_LsaPolicyHandle@@3PEAXEA; void * g_LsaPolicyHandle
0x18004a4bd  call    cs:__imp_LsaIOpenPolicyTrusted
0x18004a4c3  mov     ebx, eax
0x18004a4c5  test    eax, eax
0x18004a4c7  jz      short loc_18004A4FD
0x18004a4c9  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a4d0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a4d5  mov     r9, rax
0x18004a4d8  lea     rax, Class
0x18004a4df  mov     [rsp+48h+var_18], rax
0x18004a4e4  lea     rax, aLsaiopenpolicy; "LsaIOpenPolicyTrusted"
0x18004a4eb  mov     [rsp+48h+var_20], rax
0x18004a4f0  mov     [rsp+48h+var_28], 19Bh
0x18004a4f8  jmp     loc_18004A43B
0x18004a4fd  mov     eax, cs:?g_ulPlatformId@@3KA; ulong g_ulPlatformId
0x18004a503  add     eax, 0FFFFFFF2h
0x18004a506  mov     cs:?g_bAutoProvisionTBAL@@3EA, 0; uchar g_bAutoProvisionTBAL
0x18004a50d  test    eax, 0FFFFFFFDh
0x18004a512  jnz     short loc_18004A51B
0x18004a514  mov     cs:?g_bAutoProvisionTBAL@@3EA, 1; uchar g_bAutoProvisionTBAL
0x18004a51b  xor     ebx, ebx
0x18004a51d  mov     eax, ebx
0x18004a51f  add     rsp, 40h
0x18004a523  pop     rbx
0x18004a524  retn
```
