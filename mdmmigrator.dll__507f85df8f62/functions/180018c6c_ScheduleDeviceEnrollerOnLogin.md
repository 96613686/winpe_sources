# ScheduleDeviceEnrollerOnLogin

- ea: `0x180018c6c`
- end: `0x1800194b5`
- name: `ScheduleDeviceEnrollerOnLogin`
- size: `2121`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a1c4`

## callees

- `0x18000aa2c`
- `0x18000aab8`
- `0x18000ab84`
- `0x1800117c8`
- `0x180011d5c`
- `0x180012ed4`
- `0x180018c6c`
- `0x18001dce8`
- `0x18001e264`
- `0x180020010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180019256`
- `OLEAUT32!__imp_SysAllocString` at `0x180019256`
- `OLEAUT32!__imp_VariantInit` at `0x18001912b`
- `OLEAUT32!__imp_VariantInit` at `0x18001913e`
- `OLEAUT32!__imp_VariantInit` at `0x180019153`
- `OLEAUT32!__imp_VariantInit` at `0x18001921f`
- `OLEAUT32!__imp_VariantInit` at `0x180019234`
- `OLEAUT32!__imp_VariantInit` at `0x180019279`
- `OLEAUT32!__imp_VariantInit` at `0x18001912b`
- `OLEAUT32!__imp_VariantInit` at `0x18001913e`
- `OLEAUT32!__imp_VariantInit` at `0x180019153`
- `OLEAUT32!__imp_VariantInit` at `0x18001921f`
- `OLEAUT32!__imp_VariantInit` at `0x180019234`
- `OLEAUT32!__imp_VariantInit` at `0x180019279`
- `OLEAUT32!__imp_VariantClear` at `0x1800191fb`
- `OLEAUT32!__imp_VariantClear` at `0x180019205`
- `OLEAUT32!__imp_VariantClear` at `0x18001933a`
- `OLEAUT32!__imp_VariantClear` at `0x180019349`
- `OLEAUT32!__imp_VariantClear` at `0x180019353`
- `OLEAUT32!__imp_VariantClear` at `0x18001935d`
- `OLEAUT32!__imp_VariantClear` at `0x1800191fb`
- `OLEAUT32!__imp_VariantClear` at `0x180019205`
- `OLEAUT32!__imp_VariantClear` at `0x18001933a`
- `OLEAUT32!__imp_VariantClear` at `0x180019349`
- `OLEAUT32!__imp_VariantClear` at `0x180019353`
- `OLEAUT32!__imp_VariantClear` at `0x18001935d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019463`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019463`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180018ce6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180018ce6`

## string_xrefs

- `0x180019298`: `Login Schedule created by enrollment client`
- `0x180018d68`: `%windir%\system32\deviceenroller.exe `
- `0x180018ccc`: `ScheduleDeviceEnrollerOnLogin`
- `0x180019371`: `ScheduleDeviceEnrollerOnLogin`
- `0x180019169`: `First Login Schedule created by enrollment client`

## pseudocode

```c
__int64 __fastcall ScheduleDeviceEnrollerOnLogin(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5)
{
  HRESULT v8; // edi
  int v9; // ebx
  unsigned __int16 *v10; // rax
  __int64 *v11; // rdi
  __int64 (__fastcall *v12)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // r14
  __int128 v13; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v15; // xmm8
  IRecordInfo *v16; // xmm9_8
  __int128 v17; // xmm10
  IRecordInfo *v18; // xmm11_8
  __int64 v19; // rsi
  _bstr_t *v20; // rax
  __int64 v21; // rdx
  const struct std::nothrow_t *v22; // rdx
  VARIANTARG *p_pvarg; // rcx
  __int64 *v24; // r14
  __int64 v25; // r15
  __int128 v26; // xmm8
  IRecordInfo *v27; // xmm9_8
  __int128 v28; // xmm10
  IRecordInfo *v29; // xmm11_8
  VARIANTARG *v30; // rax
  char v31; // di
  __int128 v32; // xmm6
  IRecordInfo *v33; // xmm7_8
  __int64 v34; // rsi
  _bstr_t *v35; // rax
  __int64 v36; // rdx
  const struct std::nothrow_t *v37; // rdx
  CEnrollmentLogger *Logger; // rax
  int v40[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v41; // [rsp+80h] [rbp-88h] BYREF
  int v42[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v43; // [rsp+90h] [rbp-78h] BYREF
  __int64 v44; // [rsp+98h] [rbp-70h] BYREF
  __int64 v45; // [rsp+A0h] [rbp-68h] BYREF
  __int64 (__fastcall ***v46)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp-60h] BYREF
  int v47[2]; // [rsp+B0h] [rbp-58h] BYREF
  int v48[2]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v49[8]; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v50; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v51; // [rsp+E0h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v53[3]; // [rsp+110h] [rbp+8h] BYREF
  __int128 v54; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v55; // [rsp+138h] [rbp+30h]
  __int128 v56; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v57; // [rsp+158h] [rbp+50h]
  __int128 v58; // [rsp+168h] [rbp+60h] BYREF
  IRecordInfo *v59; // [rsp+178h] [rbp+70h]
  VARIANTARG v60; // [rsp+188h] [rbp+80h] BYREF
  int Task; // [rsp+270h] [rbp+168h] BYREF

  Task = 0;
  v53[0] = "ScheduleDeviceEnrollerOnLogin";
  v53[1] = &Task;
  v8 = CoInitializeEx(0, 0);
  Task = v8;
  if ( v8 < 0 )
  {
    v9 = 0;
    if ( v8 != -2147417850 )
      goto LABEL_61;
  }
  else
  {
    v9 = 1;
  }
  *(_QWORD *)v48 = 0;
  *(_QWORD *)v42 = 0;
  *(_QWORD *)v40 = 0;
  *(_QWORD *)v47 = 0;
  v41 = 0;
  v46 = 0;
  v45 = 0;
  v44 = 0;
  v43 = 0;
  v10 = L"S-1-5-32-545";
  if ( a3 )
    v10 = a3;
  Task = CreateTask(
           v48,
           (__int64 *)v42,
           v40,
           v47,
           a1,
           L"%windir%\\system32\\deviceenroller.exe ",
           a2,
           v10,
           0,
           0,
           1,
           1,
           1);
  if ( Task >= 0 )
  {
    Task = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v40 + 72LL))(*(_QWORD *)v40, &v41);
    if ( Task >= 0 )
    {
      Task = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v41 + 80LL))(v41, 9, &v46);
      if ( Task >= 0 )
      {
        Task = (**v46)(v46, &IID_ILogonTrigger, &v45);
        if ( Task >= 0 )
        {
          Task = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 80LL))(v45, &v43);
          if ( Task >= 0 )
          {
            Task = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v43 + 96LL))(v43, 0);
            if ( Task >= 0 )
            {
              Task = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v40 + 80LL))(*(_QWORD *)v40, v41);
              if ( Task >= 0 )
              {
                if ( a5 )
                {
                  v11 = *(__int64 **)v42;
                  v12 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(**(_QWORD **)v42 + 136LL);
                  VariantInit(&pvarg);
                  v13 = *(_OWORD *)&pvarg.vt;
                  pRecInfo = pvarg.pRecInfo;
                  VariantInit(&v51);
                  v15 = *(_OWORD *)&v51.vt;
                  v16 = v51.pRecInfo;
                  VariantInit(&v50);
                  v17 = *(_OWORD *)&v50.vt;
                  v18 = v50.pRecInfo;
                  v19 = *(_QWORD *)v40;
                  v20 = _bstr_t::_bstr_t((_bstr_t *)v49, L"First Login Schedule created by enrollment client");
                  if ( *(_QWORD *)v20 )
                    v21 = **(_QWORD **)v20;
                  else
                    v21 = 0;
                  v54 = v13;
                  v55 = pRecInfo;
                  v56 = v15;
                  v57 = v16;
                  v58 = v17;
                  v59 = v18;
                  Task = v12(v11, v21, v19, 6, &v58, &v56, 3, &v54, &v44);
                  _bstr_t::~_bstr_t((_bstr_t *)v49, v22);
                  VariantClear(&v50);
                  VariantClear(&v51);
                  p_pvarg = &pvarg;
                }
                else
                {
                  v24 = *(__int64 **)v42;
                  v25 = **(_QWORD **)v42;
                  VariantInit(&v50);
                  v26 = *(_OWORD *)&v50.vt;
                  v27 = v50.pRecInfo;
                  VariantInit(&v51);
                  v28 = *(_OWORD *)&v51.vt;
                  v29 = v51.pRecInfo;
                  if ( a3 )
                  {
                    pvarg.vt = 8;
                    pvarg.llVal = (LONGLONG)SysAllocString(a3);
                    if ( !pvarg.llVal )
                      _com_issue_error(-2147024882);
                    v30 = &pvarg;
                    v31 = 1;
                  }
                  else
                  {
                    VariantInit(&v60);
                    v30 = &v60;
                    v31 = 2;
                  }
                  v32 = *(_OWORD *)&v30->vt;
                  v33 = v30->pRecInfo;
                  v34 = *(_QWORD *)v40;
                  v35 = _bstr_t::_bstr_t((_bstr_t *)v49, L"Login Schedule created by enrollment client");
                  if ( *(_QWORD *)v35 )
                    v36 = **(_QWORD **)v35;
                  else
                    v36 = 0;
                  v58 = v26;
                  v59 = v27;
                  v56 = v28;
                  v57 = v29;
                  v54 = v32;
                  v55 = v33;
                  Task = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v25 + 136))(
                           v24,
                           v36,
                           v34,
                           6,
                           &v54,
                           &v56,
                           3,
                           &v58,
                           &v44);
                  _bstr_t::~_bstr_t((_bstr_t *)v49, v37);
                  if ( (v31 & 2) != 0 )
                  {
                    v31 &= ~2u;
                    VariantClear(&v60);
                  }
                  if ( (v31 & 1) != 0 )
                    VariantClear(&pvarg);
                  VariantClear(&v51);
                  p_pvarg = &v50;
                }
                VariantClear(p_pvarg);
                if ( Task >= 0 )
                {
                  if ( v43 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                }
                else
                {
                  Logger = CEnrollmentLogger::GetLogger();
                  CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Task, "ScheduleDeviceEnrollerOnLogin");
                  if ( v43 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                }
              }
              else if ( v43 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
              }
            }
            else if ( v43 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
            }
          }
          else if ( v43 )
          {
            (*(void (**)(void))(*(_QWORD *)v43 + 16LL))();
          }
        }
        else if ( v43 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        }
      }
      else if ( v43 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      }
    }
    else if ( v43 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
  }
  else if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v44);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v45);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)&v46);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v41);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v47);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v40);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v42);
  if ( *(_QWORD *)v48 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v48 + 16LL))(*(_QWORD *)v48);
  v8 = Task;
  if ( v9 )
    CoUninitialize();
