# RebootCSP::TaskManager::RegisterTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,RecurrenceFrequency)

- ea: `0x180063d94`
- end: `0x1800645f4`
- name: `?RegisterTask@TaskManager@RebootCSP@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4RecurrenceFrequency@@@Z`
- size: `2144`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800632c4`
- `0x1800633dc`

## callees

- `0x1800091b0`
- `0x18000caf4`
- `0x18000d4d4`
- `0x18002031c`
- `0x1800637f4`
- `0x180063870`
- `0x1800639d0`
- `0x1800639f8`
- `0x180063d94`
- `0x180064c28`
- `0x180064eb8`
- `0x1800652f4`
- `0x180065564`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800640be`
- `OLEAUT32!__imp_SysFreeString` at `0x180064295`
- `OLEAUT32!__imp_SysFreeString` at `0x180064486`
- `OLEAUT32!__imp_SysFreeString` at `0x1800640be`
- `OLEAUT32!__imp_SysFreeString` at `0x180064295`
- `OLEAUT32!__imp_SysFreeString` at `0x180064486`
- `OLEAUT32!__imp_VariantInit` at `0x180063e3f`
- `OLEAUT32!__imp_VariantInit` at `0x180063e5b`
- `OLEAUT32!__imp_VariantInit` at `0x180063e77`
- `OLEAUT32!__imp_VariantInit` at `0x180063e91`
- `OLEAUT32!__imp_VariantInit` at `0x180064383`
- `OLEAUT32!__imp_VariantInit` at `0x18006439d`
- `OLEAUT32!__imp_VariantInit` at `0x1800643b9`
- `OLEAUT32!__imp_VariantInit` at `0x180063e3f`
- `OLEAUT32!__imp_VariantInit` at `0x180063e5b`
- `OLEAUT32!__imp_VariantInit` at `0x180063e77`
- `OLEAUT32!__imp_VariantInit` at `0x180063e91`
- `OLEAUT32!__imp_VariantInit` at `0x180064383`
- `OLEAUT32!__imp_VariantInit` at `0x18006439d`
- `OLEAUT32!__imp_VariantInit` at `0x1800643b9`
- `DMCmnUtils!WriteRebootCSPTaskToRegistry` at `0x18006453d`
- `DMCmnUtils!WriteRebootCSPTaskToRegistry` at `0x18006453d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063e10`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063e10`

## string_xrefs

- `0x180064067`: `Reboot Configuration Service Provider`
- `0x180063f24`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x180063f6b`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x180063fe1`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x18006403b`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x1800640fa`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x1800641d4`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x1800642d1`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x1800644e4`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x180064559`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall RebootCSP::TaskManager::RegisterTask(__int64 a1, __int64 a2, unsigned int a3)
{
  HRESULT v6; // eax
  int v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, VARIANTARG *, __int128 *, int *); // rbx
  __int128 v12; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v14; // xmm8
  IRecordInfo *v15; // xmm9_8
  __int128 v16; // xmm6
  IRecordInfo *v17; // xmm7_8
  int v18; // r9d
  int TaskFolder; // eax
  LPVOID v20; // rdi
  __int64 (__fastcall *v21)(LPVOID, _QWORD, __int64 *); // rbx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64 *); // rbx
  int v25; // eax
  unsigned __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rbx
  __int64 (__fastcall *v29)(__int64, __int64); // rdi
  _bstr_t *v30; // rax
  __int64 v31; // rdx
  int v32; // edi
  BSTR *v33; // rbx
  BSTR v34; // rcx
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, VARIANTARG *); // rbx
  const unsigned __int16 *v37; // rax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, __int64 *); // rbx
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rbx
  __int64 (__fastcall *v43)(__int64, __int64); // rdi
  _bstr_t *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rcx
  BSTR *v47; // rbx
  BSTR v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rbx
  __int64 (__fastcall *v51)(__int64, _QWORD *, __int64, __int64); // r13
  __int128 v52; // xmm6
  IRecordInfo *v53; // xmm7_8
  __int128 v54; // xmm8
  IRecordInfo *v55; // xmm9_8
  __int128 v56; // xmm10
  IRecordInfo *v57; // xmm11_8
  __int64 v58; // rdi
  const unsigned __int16 *v59; // rax
  _QWORD *v60; // rdx
  BSTR *v61; // rbx
  BSTR v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // r10
  int v66; // eax
  int *ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  __int64 v70; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v71; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v72; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v73; // [rsp+70h] [rbp-98h] BYREF
  LPVOID v74; // [rsp+78h] [rbp-90h] BYREF
  void *Block; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v76[2]; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v77; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG v78; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v79; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v81; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v82; // [rsp+118h] [rbp+10h]
  int v83[4]; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v84; // [rsp+138h] [rbp+30h]
  VARIANTARG v85; // [rsp+148h] [rbp+40h] BYREF
  int v86[4]; // [rsp+168h] [rbp+60h] BYREF
  IRecordInfo *v87; // [rsp+178h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+230h] [rbp+128h]

  v74 = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v74);
  v6 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v74);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v10 = v74;
    v11 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, int *))(*(_QWORD *)v74 + 80LL);
    VariantInit(&pvarg);
    v12 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v79);
    v14 = *(_OWORD *)&v79.vt;
    v15 = v79.pRecInfo;
    VariantInit(&v78);
    v16 = *(_OWORD *)&v78.vt;
    v17 = v78.pRecInfo;
    VariantInit(&v85);
    *(_OWORD *)v86 = v12;
    v87 = pRecInfo;
    *(_OWORD *)v83 = v14;
    v84 = v15;
    v81 = v16;
    v82 = v17;
    v77 = v85;
    ppv = v86;
    v7 = v11(v10, &v77, &v81, v83);
    _variant_t::~_variant_t((_variant_t *)&v85);
    _variant_t::~_variant_t((_variant_t *)&v78);
    _variant_t::~_variant_t((_variant_t *)&v79);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    if ( v7 < 0 )
    {
      v8 = (unsigned int)v7;
      v9 = 315;
      goto LABEL_5;
    }
    v71 = 0;
    LOBYTE(v18) = 1;
    TaskFolder = RebootCSP::TaskManager::GetTaskFolder(a1, (unsigned int)&v74, (unsigned int)&v71, v18, a3);
    v7 = TaskFolder;
    if ( TaskFolder < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
        (const char *)(unsigned int)TaskFolder,
        ppva);
LABEL_8:
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v71);
      goto LABEL_81;
    }
    if ( !*(_QWORD *)(a2 + 16) )
    {
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v71);
      v7 = 0;
      goto LABEL_81;
    }
    v70 = 0;
    v20 = v74;
    v21 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v74 + 72LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v70);
    v22 = v21(v20, 0, &v70);
    v7 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14A,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
        (const char *)(unsigned int)v22,
        ppva);
LABEL_13:
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v70);
      goto LABEL_8;
    }
    v72 = 0;
    v23 = v70;
    v24 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v70 + 56LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v72);
    v25 = v24(v23, &v72);
    v7 = v25;
    if ( v25 < 0 )
    {
      v26 = (unsigned int)v25;
      v27 = 333;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
        (const char *)v26,
        ppva);
LABEL_17:
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v72);
      goto LABEL_13;
    }
    v28 = v72;
    v29 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v72 + 80LL);
    v30 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"Reboot Configuration Service Provider");
    if ( *(_QWORD *)v30 )
      v31 = **(_QWORD **)v30;
    else
      v31 = 0;
    v32 = v29(v28, v31);
    v33 = (BSTR *)Block;
    if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v33 )
    {
      if ( *v33 )
      {
        SysFreeString(*v33);
        *v33 = 0;
      }
      v34 = v33[1];
      if ( v34 )
      {
        operator delete(v34);
        v33[1] = 0;
      }
      operator delete(v33);
    }
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
        (const char *)(unsigned int)v32,
        ppva);
LABEL_31:
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v72);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v70);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v71);
      v7 = v32;
      goto LABEL_81;
    }
    v35 = v72;
    v36 = *(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v72 + 176LL);
    v37 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 96);
    v77 = *(VARIANTARG *)_variant_t::_variant_t((_variant_t *)&v81, v37);
    v7 = v36(v35, &v77);
    _variant_t::~_variant_t((_variant_t *)&v81);
    if ( v7 < 0 )
    {
      v26 = (unsigned int)v7;
      v27 = 337;
      goto LABEL_16;
    }
    v73 = 0;
    v38 = v70;
    v39 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v70 + 120LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v73);
    v40 = v39(v38, &v73);
    v7 = v40;
    if ( v40 >= 0 )
    {
      v40 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v73 + 112LL))(v73, 3);
      v7 = v40;
      if ( v40 >= 0 )
      {
        v40 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v73 + 144LL))(v73, 0);
        v7 = v40;
        if ( v40 >= 0 )
        {
          v42 = v73;
          v43 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v73 + 96LL);
          v44 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"S-1-5-18");
          if ( *(_QWORD *)v44 )
            v45 = **(_QWORD **)v44;
          else
            v45 = 0;
          v32 = v43(v42, v45);
          v47 = (BSTR *)Block;
          if ( Block )
          {
            v46 = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)Block + 4);
            if ( !(_DWORD)v46 )
            {
              if ( v47 )
              {
                if ( *v47 )
                {
                  SysFreeString(*v47);
                  *v47 = 0;
                }
                v48 = v47[1];
                if ( v48 )
                {
                  operator delete(v48);
                  v47[1] = 0;
                }
                operator delete(v47);
              }
            }
          }
          if ( v32 >= 0 )
          {
            v40 = RebootCSP::TaskManager::SetTaskSettings(v46, &v70);
            v7 = v40;
            if ( v40 < 0 )
            {
              v41 = 348;
              goto LABEL_36;
            }
            if ( a3 )
            {
              v40 = RebootCSP::TaskManager::SetRecurrentTrigger(v49, &v70, a2, a3);
              v7 = v40;
              if ( v40 < 0 )
              {
                v41 = 352;
                goto LABEL_36;
              }
            }
            else
            {
              v40 = RebootCSP::TaskManager::SetTimeTrigger(v49, &v70, a2);
              v7 = v40;
              if ( v40 < 0 )
              {
                v41 = 356;
                goto LABEL_36;
              }
            }
            v40 = RebootCSP::TaskManager::SetTaskAction(a1, &v70);
            v7 = v40;
            if ( v40 < 0 )
            {
              v41 = 359;
              goto LABEL_36;
            }
            v76[0] = 0;
            v50 = v71;
            v51 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64, __int64))(*(_QWORD *)v71 + 136LL);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v76);
            VariantInit(&v78);
            v52 = *(_OWORD *)&v78.vt;
            v53 = v78.pRecInfo;
            VariantInit(&v79);
            v54 = *(_OWORD *)&v79.vt;
            v55 = v79.pRecInfo;
            VariantInit(&pvarg);
            v56 = *(_OWORD *)&pvarg.vt;
            v57 = pvarg.pRecInfo;
            v58 = v70;
            v59 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 192);
            v60 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&Block, v59);
            if ( v60 )
              v60 = (_QWORD *)*v60;
            *(_OWORD *)&v77.vt = v52;
            v77.pRecInfo = v53;
            v81 = v54;
            v82 = v55;
            *(_OWORD *)v83 = v56;
            v84 = v57;
            v32 = v51(v50, v60, v58, 6);
            v61 = (BSTR *)Block;
            if ( Block )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v61 )
              {
                if ( *v61 )
                {
                  SysFreeString(*v61);
                  *v61 = 0;
                }
                v62 = v61[1];
                if ( v62 )
                {
                  operator delete(v62);
                  v61[1] = 0;
                }
                operator delete(v61);
              }
              Block = 0;
            }
            _variant_t::~_variant_t((_variant_t *)&pvarg);
            _variant_t::~_variant_t((_variant_t *)&v79);
            _variant_t::~_variant_t((_variant_t *)&v78);
            if ( v32 >= 0 )
            {
              std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 64);
              std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 192);
              std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 128);
              v63 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
              v66 = WriteRebootCSPTaskToRegistry(v65, v64, v63);
              v7 = v66;
              if ( v66 >= 0 )
              {
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v76);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v73);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v72);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v70);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v71);
                v7 = 0;
                goto LABEL_81;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x177,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
                (const char *)(unsigned int)v66,
                a3);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v76);
              goto LABEL_37;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x171,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
              (const char *)(unsigned int)v32,
              (int)v83);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v76);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x15A,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
              (const char *)(unsigned int)v32,
              ppva);
          }
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v73);
          goto LABEL_31;
        }
        v41 = 344;
      }
      else
      {
        v41 = 342;
      }
    }
    else
    {
      v41 = 340;
    }
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
      (const char *)(unsigned int)v40,
      ppva);
LABEL_37:
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v73);
    goto LABEL_17;
  }
  v8 = (unsigned int)v6;
  v9 = 313;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
    (const char *)v8,
    (int)ppv);
LABEL_81:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v74);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180063d94  mov     rax, rsp
0x180063d97  push    rbp
0x180063d98  push    rbx
0x180063d99  push    rsi
0x180063d9a  push    rdi
0x180063d9b  push    r12
0x180063d9d  push    r13
0x180063d9f  push    r14
0x180063da1  push    r15
0x180063da3  lea     rbp, [rax-128h]
0x180063daa  sub     rsp, 1E8h
0x180063db1  movaps  xmmword ptr [rax-58h], xmm6
0x180063db5  movaps  xmmword ptr [rax-68h], xmm7
0x180063db9  movaps  xmmword ptr [rax-78h], xmm8
0x180063dbe  movaps  xmmword ptr [rax-88h], xmm9
0x180063dc6  movaps  xmmword ptr [rax-98h], xmm10
0x180063dce  movaps  xmmword ptr [rax-0A8h], xmm11
0x180063dd6  mov     r15d, r8d
0x180063dd9  mov     r14, rdx
0x180063ddc  mov     rsi, rcx
0x180063ddf  xor     r12d, r12d
0x180063de2  mov     [rsp+220h+var_1B0], r12
0x180063de7  lea     rcx, [rsp+220h+var_1B0]
0x180063dec  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180063df1  lea     rax, [rsp+220h+var_1B0]
0x180063df6  mov     [rsp+220h+ppv], rax; ppv
0x180063dfb  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180063e02  xor     edx, edx; pUnkOuter
0x180063e04  lea     r8d, [r12+1]; dwClsContext
0x180063e09  lea     rcx, CLSID_TaskScheduler; rclsid
0x180063e10  call    cs:__imp_CoCreateInstance
0x180063e17  nop     dword ptr [rax+rax+00h]
0x180063e1c  mov     ebx, eax
0x180063e1e  test    eax, eax
0x180063e20  jns     short loc_180063E2F
0x180063e22  mov     r9d, eax
0x180063e25  mov     edx, 139h
0x180063e2a  jmp     loc_180063F24
0x180063e2f  mov     rdi, [rsp+220h+var_1B0]
0x180063e34  mov     rax, [rdi]
0x180063e37  mov     rbx, [rax+50h]
0x180063e3b  lea     rcx, [rbp+120h+pvarg]; pvarg
0x180063e3f  call    cs:__imp_VariantInit
0x180063e46  nop     dword ptr [rax+rax+00h]
0x180063e4b  nop
0x180063e4c  movups  xmm10, xmmword ptr [rbp+120h+pvarg]
0x180063e51  movsd   xmm11, qword ptr [rbp+120h+pvarg+10h]
0x180063e57  lea     rcx, [rbp+120h+var_158]; pvarg
0x180063e5b  call    cs:__imp_VariantInit
0x180063e62  nop     dword ptr [rax+rax+00h]
0x180063e67  nop
0x180063e68  movups  xmm8, xmmword ptr [rbp+120h+var_158]
0x180063e6d  movsd   xmm9, qword ptr [rbp+120h+var_158+10h]
0x180063e73  lea     rcx, [rbp+120h+var_170]; pvarg
0x180063e77  call    cs:__imp_VariantInit
0x180063e7e  nop     dword ptr [rax+rax+00h]
0x180063e83  nop
0x180063e84  movups  xmm6, xmmword ptr [rbp+120h+var_170]
0x180063e88  movsd   xmm7, qword ptr [rbp+120h+var_170+10h]
0x180063e8d  lea     rcx, [rbp+120h+var_E0]; pvarg
0x180063e91  call    cs:__imp_VariantInit
0x180063e98  nop     dword ptr [rax+rax+00h]
0x180063e9d  nop
0x180063e9e  movups  xmm0, xmmword ptr [rbp+120h+var_E0]
0x180063ea2  movsd   xmm1, qword ptr [rbp+120h+var_E0+10h]
0x180063ea7  movaps  xmmword ptr [rbp+120h+var_C0], xmm10
0x180063eac  movsd   [rbp+120h+var_B0], xmm11
0x180063eb2  movaps  xmmword ptr [rbp+120h+var_100], xmm8
0x180063eb7  movsd   [rbp+120h+var_F0], xmm9
0x180063ebd  movaps  [rbp+120h+var_120], xmm6
0x180063ec1  movsd   [rbp+120h+var_110], xmm7
0x180063ec6  movaps  [rbp+120h+var_190], xmm0
0x180063eca  movsd   [rbp+120h+var_180], xmm1
0x180063ecf  lea     rax, [rbp+120h+var_C0]
0x180063ed3  mov     [rsp+220h+ppv], rax; int
0x180063ed8  lea     r9, [rbp+120h+var_100]
0x180063edc  lea     r8, [rbp+120h+var_120]
0x180063ee0  lea     rdx, [rbp+120h+var_190]
0x180063ee4  mov     rcx, rdi
0x180063ee7  mov     rax, rbx
0x180063eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063eef  mov     ebx, eax
0x180063ef1  lea     rcx, [rbp+120h+var_E0]; this
0x180063ef5  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180063efa  nop
0x180063efb  lea     rcx, [rbp+120h+var_170]; this
0x180063eff  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180063f04  nop
0x180063f05  lea     rcx, [rbp+120h+var_158]; this
0x180063f09  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180063f0e  nop
0x180063f0f  lea     rcx, [rbp+120h+pvarg]; this
0x180063f13  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180063f18  test    ebx, ebx
0x180063f1a  jns     short loc_180063F3C
0x180063f1c  mov     r9d, ebx; char *
0x180063f1f  mov     edx, 13Bh; void *
0x180063f24  lea     r8, aOnecoreuapAdmi_58; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180063f2b  mov     rcx, [rbp+128h]; this
0x180063f32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063f37  jmp     loc_1800645B1
0x180063f3c  mov     [rsp+220h+var_1C8], r12
0x180063f41  mov     dword ptr [rsp+220h+ppv], r15d; int
0x180063f46  mov     r9b, 1
0x180063f49  lea     r8, [rsp+220h+var_1C8]
0x180063f4e  lea     rdx, [rsp+220h+var_1B0]
0x180063f53  mov     rcx, rsi
0x180063f56  call    ?GetTaskFolder@TaskManager@RebootCSP@@AEAAJAEAV?$ComPtr@UITaskService@@@WRL@Microsoft@@AEAV?$ComPtr@UITaskFolder@@@45@_NW4RecurrenceFrequency@@@Z; RebootCSP::TaskManager::GetTaskFolder(Microsoft::WRL::ComPtr<ITaskService> &,Microsoft::WRL::ComPtr<ITaskFolder> &,bool,RecurrenceFrequency)
0x180063f5b  mov     ebx, eax
0x180063f5d  test    eax, eax
0x180063f5f  jns     short loc_180063F8C
0x180063f61  mov     rcx, [rbp+128h]; this
0x180063f68  mov     r9d, eax; char *
0x180063f6b  lea     r8, aOnecoreuapAdmi_58; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180063f72  mov     edx, 13Fh; void *
0x180063f77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063f7c  nop
0x180063f7d  lea     rcx, [rsp+220h+var_1C8]
0x180063f82  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180063f87  jmp     loc_1800645B1
0x180063f8c  cmp     [r14+10h], r12
0x180063f90  jnz     short loc_180063FA4
0x180063f92  lea     rcx, [rsp+220h+var_1C8]
0x180063f97  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180063f9c  mov     ebx, r12d
0x180063f9f  jmp     loc_1800645B1
0x180063fa4  mov     [rsp+220h+var_1D0], r12
0x180063fa9  mov     rdi, [rsp+220h+var_1B0]
0x180063fae  mov     rax, [rdi]
0x180063fb1  mov     rbx, [rax+48h]
0x180063fb5  lea     rcx, [rsp+220h+var_1D0]
0x180063fba  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180063fbf  lea     r8, [rsp+220h+var_1D0]
0x180063fc4  xor     edx, edx
0x180063fc6  mov     rcx, rdi
0x180063fc9  mov     rax, rbx
0x180063fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063fd1  mov     ebx, eax
0x180063fd3  test    eax, eax
0x180063fd5  jns     short loc_180064002
0x180063fd7  mov     rcx, [rbp+128h]; this
0x180063fde  mov     r9d, eax; char *
0x180063fe1  lea     r8, aOnecoreuapAdmi_58; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180063fe8  mov     edx, 14Ah; void *
0x180063fed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063ff2  nop
0x180063ff3  lea     rcx, [rsp+220h+var_1D0]
0x180063ff8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180063ffd  jmp     loc_180063F7D
0x180064002  mov     [rsp+220h+var_1C0], r12
0x180064007  mov     rdi, [rsp+220h+var_1D0]
0x18006400c  mov     rax, [rdi]
0x18006400f  mov     rbx, [rax+38h]
0x180064013  lea     rcx, [rsp+220h+var_1C0]
0x180064018  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18006401d  lea     rdx, [rsp+220h+var_1C0]
0x180064022  mov     rcx, rdi
0x180064025  mov     rax, rbx
0x180064028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006402d  mov     ebx, eax
0x18006402f  test    eax, eax
0x180064031  jns     short loc_18006405B
0x180064033  mov     r9d, eax; char *
0x180064036  mov     edx, 14Dh; void *
0x18006403b  lea     r8, aOnecoreuapAdmi_58; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180064042  mov     rcx, [rbp+128h]; this
0x180064049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006404e  nop
0x18006404f  lea     rcx, [rsp+220h+var_1C0]
0x180064054  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180064059  jmp     short loc_180063FF3
0x18006405b  mov     rbx, [rsp+220h+var_1C0]
0x180064060  mov     rax, [rbx]
0x180064063  mov     rdi, [rax+50h]
0x180064067  lea     rdx, aRebootConfigur; "Reboot Configuration Service Provider"
0x18006406e  lea     rcx, [rsp+220h+Block]; this
0x180064073  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180064078  nop
0x180064079  mov     rcx, [rax]
0x18006407c  test    rcx, rcx
0x18006407f  jz      short loc_180064086
0x180064081  mov     rdx, [rcx]
0x180064084  jmp     short loc_180064089
0x180064086  mov     rdx, r12
0x180064089  mov     rcx, rbx
0x18006408c  mov     rax, rdi
0x18006408f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064094  mov     edi, eax
0x180064096  or      r13d, 0FFFFFFFFh
0x18006409a  mov     rbx, [rsp+220h+Block]
0x18006409f  test    rbx, rbx
0x1800640a2  jz      short loc_1800640EC
0x1800640a4  mov     ecx, r13d
0x1800640a7  lock xadd [rbx+10h], ecx
0x1800640ac  add     ecx, r13d
0x1800640af  jnz     short loc_1800640EC
0x1800640b1  test    rbx, rbx
0x1800640b4  jz      short loc_1800640EC
0x1800640b6  mov     rcx, [rbx]; bstrString
0x1800640b9  test    rcx, rcx
0x1800640bc  jz      short loc_1800640CD
0x1800640be  call    cs:__imp_SysFreeString
0x1800640c5  nop     dword ptr [rax+rax+00h]
0x1800640ca  mov     [rbx], r12
0x1800640cd  mov     rcx, [rbx+8]; Block
0x1800640d1  test    rcx, rcx
0x1800640d4  jz      short loc_1800640DF
0x1800640d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800640db  mov     [rbx+8], r12
0x1800640df  mov     edx, 18h
0x1800640e4  mov     rcx, rbx; Block
0x1800640e7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800640ec  test    edi, edi
0x1800640ee  jns     short loc_180064133
0x1800640f0  mov     rcx, [rbp+128h]; this
0x1800640f7  mov     r9d, edi; char *
0x1800640fa  lea     r8, aOnecoreuapAdmi_58; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180064101  mov     edx, 14Fh; void *
0x180064106  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006410b  nop
0x18006410c  lea     rcx, [rsp+220h+var_1C0]
0x180064111  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180064116  nop
0x180064117  lea     rcx, [rsp+220h+var_1D0]
0x18006411c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180064121  nop
0x180064122  lea     rcx, [rsp+220h+var_1C8]
0x180064127  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18006412c  mov     ebx, edi
0x18006412e  jmp     loc_1800645B1
0x180064133  mov     rdi, [rsp+220h+var_1C0]
0x180064138  mov     rax, [rdi]
0x18006413b  mov     rbx, [rax+0B0h]
0x180064142  lea     rcx, [rsi+60h]
0x180064146  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006414b  mov     rdx, rax; unsigned __int16 *
0x18006414e  lea     rcx, [rbp+120h+var_120]; this
0x180064152  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180064157  nop
0x180064158  movups  xmm0, xmmword ptr [rax]
0x18006415b  movaps  [rbp+120h+var_190], xmm0
0x18006415f  movsd   xmm1, qword ptr [rax+10h]
0x180064164  movsd   [rbp+120h+var_180], xmm1
0x180064169  lea     rdx, [rbp+120h+var_190]
0x18006416d  mov     rcx, rdi
0x180064170  mov     rax, rbx
0x180064173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064178  mov     ebx, eax
0x18006417a  lea     rcx, [rbp+120h+var_120]; this
0x18006417e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180064183  test    ebx, ebx
0x180064185  jns     short loc_180064194
0x180064187  mov     r9d, ebx
0x18006418a  mov     edx, 151h
0x18006418f  jmp     loc_18006403B
0x180064194  mov     [rsp+220h+var_1B8], r12
0x180064199  mov     rdi, [rsp+220h+var_1D0]
0x18006419e  mov     rax, [rdi]
0x1800641a1  mov     rbx, [rax+78h]
0x1800641a5  lea     rcx, [rsp+220h+var_1B8]
0x1800641aa  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800641af  lea     rdx, [rsp+220h+var_1B8]
0x1800641b4  mov     rcx, rdi
0x1800641b7  mov     rax, rbx
0x1800641ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800641bf  mov     ebx, eax
0x1800641c1  test    eax, eax
0x1800641c3  jns     short loc_1800641F0
0x1800641c5  mov     edx, 154h; void *
0x1800641ca  mov     rcx, [rbp+128h]; this
0x1800641d1  mov     r9d, eax; char *
0x1800641d4  lea     r8, aOnecoreuapAdmi_58; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800641db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800641e0  nop
0x1800641e1  lea     rcx, [rsp+220h+var_1B8]
0x1800641e6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800641eb  jmp     loc_18006404F
0x1800641f0  mov     rcx, [rsp+220h+var_1B8]
0x1800641f5  mov     rax, [rcx]
0x1800641f8  mov     edx, 3
0x1800641fd  mov     rax, [rax+70h]
0x180064201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064206  mov     ebx, eax
0x180064208  test    eax, eax
0x18006420a  jns     short loc_180064213
0x18006420c  mov     edx, 156h
0x180064211  jmp     short loc_1800641CA
0x180064213  mov     rcx, [rsp+220h+var_1B8]
0x180064218  mov     rax, [rcx]
0x18006421b  xor     edx, edx
0x18006421d  mov     rax, [rax+90h]
0x180064224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064229  mov     ebx, eax
0x18006422b  test    eax, eax
0x18006422d  jns     short loc_180064236
0x18006422f  mov     edx, 158h
0x180064234  jmp     short loc_1800641CA
0x180064236  mov     rbx, [rsp+220h+var_1B8]
0x18006423b  mov     rax, [rbx]
0x18006423e  mov     rdi, [rax+60h]
  ... truncated ...
```
