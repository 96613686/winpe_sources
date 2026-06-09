# RPCServiceStartThread(void *)

- ea: `0x180036f60`
- end: `0x180037365`
- name: `?RPCServiceStartThread@@YAKPEAX@Z`
- size: `1029`
- prototype: `void __fastcall __noreturn(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000bb84`
- `0x18000f0b4`
- `0x18001ad74`
- `0x18001ae3c`
- `0x18001aea4`
- `0x180022910`
- `0x180036f60`
- `0x18003827c`
- `0x180038aa0`

## import_xrefs

- `mstlsapi!__imp_TLSInDomain` at `0x1800370e9`
- `mstlsapi!__imp_TLSInDomain` at `0x1800370e9`
- `ADVAPI32!RegGetValueW` at `0x180037166`
- `ADVAPI32!RegGetValueW` at `0x180037166`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180036fef`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180036fef`
- `RPCRT4!RpcServerInqBindings` at `0x180037084`
- `RPCRT4!RpcServerInqBindings` at `0x180037084`
- `RPCRT4!RpcEpRegisterW` at `0x1800370b6`
- `RPCRT4!RpcEpRegisterW` at `0x1800370b6`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180037274`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180037274`
- `RPCRT4!RpcServerRegisterIf2` at `0x1800372cf`
- `RPCRT4!RpcServerRegisterIf2` at `0x1800372cf`
- `RPCRT4!RpcServerRegisterIf` at `0x18003720b`
- `RPCRT4!RpcServerRegisterIf` at `0x18003720b`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800372f7`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800372f7`
- `RPCRT4!RpcServerUseProtseqW` at `0x180036fc9`
- `RPCRT4!RpcServerUseProtseqW` at `0x18003705e`
- `RPCRT4!RpcServerUseProtseqW` at `0x180036fc9`
- `RPCRT4!RpcServerUseProtseqW` at `0x18003705e`
- `KERNEL32!ExitThread` at `0x180037358`
- `KERNEL32!ExitThread` at `0x180037358`

## string_xrefs

