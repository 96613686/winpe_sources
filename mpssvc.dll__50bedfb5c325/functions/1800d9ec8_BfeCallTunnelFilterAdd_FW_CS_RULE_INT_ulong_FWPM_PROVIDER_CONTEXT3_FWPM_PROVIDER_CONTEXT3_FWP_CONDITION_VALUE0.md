# BfeCallTunnelFilterAdd(_FW_CS_RULE_INT_ *,ulong,FWPM_PROVIDER_CONTEXT3_ *,FWPM_PROVIDER_CONTEXT3_ *,FWP_CONDITION_VALUE0_ *,FWP_CONDITION_VALUE0_ *,_GUID *)

- ea: `0x1800d9ec8`
- end: `0x1800da2da`
- name: `?BfeCallTunnelFilterAdd@@YAKPEAU_FW_CS_RULE_INT_@@KPEAUFWPM_PROVIDER_CONTEXT3_@@1PEAUFWP_CONDITION_VALUE0_@@2PEAU_GUID@@@Z`
- size: `1042`
- prototype: `unsigned int(struct _FW_CS_RULE_INT_ *, unsigned int, struct FWPM_PROVIDER_CONTEXT3_ *, struct FWPM_PROVIDER_CONTEXT3_ *, struct FWP_CONDITION_VALUE0_ *, struct FWP_CONDITION_VALUE0_ *, struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800db9e4`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x18004f4ac`
- `0x18006e384`
- `0x1800729c0`
- `0x180073488`
- `0x1800d9c1c`
- `0x1800d9ec8`
- `0x1800daaa0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da17c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800da168`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800da168`
- `RPCRT4!UuidCreate` at `0x1800d9f6e`
- `RPCRT4!UuidCreate` at `0x1800d9f6e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800da10c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800da10c`
- `fwpuclnt!FwpmIPsecTunnelAddConditions0` at `0x1800da273`
- `fwpuclnt!FwpmIPsecTunnelAddConditions0` at `0x1800da273`

## string_xrefs

