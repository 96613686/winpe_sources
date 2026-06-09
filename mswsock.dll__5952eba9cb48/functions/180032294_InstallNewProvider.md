# InstallNewProvider

- ea: `0x180032294`
- end: `0x1800326c8`
- name: `InstallNewProvider`
- size: `1076`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800328c0`

## callees

- `0x1800222f0`
- `0x180030cdc`
- `0x1800317c8`
- `0x180031918`
- `0x180031e74`
- `0x180032294`
- `0x1800327cc`
- `0x18003281c`
- `0x180032848`
- `0x180032864`
- `0x18003388c`
- `0x180035538`
- `0x18003592c`
- `0x180035d84`
- `0x18003ae8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180032524`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003253e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180032524`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003253e`
- `ntdll!RtlFreeHeap` at `0x1800325ca`
- `ntdll!RtlFreeHeap` at `0x1800325ca`
- `WS2_32!WSCDeinstallProviderEx` at `0x1800325ff`
- `WS2_32!WSCDeinstallProviderEx` at `0x180032638`
- `WS2_32!WSCDeinstallProviderEx` at `0x1800325ff`
- `WS2_32!WSCDeinstallProviderEx` at `0x180032638`
- `WS2_32!WSCInstallProviderEx` at `0x18003243a`
- `WS2_32!WSCInstallProviderEx` at `0x1800324d9`
- `WS2_32!WSCInstallProviderEx` at `0x18003243a`
- `WS2_32!WSCInstallProviderEx` at `0x1800324d9`

## string_xrefs

- `0x18003240e`: `%SystemRoot%\system32\mswsock.dll`
- `0x1800324b3`: `%SystemRoot%\system32\mswsock.dll`
- `0x180032342`: `BuildWinsock2ProtocolList failed`
- `0x1800323f0`: `CreateMigrationRegistryForProvider failed`
- `0x180032453`: `Failed to install provider; will try sanitizing the configuration for this provider before trying again`
- `0x1800324a0`: `Retrying installation`
- `0x1800324ed`: `2nd attempt to install provider failed`
- `0x180032504`: `SanitizeWinsock2ConfigForProvider failed`
- `0x1800325e8`: `Uninstalling provider, since there was an error`

## pseudocode

```c
__int64 __fastcall InstallNewProvider(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7,
        __int64 a8,
        int a9,
        unsigned int a10,
        __int64 a11,
        __int64 a12)
{
  int v13; // r12d
  unsigned int v14; // eax
  const wchar_t *v15; // rdx
  __int64 v16; // r13
  int v17; // r14d
  __int64 v18; // rdx
  unsigned int v19; // r9d
  __int64 v20; // rcx
  __int64 v21; // rcx
  unsigned int v23; // [rsp+40h] [rbp-61h] BYREF
  unsigned int v24; // [rsp+48h] [rbp-59h] BYREF
  int v25; // [rsp+4Ch] [rbp-55h] BYREF
  PVOID P; // [rsp+50h] [rbp-51h] BYREF
  __int64 v27; // [rsp+58h] [rbp-49h] BYREF
  __int64 v28; // [rsp+60h] [rbp-41h]
  __int64 v29; // [rsp+68h] [rbp-39h]
  __int64 v30; // [rsp+70h] [rbp-31h]
  __int128 v31; // [rsp+78h] [rbp-29h] BYREF
  __int128 v32; // [rsp+88h] [rbp-19h] BYREF

  v29 = a2;
  v13 = 0;
  v24 = 0;
  v25 = 0;
  P = 0;
  *(_QWORD *)&v32 = a1;
  v30 = a6;
  v27 = a3;
  v31 = 0;
  v14 = BuildWinsock2ProtocolList(a3, a4, a5, a6, a8, a10, &P, &v24, 0);
  v23 = v14;
  if ( v14 )
  {
    v15 = L"BuildWinsock2ProtocolList failed";
LABEL_3:
    LogErrorWithProvider(v14, v15, a5);
    v16 = v29;
    v17 = 0;
    goto LABEL_26;
  }
  v14 = DetermineGuidForProvider(v27, v32, a4, a5, v30, &v31);
  v23 = v14;
  if ( v14 )
  {
    v15 = L"DetermineGuidForProvider failed";
    goto LABEL_3;
  }
  if ( a10 )
    MapProtocolInfoToSelfRelative(a8, a10);
  v18 = a4;
  v16 = v29;
  v23 = CreateMigrationRegistryForProvider(v29, v18, a5, a7, a8, a9, &v31);
  v19 = v23;
  if ( a10 )
    MapProtocolInfoToAbsolute(a8, a10);
  if ( v19 )
  {
    LogErrorWithProvider(v19, L"CreateMigrationRegistryForProvider failed", a5);
    v17 = 0;
    goto LABEL_26;
  }
  v17 = 1;
  if ( (unsigned int)WSCInstallProviderEx(
                       &v31,
                       L"%SystemRoot%\\system32\\mswsock.dll",
                       P,
                       v24,
                       &v23,
                       a12,
                       qword_180063FD0) == -1 )
  {
    LogErrorWithProvider(
      0xFFFFFFFFLL,
      L"Failed to install provider; will try sanitizing the configuration for this provider before trying again",
      a5);
    if ( (unsigned int)SanitizeWinsock2ConfigForProvider(&v31, a11, a12) )
    {
      LogErrorWithProvider(v23, L"SanitizeWinsock2ConfigForProvider failed", a5);
    }
    else
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 48, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, 0xFFFFFFFFLL);
      LogMsgWithProvider(L"Retrying installation", a5);
      if ( (unsigned int)WSCInstallProviderEx(
                           &v31,
                           L"%SystemRoot%\\system32\\mswsock.dll",
                           P,
                           v24,
                           &v23,
                           a12,
                           qword_180063FD0) == -1 )
      {
        LogErrorWithProvider(0xFFFFFFFFLL, L"2nd attempt to install provider failed", a5);
        goto LABEL_26;
      }
    }
    v23 = 0;
  }
  v13 = 1;
  if ( !(unsigned int)_o__wcsicmp(a5, L"Tcpip") || !(unsigned int)_o__wcsicmp(a5, L"Tcpip6") )
  {
    v32 = 0;
    if ( !(unsigned int)ReadProviderId(v16, L"Psched", &v32) )
    {
      v23 = HandleQoSReordering(v20, &v31, &v32, a12);
      if ( !v23 && ((*(_DWORD *)(a12 + 4) - 2) & 0xFFFFFFFD) == 0 )
      {
        LODWORD(v27) = *(_DWORD *)a12;
        v28 = *(_QWORD *)(a12 + 8);
        HIDWORD(v27) = 4;
        v23 = HandleQoSReordering(v21, &v31, &v32, &v27);
      }
    }
  }
