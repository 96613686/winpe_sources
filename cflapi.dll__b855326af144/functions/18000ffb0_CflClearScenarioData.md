# CflClearScenarioData

- ea: `0x18000ffb0`
- end: `0x1800101ad`
- name: `CflClearScenarioData`
- size: `509`
- prototype: `__int64 __fastcall(_QWORD *)`
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
- `0x18000c85c`
- `0x18000d8d8`
- `0x18000ffb0`
- `0x1800286d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fff4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fff4`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001000c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001000c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180010012`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180010012`

## string_xrefs

- `0x18001012c`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`
- `0x180010112`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CflClearScenarioData(_QWORD *a1)
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  __int64 v4; // rcx
  unsigned int v5; // r8d
  unsigned int v6; // ebx
  __int64 v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-3B8h]
  DWORD dwSize; // [rsp+40h] [rbp-398h] BYREF
  int v13; // [rsp+44h] [rbp-394h] BYREF
  __int16 v14; // [rsp+48h] [rbp-390h]
  __int64 v15; // [rsp+50h] [rbp-388h] BYREF
  _QWORD v16[42]; // [rsp+60h] [rbp-378h] BYREF
  WCHAR ExeName[264]; // [rsp+1B0h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3D8h] [rbp+0h]

  memset_0(ExeName, 0, 0x20Au);
  dwSize = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize);
  CommandLineW = GetCommandLineW();
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v16,
    "CflClearScenarioDataActivity");
  try
  {
    v16[0] = &CflApiTraceProvider::CflClearScenarioDataActivity::`vftable';
    CflApiTraceProvider::CflClearScenarioDataActivity::StartActivity(
      (CflApiTraceProvider::CflClearScenarioDataActivity *)v16,
      ExeName,
      CommandLineW);
    v5 = *(_DWORD *)Feature_AADPinResetV2__descriptor;
    if ( (*(_DWORD *)Feature_AADPinResetV2__descriptor & 4) == 0 )
    {
      v15 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::GetCachedFeatureEnabledState(
                         v4,
                         &v15);
      v5 = v15;
    }
    v13 = 0;
    v14 = 3;
    wil::details::ReportUsageToService(&qword_18003F868, 39729128, (v5 >> 10) & 1, (v5 >> 11) & 1);
    if ( !a1 )
    {
      v6 = -2147467261;
      v7 = 258;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
        (const char *)v6,
        (int)&v13);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
        (const char *)v6,
        v11);
      v16[0] = &CflApiTraceProvider::CflClearScenarioDataActivity::`vftable';
      wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v16);
      wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v16);
      return v6;
    }
    if ( !*a1 && a1[1] == _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] )
    {
      v6 = -2147024809;
      v7 = 260;
      goto LABEL_11;
    }
    v6 = CflApiNew::ClearScenarioDataWithReason((char *)3, a1);
    if ( (v6 & 0x80000000) != 0 )
    {
      v7 = 262;
      goto LABEL_11;
    }
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v16);
    v16[0] = &CflApiTraceProvider::CflClearScenarioDataActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v16);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v16);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x12E, v8, v9);
  }
  return result;
}

```

## disassembly

