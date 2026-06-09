# ScheduleProvisioningInitiatedSyncHelper

- ea: `0x1800225f8`
- end: `0x1800229ea`
- name: `ScheduleProvisioningInitiatedSyncHelper`
- size: `1010`
- prototype: `__int64 __fastcall(OLECHAR *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021690`

## callees

- `0x1800039f0`
- `0x18000604c`
- `0x18000c63c`
- `0x18001cdb8`
- `0x18001ce6c`
- `0x18001dd58`
- `0x1800225f8`
- `0x1800245fc`
- `0x180024b94`
- `0x18003593c`
- `0x18003b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180022822`
- `OLEAUT32!__imp_SysAllocString` at `0x180022871`
- `OLEAUT32!__imp_SysAllocString` at `0x180022822`
- `OLEAUT32!__imp_SysAllocString` at `0x180022871`
- `OLEAUT32!__imp_VariantInit` at `0x1800227fb`
- `OLEAUT32!__imp_VariantInit` at `0x18002280e`
- `OLEAUT32!__imp_VariantInit` at `0x1800227fb`
- `OLEAUT32!__imp_VariantInit` at `0x18002280e`
- `OLEAUT32!__imp_VariantClear` at `0x1800228fe`
- `OLEAUT32!__imp_VariantClear` at `0x180022910`
- `OLEAUT32!__imp_VariantClear` at `0x180022922`
- `OLEAUT32!__imp_VariantClear` at `0x1800228fe`
- `OLEAUT32!__imp_VariantClear` at `0x180022910`
- `OLEAUT32!__imp_VariantClear` at `0x180022922`

## string_xrefs

- `0x1800227ae`: `%windir%\system32\deviceenroller.exe `

## pseudocode

