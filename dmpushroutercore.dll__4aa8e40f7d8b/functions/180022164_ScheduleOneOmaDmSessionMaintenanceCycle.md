# ScheduleOneOmaDmSessionMaintenanceCycle

- ea: `0x180022164`
- end: `0x180022559`
- name: `ScheduleOneOmaDmSessionMaintenanceCycle`
- size: `1013`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *, __int64, unsigned __int16 *, __int64, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021b88`

## callees

- `0x18000604c`
- `0x18001cdb8`
- `0x18001ce6c`
- `0x18001dd58`
- `0x180022164`
- `0x1800245fc`
- `0x180024b94`
- `0x18003593c`
- `0x180035950`
- `0x18003b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180022370`
- `OLEAUT32!__imp_SysAllocString` at `0x180022370`
- `OLEAUT32!__imp_VariantInit` at `0x180022317`
- `OLEAUT32!__imp_VariantInit` at `0x18002232a`
- `OLEAUT32!__imp_VariantInit` at `0x18002233f`
- `OLEAUT32!__imp_VariantInit` at `0x180022317`
- `OLEAUT32!__imp_VariantInit` at `0x18002232a`
- `OLEAUT32!__imp_VariantInit` at `0x18002233f`
- `OLEAUT32!__imp_VariantClear` at `0x180022404`
- `OLEAUT32!__imp_VariantClear` at `0x180022416`
- `OLEAUT32!__imp_VariantClear` at `0x180022428`
- `OLEAUT32!__imp_VariantClear` at `0x180022404`
- `OLEAUT32!__imp_VariantClear` at `0x180022416`
- `OLEAUT32!__imp_VariantClear` at `0x180022428`

## string_xrefs

- `0x1800221fb`: `%windir%\system32\deviceenroller.exe `

## pseudocode

```c
__int64 __fastcall ScheduleOneOmaDmSessionMaintenanceCycle(
        OLECHAR *psz,
        OLECHAR *a2,
        __int64 a3,
        unsigned __int16 *a4,
        __int64 a5,
        int a6)
{
  unsigned int v7; // ebx
  __int64 *v8; // rdi
  __int64 v9; // r14
  unsigned __int16 **v10; // rbx
  unsigned __int16 *v11; // rax
  __int64 *v12; // rdi
  __int64 v13; // r14
  __int128 v14; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v16; // xmm8
  IRecordInfo *v17; // xmm9_8
  __int128 v18; // xmm10
  __int64 v19; // r15
  IRecordInfo *v20; // xmm11_8
  BSTR *v21; // rbx
  BSTR v22; // rax
  BSTR v23; // rdx
  __int64 (__fastcall *v24)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rax
  HRESULT v25; // eax
  HRESULT v26; // eax
  HRESULT v27; // eax
  CEnrollmentLogger *Logger; // rax
  int v30[2]; // [rsp+78h] [rbp-90h] BYREF
  int v31[2]; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int16 **v32; // [rsp+88h] [rbp-80h] BYREF
  __int64 v33; // [rsp+90h] [rbp-78h] BYREF
  int v34[2]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v35[2]; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG v36; // [rsp+B0h] [rbp-58h] BYREF
  VARIANTARG v37; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v39; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v40; // [rsp+108h] [rbp+0h]
  __int128 v41; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v42; // [rsp+128h] [rbp+20h]
  __int128 v43; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v44; // [rsp+148h] [rbp+40h]
  __int64 *v45; // [rsp+1F8h] [rbp+F0h] BYREF

  v35[0] = "ScheduleOneOmaDmSessionMaintenanceCycle";
  v35[1] = &a6;
  a6 = 0;
  *(_QWORD *)v34 = 0;
  *(_QWORD *)v31 = 0;
  *(_QWORD *)v30 = 0;
  a5 = 0;
  v33 = 0;
  v45 = 0;
  a6 = CreateTask(
         (LPVOID *)v34,
         (BSTR ***)v31,
         v30,
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
  v7 = a6;
  if ( a6 >= 0 )
  {
    a6 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)a5 + 424LL))(a5, &v45);
    v7 = a6;
    if ( a6 >= 0 )
    {
      v8 = v45;
      v9 = *v45;
      v10 = (unsigned __int16 **)operator new(0x18u);
      v10[1] = 0;
      *((_DWORD *)v10 + 4) = 1;
      v11 = _com_util::ConvertStringToBSTR("P1D");
      *v10 = v11;
      if ( !v11 )
        _com_issue_error(-2147024882);
      v32 = v10;
      a6 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 *))(v9 + 56))(v8, v11);
      _bstr_t::~_bstr_t((_bstr_t *)&v32);
      v7 = a6;
      if ( a6 >= 0 )
      {
        v12 = *(__int64 **)v31;
        v13 = **(_QWORD **)v31;
        VariantInit(&pvarg);
        v14 = *(_OWORD *)&pvarg.vt;
        pRecInfo = pvarg.pRecInfo;
        VariantInit(&v37);
        v16 = *(_OWORD *)&v37.vt;
        v17 = v37.pRecInfo;
        VariantInit(&v36);
        v18 = *(_OWORD *)&v36.vt;
        v19 = *(_QWORD *)v30;
        v20 = v36.pRecInfo;
        v21 = (BSTR *)operator new(0x18u);
        v21[1] = 0;
        *((_DWORD *)v21 + 4) = 1;
        v22 = SysAllocString(psz);
        *v21 = v22;
        if ( !v22 && psz )
          _com_issue_error(-2147024882);
        v32 = v21;
        v23 = v22;
        v24 = *(__int64 (__fastcall **)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v13 + 136);
        v39 = v14;
        v40 = pRecInfo;
        v41 = v16;
        v42 = v17;
        v43 = v18;
        v44 = v20;
        a6 = v24(v12, v23, v19, 6, &v43, &v41, 3, &v39, &v33);
        _bstr_t::~_bstr_t((_bstr_t *)&v32);
        v25 = VariantClear(&v36);
        if ( v25 < 0 )
          _com_issue_error(v25);
        v26 = VariantClear(&v37);
        if ( v26 < 0 )
          _com_issue_error(v26);
        v27 = VariantClear(&pvarg);
        if ( v27 < 0 )
          _com_issue_error(v27);
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
  if ( v45 )
    (*(void (__fastcall **)(__int64 *))(*v45 + 16))(v45);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( a5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a5 + 16LL))(a5);
  if ( *(_QWORD *)v30 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v30 + 16LL))(*(_QWORD *)v30);
  if ( *(_QWORD *)v31 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 16LL))(*(_QWORD *)v31);
  if ( *(_QWORD *)v34 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v34 + 16LL))(*(_QWORD *)v34);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v35);
  return v7;
}

