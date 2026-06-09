# DeclaredConfigurationStore_DeleteScheduledTask(ushort const *,ushort const *)

- ea: `0x1800763f8`
- end: `0x1800768c1`
- name: `?DeclaredConfigurationStore_DeleteScheduledTask@@YAJPEBG0@Z`
- size: `1225`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180067c90`

## callees

- `0x1800067a0`
- `0x18000efc4`
- `0x180011938`
- `0x1800217d8`
- `0x18002e1a0`
- `0x18002e570`
- `0x1800434d0`
- `0x180060974`
- `0x1800763f8`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007646c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007646c`
- `OLEAUT32!__imp_SysFreeString` at `0x180076747`
- `OLEAUT32!__imp_SysFreeString` at `0x180076823`
- `OLEAUT32!__imp_SysFreeString` at `0x180076747`
- `OLEAUT32!__imp_SysFreeString` at `0x180076823`
- `OLEAUT32!__imp_VariantInit` at `0x1800764d1`
- `OLEAUT32!__imp_VariantInit` at `0x1800764f3`
- `OLEAUT32!__imp_VariantInit` at `0x180076512`
- `OLEAUT32!__imp_VariantInit` at `0x180076529`
- `OLEAUT32!__imp_VariantInit` at `0x1800764d1`
- `OLEAUT32!__imp_VariantInit` at `0x1800764f3`
- `OLEAUT32!__imp_VariantInit` at `0x180076512`
- `OLEAUT32!__imp_VariantInit` at `0x180076529`

## string_xrefs