```c
__int64 __fastcall ScheduleProvisioningInitiatedSyncHelper(OLECHAR *a1)
{
  unsigned int v2; // ebx
  void (*v3)(void); // rax
  void (*v4)(void); // rax
  __int64 *v6; // rdi
  __int64 v7; // rsi
  __int128 v8; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v10; // xmm8
  IRecordInfo *v11; // xmm9_8
  BSTR v12; // rax
  IRecordInfo *v13; // xmm11_8
  __int64 v14; // r14
  __int128 v15; // xmm10
  BSTR *v16; // rbx
  BSTR v17; // rax
  BSTR v18; // rdx
  __int64 (__fastcall *v19)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rax
  const struct std::nothrow_t *v20; // rdx
  HRESULT v21; // eax
  HRESULT v22; // eax
  HRESULT v23; // eax
  CEnrollmentLogger *Logger; // rax
  int v25[2]; // [rsp+78h] [rbp-90h] BYREF
  int v26[2]; // [rsp+80h] [rbp-88h] BYREF
  int v27[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v28; // [rsp+90h] [rbp-78h] BYREF
  int v29[2]; // [rsp+98h] [rbp-70h] BYREF
  int v30[2]; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v31[2]; // [rsp+A8h] [rbp-60h] BYREF
  BSTR *v32; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v33; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v34; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v36; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v37; // [rsp+118h] [rbp+10h]
  __int128 v38; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v39; // [rsp+138h] [rbp+30h]
  __int128 v40; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v41; // [rsp+158h] [rbp+50h]
  unsigned __int16 v42[264]; // [rsp+168h] [rbp+60h] BYREF

  *(_QWORD *)v30 = 0;
  *(_QWORD *)v27 = 0;
  *(_QWORD *)v26 = 0;
  *(_QWORD *)v29 = 0;
  v28 = 0;
  v2 = StringCchPrintfW(v42, 0x104u, L"/c /ProvInitiatedSession /o \"%s\"", a1);
  v25[0] = v2;
  v31[1] = v25;
  v31[0] = "ScheduleProvisioningInitiatedSyncHelper";
  if ( (v2 & 0x80000000) != 0 )
  {
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v31);
    if ( !v28 )
      goto LABEL_5;
    v3 = *(void (**)(void))(*(_QWORD *)v28 + 16LL);
    goto LABEL_4;
  }
  v25[0] = CreateTask(
             v30,
             (BSTR ***)v27,
             v26,
             v29,
             a1,
             L"%windir%\\system32\\deviceenroller.exe ",
             v42,
             L"S-1-5-18",
             0,
             1,
             0,
             0,
             0);
  v2 = v25[0];
  if ( v25[0] < 0 )
  {
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v31);
    if ( !v28 )
    {
LABEL_5:
      if ( *(_QWORD *)v29 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 16LL))(*(_QWORD *)v29);
      if ( *(_QWORD *)v26 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v26 + 16LL))(*(_QWORD *)v26);
      if ( *(_QWORD *)v27 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 16LL))(*(_QWORD *)v27);
      if ( *(_QWORD *)v30 )
      {
        v4 = *(void (**)(void))(**(_QWORD **)v30 + 16LL);
LABEL_13:
        v4();
        return v2;
      }
      return v2;
    }
    v3 = *(void (**)(void))(*(_QWORD *)v28 + 16LL);
LABEL_4:
    v3();
    goto LABEL_5;
  }
  v6 = *(__int64 **)v27;
  v7 = **(_QWORD **)v27;
  VariantInit(&pvarg);
  v8 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v34);
  v10 = *(_OWORD *)&v34.vt;
  v11 = v34.pRecInfo;
  v12 = SysAllocString(L"S-1-5-18");
  if ( !v12 )
    goto LABEL_36;
  v13 = v33.pRecInfo;
  v14 = *(_QWORD *)v26;
  v33.vt = 8;
  v33.llVal = (LONGLONG)v12;
  v15 = *(_OWORD *)&v33.vt;
  v16 = (BSTR *)operator new(0x18u);
  v16[1] = 0;
  *((_DWORD *)v16 + 4) = 1;
  v17 = SysAllocString(L"Provisioning initiated session");
  *v16 = v17;
  if ( !v17 )
LABEL_36:
    _com_issue_error(-2147024882);
  v32 = v16;
  v18 = v17;
  v19 = *(__int64 (__fastcall **)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v7 + 136);
  v36 = v8;
  v37 = pRecInfo;
  v38 = v10;
  v39 = v11;
  v40 = v15;
  v41 = v13;
  v25[0] = v19(v6, v18, v14, 6, &v40, &v38, 3, &v36, &v28);
  _bstr_t::~_bstr_t((_bstr_t *)&v32, v20);
  v21 = VariantClear(&v33);
  if ( v21 < 0 )
    _com_issue_error(v21);
  v22 = VariantClear(&v34);
  if ( v22 < 0 )
    _com_issue_error(v22);
  v23 = VariantClear(&pvarg);
  if ( v23 < 0 )
    _com_issue_error(v23);
  v2 = v25[0];
  if ( v25[0] < 0 )
  {
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, v25[0], "ScheduleProvisioningInitiatedSyncHelper");
    v2 = v25[0];
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v31);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( *(_QWORD *)v29 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 16LL))(*(_QWORD *)v29);
  if ( *(_QWORD *)v26 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v26 + 16LL))(*(_QWORD *)v26);
  if ( *(_QWORD *)v27 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 16LL))(*(_QWORD *)v27);
  if ( *(_QWORD *)v30 )
  {
    v4 = *(void (**)(void))(**(_QWORD **)v30 + 16LL);
    goto LABEL_13;
  }
  return v2;
}

```

## disassembly

