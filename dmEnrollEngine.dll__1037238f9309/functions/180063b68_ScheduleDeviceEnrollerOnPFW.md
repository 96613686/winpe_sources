# ScheduleDeviceEnrollerOnPFW

- ea: `0x180063b68`
- end: `0x180063fd6`
- name: `ScheduleDeviceEnrollerOnPFW`
- size: `1134`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180065d70`

## callees

- `0x1800067a0`
- `0x18000efc4`
- `0x1800140d0`
- `0x180018074`
- `0x18001aec8`
- `0x18002e1a0`
- `0x18002e570`
- `0x18003708c`
- `0x1800434d0`
- `0x180043544`
- `0x180060974`
- `0x1800613ac`
- `0x180063b68`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180063f84`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180063f84`
- `OLEAUT32!__imp_SysFreeString` at `0x180063d65`
- `OLEAUT32!__imp_SysFreeString` at `0x180063eb4`
- `OLEAUT32!__imp_SysFreeString` at `0x180063d65`
- `OLEAUT32!__imp_SysFreeString` at `0x180063eb4`
- `OLEAUT32!__imp_VariantInit` at `0x180063dcb`
- `OLEAUT32!__imp_VariantInit` at `0x180063dde`
- `OLEAUT32!__imp_VariantInit` at `0x180063dcb`
- `OLEAUT32!__imp_VariantInit` at `0x180063dde`

## string_xrefs

- `0x180063c7a`: `%windir%\system32\deviceenroller.exe `
- `0x180063e04`: `Passport for Work alert created by enrollment client`
- `0x180063bc3`: `ScheduleDeviceEnrollerOnPFW`
- `0x180063d09`: `<QueryList><Query Id="0" Path="Microsoft-Windows-User Device Registration/Admin"><Select Path="Microsoft-Windows-User Device Registration/Admin">*[System[Provider[@Name='Microsoft-Windows-User Device Registration'] and EventID=300]]</Select></Query></QueryList>`

## pseudocode

```c
__int64 __fastcall ScheduleDeviceEnrollerOnPFW(unsigned __int16 *a1, unsigned int a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rbx
  __int64 (__fastcall *v5)(__int64, __int64); // rdi
  _bstr_t *v6; // rax
  __int64 v7; // rdx
  int v8; // eax
  BSTR *v9; // rbx
  BSTR v10; // rcx
  struct IUnknown *v11; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // rsi
  __int128 v13; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v15; // xmm8
  IRecordInfo *v16; // xmm9_8
  _variant_t *v17; // rax
  __int64 v18; // rdi
  __int128 v19; // xmm10
  __int64 v20; // xmm11_8
  _bstr_t *v21; // rax
  __int64 v22; // rdx
  int v23; // eax
  BSTR *v24; // rbx
  BSTR v25; // rcx
  CEnrollmentLogger *Logger; // rax
  int v28; // [rsp+68h] [rbp-A0h]
  int v29[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v30; // [rsp+80h] [rbp-88h] BYREF
  __int64 v31; // [rsp+88h] [rbp-80h] BYREF
  void *Block[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-68h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp-60h] BYREF
  struct IUnknown *v35; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v36; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v39; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD v40[2]; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG v41; // [rsp+E8h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+100h] [rbp-8h] BYREF
  __int128 v43; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v44; // [rsp+128h] [rbp+20h]
  __int128 v45; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v46; // [rsp+148h] [rbp+40h]
  __int128 v47; // [rsp+158h] [rbp+50h] BYREF
  __int64 v48; // [rsp+168h] [rbp+60h]
  _BYTE v49[32]; // [rsp+178h] [rbp+70h] BYREF
  unsigned __int16 v50[264]; // [rsp+198h] [rbp+90h] BYREF

  v40[1] = v29;
  v29[0] = 0;
  v40[0] = "ScheduleDeviceEnrollerOnPFW";
  v29[1] = 0;
  v29[0] = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v29[1], a2);
  v3 = v29[0];
  if ( v29[0] >= 0 )
  {
    v38 = 0;
    v35 = 0;
    v30 = 0;
    v37 = 0;
    v31 = 0;
    v34 = 0;
    v33 = 0;
    v36 = 0;
    v39 = 0;
    v29[0] = StringCchPrintfW(v50, 0x104u, L"/o \"%s\" /c /PFW", a1);
    if ( v29[0] >= 0 )
    {
      v28 = 0;
      v29[0] = CreateTask(
                 &v38,
                 &v35,
                 &v30,
                 &v37,
                 a1,
                 L"%windir%\\system32\\deviceenroller.exe ",
                 v50,
                 0,
                 0,
                 1,
                 0,
                 0,
                 v28);
      if ( v29[0] >= 0 )
      {
        v29[0] = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 72LL))(v30, &v31);
        if ( v29[0] >= 0 )
        {
          v29[0] = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v31 + 80LL))(v31, 0, &v34);
          if ( v29[0] >= 0 )
          {
            v29[0] = (**v34)(v34, &IID_IEventTrigger, &v33);
            if ( v29[0] >= 0 )
            {
              v4 = v33;
              v5 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 168LL);
              v6 = _bstr_t::_bstr_t(
                     (_bstr_t *)Block,
                     L"<QueryList><Query Id=\"0\" Path=\"Microsoft-Windows-User Device Registration/Admin\"><Select Path=\""
                      "Microsoft-Windows-User Device Registration/Admin\">*[System[Provider[@Name='Microsoft-Windows-User"
                      " Device Registration'] and EventID=300]]</Select></Query></QueryList>");
              if ( *(_QWORD *)v6 )
                v7 = **(_QWORD **)v6;
              else
                v7 = 0;
              v8 = v5(v4, v7);
              v9 = (BSTR *)Block[0];
              v29[0] = v8;
              if ( Block[0] && _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v9 )
              {
                if ( *v9 )
                {
                  SysFreeString(*v9);
                  *v9 = 0;
                }
                v10 = v9[1];
                if ( v10 )
                {
                  operator delete(v10);
                  v9[1] = 0;
                }
                operator delete(v9);
              }
              if ( v29[0] >= 0 )
              {
                v29[0] = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 80LL))(v30, v31);
                if ( v29[0] >= 0 )
                {
                  v11 = v35;
                  Release = v35->lpVtbl[5].Release;
                  VariantInit(&pvarg);
                  v13 = *(_OWORD *)&pvarg.vt;
                  pRecInfo = pvarg.pRecInfo;
                  VariantInit(&v41);
                  v15 = *(_OWORD *)&v41.vt;
                  v16 = v41.pRecInfo;
                  v17 = _variant_t::_variant_t((_variant_t *)v49, L"S-1-5-18");
                  v18 = v30;
                  v19 = *(_OWORD *)v17;
                  v20 = *((_QWORD *)v17 + 2);
                  v21 = _bstr_t::_bstr_t((_bstr_t *)Block, L"Passport for Work alert created by enrollment client");
                  if ( *(_QWORD *)v21 )
                    v22 = **(_QWORD **)v21;
                  else
                    v22 = 0;
                  v43 = v13;
                  v44 = pRecInfo;
                  v45 = v15;
                  v46 = v16;
                  v47 = v19;
                  v48 = v20;
                  v23 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))Release)(
                          v11,
                          v22,
                          v18,
                          6,
                          &v47,
                          &v45,
                          3,
                          &v43,
                          &v36);
                  v24 = (BSTR *)Block[0];
                  v29[0] = v23;
                  if ( Block[0] )
                  {
                    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v24 )
                    {
                      if ( *v24 )
                      {
                        SysFreeString(*v24);
                        *v24 = 0;
                      }
                      v25 = v24[1];
                      if ( v25 )
                      {
                        operator delete(v25);
                        v24[1] = 0;
                      }
                      operator delete(v24);
                    }
                    Block[0] = 0;
                  }
                  _variant_t::~_variant_t((_variant_t *)v49);
                  _variant_t::~_variant_t((_variant_t *)&v41);
                  _variant_t::~_variant_t((_variant_t *)&pvarg);
                  if ( (int)(v29[0] + 0x80000000) >= 0 && v29[0] != -2147024769 )
                  {
                    Logger = CEnrollmentLogger::GetLogger();
                    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, v29[0], "ScheduleDeviceEnrollerOnPFW");
                  }
                }
              }
            }
          }
        }
      }
    }
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v39);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v36);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v33);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v34);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v31);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v37);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v30);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v35);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v38);
    v3 = v29[0];
  }
  if ( v29[1] )
    CoUninitialize();
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
  return v3;
}

