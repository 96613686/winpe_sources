# ScheduleProvisioningInitiatedSyncHelper

- ea: `0x18001a25c`
- end: `0x18001a5c2`
- name: `ScheduleProvisioningInitiatedSyncHelper`
- size: `870`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800194bc`

## callees

- `0x1800022e0`
- `0x180006c98`
- `0x18000aa2c`
- `0x18000aab8`
- `0x18000ab84`
- `0x1800117c8`
- `0x180011d5c`
- `0x180012ed4`
- `0x18001a25c`
- `0x18001dce8`
- `0x18001e264`
- `0x180020010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001a437`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a437`
- `OLEAUT32!__imp_VariantInit` at `0x18001a405`
- `OLEAUT32!__imp_VariantInit` at `0x18001a41a`
- `OLEAUT32!__imp_VariantInit` at `0x18001a405`
- `OLEAUT32!__imp_VariantInit` at `0x18001a41a`
- `OLEAUT32!__imp_VariantClear` at `0x18001a4ee`
- `OLEAUT32!__imp_VariantClear` at `0x18001a4f8`
- `OLEAUT32!__imp_VariantClear` at `0x18001a502`
- `OLEAUT32!__imp_VariantClear` at `0x18001a4ee`
- `OLEAUT32!__imp_VariantClear` at `0x18001a4f8`
- `OLEAUT32!__imp_VariantClear` at `0x18001a502`

## string_xrefs

- `0x18001a391`: `%windir%\system32\deviceenroller.exe `

## pseudocode

```c
__int64 __fastcall ScheduleProvisioningInitiatedSyncHelper(unsigned __int16 *a1)
{
  int Task; // ebx
  void (*v3)(void); // rax
  __int64 *v4; // rdi
  __int64 v5; // rbx
  __int128 v6; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v8; // xmm10
  IRecordInfo *v9; // xmm11_8
  __int64 (__fastcall *v10)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rsi
  __int128 v11; // xmm6
  IRecordInfo *v12; // xmm7_8
  __int64 v13; // rbx
  _bstr_t *v14; // rax
  __int64 v15; // rdx
  const struct std::nothrow_t *v16; // rdx
  CEnrollmentLogger *Logger; // rax
  int v19[2]; // [rsp+78h] [rbp-90h] BYREF
  int v20[2]; // [rsp+80h] [rbp-88h] BYREF
  int v21[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v22; // [rsp+90h] [rbp-78h] BYREF
  int v23[2]; // [rsp+98h] [rbp-70h] BYREF
  int v24[2]; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v25[2]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v26[8]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v27; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v28; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v30; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v31; // [rsp+118h] [rbp+10h]
  __int128 v32; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v33; // [rsp+138h] [rbp+30h]
  __int128 v34; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v35; // [rsp+158h] [rbp+50h]
  unsigned __int16 v36[264]; // [rsp+168h] [rbp+60h] BYREF

  *(_QWORD *)v24 = 0;
  *(_QWORD *)v21 = 0;
  *(_QWORD *)v20 = 0;
  *(_QWORD *)v23 = 0;
  v22 = 0;
  Task = StringCchPrintfW(v36, 0x104u, L"/c /ProvInitiatedSession /o \"%s\"", a1);
  v19[0] = Task;
  v25[0] = "ScheduleProvisioningInitiatedSyncHelper";
  v25[1] = v19;
  if ( Task < 0
    || (Task = CreateTask(
                 v24,
                 (__int64 *)v21,
                 v20,
                 v23,
                 a1,
                 L"%windir%\\system32\\deviceenroller.exe ",
                 v36,
                 L"S-1-5-18",
                 0,
                 1,
                 0,
                 0,
                 0),
        v19[0] = Task,
        Task < 0) )
  {
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v25);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v22);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v23);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v20);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v21);
    if ( *(_QWORD *)v24 )
    {
      v3 = *(void (**)(void))(**(_QWORD **)v24 + 16LL);
LABEL_13:
      v3();
    }
  }
  else
  {
    v4 = *(__int64 **)v21;
    v5 = **(_QWORD **)v21;
    VariantInit(&pvarg);
    v6 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v28);
    v8 = *(_OWORD *)&v28.vt;
    v9 = v28.pRecInfo;
    v27.vt = 8;
    v27.llVal = (LONGLONG)SysAllocString(L"S-1-5-18");
    if ( !v27.llVal )
      _com_issue_error(-2147024882);
    v10 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v5 + 136);
    v11 = *(_OWORD *)&v27.vt;
    v12 = v27.pRecInfo;
    v13 = *(_QWORD *)v20;
    v14 = _bstr_t::_bstr_t((_bstr_t *)v26, L"Provisioning initiated session");
    if ( *(_QWORD *)v14 )
      v15 = **(_QWORD **)v14;
    else
      v15 = 0;
    v30 = v6;
    v31 = pRecInfo;
    v32 = v8;
    v33 = v9;
    v34 = v11;
    v35 = v12;
    v19[0] = v10(v4, v15, v13, 6, &v34, &v32, 3, &v30, &v22);
    _bstr_t::~_bstr_t((_bstr_t *)v26, v16);
    VariantClear(&v27);
    VariantClear(&v28);
    VariantClear(&pvarg);
    Task = v19[0];
    if ( v19[0] < 0 )
    {
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, v19[0], "ScheduleProvisioningInitiatedSyncHelper");
      Task = v19[0];
    }
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v25);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v22);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v23);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v20);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v21);
    if ( *(_QWORD *)v24 )
    {
      v3 = *(void (**)(void))(**(_QWORD **)v24 + 16LL);
      goto LABEL_13;
    }
  }
  return (unsigned int)Task;
}

```