```asm
0x1800225f8  mov     rax, rsp
0x1800225fb  push    rbp
0x1800225fc  push    rbx
0x1800225fd  push    rsi
0x1800225fe  push    rdi
0x1800225ff  push    r12
0x180022601  push    r14
0x180022603  lea     rbp, [rax-318h]
0x18002260a  sub     rsp, 3E8h
0x180022611  movaps  xmmword ptr [rax-48h], xmm6
0x180022615  movaps  xmmword ptr [rax-58h], xmm7
0x180022619  movaps  xmmword ptr [rax-68h], xmm8
0x18002261e  movaps  xmmword ptr [rax-78h], xmm9
0x180022623  movaps  xmmword ptr [rax-88h], xmm10
0x18002262b  movaps  xmmword ptr [rax-98h], xmm11
0x180022633  mov     rax, cs:__security_cookie
0x18002263a  xor     rax, rsp
0x18002263d  mov     [rbp+310h+var_A0], rax
0x180022644  mov     rdi, rcx
0x180022647  mov     qword ptr [rbp+310h+var_378], 0
0x18002264f  mov     r9, rcx
0x180022652  mov     qword ptr [rbp+310h+var_390], 0
0x18002265a  lea     rcx, [rbp+310h+var_2B0]; unsigned __int16 *
0x18002265e  mov     qword ptr [rsp+410h+var_398], 0
0x180022667  lea     r8, aCProvinitiated; "/c /ProvInitiatedSession /o \"%s\""
0x18002266e  mov     qword ptr [rbp+310h+var_380], 0
0x180022676  mov     edx, 104h; unsigned __int64
0x18002267b  mov     [rbp+310h+var_388], 0
0x180022683  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022688  mov     ebx, eax
0x18002268a  mov     [rsp+410h+var_3A0], eax
0x18002268e  lea     rax, [rsp+410h+var_3A0]
0x180022693  mov     [rbp+310h+var_368], rax
0x180022697  lea     r12, aScheduleprovis; "ScheduleProvisioningInitiatedSyncHelper"
0x18002269e  mov     [rbp+310h+var_370], r12
0x1800226a2  test    ebx, ebx
0x1800226a4  jns     loc_180022760
0x1800226aa  lea     rcx, [rbp+310h+var_370]; this
0x1800226ae  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800226b3  mov     rcx, [rbp+310h+var_388]
0x1800226b7  test    rcx, rcx
0x1800226ba  jz      short loc_1800226C8
0x1800226bc  mov     rax, [rcx]
0x1800226bf  mov     rax, [rax+10h]
0x1800226c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226c8  mov     rcx, qword ptr [rbp+310h+var_380]
0x1800226cc  test    rcx, rcx
0x1800226cf  jz      short loc_1800226DD
0x1800226d1  mov     rax, [rcx]
0x1800226d4  mov     rax, [rax+10h]
0x1800226d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226dd  mov     rcx, qword ptr [rsp+410h+var_398]
0x1800226e2  test    rcx, rcx
0x1800226e5  jz      short loc_1800226F3
0x1800226e7  mov     rax, [rcx]
0x1800226ea  mov     rax, [rax+10h]
0x1800226ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226f3  mov     rcx, qword ptr [rbp+310h+var_390]
0x1800226f7  test    rcx, rcx
0x1800226fa  jz      short loc_180022708
0x1800226fc  mov     rax, [rcx]
0x1800226ff  mov     rax, [rax+10h]
0x180022703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022708  mov     rcx, qword ptr [rbp+310h+var_378]
0x18002270c  test    rcx, rcx
0x18002270f  jz      short loc_18002271D
0x180022711  mov     rax, [rcx]
0x180022714  mov     rax, [rax+10h]
0x180022718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002271d  mov     eax, ebx
0x18002271f  mov     rcx, [rbp+310h+var_A0]
0x180022726  xor     rcx, rsp; StackCookie
0x180022729  call    __security_check_cookie
0x18002272e  lea     r11, [rsp+410h+var_28]
0x180022736  movaps  xmm6, xmmword ptr [r11-18h]
0x18002273b  movaps  xmm7, xmmword ptr [r11-28h]
0x180022740  movaps  xmm8, xmmword ptr [r11-38h]
0x180022745  movaps  xmm9, xmmword ptr [r11-48h]
0x18002274a  movaps  xmm10, xmmword ptr [r11-58h]
0x18002274f  movaps  xmm11, xmmword ptr [r11-68h]
0x180022754  mov     rsp, r11
0x180022757  pop     r14
0x180022759  pop     r12
0x18002275b  pop     rdi
0x18002275c  pop     rsi
0x18002275d  pop     rbx
0x18002275e  pop     rbp
0x18002275f  retn
0x180022760  mov     [rsp+410h+Data], 0; Data
0x180022768  lea     rax, [rbp+310h+var_2B0]
0x18002276c  mov     [rsp+410h+var_3B8], 0; int
0x180022774  lea     r14, aS1518; "S-1-5-18"
0x18002277b  mov     [rsp+410h+var_3C0], 0; int
0x180022783  lea     r9, [rbp+310h+var_380]; int
0x180022787  mov     [rsp+410h+var_3C8], 1; int
0x18002278f  lea     r8, [rsp+410h+var_398]; int
0x180022794  mov     [rsp+410h+var_3D0], 0; int
0x18002279c  lea     rdx, [rbp+310h+var_390]; int
0x1800227a0  mov     [rsp+410h+var_3D8], r14; unsigned __int16 *
0x1800227a5  lea     rcx, [rbp+310h+var_378]; int
0x1800227a9  mov     [rsp+410h+var_3E0], rax; unsigned __int16 *
0x1800227ae  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x1800227b5  mov     [rsp+410h+var_3E8], rax; unsigned __int16 *
0x1800227ba  mov     [rsp+410h+var_3F0], rdi; OLECHAR *
0x1800227bf  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x1800227c4  mov     [rsp+410h+var_3A0], eax
0x1800227c8  mov     ebx, eax
0x1800227ca  test    eax, eax
0x1800227cc  jns     short loc_1800227F0
0x1800227ce  lea     rcx, [rbp+310h+var_370]; this
0x1800227d2  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800227d7  mov     rcx, [rbp+310h+var_388]
0x1800227db  test    rcx, rcx
0x1800227de  jz      loc_1800226C8
0x1800227e4  mov     rdx, [rcx]
0x1800227e7  mov     rax, [rdx+10h]
0x1800227eb  jmp     loc_1800226C3
0x1800227f0  mov     rdi, qword ptr [rbp+310h+var_390]
0x1800227f4  lea     rcx, [rbp+310h+pvarg]; pvarg
0x1800227f8  mov     rsi, [rdi]
0x1800227fb  call    cs:__imp_VariantInit
0x180022801  movups  xmm6, xmmword ptr [rbp+310h+pvarg]
0x180022805  lea     rcx, [rbp+310h+var_340]; pvarg
0x180022809  movsd   xmm7, qword ptr [rbp+310h+pvarg+10h]
0x18002280e  call    cs:__imp_VariantInit
0x180022814  movups  xmm8, xmmword ptr [rbp+310h+var_340]
0x180022819  mov     rcx, r14; psz
0x18002281c  movsd   xmm9, qword ptr [rbp+310h+var_340+10h]
0x180022822  call    cs:__imp_SysAllocString
0x180022828  test    rax, rax
0x18002282b  jz      loc_1800229CF
0x180022831  movsd   xmm11, qword ptr [rbp+310h+var_358+10h]
0x180022837  mov     ecx, 8
0x18002283c  mov     r14, qword ptr [rsp+410h+var_398]
0x180022841  mov     word ptr [rbp+310h+var_358], cx
0x180022845  mov     ecx, 18h; Size
0x18002284a  mov     qword ptr [rbp+310h+var_358+8], rax
0x18002284e  movups  xmm10, xmmword ptr [rbp+310h+var_358]
0x180022853  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022858  lea     rcx, aProvisioningIn; "Provisioning initiated session"
0x18002285f  mov     rbx, rax
0x180022862  mov     qword ptr [rax+8], 0
0x18002286a  mov     dword ptr [rax+10h], 1
0x180022871  call    cs:__imp_SysAllocString
0x180022877  mov     [rbx], rax
0x18002287a  test    rax, rax
0x18002287d  jz      loc_1800229CF
0x180022883  lea     rcx, [rbp+310h+var_388]
0x180022887  mov     [rbp+310h+var_360], rbx
0x18002288b  mov     qword ptr [rsp+410h+var_3D0], rcx
0x180022890  mov     rdx, rax
0x180022893  mov     rax, [rsi+88h]
0x18002289a  lea     rcx, [rbp+310h+var_310]
0x18002289e  mov     [rsp+410h+var_3D8], rcx
0x1800228a3  mov     r9d, 6
0x1800228a9  lea     rcx, [rbp+310h+var_2F0]
0x1800228ad  mov     dword ptr [rsp+410h+var_3E0], 3
0x1800228b5  mov     [rsp+410h+var_3E8], rcx
0x1800228ba  mov     r8, r14
0x1800228bd  lea     rcx, [rbp+310h+var_2D0]
0x1800228c1  movaps  [rbp+310h+var_310], xmm6
0x1800228c5  mov     [rsp+410h+var_3F0], rcx
0x1800228ca  mov     rcx, rdi
0x1800228cd  movsd   [rbp+310h+var_300], xmm7
0x1800228d2  movaps  [rbp+310h+var_2F0], xmm8
0x1800228d7  movsd   [rbp+310h+var_2E0], xmm9
0x1800228dd  movaps  [rbp+310h+var_2D0], xmm10
0x1800228e2  movsd   [rbp+310h+var_2C0], xmm11
0x1800228e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228ed  lea     rcx, [rbp+310h+var_360]; this
0x1800228f1  mov     [rsp+410h+var_3A0], eax
0x1800228f5  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800228fa  lea     rcx, [rbp+310h+var_358]; pvarg
0x1800228fe  call    cs:__imp_VariantClear
0x180022904  test    eax, eax
0x180022906  js      loc_1800229DA
0x18002290c  lea     rcx, [rbp+310h+var_340]; pvarg
0x180022910  call    cs:__imp_VariantClear
0x180022916  test    eax, eax
0x180022918  js      loc_1800229E2
0x18002291e  lea     rcx, [rbp+310h+pvarg]; pvarg
0x180022922  call    cs:__imp_VariantClear
0x180022928  test    eax, eax
0x18002292a  js      loc_1800229C7
0x180022930  mov     ebx, [rsp+410h+var_3A0]
0x180022934  test    ebx, ebx
0x180022936  jns     short loc_180022950
0x180022938  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18002293d  mov     edx, [rsp+410h+var_3A0]; int
0x180022941  mov     r8, r12; char *
0x180022944  mov     rcx, rax; this
0x180022947  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18002294c  mov     ebx, [rsp+410h+var_3A0]
0x180022950  lea     rcx, [rbp+310h+var_370]; this
0x180022954  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180022959  mov     rcx, [rbp+310h+var_388]
0x18002295d  test    rcx, rcx
0x180022960  jz      short loc_18002296E
0x180022962  mov     rax, [rcx]
0x180022965  mov     rax, [rax+10h]
0x180022969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002296e  mov     rcx, qword ptr [rbp+310h+var_380]
0x180022972  test    rcx, rcx
0x180022975  jz      short loc_180022983
0x180022977  mov     rax, [rcx]
0x18002297a  mov     rax, [rax+10h]
0x18002297e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022983  mov     rcx, qword ptr [rsp+410h+var_398]
0x180022988  test    rcx, rcx
0x18002298b  jz      short loc_180022999
0x18002298d  mov     rax, [rcx]
0x180022990  mov     rax, [rax+10h]
0x180022994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022999  mov     rcx, qword ptr [rbp+310h+var_390]
0x18002299d  test    rcx, rcx
0x1800229a0  jz      short loc_1800229AE
0x1800229a2  mov     rax, [rcx]
0x1800229a5  mov     rax, [rax+10h]
0x1800229a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229ae  mov     rcx, qword ptr [rbp+310h+var_378]
0x1800229b2  test    rcx, rcx
0x1800229b5  jz      loc_18002271D
0x1800229bb  mov     rdx, [rcx]
0x1800229be  mov     rax, [rdx+10h]
0x1800229c2  jmp     loc_180022718
0x1800229c7  mov     ecx, eax; int
0x1800229c9  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800229cf  mov     ecx, 8007000Eh; int
0x1800229d4  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800229da  mov     ecx, eax; int
0x1800229dc  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800229e2  mov     ecx, eax; int
0x1800229e4  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
