# ScheduleDeviceEnrollerOnLogin

- ea: `0x180020b70`
- end: `0x1800211b9`
- name: `ScheduleDeviceEnrollerOnLogin`
- size: `1609`
- prototype: `__int64 __usercall@<rax>(OLECHAR *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022560`

## callees

- `0x18000604c`
- `0x18001cdb8`
- `0x18001ce6c`
- `0x18001dd58`
- `0x180020b70`
- `0x1800245fc`
- `0x180024b94`
- `0x18003593c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021124`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021124`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180020bea`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180020bea`
- `OLEAUT32!__imp_SysAllocString` at `0x180020ded`
- `OLEAUT32!__imp_SysAllocString` at `0x180020ef1`
- `OLEAUT32!__imp_SysAllocString` at `0x180020f56`
- `OLEAUT32!__imp_SysAllocString` at `0x180020ded`
- `OLEAUT32!__imp_SysAllocString` at `0x180020ef1`
- `OLEAUT32!__imp_SysAllocString` at `0x180020f56`
- `OLEAUT32!__imp_VariantInit` at `0x180020d93`
- `OLEAUT32!__imp_VariantInit` at `0x180020da6`
- `OLEAUT32!__imp_VariantInit` at `0x180020dbb`
- `OLEAUT32!__imp_VariantInit` at `0x180020ebe`
- `OLEAUT32!__imp_VariantInit` at `0x180020ed3`
- `OLEAUT32!__imp_VariantInit` at `0x180020f1d`
- `OLEAUT32!__imp_VariantInit` at `0x180020d93`
- `OLEAUT32!__imp_VariantInit` at `0x180020da6`
- `OLEAUT32!__imp_VariantInit` at `0x180020dbb`
- `OLEAUT32!__imp_VariantInit` at `0x180020ebe`
- `OLEAUT32!__imp_VariantInit` at `0x180020ed3`
- `OLEAUT32!__imp_VariantInit` at `0x180020f1d`
- `OLEAUT32!__imp_VariantClear` at `0x180020e7c`
- `OLEAUT32!__imp_VariantClear` at `0x180020e8e`
- `OLEAUT32!__imp_VariantClear` at `0x180020ea0`
- `OLEAUT32!__imp_VariantClear` at `0x180020fee`
- `OLEAUT32!__imp_VariantClear` at `0x180021006`
- `OLEAUT32!__imp_VariantClear` at `0x180021018`
- `OLEAUT32!__imp_VariantClear` at `0x18002102a`
- `OLEAUT32!__imp_VariantClear` at `0x180020e7c`
- `OLEAUT32!__imp_VariantClear` at `0x180020e8e`
- `OLEAUT32!__imp_VariantClear` at `0x180020ea0`
- `OLEAUT32!__imp_VariantClear` at `0x180020fee`
- `OLEAUT32!__imp_VariantClear` at `0x180021006`
- `OLEAUT32!__imp_VariantClear` at `0x180021018`
- `OLEAUT32!__imp_VariantClear` at `0x18002102a`

## string_xrefs

- `0x180020f41`: `Login Schedule created by enrollment client`
- `0x180020c5f`: `%windir%\system32\deviceenroller.exe `
- `0x180020bcd`: `ScheduleDeviceEnrollerOnLogin`
- `0x18002104c`: `ScheduleDeviceEnrollerOnLogin`
- `0x180020ddb`: `First Login Schedule created by enrollment client`

## pseudocode

```c
__int64 __fastcall ScheduleDeviceEnrollerOnLogin(
        OLECHAR *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5)
{
  unsigned int v8; // edi
  int v9; // ebx
  unsigned __int16 *v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  __int64 *v13; // rsi
  __int64 v14; // r14
  __int128 v15; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v17; // xmm8
  IRecordInfo *v18; // xmm9_8
  __int128 v19; // xmm10
  __int64 v20; // r15
  IRecordInfo *v21; // xmm11_8
  BSTR *v22; // rdi
  BSTR v23; // rax
  BSTR v24; // rdx
  __int64 (__fastcall *v25)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rax
  const struct std::nothrow_t *v26; // rdx
  HRESULT v27; // eax
  HRESULT v28; // eax
  HRESULT v29; // eax
  __int64 *v30; // r14
  __int64 v31; // r13
  __int128 v32; // xmm8
  IRecordInfo *v33; // xmm9_8
  IRecordInfo *v34; // xmm11_8
  __int128 v35; // xmm10
  char v36; // di
  BSTR v37; // rax
  VARIANTARG *p_pvarg; // rax
  __int128 v39; // xmm6
  __int64 v40; // r15
  IRecordInfo *v41; // xmm7_8
  BSTR *v42; // rsi
  BSTR v43; // rax
  BSTR v44; // rdx
  __int64 (__fastcall *v45)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rax
  const struct std::nothrow_t *v46; // rdx
  HRESULT v47; // eax
  HRESULT v48; // eax
  HRESULT v49; // eax
  HRESULT v50; // eax
  CEnrollmentLogger *Logger; // rax
  int v53[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v54; // [rsp+80h] [rbp-88h] BYREF
  int v55[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v56; // [rsp+90h] [rbp-78h] BYREF
  __int64 v57; // [rsp+98h] [rbp-70h] BYREF
  __int64 v58; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v59; // [rsp+A8h] [rbp-60h] BYREF
  int v60[2]; // [rsp+B0h] [rbp-58h] BYREF
  int v61[2]; // [rsp+B8h] [rbp-50h] BYREF
  BSTR *v62; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v63; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v64; // [rsp+E0h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v66[3]; // [rsp+110h] [rbp+8h] BYREF
  __int128 v67; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v68; // [rsp+138h] [rbp+30h]
  __int128 v69; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v70; // [rsp+158h] [rbp+50h]
  __int128 v71; // [rsp+168h] [rbp+60h] BYREF
  IRecordInfo *v72; // [rsp+178h] [rbp+70h]
  VARIANTARG v73; // [rsp+188h] [rbp+80h] BYREF
  int Task; // [rsp+270h] [rbp+168h] BYREF

  v66[0] = "ScheduleDeviceEnrollerOnLogin";
  v66[1] = &Task;
  Task = 0;
  Task = CoInitializeEx(0, 0);
  v8 = Task;
  if ( Task < 0 )
  {
    v9 = 0;
    if ( Task != -2147417850 )
      goto LABEL_53;
  }
  else
  {
    v9 = 1;
  }
  v10 = L"S-1-5-32-545";
  *(_QWORD *)v61 = 0;
  *(_QWORD *)v55 = 0;
  if ( a3 )
    v10 = a3;
  *(_QWORD *)v53 = 0;
  *(_QWORD *)v60 = 0;
  v54 = 0;
  v59 = 0;
  v58 = 0;
  v57 = 0;
  v56 = 0;
  Task = CreateTask(
           v61,
           (BSTR ***)v55,
           v53,
           v60,
           a1,
           L"%windir%\\system32\\deviceenroller.exe ",
           a2,
           v10,
           0,
           0,
           1,
           1,
           1);
  if ( Task < 0 )
    goto LABEL_32;
  Task = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v53 + 72LL))(*(_QWORD *)v53, &v54);
  if ( Task < 0 )
    goto LABEL_32;
  Task = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v54 + 80LL))(v54, 9, &v59);
  if ( Task < 0 )
    goto LABEL_32;
  Task = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v59)(v59, &IID_ILogonTrigger, &v58);
  if ( Task < 0 )
    goto LABEL_32;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 80LL))(v58, &v56);
  v12 = v56;
  Task = v11;
  if ( v11 >= 0 )
  {
    Task = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v56 + 96LL))(v56, 0);
    if ( Task < 0
      || (Task = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v53 + 80LL))(*(_QWORD *)v53, v54), Task < 0) )
    {
LABEL_32:
      v12 = v56;
      goto LABEL_33;
    }
    if ( a5 )
    {
      v13 = *(__int64 **)v55;
      v14 = **(_QWORD **)v55;
      VariantInit(&pvarg);
      v15 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v64);
      v17 = *(_OWORD *)&v64.vt;
      v18 = v64.pRecInfo;
      VariantInit(&v63);
      v19 = *(_OWORD *)&v63.vt;
      v20 = *(_QWORD *)v53;
      v21 = v63.pRecInfo;
      v22 = (BSTR *)operator new(0x18u);
      v22[1] = 0;
      *((_DWORD *)v22 + 4) = 1;
      v23 = SysAllocString(L"First Login Schedule created by enrollment client");
      *v22 = v23;
      if ( !v23 )
        _com_issue_error(-2147024882);
      v62 = v22;
      v24 = v23;
      v25 = *(__int64 (__fastcall **)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v14 + 136);
      v67 = v15;
      v68 = pRecInfo;
      v69 = v17;
      v70 = v18;
      v71 = v19;
      v72 = v21;
      Task = v25(v13, v24, v20, 6, &v71, &v69, 3, &v67, &v57);
      _bstr_t::~_bstr_t((_bstr_t *)&v62, v26);
      v27 = VariantClear(&v63);
      if ( v27 < 0 )
        _com_issue_error(v27);
      v28 = VariantClear(&v64);
      if ( v28 < 0 )
        _com_issue_error(v28);
      v29 = VariantClear(&pvarg);
      if ( v29 < 0 )
        _com_issue_error(v29);
