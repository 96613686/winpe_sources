# Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetScheduleData(void)

- ea: `0x180118e40`
- end: `0x1801193d0`
- name: `?GetScheduleData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ`
- size: `1424`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801184c0`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x180118264`
- `0x180118444`
- `0x180118554`
- `0x180118e40`
- `0x1801194b0`
- `0x180119524`
- `0x180119600`
- `0x180193010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180118f3f`
- `OLEAUT32!__imp_VariantInit` at `0x180118f5b`
- `OLEAUT32!__imp_VariantInit` at `0x180118f77`
- `OLEAUT32!__imp_VariantInit` at `0x180118f92`
- `OLEAUT32!__imp_VariantInit` at `0x180118f3f`
- `OLEAUT32!__imp_VariantInit` at `0x180118f5b`
- `OLEAUT32!__imp_VariantInit` at `0x180118f77`
- `OLEAUT32!__imp_VariantInit` at `0x180118f92`
- `OLEAUT32!__imp_VariantClear` at `0x180118ffb`
- `OLEAUT32!__imp_VariantClear` at `0x18011900c`
- `OLEAUT32!__imp_VariantClear` at `0x18011901d`
- `OLEAUT32!__imp_VariantClear` at `0x18011902e`
- `OLEAUT32!__imp_VariantClear` at `0x180119234`
- `OLEAUT32!__imp_VariantClear` at `0x180118ffb`
- `OLEAUT32!__imp_VariantClear` at `0x18011900c`
- `OLEAUT32!__imp_VariantClear` at `0x18011901d`
- `OLEAUT32!__imp_VariantClear` at `0x18011902e`
- `OLEAUT32!__imp_VariantClear` at `0x180119234`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180118efe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180118efe`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180118eb8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180118eb8`

## string_xrefs

- `0x180118e95`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`
- `0x180118f1e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`
- `0x1801190b9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`
- `0x180119159`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`
- `0x18011931f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`
- `0x180119344`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetScheduleData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource *this)
{
  int v2; // eax
  int v3; // ebx
  HRESULT v4; // eax
  __int64 v5; // rdx
  unsigned __int64 v6; // r9
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, _QWORD *, __int128 *, __int128 *); // rbx
  __int128 v9; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v11; // xmm8
  IRecordInfo *v12; // xmm9_8
  __int128 v13; // xmm6
  IRecordInfo *v14; // xmm7_8
  LPVOID v15; // rbx
  __int64 (__fastcall *v16)(LPVOID, _QWORD *, __int64 *); // rdi
  const unsigned __int16 *v17; // rdx
  _QWORD *v18; // rdx
  __int64 v19; // rdi
  int (__fastcall *v20)(__int64, const wchar_t *, __int64 *); // rbx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, __int64 **); // rbx
  int v23; // eax
  __int64 v24; // rdx
  int v25; // r14d
  __int64 *v26; // rdi
  __int64 v27; // rbx
  __int64 v28; // rdi
  int (__fastcall *v29)(__int64, const wchar_t *, VARIANTARG *); // rbx
  int v30; // eax
  __int64 v31; // rdx
  int *ppv; // [rsp+28h] [rbp-E0h]
  __int64 v34; // [rsp+38h] [rbp-D0h] BYREF
  __int64 *v35; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID v37; // [rsp+50h] [rbp-B8h] BYREF
  VARIANTARG v38; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v39[3]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v40; // [rsp+88h] [rbp-80h]
  VARIANTARG v41; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG v42; // [rsp+B0h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+C8h] [rbp-40h] BYREF
  int v44[4]; // [rsp+E8h] [rbp-20h] BYREF
  IRecordInfo *v45; // [rsp+F8h] [rbp-10h]
  __int128 v46; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v47; // [rsp+118h] [rbp+10h]
  __int128 v48; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v49; // [rsp+138h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]
  _bstr_t::Data_t *v51; // [rsp+1E0h] [rbp+D8h] BYREF
  __int64 v52; // [rsp+1E8h] [rbp+E0h]
  __int64 v53; // [rsp+1F0h] [rbp+E8h] BYREF

  v2 = Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteStartElement(this, L"Schedules");
  v3 = v2;
  if ( v2 >= 0 )
  {
    v37 = 0;
    v4 = CoInitializeEx(0, 0);
    v3 = v4;
    if ( v4 < 0 )
    {
      v5 = 124;
LABEL_7:
      v6 = (unsigned int)v4;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\schedulesdiagdata.cpp",
        (const char *)v6,
        (int)ppv);
LABEL_43:
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
      return (unsigned int)v3;
    }
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
    v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v37);
    v3 = v4;
    if ( v4 < 0 )
    {
      v5 = 127;
      goto LABEL_7;
    }
    v7 = v37;
    v8 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int128 *, __int128 *))(*(_QWORD *)v37 + 80LL);
    VariantInit(&pvarg);
    v9 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v42);
    v11 = *(_OWORD *)&v42.vt;
    v12 = v42.pRecInfo;
    VariantInit(&v41);
    v13 = *(_OWORD *)&v41.vt;
    v14 = v41.pRecInfo;
    VariantInit((VARIANTARG *)&v38.decVal.8);
    *(_OWORD *)v44 = v9;
    v45 = pRecInfo;
    v46 = v11;
    v47 = v12;
    v48 = v13;
    v49 = v14;
    *(_OWORD *)&v39[1] = *(_OWORD *)&v38.decVal.Lo32;
    v40 = v39[0];
    ppv = v44;
    v3 = v8(v7, &v39[1], &v48, &v46);
    VariantClear((VARIANTARG *)&v38.decVal.8);
    VariantClear(&v41);
    VariantClear(&v42);
    VariantClear(&pvarg);
    if ( v3 < 0 )
    {
      v6 = (unsigned int)v3;
      v5 = 129;
      goto LABEL_8;
    }
    v53 = 0;
    v15 = v37;
    v16 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64 *))(*(_QWORD *)v37 + 56LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v53);
    v18 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v51, v17);
    if ( v18 )
      v18 = (_QWORD *)*v18;
    v3 = v16(v15, v18, &v53);
    if ( v51 )
      _bstr_t::Data_t::Release(v51);
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x84,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\schedulesdiagdata.cpp",
        (const char *)(unsigned int)v3,
        (int)v44);
