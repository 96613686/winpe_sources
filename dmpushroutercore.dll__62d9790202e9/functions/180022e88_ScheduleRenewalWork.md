# ScheduleRenewalWork

- ea: `0x180022e88`
- end: `0x1800235a5`
- name: `ScheduleRenewalWork`
- size: `1821`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800229f0`

## callees

- `0x1800039f0`
- `0x18000604c`
- `0x18001cdb8`
- `0x18001ce6c`
- `0x18001d9dc`
- `0x18001dbb0`
- `0x18001dd58`
- `0x180022e88`
- `0x1800245fc`
- `0x180024b94`
- `0x18003593c`
- `0x18003b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180023078`
- `OLEAUT32!__imp_SysAllocString` at `0x1800231ab`
- `OLEAUT32!__imp_SysAllocString` at `0x1800233ab`
- `OLEAUT32!__imp_SysAllocString` at `0x18002344f`
- `OLEAUT32!__imp_SysAllocString` at `0x180023495`
- `OLEAUT32!__imp_SysAllocString` at `0x180023078`
- `OLEAUT32!__imp_SysAllocString` at `0x1800231ab`
- `OLEAUT32!__imp_SysAllocString` at `0x1800233ab`
- `OLEAUT32!__imp_SysAllocString` at `0x18002344f`
- `OLEAUT32!__imp_SysAllocString` at `0x180023495`
- `OLEAUT32!__imp_VariantInit` at `0x180023418`
- `OLEAUT32!__imp_VariantInit` at `0x18002342d`
- `OLEAUT32!__imp_VariantInit` at `0x180023418`
- `OLEAUT32!__imp_VariantInit` at `0x18002342d`
- `OLEAUT32!__imp_VariantClear` at `0x180023524`
- `OLEAUT32!__imp_VariantClear` at `0x180023532`
- `OLEAUT32!__imp_VariantClear` at `0x180023540`
- `OLEAUT32!__imp_VariantClear` at `0x180023524`
- `OLEAUT32!__imp_VariantClear` at `0x180023532`
- `OLEAUT32!__imp_VariantClear` at `0x180023540`

## string_xrefs

- `0x180022f37`: `%windir%\system32\deviceenroller.exe `
- `0x180023480`: `Schedule created by enrollment client for renewal of certificate warning`

## pseudocode

```c
__int64 __fastcall ScheduleRenewalWork(
        __int64 a1,
        OLECHAR *a2,
        unsigned int a3,
        unsigned int a4,
        struct _SYSTEMTIME *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7)
{
  const OLECHAR *v7; // r15
  __int64 v8; // r12
  int v10; // ebx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, BSTR); // r14
  BSTR *v13; // rbx
  BSTR v14; // rax
  const struct std::nothrow_t *v15; // rdx
  unsigned __int64 v16; // r9
  __int64 *v17; // rdi
  __int64 (__fastcall *v18)(__int64 *, BSTR); // rsi
  BSTR *v19; // rbx
  BSTR v20; // rax
  const struct std::nothrow_t *v21; // rdx
  bool v22; // sf
  __int64 *v24; // rdi
  __int64 v25; // rsi
  BSTR *v26; // rbx
  BSTR v27; // rax
  const struct std::nothrow_t *v28; // rdx
  __int64 *v29; // rdi
  __int64 v30; // r14
  __int128 v31; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v33; // xmm10
  IRecordInfo *v34; // xmm11_8
  BSTR v35; // rax
  IRecordInfo *v36; // xmm7_8
  __int64 v37; // rsi
  __int128 v38; // xmm6
  BSTR *v39; // rbx
  BSTR v40; // rax
  BSTR v41; // rdx
  __int64 (__fastcall *v42)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rax
  const struct std::nothrow_t *v43; // rdx
  HRESULT v44; // eax
  HRESULT v45; // eax
  HRESULT v46; // eax
  CEnrollmentLogger *Logger; // rax
  int v48[2]; // [rsp+78h] [rbp-90h] BYREF
  BSTR *v49; // [rsp+80h] [rbp-88h] BYREF
  __int64 *v50; // [rsp+88h] [rbp-80h] BYREF
  int v51[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v52; // [rsp+98h] [rbp-70h] BYREF
  __int64 v53; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-60h] BYREF
  int v55[2]; // [rsp+B0h] [rbp-58h] BYREF
  int v56[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v57; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v58; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v59; // [rsp+F0h] [rbp-18h] BYREF
  int v60[2]; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v61[2]; // [rsp+100h] [rbp-8h] BYREF
  VARIANTARG pvarg; // [rsp+110h] [rbp+8h] BYREF
  __int128 v63; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v64; // [rsp+138h] [rbp+30h]
  __int128 v65; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v66; // [rsp+158h] [rbp+50h]
  __int128 v67; // [rsp+168h] [rbp+60h] BYREF
  IRecordInfo *v68; // [rsp+178h] [rbp+70h]
  OLECHAR psz[264]; // [rsp+188h] [rbp+80h] BYREF
  OLECHAR v70[264]; // [rsp+398h] [rbp+290h] BYREF
  OLECHAR v71[264]; // [rsp+5A8h] [rbp+4A0h] BYREF

  v7 = a7;
  v61[0] = "ScheduleRenewalWork";
  v8 = a4;
  v61[1] = v48;
  v48[0] = 0;
  *(_QWORD *)v60 = 0;
  *(_QWORD *)v56 = 0;
  *(_QWORD *)v51 = 0;
  *(_QWORD *)v55 = 0;
  v53 = 0;
  v54 = 0;
  v52 = 0;
  v59 = 0;
  v50 = 0;
  *(_OWORD *)&v57.vt = 0;
  *(_OWORD *)&v58.vt = 0;
  v48[0] = CreateTask(
             v60,
             (BSTR ***)v56,
             v51,
             v55,
             a2,
             L"%windir%\\system32\\deviceenroller.exe ",
             a6,
             a7,
             0,
             1,
             1,
             1,
             0);
  v10 = v48[0];
  if ( v48[0] < 0 )
    goto LABEL_17;
  v48[0] = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v55 + 208LL))(*(_QWORD *)v55, 0xFFFFFFFFLL);
  v10 = v48[0];
  if ( v48[0] < 0 )
    goto LABEL_17;
  v48[0] = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v51 + 72LL))(*(_QWORD *)v51, &v53);
  v10 = v48[0];
  if ( v48[0] < 0 )
    goto LABEL_17;
  v48[0] = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v53 + 80LL))(v53, 1, &v54);
  v10 = v48[0];
  if ( v48[0] < 0 )
    goto LABEL_17;
  v48[0] = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v54)(v54, &IID_ITimeTrigger, &v52);
  v10 = v48[0];
  if ( v48[0] < 0 )
    goto LABEL_17;
  v48[0] = CreateDelayTimeString(a5, psz);
  v10 = v48[0];
  if ( v48[0] < 0 )
    goto LABEL_17;
  v11 = v52;
  v12 = *(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v52 + 120LL);
  v13 = (BSTR *)operator new(0x18u);
  v13[1] = 0;
  *((_DWORD *)v13 + 4) = 1;
  v14 = SysAllocString(psz);
  *v13 = v14;
  if ( !v14 )
    goto LABEL_52;
  v49 = v13;
  v48[0] = v12(v11, v14);
  _bstr_t::~_bstr_t((_bstr_t *)&v49, v15);
  v10 = v48[0];
  if ( v48[0] < 0 )
    goto LABEL_17;
  v48[0] = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v52 + 80LL))(v52, &v50);
  v10 = v48[0];
  if ( v48[0] < 0 )
    goto LABEL_17;
  if ( a3 )
  {
    v48[0] = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v50 + 96))(v50, 0xFFFFFFFFLL);
    v10 = v48[0];
    if ( v48[0] < 0 )
      goto LABEL_17;
    v16 = v8 * a3;
    if ( v16 > 0xFFFFFFFF )
    {
      v10 = -2147024362;
      v48[0] = -2147024362;
      goto LABEL_17;
    }
    *(_DWORD *)&v58.vt = 0;
    v48[0] = 0;
    v58.wReserved3 = (unsigned int)v16 / 0x3C / 0x18;
    WORD1(v58.decVal.Lo64) = (unsigned int)v16 % 0x3C;
    v58.iVal = (unsigned int)v16 / 0x3C % 0x18;
    v48[0] = CreateScheduleTimeString(&v58, v70);
    v10 = v48[0];
    if ( v48[0] < 0 )
      goto LABEL_17;
    v17 = v50;
    v18 = *(__int64 (__fastcall **)(__int64 *, BSTR))(*v50 + 80);
    v19 = (BSTR *)operator new(0x18u);
    v19[1] = 0;
    *((_DWORD *)v19 + 4) = 1;
    v20 = SysAllocString(v70);
    *v19 = v20;
    if ( !v20 )
      goto LABEL_52;
    v49 = v19;
    v48[0] = v18(v17, v20);
    _bstr_t::~_bstr_t((_bstr_t *)&v49, v21);
    v10 = v48[0];
    v22 = v48[0] < 0;
  }
  else
  {
    v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v50 + 96))(v50, 0);
    v48[0] = v10;
    v22 = v10 < 0;
  }
  if ( v22 )
    goto LABEL_17;
  *(_DWORD *)&v57.vt = 0;
  v48[0] = 0;
  v57.wReserved3 = (unsigned int)v8 / 0x3C / 0x18;
  WORD1(v57.decVal.Lo64) = (unsigned int)v8 % 0x3C;
  v57.iVal = (unsigned int)v8 / 0x3C % 0x18;
  v48[0] = CreateScheduleTimeString(&v57, v71);
  v10 = v48[0];
  if ( v48[0] < 0 )
    goto LABEL_17;
  v24 = v50;
  v25 = *v50;
  v26 = (BSTR *)operator new(0x18u);
  v26[1] = 0;
  *((_DWORD *)v26 + 4) = 1;
  v27 = SysAllocString(v71);
  *v26 = v27;
  if ( !v27 )
