# ScheduleOneOmaDmSessionClient

- ea: `0x1800dc068`
- end: `0x1800dc438`
- name: `ScheduleOneOmaDmSessionClient`
- size: `976`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, int, __int64, __int64, __int64, int Data, int, int)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800dbdd0`
- `0x1800dbe9c`
- `0x1800ddd04`

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
- `0x1800d820c`
- `0x1800dc068`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800dc2f2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dc2f2`
- `OLEAUT32!__imp_VariantInit` at `0x1800dc1ff`
- `OLEAUT32!__imp_VariantInit` at `0x1800dc218`
- `OLEAUT32!__imp_VariantInit` at `0x1800dc1ff`
- `OLEAUT32!__imp_VariantInit` at `0x1800dc218`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800dc376`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800dc376`

## string_xrefs

- `0x1800dc35e`: `24RegisterTaskDefinition`
- `0x1800dc11a`: `%windir%\system32\deviceenroller.exe `

## pseudocode

```c
__int64 __fastcall ScheduleOneOmaDmSessionClient(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        unsigned __int16 *a7,
        __int64 a8,
        int Data,
        int a10,
        int a11)
{
  unsigned int v14; // ebx
  struct IUnknown *v15; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // rsi
  __int128 v17; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v19; // xmm8
  IRecordInfo *v20; // xmm9_8
  _variant_t *v21; // rax
  __int64 v22; // rdi
  __int128 v23; // xmm10
  __int64 v24; // xmm11_8
  _bstr_t *v25; // rax
  __int64 v26; // rdx
  int v27; // eax
  BSTR *v28; // rbx
  BSTR v29; // rcx
  CEnrollmentLogger *Logger; // rax
  int v32; // [rsp+68h] [rbp-A0h]
  struct IUnknown *v33; // [rsp+78h] [rbp-90h] BYREF
  void *Block; // [rsp+80h] [rbp-88h] BYREF
  __int64 v35; // [rsp+88h] [rbp-80h] BYREF
  __int64 v36; // [rsp+90h] [rbp-78h] BYREF
  LPVOID v37; // [rsp+98h] [rbp-70h] BYREF
  __int64 v38; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v40; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD v41[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v42; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v44; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v45; // [rsp+108h] [rbp+0h]
  __int128 v46; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v47; // [rsp+128h] [rbp+20h]
  __int128 v48; // [rsp+138h] [rbp+30h] BYREF
  __int64 v49; // [rsp+148h] [rbp+40h]
  _BYTE v50[136]; // [rsp+158h] [rbp+50h] BYREF

  v32 = 0;
  Data = 0;
  v41[1] = &Data;
  v41[0] = "ScheduleOneOmaDmSessionClient";
  v37 = 0;
  v33 = 0;
  a6 = 0;
  v36 = 0;
  a8 = 0;
  v40 = 0;
  v39 = 0;
  v38 = 0;
  v35 = 0;
  Data = CreateTask(
           &v37,
           &v33,
           &a6,
           &v36,
           a2,
           L"%windir%\\system32\\deviceenroller.exe ",
           a7,
           L"S-1-5-18",
           0,
           a11,
           1,
           1,
           v32);
  v14 = Data;
  if ( Data >= 0 )
  {
    Data = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a6 + 72LL))(a6, &a8);
    v14 = Data;
    if ( Data >= 0 )
    {
      Data = AddTimeTaskTriggers(&a8, a3, a4, a5);
      v14 = Data;
      if ( Data >= 0 )
      {
        Data = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a6 + 80LL))(a6, a8);
        v14 = Data;
        if ( Data >= 0 )
        {
          v15 = v33;
          Release = v33->lpVtbl[5].Release;
          VariantInit(&pvarg);
          v17 = *(_OWORD *)&pvarg.vt;
          pRecInfo = pvarg.pRecInfo;
          VariantInit(&v42);
          v19 = *(_OWORD *)&v42.vt;
          v20 = v42.pRecInfo;
          v21 = _variant_t::_variant_t((_variant_t *)v50, L"S-1-5-18");
          v22 = a6;
          v23 = *(_OWORD *)v21;
          v24 = *((_QWORD *)v21 + 2);
          v25 = _bstr_t::_bstr_t((_bstr_t *)&Block, a1);
          if ( *(_QWORD *)v25 )
            v26 = **(_QWORD **)v25;
          else
            v26 = 0;
          v44 = v17;
          v45 = pRecInfo;
          v46 = v19;
          v47 = v20;
          v48 = v23;
          v49 = v24;
          v27 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))Release)(
                  v15,
                  v26,
                  v22,
                  6,
                  &v48,
                  &v46,
                  3,
                  &v44,
                  &v35);
          v28 = (BSTR *)Block;
          Data = v27;
          if ( Block )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v28 )
            {
              if ( *v28 )
              {
                SysFreeString(*v28);
                *v28 = 0;
              }
              v29 = v28[1];
              if ( v29 )
              {
                operator delete(v29);
                v28[1] = 0;
              }
              operator delete(v28);
            }
            Block = 0;
          }
          _variant_t::~_variant_t((_variant_t *)v50);
          _variant_t::~_variant_t((_variant_t *)&v42);
          _variant_t::~_variant_t((_variant_t *)&pvarg);
          v14 = Data;
          if ( Data < 0 )
          {
            RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"24RegisterTaskDefinition", 4u, &Data, 4u);
            Logger = CEnrollmentLogger::GetLogger();
            CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Data, "ScheduleOneOmaDmSessionClient");
            v14 = Data;
          }
        }
      }
    }
  }
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v35);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v38);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v39);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v40);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&a8);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v36);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&a6);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v33);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v37);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v41);
  return v14;
}

```