LABEL_17:
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v53);
      goto LABEL_43;
    }
    v34 = 0;
    v19 = v53;
    v20 = *(int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v53 + 72LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v34);
    if ( v20(v19, L"\\Microsoft\\Windows\\EnterpriseMgmt", &v34) >= 0 )
    {
      v35 = 0;
      v21 = v34;
      v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)v34 + 80LL);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
      v23 = v22(v21, 1, &v35);
      v3 = v23;
      if ( v23 < 0 )
      {
        v24 = 139;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\schedulesdiagdata.cpp",
          (const char *)(unsigned int)v23,
          (int)v44);
LABEL_22:
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
LABEL_23:
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v34);
        goto LABEL_17;
      }
      LODWORD(v51) = 0;
      v23 = (*(__int64 (__fastcall **)(__int64 *, _bstr_t::Data_t **))(*v35 + 56))(v35, &v51);
      v3 = v23;
      if ( v23 < 0 )
      {
        v24 = 142;
        goto LABEL_21;
      }
      v25 = 0;
      if ( (int)v51 > 0 )
      {
        while ( 1 )
        {
          v36 = 0;
          v26 = v35;
          v27 = *v35;
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v36);
          ++v25;
          v38.iVal = 3;
          *((_DWORD *)&v38.decVal + 4) = v25;
          *(_OWORD *)&v39[1] = *(_OWORD *)&v38.decVal.Lo32;
          v40 = v39[0];
          v3 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, __int64 *))(v27 + 64))(v26, &v39[1], &v36);
          VariantClear((VARIANTARG *)&v38.decVal.8);
          if ( v3 < 0 )
            break;
          v52 = v36;
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
          Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetFolderData(this);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v36);
          if ( v25 >= (int)v51 )
            goto LABEL_31;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x95,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\schedulesdiagdata.cpp",
          (const char *)(unsigned int)v3,
          (int)v44);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v36);
        goto LABEL_22;
      }
