# ScheduleOMADMClientTaskHelper

- ea: `0x180019560`
- end: `0x1800198fc`
- name: `ScheduleOMADMClientTaskHelper`
- size: `924`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800194bc`

## callees

- `0x1800022e0`
- `0x180006c98`
- `0x18000aa2c`
- `0x18000aab8`
- `0x18000ab84`
- `0x1800117c8`
- `0x180011d5c`
- `0x180012ed4`
- `0x180019560`
- `0x18001dce8`
- `0x18001e264`
- `0x180020010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180019746`
- `OLEAUT32!__imp_SysAllocString` at `0x180019746`
- `OLEAUT32!__imp_VariantInit` at `0x180019710`
- `OLEAUT32!__imp_VariantInit` at `0x180019725`
- `OLEAUT32!__imp_VariantInit` at `0x180019710`
- `OLEAUT32!__imp_VariantInit` at `0x180019725`
- `OLEAUT32!__imp_VariantClear` at `0x1800197f9`
- `OLEAUT32!__imp_VariantClear` at `0x180019803`
- `OLEAUT32!__imp_VariantClear` at `0x18001980d`
- `OLEAUT32!__imp_VariantClear` at `0x1800197f9`
- `OLEAUT32!__imp_VariantClear` at `0x180019803`
- `OLEAUT32!__imp_VariantClear` at `0x18001980d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180019845`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180019845`

## string_xrefs

- `0x1800195fe`: `ScheduleOMADMClientTaskHelper`
- `0x18001969c`: `%windir%\system32\omadmclient.exe `
- `0x180019830`: `54RegisterTaskDefinition`

## pseudocode

```c
__int64 __fastcall ScheduleOMADMClientTaskHelper(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3, int a4)
{
  int Task; // ebx
  void (*v7)(void); // rax
  __int64 *v8; // rdi
  __int64 v9; // rbx
  __int128 v10; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v12; // xmm10
  IRecordInfo *v13; // xmm11_8
  __int64 (__fastcall *v14)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // r14
  __int128 v15; // xmm6
  IRecordInfo *v16; // xmm7_8
  __int64 v17; // rbx
  _bstr_t *v18; // rax
  __int64 v19; // rdx
  const struct std::nothrow_t *v20; // rdx
  CEnrollmentLogger *Logger; // rax
  __int64 Data; // [rsp+78h] [rbp-90h] BYREF
  int v24[2]; // [rsp+80h] [rbp-88h] BYREF
  int v25[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v26; // [rsp+90h] [rbp-78h] BYREF
  int v27[2]; // [rsp+98h] [rbp-70h] BYREF
  int v28[2]; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v29[2]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v30[8]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v31; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v32; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v34; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v35; // [rsp+118h] [rbp+10h]
  __int128 v36; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v37; // [rsp+138h] [rbp+30h]
  __int128 v38; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v39; // [rsp+158h] [rbp+50h]
  unsigned __int16 v40[264]; // [rsp+168h] [rbp+60h] BYREF

  *(_QWORD *)v28 = 0;
  *(_QWORD *)v25 = 0;
  *(_QWORD *)v24 = 0;
  *(_QWORD *)v27 = 0;
  v26 = 0;
  Task = StringCchPrintfW(v40, 0x104u, L"/serverid \"%s\" /lookuptype 1 /initiator %d ", a1, a4);
  LODWORD(Data) = Task;
  v29[0] = "ScheduleOMADMClientTaskHelper";
  v29[1] = &Data;
  if ( Task < 0
    || (Task = CreateTask(
                 v28,
                 (__int64 *)v25,
                 v24,
                 v27,
                 a1,
                 L"%windir%\\system32\\omadmclient.exe ",
                 v40,
                 0,
                 0,
                 1,
                 0,
                 0,
                 0),
        LODWORD(Data) = Task,
        Task < 0) )
  {
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v29);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v26);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v27);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v24);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v25);
    if ( *(_QWORD *)v28 )
    {
      v7 = *(void (**)(void))(**(_QWORD **)v28 + 16LL);
LABEL_13:
      v7();
    }
  }
  else
  {
    v8 = *(__int64 **)v25;
    v9 = **(_QWORD **)v25;
    VariantInit(&pvarg);
    v10 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v32);
    v12 = *(_OWORD *)&v32.vt;
    v13 = v32.pRecInfo;
    v31.vt = 8;
    v31.llVal = (LONGLONG)SysAllocString(L"S-1-5-18");
    if ( !v31.llVal )
      _com_issue_error(-2147024882);
    v14 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v9 + 136);
    v15 = *(_OWORD *)&v31.vt;
    v16 = v31.pRecInfo;
    v17 = *(_QWORD *)v24;
    v18 = _bstr_t::_bstr_t((_bstr_t *)v30, a3);
    if ( *(_QWORD *)v18 )
      v19 = **(_QWORD **)v18;
    else
      v19 = 0;
    v34 = v10;
    v35 = pRecInfo;
    v36 = v12;
    v37 = v13;
    v38 = v15;
    v39 = v16;
    LODWORD(Data) = v14(v8, v19, v17, 6, &v38, &v36, 3, &v34, &v26);
    _bstr_t::~_bstr_t((_bstr_t *)v30, v20);
    VariantClear(&v31);
    VariantClear(&v32);
    VariantClear(&pvarg);
    Task = Data;
    if ( (int)Data < 0 )
    {
      RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"54RegisterTaskDefinition", 4u, &Data, 4u);
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Data, "ScheduleOMADMClientTaskHelper");
      Task = Data;
    }
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v29);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v26);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v27);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v24);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v25);
    if ( *(_QWORD *)v28 )
    {
      v7 = *(void (**)(void))(**(_QWORD **)v28 + 16LL);
      goto LABEL_13;
    }
  }
  return (unsigned int)Task;
}

```

