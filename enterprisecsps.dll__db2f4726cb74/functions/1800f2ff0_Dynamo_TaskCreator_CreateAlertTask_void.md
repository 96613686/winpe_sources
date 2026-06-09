# Dynamo::TaskCreator::CreateAlertTask(void)

- ea: `0x1800f2ff0`
- end: `0x1800f3333`
- name: `?CreateAlertTask@TaskCreator@Dynamo@@UEAAXXZ`
- size: `835`
- prototype: `void __fastcall(Dynamo::TaskCreator *__hidden this)`
- caller_count: `0`
- callee_count: `14`
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
- `0x1800f2ff0`
- `0x1800f37bc`
- `0x1800f482c`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800f30d4`
- `OLEAUT32!__imp_VariantInit` at `0x1800f30f0`
- `OLEAUT32!__imp_VariantInit` at `0x1800f310d`
- `OLEAUT32!__imp_VariantInit` at `0x1800f312a`
- `OLEAUT32!__imp_VariantInit` at `0x1800f30d4`
- `OLEAUT32!__imp_VariantInit` at `0x1800f30f0`
- `OLEAUT32!__imp_VariantInit` at `0x1800f310d`
- `OLEAUT32!__imp_VariantInit` at `0x1800f312a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800f32ec`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800f32ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f3098`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f3098`

## string_xrefs

- `0x1800f32b5`: `AlertTask`
- `0x1800f3233`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">\n    <RegistrationInfo>\n        <Author>$(@%systemRoot%\system32\deviceenroller.exe,-101)</Author>\n        <Description>$(@%systemRoot%\system32\deviceenroller.exe,-104)</Description>\n        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>\n    </RegistrationInfo>\n    <Principals>\n        <Principal id="LocalSystem">\n            <UserId>S-1-5-18</UserId`
- `0x1800f3055`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f30b2`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3198`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3212`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3261`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Dynamo::TaskCreator::CreateAlertTask(Dynamo::TaskCreator *this, unsigned int a2)
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
  __int64 v12; // xmm7_8
  int v13; // eax
  struct ITaskService *v14; // rdi
  HRESULT (__stdcall *NewTask)(ITaskService *, DWORD, ITaskDefinition **); // rbx
  int v16; // eax
  struct ITaskDefinition *v17; // rdi
  HRESULT (__stdcall *put_XmlText)(ITaskDefinition *, BSTR); // rbx
  _QWORD *bstr; // rax
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  struct ITaskDefinition *v25; // [rsp+38h] [rbp-D0h] BYREF
  struct ITaskService *v26; // [rsp+40h] [rbp-C8h] BYREF
  int v27; // [rsp+48h] [rbp-C0h] BYREF
  VARIANTARG v28; // [rsp+50h] [rbp-B8h] BYREF
  VARIANTARG v29; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+80h] [rbp-88h]
  VARIANTARG v31; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-68h] BYREF
  int v33[4]; // [rsp+B8h] [rbp-50h] BYREF
  IRecordInfo *v34; // [rsp+C8h] [rbp-40h]
  __int128 v35; // [rsp+D8h] [rbp-30h] BYREF
  IRecordInfo *v36; // [rsp+E8h] [rbp-20h]
  __int128 v37; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v38; // [rsp+108h] [rbp+0h]
  __int128 v39; // [rsp+118h] [rbp+10h] BYREF
  __int64 v40; // [rsp+128h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]

  v27 = 0;
  v3 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v27, a2);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v3,
      ppv);
  v26 = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v26);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)&v26);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  v5 = v26;
  Connect = v26->lpVtbl->Connect;
  VariantInit(&pvarg);
  v7 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v31);
  v9 = *(_OWORD *)&v31.vt;
  v10 = v31.pRecInfo;
  VariantInit((VARIANTARG *)&v29.decVal.8);
  v11 = *(_OWORD *)&v29.decVal.Lo32;
  v12 = v30;
  VariantInit((VARIANTARG *)&v28.decVal.8);
  *(_OWORD *)v33 = v7;
  v34 = pRecInfo;
  v35 = v9;
  v36 = v10;
  v37 = v11;
  v38 = v12;
  v39 = *(_OWORD *)&v28.decVal.Lo32;
  v40 = *(_QWORD *)&v29.vt;
  v13 = ((__int64 (__fastcall *)(struct ITaskService *, __int128 *, __int128 *, __int128 *))Connect)(
          v5,
          &v39,
          &v37,
          &v35);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v13,
      (int)v33);
  _variant_t::~_variant_t((_variant_t *)&v28.decVal.8);
  _variant_t::~_variant_t((_variant_t *)&v29.decVal.8);
  _variant_t::~_variant_t((_variant_t *)&v31);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  v25 = 0;
  v14 = v26;
  NewTask = v26->lpVtbl->NewTask;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v25);
  v16 = ((__int64 (__fastcall *)(struct ITaskService *, _QWORD, struct ITaskDefinition **))NewTask)(v14, 0, &v25);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v16,
      (int)v33);
  v17 = v25;
  put_XmlText = v25->lpVtbl->put_XmlText;
  bstr = (_QWORD *)wil::make_bstr(
                     &v28,
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
      (void *)0xF8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v20,
      (int)v33);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
  v21 = anonymous_namespace_::CreateCommandLine(&v39, *((_QWORD *)this + 1), *((_QWORD *)this + 2), L"Alert");
  v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
  anonymous_namespace_::AddCommandLine(v25, v22);
  std::wstring::~wstring(&v39);
  Dynamo::TaskCreator::RegisterTask(this, v26, v25, L"AlertTask");
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v26);
  if ( v27 )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800f2ff0  mov     rax, rsp