- `0x180037159`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Parameters`
- `0x180036f86`: `RPCServiceStartThread`

## pseudocode

```c
void __fastcall __noreturn RPCServiceStartThread(PVOID Parameter)
{
  BOOL v1; // ebx
  unsigned __int16 *v2; // rcx
  int v3; // edi
  unsigned int v4; // eax
  unsigned int v5; // ebx
  CrimsonHelper *Instance; // rax
  RPC_STATUS v7; // eax
  int v8; // ecx
  BOOL v9; // ebx
  int v10; // eax
  int v11; // eax
  PVOID *v12; // rcx
  RPC_STATUS v13; // eax
  RPC_STATUS v14; // ebx
  RPC_BINDING_VECTOR *BindingVector; // [rsp+40h] [rbp-20h] BYREF
  struct _EVENT_DESCRIPTOR v16; // [rsp+50h] [rbp-10h] BYREF
  int v17; // [rsp+A8h] [rbp+48h] BYREF
  int pvData; // [rsp+B0h] [rbp+50h] BYREF
  DWORD pcbData; // [rsp+B8h] [rbp+58h] BYREF

  BindingVector = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids,
      L"RPCServiceStartThread");
  v1 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, 0) == 0;
  v3 = v1 + 1;
  if ( RpcServerUseProtseqEpW((RPC_WSTR)L"ncacn_np", 0xAu, (RPC_WSTR)L"\\pipe\\HydraLsPipe", 0) )
    v3 = v1;
  v4 = SetSecurityDescriptorOnNamedPipe(v2);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, v4);
    v5 = 4142;
    Instance = CrimsonHelper::getInstance();
    CrimsonHelper::RaiseEvent(Instance, &TLS_E_CVT_SECURITY_DESCRIPTOR);
  }
  else
  {
    v7 = RpcServerUseProtseqW((RPC_WSTR)L"ncacn_ip_tcp", 0xAu, 0);
    v8 = v3 + 1;
    if ( v7 )
      v8 = v3;
    if ( v8 )
    {
      if ( RpcServerInqBindings(&BindingVector) )
      {
        v5 = -1073479677;
      }
      else if ( RpcEpRegisterW(qword_1800AC110, BindingVector, 0, (RPC_WSTR)&pszSrc) )
      {
        v5 = -1073479676;
      }
      else
      {
        pvData = 0;
        v9 = 1;
        pcbData = 4;
        v17 = 1;
        v10 = TLSInDomain(&v17, 0);
        if ( v10 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              32,
              (unsigned int)WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids,
              (unsigned int)L"RPCServiceStartThread",
              v10);
          v11 = 1;
          v17 = 1;
        }
        else
        {
          v11 = v17;
        }
        if ( v11 )
          goto LABEL_59;
        if ( RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Parameters",
               L"DisableWorkgroupAuthEnforcement",
               0x10u,
               0,
               &pvData,
               &pcbData) )
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              34,
              WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids,
              L"RPCServiceStartThread");
            v12 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
        else
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              (unsigned int)WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids,
              (unsigned int)L"RPCServiceStartThread",
              pvData);
            v12 = (PVOID *)WPP_GLOBAL_Control;
          }
          v9 = pvData == 0;
        }
        v17 = v9;
        if ( v9 )
        {
LABEL_59:
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RDLicensingAuthFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RDLicensingAuthFix>::GetImpl'::`2'::impl) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                35,
                WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids,
                L"RPCServiceStartThread");
            v13 = RpcServerRegisterIfEx(qword_1800AC110, 0, 0, 8u, 0x4D2u, (RPC_IF_CALLBACK_FN *)TLSRpcSecurityCallback);
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                36,
                WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids,
                L"RPCServiceStartThread");
            v13 = RpcServerRegisterIf2(
                    qword_1800AC110,
                    0,
                    0,
                    8u,
                    0x4D2u,
                    0,
                    (RPC_IF_CALLBACK_FN *)TLSRpcSecurityCallback);
          }
        }
        else
        {
          if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x1000) != 0 )
            WPP_SF_S(v12[2], 37, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, L"RPCServiceStartThread");
          v13 = RpcServerRegisterIf(qword_1800AC110, 0, 0);
        }
        if ( v13 )
        {
          v5 = -1073479678;
        }
        else
        {
          v14 = RpcServerRegisterAuthInfoW((RPC_WSTR)L"TermServLicensing", 9u, 0, 0);
          if ( !v14 )
            goto LABEL_53;
          v5 = -1073479673;
        }
      }
    }
    else
    {
      v5 = -1073479679;
    }
  }
  v16 = (struct _EVENT_DESCRIPTOR)TLS_E_SERVICEINIT;
  TLSLogEvent(&v16, 0xC001000F, v5);
  v14 = -1073676271;
LABEL_53:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids,
      L"RPCServiceStartThread");
  ExitThread(v14);
}

