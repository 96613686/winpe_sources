# Dynamo::TaskCreator::CreateContextTask(_WNF_STATE_NAME const *)

- ea: `0x1800f3900`
- end: `0x1800f3c80`
- name: `?CreateContextTask@TaskCreator@Dynamo@@UEAAXPEBU_WNF_STATE_NAME@@@Z`
- size: `896`
- prototype: `void __fastcall(Dynamo::TaskCreator *__hidden this, const struct _WNF_STATE_NAME *)`
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
- `0x1800f37bc`
- `0x1800f3900`
- `0x1800f482c`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800f3a10`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3a2c`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3a49`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3a66`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3a10`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3a2c`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3a49`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3a66`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800f3c31`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800f3c31`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f39d4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f39d4`

## string_xrefs

- `0x1800f3bfa`: `ContextTask`
- `0x1800f3b6f`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">\n    <RegistrationInfo>\n        <Author>$(@%systemRoot%\system32\deviceenroller.exe,-101)</Author>\n        <Description>$(@%systemRoot%\system32\deviceenroller.exe,-104)</Description>\n        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>\n    </RegistrationInfo>\n    <Principals>\n        <Principal id="LocalSystem">\n            <UserId>S-1-5-18</UserId`
- `0x1800f395f`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3991`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f39ee`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3ad4`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3b4e`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f3b9d`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Dynamo::TaskCreator::CreateContextTask(Dynamo::TaskCreator *this, const struct _WNF_STATE_NAME *a2)
{
  int v4; // eax
  HRESULT Instance; // eax
  struct ITaskService *v6; // rdi
  HRESULT (__stdcall *Connect)(ITaskService *, VARIANT, VARIANT, VARIANT, VARIANT); // rbx
  __int128 v8; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v10; // xmm8
  IRecordInfo *v11; // xmm9_8
  __int128 v12; // xmm6
  __int64 v13; // xmm7_8
  int v14; // eax
  struct ITaskService *v15; // rdi
  HRESULT (__stdcall *NewTask)(ITaskService *, DWORD, ITaskDefinition **); // rbx
  int v17; // eax
  struct ITaskDefinition *v18; // rdi
  HRESULT (__stdcall *put_XmlText)(ITaskDefinition *, BSTR); // rbx
  _QWORD *bstr; // rax
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  struct ITaskDefinition *v26; // [rsp+38h] [rbp-D0h] BYREF
  struct ITaskService *v27; // [rsp+40h] [rbp-C8h] BYREF
  int v28; // [rsp+48h] [rbp-C0h] BYREF
  VARIANTARG v29; // [rsp+50h] [rbp-B8h] BYREF
  VARIANTARG v30; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+80h] [rbp-88h]
  VARIANTARG v32; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-68h] BYREF
  int v34[4]; // [rsp+B8h] [rbp-50h] BYREF
  IRecordInfo *v35; // [rsp+C8h] [rbp-40h]
  __int128 v36; // [rsp+D8h] [rbp-30h] BYREF
  IRecordInfo *v37; // [rsp+E8h] [rbp-20h]
  __int128 v38; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v39; // [rsp+108h] [rbp+0h]
  __int128 v40; // [rsp+118h] [rbp+10h] BYREF
  __int64 v41; // [rsp+128h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+1C0h] [rbp+B8h]

  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)0x80070057LL,
      ppv);
  v28 = 0;
  v4 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v28, (unsigned int)a2);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  v27 = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v27);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)&v27);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  v6 = v27;
  Connect = v27->lpVtbl->Connect;
  VariantInit(&pvarg);
  v8 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v32);
  v10 = *(_OWORD *)&v32.vt;
  v11 = v32.pRecInfo;
  VariantInit((VARIANTARG *)&v30.decVal.8);
  v12 = *(_OWORD *)&v30.decVal.Lo32;
  v13 = v31;
  VariantInit((VARIANTARG *)&v29.decVal.8);
  *(_OWORD *)v34 = v8;
  v35 = pRecInfo;
  v36 = v10;
  v37 = v11;
  v38 = v12;
  v39 = v13;
  v40 = *(_OWORD *)&v29.decVal.Lo32;
  v41 = *(_QWORD *)&v30.vt;
  v14 = ((__int64 (__fastcall *)(struct ITaskService *, __int128 *, __int128 *, __int128 *))Connect)(
          v6,
          &v40,
          &v38,
          &v36);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v14,
      (int)v34);
  _variant_t::~_variant_t((_variant_t *)&v29.decVal.8);
  _variant_t::~_variant_t((_variant_t *)&v30.decVal.8);
  _variant_t::~_variant_t((_variant_t *)&v32);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  v26 = 0;
  v15 = v27;
  NewTask = v27->lpVtbl->NewTask;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v26);
  v17 = ((__int64 (__fastcall *)(struct ITaskService *, _QWORD, struct ITaskDefinition **))NewTask)(v15, 0, &v26);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v17,
      (int)v34);
  v18 = v26;
  put_XmlText = v26->lpVtbl->put_XmlText;
  bstr = (_QWORD *)wil::make_bstr(
                     &v29,
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
  v21 = ((__int64 (__fastcall *)(struct ITaskDefinition *, _QWORD))put_XmlText)(v18, *bstr);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v21,
      (int)v34);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
  anonymous_namespace_::AddWnfTrigger(v26, a2);
  v22 = anonymous_namespace_::CreateCommandLine(&v40, *((_QWORD *)this + 1), *((_QWORD *)this + 2), 0);
  v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
  anonymous_namespace_::AddCommandLine(v26, v23);
  std::wstring::~wstring(&v40);
  Dynamo::TaskCreator::RegisterTask(this, v27, v26, L"ContextTask");
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v27);
  if ( v28 )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800f3900  mov     rax, rsp
0x1800f3903  mov     [rax+18h], rbx
0x1800f3907  mov     [rax+20h], rsi
0x1800f390b  push    rbp
0x1800f390c  push    rdi
0x1800f390d  push    r14
0x1800f390f  lea     rbp, [rax-0B8h]
0x1800f3916  sub     rsp, 1A0h
0x1800f391d  movaps  xmmword ptr [rax-28h], xmm6
0x1800f3921  movaps  xmmword ptr [rax-38h], xmm7
0x1800f3925  movaps  xmmword ptr [rax-48h], xmm8
0x1800f392a  movaps  xmmword ptr [rax-58h], xmm9
0x1800f392f  movaps  xmmword ptr [rax-68h], xmm10
0x1800f3934  movaps  xmmword ptr [rax-78h], xmm11
0x1800f3939  mov     rax, cs:__security_cookie
0x1800f3940  xor     rax, rsp
0x1800f3943  mov     [rbp+0B0h+var_80], rax
0x1800f3947  mov     r14, rdx
0x1800f394a  mov     rsi, rcx
0x1800f394d  mov     rcx, [rbp+0B8h]; this
0x1800f3954  test    rdx, rdx
0x1800f3957  jnz     short loc_1800F3971
0x1800f3959  mov     r9d, 80070057h; char *
0x1800f395f  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3966  mov     edx, 85h; void *
0x1800f396b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3971  mov     [rsp+1B0h+var_170], 0
0x1800f3979  lea     rcx, [rsp+1B0h+var_170]; this
0x1800f397e  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800f3983  mov     rcx, [rbp+0B8h]; this
0x1800f398a  test    eax, eax
0x1800f398c  jns     short loc_1800F39A3
0x1800f398e  mov     r9d, eax; char *
0x1800f3991  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3998  mov     edx, 87h; void *
0x1800f399d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f39a3  mov     [rsp+1B0h+var_178], 0
0x1800f39ac  lea     rcx, [rsp+1B0h+var_178]
0x1800f39b1  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f39b6  lea     rax, [rsp+1B0h+var_178]
0x1800f39bb  mov     qword ptr [rsp+1B0h+ppv], rax; int
0x1800f39c0  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800f39c7  xor     edx, edx; pUnkOuter
0x1800f39c9  lea     r8d, [rdx+1]; dwClsContext
0x1800f39cd  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800f39d4  call    cs:__imp_CoCreateInstance
0x1800f39db  nop     dword ptr [rax+rax+00h]
0x1800f39e0  mov     rcx, [rbp+0B8h]; this
0x1800f39e7  test    eax, eax
0x1800f39e9  jns     short loc_1800F3A00
0x1800f39eb  mov     r9d, eax; char *
0x1800f39ee  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f39f5  mov     edx, 8Ah; void *
0x1800f39fa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3a00  mov     rdi, [rsp+1B0h+var_178]
0x1800f3a05  mov     rax, [rdi]
0x1800f3a08  mov     rbx, [rax+50h]
0x1800f3a0c  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x1800f3a10  call    cs:__imp_VariantInit
0x1800f3a17  nop     dword ptr [rax+rax+00h]
0x1800f3a1c  nop
0x1800f3a1d  movups  xmm10, xmmword ptr [rbp+0B0h+pvarg]
0x1800f3a22  movsd   xmm11, qword ptr [rbp+0B0h+pvarg+10h]
0x1800f3a28  lea     rcx, [rbp+0B0h+var_130]; pvarg
0x1800f3a2c  call    cs:__imp_VariantInit
0x1800f3a33  nop     dword ptr [rax+rax+00h]
0x1800f3a38  nop
0x1800f3a39  movups  xmm8, xmmword ptr [rbp+0B0h+var_130]
0x1800f3a3e  movsd   xmm9, qword ptr [rbp+0B0h+var_130+10h]
0x1800f3a44  lea     rcx, [rsp+1B0h+var_150+8]; pvarg
0x1800f3a49  call    cs:__imp_VariantInit
0x1800f3a50  nop     dword ptr [rax+rax+00h]
0x1800f3a55  nop
0x1800f3a56  movups  xmm6, xmmword ptr [rsp+1B0h+var_150+8]
0x1800f3a5b  movsd   xmm7, [rsp+1B0h+var_138]
0x1800f3a61  lea     rcx, [rsp+1B0h+var_168+8]; pvarg
0x1800f3a66  call    cs:__imp_VariantInit
0x1800f3a6d  nop     dword ptr [rax+rax+00h]
0x1800f3a72  nop
0x1800f3a73  movups  xmm0, xmmword ptr [rsp+1B0h+var_168+8]
0x1800f3a78  movsd   xmm1, qword ptr [rsp+1B0h+var_150]
0x1800f3a7e  movaps  xmmword ptr [rbp+0B0h+var_100], xmm10
0x1800f3a83  movsd   [rbp+0B0h+var_F0], xmm11
0x1800f3a89  movaps  [rbp+0B0h+var_E0], xmm8
0x1800f3a8e  movsd   [rbp+0B0h+var_D0], xmm9
0x1800f3a94  movaps  [rbp+0B0h+var_C0], xmm6
0x1800f3a98  movsd   [rbp+0B0h+var_B0], xmm7
0x1800f3a9d  movaps  [rbp+0B0h+var_A0], xmm0
0x1800f3aa1  movsd   [rbp+0B0h+var_90], xmm1
0x1800f3aa6  lea     rax, [rbp+0B0h+var_100]
0x1800f3aaa  mov     qword ptr [rsp+1B0h+ppv], rax; int
0x1800f3aaf  lea     r9, [rbp+0B0h+var_E0]
0x1800f3ab3  lea     r8, [rbp+0B0h+var_C0]
0x1800f3ab7  lea     rdx, [rbp+0B0h+var_A0]
0x1800f3abb  mov     rcx, rdi
0x1800f3abe  mov     rax, rbx
0x1800f3ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3ac6  mov     rcx, [rbp+0B8h]; this
0x1800f3acd  test    eax, eax
0x1800f3acf  jns     short loc_1800F3AE6
0x1800f3ad1  mov     r9d, eax; char *
0x1800f3ad4  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3adb  mov     edx, 8Bh; void *
0x1800f3ae0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3ae6  lea     rcx, [rsp+1B0h+var_168+8]; this
0x1800f3aeb  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f3af0  nop
0x1800f3af1  lea     rcx, [rsp+1B0h+var_150+8]; this
0x1800f3af6  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f3afb  nop
0x1800f3afc  lea     rcx, [rbp+0B0h+var_130]; this
0x1800f3b00  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f3b05  nop
0x1800f3b06  lea     rcx, [rbp+0B0h+pvarg]; this
0x1800f3b0a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f3b0f  mov     [rsp+1B0h+var_180], 0
0x1800f3b18  mov     rdi, [rsp+1B0h+var_178]
0x1800f3b1d  mov     rax, [rdi]
0x1800f3b20  mov     rbx, [rax+48h]
0x1800f3b24  lea     rcx, [rsp+1B0h+var_180]
0x1800f3b29  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f3b2e  lea     r8, [rsp+1B0h+var_180]
0x1800f3b33  xor     edx, edx
0x1800f3b35  mov     rcx, rdi
0x1800f3b38  mov     rax, rbx
0x1800f3b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3b40  mov     rcx, [rbp+0B8h]; this
0x1800f3b47  test    eax, eax
0x1800f3b49  jns     short loc_1800F3B60
0x1800f3b4b  mov     r9d, eax; char *
0x1800f3b4e  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3b55  mov     edx, 8Eh; void *
0x1800f3b5a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3b60  mov     rdi, [rsp+1B0h+var_180]
0x1800f3b65  mov     rax, [rdi]
0x1800f3b68  mov     rbx, [rax+0A0h]
0x1800f3b6f  lea     rdx, aTaskXmlnsHttpS; "<Task xmlns=\"http://schemas.microsoft."...
0x1800f3b76  lea     rcx, [rsp+1B0h+var_168]
0x1800f3b7b  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800f3b80  nop
0x1800f3b81  mov     rdx, [rax]
0x1800f3b84  mov     rcx, rdi
0x1800f3b87  mov     rax, rbx
0x1800f3b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3b8f  mov     rcx, [rbp+0B8h]; this
0x1800f3b96  test    eax, eax
0x1800f3b98  jns     short loc_1800F3BAF
0x1800f3b9a  mov     r9d, eax; char *
0x1800f3b9d  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f3ba4  mov     edx, 8Fh; void *
0x1800f3ba9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3baf  lea     rcx, [rsp+1B0h+var_168]
0x1800f3bb4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f3bb9  mov     rdx, r14
0x1800f3bbc  mov     rcx, [rsp+1B0h+var_180]
0x1800f3bc1  call    _anonymous_namespace___AddWnfTrigger
0x1800f3bc6  xor     r9d, r9d
0x1800f3bc9  mov     r8, [rsi+10h]
0x1800f3bcd  mov     rdx, [rsi+8]
0x1800f3bd1  lea     rcx, [rbp+0B0h+var_A0]
0x1800f3bd5  call    _anonymous_namespace___CreateCommandLine
0x1800f3bda  nop
0x1800f3bdb  mov     rcx, rax
0x1800f3bde  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f3be3  mov     rdx, rax
0x1800f3be6  mov     rcx, [rsp+1B0h+var_180]
0x1800f3beb  call    _anonymous_namespace___AddCommandLine
0x1800f3bf0  nop
0x1800f3bf1  lea     rcx, [rbp+0B0h+var_A0]
0x1800f3bf5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f3bfa  lea     r9, aContexttask; "ContextTask"
0x1800f3c01  mov     r8, [rsp+1B0h+var_180]; struct ITaskDefinition *
0x1800f3c06  mov     rdx, [rsp+1B0h+var_178]; struct ITaskService *
0x1800f3c0b  mov     rcx, rsi; this
0x1800f3c0e  call    ?RegisterTask@TaskCreator@Dynamo@@AEAAXPEAUITaskService@@PEAUITaskDefinition@@PEBG@Z; Dynamo::TaskCreator::RegisterTask(ITaskService *,ITaskDefinition *,ushort const *)
0x1800f3c13  nop
0x1800f3c14  lea     rcx, [rsp+1B0h+var_180]
0x1800f3c19  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f3c1e  nop
0x1800f3c1f  lea     rcx, [rsp+1B0h+var_178]
0x1800f3c24  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f3c29  nop
0x1800f3c2a  cmp     [rsp+1B0h+var_170], 0
0x1800f3c2f  jz      short loc_1800F3C3D
0x1800f3c31  call    cs:__imp_CoUninitialize
0x1800f3c38  nop     dword ptr [rax+rax+00h]
0x1800f3c3d  mov     rcx, [rbp+0B0h+var_80]
0x1800f3c41  xor     rcx, rsp; StackCookie
0x1800f3c44  call    __security_check_cookie
0x1800f3c49  lea     r11, [rsp+1B0h+var_10]
0x1800f3c51  mov     rbx, [r11+30h]
0x1800f3c55  mov     rsi, [r11+38h]
0x1800f3c59  movaps  xmm6, xmmword ptr [r11-10h]
0x1800f3c5e  movaps  xmm7, xmmword ptr [r11-20h]
0x1800f3c63  movaps  xmm8, xmmword ptr [r11-30h]
0x1800f3c68  movaps  xmm9, xmmword ptr [r11-40h]
0x1800f3c6d  movaps  xmm10, xmmword ptr [r11-50h]
0x1800f3c72  movaps  xmm11, xmmword ptr [r11-60h]
0x1800f3c77  mov     rsp, r11
0x1800f3c7a  pop     r14
0x1800f3c7c  pop     rdi
0x1800f3c7d  pop     rbp
0x1800f3c7e  retn
```
