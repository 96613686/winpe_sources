# Dynamo::TaskCreator::CreateUserLoginTask(void)

- ea: `0x1800f3c90`
- end: `0x1800f412c`
- name: `?CreateUserLoginTask@TaskCreator@Dynamo@@UEAAXXZ`
- size: `1180`
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
- `0x1800f2aa0`
- `0x1800f2c6c`
- `0x1800f37bc`
- `0x1800f3c90`
- `0x1800f482c`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800f3d7f`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3d9b`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3db7`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3dd2`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3d7f`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3d9b`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3db7`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3dd2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800f40e5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800f40e5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f3d43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f3d43`

## string_xrefs

- `0x1800f408d`: `LoginTask`
- `0x1800f3eda`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">\n    <RegistrationInfo>\n        <Author>$(@%systemRoot%\system32\deviceenroller.exe,-101)</Author>\n        <Description>$(@%systemRoot%\system32\deviceenroller.exe,-104)</Description>\n        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>\n    </RegistrationInfo>\n    <Principals>\n        <Principal id="LocalSystem">\n            <UserId>S-1-5-18</UserId`
- `0x1800f3d00`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3d5d`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3e40`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3eb9`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3f08`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3f61`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3fb5`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3fed`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f4039`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall Dynamo::TaskCreator::CreateUserLoginTask(Dynamo::TaskCreator *this, unsigned int a2)
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
  __int64 (__fastcall *v25)(__int64, __int64, __int64 *); // rbx
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, _QWORD); // rbx
  _QWORD *v30; // rax
  int v31; // eax
  __int64 v32; // rax
  __int64 v33; // rax
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  struct ITaskDefinition *v36; // [rsp+38h] [rbp-D0h] BYREF
  struct ITaskService *v37; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v38; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG v42; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+80h] [rbp-88h]
  VARIANTARG v44; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v45; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-50h] BYREF
  int v47[4]; // [rsp+D8h] [rbp-30h] BYREF
  IRecordInfo *v48; // [rsp+E8h] [rbp-20h]
  __int128 v49; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v50; // [rsp+108h] [rbp+0h]
  __int128 v51; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v52; // [rsp+128h] [rbp+20h]
  __int128 v53; // [rsp+138h] [rbp+30h] BYREF
  __int64 v54; // [rsp+148h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+1F0h] [rbp+E8h]

  if ( *((_QWORD *)this + 2) )
  {
    LODWORD(v38) = 0;
    v3 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v38, a2);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v3,
        ppv);
    v37 = 0;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
    Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)&v37);
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCC,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)Instance,
        ppva);
    v5 = v37;
    Connect = v37->lpVtbl->Connect;
    VariantInit(&pvarg);
    v7 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v45);
    v9 = *(_OWORD *)&v45.vt;
    v10 = v45.pRecInfo;
    VariantInit(&v44);
    v11 = *(_OWORD *)&v44.vt;
    v12 = v44.pRecInfo;
    VariantInit((VARIANTARG *)&v42.decVal.8);
    *(_OWORD *)v47 = v7;
    v48 = pRecInfo;
    v49 = v9;
    v50 = v10;
    v51 = v11;
    v52 = v12;
    v53 = *(_OWORD *)&v42.decVal.Lo32;
    v54 = v43;
    v13 = ((__int64 (__fastcall *)(struct ITaskService *, __int128 *, __int128 *, __int128 *))Connect)(
            v5,
            &v53,
            &v51,
            &v49);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v13,
        (int)v47);
    _variant_t::~_variant_t((_variant_t *)&v42.decVal.8);
    _variant_t::~_variant_t((_variant_t *)&v44);
    _variant_t::~_variant_t((_variant_t *)&v45);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    v36 = 0;
    v14 = v37;
    NewTask = v37->lpVtbl->NewTask;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v36);
    v16 = ((__int64 (__fastcall *)(struct ITaskService *, _QWORD, struct ITaskDefinition **))NewTask)(v14, 0, &v36);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD0,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v16,
        (int)v47);
    v17 = v36;
    put_XmlText = v36->lpVtbl->put_XmlText;
    bstr = (_QWORD *)wil::make_bstr(
                       &v42,
                       L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\" xmlns:auto-ns1=\"urn:schema"
                        "s-microsoft-com:asm.v3\">\n"
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
        (void *)0xD1,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v20,
        (int)v47);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
    v40 = 0;
    v21 = v36;
    get_Triggers = v36->lpVtbl->get_Triggers;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v40);
    v23 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))get_Triggers)(v21, &v40);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v23,
        (int)v47);
    v39 = 0;
    v24 = v40;
    v25 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v40 + 80LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v39);
    v26 = v25(v24, 9, &v39);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v26,
        (int)v47);
    v41 = 0;
    v27 = Microsoft::WRL::ComPtr<ITrigger>::As<ILogonTrigger>(&v39, &v41);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDA,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v27,
        (int)v47);
    v28 = v41;
    v29 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v41 + 184LL);
    v30 = (_QWORD *)wil::make_bstr(&v42, *((_QWORD *)this + 2));
    v31 = v29(v28, *v30);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDC,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v31,
        (int)v47);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
    v32 = anonymous_namespace_::CreateCommandLine(&v53, *((_QWORD *)this + 1), *((_QWORD *)this + 2), L"Login");
    v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
    anonymous_namespace_::AddCommandLine(v36, v33);
    std::wstring::~wstring(&v53);
    Dynamo::TaskCreator::RegisterTask(this, v37, v36, L"LoginTask");
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v41);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
    if ( (_DWORD)v38 )
      CoUninitialize();
  }
}

