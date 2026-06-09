# ScheduleOneOmaDmSessionClient

- ea: `0x180064578`
- end: `0x18006492f`
- name: `ScheduleOneOmaDmSessionClient`
- size: `951`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, int, __int64, __int64, __int64, int Data, int, int)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800634f4`
- `0x180063564`
- `0x1800643c0`

## callees

- `0x18000efc4`
- `0x1800140d0`
- `0x180018074`
- `0x18001aec8`
- `0x18002e570`
- `0x1800434d0`
- `0x180043544`
- `0x180060974`
- `0x180060aa8`
- `0x1800613ac`
- `0x180064578`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180064874`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180064874`
- `OLEAUT32!__imp_SysFreeString` at `0x1800647f6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800647f6`
- `OLEAUT32!__imp_VariantInit` at `0x18006470f`
- `OLEAUT32!__imp_VariantInit` at `0x180064722`
- `OLEAUT32!__imp_VariantInit` at `0x18006470f`
- `OLEAUT32!__imp_VariantInit` at `0x180064722`

## string_xrefs

- `0x18006485c`: `24RegisterTaskDefinition`
- `0x18006462a`: `%windir%\system32\deviceenroller.exe `

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
  __int64 v31; // rdx
  int v33; // [rsp+68h] [rbp-A0h]
  struct IUnknown *v34; // [rsp+78h] [rbp-90h] BYREF
  void *Block; // [rsp+80h] [rbp-88h] BYREF
  __int64 v36; // [rsp+88h] [rbp-80h] BYREF
  __int64 v37; // [rsp+90h] [rbp-78h] BYREF
  __int64 v38; // [rsp+98h] [rbp-70h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD v42[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v43; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v45; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v46; // [rsp+108h] [rbp+0h]
  __int128 v47; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v48; // [rsp+128h] [rbp+20h]
  __int128 v49; // [rsp+138h] [rbp+30h] BYREF
  __int64 v50; // [rsp+148h] [rbp+40h]
  VARIANTARG v51[5]; // [rsp+158h] [rbp+50h] BYREF

  v33 = 0;
  Data = 0;
  v42[1] = &Data;
  v42[0] = "ScheduleOneOmaDmSessionClient";
  v38 = 0;
  v34 = 0;
  a6 = 0;
  v37 = 0;
  a8 = 0;
  v41 = 0;
  v40 = 0;
  v39 = 0;
  v36 = 0;
  Data = CreateTask(
           &v38,
           &v34,
           &a6,
           &v37,
           a2,
           L"%windir%\\system32\\deviceenroller.exe ",
           a7,
           L"S-1-5-18",
           0,
           a11,
           1,
           1,
           v33);
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
          v15 = v34;
          Release = v34->lpVtbl[5].Release;
          VariantInit(&pvarg);
          v17 = *(_OWORD *)&pvarg.vt;
          pRecInfo = pvarg.pRecInfo;
          VariantInit(&v43);
          v19 = *(_OWORD *)&v43.vt;
          v20 = v43.pRecInfo;
          v21 = _variant_t::_variant_t((_variant_t *)v51, L"S-1-5-18");
          v22 = a6;
          v23 = *(_OWORD *)v21;
          v24 = *((_QWORD *)v21 + 2);
          v25 = _bstr_t::_bstr_t((_bstr_t *)&Block, a1);
          if ( *(_QWORD *)v25 )
            v26 = **(_QWORD **)v25;
          else
            v26 = 0;
          v45 = v17;
          v46 = pRecInfo;
          v47 = v19;
          v48 = v20;
          v49 = v23;
          v50 = v24;
          v27 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))Release)(
                  v15,
                  v26,
                  v22,
                  6,
                  &v49,
                  &v47,
                  3,
                  &v45,
                  &v36);
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
          _variant_t::~_variant_t(v51);
          _variant_t::~_variant_t(&v43);
          _variant_t::~_variant_t(&pvarg);
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
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v36);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v39);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v40);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v41);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&a8);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v37);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&a6);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&v34);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v38);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v42, v31);
  return v14;
}

```

