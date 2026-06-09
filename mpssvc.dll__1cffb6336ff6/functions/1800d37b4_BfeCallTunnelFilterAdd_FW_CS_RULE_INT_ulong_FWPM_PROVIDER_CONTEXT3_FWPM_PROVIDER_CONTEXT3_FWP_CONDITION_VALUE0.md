# BfeCallTunnelFilterAdd(_FW_CS_RULE_INT_ *,ulong,FWPM_PROVIDER_CONTEXT3_ *,FWPM_PROVIDER_CONTEXT3_ *,FWP_CONDITION_VALUE0_ *,FWP_CONDITION_VALUE0_ *,_GUID *)

- ea: `0x1800d37b4`
- end: `0x1800d3ba1`
- name: `?BfeCallTunnelFilterAdd@@YAKPEAU_FW_CS_RULE_INT_@@KPEAUFWPM_PROVIDER_CONTEXT3_@@1PEAUFWP_CONDITION_VALUE0_@@2PEAU_GUID@@@Z`
- size: `1005`
- prototype: `unsigned int __fastcall(struct _FW_CS_RULE_INT_ *, unsigned int, struct FWPM_PROVIDER_CONTEXT3_ *, struct FWPM_PROVIDER_CONTEXT3_ *, struct FWP_CONDITION_VALUE0_ *, struct FWP_CONDITION_VALUE0_ *, struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d522c`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x18004c284`
- `0x18006b2b8`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800d351c`
- `0x1800d37b4`
- `0x1800d4300`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3a50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d3a42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d3a42`
- `RPCRT4!UuidCreate` at `0x1800d385a`
- `RPCRT4!UuidCreate` at `0x1800d385a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800d39f2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800d39f2`
- `fwpuclnt!FwpmIPsecTunnelAddConditions0` at `0x1800d3b40`
- `fwpuclnt!FwpmIPsecTunnelAddConditions0` at `0x1800d3b40`

## string_xrefs

- `0x1800d39eb`: `fwpuclnt.dll`

## pseudocode

```c
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
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  _DWORD *v15; // rax
  BOOL v16; // eax
  RPC_STATUS v17; // eax
  unsigned int v18; // edi
  unsigned int v19; // edx
  __int64 v20; // rcx
  __int64 v21; // rcx
  unsigned int v22; // r14d
  __int64 v23; // rcx
  __int64 v24; // rcx
  unsigned int v25; // edx
  __int64 v26; // rcx
  HMODULE LibraryW; // rbx
  DWORD LastError; // eax
  unsigned int v29; // edx
  FARPROC ProcAddress; // rbx
  HMODULE v32; // [rsp+50h] [rbp-B0h] BYREF
  struct FWPM_PROVIDER_CONTEXT3_ *v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+74h] [rbp-8Ch] BYREF
  int v37; // [rsp+7Ch] [rbp-84h]
  int v38; // [rsp+80h] [rbp-80h]
  _OWORD v39[8]; // [rsp+88h] [rbp-78h]

  v33 = a3;
  v35 = 0;
  memset_0(&v36, 0, 0x9Cu);
  v34 = 0;
  v10 = *((_DWORD *)a1 + 38) != *((_DWORD *)a1 + 43);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226>::GetImpl'::`2'::impl) )
  {
    v15 = (_DWORD *)*((_QWORD *)a4 + 9);
    v16 = v15 && (*v15 & 0x20000) != 0;
    v10 |= v16;
  }
  if ( v10 == 1 )
  {
    v17 = UuidCreate((UUID *)a4);
    v18 = v17;
    if ( v17 && v17 != 1824 && v17 != 1739 )
    {
      v19 = 628;
LABEL_46:
      IpsTraceError("BfeCallTunnelFilterAdd", v19, v17, 0);
      goto LABEL_47;
    }
  }
  else
  {
    *(struct _GUID *)a4 = *a7;
  }
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)a4 && *(_QWORD *)GUID_NULL.Data4 == *((_QWORD *)a4 + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13, v14);
  if ( v10 == 1 )
  {
    v20 = *(_QWORD *)(*(_QWORD *)a1 + 24LL);
    *((_QWORD *)a4 + 2) = v20;
    if ( !v20 )
      *((_QWORD *)a4 + 2) = L" ";
    v21 = *(_QWORD *)(*(_QWORD *)a1 + 32LL);
    if ( v21 )
      *((_QWORD *)a4 + 3) = v21;
    *((_QWORD *)a4 + 5) = &MipsProviderGuid;
  }
  v22 = 0;
  if ( a5 )
  {
    v35 = -638713634;
    v36 = *(_QWORD *)&FWPM_CONDITION_IP_LOCAL_ADDRESS.Data2;
    v37 = *(_DWORD *)&FWPM_CONDITION_IP_LOCAL_ADDRESS.Data4[4];
    v38 = 0;
    v39[0] = *a5;
    v22 = 1;
  }
  if ( a6 )
  {
    v23 = 5LL * v22;
    *(GUID *)(&v35 + 2 * v23) = FWPM_CONDITION_IP_REMOTE_ADDRESS;
    *((int *)v39 + 2 * v23) = 0;
    *(struct FWP_CONDITION_VALUE0_ *)((char *)v39 + 8 * v23) = *a6;
    ++v22;
  }
  if ( *((_QWORD *)a1 + 18) )
  {
    v34 = *((_QWORD *)a1 + 18);
    v24 = 5LL * v22;
    *(GUID *)(&v35 + 2 * v24) = FWPM_CONDITION_IP_LOCAL_INTERFACE;
    *((int *)v39 + 2 * v24) = 0;
    *((_DWORD *)v39 + 2 * v24) = 4;
    *((_QWORD *)v39 + v24 + 1) = &v34;
    ++v22;
  }
  v25 = *((_DWORD *)a1 + 38);
  if ( v25 <= 3 )
  {
    if ( !v10 )
      goto LABEL_44;
    v26 = 5LL * v22;
    *(GUID *)(&v35 + 2 * v26) = FWPM_CONDITION_CURRENT_PROFILE_ID;
    *((int *)v39 + 2 * v26) = 0;
    *((_DWORD *)v39 + 2 * v26) = 3;
    *((_DWORD *)v39 + 2 * v26 + 2) = *((_DWORD *)qword_1800F60F0 + v25);
    ++v22;
  }
  if ( v10 != 1 )
  {
LABEL_44:
    v17 = FwpmIPsecTunnelAddConditions0(gvBfeEngineHandle, a2, a4, v22, &v35);
    v18 = v17;
    if ( v17 )
    {
      v19 = 751;
      goto LABEL_46;
    }
    goto LABEL_42;
  }
  LibraryW = LoadLibraryW(L"fwpuclnt.dll");
  v32 = LibraryW;
  if ( LibraryW || (LastError = GetLastError(), (v18 = LastError) == 0) )
  {
    ProcAddress = GetProcAddress(LibraryW, "FwpmIPsecTunnelAdd3");
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v18 = LastError;
      if ( LastError )
      {
        v29 = 720;
        goto LABEL_35;
      }
    }
    LastError = ((__int64 (__fastcall *)(HANDLE, _QWORD, struct FWPM_PROVIDER_CONTEXT3_ *, struct FWPM_PROVIDER_CONTEXT3_ *, unsigned int, int *, unsigned __int64, _QWORD))ProcAddress)(
                  gvBfeEngineHandle,
                  a2,
                  v33,
                  a4,
                  v22,
                  &v35,
                  (unsigned __int64)&FWPM_KEYING_MODULE_IKEV2
                & -(__int64)((*(_DWORD *)(*((_QWORD *)v33 + 9) + 32LL) & 0x200) != 0),
                  0);
    v18 = LastError;
    if ( LastError )
    {
      v29 = 739;
      goto LABEL_35;
    }
    *((_DWORD *)a1 + 43) = *((_DWORD *)a1 + 38);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v32);
