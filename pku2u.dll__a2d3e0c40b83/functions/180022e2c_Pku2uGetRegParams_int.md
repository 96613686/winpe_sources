# Pku2uGetRegParams(int)

- ea: `0x180022e2c`
- end: `0x1800233e4`
- name: `?Pku2uGetRegParams@@YAXH@Z`
- size: `1464`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023520`
- `0x1800238f0`

## callees

- `0x1800057f0`
- `0x1800179f0`
- `0x180018870`
- `0x18001fc04`
- `0x1800210f0`
- `0x180022e2c`
- `0x1800233ec`
- `0x180023cb8`
- `0x180023ce0`
- `0x180023d20`
- `0x180023d9c`
- `0x18002fcd0`
- `0x1800302c8`
- `0x180044f80`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180023081`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180023081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002315c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002315c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022fe7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023020`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800233af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800233bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022fe7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023020`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800233af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800233bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022fd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002300c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022fd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002300c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002323f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800232f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002323f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800232f1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800231a2`
- `ntdll!RtlLeaveCriticalSection` at `0x180023205`
- `ntdll!RtlLeaveCriticalSection` at `0x1800231a2`
- `ntdll!RtlLeaveCriticalSection` at `0x180023205`
- `ntdll!RtlEnterCriticalSection` at `0x1800230fb`
- `ntdll!RtlEnterCriticalSection` at `0x1800230fb`

## string_xrefs

- `0x180022e78`: `MaxTokenSize`

## pseudocode

```c
void __fastcall Pku2uGetRegParams(int a1)
{
  unsigned int v2; // r8d
  PRTL_GENERIC_TABLE v3; // rbx
  union _LARGE_INTEGER v4; // rax
  PRTL_SPLAY_LINKS TableRoot; // r8
  struct _CERT_X942_DH_PARAMETERS *v6; // r8
  char LastError; // al
  const char *v8; // r8
  const char *v9; // r8
  LSTATUS Value; // eax
  unsigned int v11; // eax
  unsigned int v12; // ebx
  void *v13; // rdi
  int v14; // esi
  __int128 v15; // xmm0
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v17; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  LPBYTE lpData[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v22; // [rsp+60h] [rbp-A0h] BYREF
  union _LARGE_INTEGER v23; // [rsp+68h] [rbp-98h] BYREF
  union _LARGE_INTEGER v24; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v25[3]; // [rsp+80h] [rbp-80h] BYREF
  int v26; // [rsp+98h] [rbp-68h]
  const wchar_t *v27; // [rsp+A0h] [rbp-60h]
  unsigned int *v28; // [rsp+A8h] [rbp-58h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  int v30; // [rsp+B8h] [rbp-48h]
  const wchar_t *v31; // [rsp+C0h] [rbp-40h]
  unsigned int *v32; // [rsp+C8h] [rbp-38h]
  __int64 v33; // [rsp+D0h] [rbp-30h]
  int v34; // [rsp+D8h] [rbp-28h]
  const wchar_t *v35; // [rsp+E0h] [rbp-20h]
  unsigned int *v36; // [rsp+E8h] [rbp-18h]
  __int64 v37; // [rsp+F0h] [rbp-10h]
  int v38; // [rsp+F8h] [rbp-8h]
  const wchar_t *v39; // [rsp+100h] [rbp+0h]
  int *v40; // [rsp+108h] [rbp+8h]
  __int64 v41; // [rsp+110h] [rbp+10h]
  int v42; // [rsp+118h] [rbp+18h]
  const wchar_t *v43; // [rsp+120h] [rbp+20h]
  unsigned int *v44; // [rsp+128h] [rbp+28h]
  __int64 v45; // [rsp+130h] [rbp+30h]
  int v46; // [rsp+138h] [rbp+38h]
  const wchar_t *v47; // [rsp+140h] [rbp+40h]
  unsigned int *v48; // [rsp+148h] [rbp+48h]
  __int64 v49; // [rsp+150h] [rbp+50h]
  int v50; // [rsp+158h] [rbp+58h]
  const wchar_t *v51; // [rsp+160h] [rbp+60h]
  unsigned int *v52; // [rsp+168h] [rbp+68h]
  __int64 v53; // [rsp+170h] [rbp+70h]
  int v54; // [rsp+178h] [rbp+78h]
  const wchar_t *v55; // [rsp+180h] [rbp+80h]
  unsigned int *v56; // [rsp+188h] [rbp+88h]
  __int64 v57; // [rsp+190h] [rbp+90h]
  int v58; // [rsp+198h] [rbp+98h]

  v17 = Pku2uGlobalMODPDHModulusSize;
  v16 = Pku2uGlobalPreferWellknownMODPDHDomainParameters;
  hKey = 0;
  v25[0] = L"MaxTokenSize";
  phkResult = 0;
  v25[1] = &Pku2uGlobalMaxTokenSize;
  v22 = 0;
  v27 = L"SkewTime";
  v25[2] = 12000;
  v28 = &v22;
  v26 = 1;
  v31 = L"MODPDHModulusSize";
  v29 = 5;
  v32 = &v17;
  v30 = 0;
  v35 = L"MinMODPDHModulusSize";
  v36 = &Pku2uGlobalMinMODPDHModulusSize;
  v39 = L"PreferWellKnownMODPDHDomainParameters";
  v40 = &v16;
  v43 = L"LeafOnly";
  v44 = &Pku2uGlobalSendOnlyLeafCertificate;
  v47 = L"SupportInitiatorFirst";
  v48 = &Pku2uGlobalSupportInitiatorFirst;
  v51 = L"SupportLocalHost";
  v52 = &Pku2uGlobalSupportLocalHost;
  v55 = L"AlwaysPrompt";
  v56 = &Pku2uGlobalAlwaysPrompt;
  *(_OWORD *)lpData = 0;
  v33 = 1024;
  v34 = 1;
  v37 = 1024;
  v38 = 1;
  v41 = 1;
  v42 = 1;
  v45 = 1;
  v46 = 1;
  v49 = 1;
  v50 = 1;
  v53 = 0;
  v54 = 1;
  v57 = 0;
  v58 = 1;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Lsa\\pku2u\\Parameters",
         0,
         0x20019u,
         &hKey)
    && hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\pku2u\\Parameters",
         0,
         0x20019u,
         &phkResult)
    && phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( !hKey && !phkResult && !a1 )
    goto LABEL_53;
  Pku2uGetRegistryDwords(hKey, phkResult, v2, (struct _PKU2U_REG_PARAMETER *)v25);
  v3 = Pku2uGlobalAuthenticators;
  v4.QuadPart = 600000000LL * v22;
  Pku2uGlobalSkewTime = v4;
  if ( Pku2uGlobalAuthenticators[1].TableRoot != (PRTL_SPLAY_LINKS)v4.QuadPart )
  {
    SystemTimeAsFileTime = 0;
    Pku2uGlobalAuthenticators[1].TableRoot = (PRTL_SPLAY_LINKS)v4.QuadPart;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    TableRoot = v3[1].TableRoot;
    v24.QuadPart = *(_QWORD *)&SystemTimeAsFileTime - (_QWORD)TableRoot;
    v23.QuadPart = (LONGLONG)TableRoot + *(_QWORD *)&SystemTimeAsFileTime;
    CAuthenticatorList::Age(v3, &v24, &v23);
  }
  if ( !a1
    && (v16 != Pku2uGlobalPreferWellknownMODPDHDomainParameters
     || v17 != Pku2uGlobalMODPDHModulusSize
     || !Pku2uGlobalDHParametersInitialized) )
  {
    RtlEnterCriticalSection(&Pku2uGlobalDHParametersLock);
    if ( Pku2uGlobalDHAvailable )
    {
      Pku2uFreeDHParameters((struct _CERT_X942_DH_PARAMETERS *)&Pku2uGlobalDHParameters);
      if ( Pku2uGlobalDHAlgorithm.Parameters.pbData )
      {
        Pku2uFree(Pku2uGlobalDHAlgorithm.Parameters.pbData);
        Pku2uGlobalDHAlgorithm.Parameters.pbData = 0;
      }
      if ( !Pku2uGenerateDHAlgorithmId(v17, v16, v6, &Pku2uGlobalDHAlgorithm) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          v8 = "true";
          if ( !v16 )
            v8 = "false";
          WPP_SF_dsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)&WPP_7baf66d6931d3ad9b39b627cc97f3291_Traceguids,
            v17,
            (__int64)v8,
            LastError);
        }
        RtlLeaveCriticalSection(&Pku2uGlobalDHParametersLock);
        goto LABEL_32;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v9 = "true";
        if ( !v16 )
          v9 = "false";
        WPP_SF_ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)&WPP_7baf66d6931d3ad9b39b627cc97f3291_Traceguids,
          v17,
          (__int64)v9);
      }
    }
    Pku2uGlobalPreferWellknownMODPDHDomainParameters = v16;
    Pku2uGlobalMODPDHModulusSize = v17;
    RtlLeaveCriticalSection(&Pku2uGlobalDHParametersLock);
    Pku2uGlobalDHParametersInitialized = 1;
  }