LABEL_52:
    _com_issue_error(-2147024882);
  v49 = v26;
  v48[0] = (*(__int64 (__fastcall **)(__int64 *, BSTR))(v25 + 64))(v24, v27);
  _bstr_t::~_bstr_t((_bstr_t *)&v49, v28);
  v10 = v48[0];
  if ( v48[0] >= 0 )
  {
    v48[0] = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v51 + 80LL))(*(_QWORD *)v51, v53);
    v10 = v48[0];
    if ( v48[0] >= 0 )
    {
      v29 = *(__int64 **)v56;
      v30 = **(_QWORD **)v56;
      VariantInit(&pvarg);
      v31 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v58);
      v33 = *(_OWORD *)&v58.vt;
      v34 = v58.pRecInfo;
      if ( !a7 )
        v7 = L"S-1-5-18";
      v35 = SysAllocString(v7);
      if ( !v35 )
        goto LABEL_51;
      v36 = v57.pRecInfo;
      v37 = *(_QWORD *)v51;
      v57.vt = 8;
      v57.llVal = (LONGLONG)v35;
      v38 = *(_OWORD *)&v57.vt;
      v39 = (BSTR *)operator new(0x18u);
      v39[1] = 0;
      *((_DWORD *)v39 + 4) = 1;
      v40 = SysAllocString(L"Schedule created by enrollment client for renewal of certificate warning");
      *v39 = v40;
      if ( !v40 )