LABEL_42:
    *a7 = *(struct _GUID *)a4;
    return IpsReturnError("BfeCallTunnelFilterAdd", 0x2FAu, v18, 0, 0);
  }
  v29 = 713;
LABEL_35:
  IpsTraceError("BfeCallTunnelFilterAdd", v29, LastError, 0);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v32);
LABEL_47:
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_169c6de1de293722f3983229da9d1164_Traceguids, v18);
  return IpsReturnError("BfeCallTunnelFilterAdd", 0x2FAu, v18, 0, 0);
}

```

## disassembly

```asm
0x1800d37b4  push    rbp
0x1800d37b6  push    rbx
0x1800d37b7  push    rsi
0x1800d37b8  push    rdi
0x1800d37b9  push    r12
0x1800d37bb  push    r13
0x1800d37bd  push    r14
0x1800d37bf  push    r15
0x1800d37c1  lea     rbp, [rsp-28h]
0x1800d37c6  sub     rsp, 128h
0x1800d37cd  mov     rax, cs:__security_cookie
0x1800d37d4  xor     rax, rsp
0x1800d37d7  mov     [rbp+60h+var_50], rax
0x1800d37db  mov     rsi, r9
0x1800d37de  mov     [rsp+160h+var_108], r8
0x1800d37e3  mov     r13d, edx
0x1800d37e6  mov     r15, rcx
0x1800d37e9  mov     r12, [rbp+60h+arg_30]
0x1800d37f0  mov     dword ptr [rsp+160h+var_F0], 0
0x1800d37f8  xor     edx, edx; Val
0x1800d37fa  mov     r8d, 9Ch; Size
0x1800d3800  lea     rcx, [rsp+160h+var_F0+4]; void *
0x1800d3805  call    memset_0
0x1800d380a  mov     [rsp+160h+var_100], 0
0x1800d3813  xor     ebx, ebx
0x1800d3815  mov     eax, [r15+0ACh]
0x1800d381c  cmp     [r15+98h], eax
0x1800d3823  setnz   bl
0x1800d3826  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226> `wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226>::GetImpl(void)'::`2'::impl
0x1800d382d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_60329226>::__private_IsEnabled(void)
0x1800d3832  test    al, al
0x1800d3834  jz      short loc_1800D3852
0x1800d3836  mov     rax, [rsi+48h]
0x1800d383a  test    rax, rax
0x1800d383d  jz      short loc_1800D384E
0x1800d383f  test    dword ptr [rax], 20000h
0x1800d3845  jz      short loc_1800D384E
0x1800d3847  mov     eax, 1
0x1800d384c  jmp     short loc_1800D3850
0x1800d384e  xor     eax, eax
0x1800d3850  or      ebx, eax
0x1800d3852  cmp     ebx, 1
0x1800d3855  jnz     short loc_1800D387E
0x1800d3857  mov     rcx, rsi; Uuid
0x1800d385a  call    cs:__imp_UuidCreate
0x1800d3860  mov     edi, eax
0x1800d3862  test    eax, eax
0x1800d3864  jz      short loc_1800D3887
0x1800d3866  cmp     eax, 720h
0x1800d386b  jz      short loc_1800D3887
0x1800d386d  cmp     eax, 6CBh
0x1800d3872  jz      short loc_1800D3887
0x1800d3874  mov     edx, 274h
0x1800d3879  jmp     loc_1800D3B51
0x1800d387e  movups  xmm0, xmmword ptr [r12]
0x1800d3883  movdqu  xmmword ptr [rsi], xmm0
0x1800d3887  mov     rax, qword ptr cs:GUID_NULL.Data1
0x1800d388e  cmp     rax, [rsi]
0x1800d3891  jnz     short loc_1800D38A5
0x1800d3893  mov     rax, qword ptr cs:GUID_NULL.Data4
0x1800d389a  cmp     rax, [rsi+8]
0x1800d389e  jnz     short loc_1800D38A5
0x1800d38a0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800d38a5  cmp     ebx, 1
0x1800d38a8  jnz     short loc_1800D38E0
0x1800d38aa  mov     rax, [r15]
0x1800d38ad  mov     rcx, [rax+18h]
0x1800d38b1  mov     [rsi+10h], rcx
0x1800d38b5  test    rcx, rcx
0x1800d38b8  jnz     short loc_1800D38C5
0x1800d38ba  lea     rax, asc_18010B39C; " "
0x1800d38c1  mov     [rsi+10h], rax
0x1800d38c5  mov     rax, [r15]
0x1800d38c8  mov     rcx, [rax+20h]
0x1800d38cc  test    rcx, rcx
0x1800d38cf  jz      short loc_1800D38D5
0x1800d38d1  mov     [rsi+18h], rcx
0x1800d38d5  lea     rax, ?MipsProviderGuid@@3U_GUID@@A; _GUID MipsProviderGuid
0x1800d38dc  mov     [rsi+28h], rax
0x1800d38e0  xor     r14d, r14d
0x1800d38e3  mov     rcx, [rbp+60h+arg_20]
0x1800d38ea  test    rcx, rcx
0x1800d38ed  jz      short loc_1800D3921
0x1800d38ef  mov     dword ptr [rsp+160h+var_F0], 0D9EE00DEh
0x1800d38f7  movsd   xmm0, qword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data2
0x1800d38ff  movsd   qword ptr [rsp+160h+var_F0+4], xmm0
0x1800d3905  mov     eax, dword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data4+4
0x1800d390b  mov     dword ptr [rsp+160h+var_F0+0Ch], eax
0x1800d390f  mov     [rbp+60h+var_E0], r14d
0x1800d3913  movups  xmm0, xmmword ptr [rcx]
0x1800d3916  movdqu  [rbp+60h+var_D8], xmm0
0x1800d391b  mov     r14d, 1
0x1800d3921  mov     rdx, [rbp+60h+arg_28]
0x1800d3928  test    rdx, rdx
0x1800d392b  jz      short loc_1800D3955
0x1800d392d  mov     eax, r14d
0x1800d3930  lea     rcx, [rax+rax*4]
0x1800d3934  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_ADDRESS.Data1
0x1800d393b  movdqu  [rsp+rcx*8+160h+var_F0], xmm0
0x1800d3941  mov     [rbp+rcx*8+60h+var_E0], 0
0x1800d3949  movups  xmm0, xmmword ptr [rdx]
0x1800d394c  movdqu  [rbp+rcx*8+60h+var_D8], xmm0
0x1800d3952  inc     r14d
0x1800d3955  mov     rax, [r15+90h]
0x1800d395c  test    rax, rax
0x1800d395f  jz      short loc_1800D3997
0x1800d3961  mov     [rsp+160h+var_100], rax
0x1800d3966  mov     eax, r14d
0x1800d3969  lea     rcx, [rax+rax*4]
0x1800d396d  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_INTERFACE.Data1
0x1800d3974  movdqu  [rsp+rcx*8+160h+var_F0], xmm0
0x1800d397a  mov     [rbp+rcx*8+60h+var_E0], 0
0x1800d3982  mov     dword ptr [rbp+rcx*8+60h+var_D8], 4
0x1800d398a  lea     rax, [rsp+160h+var_100]
0x1800d398f  mov     qword ptr [rbp+rcx*8+60h+var_D8+8], rax
0x1800d3994  inc     r14d
0x1800d3997  mov     edx, [r15+98h]
0x1800d399e  cmp     edx, 3
0x1800d39a1  ja      short loc_1800D39E2
0x1800d39a3  test    ebx, ebx
0x1800d39a5  jz      loc_1800D3B26
0x1800d39ab  mov     eax, r14d
0x1800d39ae  lea     rcx, [rax+rax*4]
0x1800d39b2  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_CURRENT_PROFILE_ID.Data1
0x1800d39b9  movdqu  [rsp+rcx*8+160h+var_F0], xmm0
0x1800d39bf  mov     [rbp+rcx*8+60h+var_E0], 0
0x1800d39c7  mov     dword ptr [rbp+rcx*8+60h+var_D8], 3
0x1800d39cf  mov     eax, edx
0x1800d39d1  lea     rdx, qword_1800F60F0
0x1800d39d8  mov     eax, [rdx+rax*4]
0x1800d39db  mov     dword ptr [rbp+rcx*8+60h+var_D8+8], eax
0x1800d39df  inc     r14d
0x1800d39e2  cmp     ebx, 1
0x1800d39e5  jnz     loc_1800D3B26
0x1800d39eb  lea     rcx, aFwpuclntDll_0; "fwpuclnt.dll"
0x1800d39f2  call    cs:__imp_LoadLibraryW
0x1800d39f8  mov     rbx, rax
0x1800d39fb  mov     [rsp+160h+var_110], rax
0x1800d3a00  test    rax, rax
0x1800d3a03  jnz     short loc_1800D3A38
0x1800d3a05  call    cs:__imp_GetLastError
0x1800d3a0b  mov     edi, eax
0x1800d3a0d  test    eax, eax
0x1800d3a0f  jz      short loc_1800D3A38
0x1800d3a11  mov     edx, 2C9h; unsigned int
0x1800d3a16  xor     r9d, r9d; int
0x1800d3a19  mov     r8d, eax; unsigned int
0x1800d3a1c  lea     rcx, aBfecalltunnelf; "BfeCallTunnelFilterAdd"
0x1800d3a23  call    ?IpsTraceError@@YAXPEBDKKH@Z; IpsTraceError(char const *,ulong,ulong,int)
0x1800d3a28  nop
0x1800d3a29  lea     rcx, [rsp+160h+var_110]
0x1800d3a2e  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800d3a33  jmp     loc_1800D3B63
0x1800d3a38  lea     rdx, aFwpmipsectunne_2; "FwpmIPsecTunnelAdd3"
0x1800d3a3f  mov     rcx, rbx; hModule
0x1800d3a42  call    cs:__imp_GetProcAddress
0x1800d3a48  mov     rbx, rax
0x1800d3a4b  test    rax, rax
0x1800d3a4e  jnz     short loc_1800D3A63
0x1800d3a50  call    cs:__imp_GetLastError
0x1800d3a56  mov     edi, eax
0x1800d3a58  test    eax, eax
0x1800d3a5a  jz      short loc_1800D3A63
0x1800d3a5c  mov     edx, 2D0h
0x1800d3a61  jmp     short loc_1800D3A16
0x1800d3a63  mov     r8, [rsp+160h+var_108]
0x1800d3a68  mov     rax, [r8+48h]
0x1800d3a6c  mov     ecx, [rax+20h]
0x1800d3a6f  and     ecx, 200h
0x1800d3a75  lea     rdx, FWPM_KEYING_MODULE_IKEV2
0x1800d3a7c  neg     ecx
0x1800d3a7e  sbb     rax, rax
0x1800d3a81  and     rax, rdx
0x1800d3a84  mov     [rsp+160h+var_128], 0
0x1800d3a8d  mov     [rsp+160h+var_130], rax
0x1800d3a92  lea     rax, [rsp+160h+var_F0]
0x1800d3a97  mov     [rsp+160h+var_138], rax
0x1800d3a9c  mov     [rsp+160h+var_140], r14d
0x1800d3aa1  mov     r9, rsi
0x1800d3aa4  mov     edx, r13d
0x1800d3aa7  mov     rcx, cs:?gvBfeEngineHandle@@3PEAXEA; void * gvBfeEngineHandle
0x1800d3aae  mov     rax, rbx
0x1800d3ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3ab6  mov     edi, eax
0x1800d3ab8  test    eax, eax
0x1800d3aba  jz      short loc_1800D3AC6
0x1800d3abc  mov     edx, 2E3h
0x1800d3ac1  jmp     loc_1800D3A16
0x1800d3ac6  mov     eax, [r15+98h]
0x1800d3acd  mov     [r15+0ACh], eax
0x1800d3ad4  lea     rcx, [rsp+160h+var_110]
0x1800d3ad9  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800d3ade  movups  xmm0, xmmword ptr [rsi]
0x1800d3ae1  movdqu  xmmword ptr [r12], xmm0
0x1800d3ae7  mov     [rsp+160h+var_140], 0; int
0x1800d3aef  xor     r9d, r9d; int
0x1800d3af2  mov     r8d, edi; unsigned int
0x1800d3af5  mov     edx, 2FAh; unsigned int
0x1800d3afa  lea     rcx, aBfecalltunnelf; "BfeCallTunnelFilterAdd"
0x1800d3b01  call    ?IpsReturnError@@YAKPEBDKKHH@Z; IpsReturnError(char const *,ulong,ulong,int,int)
0x1800d3b06  mov     rcx, [rbp+60h+var_50]
0x1800d3b0a  xor     rcx, rsp; StackCookie
0x1800d3b0d  call    __security_check_cookie
0x1800d3b12  add     rsp, 128h
0x1800d3b19  pop     r15
0x1800d3b1b  pop     r14
0x1800d3b1d  pop     r13
0x1800d3b1f  pop     r12
0x1800d3b21  pop     rdi
0x1800d3b22  pop     rsi
0x1800d3b23  pop     rbx
0x1800d3b24  pop     rbp
0x1800d3b25  retn
0x1800d3b26  lea     rax, [rsp+160h+var_F0]
0x1800d3b2b  mov     qword ptr [rsp+160h+var_140], rax
0x1800d3b30  mov     r9d, r14d
0x1800d3b33  mov     r8, rsi
0x1800d3b36  mov     edx, r13d
0x1800d3b39  mov     rcx, cs:?gvBfeEngineHandle@@3PEAXEA; void * gvBfeEngineHandle
0x1800d3b40  call    cs:__imp_FwpmIPsecTunnelAddConditions0
0x1800d3b46  mov     edi, eax
0x1800d3b48  test    eax, eax
0x1800d3b4a  jz      short loc_1800D3ADE
0x1800d3b4c  mov     edx, 2EFh; unsigned int
0x1800d3b51  xor     r9d, r9d; int
0x1800d3b54  mov     r8d, eax; unsigned int
0x1800d3b57  lea     rcx, aBfecalltunnelf; "BfeCallTunnelFilterAdd"
0x1800d3b5e  call    ?IpsTraceError@@YAXPEBDKKH@Z; IpsTraceError(char const *,ulong,ulong,int)
0x1800d3b63  lea     rax, WPP_GLOBAL_Control
0x1800d3b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3b71  cmp     rcx, rax
0x1800d3b74  jz      loc_1800D3AE7
0x1800d3b7a  test    byte ptr [rcx+1Ch], 1
0x1800d3b7e  jz      loc_1800D3AE7
0x1800d3b84  mov     edx, 0Ch
0x1800d3b89  mov     r9d, edi
0x1800d3b8c  lea     r8, WPP_169c6de1de293722f3983229da9d1164_Traceguids
0x1800d3b93  mov     rcx, [rcx+10h]
0x1800d3b97  call    WPP_SF_d
0x1800d3b9c  jmp     loc_1800D3AE7
```
