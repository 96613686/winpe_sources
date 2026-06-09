# EnableOrDisableIPForwarding

- ea: `0x180050434`
- end: `0x180050b6e`
- name: `EnableOrDisableIPForwarding`
- size: `1850`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800236d4`
- `0x180025eac`
- `0x180050e40`

## callees

- `0x180002040`
- `0x18000ac60`
- `0x18001255c`
- `0x180050434`
- `0x18005381c`
- `0x1800539b0`
- `0x180055bdc`
- `0x180055fc8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `msvcrt!free` at `0x180050ae6`
- `msvcrt!free` at `0x180050af4`
- `msvcrt!free` at `0x180050ae6`
- `msvcrt!free` at `0x180050af4`
- `msvcrt!malloc` at `0x180050736`
- `msvcrt!malloc` at `0x180050736`
- `ntdll!RtlReleaseResource` at `0x180050951`
- `ntdll!RtlReleaseResource` at `0x180050951`
- `ntdll!RtlAcquireResourceShared` at `0x180050913`
- `ntdll!RtlAcquireResourceShared` at `0x180050913`
- `KERNEL32!LocalFree` at `0x180050b12`
- `KERNEL32!LocalFree` at `0x180050b12`
- `KERNEL32!SetEvent` at `0x180050b3b`
- `KERNEL32!SetEvent` at `0x180050b3b`
- `ADVAPI32!RegCloseKey` at `0x180050b03`
- `ADVAPI32!RegCloseKey` at `0x180050b03`
- `ADVAPI32!RegOpenKeyExW` at `0x180050696`
- `ADVAPI32!RegOpenKeyExW` at `0x180050696`
- `ADVAPI32!RegQueryValueExW` at `0x180050711`
- `ADVAPI32!RegQueryValueExW` at `0x18005077f`
- `ADVAPI32!RegQueryValueExW` at `0x180050711`
- `ADVAPI32!RegQueryValueExW` at `0x18005077f`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180050876`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180050876`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x1800508c0`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x1800508c0`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x1800508e3`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x1800508e3`
- `rtutils!RouterGetErrorStringW` at `0x1800509f4`
- `rtutils!RouterGetErrorStringW` at `0x1800509f4`
- `rtutils!LogEventW` at `0x180050a25`
- `rtutils!LogEventW` at `0x180050a25`
- `NSI!NsiSetAllParameters` at `0x180050a82`
- `NSI!NsiSetAllParameters` at `0x180050a82`
- `RPCRT4!UuidFromStringW` at `0x18005080c`
- `RPCRT4!UuidFromStringW` at `0x18005080c`

## string_xrefs