- `0x1800767cd`: `Refresh schedule created by Declared Configuration to refresh any settings changed on the device`
- `0x1800765f2`: `Failed to Connect to TaskService`
- `0x180076788`: `Failed to Get task folder %ws`
- `0x180076480`: `Failed to create instance for CLSID_TaskScheduler`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall DeclaredConfigurationStore_DeleteScheduledTask(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  HRESULT v3; // ebx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v7; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v9; // xmm8
  IRecordInfo *v10; // xmm9_8
  __int128 v11; // xmm6
  IRecordInfo *v12; // xmm7_8
  int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  LPVOID v18; // rbx
  __int64 v19; // rsi
  __int64 *v20; // rax
  __int64 v21; // rdx
  int v22; // esi
  BSTR *v23; // rbx
  BSTR v24; // rcx
  _QWORD *v25; // rbx
  __int64 v26; // rdi
  __int64 *v27; // rax
  __int64 v28; // rdx
  unsigned int v29; // edi
  BSTR *v30; // rbx
  BSTR v31; // rcx
  unsigned int v32; // ebx
  char *v33; // [rsp+28h] [rbp-390h]
  LPVOID ppv; // [rsp+30h] [rbp-388h] BYREF
  _QWORD *v35; // [rsp+38h] [rbp-380h] BYREF
  void *Block; // [rsp+48h] [rbp-370h] BYREF
  VARIANTARG v37; // [rsp+50h] [rbp-368h] BYREF
  VARIANTARG v38; // [rsp+68h] [rbp-350h] BYREF
  VARIANTARG v39; // [rsp+80h] [rbp-338h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-320h] BYREF
  int v41[4]; // [rsp+B0h] [rbp-308h] BYREF
  IRecordInfo *v42; // [rsp+C0h] [rbp-2F8h]
  __int128 v43; // [rsp+D0h] [rbp-2E8h] BYREF
  IRecordInfo *v44; // [rsp+E0h] [rbp-2D8h]
  __int128 v45; // [rsp+F0h] [rbp-2C8h] BYREF
  IRecordInfo *v46; // [rsp+100h] [rbp-2B8h]
  VARIANTARG v47; // [rsp+110h] [rbp-2A8h] BYREF
  unsigned __int16 v48[264]; // [rsp+130h] [rbp-288h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+0h]

  ppv = 0;
  v35 = 0;
  v3 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC6F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)(unsigned int)v3,
      (int)"Failed to create instance for CLSID_TaskScheduler",
      v33);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&v35);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&ppv);
    return (unsigned int)v3;
  }
  v5 = ppv;
  v6 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
  VariantInit(&pvarg);
  v7 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v39);
  v9 = *(_OWORD *)&v39.vt;
  v10 = v39.pRecInfo;
  VariantInit(&v38);
  v11 = *(_OWORD *)&v38.vt;
  v12 = v38.pRecInfo;
  VariantInit(&v37);
  *(_OWORD *)v41 = v7;
  v42 = pRecInfo;
  v43 = v9;
  v44 = v10;
  v45 = v11;
  v46 = v12;
  v47 = v37;
  v13 = v6(v5, &v47, &v45, &v43);
  _variant_t::~_variant_t(&v37);
  _variant_t::~_variant_t(&v38);
  _variant_t::~_variant_t(&v39);
  _variant_t::~_variant_t(&pvarg);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC72,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)(unsigned int)v13,
      (int)"Failed to Connect to TaskService",
      v33);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&v35);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&ppv);
    return (unsigned int)v13;
  }
  if ( a2 )
  {
    v14 = StringCchPrintfW(v48, 0x104u, L"\\Microsoft\\Windows\\EnterpriseMgmt\\%s", a2);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC79,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
        (const char *)(unsigned int)v14,
        (int)v41);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&v35);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&ppv);
      return v15;
    }
  }
  else
  {
    v16 = StringCchPrintfW(v48, 0x104u, L"\\Microsoft\\Windows\\EnterpriseMgmt");
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC7F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
        (const char *)(unsigned int)v16,
        (int)v41);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&v35);
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&ppv);
      return v17;
    }
  }
  v18 = ppv;
  v19 = *(_QWORD *)ppv;
  v20 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&Block, v48);
  if ( v20 )
    v21 = *v20;
  else
    v21 = 0;
  v22 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD **))(v19 + 56))(v18, v21, &v35);
  v23 = (BSTR *)Block;
  if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v23 )
  {
    if ( *v23 )
    {
      SysFreeString(*v23);
      *v23 = 0;
    }
    v24 = v23[1];
    if ( v24 )
    {
      operator delete(v24);
      v23[1] = 0;
    }
    operator delete(v23);
  }
  if ( v22 >= 0 )
  {
    v25 = v35;
    v26 = *v35;
    v27 = *(__int64 **)_bstr_t::_bstr_t(
                         (_bstr_t *)&Block,
                         L"Refresh schedule created by Declared Configuration to refresh any settings changed on the device");
    if ( v27 )
      v28 = *v27;
    else
      v28 = 0;
    v29 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD))(v26 + 120))(v25, v28, 0);
    v30 = (BSTR *)Block;
    if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v30 )
    {
      if ( *v30 )
      {
        SysFreeString(*v30);
        *v30 = 0;
      }
      v31 = v30[1];
      if ( v31 )
      {
        operator delete(v31);
        v30[1] = 0;
      }
      operator delete(v30);
    }
    v32 = 0;
    if ( v29 != -2147024894 )
      v32 = v29;
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&v35);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&ppv);
    return v32;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC83,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)(unsigned int)v22,
      (int)"Failed to Get task folder %ws",
      L"\\Microsoft\\Windows\\EnterpriseMgmt");
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&v35);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&ppv);
    return (unsigned int)v22;
  }
}

