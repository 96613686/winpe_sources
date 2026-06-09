# ScheduleDeviceEnrollerOnLogin

- ea: `0x1800635d4`
- end: `0x180063b60`
- name: `ScheduleDeviceEnrollerOnLogin`
- size: `1420`
- prototype: `__int64 __fastcall(__int64, __int64, const unsigned __int16 *, int, int, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18006116c`
- `0x180064cfc`

## callees

- `0x18000efc4`
- `0x1800140d0`
- `0x180018074`
- `0x18001aec8`
- `0x18002e570`
- `0x18003708c`
- `0x1800434d0`
- `0x180043544`
- `0x180060974`
- `0x1800613ac`
- `0x1800635d4`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180063b16`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180063b16`
- `OLEAUT32!__imp_SysFreeString` at `0x1800638dd`
- `OLEAUT32!__imp_SysFreeString` at `0x180063a39`
- `OLEAUT32!__imp_SysFreeString` at `0x1800638dd`
- `OLEAUT32!__imp_SysFreeString` at `0x180063a39`
- `OLEAUT32!__imp_VariantInit` at `0x1800637f7`
- `OLEAUT32!__imp_VariantInit` at `0x18006380a`
- `OLEAUT32!__imp_VariantInit` at `0x18006381f`
- `OLEAUT32!__imp_VariantInit` at `0x18006392f`
- `OLEAUT32!__imp_VariantInit` at `0x180063944`
- `OLEAUT32!__imp_VariantInit` at `0x180063972`
- `OLEAUT32!__imp_VariantInit` at `0x1800637f7`
- `OLEAUT32!__imp_VariantInit` at `0x18006380a`
- `OLEAUT32!__imp_VariantInit` at `0x18006381f`
- `OLEAUT32!__imp_VariantInit` at `0x18006392f`
- `OLEAUT32!__imp_VariantInit` at `0x180063944`
- `OLEAUT32!__imp_VariantInit` at `0x180063972`

## string_xrefs

- `0x180063987`: `Login Schedule created by enrollment client`
- `0x1800636c6`: `%windir%\system32\deviceenroller.exe `
- `0x18006362a`: `ScheduleDeviceEnrollerOnLogin`
- `0x180063aa8`: `ScheduleDeviceEnrollerOnLogin`
- `0x18006382a`: `First Login Schedule created by enrollment client`

## pseudocode