LABEL_26:
  if ( P )
    RtlFreeHeap(SockPrivateHeap, 0, P);
  if ( v23 )
  {
    if ( v13 )
    {
      LogMsgWithProvider(L"Uninstalling provider, since there was an error", a5);
      WSCDeinstallProviderEx(&v31, &v25, a12);
      if ( ((*(_DWORD *)(a12 + 4) - 2) & 0xFFFFFFFD) == 0 )
      {
        LODWORD(v27) = *(_DWORD *)a12;
        v28 = *(_QWORD *)(a12 + 8);
        HIDWORD(v27) = 4;
        WSCDeinstallProviderEx(&v31, &v25, &v27);
      }
    }
  }
  else if ( v13 && *(_DWORD *)a11 == 1297109836 )
  {
    if ( *(_DWORD *)(a11 + 20) )
      MwcMarkReinstalledProtocols(&v31, *(_QWORD *)(a11 + 8), *(unsigned int *)(a11 + 16));
    if ( ((*(_DWORD *)(a12 + 4) - 2) & 0xFFFFFFFD) == 0 && *(_DWORD *)(a11 + 36) )
      MwcMarkReinstalledProtocols(&v31, *(_QWORD *)(a11 + 24), *(unsigned int *)(a11 + 32));
  }
  if ( v23 && v17 )
    RecursivelyDeleteRegistryTree(v16, a5);
  return v23;
}