```

## disassembly

```asm
0x1800f3c90  mov     rax, rsp
0x1800f3c93  push    rbp
0x1800f3c94  push    rbx
0x1800f3c95  push    rsi
0x1800f3c96  push    rdi
0x1800f3c97  lea     rbp, [rax-0E8h]
0x1800f3c9e  sub     rsp, 1C8h
0x1800f3ca5  movaps  xmmword ptr [rax-38h], xmm6
0x1800f3ca9  movaps  xmmword ptr [rax-48h], xmm7
0x1800f3cad  movaps  xmmword ptr [rax-58h], xmm8
0x1800f3cb2  movaps  xmmword ptr [rax-68h], xmm9
0x1800f3cb7  movaps  xmmword ptr [rax-78h], xmm10
0x1800f3cbc  movaps  xmmword ptr [rax-88h], xmm11
0x1800f3cc4  mov     rax, cs:__security_cookie
0x1800f3ccb  xor     rax, rsp
0x1800f3cce  mov     [rbp+0E0h+var_90], rax
0x1800f3cd2  mov     rsi, rcx
0x1800f3cd5  cmp     qword ptr [rcx+10h], 0
0x1800f3cda  jz      loc_1800F40F1
0x1800f3ce0  mov     dword ptr [rsp+1E0h+var_1A0], 0
0x1800f3ce8  lea     rcx, [rsp+1E0h+var_1A0]; this
0x1800f3ced  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800f3cf2  mov     rcx, [rbp+0E8h]; this
0x1800f3cf9  test    eax, eax
0x1800f3cfb  jns     short loc_1800F3D12
0x1800f3cfd  mov     r9d, eax; char *
0x1800f3d00  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3d07  mov     edx, 0C9h; void *
0x1800f3d0c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3d12  mov     [rsp+1E0h+var_1A8], 0
0x1800f3d1b  lea     rcx, [rsp+1E0h+var_1A8]
0x1800f3d20  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f3d25  lea     rax, [rsp+1E0h+var_1A8]
0x1800f3d2a  mov     qword ptr [rsp+1E0h+ppv], rax; int
0x1800f3d2f  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800f3d36  xor     edx, edx; pUnkOuter
0x1800f3d38  lea     r8d, [rdx+1]; dwClsContext
0x1800f3d3c  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800f3d43  call    cs:__imp_CoCreateInstance
0x1800f3d4a  nop     dword ptr [rax+rax+00h]
0x1800f3d4f  mov     rcx, [rbp+0E8h]; this
0x1800f3d56  test    eax, eax
0x1800f3d58  jns     short loc_1800F3D6F
0x1800f3d5a  mov     r9d, eax; char *
0x1800f3d5d  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3d64  mov     edx, 0CCh; void *
0x1800f3d69  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3d6f  mov     rdi, [rsp+1E0h+var_1A8]
0x1800f3d74  mov     rax, [rdi]
0x1800f3d77  mov     rbx, [rax+50h]
0x1800f3d7b  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x1800f3d7f  call    cs:__imp_VariantInit
0x1800f3d86  nop     dword ptr [rax+rax+00h]
0x1800f3d8b  nop
0x1800f3d8c  movups  xmm10, xmmword ptr [rbp+0E0h+pvarg]
0x1800f3d91  movsd   xmm11, qword ptr [rbp+0E0h+pvarg+10h]
0x1800f3d97  lea     rcx, [rbp+0E0h+var_148]; pvarg
0x1800f3d9b  call    cs:__imp_VariantInit
0x1800f3da2  nop     dword ptr [rax+rax+00h]
0x1800f3da7  nop
0x1800f3da8  movups  xmm8, xmmword ptr [rbp+0E0h+var_148]
0x1800f3dad  movsd   xmm9, qword ptr [rbp+0E0h+var_148+10h]
0x1800f3db3  lea     rcx, [rbp+0E0h+var_160]; pvarg
0x1800f3db7  call    cs:__imp_VariantInit
0x1800f3dbe  nop     dword ptr [rax+rax+00h]
0x1800f3dc3  nop
0x1800f3dc4  movups  xmm6, xmmword ptr [rbp+0E0h+var_160]
0x1800f3dc8  movsd   xmm7, qword ptr [rbp+0E0h+var_160+10h]
0x1800f3dcd  lea     rcx, [rsp+1E0h+var_180+8]; pvarg
0x1800f3dd2  call    cs:__imp_VariantInit
0x1800f3dd9  nop     dword ptr [rax+rax+00h]
0x1800f3dde  nop
0x1800f3ddf  movups  xmm0, xmmword ptr [rsp+1E0h+var_180+8]
0x1800f3de4  movsd   xmm1, [rsp+1E0h+var_168]
0x1800f3dea  movaps  xmmword ptr [rbp+0E0h+var_110], xmm10
0x1800f3def  movsd   [rbp+0E0h+var_100], xmm11
0x1800f3df5  movaps  [rbp+0E0h+var_F0], xmm8
0x1800f3dfa  movsd   [rbp+0E0h+var_E0], xmm9
0x1800f3e00  movaps  [rbp+0E0h+var_D0], xmm6
0x1800f3e04  movsd   [rbp+0E0h+var_C0], xmm7
0x1800f3e09  movaps  [rbp+0E0h+var_B0], xmm0
0x1800f3e0d  movsd   [rbp+0E0h+var_A0], xmm1
0x1800f3e12  lea     rax, [rbp+0E0h+var_110]
0x1800f3e16  mov     qword ptr [rsp+1E0h+ppv], rax; int
0x1800f3e1b  lea     r9, [rbp+0E0h+var_F0]
0x1800f3e1f  lea     r8, [rbp+0E0h+var_D0]
0x1800f3e23  lea     rdx, [rbp+0E0h+var_B0]
0x1800f3e27  mov     rcx, rdi
0x1800f3e2a  mov     rax, rbx
0x1800f3e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3e32  mov     rcx, [rbp+0E8h]; this
0x1800f3e39  test    eax, eax
0x1800f3e3b  jns     short loc_1800F3E52
0x1800f3e3d  mov     r9d, eax; char *
0x1800f3e40  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3e47  mov     edx, 0CDh; void *
0x1800f3e4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3e52  lea     rcx, [rsp+1E0h+var_180+8]; this
0x1800f3e57  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f3e5c  nop
0x1800f3e5d  lea     rcx, [rbp+0E0h+var_160]; this
0x1800f3e61  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f3e66  nop
0x1800f3e67  lea     rcx, [rbp+0E0h+var_148]; this
0x1800f3e6b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f3e70  nop
0x1800f3e71  lea     rcx, [rbp+0E0h+pvarg]; this
0x1800f3e75  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f3e7a  mov     [rsp+1E0h+var_1B0], 0
0x1800f3e83  mov     rdi, [rsp+1E0h+var_1A8]
0x1800f3e88  mov     rax, [rdi]
0x1800f3e8b  mov     rbx, [rax+48h]
0x1800f3e8f  lea     rcx, [rsp+1E0h+var_1B0]
0x1800f3e94  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f3e99  lea     r8, [rsp+1E0h+var_1B0]
0x1800f3e9e  xor     edx, edx
0x1800f3ea0  mov     rcx, rdi
0x1800f3ea3  mov     rax, rbx
0x1800f3ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3eab  mov     rcx, [rbp+0E8h]; this
0x1800f3eb2  test    eax, eax
0x1800f3eb4  jns     short loc_1800F3ECB
0x1800f3eb6  mov     r9d, eax; char *
0x1800f3eb9  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3ec0  mov     edx, 0D0h; void *
0x1800f3ec5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3ecb  mov     rdi, [rsp+1E0h+var_1B0]
0x1800f3ed0  mov     rax, [rdi]
0x1800f3ed3  mov     rbx, [rax+0A0h]
0x1800f3eda  lea     rdx, aTaskXmlnsHttpS; "<Task xmlns=\"http://schemas.microsoft."...
0x1800f3ee1  lea     rcx, [rsp+1E0h+var_180]
0x1800f3ee6  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800f3eeb  nop
0x1800f3eec  mov     rdx, [rax]
0x1800f3eef  mov     rcx, rdi
0x1800f3ef2  mov     rax, rbx
0x1800f3ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3efa  mov     rcx, [rbp+0E8h]; this
0x1800f3f01  test    eax, eax
0x1800f3f03  jns     short loc_1800F3F1A
0x1800f3f05  mov     r9d, eax; char *
0x1800f3f08  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3f0f  mov     edx, 0D1h; void *
0x1800f3f14  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3f1a  lea     rcx, [rsp+1E0h+var_180]
0x1800f3f1f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f3f24  mov     [rsp+1E0h+var_190], 0
0x1800f3f2d  mov     rdi, [rsp+1E0h+var_1B0]
0x1800f3f32  mov     rax, [rdi]
0x1800f3f35  mov     rbx, [rax+48h]
0x1800f3f39  lea     rcx, [rsp+1E0h+var_190]
0x1800f3f3e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f3f43  lea     rdx, [rsp+1E0h+var_190]
0x1800f3f48  mov     rcx, rdi
0x1800f3f4b  mov     rax, rbx
0x1800f3f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3f53  mov     rcx, [rbp+0E8h]; this
0x1800f3f5a  test    eax, eax
0x1800f3f5c  jns     short loc_1800F3F73
0x1800f3f5e  mov     r9d, eax; char *
0x1800f3f61  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3f68  mov     edx, 0D4h; void *
0x1800f3f6d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3f73  mov     [rsp+1E0h+var_198], 0
0x1800f3f7c  mov     rdi, [rsp+1E0h+var_190]
0x1800f3f81  mov     rax, [rdi]
0x1800f3f84  mov     rbx, [rax+50h]
0x1800f3f88  lea     rcx, [rsp+1E0h+var_198]
0x1800f3f8d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f3f92  lea     r8, [rsp+1E0h+var_198]
0x1800f3f97  mov     edx, 9
0x1800f3f9c  mov     rcx, rdi
0x1800f3f9f  mov     rax, rbx
0x1800f3fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3fa7  mov     rcx, [rbp+0E8h]; this
0x1800f3fae  test    eax, eax
0x1800f3fb0  jns     short loc_1800F3FC7
0x1800f3fb2  mov     r9d, eax; char *
0x1800f3fb5  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3fbc  mov     edx, 0D7h; void *
0x1800f3fc1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3fc7  mov     [rsp+1E0h+var_188], 0
0x1800f3fd0  lea     rdx, [rsp+1E0h+var_188]
0x1800f3fd5  lea     rcx, [rsp+1E0h+var_198]
0x1800f3fda  call    ??$As@UILogonTrigger@@@?$ComPtr@UITrigger@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UILogonTrigger@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ITrigger>::As<ILogonTrigger>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ILogonTrigger>>)
0x1800f3fdf  mov     rcx, [rbp+0E8h]; this
0x1800f3fe6  test    eax, eax
0x1800f3fe8  jns     short loc_1800F3FFF
0x1800f3fea  mov     r9d, eax; char *
0x1800f3fed  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3ff4  mov     edx, 0DAh; void *
0x1800f3ff9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3fff  mov     rdi, [rsp+1E0h+var_188]
0x1800f4004  mov     rax, [rdi]
0x1800f4007  mov     rbx, [rax+0B8h]
0x1800f400e  mov     rdx, [rsi+10h]
0x1800f4012  lea     rcx, [rsp+1E0h+var_180]
0x1800f4017  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800f401c  nop
0x1800f401d  mov     rdx, [rax]
0x1800f4020  mov     rcx, rdi
0x1800f4023  mov     rax, rbx
0x1800f4026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f402b  mov     rcx, [rbp+0E8h]; this
0x1800f4032  test    eax, eax
0x1800f4034  jns     short loc_1800F404B
0x1800f4036  mov     r9d, eax; char *
0x1800f4039  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f4040  mov     edx, 0DCh; void *
0x1800f4045  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f404b  lea     rcx, [rsp+1E0h+var_180]
0x1800f4050  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f4055  lea     r9, aLogin; "Login"
0x1800f405c  mov     r8, [rsi+10h]
0x1800f4060  mov     rdx, [rsi+8]
0x1800f4064  lea     rcx, [rbp+0E0h+var_B0]
0x1800f4068  call    _anonymous_namespace___CreateCommandLine
0x1800f406d  nop
0x1800f406e  mov     rcx, rax
0x1800f4071  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f4076  mov     rdx, rax
0x1800f4079  mov     rcx, [rsp+1E0h+var_1B0]
0x1800f407e  call    _anonymous_namespace___AddCommandLine
0x1800f4083  nop
0x1800f4084  lea     rcx, [rbp+0E0h+var_B0]
0x1800f4088  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f408d  lea     r9, aLogintask; "LoginTask"
0x1800f4094  mov     r8, [rsp+1E0h+var_1B0]; struct ITaskDefinition *
0x1800f4099  mov     rdx, [rsp+1E0h+var_1A8]; struct ITaskService *
0x1800f409e  mov     rcx, rsi; this
0x1800f40a1  call    ?RegisterTask@TaskCreator@Dynamo@@AEAAXPEAUITaskService@@PEAUITaskDefinition@@PEBG@Z; Dynamo::TaskCreator::RegisterTask(ITaskService *,ITaskDefinition *,ushort const *)
0x1800f40a6  nop
0x1800f40a7  lea     rcx, [rsp+1E0h+var_188]
0x1800f40ac  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f40b1  nop
0x1800f40b2  lea     rcx, [rsp+1E0h+var_198]
0x1800f40b7  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f40bc  nop
0x1800f40bd  lea     rcx, [rsp+1E0h+var_190]
0x1800f40c2  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f40c7  nop
0x1800f40c8  lea     rcx, [rsp+1E0h+var_1B0]
0x1800f40cd  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f40d2  nop
0x1800f40d3  lea     rcx, [rsp+1E0h+var_1A8]
0x1800f40d8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f40dd  nop
0x1800f40de  cmp     dword ptr [rsp+1E0h+var_1A0], 0
0x1800f40e3  jz      short loc_1800F40F1
0x1800f40e5  call    cs:__imp_CoUninitialize
0x1800f40ec  nop     dword ptr [rax+rax+00h]
0x1800f40f1  mov     rcx, [rbp+0E0h+var_90]
0x1800f40f5  xor     rcx, rsp; StackCookie
0x1800f40f8  call    __security_check_cookie
0x1800f40fd  lea     r11, [rsp+1E0h+var_18]
0x1800f4105  movaps  xmm6, xmmword ptr [r11-18h]
0x1800f410a  movaps  xmm7, xmmword ptr [r11-28h]
0x1800f410f  movaps  xmm8, xmmword ptr [r11-38h]
0x1800f4114  movaps  xmm9, xmmword ptr [r11-48h]
0x1800f4119  movaps  xmm10, xmmword ptr [r11-58h]
0x1800f411e  movaps  xmm11, xmmword ptr [r11-68h]
0x1800f4123  mov     rsp, r11
0x1800f4126  pop     rdi
0x1800f4127  pop     rsi
0x1800f4128  pop     rbx
0x1800f4129  pop     rbp
0x1800f412a  retn
```