## disassembly

```asm
0x180064578  mov     rax, rsp
0x18006457b  push    rbp
0x18006457c  push    rbx
0x18006457d  push    rsi
0x18006457e  push    rdi
0x18006457f  push    r12
0x180064581  push    r13
0x180064583  push    r14
0x180064585  push    r15
0x180064587  lea     rbp, [rax-118h]
0x18006458e  sub     rsp, 1D8h
0x180064595  xor     r15d, r15d
0x180064598  movaps  xmmword ptr [rax-58h], xmm6
0x18006459c  movaps  xmmword ptr [rax-68h], xmm7
0x1800645a0  lea     r13, aS1518; "S-1-5-18"
0x1800645a7  movaps  xmmword ptr [rax-78h], xmm8
0x1800645ac  lea     r12, aScheduleoneoma_0; "ScheduleOneOmaDmSessionClient"
0x1800645b3  movaps  xmmword ptr [rax-88h], xmm9
0x1800645bb  mov     edi, r9d
0x1800645be  mov     [rsp+210h+var_1B0], r15d
0x1800645c3  lea     r9, [rbp+110h+var_188]
0x1800645c7  movaps  xmmword ptr [rax-98h], xmm10
0x1800645cf  mov     esi, r8d
0x1800645d2  movaps  xmmword ptr [rax-0A8h], xmm11
0x1800645da  lea     r8, [rbp+110h+arg_28]
0x1800645e1  lea     rax, [rbp+110h+Data]
0x1800645e8  mov     [rbp+110h+Data], r15d
0x1800645ef  mov     [rbp+110h+var_158], rax
0x1800645f3  mov     r14, rcx
0x1800645f6  lea     eax, [r15+1]
0x1800645fa  mov     [rbp+110h+var_160], r12
0x1800645fe  mov     [rsp+210h+var_1B8], eax
0x180064602  lea     rcx, [rbp+110h+var_180]
0x180064606  mov     [rsp+210h+var_1C0], eax
0x18006460a  mov     eax, [rbp+110h+arg_50]
0x180064610  mov     [rsp+210h+var_1C8], eax
0x180064614  mov     rax, [rbp+110h+arg_30]
0x18006461b  mov     [rsp+210h+var_1D0], r15d
0x180064620  mov     [rsp+210h+var_1D8], r13
0x180064625  mov     [rsp+210h+var_1E0], rax
0x18006462a  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x180064631  mov     qword ptr [rsp+210h+cbData], rax
0x180064636  mov     [rsp+210h+lpData], rdx
0x18006463b  lea     rdx, [rsp+210h+var_1A0]
0x180064640  mov     [rbp+110h+var_180], r15
0x180064644  mov     [rsp+210h+var_1A0], r15
0x180064649  mov     [rbp+110h+arg_28], r15
0x180064650  mov     [rbp+110h+var_188], r15
0x180064654  mov     [rbp+110h+arg_38], r15
0x18006465b  mov     [rbp+110h+var_168], r15
0x18006465f  mov     [rbp+110h+var_170], r15
0x180064663  mov     [rbp+110h+var_178], r15
0x180064667  mov     [rbp+110h+var_190], r15
0x18006466b  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180064670  mov     [rbp+110h+Data], eax
0x180064676  mov     ebx, eax
0x180064678  test    eax, eax
0x18006467a  js      loc_180064896
0x180064680  mov     rcx, [rbp+110h+arg_28]
0x180064687  lea     rdx, [rbp+110h+arg_38]
0x18006468e  mov     rax, [rcx]
0x180064691  mov     rax, [rax+48h]
0x180064695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006469a  mov     [rbp+110h+Data], eax
0x1800646a0  mov     ebx, eax
0x1800646a2  test    eax, eax
0x1800646a4  js      loc_180064896
0x1800646aa  mov     r9d, [rbp+110h+arg_20]
0x1800646b1  lea     rcx, [rbp+110h+arg_38]
0x1800646b8  mov     r8d, edi
0x1800646bb  mov     edx, esi
0x1800646bd  call    ?AddTimeTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@KKK@Z; AddTimeTaskTriggers(ATL::CComPtr<ITriggerCollection> &,ulong,ulong,ulong)
0x1800646c2  mov     [rbp+110h+Data], eax
0x1800646c8  mov     ebx, eax
0x1800646ca  test    eax, eax
0x1800646cc  js      loc_180064896
0x1800646d2  mov     rcx, [rbp+110h+arg_28]
0x1800646d9  mov     rdx, [rbp+110h+arg_38]
0x1800646e0  mov     rax, [rcx]
0x1800646e3  mov     rax, [rax+50h]
0x1800646e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800646ec  mov     [rbp+110h+Data], eax
0x1800646f2  mov     ebx, eax
0x1800646f4  test    eax, eax
0x1800646f6  js      loc_180064896
0x1800646fc  mov     rbx, [rsp+210h+var_1A0]
0x180064701  lea     rcx, [rbp+110h+pvarg]; pvarg
0x180064705  mov     rax, [rbx]
0x180064708  mov     rsi, [rax+88h]
0x18006470f  call    cs:__imp_VariantInit
0x180064715  movups  xmm6, xmmword ptr [rbp+110h+pvarg]
0x180064719  lea     rcx, [rbp+110h+var_150]; pvarg
0x18006471d  movsd   xmm7, qword ptr [rbp+110h+pvarg+10h]
0x180064722  call    cs:__imp_VariantInit
0x180064728  movups  xmm8, xmmword ptr [rbp+110h+var_150]
0x18006472d  lea     rcx, [rbp+110h+var_C0]; this
0x180064731  mov     rdx, r13; unsigned __int16 *
0x180064734  movsd   xmm9, qword ptr [rbp+110h+var_150+10h]
0x18006473a  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18006473f  mov     rdi, [rbp+110h+arg_28]
0x180064746  lea     rcx, [rsp+210h+Block]; this
0x18006474b  mov     rdx, r14; unsigned __int16 *
0x18006474e  movups  xmm10, xmmword ptr [rax]
0x180064752  movsd   xmm11, qword ptr [rax+10h]
0x180064758  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006475d  mov     rdx, [rax]
0x180064760  test    rdx, rdx
0x180064763  jz      short loc_18006476A
0x180064765  mov     rdx, [rdx]
0x180064768  jmp     short loc_18006476D
0x18006476a  mov     rdx, r15
0x18006476d  lea     rax, [rbp+110h+var_190]
0x180064771  movaps  [rbp+110h+var_120], xmm6
0x180064775  mov     qword ptr [rsp+210h+var_1D0], rax
0x18006477a  mov     r9d, 6
0x180064780  lea     rax, [rbp+110h+var_120]
0x180064784  movsd   [rbp+110h+var_110], xmm7
0x180064789  mov     [rsp+210h+var_1D8], rax
0x18006478e  mov     r8, rdi
0x180064791  lea     rax, [rbp+110h+var_100]
0x180064795  mov     dword ptr [rsp+210h+var_1E0], 3
0x18006479d  mov     qword ptr [rsp+210h+cbData], rax
0x1800647a2  mov     rcx, rbx
0x1800647a5  lea     rax, [rbp+110h+var_E0]
0x1800647a9  movaps  [rbp+110h+var_100], xmm8
0x1800647ae  mov     [rsp+210h+lpData], rax
0x1800647b3  mov     rax, rsi
0x1800647b6  movsd   [rbp+110h+var_F0], xmm9
0x1800647bc  movaps  [rbp+110h+var_E0], xmm10
0x1800647c1  movsd   [rbp+110h+var_D0], xmm11
0x1800647c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800647cc  mov     rbx, [rsp+210h+Block]
0x1800647d1  mov     [rbp+110h+Data], eax
0x1800647d7  test    rbx, rbx
0x1800647da  jz      short loc_180064823
0x1800647dc  or      eax, 0FFFFFFFFh
0x1800647df  lock xadd [rbx+10h], eax
0x1800647e4  cmp     eax, 1
0x1800647e7  jnz     short loc_18006481E
0x1800647e9  test    rbx, rbx
0x1800647ec  jz      short loc_18006481E
0x1800647ee  mov     rcx, [rbx]; bstrString
0x1800647f1  test    rcx, rcx
0x1800647f4  jz      short loc_1800647FF
0x1800647f6  call    cs:__imp_SysFreeString
0x1800647fc  mov     [rbx], r15
0x1800647ff  mov     rcx, [rbx+8]; Block
0x180064803  test    rcx, rcx
0x180064806  jz      short loc_180064811
0x180064808  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006480d  mov     [rbx+8], r15
0x180064811  mov     edx, 18h
0x180064816  mov     rcx, rbx; Block
0x180064819  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006481e  mov     [rsp+210h+Block], r15
0x180064823  lea     rcx, [rbp+110h+var_C0]; this
0x180064827  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006482c  lea     rcx, [rbp+110h+var_150]; this
0x180064830  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180064835  lea     rcx, [rbp+110h+pvarg]; this
0x180064839  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006483e  mov     ebx, [rbp+110h+Data]
0x180064844  test    ebx, ebx
0x180064846  jns     short loc_180064896
0x180064848  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x18006484f  lea     rax, [rbp+110h+Data]
0x180064856  mov     r9d, 4; dwType
0x18006485c  lea     r8, a24registertask; "24RegisterTaskDefinition"
0x180064863  mov     [rsp+210h+cbData], r9d; cbData
0x180064868  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006486f  mov     [rsp+210h+lpData], rax; lpData
0x180064874  call    cs:__imp_RegSetKeyValueW
0x18006487a  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18006487f  mov     edx, [rbp+110h+Data]; int
0x180064885  mov     r8, r12; char *
0x180064888  mov     rcx, rax; this
0x18006488b  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x180064890  mov     ebx, [rbp+110h+Data]
0x180064896  lea     rcx, [rbp+110h+var_190]
0x18006489a  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18006489f  lea     rcx, [rbp+110h+var_178]
0x1800648a3  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800648a8  lea     rcx, [rbp+110h+var_170]
0x1800648ac  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800648b1  lea     rcx, [rbp+110h+var_168]
0x1800648b5  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800648ba  lea     rcx, [rbp+110h+arg_38]
0x1800648c1  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800648c6  lea     rcx, [rbp+110h+var_188]
0x1800648ca  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800648cf  lea     rcx, [rbp+110h+arg_28]
0x1800648d6  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800648db  lea     rcx, [rsp+210h+var_1A0]
0x1800648e0  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800648e5  lea     rcx, [rbp+110h+var_180]
0x1800648e9  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1800648ee  lea     rcx, [rbp+110h+var_160]; this
0x1800648f2  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800648f7  lea     r11, [rsp+210h+var_38]
0x1800648ff  mov     eax, ebx
0x180064901  movaps  xmm6, xmmword ptr [r11-18h]
0x180064906  movaps  xmm7, xmmword ptr [r11-28h]
0x18006490b  movaps  xmm8, xmmword ptr [r11-38h]
0x180064910  movaps  xmm9, xmmword ptr [r11-48h]
0x180064915  movaps  xmm10, xmmword ptr [r11-58h]
0x18006491a  movaps  xmm11, xmmword ptr [r11-68h]
0x18006491f  mov     rsp, r11
0x180064922  pop     r15
0x180064924  pop     r14
0x180064926  pop     r13
0x180064928  pop     r12
0x18006492a  pop     rdi
0x18006492b  pop     rsi
0x18006492c  pop     rbx
0x18006492d  pop     rbp
0x18006492e  retn
```
