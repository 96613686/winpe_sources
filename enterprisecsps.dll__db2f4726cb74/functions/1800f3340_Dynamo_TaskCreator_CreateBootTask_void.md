# Dynamo::TaskCreator::CreateBootTask(void)

- ea: `0x1800f3340`
- end: `0x1800f37b4`
- name: `?CreateBootTask@TaskCreator@Dynamo@@UEAAXXZ`
- size: `1140`
- prototype: `void __fastcall(Dynamo::TaskCreator *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180008de0`
- `0x18000caf4`
- `0x18000f0c8`
- `0x18002031c`
- `0x180023874`
- `0x180025a9c`
- `0x180050f28`
- `0x1800639d0`
- `0x1800d7e58`
- `0x1800f2c6c`
- `0x1800f2dc8`
- `0x1800f3340`
- `0x1800f37bc`
- `0x1800f482c`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800f3424`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3440`
- `OLEAUT32!__imp_VariantInit` at `0x1800f345c`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3477`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3424`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3440`
- `OLEAUT32!__imp_VariantInit` at `0x1800f345c`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3477`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800f376d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800f376d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f33e8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f33e8`

## string_xrefs

- `0x1800f3715`: `BootTask`
- `0x1800f357f`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">\n    <RegistrationInfo>\n        <Author>$(@%systemRoot%\system32\deviceenroller.exe,-101)</Author>\n        <Description>$(@%systemRoot%\system32\deviceenroller.exe,-104)</Description>\n        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>\n    </RegistrationInfo>\n    <Principals>\n        <Principal id="LocalSystem">\n            <UserId>S-1-5-18</UserId`
- `0x1800f33a5`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3402`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f34e5`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f355e`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f35ad`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3606`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f365a`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f36b0`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall Dynamo::TaskCreator::CreateBootTask(Dynamo::TaskCreator *this, unsigned int a2)
{
  int v3; // eax
  HRESULT Instance; // eax
  struct ITaskService *v5; // rdi
  HRESULT (__stdcall *Connect)(ITaskService *, VARIANT, VARIANT, VARIANT, VARIANT); // rbx
  __int128 v7; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v9; // xmm8
  IRecordInfo *v10; // xmm9_8
  __int128 v11; // xmm6
  IRecordInfo *v12; // xmm7_8
  int v13; // eax
  struct ITaskService *v14; // rdi
  HRESULT (__stdcall *NewTask)(ITaskService *, DWORD, ITaskDefinition **); // rbx
  int v16; // eax
  struct ITaskDefinition *v17; // rdi
  HRESULT (__stdcall *put_XmlText)(ITaskDefinition *, BSTR); // rbx
  _QWORD *bstr; // rax
  int v20; // eax
  struct ITaskDefinition *v21; // rdi
  HRESULT (__stdcall *get_Triggers)(ITaskDefinition *, ITriggerCollection **); // rbx
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, __int64, _QWORD); // rbx
  int v26; // eax
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v28)(_QWORD, GUID *, __int64 *); // rdi
  int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rax
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  struct ITaskDefinition *v34; // [rsp+38h] [rbp-D0h] BYREF
  struct ITaskService *v35; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+48h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG v40; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+80h] [rbp-88h]
  VARIANTARG v42; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v43; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-50h] BYREF
  int v45[4]; // [rsp+D8h] [rbp-30h] BYREF
  IRecordInfo *v46; // [rsp+E8h] [rbp-20h]
  __int128 v47; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v48; // [rsp+108h] [rbp+0h]
  __int128 v49; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v50; // [rsp+128h] [rbp+20h]
  __int128 v51; // [rsp+138h] [rbp+30h] BYREF
  __int64 v52; // [rsp+148h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+1F0h] [rbp+E8h]

  LODWORD(v36) = 0;
  v3 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v36, a2);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v3,
      ppv);
  v35 = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)&v35);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  v5 = v35;
  Connect = v35->lpVtbl->Connect;
  VariantInit(&pvarg);
  v7 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v43);
  v9 = *(_OWORD *)&v43.vt;
  v10 = v43.pRecInfo;
  VariantInit(&v42);
  v11 = *(_OWORD *)&v42.vt;
  v12 = v42.pRecInfo;
  VariantInit((VARIANTARG *)&v40.decVal.8);
  *(_OWORD *)v45 = v7;
  v46 = pRecInfo;
  v47 = v9;
  v48 = v10;
  v49 = v11;
  v50 = v12;
  v51 = *(_OWORD *)&v40.decVal.Lo32;
  v52 = v41;
  v13 = ((__int64 (__fastcall *)(struct ITaskService *, __int128 *, __int128 *, __int128 *))Connect)(
          v5,
          &v51,
          &v49,
          &v47);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v13,
      (int)v45);
  _variant_t::~_variant_t((_variant_t *)&v40.decVal.8);
  _variant_t::~_variant_t((_variant_t *)&v42);
  _variant_t::~_variant_t((_variant_t *)&v43);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  v34 = 0;
  v14 = v35;
  NewTask = v35->lpVtbl->NewTask;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v34);
  v16 = ((__int64 (__fastcall *)(struct ITaskService *, _QWORD, struct ITaskDefinition **))NewTask)(v14, 0, &v34);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v16,
      (int)v45);
  v17 = v34;
  put_XmlText = v34->lpVtbl->put_XmlText;
  bstr = (_QWORD *)wil::make_bstr(
                     &v40,
                     L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\" xmlns:auto-ns1=\"urn:schemas-"
                      "microsoft-com:asm.v3\">\n"
                      "    <RegistrationInfo>\n"
                      "        <Author>$(@%systemRoot%\\system32\\deviceenroller.exe,-101)</Author>\n"
                      "        <Description>$(@%systemRoot%\\system32\\deviceenroller.exe,-104)</Description>\n"
                      "        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>\n"
                      "    </RegistrationInfo>\n"
                      "    <Principals>\n"
                      "        <Principal id=\"LocalSystem\">\n"
                      "            <UserId>S-1-5-18</UserId>\n"
                      "            <RunLevel>HighestAvailable</RunLevel>\n"
                      "        </Principal>\n"
                      "    </Principals>\n"
                      "    <Settings>\n"
                      "        <MultipleInstancesPolicy>Queue</MultipleInstancesPolicy>\n"
                      "        <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>\n"
                      "        <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>\n"
                      "        <AllowHardTerminate>false</AllowHardTerminate>\n"
                      "        <StartWhenAvailable>true</StartWhenAvailable>\n"
                      "        <AllowStartOnDemand>true</AllowStartOnDemand>\n"
                      "        <Hidden>true</Hidden>\n"
                      "        <RunOnlyIfIdle>false</RunOnlyIfIdle>\n"
                      "        <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>\n"
                      "        <ExecutionTimeLimit>PT1H</ExecutionTimeLimit>\n"
                      "    </Settings>\n"
                      "    <Actions Context=\"LocalSystem\">\n"
                      "        <Exec>\n"
                      "            <Command>%windir%\\system32\\deviceenroller.exe</Command>\n"
                      "        </Exec>\n"
                      "    </Actions>\n"
                      "</Task>");
  v20 = ((__int64 (__fastcall *)(struct ITaskDefinition *, _QWORD))put_XmlText)(v17, *bstr);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v20,
      (int)v45);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
  v38 = 0;
  v21 = v34;
  get_Triggers = v34->lpVtbl->get_Triggers;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v38);
  v23 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))get_Triggers)(v21, &v38);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v23,
      (int)v45);
  v37 = 0;
  v24 = v38;
  v25 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v38 + 80LL);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
  v26 = v25(v24, 8, &v37);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v26,
      (int)v45);
  v39 = 0;
  v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v37;
  v28 = **v37;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v39);
  v29 = v28(v27, &GUID_2a9c35da_d357_41f4_bbc1_207ac1b1f3cb, &v39);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v29,
      (int)v45);
  v30 = anonymous_namespace_::CreateCommandLine(&v51, *((_QWORD *)this + 1), *((_QWORD *)this + 2), L"Boot");
  v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
  anonymous_namespace_::AddCommandLine(v34, v31);
  std::wstring::~wstring(&v51);
  *(_QWORD *)&v40.vt = WNF_NASV_SERVICE_RUNNING;
  anonymous_namespace_::AddWnfTrigger(v34, &v40);
  Dynamo::TaskCreator::RegisterTask(this, v35, v34, L"BootTask");
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
  if ( (_DWORD)v36 )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800f3340  mov     rax, rsp
0x1800f3343  push    rbp
0x1800f3344  push    rbx
0x1800f3345  push    rsi
0x1800f3346  push    rdi
0x1800f3347  lea     rbp, [rax-0E8h]
0x1800f334e  sub     rsp, 1C8h
0x1800f3355  movaps  xmmword ptr [rax-38h], xmm6
0x1800f3359  movaps  xmmword ptr [rax-48h], xmm7
0x1800f335d  movaps  xmmword ptr [rax-58h], xmm8
0x1800f3362  movaps  xmmword ptr [rax-68h], xmm9
0x1800f3367  movaps  xmmword ptr [rax-78h], xmm10
0x1800f336c  movaps  xmmword ptr [rax-88h], xmm11
0x1800f3374  mov     rax, cs:__security_cookie
0x1800f337b  xor     rax, rsp
0x1800f337e  mov     [rbp+0E0h+var_90], rax
0x1800f3382  mov     rsi, rcx
0x1800f3385  mov     dword ptr [rsp+1E0h+var_1A0], 0
0x1800f338d  lea     rcx, [rsp+1E0h+var_1A0]; this
0x1800f3392  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800f3397  mov     rcx, [rbp+0E8h]; this
0x1800f339e  test    eax, eax
0x1800f33a0  jns     short loc_1800F33B7
0x1800f33a2  mov     r9d, eax; char *
0x1800f33a5  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f33ac  mov     edx, 0A0h; void *
0x1800f33b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f33b7  mov     [rsp+1E0h+var_1A8], 0
0x1800f33c0  lea     rcx, [rsp+1E0h+var_1A8]
0x1800f33c5  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f33ca  lea     rax, [rsp+1E0h+var_1A8]
0x1800f33cf  mov     qword ptr [rsp+1E0h+ppv], rax; int
0x1800f33d4  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800f33db  xor     edx, edx; pUnkOuter
0x1800f33dd  lea     r8d, [rdx+1]; dwClsContext
0x1800f33e1  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800f33e8  call    cs:__imp_CoCreateInstance
0x1800f33ef  nop     dword ptr [rax+rax+00h]
0x1800f33f4  mov     rcx, [rbp+0E8h]; this
0x1800f33fb  test    eax, eax
0x1800f33fd  jns     short loc_1800F3414
0x1800f33ff  mov     r9d, eax; char *
0x1800f3402  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3409  mov     edx, 0A3h; void *
0x1800f340e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3414  mov     rdi, [rsp+1E0h+var_1A8]
0x1800f3419  mov     rax, [rdi]
0x1800f341c  mov     rbx, [rax+50h]
0x1800f3420  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x1800f3424  call    cs:__imp_VariantInit
0x1800f342b  nop     dword ptr [rax+rax+00h]
0x1800f3430  nop
0x1800f3431  movups  xmm10, xmmword ptr [rbp+0E0h+pvarg]
0x1800f3436  movsd   xmm11, qword ptr [rbp+0E0h+pvarg+10h]
0x1800f343c  lea     rcx, [rbp+0E0h+var_148]; pvarg
0x1800f3440  call    cs:__imp_VariantInit
0x1800f3447  nop     dword ptr [rax+rax+00h]
0x1800f344c  nop
0x1800f344d  movups  xmm8, xmmword ptr [rbp+0E0h+var_148]
0x1800f3452  movsd   xmm9, qword ptr [rbp+0E0h+var_148+10h]
0x1800f3458  lea     rcx, [rbp+0E0h+var_160]; pvarg
0x1800f345c  call    cs:__imp_VariantInit
0x1800f3463  nop     dword ptr [rax+rax+00h]
0x1800f3468  nop
0x1800f3469  movups  xmm6, xmmword ptr [rbp+0E0h+var_160]
0x1800f346d  movsd   xmm7, qword ptr [rbp+0E0h+var_160+10h]
0x1800f3472  lea     rcx, [rsp+1E0h+var_180+8]; pvarg
0x1800f3477  call    cs:__imp_VariantInit
0x1800f347e  nop     dword ptr [rax+rax+00h]
0x1800f3483  nop
0x1800f3484  movups  xmm0, xmmword ptr [rsp+1E0h+var_180+8]
0x1800f3489  movsd   xmm1, [rsp+1E0h+var_168]
0x1800f348f  movaps  xmmword ptr [rbp+0E0h+var_110], xmm10
0x1800f3494  movsd   [rbp+0E0h+var_100], xmm11
0x1800f349a  movaps  [rbp+0E0h+var_F0], xmm8
0x1800f349f  movsd   [rbp+0E0h+var_E0], xmm9
0x1800f34a5  movaps  [rbp+0E0h+var_D0], xmm6
0x1800f34a9  movsd   [rbp+0E0h+var_C0], xmm7
0x1800f34ae  movaps  [rbp+0E0h+var_B0], xmm0
0x1800f34b2  movsd   [rbp+0E0h+var_A0], xmm1
0x1800f34b7  lea     rax, [rbp+0E0h+var_110]
0x1800f34bb  mov     qword ptr [rsp+1E0h+ppv], rax; int
0x1800f34c0  lea     r9, [rbp+0E0h+var_F0]
0x1800f34c4  lea     r8, [rbp+0E0h+var_D0]
0x1800f34c8  lea     rdx, [rbp+0E0h+var_B0]
0x1800f34cc  mov     rcx, rdi
0x1800f34cf  mov     rax, rbx
0x1800f34d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f34d7  mov     rcx, [rbp+0E8h]; this
0x1800f34de  test    eax, eax
0x1800f34e0  jns     short loc_1800F34F7
0x1800f34e2  mov     r9d, eax; char *
0x1800f34e5  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f34ec  mov     edx, 0A4h; void *
0x1800f34f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f34f7  lea     rcx, [rsp+1E0h+var_180+8]; this
0x1800f34fc  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f3501  nop
0x1800f3502  lea     rcx, [rbp+0E0h+var_160]; this
0x1800f3506  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f350b  nop
0x1800f350c  lea     rcx, [rbp+0E0h+var_148]; this
0x1800f3510  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f3515  nop
0x1800f3516  lea     rcx, [rbp+0E0h+pvarg]; this
0x1800f351a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f351f  mov     [rsp+1E0h+var_1B0], 0
0x1800f3528  mov     rdi, [rsp+1E0h+var_1A8]
0x1800f352d  mov     rax, [rdi]
0x1800f3530  mov     rbx, [rax+48h]
0x1800f3534  lea     rcx, [rsp+1E0h+var_1B0]
0x1800f3539  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f353e  lea     r8, [rsp+1E0h+var_1B0]
0x1800f3543  xor     edx, edx
0x1800f3545  mov     rcx, rdi
0x1800f3548  mov     rax, rbx
0x1800f354b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3550  mov     rcx, [rbp+0E8h]; this
0x1800f3557  test    eax, eax
0x1800f3559  jns     short loc_1800F3570
0x1800f355b  mov     r9d, eax; char *
0x1800f355e  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3565  mov     edx, 0A7h; void *
0x1800f356a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3570  mov     rdi, [rsp+1E0h+var_1B0]
0x1800f3575  mov     rax, [rdi]
0x1800f3578  mov     rbx, [rax+0A0h]
0x1800f357f  lea     rdx, aTaskXmlnsHttpS; "<Task xmlns=\"http://schemas.microsoft."...
0x1800f3586  lea     rcx, [rsp+1E0h+var_180]
0x1800f358b  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800f3590  nop
0x1800f3591  mov     rdx, [rax]
0x1800f3594  mov     rcx, rdi
0x1800f3597  mov     rax, rbx
0x1800f359a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f359f  mov     rcx, [rbp+0E8h]; this
0x1800f35a6  test    eax, eax
0x1800f35a8  jns     short loc_1800F35BF
0x1800f35aa  mov     r9d, eax; char *
0x1800f35ad  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f35b4  mov     edx, 0A8h; void *
0x1800f35b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f35bf  lea     rcx, [rsp+1E0h+var_180]
0x1800f35c4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f35c9  mov     [rsp+1E0h+var_190], 0
0x1800f35d2  mov     rdi, [rsp+1E0h+var_1B0]
0x1800f35d7  mov     rax, [rdi]
0x1800f35da  mov     rbx, [rax+48h]
0x1800f35de  lea     rcx, [rsp+1E0h+var_190]
0x1800f35e3  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f35e8  lea     rdx, [rsp+1E0h+var_190]
0x1800f35ed  mov     rcx, rdi
0x1800f35f0  mov     rax, rbx
0x1800f35f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f35f8  mov     rcx, [rbp+0E8h]; this
0x1800f35ff  test    eax, eax
0x1800f3601  jns     short loc_1800F3618
0x1800f3603  mov     r9d, eax; char *
0x1800f3606  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f360d  mov     edx, 0ABh; void *
0x1800f3612  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3618  mov     [rsp+1E0h+var_198], 0
0x1800f3621  mov     rdi, [rsp+1E0h+var_190]
0x1800f3626  mov     rax, [rdi]
0x1800f3629  mov     rbx, [rax+50h]
0x1800f362d  lea     rcx, [rsp+1E0h+var_198]
0x1800f3632  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f3637  lea     r8, [rsp+1E0h+var_198]
0x1800f363c  mov     edx, 8
0x1800f3641  mov     rcx, rdi
0x1800f3644  mov     rax, rbx
0x1800f3647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f364c  mov     rcx, [rbp+0E8h]; this
0x1800f3653  test    eax, eax
0x1800f3655  jns     short loc_1800F366C
0x1800f3657  mov     r9d, eax; char *
0x1800f365a  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3661  mov     edx, 0AEh; void *
0x1800f3666  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f366c  mov     [rsp+1E0h+var_188], 0
0x1800f3675  mov     rbx, [rsp+1E0h+var_198]
0x1800f367a  mov     rax, [rbx]
0x1800f367d  mov     rdi, [rax]
0x1800f3680  lea     rcx, [rsp+1E0h+var_188]
0x1800f3685  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f368a  lea     r8, [rsp+1E0h+var_188]
0x1800f368f  lea     rdx, _GUID_2a9c35da_d357_41f4_bbc1_207ac1b1f3cb
0x1800f3696  mov     rcx, rbx
0x1800f3699  mov     rax, rdi
0x1800f369c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f36a1  nop
0x1800f36a2  mov     rcx, [rbp+0E8h]; this
0x1800f36a9  test    eax, eax
0x1800f36ab  jns     short loc_1800F36C2
0x1800f36ad  mov     r9d, eax; char *
0x1800f36b0  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f36b7  mov     edx, 0B1h; void *
0x1800f36bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f36c2  lea     r9, aBoot; "Boot"
0x1800f36c9  mov     r8, [rsi+10h]
0x1800f36cd  mov     rdx, [rsi+8]
0x1800f36d1  lea     rcx, [rbp+0E0h+var_B0]
0x1800f36d5  call    _anonymous_namespace___CreateCommandLine
0x1800f36da  nop
0x1800f36db  mov     rcx, rax
0x1800f36de  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f36e3  mov     rdx, rax
0x1800f36e6  mov     rcx, [rsp+1E0h+var_1B0]
0x1800f36eb  call    _anonymous_namespace___AddCommandLine
0x1800f36f0  nop
0x1800f36f1  lea     rcx, [rbp+0E0h+var_B0]
0x1800f36f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f36fa  mov     rax, cs:WNF_NASV_SERVICE_RUNNING
0x1800f3701  mov     qword ptr [rsp+1E0h+var_180], rax
0x1800f3706  lea     rdx, [rsp+1E0h+var_180]
0x1800f370b  mov     rcx, [rsp+1E0h+var_1B0]
0x1800f3710  call    _anonymous_namespace___AddWnfTrigger
0x1800f3715  lea     r9, aBoottask; "BootTask"
0x1800f371c  mov     r8, [rsp+1E0h+var_1B0]; struct ITaskDefinition *
0x1800f3721  mov     rdx, [rsp+1E0h+var_1A8]; struct ITaskService *
0x1800f3726  mov     rcx, rsi; this
0x1800f3729  call    ?RegisterTask@TaskCreator@Dynamo@@AEAAXPEAUITaskService@@PEAUITaskDefinition@@PEBG@Z; Dynamo::TaskCreator::RegisterTask(ITaskService *,ITaskDefinition *,ushort const *)
0x1800f372e  nop
0x1800f372f  lea     rcx, [rsp+1E0h+var_188]
0x1800f3734  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f3739  nop
0x1800f373a  lea     rcx, [rsp+1E0h+var_198]
0x1800f373f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f3744  nop
0x1800f3745  lea     rcx, [rsp+1E0h+var_190]
0x1800f374a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f374f  nop
0x1800f3750  lea     rcx, [rsp+1E0h+var_1B0]
0x1800f3755  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f375a  nop
0x1800f375b  lea     rcx, [rsp+1E0h+var_1A8]
0x1800f3760  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f3765  nop
0x1800f3766  cmp     dword ptr [rsp+1E0h+var_1A0], 0
0x1800f376b  jz      short loc_1800F3779
0x1800f376d  call    cs:__imp_CoUninitialize
0x1800f3774  nop     dword ptr [rax+rax+00h]
0x1800f3779  mov     rcx, [rbp+0E0h+var_90]
0x1800f377d  xor     rcx, rsp; StackCookie
0x1800f3780  call    __security_check_cookie
0x1800f3785  lea     r11, [rsp+1E0h+var_18]
0x1800f378d  movaps  xmm6, xmmword ptr [r11-18h]
0x1800f3792  movaps  xmm7, xmmword ptr [r11-28h]
0x1800f3797  movaps  xmm8, xmmword ptr [r11-38h]
0x1800f379c  movaps  xmm9, xmmword ptr [r11-48h]
0x1800f37a1  movaps  xmm10, xmmword ptr [r11-58h]
0x1800f37a6  movaps  xmm11, xmmword ptr [r11-68h]
0x1800f37ab  mov     rsp, r11
0x1800f37ae  pop     rdi
0x1800f37af  pop     rsi
0x1800f37b0  pop     rbx
0x1800f37b1  pop     rbp
0x1800f37b2  retn
```
