# ScheduleOneOmaDmSessionClientInFolder

- ea: `0x1800dc440`
- end: `0x1800dc822`
- name: `ScheduleOneOmaDmSessionClientInFolder`
- size: `994`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, __int64, __int64, void *Block)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800db314`

## callees

- `0x1800091b0`
- `0x18001a4fc`
- `0x1800637f4`
- `0x180063870`
- `0x1800639d0`
- `0x1800d11a4`
- `0x1800d14ec`
- `0x1800d7300`
- `0x1800d7840`
- `0x1800d935c`
- `0x1800dc440`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800dc6d7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc6d7`
- `OLEAUT32!__imp_VariantInit` at `0x1800dc5db`
- `OLEAUT32!__imp_VariantInit` at `0x1800dc5f4`
- `OLEAUT32!__imp_VariantInit` at `0x1800dc5db`
- `OLEAUT32!__imp_VariantInit` at `0x1800dc5f4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800dc75d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800dc75d`

## string_xrefs

- `0x1800dc61e`: `Schedule created by dm client to refresh settings`
- `0x1800dc745`: `24RegisterTaskDefinition`
- `0x1800dc4e6`: `%windir%\system32\deviceenroller.exe `

## pseudocode

```c
__int64 __fastcall ScheduleOneOmaDmSessionClientInFolder(
        __int64 a1,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        volatile signed __int32 *Block)
{
  unsigned int v9; // ebx
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rsi
  __int128 v12; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v14; // xmm8
  IRecordInfo *v15; // xmm9_8
  _variant_t *v16; // rax
  __int64 v17; // rdi
  __int128 v18; // xmm10
  __int64 v19; // xmm11_8
  _bstr_t *v20; // rax
  __int64 v21; // rdx
  int v22; // eax
  BSTR *v23; // rbx
  BSTR v24; // rcx
  CEnrollmentLogger *Logger; // rax
  int v27; // [rsp+50h] [rbp-B8h]
  int v28; // [rsp+58h] [rbp-B0h]
  int v29; // [rsp+60h] [rbp-A8h]
  int v30; // [rsp+68h] [rbp-A0h]
  int v31; // [rsp+70h] [rbp-98h]
  __int64 v32; // [rsp+78h] [rbp-90h] BYREF
  __int64 v33; // [rsp+80h] [rbp-88h] BYREF
  LPVOID v34; // [rsp+88h] [rbp-80h] BYREF
  __int64 v35; // [rsp+90h] [rbp-78h] BYREF
  __int64 v36; // [rsp+98h] [rbp-70h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v38[2]; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG v39; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v41; // [rsp+E8h] [rbp-20h] BYREF
  IRecordInfo *v42; // [rsp+F8h] [rbp-10h]
  __int128 v43; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v44; // [rsp+118h] [rbp+10h]
  __int128 v45; // [rsp+128h] [rbp+20h] BYREF
  __int64 v46; // [rsp+138h] [rbp+30h]
  _BYTE v47[128]; // [rsp+148h] [rbp+40h] BYREF
  __int64 v48; // [rsp+1F8h] [rbp+F0h] BYREF
  int Data; // [rsp+210h] [rbp+108h] BYREF

  v31 = 0;
  v38[1] = &Data;
  v30 = 1;
  v29 = 1;
  v28 = 1;
  v27 = 0;
  Data = 0;
  v38[0] = "ScheduleOneOmaDmSessionClientInFolder";
  v34 = 0;
  a8 = 0;
  v48 = 0;
  v33 = 0;
  a6 = 0;
  v37 = 0;
  v36 = 0;
  v35 = 0;
  Data = CreateTaskInFolder(
           &v34,
           (struct IUnknown **)&a8,
           &v48,
           &v33,
           a2,
           L"%windir%\\system32\\deviceenroller.exe ",
           a7,
           L"\\Microsoft\\Windows\\EnterpriseMgmtNonCritical",
           L"S-1-5-18",
           v27,
           v28,
           v29,
           v30,
           v31,
           0);
  v9 = Data;
  if ( Data >= 0 )
  {
    Data = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v48 + 72LL))(v48, &a6);
    v9 = Data;
    if ( Data >= 0 )
    {
      Data = AddTimeTaskTriggers(&a6, 0, 90, 0);
      v9 = Data;
      if ( Data >= 0 )
      {
        Data = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 80LL))(v48, a6);
        v9 = Data;
        if ( Data >= 0 )
        {
          v10 = a8;
          v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(*(_QWORD *)a8 + 136LL);
          VariantInit(&pvarg);
          v12 = *(_OWORD *)&pvarg.vt;
          pRecInfo = pvarg.pRecInfo;
          VariantInit(&v39);
          v14 = *(_OWORD *)&v39.vt;
          v15 = v39.pRecInfo;
          v16 = _variant_t::_variant_t((_variant_t *)v47, L"S-1-5-18");
          v17 = v48;
          v18 = *(_OWORD *)v16;
          v19 = *((_QWORD *)v16 + 2);
          v20 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"Schedule created by dm client to refresh settings");
          if ( *(_QWORD *)v20 )
            v21 = **(_QWORD **)v20;
          else
            v21 = 0;
          v41 = v12;
          v42 = pRecInfo;
          v43 = v14;
          v44 = v15;
          v45 = v18;
          v46 = v19;
          v22 = v11(v10, v21, v17, 6, &v45, &v43, 3, &v41, &v32);
          v23 = (BSTR *)Block;
          Data = v22;
          if ( Block )
          {
            if ( _InterlockedExchangeAdd(Block + 4, 0xFFFFFFFF) == 1 && v23 )
            {
              if ( *v23 )
              {
                SysFreeString(*v23);
                *v23 = 0;
              }
              v24 = v23[1];
              if ( v24 )
              {
                operator delete(v24);
                v23[1] = 0;
              }
              operator delete(v23);
            }
            Block = 0;
          }
          _variant_t::~_variant_t((_variant_t *)v47);
          _variant_t::~_variant_t((_variant_t *)&v39);
          _variant_t::~_variant_t((_variant_t *)&pvarg);
          v9 = Data;
          if ( Data < 0 )
          {
            RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"24RegisterTaskDefinition", 4u, &Data, 4u);
            Logger = CEnrollmentLogger::GetLogger();
            CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Data, "ScheduleOneOmaDmSessionClientInFolder");
            v9 = Data;
          }
        }
      }
    }
  }
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v32);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v35);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v36);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v37);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&a6);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v33);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v48);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&a8);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v34);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v38);
  return v9;
}

```