```c
__int64 __fastcall ScheduleDeviceEnrollerOnLogin(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        int a4,
        int a5,
        int a6)
{
  unsigned int v10; // ebx
  int v11; // edi
  const unsigned __int16 *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 (__fastcall *v15)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rsi
  __int128 v16; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v18; // xmm8
  IRecordInfo *v19; // xmm9_8
  __int128 v20; // xmm10
  __int64 v21; // rdi
  IRecordInfo *v22; // xmm11_8
  _bstr_t *v23; // rax
  __int64 v24; // rdx
  int v25; // eax
  BSTR *v26; // rbx
  BSTR v27; // rcx
  VARIANTARG *p_pvarg; // rcx
  __int64 (__fastcall *v29)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // r15
  __int128 v30; // xmm8
  IRecordInfo *v31; // xmm9_8
  IRecordInfo *v32; // xmm11_8
  __int128 v33; // xmm10
  VARIANTARG *v34; // rax
  int v35; // esi
  __int128 v36; // xmm6
  __int64 v37; // r14
  IRecordInfo *v38; // xmm7_8
  _bstr_t *v39; // rax
  __int64 v40; // rdx
  int v41; // eax
  BSTR *v42; // rbx
  BSTR v43; // rcx
  CEnrollmentLogger *Logger; // rax
  __int64 v46; // [rsp+78h] [rbp-90h] BYREF
  __int64 v47; // [rsp+80h] [rbp-88h] BYREF
  void *Block; // [rsp+88h] [rbp-80h] BYREF
  __int64 v49; // [rsp+90h] [rbp-78h] BYREF
  _QWORD v50[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-50h] BYREF
  __int64 (__fastcall ***v54)(_QWORD, GUID *, __int64 *); // [rsp+C0h] [rbp-48h] BYREF
  __int64 v55; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v56; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG v57; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+F0h] [rbp-18h] BYREF
  VARIANTARG v59; // [rsp+108h] [rbp+0h] BYREF
  __int128 v60; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v61; // [rsp+138h] [rbp+30h]
  __int128 v62; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v63; // [rsp+158h] [rbp+50h]
  __int128 v64; // [rsp+168h] [rbp+60h] BYREF
  IRecordInfo *v65; // [rsp+178h] [rbp+70h]
  _QWORD v66[2]; // [rsp+188h] [rbp+80h] BYREF
  _BYTE v67[136]; // [rsp+198h] [rbp+90h] BYREF

  a6 = 0;
  v66[0] = "ScheduleDeviceEnrollerOnLogin";
  v66[1] = &a6;
  LODWORD(v46) = 0;
  a6 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v46, a2);
  v10 = a6;
  if ( (int)(a6 + 0x80000000) < 0 || a6 == -2147417850 )
  {
    v11 = 1;
    v56 = 0;
    v12 = L"S-1-5-32-545";
    v50[0] = 0;
    v47 = 0;
    if ( a3 )
      v12 = a3;
    v55 = 0;
    v49 = 0;
    v54 = 0;
    v53 = 0;
    v52 = 0;
    v51 = 0;
    a6 = CreateTask(&v56, v50, &v47, &v55, a1, L"%windir%\\system32\\deviceenroller.exe ", a2, v12, a4, 0, 1, 1, 1);
    if ( a6 >= 0 )
    {
      a6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v47 + 72LL))(v47, &v49);
      if ( a6 >= 0 )
      {
        a6 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v49 + 80LL))(v49, 9, &v54);
        if ( a6 >= 0 )
        {
          a6 = (**v54)(v54, &IID_ILogonTrigger, &v53);
          if ( a6 >= 0 )
          {
            a6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v53 + 80LL))(v53, &v51);
            if ( a6 >= 0 )
            {
              a6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v51 + 96LL))(v51, 0);
              if ( a6 >= 0 )
              {
                a6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v47 + 80LL))(v47, v49);
                if ( a6 >= 0 )
                {
                  v13 = v50[0];
                  v14 = *(_QWORD *)v50[0];
                  if ( a5 )
                  {
                    v15 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v14 + 136);
                    VariantInit(&pvarg);
                    v16 = *(_OWORD *)&pvarg.vt;
                    pRecInfo = pvarg.pRecInfo;
                    VariantInit(&v57);
                    v18 = *(_OWORD *)&v57.vt;
                    v19 = v57.pRecInfo;
                    VariantInit(&v59);
                    v20 = *(_OWORD *)&v59.vt;
                    v21 = v47;
                    v22 = v59.pRecInfo;
                    v23 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"First Login Schedule created by enrollment client");
                    if ( *(_QWORD *)v23 )
                      v24 = **(_QWORD **)v23;
                    else
                      v24 = 0;
                    v60 = v16;
                    v61 = pRecInfo;
                    v62 = v18;
                    v63 = v19;
                    v64 = v20;
                    v65 = v22;
                    v25 = v15(v13, v24, v21, 6, &v64, &v62, 3, &v60, &v52);
                    v26 = (BSTR *)Block;
                    a6 = v25;
                    if ( Block )
                    {
                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v26 )
                      {
                        if ( *v26 )
                        {
                          SysFreeString(*v26);
                          *v26 = 0;
                        }
                        v27 = v26[1];
                        if ( v27 )
                        {
                          operator delete(v27);
                          v26[1] = 0;
                        }
                        operator delete(v26);
                      }
                      Block = 0;
                    }
                    _variant_t::~_variant_t((_variant_t *)&v59);
                    _variant_t::~_variant_t((_variant_t *)&v57);
                    p_pvarg = &pvarg;
                  }
                  else
                  {
                    v29 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v14 + 136);
                    VariantInit(&v57);
                    v30 = *(_OWORD *)&v57.vt;
                    v31 = v57.pRecInfo;
                    VariantInit(&pvarg);
                    v32 = pvarg.pRecInfo;
                    v33 = *(_OWORD *)&pvarg.vt;
                    if ( a3 )
                    {
                      v34 = (VARIANTARG *)_variant_t::_variant_t((_variant_t *)v67, a3);
                      v35 = 0;
                    }
                    else
                    {
                      VariantInit(&v59);
                      v34 = &v59;
                      v11 = 0;
                      v35 = 2;
                    }
                    v36 = *(_OWORD *)&v34->vt;
                    v37 = v47;
                    v38 = v34->pRecInfo;
                    v39 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"Login Schedule created by enrollment client");
                    if ( *(_QWORD *)v39 )
                      v40 = **(_QWORD **)v39;
                    else
                      v40 = 0;
                    v64 = v30;
                    v65 = v31;
                    v62 = v33;
                    v63 = v32;
                    v60 = v36;
                    v61 = v38;
                    v41 = v29(v13, v40, v37, 6, &v60, &v62, 3, &v64, &v52);
                    v42 = (BSTR *)Block;
                    a6 = v41;
                    if ( Block )
                    {
                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v42 )
                      {
                        if ( *v42 )
                        {
                          SysFreeString(*v42);
                          *v42 = 0;
                        }
                        v43 = v42[1];
                        if ( v43 )
                        {
                          operator delete(v43);
                          v42[1] = 0;
                        }
                        operator delete(v42);
                      }
                      Block = 0;
                    }
                    if ( v35 )
                      _variant_t::~_variant_t((_variant_t *)&v59);
                    if ( v11 )
                      _variant_t::~_variant_t((_variant_t *)v67);
                    _variant_t::~_variant_t((_variant_t *)&pvarg);
                    p_pvarg = &v57;
                  }
                  _variant_t::~_variant_t((_variant_t *)p_pvarg);
                  if ( a6 < 0 )
                  {
                    Logger = CEnrollmentLogger::GetLogger();
                    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, a6, "ScheduleDeviceEnrollerOnLogin");
                  }
                }
              }
            }
          }
        }
      }
    }
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v51);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v52);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v53);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v54);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v49);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v55);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v47);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v50);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v56);
    v10 = a6;
  }
  if ( (_DWORD)v46 )
    CoUninitialize();
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v66);
  return v10;
}

```

