# CflGetTransitionScenarioData

- ea: `0x180010db0`
- end: `0x18001101e`
- name: `CflGetTransitionScenarioData`
- size: `622`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x1800067c4`
- `0x1800084d4`
- `0x180008868`
- `0x180009adc`
- `0x18000a11c`
- `0x18000c44c`
- `0x18000cddc`
- `0x18000d8d8`
- `0x180010db0`
- `0x1800298d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010e0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010e0e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180010e26`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180010e26`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180010e2c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180010e2c`

## string_xrefs

- `0x180010fc0`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`
- `0x180010fa6`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CflGetTransitionScenarioData(_QWORD *a1, _QWORD *a2, DWORD *a3, _QWORD *a4, _QWORD *a5, DWORD *a6)
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  __int64 v12; // rcx
  unsigned int v13; // r8d
  unsigned int AllScenarioData; // ebx
  __int64 v15; // rdx
  unsigned int v16; // r8d
  const char *v17; // r9
  __int64 result; // rax
  int *v19; // [rsp+20h] [rbp-3E8h]
  int v20; // [rsp+20h] [rbp-3E8h]
  DWORD dwSize; // [rsp+40h] [rbp-3C8h] BYREF
  int v22; // [rsp+44h] [rbp-3C4h] BYREF
  __int16 v23; // [rsp+48h] [rbp-3C0h]
  __int64 v24; // [rsp+50h] [rbp-3B8h] BYREF
  _QWORD v25[42]; // [rsp+60h] [rbp-3A8h] BYREF
  WCHAR ExeName[264]; // [rsp+1B0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+0h]

  memset_0(ExeName, 0, 0x20Au);
  dwSize = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize);
  CommandLineW = GetCommandLineW();
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v25,
    "CflGetTransitionScenarioDataActivity");
  try
  {
    v25[0] = &CflApiTraceProvider::CflGetTransitionScenarioDataActivity::`vftable';
    CflApiTraceProvider::CflGetTransitionScenarioDataActivity::StartActivity(
      (CflApiTraceProvider::CflGetTransitionScenarioDataActivity *)v25,
      ExeName,
      CommandLineW);
    v13 = *(_DWORD *)Feature_AADPinResetV2__descriptor;
    if ( (*(_DWORD *)Feature_AADPinResetV2__descriptor & 4) == 0 )
    {
      v24 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::GetCachedFeatureEnabledState(
                         v12,
                         &v24);
      v13 = v24;
    }
    v22 = 0;
    v23 = 3;
    v19 = &v22;
    wil::details::ReportUsageToService(&qword_18003F868, 39729128, (v13 >> 10) & 1, (v13 >> 11) & 1);
    if ( a1 && a2 && a3 )
    {
      if ( *a1 || a1[1] != _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] )
      {
        if ( a5 )
        {
          if ( a6 )
            goto LABEL_13;
        }
        else if ( !a6 )
        {
LABEL_13:
          AllScenarioData = CflApiNew::GetAllScenarioData(2, a1, a2, a3, a4, a5, a6, 0);
          if ( (AllScenarioData & 0x80000000) == 0 )
          {
            wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v25);
            v25[0] = &CflApiTraceProvider::CflGetTransitionScenarioDataActivity::`vftable';
            wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v25);
            wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v25);
            return 0;
          }
          v15 = 216;
          goto LABEL_18;
        }
      }
      AllScenarioData = -2147024809;
      v15 = 205;
    }
    else
    {
      AllScenarioData = -2147467261;
      v15 = 199;
    }
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)AllScenarioData,
      (int)v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
      (const char *)AllScenarioData,
      v20);
    v25[0] = &CflApiTraceProvider::CflGetTransitionScenarioDataActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v25);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v25);
    result = AllScenarioData;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0xE1, v16, v17);
  }
  return result;
}