- `0x1800da105`: `fwpuclnt.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall BfeCallTunnelFilterAdd(
        struct _FW_CS_RULE_INT_ *a1,
        unsigned int a2,
        struct FWPM_PROVIDER_CONTEXT3_ *a3,
        struct FWPM_PROVIDER_CONTEXT3_ *a4,
        struct FWP_CONDITION_VALUE0_ *a5,
        struct FWP_CONDITION_VALUE0_ *a6,
        struct _GUID *a7)
{
  int v10; // ebx
  __int64 v11; // rcx
  _DWORD *v12; // rax
  BOOL v13; // eax
  RPC_STATUS v14; // eax
  unsigned int v15; // edi
  unsigned int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned int v19; // r14d
  __int64 v20; // rcx
  __int64 v21; // rcx
  unsigned int v22; // edx
  __int64 v23; // rcx
  HMODULE LibraryW; // rbx
  DWORD LastError; // eax
  unsigned int v26; // edx
  FARPROC ProcAddress; // rbx
  HMODULE v29; // [rsp+50h] [rbp-B0h] BYREF
  struct FWPM_PROVIDER_CONTEXT3_ *v30; // [rsp+58h] [rbp-A8h]
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+74h] [rbp-8Ch] BYREF
  int v34; // [rsp+7Ch] [rbp-84h]
  int v35; // [rsp+80h] [rbp-80h]
  _OWORD v36[8]; // [rsp+88h] [rbp-78h]

  v30 = a3;
  v32 = 0;
  memset_0(&v33, 0, 0x9Cu);
  v31 = 0;
  v10 = *((_DWORD *)a1 + 38) != *((_DWORD *)a1 + 43);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226>::GetImpl'::`2'::impl) )
  {
    v12 = (_DWORD *)*((_QWORD *)a4 + 9);
    v13 = v12 && (*v12 & 0x20000) != 0;
    v10 |= v13;
  }
  if ( v10 == 1 )
  {
    v14 = UuidCreate((UUID *)a4);
    v15 = v14;
    if ( v14 && v14 != 1824 && v14 != 1739 )
    {
      v16 = 628;
LABEL_46:
      IpsTraceError("BfeCallTunnelFilterAdd", v16, v14, 0);
      goto LABEL_47;
    }
  }
  else
  {
    *(struct _GUID *)a4 = *a7;
  }
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)a4 && *(_QWORD *)GUID_NULL.Data4 == *((_QWORD *)a4 + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v11);
  if ( v10 == 1 )
  {
    v17 = *(_QWORD *)(*(_QWORD *)a1 + 24LL);
    *((_QWORD *)a4 + 2) = v17;
    if ( !v17 )
      *((_QWORD *)a4 + 2) = L" ";
    v18 = *(_QWORD *)(*(_QWORD *)a1 + 32LL);
    if ( v18 )
      *((_QWORD *)a4 + 3) = v18;
    *((_QWORD *)a4 + 5) = &MipsProviderGuid;
  }
  v19 = 0;
  if ( a5 )
  {
    v32 = -638713634;
    v33 = *(_QWORD *)&FWPM_CONDITION_IP_LOCAL_ADDRESS.Data2;
    v34 = *(_DWORD *)&FWPM_CONDITION_IP_LOCAL_ADDRESS.Data4[4];
    v35 = 0;
    v36[0] = *a5;
    v19 = 1;
  }
  if ( a6 )
  {
    v20 = 5LL * v19;
    *(GUID *)(&v32 + 2 * v20) = FWPM_CONDITION_IP_REMOTE_ADDRESS;
    *((int *)v36 + 2 * v20) = 0;
    *(struct FWP_CONDITION_VALUE0_ *)((char *)v36 + 8 * v20) = *a6;
    ++v19;
  }
  if ( *((_QWORD *)a1 + 18) )
  {
    v31 = *((_QWORD *)a1 + 18);
    v21 = 5LL * v19;
    *(GUID *)(&v32 + 2 * v21) = FWPM_CONDITION_IP_LOCAL_INTERFACE;
    *((int *)v36 + 2 * v21) = 0;
    *((_DWORD *)v36 + 2 * v21) = 4;
    *((_QWORD *)v36 + v21 + 1) = &v31;
    ++v19;
  }
  v22 = *((_DWORD *)a1 + 38);
  if ( v22 <= 3 )
  {
    if ( !v10 )
      goto LABEL_44;
    v23 = 5LL * v19;
    *(GUID *)(&v32 + 2 * v23) = FWPM_CONDITION_CURRENT_PROFILE_ID;
    *((int *)v36 + 2 * v23) = 0;
    *((_DWORD *)v36 + 2 * v23) = 3;
    *((_DWORD *)v36 + 2 * v23 + 2) = *((_DWORD *)qword_1800FC150 + v22);
    ++v19;
  }
  if ( v10 != 1 )
  {
LABEL_44:
    v14 = FwpmIPsecTunnelAddConditions0(gvBfeEngineHandle, a2, a4, v19, &v32);
    v15 = v14;
    if ( v14 )
    {
      v16 = 751;
      goto LABEL_46;
    }
    goto LABEL_42;
  }
  LibraryW = LoadLibraryW(L"fwpuclnt.dll");
  v29 = LibraryW;
  if ( LibraryW || (LastError = GetLastError(), (v15 = LastError) == 0) )
  {
    ProcAddress = GetProcAddress(LibraryW, "FwpmIPsecTunnelAdd3");
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError )
      {
        v26 = 720;
        goto LABEL_35;
      }
    }
    LastError = ((__int64 (__fastcall *)(HANDLE, _QWORD, struct FWPM_PROVIDER_CONTEXT3_ *, struct FWPM_PROVIDER_CONTEXT3_ *, unsigned int, int *, unsigned __int64, _QWORD))ProcAddress)(
                  gvBfeEngineHandle,
                  a2,
                  v30,
                  a4,
                  v19,
                  &v32,
                  (unsigned __int64)&FWPM_KEYING_MODULE_IKEV2
                & -(__int64)((*(_DWORD *)(*((_QWORD *)v30 + 9) + 32LL) & 0x200) != 0),
                  0);
    v15 = LastError;
    if ( LastError )
    {
      v26 = 739;
      goto LABEL_35;
    }
    *((_DWORD *)a1 + 43) = *((_DWORD *)a1 + 38);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v29);
