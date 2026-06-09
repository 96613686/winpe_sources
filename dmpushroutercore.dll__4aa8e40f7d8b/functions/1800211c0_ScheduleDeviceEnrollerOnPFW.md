# ScheduleDeviceEnrollerOnPFW

- ea: `0x1800211c0`
- end: `0x180021687`
- name: `ScheduleDeviceEnrollerOnPFW`
- size: `1223`
- prototype: `__int64 __fastcall(OLECHAR *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023908`

## callees

- `0x1800039f0`
- `0x18000604c`
- `0x18000c63c`
- `0x18001cdb8`
- `0x18001ce6c`
- `0x18001dd58`
- `0x1800211c0`
- `0x1800245fc`
- `0x180024b94`
- `0x18003593c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002164e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002164e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180021232`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180021232`
- `OLEAUT32!__imp_SysAllocString` at `0x1800213c8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002146b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800214b2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800213c8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002146b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800214b2`
- `OLEAUT32!__imp_VariantInit` at `0x180021434`
- `OLEAUT32!__imp_VariantInit` at `0x180021449`
- `OLEAUT32!__imp_VariantInit` at `0x180021434`
- `OLEAUT32!__imp_VariantInit` at `0x180021449`
- `OLEAUT32!__imp_VariantClear` at `0x18002153f`
- `OLEAUT32!__imp_VariantClear` at `0x180021551`
- `OLEAUT32!__imp_VariantClear` at `0x180021563`
- `OLEAUT32!__imp_VariantClear` at `0x18002153f`
- `OLEAUT32!__imp_VariantClear` at `0x180021551`
- `OLEAUT32!__imp_VariantClear` at `0x180021563`

## string_xrefs

- `0x1800213b3`: `<QueryList><Query Id="0" Path="Microsoft-Windows-User Device Registration/Admin"><Select Path="Microsoft-Windows-User Device Registration/Admin">*[System[Provider[@Name='Microsoft-Windows-User Device Registration'] and EventID=300]]</Select></Query></QueryList>`
- `0x180021317`: `%windir%\system32\deviceenroller.exe `
- `0x18002120c`: `ScheduleDeviceEnrollerOnPFW`
- `0x180021592`: `ScheduleDeviceEnrollerOnPFW`
- `0x18002149d`: `Passport for Work alert created by enrollment client`

## pseudocode

```c
__int64 __fastcall ScheduleDeviceEnrollerOnPFW(OLECHAR *a1, unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  __int64 *v6; // rsi
  __int64 v7; // r14
  BSTR *v8; // rbx
  BSTR v9; // rax
  __int64 *v10; // rsi
  __int64 v11; // r14
  __int128 v12; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v14; // xmm10
  IRecordInfo *v15; // xmm11_8
  BSTR v16; // rax
  IRecordInfo *v17; // xmm7_8
  __int64 v18; // rdi
  __int128 v19; // xmm6
  BSTR *v20; // rbx
  BSTR v21; // rax
  BSTR v22; // rdx
  __int64 (__fastcall *v23)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rax
  HRESULT v24; // eax
  HRESULT v25; // eax
  HRESULT v26; // eax
  CEnrollmentLogger *Logger; // rax
  int v28[2]; // [rsp+78h] [rbp-90h] BYREF
  int v29[2]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v30; // [rsp+88h] [rbp-80h] BYREF
  __int64 *v31; // [rsp+90h] [rbp-78h] BYREF
  __int64 v32; // [rsp+98h] [rbp-70h] BYREF
  int v33[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v34; // [rsp+A8h] [rbp-60h] BYREF
  int v35[2]; // [rsp+B0h] [rbp-58h] BYREF
  int v36[2]; // [rsp+B8h] [rbp-50h] BYREF
  BSTR *v37; // [rsp+C0h] [rbp-48h] BYREF
  _QWORD v38[2]; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v39; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG v40; // [rsp+F0h] [rbp-18h] BYREF
  VARIANTARG pvarg; // [rsp+108h] [rbp+0h] BYREF
  __int128 v42; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v43; // [rsp+138h] [rbp+30h]
  __int128 v44; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v45; // [rsp+158h] [rbp+50h]
  __int128 v46; // [rsp+168h] [rbp+60h] BYREF
  IRecordInfo *v47; // [rsp+178h] [rbp+70h]
  unsigned __int16 v48[264]; // [rsp+188h] [rbp+80h] BYREF

  v38[0] = "ScheduleDeviceEnrollerOnPFW";
  v38[1] = v28;
  v28[0] = 0;
  v28[0] = CoInitializeEx(0, 0);
  v4 = v28[0];
  if ( v28[0] >= 0 )
  {
    *(_QWORD *)v36 = 0;
    *(_QWORD *)v33 = 0;
    *(_QWORD *)v29 = 0;
    *(_QWORD *)v35 = 0;
    v30 = 0;
    v32 = 0;
    v31 = 0;
    v34 = 0;
    v28[0] = StringCchPrintfW(v48, 0x104u, L"/o \"%s\" /c /PFW", a1);
    if ( v28[0] >= 0 )
    {
      v28[0] = CreateTask(
                 (LPVOID *)v36,
                 (BSTR ***)v33,
                 v29,
                 v35,
                 a1,
                 L"%windir%\\system32\\deviceenroller.exe ",
                 v48,
                 a2,
                 0,
                 1,
                 0,
                 0,
                 0);
      if ( v28[0] >= 0 )
      {
        v28[0] = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v29 + 72LL))(*(_QWORD *)v29, &v30);
        if ( v28[0] >= 0 )
        {
          v28[0] = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 80LL))(v30, 0, &v32);
          if ( v28[0] >= 0 )
          {
            v28[0] = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v32)(v32, &IID_IEventTrigger, &v31);
            if ( v28[0] >= 0 )
            {
              v6 = v31;
              v7 = *v31;
              v8 = (BSTR *)operator new(0x18u);
              v8[1] = 0;
              *((_DWORD *)v8 + 4) = 1;
              v9 = SysAllocString(
                     L"<QueryList><Query Id=\"0\" Path=\"Microsoft-Windows-User Device Registration/Admin\"><Select Path=\""
                      "Microsoft-Windows-User Device Registration/Admin\">*[System[Provider[@Name='Microsoft-Windows-User"
                      " Device Registration'] and EventID=300]]</Select></Query></QueryList>");
              *v8 = v9;
              if ( !v9 )
                _com_issue_error(-2147024882);
              v37 = v8;
              v28[0] = (*(__int64 (__fastcall **)(__int64 *, BSTR))(v7 + 168))(v6, v9);
              _bstr_t::~_bstr_t((_bstr_t *)&v37);
              if ( v28[0] >= 0 )
              {
                v28[0] = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v29 + 80LL))(*(_QWORD *)v29, v30);
                if ( v28[0] >= 0 )
                {
                  v10 = *(__int64 **)v33;
                  v11 = **(_QWORD **)v33;
                  VariantInit(&pvarg);
                  v12 = *(_OWORD *)&pvarg.vt;
                  pRecInfo = pvarg.pRecInfo;
                  VariantInit(&v40);
                  v14 = *(_OWORD *)&v40.vt;
                  v15 = v40.pRecInfo;
                  if ( !a2 )
                    a2 = L"S-1-5-18";
                  v16 = SysAllocString(a2);
                  if ( !v16 )
                    goto LABEL_39;
                  v17 = v39.pRecInfo;
                  v18 = *(_QWORD *)v29;
                  v39.vt = 8;
                  v39.llVal = (LONGLONG)v16;
                  v19 = *(_OWORD *)&v39.vt;
                  v20 = (BSTR *)operator new(0x18u);
                  v20[1] = 0;
                  *((_DWORD *)v20 + 4) = 1;
                  v21 = SysAllocString(L"Passport for Work alert created by enrollment client");
                  *v20 = v21;
                  if ( !v21 )
LABEL_39:
                    _com_issue_error(-2147024882);
                  v37 = v20;
                  v22 = v21;
                  v23 = *(__int64 (__fastcall **)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v11 + 136);
                  v42 = v12;
                  v43 = pRecInfo;
                  v44 = v14;
                  v45 = v15;
                  v46 = v19;
                  v47 = v17;
                  v28[0] = v23(v10, v22, v18, 6, &v46, &v44, 3, &v42, &v34);
                  _bstr_t::~_bstr_t((_bstr_t *)&v37);
                  v24 = VariantClear(&v39);
                  if ( v24 < 0 )
                    _com_issue_error(v24);
                  v25 = VariantClear(&v40);
                  if ( v25 < 0 )
                    _com_issue_error(v25);
                  v26 = VariantClear(&pvarg);
                  if ( v26 < 0 )
                    _com_issue_error(v26);
                  if ( (int)(v28[0] + 0x80000000) >= 0 && v28[0] != -2147024769 )
                  {
                    Logger = CEnrollmentLogger::GetLogger();
                    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, v28[0], "ScheduleDeviceEnrollerOnPFW");
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( v31 )
      (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    if ( *(_QWORD *)v35 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v35 + 16LL))(*(_QWORD *)v35);
    if ( *(_QWORD *)v29 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 16LL))(*(_QWORD *)v29);
    if ( *(_QWORD *)v33 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33 + 16LL))(*(_QWORD *)v33);
    if ( *(_QWORD *)v36 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v36 + 16LL))(*(_QWORD *)v36);
    v4 = v28[0];
    CoUninitialize();
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v38);
  return v4;
}