LABEL_31:
      *(_QWORD *)&v38.vt = 0;
      v28 = v53;
      v29 = *(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v53 + 72LL);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v38);
      if ( v29(v28, L"\\Microsoft\\Windows\\TPM", &v38) >= 0 )
      {
        v52 = *(_QWORD *)&v38.vt;
        if ( *(_QWORD *)&v38.vt )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v38.vt + 8LL))(*(_QWORD *)&v38.vt);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetFolderData(this);
      }
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
    }
    v30 = Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteEndElement(this);
    v3 = v30;
    if ( v30 >= 0 )
    {
      v30 = Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::FinishFileWrite(this);
      v3 = v30;
      if ( v30 >= 0 )
      {
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v34);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v53);
        v3 = 0;
        goto LABEL_43;
      }
      v31 = 168;
    }
    else
    {
      v31 = 167;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\schedulesdiagdata.cpp",
      (const char *)(unsigned int)v30,
      (int)v44);
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x78,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\schedulesdiagdata.cpp",
    (const char *)(unsigned int)v2,
    (int)ppv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180118e40  mov     rax, rsp
0x180118e43  push    rbp
0x180118e44  push    rbx
0x180118e45  push    rsi
0x180118e46  push    rdi
0x180118e47  push    r14
0x180118e49  lea     rbp, [rax-0C8h]
0x180118e50  sub     rsp, 1A0h
0x180118e57  movaps  xmmword ptr [rax-38h], xmm6
0x180118e5b  movaps  xmmword ptr [rax-48h], xmm7
0x180118e5f  movaps  xmmword ptr [rax-58h], xmm8
0x180118e64  movaps  xmmword ptr [rax-68h], xmm9
0x180118e69  movaps  xmmword ptr [rax-78h], xmm10
0x180118e6e  movaps  xmmword ptr [rax-88h], xmm11
0x180118e76  mov     rsi, rcx
0x180118e79  lea     rdx, aSchedules; "Schedules"
0x180118e80  call    ?WriteStartElement@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteStartElement(ushort const *)
0x180118e85  mov     ebx, eax
0x180118e87  test    eax, eax
0x180118e89  jns     short loc_180118EAB
0x180118e8b  mov     rcx, [rbp+0C8h]; this
0x180118e92  mov     r9d, eax; char *
0x180118e95  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180118e9c  mov     edx, 78h ; 'x'; void *
0x180118ea1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118ea6  jmp     loc_18011939D
0x180118eab  mov     [rsp+1C0h+var_178], 0
0x180118eb4  xor     edx, edx; dwCoInit
0x180118eb6  xor     ecx, ecx; pvReserved
0x180118eb8  call    cs:__imp_CoInitializeEx
0x180118ebf  nop     dword ptr [rax+rax+00h]
0x180118ec4  mov     ebx, eax
0x180118ec6  test    eax, eax
0x180118ec8  jns     short loc_180118ED1
0x180118eca  mov     edx, 7Ch ; '|'
0x180118ecf  jmp     short loc_180118F14
0x180118ed1  lea     rcx, [rsp+1C0h+var_178]
0x180118ed6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180118edb  lea     rax, [rsp+1C0h+var_178]
0x180118ee0  mov     [rsp+1C0h+ppv], rax; int
0x180118ee5  lea     r9, IID_ITaskService; riid
0x180118eec  mov     r14d, 1
0x180118ef2  mov     r8d, r14d; dwClsContext
0x180118ef5  xor     edx, edx; pUnkOuter
0x180118ef7  lea     rcx, CLSID_TaskScheduler; rclsid
0x180118efe  call    cs:__imp_CoCreateInstance
0x180118f05  nop     dword ptr [rax+rax+00h]
0x180118f0a  mov     ebx, eax
0x180118f0c  test    eax, eax
0x180118f0e  jns     short loc_180118F2F
0x180118f10  lea     edx, [r14+7Eh]; void *
0x180118f14  mov     r9d, eax; char *
0x180118f17  mov     rcx, [rbp+0C8h]; this
0x180118f1e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180118f25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118f2a  jmp     loc_180119393
0x180118f2f  mov     rdi, [rsp+1C0h+var_178]
0x180118f34  mov     rax, [rdi]
0x180118f37  mov     rbx, [rax+50h]
0x180118f3b  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x180118f3f  call    cs:__imp_VariantInit
0x180118f46  nop     dword ptr [rax+rax+00h]
0x180118f4b  nop
0x180118f4c  movups  xmm10, xmmword ptr [rbp+0C0h+pvarg]
0x180118f51  movsd   xmm11, qword ptr [rbp+0C0h+pvarg+10h]
0x180118f57  lea     rcx, [rbp+0C0h+var_118]; pvarg
0x180118f5b  call    cs:__imp_VariantInit
0x180118f62  nop     dword ptr [rax+rax+00h]
0x180118f67  nop
0x180118f68  movups  xmm8, xmmword ptr [rbp+0C0h+var_118]
0x180118f6d  movsd   xmm9, qword ptr [rbp+0C0h+var_118+10h]
0x180118f73  lea     rcx, [rbp+0C0h+var_130]; pvarg
0x180118f77  call    cs:__imp_VariantInit
0x180118f7e  nop     dword ptr [rax+rax+00h]
0x180118f83  nop
0x180118f84  movups  xmm6, xmmword ptr [rbp+0C0h+var_130]
0x180118f88  movsd   xmm7, qword ptr [rbp+0C0h+var_130+10h]
0x180118f8d  lea     rcx, [rsp+1C0h+var_170+8]; pvarg
0x180118f92  call    cs:__imp_VariantInit
0x180118f99  nop     dword ptr [rax+rax+00h]
0x180118f9e  nop
0x180118f9f  movups  xmm0, xmmword ptr [rsp+1C0h+var_170+8]
0x180118fa4  movsd   xmm1, qword ptr [rsp+1C0h+var_158]
0x180118faa  movaps  xmmword ptr [rbp+0C0h+var_E0], xmm10
0x180118faf  movsd   [rbp+0C0h+var_D0], xmm11
0x180118fb5  movaps  [rbp+0C0h+var_C0], xmm8
0x180118fba  movsd   [rbp+0C0h+var_B0], xmm9
0x180118fc0  movaps  [rbp+0C0h+var_A0], xmm6
0x180118fc4  movsd   [rbp+0C0h+var_90], xmm7
0x180118fc9  movaps  xmmword ptr [rsp+1C0h+var_158+8], xmm0
0x180118fce  movsd   [rbp+0C0h+var_140], xmm1
0x180118fd3  lea     rax, [rbp+0C0h+var_E0]
0x180118fd7  mov     [rsp+1C0h+ppv], rax; int
0x180118fdc  lea     r9, [rbp+0C0h+var_C0]
0x180118fe0  lea     r8, [rbp+0C0h+var_A0]
0x180118fe4  lea     rdx, [rsp+1C0h+var_158+8]
0x180118fe9  mov     rcx, rdi
0x180118fec  mov     rax, rbx
0x180118fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118ff4  mov     ebx, eax
0x180118ff6  lea     rcx, [rsp+1C0h+var_170+8]; pvarg
0x180118ffb  call    cs:__imp_VariantClear
0x180119002  nop     dword ptr [rax+rax+00h]
0x180119007  nop
0x180119008  lea     rcx, [rbp+0C0h+var_130]; pvarg
0x18011900c  call    cs:__imp_VariantClear
0x180119013  nop     dword ptr [rax+rax+00h]
0x180119018  nop
0x180119019  lea     rcx, [rbp+0C0h+var_118]; pvarg
0x18011901d  call    cs:__imp_VariantClear
0x180119024  nop     dword ptr [rax+rax+00h]
0x180119029  nop
0x18011902a  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x18011902e  call    cs:__imp_VariantClear
0x180119035  nop     dword ptr [rax+rax+00h]
0x18011903a  test    ebx, ebx
0x18011903c  jns     short loc_18011904B
0x18011903e  mov     r9d, ebx
0x180119041  mov     edx, 81h
0x180119046  jmp     loc_180118F17
0x18011904b  mov     [rbp+0C0h+arg_18], 0
0x180119056  mov     rbx, [rsp+1C0h+var_178]
0x18011905b  mov     rax, [rbx]
0x18011905e  mov     rdi, [rax+38h]
0x180119062  lea     rcx, [rbp+0C0h+arg_18]
0x180119069  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18011906e  lea     rcx, [rbp+0C0h+arg_8]; this
0x180119075  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18011907a  nop
0x18011907b  mov     rdx, [rax]
0x18011907e  test    rdx, rdx
0x180119081  jz      short loc_180119086
0x180119083  mov     rdx, [rdx]
0x180119086  lea     r8, [rbp+0C0h+arg_18]
0x18011908d  mov     rcx, rbx
0x180119090  mov     rax, rdi
0x180119093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119098  mov     ebx, eax
0x18011909a  mov     rcx, [rbp+0C0h+arg_8]; this
0x1801190a1  test    rcx, rcx
0x1801190a4  jz      short loc_1801190AB
0x1801190a6  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x1801190ab  test    ebx, ebx
0x1801190ad  jns     short loc_1801190DC
0x1801190af  mov     rcx, [rbp+0C8h]; this
0x1801190b6  mov     r9d, ebx; char *
0x1801190b9  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801190c0  mov     edx, 84h; void *
0x1801190c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801190ca  nop
0x1801190cb  lea     rcx, [rbp+0C0h+arg_18]
0x1801190d2  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801190d7  jmp     loc_180119393
0x1801190dc  mov     [rsp+1C0h+var_190], 0
0x1801190e5  mov     rdi, [rbp+0C0h+arg_18]
0x1801190ec  mov     rax, [rdi]
0x1801190ef  mov     rbx, [rax+48h]
0x1801190f3  lea     rcx, [rsp+1C0h+var_190]
0x1801190f8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801190fd  lea     r8, [rsp+1C0h+var_190]
0x180119102  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180119109  mov     rcx, rdi
0x18011910c  mov     rax, rbx
0x18011910f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119114  test    eax, eax
0x180119116  js      loc_18011930C
0x18011911c  mov     [rsp+1C0h+var_188], 0
0x180119125  mov     rdi, [rsp+1C0h+var_190]
0x18011912a  mov     rax, [rdi]
0x18011912d  mov     rbx, [rax+50h]
0x180119131  lea     rcx, [rsp+1C0h+var_188]
0x180119136  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18011913b  lea     r8, [rsp+1C0h+var_188]
0x180119140  mov     edx, r14d
0x180119143  mov     rcx, rdi
0x180119146  mov     rax, rbx
0x180119149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011914e  mov     ebx, eax
0x180119150  test    eax, eax
0x180119152  jns     short loc_18011918A
0x180119154  mov     edx, 8Bh; void *
0x180119159  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180119160  mov     r9d, eax; char *
0x180119163  mov     rcx, [rbp+0C8h]; this
0x18011916a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011916f  nop
0x180119170  lea     rcx, [rsp+1C0h+var_188]
0x180119175  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18011917a  nop
0x18011917b  lea     rcx, [rsp+1C0h+var_190]
0x180119180  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180119185  jmp     loc_1801190CB
0x18011918a  mov     dword ptr [rbp+0C0h+arg_8], 0
0x180119194  mov     rcx, [rsp+1C0h+var_188]
0x180119199  mov     rax, [rcx]
0x18011919c  lea     rdx, [rbp+0C0h+arg_8]
0x1801191a3  mov     rax, [rax+38h]
0x1801191a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801191ac  mov     ebx, eax
0x1801191ae  test    eax, eax
0x1801191b0  jns     short loc_1801191B9
0x1801191b2  mov     edx, 8Eh
0x1801191b7  jmp     short loc_180119159
0x1801191b9  xor     r14d, r14d
0x1801191bc  cmp     dword ptr [rbp+0C0h+arg_8], r14d
0x1801191c3  jle     loc_18011928D
0x1801191c9  mov     [rsp+1C0h+var_180], 0
0x1801191d2  mov     rdi, [rsp+1C0h+var_188]
0x1801191d7  mov     rbx, [rdi]
0x1801191da  lea     rcx, [rsp+1C0h+var_180]
0x1801191df  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801191e4  inc     r14d
0x1801191e7  mov     eax, 3
0x1801191ec  mov     word ptr [rsp+1C0h+var_170+8], ax
0x1801191f1  mov     word ptr [rsp+1C0h+var_170+10h], r14w
0x1801191f7  mov     edx, r14d
0x1801191fa  sar     edx, 10h
0x1801191fd  mov     word ptr [rsp+1C0h+var_170+12h], dx
0x180119202  movups  xmm0, xmmword ptr [rsp+1C0h+var_170+8]
0x180119207  movaps  xmmword ptr [rsp+1C0h+var_158+8], xmm0
0x18011920c  movsd   xmm1, qword ptr [rsp+1C0h+var_158]
0x180119212  movsd   [rbp+0C0h+var_140], xmm1
0x180119217  lea     r8, [rsp+1C0h+var_180]
0x18011921c  lea     rdx, [rsp+1C0h+var_158+8]
0x180119221  mov     rcx, rdi
0x180119224  mov     rax, [rbx+40h]
0x180119228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011922d  mov     ebx, eax
0x18011922f  lea     rcx, [rsp+1C0h+var_170+8]; pvarg
0x180119234  call    cs:__imp_VariantClear
0x18011923b  nop     dword ptr [rax+rax+00h]
0x180119240  test    ebx, ebx
0x180119242  js      loc_18011933A
0x180119248  mov     rcx, [rsp+1C0h+var_180]
0x18011924d  mov     [rbp+0C0h+arg_10], rcx
0x180119254  test    rcx, rcx
0x180119257  jz      short loc_180119266
0x180119259  mov     rax, [rcx]
0x18011925c  mov     rax, [rax+8]
0x180119260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119265  nop
0x180119266  lea     rdx, [rbp+0C0h+arg_10]
0x18011926d  mov     rcx, rsi; this
0x180119270  call    ?GetFolderData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJV?$ComPtr@UITaskFolder@@@WRL@5@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetFolderData(Microsoft::WRL::ComPtr<ITaskFolder>)
0x180119275  nop
0x180119276  lea     rcx, [rsp+1C0h+var_180]
0x18011927b  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180119280  cmp     r14d, dword ptr [rbp+0C0h+arg_8]
0x180119287  jl      loc_1801191C9
0x18011928d  mov     qword ptr [rsp+1C0h+var_170], 0
0x180119296  mov     rdi, [rbp+0C0h+arg_18]
0x18011929d  mov     rax, [rdi]
0x1801192a0  mov     rbx, [rax+48h]
0x1801192a4  lea     rcx, [rsp+1C0h+var_170]
0x1801192a9  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801192ae  lea     r8, [rsp+1C0h+var_170]
0x1801192b3  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\TPM"
0x1801192ba  mov     rcx, rdi
0x1801192bd  mov     rax, rbx
0x1801192c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801192c5  test    eax, eax
0x1801192c7  js      short loc_1801192F7
0x1801192c9  mov     rcx, qword ptr [rsp+1C0h+var_170]
0x1801192ce  mov     [rbp+0C0h+arg_10], rcx
0x1801192d5  test    rcx, rcx
0x1801192d8  jz      short loc_1801192E7
0x1801192da  mov     rax, [rcx]
0x1801192dd  mov     rax, [rax+8]
0x1801192e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801192e6  nop
0x1801192e7  lea     rdx, [rbp+0C0h+arg_10]
0x1801192ee  mov     rcx, rsi; this
0x1801192f1  call    ?GetFolderData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJV?$ComPtr@UITaskFolder@@@WRL@5@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetFolderData(Microsoft::WRL::ComPtr<ITaskFolder>)
0x1801192f6  nop
0x1801192f7  lea     rcx, [rsp+1C0h+var_170]
0x1801192fc  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180119301  nop
0x180119302  lea     rcx, [rsp+1C0h+var_188]
0x180119307  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18011930c  mov     rcx, rsi; this
0x18011930f  call    ?WriteEndElement@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteEndElement(void)
0x180119314  mov     ebx, eax
0x180119316  test    eax, eax
0x180119318  jns     short loc_180119365
0x18011931a  mov     edx, 0A7h; void *
0x18011931f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180119326  mov     r9d, eax; char *
0x180119329  mov     rcx, [rbp+0C8h]; this
0x180119330  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119335  jmp     loc_18011917B
0x18011933a  mov     rcx, [rbp+0C8h]; this
0x180119341  mov     r9d, ebx; char *
0x180119344  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011934b  mov     edx, 95h; void *
0x180119350  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119355  nop
0x180119356  lea     rcx, [rsp+1C0h+var_180]
0x18011935b  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180119360  jmp     loc_180119170
0x180119365  mov     rcx, rsi; this
  ... truncated ...
```