LABEL_32:
  SystemTimeAsFileTime.dwLowDateTime = 0;
  Value = RegQueryValueExW(hKey, L"DHDomainParameters", 0, (LPDWORD)&SystemTimeAsFileTime, lpData[1], (LPDWORD)lpData);
  if ( Value == 2 )
  {
    if ( *((_QWORD *)&xmmword_180054A38 + 1) )
    {
      Pku2uFree(*((void **)&xmmword_180054A38 + 1));
      Pku2uAddWellknownDomainParameters(0x400u, 0, 0);
    }
    xmmword_180054A38 = 0;
    goto LABEL_53;
  }
  if ( Value )
    goto LABEL_53;
  lpData[1] = (LPBYTE)basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, LODWORD(lpData[0]));
  if ( !lpData[1] )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_7baf66d6931d3ad9b39b627cc97f3291_Traceguids);
    goto LABEL_53;
  }
  v11 = RegQueryValueExW(hKey, L"DHDomainParameters", 0, (LPDWORD)&SystemTimeAsFileTime, lpData[1], (LPDWORD)lpData);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_7baf66d6931d3ad9b39b627cc97f3291_Traceguids, v11);
    goto LABEL_53;
  }
  if ( SystemTimeAsFileTime.dwLowDateTime != 3 )
  {
LABEL_53:
    if ( lpData[1] )
      Pku2uFree(lpData[1]);
    goto LABEL_55;
  }
  v12 = (unsigned int)lpData[0];
  v13 = (void *)*((_QWORD *)&xmmword_180054A38 + 1);
  if ( (_DWORD)xmmword_180054A38 != LODWORD(lpData[0])
    || (v14 = 0, memcmp_0(lpData[1], *((const void **)&xmmword_180054A38 + 1), LODWORD(lpData[0]))) )
  {
    v14 = 1;
  }
  if ( v13 )
  {
    Pku2uFree(v13);
    v12 = (unsigned int)lpData[0];
  }
  v15 = *(_OWORD *)lpData;
  lpData[1] = 0;
  xmmword_180054A38 = v15;
  if ( v14 )
  {
    Pku2uAddWellknownDomainParameters(Pku2uGlobalMinMODPDHModulusSize, 0, v12);
    goto LABEL_53;
  }