```asm
0x18000ffb0  mov     [rsp+arg_8], rbx
0x18000ffb5  mov     [rsp+arg_10], rsi
0x18000ffba  push    rdi
0x18000ffbb  sub     rsp, 3D0h
0x18000ffc2  mov     rax, cs:__security_cookie
0x18000ffc9  xor     rax, rsp
0x18000ffcc  mov     [rsp+3D8h+var_18], rax
0x18000ffd4  mov     rdi, rcx
0x18000ffd7  xor     edx, edx; Val
0x18000ffd9  mov     r8d, 20Ah; Size
0x18000ffdf  lea     rcx, [rsp+3D8h+ExeName]; void *
0x18000ffe7  call    memset_0
0x18000ffec  mov     [rsp+3D8h+dwSize], 105h
0x18000fff4  call    cs:__imp_GetCurrentProcess
0x18000fffa  mov     rcx, rax; hProcess
0x18000fffd  lea     r9, [rsp+3D8h+dwSize]; lpdwSize
0x180010002  lea     r8, [rsp+3D8h+ExeName]; lpExeName
0x18001000a  xor     edx, edx; dwFlags
0x18001000c  call    cs:__imp_QueryFullProcessImageNameW
0x180010012  call    cs:__imp_GetCommandLineW
0x180010018  mov     rbx, rax
0x18001001b  lea     rdx, aCflclearscenar_0; "CflClearScenarioDataActivity"
0x180010022  lea     rcx, [rsp+3D8h+var_378]
0x180010027  call    ??0?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001002c  lea     rsi, ??_7CflClearScenarioDataActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflClearScenarioDataActivity::`vftable'
0x180010033  mov     [rsp+3D8h+var_378], rsi
0x180010038  mov     r8, rbx; unsigned __int16 *
0x18001003b  lea     rdx, [rsp+3D8h+ExeName]; unsigned __int16 *
0x180010043  lea     rcx, [rsp+3D8h+var_378]; this
0x180010048  call    ?StartActivity@CflClearScenarioDataActivity@CflApiTraceProvider@@QEAAXPEBG0@Z; CflApiTraceProvider::CflClearScenarioDataActivity::StartActivity(ushort const *,ushort const *)
0x18001004d  nop
0x18001004e  mov     rax, cs:Feature_AADPinResetV2__descriptor
0x180010055  mov     r8d, [rax]
0x180010058  test    r8b, 4
0x18001005c  jnz     short loc_180010073
0x18001005e  lea     rdx, [rsp+3D8h+var_388]
0x180010063  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AADPinResetV2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::GetCachedFeatureEnabledState(void)
0x180010068  mov     rax, [rax]
0x18001006b  mov     [rsp+3D8h+var_388], rax
0x180010070  mov     r8d, eax
0x180010073  xor     eax, eax
0x180010075  mov     [rsp+3D8h+var_394], eax
0x180010079  lea     ebx, [rax+3]
0x18001007c  mov     [rsp+3D8h+var_390], bx
0x180010081  mov     r9d, r8d
0x180010084  shr     r9d, 0Bh
0x180010088  and     r9d, 1
0x18001008c  shr     r8d, 0Ah
0x180010090  and     r8d, 1
0x180010094  mov     [rsp+3D8h+var_3A8], ebx
0x180010098  mov     [rsp+3D8h+var_3B0], 1
0x1800100a0  lea     rax, [rsp+3D8h+var_394]
0x1800100a5  mov     qword ptr [rsp+3D8h+var_3B8], rax; int
0x1800100aa  mov     edx, 25E37E8h
0x1800100af  lea     rcx, qword_18003F868
0x1800100b6  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800100bb  test    rdi, rdi
0x1800100be  jnz     short loc_1800100CC
0x1800100c0  mov     ebx, 80004003h
0x1800100c5  mov     edx, 102h
0x1800100ca  jmp     short loc_18001010A
0x1800100cc  xorps   xmm0, xmm0
0x1800100cf  movq    rax, xmm0
0x1800100d4  cmp     [rdi], rax
0x1800100d7  jnz     short loc_1800100F5
0x1800100d9  psrldq  xmm0, 8
0x1800100de  movq    rax, xmm0
0x1800100e3  cmp     [rdi+8], rax
0x1800100e7  jnz     short loc_1800100F5
0x1800100e9  mov     ebx, 80070057h
0x1800100ee  mov     edx, 104h
0x1800100f3  jmp     short loc_18001010A
0x1800100f5  mov     rdx, rdi
0x1800100f8  mov     ecx, ebx; char *
0x1800100fa  call    CflApiNew__ClearScenarioDataWithReason
0x1800100ff  mov     ebx, eax
0x180010101  test    eax, eax
0x180010103  jns     short loc_18001015B
0x180010105  mov     edx, 106h; void *
0x18001010a  mov     rcx, [rsp+3D8h]; this
0x180010112  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180010119  mov     r9d, ebx; char *
0x18001011c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010121  mov     rcx, [rsp+3D8h]; this
0x180010129  mov     r9d, ebx; char *
0x18001012c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x180010133  mov     edx, 124h; void *
0x180010138  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001013d  nop
0x18001013e  mov     [rsp+3D8h+var_378], rsi
0x180010143  lea     rcx, [rsp+3D8h+var_378]
0x180010148  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001014d  lea     rcx, [rsp+3D8h+var_378]
0x180010152  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010157  mov     eax, ebx
0x180010159  jmp     short loc_180010187
0x18001015b  lea     rcx, [rsp+3D8h+var_378]
0x180010160  call    ?Stop@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180010165  nop
0x180010166  mov     [rsp+3D8h+var_378], rsi
0x18001016b  lea     rcx, [rsp+3D8h+var_378]
0x180010170  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010175  lea     rcx, [rsp+3D8h+var_378]
0x18001017a  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001017f  xor     eax, eax
0x180010181  jmp     short loc_180010187
0x180010183  mov     eax, [rsp+3D8h+dwSize]
0x180010187  mov     rcx, [rsp+3D8h+var_18]
0x18001018f  xor     rcx, rsp; StackCookie
0x180010192  call    __security_check_cookie
0x180010197  lea     r11, [rsp+3D8h+var_8]
0x18001019f  mov     rbx, [r11+18h]
0x1800101a3  mov     rsi, [r11+20h]
0x1800101a7  mov     rsp, r11
0x1800101aa  pop     rdi
0x1800101ab  retn
```