```

## disassembly

```asm
0x1800763f8  mov     rax, rsp
0x1800763fb  mov     [rax+8], rbx
0x1800763ff  mov     [rax+18h], rsi
0x180076403  push    rdi
0x180076404  sub     rsp, 3B0h
0x18007640b  movaps  xmmword ptr [rax-18h], xmm6
0x18007640f  movaps  xmmword ptr [rax-28h], xmm7
0x180076413  movaps  xmmword ptr [rax-38h], xmm8
0x180076418  movaps  xmmword ptr [rax-48h], xmm9
0x18007641d  movaps  xmmword ptr [rax-58h], xmm10
0x180076422  movaps  xmmword ptr [rax-68h], xmm11
0x180076427  mov     rax, cs:__security_cookie
0x18007642e  xor     rax, rsp
0x180076431  mov     [rsp+3B8h+var_78], rax
0x180076439  mov     rsi, rdx
0x18007643c  mov     [rsp+3B8h+var_388], 0
0x180076445  mov     [rsp+3B8h+var_380], 0
0x18007644e  lea     rax, [rsp+3B8h+var_388]
0x180076453  mov     [rsp+3B8h+ppv], rax; ppv
0x180076458  lea     r9, IID_ITaskService; riid
0x18007645f  xor     edx, edx; pUnkOuter
0x180076461  lea     r8d, [rdx+1]; dwClsContext
0x180076465  lea     rcx, CLSID_TaskScheduler; rclsid
0x18007646c  call    cs:__imp_CoCreateInstance
0x180076472  mov     ebx, eax
0x180076474  test    eax, eax
0x180076476  jns     short loc_1800764BD
0x180076478  mov     rcx, [rsp+3B8h]; this
0x180076480  lea     rax, aFailedToCreate; "Failed to create instance for CLSID_Tas"...
0x180076487  mov     [rsp+3B8h+ppv], rax; int
0x18007648c  mov     r9d, ebx; char *
0x18007648f  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x180076496  mov     edx, 0C6Fh; void *
0x18007649b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800764a0  nop
0x1800764a1  lea     rcx, [rsp+3B8h+var_380]
0x1800764a6  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800764ab  nop
0x1800764ac  lea     rcx, [rsp+3B8h+var_388]
0x1800764b1  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800764b6  mov     eax, ebx
0x1800764b8  jmp     loc_18007687D
0x1800764bd  mov     rdi, [rsp+3B8h+var_388]
0x1800764c2  mov     rax, [rdi]
0x1800764c5  mov     rbx, [rax+50h]
0x1800764c9  lea     rcx, [rsp+3B8h+pvarg]; pvarg
0x1800764d1  call    cs:__imp_VariantInit
0x1800764d7  nop
0x1800764d8  movups  xmm10, xmmword ptr [rsp+3B8h+pvarg]
0x1800764e1  movsd   xmm11, qword ptr [rsp+3B8h+pvarg+10h]
0x1800764eb  lea     rcx, [rsp+3B8h+var_338]; pvarg
0x1800764f3  call    cs:__imp_VariantInit
0x1800764f9  nop
0x1800764fa  movups  xmm8, xmmword ptr [rsp+3B8h+var_338]
0x180076503  movsd   xmm9, qword ptr [rsp+3B8h+var_338+10h]
0x18007650d  lea     rcx, [rsp+3B8h+var_350]; pvarg
0x180076512  call    cs:__imp_VariantInit
0x180076518  nop
0x180076519  movups  xmm6, xmmword ptr [rsp+3B8h+var_350]
0x18007651e  movsd   xmm7, qword ptr [rsp+3B8h+var_350+10h]
0x180076524  lea     rcx, [rsp+3B8h+var_368]; pvarg
0x180076529  call    cs:__imp_VariantInit
0x18007652f  nop
0x180076530  movups  xmm0, xmmword ptr [rsp+3B8h+var_368]
0x180076535  movsd   xmm1, qword ptr [rsp+3B8h+var_368+10h]
0x18007653b  movaps  xmmword ptr [rsp+3B8h+var_308], xmm10
0x180076544  movsd   [rsp+3B8h+var_2F8], xmm11
0x18007654e  movaps  [rsp+3B8h+var_2E8], xmm8
0x180076557  movsd   [rsp+3B8h+var_2D8], xmm9
0x180076561  movaps  [rsp+3B8h+var_2C8], xmm6
0x180076569  movsd   [rsp+3B8h+var_2B8], xmm7
0x180076572  movaps  [rsp+3B8h+var_2A8], xmm0
0x18007657a  movsd   [rsp+3B8h+var_298], xmm1
0x180076583  lea     rax, [rsp+3B8h+var_308]
0x18007658b  mov     [rsp+3B8h+ppv], rax; int
0x180076590  lea     r9, [rsp+3B8h+var_2E8]
0x180076598  lea     r8, [rsp+3B8h+var_2C8]
0x1800765a0  lea     rdx, [rsp+3B8h+var_2A8]
0x1800765a8  mov     rcx, rdi
0x1800765ab  mov     rax, rbx
0x1800765ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800765b3  mov     ebx, eax
0x1800765b5  lea     rcx, [rsp+3B8h+var_368]; this
0x1800765ba  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800765bf  nop
0x1800765c0  lea     rcx, [rsp+3B8h+var_350]; this
0x1800765c5  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800765ca  nop
0x1800765cb  lea     rcx, [rsp+3B8h+var_338]; this
0x1800765d3  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800765d8  nop
0x1800765d9  lea     rcx, [rsp+3B8h+pvarg]; this
0x1800765e1  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800765e6  test    ebx, ebx
0x1800765e8  jns     short loc_18007662F
0x1800765ea  mov     rcx, [rsp+3B8h]; this
0x1800765f2  lea     rax, aFailedToConnec; "Failed to Connect to TaskService"
0x1800765f9  mov     [rsp+3B8h+ppv], rax; int
0x1800765fe  mov     r9d, ebx; char *
0x180076601  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x180076608  mov     edx, 0C72h; void *
0x18007660d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180076612  nop
0x180076613  lea     rcx, [rsp+3B8h+var_380]
0x180076618  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18007661d  nop
0x18007661e  lea     rcx, [rsp+3B8h+var_388]
0x180076623  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180076628  mov     eax, ebx
0x18007662a  jmp     loc_18007687D
0x18007662f  mov     edx, 104h; unsigned __int64
0x180076634  lea     rcx, [rsp+3B8h+var_288]; unsigned __int16 *
0x18007663c  test    rsi, rsi
0x18007663f  jz      short loc_180076698
0x180076641  mov     r9, rsi
0x180076644  lea     r8, aMicrosoftWindo_2; "\\Microsoft\\Windows\\EnterpriseMgmt\\%"...
0x18007664b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180076650  mov     ebx, eax
0x180076652  test    eax, eax
0x180076654  jns     short loc_18007668F
0x180076656  mov     rcx, [rsp+3B8h]; this
0x18007665e  mov     r9d, eax; char *
0x180076661  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x180076668  mov     edx, 0C79h; void *
0x18007666d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076672  nop
0x180076673  lea     rcx, [rsp+3B8h+var_380]
0x180076678  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18007667d  nop
0x18007667e  lea     rcx, [rsp+3B8h+var_388]
0x180076683  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180076688  mov     eax, ebx
0x18007668a  jmp     loc_18007687D
0x18007668f  lea     rdi, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180076696  jmp     short loc_1800766E6
0x180076698  lea     rdi, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x18007669f  mov     r8, rdi; unsigned __int16 *
0x1800766a2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800766a7  mov     ebx, eax
0x1800766a9  test    eax, eax
0x1800766ab  jns     short loc_1800766E6
0x1800766ad  mov     rcx, [rsp+3B8h]; this
0x1800766b5  mov     r9d, eax; char *
0x1800766b8  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x1800766bf  mov     edx, 0C7Fh; void *
0x1800766c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800766c9  nop
0x1800766ca  lea     rcx, [rsp+3B8h+var_380]
0x1800766cf  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800766d4  nop
0x1800766d5  lea     rcx, [rsp+3B8h+var_388]
0x1800766da  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800766df  mov     eax, ebx
0x1800766e1  jmp     loc_18007687D
0x1800766e6  mov     rbx, [rsp+3B8h+var_388]
0x1800766eb  mov     rsi, [rbx]
0x1800766ee  lea     rdx, [rsp+3B8h+var_288]; unsigned __int16 *
0x1800766f6  lea     rcx, [rsp+3B8h+Block]; this
0x1800766fb  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180076700  nop
0x180076701  mov     rax, [rax]
0x180076704  test    rax, rax
0x180076707  jz      short loc_18007670E
0x180076709  mov     rdx, [rax]
0x18007670c  jmp     short loc_180076710
0x18007670e  xor     edx, edx
0x180076710  lea     r8, [rsp+3B8h+var_380]
0x180076715  mov     rcx, rbx
0x180076718  mov     rax, [rsi+38h]
0x18007671c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076721  mov     esi, eax
0x180076723  mov     rbx, [rsp+3B8h+Block]
0x180076728  test    rbx, rbx
0x18007672b  jz      short loc_180076777
0x18007672d  or      ecx, 0FFFFFFFFh
0x180076730  lock xadd [rbx+10h], ecx
0x180076735  cmp     ecx, 1
0x180076738  jnz     short loc_180076777
0x18007673a  test    rbx, rbx
0x18007673d  jz      short loc_180076777
0x18007673f  mov     rcx, [rbx]; bstrString
0x180076742  test    rcx, rcx
0x180076745  jz      short loc_180076754
0x180076747  call    cs:__imp_SysFreeString
0x18007674d  mov     qword ptr [rbx], 0
0x180076754  mov     rcx, [rbx+8]; Block
0x180076758  test    rcx, rcx
0x18007675b  jz      short loc_18007676A
0x18007675d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180076762  mov     qword ptr [rbx+8], 0
0x18007676a  mov     edx, 18h
0x18007676f  mov     rcx, rbx; Block
0x180076772  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180076777  test    esi, esi
0x180076779  jns     short loc_1800767C5
0x18007677b  mov     rcx, [rsp+3B8h]; this
0x180076783  mov     [rsp+3B8h+var_390], rdi; char *
0x180076788  lea     rax, aFailedToGetTas; "Failed to Get task folder %ws"
0x18007678f  mov     [rsp+3B8h+ppv], rax; int
0x180076794  mov     r9d, esi; char *
0x180076797  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x18007679e  mov     edx, 0C83h; void *
0x1800767a3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800767a8  nop
0x1800767a9  lea     rcx, [rsp+3B8h+var_380]
0x1800767ae  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800767b3  nop
0x1800767b4  lea     rcx, [rsp+3B8h+var_388]
0x1800767b9  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800767be  mov     eax, esi
0x1800767c0  jmp     loc_18007687D
0x1800767c5  mov     rbx, [rsp+3B8h+var_380]
0x1800767ca  mov     rdi, [rbx]
0x1800767cd  lea     rdx, aRefreshSchedul; "Refresh schedule created by Declared Co"...
0x1800767d4  lea     rcx, [rsp+3B8h+Block]; this
0x1800767d9  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800767de  nop
0x1800767df  mov     rax, [rax]
0x1800767e2  test    rax, rax
0x1800767e5  jz      short loc_1800767EC
0x1800767e7  mov     rdx, [rax]
0x1800767ea  jmp     short loc_1800767EE
0x1800767ec  xor     edx, edx
0x1800767ee  xor     r8d, r8d
0x1800767f1  mov     rcx, rbx
0x1800767f4  mov     rax, [rdi+78h]
0x1800767f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800767fd  mov     edi, eax
0x1800767ff  mov     rbx, [rsp+3B8h+Block]
0x180076804  test    rbx, rbx
0x180076807  jz      short loc_180076854
0x180076809  or      ecx, 0FFFFFFFFh
0x18007680c  lock xadd [rbx+10h], ecx
0x180076811  cmp     ecx, 1
0x180076814  jnz     short loc_180076854
0x180076816  test    rbx, rbx
0x180076819  jz      short loc_180076854
0x18007681b  mov     rcx, [rbx]; bstrString
0x18007681e  test    rcx, rcx
0x180076821  jz      short loc_180076830
0x180076823  call    cs:__imp_SysFreeString
0x180076829  mov     qword ptr [rbx], 0
0x180076830  mov     rcx, [rbx+8]; Block
0x180076834  test    rcx, rcx
0x180076837  jz      short loc_180076846
0x180076839  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007683e  mov     qword ptr [rbx+8], 0
0x180076846  mov     edx, 18h
0x18007684b  mov     rcx, rbx; Block
0x18007684e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180076853  nop
0x180076854  xor     ebx, ebx
0x180076856  cmp     edi, 80070002h
0x18007685c  cmovnz  ebx, edi
0x18007685f  lea     rcx, [rsp+3B8h+var_380]
0x180076864  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180076869  nop
0x18007686a  lea     rcx, [rsp+3B8h+var_388]
0x18007686f  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180076874  nop
0x180076875  jmp     short loc_18007687B
0x180076877  mov     ebx, [rsp+3B8h+var_378]
0x18007687b  mov     eax, ebx
0x18007687d  mov     rcx, [rsp+3B8h+var_78]
0x180076885  xor     rcx, rsp; StackCookie
0x180076888  call    __security_check_cookie
0x18007688d  lea     r11, [rsp+3B8h+var_8]
0x180076895  mov     rbx, [r11+10h]
0x180076899  mov     rsi, [r11+20h]
0x18007689d  movaps  xmm6, xmmword ptr [r11-10h]
0x1800768a2  movaps  xmm7, xmmword ptr [r11-20h]
0x1800768a7  movaps  xmm8, xmmword ptr [r11-30h]
0x1800768ac  movaps  xmm9, xmmword ptr [r11-40h]
0x1800768b1  movaps  xmm10, xmmword ptr [r11-50h]
0x1800768b6  movaps  xmm11, xmmword ptr [r11-60h]
0x1800768bb  mov     rsp, r11
0x1800768be  pop     rdi
0x1800768bf  retn
```