```

## disassembly

```asm
0x180022164  mov     rax, rsp
0x180022167  mov     [rax+8], rbx
0x18002216b  mov     [rax+10h], rsi
0x18002216f  mov     [rax+18h], r8
0x180022173  push    rbp
0x180022174  push    rdi
0x180022175  push    r13
0x180022177  push    r14
0x180022179  push    r15
0x18002217b  lea     rbp, [rax-0D8h]
0x180022182  sub     rsp, 1B0h
0x180022189  movaps  xmmword ptr [rax-38h], xmm6
0x18002218d  lea     r8, [rsp+1D0h+var_160]; int
0x180022192  movaps  xmmword ptr [rax-48h], xmm7
0x180022196  mov     r13d, 1
0x18002219c  movaps  xmmword ptr [rax-58h], xmm8
0x1800221a1  mov     rsi, rcx
0x1800221a4  mov     [rsp+1D0h+Data], 0; Data
0x1800221ac  lea     rcx, [rbp+0D0h+var_140]; int
0x1800221b0  movaps  xmmword ptr [rax-68h], xmm9
0x1800221b5  mov     [rsp+1D0h+var_178], r13d; int
0x1800221ba  movaps  xmmword ptr [rax-78h], xmm10
0x1800221bf  mov     [rsp+1D0h+var_180], r13d; int
0x1800221c4  movaps  xmmword ptr [rax-88h], xmm11
0x1800221cc  lea     rax, aScheduleoneoma_1; "ScheduleOneOmaDmSessionMaintenanceCycle"
0x1800221d3  mov     [rsp+1D0h+var_188], r13d; int
0x1800221d8  mov     [rbp+0D0h+var_138], rax
0x1800221dc  lea     rax, [rbp+0D0h+arg_28]
0x1800221e3  mov     [rsp+1D0h+var_190], 0; int
0x1800221eb  mov     [rbp+0D0h+var_130], rax
0x1800221ef  lea     rax, aS1518; "S-1-5-18"
0x1800221f6  mov     [rsp+1D0h+var_198], rax; unsigned __int16 *
0x1800221fb  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x180022202  mov     [rsp+1D0h+var_1A0], r9; unsigned __int16 *
0x180022207  lea     r9, [rbp+0D0h+arg_20]; int
0x18002220e  mov     [rsp+1D0h+var_1A8], rax; unsigned __int16 *
0x180022213  mov     [rsp+1D0h+var_1B0], rdx; OLECHAR *
0x180022218  lea     rdx, [rsp+1D0h+var_158]; int
0x18002221d  mov     [rbp+0D0h+arg_28], 0
0x180022227  mov     qword ptr [rbp+0D0h+var_140], 0
0x18002222f  mov     qword ptr [rsp+1D0h+var_158], 0
0x180022238  mov     qword ptr [rsp+1D0h+var_160], 0
0x180022241  mov     [rbp+0D0h+arg_20], 0
0x18002224c  mov     [rbp+0D0h+var_148], 0
0x180022254  mov     [rbp+0D0h+arg_10], 0
0x18002225f  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180022264  mov     [rbp+0D0h+arg_28], eax
0x18002226a  mov     ebx, eax
0x18002226c  test    eax, eax
0x18002226e  js      loc_180022460
0x180022274  mov     rcx, [rbp+0D0h+arg_20]
0x18002227b  lea     rdx, [rbp+0D0h+arg_10]
0x180022282  mov     rax, [rcx]
0x180022285  mov     rax, [rax+1A8h]
0x18002228c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022291  mov     [rbp+0D0h+arg_28], eax
0x180022297  mov     ebx, eax
0x180022299  test    eax, eax
0x18002229b  js      loc_180022460
0x1800222a1  mov     rdi, [rbp+0D0h+arg_10]
0x1800222a8  lea     ecx, [r13+17h]; Size
0x1800222ac  mov     r14, [rdi]
0x1800222af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800222b4  lea     rcx, MultiByteStr; "P1D"
0x1800222bb  mov     rbx, rax
0x1800222be  mov     qword ptr [rax+8], 0
0x1800222c6  mov     [rax+10h], r13d
0x1800222ca  call    ?ConvertStringToBSTR@_com_util@@YAPEAGPEBD@Z; _com_util::ConvertStringToBSTR(char const *)
0x1800222cf  mov     [rbx], rax
0x1800222d2  test    rax, rax
0x1800222d5  jz      loc_180022533
0x1800222db  mov     rdx, rax
0x1800222de  mov     [rbp+0D0h+var_150], rbx
0x1800222e2  mov     rax, [r14+38h]
0x1800222e6  mov     rcx, rdi
0x1800222e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222ee  lea     rcx, [rbp+0D0h+var_150]; this
0x1800222f2  mov     [rbp+0D0h+arg_28], eax
0x1800222f8  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800222fd  mov     ebx, [rbp+0D0h+arg_28]
0x180022303  test    ebx, ebx
0x180022305  js      loc_180022460
0x18002230b  mov     rdi, qword ptr [rsp+1D0h+var_158]
0x180022310  lea     rcx, [rbp+0D0h+pvarg]; pvarg
0x180022314  mov     r14, [rdi]
0x180022317  call    cs:__imp_VariantInit
0x18002231d  movups  xmm6, xmmword ptr [rbp+0D0h+pvarg]
0x180022321  lea     rcx, [rbp+0D0h+var_110]; pvarg
0x180022325  movsd   xmm7, qword ptr [rbp+0D0h+pvarg+10h]
0x18002232a  call    cs:__imp_VariantInit
0x180022330  movups  xmm8, xmmword ptr [rbp+0D0h+var_110]
0x180022335  lea     rcx, [rbp+0D0h+var_128]; pvarg
0x180022339  movsd   xmm9, qword ptr [rbp+0D0h+var_110+10h]
0x18002233f  call    cs:__imp_VariantInit
0x180022345  movups  xmm10, xmmword ptr [rbp+0D0h+var_128]
0x18002234a  lea     ecx, [r13+17h]; Size
0x18002234e  mov     r15, qword ptr [rsp+1D0h+var_160]
0x180022353  movsd   xmm11, qword ptr [rbp+0D0h+var_128+10h]
0x180022359  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002235e  mov     rcx, rsi; psz
0x180022361  mov     rbx, rax
0x180022364  mov     qword ptr [rax+8], 0
0x18002236c  mov     [rax+10h], r13d
0x180022370  call    cs:__imp_SysAllocString
0x180022376  mov     [rbx], rax
0x180022379  test    rax, rax
0x18002237c  jnz     short loc_180022387
0x18002237e  test    rsi, rsi
0x180022381  jnz     loc_18002253E
0x180022387  lea     rcx, [rbp+0D0h+var_148]
0x18002238b  mov     [rbp+0D0h+var_150], rbx
0x18002238f  mov     qword ptr [rsp+1D0h+var_190], rcx
0x180022394  mov     rdx, rax
0x180022397  mov     rax, [r14+88h]
0x18002239e  lea     rcx, [rbp+0D0h+var_E0]
0x1800223a2  mov     [rsp+1D0h+var_198], rcx
0x1800223a7  mov     r9d, 6
0x1800223ad  lea     rcx, [rbp+0D0h+var_C0]
0x1800223b1  mov     dword ptr [rsp+1D0h+var_1A0], 3
0x1800223b9  mov     [rsp+1D0h+var_1A8], rcx
0x1800223be  mov     r8, r15
0x1800223c1  lea     rcx, [rbp+0D0h+var_A0]
0x1800223c5  movaps  [rbp+0D0h+var_E0], xmm6
0x1800223c9  mov     [rsp+1D0h+var_1B0], rcx
0x1800223ce  mov     rcx, rdi
0x1800223d1  movsd   [rbp+0D0h+var_D0], xmm7
0x1800223d6  movaps  [rbp+0D0h+var_C0], xmm8
0x1800223db  movsd   [rbp+0D0h+var_B0], xmm9
0x1800223e1  movaps  [rbp+0D0h+var_A0], xmm10
0x1800223e6  movsd   [rbp+0D0h+var_90], xmm11
0x1800223ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223f1  lea     rcx, [rbp+0D0h+var_150]; this
0x1800223f5  mov     [rbp+0D0h+arg_28], eax
0x1800223fb  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180022400  lea     rcx, [rbp+0D0h+var_128]; pvarg
0x180022404  call    cs:__imp_VariantClear
0x18002240a  test    eax, eax
0x18002240c  js      loc_180022549
0x180022412  lea     rcx, [rbp+0D0h+var_110]; pvarg
0x180022416  call    cs:__imp_VariantClear
0x18002241c  test    eax, eax
0x18002241e  js      loc_180022551
0x180022424  lea     rcx, [rbp+0D0h+pvarg]; pvarg
0x180022428  call    cs:__imp_VariantClear
0x18002242e  test    eax, eax
0x180022430  js      loc_18002252B
0x180022436  mov     ebx, [rbp+0D0h+arg_28]
0x18002243c  test    ebx, ebx
0x18002243e  jns     short loc_180022460
0x180022440  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180022445  mov     edx, [rbp+0D0h+arg_28]; int
0x18002244b  lea     r8, aScheduleoneoma_1; "ScheduleOneOmaDmSessionMaintenanceCycle"
0x180022452  mov     rcx, rax; this
0x180022455  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18002245a  mov     ebx, [rbp+0D0h+arg_28]
0x180022460  mov     rcx, [rbp+0D0h+arg_10]
0x180022467  test    rcx, rcx
0x18002246a  jz      short loc_180022478
0x18002246c  mov     rax, [rcx]
0x18002246f  mov     rax, [rax+10h]
0x180022473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022478  mov     rcx, [rbp+0D0h+var_148]
0x18002247c  test    rcx, rcx
0x18002247f  jz      short loc_18002248D
0x180022481  mov     rax, [rcx]
0x180022484  mov     rax, [rax+10h]
0x180022488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002248d  mov     rcx, [rbp+0D0h+arg_20]
0x180022494  test    rcx, rcx
0x180022497  jz      short loc_1800224A5
0x180022499  mov     rax, [rcx]
0x18002249c  mov     rax, [rax+10h]
0x1800224a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224a5  mov     rcx, qword ptr [rsp+1D0h+var_160]
0x1800224aa  test    rcx, rcx
0x1800224ad  jz      short loc_1800224BB
0x1800224af  mov     rax, [rcx]
0x1800224b2  mov     rax, [rax+10h]
0x1800224b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224bb  mov     rcx, qword ptr [rsp+1D0h+var_158]
0x1800224c0  test    rcx, rcx
0x1800224c3  jz      short loc_1800224D1
0x1800224c5  mov     rax, [rcx]
0x1800224c8  mov     rax, [rax+10h]
0x1800224cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224d1  mov     rcx, qword ptr [rbp+0D0h+var_140]
0x1800224d5  test    rcx, rcx
0x1800224d8  jz      short loc_1800224E6
0x1800224da  mov     rdx, [rcx]
0x1800224dd  mov     rax, [rdx+10h]
0x1800224e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224e6  lea     rcx, [rbp+0D0h+var_138]; this
0x1800224ea  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800224ef  lea     r11, [rsp+1D0h+var_20]
0x1800224f7  mov     eax, ebx
0x1800224f9  mov     rbx, [r11+30h]
0x1800224fd  mov     rsi, [r11+38h]
0x180022501  movaps  xmm6, xmmword ptr [r11-10h]
0x180022506  movaps  xmm7, xmmword ptr [r11-20h]
0x18002250b  movaps  xmm8, xmmword ptr [r11-30h]
0x180022510  movaps  xmm9, xmmword ptr [r11-40h]
0x180022515  movaps  xmm10, xmmword ptr [r11-50h]
0x18002251a  movaps  xmm11, xmmword ptr [r11-60h]
0x18002251f  mov     rsp, r11
0x180022522  pop     r15
0x180022524  pop     r14
0x180022526  pop     r13
0x180022528  pop     rdi
0x180022529  pop     rbp
0x18002252a  retn
0x18002252b  mov     ecx, eax; int
0x18002252d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180022533  mov     ecx, 8007000Eh; int
0x180022538  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002253e  mov     ecx, 8007000Eh; int
0x180022543  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180022549  mov     ecx, eax; int
0x18002254b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180022551  mov     ecx, eax; int
0x180022553  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