## disassembly

```asm
0x1800dc068  mov     rax, rsp
0x1800dc06b  push    rbp
0x1800dc06c  push    rbx
0x1800dc06d  push    rsi
0x1800dc06e  push    rdi
0x1800dc06f  push    r12
0x1800dc071  push    r13
0x1800dc073  push    r14
0x1800dc075  push    r15
0x1800dc077  lea     rbp, [rax-118h]
0x1800dc07e  sub     rsp, 1D8h
0x1800dc085  xor     r15d, r15d
0x1800dc088  movaps  xmmword ptr [rax-58h], xmm6
0x1800dc08c  movaps  xmmword ptr [rax-68h], xmm7
0x1800dc090  lea     r13, aS1518; "S-1-5-18"
0x1800dc097  movaps  xmmword ptr [rax-78h], xmm8
0x1800dc09c  lea     r12, aScheduleoneoma_0; "ScheduleOneOmaDmSessionClient"
0x1800dc0a3  movaps  xmmword ptr [rax-88h], xmm9
0x1800dc0ab  mov     edi, r9d
0x1800dc0ae  mov     [rsp+210h+var_1B0], r15d
0x1800dc0b3  lea     r9, [rbp+110h+var_188]
0x1800dc0b7  movaps  xmmword ptr [rax-98h], xmm10
0x1800dc0bf  mov     esi, r8d
0x1800dc0c2  movaps  xmmword ptr [rax-0A8h], xmm11
0x1800dc0ca  lea     r8, [rbp+110h+arg_28]
0x1800dc0d1  lea     rax, [rbp+110h+Data]
0x1800dc0d8  mov     [rbp+110h+Data], r15d
0x1800dc0df  mov     [rbp+110h+var_158], rax
0x1800dc0e3  mov     r14, rcx
0x1800dc0e6  lea     eax, [r15+1]
0x1800dc0ea  mov     [rbp+110h+var_160], r12
0x1800dc0ee  mov     [rsp+210h+var_1B8], eax
0x1800dc0f2  lea     rcx, [rbp+110h+var_180]
0x1800dc0f6  mov     [rsp+210h+var_1C0], eax
0x1800dc0fa  mov     eax, [rbp+110h+arg_50]
0x1800dc100  mov     [rsp+210h+var_1C8], eax
0x1800dc104  mov     rax, [rbp+110h+arg_30]
0x1800dc10b  mov     [rsp+210h+var_1D0], r15d
0x1800dc110  mov     [rsp+210h+var_1D8], r13
0x1800dc115  mov     [rsp+210h+var_1E0], rax
0x1800dc11a  lea     rax, aWindirSystem32_2; "%windir%\\system32\\deviceenroller.exe "
0x1800dc121  mov     qword ptr [rsp+210h+cbData], rax
0x1800dc126  mov     [rsp+210h+lpData], rdx
0x1800dc12b  lea     rdx, [rsp+210h+var_1A0]
0x1800dc130  mov     [rbp+110h+var_180], r15
0x1800dc134  mov     [rsp+210h+var_1A0], r15
0x1800dc139  mov     [rbp+110h+arg_28], r15
0x1800dc140  mov     [rbp+110h+var_188], r15
0x1800dc144  mov     [rbp+110h+arg_38], r15
0x1800dc14b  mov     [rbp+110h+var_168], r15
0x1800dc14f  mov     [rbp+110h+var_170], r15
0x1800dc153  mov     [rbp+110h+var_178], r15
0x1800dc157  mov     [rbp+110h+var_190], r15
0x1800dc15b  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x1800dc160  mov     [rbp+110h+Data], eax
0x1800dc166  mov     ebx, eax
0x1800dc168  test    eax, eax
0x1800dc16a  js      loc_1800DC39E
0x1800dc170  mov     rcx, [rbp+110h+arg_28]
0x1800dc177  lea     rdx, [rbp+110h+arg_38]
0x1800dc17e  mov     rax, [rcx]
0x1800dc181  mov     rax, [rax+48h]
0x1800dc185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc18a  mov     [rbp+110h+Data], eax
0x1800dc190  mov     ebx, eax
0x1800dc192  test    eax, eax
0x1800dc194  js      loc_1800DC39E
0x1800dc19a  mov     r9d, [rbp+110h+arg_20]
0x1800dc1a1  lea     rcx, [rbp+110h+arg_38]
0x1800dc1a8  mov     r8d, edi
0x1800dc1ab  mov     edx, esi
0x1800dc1ad  call    ?AddTimeTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@KKK@Z; AddTimeTaskTriggers(ATL::CComPtr<ITriggerCollection> &,ulong,ulong,ulong)
0x1800dc1b2  mov     [rbp+110h+Data], eax
0x1800dc1b8  mov     ebx, eax
0x1800dc1ba  test    eax, eax
0x1800dc1bc  js      loc_1800DC39E
0x1800dc1c2  mov     rcx, [rbp+110h+arg_28]
0x1800dc1c9  mov     rdx, [rbp+110h+arg_38]
0x1800dc1d0  mov     rax, [rcx]
0x1800dc1d3  mov     rax, [rax+50h]
0x1800dc1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc1dc  mov     [rbp+110h+Data], eax
0x1800dc1e2  mov     ebx, eax
0x1800dc1e4  test    eax, eax
0x1800dc1e6  js      loc_1800DC39E
0x1800dc1ec  mov     rbx, [rsp+210h+var_1A0]
0x1800dc1f1  lea     rcx, [rbp+110h+pvarg]; pvarg
0x1800dc1f5  mov     rax, [rbx]
0x1800dc1f8  mov     rsi, [rax+88h]
0x1800dc1ff  call    cs:__imp_VariantInit
0x1800dc206  nop     dword ptr [rax+rax+00h]
0x1800dc20b  movups  xmm6, xmmword ptr [rbp+110h+pvarg]
0x1800dc20f  lea     rcx, [rbp+110h+var_150]; pvarg
0x1800dc213  movsd   xmm7, qword ptr [rbp+110h+pvarg+10h]
0x1800dc218  call    cs:__imp_VariantInit
0x1800dc21f  nop     dword ptr [rax+rax+00h]
0x1800dc224  movups  xmm8, xmmword ptr [rbp+110h+var_150]
0x1800dc229  lea     rcx, [rbp+110h+var_C0]; this
0x1800dc22d  mov     rdx, r13; unsigned __int16 *
0x1800dc230  movsd   xmm9, qword ptr [rbp+110h+var_150+10h]
0x1800dc236  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x1800dc23b  mov     rdi, [rbp+110h+arg_28]
0x1800dc242  lea     rcx, [rsp+210h+Block]; this
0x1800dc247  mov     rdx, r14; unsigned __int16 *
0x1800dc24a  movups  xmm10, xmmword ptr [rax]
0x1800dc24e  movsd   xmm11, qword ptr [rax+10h]
0x1800dc254  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800dc259  mov     rdx, [rax]
0x1800dc25c  test    rdx, rdx
0x1800dc25f  jz      short loc_1800DC266
0x1800dc261  mov     rdx, [rdx]
0x1800dc264  jmp     short loc_1800DC269
0x1800dc266  mov     rdx, r15
0x1800dc269  lea     rax, [rbp+110h+var_190]
0x1800dc26d  movaps  [rbp+110h+var_120], xmm6
0x1800dc271  mov     qword ptr [rsp+210h+var_1D0], rax
0x1800dc276  mov     r9d, 6
0x1800dc27c  lea     rax, [rbp+110h+var_120]
0x1800dc280  movsd   [rbp+110h+var_110], xmm7
0x1800dc285  mov     [rsp+210h+var_1D8], rax
0x1800dc28a  mov     r8, rdi
0x1800dc28d  lea     rax, [rbp+110h+var_100]
0x1800dc291  mov     dword ptr [rsp+210h+var_1E0], 3
0x1800dc299  mov     qword ptr [rsp+210h+cbData], rax
0x1800dc29e  mov     rcx, rbx
0x1800dc2a1  lea     rax, [rbp+110h+var_E0]
0x1800dc2a5  movaps  [rbp+110h+var_100], xmm8
0x1800dc2aa  mov     [rsp+210h+lpData], rax
0x1800dc2af  mov     rax, rsi
0x1800dc2b2  movsd   [rbp+110h+var_F0], xmm9
0x1800dc2b8  movaps  [rbp+110h+var_E0], xmm10
0x1800dc2bd  movsd   [rbp+110h+var_D0], xmm11
0x1800dc2c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc2c8  mov     rbx, [rsp+210h+Block]
0x1800dc2cd  mov     [rbp+110h+Data], eax
0x1800dc2d3  test    rbx, rbx
0x1800dc2d6  jz      short loc_1800DC325
0x1800dc2d8  or      eax, 0FFFFFFFFh
0x1800dc2db  lock xadd [rbx+10h], eax
0x1800dc2e0  cmp     eax, 1
0x1800dc2e3  jnz     short loc_1800DC320
0x1800dc2e5  test    rbx, rbx
0x1800dc2e8  jz      short loc_1800DC320
0x1800dc2ea  mov     rcx, [rbx]; bstrString
0x1800dc2ed  test    rcx, rcx
0x1800dc2f0  jz      short loc_1800DC301
0x1800dc2f2  call    cs:__imp_SysFreeString
0x1800dc2f9  nop     dword ptr [rax+rax+00h]
0x1800dc2fe  mov     [rbx], r15
0x1800dc301  mov     rcx, [rbx+8]; Block
0x1800dc305  test    rcx, rcx
0x1800dc308  jz      short loc_1800DC313
0x1800dc30a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dc30f  mov     [rbx+8], r15
0x1800dc313  mov     edx, 18h
0x1800dc318  mov     rcx, rbx; Block
0x1800dc31b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dc320  mov     [rsp+210h+Block], r15
0x1800dc325  lea     rcx, [rbp+110h+var_C0]; this
0x1800dc329  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800dc32e  lea     rcx, [rbp+110h+var_150]; this
0x1800dc332  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800dc337  lea     rcx, [rbp+110h+pvarg]; this
0x1800dc33b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800dc340  mov     ebx, [rbp+110h+Data]
0x1800dc346  test    ebx, ebx
0x1800dc348  jns     short loc_1800DC39E
0x1800dc34a  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x1800dc351  lea     rax, [rbp+110h+Data]
0x1800dc358  mov     r9d, 4; dwType
0x1800dc35e  lea     r8, a24registertask; "24RegisterTaskDefinition"
0x1800dc365  mov     [rsp+210h+cbData], r9d; cbData
0x1800dc36a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800dc371  mov     [rsp+210h+lpData], rax; lpData
0x1800dc376  call    cs:__imp_RegSetKeyValueW
0x1800dc37d  nop     dword ptr [rax+rax+00h]
0x1800dc382  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800dc387  mov     edx, [rbp+110h+Data]; int
0x1800dc38d  mov     r8, r12; char *
0x1800dc390  mov     rcx, rax; this
0x1800dc393  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x1800dc398  mov     ebx, [rbp+110h+Data]
0x1800dc39e  lea     rcx, [rbp+110h+var_190]
0x1800dc3a2  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc3a7  lea     rcx, [rbp+110h+var_178]
0x1800dc3ab  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc3b0  lea     rcx, [rbp+110h+var_170]
0x1800dc3b4  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc3b9  lea     rcx, [rbp+110h+var_168]
0x1800dc3bd  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc3c2  lea     rcx, [rbp+110h+arg_38]
0x1800dc3c9  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc3ce  lea     rcx, [rbp+110h+var_188]
0x1800dc3d2  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc3d7  lea     rcx, [rbp+110h+arg_28]
0x1800dc3de  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc3e3  lea     rcx, [rsp+210h+var_1A0]
0x1800dc3e8  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc3ed  lea     rcx, [rbp+110h+var_180]
0x1800dc3f1  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc3f6  lea     rcx, [rbp+110h+var_160]; this
0x1800dc3fa  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800dc3ff  lea     r11, [rsp+210h+var_38]
0x1800dc407  mov     eax, ebx
0x1800dc409  movaps  xmm6, xmmword ptr [r11-18h]
0x1800dc40e  movaps  xmm7, xmmword ptr [r11-28h]
0x1800dc413  movaps  xmm8, xmmword ptr [r11-38h]
0x1800dc418  movaps  xmm9, xmmword ptr [r11-48h]
0x1800dc41d  movaps  xmm10, xmmword ptr [r11-58h]
0x1800dc422  movaps  xmm11, xmmword ptr [r11-68h]
0x1800dc427  mov     rsp, r11
0x1800dc42a  pop     r15
0x1800dc42c  pop     r14
0x1800dc42e  pop     r13
0x1800dc430  pop     r12
0x1800dc432  pop     rdi
0x1800dc433  pop     rsi
0x1800dc434  pop     rbx
0x1800dc435  pop     rbp
0x1800dc436  retn
```