- `0x180050688`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`
- `0x180050561`: `EnableOrDisableIPForwarding: DirectAccess registry keys not found. Continuing in normal mode.`
- `0x1800505d0`: `EnableOrDisableIPForwarding: IsDirectAccessConfigured failed with error %d`
- `0x1800505a4`: `EnableOrDisableIPForwarding: DirectAccess is deployed. No need to change the IPv6 forwarding settings.`
- `0x180050644`: `EnableOrDisableIPForwarding: GetDirectAccessInterfaces failed with error %d, trying to read remoteaccess service registry`
- `0x1800506ac`: `EnableOrDisableIPForwarding: Opening remoteaccess service registry failed with error %d`
- `0x180050727`: `EnableOrDisableIPForwarding: Querying remoteaccess service registry failed with error %d`
- `0x180050798`: `EnableOrDisableIPForwarding: Querying remoteaccess service registry failed with error %d`

## pseudocode

```c
__int64 __fastcall EnableOrDisableIPForwarding(int a1, unsigned int a2, __int64 a3, int a4, _DWORD *a5)
{
  const NPI_MODULEID *v7; // r13
  int v8; // ebx
  WCHAR *v9; // r12
  __int64 v10; // rcx
  unsigned int v11; // r14d
  const wchar_t *v12; // r8
  __int64 *v13; // rdx
  unsigned int DirectAccessInterfaces; // eax
  unsigned int v15; // eax
  const wchar_t *v16; // rdx
  size_t v17; // rbx
  WCHAR *v18; // rax
  unsigned int v19; // eax
  __int64 v20; // r8
  const wchar_t *v21; // rdx
  __int64 v22; // rax
  unsigned int v23; // eax
  struct RtMgrRdConfigStore *Instance; // rdi
  _QWORD *v25; // rbx
  RtMgrRoutingDomainConfig *v26; // rsi
  unsigned int CompartmentId; // eax
  DWORD v28; // edx
  unsigned int v29; // eax
  int v31; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbData; // [rsp+74h] [rbp-8Ch] BYREF
  int v33; // [rsp+78h] [rbp-88h]
  PRTL_RESOURCE Resource; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v35; // [rsp+88h] [rbp-78h] BYREF
  int v36; // [rsp+98h] [rbp-68h]
  int v37; // [rsp+9Ch] [rbp-64h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v39; // [rsp+A8h] [rbp-58h]
  LPWSTR lpwszErrorString; // [rsp+B0h] [rbp-50h] BYREF
  NET_LUID InterfaceLuid; // [rsp+B8h] [rbp-48h] BYREF
  void *Block; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v43; // [rsp+C8h] [rbp-38h]
  UUID Uuid; // [rsp+D0h] [rbp-30h] BYREF
  _MIB_IPINTERFACE_ROW Row; // [rsp+E0h] [rbp-20h] BYREF
  LPWSTR plpwsSubStrings[2]; // [rsp+190h] [rbp+90h] BYREF
  LPWSTR v47; // [rsp+1A0h] [rbp+A0h]
  char pszDest[40]; // [rsp+1A8h] [rbp+A8h] BYREF
  int v49; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v50[2044]; // [rsp+1D4h] [rbp+D4h] BYREF

  v43 = a3;
  v33 = a1;
  v36 = a4;
  v37 = 0;
  v7 = &NPI_MS_IPV4_MODULEID;
  v31 = 0;
  if ( !a2 )
    v7 = &NPI_MS_IPV6_MODULEID;
  cbData = 0;
  InterfaceLuid.Value = 0;
  v8 = -1073741811;
  v39 = 7 - (a1 != 0);
  memset_0(&Row, 0, sizeof(Row));
  Block = 0;
  *(_OWORD *)plpwsSubStrings = 0;
  strcpy(pszDest, "GUID_NULL");
  v47 = 0;
  v9 = 0;
  memset(&pszDest[10], 0, 30);
  Resource = 0;
  lpwszErrorString = 0;
  hKey = 0;
  v35 = 0;
  v49 = 0;
  memset_0(v50, 0, sizeof(v50));
  v11 = IsDirectAccessConfigured(v10, &v31);
  if ( v11 )
  {
    if ( v11 != 2 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v49) = 0;
        FormatRRASErrorString(&v49, L"EnableOrDisableIPForwarding: IsDirectAccessConfigured failed with error %d", v11);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v12 = (const wchar_t *)&v49;
          v13 = RasRtrMgrTraceError;
LABEL_14:
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v13, v12);
          goto LABEL_72;
        }
      }
      goto LABEL_72;
    }
    v11 = 0;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"EnableOrDisableIPForwarding: DirectAccess registry keys not found. Continuing in normal mode.");
  }
  if ( v31 == 1 )
  {
    Uuid = 0;
    if ( !a2 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_72;
      v12 = L"EnableOrDisableIPForwarding: DirectAccess is deployed. No need to change the IPv6 forwarding settings.";
      v13 = RasRtrmgrTraceInfo;
      goto LABEL_14;
    }
    DirectAccessInterfaces = GetDirectAccessInterfaces(1, &Block, &Resource);
    v11 = DirectAccessInterfaces;
    if ( DirectAccessInterfaces )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v49) = 0;
        FormatRRASErrorString(
          &v49,
          L"EnableOrDisableIPForwarding: GetDirectAccessInterfaces failed with error %d, trying to read remoteaccess service registry",
          DirectAccessInterfaces);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v49);
      }
      v15 = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip",
              0,
              0x20019u,
              &hKey);
      v11 = v15;
      if ( v15 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v16 = L"EnableOrDisableIPForwarding: Opening remoteaccess service registry failed with error %d";
          goto LABEL_22;
        }
        goto LABEL_24;
      }
      v15 = RegQueryValueExW(hKey, L"NetworkAdapterGUID", 0, 0, 0, &cbData);
      v11 = v15;
      if ( v15 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v16 = L"EnableOrDisableIPForwarding: Querying remoteaccess service registry failed with error %d";
LABEL_22:
          LOWORD(v49) = 0;
          FormatRRASErrorString(&v49, v16, v15);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v49);
        }