LABEL_30:
      if ( Task < 0 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Task, "ScheduleDeviceEnrollerOnLogin");
      }
      goto LABEL_32;
    }
    v30 = *(__int64 **)v55;
    v31 = **(_QWORD **)v55;
    VariantInit(&v63);
    v32 = *(_OWORD *)&v63.vt;
    v33 = v63.pRecInfo;
    VariantInit(&v64);
    v34 = v64.pRecInfo;
    v35 = *(_OWORD *)&v64.vt;
    if ( a3 )
    {
      v36 = 1;
      v37 = SysAllocString(a3);
      if ( !v37 )
        goto LABEL_59;
      pvarg.llVal = (LONGLONG)v37;
      pvarg.vt = 8;
      p_pvarg = &pvarg;
    }
    else
    {
      v36 = 2;
      VariantInit(&v73);
      p_pvarg = &v73;
    }
    v39 = *(_OWORD *)&p_pvarg->vt;
    v40 = *(_QWORD *)v53;
    v41 = p_pvarg->pRecInfo;
    v42 = (BSTR *)operator new(0x18u);
    v42[1] = 0;
    *((_DWORD *)v42 + 4) = 1;
    v43 = SysAllocString(L"Login Schedule created by enrollment client");
    *v42 = v43;
    if ( v43 )
    {
      v62 = v42;
      v44 = v43;
      v45 = *(__int64 (__fastcall **)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v31 + 136);
      v71 = v32;
      v72 = v33;
      v69 = v35;
      v70 = v34;
      v67 = v39;
      v68 = v41;
      Task = v45(v30, v44, v40, 6, &v67, &v69, 3, &v71, &v57);
      _bstr_t::~_bstr_t((_bstr_t *)&v62, v46);
      if ( (v36 & 2) != 0 )
      {
        v47 = VariantClear(&v73);
        if ( v47 < 0 )
          _com_issue_error(v47);
      }
      if ( (v36 & 1) != 0 )
      {
        v48 = VariantClear(&pvarg);
        if ( v48 < 0 )
          _com_issue_error(v48);
      }
      v49 = VariantClear(&v64);
      if ( v49 < 0 )
        _com_issue_error(v49);
      v50 = VariantClear(&v63);
      if ( v50 < 0 )
        _com_issue_error(v50);
      goto LABEL_30;
    }
