# ScheduleOMADMClientTaskHelper

- ea: `0x1800640a4`
- end: `0x1800643b8`
- name: `ScheduleOMADMClientTaskHelper`
- size: `788`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180063fdc`

## callees

- `0x1800067a0`
- `0x18000efc4`
- `0x1800140d0`
- `0x180018074`
- `0x18001aec8`
- `0x18002e1a0`
- `0x18002e570`
- `0x1800434d0`
- `0x180043544`
- `0x180060974`
- `0x1800613ac`
- `0x1800640a4`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006431e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006431e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800642a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800642a5`
- `OLEAUT32!__imp_VariantInit` at `0x1800641c0`
- `OLEAUT32!__imp_VariantInit` at `0x1800641d3`
- `OLEAUT32!__imp_VariantInit` at `0x1800641c0`
- `OLEAUT32!__imp_VariantInit` at `0x1800641d3`

## string_xrefs

- `0x18006413c`: `ScheduleOMADMClientTaskHelper`
- `0x18006418a`: `%windir%\system32\omadmclient.exe `
- `0x180064306`: `54RegisterTaskDefinition`

## pseudocode

```c
__int64 __fastcall ScheduleOMADMClientTaskHelper(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3, int a4)
{
  __int64 v6; // rdx
  int v7; // ebx
  struct IUnknown *v8; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // r14
  __int128 v10; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v12; // xmm8
  IRecordInfo *v13; // xmm9_8
  _variant_t *v14; // rax
  __int64 v15; // rdi
  __int128 v16; // xmm10
  __int64 v17; // xmm11_8
  _bstr_t *v18; // rax
  __int64 v19; // rdx
  int v20; // eax
  BSTR *v21; // rbx
  BSTR v22; // rcx
  CEnrollmentLogger *Logger; // rax
  int v26; // [rsp+68h] [rbp-A0h]
  __int64 Data; // [rsp+78h] [rbp-90h] BYREF
  __int64 v28; // [rsp+80h] [rbp-88h] BYREF
  struct IUnknown *v29; // [rsp+88h] [rbp-80h] BYREF
  void *Block; // [rsp+90h] [rbp-78h] BYREF
  __int64 v31; // [rsp+98h] [rbp-70h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v33[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v34[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v35; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v37; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v38; // [rsp+108h] [rbp+0h]
  __int128 v39; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v40; // [rsp+128h] [rbp+20h]
  __int128 v41; // [rsp+138h] [rbp+30h] BYREF
  __int64 v42; // [rsp+148h] [rbp+40h]
  VARIANTARG v43; // [rsp+158h] [rbp+50h] BYREF
  unsigned __int16 v44[264]; // [rsp+178h] [rbp+70h] BYREF

  v33[0] = 0;
  v29 = 0;
  v28 = 0;
  v32 = 0;
  v31 = 0;
  v7 = StringCchPrintfW(v44, 0x104u, L"/serverid \"%s\" /lookuptype 1 /initiator %d ", a1, a4);
  LODWORD(Data) = v7;
  v34[1] = &Data;
  v34[0] = "ScheduleOMADMClientTaskHelper";
  if ( v7 >= 0 )
  {
    v26 = 0;
    LODWORD(Data) = CreateTask(
                      v33,
                      &v29,
                      &v28,
                      &v32,
                      a1,
                      L"%windir%\\system32\\omadmclient.exe ",
                      v44,
                      0,
                      0,
                      1,
                      0,
                      0,
                      v26);
    v7 = Data;
    if ( (int)Data >= 0 )
    {
      v8 = v29;
      Release = v29->lpVtbl[5].Release;
      VariantInit(&pvarg);
      v10 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v35);
      v12 = *(_OWORD *)&v35.vt;
      v13 = v35.pRecInfo;
      v14 = _variant_t::_variant_t((_variant_t *)&v43, L"S-1-5-18");
      v15 = v28;
      v16 = *(_OWORD *)v14;
      v17 = *((_QWORD *)v14 + 2);
      v18 = _bstr_t::_bstr_t((_bstr_t *)&Block, a3);
      if ( *(_QWORD *)v18 )
        v19 = **(_QWORD **)v18;
      else
        v19 = 0;
      v37 = v10;
      v38 = pRecInfo;
      v39 = v12;
      v40 = v13;
      v41 = v16;
      v42 = v17;
      v20 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))Release)(
              v8,
              v19,
              v15,
              6,
              &v41,
              &v39,
              3,
              &v37,
              &v31);
      v21 = (BSTR *)Block;
      LODWORD(Data) = v20;
      if ( Block )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v21 )
        {
          if ( *v21 )
          {
            SysFreeString(*v21);
            *v21 = 0;
          }
          v22 = v21[1];
          if ( v22 )
          {
            operator delete(v22);
            v21[1] = 0;
          }
          operator delete(v21);
        }
        Block = 0;
      }
      _variant_t::~_variant_t(&v43);
      _variant_t::~_variant_t(&v35);
      _variant_t::~_variant_t(&pvarg);
      v7 = Data;
      if ( (int)Data < 0 )
      {
        RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"54RegisterTaskDefinition", 4u, &Data, 4u);
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Data, "ScheduleOMADMClientTaskHelper");
        v7 = Data;
      }
    }
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v34, v6);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v31);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v32);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v28);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&v29);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v33);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800640a4  mov     rax, rsp
0x1800640a7  push    rbp
0x1800640a8  push    rbx
0x1800640a9  push    rsi
0x1800640aa  push    rdi
0x1800640ab  push    r12
0x1800640ad  push    r14
0x1800640af  push    r15
0x1800640b1  lea     rbp, [rax-328h]
0x1800640b8  sub     rsp, 3F0h
0x1800640bf  movaps  xmmword ptr [rax-48h], xmm6
0x1800640c3  movaps  xmmword ptr [rax-58h], xmm7
0x1800640c7  movaps  xmmword ptr [rax-68h], xmm8
0x1800640cc  movaps  xmmword ptr [rax-78h], xmm9
0x1800640d1  movaps  xmmword ptr [rax-88h], xmm10
0x1800640d9  movaps  xmmword ptr [rax-98h], xmm11
0x1800640e1  mov     rax, cs:__security_cookie
0x1800640e8  xor     rax, rsp
0x1800640eb  mov     [rbp+320h+var_A0], rax
0x1800640f2  xor     r15d, r15d
0x1800640f5  mov     dword ptr [rsp+420h+lpData], r9d
0x1800640fa  mov     r9, rcx
0x1800640fd  mov     [rbp+320h+var_380], r15
0x180064101  mov     rsi, r8
0x180064104  mov     [rbp+320h+var_3A0], r15
0x180064108  mov     rdi, rcx
0x18006410b  mov     [rsp+420h+var_3A8], r15
0x180064110  lea     rcx, [rbp+320h+var_2B0]; unsigned __int16 *
0x180064114  mov     [rbp+320h+var_388], r15
0x180064118  lea     r8, aServeridSLooku; "/serverid \"%s\" /lookuptype 1 /initiat"...
0x18006411f  mov     [rbp+320h+var_390], r15
0x180064123  mov     edx, 104h; unsigned __int64
0x180064128  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006412d  mov     ebx, eax
0x18006412f  mov     dword ptr [rsp+420h+Data], eax
0x180064133  lea     rax, [rsp+420h+Data]
0x180064138  mov     [rbp+320h+var_368], rax
0x18006413c  lea     r12, aScheduleomadmc; "ScheduleOMADMClientTaskHelper"
0x180064143  mov     [rbp+320h+var_370], r12
0x180064147  test    ebx, ebx
0x180064149  js      loc_18006433C
0x18006414f  mov     [rsp+420h+var_3C0], r15d
0x180064154  lea     rax, [rbp+320h+var_2B0]
0x180064158  mov     [rsp+420h+var_3C8], r15d
0x18006415d  lea     r9, [rbp+320h+var_388]
0x180064161  mov     [rsp+420h+var_3D0], r15d
0x180064166  lea     r8, [rsp+420h+var_3A8]
0x18006416b  mov     [rsp+420h+var_3D8], 1
0x180064173  lea     rdx, [rbp+320h+var_3A0]
0x180064177  mov     [rsp+420h+var_3E0], r15d
0x18006417c  lea     rcx, [rbp+320h+var_380]
0x180064180  mov     [rsp+420h+var_3E8], r15
0x180064185  mov     [rsp+420h+var_3F0], rax
0x18006418a  lea     rax, aWindirSystem32; "%windir%\\system32\\omadmclient.exe "
0x180064191  mov     qword ptr [rsp+420h+cbData], rax
0x180064196  mov     [rsp+420h+lpData], rdi
0x18006419b  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x1800641a0  mov     dword ptr [rsp+420h+Data], eax
0x1800641a4  mov     ebx, eax
0x1800641a6  test    eax, eax
0x1800641a8  js      loc_18006433C
0x1800641ae  mov     rbx, [rbp+320h+var_3A0]
0x1800641b2  lea     rcx, [rbp+320h+pvarg]; pvarg
0x1800641b6  mov     rax, [rbx]
0x1800641b9  mov     r14, [rax+88h]
0x1800641c0  call    cs:__imp_VariantInit
0x1800641c6  movups  xmm6, xmmword ptr [rbp+320h+pvarg]
0x1800641ca  lea     rcx, [rbp+320h+var_360]; pvarg
0x1800641ce  movsd   xmm7, qword ptr [rbp+320h+pvarg+10h]
0x1800641d3  call    cs:__imp_VariantInit
0x1800641d9  movups  xmm8, xmmword ptr [rbp+320h+var_360]
0x1800641de  lea     rdx, aS1518; "S-1-5-18"
0x1800641e5  movsd   xmm9, qword ptr [rbp+320h+var_360+10h]
0x1800641eb  lea     rcx, [rbp+320h+var_2D0]; this
0x1800641ef  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x1800641f4  mov     rdi, [rsp+420h+var_3A8]
0x1800641f9  lea     rcx, [rbp+320h+Block]; this
0x1800641fd  mov     rdx, rsi; unsigned __int16 *
0x180064200  movups  xmm10, xmmword ptr [rax]
0x180064204  movsd   xmm11, qword ptr [rax+10h]
0x18006420a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006420f  mov     rdx, [rax]
0x180064212  test    rdx, rdx
0x180064215  jz      short loc_18006421C
0x180064217  mov     rdx, [rdx]
0x18006421a  jmp     short loc_18006421F
0x18006421c  mov     rdx, r15
0x18006421f  lea     rax, [rbp+320h+var_390]
0x180064223  movaps  [rbp+320h+var_330], xmm6
0x180064227  mov     qword ptr [rsp+420h+var_3E0], rax
0x18006422c  mov     r9d, 6
0x180064232  lea     rax, [rbp+320h+var_330]
0x180064236  movsd   [rbp+320h+var_320], xmm7
0x18006423b  mov     [rsp+420h+var_3E8], rax
0x180064240  mov     r8, rdi
0x180064243  lea     rax, [rbp+320h+var_310]
0x180064247  mov     dword ptr [rsp+420h+var_3F0], 3
0x18006424f  mov     qword ptr [rsp+420h+cbData], rax
0x180064254  mov     rcx, rbx
0x180064257  lea     rax, [rbp+320h+var_2F0]
0x18006425b  movaps  [rbp+320h+var_310], xmm8
0x180064260  mov     [rsp+420h+lpData], rax
0x180064265  mov     rax, r14
0x180064268  movsd   [rbp+320h+var_300], xmm9
0x18006426e  movaps  [rbp+320h+var_2F0], xmm10
0x180064273  movsd   [rbp+320h+var_2E0], xmm11
0x180064279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006427e  mov     rbx, [rbp+320h+Block]
0x180064282  mov     dword ptr [rsp+420h+Data], eax
0x180064286  test    rbx, rbx
0x180064289  jz      short loc_1800642D1
0x18006428b  or      eax, 0FFFFFFFFh
0x18006428e  lock xadd [rbx+10h], eax
0x180064293  cmp     eax, 1
0x180064296  jnz     short loc_1800642CD
0x180064298  test    rbx, rbx
0x18006429b  jz      short loc_1800642CD
0x18006429d  mov     rcx, [rbx]; bstrString
0x1800642a0  test    rcx, rcx
0x1800642a3  jz      short loc_1800642AE
0x1800642a5  call    cs:__imp_SysFreeString
0x1800642ab  mov     [rbx], r15
0x1800642ae  mov     rcx, [rbx+8]; Block
0x1800642b2  test    rcx, rcx
0x1800642b5  jz      short loc_1800642C0
0x1800642b7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800642bc  mov     [rbx+8], r15
0x1800642c0  mov     edx, 18h
0x1800642c5  mov     rcx, rbx; Block
0x1800642c8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800642cd  mov     [rbp+320h+Block], r15
0x1800642d1  lea     rcx, [rbp+320h+var_2D0]; this
0x1800642d5  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800642da  lea     rcx, [rbp+320h+var_360]; this
0x1800642de  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800642e3  lea     rcx, [rbp+320h+pvarg]; this
0x1800642e7  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800642ec  mov     ebx, dword ptr [rsp+420h+Data]
0x1800642f0  test    ebx, ebx
0x1800642f2  jns     short loc_18006433C
0x1800642f4  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x1800642fb  lea     rax, [rsp+420h+Data]
0x180064300  mov     r9d, 4; dwType
0x180064306  lea     r8, a54registertask; "54RegisterTaskDefinition"
0x18006430d  mov     [rsp+420h+cbData], r9d; cbData
0x180064312  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180064319  mov     [rsp+420h+lpData], rax; lpData
0x18006431e  call    cs:__imp_RegSetKeyValueW
0x180064324  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180064329  mov     edx, dword ptr [rsp+420h+Data]; int
0x18006432d  mov     r8, r12; char *
0x180064330  mov     rcx, rax; this
0x180064333  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x180064338  mov     ebx, dword ptr [rsp+420h+Data]
0x18006433c  lea     rcx, [rbp+320h+var_370]; this
0x180064340  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180064345  lea     rcx, [rbp+320h+var_390]
0x180064349  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18006434e  lea     rcx, [rbp+320h+var_388]
0x180064352  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180064357  lea     rcx, [rsp+420h+var_3A8]
0x18006435c  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180064361  lea     rcx, [rbp+320h+var_3A0]
0x180064365  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18006436a  lea     rcx, [rbp+320h+var_380]
0x18006436e  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180064373  mov     eax, ebx
0x180064375  mov     rcx, [rbp+320h+var_A0]
0x18006437c  xor     rcx, rsp; StackCookie
0x18006437f  call    __security_check_cookie
0x180064384  lea     r11, [rsp+420h+var_30]
0x18006438c  movaps  xmm6, xmmword ptr [r11-10h]
0x180064391  movaps  xmm7, xmmword ptr [r11-20h]
0x180064396  movaps  xmm8, xmmword ptr [r11-30h]
0x18006439b  movaps  xmm9, xmmword ptr [r11-40h]
0x1800643a0  movaps  xmm10, xmmword ptr [r11-50h]
0x1800643a5  movaps  xmm11, xmmword ptr [r11-60h]
0x1800643aa  mov     rsp, r11
0x1800643ad  pop     r15
0x1800643af  pop     r14
0x1800643b1  pop     r12
0x1800643b3  pop     rdi
0x1800643b4  pop     rsi
0x1800643b5  pop     rbx
0x1800643b6  pop     rbp
0x1800643b7  retn
```