0x1800f2ff3  push    rbp
0x1800f2ff4  push    rbx
0x1800f2ff5  push    rsi
0x1800f2ff6  push    rdi
0x1800f2ff7  lea     rbp, [rax-0C8h]
0x1800f2ffe  sub     rsp, 1A8h
0x1800f3005  movaps  xmmword ptr [rax-38h], xmm6
0x1800f3009  movaps  xmmword ptr [rax-48h], xmm7
0x1800f300d  movaps  xmmword ptr [rax-58h], xmm8
0x1800f3012  movaps  xmmword ptr [rax-68h], xmm9
0x1800f3017  movaps  xmmword ptr [rax-78h], xmm10
0x1800f301c  movaps  xmmword ptr [rax-88h], xmm11
0x1800f3024  mov     rax, cs:__security_cookie
0x1800f302b  xor     rax, rsp
0x1800f302e  mov     [rbp+0C0h+var_90], rax
0x1800f3032  mov     rsi, rcx
0x1800f3035  mov     [rsp+1C0h+var_180], 0
0x1800f303d  lea     rcx, [rsp+1C0h+var_180]; this
0x1800f3042  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800f3047  mov     rcx, [rbp+0C8h]; this
0x1800f304e  test    eax, eax
0x1800f3050  jns     short loc_1800F3067
0x1800f3052  mov     r9d, eax; char *
0x1800f3055  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f305c  mov     edx, 0F0h; void *
0x1800f3061  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3067  mov     [rsp+1C0h+var_188], 0
0x1800f3070  lea     rcx, [rsp+1C0h+var_188]
0x1800f3075  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f307a  lea     rax, [rsp+1C0h+var_188]
0x1800f307f  mov     qword ptr [rsp+1C0h+ppv], rax; int
0x1800f3084  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800f308b  xor     edx, edx; pUnkOuter
0x1800f308d  lea     r8d, [rdx+1]; dwClsContext
0x1800f3091  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800f3098  call    cs:__imp_CoCreateInstance
0x1800f309f  nop     dword ptr [rax+rax+00h]
0x1800f30a4  mov     rcx, [rbp+0C8h]; this
0x1800f30ab  test    eax, eax
0x1800f30ad  jns     short loc_1800F30C4
0x1800f30af  mov     r9d, eax; char *
0x1800f30b2  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f30b9  mov     edx, 0F3h; void *
0x1800f30be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f30c4  mov     rdi, [rsp+1C0h+var_188]
0x1800f30c9  mov     rax, [rdi]
0x1800f30cc  mov     rbx, [rax+50h]
0x1800f30d0  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x1800f30d4  call    cs:__imp_VariantInit
0x1800f30db  nop     dword ptr [rax+rax+00h]
0x1800f30e0  nop
0x1800f30e1  movups  xmm10, xmmword ptr [rbp+0C0h+pvarg]
0x1800f30e6  movsd   xmm11, qword ptr [rbp+0C0h+pvarg+10h]
0x1800f30ec  lea     rcx, [rbp+0C0h+var_140]; pvarg
0x1800f30f0  call    cs:__imp_VariantInit
0x1800f30f7  nop     dword ptr [rax+rax+00h]
0x1800f30fc  nop
0x1800f30fd  movups  xmm8, xmmword ptr [rbp+0C0h+var_140]
0x1800f3102  movsd   xmm9, qword ptr [rbp+0C0h+var_140+10h]
0x1800f3108  lea     rcx, [rsp+1C0h+var_160+8]; pvarg
0x1800f310d  call    cs:__imp_VariantInit
0x1800f3114  nop     dword ptr [rax+rax+00h]
0x1800f3119  nop
0x1800f311a  movups  xmm6, xmmword ptr [rsp+1C0h+var_160+8]
0x1800f311f  movsd   xmm7, [rsp+1C0h+var_148]
0x1800f3125  lea     rcx, [rsp+1C0h+var_178+8]; pvarg
0x1800f312a  call    cs:__imp_VariantInit
0x1800f3131  nop     dword ptr [rax+rax+00h]
0x1800f3136  nop
0x1800f3137  movups  xmm0, xmmword ptr [rsp+1C0h+var_178+8]
0x1800f313c  movsd   xmm1, qword ptr [rsp+1C0h+var_160]
0x1800f3142  movaps  xmmword ptr [rbp+0C0h+var_110], xmm10
0x1800f3147  movsd   [rbp+0C0h+var_100], xmm11
0x1800f314d  movaps  [rbp+0C0h+var_F0], xmm8
0x1800f3152  movsd   [rbp+0C0h+var_E0], xmm9
0x1800f3158  movaps  [rbp+0C0h+var_D0], xmm6
0x1800f315c  movsd   [rbp+0C0h+var_C0], xmm7
0x1800f3161  movaps  [rbp+0C0h+var_B0], xmm0
0x1800f3165  movsd   [rbp+0C0h+var_A0], xmm1
0x1800f316a  lea     rax, [rbp+0C0h+var_110]
0x1800f316e  mov     qword ptr [rsp+1C0h+ppv], rax; int
0x1800f3173  lea     r9, [rbp+0C0h+var_F0]
0x1800f3177  lea     r8, [rbp+0C0h+var_D0]
0x1800f317b  lea     rdx, [rbp+0C0h+var_B0]
0x1800f317f  mov     rcx, rdi
0x1800f3182  mov     rax, rbx
0x1800f3185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f318a  mov     rcx, [rbp+0C8h]; this
0x1800f3191  test    eax, eax
0x1800f3193  jns     short loc_1800F31AA
0x1800f3195  mov     r9d, eax; char *
0x1800f3198  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f319f  mov     edx, 0F4h; void *
0x1800f31a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f31aa  lea     rcx, [rsp+1C0h+var_178+8]; this
0x1800f31af  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f31b4  nop
0x1800f31b5  lea     rcx, [rsp+1C0h+var_160+8]; this
0x1800f31ba  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f31bf  nop
0x1800f31c0  lea     rcx, [rbp+0C0h+var_140]; this
0x1800f31c4  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f31c9  nop
0x1800f31ca  lea     rcx, [rbp+0C0h+pvarg]; this
0x1800f31ce  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f31d3  mov     [rsp+1C0h+var_190], 0
0x1800f31dc  mov     rdi, [rsp+1C0h+var_188]
0x1800f31e1  mov     rax, [rdi]
0x1800f31e4  mov     rbx, [rax+48h]
0x1800f31e8  lea     rcx, [rsp+1C0h+var_190]
0x1800f31ed  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f31f2  lea     r8, [rsp+1C0h+var_190]
0x1800f31f7  xor     edx, edx
0x1800f31f9  mov     rcx, rdi
0x1800f31fc  mov     rax, rbx
0x1800f31ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3204  mov     rcx, [rbp+0C8h]; this
0x1800f320b  test    eax, eax
0x1800f320d  jns     short loc_1800F3224
0x1800f320f  mov     r9d, eax; char *
0x1800f3212  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3219  mov     edx, 0F7h; void *
0x1800f321e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3224  mov     rdi, [rsp+1C0h+var_190]
0x1800f3229  mov     rax, [rdi]
0x1800f322c  mov     rbx, [rax+0A0h]
0x1800f3233  lea     rdx, aTaskXmlnsHttpS; "<Task xmlns=\"http://schemas.microsoft."...
0x1800f323a  lea     rcx, [rsp+1C0h+var_178]
0x1800f323f  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800f3244  nop
0x1800f3245  mov     rdx, [rax]
0x1800f3248  mov     rcx, rdi
0x1800f324b  mov     rax, rbx
0x1800f324e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3253  mov     rcx, [rbp+0C8h]; this
0x1800f325a  test    eax, eax
0x1800f325c  jns     short loc_1800F3273
0x1800f325e  mov     r9d, eax; char *
0x1800f3261  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3268  mov     edx, 0F8h; void *
0x1800f326d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3273  lea     rcx, [rsp+1C0h+var_178]
0x1800f3278  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f327d  lea     r9, aAlert; "Alert"
0x1800f3284  mov     r8, [rsi+10h]
0x1800f3288  mov     rdx, [rsi+8]
0x1800f328c  lea     rcx, [rbp+0C0h+var_B0]
0x1800f3290  call    _anonymous_namespace___CreateCommandLine
0x1800f3295  nop
0x1800f3296  mov     rcx, rax
0x1800f3299  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f329e  mov     rdx, rax
0x1800f32a1  mov     rcx, [rsp+1C0h+var_190]
0x1800f32a6  call    _anonymous_namespace___AddCommandLine
0x1800f32ab  nop
0x1800f32ac  lea     rcx, [rbp+0C0h+var_B0]
0x1800f32b0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f32b5  lea     r9, aAlerttask; "AlertTask"
0x1800f32bc  mov     r8, [rsp+1C0h+var_190]; struct ITaskDefinition *
0x1800f32c1  mov     rdx, [rsp+1C0h+var_188]; struct ITaskService *
0x1800f32c6  mov     rcx, rsi; this
0x1800f32c9  call    ?RegisterTask@TaskCreator@Dynamo@@AEAAXPEAUITaskService@@PEAUITaskDefinition@@PEBG@Z; Dynamo::TaskCreator::RegisterTask(ITaskService *,ITaskDefinition *,ushort const *)
0x1800f32ce  nop
0x1800f32cf  lea     rcx, [rsp+1C0h+var_190]
0x1800f32d4  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f32d9  nop
0x1800f32da  lea     rcx, [rsp+1C0h+var_188]
0x1800f32df  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f32e4  nop
0x1800f32e5  cmp     [rsp+1C0h+var_180], 0
0x1800f32ea  jz      short loc_1800F32F8
0x1800f32ec  call    cs:__imp_CoUninitialize
0x1800f32f3  nop     dword ptr [rax+rax+00h]
0x1800f32f8  mov     rcx, [rbp+0C0h+var_90]
0x1800f32fc  xor     rcx, rsp; StackCookie
0x1800f32ff  call    __security_check_cookie
0x1800f3304  lea     r11, [rsp+1C0h+var_18]
0x1800f330c  movaps  xmm6, xmmword ptr [r11-18h]
0x1800f3311  movaps  xmm7, xmmword ptr [r11-28h]
0x1800f3316  movaps  xmm8, xmmword ptr [r11-38h]
0x1800f331b  movaps  xmm9, xmmword ptr [r11-48h]
0x1800f3320  movaps  xmm10, xmmword ptr [r11-58h]
0x1800f3325  movaps  xmm11, xmmword ptr [r11-68h]
0x1800f332a  mov     rsp, r11
0x1800f332d  pop     rdi
0x1800f332e  pop     rsi
0x1800f332f  pop     rbx
0x1800f3330  pop     rbp
0x1800f3331  retn
```