```

## disassembly

```asm
0x180010db0  push    rbx
0x180010db2  push    rsi
0x180010db3  push    rdi
0x180010db4  push    r12
0x180010db6  push    r13
0x180010db8  push    r14
0x180010dba  push    r15
0x180010dbc  sub     rsp, 3D0h
0x180010dc3  mov     rax, cs:__security_cookie
0x180010dca  xor     rax, rsp
0x180010dcd  mov     [rsp+408h+var_48], rax
0x180010dd5  mov     r13, r9
0x180010dd8  mov     r15, r8
0x180010ddb  mov     r14, rdx
0x180010dde  mov     rdi, rcx
0x180010de1  mov     r12, [rsp+408h+arg_20]
0x180010de9  mov     rsi, [rsp+408h+arg_28]
0x180010df1  xor     edx, edx; Val
0x180010df3  mov     r8d, 20Ah; Size
0x180010df9  lea     rcx, [rsp+408h+ExeName]; void *
0x180010e01  call    memset_0
0x180010e06  mov     [rsp+408h+dwSize], 105h
0x180010e0e  call    cs:__imp_GetCurrentProcess
0x180010e14  mov     rcx, rax; hProcess
0x180010e17  lea     r9, [rsp+408h+dwSize]; lpdwSize
0x180010e1c  lea     r8, [rsp+408h+ExeName]; lpExeName
0x180010e24  xor     edx, edx; dwFlags
0x180010e26  call    cs:__imp_QueryFullProcessImageNameW
0x180010e2c  call    cs:__imp_GetCommandLineW
0x180010e32  mov     rbx, rax
0x180010e35  lea     rdx, aCflgettransiti_0; "CflGetTransitionScenarioDataActivity"
0x180010e3c  lea     rcx, [rsp+408h+var_3A8]
0x180010e41  call    ??0?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180010e46  lea     rax, ??_7CflGetTransitionScenarioDataActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflGetTransitionScenarioDataActivity::`vftable'
0x180010e4d  mov     [rsp+408h+var_3A8], rax
0x180010e52  mov     r8, rbx; unsigned __int16 *
0x180010e55  lea     rdx, [rsp+408h+ExeName]; unsigned __int16 *
0x180010e5d  lea     rcx, [rsp+408h+var_3A8]; this
0x180010e62  call    ?StartActivity@CflGetTransitionScenarioDataActivity@CflApiTraceProvider@@QEAAXPEBG0@Z; CflApiTraceProvider::CflGetTransitionScenarioDataActivity::StartActivity(ushort const *,ushort const *)
0x180010e67  nop
0x180010e68  mov     rax, cs:Feature_AADPinResetV2__descriptor
0x180010e6f  mov     r8d, [rax]
0x180010e72  test    r8b, 4
0x180010e76  jnz     short loc_180010E8D
0x180010e78  lea     rdx, [rsp+408h+var_3B8]
0x180010e7d  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AADPinResetV2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::GetCachedFeatureEnabledState(void)
0x180010e82  mov     rax, [rax]
0x180010e85  mov     [rsp+408h+var_3B8], rax
0x180010e8a  mov     r8d, eax
0x180010e8d  xor     eax, eax
0x180010e8f  mov     [rsp+408h+var_3C4], eax
0x180010e93  mov     [rsp+408h+var_3C0], 3
0x180010e9a  mov     r9d, r8d
0x180010e9d  shr     r9d, 0Bh
0x180010ea1  and     r9d, 1
0x180010ea5  shr     r8d, 0Ah
0x180010ea9  and     r8d, 1
0x180010ead  mov     dword ptr [rsp+408h+var_3D8], 3
0x180010eb5  mov     dword ptr [rsp+408h+var_3E0], 1
0x180010ebd  lea     rax, [rsp+408h+var_3C4]
0x180010ec2  mov     qword ptr [rsp+408h+var_3E8], rax; int
0x180010ec7  mov     edx, 25E37E8h
0x180010ecc  lea     rcx, qword_18003F868
0x180010ed3  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180010ed8  test    rdi, rdi
0x180010edb  jz      loc_180010F94
0x180010ee1  test    r14, r14
0x180010ee4  jz      loc_180010F94
0x180010eea  test    r15, r15
0x180010eed  jz      loc_180010F94
0x180010ef3  xorps   xmm0, xmm0
0x180010ef6  movq    rax, xmm0
0x180010efb  cmp     [rdi], rax
0x180010efe  jnz     short loc_180010F10
0x180010f00  psrldq  xmm0, 8
0x180010f05  movq    rax, xmm0
0x180010f0a  cmp     [rdi+8], rax
0x180010f0e  jz      short loc_180010F88
0x180010f10  test    r12, r12
0x180010f13  jz      short loc_180010F1C
0x180010f15  test    rsi, rsi
0x180010f18  jz      short loc_180010F88
0x180010f1a  jmp     short loc_180010F21
0x180010f1c  test    rsi, rsi
0x180010f1f  jnz     short loc_180010F88
0x180010f21  mov     [rsp+408h+var_3D0], 0
0x180010f2a  mov     [rsp+408h+var_3D8], rsi
0x180010f2f  mov     [rsp+408h+var_3E0], r12
0x180010f34  mov     qword ptr [rsp+408h+var_3E8], r13
0x180010f39  mov     r9, r15
0x180010f3c  mov     r8, r14
0x180010f3f  mov     rdx, rdi
0x180010f42  mov     ecx, 2
0x180010f47  call    CflApiNew__GetAllScenarioData
0x180010f4c  mov     ebx, eax
0x180010f4e  test    eax, eax
0x180010f50  jns     short loc_180010F59
0x180010f52  mov     edx, 0D8h
0x180010f57  jmp     short loc_180010F9E
0x180010f59  lea     rcx, [rsp+408h+var_3A8]
0x180010f5e  call    ?Stop@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180010f63  nop
0x180010f64  lea     rax, ??_7CflGetTransitionScenarioDataActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflGetTransitionScenarioDataActivity::`vftable'
0x180010f6b  mov     [rsp+408h+var_3A8], rax
0x180010f70  lea     rcx, [rsp+408h+var_3A8]
0x180010f75  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010f7a  lea     rcx, [rsp+408h+var_3A8]
0x180010f7f  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010f84  xor     eax, eax
0x180010f86  jmp     short loc_180010FFA
0x180010f88  mov     ebx, 80070057h
0x180010f8d  mov     edx, 0CDh
0x180010f92  jmp     short loc_180010F9E
0x180010f94  mov     ebx, 80004003h
0x180010f99  mov     edx, 0C7h; void *
0x180010f9e  mov     rcx, [rsp+408h]; this
0x180010fa6  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180010fad  mov     r9d, ebx; char *
0x180010fb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010fb5  mov     rcx, [rsp+408h]; this
0x180010fbd  mov     r9d, ebx; char *
0x180010fc0  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x180010fc7  mov     edx, 0D0h; void *
0x180010fcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010fd1  nop
0x180010fd2  lea     rax, ??_7CflGetTransitionScenarioDataActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflGetTransitionScenarioDataActivity::`vftable'
0x180010fd9  mov     [rsp+408h+var_3A8], rax
0x180010fde  lea     rcx, [rsp+408h+var_3A8]
0x180010fe3  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010fe8  lea     rcx, [rsp+408h+var_3A8]
0x180010fed  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010ff2  mov     eax, ebx
0x180010ff4  jmp     short loc_180010FFA
0x180010ff6  mov     eax, [rsp+408h+dwSize]
0x180010ffa  mov     rcx, [rsp+408h+var_48]
0x180011002  xor     rcx, rsp; StackCookie
0x180011005  call    __security_check_cookie
0x18001100a  add     rsp, 3D0h
0x180011011  pop     r15
0x180011013  pop     r14
0x180011015  pop     r13
0x180011017  pop     r12
0x180011019  pop     rdi
0x18001101a  pop     rsi
0x18001101b  pop     rbx
0x18001101c  retn
```
