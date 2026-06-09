# ScheduleRenewalWork

- ea: `0x18001aa50`
- end: `0x18001b08d`
- name: `ScheduleRenewalWork`
- size: `1597`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, unsigned int, unsigned int, struct _SYSTEMTIME *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a5c8`

## callees

- `0x1800022e0`
- `0x18000aa2c`
- `0x18000aab8`
- `0x18000ab84`
- `0x1800117c8`
- `0x180011d5c`
- `0x180012b58`
- `0x180012d2c`
- `0x180012ed4`
- `0x18001aa50`
- `0x18001dce8`
- `0x18001e264`
- `0x180020010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001aec2`
- `OLEAUT32!__imp_SysAllocString` at `0x18001aec2`
- `OLEAUT32!__imp_VariantInit` at `0x18001ae8c`
- `OLEAUT32!__imp_VariantInit` at `0x18001aea1`
- `OLEAUT32!__imp_VariantInit` at `0x18001ae8c`
- `OLEAUT32!__imp_VariantInit` at `0x18001aea1`
- `OLEAUT32!__imp_VariantClear` at `0x18001af7b`
- `OLEAUT32!__imp_VariantClear` at `0x18001af85`
- `OLEAUT32!__imp_VariantClear` at `0x18001af8f`
- `OLEAUT32!__imp_VariantClear` at `0x18001af7b`
- `OLEAUT32!__imp_VariantClear` at `0x18001af85`
- `OLEAUT32!__imp_VariantClear` at `0x18001af8f`

## string_xrefs

- `0x18001ab2a`: `%windir%\system32\deviceenroller.exe `
- `0x18001aee9`: `Schedule created by enrollment client for renewal of certificate warning`

## pseudocode

```c
__int64 __fastcall ScheduleRenewalWork(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        struct _SYSTEMTIME *a5,
        unsigned __int16 *a6)
{
  __int64 v6; // rsi
  __int64 v7; // rdi
  int Task; // ebx
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, __int64); // r14
  _bstr_t *v11; // rax
  __int64 v12; // rdx
  const struct std::nothrow_t *v13; // rdx
  unsigned int v14; // r9d
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, __int64); // rdi
  _bstr_t *v17; // rax
  __int64 v18; // rdx
  const struct std::nothrow_t *v19; // rdx
  bool v20; // sf
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, __int64); // rdi
  _bstr_t *v23; // rax
  __int64 v24; // rdx
  const struct std::nothrow_t *v25; // rdx
  __int64 *v26; // rdi
  __int64 v27; // rbx
  __int128 v28; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v30; // xmm10
  IRecordInfo *v31; // xmm11_8
  __int64 (__fastcall *v32)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rsi
  __int128 v33; // xmm6
  IRecordInfo *v34; // xmm7_8
  __int64 v35; // rbx
  _bstr_t *v36; // rax
  __int64 v37; // rdx
  const struct std::nothrow_t *v38; // rdx
  CEnrollmentLogger *Logger; // rax
  int v41; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v42[8]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v43; // [rsp+88h] [rbp-80h] BYREF
  int v44[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v45; // [rsp+98h] [rbp-70h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-68h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp-60h] BYREF
  int v48[2]; // [rsp+B0h] [rbp-58h] BYREF
  int v49[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v50; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v51; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v52; // [rsp+F0h] [rbp-18h] BYREF
  int v53[2]; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v54[2]; // [rsp+100h] [rbp-8h] BYREF
  VARIANTARG pvarg; // [rsp+110h] [rbp+8h] BYREF
  __int128 v56; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v57; // [rsp+138h] [rbp+30h]
  __int128 v58; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v59; // [rsp+158h] [rbp+50h]
  __int128 v60; // [rsp+168h] [rbp+60h] BYREF
  IRecordInfo *v61; // [rsp+178h] [rbp+70h]
  unsigned __int16 v62[264]; // [rsp+188h] [rbp+80h] BYREF
  unsigned __int16 v63[264]; // [rsp+398h] [rbp+290h] BYREF
  unsigned __int16 v64[264]; // [rsp+5A8h] [rbp+4A0h] BYREF

  v6 = a4;
  v7 = a3;
  v41 = 0;
  v54[0] = "ScheduleRenewalWork";
  v54[1] = &v41;
  *(_QWORD *)v53 = 0;
  *(_QWORD *)v49 = 0;
  *(_QWORD *)v44 = 0;
  *(_QWORD *)v48 = 0;
  v46 = 0;
  v47 = 0;
  v45 = 0;
  v52 = 0;
  v43 = 0;
  *(_OWORD *)&v50.vt = 0;
  *(_OWORD *)&v51.vt = 0;
  Task = CreateTask(v53, (__int64 *)v49, v44, v48, a2, L"%windir%\\system32\\deviceenroller.exe ", a6, 0, 0, 1, 1, 1, 0);
  v41 = Task;
  if ( Task >= 0 )
  {
    Task = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v48 + 208LL))(*(_QWORD *)v48, 0xFFFFFFFFLL);
    v41 = Task;
    if ( Task >= 0 )
    {
      Task = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v44 + 72LL))(*(_QWORD *)v44, &v46);
      v41 = Task;
      if ( Task >= 0 )
      {
        Task = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v46 + 80LL))(v46, 1, &v47);
        v41 = Task;
        if ( Task >= 0 )
        {
          Task = (**v47)(v47, &IID_ITimeTrigger, &v45);
          v41 = Task;
          if ( Task >= 0 )
          {
            Task = CreateDelayTimeString(a5, v62);
            v41 = Task;
            if ( Task >= 0 )
            {
              v9 = v45;
              v10 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 120LL);
              v11 = _bstr_t::_bstr_t((_bstr_t *)v42, v62);
              v12 = *(_QWORD *)v11 ? **(_QWORD **)v11 : 0LL;
              v41 = v10(v9, v12);
              _bstr_t::~_bstr_t((_bstr_t *)v42, v13);
              Task = v41;
              if ( v41 >= 0 )
              {
                Task = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 80LL))(v45, &v43);
                v41 = Task;
                if ( Task >= 0 )
                {
                  if ( (_DWORD)v7 )
                  {
                    Task = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 96LL))(v43, 0xFFFFFFFFLL);
                    v41 = Task;
                    if ( Task < 0 )
                      goto LABEL_35;
                    v14 = v6 * v7;
                    if ( (unsigned __int64)(v6 * v7) > 0xFFFFFFFF )
                    {
                      Task = -2147024362;
                      v41 = -2147024362;
                      goto LABEL_35;
                    }
                    WORD1(v51.decVal.Lo64) = v14 % 0x3C;
                    v51.iVal = v14 / 0x3C % 0x18;
                    v51.wReserved3 = v14 / 0x3C / 0x18;
                    *(_DWORD *)&v51.vt = 0;
                    v41 = 0;
                    Task = CreateScheduleTimeString(&v51, v63);
                    v41 = Task;
                    if ( Task < 0 )
                      goto LABEL_35;
                    v15 = v43;
                    v16 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 80LL);
                    v17 = _bstr_t::_bstr_t((_bstr_t *)v42, v63);
                    if ( *(_QWORD *)v17 )
                      v18 = **(_QWORD **)v17;
                    else
                      v18 = 0;
                    v41 = v16(v15, v18);
                    _bstr_t::~_bstr_t((_bstr_t *)v42, v19);
                    Task = v41;
                    v20 = v41 < 0;
                  }
                  else
                  {
                    Task = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v43 + 96LL))(v43, 0);
                    v41 = Task;
                    v20 = Task < 0;
                  }
                  if ( !v20 )
                  {
                    WORD1(v50.decVal.Lo64) = (unsigned int)v6 % 0x3C;
                    v50.iVal = (unsigned int)v6 / 0x3C % 0x18;
                    v50.wReserved3 = (unsigned int)v6 / 0x3C / 0x18;
                    *(_DWORD *)&v50.vt = 0;
                    v41 = 0;
                    Task = CreateScheduleTimeString(&v50, v64);
                    v41 = Task;
                    if ( Task >= 0 )
                    {
                      v21 = v43;
                      v22 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 64LL);
                      v23 = _bstr_t::_bstr_t((_bstr_t *)v42, v64);
                      v24 = *(_QWORD *)v23 ? **(_QWORD **)v23 : 0LL;
                      v41 = v22(v21, v24);
                      _bstr_t::~_bstr_t((_bstr_t *)v42, v25);
                      Task = v41;
                      if ( v41 >= 0 )
                      {
                        Task = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v44 + 80LL))(
                                 *(_QWORD *)v44,
                                 v46);
                        v41 = Task;
                        if ( Task >= 0 )
                        {
                          v26 = *(__int64 **)v49;
                          v27 = **(_QWORD **)v49;
                          VariantInit(&pvarg);
                          v28 = *(_OWORD *)&pvarg.vt;
                          pRecInfo = pvarg.pRecInfo;
                          VariantInit(&v51);
                          v30 = *(_OWORD *)&v51.vt;
                          v31 = v51.pRecInfo;
                          v50.vt = 8;
                          v50.llVal = (LONGLONG)SysAllocString(L"S-1-5-18");
                          if ( !v50.llVal )
                            _com_issue_error(-2147024882);
                          v32 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v27 + 136);
                          v33 = *(_OWORD *)&v50.vt;
                          v34 = v50.pRecInfo;
                          v35 = *(_QWORD *)v44;
                          v36 = _bstr_t::_bstr_t(
                                  (_bstr_t *)v42,
                                  L"Schedule created by enrollment client for renewal of certificate warning");
                          if ( *(_QWORD *)v36 )
                            v37 = **(_QWORD **)v36;
                          else
                            v37 = 0;
                          v56 = v28;
                          v57 = pRecInfo;
                          v58 = v30;
                          v59 = v31;
                          v60 = v33;
                          v61 = v34;
                          v41 = v32(v26, v37, v35, 6, &v60, &v58, 3, &v56, &v52);
                          _bstr_t::~_bstr_t((_bstr_t *)v42, v38);
                          VariantClear(&v50);
                          VariantClear(&v51);
                          VariantClear(&pvarg);
                          Task = v41;
                          if ( v41 < 0 )
                          {
                            Logger = CEnrollmentLogger::GetLogger();
                            CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, v41, "ScheduleRenewalWork");
                            Task = v41;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_35:
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v52);
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)&v47);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v46);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v48);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v44);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v49);
  if ( *(_QWORD *)v53 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v53 + 16LL))(*(_QWORD *)v53);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v54);
  return (unsigned int)Task;
}