```

## disassembly

```asm
0x1800211c0  mov     rax, rsp
0x1800211c3  mov     [rax+18h], rbx
0x1800211c7  push    rbp
0x1800211c8  push    rsi
0x1800211c9  push    rdi
0x1800211ca  push    r14
0x1800211cc  push    r15
0x1800211ce  lea     rbp, [rax-328h]
0x1800211d5  sub     rsp, 400h
0x1800211dc  movaps  xmmword ptr [rax-38h], xmm6
0x1800211e0  movaps  xmmword ptr [rax-48h], xmm7
0x1800211e4  movaps  xmmword ptr [rax-58h], xmm8
0x1800211e9  movaps  xmmword ptr [rax-68h], xmm9
0x1800211ee  movaps  xmmword ptr [rax-78h], xmm10
0x1800211f3  movaps  xmmword ptr [rax-88h], xmm11
0x1800211fb  mov     rax, cs:__security_cookie
0x180021202  xor     rax, rsp
0x180021205  mov     [rbp+320h+var_90], rax
0x18002120c  lea     rax, aScheduledevice_0; "ScheduleDeviceEnrollerOnPFW"
0x180021213  mov     rdi, rdx
0x180021216  mov     [rbp+320h+var_360], rax
0x18002121a  mov     rsi, rcx
0x18002121d  lea     rax, [rsp+420h+var_3B0]
0x180021222  xor     r15d, r15d
0x180021225  xor     edx, edx; dwCoInit
0x180021227  mov     [rbp+320h+var_358], rax
0x18002122b  xor     ecx, ecx; pvReserved
0x18002122d  mov     [rsp+420h+var_3B0], r15d
0x180021232  call    cs:__imp_CoInitializeEx
0x180021238  mov     [rsp+420h+var_3B0], eax
0x18002123c  mov     ebx, eax
0x18002123e  test    eax, eax
0x180021240  jns     short loc_180021291
0x180021242  lea     rcx, [rbp+320h+var_360]; this
0x180021246  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002124b  mov     eax, ebx
0x18002124d  mov     rcx, [rbp+320h+var_90]
0x180021254  xor     rcx, rsp; StackCookie
0x180021257  call    __security_check_cookie
0x18002125c  lea     r11, [rsp+420h+var_20]
0x180021264  mov     rbx, [r11+40h]
0x180021268  movaps  xmm6, xmmword ptr [r11-10h]
0x18002126d  movaps  xmm7, xmmword ptr [r11-20h]
0x180021272  movaps  xmm8, xmmword ptr [r11-30h]
0x180021277  movaps  xmm9, xmmword ptr [r11-40h]
0x18002127c  movaps  xmm10, xmmword ptr [r11-50h]
0x180021281  movaps  xmm11, xmmword ptr [r11-60h]
0x180021286  mov     rsp, r11
0x180021289  pop     r15
0x18002128b  pop     r14
0x18002128d  pop     rdi
0x18002128e  pop     rsi
0x18002128f  pop     rbp
0x180021290  retn
0x180021291  mov     r9, rsi
0x180021294  mov     qword ptr [rbp+320h+var_370], r15
0x180021298  lea     r8, aOSCPfw; "/o \"%s\" /c /PFW"
0x18002129f  mov     qword ptr [rbp+320h+var_388], r15
0x1800212a3  mov     edx, 104h; unsigned __int64
0x1800212a8  mov     qword ptr [rsp+420h+var_3A8], r15
0x1800212ad  lea     rcx, [rbp+320h+var_2A0]; unsigned __int16 *
0x1800212b4  mov     qword ptr [rbp+320h+var_378], r15
0x1800212b8  mov     [rbp+320h+var_3A0], r15
0x1800212bc  mov     [rbp+320h+var_390], r15
0x1800212c0  mov     [rbp+320h+var_398], r15
0x1800212c4  mov     [rbp+320h+var_380], r15
0x1800212c8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800212cd  mov     [rsp+420h+var_3B0], eax
0x1800212d1  test    eax, eax
0x1800212d3  js      loc_1800215A1
0x1800212d9  mov     [rsp+420h+Data], r15d; Data
0x1800212de  lea     rax, [rbp+320h+var_2A0]
0x1800212e5  mov     [rsp+420h+var_3C8], r15d; int
0x1800212ea  lea     r9, [rbp+320h+var_378]; int
0x1800212ee  mov     [rsp+420h+var_3D0], r15d; int
0x1800212f3  lea     r8, [rsp+420h+var_3A8]; int
0x1800212f8  mov     [rsp+420h+var_3D8], 1; int
0x180021300  lea     rdx, [rbp+320h+var_388]; int
0x180021304  mov     [rsp+420h+var_3E0], r15d; int
0x180021309  lea     rcx, [rbp+320h+var_370]; int
0x18002130d  mov     [rsp+420h+var_3E8], rdi; unsigned __int16 *
0x180021312  mov     [rsp+420h+var_3F0], rax; unsigned __int16 *
0x180021317  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x18002131e  mov     [rsp+420h+var_3F8], rax; unsigned __int16 *
0x180021323  mov     [rsp+420h+var_400], rsi; OLECHAR *
0x180021328  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x18002132d  mov     [rsp+420h+var_3B0], eax
0x180021331  test    eax, eax
0x180021333  js      loc_1800215A1
0x180021339  mov     rcx, qword ptr [rsp+420h+var_3A8]
0x18002133e  lea     rdx, [rbp+320h+var_3A0]
0x180021342  mov     rax, [rcx]
0x180021345  mov     rax, [rax+48h]
0x180021349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002134e  mov     [rsp+420h+var_3B0], eax
0x180021352  test    eax, eax
0x180021354  js      loc_1800215A1
0x18002135a  mov     rcx, [rbp+320h+var_3A0]
0x18002135e  lea     r8, [rbp+320h+var_390]
0x180021362  xor     edx, edx
0x180021364  mov     rax, [rcx]
0x180021367  mov     rax, [rax+50h]
0x18002136b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021370  mov     [rsp+420h+var_3B0], eax
0x180021374  test    eax, eax
0x180021376  js      loc_1800215A1
0x18002137c  mov     rcx, [rbp+320h+var_390]
0x180021380  lea     r8, [rbp+320h+var_398]
0x180021384  lea     rdx, IID_IEventTrigger
0x18002138b  mov     rax, [rcx]
0x18002138e  mov     rax, [rax]
0x180021391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021396  mov     [rsp+420h+var_3B0], eax
0x18002139a  test    eax, eax
0x18002139c  js      loc_1800215A1
0x1800213a2  mov     rsi, [rbp+320h+var_398]
0x1800213a6  mov     ecx, 18h; Size
0x1800213ab  mov     r14, [rsi]
0x1800213ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800213b3  lea     rcx, aQuerylistQuery; "<QueryList><Query Id=\"0\" Path=\"Micro"...
0x1800213ba  mov     rbx, rax
0x1800213bd  mov     [rax+8], r15
0x1800213c1  mov     dword ptr [rax+10h], 1
0x1800213c8  call    cs:__imp_SysAllocString
0x1800213ce  mov     [rbx], rax
0x1800213d1  test    rax, rax
0x1800213d4  jz      loc_18002166C
0x1800213da  mov     rdx, rax
0x1800213dd  mov     [rbp+320h+var_368], rbx
0x1800213e1  mov     rax, [r14+0A8h]
0x1800213e8  mov     rcx, rsi
0x1800213eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213f0  lea     rcx, [rbp+320h+var_368]; this
0x1800213f4  mov     [rsp+420h+var_3B0], eax
0x1800213f8  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800213fd  cmp     [rsp+420h+var_3B0], r15d
0x180021402  jl      loc_1800215A1
0x180021408  mov     rcx, qword ptr [rsp+420h+var_3A8]
0x18002140d  mov     rdx, [rbp+320h+var_3A0]
0x180021411  mov     rax, [rcx]
0x180021414  mov     rax, [rax+50h]
0x180021418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002141d  mov     [rsp+420h+var_3B0], eax
0x180021421  test    eax, eax
0x180021423  js      loc_1800215A1
0x180021429  mov     rsi, qword ptr [rbp+320h+var_388]
0x18002142d  lea     rcx, [rbp+320h+pvarg]; pvarg
0x180021431  mov     r14, [rsi]
0x180021434  call    cs:__imp_VariantInit
0x18002143a  movups  xmm8, xmmword ptr [rbp+320h+pvarg]
0x18002143f  lea     rcx, [rbp+320h+var_338]; pvarg
0x180021443  movsd   xmm9, qword ptr [rbp+320h+pvarg+10h]
0x180021449  call    cs:__imp_VariantInit
0x18002144f  movups  xmm10, xmmword ptr [rbp+320h+var_338]
0x180021454  lea     rax, aS1518; "S-1-5-18"
0x18002145b  test    rdi, rdi
0x18002145e  movsd   xmm11, qword ptr [rbp+320h+var_338+10h]
0x180021464  cmovz   rdi, rax
0x180021468  mov     rcx, rdi; psz
0x18002146b  call    cs:__imp_SysAllocString
0x180021471  test    rax, rax
0x180021474  jz      loc_180021661
0x18002147a  movsd   xmm7, qword ptr [rbp+320h+var_350+10h]
0x18002147f  mov     edx, 8
0x180021484  mov     rdi, qword ptr [rsp+420h+var_3A8]
0x180021489  mov     word ptr [rbp+320h+var_350], dx
0x18002148d  mov     qword ptr [rbp+320h+var_350+8], rax
0x180021491  movups  xmm6, xmmword ptr [rbp+320h+var_350]
0x180021495  lea     ecx, [rdx+10h]; Size
0x180021498  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002149d  lea     rcx, aPassportForWor; "Passport for Work alert created by enro"...
0x1800214a4  mov     rbx, rax
0x1800214a7  mov     [rax+8], r15
0x1800214ab  mov     dword ptr [rax+10h], 1
0x1800214b2  call    cs:__imp_SysAllocString
0x1800214b8  mov     [rbx], rax
0x1800214bb  test    rax, rax
0x1800214be  jz      loc_180021661
0x1800214c4  lea     rcx, [rbp+320h+var_380]
0x1800214c8  mov     [rbp+320h+var_368], rbx
0x1800214cc  mov     qword ptr [rsp+420h+var_3E0], rcx
0x1800214d1  mov     rdx, rax
0x1800214d4  mov     rax, [r14+88h]
0x1800214db  lea     rcx, [rbp+320h+var_300]
0x1800214df  mov     [rsp+420h+var_3E8], rcx
0x1800214e4  mov     r9d, 6
0x1800214ea  lea     rcx, [rbp+320h+var_2E0]
0x1800214ee  mov     dword ptr [rsp+420h+var_3F0], 3
0x1800214f6  mov     [rsp+420h+var_3F8], rcx
0x1800214fb  mov     r8, rdi
0x1800214fe  lea     rcx, [rbp+320h+var_2C0]
0x180021502  movaps  [rbp+320h+var_300], xmm8
0x180021507  mov     [rsp+420h+var_400], rcx
0x18002150c  mov     rcx, rsi
0x18002150f  movsd   [rbp+320h+var_2F0], xmm9
0x180021515  movaps  [rbp+320h+var_2E0], xmm10
0x18002151a  movsd   [rbp+320h+var_2D0], xmm11
0x180021520  movaps  [rbp+320h+var_2C0], xmm6
0x180021524  movsd   [rbp+320h+var_2B0], xmm7
0x180021529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002152e  lea     rcx, [rbp+320h+var_368]; this
0x180021532  mov     [rsp+420h+var_3B0], eax
0x180021536  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18002153b  lea     rcx, [rbp+320h+var_350]; pvarg
0x18002153f  call    cs:__imp_VariantClear
0x180021545  test    eax, eax
0x180021547  js      loc_180021677
0x18002154d  lea     rcx, [rbp+320h+var_338]; pvarg
0x180021551  call    cs:__imp_VariantClear
0x180021557  test    eax, eax
0x180021559  js      loc_18002167F
0x18002155f  lea     rcx, [rbp+320h+pvarg]; pvarg
0x180021563  call    cs:__imp_VariantClear
0x180021569  test    eax, eax
0x18002156b  js      loc_180021659
0x180021571  mov     ecx, [rsp+420h+var_3B0]
0x180021575  mov     edx, 80000000h
0x18002157a  lea     eax, [rcx+rdx]
0x18002157d  test    edx, eax
0x18002157f  jnz     short loc_1800215A1
0x180021581  cmp     ecx, 8007007Fh
0x180021587  jz      short loc_1800215A1
0x180021589  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18002158e  mov     edx, [rsp+420h+var_3B0]; int
0x180021592  lea     r8, aScheduledevice_0; "ScheduleDeviceEnrollerOnPFW"
0x180021599  mov     rcx, rax; this
0x18002159c  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x1800215a1  mov     rcx, [rbp+320h+var_380]
0x1800215a5  test    rcx, rcx
0x1800215a8  jz      short loc_1800215B6
0x1800215aa  mov     rax, [rcx]
0x1800215ad  mov     rax, [rax+10h]
0x1800215b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215b6  mov     rcx, [rbp+320h+var_398]
0x1800215ba  test    rcx, rcx
0x1800215bd  jz      short loc_1800215CB
0x1800215bf  mov     rax, [rcx]
0x1800215c2  mov     rax, [rax+10h]
0x1800215c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215cb  mov     rcx, [rbp+320h+var_390]
0x1800215cf  test    rcx, rcx
0x1800215d2  jz      short loc_1800215E0
0x1800215d4  mov     rax, [rcx]
0x1800215d7  mov     rax, [rax+10h]
0x1800215db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215e0  mov     rcx, [rbp+320h+var_3A0]
0x1800215e4  test    rcx, rcx
0x1800215e7  jz      short loc_1800215F5
0x1800215e9  mov     rax, [rcx]
0x1800215ec  mov     rax, [rax+10h]
0x1800215f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215f5  mov     rcx, qword ptr [rbp+320h+var_378]
0x1800215f9  test    rcx, rcx
0x1800215fc  jz      short loc_18002160A
0x1800215fe  mov     rax, [rcx]
0x180021601  mov     rax, [rax+10h]
0x180021605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002160a  mov     rcx, qword ptr [rsp+420h+var_3A8]
0x18002160f  test    rcx, rcx
0x180021612  jz      short loc_180021620
0x180021614  mov     rax, [rcx]
0x180021617  mov     rax, [rax+10h]
0x18002161b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021620  mov     rcx, qword ptr [rbp+320h+var_388]
0x180021624  test    rcx, rcx
0x180021627  jz      short loc_180021635
0x180021629  mov     rax, [rcx]
0x18002162c  mov     rax, [rax+10h]
0x180021630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021635  mov     rcx, qword ptr [rbp+320h+var_370]
0x180021639  test    rcx, rcx
0x18002163c  jz      short loc_18002164A
0x18002163e  mov     rax, [rcx]
0x180021641  mov     rax, [rax+10h]
0x180021645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002164a  mov     ebx, [rsp+420h+var_3B0]
0x18002164e  call    cs:__imp_CoUninitialize
0x180021654  jmp     loc_180021242
0x180021659  mov     ecx, eax; int
0x18002165b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180021661  mov     ecx, 8007000Eh; int
0x180021666  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002166c  mov     ecx, 8007000Eh; int
0x180021671  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180021677  mov     ecx, eax; int
0x180021679  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002167f  mov     ecx, eax; int
0x180021681  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
