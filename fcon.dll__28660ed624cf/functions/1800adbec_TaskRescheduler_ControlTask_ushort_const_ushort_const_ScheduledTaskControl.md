# TaskRescheduler::ControlTask(ushort const *,ushort const *,ScheduledTaskControl)

- ea: `0x1800adbec`
- end: `0x1800adf15`
- name: `?ControlTask@TaskRescheduler@@SAXPEBG0W4ScheduledTaskControl@@@Z`
- size: `809`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006f440`
- `0x180073650`

## callees

- `0x1800107b0`
- `0x1800109ac`
- `0x1800adbec`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800adc28`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800adc28`
- `OLEAUT32!__imp_VariantInit` at `0x1800adc3e`
- `OLEAUT32!__imp_VariantInit` at `0x1800adc3e`
- `OLEAUT32!__imp_VariantClear` at `0x1800ade54`
- `OLEAUT32!__imp_VariantClear` at `0x1800ade54`

## string_xrefs

- `0x1800adcbe`: `\Microsoft\Windows\Flighting\FeatureConfig`
- `0x1800ade70`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ade85`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ade9a`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800adeaf`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800adec4`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800aded9`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800adeee`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800adf03`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall TaskRescheduler::ControlTask(__int64 *a1, __int64 *a2)
{
  HRESULT v2; // eax
  int v3; // eax
  __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  int ppv; // [rsp+20h] [rbp-89h]
  __int64 *v17; // [rsp+50h] [rbp-59h] BYREF
  LPVOID v18; // [rsp+58h] [rbp-51h] BYREF
  __int64 v19; // [rsp+60h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-41h] BYREF
  VARIANTARG v21; // [rsp+80h] [rbp-29h] BYREF
  VARIANTARG v22; // [rsp+A0h] [rbp-9h] BYREF
  VARIANTARG v23; // [rsp+C0h] [rbp+17h] BYREF
  VARIANTARG v24; // [rsp+E0h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  __int64 *v26; // [rsp+110h] [rbp+67h] BYREF
  __int64 *v27; // [rsp+118h] [rbp+6Fh] BYREF
  __int64 v28; // [rsp+128h] [rbp+7Fh] BYREF

  v27 = a2;
  v26 = a1;
  v18 = 0;
  v2 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v18);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v2,
      ppv);
  VariantInit(&pvarg);
  v24 = pvarg;
  v21 = pvarg;
  v22 = pvarg;
  v23 = pvarg;
  v3 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v18 + 80LL))(
         v18,
         &v23,
         &v22,
         &v21);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v3,
      (int)&v24);
  v26 = 0;
  v4 = *(_QWORD *)v18;
  v26 = 0;
  v5 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 **))(v4 + 56))(
         v18,
         L"\\Microsoft\\Windows\\Flighting\\FeatureConfig",
         &v26);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v5,
      (int)&v24);
  v17 = 0;
  v6 = *v26;
  v17 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 **))(v6 + 104))(
         v26,
         L"BootstrapUsageDataReporting",
         &v17);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v7,
      (int)&v24);
  v27 = 0;
  v8 = *v17;
  v27 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v8 + 152))(v17, &v27);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v9,
      (int)&v24);
  v28 = 0;
  v10 = *v27;
  v28 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v10 + 88))(v27, &v28);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v11,
      (int)&v24);
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 240LL))(v28, 0);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v12,
      (int)&v24);
  v19 = 0;
  v13 = *v26;
  v19 = 0;
  v23 = pvarg;
  v22 = pvarg;
  v21 = pvarg;
  v14 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 *))(v13 + 136))(
          v26,
          L"BootstrapUsageDataReporting",
          v27);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v14,
      (int)&v21);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v19);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v28);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v27);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v17);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v26);
  VariantClear(&pvarg);
  return wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v18);
}