## disassembly

```asm
0x1800dc440  mov     rax, rsp
0x1800dc443  mov     [rax+10h], rbx
0x1800dc447  mov     [rax+20h], r9d
0x1800dc44b  mov     [rax+8], rcx
0x1800dc44f  push    rbp
0x1800dc450  push    rsi
0x1800dc451  push    rdi
0x1800dc452  push    r14
0x1800dc454  push    r15
0x1800dc456  lea     rbp, [rax-0E8h]
0x1800dc45d  sub     rsp, 1C0h
0x1800dc464  xor     r14d, r14d
0x1800dc467  movaps  xmmword ptr [rax-38h], xmm6
0x1800dc46b  movaps  xmmword ptr [rax-48h], xmm7
0x1800dc46f  lea     rdi, aS1518; "S-1-5-18"
0x1800dc476  movaps  xmmword ptr [rax-58h], xmm8
0x1800dc47b  lea     r15, aScheduleoneoma_1; "ScheduleOneOmaDmSessionClientInFolder"
0x1800dc482  mov     dword ptr [rsp+1E0h+var_178], r14d
0x1800dc487  lea     r9, [rsp+1E0h+var_168]
0x1800dc48c  movaps  xmmword ptr [rax-68h], xmm9
0x1800dc491  lea     r8, [rbp+0E0h+arg_0]
0x1800dc498  movaps  xmmword ptr [rax-78h], xmm10
0x1800dc49d  lea     rcx, [rbp+0E0h+var_160]
0x1800dc4a1  movaps  xmmword ptr [rax-88h], xmm11
0x1800dc4a9  lea     rax, [rbp+0E0h+Data]
0x1800dc4b0  mov     [rbp+0E0h+var_138], rax
0x1800dc4b4  lea     eax, [r14+1]
0x1800dc4b8  mov     [rsp+1E0h+var_180], eax
0x1800dc4bc  mov     [rsp+1E0h+var_188], eax
0x1800dc4c0  mov     [rsp+1E0h+var_190], eax
0x1800dc4c4  lea     rax, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmtNon"...
0x1800dc4cb  mov     [rsp+1E0h+var_198], r14d
0x1800dc4d0  mov     qword ptr [rsp+1E0h+var_1A0], rdi
0x1800dc4d5  mov     [rsp+1E0h+var_1A8], rax
0x1800dc4da  mov     rax, [rbp+0E0h+arg_30]
0x1800dc4e1  mov     [rsp+1E0h+var_1B0], rax
0x1800dc4e6  lea     rax, aWindirSystem32_2; "%windir%\\system32\\deviceenroller.exe "
0x1800dc4ed  mov     qword ptr [rsp+1E0h+cbData], rax
0x1800dc4f2  mov     [rsp+1E0h+lpData], rdx
0x1800dc4f7  lea     rdx, [rbp+0E0h+arg_38]
0x1800dc4fe  mov     [rbp+0E0h+Data], r14d
0x1800dc505  mov     [rbp+0E0h+var_140], r15
0x1800dc509  mov     [rbp+0E0h+var_160], r14
0x1800dc50d  mov     [rbp+0E0h+arg_38], r14
0x1800dc514  mov     [rbp+0E0h+arg_0], r14
0x1800dc51b  mov     [rsp+1E0h+var_168], r14
0x1800dc520  mov     [rbp+0E0h+arg_28], r14
0x1800dc527  mov     [rbp+0E0h+var_148], r14
0x1800dc52b  mov     [rbp+0E0h+var_150], r14
0x1800dc52f  mov     [rbp+0E0h+var_158], r14
0x1800dc533  mov     [rsp+1E0h+var_170], r14
0x1800dc538  call    ?CreateTaskInFolder@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG4444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTaskInFolder(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x1800dc53d  mov     [rbp+0E0h+Data], eax
0x1800dc543  mov     ebx, eax
0x1800dc545  test    eax, eax
0x1800dc547  js      loc_1800DC785
0x1800dc54d  mov     rcx, [rbp+0E0h+arg_0]
0x1800dc554  lea     rdx, [rbp+0E0h+arg_28]
0x1800dc55b  mov     rax, [rcx]
0x1800dc55e  mov     rax, [rax+48h]
0x1800dc562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc567  mov     [rbp+0E0h+Data], eax
0x1800dc56d  mov     ebx, eax
0x1800dc56f  test    eax, eax
0x1800dc571  js      loc_1800DC785
0x1800dc577  xor     r9d, r9d
0x1800dc57a  lea     r8d, [r14+5Ah]
0x1800dc57e  xor     edx, edx
0x1800dc580  lea     rcx, [rbp+0E0h+arg_28]
0x1800dc587  call    ?AddTimeTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@KKK@Z; AddTimeTaskTriggers(ATL::CComPtr<ITriggerCollection> &,ulong,ulong,ulong)
0x1800dc58c  mov     [rbp+0E0h+Data], eax
0x1800dc592  mov     ebx, eax
0x1800dc594  test    eax, eax
0x1800dc596  js      loc_1800DC785
0x1800dc59c  mov     rcx, [rbp+0E0h+arg_0]
0x1800dc5a3  mov     rdx, [rbp+0E0h+arg_28]
0x1800dc5aa  mov     rax, [rcx]
0x1800dc5ad  mov     rax, [rax+50h]
0x1800dc5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc5b6  mov     [rbp+0E0h+Data], eax
0x1800dc5bc  mov     ebx, eax
0x1800dc5be  test    eax, eax
0x1800dc5c0  js      loc_1800DC785
0x1800dc5c6  mov     rbx, [rbp+0E0h+arg_38]
0x1800dc5cd  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x1800dc5d1  mov     rax, [rbx]
0x1800dc5d4  mov     rsi, [rax+88h]
0x1800dc5db  call    cs:__imp_VariantInit
0x1800dc5e2  nop     dword ptr [rax+rax+00h]
0x1800dc5e7  movups  xmm6, xmmword ptr [rbp+0E0h+pvarg]
0x1800dc5eb  lea     rcx, [rbp+0E0h+var_130]; pvarg
0x1800dc5ef  movsd   xmm7, qword ptr [rbp+0E0h+pvarg+10h]
0x1800dc5f4  call    cs:__imp_VariantInit
0x1800dc5fb  nop     dword ptr [rax+rax+00h]
0x1800dc600  movups  xmm8, xmmword ptr [rbp+0E0h+var_130]
0x1800dc605  lea     rcx, [rbp+0E0h+var_A0]; this
0x1800dc609  mov     rdx, rdi; unsigned __int16 *
0x1800dc60c  movsd   xmm9, qword ptr [rbp+0E0h+var_130+10h]
0x1800dc612  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x1800dc617  mov     rdi, [rbp+0E0h+arg_0]
0x1800dc61e  lea     rdx, aScheduleCreate; "Schedule created by dm client to refres"...
0x1800dc625  lea     rcx, [rbp+0E0h+Block]; this
0x1800dc62c  movups  xmm10, xmmword ptr [rax]
0x1800dc630  movsd   xmm11, qword ptr [rax+10h]
0x1800dc636  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800dc63b  mov     rdx, [rax]
0x1800dc63e  test    rdx, rdx
0x1800dc641  jz      short loc_1800DC648
0x1800dc643  mov     rdx, [rdx]
0x1800dc646  jmp     short loc_1800DC64B
0x1800dc648  mov     rdx, r14
0x1800dc64b  lea     rax, [rsp+1E0h+var_170]
0x1800dc650  movaps  [rbp+0E0h+var_100], xmm6
0x1800dc654  mov     qword ptr [rsp+1E0h+var_1A0], rax
0x1800dc659  mov     r9d, 6
0x1800dc65f  lea     rax, [rbp+0E0h+var_100]
0x1800dc663  movsd   [rbp+0E0h+var_F0], xmm7
0x1800dc668  mov     [rsp+1E0h+var_1A8], rax
0x1800dc66d  mov     r8, rdi
0x1800dc670  lea     rax, [rbp+0E0h+var_E0]
0x1800dc674  mov     dword ptr [rsp+1E0h+var_1B0], 3
0x1800dc67c  mov     qword ptr [rsp+1E0h+cbData], rax
0x1800dc681  mov     rcx, rbx
0x1800dc684  lea     rax, [rbp+0E0h+var_C0]
0x1800dc688  movaps  [rbp+0E0h+var_E0], xmm8
0x1800dc68d  mov     [rsp+1E0h+lpData], rax
0x1800dc692  mov     rax, rsi
0x1800dc695  movsd   [rbp+0E0h+var_D0], xmm9
0x1800dc69b  movaps  [rbp+0E0h+var_C0], xmm10
0x1800dc6a0  movsd   [rbp+0E0h+var_B0], xmm11
0x1800dc6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc6ab  mov     rbx, [rbp+0E0h+Block]
0x1800dc6b2  mov     [rbp+0E0h+Data], eax
0x1800dc6b8  test    rbx, rbx
0x1800dc6bb  jz      short loc_1800DC70C
0x1800dc6bd  or      eax, 0FFFFFFFFh
0x1800dc6c0  lock xadd [rbx+10h], eax
0x1800dc6c5  cmp     eax, 1
0x1800dc6c8  jnz     short loc_1800DC705
0x1800dc6ca  test    rbx, rbx
0x1800dc6cd  jz      short loc_1800DC705
0x1800dc6cf  mov     rcx, [rbx]; bstrString
0x1800dc6d2  test    rcx, rcx
0x1800dc6d5  jz      short loc_1800DC6E6
0x1800dc6d7  call    cs:__imp_SysFreeString
0x1800dc6de  nop     dword ptr [rax+rax+00h]
0x1800dc6e3  mov     [rbx], r14
0x1800dc6e6  mov     rcx, [rbx+8]; Block
0x1800dc6ea  test    rcx, rcx
0x1800dc6ed  jz      short loc_1800DC6F8
0x1800dc6ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dc6f4  mov     [rbx+8], r14
0x1800dc6f8  mov     edx, 18h
0x1800dc6fd  mov     rcx, rbx; Block
0x1800dc700  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dc705  mov     [rbp+0E0h+Block], r14
0x1800dc70c  lea     rcx, [rbp+0E0h+var_A0]; this
0x1800dc710  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800dc715  lea     rcx, [rbp+0E0h+var_130]; this
0x1800dc719  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800dc71e  lea     rcx, [rbp+0E0h+pvarg]; this
0x1800dc722  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800dc727  mov     ebx, [rbp+0E0h+Data]
0x1800dc72d  test    ebx, ebx
0x1800dc72f  jns     short loc_1800DC785
0x1800dc731  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x1800dc738  lea     rax, [rbp+0E0h+Data]
0x1800dc73f  mov     r9d, 4; dwType
0x1800dc745  lea     r8, a24registertask; "24RegisterTaskDefinition"
0x1800dc74c  mov     [rsp+1E0h+cbData], r9d; cbData
0x1800dc751  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800dc758  mov     [rsp+1E0h+lpData], rax; lpData
0x1800dc75d  call    cs:__imp_RegSetKeyValueW
0x1800dc764  nop     dword ptr [rax+rax+00h]
0x1800dc769  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800dc76e  mov     edx, [rbp+0E0h+Data]; int
0x1800dc774  mov     r8, r15; char *
0x1800dc777  mov     rcx, rax; this
0x1800dc77a  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x1800dc77f  mov     ebx, [rbp+0E0h+Data]
0x1800dc785  lea     rcx, [rsp+1E0h+var_170]
0x1800dc78a  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc78f  lea     rcx, [rbp+0E0h+var_158]
0x1800dc793  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc798  lea     rcx, [rbp+0E0h+var_150]
0x1800dc79c  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc7a1  lea     rcx, [rbp+0E0h+var_148]
0x1800dc7a5  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc7aa  lea     rcx, [rbp+0E0h+arg_28]
0x1800dc7b1  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc7b6  lea     rcx, [rsp+1E0h+var_168]
0x1800dc7bb  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc7c0  lea     rcx, [rbp+0E0h+arg_0]
0x1800dc7c7  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc7cc  lea     rcx, [rbp+0E0h+arg_38]
0x1800dc7d3  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc7d8  lea     rcx, [rbp+0E0h+var_160]
0x1800dc7dc  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc7e1  lea     rcx, [rbp+0E0h+var_140]; this
0x1800dc7e5  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800dc7ea  lea     r11, [rsp+1E0h+var_20]
0x1800dc7f2  mov     eax, ebx
0x1800dc7f4  mov     rbx, [r11+38h]
0x1800dc7f8  movaps  xmm6, xmmword ptr [r11-10h]
0x1800dc7fd  movaps  xmm7, xmmword ptr [r11-20h]
0x1800dc802  movaps  xmm8, xmmword ptr [r11-30h]
0x1800dc807  movaps  xmm9, xmmword ptr [r11-40h]
0x1800dc80c  movaps  xmm10, xmmword ptr [r11-50h]
0x1800dc811  movaps  xmm11, xmmword ptr [r11-60h]
0x1800dc816  mov     rsp, r11
0x1800dc819  pop     r15
0x1800dc81b  pop     r14
0x1800dc81d  pop     rdi
0x1800dc81e  pop     rsi
0x1800dc81f  pop     rbp
0x1800dc820  retn
```