LABEL_24:
        v9 = (WCHAR *)Resource;
LABEL_68:
        if ( Block )
          free(Block);
        if ( v9 )
          free(v9);
        goto LABEL_72;
      }
      v17 = cbData;
      v18 = (WCHAR *)malloc(cbData);
      v9 = v18;
      if ( !v18 )
      {
        v8 = -1073741811;
        v11 = 14;
        goto LABEL_68;
      }
      memset_0(v18, 0, v17);
      v19 = RegQueryValueExW(hKey, L"NetworkAdapterGUID", 0, 0, (LPBYTE)v9, &cbData);
      v11 = v19;
      if ( v19 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v20 = v19;
          v21 = L"EnableOrDisableIPForwarding: Querying remoteaccess service registry failed with error %d";
LABEL_33:
          LOWORD(v49) = 0;
          FormatRRASErrorString(&v49, v21, v20);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v49);
          goto LABEL_35;
        }
        goto LABEL_35;
      }
      v8 = -1073741811;
    }
    else
    {
      v9 = (WCHAR *)Resource;
    }
    v22 = -1;
    do
      ++v22;
    while ( v9[v22] );
    if ( !(_DWORD)v22 )
      goto LABEL_68;
    v9[(unsigned int)(v22 - 1)] = 0;
    if ( UuidFromStringW(v9 + 1, &Uuid) )
    {
      v11 = 1003;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_68;
      LOWORD(v49) = 0;
      FormatRRASErrorString(&v49, L"EnableOrDisableIPForwarding: UuidFromStringW failed with error %d", 1003);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_68;
    }
    else
    {
      v23 = ConvertInterfaceGuidToLuid(&Uuid, &InterfaceLuid);
      v11 = v23;
      if ( !v23 )
      {
        InitializeIpInterfaceEntry(&Row);
        Row.InterfaceLuid = InterfaceLuid;
        Row.Family = 2;
        Row.ForwardingEnabled = v33 != 0;
        v11 = SetIpInterfaceEntry(&Row);
        if ( !v11 )
          goto LABEL_35;
        Instance = RtMgrRdConfigStore::GetInstance();
        v31 = 1168;
        Resource = (PRTL_RESOURCE)((char *)Instance + 184);
        RtlAcquireResourceShared((PRTL_RESOURCE)((char *)Instance + 184), 1u);
        v25 = (_QWORD *)*((_QWORD *)Instance + 2);
        while ( 1 )
        {
          v25 = (_QWORD *)*v25;
          if ( v25 == *((_QWORD **)Instance + 2) )
            break;
          v26 = (RtMgrRoutingDomainConfig *)v25[4];
          CompartmentId = RtMgrRoutingDomainConfig::GetCompartmentId(v26);
          if ( CompartmentId == v36 )
          {
            v31 = 0;
            RtMgrRoutingDomainConfig::GetRoutingDomainId(v26, &v35);
            break;
          }
        }
        RtlReleaseResource(Resource);
        if ( !v31 )
          StringCbPrintfA(
            pszDest,
            0x28u,
            "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
            v35.Data1,
            v35.Data2,
            v35.Data3,
            v35.Data4[0],
            v35.Data4[1],
            v35.Data4[2],
            v35.Data4[3],
            v35.Data4[4],
            v35.Data4[5],
            v35.Data4[6],
            v35.Data4[7]);
        plpwsSubStrings[0] = (LPWSTR)pszDest;
        plpwsSubStrings[1] = v9 + 1;
        RouterGetErrorStringW(v11, &lpwszErrorString);
        v47 = lpwszErrorString;
        v28 = 20282;
        if ( !v33 )
          v28 = 20283;
        LogEventW(1u, v28, 3u, plpwsSubStrings);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_35;
        v20 = v11;
        v21 = L"EnableOrDisableIPForwarding: SetIpInterfaceEntry failed with error %d";
        goto LABEL_33;
      }
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0
        || (LOWORD(v49) = 0,
            FormatRRASErrorString(
              &v49,
              L"EnableOrDisableIPForwarding: ConvertInterfaceGuidToLuid failed with error %d",
              v23),
            (Microsoft_Windows_RRASEnableBits & 0x40) == 0) )
      {
LABEL_35:
        v8 = -1073741811;
        goto LABEL_68;
      }
    }
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v49);
    goto LABEL_68;
  }
  if ( !a1 && a5 )
    *a5 = 0x7FFFFFFF;
  v37 = v36;
  v29 = NsiSetAllParameters(1, v39, v7);
  v8 = v29;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v49) = 0;
    FormatRRASErrorString(&v49, L"EnableOrDisableIPForwarding status %d for bV4=%d\n\n", v29, a2, &v37, 4, 0, 0);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v49);
  }
  if ( v8 < 0 )
  {
    v11 = v8;
    goto LABEL_68;
  }