```

## disassembly

```asm
0x180032294  push    rbp
0x180032296  push    rbx
0x180032297  push    rsi
0x180032298  push    rdi
0x180032299  push    r12
0x18003229b  push    r13
0x18003229d  push    r14
0x18003229f  push    r15
0x1800322a1  lea     rbp, [rsp-7]
0x1800322a6  sub     rsp, 0A8h
0x1800322ad  mov     rax, cs:__security_cookie
0x1800322b4  xor     rax, rsp
0x1800322b7  mov     [rbp+3Fh+var_48], rax
0x1800322bb  mov     rbx, [rbp+3Fh+arg_20]
0x1800322bf  mov     rax, r8
0x1800322c2  mov     r15, [rbp+3Fh+arg_38]
0x1800322c9  mov     r13d, r9d
0x1800322cc  mov     r14d, [rbp+3Fh+arg_48]
0x1800322d3  xorps   xmm0, xmm0
0x1800322d6  mov     rsi, [rbp+3Fh+arg_50]
0x1800322dd  mov     r8, rbx
0x1800322e0  mov     rdi, [rbp+3Fh+arg_58]
0x1800322e7  mov     [rbp+3Fh+var_78], rdx
0x1800322eb  xor     edx, edx
0x1800322ed  mov     [rbp+3Fh+var_A0], edx
0x1800322f0  mov     r12d, edx
0x1800322f3  mov     [rbp+3Fh+var_98], edx
0x1800322f6  mov     [rbp+3Fh+var_94], edx
0x1800322f9  mov     [rbp+3Fh+P], rdx
0x1800322fd  lea     rdx, [rbp+3Fh+var_98]
0x180032301  mov     [rsp+0E0h+var_A8], rdx
0x180032306  lea     rdx, [rbp+3Fh+P]
0x18003230a  mov     [rsp+0E0h+var_B0], rdx
0x18003230f  mov     edx, r13d
0x180032312  mov     qword ptr [rbp+3Fh+var_58], rcx
0x180032316  mov     rcx, [rbp+3Fh+arg_28]
0x18003231a  mov     [rbp+3Fh+var_70], rcx
0x18003231e  mov     r9, rcx
0x180032321  mov     dword ptr [rsp+0E0h+var_B8], r14d
0x180032326  mov     rcx, rax
0x180032329  mov     [rsp+0E0h+var_C0], r15
0x18003232e  mov     [rbp+3Fh+var_88], rax
0x180032332  movups  [rbp+3Fh+var_68], xmm0
0x180032336  call    BuildWinsock2ProtocolList
0x18003233b  mov     [rbp+3Fh+var_A0], eax
0x18003233e  test    eax, eax
0x180032340  jz      short loc_18003235F
0x180032342  lea     rdx, aBuildwinsock2p; "BuildWinsock2ProtocolList failed"
0x180032349  mov     r8, rbx
0x18003234c  mov     ecx, eax
0x18003234e  call    LogErrorWithProvider
0x180032353  mov     r13, [rbp+3Fh+var_78]
0x180032357  mov     r14d, r12d
0x18003235a  jmp     loc_1800325B8
0x18003235f  mov     rdx, qword ptr [rbp+3Fh+var_58]
0x180032363  lea     rax, [rbp+3Fh+var_68]
0x180032367  mov     rcx, [rbp+3Fh+var_88]
0x18003236b  mov     r9, rbx
0x18003236e  mov     [rsp+0E0h+var_B8], rax
0x180032373  mov     r8d, r13d
0x180032376  mov     rax, [rbp+3Fh+var_70]
0x18003237a  mov     [rsp+0E0h+var_C0], rax
0x18003237f  call    DetermineGuidForProvider
0x180032384  mov     [rbp+3Fh+var_A0], eax
0x180032387  test    eax, eax
0x180032389  jz      short loc_180032394
0x18003238b  lea     rdx, aDetermineguidf; "DetermineGuidForProvider failed"
0x180032392  jmp     short loc_180032349
0x180032394  test    r14d, r14d
0x180032397  jz      short loc_1800323A4
0x180032399  mov     edx, r14d
0x18003239c  mov     rcx, r15
0x18003239f  call    MapProtocolInfoToSelfRelative
0x1800323a4  mov     r9d, [rbp+3Fh+arg_30]
0x1800323a8  lea     rax, [rbp+3Fh+var_68]
0x1800323ac  mov     [rsp+0E0h+var_B0], rax
0x1800323b1  mov     edx, r13d
0x1800323b4  mov     eax, [rbp+3Fh+arg_40]
0x1800323ba  mov     r8, rbx
0x1800323bd  mov     r13, [rbp+3Fh+var_78]
0x1800323c1  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1800323c5  mov     rcx, r13
0x1800323c8  mov     [rsp+0E0h+var_C0], r15
0x1800323cd  call    CreateMigrationRegistryForProvider
0x1800323d2  mov     [rbp+3Fh+var_A0], eax
0x1800323d5  mov     r9d, eax
0x1800323d8  test    r14d, r14d
0x1800323db  jz      short loc_1800323E8
0x1800323dd  mov     edx, r14d
0x1800323e0  mov     rcx, r15
0x1800323e3  call    MapProtocolInfoToAbsolute
0x1800323e8  test    r9d, r9d
0x1800323eb  jz      short loc_180032407
0x1800323ed  mov     r8, rbx
0x1800323f0  lea     rdx, aCreatemigratio; "CreateMigrationRegistryForProvider fail"...
0x1800323f7  mov     ecx, r9d
0x1800323fa  call    LogErrorWithProvider
0x1800323ff  mov     r14d, r12d
0x180032402  jmp     loc_1800325B8
0x180032407  mov     rax, cs:qword_180063FD0
0x18003240e  lea     rdx, szProviderDllPath; "%SystemRoot%\\system32\\mswsock.dll"
0x180032415  mov     r9d, [rbp+3Fh+var_98]
0x180032419  lea     rcx, [rbp+3Fh+var_68]
0x18003241d  mov     r8, [rbp+3Fh+P]
0x180032421  mov     r14d, 1
0x180032427  mov     [rsp+0E0h+var_B0], rax
0x18003242c  lea     rax, [rbp+3Fh+var_A0]
0x180032430  mov     [rsp+0E0h+var_B8], rdi
0x180032435  mov     [rsp+0E0h+var_C0], rax
0x18003243a  call    cs:__imp_WSCInstallProviderEx
0x180032441  nop     dword ptr [rax+rax+00h]
0x180032446  cmp     eax, 0FFFFFFFFh
0x180032449  jnz     loc_180032517
0x18003244f  or      r15d, 0FFFFFFFFh
0x180032453  lea     rdx, aFailedToInstal; "Failed to install provider; will try sa"...
0x18003245a  mov     ecx, r15d
0x18003245d  mov     r8, rbx
0x180032460  call    LogErrorWithProvider
0x180032465  mov     r8, rdi
0x180032468  lea     rcx, [rbp+3Fh+var_68]
0x18003246c  mov     rdx, rsi
0x18003246f  call    SanitizeWinsock2ConfigForProvider
0x180032474  test    eax, eax
0x180032476  jnz     loc_180032501
0x18003247c  test    byte ptr cs:xmmword_180063D60, 2
0x180032483  jz      short loc_18003249D
0x180032485  lea     edx, [rax+30h]
0x180032488  mov     ecx, 401h
0x18003248d  or      r9d, 0FFFFFFFFh
0x180032491  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180032498  call    WPP_SF_d
0x18003249d  mov     rdx, rbx
0x1800324a0  lea     rcx, aRetryingInstal; "Retrying installation"
0x1800324a7  call    LogMsgWithProvider
0x1800324ac  mov     rax, cs:qword_180063FD0
0x1800324b3  lea     rdx, szProviderDllPath; "%SystemRoot%\\system32\\mswsock.dll"
0x1800324ba  mov     r9d, [rbp+3Fh+var_98]
0x1800324be  lea     rcx, [rbp+3Fh+var_68]
0x1800324c2  mov     r8, [rbp+3Fh+P]
0x1800324c6  mov     [rsp+0E0h+var_B0], rax
0x1800324cb  lea     rax, [rbp+3Fh+var_A0]
0x1800324cf  mov     [rsp+0E0h+var_B8], rdi
0x1800324d4  mov     [rsp+0E0h+var_C0], rax
0x1800324d9  call    cs:__imp_WSCInstallProviderEx
0x1800324e0  nop     dword ptr [rax+rax+00h]
0x1800324e5  cmp     eax, 0FFFFFFFFh
0x1800324e8  jnz     short loc_180032513
0x1800324ea  mov     r8, rbx
0x1800324ed  lea     rdx, a2ndAttemptToIn; "2nd attempt to install provider failed"
0x1800324f4  mov     ecx, r15d
0x1800324f7  call    LogErrorWithProvider
0x1800324fc  jmp     loc_1800325B8
0x180032501  mov     ecx, [rbp+3Fh+var_A0]
0x180032504  lea     rdx, aSanitizewinsoc; "SanitizeWinsock2ConfigForProvider faile"...
0x18003250b  mov     r8, rbx
0x18003250e  call    LogErrorWithProvider
0x180032513  mov     [rbp+3Fh+var_A0], r12d
0x180032517  lea     rdx, aTcpip; "Tcpip"
0x18003251e  mov     rcx, rbx
0x180032521  mov     r12d, r14d
0x180032524  call    cs:__imp__o__wcsicmp
0x18003252b  nop     dword ptr [rax+rax+00h]
0x180032530  test    eax, eax
0x180032532  jz      short loc_18003254E
0x180032534  lea     rdx, aTcpip6; "Tcpip6"
0x18003253b  mov     rcx, rbx
0x18003253e  call    cs:__imp__o__wcsicmp
0x180032545  nop     dword ptr [rax+rax+00h]
0x18003254a  test    eax, eax
0x18003254c  jnz     short loc_1800325B8
0x18003254e  xorps   xmm0, xmm0
0x180032551  lea     r8, [rbp+3Fh+var_58]
0x180032555  lea     rdx, aPsched; "Psched"
0x18003255c  mov     rcx, r13
0x18003255f  movups  [rbp+3Fh+var_58], xmm0
0x180032563  call    ReadProviderId
0x180032568  test    eax, eax
0x18003256a  jnz     short loc_1800325B8
0x18003256c  mov     r9, rdi
0x18003256f  lea     r8, [rbp+3Fh+var_58]
0x180032573  lea     rdx, [rbp+3Fh+var_68]
0x180032577  call    HandleQoSReordering
0x18003257c  mov     [rbp+3Fh+var_A0], eax
0x18003257f  test    eax, eax
0x180032581  jnz     short loc_1800325B8
0x180032583  mov     eax, [rdi+4]
0x180032586  sub     eax, 2
0x180032589  test    eax, 0FFFFFFFDh
0x18003258e  jnz     short loc_1800325B8
0x180032590  mov     eax, [rdi]
0x180032592  lea     r9, [rbp+3Fh+var_88]
0x180032596  mov     dword ptr [rbp+3Fh+var_88], eax
0x180032599  lea     r8, [rbp+3Fh+var_58]
0x18003259d  mov     rax, [rdi+8]
0x1800325a1  lea     rdx, [rbp+3Fh+var_68]
0x1800325a5  mov     [rbp+3Fh+var_80], rax
0x1800325a9  mov     dword ptr [rbp+3Fh+var_88+4], 4
0x1800325b0  call    HandleQoSReordering
0x1800325b5  mov     [rbp+3Fh+var_A0], eax
0x1800325b8  mov     r8, [rbp+3Fh+P]; P
0x1800325bc  test    r8, r8
0x1800325bf  jz      short loc_1800325D6
0x1800325c1  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800325c8  xor     edx, edx; Flags
0x1800325ca  call    cs:__imp_RtlFreeHeap
0x1800325d1  nop     dword ptr [rax+rax+00h]
0x1800325d6  cmp     [rbp+3Fh+var_A0], 0
0x1800325da  jz      short loc_180032646
0x1800325dc  test    r12d, r12d
0x1800325df  jz      loc_18003268E
0x1800325e5  mov     rdx, rbx
0x1800325e8  lea     rcx, aUninstallingPr; "Uninstalling provider, since there was "...
0x1800325ef  call    LogMsgWithProvider
0x1800325f4  mov     r8, rdi
0x1800325f7  lea     rdx, [rbp+3Fh+var_94]
0x1800325fb  lea     rcx, [rbp+3Fh+var_68]
0x1800325ff  call    cs:__imp_WSCDeinstallProviderEx
0x180032606  nop     dword ptr [rax+rax+00h]
0x18003260b  mov     eax, [rdi+4]
0x18003260e  sub     eax, 2
0x180032611  test    eax, 0FFFFFFFDh
0x180032616  jnz     short loc_18003268E
0x180032618  mov     eax, [rdi]
0x18003261a  lea     r8, [rbp+3Fh+var_88]
0x18003261e  mov     dword ptr [rbp+3Fh+var_88], eax
0x180032621  lea     rdx, [rbp+3Fh+var_94]
0x180032625  mov     rax, [rdi+8]
0x180032629  lea     rcx, [rbp+3Fh+var_68]
0x18003262d  mov     [rbp+3Fh+var_80], rax
0x180032631  mov     dword ptr [rbp+3Fh+var_88+4], 4
0x180032638  call    cs:__imp_WSCDeinstallProviderEx
0x18003263f  nop     dword ptr [rax+rax+00h]
0x180032644  jmp     short loc_18003268E
0x180032646  test    r12d, r12d
0x180032649  jz      short loc_18003268E
0x18003264b  cmp     dword ptr [rsi], 4D50534Ch
0x180032651  jnz     short loc_18003268E
0x180032653  cmp     dword ptr [rsi+14h], 0
0x180032657  jbe     short loc_18003266A
0x180032659  mov     r8d, [rsi+10h]
0x18003265d  lea     rcx, [rbp+3Fh+var_68]
0x180032661  mov     rdx, [rsi+8]
0x180032665  call    MwcMarkReinstalledProtocols
0x18003266a  mov     eax, [rdi+4]
0x18003266d  sub     eax, 2
0x180032670  test    eax, 0FFFFFFFDh
0x180032675  jnz     short loc_18003268E
0x180032677  cmp     dword ptr [rsi+24h], 0
0x18003267b  jbe     short loc_18003268E
0x18003267d  mov     r8d, [rsi+20h]
0x180032681  lea     rcx, [rbp+3Fh+var_68]
0x180032685  mov     rdx, [rsi+18h]
0x180032689  call    MwcMarkReinstalledProtocols
0x18003268e  cmp     [rbp+3Fh+var_A0], 0
0x180032692  jz      short loc_1800326A4
0x180032694  test    r14d, r14d
0x180032697  jz      short loc_1800326A4
0x180032699  mov     rdx, rbx
0x18003269c  mov     rcx, r13
0x18003269f  call    RecursivelyDeleteRegistryTree
0x1800326a4  mov     eax, [rbp+3Fh+var_A0]
0x1800326a7  mov     rcx, [rbp+3Fh+var_48]
0x1800326ab  xor     rcx, rsp; StackCookie
0x1800326ae  call    __security_check_cookie
0x1800326b3  add     rsp, 0A8h
0x1800326ba  pop     r15
0x1800326bc  pop     r14
0x1800326be  pop     r13
0x1800326c0  pop     r12
0x1800326c2  pop     rdi
0x1800326c3  pop     rsi
0x1800326c4  pop     rbx
0x1800326c5  pop     rbp
0x1800326c6  retn
```
