# Dynamo::TaskCreator::RunAlertTask(void)

- ea: `0x1800f4a10`
- end: `0x1800f4d5e`
- name: `?RunAlertTask@TaskCreator@Dynamo@@UEAAXXZ`
- size: `846`
- prototype: `void __fastcall(Dynamo::TaskCreator *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000caf4`
- `0x180023874`
- `0x180025a9c`
- `0x1800639d0`
- `0x1800d7e58`
- `0x1800f4494`
- `0x1800f4740`
- `0x1800f4a10`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800f4af3`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4b11`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4b2d`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4b47`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4c91`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4af3`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4b11`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4b2d`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4b47`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4c91`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800f4d20`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800f4d20`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f4ab4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f4ab4`

## string_xrefs

- `0x1800f4c29`: `AlertTask`
- `0x1800f4a6b`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f4ace`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f4bb6`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f4c62`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f4cd5`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Dynamo::TaskCreator::RunAlertTask(Dynamo::TaskCreator *this, unsigned int a2)
{
  int v3; // eax
  HRESULT v4; // eax
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v7; // xmm10
  IRecordInfo *v8; // xmm11_8
  __int128 v9; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v11; // xmm6
  IRecordInfo *v12; // xmm7_8
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  _QWORD *TaskName; // rax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, VARIANTARG *, _QWORD); // rbx
  int v20; // eax
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  VARIANTARG pvarg; // [rsp+38h] [rbp-D0h] BYREF
  IRecordInfo *v24; // [rsp+50h] [rbp-B8h]
  char v25[8]; // [rsp+58h] [rbp-B0h] BYREF
  VARIANTARG v26; // [rsp+68h] [rbp-A0h] BYREF
  VARIANTARG v27; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v28; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG v29; // [rsp+B8h] [rbp-50h] BYREF
  int v30[4]; // [rsp+D8h] [rbp-30h] BYREF
  IRecordInfo *v31; // [rsp+E8h] [rbp-20h]
  __int128 v32; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v33; // [rsp+108h] [rbp+0h]
  __int128 v34; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v35; // [rsp+128h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+1B0h] [rbp+A8h]
  int v37; // [rsp+1C0h] [rbp+B8h] BYREF
  LPVOID v38; // [rsp+1C8h] [rbp+C0h] BYREF
  __int64 v39; // [rsp+1D0h] [rbp+C8h] BYREF

  v37 = 0;
  v3 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v37, a2);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v3,
      ppv);
  v38 = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v38);
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v38);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v4,
      ppva);
  v5 = v38;
  v6 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v38 + 80LL);
  VariantInit((VARIANTARG *)&pvarg.decVal.8);
  v7 = *(_OWORD *)&pvarg.decVal.Lo32;
  v8 = v24;
  VariantInit(&v29);
  v9 = *(_OWORD *)&v29.vt;
  pRecInfo = v29.pRecInfo;
  VariantInit(&v28);
  v11 = *(_OWORD *)&v28.vt;
  v12 = v28.pRecInfo;
  VariantInit(&v27);
  *(_OWORD *)v30 = v7;
  v31 = v8;
  v32 = v9;
  v33 = pRecInfo;
  v34 = v11;
  v35 = v12;
  v26 = v27;
  v13 = v6(v5, &v26, &v34, &v32);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v13,
      (int)v30);
  _variant_t::~_variant_t((_variant_t *)&v27);
  _variant_t::~_variant_t((_variant_t *)&v28);
  _variant_t::~_variant_t((_variant_t *)&v29);
  _variant_t::~_variant_t((_variant_t *)&pvarg.decVal.8);
  anonymous_namespace_::GetTaskFolder(&pvarg, v38, *((_QWORD *)this + 1));
  v39 = 0;
  v14 = *(_QWORD *)&pvarg.vt;
  v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)&pvarg.vt + 104LL);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v39);
  TaskName = (_QWORD *)anonymous_namespace_::GetTaskName(v25, *((_QWORD *)this + 2), L"AlertTask");
  v17 = v15(v14, *TaskName, &v39);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x110,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v17,
      (int)v30);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v25);
  v18 = v39;
  v19 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, _QWORD))(*(_QWORD *)v39 + 96LL);
  VariantInit((VARIANTARG *)&pvarg.decVal.8);
  *(_OWORD *)&v26.vt = *(_OWORD *)&pvarg.decVal.Lo32;
  v26.pRecInfo = v24;
  v20 = v19(v18, &v26, 0);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v20,
      (int)v30);
  _variant_t::~_variant_t((_variant_t *)&pvarg.decVal.8);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&pvarg);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v38);
  if ( v37 )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800f4a10  mov     rax, rsp
0x1800f4a13  mov     [rax+8], rbx
0x1800f4a17  push    rbp
0x1800f4a18  push    rsi
0x1800f4a19  push    rdi
0x1800f4a1a  lea     rbp, [rax-0A8h]
0x1800f4a21  sub     rsp, 190h
0x1800f4a28  movaps  xmmword ptr [rax-28h], xmm6
0x1800f4a2c  movaps  xmmword ptr [rax-38h], xmm7
0x1800f4a30  movaps  xmmword ptr [rax-48h], xmm8
0x1800f4a35  movaps  xmmword ptr [rax-58h], xmm9
0x1800f4a3a  movaps  xmmword ptr [rax-68h], xmm10
0x1800f4a3f  movaps  xmmword ptr [rax-78h], xmm11
0x1800f4a44  mov     rsi, rcx
0x1800f4a47  mov     [rbp+0A0h+arg_8], 0
0x1800f4a51  lea     rcx, [rbp+0A0h+arg_8]; this
0x1800f4a58  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800f4a5d  mov     rcx, [rbp+0A8h]; this
0x1800f4a64  test    eax, eax
0x1800f4a66  jns     short loc_1800F4A7D
0x1800f4a68  mov     r9d, eax; char *
0x1800f4a6b  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f4a72  mov     edx, 107h; void *
0x1800f4a77  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f4a7d  mov     [rbp+0A0h+arg_10], 0
0x1800f4a88  lea     rcx, [rbp+0A0h+arg_10]
0x1800f4a8f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f4a94  lea     rax, [rbp+0A0h+arg_10]
0x1800f4a9b  mov     qword ptr [rsp+1A0h+ppv], rax; int
0x1800f4aa0  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800f4aa7  xor     edx, edx; pUnkOuter
0x1800f4aa9  lea     r8d, [rdx+1]; dwClsContext
0x1800f4aad  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800f4ab4  call    cs:__imp_CoCreateInstance
0x1800f4abb  nop     dword ptr [rax+rax+00h]
0x1800f4ac0  mov     rcx, [rbp+0A8h]; this
0x1800f4ac7  test    eax, eax
0x1800f4ac9  jns     short loc_1800F4AE0
0x1800f4acb  mov     r9d, eax; char *
0x1800f4ace  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f4ad5  mov     edx, 10Ah; void *
0x1800f4ada  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f4ae0  mov     rdi, [rbp+0A0h+arg_10]
0x1800f4ae7  mov     rax, [rdi]
0x1800f4aea  mov     rbx, [rax+50h]
0x1800f4aee  lea     rcx, [rsp+1A0h+pvarg+8]; pvarg
0x1800f4af3  call    cs:__imp_VariantInit
0x1800f4afa  nop     dword ptr [rax+rax+00h]
0x1800f4aff  nop
0x1800f4b00  movups  xmm10, xmmword ptr [rsp+1A0h+pvarg+8]
0x1800f4b06  movsd   xmm11, [rsp+1A0h+var_158]
0x1800f4b0d  lea     rcx, [rbp+0A0h+var_F0]; pvarg
0x1800f4b11  call    cs:__imp_VariantInit
0x1800f4b18  nop     dword ptr [rax+rax+00h]
0x1800f4b1d  nop
0x1800f4b1e  movups  xmm8, xmmword ptr [rbp+0A0h+var_F0]
0x1800f4b23  movsd   xmm9, qword ptr [rbp+0A0h+var_F0+10h]
0x1800f4b29  lea     rcx, [rbp+0A0h+var_108]; pvarg
0x1800f4b2d  call    cs:__imp_VariantInit
0x1800f4b34  nop     dword ptr [rax+rax+00h]
0x1800f4b39  nop
0x1800f4b3a  movups  xmm6, xmmword ptr [rbp+0A0h+var_108]
0x1800f4b3e  movsd   xmm7, qword ptr [rbp+0A0h+var_108+10h]
0x1800f4b43  lea     rcx, [rbp+0A0h+var_120]; pvarg
0x1800f4b47  call    cs:__imp_VariantInit
0x1800f4b4e  nop     dword ptr [rax+rax+00h]
0x1800f4b53  nop
0x1800f4b54  movups  xmm0, xmmword ptr [rbp+0A0h+var_120]
0x1800f4b58  movsd   xmm1, qword ptr [rbp+0A0h+var_120+10h]
0x1800f4b5d  movaps  xmmword ptr [rbp+0A0h+var_D0], xmm10
0x1800f4b62  movsd   [rbp+0A0h+var_C0], xmm11
0x1800f4b68  movaps  [rbp+0A0h+var_B0], xmm8
0x1800f4b6d  movsd   [rbp+0A0h+var_A0], xmm9
0x1800f4b73  movaps  [rbp+0A0h+var_90], xmm6
0x1800f4b77  movsd   [rbp+0A0h+var_80], xmm7
0x1800f4b7c  movaps  xmmword ptr [rsp+1A0h+var_148+8], xmm0
0x1800f4b81  movsd   [rsp+1A0h+var_130], xmm1
0x1800f4b87  lea     rax, [rbp+0A0h+var_D0]
0x1800f4b8b  mov     qword ptr [rsp+1A0h+ppv], rax; int
0x1800f4b90  lea     r9, [rbp+0A0h+var_B0]
0x1800f4b94  lea     r8, [rbp+0A0h+var_90]
0x1800f4b98  lea     rdx, [rsp+1A0h+var_148+8]
0x1800f4b9d  mov     rcx, rdi
0x1800f4ba0  mov     rax, rbx
0x1800f4ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4ba8  mov     rcx, [rbp+0A8h]; this
0x1800f4baf  test    eax, eax
0x1800f4bb1  jns     short loc_1800F4BC8
0x1800f4bb3  mov     r9d, eax; char *
0x1800f4bb6  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f4bbd  mov     edx, 10Bh; void *
0x1800f4bc2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f4bc8  lea     rcx, [rbp+0A0h+var_120]; this
0x1800f4bcc  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f4bd1  nop
0x1800f4bd2  lea     rcx, [rbp+0A0h+var_108]; this
0x1800f4bd6  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f4bdb  nop
0x1800f4bdc  lea     rcx, [rbp+0A0h+var_F0]; this
0x1800f4be0  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f4be5  nop
0x1800f4be6  lea     rcx, [rsp+1A0h+pvarg+8]; this
0x1800f4beb  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f4bf0  mov     r8, [rsi+8]
0x1800f4bf4  mov     rdx, [rbp+0A0h+arg_10]
0x1800f4bfb  lea     rcx, [rsp+1A0h+pvarg]
0x1800f4c00  call    _anonymous_namespace___GetTaskFolder
0x1800f4c05  nop
0x1800f4c06  mov     [rbp+0A0h+arg_18], 0
0x1800f4c11  mov     rdi, qword ptr [rsp+1A0h+pvarg]
0x1800f4c16  mov     rax, [rdi]
0x1800f4c19  mov     rbx, [rax+68h]
0x1800f4c1d  lea     rcx, [rbp+0A0h+arg_18]
0x1800f4c24  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f4c29  lea     r8, aAlerttask; "AlertTask"
0x1800f4c30  mov     rdx, [rsi+10h]
0x1800f4c34  lea     rcx, [rsp+1A0h+var_150]
0x1800f4c39  call    _anonymous_namespace___GetTaskName
0x1800f4c3e  nop
0x1800f4c3f  lea     r8, [rbp+0A0h+arg_18]
0x1800f4c46  mov     rdx, [rax]
0x1800f4c49  mov     rcx, rdi
0x1800f4c4c  mov     rax, rbx
0x1800f4c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4c54  mov     rcx, [rbp+0A8h]; this
0x1800f4c5b  test    eax, eax
0x1800f4c5d  jns     short loc_1800F4C74
0x1800f4c5f  mov     r9d, eax; char *
0x1800f4c62  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f4c69  mov     edx, 110h; void *
0x1800f4c6e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f4c74  lea     rcx, [rsp+1A0h+var_150]
0x1800f4c79  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f4c7e  mov     rdi, [rbp+0A0h+arg_18]
0x1800f4c85  mov     rax, [rdi]
0x1800f4c88  mov     rbx, [rax+60h]
0x1800f4c8c  lea     rcx, [rsp+1A0h+pvarg+8]; pvarg
0x1800f4c91  call    cs:__imp_VariantInit
0x1800f4c98  nop     dword ptr [rax+rax+00h]
0x1800f4c9d  nop
0x1800f4c9e  movups  xmm0, xmmword ptr [rsp+1A0h+pvarg+8]
0x1800f4ca3  movaps  xmmword ptr [rsp+1A0h+var_148+8], xmm0
0x1800f4ca8  movsd   xmm1, [rsp+1A0h+var_158]
0x1800f4cae  movsd   [rsp+1A0h+var_130], xmm1
0x1800f4cb4  xor     r8d, r8d
0x1800f4cb7  lea     rdx, [rsp+1A0h+var_148+8]
0x1800f4cbc  mov     rcx, rdi
0x1800f4cbf  mov     rax, rbx
0x1800f4cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4cc7  mov     rcx, [rbp+0A8h]; this
0x1800f4cce  test    eax, eax
0x1800f4cd0  jns     short loc_1800F4CE7
0x1800f4cd2  mov     r9d, eax; char *
0x1800f4cd5  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f4cdc  mov     edx, 112h; void *
0x1800f4ce1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f4ce7  lea     rcx, [rsp+1A0h+pvarg+8]; this
0x1800f4cec  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f4cf1  nop
0x1800f4cf2  lea     rcx, [rbp+0A0h+arg_18]
0x1800f4cf9  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f4cfe  nop
0x1800f4cff  lea     rcx, [rsp+1A0h+pvarg]
0x1800f4d04  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f4d09  nop
0x1800f4d0a  lea     rcx, [rbp+0A0h+arg_10]
0x1800f4d11  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f4d16  nop
0x1800f4d17  cmp     [rbp+0A0h+arg_8], 0
0x1800f4d1e  jz      short loc_1800F4D2C
0x1800f4d20  call    cs:__imp_CoUninitialize
0x1800f4d27  nop     dword ptr [rax+rax+00h]
0x1800f4d2c  lea     r11, [rsp+1A0h+var_10]
0x1800f4d34  mov     rbx, [r11+20h]
0x1800f4d38  movaps  xmm6, xmmword ptr [r11-10h]
0x1800f4d3d  movaps  xmm7, xmmword ptr [r11-20h]
0x1800f4d42  movaps  xmm8, xmmword ptr [r11-30h]
0x1800f4d47  movaps  xmm9, xmmword ptr [r11-40h]
0x1800f4d4c  movaps  xmm10, xmmword ptr [r11-50h]
0x1800f4d51  movaps  xmm11, xmmword ptr [r11-60h]
0x1800f4d56  mov     rsp, r11
0x1800f4d59  pop     rdi
0x1800f4d5a  pop     rsi
0x1800f4d5b  pop     rbp
0x1800f4d5c  retn
```