## disassembly

```asm
0x180019560  mov     rax, rsp
0x180019563  mov     [rax+10h], rbx
0x180019567  push    rbp
0x180019568  push    rsi
0x180019569  push    rdi
0x18001956a  push    r12
0x18001956c  push    r14
0x18001956e  lea     rbp, [rax-308h]
0x180019575  sub     rsp, 3E0h
0x18001957c  movaps  xmmword ptr [rax-38h], xmm6
0x180019580  movaps  xmmword ptr [rax-48h], xmm7
0x180019584  movaps  xmmword ptr [rax-58h], xmm8
0x180019589  movaps  xmmword ptr [rax-68h], xmm9
0x18001958e  movaps  xmmword ptr [rax-78h], xmm10
0x180019593  movaps  xmmword ptr [rax-88h], xmm11
0x18001959b  mov     rax, cs:__security_cookie
0x1800195a2  xor     rax, rsp
0x1800195a5  mov     [rbp+300h+var_90], rax
0x1800195ac  mov     rsi, r8
0x1800195af  mov     rdi, rcx
0x1800195b2  mov     qword ptr [rbp+300h+var_368], 0
0x1800195ba  mov     qword ptr [rbp+300h+var_380], 0
0x1800195c2  mov     qword ptr [rsp+400h+var_388], 0
0x1800195cb  mov     qword ptr [rbp+300h+var_370], 0
0x1800195d3  mov     [rbp+300h+var_378], 0
0x1800195db  mov     dword ptr [rsp+400h+lpData], r9d
0x1800195e0  mov     r9, rcx
0x1800195e3  lea     r8, aServeridSLooku; "/serverid \"%s\" /lookuptype 1 /initiat"...
0x1800195ea  mov     edx, 104h; unsigned __int64
0x1800195ef  lea     rcx, [rbp+300h+var_2A0]; unsigned __int16 *
0x1800195f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800195f8  mov     ebx, eax
0x1800195fa  mov     dword ptr [rsp+400h+Data], eax
0x1800195fe  lea     r12, aScheduleomadmc; "ScheduleOMADMClientTaskHelper"
0x180019605  mov     [rbp+300h+var_360], r12
0x180019609  lea     rax, [rsp+400h+Data]
0x18001960e  mov     [rbp+300h+var_358], rax
0x180019612  test    ebx, ebx
0x180019614  jns     short loc_180019662
0x180019616  lea     rcx, [rbp+300h+var_360]; this
0x18001961a  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001961f  nop
0x180019620  lea     rcx, [rbp+300h+var_378]
0x180019624  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019629  nop
0x18001962a  lea     rcx, [rbp+300h+var_370]
0x18001962e  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019633  nop
0x180019634  lea     rcx, [rsp+400h+var_388]
0x180019639  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001963e  nop
0x18001963f  lea     rcx, [rbp+300h+var_380]
0x180019643  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019648  nop
0x180019649  mov     rcx, qword ptr [rbp+300h+var_368]
0x18001964d  test    rcx, rcx
0x180019650  jz      loc_1800198AB
0x180019656  mov     rax, [rcx]
0x180019659  mov     rax, [rax+10h]
0x18001965d  jmp     loc_1800198A6
0x180019662  mov     [rsp+400h+var_3A0], 0; int
0x18001966a  mov     [rsp+400h+var_3A8], 0; int
0x180019672  mov     [rsp+400h+var_3B0], 0; int
0x18001967a  mov     [rsp+400h+var_3B8], 1; int
0x180019682  mov     [rsp+400h+var_3C0], 0; int
0x18001968a  mov     [rsp+400h+var_3C8], 0; unsigned __int16 *
0x180019693  lea     rax, [rbp+300h+var_2A0]
0x180019697  mov     [rsp+400h+var_3D0], rax; unsigned __int16 *
0x18001969c  lea     rax, aWindirSystem32; "%windir%\\system32\\omadmclient.exe "
0x1800196a3  mov     qword ptr [rsp+400h+cbData], rax; unsigned __int16 *
0x1800196a8  mov     [rsp+400h+lpData], rdi; unsigned __int16 *
0x1800196ad  lea     r9, [rbp+300h+var_370]; int
0x1800196b1  lea     r8, [rsp+400h+var_388]; int
0x1800196b6  lea     rdx, [rbp+300h+var_380]; int
0x1800196ba  lea     rcx, [rbp+300h+var_368]; int
0x1800196be  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x1800196c3  mov     ebx, eax
0x1800196c5  mov     dword ptr [rsp+400h+Data], eax
0x1800196c9  test    eax, eax
0x1800196cb  jns     short loc_180019705
0x1800196cd  lea     rcx, [rbp+300h+var_360]; this
0x1800196d1  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800196d6  nop
0x1800196d7  lea     rcx, [rbp+300h+var_378]
0x1800196db  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1800196e0  nop
0x1800196e1  lea     rcx, [rbp+300h+var_370]
0x1800196e5  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1800196ea  nop
0x1800196eb  lea     rcx, [rsp+400h+var_388]
0x1800196f0  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1800196f5  nop
0x1800196f6  lea     rcx, [rbp+300h+var_380]
0x1800196fa  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1800196ff  nop
0x180019700  jmp     loc_180019649
0x180019705  mov     rdi, qword ptr [rbp+300h+var_380]
0x180019709  mov     rbx, [rdi]
0x18001970c  lea     rcx, [rbp+300h+pvarg]; pvarg
0x180019710  call    cs:__imp_VariantInit
0x180019716  movups  xmm8, xmmword ptr [rbp+300h+pvarg]
0x18001971b  movsd   xmm9, qword ptr [rbp+300h+pvarg+10h]
0x180019721  lea     rcx, [rbp+300h+var_330]; pvarg
0x180019725  call    cs:__imp_VariantInit
0x18001972b  movups  xmm10, xmmword ptr [rbp+300h+var_330]
0x180019730  movsd   xmm11, qword ptr [rbp+300h+var_330+10h]
0x180019736  mov     eax, 8
0x18001973b  mov     word ptr [rbp+300h+var_348], ax
0x18001973f  lea     rcx, psz; "S-1-5-18"
0x180019746  call    cs:__imp_SysAllocString
0x18001974c  mov     qword ptr [rbp+300h+var_348+8], rax
0x180019750  test    rax, rax
0x180019753  jz      loc_1800198F1
0x180019759  mov     r14, [rbx+88h]
0x180019760  movups  xmm6, xmmword ptr [rbp+300h+var_348]
0x180019764  movsd   xmm7, qword ptr [rbp+300h+var_348+10h]
0x180019769  mov     rbx, qword ptr [rsp+400h+var_388]
0x18001976e  mov     rdx, rsi; unsigned __int16 *
0x180019771  lea     rcx, [rbp+300h+var_350]; this
0x180019775  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001977a  mov     rcx, [rax]
0x18001977d  test    rcx, rcx
0x180019780  jz      short loc_180019787
0x180019782  mov     rdx, [rcx]
0x180019785  jmp     short loc_180019789
0x180019787  xor     edx, edx
0x180019789  movaps  [rbp+300h+var_300], xmm8
0x18001978e  movsd   [rbp+300h+var_2F0], xmm9
0x180019794  movaps  [rbp+300h+var_2E0], xmm10
0x180019799  movsd   [rbp+300h+var_2D0], xmm11
0x18001979f  movaps  [rbp+300h+var_2C0], xmm6
0x1800197a3  movsd   [rbp+300h+var_2B0], xmm7
0x1800197a8  lea     rax, [rbp+300h+var_378]
0x1800197ac  mov     qword ptr [rsp+400h+var_3C0], rax
0x1800197b1  lea     rax, [rbp+300h+var_300]
0x1800197b5  mov     [rsp+400h+var_3C8], rax
0x1800197ba  mov     dword ptr [rsp+400h+var_3D0], 3
0x1800197c2  lea     rax, [rbp+300h+var_2E0]
0x1800197c6  mov     qword ptr [rsp+400h+cbData], rax
0x1800197cb  lea     rax, [rbp+300h+var_2C0]
0x1800197cf  mov     [rsp+400h+lpData], rax
0x1800197d4  mov     r9d, 6
0x1800197da  mov     r8, rbx
0x1800197dd  mov     rcx, rdi
0x1800197e0  mov     rax, r14
0x1800197e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197e8  mov     dword ptr [rsp+400h+Data], eax
0x1800197ec  lea     rcx, [rbp+300h+var_350]; this
0x1800197f0  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800197f5  lea     rcx, [rbp+300h+var_348]; pvarg
0x1800197f9  call    cs:__imp_VariantClear
0x1800197ff  lea     rcx, [rbp+300h+var_330]; pvarg
0x180019803  call    cs:__imp_VariantClear
0x180019809  lea     rcx, [rbp+300h+pvarg]; pvarg
0x18001980d  call    cs:__imp_VariantClear
0x180019813  mov     ebx, dword ptr [rsp+400h+Data]
0x180019817  test    ebx, ebx
0x180019819  jns     short loc_180019863
0x18001981b  mov     r9d, 4; dwType
0x180019821  mov     [rsp+400h+cbData], r9d; cbData
0x180019826  lea     rax, [rsp+400h+Data]
0x18001982b  mov     [rsp+400h+lpData], rax; lpData
0x180019830  lea     r8, a54registertask; "54RegisterTaskDefinition"
0x180019837  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x18001983e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019845  call    cs:__imp_RegSetKeyValueW
0x18001984b  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180019850  mov     r8, r12; char *
0x180019853  mov     edx, dword ptr [rsp+400h+Data]; int
0x180019857  mov     rcx, rax; this
0x18001985a  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18001985f  mov     ebx, dword ptr [rsp+400h+Data]
0x180019863  lea     rcx, [rbp+300h+var_360]; this
0x180019867  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001986c  nop
0x18001986d  lea     rcx, [rbp+300h+var_378]
0x180019871  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019876  nop
0x180019877  lea     rcx, [rbp+300h+var_370]
0x18001987b  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019880  nop
0x180019881  lea     rcx, [rsp+400h+var_388]
0x180019886  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001988b  nop
0x18001988c  lea     rcx, [rbp+300h+var_380]
0x180019890  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019895  nop
0x180019896  mov     rcx, qword ptr [rbp+300h+var_368]
0x18001989a  test    rcx, rcx
0x18001989d  jz      short loc_1800198AB
0x18001989f  mov     rdx, [rcx]
0x1800198a2  mov     rax, [rdx+10h]
0x1800198a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198ab  mov     eax, ebx
0x1800198ad  mov     rcx, [rbp+300h+var_90]
0x1800198b4  xor     rcx, rsp; StackCookie
0x1800198b7  call    __security_check_cookie
0x1800198bc  lea     r11, [rsp+400h+var_20]
0x1800198c4  mov     rbx, [r11+38h]
0x1800198c8  movaps  xmm6, xmmword ptr [r11-10h]
0x1800198cd  movaps  xmm7, xmmword ptr [r11-20h]
0x1800198d2  movaps  xmm8, xmmword ptr [r11-30h]
0x1800198d7  movaps  xmm9, xmmword ptr [r11-40h]
0x1800198dc  movaps  xmm10, xmmword ptr [r11-50h]
0x1800198e1  movaps  xmm11, xmmword ptr [r11-60h]
0x1800198e6  mov     rsp, r11
0x1800198e9  pop     r14
0x1800198eb  pop     r12
0x1800198ed  pop     rdi
0x1800198ee  pop     rsi
0x1800198ef  pop     rbp
0x1800198f0  retn
0x1800198f1  mov     ecx, 8007000Eh; int
0x1800198f6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
