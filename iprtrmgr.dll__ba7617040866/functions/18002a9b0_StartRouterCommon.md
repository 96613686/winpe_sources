# StartRouterCommon

- ea: `0x18002a9b0`
- end: `0x18002aeec`
- name: `StartRouterCommon`
- size: `1340`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a4f0`

## callees

- `0x180002040`
- `0x18000ac60`
- `0x18000c054`
- `0x18001fbc8`
- `0x18002a9b0`
- `0x18002c654`
- `0x180037278`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x18002aeb3`
- `ntdll!RtlInitializeResource` at `0x18002aeb3`
- `KERNEL32!GetVersionExA` at `0x18002abde`
- `KERNEL32!GetVersionExA` at `0x18002abde`
- `KERNEL32!LoadLibraryExA` at `0x18002aa83`
- `KERNEL32!LoadLibraryExA` at `0x18002aa83`
- `KERNEL32!FreeLibrary` at `0x18002ab6c`
- `KERNEL32!FreeLibrary` at `0x18002ab6c`
- `KERNEL32!GetLastError` at `0x18002aa95`
- `KERNEL32!GetLastError` at `0x18002ac08`
- `KERNEL32!GetLastError` at `0x18002aa95`
- `KERNEL32!GetLastError` at `0x18002ac08`
- `rtutils!TraceDeregisterA` at `0x18002ab7f`
- `rtutils!TraceDeregisterA` at `0x18002ab7f`
- `USER32!LoadStringA` at `0x18002ad41`
- `USER32!LoadStringA` at `0x18002ad5d`
- `USER32!LoadStringA` at `0x18002ad79`
- `USER32!LoadStringA` at `0x18002ad41`
- `USER32!LoadStringA` at `0x18002ad5d`
- `USER32!LoadStringA` at `0x18002ad79`
- `WS2_32!__imp_WSAGetLastError` at `0x18002ab26`
- `WS2_32!__imp_WSAGetLastError` at `0x18002ab26`
- `WS2_32!__imp_WSAStartup` at `0x18002ab0b`
- `WS2_32!__imp_WSAStartup` at `0x18002ab0b`

## string_xrefs

- `0x18002aa7a`: `IPRTRMGR.DLL`

## pseudocode

