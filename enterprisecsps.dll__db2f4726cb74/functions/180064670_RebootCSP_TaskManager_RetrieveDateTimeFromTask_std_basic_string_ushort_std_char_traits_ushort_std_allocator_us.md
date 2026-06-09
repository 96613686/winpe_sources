# RebootCSP::TaskManager::RetrieveDateTimeFromTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,RecurrenceFrequency)

- ea: `0x180064670`
- end: `0x180064c1f`
- name: `?RetrieveDateTimeFromTask@TaskManager@RebootCSP@@AEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4RecurrenceFrequency@@@Z`
- size: `1455`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006308c`
- `0x1800631a4`

## callees

- `0x1800091b0`
- `0x18000caf4`
- `0x18000d4d4`
- `0x18002031c`
- `0x180023fa0`
- `0x1800637f4`
- `0x1800639d0`
- `0x1800639f8`
- `0x180064670`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800648e2`
- `OLEAUT32!__imp_SysFreeString` at `0x180064b37`
- `OLEAUT32!__imp_SysFreeString` at `0x180064b58`
- `OLEAUT32!__imp_SysFreeString` at `0x1800648e2`
- `OLEAUT32!__imp_SysFreeString` at `0x180064b37`
- `OLEAUT32!__imp_SysFreeString` at `0x180064b58`
- `OLEAUT32!__imp_VariantInit` at `0x180064714`
- `OLEAUT32!__imp_VariantInit` at `0x180064730`
- `OLEAUT32!__imp_VariantInit` at `0x18006474c`
- `OLEAUT32!__imp_VariantInit` at `0x180064767`
- `OLEAUT32!__imp_VariantInit` at `0x180064714`
- `OLEAUT32!__imp_VariantInit` at `0x180064730`
- `OLEAUT32!__imp_VariantInit` at `0x18006474c`
- `OLEAUT32!__imp_VariantInit` at `0x180064767`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800646e5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800646e5`

## string_xrefs

- `0x1800647fc`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x180064847`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x180064926`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x180064996`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x1800649fc`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x180064b20`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x180064b7d`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall RebootCSP::TaskManager::RetrieveDateTimeFromTask(__int64 a1, __int64 a2, int a3)
{
  HRESULT Instance; // eax
  int v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v12; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v14; // xmm8
  IRecordInfo *v15; // xmm9_8
  __int128 v16; // xmm6
  IRecordInfo *v17; // xmm7_8
  int TaskFolder; // eax
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, _QWORD *, __int64 *); // rdi
  const unsigned __int16 *v21; // rax
  _QWORD *v22; // rdx
  int v23; // edi
  BSTR *v24; // rbx
  BSTR v25; // rcx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64 *); // rbx
  int v31; // eax
  __int64 v32; // rdx
  int i; // esi
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, _QWORD, __int64 *); // rbx
  int v36; // eax
  int v37; // eax
  __int64 v38; // rdx
  int *ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  __int64 v42; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v43; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v44; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+58h] [rbp-B0h] BYREF
  void *Block; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+68h] [rbp-A0h] BYREF
  VARIANTARG v49; // [rsp+70h] [rbp-98h] BYREF
  __int64 v50; // [rsp+88h] [rbp-80h]
  VARIANTARG v51; // [rsp+90h] [rbp-78h] BYREF
  VARIANTARG v52; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-48h] BYREF
  int v54[4]; // [rsp+D8h] [rbp-30h] BYREF
  IRecordInfo *v55; // [rsp+E8h] [rbp-20h]
  __int128 v56; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v57; // [rsp+108h] [rbp+0h]
  __int128 v58; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v59; // [rsp+128h] [rbp+20h]
  __int128 v60; // [rsp+138h] [rbp+30h] BYREF
  __int64 v61; // [rsp+148h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+1F0h] [rbp+E8h]
  int v63; // [rsp+210h] [rbp+108h] BYREF

  *(_QWORD *)&v49.vt = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v49);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)&v49);
  v7 = Instance;
  if ( Instance < 0 )
  {
    v8 = (unsigned int)Instance;
    v9 = 74;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
      (const char *)v8,
      (int)ppv);
    goto LABEL_48;
  }
  v10 = *(_QWORD *)&v49.vt;
  v11 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *))(**(_QWORD **)&v49.vt + 80LL);
  VariantInit(&pvarg);
  v12 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v52);
  v14 = *(_OWORD *)&v52.vt;
  v15 = v52.pRecInfo;
  VariantInit(&v51);
  v16 = *(_OWORD *)&v51.vt;
  v17 = v51.pRecInfo;
  VariantInit((VARIANTARG *)&v49.decVal.8);
  *(_OWORD *)v54 = v12;
  v55 = pRecInfo;
  v56 = v14;
  v57 = v15;
  v58 = v16;
  v59 = v17;
  v60 = *(_OWORD *)&v49.decVal.Lo32;
  v61 = v50;
  ppv = v54;
  v7 = v11(v10, &v60, &v58, &v56);
  _variant_t::~_variant_t((_variant_t *)&v49.decVal.8);
  _variant_t::~_variant_t((_variant_t *)&v51);
  _variant_t::~_variant_t((_variant_t *)&v52);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  if ( v7 < 0 )
  {
    v8 = (unsigned int)v7;
    v9 = 76;
    goto LABEL_5;
  }
  v43 = 0;
  TaskFolder = RebootCSP::TaskManager::GetTaskFolder(a1, (unsigned int)&v49, (unsigned int)&v43, 0, a3);
  v7 = TaskFolder;
  if ( TaskFolder < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
      (const char *)(unsigned int)TaskFolder,
      ppva);
LABEL_8:
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
    goto LABEL_48;
  }
  v42 = 0;
  v19 = v43;
  v20 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)v43 + 104LL);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v42);
  v21 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 192);
  v22 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&Block, v21);
  if ( v22 )
    v22 = (_QWORD *)*v22;
  v23 = v20(v19, v22, &v42);
  v24 = (BSTR *)Block;
  if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v24 )
  {
    if ( *v24 )
    {
      SysFreeString(*v24);
      *v24 = 0;
    }
    v25 = v24[1];
    if ( v25 )
    {
      operator delete(v25);
      v24[1] = 0;
    }
    operator delete(v24);
  }
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
      (const char *)(unsigned int)v23,
      ppva);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
    v7 = v23;
    goto LABEL_48;
  }
  v45 = 0;
  v26 = v42;
  v27 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 152LL);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
  v28 = v27(v26, &v45);
  v7 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
      (const char *)(unsigned int)v28,
      ppva);
LABEL_23:
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v42);
    goto LABEL_8;
  }
  v44 = 0;
  v29 = v45;
  v30 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 72LL);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
  v31 = v30(v29, &v44);
  v7 = v31;
  if ( v31 < 0 )
  {
    v32 = 88;
    goto LABEL_26;
  }
  LODWORD(v48) = 0;
  v31 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 56LL))(v44, &v48);
  v7 = v31;
  if ( v31 < 0 )
  {
    v32 = 91;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
      (const char *)(unsigned int)v31,
      ppva);
LABEL_27:
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
    goto LABEL_23;
  }
  for ( i = 1; ; ++i )
  {
    if ( i > (int)v48 )
    {
      std::wstring::operator=(a2, &Class);
      goto LABEL_47;
    }
    v46 = 0;
    v34 = v44;
    v35 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v44 + 64LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
    v36 = v35(v34, (unsigned int)i, &v46);
    v7 = v36;
    if ( v36 < 0 )
    {
      v38 = 96;
      goto LABEL_44;
    }
    v63 = 0;
    v36 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 56LL))(v46, &v63);
    v7 = v36;
    if ( v36 < 0 )
    {
      v38 = 99;
LABEL_44:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
        (const char *)(unsigned int)v36,
        ppva);
      goto LABEL_45;
    }
    if ( !a3 && v63 == 1 || (unsigned int)(a3 - 1) <= 1 && v63 == 2 )
      break;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
  }
  Block = 0;
  v37 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v46 + 112LL))(v46, &Block);
  v7 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
      (const char *)(unsigned int)v37,
      ppva);
    SysFreeString((BSTR)Block);
LABEL_45:
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
    goto LABEL_27;
  }
  std::wstring::operator=(a2, Block);
  SysFreeString((BSTR)Block);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
LABEL_47:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v42);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
  v7 = 0;
LABEL_48:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v49);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180064670  mov     rax, rsp
0x180064673  push    rbp
0x180064674  push    rbx
0x180064675  push    rsi
0x180064676  push    rdi
0x180064677  push    r14
0x180064679  push    r15
0x18006467b  lea     rbp, [rax-0E8h]
0x180064682  sub     rsp, 1B8h
0x180064689  movaps  xmmword ptr [rax-48h], xmm6
0x18006468d  movaps  xmmword ptr [rax-58h], xmm7
0x180064691  movaps  xmmword ptr [rax-68h], xmm8
0x180064696  movaps  xmmword ptr [rax-78h], xmm9
0x18006469b  movaps  xmmword ptr [rax-88h], xmm10
0x1800646a3  movaps  xmmword ptr [rax-98h], xmm11
0x1800646ab  mov     r14d, r8d
0x1800646ae  mov     r15, rdx
0x1800646b1  mov     rsi, rcx
0x1800646b4  mov     qword ptr [rsp+1E0h+var_178], 0
0x1800646bd  lea     rcx, [rsp+1E0h+var_178]
0x1800646c2  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800646c7  lea     rax, [rsp+1E0h+var_178]
0x1800646cc  mov     [rsp+1E0h+ppv], rax; ppv
0x1800646d1  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800646d8  xor     edx, edx; pUnkOuter
0x1800646da  lea     r8d, [rdx+1]; dwClsContext
0x1800646de  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800646e5  call    cs:__imp_CoCreateInstance
0x1800646ec  nop     dword ptr [rax+rax+00h]
0x1800646f1  mov     ebx, eax
0x1800646f3  test    eax, eax
0x1800646f5  jns     short loc_180064704
0x1800646f7  mov     r9d, eax
0x1800646fa  mov     edx, 4Ah ; 'J'
0x1800646ff  jmp     loc_1800647FC
0x180064704  mov     rdi, qword ptr [rsp+1E0h+var_178]
0x180064709  mov     rax, [rdi]
0x18006470c  mov     rbx, [rax+50h]
0x180064710  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x180064714  call    cs:__imp_VariantInit
0x18006471b  nop     dword ptr [rax+rax+00h]
0x180064720  nop
0x180064721  movups  xmm10, xmmword ptr [rbp+0E0h+pvarg]
0x180064726  movsd   xmm11, qword ptr [rbp+0E0h+pvarg+10h]
0x18006472c  lea     rcx, [rbp+0E0h+var_140]; pvarg
0x180064730  call    cs:__imp_VariantInit
0x180064737  nop     dword ptr [rax+rax+00h]
0x18006473c  nop
0x18006473d  movups  xmm8, xmmword ptr [rbp+0E0h+var_140]
0x180064742  movsd   xmm9, qword ptr [rbp+0E0h+var_140+10h]
0x180064748  lea     rcx, [rbp+0E0h+var_158]; pvarg
0x18006474c  call    cs:__imp_VariantInit
0x180064753  nop     dword ptr [rax+rax+00h]
0x180064758  nop
0x180064759  movups  xmm6, xmmword ptr [rbp+0E0h+var_158]
0x18006475d  movsd   xmm7, qword ptr [rbp+0E0h+var_158+10h]
0x180064762  lea     rcx, [rsp+1E0h+var_178+8]; pvarg
0x180064767  call    cs:__imp_VariantInit
0x18006476e  nop     dword ptr [rax+rax+00h]
0x180064773  nop
0x180064774  movups  xmm0, xmmword ptr [rsp+1E0h+var_178+8]
0x180064779  movsd   xmm1, [rbp+0E0h+var_160]
0x18006477e  movaps  xmmword ptr [rbp+0E0h+var_110], xmm10
0x180064783  movsd   [rbp+0E0h+var_100], xmm11
0x180064789  movaps  [rbp+0E0h+var_F0], xmm8
0x18006478e  movsd   [rbp+0E0h+var_E0], xmm9
0x180064794  movaps  [rbp+0E0h+var_D0], xmm6
0x180064798  movsd   [rbp+0E0h+var_C0], xmm7
0x18006479d  movaps  [rbp+0E0h+var_B0], xmm0
0x1800647a1  movsd   [rbp+0E0h+var_A0], xmm1
0x1800647a6  lea     rax, [rbp+0E0h+var_110]
0x1800647aa  mov     [rsp+1E0h+ppv], rax; int
0x1800647af  lea     r9, [rbp+0E0h+var_F0]
0x1800647b3  lea     r8, [rbp+0E0h+var_D0]
0x1800647b7  lea     rdx, [rbp+0E0h+var_B0]
0x1800647bb  mov     rcx, rdi
0x1800647be  mov     rax, rbx
0x1800647c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800647c6  mov     ebx, eax
0x1800647c8  lea     rcx, [rsp+1E0h+var_178+8]; this
0x1800647cd  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800647d2  nop
0x1800647d3  lea     rcx, [rbp+0E0h+var_158]; this
0x1800647d7  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800647dc  nop
0x1800647dd  lea     rcx, [rbp+0E0h+var_140]; this
0x1800647e1  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800647e6  nop
0x1800647e7  lea     rcx, [rbp+0E0h+pvarg]; this
0x1800647eb  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800647f0  test    ebx, ebx
0x1800647f2  jns     short loc_180064814
0x1800647f4  mov     r9d, ebx; char *
0x1800647f7  mov     edx, 4Ch ; 'L'; void *
0x1800647fc  lea     r8, aOnecoreuapAdmi_58; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180064803  mov     rcx, [rbp+0E8h]; this
0x18006480a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006480f  jmp     loc_180064BE0
0x180064814  mov     [rsp+1E0h+var_1A8], 0
0x18006481d  mov     dword ptr [rsp+1E0h+ppv], r14d; int
0x180064822  xor     r9d, r9d
0x180064825  lea     r8, [rsp+1E0h+var_1A8]
0x18006482a  lea     rdx, [rsp+1E0h+var_178]
0x18006482f  mov     rcx, rsi
0x180064832  call    ?GetTaskFolder@TaskManager@RebootCSP@@AEAAJAEAV?$ComPtr@UITaskService@@@WRL@Microsoft@@AEAV?$ComPtr@UITaskFolder@@@45@_NW4RecurrenceFrequency@@@Z; RebootCSP::TaskManager::GetTaskFolder(Microsoft::WRL::ComPtr<ITaskService> &,Microsoft::WRL::ComPtr<ITaskFolder> &,bool,RecurrenceFrequency)
0x180064837  mov     ebx, eax
0x180064839  test    eax, eax
0x18006483b  jns     short loc_180064868
0x18006483d  mov     rcx, [rbp+0E8h]; this
0x180064844  mov     r9d, eax; char *
0x180064847  lea     r8, aOnecoreuapAdmi_58; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18006484e  mov     edx, 4Fh ; 'O'; void *
0x180064853  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064858  nop
0x180064859  lea     rcx, [rsp+1E0h+var_1A8]
0x18006485e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180064863  jmp     loc_180064BE0
0x180064868  mov     [rsp+1E0h+var_1B0], 0
0x180064871  mov     rbx, [rsp+1E0h+var_1A8]
0x180064876  mov     rax, [rbx]
0x180064879  mov     rdi, [rax+68h]
0x18006487d  lea     rcx, [rsp+1E0h+var_1B0]
0x180064882  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180064887  lea     rcx, [rsi+0C0h]
0x18006488e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180064893  mov     rdx, rax; unsigned __int16 *
0x180064896  lea     rcx, [rsp+1E0h+Block]; this
0x18006489b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800648a0  nop
0x1800648a1  mov     rdx, [rax]
0x1800648a4  test    rdx, rdx
0x1800648a7  jz      short loc_1800648AC
0x1800648a9  mov     rdx, [rdx]
0x1800648ac  lea     r8, [rsp+1E0h+var_1B0]
0x1800648b1  mov     rcx, rbx
0x1800648b4  mov     rax, rdi
0x1800648b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800648bc  mov     edi, eax
0x1800648be  mov     rbx, [rsp+1E0h+Block]
0x1800648c3  test    rbx, rbx
0x1800648c6  jz      short loc_180064918
0x1800648c8  or      ecx, 0FFFFFFFFh
0x1800648cb  lock xadd [rbx+10h], ecx
0x1800648d0  cmp     ecx, 1
0x1800648d3  jnz     short loc_180064918
0x1800648d5  test    rbx, rbx
0x1800648d8  jz      short loc_180064918
0x1800648da  mov     rcx, [rbx]; bstrString
0x1800648dd  test    rcx, rcx
0x1800648e0  jz      short loc_1800648F5
0x1800648e2  call    cs:__imp_SysFreeString
0x1800648e9  nop     dword ptr [rax+rax+00h]
0x1800648ee  mov     qword ptr [rbx], 0
0x1800648f5  mov     rcx, [rbx+8]; Block
0x1800648f9  test    rcx, rcx
0x1800648fc  jz      short loc_18006490B
0x1800648fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180064903  mov     qword ptr [rbx+8], 0
0x18006490b  mov     edx, 18h
0x180064910  mov     rcx, rbx; Block
0x180064913  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180064918  test    edi, edi
0x18006491a  jns     short loc_180064954
0x18006491c  mov     rcx, [rbp+0E8h]; this
0x180064923  mov     r9d, edi; char *
0x180064926  lea     r8, aOnecoreuapAdmi_58; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18006492d  mov     edx, 52h ; 'R'; void *
0x180064932  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064937  nop
0x180064938  lea     rcx, [rsp+1E0h+var_1B0]
0x18006493d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180064942  nop
0x180064943  lea     rcx, [rsp+1E0h+var_1A8]
0x180064948  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18006494d  mov     ebx, edi
0x18006494f  jmp     loc_180064BE0
0x180064954  mov     [rsp+1E0h+var_198], 0
0x18006495d  mov     rdi, [rsp+1E0h+var_1B0]
0x180064962  mov     rax, [rdi]
0x180064965  mov     rbx, [rax+98h]
0x18006496c  lea     rcx, [rsp+1E0h+var_198]
0x180064971  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180064976  lea     rdx, [rsp+1E0h+var_198]
0x18006497b  mov     rcx, rdi
0x18006497e  mov     rax, rbx
0x180064981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064986  mov     ebx, eax
0x180064988  test    eax, eax
0x18006498a  jns     short loc_1800649C2
0x18006498c  mov     rcx, [rbp+0E8h]; this
0x180064993  mov     r9d, eax; char *
0x180064996  lea     r8, aOnecoreuapAdmi_58; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18006499d  mov     edx, 55h ; 'U'; void *
0x1800649a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800649a7  nop
0x1800649a8  lea     rcx, [rsp+1E0h+var_198]
0x1800649ad  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800649b2  nop
0x1800649b3  lea     rcx, [rsp+1E0h+var_1B0]
0x1800649b8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800649bd  jmp     loc_180064859
0x1800649c2  mov     [rsp+1E0h+var_1A0], 0
0x1800649cb  mov     rdi, [rsp+1E0h+var_198]
0x1800649d0  mov     rax, [rdi]
0x1800649d3  mov     rbx, [rax+48h]
0x1800649d7  lea     rcx, [rsp+1E0h+var_1A0]
0x1800649dc  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800649e1  lea     rdx, [rsp+1E0h+var_1A0]
0x1800649e6  mov     rcx, rdi
0x1800649e9  mov     rax, rbx
0x1800649ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800649f1  mov     ebx, eax
0x1800649f3  test    eax, eax
0x1800649f5  jns     short loc_180064A1F
0x1800649f7  mov     edx, 58h ; 'X'; void *
0x1800649fc  lea     r8, aOnecoreuapAdmi_58; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180064a03  mov     r9d, eax; char *
0x180064a06  mov     rcx, [rbp+0E8h]; this
0x180064a0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064a12  nop
0x180064a13  lea     rcx, [rsp+1E0h+var_1A0]
0x180064a18  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180064a1d  jmp     short loc_1800649A8
0x180064a1f  mov     dword ptr [rsp+1E0h+var_180], 0
0x180064a27  mov     rcx, [rsp+1E0h+var_1A0]
0x180064a2c  mov     rax, [rcx]
0x180064a2f  lea     rdx, [rsp+1E0h+var_180]
0x180064a34  mov     rax, [rax+38h]
0x180064a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a3d  mov     ebx, eax
0x180064a3f  test    eax, eax
0x180064a41  jns     short loc_180064A4A
0x180064a43  mov     edx, 5Bh ; '['
0x180064a48  jmp     short loc_1800649FC
0x180064a4a  mov     esi, 1
0x180064a4f  cmp     esi, dword ptr [rsp+1E0h+var_180]
0x180064a53  jg      loc_180064BA3
0x180064a59  mov     [rsp+1E0h+var_190], 0
0x180064a62  mov     rdi, [rsp+1E0h+var_1A0]
0x180064a67  mov     rax, [rdi]
0x180064a6a  mov     rbx, [rax+40h]
0x180064a6e  lea     rcx, [rsp+1E0h+var_190]
0x180064a73  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180064a78  lea     r8, [rsp+1E0h+var_190]
0x180064a7d  mov     edx, esi
0x180064a7f  mov     rcx, rdi
0x180064a82  mov     rax, rbx
0x180064a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a8a  mov     ebx, eax
0x180064a8c  test    eax, eax
0x180064a8e  js      loc_180064B78
0x180064a94  mov     [rbp+0E0h+arg_18], 0
0x180064a9e  mov     rcx, [rsp+1E0h+var_190]
0x180064aa3  mov     rax, [rcx]
0x180064aa6  lea     rdx, [rbp+0E0h+arg_18]
0x180064aad  mov     rax, [rax+38h]
0x180064ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ab6  mov     ebx, eax
0x180064ab8  test    eax, eax
0x180064aba  js      loc_180064B71
0x180064ac0  test    r14d, r14d
0x180064ac3  jnz     short loc_180064ACE
0x180064ac5  cmp     [rbp+0E0h+arg_18], 1
0x180064acc  jz      short loc_180064AF1
0x180064ace  lea     eax, [r14-1]
0x180064ad2  cmp     eax, 1
0x180064ad5  ja      short loc_180064AE0
0x180064ad7  cmp     [rbp+0E0h+arg_18], 2
0x180064ade  jz      short loc_180064AF1
0x180064ae0  lea     rcx, [rsp+1E0h+var_190]
0x180064ae5  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180064aea  inc     esi
0x180064aec  jmp     loc_180064A4F
0x180064af1  mov     [rsp+1E0h+Block], 0
0x180064afa  mov     rcx, [rsp+1E0h+var_190]
0x180064aff  mov     rax, [rcx]
0x180064b02  lea     rdx, [rsp+1E0h+Block]
0x180064b07  mov     rax, [rax+70h]
0x180064b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b10  mov     ebx, eax
0x180064b12  test    eax, eax
0x180064b14  jns     short loc_180064B45
0x180064b16  mov     rcx, [rbp+0E8h]; this
0x180064b1d  mov     r9d, eax; char *
0x180064b20  lea     r8, aOnecoreuapAdmi_58; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180064b27  mov     edx, 6Ah ; 'j'; void *
0x180064b2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064b31  nop
0x180064b32  mov     rcx, [rsp+1E0h+Block]; bstrString
0x180064b37  call    cs:__imp_SysFreeString
0x180064b3e  nop     dword ptr [rax+rax+00h]
0x180064b43  jmp     short loc_180064B94
0x180064b45  mov     rdx, [rsp+1E0h+Block]
0x180064b4a  mov     rcx, r15
0x180064b4d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x180064b52  nop
0x180064b53  mov     rcx, [rsp+1E0h+Block]; bstrString
0x180064b58  call    cs:__imp_SysFreeString
0x180064b5f  nop     dword ptr [rax+rax+00h]
0x180064b64  nop
  ... truncated ...
```