LABEL_59:
    _com_issue_error(-2147024882);
  }
LABEL_33:
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v57 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  if ( v58 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  if ( v59 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  if ( v54 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  if ( *(_QWORD *)v60 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v60 + 16LL))(*(_QWORD *)v60);
  if ( *(_QWORD *)v53 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v53 + 16LL))(*(_QWORD *)v53);
  if ( *(_QWORD *)v55 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v55 + 16LL))(*(_QWORD *)v55);
  if ( *(_QWORD *)v61 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v61 + 16LL))(*(_QWORD *)v61);
  v8 = Task;
  if ( v9 )
    CoUninitialize();
LABEL_53:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v66);
  return v8;
}

```

## disassembly

```asm
0x180020b70  mov     rax, rsp
0x180020b73  mov     [rax+20h], r9d
0x180020b77  push    rbp
0x180020b78  push    rbx
0x180020b79  push    rsi
0x180020b7a  push    rdi
0x180020b7b  push    r12
0x180020b7d  push    r13
0x180020b7f  push    r14
0x180020b81  push    r15
0x180020b83  lea     rbp, [rax-148h]
0x180020b8a  sub     rsp, 208h
0x180020b91  movaps  xmmword ptr [rax-58h], xmm6
0x180020b95  xor     r12d, r12d
0x180020b98  movaps  xmmword ptr [rax-68h], xmm7
0x180020b9c  mov     r14, rdx
0x180020b9f  movaps  xmmword ptr [rax-78h], xmm8
0x180020ba4  mov     r15, rcx
0x180020ba7  movaps  xmmword ptr [rax-88h], xmm9
0x180020baf  xor     edx, edx; dwCoInit
0x180020bb1  movaps  xmmword ptr [rax-98h], xmm10
0x180020bb9  xor     ecx, ecx; pvReserved
0x180020bbb  mov     [rbp+140h+arg_18], r12d
0x180020bc2  mov     rsi, r8
0x180020bc5  movaps  xmmword ptr [rax-0A8h], xmm11
0x180020bcd  lea     rax, aScheduledevice; "ScheduleDeviceEnrollerOnLogin"
0x180020bd4  mov     [rbp+140h+var_138], rax
0x180020bd8  lea     rax, [rbp+140h+arg_18]
0x180020bdf  mov     [rbp+140h+var_130], rax
0x180020be3  mov     [rbp+140h+arg_18], r12d
0x180020bea  call    cs:__imp_CoInitializeEx
0x180020bf0  mov     [rbp+140h+arg_18], eax
0x180020bf6  mov     edi, eax
0x180020bf8  lea     r13d, [r12+1]
0x180020bfd  test    eax, eax
0x180020bff  js      short loc_180020C06
0x180020c01  mov     ebx, r13d
0x180020c04  jmp     short loc_180020C15
0x180020c06  mov     ebx, r12d
0x180020c09  cmp     edi, 80010106h
0x180020c0f  jnz     loc_18002112A
0x180020c15  mov     [rsp+240h+Data], r13d; Data
0x180020c1a  lea     rax, aS1532545; "S-1-5-32-545"
0x180020c21  mov     [rsp+240h+var_1E8], r13d; int
0x180020c26  lea     r9, [rbp+140h+var_198]; int
0x180020c2a  mov     [rsp+240h+var_1F0], r13d; int
0x180020c2f  lea     r8, [rsp+240h+var_1D0]; int
0x180020c34  mov     [rsp+240h+var_1F8], r12d; int
0x180020c39  lea     rdx, [rbp+140h+var_1C0]; int
0x180020c3d  mov     [rsp+240h+var_200], r12d; int
0x180020c42  lea     rcx, [rbp+140h+var_190]; int
0x180020c46  test    rsi, rsi
0x180020c49  mov     qword ptr [rbp+140h+var_190], r12
0x180020c4d  mov     qword ptr [rbp+140h+var_1C0], r12
0x180020c51  cmovnz  rax, rsi
0x180020c55  mov     qword ptr [rsp+240h+var_1D0], r12
0x180020c5a  mov     [rsp+240h+var_208], rax; unsigned __int16 *
0x180020c5f  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x180020c66  mov     [rsp+240h+var_210], r14; unsigned __int16 *
0x180020c6b  mov     [rsp+240h+var_218], rax; unsigned __int16 *
0x180020c70  mov     [rsp+240h+var_220], r15; OLECHAR *
0x180020c75  mov     qword ptr [rbp+140h+var_198], r12
0x180020c79  mov     [rsp+240h+var_1C8], r12
0x180020c7e  mov     [rbp+140h+var_1A0], r12
0x180020c82  mov     [rbp+140h+var_1A8], r12
0x180020c86  mov     [rbp+140h+var_1B0], r12
0x180020c8a  mov     [rbp+140h+var_1B8], r12
0x180020c8e  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180020c93  mov     [rbp+140h+arg_18], eax
0x180020c99  test    eax, eax
0x180020c9b  js      loc_18002105B
0x180020ca1  mov     rcx, qword ptr [rsp+240h+var_1D0]
0x180020ca6  lea     rdx, [rsp+240h+var_1C8]
0x180020cab  mov     rax, [rcx]
0x180020cae  mov     rax, [rax+48h]
0x180020cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cb7  mov     [rbp+140h+arg_18], eax
0x180020cbd  test    eax, eax
0x180020cbf  js      loc_18002105B
0x180020cc5  mov     rcx, [rsp+240h+var_1C8]
0x180020cca  lea     r8, [rbp+140h+var_1A0]
0x180020cce  mov     edx, 9
0x180020cd3  mov     rax, [rcx]
0x180020cd6  mov     rax, [rax+50h]
0x180020cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cdf  mov     [rbp+140h+arg_18], eax
0x180020ce5  test    eax, eax
0x180020ce7  js      loc_18002105B
0x180020ced  mov     rcx, [rbp+140h+var_1A0]
0x180020cf1  lea     r8, [rbp+140h+var_1A8]
0x180020cf5  lea     rdx, IID_ILogonTrigger
0x180020cfc  mov     rax, [rcx]
0x180020cff  mov     rax, [rax]
0x180020d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d07  mov     [rbp+140h+arg_18], eax
0x180020d0d  test    eax, eax
0x180020d0f  js      loc_18002105B
0x180020d15  mov     rcx, [rbp+140h+var_1A8]
0x180020d19  lea     rdx, [rbp+140h+var_1B8]
0x180020d1d  mov     rax, [rcx]
0x180020d20  mov     rax, [rax+50h]
0x180020d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d29  mov     rcx, [rbp+140h+var_1B8]
0x180020d2d  mov     [rbp+140h+arg_18], eax
0x180020d33  test    eax, eax
0x180020d35  js      loc_18002105F
0x180020d3b  mov     rax, [rcx]
0x180020d3e  xor     edx, edx
0x180020d40  mov     rax, [rax+60h]
0x180020d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d49  mov     [rbp+140h+arg_18], eax
0x180020d4f  test    eax, eax
0x180020d51  js      loc_18002105B
0x180020d57  mov     rcx, qword ptr [rsp+240h+var_1D0]
0x180020d5c  mov     rdx, [rsp+240h+var_1C8]
0x180020d61  mov     rax, [rcx]
0x180020d64  mov     rax, [rax+50h]
0x180020d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d6d  mov     [rbp+140h+arg_18], eax
0x180020d73  test    eax, eax
0x180020d75  js      loc_18002105B
0x180020d7b  cmp     [rbp+140h+arg_20], r12d
0x180020d82  jz      loc_180020EB3
0x180020d88  mov     rsi, qword ptr [rbp+140h+var_1C0]
0x180020d8c  lea     rcx, [rbp+140h+pvarg]; pvarg
0x180020d90  mov     r14, [rsi]
0x180020d93  call    cs:__imp_VariantInit
0x180020d99  movups  xmm6, xmmword ptr [rbp+140h+pvarg]
0x180020d9d  lea     rcx, [rbp+140h+var_168]; pvarg
0x180020da1  movsd   xmm7, qword ptr [rbp+140h+pvarg+10h]
0x180020da6  call    cs:__imp_VariantInit
0x180020dac  movups  xmm8, xmmword ptr [rbp+140h+var_168]
0x180020db1  lea     rcx, [rbp+140h+var_180]; pvarg
0x180020db5  movsd   xmm9, qword ptr [rbp+140h+var_168+10h]
0x180020dbb  call    cs:__imp_VariantInit
0x180020dc1  movups  xmm10, xmmword ptr [rbp+140h+var_180]
0x180020dc6  mov     ecx, 18h; Size
0x180020dcb  mov     r15, qword ptr [rsp+240h+var_1D0]
0x180020dd0  movsd   xmm11, qword ptr [rbp+140h+var_180+10h]
0x180020dd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020ddb  lea     rcx, aFirstLoginSche; "First Login Schedule created by enrollm"...
0x180020de2  mov     rdi, rax
0x180020de5  mov     [rax+8], r12
0x180020de9  mov     [rax+10h], r13d
0x180020ded  call    cs:__imp_SysAllocString
0x180020df3  mov     [rdi], rax
0x180020df6  test    rax, rax
0x180020df9  jz      loc_18002117B
0x180020dff  lea     rcx, [rbp+140h+var_1B0]
0x180020e03  mov     [rbp+140h+var_188], rdi
0x180020e07  mov     qword ptr [rsp+240h+var_200], rcx
0x180020e0c  mov     rdx, rax
0x180020e0f  mov     rax, [r14+88h]
0x180020e16  lea     rcx, [rbp+140h+var_120]
0x180020e1a  mov     [rsp+240h+var_208], rcx
0x180020e1f  mov     r9d, 6
0x180020e25  lea     rcx, [rbp+140h+var_100]
0x180020e29  mov     dword ptr [rsp+240h+var_210], 3
0x180020e31  mov     [rsp+240h+var_218], rcx
0x180020e36  mov     r8, r15
0x180020e39  lea     rcx, [rbp+140h+var_E0]
0x180020e3d  movaps  [rbp+140h+var_120], xmm6
0x180020e41  mov     [rsp+240h+var_220], rcx
0x180020e46  mov     rcx, rsi
0x180020e49  movsd   [rbp+140h+var_110], xmm7
0x180020e4e  movaps  [rbp+140h+var_100], xmm8
0x180020e53  movsd   [rbp+140h+var_F0], xmm9
0x180020e59  movaps  [rbp+140h+var_E0], xmm10
0x180020e5e  movsd   [rbp+140h+var_D0], xmm11
0x180020e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e69  lea     rcx, [rbp+140h+var_188]; this
0x180020e6d  mov     [rbp+140h+arg_18], eax
0x180020e73  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180020e78  lea     rcx, [rbp+140h+var_180]; pvarg
0x180020e7c  call    cs:__imp_VariantClear
0x180020e82  test    eax, eax
0x180020e84  js      loc_180021186
0x180020e8a  lea     rcx, [rbp+140h+var_168]; pvarg
0x180020e8e  call    cs:__imp_VariantClear
0x180020e94  test    eax, eax
0x180020e96  js      loc_18002118E
0x180020e9c  lea     rcx, [rbp+140h+pvarg]; pvarg
0x180020ea0  call    cs:__imp_VariantClear
0x180020ea6  test    eax, eax
0x180020ea8  js      loc_180021173
0x180020eae  jmp     loc_180021038
0x180020eb3  mov     r14, qword ptr [rbp+140h+var_1C0]
0x180020eb7  lea     rcx, [rbp+140h+var_180]; pvarg
0x180020ebb  mov     r13, [r14]
0x180020ebe  call    cs:__imp_VariantInit
0x180020ec4  movups  xmm8, xmmword ptr [rbp+140h+var_180]
0x180020ec9  lea     rcx, [rbp+140h+var_168]; pvarg
0x180020ecd  movsd   xmm9, qword ptr [rbp+140h+var_180+10h]
0x180020ed3  call    cs:__imp_VariantInit
0x180020ed9  movsd   xmm11, qword ptr [rbp+140h+var_168+10h]
0x180020edf  movups  xmm10, xmmword ptr [rbp+140h+var_168]
0x180020ee4  test    rsi, rsi
0x180020ee7  jz      short loc_180020F11
0x180020ee9  mov     rcx, rsi; psz
0x180020eec  mov     edi, 1
0x180020ef1  call    cs:__imp_SysAllocString
0x180020ef7  test    rax, rax
0x180020efa  jz      loc_180021196
0x180020f00  lea     ecx, [rdi+7]
0x180020f03  mov     qword ptr [rbp+140h+pvarg+8], rax
0x180020f07  mov     word ptr [rbp+140h+pvarg], cx
0x180020f0b  lea     rax, [rbp+140h+pvarg]
0x180020f0f  jmp     short loc_180020F2A
0x180020f11  lea     rcx, [rbp+140h+var_C0]; pvarg
0x180020f18  mov     edi, 2
0x180020f1d  call    cs:__imp_VariantInit
0x180020f23  lea     rax, [rbp+140h+var_C0]
0x180020f2a  movups  xmm6, xmmword ptr [rax]
0x180020f2d  mov     ecx, 18h; Size
0x180020f32  mov     r15, qword ptr [rsp+240h+var_1D0]
0x180020f37  movsd   xmm7, qword ptr [rax+10h]
0x180020f3c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020f41  lea     rcx, aLoginScheduleC; "Login Schedule created by enrollment cl"...
0x180020f48  mov     rsi, rax
0x180020f4b  mov     [rax+8], r12
0x180020f4f  mov     dword ptr [rax+10h], 1
0x180020f56  call    cs:__imp_SysAllocString
0x180020f5c  mov     [rsi], rax
0x180020f5f  test    rax, rax
0x180020f62  jz      loc_180021196
0x180020f68  lea     rcx, [rbp+140h+var_1B0]
0x180020f6c  mov     [rbp+140h+var_188], rsi
0x180020f70  mov     qword ptr [rsp+240h+var_200], rcx
0x180020f75  mov     rdx, rax
0x180020f78  mov     rax, [r13+88h]
0x180020f7f  lea     rcx, [rbp+140h+var_E0]
0x180020f83  mov     [rsp+240h+var_208], rcx
0x180020f88  mov     r9d, 6
0x180020f8e  lea     rcx, [rbp+140h+var_100]
0x180020f92  mov     dword ptr [rsp+240h+var_210], 3
0x180020f9a  mov     [rsp+240h+var_218], rcx
0x180020f9f  mov     r8, r15
0x180020fa2  lea     rcx, [rbp+140h+var_120]
0x180020fa6  movaps  [rbp+140h+var_E0], xmm8
0x180020fab  mov     [rsp+240h+var_220], rcx
0x180020fb0  mov     rcx, r14
0x180020fb3  movsd   [rbp+140h+var_D0], xmm9
0x180020fb9  movaps  [rbp+140h+var_100], xmm10
0x180020fbe  movsd   [rbp+140h+var_F0], xmm11
0x180020fc4  movaps  [rbp+140h+var_120], xmm6
0x180020fc8  movsd   [rbp+140h+var_110], xmm7
0x180020fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fd2  lea     rcx, [rbp+140h+var_188]; this
0x180020fd6  mov     [rbp+140h+arg_18], eax
0x180020fdc  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180020fe1  test    dil, 2
0x180020fe5  jz      short loc_180020FFC
0x180020fe7  lea     rcx, [rbp+140h+var_C0]; pvarg
0x180020fee  call    cs:__imp_VariantClear
0x180020ff4  test    eax, eax
0x180020ff6  js      loc_1800211A1
0x180020ffc  test    dil, 1
0x180021000  jz      short loc_180021014
0x180021002  lea     rcx, [rbp+140h+pvarg]; pvarg
0x180021006  call    cs:__imp_VariantClear
0x18002100c  test    eax, eax
0x18002100e  js      loc_1800211A9
0x180021014  lea     rcx, [rbp+140h+var_168]; pvarg
0x180021018  call    cs:__imp_VariantClear
0x18002101e  test    eax, eax
0x180021020  js      loc_1800211B1
0x180021026  lea     rcx, [rbp+140h+var_180]; pvarg
0x18002102a  call    cs:__imp_VariantClear
0x180021030  test    eax, eax
0x180021032  js      loc_18002116B
0x180021038  cmp     [rbp+140h+arg_18], r12d
0x18002103f  jge     short loc_18002105B
0x180021041  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180021046  mov     edx, [rbp+140h+arg_18]; int
0x18002104c  lea     r8, aScheduledevice; "ScheduleDeviceEnrollerOnLogin"
0x180021053  mov     rcx, rax; this
0x180021056  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18002105b  mov     rcx, [rbp+140h+var_1B8]
0x18002105f  test    rcx, rcx
0x180021062  jz      short loc_180021070
0x180021064  mov     rax, [rcx]
0x180021067  mov     rax, [rax+10h]
0x18002106b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021070  mov     rcx, [rbp+140h+var_1B0]
0x180021074  test    rcx, rcx
0x180021077  jz      short loc_180021085
0x180021079  mov     rax, [rcx]
0x18002107c  mov     rax, [rax+10h]
0x180021080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021085  mov     rcx, [rbp+140h+var_1A8]
0x180021089  test    rcx, rcx
0x18002108c  jz      short loc_18002109A
0x18002108e  mov     rax, [rcx]
0x180021091  mov     rax, [rax+10h]
0x180021095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002109a  mov     rcx, [rbp+140h+var_1A0]
0x18002109e  test    rcx, rcx
0x1800210a1  jz      short loc_1800210AF
0x1800210a3  mov     rax, [rcx]
0x1800210a6  mov     rax, [rax+10h]
  ... truncated ...
```
