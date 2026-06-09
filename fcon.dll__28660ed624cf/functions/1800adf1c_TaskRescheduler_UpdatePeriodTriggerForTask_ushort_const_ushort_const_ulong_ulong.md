# TaskRescheduler::UpdatePeriodTriggerForTask(ushort const *,ushort const *,ulong,ulong)

- ea: `0x1800adf1c`
- end: `0x1800ae5af`
- name: `?UpdatePeriodTriggerForTask@TaskRescheduler@@SAXPEBG0KK@Z`
- size: `1683`
- prototype: `static void(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180073650`

## callees

- `0x1800107b0`
- `0x1800109ac`
- `0x18004bb94`
- `0x1800563b8`
- `0x1800adaa4`
- `0x1800adf1c`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800adf70`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800adf70`
- `OLEAUT32!__imp_VariantInit` at `0x1800adf8e`
- `OLEAUT32!__imp_VariantInit` at `0x1800adf8e`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae42a`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae42a`

## string_xrefs

- `0x1800ae549`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x1800ae04d`: `\Microsoft\Windows\Flighting\FeatureConfig`
- `0x1800ae45e`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ae471`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ae486`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ae49b`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ae4b0`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ae4c5`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ae4da`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ae4f2`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ae50a`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ae51f`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ae534`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ae55e`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ae573`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ae588`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800ae59d`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall TaskRescheduler::UpdatePeriodTriggerForTask(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4)
{
  char v6; // di
  HRESULT Instance; // eax
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  unsigned int v18; // esi
  __int64 v19; // r14
  __int64 (__fastcall *v20)(__int64, _QWORD, struct ITrigger **); // r15
  struct ITrigger *v21; // rcx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  const char *v29; // r9
  __int64 v30; // rax
  int v31; // eax
  int ppv; // [rsp+20h] [rbp-148h]
  struct ITrigger *v33; // [rsp+50h] [rbp-118h] BYREF
  __int64 v34; // [rsp+58h] [rbp-110h] BYREF
  __int64 *v35; // [rsp+60h] [rbp-108h] BYREF
  __int64 *v36; // [rsp+68h] [rbp-100h] BYREF
  __int64 v37; // [rsp+70h] [rbp-F8h] BYREF
  __int64 *v38; // [rsp+78h] [rbp-F0h] BYREF
  __int64 *v39; // [rsp+80h] [rbp-E8h] BYREF
  __int64 v40; // [rsp+88h] [rbp-E0h] BYREF
  _QWORD v41[2]; // [rsp+90h] [rbp-D8h] BYREF
  VARIANTARG v42; // [rsp+A0h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-A8h] BYREF
  VARIANTARG v44; // [rsp+E0h] [rbp-88h] BYREF
  VARIANTARG v45; // [rsp+100h] [rbp-68h] BYREF
  VARIANTARG v46; // [rsp+120h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]
  const unsigned __int16 *v48; // [rsp+170h] [rbp+8h] BYREF
  const unsigned __int16 *v49; // [rsp+178h] [rbp+10h] BYREF

  v49 = a2;
  v48 = a1;
  v39 = 0;
  v6 = 1;
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)&v39);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  VariantInit(&pvarg);
  v42 = pvarg;
  v44 = pvarg;
  v45 = pvarg;
  v46 = pvarg;
  v8 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*v39 + 80))(
         v39,
         &v46,
         &v45,
         &v44);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v8,
      (int)&v42);
  v36 = 0;
  v9 = *v39;
  v36 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 **))(v9 + 56))(
          v39,
          L"\\Microsoft\\Windows\\Flighting\\FeatureConfig",
          &v36);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v10,
      (int)&v42);
  v38 = 0;
  v11 = *v36;
  v38 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 **))(v11 + 104))(
          v36,
          L"BootstrapUsageDataReporting",
          &v38);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v12,
      (int)&v42);
  v35 = 0;
  v13 = *v38;
  v35 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v13 + 152))(v38, &v35);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v14,
      (int)&v42);
  v34 = 0;
  v15 = *v35;
  v34 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v15 + 72))(v35, &v34);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v16,
      (int)&v42);
  LODWORD(v49) = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v34 + 56LL))(v34, &v49);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v17,
      (int)&v42);
  if ( !(_DWORD)v49 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)0x8000FFFFLL,
      (int)&v42);
  v33 = 0;
  LODWORD(v48) = 0;
  v18 = 1;
  if ( (int)v49 >= 1 )
  {
    while ( 1 )
    {
      v19 = v34;
      v20 = *(__int64 (__fastcall **)(__int64, _QWORD, struct ITrigger **))(*(_QWORD *)v34 + 64LL);
      v21 = v33;
      v33 = 0;
      if ( v21 )
        ((void (__fastcall *)(struct ITrigger *, struct ITriggerVtbl *))v21->lpVtbl->Release)(v21, v21->lpVtbl);
      v22 = v20(v19, v18, &v33);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2A,
          (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
          (const char *)(unsigned int)v22,
          (int)&v42);
      v23 = ((__int64 (__fastcall *)(struct ITrigger *, const unsigned __int16 **))v33->lpVtbl->get_Type)(v33, &v48);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2B,
          (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
          (const char *)(unsigned int)v23,
          (int)&v42);
      if ( (_DWORD)v48 == 1 )
        break;
      if ( (int)++v18 > (int)v49 )
        goto LABEL_16;
    }
    v6 = 0;
  }
LABEL_16:
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)0x8000FFFFLL,
      (int)&v42);
  v41[0] = 0;
  v24 = ((__int64 (__fastcall *)(struct ITrigger *, GUID *, _QWORD *))v33->lpVtbl->QueryInterface)(
          v33,
          &GUID_b45747e0_eba7_4276_9f29_85c5bb300006,
          v41);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)v24,
      (int)&v42);
  v37 = 0;
  v25 = *(_QWORD *)v41[0];
  v37 = 0;
  v26 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v25 + 80))(v41[0], &v37);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v26,
      (int)&v42);
  memset(&v42, 0, sizeof(v42));
  v27 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          &v42,
          L"PT%dM",
          a3);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v27,
      (int)&v42);
  v28 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v37 + 64LL))(v37, *(_QWORD *)&v42.vt);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v28,
      (int)&v42);
  try
  {
    TaskRescheduler::AdjustNextRunTime(v33, a4);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      v29);
  }
  v40 = 0;
  v30 = *v36;
  v40 = 0;
  v46 = pvarg;
  v45 = pvarg;
  v44 = pvarg;
  v31 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 *))(v30 + 136))(
          v36,
          L"BootstrapUsageDataReporting",
          v35);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v31,
      (int)&v44);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v40);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v42);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v37);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(v41);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v33);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v34);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v35);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v38);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v36);
  VariantClear(&pvarg);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v39);
}

```