```

## disassembly

```asm
0x1800adbec  mov     [rsp-8+arg_8], rdx
0x1800adbf1  mov     [rsp-8+arg_0], rcx
0x1800adbf6  push    rbp
0x1800adbf7  lea     rbp, [rsp-57h]
0x1800adbfc  sub     rsp, 100h
0x1800adc03  mov     [rbp+57h+var_A8], 0
0x1800adc0b  lea     rax, [rbp+57h+var_A8]
0x1800adc0f  mov     [rsp+100h+ppv], rax; int
0x1800adc14  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800adc1b  xor     edx, edx; pUnkOuter
0x1800adc1d  lea     r8d, [rdx+1]; dwClsContext
0x1800adc21  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800adc28  call    cs:__imp_CoCreateInstance
0x1800adc2e  mov     rcx, [rbp+5Fh]; this
0x1800adc32  test    eax, eax
0x1800adc34  js      loc_1800ADE82
0x1800adc3a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800adc3e  call    cs:__imp_VariantInit
0x1800adc44  nop
0x1800adc45  mov     rcx, [rbp+57h+var_A8]
0x1800adc49  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x1800adc4d  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x1800adc52  movaps  xmmword ptr [rbp+57h+var_20], xmm1
0x1800adc56  movsd   [rbp+57h+var_10], xmm0
0x1800adc5b  movaps  xmmword ptr [rbp+57h+var_80], xmm1
0x1800adc5f  movsd   [rbp+57h+var_70], xmm0
0x1800adc64  movaps  [rbp+57h+var_60], xmm1
0x1800adc68  movsd   [rbp+57h+var_50], xmm0
0x1800adc6d  movaps  [rbp+57h+var_40], xmm1
0x1800adc71  movsd   [rbp+57h+var_30], xmm0
0x1800adc76  mov     rax, [rcx]
0x1800adc79  lea     rdx, [rbp+57h+var_20]
0x1800adc7d  mov     [rsp+100h+ppv], rdx; int
0x1800adc82  lea     r9, [rbp+57h+var_80]
0x1800adc86  lea     r8, [rbp+57h+var_60]
0x1800adc8a  lea     rdx, [rbp+57h+var_40]
0x1800adc8e  mov     rax, [rax+50h]
0x1800adc92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adc97  mov     rcx, [rbp+5Fh]; this
0x1800adc9b  test    eax, eax
0x1800adc9d  js      loc_1800ADE97
0x1800adca3  mov     [rbp+57h+arg_0], 0
0x1800adcab  mov     rcx, [rbp+57h+var_A8]
0x1800adcaf  mov     rax, [rcx]
0x1800adcb2  mov     [rbp+57h+arg_0], 0
0x1800adcba  lea     r8, [rbp+57h+arg_0]
0x1800adcbe  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Flighting\\Featur"...
0x1800adcc5  mov     rax, [rax+38h]
0x1800adcc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adcce  mov     rcx, [rbp+5Fh]; this
0x1800adcd2  test    eax, eax
0x1800adcd4  js      loc_1800ADEAC
0x1800adcda  mov     [rbp+57h+var_B0], 0
0x1800adce2  mov     rcx, [rbp+57h+arg_0]
0x1800adce6  mov     rax, [rcx]
0x1800adce9  mov     [rbp+57h+var_B0], 0
0x1800adcf1  lea     r8, [rbp+57h+var_B0]
0x1800adcf5  lea     rdx, aBootstrapusage; "BootstrapUsageDataReporting"
0x1800adcfc  mov     rax, [rax+68h]
0x1800add00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add05  mov     rcx, [rbp+5Fh]; this
0x1800add09  test    eax, eax
0x1800add0b  js      loc_1800ADEC1
0x1800add11  mov     [rbp+57h+arg_8], 0
0x1800add19  mov     rcx, [rbp+57h+var_B0]
0x1800add1d  mov     rax, [rcx]
0x1800add20  mov     [rbp+57h+arg_8], 0
0x1800add28  lea     rdx, [rbp+57h+arg_8]
0x1800add2c  mov     rax, [rax+98h]
0x1800add33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add38  mov     rcx, [rbp+5Fh]; this
0x1800add3c  test    eax, eax
0x1800add3e  js      loc_1800ADED6
0x1800add44  mov     [rbp+57h+arg_18], 0
0x1800add4c  mov     rcx, [rbp+57h+arg_8]
0x1800add50  mov     rax, [rcx]
0x1800add53  mov     [rbp+57h+arg_18], 0
0x1800add5b  lea     rdx, [rbp+57h+arg_18]
0x1800add5f  mov     rax, [rax+58h]
0x1800add63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add68  mov     rcx, [rbp+5Fh]; this
0x1800add6c  test    eax, eax
0x1800add6e  js      loc_1800ADEEB
0x1800add74  mov     rcx, [rbp+57h+arg_18]
0x1800add78  mov     rax, [rcx]
0x1800add7b  xor     edx, edx
0x1800add7d  mov     rax, [rax+0F0h]
0x1800add84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add89  mov     rcx, [rbp+5Fh]; this
0x1800add8d  test    eax, eax
0x1800add8f  js      loc_1800ADF00
0x1800add95  mov     [rbp+57h+var_A0], 0
0x1800add9d  mov     rcx, [rbp+57h+arg_0]
0x1800adda1  mov     rax, [rcx]
0x1800adda4  mov     [rbp+57h+var_A0], 0
0x1800addac  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x1800addb0  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x1800addb5  movaps  [rbp+57h+var_40], xmm1
0x1800addb9  movsd   [rbp+57h+var_30], xmm0
0x1800addbe  movaps  [rbp+57h+var_60], xmm1
0x1800addc2  movsd   [rbp+57h+var_50], xmm0
0x1800addc7  movaps  xmmword ptr [rbp+57h+var_80], xmm1
0x1800addcb  movsd   [rbp+57h+var_70], xmm0
0x1800addd0  lea     r8, [rbp+57h+var_A0]
0x1800addd4  mov     [rsp+100h+var_C0], r8
0x1800addd9  lea     r8, [rbp+57h+var_40]
0x1800adddd  mov     [rsp+100h+var_C8], r8
0x1800adde2  mov     r9d, 4
0x1800adde8  mov     [rsp+100h+var_D0], r9d
0x1800added  lea     r8, [rbp+57h+var_60]
0x1800addf1  mov     [rsp+100h+var_D8], r8
0x1800addf6  lea     r8, [rbp+57h+var_80]
0x1800addfa  mov     [rsp+100h+ppv], r8; int
0x1800addff  mov     r8, [rbp+57h+arg_8]
0x1800ade03  lea     rdx, aBootstrapusage; "BootstrapUsageDataReporting"
0x1800ade0a  mov     rax, [rax+88h]
0x1800ade11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ade16  mov     rcx, [rbp+5Fh]; this
0x1800ade1a  test    eax, eax
0x1800ade1c  js      short loc_1800ADE6D
0x1800ade1e  lea     rcx, [rbp+57h+var_A0]
0x1800ade22  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ade27  nop
0x1800ade28  lea     rcx, [rbp+57h+arg_18]
0x1800ade2c  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ade31  nop
0x1800ade32  lea     rcx, [rbp+57h+arg_8]
0x1800ade36  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ade3b  nop
0x1800ade3c  lea     rcx, [rbp+57h+var_B0]
0x1800ade40  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ade45  nop
0x1800ade46  lea     rcx, [rbp+57h+arg_0]
0x1800ade4a  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ade4f  nop
0x1800ade50  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800ade54  call    cs:__imp_VariantClear
0x1800ade5a  nop
0x1800ade5b  lea     rcx, [rbp+57h+var_A8]
0x1800ade5f  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ade64  add     rsp, 100h
0x1800ade6b  pop     rbp
0x1800ade6c  retn
0x1800ade6d  mov     r9d, eax; char *
0x1800ade70  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800ade77  mov     edx, 92h; void *
0x1800ade7c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ade82  mov     r9d, eax; char *
0x1800ade85  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800ade8c  mov     edx, 73h ; 's'; void *
0x1800ade91  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ade97  mov     r9d, eax; char *
0x1800ade9a  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800adea1  mov     edx, 76h ; 'v'; void *
0x1800adea6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800adeac  mov     r9d, eax; char *
0x1800adeaf  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800adeb6  mov     edx, 7Ah ; 'z'; void *
0x1800adebb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800adec1  mov     r9d, eax; char *
0x1800adec4  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800adecb  mov     edx, 7Dh ; '}'; void *
0x1800aded0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800aded6  mov     r9d, eax; char *
0x1800aded9  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800adee0  mov     edx, 80h; void *
0x1800adee5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800adeeb  mov     r9d, eax; char *
0x1800adeee  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800adef5  mov     edx, 83h; void *
0x1800adefa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800adf00  mov     r9d, eax; char *
0x1800adf03  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800adf0a  mov     edx, 88h; void *
0x1800adf0f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
