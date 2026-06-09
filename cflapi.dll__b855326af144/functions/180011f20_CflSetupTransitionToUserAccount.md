# CflSetupTransitionToUserAccount

- ea: `0x180011f20`
- end: `0x180012203`
- name: `CflSetupTransitionToUserAccount`
- size: `739`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x1800067c4`
- `0x1800087f0`
- `0x1800099c4`
- `0x18000a11c`
- `0x18000c44c`
- `0x18000d5dc`
- `0x18000d78c`
- `0x180011f20`
- `0x18002ba10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011f6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011f6c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180011f84`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180011f84`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180011f8a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180011f8a`

## string_xrefs

- `0x1800121a7`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`
- `0x18001218d`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CflSetupTransitionToUserAccount(BYTE *a1, DWORD a2, const BYTE *a3, BYTE *a4, DWORD cbData)
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  __int64 v11; // rcx
  unsigned int v12; // r8d
  unsigned int v13; // ebx
  __int64 v14; // rdx
  unsigned int v15; // r8d
  const char *v16; // r9
  __int64 result; // rax
  int *lpData; // [rsp+20h] [rbp-3E8h]
  int lpDataa; // [rsp+20h] [rbp-3E8h]
  DWORD dwSize; // [rsp+40h] [rbp-3C8h] BYREF
  int v21; // [rsp+44h] [rbp-3C4h] BYREF
  __int16 v22; // [rsp+48h] [rbp-3C0h]
  __int64 v23; // [rsp+50h] [rbp-3B8h] BYREF
  void **v24; // [rsp+60h] [rbp-3A8h] BYREF
  int v25; // [rsp+68h] [rbp-3A0h] BYREF
  char v26; // [rsp+6Ch] [rbp-39Ch]
  int v27; // [rsp+90h] [rbp-378h] BYREF
  const char *v28; // [rsp+98h] [rbp-370h]
  __int64 v29; // [rsp+A0h] [rbp-368h]
  char v30; // [rsp+A8h] [rbp-360h]
  int v31; // [rsp+B0h] [rbp-358h]
  _BYTE v32[152]; // [rsp+B8h] [rbp-350h] BYREF
  __int128 v33; // [rsp+150h] [rbp-2B8h]
  int v34; // [rsp+160h] [rbp-2A8h]
  __int64 v35; // [rsp+168h] [rbp-2A0h]
  int *v36; // [rsp+170h] [rbp-298h]
  __int64 v37; // [rsp+178h] [rbp-290h]
  __int64 v38; // [rsp+180h] [rbp-288h]
  void ***v39; // [rsp+188h] [rbp-280h]
  __int64 v40; // [rsp+190h] [rbp-278h]
  int v41; // [rsp+198h] [rbp-270h]
  int *v42; // [rsp+1A0h] [rbp-268h]
  char v43; // [rsp+1A8h] [rbp-260h]
  WCHAR ExeName[264]; // [rsp+1B0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+0h]

  memset_0(ExeName, 0, 0x20Au);
  dwSize = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize);
  CommandLineW = GetCommandLineW();
  v25 = 0;
  v26 = 0;
  v30 = 0;
  v27 = 0;
  v28 = "CflSetupTransitionToUserAccountMeasure";
  v29 = 0;
  v31 = 0;
  v33 = 0;
  memset_0(v32, 0, sizeof(v32));
  try
  {
    v34 = 1;
    v35 = 0;
    v36 = &v25;
    v37 = 0;
    v38 = 0;
    v39 = &v24;
    v40 = 0;
    v41 = 0;
    v42 = &v27;
    v43 = 0;
    v24 = &CflApiTraceProvider::CflSetupTransitionToUserAccountMeasure::`vftable';
    CflApiTraceProvider::CflSetupTransitionToUserAccountMeasure::StartActivity(
      (CflApiTraceProvider::CflSetupTransitionToUserAccountMeasure *)&v24,
      ExeName,
      CommandLineW);
    v12 = *(_DWORD *)Feature_AADPinResetV2__descriptor;
    if ( (*(_DWORD *)Feature_AADPinResetV2__descriptor & 4) == 0 )
    {
      v23 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::GetCachedFeatureEnabledState(
                         v11,
                         &v23);
      v12 = v23;
    }
    v21 = 0;
    v22 = 3;
    lpData = &v21;
    wil::details::ReportUsageToService(&qword_18003F868, 39729128, (v12 >> 10) & 1, (v12 >> 11) & 1);
    if ( !a1 )
    {
      v13 = -2147467261;
      v14 = 132;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
        (const char *)v13,
        (int)lpData);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
        (const char *)v13,
        lpDataa);
      v24 = &CflApiTraceProvider::CflSetupTransitionToUserAccountMeasure::`vftable';
      wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v24);
      wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v24);
      return v13;
    }
    if ( a2 )
    {
      if ( a4 )
      {
        if ( cbData )
          goto LABEL_11;
      }
      else if ( !cbData )
      {
LABEL_11:
        if ( a3 || !a4 )
        {
          v13 = CflApiNew::SetAllScenarioData(0, a1, a2, a3, a4, cbData, 0);
          if ( (v13 & 0x80000000) == 0 )
          {
            wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v24);
            v24 = &CflApiTraceProvider::CflSetupTransitionToUserAccountMeasure::`vftable';
            wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v24);
            wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v24);
            return 0;
          }
          v14 = 149;
          goto LABEL_17;
        }
      }
    }
    v13 = -2147024809;
    v14 = 139;
    goto LABEL_17;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x78, v15, v16);
  }
  return result;
}

```

## disassembly

```asm
0x180011f20  push    rbx
0x180011f22  push    rsi
0x180011f23  push    rdi
0x180011f24  push    r12
0x180011f26  push    r14
0x180011f28  push    r15
0x180011f2a  sub     rsp, 3D8h
0x180011f31  mov     rax, cs:__security_cookie
0x180011f38  xor     rax, rsp
0x180011f3b  mov     [rsp+408h+var_48], rax
0x180011f43  mov     rdi, r9
0x180011f46  mov     r15, r8
0x180011f49  mov     r14d, edx
0x180011f4c  mov     rsi, rcx
0x180011f4f  xor     edx, edx; Val
0x180011f51  mov     r8d, 20Ah; Size
0x180011f57  lea     rcx, [rsp+408h+ExeName]; void *
0x180011f5f  call    memset_0
0x180011f64  mov     [rsp+408h+dwSize], 105h
0x180011f6c  call    cs:__imp_GetCurrentProcess
0x180011f72  mov     rcx, rax; hProcess
0x180011f75  lea     r9, [rsp+408h+dwSize]; lpdwSize
0x180011f7a  lea     r8, [rsp+408h+ExeName]; lpExeName
0x180011f82  xor     edx, edx; dwFlags
0x180011f84  call    cs:__imp_QueryFullProcessImageNameW
0x180011f8a  call    cs:__imp_GetCommandLineW
0x180011f90  mov     rbx, rax
0x180011f93  xor     r12d, r12d
0x180011f96  mov     [rsp+408h+var_3A0], r12d
0x180011f9b  mov     [rsp+408h+var_39C], r12b
0x180011fa0  mov     [rsp+408h+var_360], r12b
0x180011fa8  mov     [rsp+408h+var_378], r12d
0x180011fb0  lea     rax, aCflsetuptransi_0; "CflSetupTransitionToUserAccountMeasure"
0x180011fb7  mov     [rsp+408h+var_370], rax
0x180011fbf  mov     [rsp+408h+var_368], r12
0x180011fc7  mov     [rsp+408h+var_358], r12d
0x180011fcf  xorps   xmm0, xmm0
0x180011fd2  movdqa  [rsp+408h+var_2B8], xmm0
0x180011fdb  xor     edx, edx; Val
0x180011fdd  mov     r8d, 98h; Size
0x180011fe3  lea     rcx, [rsp+408h+var_350]; void *
0x180011feb  call    memset_0
0x180011ff0  mov     [rsp+408h+var_2A8], 1
0x180011ffb  xor     eax, eax
0x180011ffd  mov     [rsp+408h+var_2A0], rax
0x180012005  lea     rax, [rsp+408h+var_3A0]
0x18001200a  mov     [rsp+408h+var_298], rax
0x180012012  mov     [rsp+408h+var_290], r12
0x18001201a  mov     [rsp+408h+var_288], r12
0x180012022  lea     rax, [rsp+408h+var_3A8]
0x180012027  mov     [rsp+408h+var_280], rax
0x18001202f  mov     [rsp+408h+var_278], r12
0x180012037  mov     [rsp+408h+var_270], r12d
0x18001203f  lea     rax, [rsp+408h+var_378]
0x180012047  mov     [rsp+408h+var_268], rax
0x18001204f  mov     [rsp+408h+var_260], r12b
0x180012057  lea     rax, ??_7CflSetupTransitionToUserAccountMeasure@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSetupTransitionToUserAccountMeasure::`vftable'
0x18001205e  mov     [rsp+408h+var_3A8], rax
0x180012063  mov     r8, rbx; unsigned __int16 *
0x180012066  lea     rdx, [rsp+408h+ExeName]; unsigned __int16 *
0x18001206e  lea     rcx, [rsp+408h+var_3A8]; this
0x180012073  call    ?StartActivity@CflSetupTransitionToUserAccountMeasure@CflApiTraceProvider@@QEAAXPEBG0@Z; CflApiTraceProvider::CflSetupTransitionToUserAccountMeasure::StartActivity(ushort const *,ushort const *)
0x180012078  nop
0x180012079  mov     rax, cs:Feature_AADPinResetV2__descriptor
0x180012080  mov     r8d, [rax]
0x180012083  test    r8b, 4
0x180012087  jnz     short loc_18001209E
0x180012089  lea     rdx, [rsp+408h+var_3B8]
0x18001208e  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AADPinResetV2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::GetCachedFeatureEnabledState(void)
0x180012093  mov     rax, [rax]
0x180012096  mov     [rsp+408h+var_3B8], rax
0x18001209b  mov     r8d, eax
0x18001209e  mov     [rsp+408h+var_3C4], r12d
0x1800120a3  mov     [rsp+408h+var_3C0], 3
0x1800120aa  mov     r9d, r8d
0x1800120ad  shr     r9d, 0Bh
0x1800120b1  and     r9d, 1
0x1800120b5  shr     r8d, 0Ah
0x1800120b9  and     r8d, 1
0x1800120bd  mov     dword ptr [rsp+408h+Data], 3
0x1800120c5  mov     [rsp+408h+cbData], 1
0x1800120cd  lea     rax, [rsp+408h+var_3C4]
0x1800120d2  mov     [rsp+408h+lpData], rax; int
0x1800120d7  mov     edx, 25E37E8h
0x1800120dc  lea     rcx, qword_18003F868
0x1800120e3  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800120e8  test    rsi, rsi
0x1800120eb  jnz     short loc_1800120FC
0x1800120ed  mov     ebx, 80004003h
0x1800120f2  mov     edx, 84h
0x1800120f7  jmp     loc_180012185
0x1800120fc  test    r14d, r14d
0x1800120ff  jz      short loc_18001217B
0x180012101  mov     eax, [rsp+408h+arg_20]
0x180012108  test    rdi, rdi
0x18001210b  jz      short loc_180012113
0x18001210d  test    eax, eax
0x18001210f  jz      short loc_18001217B
0x180012111  jmp     short loc_180012117
0x180012113  test    eax, eax
0x180012115  jnz     short loc_18001217B
0x180012117  test    r15, r15
0x18001211a  jnz     short loc_180012121
0x18001211c  test    rdi, rdi
0x18001211f  jnz     short loc_18001217B
0x180012121  mov     dword ptr [rsp+408h+Data], r12d; Data
0x180012126  mov     [rsp+408h+cbData], eax; cbData
0x18001212a  mov     [rsp+408h+lpData], rdi; lpData
0x18001212f  mov     r9, r15
0x180012132  mov     r8d, r14d
0x180012135  mov     rdx, rsi
0x180012138  xor     ecx, ecx; rclsid
0x18001213a  call    CflApiNew__SetAllScenarioData
0x18001213f  mov     ebx, eax
0x180012141  test    eax, eax
0x180012143  jns     short loc_18001214C
0x180012145  mov     edx, 95h
0x18001214a  jmp     short loc_180012185
0x18001214c  lea     rcx, [rsp+408h+var_3A8]
0x180012151  call    ?Stop@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180012156  nop
0x180012157  lea     rax, ??_7CflSetupTransitionToUserAccountMeasure@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSetupTransitionToUserAccountMeasure::`vftable'
0x18001215e  mov     [rsp+408h+var_3A8], rax
0x180012163  lea     rcx, [rsp+408h+var_3A8]
0x180012168  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001216d  lea     rcx, [rsp+408h+var_3A8]
0x180012172  call    ??1?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180012177  xor     eax, eax
0x180012179  jmp     short loc_1800121E1
0x18001217b  mov     ebx, 80070057h
0x180012180  mov     edx, 8Bh; void *
0x180012185  mov     rcx, [rsp+408h]; this
0x18001218d  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180012194  mov     r9d, ebx; char *
0x180012197  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001219c  mov     rcx, [rsp+408h]; this
0x1800121a4  mov     r9d, ebx; char *
0x1800121a7  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x1800121ae  mov     edx, 68h ; 'h'; void *
0x1800121b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800121b8  nop
0x1800121b9  lea     rax, ??_7CflSetupTransitionToUserAccountMeasure@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSetupTransitionToUserAccountMeasure::`vftable'
0x1800121c0  mov     [rsp+408h+var_3A8], rax
0x1800121c5  lea     rcx, [rsp+408h+var_3A8]
0x1800121ca  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800121cf  lea     rcx, [rsp+408h+var_3A8]
0x1800121d4  call    ??1?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800121d9  mov     eax, ebx
0x1800121db  jmp     short loc_1800121E1
0x1800121dd  mov     eax, [rsp+408h+dwSize]
0x1800121e1  mov     rcx, [rsp+408h+var_48]
0x1800121e9  xor     rcx, rsp; StackCookie
0x1800121ec  call    __security_check_cookie
0x1800121f1  add     rsp, 3D8h
0x1800121f8  pop     r15
0x1800121fa  pop     r14
0x1800121fc  pop     r12
0x1800121fe  pop     rdi
0x1800121ff  pop     rsi
0x180012200  pop     rbx
0x180012201  retn
```