```c
__int64 __fastcall StartRouterCommon(__int64 a1, int a2, __int64 a3, int a4)
{
  __int64 result; // rax
  DWORD v9; // eax
  DWORD v10; // ebx
  unsigned int Error; // eax
  DWORD LastError; // eax
  const wchar_t *v13; // r8
  unsigned int inited; // eax
  unsigned int v15; // edi
  int v16; // edi
  struct RtMgrRdConfigStore *Instance; // rax
  struct RtMgrRdConfigStore *v18; // rbx
  _OSVERSIONINFOA VersionInformation; // [rsp+30h] [rbp-D0h] BYREF
  char v20; // [rsp+CAh] [rbp-36h]
  WSAData WSAData; // [rsp+D0h] [rbp-30h] BYREF
  int v22; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v23[2044]; // [rsp+274h] [rbp+174h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  memset_0(&VersionInformation, 0, 0x9Cu);
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  if ( g_fRouterManagerInitialized )
    return 4317;
  if ( (unsigned int)VerifyOrStartIpStack() )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrMgrTraceError,
        L"StartRouter: Unable to start ip stack.");
    return 1068;
  }
  else
  {
    g_hOwnModule = LoadLibraryExA("IPRTRMGR.DLL", 0, 0);
    if ( g_hOwnModule )
    {
      LODWORD(RouterState) = 0;
      g_dwNextICBSeqNumberCounter = 1;
      if ( WSAStartup(2u, &WSAData) )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v22) = 0;
          Error = WSAGetLastError();
          FormatRRASErrorString(&v22, L"StartRouter: WSAStartup failed. Error %d", Error);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v22);
        }
        FreeLibrary(g_hOwnModule);
        g_hOwnModule = 0;
        TraceDeregisterA(TraceHandle);
        return 1003;
      }
      else
      {
        RouterRoleLanOnly = a2;
        g_bEnableFwdRequestV4 = 1;
        g_bEnableFwdRequestV6 = 1;
        g_bFwdEnabledV4 = 0;
        g_bFwdEnabledV6 = 0;
        g_bSetRoutesToStack = 1;
        g_bEnableNetbtBcastFrowarding = 0;
        memset_0(&VersionInformation.dwMajorVersion, 0, 0x98u);
        VersionInformation.dwOSVersionInfoSize = 156;
        if ( GetVersionExA(&VersionInformation) )
        {
          if ( v20 == 1 )
            g_bSetRoutesToStack = 0;
        }
        else if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v22) = 0;
          LastError = GetLastError();
          FormatRRASErrorString(&v22, L"StartRouter: GetVersionEx failed with %d\n", LastError);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v22);
        }
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v13 = L"router";
          LOWORD(v22) = 0;
          if ( !g_bSetRoutesToStack )
            v13 = L"non-router";
          FormatRRASErrorString(&v22, L"\n\nStartRouter: Machine will run as %ws\n\n", v13);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v22);
        }
        g_bDisableMulticastForwarding = IsMulticastForwardingDisabled();
        inited = InitRouter(a3, a4);
        v15 = inited;
        if ( inited )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            LOWORD(v22) = 0;
            FormatRRASErrorString(&v22, L"StartRouter: InitRouter failed %d", inited);
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v22);
          }
          RouterManagerCleanup(-1);
          result = v15;
          LODWORD(RouterState) = 2;
        }
        else
        {
          LoadStringA(g_hOwnModule, 0x2706u, g_rgcLoopbackString, 257);
          LoadStringA(g_hOwnModule, 0x2707u, g_rgcInternalString, 257);
          LoadStringA(g_hOwnModule, 0x2708u, g_rgcWanString, 257);
          qword_18008C0E8 = (__int64)DemandDialRequest;
          qword_18008C0F0 = (__int64)SetInterfaceReceiveType;
          qword_18008C0F8 = (__int64)ValidateRouteForProtocol;
          qword_18008C130 = (__int64)GetRouterId;
          qword_18008C138 = (__int64)RmHasBoundary;
          qword_18008C140 = (__int64)ValidateRouteForProtocolEx;
          qword_18008C148 = (__int64)GetRoutingDomainInfoForProtocol;
          qword_18008C150 = (__int64)GetInterfaceInformation;
          if ( *(_DWORD *)(a1 + 272) )
            dword_18008C0E4 |= 1u;
          v16 = *(_DWORD *)(a1 + 272);
          ConnectInterface = *(_QWORD *)(a1 + 200);
          SaveInterfaceInfo = *(_QWORD *)(a1 + 216);
          RestoreInterfaceInfo = *(_QWORD *)(a1 + 224);
          RouterStopped = *(_QWORD *)(a1 + 240);
          SaveGlobalInfo = *(_QWORD *)(a1 + 232);
          EnableInterfaceWithDIM = *(_QWORD *)(a1 + 248);
          GetInterfaceHandle = *(_QWORD *)(a1 + 264);
          GetInterfaceDeviceGuid = *(_QWORD *)(a1 + 336);
          GetRoutingDomainIdForInterface = *(_QWORD *)(a1 + 344);
          GetInfoForTenantInterface = *(_QWORD *)(a1 + 352);
          IPRouterHeap = IPRouterHeap;
          Instance = RtMgrRdConfigStore::GetInstance();
          v18 = Instance;
          if ( !*(_DWORD *)Instance )
          {
            RtlInitializeResource((PRTL_RESOURCE)((char *)Instance + 184));
            *((_DWORD *)v18 + 1) = v16;
            *(_DWORD *)v18 = 1;
          }
          return 0;
        }
      }
    }
    else
    {
      v9 = GetLastError();
      v10 = v9;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v22) = 0;
        FormatRRASErrorString(&v22, L"StartRouter: Unable to load itself. %d", v9);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v22);
      }
      return v10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002a9b0  mov     [rsp-8+arg_0], rbx
0x18002a9b5  mov     [rsp-8+arg_8], rsi
0x18002a9ba  push    rbp
0x18002a9bb  push    rdi
0x18002a9bc  push    r12
0x18002a9be  push    r14
0x18002a9c0  push    r15
0x18002a9c2  lea     rbp, [rsp-980h]
0x18002a9ca  sub     rsp, 0A80h
0x18002a9d1  mov     rax, cs:__security_cookie
0x18002a9d8  xor     rax, rsp
0x18002a9db  mov     [rbp+9A0h+var_30], rax
0x18002a9e2  mov     rsi, r8
0x18002a9e5  mov     edi, edx
0x18002a9e7  mov     rbx, rcx
0x18002a9ea  xor     edx, edx; Val
0x18002a9ec  mov     r8d, 198h; Size
0x18002a9f2  lea     rcx, [rbp+9A0h+WSAData]; void *
0x18002a9f6  mov     r14d, r9d
0x18002a9f9  call    memset_0
0x18002a9fe  xor     edx, edx; Val
0x18002aa00  lea     rcx, [rsp+0AA0h+VersionInformation]; void *
0x18002aa05  mov     r8d, 9Ch; Size
0x18002aa0b  call    memset_0
0x18002aa10  xor     r15d, r15d
0x18002aa13  lea     rcx, [rbp+9A0h+var_82C]; void *
0x18002aa1a  xor     edx, edx; Val
0x18002aa1c  mov     [rbp+9A0h+var_830], r15d
0x18002aa23  mov     r8d, 7FCh; Size
0x18002aa29  call    memset_0
0x18002aa2e  cmp     cs:g_fRouterManagerInitialized, r15d
0x18002aa35  jz      short loc_18002AA41
0x18002aa37  mov     eax, 10DDh
0x18002aa3c  jmp     loc_18002AEC1
0x18002aa41  call    VerifyOrStartIpStack
0x18002aa46  test    eax, eax
0x18002aa48  jz      short loc_18002AA77
0x18002aa4a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002aa51  jz      short loc_18002AA6D
0x18002aa53  lea     r8, aStartrouterUna; "StartRouter: Unable to start ip stack."
0x18002aa5a  lea     rdx, RasRtrMgrTraceError
0x18002aa61  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002aa68  call    McTemplateU0z_EventWriteTransfer
0x18002aa6d  mov     eax, 42Ch
0x18002aa72  jmp     loc_18002AEC1
0x18002aa77  xor     r8d, r8d; dwFlags
0x18002aa7a  lea     rcx, LibFileName; "IPRTRMGR.DLL"
0x18002aa81  xor     edx, edx; hFile
0x18002aa83  call    cs:__imp_LoadLibraryExA
0x18002aa89  mov     cs:g_hOwnModule, rax
0x18002aa90  test    rax, rax
0x18002aa93  jnz     short loc_18002AAEE
0x18002aa95  call    cs:__imp_GetLastError
0x18002aa9b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002aaa2  mov     ebx, eax
0x18002aaa4  jz      short loc_18002AAE7
0x18002aaa6  mov     r8d, eax
0x18002aaa9  mov     word ptr [rbp+9A0h+var_830], r15w
0x18002aab1  lea     rdx, aStartrouterUna_0; "StartRouter: Unable to load itself. %d"
0x18002aab8  lea     rcx, [rbp+9A0h+var_830]
0x18002aabf  call    FormatRRASErrorString
0x18002aac4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002aacb  jz      short loc_18002AAE7
0x18002aacd  lea     r8, [rbp+9A0h+var_830]
0x18002aad4  lea     rdx, RasRtrMgrTraceError
0x18002aadb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002aae2  call    McTemplateU0z_EventWriteTransfer
0x18002aae7  mov     eax, ebx
0x18002aae9  jmp     loc_18002AEC1
0x18002aaee  mov     r12d, 1
0x18002aaf4  mov     dword ptr cs:RouterState, r15d
0x18002aafb  lea     rdx, [rbp+9A0h+WSAData]; lpWSAData
0x18002aaff  mov     cs:g_dwNextICBSeqNumberCounter, r12d
0x18002ab06  lea     ecx, [r12+1]; wVersionRequested
0x18002ab0b  call    cs:__imp_WSAStartup
0x18002ab11  test    eax, eax
0x18002ab13  jz      short loc_18002AB8F
0x18002ab15  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002ab1c  jz      short loc_18002AB65
0x18002ab1e  mov     word ptr [rbp+9A0h+var_830], r15w
0x18002ab26  call    cs:__imp_WSAGetLastError
0x18002ab2c  mov     r8d, eax
0x18002ab2f  lea     rdx, aStartrouterWsa; "StartRouter: WSAStartup failed. Error %"...
0x18002ab36  lea     rcx, [rbp+9A0h+var_830]
0x18002ab3d  call    FormatRRASErrorString
0x18002ab42  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002ab49  jz      short loc_18002AB65
0x18002ab4b  lea     r8, [rbp+9A0h+var_830]
0x18002ab52  lea     rdx, RasRtrMgrTraceError
0x18002ab59  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002ab60  call    McTemplateU0z_EventWriteTransfer
0x18002ab65  mov     rcx, cs:g_hOwnModule; hLibModule
0x18002ab6c  call    cs:__imp_FreeLibrary
0x18002ab72  mov     ecx, cs:TraceHandle; dwTraceID
0x18002ab78  mov     cs:g_hOwnModule, r15
0x18002ab7f  call    cs:__imp_TraceDeregisterA
0x18002ab85  mov     eax, 3EBh
0x18002ab8a  jmp     loc_18002AEC1
0x18002ab8f  xor     edx, edx; Val
0x18002ab91  mov     cs:RouterRoleLanOnly, edi
0x18002ab97  mov     r8d, 98h; Size
0x18002ab9d  mov     cs:g_bEnableFwdRequestV4, r12d
0x18002aba4  lea     rcx, [rsp+0AA0h+VersionInformation.dwMajorVersion]; void *
0x18002aba9  mov     cs:g_bEnableFwdRequestV6, r12d
0x18002abb0  mov     cs:g_bFwdEnabledV4, r15d
0x18002abb7  mov     cs:g_bFwdEnabledV6, r15d
0x18002abbe  mov     cs:g_bSetRoutesToStack, r12d
0x18002abc5  mov     cs:g_bEnableNetbtBcastFrowarding, r15d
0x18002abcc  call    memset_0
0x18002abd1  lea     rcx, [rsp+0AA0h+VersionInformation]; lpVersionInformation
0x18002abd6  mov     [rsp+0AA0h+VersionInformation.dwOSVersionInfoSize], 9Ch
0x18002abde  call    cs:__imp_GetVersionExA
0x18002abe4  test    eax, eax
0x18002abe6  jz      short loc_18002ABF7
0x18002abe8  cmp     [rbp+9A0h+var_9D6], r12b
0x18002abec  jnz     short loc_18002AC47
0x18002abee  mov     cs:g_bSetRoutesToStack, r15d
0x18002abf5  jmp     short loc_18002AC47
0x18002abf7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002abfe  jz      short loc_18002AC47
0x18002ac00  mov     word ptr [rbp+9A0h+var_830], r15w
0x18002ac08  call    cs:__imp_GetLastError
0x18002ac0e  mov     r8d, eax
0x18002ac11  lea     rdx, aStartrouterGet; "StartRouter: GetVersionEx failed with %"...
0x18002ac18  lea     rcx, [rbp+9A0h+var_830]
0x18002ac1f  call    FormatRRASErrorString
0x18002ac24  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002ac2b  jz      short loc_18002AC47
0x18002ac2d  lea     r8, [rbp+9A0h+var_830]
0x18002ac34  lea     rdx, RasRtrMgrTraceError
0x18002ac3b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002ac42  call    McTemplateU0z_EventWriteTransfer
0x18002ac47  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18002ac4e  jge     short loc_18002ACA7
0x18002ac50  cmp     cs:g_bSetRoutesToStack, r15d
0x18002ac57  lea     rax, aNonRouter; "non-router"
0x18002ac5e  lea     r8, aRouter; "router"
0x18002ac65  mov     word ptr [rbp+9A0h+var_830], r15w
0x18002ac6d  cmovz   r8, rax
0x18002ac71  lea     rdx, aStartrouterMac; "\n\nStartRouter: Machine will run as %w"...
0x18002ac78  lea     rcx, [rbp+9A0h+var_830]
0x18002ac7f  call    FormatRRASErrorString
0x18002ac84  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18002ac8b  jge     short loc_18002ACA7
0x18002ac8d  lea     r8, [rbp+9A0h+var_830]
0x18002ac94  lea     rdx, RasRtrmgrTraceInfo
0x18002ac9b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002aca2  call    McTemplateU0z_EventWriteTransfer
0x18002aca7  call    IsMulticastForwardingDisabled
0x18002acac  mov     edx, r14d
0x18002acaf  mov     cs:g_bDisableMulticastForwarding, eax
0x18002acb5  mov     rcx, rsi
0x18002acb8  call    InitRouter
0x18002acbd  mov     edi, eax
0x18002acbf  test    eax, eax
0x18002acc1  jz      short loc_18002AD26
0x18002acc3  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18002acca  jge     short loc_18002AD0D
0x18002accc  mov     r8d, eax
0x18002accf  mov     word ptr [rbp+9A0h+var_830], r15w
0x18002acd7  lea     rdx, aStartrouterIni_1; "StartRouter: InitRouter failed %d"
0x18002acde  lea     rcx, [rbp+9A0h+var_830]
0x18002ace5  call    FormatRRASErrorString
0x18002acea  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18002acf1  jge     short loc_18002AD0D
0x18002acf3  lea     r8, [rbp+9A0h+var_830]
0x18002acfa  lea     rdx, RasRtrmgrTraceInfo
0x18002ad01  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002ad08  call    McTemplateU0z_EventWriteTransfer
0x18002ad0d  or      ecx, 0FFFFFFFFh
0x18002ad10  call    RouterManagerCleanup
0x18002ad15  mov     eax, edi
0x18002ad17  mov     dword ptr cs:RouterState, 2
0x18002ad21  jmp     loc_18002AEC1
0x18002ad26  mov     rcx, cs:g_hOwnModule; hInstance
0x18002ad2d  lea     r8, g_rgcLoopbackString; lpBuffer
0x18002ad34  mov     edi, 101h
0x18002ad39  mov     edx, 2706h; uID
0x18002ad3e  mov     r9d, edi; cchBufferMax
0x18002ad41  call    cs:__imp_LoadStringA
0x18002ad47  mov     rcx, cs:g_hOwnModule; hInstance
0x18002ad4e  lea     r8, g_rgcInternalString; lpBuffer
0x18002ad55  mov     r9d, edi; cchBufferMax
0x18002ad58  mov     edx, 2707h; uID
0x18002ad5d  call    cs:__imp_LoadStringA
0x18002ad63  mov     rcx, cs:g_hOwnModule; hInstance
0x18002ad6a  lea     r8, g_rgcWanString; lpBuffer
0x18002ad71  mov     r9d, edi; cchBufferMax
0x18002ad74  mov     edx, 2708h; uID
0x18002ad79  call    cs:__imp_LoadStringA
0x18002ad7f  lea     rax, DemandDialRequest
0x18002ad86  mov     cs:qword_18008C0E8, rax
0x18002ad8d  lea     rax, SetInterfaceReceiveType
0x18002ad94  mov     cs:qword_18008C0F0, rax
0x18002ad9b  lea     rax, ValidateRouteForProtocol
0x18002ada2  mov     cs:qword_18008C0F8, rax
0x18002ada9  lea     rax, GetRouterId
0x18002adb0  mov     cs:qword_18008C130, rax
0x18002adb7  lea     rax, RmHasBoundary
0x18002adbe  mov     cs:qword_18008C138, rax
0x18002adc5  lea     rax, ValidateRouteForProtocolEx
0x18002adcc  mov     cs:qword_18008C140, rax
0x18002add3  lea     rax, GetRoutingDomainInfoForProtocol
0x18002adda  mov     cs:qword_18008C148, rax
0x18002ade1  lea     rax, GetInterfaceInformation
0x18002ade8  mov     cs:qword_18008C150, rax
0x18002adef  cmp     [rbx+110h], r15d
0x18002adf6  jz      short loc_18002ADFF
0x18002adf8  or      cs:dword_18008C0E4, r12d
0x18002adff  mov     rax, [rbx+0C8h]
0x18002ae06  mov     edi, [rbx+110h]
0x18002ae0c  mov     cs:ConnectInterface, rax
0x18002ae13  mov     rax, [rbx+0D8h]
0x18002ae1a  mov     cs:SaveInterfaceInfo, rax
0x18002ae21  mov     rax, [rbx+0E0h]
0x18002ae28  mov     cs:RestoreInterfaceInfo, rax
0x18002ae2f  mov     rax, [rbx+0F0h]
0x18002ae36  mov     cs:RouterStopped, rax
0x18002ae3d  mov     rax, [rbx+0E8h]
0x18002ae44  mov     cs:SaveGlobalInfo, rax
0x18002ae4b  mov     rax, [rbx+0F8h]
0x18002ae52  mov     cs:EnableInterfaceWithDIM, rax
0x18002ae59  mov     rax, [rbx+108h]
0x18002ae60  mov     cs:GetInterfaceHandle, rax
0x18002ae67  mov     rax, [rbx+150h]
0x18002ae6e  mov     cs:GetInterfaceDeviceGuid, rax
0x18002ae75  mov     rax, [rbx+158h]
0x18002ae7c  mov     cs:GetRoutingDomainIdForInterface, rax
0x18002ae83  mov     rax, [rbx+160h]
0x18002ae8a  mov     cs:GetInfoForTenantInterface, rax
0x18002ae91  mov     rax, cs:IPRouterHeap
0x18002ae98  mov     cs:?IPRouterHeap@@3PEAXEA, rax; void * IPRouterHeap
0x18002ae9f  call    ?GetInstance@RtMgrRdConfigStore@@SAPEAV1@XZ; RtMgrRdConfigStore::GetInstance(void)
0x18002aea4  mov     rbx, rax
0x18002aea7  cmp     [rax], r15d
0x18002aeaa  jnz     short loc_18002AEBF
0x18002aeac  lea     rcx, [rax+0B8h]; Resource
0x18002aeb3  call    cs:__imp_RtlInitializeResource
0x18002aeb9  mov     [rbx+4], edi
0x18002aebc  mov     [rbx], r12d
0x18002aebf  xor     eax, eax
0x18002aec1  mov     rcx, [rbp+9A0h+var_30]
0x18002aec8  xor     rcx, rsp; StackCookie
0x18002aecb  call    __security_check_cookie
0x18002aed0  lea     r11, [rsp+0AA0h+var_20]
0x18002aed8  mov     rbx, [r11+30h]
0x18002aedc  mov     rsi, [r11+38h]
0x18002aee0  mov     rsp, r11
0x18002aee3  pop     r15
0x18002aee5  pop     r14
0x18002aee7  pop     r12
0x18002aee9  pop     rdi
0x18002aeea  pop     rbp
0x18002aeeb  retn
```
