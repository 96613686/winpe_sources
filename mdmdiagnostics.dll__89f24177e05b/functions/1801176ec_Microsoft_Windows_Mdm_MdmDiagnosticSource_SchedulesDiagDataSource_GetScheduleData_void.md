# Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetScheduleData(void)

- ea: `0x1801176ec`
- end: `0x180117c39`
- name: `?GetScheduleData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ`
- size: `1357`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180116dc0`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x180116b78`
- `0x180116d44`
- `0x180116e50`
- `0x1801176ec`
- `0x180117d10`
- `0x180117d7c`
- `0x180117e58`
- `0x180191010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1801177df`
- `OLEAUT32!__imp_VariantInit` at `0x1801177f5`
- `OLEAUT32!__imp_VariantInit` at `0x18011780b`
- `OLEAUT32!__imp_VariantInit` at `0x180117820`
- `OLEAUT32!__imp_VariantInit` at `0x1801177df`
- `OLEAUT32!__imp_VariantInit` at `0x1801177f5`
- `OLEAUT32!__imp_VariantInit` at `0x18011780b`
- `OLEAUT32!__imp_VariantInit` at `0x180117820`
- `OLEAUT32!__imp_VariantClear` at `0x180117883`
- `OLEAUT32!__imp_VariantClear` at `0x18011788e`
- `OLEAUT32!__imp_VariantClear` at `0x180117899`
- `OLEAUT32!__imp_VariantClear` at `0x1801178a4`
- `OLEAUT32!__imp_VariantClear` at `0x180117aa4`
- `OLEAUT32!__imp_VariantClear` at `0x180117883`
- `OLEAUT32!__imp_VariantClear` at `0x18011788e`
- `OLEAUT32!__imp_VariantClear` at `0x180117899`
- `OLEAUT32!__imp_VariantClear` at `0x1801178a4`
- `OLEAUT32!__imp_VariantClear` at `0x180117aa4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801177a4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801177a4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180117764`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180117764`

## string_xrefs

- `0x180117741`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`
- `0x1801177be`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`
- `0x180117929`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`
- `0x1801179c9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`
- `0x180117b89`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`
- `0x180117bae`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`

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
0x1801176ec  mov     rax, rsp
0x1801176ef  push    rbp
0x1801176f0  push    rbx
0x1801176f1  push    rsi
0x1801176f2  push    rdi
0x1801176f3  push    r14
0x1801176f5  lea     rbp, [rax-0C8h]
0x1801176fc  sub     rsp, 1A0h
0x180117703  movaps  xmmword ptr [rax-38h], xmm6
0x180117707  movaps  xmmword ptr [rax-48h], xmm7
0x18011770b  movaps  xmmword ptr [rax-58h], xmm8
0x180117710  movaps  xmmword ptr [rax-68h], xmm9
0x180117715  movaps  xmmword ptr [rax-78h], xmm10
0x18011771a  movaps  xmmword ptr [rax-88h], xmm11
0x180117722  mov     rsi, rcx
0x180117725  lea     rdx, aSchedules; "Schedules"
0x18011772c  call    ?WriteStartElement@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteStartElement(ushort const *)
0x180117731  mov     ebx, eax
0x180117733  test    eax, eax
0x180117735  jns     short loc_180117757
0x180117737  mov     rcx, [rbp+0C8h]; this
0x18011773e  mov     r9d, eax; char *
0x180117741  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180117748  mov     edx, 78h ; 'x'; void *
0x18011774d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117752  jmp     loc_180117C07
0x180117757  mov     [rsp+1C0h+var_178], 0
0x180117760  xor     edx, edx; dwCoInit
0x180117762  xor     ecx, ecx; pvReserved
0x180117764  call    cs:__imp_CoInitializeEx
0x18011776a  mov     ebx, eax
0x18011776c  test    eax, eax
0x18011776e  jns     short loc_180117777
0x180117770  mov     edx, 7Ch ; '|'
0x180117775  jmp     short loc_1801177B4
0x180117777  lea     rcx, [rsp+1C0h+var_178]
0x18011777c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180117781  lea     rax, [rsp+1C0h+var_178]
0x180117786  mov     [rsp+1C0h+ppv], rax; int
0x18011778b  lea     r9, IID_ITaskService; riid
0x180117792  mov     r14d, 1
0x180117798  mov     r8d, r14d; dwClsContext
0x18011779b  xor     edx, edx; pUnkOuter
0x18011779d  lea     rcx, CLSID_TaskScheduler; rclsid
0x1801177a4  call    cs:__imp_CoCreateInstance
0x1801177aa  mov     ebx, eax
0x1801177ac  test    eax, eax
0x1801177ae  jns     short loc_1801177CF
0x1801177b0  lea     edx, [r14+7Eh]; void *
0x1801177b4  mov     r9d, eax; char *
0x1801177b7  mov     rcx, [rbp+0C8h]; this
0x1801177be  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801177c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801177ca  jmp     loc_180117BFD
0x1801177cf  mov     rdi, [rsp+1C0h+var_178]
0x1801177d4  mov     rax, [rdi]
0x1801177d7  mov     rbx, [rax+50h]
0x1801177db  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x1801177df  call    cs:__imp_VariantInit
0x1801177e5  nop
0x1801177e6  movups  xmm10, xmmword ptr [rbp+0C0h+pvarg]
0x1801177eb  movsd   xmm11, qword ptr [rbp+0C0h+pvarg+10h]
0x1801177f1  lea     rcx, [rbp+0C0h+var_118]; pvarg
0x1801177f5  call    cs:__imp_VariantInit
0x1801177fb  nop
0x1801177fc  movups  xmm8, xmmword ptr [rbp+0C0h+var_118]
0x180117801  movsd   xmm9, qword ptr [rbp+0C0h+var_118+10h]
0x180117807  lea     rcx, [rbp+0C0h+var_130]; pvarg
0x18011780b  call    cs:__imp_VariantInit
0x180117811  nop
0x180117812  movups  xmm6, xmmword ptr [rbp+0C0h+var_130]
0x180117816  movsd   xmm7, qword ptr [rbp+0C0h+var_130+10h]
0x18011781b  lea     rcx, [rsp+1C0h+var_170+8]; pvarg
0x180117820  call    cs:__imp_VariantInit
0x180117826  nop
0x180117827  movups  xmm0, xmmword ptr [rsp+1C0h+var_170+8]
0x18011782c  movsd   xmm1, qword ptr [rsp+1C0h+var_158]
0x180117832  movaps  xmmword ptr [rbp+0C0h+var_E0], xmm10
0x180117837  movsd   [rbp+0C0h+var_D0], xmm11
0x18011783d  movaps  [rbp+0C0h+var_C0], xmm8
0x180117842  movsd   [rbp+0C0h+var_B0], xmm9
0x180117848  movaps  [rbp+0C0h+var_A0], xmm6
0x18011784c  movsd   [rbp+0C0h+var_90], xmm7
0x180117851  movaps  xmmword ptr [rsp+1C0h+var_158+8], xmm0
0x180117856  movsd   [rbp+0C0h+var_140], xmm1
0x18011785b  lea     rax, [rbp+0C0h+var_E0]
0x18011785f  mov     [rsp+1C0h+ppv], rax; int
0x180117864  lea     r9, [rbp+0C0h+var_C0]
0x180117868  lea     r8, [rbp+0C0h+var_A0]
0x18011786c  lea     rdx, [rsp+1C0h+var_158+8]
0x180117871  mov     rcx, rdi
0x180117874  mov     rax, rbx
0x180117877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011787c  mov     ebx, eax
0x18011787e  lea     rcx, [rsp+1C0h+var_170+8]; pvarg
0x180117883  call    cs:__imp_VariantClear
0x180117889  nop
0x18011788a  lea     rcx, [rbp+0C0h+var_130]; pvarg
0x18011788e  call    cs:__imp_VariantClear
0x180117894  nop
0x180117895  lea     rcx, [rbp+0C0h+var_118]; pvarg
0x180117899  call    cs:__imp_VariantClear
0x18011789f  nop
0x1801178a0  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x1801178a4  call    cs:__imp_VariantClear
0x1801178aa  test    ebx, ebx
0x1801178ac  jns     short loc_1801178BB
0x1801178ae  mov     r9d, ebx
0x1801178b1  mov     edx, 81h
0x1801178b6  jmp     loc_1801177B7
0x1801178bb  mov     [rbp+0C0h+arg_18], 0
0x1801178c6  mov     rbx, [rsp+1C0h+var_178]
0x1801178cb  mov     rax, [rbx]
0x1801178ce  mov     rdi, [rax+38h]
0x1801178d2  lea     rcx, [rbp+0C0h+arg_18]
0x1801178d9  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801178de  lea     rcx, [rbp+0C0h+arg_8]; this
0x1801178e5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1801178ea  nop
0x1801178eb  mov     rdx, [rax]
0x1801178ee  test    rdx, rdx
0x1801178f1  jz      short loc_1801178F6
0x1801178f3  mov     rdx, [rdx]
0x1801178f6  lea     r8, [rbp+0C0h+arg_18]
0x1801178fd  mov     rcx, rbx
0x180117900  mov     rax, rdi
0x180117903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117908  mov     ebx, eax
0x18011790a  mov     rcx, [rbp+0C0h+arg_8]; this
0x180117911  test    rcx, rcx
0x180117914  jz      short loc_18011791B
0x180117916  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x18011791b  test    ebx, ebx
0x18011791d  jns     short loc_18011794C
0x18011791f  mov     rcx, [rbp+0C8h]; this
0x180117926  mov     r9d, ebx; char *
0x180117929  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180117930  mov     edx, 84h; void *
0x180117935  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011793a  nop
0x18011793b  lea     rcx, [rbp+0C0h+arg_18]
0x180117942  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180117947  jmp     loc_180117BFD
0x18011794c  mov     [rsp+1C0h+var_190], 0
0x180117955  mov     rdi, [rbp+0C0h+arg_18]
0x18011795c  mov     rax, [rdi]
0x18011795f  mov     rbx, [rax+48h]
0x180117963  lea     rcx, [rsp+1C0h+var_190]
0x180117968  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18011796d  lea     r8, [rsp+1C0h+var_190]
0x180117972  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180117979  mov     rcx, rdi
0x18011797c  mov     rax, rbx
0x18011797f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117984  test    eax, eax
0x180117986  js      loc_180117B76
0x18011798c  mov     [rsp+1C0h+var_188], 0
0x180117995  mov     rdi, [rsp+1C0h+var_190]
0x18011799a  mov     rax, [rdi]
0x18011799d  mov     rbx, [rax+50h]
0x1801179a1  lea     rcx, [rsp+1C0h+var_188]
0x1801179a6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801179ab  lea     r8, [rsp+1C0h+var_188]
0x1801179b0  mov     edx, r14d
0x1801179b3  mov     rcx, rdi
0x1801179b6  mov     rax, rbx
0x1801179b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801179be  mov     ebx, eax
0x1801179c0  test    eax, eax
0x1801179c2  jns     short loc_1801179FA
0x1801179c4  mov     edx, 8Bh; void *
0x1801179c9  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801179d0  mov     r9d, eax; char *
0x1801179d3  mov     rcx, [rbp+0C8h]; this
0x1801179da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801179df  nop
0x1801179e0  lea     rcx, [rsp+1C0h+var_188]
0x1801179e5  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801179ea  nop
0x1801179eb  lea     rcx, [rsp+1C0h+var_190]
0x1801179f0  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801179f5  jmp     loc_18011793B
0x1801179fa  mov     dword ptr [rbp+0C0h+arg_8], 0
0x180117a04  mov     rcx, [rsp+1C0h+var_188]
0x180117a09  mov     rax, [rcx]
0x180117a0c  lea     rdx, [rbp+0C0h+arg_8]
0x180117a13  mov     rax, [rax+38h]
0x180117a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117a1c  mov     ebx, eax
0x180117a1e  test    eax, eax
0x180117a20  jns     short loc_180117A29
0x180117a22  mov     edx, 8Eh
0x180117a27  jmp     short loc_1801179C9
0x180117a29  xor     r14d, r14d
0x180117a2c  cmp     dword ptr [rbp+0C0h+arg_8], r14d
0x180117a33  jle     loc_180117AF7
0x180117a39  mov     [rsp+1C0h+var_180], 0
0x180117a42  mov     rdi, [rsp+1C0h+var_188]
0x180117a47  mov     rbx, [rdi]
0x180117a4a  lea     rcx, [rsp+1C0h+var_180]
0x180117a4f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180117a54  inc     r14d
0x180117a57  mov     eax, 3
0x180117a5c  mov     word ptr [rsp+1C0h+var_170+8], ax
0x180117a61  mov     word ptr [rsp+1C0h+var_170+10h], r14w
0x180117a67  mov     edx, r14d
0x180117a6a  sar     edx, 10h
0x180117a6d  mov     word ptr [rsp+1C0h+var_170+12h], dx
0x180117a72  movups  xmm0, xmmword ptr [rsp+1C0h+var_170+8]
0x180117a77  movaps  xmmword ptr [rsp+1C0h+var_158+8], xmm0
0x180117a7c  movsd   xmm1, qword ptr [rsp+1C0h+var_158]
0x180117a82  movsd   [rbp+0C0h+var_140], xmm1
0x180117a87  lea     r8, [rsp+1C0h+var_180]
0x180117a8c  lea     rdx, [rsp+1C0h+var_158+8]
0x180117a91  mov     rcx, rdi
0x180117a94  mov     rax, [rbx+40h]
0x180117a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117a9d  mov     ebx, eax
0x180117a9f  lea     rcx, [rsp+1C0h+var_170+8]; pvarg
0x180117aa4  call    cs:__imp_VariantClear
0x180117aaa  test    ebx, ebx
0x180117aac  js      loc_180117BA4
0x180117ab2  mov     rcx, [rsp+1C0h+var_180]
0x180117ab7  mov     [rbp+0C0h+arg_10], rcx
0x180117abe  test    rcx, rcx
0x180117ac1  jz      short loc_180117AD0
0x180117ac3  mov     rax, [rcx]
0x180117ac6  mov     rax, [rax+8]
0x180117aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117acf  nop
0x180117ad0  lea     rdx, [rbp+0C0h+arg_10]
0x180117ad7  mov     rcx, rsi; this
0x180117ada  call    ?GetFolderData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJV?$ComPtr@UITaskFolder@@@WRL@5@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetFolderData(Microsoft::WRL::ComPtr<ITaskFolder>)
0x180117adf  nop
0x180117ae0  lea     rcx, [rsp+1C0h+var_180]
0x180117ae5  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180117aea  cmp     r14d, dword ptr [rbp+0C0h+arg_8]
0x180117af1  jl      loc_180117A39
0x180117af7  mov     qword ptr [rsp+1C0h+var_170], 0
0x180117b00  mov     rdi, [rbp+0C0h+arg_18]
0x180117b07  mov     rax, [rdi]
0x180117b0a  mov     rbx, [rax+48h]
0x180117b0e  lea     rcx, [rsp+1C0h+var_170]
0x180117b13  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180117b18  lea     r8, [rsp+1C0h+var_170]
0x180117b1d  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\TPM"
0x180117b24  mov     rcx, rdi
0x180117b27  mov     rax, rbx
0x180117b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117b2f  test    eax, eax
0x180117b31  js      short loc_180117B61
0x180117b33  mov     rcx, qword ptr [rsp+1C0h+var_170]
0x180117b38  mov     [rbp+0C0h+arg_10], rcx
0x180117b3f  test    rcx, rcx
0x180117b42  jz      short loc_180117B51
0x180117b44  mov     rax, [rcx]
0x180117b47  mov     rax, [rax+8]
0x180117b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117b50  nop
0x180117b51  lea     rdx, [rbp+0C0h+arg_10]
0x180117b58  mov     rcx, rsi; this
0x180117b5b  call    ?GetFolderData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJV?$ComPtr@UITaskFolder@@@WRL@5@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetFolderData(Microsoft::WRL::ComPtr<ITaskFolder>)
0x180117b60  nop
0x180117b61  lea     rcx, [rsp+1C0h+var_170]
0x180117b66  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180117b6b  nop
0x180117b6c  lea     rcx, [rsp+1C0h+var_188]
0x180117b71  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180117b76  mov     rcx, rsi; this
0x180117b79  call    ?WriteEndElement@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteEndElement(void)
0x180117b7e  mov     ebx, eax
0x180117b80  test    eax, eax
0x180117b82  jns     short loc_180117BCF
0x180117b84  mov     edx, 0A7h; void *
0x180117b89  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180117b90  mov     r9d, eax; char *
0x180117b93  mov     rcx, [rbp+0C8h]; this
0x180117b9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117b9f  jmp     loc_1801179EB
0x180117ba4  mov     rcx, [rbp+0C8h]; this
0x180117bab  mov     r9d, ebx; char *
0x180117bae  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180117bb5  mov     edx, 95h; void *
0x180117bba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117bbf  nop
0x180117bc0  lea     rcx, [rsp+1C0h+var_180]
0x180117bc5  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180117bca  jmp     loc_1801179E0
0x180117bcf  mov     rcx, rsi; this
0x180117bd2  call    ?FinishFileWrite@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::FinishFileWrite(void)
0x180117bd7  mov     ebx, eax
0x180117bd9  test    eax, eax
0x180117bdb  jns     short loc_180117BE4
0x180117bdd  mov     edx, 0A8h
0x180117be2  jmp     short loc_180117B89
0x180117be4  lea     rcx, [rsp+1C0h+var_190]
0x180117be9  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180117bee  nop
0x180117bef  lea     rcx, [rbp+0C0h+arg_18]
0x180117bf6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
  ... truncated ...
```