## disassembly

```asm
0x18001a25c  mov     rax, rsp
0x18001a25f  mov     [rax+10h], rbx
0x18001a263  mov     [rax+18h], rsi
0x18001a267  push    rbp
0x18001a268  push    rdi
0x18001a269  push    r15
0x18001a26b  lea     rbp, [rax-2F8h]
0x18001a272  sub     rsp, 3E0h
0x18001a279  movaps  xmmword ptr [rax-28h], xmm6
0x18001a27d  movaps  xmmword ptr [rax-38h], xmm7
0x18001a281  movaps  xmmword ptr [rax-48h], xmm8
0x18001a286  movaps  xmmword ptr [rax-58h], xmm9
0x18001a28b  movaps  xmmword ptr [rax-68h], xmm10
0x18001a290  movaps  xmmword ptr [rax-78h], xmm11
0x18001a295  mov     rax, cs:__security_cookie
0x18001a29c  xor     rax, rsp
0x18001a29f  mov     [rbp+2F0h+var_80], rax
0x18001a2a6  mov     rdi, rcx
0x18001a2a9  mov     qword ptr [rbp+2F0h+var_358], 0
0x18001a2b1  mov     qword ptr [rbp+2F0h+var_370], 0
0x18001a2b9  mov     qword ptr [rsp+3F0h+var_378], 0
0x18001a2c2  mov     qword ptr [rbp+2F0h+var_360], 0
0x18001a2ca  mov     [rbp+2F0h+var_368], 0
0x18001a2d2  mov     r9, rcx
0x18001a2d5  lea     r8, aCProvinitiated; "/c /ProvInitiatedSession /o \"%s\""
0x18001a2dc  mov     edx, 104h; unsigned __int64
0x18001a2e1  lea     rcx, [rbp+2F0h+var_290]; unsigned __int16 *
0x18001a2e5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a2ea  mov     ebx, eax
0x18001a2ec  mov     [rsp+3F0h+var_380], eax
0x18001a2f0  lea     r15, aScheduleprovis; "ScheduleProvisioningInitiatedSyncHelper"
0x18001a2f7  mov     [rbp+2F0h+var_350], r15
0x18001a2fb  lea     rax, [rsp+3F0h+var_380]
0x18001a300  mov     [rbp+2F0h+var_348], rax
0x18001a304  test    ebx, ebx
0x18001a306  jns     short loc_18001A354
0x18001a308  lea     rcx, [rbp+2F0h+var_350]; this
0x18001a30c  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001a311  nop
0x18001a312  lea     rcx, [rbp+2F0h+var_368]
0x18001a316  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a31b  nop
0x18001a31c  lea     rcx, [rbp+2F0h+var_360]
0x18001a320  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a325  nop
0x18001a326  lea     rcx, [rsp+3F0h+var_378]
0x18001a32b  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a330  nop
0x18001a331  lea     rcx, [rbp+2F0h+var_370]
0x18001a335  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a33a  nop
0x18001a33b  mov     rcx, qword ptr [rbp+2F0h+var_358]
0x18001a33f  test    rcx, rcx
0x18001a342  jz      loc_18001A570
0x18001a348  mov     rax, [rcx]
0x18001a34b  mov     rax, [rax+10h]
0x18001a34f  jmp     loc_18001A56B
0x18001a354  mov     [rsp+3F0h+var_390], 0; int
0x18001a35c  mov     [rsp+3F0h+var_398], 0; int
0x18001a364  mov     [rsp+3F0h+var_3A0], 0; int
0x18001a36c  mov     [rsp+3F0h+var_3A8], 1; int
0x18001a374  mov     [rsp+3F0h+var_3B0], 0; int
0x18001a37c  lea     rsi, psz; "S-1-5-18"
0x18001a383  mov     [rsp+3F0h+var_3B8], rsi; unsigned __int16 *
0x18001a388  lea     rax, [rbp+2F0h+var_290]
0x18001a38c  mov     [rsp+3F0h+var_3C0], rax; unsigned __int16 *
0x18001a391  lea     rax, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe "
0x18001a398  mov     [rsp+3F0h+var_3C8], rax; unsigned __int16 *
0x18001a39d  mov     [rsp+3F0h+var_3D0], rdi; unsigned __int16 *
0x18001a3a2  lea     r9, [rbp+2F0h+var_360]; int
0x18001a3a6  lea     r8, [rsp+3F0h+var_378]; int
0x18001a3ab  lea     rdx, [rbp+2F0h+var_370]; int
0x18001a3af  lea     rcx, [rbp+2F0h+var_358]; int
0x18001a3b3  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x18001a3b8  mov     ebx, eax
0x18001a3ba  mov     [rsp+3F0h+var_380], eax
0x18001a3be  test    eax, eax
0x18001a3c0  jns     short loc_18001A3FA
0x18001a3c2  lea     rcx, [rbp+2F0h+var_350]; this
0x18001a3c6  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001a3cb  nop
0x18001a3cc  lea     rcx, [rbp+2F0h+var_368]
0x18001a3d0  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a3d5  nop
0x18001a3d6  lea     rcx, [rbp+2F0h+var_360]
0x18001a3da  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a3df  nop
0x18001a3e0  lea     rcx, [rsp+3F0h+var_378]
0x18001a3e5  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a3ea  nop
0x18001a3eb  lea     rcx, [rbp+2F0h+var_370]
0x18001a3ef  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a3f4  nop
0x18001a3f5  jmp     loc_18001A33B
0x18001a3fa  mov     rdi, qword ptr [rbp+2F0h+var_370]
0x18001a3fe  mov     rbx, [rdi]
0x18001a401  lea     rcx, [rbp+2F0h+pvarg]; pvarg
0x18001a405  call    cs:__imp_VariantInit
0x18001a40b  movups  xmm8, xmmword ptr [rbp+2F0h+pvarg]
0x18001a410  movsd   xmm9, qword ptr [rbp+2F0h+pvarg+10h]
0x18001a416  lea     rcx, [rbp+2F0h+var_320]; pvarg
0x18001a41a  call    cs:__imp_VariantInit
0x18001a420  movups  xmm10, xmmword ptr [rbp+2F0h+var_320]
0x18001a425  movsd   xmm11, qword ptr [rbp+2F0h+var_320+10h]
0x18001a42b  mov     eax, 8
0x18001a430  mov     word ptr [rbp+2F0h+var_338], ax
0x18001a434  mov     rcx, rsi; psz
0x18001a437  call    cs:__imp_SysAllocString
0x18001a43d  mov     qword ptr [rbp+2F0h+var_338+8], rax
0x18001a441  test    rax, rax
0x18001a444  jz      loc_18001A5B7
0x18001a44a  mov     rsi, [rbx+88h]
0x18001a451  movups  xmm6, xmmword ptr [rbp+2F0h+var_338]
0x18001a455  movsd   xmm7, qword ptr [rbp+2F0h+var_338+10h]
0x18001a45a  mov     rbx, qword ptr [rsp+3F0h+var_378]
0x18001a45f  lea     rdx, aProvisioningIn; "Provisioning initiated session"
0x18001a466  lea     rcx, [rbp+2F0h+var_340]; this
0x18001a46a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001a46f  mov     rcx, [rax]
0x18001a472  test    rcx, rcx
0x18001a475  jz      short loc_18001A47C
0x18001a477  mov     rdx, [rcx]
0x18001a47a  jmp     short loc_18001A47E
0x18001a47c  xor     edx, edx
0x18001a47e  movaps  [rbp+2F0h+var_2F0], xmm8
0x18001a483  movsd   [rbp+2F0h+var_2E0], xmm9
0x18001a489  movaps  [rbp+2F0h+var_2D0], xmm10
0x18001a48e  movsd   [rbp+2F0h+var_2C0], xmm11
0x18001a494  movaps  [rbp+2F0h+var_2B0], xmm6
0x18001a498  movsd   [rbp+2F0h+var_2A0], xmm7
0x18001a49d  lea     rax, [rbp+2F0h+var_368]
0x18001a4a1  mov     qword ptr [rsp+3F0h+var_3B0], rax
0x18001a4a6  lea     rax, [rbp+2F0h+var_2F0]
0x18001a4aa  mov     [rsp+3F0h+var_3B8], rax
0x18001a4af  mov     dword ptr [rsp+3F0h+var_3C0], 3
0x18001a4b7  lea     rax, [rbp+2F0h+var_2D0]
0x18001a4bb  mov     [rsp+3F0h+var_3C8], rax
0x18001a4c0  lea     rax, [rbp+2F0h+var_2B0]
0x18001a4c4  mov     [rsp+3F0h+var_3D0], rax
0x18001a4c9  mov     r9d, 6
0x18001a4cf  mov     r8, rbx
0x18001a4d2  mov     rcx, rdi
0x18001a4d5  mov     rax, rsi
0x18001a4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4dd  mov     [rsp+3F0h+var_380], eax
0x18001a4e1  lea     rcx, [rbp+2F0h+var_340]; this
0x18001a4e5  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a4ea  lea     rcx, [rbp+2F0h+var_338]; pvarg
0x18001a4ee  call    cs:__imp_VariantClear
0x18001a4f4  lea     rcx, [rbp+2F0h+var_320]; pvarg
0x18001a4f8  call    cs:__imp_VariantClear
0x18001a4fe  lea     rcx, [rbp+2F0h+pvarg]; pvarg
0x18001a502  call    cs:__imp_VariantClear
0x18001a508  mov     ebx, [rsp+3F0h+var_380]
0x18001a50c  test    ebx, ebx
0x18001a50e  jns     short loc_18001A528
0x18001a510  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001a515  mov     r8, r15; char *
0x18001a518  mov     edx, [rsp+3F0h+var_380]; int
0x18001a51c  mov     rcx, rax; this
0x18001a51f  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18001a524  mov     ebx, [rsp+3F0h+var_380]
0x18001a528  lea     rcx, [rbp+2F0h+var_350]; this
0x18001a52c  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001a531  nop
0x18001a532  lea     rcx, [rbp+2F0h+var_368]
0x18001a536  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a53b  nop
0x18001a53c  lea     rcx, [rbp+2F0h+var_360]
0x18001a540  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a545  nop
0x18001a546  lea     rcx, [rsp+3F0h+var_378]
0x18001a54b  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a550  nop
0x18001a551  lea     rcx, [rbp+2F0h+var_370]
0x18001a555  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a55a  nop
0x18001a55b  mov     rcx, qword ptr [rbp+2F0h+var_358]
0x18001a55f  test    rcx, rcx
0x18001a562  jz      short loc_18001A570
0x18001a564  mov     rdx, [rcx]
0x18001a567  mov     rax, [rdx+10h]
0x18001a56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a570  mov     eax, ebx
0x18001a572  mov     rcx, [rbp+2F0h+var_80]
0x18001a579  xor     rcx, rsp; StackCookie
0x18001a57c  call    __security_check_cookie
0x18001a581  lea     r11, [rsp+3F0h+var_10]
0x18001a589  mov     rbx, [r11+28h]
0x18001a58d  mov     rsi, [r11+30h]
0x18001a591  movaps  xmm6, xmmword ptr [r11-10h]
0x18001a596  movaps  xmm7, xmmword ptr [r11-20h]
0x18001a59b  movaps  xmm8, xmmword ptr [r11-30h]
0x18001a5a0  movaps  xmm9, xmmword ptr [r11-40h]
0x18001a5a5  movaps  xmm10, xmmword ptr [r11-50h]
0x18001a5aa  movaps  xmm11, xmmword ptr [r11-60h]
0x18001a5af  mov     rsp, r11
0x18001a5b2  pop     r15
0x18001a5b4  pop     rdi
0x18001a5b5  pop     rbp
0x18001a5b6  retn
0x18001a5b7  mov     ecx, 8007000Eh; int
0x18001a5bc  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