LABEL_51:
        _com_issue_error(-2147024882);
      v49 = v39;
      v41 = v40;
      v42 = *(__int64 (__fastcall **)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v30 + 136);
      v63 = v31;
      v64 = pRecInfo;
      v65 = v33;
      v66 = v34;
      v67 = v38;
      v68 = v36;
      v48[0] = v42(v29, v41, v37, 6, &v67, &v65, 3, &v63, &v59);
      _bstr_t::~_bstr_t((_bstr_t *)&v49, v43);
      v44 = VariantClear(&v57);
      if ( v44 < 0 )
        _com_issue_error(v44);
      v45 = VariantClear(&v58);
      if ( v45 < 0 )
        _com_issue_error(v45);
      v46 = VariantClear(&pvarg);
      if ( v46 < 0 )
        _com_issue_error(v46);
      v10 = v48[0];
      if ( v48[0] < 0 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, v48[0], "ScheduleRenewalWork");
        v10 = v48[0];
      }
    }
  }
LABEL_17:
  if ( v50 )
    (*(void (__fastcall **)(__int64 *))(*v50 + 16))(v50);
  if ( v59 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  if ( v54 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  if ( *(_QWORD *)v55 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
  if ( *(_QWORD *)v51 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v51 + 16LL))(*(_QWORD *)v51);
  if ( *(_QWORD *)v56 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v56 + 16LL))(*(_QWORD *)v56);
  if ( *(_QWORD *)v60 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v60 + 16LL))(*(_QWORD *)v60);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v61);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180022e88  mov     rax, rsp