LABEL_61:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v53);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180018c6c  mov     rax, rsp
0x180018c6f  mov     [rax+20h], r9d
0x180018c73  push    rbp
0x180018c74  push    rbx
0x180018c75  push    rsi
0x180018c76  push    rdi
0x180018c77  push    r12
0x180018c79  push    r13
0x180018c7b  push    r14
0x180018c7d  push    r15
0x180018c7f  lea     rbp, [rax-148h]
0x180018c86  sub     rsp, 208h
0x180018c8d  movaps  xmmword ptr [rax-58h], xmm6
0x180018c91  movaps  xmmword ptr [rax-68h], xmm7
0x180018c95  movaps  xmmword ptr [rax-78h], xmm8
0x180018c9a  movaps  xmmword ptr [rax-88h], xmm9
0x180018ca2  movaps  xmmword ptr [rax-98h], xmm10
0x180018caa  movaps  xmmword ptr [rax-0A8h], xmm11
0x180018cb2  mov     rsi, r8
0x180018cb5  mov     r14, rdx
0x180018cb8  mov     r15, rcx
0x180018cbb  xor     r12d, r12d
0x180018cbe  mov     [rbp+140h+arg_18], r12d
0x180018cc5  mov     [rbp+140h+arg_18], r12d
0x180018ccc  lea     rax, aScheduledevice; "ScheduleDeviceEnrollerOnLogin"
0x180018cd3  mov     [rbp+140h+var_138], rax
0x180018cd7  lea     rax, [rbp+140h+arg_18]
0x180018cde  mov     [rbp+140h+var_130], rax
0x180018ce2  xor     edx, edx; dwCoInit
0x180018ce4  xor     ecx, ecx; pvReserved
0x180018ce6  call    cs:__imp_CoInitializeEx
0x180018cec  mov     edi, eax
0x180018cee  mov     [rbp+140h+arg_18], eax
0x180018cf4  lea     r13d, [r12+1]
0x180018cf9  test    eax, eax
0x180018cfb  js      short loc_180018D02
0x180018cfd  mov     ebx, r13d
0x180018d00  jmp     short loc_180018D11
0x180018d02  mov     ebx, r12d
0x180018d05  cmp     edi, 80010106h
0x180018d0b  jnz     loc_180019469
0x180018d11  mov     qword ptr [rbp+140h+var_190], r12
0x180018d15  mov     qword ptr [rbp+140h+var_1C0], r12
0x180018d19  mov     qword ptr [rsp+240h+var_1D0], r12
0x180018d1e  mov     qword ptr [rbp+140h+var_198], r12
0x180018d22  mov     [rsp+240h+var_1C8], r12
0x180018d27  mov     [rbp+140h+var_1A0], r12
0x180018d2b  mov     [rbp+140h+var_1A8], r12
0x180018d2f  mov     [rbp+140h+var_1B0], r12
0x180018d33  mov     [rbp+140h+var_1B8], r12
0x180018d37  lea     rax, aS1532545; "S-1-5-32-545"
0x180018d3e  test    rsi, rsi
0x180018d41  cmovnz  rax, rsi
0x180018d45  mov     [rsp+240h+var_1E0], r13d; int
0x180018d4a  mov     [rsp+240h+var_1E8], r13d; int
0x180018d4f  mov     [rsp+240h+var_1F0], r13d; int
0x180018d54  mov     [rsp+240h+var_1F8], r12d; int
0x180018d59  mov     [rsp+240h+var_200], r12d; int
0x180018d5e  mov     [rsp+240h+var_208], rax; unsigned __int16 *
0x180018d63  mov     [rsp+240h+var_210], r14; unsigned __int16 *
0x180018d68  lea     rax, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe "
0x180018d6f  mov     [rsp+240h+var_218], rax; unsigned __int16 *
0x180018d74  mov     [rsp+240h+var_220], r15; unsigned __int16 *
0x180018d79  lea     r9, [rbp+140h+var_198]; int
0x180018d7d  lea     r8, [rsp+240h+var_1D0]; int
0x180018d82  lea     rdx, [rbp+140h+var_1C0]; int
0x180018d86  lea     rcx, [rbp+140h+var_190]; int
0x180018d8a  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180018d8f  mov     [rbp+140h+arg_18], eax
0x180018d95  test    eax, eax
0x180018d97  jns     short loc_180018DFC
0x180018d99  mov     rcx, [rbp+140h+var_1B8]
0x180018d9d  test    rcx, rcx
0x180018da0  jz      short loc_180018DAF
0x180018da2  mov     rax, [rcx]
0x180018da5  mov     rax, [rax+10h]
0x180018da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dae  nop
0x180018daf  lea     rcx, [rbp+140h+var_1B0]
0x180018db3  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018db8  nop
0x180018db9  lea     rcx, [rbp+140h+var_1A8]
0x180018dbd  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018dc2  nop
0x180018dc3  lea     rcx, [rbp+140h+var_1A0]
0x180018dc7  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018dcc  nop
0x180018dcd  lea     rcx, [rsp+240h+var_1C8]
0x180018dd2  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018dd7  nop
0x180018dd8  lea     rcx, [rbp+140h+var_198]
0x180018ddc  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018de1  nop
0x180018de2  lea     rcx, [rsp+240h+var_1D0]
0x180018de7  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018dec  nop
0x180018ded  lea     rcx, [rbp+140h+var_1C0]
0x180018df1  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018df6  nop
0x180018df7  jmp     loc_180019444
0x180018dfc  mov     rcx, qword ptr [rsp+240h+var_1D0]
0x180018e01  mov     rax, [rcx]
0x180018e04  lea     rdx, [rsp+240h+var_1C8]
0x180018e09  mov     rax, [rax+48h]
0x180018e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e12  mov     [rbp+140h+arg_18], eax
0x180018e18  test    eax, eax
0x180018e1a  jns     short loc_180018E7F
0x180018e1c  mov     rcx, [rbp+140h+var_1B8]
0x180018e20  test    rcx, rcx
0x180018e23  jz      short loc_180018E32
0x180018e25  mov     rax, [rcx]
0x180018e28  mov     rax, [rax+10h]
0x180018e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e31  nop
0x180018e32  lea     rcx, [rbp+140h+var_1B0]
0x180018e36  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018e3b  nop
0x180018e3c  lea     rcx, [rbp+140h+var_1A8]
0x180018e40  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018e45  nop
0x180018e46  lea     rcx, [rbp+140h+var_1A0]
0x180018e4a  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018e4f  nop
0x180018e50  lea     rcx, [rsp+240h+var_1C8]
0x180018e55  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018e5a  nop
0x180018e5b  lea     rcx, [rbp+140h+var_198]
0x180018e5f  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018e64  nop
0x180018e65  lea     rcx, [rsp+240h+var_1D0]
0x180018e6a  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018e6f  nop
0x180018e70  lea     rcx, [rbp+140h+var_1C0]
0x180018e74  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018e79  nop
0x180018e7a  jmp     loc_180019444
0x180018e7f  mov     rcx, [rsp+240h+var_1C8]
0x180018e84  mov     rax, [rcx]
0x180018e87  lea     r8, [rbp+140h+var_1A0]
0x180018e8b  mov     edx, 9
0x180018e90  mov     rax, [rax+50h]
0x180018e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e99  mov     [rbp+140h+arg_18], eax
0x180018e9f  test    eax, eax
0x180018ea1  jns     short loc_180018F06
0x180018ea3  mov     rcx, [rbp+140h+var_1B8]
0x180018ea7  test    rcx, rcx
0x180018eaa  jz      short loc_180018EB9
0x180018eac  mov     rax, [rcx]
0x180018eaf  mov     rax, [rax+10h]
0x180018eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018eb8  nop
0x180018eb9  lea     rcx, [rbp+140h+var_1B0]
0x180018ebd  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018ec2  nop
0x180018ec3  lea     rcx, [rbp+140h+var_1A8]
0x180018ec7  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018ecc  nop
0x180018ecd  lea     rcx, [rbp+140h+var_1A0]
0x180018ed1  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018ed6  nop
0x180018ed7  lea     rcx, [rsp+240h+var_1C8]
0x180018edc  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018ee1  nop
0x180018ee2  lea     rcx, [rbp+140h+var_198]
0x180018ee6  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018eeb  nop
0x180018eec  lea     rcx, [rsp+240h+var_1D0]
0x180018ef1  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018ef6  nop
0x180018ef7  lea     rcx, [rbp+140h+var_1C0]
0x180018efb  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018f00  nop
0x180018f01  jmp     loc_180019444
0x180018f06  mov     rcx, [rbp+140h+var_1A0]
0x180018f0a  mov     rax, [rcx]
0x180018f0d  lea     r8, [rbp+140h+var_1A8]
0x180018f11  lea     rdx, IID_ILogonTrigger
0x180018f18  mov     rax, [rax]
0x180018f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f20  mov     [rbp+140h+arg_18], eax
0x180018f26  test    eax, eax
0x180018f28  jns     short loc_180018F8D
0x180018f2a  mov     rcx, [rbp+140h+var_1B8]
0x180018f2e  test    rcx, rcx
0x180018f31  jz      short loc_180018F40
0x180018f33  mov     rax, [rcx]
0x180018f36  mov     rax, [rax+10h]
0x180018f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f3f  nop
0x180018f40  lea     rcx, [rbp+140h+var_1B0]
0x180018f44  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018f49  nop
0x180018f4a  lea     rcx, [rbp+140h+var_1A8]
0x180018f4e  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018f53  nop
0x180018f54  lea     rcx, [rbp+140h+var_1A0]
0x180018f58  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018f5d  nop
0x180018f5e  lea     rcx, [rsp+240h+var_1C8]
0x180018f63  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018f68  nop
0x180018f69  lea     rcx, [rbp+140h+var_198]
0x180018f6d  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018f72  nop
0x180018f73  lea     rcx, [rsp+240h+var_1D0]
0x180018f78  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018f7d  nop
0x180018f7e  lea     rcx, [rbp+140h+var_1C0]
0x180018f82  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018f87  nop
0x180018f88  jmp     loc_180019444
0x180018f8d  mov     rcx, [rbp+140h+var_1A8]
0x180018f91  mov     rax, [rcx]
0x180018f94  lea     rdx, [rbp+140h+var_1B8]
0x180018f98  mov     rax, [rax+50h]
0x180018f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fa1  mov     [rbp+140h+arg_18], eax
0x180018fa7  mov     rcx, [rbp+140h+var_1B8]
0x180018fab  test    eax, eax
0x180018fad  jns     short loc_18001900E
0x180018faf  test    rcx, rcx
0x180018fb2  jz      short loc_180018FC1
0x180018fb4  mov     rax, [rcx]
0x180018fb7  mov     rax, [rax+10h]
0x180018fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fc0  nop
0x180018fc1  lea     rcx, [rbp+140h+var_1B0]
0x180018fc5  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018fca  nop
0x180018fcb  lea     rcx, [rbp+140h+var_1A8]
0x180018fcf  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018fd4  nop
0x180018fd5  lea     rcx, [rbp+140h+var_1A0]
0x180018fd9  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018fde  nop
0x180018fdf  lea     rcx, [rsp+240h+var_1C8]
0x180018fe4  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018fe9  nop
0x180018fea  lea     rcx, [rbp+140h+var_198]
0x180018fee  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018ff3  nop
0x180018ff4  lea     rcx, [rsp+240h+var_1D0]
0x180018ff9  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180018ffe  nop
0x180018fff  lea     rcx, [rbp+140h+var_1C0]
0x180019003  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019008  nop
0x180019009  jmp     loc_180019444
0x18001900e  mov     rax, [rcx]
0x180019011  xor     edx, edx
0x180019013  mov     rax, [rax+60h]
0x180019017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001901c  mov     [rbp+140h+arg_18], eax
0x180019022  test    eax, eax
0x180019024  jns     short loc_180019089
0x180019026  mov     rcx, [rbp+140h+var_1B8]
0x18001902a  test    rcx, rcx
0x18001902d  jz      short loc_18001903C
0x18001902f  mov     rax, [rcx]
0x180019032  mov     rax, [rax+10h]
0x180019036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001903b  nop
0x18001903c  lea     rcx, [rbp+140h+var_1B0]
0x180019040  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019045  nop
0x180019046  lea     rcx, [rbp+140h+var_1A8]
0x18001904a  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001904f  nop
0x180019050  lea     rcx, [rbp+140h+var_1A0]
0x180019054  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019059  nop
0x18001905a  lea     rcx, [rsp+240h+var_1C8]
0x18001905f  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019064  nop
0x180019065  lea     rcx, [rbp+140h+var_198]
0x180019069  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001906e  nop
0x18001906f  lea     rcx, [rsp+240h+var_1D0]
0x180019074  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019079  nop
0x18001907a  lea     rcx, [rbp+140h+var_1C0]
0x18001907e  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019083  nop
0x180019084  jmp     loc_180019444
0x180019089  mov     rcx, qword ptr [rsp+240h+var_1D0]
0x18001908e  mov     rax, [rcx]
0x180019091  mov     rdx, [rsp+240h+var_1C8]
0x180019096  mov     rax, [rax+50h]
0x18001909a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001909f  mov     [rbp+140h+arg_18], eax
0x1800190a5  test    eax, eax
0x1800190a7  jns     short loc_18001910C
0x1800190a9  mov     rcx, [rbp+140h+var_1B8]
0x1800190ad  test    rcx, rcx
0x1800190b0  jz      short loc_1800190BF
0x1800190b2  mov     rax, [rcx]
0x1800190b5  mov     rax, [rax+10h]
0x1800190b9  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
