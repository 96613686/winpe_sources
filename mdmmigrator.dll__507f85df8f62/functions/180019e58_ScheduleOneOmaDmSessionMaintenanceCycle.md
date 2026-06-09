# ScheduleOneOmaDmSessionMaintenanceCycle

- ea: `0x180019e58`
- end: `0x18001a1be`
- name: `ScheduleOneOmaDmSessionMaintenanceCycle`
- size: `870`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, __int64, unsigned __int16 *, __int64, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019904`

## callees

- `0x1800034ac`
- `0x18000aa2c`
- `0x18000aab8`
- `0x18000ab84`
- `0x1800117c8`
- `0x180011d5c`
- `0x180012ed4`
- `0x180019e58`
- `0x18001dce8`
- `0x18001e264`
- `0x18001e79c`
- `0x180020010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001a014`
- `OLEAUT32!__imp_VariantInit` at `0x18001a027`
- `OLEAUT32!__imp_VariantInit` at `0x18001a03c`
- `OLEAUT32!__imp_VariantInit` at `0x18001a014`
- `OLEAUT32!__imp_VariantInit` at `0x18001a027`
- `OLEAUT32!__imp_VariantInit` at `0x18001a03c`
- `OLEAUT32!__imp_VariantClear` at `0x18001a0db`
- `OLEAUT32!__imp_VariantClear` at `0x18001a0e5`
- `OLEAUT32!__imp_VariantClear` at `0x18001a0ef`
- `OLEAUT32!__imp_VariantClear` at `0x18001a0db`
- `OLEAUT32!__imp_VariantClear` at `0x18001a0e5`
- `OLEAUT32!__imp_VariantClear` at `0x18001a0ef`

## string_xrefs

- `0x180019f2b`: `%windir%\system32\deviceenroller.exe `

## pseudocode

```c
__int64 __fastcall ScheduleOneOmaDmSessionMaintenanceCycle(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        __int64 a5,
        int a6)
{
  int v7; // ebx
  __int64 *v8; // rdi
  __int64 v9; // rsi
  BSTR *v10; // rbx
  BSTR v11; // rax
  const struct std::nothrow_t *v12; // rdx
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, _QWORD *, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rsi
  __int128 v15; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v17; // xmm8
  IRecordInfo *v18; // xmm9_8
  __int128 v19; // xmm10
  IRecordInfo *v20; // xmm11_8
  __int64 v21; // rdi
  _QWORD *v22; // rdx
  const struct std::nothrow_t *v23; // rdx
  CEnrollmentLogger *Logger; // rax
  int v26[2]; // [rsp+78h] [rbp-90h] BYREF
  int v27[2]; // [rsp+80h] [rbp-88h] BYREF
  BSTR *v28; // [rsp+88h] [rbp-80h] BYREF
  __int64 v29; // [rsp+90h] [rbp-78h] BYREF
  int v30[2]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v31[2]; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG v32; // [rsp+B0h] [rbp-58h] BYREF
  VARIANTARG v33; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v35; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v36; // [rsp+108h] [rbp+0h]
  __int128 v37; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v38; // [rsp+128h] [rbp+20h]
  __int128 v39; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v40; // [rsp+148h] [rbp+40h]
  __int64 *v41; // [rsp+208h] [rbp+100h] BYREF

  a6 = 0;
  v31[0] = "ScheduleOneOmaDmSessionMaintenanceCycle";
  v31[1] = &a6;
  *(_QWORD *)v30 = 0;
  *(_QWORD *)v27 = 0;
  *(_QWORD *)v26 = 0;
  a5 = 0;
  v29 = 0;
  v41 = 0;
  v7 = CreateTask(
         v30,
         (__int64 *)v27,
         v26,
         &a5,
         a2,
         L"%windir%\\system32\\deviceenroller.exe ",
         a4,
         L"S-1-5-18",
         0,
         1,
         1,
         1,
         0);
  a6 = v7;
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)a5 + 424LL))(a5, &v41);
    a6 = v7;
    if ( v7 >= 0 )
    {
      v8 = v41;
      v9 = *v41;
      v10 = (BSTR *)operator new(0x18u);
      v10[1] = 0;
      *((_DWORD *)v10 + 4) = 1;
      v11 = _com_util::ConvertStringToBSTR("P1D");
      *v10 = v11;
      if ( !v11 )
        _com_issue_error(-2147024882);
      v28 = v10;
      a6 = (*(__int64 (__fastcall **)(__int64 *, BSTR))(v9 + 56))(v8, v11);
      _bstr_t::~_bstr_t((_bstr_t *)&v28, v12);
      v7 = a6;
      if ( a6 >= 0 )
      {
        v13 = *(_QWORD *)v27;
        v14 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(**(_QWORD **)v27 + 136LL);
        VariantInit(&pvarg);
        v15 = *(_OWORD *)&pvarg.vt;
        pRecInfo = pvarg.pRecInfo;
        VariantInit(&v33);
        v17 = *(_OWORD *)&v33.vt;
        v18 = v33.pRecInfo;
        VariantInit(&v32);
        v19 = *(_OWORD *)&v32.vt;
        v20 = v32.pRecInfo;
        v21 = *(_QWORD *)v26;
        v22 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v28, a1);
        if ( v22 )
          v22 = (_QWORD *)*v22;
        v35 = v15;
        v36 = pRecInfo;
        v37 = v17;
        v38 = v18;
        v39 = v19;
        v40 = v20;
        a6 = v14(v13, v22, v21, 6, &v39, &v37, 3, &v35, &v29);
        _bstr_t::~_bstr_t((_bstr_t *)&v28, v23);
        VariantClear(&v32);
        VariantClear(&v33);
        VariantClear(&pvarg);
        v7 = a6;
        if ( a6 < 0 )
        {
          Logger = CEnrollmentLogger::GetLogger();
          CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, a6, "ScheduleOneOmaDmSessionMaintenanceCycle");
          v7 = a6;
        }
      }
    }
  }
  if ( v41 )
    (*(void (__fastcall **)(__int64 *))(*v41 + 16))(v41);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v29);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&a5);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v26);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v27);
  if ( *(_QWORD *)v30 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v30 + 16LL))(*(_QWORD *)v30);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v31);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180019e58  mov     rax, rsp