```

## disassembly

```asm
0x18001aa50  mov     rax, rsp
0x18001aa53  push    rbp
0x18001aa54  push    rbx
0x18001aa55  push    rsi
0x18001aa56  push    rdi
0x18001aa57  push    r14
0x18001aa59  push    r15
0x18001aa5b  lea     rbp, [rax-758h]
0x18001aa62  sub     rsp, 828h
0x18001aa69  movaps  xmmword ptr [rax-48h], xmm6
0x18001aa6d  movaps  xmmword ptr [rax-58h], xmm7
0x18001aa71  movaps  xmmword ptr [rax-68h], xmm8
0x18001aa76  movaps  xmmword ptr [rax-78h], xmm9
0x18001aa7b  movaps  xmmword ptr [rax-88h], xmm10
0x18001aa83  movaps  xmmword ptr [rax-98h], xmm11
0x18001aa8b  mov     rax, cs:__security_cookie
0x18001aa92  xor     rax, rsp
0x18001aa95  mov     [rbp+750h+var_A0], rax
0x18001aa9c  mov     esi, r9d
0x18001aa9f  mov     edi, r8d
0x18001aaa2  mov     r14, [rbp+750h+arg_20]
0x18001aaa9  mov     rax, [rbp+750h+arg_28]
0x18001aab0  xor     r15d, r15d
0x18001aab3  mov     [rsp+850h+var_7E0], r15d
0x18001aab8  lea     rcx, aSchedulerenewa; "ScheduleRenewalWork"
0x18001aabf  mov     [rbp+750h+var_758], rcx
0x18001aac3  lea     rcx, [rsp+850h+var_7E0]
0x18001aac8  mov     [rbp+750h+var_750], rcx
0x18001aacc  mov     qword ptr [rbp+750h+var_760], r15
0x18001aad0  mov     qword ptr [rbp+750h+var_7A0], r15
0x18001aad4  mov     qword ptr [rbp+750h+var_7C8], r15
0x18001aad8  mov     qword ptr [rbp+750h+var_7A8], r15
0x18001aadc  mov     [rbp+750h+var_7B8], r15
0x18001aae0  mov     [rbp+750h+var_7B0], r15
0x18001aae4  mov     [rbp+750h+var_7C0], r15
0x18001aae8  mov     [rbp+750h+var_768], r15
0x18001aaec  mov     [rbp+750h+var_7D0], r15
0x18001aaf0  xorps   xmm0, xmm0
0x18001aaf3  movups  xmmword ptr [rbp+750h+var_798], xmm0
0x18001aaf7  xorps   xmm1, xmm1
0x18001aafa  movups  xmmword ptr [rbp+750h+var_780], xmm1
0x18001aafe  mov     [rsp+850h+var_7F0], r15d; int
0x18001ab03  mov     [rsp+850h+var_7F8], 1; int
0x18001ab0b  mov     [rsp+850h+var_800], 1; int
0x18001ab13  mov     [rsp+850h+var_808], 1; int
0x18001ab1b  mov     [rsp+850h+var_810], r15d; int
0x18001ab20  mov     [rsp+850h+var_818], r15; unsigned __int16 *
0x18001ab25  mov     [rsp+850h+var_820], rax; unsigned __int16 *
0x18001ab2a  lea     rax, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe "
0x18001ab31  mov     [rsp+850h+var_828], rax; unsigned __int16 *
0x18001ab36  mov     [rsp+850h+var_830], rdx; unsigned __int16 *
0x18001ab3b  lea     r9, [rbp+750h+var_7A8]; int
0x18001ab3f  lea     r8, [rbp+750h+var_7C8]; int
0x18001ab43  lea     rdx, [rbp+750h+var_7A0]; int
0x18001ab47  lea     rcx, [rbp+750h+var_760]; int
0x18001ab4b  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x18001ab50  mov     ebx, eax
0x18001ab52  mov     [rsp+850h+var_7E0], eax
0x18001ab56  test    eax, eax
0x18001ab58  js      loc_18001AFB9
0x18001ab5e  mov     rcx, qword ptr [rbp+750h+var_7A8]
0x18001ab62  mov     rax, [rcx]
0x18001ab65  or      edx, 0FFFFFFFFh
0x18001ab68  mov     rax, [rax+0D0h]
0x18001ab6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab74  mov     ebx, eax
0x18001ab76  mov     [rsp+850h+var_7E0], eax
0x18001ab7a  test    eax, eax
0x18001ab7c  js      loc_18001AFB9
0x18001ab82  mov     rcx, qword ptr [rbp+750h+var_7C8]
0x18001ab86  mov     rax, [rcx]
0x18001ab89  lea     rdx, [rbp+750h+var_7B8]
0x18001ab8d  mov     rax, [rax+48h]
0x18001ab91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab96  mov     ebx, eax
0x18001ab98  mov     [rsp+850h+var_7E0], eax
0x18001ab9c  test    eax, eax
0x18001ab9e  js      loc_18001AFB9
0x18001aba4  mov     rcx, [rbp+750h+var_7B8]
0x18001aba8  mov     rax, [rcx]
0x18001abab  lea     r8, [rbp+750h+var_7B0]
0x18001abaf  lea     edx, [r15+1]
0x18001abb3  mov     rax, [rax+50h]
0x18001abb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abbc  mov     ebx, eax
0x18001abbe  mov     [rsp+850h+var_7E0], eax
0x18001abc2  test    eax, eax
0x18001abc4  js      loc_18001AFB9
0x18001abca  mov     rcx, [rbp+750h+var_7B0]
0x18001abce  mov     rax, [rcx]
0x18001abd1  lea     r8, [rbp+750h+var_7C0]
0x18001abd5  lea     rdx, IID_ITimeTrigger
0x18001abdc  mov     rax, [rax]
0x18001abdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abe4  mov     ebx, eax
0x18001abe6  mov     [rsp+850h+var_7E0], eax
0x18001abea  test    eax, eax
0x18001abec  js      loc_18001AFB9
0x18001abf2  lea     rdx, [rbp+750h+var_6D0]; unsigned __int16 *
0x18001abf9  mov     rcx, r14; struct _SYSTEMTIME *
0x18001abfc  call    ?CreateDelayTimeString@@YAJPEAU_SYSTEMTIME@@PEAGK@Z; CreateDelayTimeString(_SYSTEMTIME *,ushort *,ulong)
0x18001ac01  mov     ebx, eax
0x18001ac03  mov     [rsp+850h+var_7E0], eax
0x18001ac07  test    eax, eax
0x18001ac09  js      loc_18001AFB9
0x18001ac0f  mov     rbx, [rbp+750h+var_7C0]
0x18001ac13  mov     rax, [rbx]
0x18001ac16  mov     r14, [rax+78h]
0x18001ac1a  lea     rdx, [rbp+750h+var_6D0]; unsigned __int16 *
0x18001ac21  lea     rcx, [rsp+850h+var_7D8]; this
0x18001ac26  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001ac2b  mov     rdx, [rax]
0x18001ac2e  test    rdx, rdx
0x18001ac31  jz      short loc_18001AC38
0x18001ac33  mov     rdx, [rdx]
0x18001ac36  jmp     short loc_18001AC3B
0x18001ac38  mov     rdx, r15
0x18001ac3b  mov     rcx, rbx
0x18001ac3e  mov     rax, r14
0x18001ac41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac46  mov     [rsp+850h+var_7E0], eax
0x18001ac4a  lea     rcx, [rsp+850h+var_7D8]; this
0x18001ac4f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ac54  mov     ebx, [rsp+850h+var_7E0]
0x18001ac58  test    ebx, ebx
0x18001ac5a  js      loc_18001AFB9
0x18001ac60  mov     rcx, [rbp+750h+var_7C0]
0x18001ac64  mov     rax, [rcx]
0x18001ac67  lea     rdx, [rbp+750h+var_7D0]
0x18001ac6b  mov     rax, [rax+50h]
0x18001ac6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac74  mov     ebx, eax
0x18001ac76  mov     [rsp+850h+var_7E0], eax
0x18001ac7a  test    eax, eax
0x18001ac7c  js      loc_18001AFB9
0x18001ac82  mov     r14d, 88888889h
0x18001ac88  mov     rcx, [rbp+750h+var_7D0]
0x18001ac8c  test    edi, edi
0x18001ac8e  jz      loc_18001AD8A
0x18001ac94  mov     rax, [rcx]
0x18001ac97  or      edx, 0FFFFFFFFh
0x18001ac9a  mov     rax, [rax+60h]
0x18001ac9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aca3  mov     ebx, eax
0x18001aca5  mov     [rsp+850h+var_7E0], eax
0x18001aca9  test    eax, eax
0x18001acab  js      loc_18001AFB9
0x18001acb1  mov     r9, rdi
0x18001acb4  imul    r9, rsi
0x18001acb8  mov     eax, 0FFFFFFFFh
0x18001acbd  cmp     r9, rax
0x18001acc0  ja      loc_18001AD7C
0x18001acc6  mov     eax, r14d
0x18001acc9  mul     r9d
0x18001accc  mov     r8d, edx
0x18001accf  shr     r8d, 5
0x18001acd3  movzx   eax, r8w
0x18001acd7  imul    ecx, eax, 3Ch ; '<'
0x18001acda  sub     r9w, cx
0x18001acde  mov     word ptr [rbp+750h+var_780+0Ah], r9w
0x18001ace3  mov     eax, 0AAAAAAABh
0x18001ace8  mul     r8d
0x18001aceb  shr     edx, 4
0x18001acee  movzx   eax, dx
0x18001acf1  add     ax, ax
0x18001acf4  lea     ecx, [rax+rdx]
0x18001acf7  shl     cx, 3
0x18001acfb  sub     r8w, cx
0x18001acff  mov     word ptr [rbp+750h+var_780+8], r8w
0x18001ad04  mov     word ptr [rbp+750h+var_780+6], dx
0x18001ad08  mov     dword ptr [rbp+750h+var_780], r15d
0x18001ad0c  mov     [rsp+850h+var_7E0], r15d
0x18001ad11  lea     rdx, [rbp+750h+var_4C0]
0x18001ad18  lea     rcx, [rbp+750h+var_780]
0x18001ad1c  call    CreateScheduleTimeString
0x18001ad21  mov     ebx, eax
0x18001ad23  mov     [rsp+850h+var_7E0], eax
0x18001ad27  test    eax, eax
0x18001ad29  js      loc_18001AFB9
0x18001ad2f  mov     rbx, [rbp+750h+var_7D0]
0x18001ad33  mov     rax, [rbx]
0x18001ad36  mov     rdi, [rax+50h]
0x18001ad3a  lea     rdx, [rbp+750h+var_4C0]; unsigned __int16 *
0x18001ad41  lea     rcx, [rsp+850h+var_7D8]; this
0x18001ad46  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001ad4b  mov     rdx, [rax]
0x18001ad4e  test    rdx, rdx
0x18001ad51  jz      short loc_18001AD58
0x18001ad53  mov     rdx, [rdx]
0x18001ad56  jmp     short loc_18001AD5B
0x18001ad58  mov     rdx, r15
0x18001ad5b  mov     rcx, rbx
0x18001ad5e  mov     rax, rdi
0x18001ad61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad66  mov     [rsp+850h+var_7E0], eax
0x18001ad6a  lea     rcx, [rsp+850h+var_7D8]; this
0x18001ad6f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ad74  mov     ebx, [rsp+850h+var_7E0]
0x18001ad78  test    ebx, ebx
0x18001ad7a  jmp     short loc_18001ADA0
0x18001ad7c  mov     ebx, 80070216h
0x18001ad81  mov     [rsp+850h+var_7E0], ebx
0x18001ad85  jmp     loc_18001AFB9
0x18001ad8a  mov     r8, [rcx]
0x18001ad8d  xor     edx, edx
0x18001ad8f  mov     rax, [r8+60h]
0x18001ad93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad98  mov     ebx, eax
0x18001ad9a  mov     [rsp+850h+var_7E0], eax
0x18001ad9e  test    eax, eax
0x18001ada0  js      loc_18001AFB9
0x18001ada6  mov     eax, r14d
0x18001ada9  mul     esi
0x18001adab  mov     r9d, edx
0x18001adae  shr     r9d, 5
0x18001adb2  movzx   ecx, r9w
0x18001adb6  imul    r8d, ecx, 3Ch ; '<'
0x18001adba  sub     si, r8w
0x18001adbe  mov     word ptr [rbp+750h+var_798+0Ah], si
0x18001adc2  mov     eax, 0AAAAAAABh
0x18001adc7  mul     r9d
0x18001adca  shr     edx, 4
0x18001adcd  movzx   eax, dx
0x18001add0  add     ax, ax
0x18001add3  lea     ecx, [rax+rdx]
0x18001add6  shl     cx, 3
0x18001adda  sub     r9w, cx
0x18001adde  mov     word ptr [rbp+750h+var_798+8], r9w
0x18001ade3  mov     word ptr [rbp+750h+var_798+6], dx
0x18001ade7  mov     dword ptr [rbp+750h+var_798], r15d
0x18001adeb  mov     [rsp+850h+var_7E0], r15d
0x18001adf0  lea     rdx, [rbp+750h+var_2B0]
0x18001adf7  lea     rcx, [rbp+750h+var_798]
0x18001adfb  call    CreateScheduleTimeString
0x18001ae00  mov     ebx, eax
0x18001ae02  mov     [rsp+850h+var_7E0], eax
0x18001ae06  test    eax, eax
0x18001ae08  js      loc_18001AFB9
0x18001ae0e  mov     rbx, [rbp+750h+var_7D0]
0x18001ae12  mov     rax, [rbx]
0x18001ae15  mov     rdi, [rax+40h]
0x18001ae19  lea     rdx, [rbp+750h+var_2B0]; unsigned __int16 *
0x18001ae20  lea     rcx, [rsp+850h+var_7D8]; this
0x18001ae25  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001ae2a  mov     rdx, [rax]
0x18001ae2d  test    rdx, rdx
0x18001ae30  jz      short loc_18001AE37
0x18001ae32  mov     rdx, [rdx]
0x18001ae35  jmp     short loc_18001AE3A
0x18001ae37  mov     rdx, r15
0x18001ae3a  mov     rcx, rbx
0x18001ae3d  mov     rax, rdi
0x18001ae40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae45  mov     [rsp+850h+var_7E0], eax
0x18001ae49  lea     rcx, [rsp+850h+var_7D8]; this
0x18001ae4e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ae53  mov     ebx, [rsp+850h+var_7E0]
0x18001ae57  test    ebx, ebx
0x18001ae59  js      loc_18001AFB9
0x18001ae5f  mov     rcx, qword ptr [rbp+750h+var_7C8]
0x18001ae63  mov     rax, [rcx]
0x18001ae66  mov     rdx, [rbp+750h+var_7B8]
0x18001ae6a  mov     rax, [rax+50h]
0x18001ae6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae73  mov     ebx, eax
0x18001ae75  mov     [rsp+850h+var_7E0], eax
0x18001ae79  test    eax, eax
0x18001ae7b  js      loc_18001AFB9
0x18001ae81  mov     rdi, qword ptr [rbp+750h+var_7A0]
0x18001ae85  mov     rbx, [rdi]
0x18001ae88  lea     rcx, [rbp+750h+pvarg]; pvarg
0x18001ae8c  call    cs:__imp_VariantInit
0x18001ae92  movups  xmm8, xmmword ptr [rbp+750h+pvarg]
0x18001ae97  movsd   xmm9, qword ptr [rbp+750h+pvarg+10h]
0x18001ae9d  lea     rcx, [rbp+750h+var_780]; pvarg
0x18001aea1  call    cs:__imp_VariantInit
0x18001aea7  movups  xmm10, xmmword ptr [rbp+750h+var_780]
0x18001aeac  movsd   xmm11, qword ptr [rbp+750h+var_780+10h]
0x18001aeb2  mov     eax, 8
0x18001aeb7  mov     word ptr [rbp+750h+var_798], ax
0x18001aebb  lea     rcx, psz; "S-1-5-18"
0x18001aec2  call    cs:__imp_SysAllocString
0x18001aec8  mov     qword ptr [rbp+750h+var_798+8], rax
0x18001aecc  test    rax, rax
0x18001aecf  jz      loc_18001B082
0x18001aed5  mov     rsi, [rbx+88h]
0x18001aedc  movups  xmm6, xmmword ptr [rbp+750h+var_798]
0x18001aee0  movsd   xmm7, qword ptr [rbp+750h+var_798+10h]
0x18001aee5  mov     rbx, qword ptr [rbp+750h+var_7C8]
0x18001aee9  lea     rdx, aScheduleCreate; "Schedule created by enrollment client f"...
0x18001aef0  lea     rcx, [rsp+850h+var_7D8]; this
0x18001aef5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001aefa  mov     rcx, [rax]
0x18001aefd  test    rcx, rcx
0x18001af00  jz      short loc_18001AF07
0x18001af02  mov     rdx, [rcx]
0x18001af05  jmp     short loc_18001AF0A
0x18001af07  mov     rdx, r15
0x18001af0a  movaps  [rbp+750h+var_730], xmm8
0x18001af0f  movsd   [rbp+750h+var_720], xmm9
  ... truncated ...
```