```

## disassembly

```asm
0x180036f60  push    rbp
0x180036f62  push    rbx
0x180036f63  push    rdi
0x180036f64  push    r12
0x180036f66  push    r13
0x180036f68  push    r14
0x180036f6a  push    r15
0x180036f6c  mov     rbp, rsp
0x180036f6f  sub     rsp, 60h
0x180036f73  and     [rbp+BindingVector], 0
0x180036f78  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f7f  lea     r14, WPP_GLOBAL_Control
0x180036f86  lea     r13, aRpcservicestar; "RPCServiceStartThread"
0x180036f8d  mov     r15d, 1000h
0x180036f93  lea     r12, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids
0x180036f9a  cmp     rcx, r14
0x180036f9d  jz      short loc_180036FB9
0x180036f9f  test    [rcx+1Ch], r15d
0x180036fa3  jz      short loc_180036FB9
0x180036fa5  mov     rcx, [rcx+10h]
0x180036fa9  mov     edx, 1Eh
0x180036fae  mov     r9, r13
0x180036fb1  mov     r8, r12
0x180036fb4  call    WPP_SF_S
0x180036fb9  xor     r8d, r8d; SecurityDescriptor
0x180036fbc  lea     rcx, Protseq; "ncalrpc"
0x180036fc3  lea     edi, [r8+0Ah]
0x180036fc7  mov     edx, edi; MaxCalls
0x180036fc9  call    cs:__imp_RpcServerUseProtseqW
0x180036fd0  nop     dword ptr [rax+rax+00h]
0x180036fd5  xor     ebx, ebx
0x180036fd7  lea     r8, Endpoint; "\\pipe\\HydraLsPipe"
0x180036fde  test    eax, eax
0x180036fe0  lea     rcx, aNcacnNp; "ncacn_np"
0x180036fe7  mov     edx, edi; MaxCalls
0x180036fe9  setz    bl
0x180036fec  xor     r9d, r9d; SecurityDescriptor
0x180036fef  call    cs:__imp_RpcServerUseProtseqEpW
0x180036ff6  nop     dword ptr [rax+rax+00h]
0x180036ffb  test    eax, eax
0x180036ffd  lea     edi, [rbx+1]
0x180037000  cmovnz  edi, ebx
0x180037003  call    ?SetSecurityDescriptorOnNamedPipe@@YAJPEAG@Z; SetSecurityDescriptorOnNamedPipe(ushort *)
0x180037008  test    eax, eax
0x18003700a  jz      short loc_180037050
0x18003700c  mov     rcx, cs:WPP_GLOBAL_Control
0x180037013  cmp     rcx, r14
0x180037016  jz      short loc_180037032
0x180037018  test    byte ptr [rcx+1Ch], 20h
0x18003701c  jz      short loc_180037032
0x18003701e  mov     rcx, [rcx+10h]
0x180037022  mov     edx, 1Fh
0x180037027  mov     r9d, eax
0x18003702a  mov     r8, r12
0x18003702d  call    WPP_SF_D
0x180037032  mov     ebx, 102Eh
0x180037037  call    ?getInstance@CrimsonHelper@@SAAEAV1@XZ; CrimsonHelper::getInstance(void)
0x18003703c  mov     rcx, rax; this
0x18003703f  lea     rdx, TLS_E_CVT_SECURITY_DESCRIPTOR; struct _EVENT_DESCRIPTOR *
0x180037046  call    ?RaiseEvent@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEvent(_EVENT_DESCRIPTOR const &)
0x18003704b  jmp     loc_18003730E
0x180037050  xor     r8d, r8d; SecurityDescriptor
0x180037053  lea     rcx, aNcacnIpTcp; "ncacn_ip_tcp"
0x18003705a  lea     edx, [r8+0Ah]; MaxCalls
0x18003705e  call    cs:__imp_RpcServerUseProtseqW
0x180037065  nop     dword ptr [rax+rax+00h]
0x18003706a  test    eax, eax
0x18003706c  lea     ecx, [rdi+1]
0x18003706f  cmovnz  ecx, edi
0x180037072  test    ecx, ecx
0x180037074  jnz     short loc_180037080
0x180037076  mov     ebx, 0C0040001h
0x18003707b  jmp     loc_18003730E
0x180037080  lea     rcx, [rbp+BindingVector]; BindingVector
0x180037084  call    cs:__imp_RpcServerInqBindings
0x18003708b  nop     dword ptr [rax+rax+00h]
0x180037090  test    eax, eax
0x180037092  jz      short loc_18003709E
0x180037094  mov     ebx, 0C0040003h
0x180037099  jmp     loc_18003730E
0x18003709e  mov     rdx, [rbp+BindingVector]; BindingVector
0x1800370a2  lea     rdi, qword_1800AC110
0x1800370a9  mov     rcx, rdi; IfSpec
0x1800370ac  lea     r9, pszSrc; Annotation
0x1800370b3  xor     r8d, r8d; UuidVector
0x1800370b6  call    cs:__imp_RpcEpRegisterW
0x1800370bd  nop     dword ptr [rax+rax+00h]
0x1800370c2  test    eax, eax
0x1800370c4  jz      short loc_1800370D0
0x1800370c6  mov     ebx, 0C0040004h
0x1800370cb  jmp     loc_18003730E
0x1800370d0  and     [rbp+arg_10], 0
0x1800370d4  lea     rcx, [rbp+arg_8]
0x1800370d8  mov     ebx, 1
0x1800370dd  mov     [rbp+arg_18], 4
0x1800370e4  xor     edx, edx
0x1800370e6  mov     [rbp+arg_8], ebx
0x1800370e9  call    cs:__imp_TLSInDomain
0x1800370f0  nop     dword ptr [rax+rax+00h]
0x1800370f5  test    eax, eax
0x1800370f7  jz      short loc_180037128
0x1800370f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180037100  cmp     rcx, r14
0x180037103  jz      short loc_180037121
0x180037105  test    [rcx+1Ch], r15d
0x180037109  jz      short loc_180037121
0x18003710b  mov     rcx, [rcx+10h]
0x18003710f  lea     edx, [rbx+1Fh]
0x180037112  mov     r9, r13
0x180037115  mov     [rsp+60h+MaxCalls], eax
0x180037119  mov     r8, r12
0x18003711c  call    WPP_SF_SD
0x180037121  mov     eax, ebx
0x180037123  mov     [rbp+arg_8], ebx
0x180037126  jmp     short loc_18003712B
0x180037128  mov     eax, [rbp+arg_8]
0x18003712b  test    eax, eax
0x18003712d  jnz     loc_18003721C
0x180037133  lea     rax, [rbp+arg_18]
0x180037137  mov     r9d, 10h; dwFlags
0x18003713d  mov     [rsp+60h+pcbData], rax; pcbData
0x180037142  lea     r8, aDisableworkgro; "DisableWorkgroupAuthEnforcement"
0x180037149  lea     rax, [rbp+arg_10]
0x18003714d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180037154  mov     [rsp+60h+pvData], rax; pvData
0x180037159  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x180037160  and     qword ptr [rsp+60h+MaxCalls], 0
0x180037166  call    cs:__imp_RegGetValueW
0x18003716d  nop     dword ptr [rax+rax+00h]
0x180037172  test    eax, eax
0x180037174  jnz     short loc_1800371B2
0x180037176  mov     rcx, cs:WPP_GLOBAL_Control
0x18003717d  cmp     rcx, r14
0x180037180  jz      short loc_1800371A8
0x180037182  test    [rcx+1Ch], r15d
0x180037186  jz      short loc_1800371A8
0x180037188  mov     rcx, [rcx+10h]
0x18003718c  lea     edx, [rax+21h]
0x18003718f  mov     eax, [rbp+arg_10]
0x180037192  mov     r9, r13
0x180037195  mov     r8, r12
0x180037198  mov     [rsp+60h+MaxCalls], eax
0x18003719c  call    WPP_SF_SD
0x1800371a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800371a8  xor     ebx, ebx
0x1800371aa  cmp     [rbp+arg_10], ebx
0x1800371ad  setz    bl
0x1800371b0  jmp     short loc_1800371DF
0x1800371b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800371b9  cmp     rcx, r14
0x1800371bc  jz      short loc_1800371DF
0x1800371be  test    [rcx+1Ch], r15d
0x1800371c2  jz      short loc_1800371DF
0x1800371c4  mov     rcx, [rcx+10h]
0x1800371c8  mov     edx, 22h ; '"'
0x1800371cd  mov     r9, r13
0x1800371d0  mov     r8, r12
0x1800371d3  call    WPP_SF_S
0x1800371d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800371df  mov     [rbp+arg_8], ebx
0x1800371e2  test    ebx, ebx
0x1800371e4  jnz     short loc_18003721C
0x1800371e6  cmp     rcx, r14
0x1800371e9  jz      short loc_180037203
0x1800371eb  test    [rcx+1Ch], r15d
0x1800371ef  jz      short loc_180037203
0x1800371f1  mov     rcx, [rcx+10h]
0x1800371f5  lea     edx, [rbx+25h]
0x1800371f8  mov     r9, r13
0x1800371fb  mov     r8, r12
0x1800371fe  call    WPP_SF_S
0x180037203  xor     r8d, r8d; MgrEpv
0x180037206  xor     edx, edx; MgrTypeUuid
0x180037208  mov     rcx, rdi; IfSpec
0x18003720b  call    cs:__imp_RpcServerRegisterIf
0x180037212  nop     dword ptr [rax+rax+00h]
0x180037217  jmp     loc_1800372DB
0x18003721c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RDLicensingAuthFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RDLicensingAuthFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RDLicensingAuthFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RDLicensingAuthFix>::GetImpl(void)'::`2'::impl
0x180037223  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RDLicensingAuthFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RDLicensingAuthFix>::__private_IsEnabled(void)
0x180037228  test    al, al
0x18003722a  jz      short loc_180037282
0x18003722c  mov     rcx, cs:WPP_GLOBAL_Control
0x180037233  cmp     rcx, r14
0x180037236  jz      short loc_180037252
0x180037238  test    [rcx+1Ch], r15d
0x18003723c  jz      short loc_180037252
0x18003723e  mov     rcx, [rcx+10h]
0x180037242  mov     edx, 23h ; '#'
0x180037247  mov     r9, r13
0x18003724a  mov     r8, r12
0x18003724d  call    WPP_SF_S
0x180037252  lea     rax, ?TLSRpcSecurityCallback@@YAJPEAX0@Z; TLSRpcSecurityCallback(void *,void *)
0x180037259  mov     r9d, 8; Flags
0x18003725f  mov     [rsp+60h+pvData], rax; IfCallback
0x180037264  xor     r8d, r8d; MgrEpv
0x180037267  xor     edx, edx; MgrTypeUuid
0x180037269  mov     [rsp+60h+MaxCalls], 4D2h; MaxCalls
0x180037271  mov     rcx, rdi; IfSpec
0x180037274  call    cs:__imp_RpcServerRegisterIfEx
0x18003727b  nop     dword ptr [rax+rax+00h]
0x180037280  jmp     short loc_1800372DB
0x180037282  mov     rcx, cs:WPP_GLOBAL_Control
0x180037289  cmp     rcx, r14
0x18003728c  jz      short loc_1800372A8
0x18003728e  test    [rcx+1Ch], r15d
0x180037292  jz      short loc_1800372A8
0x180037294  mov     rcx, [rcx+10h]
0x180037298  mov     edx, 24h ; '$'
0x18003729d  mov     r9, r13
0x1800372a0  mov     r8, r12
0x1800372a3  call    WPP_SF_S
0x1800372a8  lea     rax, ?TLSRpcSecurityCallback@@YAJPEAX0@Z; TLSRpcSecurityCallback(void *,void *)
0x1800372af  mov     r9d, 8; Flags
0x1800372b5  mov     [rsp+60h+pcbData], rax; IfCallbackFn
0x1800372ba  xor     r8d, r8d; MgrEpv
0x1800372bd  and     dword ptr [rsp+60h+pvData], 0
0x1800372c2  xor     edx, edx; MgrTypeUuid
0x1800372c4  mov     rcx, rdi; IfSpec
0x1800372c7  mov     [rsp+60h+MaxCalls], 4D2h; MaxCalls
0x1800372cf  call    cs:__imp_RpcServerRegisterIf2
0x1800372d6  nop     dword ptr [rax+rax+00h]
0x1800372db  test    eax, eax
0x1800372dd  jz      short loc_1800372E6
0x1800372df  mov     ebx, 0C0040002h
0x1800372e4  jmp     short loc_18003730E
0x1800372e6  xor     r9d, r9d; Arg
0x1800372e9  lea     rcx, ServiceName; "TermServLicensing"
0x1800372f0  xor     r8d, r8d; GetKeyFn
0x1800372f3  lea     edx, [r9+9]; AuthnSvc
0x1800372f7  call    cs:__imp_RpcServerRegisterAuthInfoW
0x1800372fe  nop     dword ptr [rax+rax+00h]
0x180037303  mov     ebx, eax
0x180037305  test    eax, eax
0x180037307  jz      short loc_180037330
0x180037309  mov     ebx, 0C0040007h
0x18003730e  movups  xmm0, cs:TLS_E_SERVICEINIT
0x180037315  mov     r8d, ebx
0x180037318  lea     rcx, [rbp+var_10]; struct _EVENT_DESCRIPTOR
0x18003731c  mov     edx, 0C001000Fh; unsigned int
0x180037321  movdqu  xmmword ptr [rbp+var_10.Id], xmm0
0x180037326  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x18003732b  mov     ebx, 0C0010011h
0x180037330  mov     rcx, cs:WPP_GLOBAL_Control
0x180037337  cmp     rcx, r14
0x18003733a  jz      short loc_180037356
0x18003733c  test    [rcx+1Ch], r15d
0x180037340  jz      short loc_180037356
0x180037342  mov     rcx, [rcx+10h]
0x180037346  mov     edx, 26h ; '&'
0x18003734b  mov     r9, r13
0x18003734e  mov     r8, r12
0x180037351  call    WPP_SF_S
0x180037356  mov     ecx, ebx; dwExitCode
0x180037358  call    cs:__imp_ExitThread
```