0x180019e5b  mov     [rax+18h], r8
0x180019e5f  push    rbp
0x180019e60  push    rbx
0x180019e61  push    rsi
0x180019e62  push    rdi
0x180019e63  push    r13
0x180019e65  push    r14
0x180019e67  lea     rbp, [rax-0E8h]
0x180019e6e  sub     rsp, 1B8h
0x180019e75  movaps  xmmword ptr [rax-48h], xmm6
0x180019e79  movaps  xmmword ptr [rax-58h], xmm7
0x180019e7d  movaps  xmmword ptr [rax-68h], xmm8
0x180019e82  movaps  xmmword ptr [rax-78h], xmm9
0x180019e87  movaps  xmmword ptr [rax-88h], xmm10
0x180019e8f  movaps  xmmword ptr [rax-98h], xmm11
0x180019e97  mov     r14, rcx
0x180019e9a  mov     [rbp+0E0h+arg_28], 0
0x180019ea4  lea     r13, aScheduleoneoma_1; "ScheduleOneOmaDmSessionMaintenanceCycle"
0x180019eab  mov     [rbp+0E0h+var_148], r13
0x180019eaf  lea     rax, [rbp+0E0h+arg_28]
0x180019eb6  mov     [rbp+0E0h+var_140], rax
0x180019eba  mov     qword ptr [rbp+0E0h+var_150], 0
0x180019ec2  mov     qword ptr [rsp+1E0h+var_168], 0
0x180019ecb  mov     qword ptr [rsp+1E0h+var_170], 0
0x180019ed4  mov     [rbp+0E0h+arg_20], 0
0x180019edf  mov     [rbp+0E0h+var_158], 0
0x180019ee7  mov     [rbp+0E0h+arg_10], 0
0x180019ef2  mov     [rsp+1E0h+var_180], 0; int
0x180019efa  mov     [rsp+1E0h+var_188], 1; int
0x180019f02  mov     [rsp+1E0h+var_190], 1; int
0x180019f0a  mov     [rsp+1E0h+var_198], 1; int
0x180019f12  mov     [rsp+1E0h+var_1A0], 0; int
0x180019f1a  lea     rax, psz; "S-1-5-18"
0x180019f21  mov     [rsp+1E0h+var_1A8], rax; unsigned __int16 *
0x180019f26  mov     [rsp+1E0h+var_1B0], r9; unsigned __int16 *
0x180019f2b  lea     rax, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe "
0x180019f32  mov     [rsp+1E0h+var_1B8], rax; unsigned __int16 *
0x180019f37  mov     [rsp+1E0h+var_1C0], rdx; unsigned __int16 *
0x180019f3c  lea     r9, [rbp+0E0h+arg_20]; int
0x180019f43  lea     r8, [rsp+1E0h+var_170]; int
0x180019f48  lea     rdx, [rsp+1E0h+var_168]; int
0x180019f4d  lea     rcx, [rbp+0E0h+var_150]; int
0x180019f51  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180019f56  mov     ebx, eax
0x180019f58  mov     [rbp+0E0h+arg_28], eax
0x180019f5e  test    eax, eax
0x180019f60  js      loc_18001A11B
0x180019f66  mov     rcx, [rbp+0E0h+arg_20]
0x180019f6d  mov     rax, [rcx]
0x180019f70  lea     rdx, [rbp+0E0h+arg_10]
0x180019f77  mov     rax, [rax+1A8h]
0x180019f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f83  mov     ebx, eax
0x180019f85  mov     [rbp+0E0h+arg_28], eax
0x180019f8b  test    eax, eax
0x180019f8d  js      loc_18001A11B
0x180019f93  mov     rdi, [rbp+0E0h+arg_10]
0x180019f9a  mov     rsi, [rdi]
0x180019f9d  mov     ecx, 18h; Size
0x180019fa2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019fa7  mov     rbx, rax
0x180019faa  mov     qword ptr [rax+8], 0
0x180019fb2  mov     dword ptr [rax+10h], 1
0x180019fb9  lea     rcx, aP1d; "P1D"
0x180019fc0  call    ?ConvertStringToBSTR@_com_util@@YAPEAGPEBD@Z; _com_util::ConvertStringToBSTR(char const *)
0x180019fc5  mov     [rbx], rax
0x180019fc8  test    rax, rax
0x180019fcb  jz      loc_18001A1B3
0x180019fd1  mov     [rbp+0E0h+var_160], rbx
0x180019fd5  mov     rdx, rax
0x180019fd8  mov     rcx, rdi
0x180019fdb  mov     rax, [rsi+38h]
0x180019fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fe4  mov     [rbp+0E0h+arg_28], eax
0x180019fea  lea     rcx, [rbp+0E0h+var_160]; this
0x180019fee  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180019ff3  mov     ebx, [rbp+0E0h+arg_28]
0x180019ff9  test    ebx, ebx
0x180019ffb  js      loc_18001A11B
0x18001a001  mov     rbx, qword ptr [rsp+1E0h+var_168]
0x18001a006  mov     rax, [rbx]
0x18001a009  mov     rsi, [rax+88h]
0x18001a010  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x18001a014  call    cs:__imp_VariantInit
0x18001a01a  movups  xmm6, xmmword ptr [rbp+0E0h+pvarg]
0x18001a01e  movsd   xmm7, qword ptr [rbp+0E0h+pvarg+10h]
0x18001a023  lea     rcx, [rbp+0E0h+var_120]; pvarg
0x18001a027  call    cs:__imp_VariantInit
0x18001a02d  movups  xmm8, xmmword ptr [rbp+0E0h+var_120]
0x18001a032  movsd   xmm9, qword ptr [rbp+0E0h+var_120+10h]
0x18001a038  lea     rcx, [rbp+0E0h+var_138]; pvarg
0x18001a03c  call    cs:__imp_VariantInit
0x18001a042  movups  xmm10, xmmword ptr [rbp+0E0h+var_138]
0x18001a047  movsd   xmm11, qword ptr [rbp+0E0h+var_138+10h]
0x18001a04d  mov     rdi, qword ptr [rsp+1E0h+var_170]
0x18001a052  mov     rdx, r14; unsigned __int16 *
0x18001a055  lea     rcx, [rbp+0E0h+var_160]; this
0x18001a059  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001a05e  mov     rdx, [rax]
0x18001a061  test    rdx, rdx
0x18001a064  jz      short loc_18001A069
0x18001a066  mov     rdx, [rdx]
0x18001a069  movaps  [rbp+0E0h+var_F0], xmm6
0x18001a06d  movsd   [rbp+0E0h+var_E0], xmm7
0x18001a072  movaps  [rbp+0E0h+var_D0], xmm8
0x18001a077  movsd   [rbp+0E0h+var_C0], xmm9
0x18001a07d  movaps  [rbp+0E0h+var_B0], xmm10
0x18001a082  movsd   [rbp+0E0h+var_A0], xmm11
0x18001a088  lea     rax, [rbp+0E0h+var_158]
0x18001a08c  mov     qword ptr [rsp+1E0h+var_1A0], rax
0x18001a091  lea     rax, [rbp+0E0h+var_F0]
0x18001a095  mov     [rsp+1E0h+var_1A8], rax
0x18001a09a  mov     dword ptr [rsp+1E0h+var_1B0], 3
0x18001a0a2  lea     rax, [rbp+0E0h+var_D0]
0x18001a0a6  mov     [rsp+1E0h+var_1B8], rax
0x18001a0ab  lea     rax, [rbp+0E0h+var_B0]
0x18001a0af  mov     [rsp+1E0h+var_1C0], rax
0x18001a0b4  mov     r9d, 6
0x18001a0ba  mov     r8, rdi
0x18001a0bd  mov     rcx, rbx
0x18001a0c0  mov     rax, rsi
0x18001a0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0c8  mov     [rbp+0E0h+arg_28], eax
0x18001a0ce  lea     rcx, [rbp+0E0h+var_160]; this
0x18001a0d2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a0d7  lea     rcx, [rbp+0E0h+var_138]; pvarg
0x18001a0db  call    cs:__imp_VariantClear
0x18001a0e1  lea     rcx, [rbp+0E0h+var_120]; pvarg
0x18001a0e5  call    cs:__imp_VariantClear
0x18001a0eb  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x18001a0ef  call    cs:__imp_VariantClear
0x18001a0f5  mov     ebx, [rbp+0E0h+arg_28]
0x18001a0fb  test    ebx, ebx
0x18001a0fd  jns     short loc_18001A11B
0x18001a0ff  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001a104  mov     r8, r13; char *
0x18001a107  mov     edx, [rbp+0E0h+arg_28]; int
0x18001a10d  mov     rcx, rax; this
0x18001a110  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18001a115  mov     ebx, [rbp+0E0h+arg_28]
0x18001a11b  mov     rcx, [rbp+0E0h+arg_10]
0x18001a122  test    rcx, rcx
0x18001a125  jz      short loc_18001A134
0x18001a127  mov     rax, [rcx]
0x18001a12a  mov     rax, [rax+10h]
0x18001a12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a133  nop
0x18001a134  lea     rcx, [rbp+0E0h+var_158]
0x18001a138  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a13d  nop
0x18001a13e  lea     rcx, [rbp+0E0h+arg_20]
0x18001a145  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a14a  nop
0x18001a14b  lea     rcx, [rsp+1E0h+var_170]
0x18001a150  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a155  nop
0x18001a156  lea     rcx, [rsp+1E0h+var_168]
0x18001a15b  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001a160  nop
0x18001a161  mov     rcx, qword ptr [rbp+0E0h+var_150]
0x18001a165  test    rcx, rcx
0x18001a168  jz      short loc_18001A176
0x18001a16a  mov     rdx, [rcx]
0x18001a16d  mov     rax, [rdx+10h]
0x18001a171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a176  lea     rcx, [rbp+0E0h+var_148]; this
0x18001a17a  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001a17f  mov     eax, ebx
0x18001a181  lea     r11, [rsp+1E0h+var_28]
0x18001a189  movaps  xmm6, xmmword ptr [r11-18h]
0x18001a18e  movaps  xmm7, xmmword ptr [r11-28h]
0x18001a193  movaps  xmm8, xmmword ptr [r11-38h]
0x18001a198  movaps  xmm9, xmmword ptr [r11-48h]
0x18001a19d  movaps  xmm10, xmmword ptr [r11-58h]
0x18001a1a2  movaps  xmm11, xmmword ptr [r11-68h]
0x18001a1a7  mov     rsp, r11
0x18001a1aa  pop     r14
0x18001a1ac  pop     r13
0x18001a1ae  pop     rdi
0x18001a1af  pop     rsi
0x18001a1b0  pop     rbx
0x18001a1b1  pop     rbp
0x18001a1b2  retn
0x18001a1b3  mov     ecx, 8007000Eh; int
0x18001a1b8  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