## disassembly

```asm
0x1800adf1c  mov     rax, rsp
0x1800adf1f  mov     [rax+18h], rbx
0x1800adf23  mov     [rax+20h], rsi
0x1800adf27  mov     [rax+10h], rdx
0x1800adf2b  mov     [rax+8], rcx
0x1800adf2f  push    rdi
0x1800adf30  push    r12
0x1800adf32  push    r13
0x1800adf34  push    r14
0x1800adf36  push    r15
0x1800adf38  sub     rsp, 140h
0x1800adf3f  mov     r12d, r9d
0x1800adf42  mov     r13d, r8d
0x1800adf45  xor     ebx, ebx
0x1800adf47  mov     [rax-0E8h], rbx
0x1800adf4e  lea     rax, [rax-0E8h]
0x1800adf55  mov     [rsp+168h+ppv], rax; int
0x1800adf5a  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800adf61  lea     edi, [rbx+1]
0x1800adf64  mov     r8d, edi; dwClsContext
0x1800adf67  xor     edx, edx; pUnkOuter
0x1800adf69  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800adf70  call    cs:__imp_CoCreateInstance
0x1800adf76  mov     rcx, [rsp+168h]; this
0x1800adf7e  test    eax, eax
0x1800adf80  js      loc_1800AE45B
0x1800adf86  lea     rcx, [rsp+168h+pvarg]; pvarg
0x1800adf8e  call    cs:__imp_VariantInit
0x1800adf94  nop
0x1800adf95  mov     rcx, [rsp+168h+var_E8]
0x1800adf9d  movups  xmm1, xmmword ptr [rsp+168h+pvarg]
0x1800adfa5  movsd   xmm0, qword ptr [rsp+168h+pvarg+10h]
0x1800adfae  movaps  xmmword ptr [rsp+168h+var_C8], xmm1
0x1800adfb6  movsd   [rsp+168h+var_B8], xmm0
0x1800adfbf  movaps  xmmword ptr [rsp+168h+var_88], xmm1
0x1800adfc7  movsd   [rsp+168h+var_78], xmm0
0x1800adfd0  movaps  [rsp+168h+var_68], xmm1
0x1800adfd8  movsd   [rsp+168h+var_58], xmm0
0x1800adfe1  movaps  [rsp+168h+var_48], xmm1
0x1800adfe9  movsd   [rsp+168h+var_38], xmm0
0x1800adff2  mov     rax, [rcx]
0x1800adff5  lea     rdx, [rsp+168h+var_C8]
0x1800adffd  mov     [rsp+168h+ppv], rdx; int
0x1800ae002  lea     r9, [rsp+168h+var_88]
0x1800ae00a  lea     r8, [rsp+168h+var_68]
0x1800ae012  lea     rdx, [rsp+168h+var_48]
0x1800ae01a  mov     rax, [rax+50h]
0x1800ae01e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae023  mov     rcx, [rsp+168h]; this
0x1800ae02b  test    eax, eax
0x1800ae02d  js      loc_1800AE46E
0x1800ae033  mov     [rsp+168h+var_100], rbx
0x1800ae038  mov     rcx, [rsp+168h+var_E8]
0x1800ae040  mov     rax, [rcx]
0x1800ae043  mov     [rsp+168h+var_100], rbx
0x1800ae048  lea     r8, [rsp+168h+var_100]
0x1800ae04d  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Flighting\\Featur"...
0x1800ae054  mov     rax, [rax+38h]
0x1800ae058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae05d  mov     rcx, [rsp+168h]; this
0x1800ae065  test    eax, eax
0x1800ae067  js      loc_1800AE483
0x1800ae06d  mov     [rsp+168h+var_F0], rbx
0x1800ae072  mov     rcx, [rsp+168h+var_100]
0x1800ae077  mov     rax, [rcx]
0x1800ae07a  mov     [rsp+168h+var_F0], rbx
0x1800ae07f  lea     r8, [rsp+168h+var_F0]
0x1800ae084  lea     rdx, aBootstrapusage; "BootstrapUsageDataReporting"
0x1800ae08b  mov     rax, [rax+68h]
0x1800ae08f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae094  mov     rcx, [rsp+168h]; this
0x1800ae09c  test    eax, eax
0x1800ae09e  js      loc_1800AE498
0x1800ae0a4  mov     [rsp+168h+var_108], rbx
0x1800ae0a9  mov     rcx, [rsp+168h+var_F0]
0x1800ae0ae  mov     rax, [rcx]
0x1800ae0b1  mov     [rsp+168h+var_108], rbx
0x1800ae0b6  lea     rdx, [rsp+168h+var_108]
0x1800ae0bb  mov     rax, [rax+98h]
0x1800ae0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae0c7  mov     rcx, [rsp+168h]; this
0x1800ae0cf  test    eax, eax
0x1800ae0d1  js      loc_1800AE4AD
0x1800ae0d7  mov     [rsp+168h+var_110], rbx
0x1800ae0dc  mov     rcx, [rsp+168h+var_108]
0x1800ae0e1  mov     rax, [rcx]
0x1800ae0e4  mov     [rsp+168h+var_110], rbx
0x1800ae0e9  lea     rdx, [rsp+168h+var_110]
0x1800ae0ee  mov     rax, [rax+48h]
0x1800ae0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae0f7  mov     rcx, [rsp+168h]; this
0x1800ae0ff  test    eax, eax
0x1800ae101  js      loc_1800AE4C2
0x1800ae107  mov     dword ptr [rsp+168h+arg_8], ebx
0x1800ae10e  mov     rcx, [rsp+168h+var_110]
0x1800ae113  mov     rax, [rcx]
0x1800ae116  lea     rdx, [rsp+168h+arg_8]
0x1800ae11e  mov     rax, [rax+38h]
0x1800ae122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae127  mov     rcx, [rsp+168h]; this
0x1800ae12f  test    eax, eax
0x1800ae131  js      loc_1800AE4D7
0x1800ae137  cmp     dword ptr [rsp+168h+arg_8], ebx
0x1800ae13e  setz    al
0x1800ae141  mov     rcx, [rsp+168h]; this
0x1800ae149  test    al, al
0x1800ae14b  jnz     loc_1800AE4EC
0x1800ae151  mov     [rsp+168h+var_118], rbx
0x1800ae156  mov     dword ptr [rsp+168h+arg_0], ebx
0x1800ae15d  mov     esi, edi
0x1800ae15f  cmp     dword ptr [rsp+168h+arg_8], edi
0x1800ae166  jl      loc_1800AE1F7
0x1800ae16c  mov     r14, [rsp+168h+var_110]
0x1800ae171  mov     rax, [r14]
0x1800ae174  mov     r15, [rax+40h]
0x1800ae178  mov     rcx, [rsp+168h+var_118]
0x1800ae17d  mov     [rsp+168h+var_118], rbx
0x1800ae182  test    rcx, rcx
0x1800ae185  jz      short loc_1800AE194
0x1800ae187  mov     rdx, [rcx]
0x1800ae18a  mov     rax, [rdx+10h]
0x1800ae18e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae193  nop
0x1800ae194  lea     r8, [rsp+168h+var_118]
0x1800ae199  mov     edx, esi
0x1800ae19b  mov     rcx, r14
0x1800ae19e  mov     rax, r15
0x1800ae1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae1a6  mov     rcx, [rsp+168h]; this
0x1800ae1ae  test    eax, eax
0x1800ae1b0  js      loc_1800AE531
0x1800ae1b6  mov     rcx, [rsp+168h+var_118]
0x1800ae1bb  mov     rax, [rcx]
0x1800ae1be  lea     rdx, [rsp+168h+arg_0]
0x1800ae1c6  mov     rax, [rax+38h]
0x1800ae1ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae1cf  mov     rcx, [rsp+168h]; this
0x1800ae1d7  test    eax, eax
0x1800ae1d9  js      loc_1800AE51C
0x1800ae1df  cmp     dword ptr [rsp+168h+arg_0], edi
0x1800ae1e6  jz      short loc_1800AE20A
0x1800ae1e8  add     esi, edi
0x1800ae1ea  cmp     esi, dword ptr [rsp+168h+arg_8]
0x1800ae1f1  jle     loc_1800AE16C
0x1800ae1f7  mov     rcx, [rsp+168h]; this
0x1800ae1ff  test    dil, dil
0x1800ae202  jnz     loc_1800AE504
0x1800ae208  jmp     short loc_1800AE20F
0x1800ae20a  mov     dil, bl
0x1800ae20d  jmp     short loc_1800AE1F7
0x1800ae20f  mov     rcx, [rsp+168h+var_118]
0x1800ae214  mov     [rsp+168h+var_D8], rbx
0x1800ae21c  mov     rax, [rcx]
0x1800ae21f  lea     r8, [rsp+168h+var_D8]
0x1800ae227  lea     rdx, _GUID_b45747e0_eba7_4276_9f29_85c5bb300006
0x1800ae22e  mov     rax, [rax]
0x1800ae231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae236  mov     rcx, [rsp+168h]; this
0x1800ae23e  test    eax, eax
0x1800ae240  js      loc_1800AE546
0x1800ae246  mov     [rsp+168h+var_F8], rbx
0x1800ae24b  mov     rcx, [rsp+168h+var_D8]
0x1800ae253  mov     rax, [rcx]
0x1800ae256  mov     [rsp+168h+var_F8], rbx
0x1800ae25b  lea     rdx, [rsp+168h+var_F8]
0x1800ae260  mov     rax, [rax+50h]
0x1800ae264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae269  mov     rcx, [rsp+168h]; this
0x1800ae271  test    eax, eax
0x1800ae273  js      loc_1800AE55B
0x1800ae279  mov     qword ptr [rsp+168h+var_C8], rbx
0x1800ae281  mov     qword ptr [rsp+168h+var_C8+8], rbx
0x1800ae289  mov     [rsp+168h+var_B8], rbx
0x1800ae291  mov     r8d, r13d
0x1800ae294  lea     rdx, aPtDm; "PT%dM"
0x1800ae29b  lea     rcx, [rsp+168h+var_C8]
0x1800ae2a3  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800ae2a8  mov     rcx, [rsp+168h]; this
0x1800ae2b0  test    eax, eax
0x1800ae2b2  js      loc_1800AE570
0x1800ae2b8  mov     rcx, [rsp+168h+var_F8]
0x1800ae2bd  mov     rax, [rcx]
0x1800ae2c0  mov     rdx, qword ptr [rsp+168h+var_C8]
0x1800ae2c8  mov     rax, [rax+40h]
0x1800ae2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae2d1  mov     rcx, [rsp+168h]; this
0x1800ae2d9  test    eax, eax
0x1800ae2db  js      loc_1800AE585
0x1800ae2e1  mov     edx, r12d; unsigned int
0x1800ae2e4  mov     rcx, [rsp+168h+var_118]; struct ITrigger *
0x1800ae2e9  call    ?AdjustNextRunTime@TaskRescheduler@@CAXPEAUITrigger@@K@Z; TaskRescheduler::AdjustNextRunTime(ITrigger *,ulong)
0x1800ae2ee  nop
0x1800ae2ef  jmp     short loc_1800AE2F3
0x1800ae2f1  xor     ebx, ebx
0x1800ae2f3  mov     [rsp+168h+var_E0], rbx
0x1800ae2fb  mov     rcx, [rsp+168h+var_100]
0x1800ae300  mov     rax, [rcx]
0x1800ae303  mov     [rsp+168h+var_E0], rbx
0x1800ae30b  movups  xmm1, xmmword ptr [rsp+168h+pvarg]
0x1800ae313  movsd   xmm0, qword ptr [rsp+168h+pvarg+10h]
0x1800ae31c  movaps  [rsp+168h+var_48], xmm1
0x1800ae324  movsd   [rsp+168h+var_38], xmm0
0x1800ae32d  movaps  [rsp+168h+var_68], xmm1
0x1800ae335  movsd   [rsp+168h+var_58], xmm0
0x1800ae33e  movaps  xmmword ptr [rsp+168h+var_88], xmm1
0x1800ae346  movsd   [rsp+168h+var_78], xmm0
0x1800ae34f  lea     rdx, [rsp+168h+var_E0]
0x1800ae357  mov     [rsp+168h+var_128], rdx
0x1800ae35c  lea     rdx, [rsp+168h+var_48]
0x1800ae364  mov     [rsp+168h+var_130], rdx
0x1800ae369  mov     r9d, 4
0x1800ae36f  mov     [rsp+168h+var_138], r9d
0x1800ae374  lea     rdx, [rsp+168h+var_68]
0x1800ae37c  mov     [rsp+168h+var_140], rdx
0x1800ae381  lea     rdx, [rsp+168h+var_88]
0x1800ae389  mov     [rsp+168h+ppv], rdx; int
0x1800ae38e  mov     r8, [rsp+168h+var_108]
0x1800ae393  lea     rdx, aBootstrapusage; "BootstrapUsageDataReporting"
0x1800ae39a  mov     rax, [rax+88h]
0x1800ae3a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae3a6  mov     rcx, [rsp+168h]; this
0x1800ae3ae  test    eax, eax
0x1800ae3b0  js      loc_1800AE59A
0x1800ae3b6  lea     rcx, [rsp+168h+var_E0]
0x1800ae3be  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ae3c3  nop
0x1800ae3c4  lea     rcx, [rsp+168h+var_C8]
0x1800ae3cc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ae3d1  nop
0x1800ae3d2  lea     rcx, [rsp+168h+var_F8]
0x1800ae3d7  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ae3dc  nop
0x1800ae3dd  lea     rcx, [rsp+168h+var_D8]
0x1800ae3e5  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ae3ea  nop
0x1800ae3eb  lea     rcx, [rsp+168h+var_118]
0x1800ae3f0  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ae3f5  nop
0x1800ae3f6  lea     rcx, [rsp+168h+var_110]
0x1800ae3fb  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ae400  nop
0x1800ae401  lea     rcx, [rsp+168h+var_108]
0x1800ae406  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ae40b  nop
0x1800ae40c  lea     rcx, [rsp+168h+var_F0]
0x1800ae411  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ae416  nop
0x1800ae417  lea     rcx, [rsp+168h+var_100]
0x1800ae41c  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ae421  nop
0x1800ae422  lea     rcx, [rsp+168h+pvarg]; pvarg
0x1800ae42a  call    cs:__imp_VariantClear
0x1800ae430  nop
0x1800ae431  lea     rcx, [rsp+168h+var_E8]
0x1800ae439  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ae43e  lea     r11, [rsp+168h+var_28]
0x1800ae446  mov     rbx, [r11+40h]
0x1800ae44a  mov     rsi, [r11+48h]
0x1800ae44e  mov     rsp, r11
0x1800ae451  pop     r15
0x1800ae453  pop     r14
0x1800ae455  pop     r13
0x1800ae457  pop     r12
0x1800ae459  pop     rdi
0x1800ae45a  retn
0x1800ae45b  mov     r9d, eax; char *
0x1800ae45e  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800ae465  lea     edx, [rbx+0Eh]; void *
0x1800ae468  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ae46e  mov     r9d, eax; char *
0x1800ae471  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800ae478  mov     edx, 11h; void *
0x1800ae47d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ae483  mov     r9d, eax; char *
0x1800ae486  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800ae48d  mov     edx, 15h; void *
0x1800ae492  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ae498  mov     r9d, eax; char *
0x1800ae49b  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800ae4a2  mov     edx, 18h; void *
0x1800ae4a7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ae4ad  mov     r9d, eax; char *
0x1800ae4b0  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800ae4b7  mov     edx, 1Bh; void *
0x1800ae4bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ae4c2  mov     r9d, eax; char *
0x1800ae4c5  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800ae4cc  mov     edx, 1Fh; void *
0x1800ae4d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ae4d7  mov     r9d, eax; char *
0x1800ae4da  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800ae4e1  mov     edx, 22h ; '"'; void *
0x1800ae4e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ae4ec  mov     r9d, 8000FFFFh; char *
0x1800ae4f2  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800ae4f9  mov     edx, 23h ; '#'; void *
0x1800ae4fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ae504  mov     r9d, 8000FFFFh; char *
0x1800ae50a  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\common\\tasku"...
0x1800ae511  mov     edx, 33h ; '3'; void *
  ... truncated ...
```