LABEL_55:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x180022e2c  push    rbp
0x180022e2e  push    rbx
0x180022e2f  push    rsi
0x180022e30  push    rdi
0x180022e31  push    r14
0x180022e33  push    r15
0x180022e35  lea     rbp, [rsp-0B8h]
0x180022e3d  sub     rsp, 1B8h
0x180022e44  mov     rax, cs:__security_cookie
0x180022e4b  xor     rax, rsp
0x180022e4e  mov     [rbp+0E0h+var_40], rax
0x180022e55  mov     eax, cs:?Pku2uGlobalMODPDHModulusSize@@3KA; ulong Pku2uGlobalMODPDHModulusSize
0x180022e5b  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Lsa"...
0x180022e62  mov     [rsp+1E0h+var_1AC], eax
0x180022e66  xor     r14d, r14d
0x180022e69  mov     eax, cs:?Pku2uGlobalPreferWellknownMODPDHDomainParameters@@3KA; ulong Pku2uGlobalPreferWellknownMODPDHDomainParameters
0x180022e6f  mov     edi, ecx
0x180022e71  mov     [rsp+1E0h+var_1B0], eax
0x180022e75  xorps   xmm0, xmm0
0x180022e78  lea     rax, aMaxtokensize; "MaxTokenSize"
0x180022e7f  mov     [rsp+1E0h+hKey], r14
0x180022e84  mov     [rbp+0E0h+var_160], rax
0x180022e88  lea     r15d, [r14+1]
0x180022e8c  lea     rax, ?Pku2uGlobalMaxTokenSize@@3KA; ulong Pku2uGlobalMaxTokenSize
0x180022e93  mov     [rsp+1E0h+var_198], r14
0x180022e98  mov     [rbp+0E0h+var_158], rax
0x180022e9c  mov     ebx, 20019h
0x180022ea1  lea     rax, aSkewtime; "SkewTime"
0x180022ea8  mov     [rsp+1E0h+var_180], r14d
0x180022ead  mov     [rbp+0E0h+var_140], rax
0x180022eb1  mov     rsi, 0FFFFFFFF80000002h
0x180022eb8  lea     rax, [rsp+1E0h+var_180]
0x180022ebd  mov     [rbp+0E0h+var_150], 2EE0h
0x180022ec5  mov     [rbp+0E0h+var_138], rax
0x180022ec9  mov     r9d, ebx; samDesired
0x180022ecc  lea     rax, aModpdhmoduluss; "MODPDHModulusSize"
0x180022ed3  mov     [rbp+0E0h+var_148], r15d
0x180022ed7  mov     [rbp+0E0h+var_120], rax
0x180022edb  xor     r8d, r8d; ulOptions
0x180022ede  lea     rax, [rsp+1E0h+var_1AC]
0x180022ee3  mov     [rbp+0E0h+var_130], 5
0x180022eeb  mov     [rbp+0E0h+var_118], rax
0x180022eef  mov     rcx, rsi; hKey
0x180022ef2  lea     rax, aMinmodpdhmodul; "MinMODPDHModulusSize"
0x180022ef9  mov     [rbp+0E0h+var_128], r14d
0x180022efd  mov     [rbp+0E0h+var_100], rax
0x180022f01  lea     rax, ?Pku2uGlobalMinMODPDHModulusSize@@3KA; ulong Pku2uGlobalMinMODPDHModulusSize
0x180022f08  mov     [rbp+0E0h+var_F8], rax
0x180022f0c  lea     rax, aPreferwellknow; "PreferWellKnownMODPDHDomainParameters"
0x180022f13  mov     [rbp+0E0h+var_E0], rax
0x180022f17  lea     rax, [rsp+1E0h+var_1B0]
0x180022f1c  mov     [rbp+0E0h+var_D8], rax
0x180022f20  lea     rax, aLeafonly; "LeafOnly"
0x180022f27  mov     [rbp+0E0h+var_C0], rax
0x180022f2b  lea     rax, ?Pku2uGlobalSendOnlyLeafCertificate@@3KA; ulong Pku2uGlobalSendOnlyLeafCertificate
0x180022f32  mov     [rbp+0E0h+var_B8], rax
0x180022f36  lea     rax, aSupportinitiat; "SupportInitiatorFirst"
0x180022f3d  mov     [rbp+0E0h+var_A0], rax
0x180022f41  lea     rax, ?Pku2uGlobalSupportInitiatorFirst@@3KA; ulong Pku2uGlobalSupportInitiatorFirst
0x180022f48  mov     [rbp+0E0h+var_98], rax
0x180022f4c  lea     rax, aSupportlocalho; "SupportLocalHost"
0x180022f53  mov     [rbp+0E0h+var_80], rax
0x180022f57  lea     rax, ?Pku2uGlobalSupportLocalHost@@3KA; ulong Pku2uGlobalSupportLocalHost
0x180022f5e  mov     [rbp+0E0h+var_78], rax
0x180022f62  lea     rax, aAlwaysprompt; "AlwaysPrompt"
0x180022f69  mov     [rbp+0E0h+var_60], rax
0x180022f70  lea     rax, ?Pku2uGlobalAlwaysPrompt@@3KA; ulong Pku2uGlobalAlwaysPrompt
0x180022f77  mov     [rbp+0E0h+var_58], rax
0x180022f7e  lea     rax, [rsp+1E0h+hKey]
0x180022f83  mov     [rsp+1E0h+phkResult], rax; phkResult
0x180022f88  movups  xmmword ptr [rsp+1E0h+lpData], xmm0
0x180022f8d  mov     [rbp+0E0h+var_110], 400h
0x180022f95  mov     [rbp+0E0h+var_108], r15d
0x180022f99  mov     [rbp+0E0h+var_F0], 400h
0x180022fa1  mov     [rbp+0E0h+var_E8], r15d
0x180022fa5  mov     [rbp+0E0h+var_D0], r15
0x180022fa9  mov     [rbp+0E0h+var_C8], r15d
0x180022fad  mov     [rbp+0E0h+var_B0], r15
0x180022fb1  mov     [rbp+0E0h+var_A8], r15d
0x180022fb5  mov     [rbp+0E0h+var_90], r15
0x180022fb9  mov     [rbp+0E0h+var_88], r15d
0x180022fbd  mov     [rbp+0E0h+var_70], r14
0x180022fc1  mov     [rbp+0E0h+var_68], r15d
0x180022fc5  mov     [rbp+0E0h+var_50], r14
0x180022fcc  mov     [rbp+0E0h+var_48], r15d
0x180022fd3  call    cs:__imp_RegOpenKeyExW
0x180022fd9  test    eax, eax
0x180022fdb  jz      short loc_180022FF2
0x180022fdd  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180022fe2  test    rcx, rcx
0x180022fe5  jz      short loc_180022FF2
0x180022fe7  call    cs:__imp_RegCloseKey
0x180022fed  mov     [rsp+1E0h+hKey], r14
0x180022ff2  lea     rax, [rsp+1E0h+var_198]
0x180022ff7  mov     r9d, ebx; samDesired
0x180022ffa  xor     r8d, r8d; ulOptions
0x180022ffd  mov     [rsp+1E0h+phkResult], rax; phkResult
0x180023002  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180023009  mov     rcx, rsi; hKey
0x18002300c  call    cs:__imp_RegOpenKeyExW
0x180023012  test    eax, eax
0x180023014  jz      short loc_18002302B
0x180023016  mov     rcx, [rsp+1E0h+var_198]; hKey
0x18002301b  test    rcx, rcx
0x18002301e  jz      short loc_18002302B
0x180023020  call    cs:__imp_RegCloseKey
0x180023026  mov     [rsp+1E0h+var_198], r14
0x18002302b  cmp     [rsp+1E0h+hKey], r14
0x180023030  jnz     short loc_180023041
0x180023032  cmp     [rsp+1E0h+var_198], r14
0x180023037  jnz     short loc_180023041
0x180023039  test    edi, edi
0x18002303b  jz      loc_180023396
0x180023041  mov     rdx, [rsp+1E0h+var_198]; HKEY
0x180023046  lea     r9, [rbp+0E0h+var_160]; struct _PKU2U_REG_PARAMETER *
0x18002304a  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18002304f  call    ?Pku2uGetRegistryDwords@@YAKPEAUHKEY__@@0KPEAU_PKU2U_REG_PARAMETER@@@Z; Pku2uGetRegistryDwords(HKEY__ *,HKEY__ *,ulong,_PKU2U_REG_PARAMETER *)
0x180023054  mov     eax, [rsp+1E0h+var_180]
0x180023058  mov     rbx, cs:?Pku2uGlobalAuthenticators@@3PEAVCAuthenticatorList@@EA; CAuthenticatorList * Pku2uGlobalAuthenticators
0x18002305f  imul    rax, 23C34600h
0x180023066  mov     cs:?Pku2uGlobalSkewTime@@3T_LARGE_INTEGER@@A, rax; _LARGE_INTEGER Pku2uGlobalSkewTime
0x18002306d  cmp     [rbx+48h], rax
0x180023071  jz      short loc_1800230B6
0x180023073  lea     rcx, [rsp+1E0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180023078  mov     qword ptr [rsp+1E0h+SystemTimeAsFileTime.dwLowDateTime], r14
0x18002307d  mov     [rbx+48h], rax
0x180023081  call    cs:__imp_GetSystemTimeAsFileTime
0x180023087  mov     r8, [rbx+48h]
0x18002308b  mov     rcx, rbx; Table
0x18002308e  mov     rax, qword ptr [rsp+1E0h+SystemTimeAsFileTime.dwLowDateTime]
0x180023093  mov     rdx, rax
0x180023096  sub     rdx, r8
0x180023099  mov     qword ptr [rsp+1E0h+var_170], rdx
0x18002309e  lea     rdx, [r8+rax]
0x1800230a2  mov     qword ptr [rsp+1E0h+var_178], rdx
0x1800230a7  lea     r8, [rsp+1E0h+var_178]; union _LARGE_INTEGER *
0x1800230ac  lea     rdx, [rsp+1E0h+var_170]; union _LARGE_INTEGER *
0x1800230b1  call    ?Age@CAuthenticatorList@@AEAAKAEBT_LARGE_INTEGER@@0@Z; CAuthenticatorList::Age(_LARGE_INTEGER const &,_LARGE_INTEGER const &)
0x1800230b6  lea     rbx, WPP_GLOBAL_Control
0x1800230bd  lea     rsi, WPP_7baf66d6931d3ad9b39b627cc97f3291_Traceguids
0x1800230c4  test    edi, edi
0x1800230c6  jnz     loc_180023212
0x1800230cc  mov     eax, cs:?Pku2uGlobalPreferWellknownMODPDHDomainParameters@@3KA; ulong Pku2uGlobalPreferWellknownMODPDHDomainParameters
0x1800230d2  cmp     [rsp+1E0h+var_1B0], eax
0x1800230d6  jnz     short loc_1800230F1
0x1800230d8  mov     eax, cs:?Pku2uGlobalMODPDHModulusSize@@3KA; ulong Pku2uGlobalMODPDHModulusSize
0x1800230de  cmp     [rsp+1E0h+var_1AC], eax
0x1800230e2  jnz     short loc_1800230F1
0x1800230e4  cmp     cs:?Pku2uGlobalDHParametersInitialized@@3HA, r14d; int Pku2uGlobalDHParametersInitialized
0x1800230eb  jnz     loc_180023212
0x1800230f1  lea     rdi, ?Pku2uGlobalDHParametersLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION Pku2uGlobalDHParametersLock
0x1800230f8  mov     rcx, rdi; CriticalSection
0x1800230fb  call    cs:__imp_RtlEnterCriticalSection
0x180023101  cmp     cs:?Pku2uGlobalDHAvailable@@3HA, r14d; int Pku2uGlobalDHAvailable
0x180023108  jz      loc_1800231EE
0x18002310e  lea     rcx, ?Pku2uGlobalDHParameters@@3U_CERT_X942_DH_PARAMETERS@@A; struct _CERT_X942_DH_PARAMETERS *
0x180023115  call    ?Pku2uFreeDHParameters@@YAXPEAU_CERT_X942_DH_PARAMETERS@@@Z; Pku2uFreeDHParameters(_CERT_X942_DH_PARAMETERS *)
0x18002311a  mov     rcx, cs:?Pku2uGlobalDHAlgorithm@@3U_CRYPT_ALGORITHM_IDENTIFIER@@A.Parameters.pbData; void *
0x180023121  test    rcx, rcx
0x180023124  jz      short loc_180023132
0x180023126  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18002312b  mov     cs:?Pku2uGlobalDHAlgorithm@@3U_CRYPT_ALGORITHM_IDENTIFIER@@A.Parameters.pbData, r14; _CRYPT_ALGORITHM_IDENTIFIER Pku2uGlobalDHAlgorithm ...
0x180023132  mov     edx, [rsp+1E0h+var_1B0]; int
0x180023136  lea     r9, ?Pku2uGlobalDHAlgorithm@@3U_CRYPT_ALGORITHM_IDENTIFIER@@A; struct _CRYPT_ALGORITHM_IDENTIFIER *
0x18002313d  mov     ecx, [rsp+1E0h+var_1AC]; unsigned int
0x180023141  call    ?Pku2uGenerateDHAlgorithmId@@YAHKHPEAU_CERT_X942_DH_PARAMETERS@@PEAU_CRYPT_ALGORITHM_IDENTIFIER@@@Z; Pku2uGenerateDHAlgorithmId(ulong,int,_CERT_X942_DH_PARAMETERS *,_CRYPT_ALGORITHM_IDENTIFIER *)
0x180023146  test    eax, eax
0x180023148  jnz     short loc_1800231AA
0x18002314a  mov     rax, cs:WPP_GLOBAL_Control
0x180023151  cmp     rax, rbx
0x180023154  jz      short loc_18002319F
0x180023156  test    [rax+1Ch], r15b
0x18002315a  jz      short loc_18002319F
0x18002315c  call    cs:__imp_GetLastError
0x180023162  cmp     [rsp+1E0h+var_1B0], r14d
0x180023167  lea     rdx, aFalse; "false"
0x18002316e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023175  lea     r8, aTrue; "true"
0x18002317c  mov     r9d, [rsp+1E0h+var_1AC]
0x180023181  cmovz   r8, rdx
0x180023185  mov     dword ptr [rsp+1E0h+lpcbData], eax
0x180023189  mov     edx, 0Fh
0x18002318e  mov     [rsp+1E0h+phkResult], r8
0x180023193  mov     r8, rsi
0x180023196  mov     rcx, [rcx+10h]
0x18002319a  call    WPP_SF_dsd
0x18002319f  mov     rcx, rdi; CriticalSection
0x1800231a2  call    cs:__imp_RtlLeaveCriticalSection
0x1800231a8  jmp     short loc_180023212
0x1800231aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231b1  cmp     rcx, rbx
0x1800231b4  jz      short loc_1800231EE
0x1800231b6  test    byte ptr [rcx+1Ch], 2
0x1800231ba  jz      short loc_1800231EE
0x1800231bc  cmp     [rsp+1E0h+var_1B0], r14d
0x1800231c1  lea     rdx, aFalse; "false"
0x1800231c8  mov     r9d, [rsp+1E0h+var_1AC]
0x1800231cd  lea     r8, aTrue; "true"
0x1800231d4  mov     rcx, [rcx+10h]
0x1800231d8  cmovz   r8, rdx
0x1800231dc  mov     [rsp+1E0h+phkResult], r8
0x1800231e1  mov     edx, 10h
0x1800231e6  mov     r8, rsi
0x1800231e9  call    WPP_SF_ds
0x1800231ee  mov     eax, [rsp+1E0h+var_1B0]
0x1800231f2  mov     rcx, rdi; CriticalSection
0x1800231f5  mov     cs:?Pku2uGlobalPreferWellknownMODPDHDomainParameters@@3KA, eax; ulong Pku2uGlobalPreferWellknownMODPDHDomainParameters
0x1800231fb  mov     eax, [rsp+1E0h+var_1AC]
0x1800231ff  mov     cs:?Pku2uGlobalMODPDHModulusSize@@3KA, eax; ulong Pku2uGlobalMODPDHModulusSize
0x180023205  call    cs:__imp_RtlLeaveCriticalSection
0x18002320b  mov     cs:?Pku2uGlobalDHParametersInitialized@@3HA, r15d; int Pku2uGlobalDHParametersInitialized
0x180023212  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180023217  lea     rax, [rsp+1E0h+lpData]
0x18002321c  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x180023221  lea     r9, [rsp+1E0h+SystemTimeAsFileTime]; lpType
0x180023226  mov     rax, [rsp+1E0h+lpData+8]
0x18002322b  lea     rdx, ValueName; "DHDomainParameters"
0x180023232  xor     r8d, r8d; lpReserved
0x180023235  mov     [rsp+1E0h+phkResult], rax; lpData
0x18002323a  mov     [rsp+1E0h+SystemTimeAsFileTime.dwLowDateTime], r14d
0x18002323f  call    cs:__imp_RegQueryValueExW
0x180023245  cmp     eax, 2
0x180023248  jnz     short loc_180023279
0x18002324a  mov     rcx, qword ptr cs:xmmword_180054A38+8; void *
0x180023251  test    rcx, rcx
0x180023254  jz      short loc_18002326A
0x180023256  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18002325b  xor     r8d, r8d; unsigned int
0x18002325e  xor     edx, edx; unsigned __int8 *
0x180023260  mov     ecx, 400h; unsigned int
0x180023265  call    ?Pku2uAddWellknownDomainParameters@@YAJKPEAEK@Z; Pku2uAddWellknownDomainParameters(ulong,uchar *,ulong)
0x18002326a  xorps   xmm0, xmm0
0x18002326d  movups  cs:xmmword_180054A38, xmm0
0x180023274  jmp     loc_180023396
0x180023279  test    eax, eax
0x18002327b  jnz     loc_180023396
0x180023281  mov     edx, dword ptr [rsp+1E0h+lpData]; unsigned __int64
0x180023285  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18002328c  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180023291  mov     [rsp+1E0h+lpData+8], rax
0x180023296  test    rax, rax
0x180023299  jnz     short loc_1800232C9
0x18002329b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800232a2  cmp     rcx, rbx
0x1800232a5  jz      loc_180023396
0x1800232ab  test    [rcx+1Ch], r15b
0x1800232af  jz      loc_180023396
0x1800232b5  mov     rcx, [rcx+10h]
0x1800232b9  lea     edx, [rax+11h]
0x1800232bc  mov     r8, rsi
0x1800232bf  call    WPP_SF_
0x1800232c4  jmp     loc_180023396
0x1800232c9  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1800232ce  lea     rax, [rsp+1E0h+lpData]
0x1800232d3  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x1800232d8  lea     r9, [rsp+1E0h+SystemTimeAsFileTime]; lpType
0x1800232dd  mov     rax, [rsp+1E0h+lpData+8]
0x1800232e2  lea     rdx, ValueName; "DHDomainParameters"
0x1800232e9  xor     r8d, r8d; lpReserved
0x1800232ec  mov     [rsp+1E0h+phkResult], rax; lpData
0x1800232f1  call    cs:__imp_RegQueryValueExW
0x1800232f7  test    eax, eax
0x1800232f9  jz      short loc_18002332B
0x1800232fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180023302  cmp     rcx, rbx
0x180023305  jz      loc_180023396
0x18002330b  test    [rcx+1Ch], r15b
0x18002330f  jz      loc_180023396
0x180023315  mov     rcx, [rcx+10h]
0x180023319  mov     edx, 12h
0x18002331e  mov     r9d, eax
0x180023321  mov     r8, rsi
0x180023324  call    WPP_SF_d
0x180023329  jmp     short loc_180023396
0x18002332b  cmp     [rsp+1E0h+SystemTimeAsFileTime.dwLowDateTime], 3
0x180023330  jnz     short loc_180023396
0x180023332  mov     ebx, dword ptr [rsp+1E0h+lpData]
0x180023336  cmp     dword ptr cs:xmmword_180054A38, ebx
0x18002333c  mov     rdi, qword ptr cs:xmmword_180054A38+8
0x180023343  jnz     short loc_18002335C
0x180023345  mov     rcx, [rsp+1E0h+lpData+8]; Buf1
0x18002334a  mov     r8d, ebx; Size
0x18002334d  mov     rdx, rdi; Buf2
0x180023350  mov     esi, r14d
0x180023353  call    memcmp_0
0x180023358  test    eax, eax
0x18002335a  jz      short loc_18002335F
0x18002335c  mov     esi, r15d
0x18002335f  test    rdi, rdi
0x180023362  jz      short loc_180023370
0x180023364  mov     rcx, rdi; void *
0x180023367  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18002336c  mov     ebx, dword ptr [rsp+1E0h+lpData]
0x180023370  movups  xmm0, xmmword ptr [rsp+1E0h+lpData]
0x180023375  mov     [rsp+1E0h+lpData+8], r14
0x18002337a  movdqu  cs:xmmword_180054A38, xmm0
0x180023382  test    esi, esi
0x180023384  jz      short loc_1800233A5
0x180023386  mov     ecx, cs:?Pku2uGlobalMinMODPDHModulusSize@@3KA; unsigned int
0x18002338c  mov     r8d, ebx; unsigned int
  ... truncated ...
```