LABEL_72:
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpwszErrorString )
    LocalFree(lpwszErrorString);
  if ( v8 >= 0 && !v11 )
  {
    if ( v33 )
      return 997;
    if ( v43 )
      SetEvent(*(HANDLE *)(v43 + 24));
  }
  return v11;
}

```

## disassembly

```asm
0x180050434  mov     [rsp-8+arg_0], rbx
0x180050439  push    rbp
0x18005043a  push    rsi
0x18005043b  push    rdi
0x18005043c  push    r12
0x18005043e  push    r13
0x180050440  push    r14
0x180050442  push    r15
0x180050444  lea     rbp, [rsp-8E0h]
0x18005044c  sub     rsp, 9E0h
0x180050453  mov     rax, cs:__security_cookie
0x18005045a  xor     rax, rsp
0x18005045d  mov     [rbp+910h+var_40], rax
0x180050464  mov     rdi, [rbp+910h+arg_20]
0x18005046b  lea     rax, NPI_MS_IPV6_MODULEID
0x180050472  xor     r14d, r14d
0x180050475  mov     [rbp+910h+var_948], r8
0x180050479  test    edx, edx
0x18005047b  mov     [rsp+0A10h+var_998], ecx
0x18005047f  mov     esi, edx
0x180050481  mov     [rbp+910h+var_978], r9d
0x180050485  mov     r15d, ecx
0x180050488  mov     [rbp+910h+var_974], r14d
0x18005048c  lea     r13, NPI_MS_IPV4_MODULEID
0x180050493  mov     [rsp+0A10h+var_9A0], r14d
0x180050498  cmovz   r13, rax
0x18005049c  mov     [rsp+0A10h+cbData], r14d
0x1800504a1  mov     eax, ecx
0x1800504a3  mov     qword ptr [rbp+910h+InterfaceLuid], r14
0x1800504a7  neg     eax
0x1800504a9  lea     rcx, [rbp+910h+Row]; void *
0x1800504ad  mov     r8d, 0A8h; Size
0x1800504b3  mov     ebx, 0C000000Dh
0x1800504b8  sbb     eax, eax
0x1800504ba  xor     edx, edx; Val
0x1800504bc  add     eax, 7
0x1800504bf  mov     [rbp+910h+var_968], eax
0x1800504c2  call    memset_0
0x1800504c7  xorps   xmm0, xmm0
0x1800504ca  mov     [rbp+910h+Block], r14
0x1800504ce  movups  xmmword ptr [rbp+910h+plpwsSubStrings], xmm0
0x1800504d5  lea     rcx, [rbp+910h+var_83C]; void *
0x1800504dc  xor     eax, eax
0x1800504de  movsd   xmm0, qword ptr cs:aGuidNull; "GUID_NULL"
0x1800504e6  xor     edx, edx; Val
0x1800504e8  movsd   qword ptr [rbp+910h+pszDest], xmm0
0x1800504f0  mov     r8d, 7FCh; Size
0x1800504f6  xorps   xmm0, xmm0
0x1800504f9  mov     [rbp+910h+var_870], rax
0x180050500  movzx   eax, word ptr cs:aGuidNull+8; "L"
0x180050507  mov     r12d, r14d
0x18005050a  movups  xmmword ptr [rbp+910h+var_85E], xmm0
0x180050511  mov     [rbp+910h+Resource], r14
0x180050515  movups  xmmword ptr [rbp+910h+var_85E+0Eh], xmm0
0x18005051c  mov     [rbp+910h+lpwszErrorString], r14
0x180050520  mov     [rbp+910h+hKey], r14
0x180050524  mov     [rbp+910h+var_860], ax
0x18005052b  movups  xmmword ptr [rbp+910h+var_988.Data1], xmm0
0x18005052f  mov     [rbp+910h+var_840], r14d
0x180050536  call    memset_0
0x18005053b  lea     rdx, [rsp+0A10h+var_9A0]
0x180050540  call    IsDirectAccessConfigured
0x180050545  mov     r14d, eax
0x180050548  xor     eax, eax
0x18005054a  test    r14d, r14d
0x18005054d  jz      short loc_18005057B
0x18005054f  cmp     r14d, 2
0x180050553  jnz     short loc_1800505B4
0x180050555  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18005055c  mov     r14d, eax
0x18005055f  jz      short loc_18005057B
0x180050561  lea     r8, aEnableordisabl_0; "EnableOrDisableIPForwarding: DirectAcce"...
0x180050568  lea     rdx, RasRtrmgrTraceInfo
0x18005056f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180050576  call    McTemplateU0z_EventWriteTransfer
0x18005057b  mov     ecx, 1
0x180050580  cmp     [rsp+0A10h+var_9A0], ecx
0x180050584  jnz     loc_180050A47
0x18005058a  xor     edi, edi
0x18005058c  xorps   xmm0, xmm0
0x18005058f  movups  xmmword ptr [rbp+910h+Uuid.Data1], xmm0
0x180050593  test    esi, esi
0x180050595  jnz     short loc_18005060F
0x180050597  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18005059e  jz      loc_180050AFA
0x1800505a4  lea     r8, aEnableordisabl_7; "EnableOrDisableIPForwarding: DirectAcce"...
0x1800505ab  lea     rdx, RasRtrmgrTraceInfo
0x1800505b2  jmp     short loc_1800505FE
0x1800505b4  mov     r15b, 40h ; '@'
0x1800505b7  xor     edi, edi
0x1800505b9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800505c0  jz      loc_180050AFA
0x1800505c6  mov     r8d, r14d
0x1800505c9  mov     word ptr [rbp+910h+var_840], di
0x1800505d0  lea     rdx, aEnableordisabl_5; "EnableOrDisableIPForwarding: IsDirectAc"...
0x1800505d7  lea     rcx, [rbp+910h+var_840]
0x1800505de  call    FormatRRASErrorString
0x1800505e3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800505ea  jz      loc_180050AFA
0x1800505f0  lea     r8, [rbp+910h+var_840]
0x1800505f7  lea     rdx, RasRtrMgrTraceError
0x1800505fe  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180050605  call    McTemplateU0z_EventWriteTransfer
0x18005060a  jmp     loc_180050AFA
0x18005060f  lea     r8, [rbp+910h+Resource]
0x180050613  lea     rdx, [rbp+910h+Block]
0x180050617  call    GetDirectAccessInterfaces
0x18005061c  lea     r13, RasRtrMgrTraceError
0x180050623  mov     r14d, eax
0x180050626  mov     r15b, 40h ; '@'
0x180050629  test    eax, eax
0x18005062b  jz      loc_1800507DB
0x180050631  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180050638  jz      short loc_180050676
0x18005063a  mov     r8d, eax
0x18005063d  mov     word ptr [rbp+910h+var_840], di
0x180050644  lea     rdx, aEnableordisabl_4; "EnableOrDisableIPForwarding: GetDirectA"...
0x18005064b  lea     rcx, [rbp+910h+var_840]
0x180050652  call    FormatRRASErrorString
0x180050657  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18005065e  jz      short loc_180050676
0x180050660  lea     r8, [rbp+910h+var_840]
0x180050667  mov     rdx, r13
0x18005066a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180050671  call    McTemplateU0z_EventWriteTransfer
0x180050676  lea     rax, [rbp+910h+hKey]
0x18005067a  mov     r9d, 20019h; samDesired
0x180050680  xor     r8d, r8d; ulOptions
0x180050683  mov     [rsp+0A10h+phkResult], rax; phkResult
0x180050688  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\Re"...
0x18005068f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180050696  call    cs:__imp_RegOpenKeyExW
0x18005069c  mov     r14d, eax
0x18005069f  test    eax, eax
0x1800506a1  jz      short loc_1800506F1
0x1800506a3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800506aa  jz      short loc_1800506E8
0x1800506ac  lea     rdx, aEnableordisabl; "EnableOrDisableIPForwarding: Opening re"...
0x1800506b3  mov     r8d, eax
0x1800506b6  mov     word ptr [rbp+910h+var_840], di
0x1800506bd  lea     rcx, [rbp+910h+var_840]
0x1800506c4  call    FormatRRASErrorString
0x1800506c9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800506d0  jz      short loc_1800506E8
0x1800506d2  lea     r8, [rbp+910h+var_840]
0x1800506d9  mov     rdx, r13
0x1800506dc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800506e3  call    McTemplateU0z_EventWriteTransfer
0x1800506e8  mov     r12, [rbp+910h+Resource]
0x1800506ec  jmp     loc_180050ADD
0x1800506f1  mov     rcx, [rbp+910h+hKey]; hKey
0x1800506f5  lea     rax, [rsp+0A10h+cbData]
0x1800506fa  mov     [rsp+0A10h+lpcbData], rax; lpcbData
0x1800506ff  lea     rdx, aNetworkadapter; "NetworkAdapterGUID"
0x180050706  xor     r9d, r9d; lpType
0x180050709  mov     [rsp+0A10h+phkResult], rdi; lpData
0x18005070e  xor     r8d, r8d; lpReserved
0x180050711  call    cs:__imp_RegQueryValueExW
0x180050717  mov     r14d, eax
0x18005071a  test    eax, eax
0x18005071c  jz      short loc_180050730
0x18005071e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180050725  jz      short loc_1800506E8
0x180050727  lea     rdx, aEnableordisabl_1; "EnableOrDisableIPForwarding: Querying r"...
0x18005072e  jmp     short loc_1800506B3
0x180050730  mov     ebx, [rsp+0A10h+cbData]
0x180050734  mov     ecx, ebx; Size
0x180050736  call    cs:__imp_malloc
0x18005073c  mov     r12, rax
0x18005073f  test    rax, rax
0x180050742  jnz     short loc_180050752
0x180050744  mov     ebx, 0C000000Dh
0x180050749  lea     r14d, [rax+0Eh]
0x18005074d  jmp     loc_180050ADD
0x180050752  mov     r8, rbx; Size
0x180050755  xor     edx, edx; Val
0x180050757  mov     rcx, r12; void *
0x18005075a  call    memset_0
0x18005075f  mov     rcx, [rbp+910h+hKey]; hKey
0x180050763  lea     rax, [rsp+0A10h+cbData]
0x180050768  mov     [rsp+0A10h+lpcbData], rax; lpcbData
0x18005076d  lea     rdx, aNetworkadapter; "NetworkAdapterGUID"
0x180050774  xor     r9d, r9d; lpType
0x180050777  mov     [rsp+0A10h+phkResult], r12; lpData
0x18005077c  xor     r8d, r8d; lpReserved
0x18005077f  call    cs:__imp_RegQueryValueExW
0x180050785  mov     r14d, eax
0x180050788  test    eax, eax
0x18005078a  jz      short loc_1800507E1
0x18005078c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180050793  jz      short loc_1800507D1
0x180050795  mov     r8d, eax
0x180050798  lea     rdx, aEnableordisabl_1; "EnableOrDisableIPForwarding: Querying r"...
0x18005079f  lea     rcx, [rbp+910h+var_840]
0x1800507a6  mov     word ptr [rbp+910h+var_840], di
0x1800507ad  call    FormatRRASErrorString
0x1800507b2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800507b9  jz      short loc_1800507D1
0x1800507bb  lea     r8, [rbp+910h+var_840]
0x1800507c2  mov     rdx, r13
0x1800507c5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800507cc  call    McTemplateU0z_EventWriteTransfer
0x1800507d1  mov     ebx, 0C000000Dh
0x1800507d6  jmp     loc_180050ADD
0x1800507db  mov     r12, [rbp+910h+Resource]
0x1800507df  jmp     short loc_1800507E6
0x1800507e1  mov     ebx, 0C000000Dh
0x1800507e6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800507ea  inc     rax
0x1800507ed  cmp     [r12+rax*2], di
0x1800507f2  jnz     short loc_1800507EA
0x1800507f4  test    eax, eax
0x1800507f6  jz      loc_180050ADD
0x1800507fc  dec     eax
0x1800507fe  lea     rcx, [r12+2]; StringUuid
0x180050803  lea     rdx, [rbp+910h+Uuid]; Uuid
0x180050807  mov     [r12+rax*2], di
0x18005080c  call    cs:__imp_UuidFromStringW
0x180050812  test    eax, eax
0x180050814  jz      short loc_18005086E
0x180050816  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18005081d  mov     r14d, 3EBh
0x180050823  jz      loc_180050ADD
0x180050829  mov     r8d, r14d
0x18005082c  mov     word ptr [rbp+910h+var_840], di
0x180050833  lea     rdx, aEnableordisabl_3; "EnableOrDisableIPForwarding: UuidFromSt"...
0x18005083a  lea     rcx, [rbp+910h+var_840]
0x180050841  call    FormatRRASErrorString
0x180050846  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18005084d  jz      loc_180050ADD
0x180050853  lea     r8, [rbp+910h+var_840]
0x18005085a  mov     rdx, r13
0x18005085d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180050864  call    McTemplateU0z_EventWriteTransfer
0x180050869  jmp     loc_180050ADD
0x18005086e  lea     rdx, [rbp+910h+InterfaceLuid]; InterfaceLuid
0x180050872  lea     rcx, [rbp+910h+Uuid]; InterfaceGuid
0x180050876  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18005087c  mov     r14d, eax
0x18005087f  test    eax, eax
0x180050881  jz      short loc_1800508BC
0x180050883  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18005088a  jz      loc_1800507D1
0x180050890  mov     r8d, eax
0x180050893  mov     word ptr [rbp+910h+var_840], di
0x18005089a  lea     rdx, aEnableordisabl_8; "EnableOrDisableIPForwarding: ConvertInt"...
0x1800508a1  lea     rcx, [rbp+910h+var_840]
0x1800508a8  call    FormatRRASErrorString
0x1800508ad  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800508b4  jz      loc_1800507D1
0x1800508ba  jmp     short loc_180050853
0x1800508bc  lea     rcx, [rbp+910h+Row]; Row
0x1800508c0  call    cs:__imp_InitializeIpInterfaceEntry
0x1800508c6  mov     rax, qword ptr [rbp+910h+InterfaceLuid]
0x1800508ca  lea     rcx, [rbp+910h+Row]; Row
0x1800508ce  cmp     [rsp+0A10h+var_998], edi
0x1800508d2  mov     qword ptr [rbp+910h+Row.InterfaceLuid], rax
0x1800508d6  mov     eax, 2
0x1800508db  mov     [rbp+910h+Row.Family], ax
0x1800508df  setnz   [rbp+910h+Row.ForwardingEnabled]
0x1800508e3  call    cs:__imp_SetIpInterfaceEntry
0x1800508e9  mov     r14d, eax
0x1800508ec  test    eax, eax
0x1800508ee  jz      loc_1800507D1
0x1800508f4  call    ?GetInstance@RtMgrRdConfigStore@@SAPEAV1@XZ; RtMgrRdConfigStore::GetInstance(void)
0x1800508f9  mov     rdi, rax
0x1800508fc  mov     [rsp+0A10h+var_9A0], 490h
0x180050904  add     rax, 0B8h
0x18005090a  mov     dl, 1; Wait
0x18005090c  mov     rcx, rax; Resource
0x18005090f  mov     [rbp+910h+Resource], rax
0x180050913  call    cs:__imp_RtlAcquireResourceShared
0x180050919  mov     rbx, [rdi+10h]
0x18005091d  mov     rbx, [rbx]
0x180050920  cmp     rbx, [rdi+10h]
0x180050924  jz      short loc_18005094B
0x180050926  mov     rsi, [rbx+20h]
0x18005092a  mov     rcx, rsi; this
0x18005092d  call    ?GetCompartmentId@RtMgrRoutingDomainConfig@@QEAAIXZ; RtMgrRoutingDomainConfig::GetCompartmentId(void)
0x180050932  cmp     eax, [rbp+910h+var_978]
0x180050935  jnz     short loc_18005091D
0x180050937  xor     edi, edi
0x180050939  lea     rdx, [rbp+910h+var_988]; struct _GUID *
0x18005093d  mov     rcx, rsi; this
0x180050940  mov     [rsp+0A10h+var_9A0], edi
0x180050944  call    ?GetRoutingDomainId@RtMgrRoutingDomainConfig@@QEAAXPEAU_GUID@@@Z; RtMgrRoutingDomainConfig::GetRoutingDomainId(_GUID *)
0x180050949  jmp     short loc_18005094D
0x18005094b  xor     edi, edi
0x18005094d  mov     rcx, [rbp+910h+Resource]; Resource
0x180050951  call    cs:__imp_RtlReleaseResource
0x180050957  cmp     [rsp+0A10h+var_9A0], edi
0x18005095b  jnz     short loc_1800509D3
0x18005095d  movzx   r9d, [rbp+910h+var_988.Data4+3]
0x180050962  movzx   eax, [rbp+910h+var_988.Data4+7]
0x180050966  movzx   ecx, [rbp+910h+var_988.Data4+6]
0x18005096a  movzx   edx, [rbp+910h+var_988.Data4+5]
0x18005096e  movzx   r8d, [rbp+910h+var_988.Data4+4]
0x180050973  movzx   r10d, [rbp+910h+var_988.Data4+2]
0x180050978  movzx   r11d, [rbp+910h+var_988.Data4+1]
0x18005097d  movzx   ebx, [rbp+910h+var_988.Data4]
  ... truncated ...
```