0x180022e8b  push    rbp
0x180022e8c  push    rbx
0x180022e8d  push    rsi
0x180022e8e  push    rdi
0x180022e8f  push    r12
0x180022e91  push    r13
0x180022e93  push    r14
0x180022e95  push    r15
0x180022e97  lea     rbp, [rax-768h]
0x180022e9e  sub     rsp, 828h
0x180022ea5  movaps  xmmword ptr [rax-58h], xmm6
0x180022ea9  movaps  xmmword ptr [rax-68h], xmm7
0x180022ead  movaps  xmmword ptr [rax-78h], xmm8
0x180022eb2  movaps  xmmword ptr [rax-88h], xmm9
0x180022eba  movaps  xmmword ptr [rax-98h], xmm10
0x180022ec2  movaps  xmmword ptr [rax-0A8h], xmm11
0x180022eca  mov     rax, cs:__security_cookie
0x180022ed1  xor     rax, rsp
0x180022ed4  mov     [rbp+760h+var_B0], rax
0x180022edb  mov     rax, [rbp+760h+arg_28]
0x180022ee2  lea     rcx, aSchedulerenewa; "ScheduleRenewalWork"
0x180022ee9  mov     r15, [rbp+760h+arg_30]
0x180022ef0  xor     r13d, r13d
0x180022ef3  mov     rdi, [rbp+760h+arg_20]
0x180022efa  xorps   xmm0, xmm0
0x180022efd  mov     [rsp+860h+Data], r13d; Data
0x180022f02  xorps   xmm1, xmm1
0x180022f05  mov     [rbp+760h+var_768], rcx
0x180022f09  lea     rcx, [rsp+860h+var_7F0]
0x180022f0e  lea     r14d, [r13+1]
0x180022f12  mov     r12d, r9d
0x180022f15  mov     [rsp+860h+var_808], r14d; int
0x180022f1a  lea     r9, [rbp+760h+var_7B8]; int
0x180022f1e  mov     [rsp+860h+var_810], r14d; int
0x180022f23  mov     [rsp+860h+var_818], r14d; int
0x180022f28  mov     [rsp+860h+var_820], r13d; int
0x180022f2d  mov     [rsp+860h+var_828], r15; unsigned __int16 *
0x180022f32  mov     [rsp+860h+var_830], rax; unsigned __int16 *
0x180022f37  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x180022f3e  mov     [rsp+860h+var_838], rax; unsigned __int16 *
0x180022f43  mov     [rsp+860h+var_840], rdx; OLECHAR *
0x180022f48  lea     rdx, [rbp+760h+var_7B0]; int
0x180022f4c  mov     esi, r8d
0x180022f4f  lea     r8, [rbp+760h+var_7D8]; int
0x180022f53  mov     [rbp+760h+var_760], rcx
0x180022f57  lea     rcx, [rbp+760h+var_770]; int
0x180022f5b  mov     [rsp+860h+var_7F0], r13d
0x180022f60  mov     qword ptr [rbp+760h+var_770], r13
0x180022f64  mov     qword ptr [rbp+760h+var_7B0], r13
0x180022f68  mov     qword ptr [rbp+760h+var_7D8], r13
0x180022f6c  mov     qword ptr [rbp+760h+var_7B8], r13
0x180022f70  mov     [rbp+760h+var_7C8], r13
0x180022f74  mov     [rbp+760h+var_7C0], r13
0x180022f78  mov     [rbp+760h+var_7D0], r13
0x180022f7c  mov     [rbp+760h+var_778], r13
0x180022f80  mov     [rbp+760h+var_7E0], r13
0x180022f84  movups  xmmword ptr [rbp+760h+var_7A8], xmm0
0x180022f88  movups  xmmword ptr [rbp+760h+var_790], xmm1
0x180022f8c  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180022f91  mov     [rsp+860h+var_7F0], eax
0x180022f95  mov     ebx, eax
0x180022f97  test    eax, eax
0x180022f99  js      loc_1800231F2
0x180022f9f  mov     rcx, qword ptr [rbp+760h+var_7B8]
0x180022fa3  or      edx, 0FFFFFFFFh
0x180022fa6  mov     rax, [rcx]
0x180022fa9  mov     rax, [rax+0D0h]
0x180022fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fb5  mov     [rsp+860h+var_7F0], eax
0x180022fb9  mov     ebx, eax
0x180022fbb  test    eax, eax
0x180022fbd  js      loc_1800231F2
0x180022fc3  mov     rcx, qword ptr [rbp+760h+var_7D8]
0x180022fc7  lea     rdx, [rbp+760h+var_7C8]
0x180022fcb  mov     rax, [rcx]
0x180022fce  mov     rax, [rax+48h]
0x180022fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fd7  mov     [rsp+860h+var_7F0], eax
0x180022fdb  mov     ebx, eax
0x180022fdd  test    eax, eax
0x180022fdf  js      loc_1800231F2
0x180022fe5  mov     rcx, [rbp+760h+var_7C8]
0x180022fe9  lea     r8, [rbp+760h+var_7C0]
0x180022fed  mov     edx, r14d
0x180022ff0  mov     rax, [rcx]
0x180022ff3  mov     rax, [rax+50h]
0x180022ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ffc  mov     [rsp+860h+var_7F0], eax
0x180023000  mov     ebx, eax
0x180023002  test    eax, eax
0x180023004  js      loc_1800231F2
0x18002300a  mov     rcx, [rbp+760h+var_7C0]
0x18002300e  lea     r8, [rbp+760h+var_7D0]
0x180023012  lea     rdx, IID_ITimeTrigger
0x180023019  mov     rax, [rcx]
0x18002301c  mov     rax, [rax]
0x18002301f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023024  mov     [rsp+860h+var_7F0], eax
0x180023028  mov     ebx, eax
0x18002302a  test    eax, eax
0x18002302c  js      loc_1800231F2
0x180023032  lea     rdx, [rbp+760h+psz]; unsigned __int16 *
0x180023039  mov     rcx, rdi; struct _SYSTEMTIME *
0x18002303c  call    ?CreateDelayTimeString@@YAJPEAU_SYSTEMTIME@@PEAGK@Z; CreateDelayTimeString(_SYSTEMTIME *,ushort *,ulong)
0x180023041  mov     [rsp+860h+var_7F0], eax
0x180023045  mov     ebx, eax
0x180023047  test    eax, eax
0x180023049  js      loc_1800231F2
0x18002304f  mov     rdi, [rbp+760h+var_7D0]
0x180023053  lea     ecx, [r13+18h]; Size
0x180023057  mov     rax, [rdi]
0x18002305a  mov     r14, [rax+78h]
0x18002305e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023063  lea     rcx, [rbp+760h+psz]; psz
0x18002306a  mov     rbx, rax
0x18002306d  mov     [rax+8], r13
0x180023071  mov     dword ptr [rax+10h], 1
0x180023078  call    cs:__imp_SysAllocString
0x18002307e  mov     [rbx], rax
0x180023081  test    rax, rax
0x180023084  jz      loc_180023582
0x18002308a  mov     rdx, rax
0x18002308d  mov     [rsp+860h+var_7E8], rbx
0x180023092  mov     rax, r14
0x180023095  mov     rcx, rdi
0x180023098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002309d  lea     rcx, [rsp+860h+var_7E8]; this
0x1800230a2  mov     [rsp+860h+var_7F0], eax
0x1800230a6  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800230ab  mov     ebx, [rsp+860h+var_7F0]
0x1800230af  test    ebx, ebx
0x1800230b1  js      loc_1800231F2
0x1800230b7  mov     rcx, [rbp+760h+var_7D0]
0x1800230bb  lea     rdx, [rbp+760h+var_7E0]
0x1800230bf  mov     rax, [rcx]
0x1800230c2  mov     rax, [rax+50h]
0x1800230c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230cb  mov     [rsp+860h+var_7F0], eax
0x1800230cf  mov     ebx, eax
0x1800230d1  test    eax, eax
0x1800230d3  js      loc_1800231F2
0x1800230d9  mov     rcx, [rbp+760h+var_7E0]
0x1800230dd  mov     r14d, 88888889h
0x1800230e3  test    esi, esi
0x1800230e5  jz      loc_1800232FF
0x1800230eb  mov     rax, [rcx]
0x1800230ee  or      edx, 0FFFFFFFFh
0x1800230f1  mov     rax, [rax+60h]
0x1800230f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230fa  mov     [rsp+860h+var_7F0], eax
0x1800230fe  mov     ebx, eax
0x180023100  test    eax, eax
0x180023102  js      loc_1800231F2
0x180023108  mov     r9d, esi
0x18002310b  mov     eax, 0FFFFFFFFh
0x180023110  imul    r9, r12
0x180023114  cmp     r9, rax
0x180023117  ja      loc_1800231E9
0x18002311d  mov     eax, r14d
0x180023120  mov     dword ptr [rbp+760h+var_790], r13d
0x180023124  mul     r9d
0x180023127  mov     [rsp+860h+var_7F0], r13d
0x18002312c  mov     r8d, edx
0x18002312f  shr     r8d, 5
0x180023133  movzx   eax, r8w
0x180023137  imul    ecx, eax, 3Ch ; '<'
0x18002313a  mov     eax, 0AAAAAAABh
0x18002313f  mul     r8d
0x180023142  sub     r9w, cx
0x180023146  shr     edx, 4
0x180023149  movzx   eax, dx
0x18002314c  mov     word ptr [rbp+760h+var_790+6], dx
0x180023150  add     ax, ax
0x180023153  mov     word ptr [rbp+760h+var_790+0Ah], r9w
0x180023158  lea     ecx, [rax+rdx]
0x18002315b  shl     cx, 3
0x18002315f  lea     rdx, [rbp+760h+var_4D0]
0x180023166  sub     r8w, cx
0x18002316a  lea     rcx, [rbp+760h+var_790]
0x18002316e  mov     word ptr [rbp+760h+var_790+8], r8w
0x180023173  call    CreateScheduleTimeString
0x180023178  mov     [rsp+860h+var_7F0], eax
0x18002317c  mov     ebx, eax
0x18002317e  test    eax, eax
0x180023180  js      short loc_1800231F2
0x180023182  mov     rdi, [rbp+760h+var_7E0]
0x180023186  lea     ecx, [r13+18h]; Size
0x18002318a  mov     rax, [rdi]
0x18002318d  mov     rsi, [rax+50h]
0x180023191  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023196  lea     rcx, [rbp+760h+var_4D0]; psz
0x18002319d  mov     rbx, rax
0x1800231a0  mov     [rax+8], r13
0x1800231a4  mov     dword ptr [rax+10h], 1
0x1800231ab  call    cs:__imp_SysAllocString
0x1800231b1  mov     [rbx], rax
0x1800231b4  test    rax, rax
0x1800231b7  jz      loc_180023582
0x1800231bd  mov     rdx, rax
0x1800231c0  mov     [rsp+860h+var_7E8], rbx
0x1800231c5  mov     rax, rsi
0x1800231c8  mov     rcx, rdi
0x1800231cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231d0  lea     rcx, [rsp+860h+var_7E8]; this
0x1800231d5  mov     [rsp+860h+var_7F0], eax
0x1800231d9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800231de  mov     ebx, [rsp+860h+var_7F0]
0x1800231e2  test    ebx, ebx
0x1800231e4  jmp     loc_180023315
0x1800231e9  mov     ebx, 80070216h
0x1800231ee  mov     [rsp+860h+var_7F0], ebx
0x1800231f2  mov     rcx, [rbp+760h+var_7E0]
0x1800231f6  test    rcx, rcx
0x1800231f9  jz      short loc_180023207
0x1800231fb  mov     rax, [rcx]
0x1800231fe  mov     rax, [rax+10h]
0x180023202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023207  mov     rcx, [rbp+760h+var_778]
0x18002320b  test    rcx, rcx
0x18002320e  jz      short loc_18002321C
0x180023210  mov     rax, [rcx]
0x180023213  mov     rax, [rax+10h]
0x180023217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002321c  mov     rcx, [rbp+760h+var_7D0]
0x180023220  test    rcx, rcx
0x180023223  jz      short loc_180023231
0x180023225  mov     rax, [rcx]
0x180023228  mov     rax, [rax+10h]
0x18002322c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023231  mov     rcx, [rbp+760h+var_7C0]
0x180023235  test    rcx, rcx
0x180023238  jz      short loc_180023246
0x18002323a  mov     rax, [rcx]
0x18002323d  mov     rax, [rax+10h]
0x180023241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023246  mov     rcx, [rbp+760h+var_7C8]
0x18002324a  test    rcx, rcx
0x18002324d  jz      short loc_18002325B
0x18002324f  mov     rax, [rcx]
0x180023252  mov     rax, [rax+10h]
0x180023256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002325b  mov     rcx, qword ptr [rbp+760h+var_7B8]
0x18002325f  test    rcx, rcx
0x180023262  jz      short loc_180023270
0x180023264  mov     rax, [rcx]
0x180023267  mov     rax, [rax+10h]
0x18002326b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023270  mov     rcx, qword ptr [rbp+760h+var_7D8]
0x180023274  test    rcx, rcx
0x180023277  jz      short loc_180023285
0x180023279  mov     rax, [rcx]
0x18002327c  mov     rax, [rax+10h]
0x180023280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023285  mov     rcx, qword ptr [rbp+760h+var_7B0]
0x180023289  test    rcx, rcx
0x18002328c  jz      short loc_18002329A
0x18002328e  mov     rax, [rcx]
0x180023291  mov     rax, [rax+10h]
0x180023295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002329a  mov     rcx, qword ptr [rbp+760h+var_770]
0x18002329e  test    rcx, rcx
0x1800232a1  jz      short loc_1800232AF
0x1800232a3  mov     rdx, [rcx]
0x1800232a6  mov     rax, [rdx+10h]
0x1800232aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232af  lea     rcx, [rbp+760h+var_768]; this
0x1800232b3  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800232b8  mov     eax, ebx
0x1800232ba  mov     rcx, [rbp+760h+var_B0]
0x1800232c1  xor     rcx, rsp; StackCookie
0x1800232c4  call    __security_check_cookie
0x1800232c9  lea     r11, [rsp+860h+var_38]
0x1800232d1  movaps  xmm6, xmmword ptr [r11-18h]
0x1800232d6  movaps  xmm7, xmmword ptr [r11-28h]
0x1800232db  movaps  xmm8, xmmword ptr [r11-38h]
0x1800232e0  movaps  xmm9, xmmword ptr [r11-48h]
0x1800232e5  movaps  xmm10, xmmword ptr [r11-58h]
0x1800232ea  movaps  xmm11, xmmword ptr [r11-68h]
0x1800232ef  mov     rsp, r11
0x1800232f2  pop     r15
0x1800232f4  pop     r14
0x1800232f6  pop     r13
0x1800232f8  pop     r12
0x1800232fa  pop     rdi
0x1800232fb  pop     rsi
0x1800232fc  pop     rbx
0x1800232fd  pop     rbp
0x1800232fe  retn
0x1800232ff  mov     r8, [rcx]
0x180023302  xor     edx, edx
0x180023304  mov     rax, [r8+60h]
0x180023308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002330d  mov     ebx, eax
0x18002330f  mov     [rsp+860h+var_7F0], eax
0x180023313  test    eax, eax
0x180023315  js      loc_1800231F2
0x18002331b  mov     eax, r14d
0x18002331e  mov     dword ptr [rbp+760h+var_7A8], r13d
0x180023322  mul     r12d
  ... truncated ...
```