LABEL_42:
    *a7 = *(struct _GUID *)a4;
    return IpsReturnError("BfeCallTunnelFilterAdd", 0x2FAu, v15, 0, 0);
  }
  v26 = 713;
LABEL_35:
  IpsTraceError("BfeCallTunnelFilterAdd", v26, LastError, 0);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v29);
LABEL_47:
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_169c6de1de293722f3983229da9d1164_Traceguids, v15);
  return IpsReturnError("BfeCallTunnelFilterAdd", 0x2FAu, v15, 0, 0);
}

```

## disassembly

```asm
0x1800d9ec8  push    rbp
0x1800d9eca  push    rbx
0x1800d9ecb  push    rsi
0x1800d9ecc  push    rdi
0x1800d9ecd  push    r12
0x1800d9ecf  push    r13
0x1800d9ed1  push    r14
0x1800d9ed3  push    r15
0x1800d9ed5  lea     rbp, [rsp-28h]
0x1800d9eda  sub     rsp, 128h
0x1800d9ee1  mov     rax, cs:__security_cookie
0x1800d9ee8  xor     rax, rsp
0x1800d9eeb  mov     [rbp+60h+var_50], rax
0x1800d9eef  mov     rsi, r9
0x1800d9ef2  mov     [rsp+160h+var_108], r8
0x1800d9ef7  mov     r13d, edx
0x1800d9efa  mov     r15, rcx
0x1800d9efd  mov     r12, [rbp+60h+arg_30]
0x1800d9f04  mov     dword ptr [rsp+160h+var_F0], 0
0x1800d9f0c  xor     edx, edx; Val
0x1800d9f0e  mov     r8d, 9Ch; Size
0x1800d9f14  lea     rcx, [rsp+160h+var_F0+4]; void *
0x1800d9f19  call    memset_0
0x1800d9f1e  mov     [rsp+160h+var_100], 0
0x1800d9f27  xor     ebx, ebx
0x1800d9f29  mov     eax, [r15+0ACh]
0x1800d9f30  cmp     [r15+98h], eax
0x1800d9f37  setnz   bl
0x1800d9f3a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226> `wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226>::GetImpl(void)'::`2'::impl
0x1800d9f41  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226>::__private_IsEnabled(void)
0x1800d9f46  test    al, al
0x1800d9f48  jz      short loc_1800D9F66
0x1800d9f4a  mov     rax, [rsi+48h]
0x1800d9f4e  test    rax, rax
0x1800d9f51  jz      short loc_1800D9F62
0x1800d9f53  test    dword ptr [rax], 20000h
0x1800d9f59  jz      short loc_1800D9F62
0x1800d9f5b  mov     eax, 1
0x1800d9f60  jmp     short loc_1800D9F64
0x1800d9f62  xor     eax, eax
0x1800d9f64  or      ebx, eax
0x1800d9f66  cmp     ebx, 1
0x1800d9f69  jnz     short loc_1800D9F98
0x1800d9f6b  mov     rcx, rsi; Uuid
0x1800d9f6e  call    cs:__imp_UuidCreate
0x1800d9f75  nop     dword ptr [rax+rax+00h]
0x1800d9f7a  mov     edi, eax
0x1800d9f7c  test    eax, eax
0x1800d9f7e  jz      short loc_1800D9FA1
0x1800d9f80  cmp     eax, 720h
0x1800d9f85  jz      short loc_1800D9FA1
0x1800d9f87  cmp     eax, 6CBh
0x1800d9f8c  jz      short loc_1800D9FA1
0x1800d9f8e  mov     edx, 274h
0x1800d9f93  jmp     loc_1800DA28A
0x1800d9f98  movups  xmm0, xmmword ptr [r12]
0x1800d9f9d  movdqu  xmmword ptr [rsi], xmm0
0x1800d9fa1  mov     rax, qword ptr cs:GUID_NULL.Data1
0x1800d9fa8  cmp     rax, [rsi]
0x1800d9fab  jnz     short loc_1800D9FBF
0x1800d9fad  mov     rax, qword ptr cs:GUID_NULL.Data4
0x1800d9fb4  cmp     rax, [rsi+8]
0x1800d9fb8  jnz     short loc_1800D9FBF
0x1800d9fba  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!IsEqualGUID(GUID_NULL, pTunnelContext->providerContextKey)")
0x1800d9fbf  cmp     ebx, 1
0x1800d9fc2  jnz     short loc_1800D9FFA
0x1800d9fc4  mov     rax, [r15]
0x1800d9fc7  mov     rcx, [rax+18h]
0x1800d9fcb  mov     [rsi+10h], rcx
0x1800d9fcf  test    rcx, rcx
0x1800d9fd2  jnz     short loc_1800D9FDF
0x1800d9fd4  lea     rax, asc_1801110D8; " "
0x1800d9fdb  mov     [rsi+10h], rax
0x1800d9fdf  mov     rax, [r15]
0x1800d9fe2  mov     rcx, [rax+20h]
0x1800d9fe6  test    rcx, rcx
0x1800d9fe9  jz      short loc_1800D9FEF
0x1800d9feb  mov     [rsi+18h], rcx
0x1800d9fef  lea     rax, ?MipsProviderGuid@@3U_GUID@@A; _GUID MipsProviderGuid
0x1800d9ff6  mov     [rsi+28h], rax
0x1800d9ffa  xor     r14d, r14d
0x1800d9ffd  mov     rcx, [rbp+60h+arg_20]
0x1800da004  test    rcx, rcx
0x1800da007  jz      short loc_1800DA03B
0x1800da009  mov     dword ptr [rsp+160h+var_F0], 0D9EE00DEh
0x1800da011  movsd   xmm0, qword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data2
0x1800da019  movsd   qword ptr [rsp+160h+var_F0+4], xmm0
0x1800da01f  mov     eax, dword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data4+4
0x1800da025  mov     dword ptr [rsp+160h+var_F0+0Ch], eax
0x1800da029  mov     [rbp+60h+var_E0], r14d
0x1800da02d  movups  xmm0, xmmword ptr [rcx]
0x1800da030  movdqu  [rbp+60h+var_D8], xmm0
0x1800da035  mov     r14d, 1
0x1800da03b  mov     rdx, [rbp+60h+arg_28]
0x1800da042  test    rdx, rdx
0x1800da045  jz      short loc_1800DA06F
0x1800da047  mov     eax, r14d
0x1800da04a  lea     rcx, [rax+rax*4]
0x1800da04e  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_ADDRESS.Data1
0x1800da055  movdqu  [rsp+rcx*8+160h+var_F0], xmm0
0x1800da05b  mov     [rbp+rcx*8+60h+var_E0], 0
0x1800da063  movups  xmm0, xmmword ptr [rdx]
0x1800da066  movdqu  [rbp+rcx*8+60h+var_D8], xmm0
0x1800da06c  inc     r14d
0x1800da06f  mov     rax, [r15+90h]
0x1800da076  test    rax, rax
0x1800da079  jz      short loc_1800DA0B1
0x1800da07b  mov     [rsp+160h+var_100], rax
0x1800da080  mov     eax, r14d
0x1800da083  lea     rcx, [rax+rax*4]
0x1800da087  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_INTERFACE.Data1
0x1800da08e  movdqu  [rsp+rcx*8+160h+var_F0], xmm0
0x1800da094  mov     [rbp+rcx*8+60h+var_E0], 0
0x1800da09c  mov     dword ptr [rbp+rcx*8+60h+var_D8], 4
0x1800da0a4  lea     rax, [rsp+160h+var_100]
0x1800da0a9  mov     qword ptr [rbp+rcx*8+60h+var_D8+8], rax
0x1800da0ae  inc     r14d
0x1800da0b1  mov     edx, [r15+98h]
0x1800da0b8  cmp     edx, 3
0x1800da0bb  ja      short loc_1800DA0FC
0x1800da0bd  test    ebx, ebx
0x1800da0bf  jz      loc_1800DA259
0x1800da0c5  mov     eax, r14d
0x1800da0c8  lea     rcx, [rax+rax*4]
0x1800da0cc  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_CURRENT_PROFILE_ID.Data1
0x1800da0d3  movdqu  [rsp+rcx*8+160h+var_F0], xmm0
0x1800da0d9  mov     [rbp+rcx*8+60h+var_E0], 0
0x1800da0e1  mov     dword ptr [rbp+rcx*8+60h+var_D8], 3
0x1800da0e9  mov     eax, edx
0x1800da0eb  lea     rdx, qword_1800FC150
0x1800da0f2  mov     eax, [rdx+rax*4]
0x1800da0f5  mov     dword ptr [rbp+rcx*8+60h+var_D8+8], eax
0x1800da0f9  inc     r14d
0x1800da0fc  cmp     ebx, 1
0x1800da0ff  jnz     loc_1800DA259
0x1800da105  lea     rcx, aFwpuclntDll_0; "fwpuclnt.dll"
0x1800da10c  call    cs:__imp_LoadLibraryW
0x1800da113  nop     dword ptr [rax+rax+00h]
0x1800da118  mov     rbx, rax
0x1800da11b  mov     [rsp+160h+var_110], rax
0x1800da120  test    rax, rax
0x1800da123  jnz     short loc_1800DA15E
0x1800da125  call    cs:__imp_GetLastError
0x1800da12c  nop     dword ptr [rax+rax+00h]
0x1800da131  mov     edi, eax
0x1800da133  test    eax, eax
0x1800da135  jz      short loc_1800DA15E
0x1800da137  mov     edx, 2C9h; unsigned int
0x1800da13c  xor     r9d, r9d; int
0x1800da13f  mov     r8d, eax; unsigned int
0x1800da142  lea     rcx, aBfecalltunnelf; "BfeCallTunnelFilterAdd"
0x1800da149  call    ?IpsTraceError@@YAXPEBDKKH@Z; IpsTraceError(char const *,ulong,ulong,int)
0x1800da14e  nop
0x1800da14f  lea     rcx, [rsp+160h+var_110]
0x1800da154  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800da159  jmp     loc_1800DA29C
0x1800da15e  lea     rdx, aFwpmipsectunne_2; "FwpmIPsecTunnelAdd3"
0x1800da165  mov     rcx, rbx; hModule
0x1800da168  call    cs:__imp_GetProcAddress
0x1800da16f  nop     dword ptr [rax+rax+00h]
0x1800da174  mov     rbx, rax
0x1800da177  test    rax, rax
0x1800da17a  jnz     short loc_1800DA195
0x1800da17c  call    cs:__imp_GetLastError
0x1800da183  nop     dword ptr [rax+rax+00h]
0x1800da188  mov     edi, eax
0x1800da18a  test    eax, eax
0x1800da18c  jz      short loc_1800DA195
0x1800da18e  mov     edx, 2D0h
0x1800da193  jmp     short loc_1800DA13C
0x1800da195  mov     r8, [rsp+160h+var_108]
0x1800da19a  mov     rax, [r8+48h]
0x1800da19e  mov     ecx, [rax+20h]
0x1800da1a1  and     ecx, 200h
0x1800da1a7  lea     rdx, FWPM_KEYING_MODULE_IKEV2
0x1800da1ae  neg     ecx
0x1800da1b0  sbb     rax, rax
0x1800da1b3  and     rax, rdx
0x1800da1b6  mov     [rsp+160h+var_128], 0
0x1800da1bf  mov     [rsp+160h+var_130], rax
0x1800da1c4  lea     rax, [rsp+160h+var_F0]
0x1800da1c9  mov     [rsp+160h+var_138], rax
0x1800da1ce  mov     [rsp+160h+var_140], r14d
0x1800da1d3  mov     r9, rsi
0x1800da1d6  mov     edx, r13d
0x1800da1d9  mov     rcx, cs:?gvBfeEngineHandle@@3PEAXEA; void * gvBfeEngineHandle
0x1800da1e0  mov     rax, rbx
0x1800da1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da1e8  mov     edi, eax
0x1800da1ea  test    eax, eax
0x1800da1ec  jz      short loc_1800DA1F8
0x1800da1ee  mov     edx, 2E3h
0x1800da1f3  jmp     loc_1800DA13C
0x1800da1f8  mov     eax, [r15+98h]
0x1800da1ff  mov     [r15+0ACh], eax
0x1800da206  lea     rcx, [rsp+160h+var_110]
0x1800da20b  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800da210  movups  xmm0, xmmword ptr [rsi]
0x1800da213  movdqu  xmmword ptr [r12], xmm0
0x1800da219  mov     [rsp+160h+var_140], 0; int
0x1800da221  xor     r9d, r9d; int
0x1800da224  mov     r8d, edi; unsigned int
0x1800da227  mov     edx, 2FAh; unsigned int
0x1800da22c  lea     rcx, aBfecalltunnelf; "BfeCallTunnelFilterAdd"
0x1800da233  call    ?IpsReturnError@@YAKPEBDKKHH@Z; IpsReturnError(char const *,ulong,ulong,int,int)
0x1800da238  mov     rcx, [rbp+60h+var_50]
0x1800da23c  xor     rcx, rsp; StackCookie
0x1800da23f  call    __security_check_cookie
0x1800da244  add     rsp, 128h
0x1800da24b  pop     r15
0x1800da24d  pop     r14
0x1800da24f  pop     r13
0x1800da251  pop     r12
0x1800da253  pop     rdi
0x1800da254  pop     rsi
0x1800da255  pop     rbx
0x1800da256  pop     rbp
0x1800da257  retn
0x1800da259  lea     rax, [rsp+160h+var_F0]
0x1800da25e  mov     qword ptr [rsp+160h+var_140], rax
0x1800da263  mov     r9d, r14d
0x1800da266  mov     r8, rsi
0x1800da269  mov     edx, r13d
0x1800da26c  mov     rcx, cs:?gvBfeEngineHandle@@3PEAXEA; void * gvBfeEngineHandle
0x1800da273  call    cs:__imp_FwpmIPsecTunnelAddConditions0
0x1800da27a  nop     dword ptr [rax+rax+00h]
0x1800da27f  mov     edi, eax
0x1800da281  test    eax, eax
0x1800da283  jz      short loc_1800DA210
0x1800da285  mov     edx, 2EFh; unsigned int
0x1800da28a  xor     r9d, r9d; int
0x1800da28d  mov     r8d, eax; unsigned int
0x1800da290  lea     rcx, aBfecalltunnelf; "BfeCallTunnelFilterAdd"
0x1800da297  call    ?IpsTraceError@@YAXPEBDKKH@Z; IpsTraceError(char const *,ulong,ulong,int)
0x1800da29c  lea     rax, WPP_GLOBAL_Control
0x1800da2a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da2aa  cmp     rcx, rax
0x1800da2ad  jz      loc_1800DA219
0x1800da2b3  test    byte ptr [rcx+1Ch], 1
0x1800da2b7  jz      loc_1800DA219
0x1800da2bd  mov     edx, 0Ch
0x1800da2c2  mov     r9d, edi
0x1800da2c5  lea     r8, WPP_169c6de1de293722f3983229da9d1164_Traceguids
0x1800da2cc  mov     rcx, [rcx+10h]
0x1800da2d0  call    WPP_SF_d
0x1800da2d5  jmp     loc_1800DA219
```