## disassembly

```asm
0x1800635d4  mov     rax, rsp
0x1800635d7  push    rbp
0x1800635d8  push    rbx
0x1800635d9  push    rsi
0x1800635da  push    rdi
0x1800635db  push    r12
0x1800635dd  push    r13
0x1800635df  push    r14
0x1800635e1  push    r15
0x1800635e3  lea     rbp, [rax-158h]
0x1800635ea  sub     rsp, 218h
0x1800635f1  movaps  xmmword ptr [rax-58h], xmm6
0x1800635f5  mov     r12, rcx
0x1800635f8  movaps  xmmword ptr [rax-68h], xmm7
0x1800635fc  lea     rcx, [rsp+250h+var_1E0]; this
0x180063601  movaps  xmmword ptr [rax-78h], xmm8
0x180063606  xor     r13d, r13d
0x180063609  movaps  xmmword ptr [rax-88h], xmm9
0x180063611  mov     r14d, r9d
0x180063614  movaps  xmmword ptr [rax-98h], xmm10
0x18006361c  mov     rsi, r8
0x18006361f  movaps  xmmword ptr [rax-0A8h], xmm11
0x180063627  mov     r15, rdx
0x18006362a  lea     rax, aScheduledevice; "ScheduleDeviceEnrollerOnLogin"
0x180063631  mov     [rbp+150h+arg_28], r13d
0x180063638  mov     [rbp+150h+var_D0], rax
0x18006363f  lea     rax, [rbp+150h+arg_28]
0x180063646  mov     [rbp+150h+var_C8], rax
0x18006364d  mov     dword ptr [rsp+250h+var_1E0], r13d
0x180063652  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x180063657  mov     ecx, 80000000h
0x18006365c  mov     [rbp+150h+arg_28], eax
0x180063662  mov     ebx, eax
0x180063664  add     eax, ecx
0x180063666  test    ecx, eax
0x180063668  jnz     short loc_180063676
0x18006366a  cmp     ebx, 80010106h
0x180063670  jnz     loc_180063B0F
0x180063676  mov     edi, 1
0x18006367b  mov     [rbp+150h+var_188], r13
0x18006367f  mov     [rsp+250h+var_1F0], edi
0x180063683  lea     rax, aS1532545; "S-1-5-32-545"
0x18006368a  mov     [rsp+250h+var_1F8], edi
0x18006368e  lea     r9, [rbp+150h+var_190]
0x180063692  mov     [rsp+250h+var_200], edi
0x180063696  lea     r8, [rsp+250h+var_1D8]
0x18006369b  mov     [rsp+250h+var_208], r13d
0x1800636a0  lea     rdx, [rbp+150h+var_1C0]
0x1800636a4  mov     [rsp+250h+var_210], r14d
0x1800636a9  lea     rcx, [rbp+150h+var_188]
0x1800636ad  test    rsi, rsi
0x1800636b0  mov     [rbp+150h+var_1C0], r13
0x1800636b4  mov     [rsp+250h+var_1D8], r13
0x1800636b9  cmovnz  rax, rsi
0x1800636bd  mov     [rbp+150h+var_190], r13
0x1800636c1  mov     [rsp+250h+var_218], rax
0x1800636c6  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x1800636cd  mov     [rsp+250h+var_220], r15
0x1800636d2  mov     [rsp+250h+var_228], rax
0x1800636d7  mov     [rsp+250h+var_230], r12
0x1800636dc  mov     [rbp+150h+var_1C8], r13
0x1800636e0  mov     [rbp+150h+var_198], r13
0x1800636e4  mov     [rbp+150h+var_1A0], r13
0x1800636e8  mov     [rbp+150h+var_1A8], r13
0x1800636ec  mov     [rbp+150h+var_1B0], r13
0x1800636f0  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x1800636f5  mov     [rbp+150h+arg_28], eax
0x1800636fb  test    eax, eax
0x1800636fd  js      loc_180063AB7
0x180063703  mov     rcx, [rsp+250h+var_1D8]
0x180063708  lea     rdx, [rbp+150h+var_1C8]
0x18006370c  mov     rax, [rcx]
0x18006370f  mov     rax, [rax+48h]
0x180063713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063718  mov     [rbp+150h+arg_28], eax
0x18006371e  test    eax, eax
0x180063720  js      loc_180063AB7
0x180063726  mov     rcx, [rbp+150h+var_1C8]
0x18006372a  lea     r8, [rbp+150h+var_198]
0x18006372e  lea     edx, [rdi+8]
0x180063731  mov     rax, [rcx]
0x180063734  mov     rax, [rax+50h]
0x180063738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006373d  mov     [rbp+150h+arg_28], eax
0x180063743  test    eax, eax
0x180063745  js      loc_180063AB7
0x18006374b  mov     rcx, [rbp+150h+var_198]
0x18006374f  lea     r8, [rbp+150h+var_1A0]
0x180063753  lea     rdx, IID_ILogonTrigger
0x18006375a  mov     rax, [rcx]
0x18006375d  mov     rax, [rax]
0x180063760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063765  mov     [rbp+150h+arg_28], eax
0x18006376b  test    eax, eax
0x18006376d  js      loc_180063AB7
0x180063773  mov     rcx, [rbp+150h+var_1A0]
0x180063777  lea     rdx, [rbp+150h+var_1B0]
0x18006377b  mov     rax, [rcx]
0x18006377e  mov     rax, [rax+50h]
0x180063782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063787  mov     [rbp+150h+arg_28], eax
0x18006378d  test    eax, eax
0x18006378f  js      loc_180063AB7
0x180063795  mov     rcx, [rbp+150h+var_1B0]
0x180063799  xor     edx, edx
0x18006379b  mov     rax, [rcx]
0x18006379e  mov     rax, [rax+60h]
0x1800637a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800637a7  mov     [rbp+150h+arg_28], eax
0x1800637ad  test    eax, eax
0x1800637af  js      loc_180063AB7
0x1800637b5  mov     rcx, [rsp+250h+var_1D8]
0x1800637ba  mov     rdx, [rbp+150h+var_1C8]
0x1800637be  mov     rax, [rcx]
0x1800637c1  mov     rax, [rax+50h]
0x1800637c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800637ca  mov     [rbp+150h+arg_28], eax
0x1800637d0  test    eax, eax
0x1800637d2  js      loc_180063AB7
0x1800637d8  mov     rbx, [rbp+150h+var_1C0]
0x1800637dc  mov     rax, [rbx]
0x1800637df  cmp     [rbp+150h+arg_20], r13d
0x1800637e6  jz      loc_180063924
0x1800637ec  mov     rsi, [rax+88h]
0x1800637f3  lea     rcx, [rbp+150h+pvarg]; pvarg
0x1800637f7  call    cs:__imp_VariantInit
0x1800637fd  movups  xmm6, xmmword ptr [rbp+150h+pvarg]
0x180063801  lea     rcx, [rbp+150h+var_180]; pvarg
0x180063805  movsd   xmm7, qword ptr [rbp+150h+pvarg+10h]
0x18006380a  call    cs:__imp_VariantInit
0x180063810  movups  xmm8, xmmword ptr [rbp+150h+var_180]
0x180063815  lea     rcx, [rbp+150h+var_150]; pvarg
0x180063819  movsd   xmm9, qword ptr [rbp+150h+var_180+10h]
0x18006381f  call    cs:__imp_VariantInit
0x180063825  movups  xmm10, xmmword ptr [rbp+150h+var_150]
0x18006382a  lea     rdx, aFirstLoginSche; "First Login Schedule created by enrollm"...
0x180063831  mov     rdi, [rsp+250h+var_1D8]
0x180063836  movsd   xmm11, qword ptr [rbp+150h+var_150+10h]
0x18006383c  lea     rcx, [rbp+150h+Block]; this
0x180063840  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180063845  mov     rdx, [rax]
0x180063848  test    rdx, rdx
0x18006384b  jz      short loc_180063852
0x18006384d  mov     rdx, [rdx]
0x180063850  jmp     short loc_180063855
0x180063852  mov     rdx, r13
0x180063855  lea     rax, [rbp+150h+var_1A8]
0x180063859  movaps  [rbp+150h+var_130], xmm6
0x18006385d  mov     qword ptr [rsp+250h+var_210], rax
0x180063862  mov     r9d, 6
0x180063868  lea     rax, [rbp+150h+var_130]
0x18006386c  movsd   [rbp+150h+var_120], xmm7
0x180063871  mov     [rsp+250h+var_218], rax
0x180063876  mov     r8, rdi
0x180063879  lea     rax, [rbp+150h+var_110]
0x18006387d  mov     dword ptr [rsp+250h+var_220], 3
0x180063885  mov     [rsp+250h+var_228], rax
0x18006388a  mov     rcx, rbx
0x18006388d  lea     rax, [rbp+150h+var_F0]
0x180063891  movaps  [rbp+150h+var_110], xmm8
0x180063896  mov     [rsp+250h+var_230], rax
0x18006389b  mov     rax, rsi
0x18006389e  movsd   [rbp+150h+var_100], xmm9
0x1800638a4  movaps  [rbp+150h+var_F0], xmm10
0x1800638a9  movsd   [rbp+150h+var_E0], xmm11
0x1800638af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800638b4  mov     rbx, [rbp+150h+Block]
0x1800638b8  mov     [rbp+150h+arg_28], eax
0x1800638be  test    rbx, rbx
0x1800638c1  jz      short loc_180063909
0x1800638c3  or      eax, 0FFFFFFFFh
0x1800638c6  lock xadd [rbx+10h], eax
0x1800638cb  cmp     eax, 1
0x1800638ce  jnz     short loc_180063905
0x1800638d0  test    rbx, rbx
0x1800638d3  jz      short loc_180063905
0x1800638d5  mov     rcx, [rbx]; bstrString
0x1800638d8  test    rcx, rcx
0x1800638db  jz      short loc_1800638E6
0x1800638dd  call    cs:__imp_SysFreeString
0x1800638e3  mov     [rbx], r13
0x1800638e6  mov     rcx, [rbx+8]; Block
0x1800638ea  test    rcx, rcx
0x1800638ed  jz      short loc_1800638F8
0x1800638ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800638f4  mov     [rbx+8], r13
0x1800638f8  mov     edx, 18h
0x1800638fd  mov     rcx, rbx; Block
0x180063900  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063905  mov     [rbp+150h+Block], r13
0x180063909  lea     rcx, [rbp+150h+var_150]; this
0x18006390d  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180063912  lea     rcx, [rbp+150h+var_180]; this
0x180063916  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006391b  lea     rcx, [rbp+150h+pvarg]
0x18006391f  jmp     loc_180063A8F
0x180063924  mov     r15, [rax+88h]
0x18006392b  lea     rcx, [rbp+150h+var_180]; pvarg
0x18006392f  call    cs:__imp_VariantInit
0x180063935  movups  xmm8, xmmword ptr [rbp+150h+var_180]
0x18006393a  lea     rcx, [rbp+150h+pvarg]; pvarg
0x18006393e  movsd   xmm9, qword ptr [rbp+150h+var_180+10h]
0x180063944  call    cs:__imp_VariantInit
0x18006394a  movsd   xmm11, qword ptr [rbp+150h+pvarg+10h]
0x180063950  movups  xmm10, xmmword ptr [rbp+150h+pvarg]
0x180063955  test    rsi, rsi
0x180063958  jz      short loc_18006396E
0x18006395a  mov     rdx, rsi; unsigned __int16 *
0x18006395d  lea     rcx, [rbp+150h+var_C0]; this
0x180063964  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180063969  mov     esi, r13d
0x18006396c  jmp     short loc_180063984
0x18006396e  lea     rcx, [rbp+150h+var_150]; pvarg
0x180063972  call    cs:__imp_VariantInit
0x180063978  lea     rax, [rbp+150h+var_150]
0x18006397c  mov     edi, r13d
0x18006397f  mov     esi, 2
0x180063984  movups  xmm6, xmmword ptr [rax]
0x180063987  lea     rdx, aLoginScheduleC; "Login Schedule created by enrollment cl"...
0x18006398e  mov     r14, [rsp+250h+var_1D8]
0x180063993  movsd   xmm7, qword ptr [rax+10h]
0x180063998  lea     rcx, [rbp+150h+Block]; this
0x18006399c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800639a1  mov     rcx, [rax]
0x1800639a4  test    rcx, rcx
0x1800639a7  jz      short loc_1800639AE
0x1800639a9  mov     rdx, [rcx]
0x1800639ac  jmp     short loc_1800639B1
0x1800639ae  mov     rdx, r13
0x1800639b1  lea     rax, [rbp+150h+var_1A8]
0x1800639b5  movaps  [rbp+150h+var_F0], xmm8
0x1800639ba  mov     qword ptr [rsp+250h+var_210], rax
0x1800639bf  mov     r9d, 6
0x1800639c5  lea     rax, [rbp+150h+var_F0]
0x1800639c9  movsd   [rbp+150h+var_E0], xmm9
0x1800639cf  mov     [rsp+250h+var_218], rax
0x1800639d4  mov     r8, r14
0x1800639d7  lea     rax, [rbp+150h+var_110]
0x1800639db  mov     dword ptr [rsp+250h+var_220], 3
0x1800639e3  mov     [rsp+250h+var_228], rax
0x1800639e8  mov     rcx, rbx
0x1800639eb  lea     rax, [rbp+150h+var_130]
0x1800639ef  movaps  [rbp+150h+var_110], xmm10
0x1800639f4  mov     [rsp+250h+var_230], rax
0x1800639f9  mov     rax, r15
0x1800639fc  movsd   [rbp+150h+var_100], xmm11
0x180063a02  movaps  [rbp+150h+var_130], xmm6
0x180063a06  movsd   [rbp+150h+var_120], xmm7
0x180063a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a10  mov     rbx, [rbp+150h+Block]
0x180063a14  mov     [rbp+150h+arg_28], eax
0x180063a1a  test    rbx, rbx
0x180063a1d  jz      short loc_180063A65
0x180063a1f  or      eax, 0FFFFFFFFh
0x180063a22  lock xadd [rbx+10h], eax
0x180063a27  cmp     eax, 1
0x180063a2a  jnz     short loc_180063A61
0x180063a2c  test    rbx, rbx
0x180063a2f  jz      short loc_180063A61
0x180063a31  mov     rcx, [rbx]; bstrString
0x180063a34  test    rcx, rcx
0x180063a37  jz      short loc_180063A42
0x180063a39  call    cs:__imp_SysFreeString
0x180063a3f  mov     [rbx], r13
0x180063a42  mov     rcx, [rbx+8]; Block
0x180063a46  test    rcx, rcx
0x180063a49  jz      short loc_180063A54
0x180063a4b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063a50  mov     [rbx+8], r13
0x180063a54  mov     edx, 18h
0x180063a59  mov     rcx, rbx; Block
0x180063a5c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063a61  mov     [rbp+150h+Block], r13
0x180063a65  test    esi, esi
0x180063a67  jz      short loc_180063A72
0x180063a69  lea     rcx, [rbp+150h+var_150]; this
0x180063a6d  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180063a72  test    edi, edi
0x180063a74  jz      short loc_180063A82
0x180063a76  lea     rcx, [rbp+150h+var_C0]; this
0x180063a7d  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180063a82  lea     rcx, [rbp+150h+pvarg]; this
0x180063a86  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180063a8b  lea     rcx, [rbp+150h+var_180]; this
0x180063a8f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180063a94  cmp     [rbp+150h+arg_28], r13d
0x180063a9b  jge     short loc_180063AB7
0x180063a9d  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180063aa2  mov     edx, [rbp+150h+arg_28]; int
0x180063aa8  lea     r8, aScheduledevice; "ScheduleDeviceEnrollerOnLogin"
0x180063aaf  mov     rcx, rax; this
0x180063ab2  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x180063ab7  lea     rcx, [rbp+150h+var_1B0]
0x180063abb  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180063ac0  lea     rcx, [rbp+150h+var_1A8]
0x180063ac4  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180063ac9  lea     rcx, [rbp+150h+var_1A0]
0x180063acd  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180063ad2  lea     rcx, [rbp+150h+var_198]
0x180063ad6  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
  ... truncated ...
```
