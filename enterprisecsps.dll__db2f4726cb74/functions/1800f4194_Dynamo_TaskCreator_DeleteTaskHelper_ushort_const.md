# Dynamo::TaskCreator::DeleteTaskHelper(ushort const *)

- ea: `0x1800f4194`
- end: `0x1800f445e`
- name: `?DeleteTaskHelper@TaskCreator@Dynamo@@AEAAXPEBG@Z`
- size: `714`
- prototype: `void __fastcall(Dynamo::TaskCreator *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800f4140`
- `0x1800f4160`
- `0x1800f4180`
- `0x1800f4470`

## callees

- `0x18000caf4`
- `0x180023874`
- `0x180025a9c`
- `0x1800639d0`
- `0x1800d7e58`
- `0x1800f4194`
- `0x1800f4494`
- `0x1800f4740`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800f427c`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4299`
- `OLEAUT32!__imp_VariantInit` at `0x1800f42b7`
- `OLEAUT32!__imp_VariantInit` at `0x1800f42d4`
- `OLEAUT32!__imp_VariantInit` at `0x1800f427c`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4299`
- `OLEAUT32!__imp_VariantInit` at `0x1800f42b7`
- `OLEAUT32!__imp_VariantInit` at `0x1800f42d4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800f441b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800f441b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f423e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f423e`

## string_xrefs

- `0x1800f41f5`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f4258`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f4342`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f43e8`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Dynamo::TaskCreator::DeleteTaskHelper(Dynamo::TaskCreator *this, const unsigned __int16 *a2)
{
  int v4; // eax
  HRESULT v5; // eax
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v8; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v10; // xmm8
  IRecordInfo *v11; // xmm9_8
  __int128 v12; // xmm6
  IRecordInfo *v13; // xmm7_8
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, _QWORD); // rbx
  _QWORD *TaskName; // rax
  unsigned int v18; // ebx
  const char *v19; // r9
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v23[8]; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG v24; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG v25; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG v26; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  int v28[4]; // [rsp+A0h] [rbp-60h] BYREF
  IRecordInfo *v29; // [rsp+B0h] [rbp-50h]
  __int128 v30; // [rsp+C0h] [rbp-40h] BYREF
  IRecordInfo *v31; // [rsp+D0h] [rbp-30h]
  __int128 v32; // [rsp+E0h] [rbp-20h] BYREF
  IRecordInfo *v33; // [rsp+F0h] [rbp-10h]
  VARIANTARG v34; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]
  int v36; // [rsp+1B0h] [rbp+B0h] BYREF
  LPVOID v37; // [rsp+1B8h] [rbp+B8h] BYREF

  v36 = 0;
  v4 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v36, (unsigned int)a2);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  v37 = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
  v5 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v37);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v5,
      ppva);
  v6 = v37;
  v7 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v37 + 80LL);
  VariantInit(&pvarg);
  v8 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v26);
  v10 = *(_OWORD *)&v26.vt;
  v11 = v26.pRecInfo;
  VariantInit(&v25);
  v12 = *(_OWORD *)&v25.vt;
  v13 = v25.pRecInfo;
  VariantInit(&v24);
  *(_OWORD *)v28 = v8;
  v29 = pRecInfo;
  v30 = v10;
  v31 = v11;
  v32 = v12;
  v33 = v13;
  v34 = v24;
  v14 = v7(v6, &v34, &v32, &v30);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v14,
      (int)v28);
  _variant_t::~_variant_t((_variant_t *)&v24);
  _variant_t::~_variant_t((_variant_t *)&v25);
  _variant_t::~_variant_t((_variant_t *)&v26);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  anonymous_namespace_::GetTaskFolder(&v22, v37, *((_QWORD *)this + 1));
  v15 = v22;
  v16 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v22 + 120LL);
  TaskName = (_QWORD *)anonymous_namespace_::GetTaskName(v23, *((_QWORD *)this + 2), a2);
  v18 = v16(v15, *TaskName, 0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v23);
  v19 = 0;
  if ( v18 != -2147024894 )
    v19 = (const char *)v18;
  if ( (int)v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x121,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      v19,
      (int)v28);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
  if ( v36 )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800f4194  mov     rax, rsp