```

## disassembly

```asm
0x180063b68  mov     rax, rsp
0x180063b6b  push    rbp
0x180063b6c  push    rbx
0x180063b6d  push    rsi
0x180063b6e  push    rdi
0x180063b6f  push    r13
0x180063b71  push    r14
0x180063b73  lea     rbp, [rax-348h]
0x180063b7a  sub     rsp, 418h
0x180063b81  movaps  xmmword ptr [rax-48h], xmm6
0x180063b85  movaps  xmmword ptr [rax-58h], xmm7
0x180063b89  movaps  xmmword ptr [rax-68h], xmm8
0x180063b8e  movaps  xmmword ptr [rax-78h], xmm9
0x180063b93  movaps  xmmword ptr [rax-88h], xmm10
0x180063b9b  movaps  xmmword ptr [rax-98h], xmm11
0x180063ba3  mov     rax, cs:__security_cookie
0x180063baa  xor     rax, rsp
0x180063bad  mov     [rbp+340h+var_A0], rax
0x180063bb4  mov     rdi, rcx
0x180063bb7  lea     rax, [rsp+440h+var_3D0]
0x180063bbc  xor     r14d, r14d
0x180063bbf  mov     [rbp+340h+var_368], rax
0x180063bc3  lea     r13, aScheduledevice_0; "ScheduleDeviceEnrollerOnPFW"
0x180063bca  mov     [rsp+440h+var_3D0], r14d
0x180063bcf  lea     rcx, [rsp+440h+var_3D0+4]; this
0x180063bd4  mov     [rbp+340h+var_370], r13
0x180063bd8  mov     [rsp+440h+var_3D0+4], r14d
0x180063bdd  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x180063be2  mov     [rsp+440h+var_3D0], eax
0x180063be6  mov     ebx, eax
0x180063be8  test    eax, eax
0x180063bea  js      loc_180063F7D
0x180063bf0  mov     r9, rdi
0x180063bf3  mov     [rbp+340h+var_380], r14
0x180063bf7  lea     r8, aOSCPfw; "/o \"%s\" /c /PFW"
0x180063bfe  mov     [rbp+340h+var_398], r14
0x180063c02  mov     edx, 104h; unsigned __int64
0x180063c07  mov     [rsp+440h+var_3C8], r14
0x180063c0c  lea     rcx, [rbp+340h+var_2B0]; unsigned __int16 *
0x180063c13  mov     [rbp+340h+var_388], r14
0x180063c17  mov     [rbp+340h+var_3C0], r14
0x180063c1b  mov     [rbp+340h+var_3A0], r14
0x180063c1f  mov     [rbp+340h+var_3A8], r14
0x180063c23  mov     [rbp+340h+var_390], r14
0x180063c27  mov     [rbp+340h+var_378], r14
0x180063c2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180063c30  mov     [rsp+440h+var_3D0], eax
0x180063c34  test    eax, eax
0x180063c36  js      loc_180063F27
0x180063c3c  mov     [rsp+440h+var_3E0], r14d
0x180063c41  lea     rax, [rbp+340h+var_2B0]
0x180063c48  mov     [rsp+440h+var_3E8], r14d
0x180063c4d  lea     r9, [rbp+340h+var_388]
0x180063c51  mov     [rsp+440h+var_3F0], r14d
0x180063c56  lea     r8, [rsp+440h+var_3C8]
0x180063c5b  mov     [rsp+440h+var_3F8], 1
0x180063c63  lea     rdx, [rbp+340h+var_398]
0x180063c67  mov     [rsp+440h+var_400], r14d
0x180063c6c  lea     rcx, [rbp+340h+var_380]
0x180063c70  mov     [rsp+440h+var_408], r14
0x180063c75  mov     [rsp+440h+var_410], rax
0x180063c7a  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x180063c81  mov     [rsp+440h+var_418], rax
0x180063c86  mov     [rsp+440h+var_420], rdi
0x180063c8b  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180063c90  mov     [rsp+440h+var_3D0], eax
0x180063c94  test    eax, eax
0x180063c96  js      loc_180063F27
0x180063c9c  mov     rcx, [rsp+440h+var_3C8]
0x180063ca1  lea     rdx, [rbp+340h+var_3C0]
0x180063ca5  mov     rax, [rcx]
0x180063ca8  mov     rax, [rax+48h]
0x180063cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cb1  mov     [rsp+440h+var_3D0], eax
0x180063cb5  test    eax, eax
0x180063cb7  js      loc_180063F27
0x180063cbd  mov     rcx, [rbp+340h+var_3C0]
0x180063cc1  lea     r8, [rbp+340h+var_3A0]
0x180063cc5  xor     edx, edx
0x180063cc7  mov     rax, [rcx]
0x180063cca  mov     rax, [rax+50h]
0x180063cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cd3  mov     [rsp+440h+var_3D0], eax
0x180063cd7  test    eax, eax
0x180063cd9  js      loc_180063F27
0x180063cdf  mov     rcx, [rbp+340h+var_3A0]
0x180063ce3  lea     r8, [rbp+340h+var_3A8]
0x180063ce7  lea     rdx, IID_IEventTrigger
0x180063cee  mov     rax, [rcx]
0x180063cf1  mov     rax, [rax]
0x180063cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cf9  mov     [rsp+440h+var_3D0], eax
0x180063cfd  test    eax, eax
0x180063cff  js      loc_180063F27
0x180063d05  mov     rbx, [rbp+340h+var_3A8]
0x180063d09  lea     rdx, aQuerylistQuery; "<QueryList><Query Id=\"0\" Path=\"Micro"...
0x180063d10  lea     rcx, [rbp+340h+Block]; this
0x180063d14  mov     rax, [rbx]
0x180063d17  mov     rdi, [rax+0A8h]
0x180063d1e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180063d23  mov     rdx, [rax]
0x180063d26  test    rdx, rdx
0x180063d29  jz      short loc_180063D30
0x180063d2b  mov     rdx, [rdx]
0x180063d2e  jmp     short loc_180063D33
0x180063d30  mov     rdx, r14
0x180063d33  mov     rcx, rbx
0x180063d36  mov     rax, rdi
0x180063d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d3e  mov     rbx, [rbp+340h+Block]
0x180063d42  mov     [rsp+440h+var_3D0], eax
0x180063d46  test    rbx, rbx
0x180063d49  jz      short loc_180063D8D
0x180063d4b  or      eax, 0FFFFFFFFh
0x180063d4e  lock xadd [rbx+10h], eax
0x180063d53  cmp     eax, 1
0x180063d56  jnz     short loc_180063D8D
0x180063d58  test    rbx, rbx
0x180063d5b  jz      short loc_180063D8D
0x180063d5d  mov     rcx, [rbx]; bstrString
0x180063d60  test    rcx, rcx
0x180063d63  jz      short loc_180063D6E
0x180063d65  call    cs:__imp_SysFreeString
0x180063d6b  mov     [rbx], r14
0x180063d6e  mov     rcx, [rbx+8]; Block
0x180063d72  test    rcx, rcx
0x180063d75  jz      short loc_180063D80
0x180063d77  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063d7c  mov     [rbx+8], r14
0x180063d80  mov     edx, 18h
0x180063d85  mov     rcx, rbx; Block
0x180063d88  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063d8d  cmp     [rsp+440h+var_3D0], r14d
0x180063d92  jl      loc_180063F27
0x180063d98  mov     rcx, [rsp+440h+var_3C8]
0x180063d9d  mov     rdx, [rbp+340h+var_3C0]
0x180063da1  mov     rax, [rcx]
0x180063da4  mov     rax, [rax+50h]
0x180063da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063dad  mov     [rsp+440h+var_3D0], eax
0x180063db1  test    eax, eax
0x180063db3  js      loc_180063F27
0x180063db9  mov     rbx, [rbp+340h+var_398]
0x180063dbd  lea     rcx, [rbp+340h+pvarg]; pvarg
0x180063dc1  mov     rax, [rbx]
0x180063dc4  mov     rsi, [rax+88h]
0x180063dcb  call    cs:__imp_VariantInit
0x180063dd1  movups  xmm6, xmmword ptr [rbp+340h+pvarg]
0x180063dd5  lea     rcx, [rbp+340h+var_360]; pvarg
0x180063dd9  movsd   xmm7, qword ptr [rbp+340h+pvarg+10h]
0x180063dde  call    cs:__imp_VariantInit
0x180063de4  movups  xmm8, xmmword ptr [rbp+340h+var_360]
0x180063de9  lea     rdx, aS1518; "S-1-5-18"
0x180063df0  movsd   xmm9, qword ptr [rbp+340h+var_360+10h]
0x180063df6  lea     rcx, [rbp+340h+var_2D0]; this
0x180063dfa  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180063dff  mov     rdi, [rsp+440h+var_3C8]
0x180063e04  lea     rdx, aPassportForWor; "Passport for Work alert created by enro"...
0x180063e0b  lea     rcx, [rbp+340h+Block]; this
0x180063e0f  movups  xmm10, xmmword ptr [rax]
0x180063e13  movsd   xmm11, qword ptr [rax+10h]
0x180063e19  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180063e1e  mov     rdx, [rax]
0x180063e21  test    rdx, rdx
0x180063e24  jz      short loc_180063E2B
0x180063e26  mov     rdx, [rdx]
0x180063e29  jmp     short loc_180063E2E
0x180063e2b  mov     rdx, r14
0x180063e2e  lea     rax, [rbp+340h+var_390]
0x180063e32  movaps  [rbp+340h+var_330], xmm6
0x180063e36  mov     qword ptr [rsp+440h+var_400], rax
0x180063e3b  mov     r9d, 6
0x180063e41  lea     rax, [rbp+340h+var_330]
0x180063e45  movsd   [rbp+340h+var_320], xmm7
0x180063e4a  mov     [rsp+440h+var_408], rax
0x180063e4f  mov     r8, rdi
0x180063e52  lea     rax, [rbp+340h+var_310]
0x180063e56  mov     dword ptr [rsp+440h+var_410], 3
0x180063e5e  mov     [rsp+440h+var_418], rax
0x180063e63  mov     rcx, rbx
0x180063e66  lea     rax, [rbp+340h+var_2F0]
0x180063e6a  movaps  [rbp+340h+var_310], xmm8
0x180063e6f  mov     [rsp+440h+var_420], rax
0x180063e74  mov     rax, rsi
0x180063e77  movsd   [rbp+340h+var_300], xmm9
0x180063e7d  movaps  [rbp+340h+var_2F0], xmm10
0x180063e82  movsd   [rbp+340h+var_2E0], xmm11
0x180063e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063e8d  mov     rbx, [rbp+340h+Block]
0x180063e91  mov     [rsp+440h+var_3D0], eax
0x180063e95  test    rbx, rbx
0x180063e98  jz      short loc_180063EE0
0x180063e9a  or      eax, 0FFFFFFFFh
0x180063e9d  lock xadd [rbx+10h], eax
0x180063ea2  cmp     eax, 1
0x180063ea5  jnz     short loc_180063EDC
0x180063ea7  test    rbx, rbx
0x180063eaa  jz      short loc_180063EDC
0x180063eac  mov     rcx, [rbx]; bstrString
0x180063eaf  test    rcx, rcx
0x180063eb2  jz      short loc_180063EBD
0x180063eb4  call    cs:__imp_SysFreeString
0x180063eba  mov     [rbx], r14
0x180063ebd  mov     rcx, [rbx+8]; Block
0x180063ec1  test    rcx, rcx
0x180063ec4  jz      short loc_180063ECF
0x180063ec6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063ecb  mov     [rbx+8], r14
0x180063ecf  mov     edx, 18h
0x180063ed4  mov     rcx, rbx; Block
0x180063ed7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063edc  mov     [rbp+340h+Block], r14
0x180063ee0  lea     rcx, [rbp+340h+var_2D0]; this
0x180063ee4  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180063ee9  lea     rcx, [rbp+340h+var_360]; this
0x180063eed  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180063ef2  lea     rcx, [rbp+340h+pvarg]; this
0x180063ef6  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180063efb  mov     ecx, [rsp+440h+var_3D0]
0x180063eff  mov     edx, 80000000h
0x180063f04  lea     eax, [rcx+rdx]
0x180063f07  test    edx, eax
0x180063f09  jnz     short loc_180063F27
0x180063f0b  cmp     ecx, 8007007Fh
0x180063f11  jz      short loc_180063F27
0x180063f13  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180063f18  mov     edx, [rsp+440h+var_3D0]; int
0x180063f1c  mov     r8, r13; char *
0x180063f1f  mov     rcx, rax; this
0x180063f22  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x180063f27  lea     rcx, [rbp+340h+var_378]
0x180063f2b  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180063f30  lea     rcx, [rbp+340h+var_390]
0x180063f34  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180063f39  lea     rcx, [rbp+340h+var_3A8]
0x180063f3d  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180063f42  lea     rcx, [rbp+340h+var_3A0]
0x180063f46  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180063f4b  lea     rcx, [rbp+340h+var_3C0]
0x180063f4f  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180063f54  lea     rcx, [rbp+340h+var_388]
0x180063f58  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180063f5d  lea     rcx, [rsp+440h+var_3C8]
0x180063f62  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180063f67  lea     rcx, [rbp+340h+var_398]
0x180063f6b  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180063f70  lea     rcx, [rbp+340h+var_380]
0x180063f74  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180063f79  mov     ebx, [rsp+440h+var_3D0]
0x180063f7d  cmp     [rsp+440h+var_3D0+4], r14d
0x180063f82  jz      short loc_180063F8A
0x180063f84  call    cs:__imp_CoUninitialize
0x180063f8a  lea     rcx, [rbp+340h+var_370]; this
0x180063f8e  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180063f93  mov     eax, ebx
0x180063f95  mov     rcx, [rbp+340h+var_A0]
0x180063f9c  xor     rcx, rsp; StackCookie
0x180063f9f  call    __security_check_cookie
0x180063fa4  lea     r11, [rsp+440h+var_28]
0x180063fac  movaps  xmm6, xmmword ptr [r11-18h]
0x180063fb1  movaps  xmm7, xmmword ptr [r11-28h]
0x180063fb6  movaps  xmm8, xmmword ptr [r11-38h]
0x180063fbb  movaps  xmm9, xmmword ptr [r11-48h]
0x180063fc0  movaps  xmm10, xmmword ptr [r11-58h]
0x180063fc5  movaps  xmm11, xmmword ptr [r11-68h]
0x180063fca  mov     rsp, r11
0x180063fcd  pop     r14
0x180063fcf  pop     r13
0x180063fd1  pop     rdi
0x180063fd2  pop     rsi
0x180063fd3  pop     rbx
0x180063fd4  pop     rbp
0x180063fd5  retn
```