0x1800f4197  mov     [rax+8], rbx
0x1800f419b  mov     [rax+10h], rsi
0x1800f419f  push    rbp
0x1800f41a0  push    rdi
0x1800f41a1  push    r14
0x1800f41a3  lea     rbp, [rsp-80h]
0x1800f41a8  sub     rsp, 180h
0x1800f41af  movaps  xmmword ptr [rax-28h], xmm6
0x1800f41b3  movaps  xmmword ptr [rax-38h], xmm7
0x1800f41b7  movaps  xmmword ptr [rax-48h], xmm8
0x1800f41bc  movaps  xmmword ptr [rax-58h], xmm9
0x1800f41c1  movaps  xmmword ptr [rax-68h], xmm10
0x1800f41c6  movaps  xmmword ptr [rax-78h], xmm11
0x1800f41cb  mov     r14, rdx
0x1800f41ce  mov     rsi, rcx
0x1800f41d1  mov     [rbp+90h+arg_10], 0
0x1800f41db  lea     rcx, [rbp+90h+arg_10]; this
0x1800f41e2  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800f41e7  mov     rcx, [rbp+98h]; this
0x1800f41ee  test    eax, eax
0x1800f41f0  jns     short loc_1800F4207
0x1800f41f2  mov     r9d, eax; char *
0x1800f41f5  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f41fc  mov     edx, 118h; void *
0x1800f4201  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f4207  mov     [rbp+90h+arg_18], 0
0x1800f4212  lea     rcx, [rbp+90h+arg_18]
0x1800f4219  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f421e  lea     rax, [rbp+90h+arg_18]
0x1800f4225  mov     qword ptr [rsp+190h+ppv], rax; int
0x1800f422a  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800f4231  xor     edx, edx; pUnkOuter
0x1800f4233  lea     r8d, [rdx+1]; dwClsContext
0x1800f4237  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800f423e  call    cs:__imp_CoCreateInstance
0x1800f4245  nop     dword ptr [rax+rax+00h]
0x1800f424a  mov     rcx, [rbp+98h]; this
0x1800f4251  test    eax, eax
0x1800f4253  jns     short loc_1800F426A
0x1800f4255  mov     r9d, eax; char *
0x1800f4258  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f425f  mov     edx, 11Bh; void *
0x1800f4264  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f426a  mov     rdi, [rbp+90h+arg_18]
0x1800f4271  mov     rax, [rdi]
0x1800f4274  mov     rbx, [rax+50h]
0x1800f4278  lea     rcx, [rbp+90h+pvarg]; pvarg
0x1800f427c  call    cs:__imp_VariantInit
0x1800f4283  nop     dword ptr [rax+rax+00h]
0x1800f4288  nop
0x1800f4289  movups  xmm10, xmmword ptr [rbp+90h+pvarg]
0x1800f428e  movsd   xmm11, qword ptr [rbp+90h+pvarg+10h]
0x1800f4294  lea     rcx, [rsp+190h+var_120]; pvarg
0x1800f4299  call    cs:__imp_VariantInit
0x1800f42a0  nop     dword ptr [rax+rax+00h]
0x1800f42a5  nop
0x1800f42a6  movups  xmm8, xmmword ptr [rsp+190h+var_120]
0x1800f42ac  movsd   xmm9, qword ptr [rbp+90h+var_120+10h]
0x1800f42b2  lea     rcx, [rsp+190h+var_138]; pvarg
0x1800f42b7  call    cs:__imp_VariantInit
0x1800f42be  nop     dword ptr [rax+rax+00h]
0x1800f42c3  nop
0x1800f42c4  movups  xmm6, xmmword ptr [rsp+190h+var_138]
0x1800f42c9  movsd   xmm7, qword ptr [rsp+190h+var_138+10h]
0x1800f42cf  lea     rcx, [rsp+190h+var_150]; pvarg
0x1800f42d4  call    cs:__imp_VariantInit
0x1800f42db  nop     dword ptr [rax+rax+00h]
0x1800f42e0  nop
0x1800f42e1  movups  xmm0, xmmword ptr [rsp+190h+var_150]
0x1800f42e6  movsd   xmm1, qword ptr [rsp+190h+var_150+10h]
0x1800f42ec  movaps  xmmword ptr [rbp+90h+var_F0], xmm10
0x1800f42f1  movsd   [rbp+90h+var_E0], xmm11
0x1800f42f7  movaps  [rbp+90h+var_D0], xmm8
0x1800f42fc  movsd   [rbp+90h+var_C0], xmm9
0x1800f4302  movaps  [rbp+90h+var_B0], xmm6
0x1800f4306  movsd   [rbp+90h+var_A0], xmm7
0x1800f430b  movaps  [rbp+90h+var_90], xmm0
0x1800f430f  movsd   [rbp+90h+var_80], xmm1
0x1800f4314  lea     rax, [rbp+90h+var_F0]
0x1800f4318  mov     qword ptr [rsp+190h+ppv], rax; int
0x1800f431d  lea     r9, [rbp+90h+var_D0]
0x1800f4321  lea     r8, [rbp+90h+var_B0]
0x1800f4325  lea     rdx, [rbp+90h+var_90]
0x1800f4329  mov     rcx, rdi
0x1800f432c  mov     rax, rbx
0x1800f432f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4334  mov     rcx, [rbp+98h]; this
0x1800f433b  test    eax, eax
0x1800f433d  jns     short loc_1800F4354
0x1800f433f  mov     r9d, eax; char *
0x1800f4342  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f4349  mov     edx, 11Ch; void *
0x1800f434e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f4354  lea     rcx, [rsp+190h+var_150]; this
0x1800f4359  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f435e  nop
0x1800f435f  lea     rcx, [rsp+190h+var_138]; this
0x1800f4364  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f4369  nop
0x1800f436a  lea     rcx, [rsp+190h+var_120]; this
0x1800f436f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f4374  nop
0x1800f4375  lea     rcx, [rbp+90h+pvarg]; this
0x1800f4379  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800f437e  mov     r8, [rsi+8]
0x1800f4382  mov     rdx, [rbp+90h+arg_18]
0x1800f4389  lea     rcx, [rsp+190h+var_160]
0x1800f438e  call    _anonymous_namespace___GetTaskFolder
0x1800f4393  nop
0x1800f4394  mov     rdi, [rsp+190h+var_160]
0x1800f4399  mov     rax, [rdi]
0x1800f439c  mov     rbx, [rax+78h]
0x1800f43a0  mov     r8, r14
0x1800f43a3  mov     rdx, [rsi+10h]
0x1800f43a7  lea     rcx, [rsp+190h+var_158]
0x1800f43ac  call    _anonymous_namespace___GetTaskName
0x1800f43b1  nop
0x1800f43b2  xor     r8d, r8d
0x1800f43b5  mov     rdx, [rax]
0x1800f43b8  mov     rcx, rdi
0x1800f43bb  mov     rax, rbx
0x1800f43be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f43c3  mov     ebx, eax
0x1800f43c5  lea     rcx, [rsp+190h+var_158]
0x1800f43ca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f43cf  xor     r9d, r9d
0x1800f43d2  cmp     ebx, 80070002h
0x1800f43d8  cmovnz  r9d, ebx; char *
0x1800f43dc  mov     rcx, [rbp+98h]; this
0x1800f43e3  test    r9d, r9d
0x1800f43e6  jns     short loc_1800F43FA
0x1800f43e8  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f43ef  mov     edx, 121h; void *
0x1800f43f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f43fa  lea     rcx, [rsp+190h+var_160]
0x1800f43ff  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f4404  nop
0x1800f4405  lea     rcx, [rbp+90h+arg_18]
0x1800f440c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f4411  nop
0x1800f4412  cmp     [rbp+90h+arg_10], 0
0x1800f4419  jz      short loc_1800F4427
0x1800f441b  call    cs:__imp_CoUninitialize
0x1800f4422  nop     dword ptr [rax+rax+00h]
0x1800f4427  lea     r11, [rsp+190h+var_10]
0x1800f442f  mov     rbx, [r11+20h]
0x1800f4433  mov     rsi, [r11+28h]
0x1800f4437  movaps  xmm6, xmmword ptr [r11-10h]
0x1800f443c  movaps  xmm7, xmmword ptr [r11-20h]
0x1800f4441  movaps  xmm8, xmmword ptr [r11-30h]
0x1800f4446  movaps  xmm9, xmmword ptr [r11-40h]
0x1800f444b  movaps  xmm10, xmmword ptr [r11-50h]
0x1800f4450  movaps  xmm11, xmmword ptr [r11-60h]
0x1800f4455  mov     rsp, r11
0x1800f4458  pop     r14
0x1800f445a  pop     rdi
0x1800f445b  pop     rbp
0x1800f445c  retn
```
