# ScheduleOneOmaDmSessionClient

- ea: `0x180021d40`
- end: `0x18002215e`
- name: `ScheduleOneOmaDmSessionClient`
- size: `1054`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *, unsigned int, unsigned int, unsigned int, __int64, unsigned __int16 *, __int64, int Data, int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021b88`

## callees

- `0x18000604c`
- `0x18001cdb8`
- `0x18001ce6c`
- `0x18001d484`
- `0x18001dd58`
- `0x180021d40`
- `0x1800245fc`
- `0x180024b94`
- `0x18003593c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180022052`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180022052`
- `OLEAUT32!__imp_SysAllocString` at `0x180021f08`
- `OLEAUT32!__imp_SysAllocString` at `0x180021f55`
- `OLEAUT32!__imp_SysAllocString` at `0x180021f08`
- `OLEAUT32!__imp_SysAllocString` at `0x180021f55`
- `OLEAUT32!__imp_VariantInit` at `0x180021ee1`
- `OLEAUT32!__imp_VariantInit` at `0x180021ef4`
- `OLEAUT32!__imp_VariantInit` at `0x180021ee1`
- `OLEAUT32!__imp_VariantInit` at `0x180021ef4`
- `OLEAUT32!__imp_VariantClear` at `0x180021fea`
- `OLEAUT32!__imp_VariantClear` at `0x180021ffc`
- `OLEAUT32!__imp_VariantClear` at `0x18002200e`
- `OLEAUT32!__imp_VariantClear` at `0x180021fea`
- `OLEAUT32!__imp_VariantClear` at `0x180021ffc`
- `OLEAUT32!__imp_VariantClear` at `0x18002200e`

## string_xrefs

- `0x18002203a`: `24RegisterTaskDefinition`
- `0x180021deb`: `%windir%\system32\deviceenroller.exe `

## pseudocode

```c
__int64 __fastcall ScheduleOneOmaDmSessionClient(
        OLECHAR *psz,
        OLECHAR *a2,
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
  __int64 *v15; // rsi
  __int64 v16; // r14
  __int128 v17; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v19; // xmm8
  IRecordInfo *v20; // xmm9_8
  BSTR v21; // rax
  IRecordInfo *v22; // xmm11_8
  __int64 v23; // r15
  __int128 v24; // xmm10
  BSTR *v25; // rbx
  BSTR v26; // rax
  BSTR v27; // rdx
  __int64 (__fastcall *v28)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rax
  HRESULT v29; // eax
  HRESULT v30; // eax
  HRESULT v31; // eax
  CEnrollmentLogger *Logger; // rax
  int v34[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v35; // [rsp+80h] [rbp-88h] BYREF
  int v36[2]; // [rsp+88h] [rbp-80h] BYREF
  int v37[2]; // [rsp+90h] [rbp-78h] BYREF
  BSTR *v38; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG v39; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v40[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v41; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v43; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v44; // [rsp+108h] [rbp+0h]
  __int128 v45; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v46; // [rsp+128h] [rbp+20h]
  __int128 v47; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v48; // [rsp+148h] [rbp+40h]

  v40[0] = "ScheduleOneOmaDmSessionClient";
  v40[1] = &Data;
  Data = 0;
  *(_QWORD *)v37 = 0;
  *(_QWORD *)v34 = 0;
  a6 = 0;
  *(_QWORD *)v36 = 0;
  a8 = 0;
  v35 = 0;
  Data = CreateTask(
           (LPVOID *)v37,
           (BSTR ***)v34,
           &a6,
           v36,
           a2,
           L"%windir%\\system32\\deviceenroller.exe ",
           a7,
           L"S-1-5-18",
           0,
           a11,
           1,
           1,
           0);
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
          v15 = *(__int64 **)v34;
          v16 = **(_QWORD **)v34;
          VariantInit(&pvarg);
          v17 = *(_OWORD *)&pvarg.vt;
          pRecInfo = pvarg.pRecInfo;
          VariantInit(&v41);
          v19 = *(_OWORD *)&v41.vt;
          v20 = v41.pRecInfo;
          v21 = SysAllocString(L"S-1-5-18");
          if ( !v21 )
            goto LABEL_27;
          v22 = v39.pRecInfo;
          v23 = a6;
          v39.vt = 8;
          v39.llVal = (LONGLONG)v21;
          v24 = *(_OWORD *)&v39.vt;
          v25 = (BSTR *)operator new(0x18u);
          v25[1] = 0;
          *((_DWORD *)v25 + 4) = 1;
          v26 = SysAllocString(psz);
          *v25 = v26;
          if ( !v26 )
          {
            if ( psz )
LABEL_27:
              _com_issue_error(-2147024882);
          }
          v38 = v25;
          v27 = v26;
          v28 = *(__int64 (__fastcall **)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v16 + 136);
          v43 = v17;
          v44 = pRecInfo;
          v45 = v19;
          v46 = v20;
          v47 = v24;
          v48 = v22;
          Data = v28(v15, v27, v23, 6, &v47, &v45, 3, &v43, &v35);
          _bstr_t::~_bstr_t((_bstr_t *)&v38);
          v29 = VariantClear(&v39);
          if ( v29 < 0 )
            _com_issue_error(v29);
          v30 = VariantClear(&v41);
          if ( v30 < 0 )
            _com_issue_error(v30);
          v31 = VariantClear(&pvarg);
          if ( v31 < 0 )
            _com_issue_error(v31);
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
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  if ( a8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a8 + 16LL))(a8);
  if ( *(_QWORD *)v36 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v36 + 16LL))(*(_QWORD *)v36);
  if ( a6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
  if ( *(_QWORD *)v34 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v34 + 16LL))(*(_QWORD *)v34);
  if ( *(_QWORD *)v37 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v37 + 16LL))(*(_QWORD *)v37);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
  return v14;
}

```

## disassembly

```asm
0x180021d40  mov     rax, rsp
0x180021d43  push    rbp
0x180021d44  push    rbx
0x180021d45  push    rsi
0x180021d46  push    rdi
0x180021d47  push    r14
0x180021d49  push    r15
0x180021d4b  lea     rbp, [rax-0E8h]
0x180021d52  sub     rsp, 1B8h
0x180021d59  movaps  xmmword ptr [rax-48h], xmm6
0x180021d5d  lea     r15, aS1518; "S-1-5-18"
0x180021d64  movaps  xmmword ptr [rax-58h], xmm7
0x180021d68  mov     esi, r9d
0x180021d6b  movaps  xmmword ptr [rax-68h], xmm8
0x180021d70  lea     r9, [rbp+0E0h+var_160]; int
0x180021d74  movaps  xmmword ptr [rax-78h], xmm9
0x180021d79  mov     r14d, r8d
0x180021d7c  mov     [rsp+1E0h+var_180], 0; Data
0x180021d84  lea     r8, [rbp+0E0h+arg_28]; int
0x180021d8b  movaps  xmmword ptr [rax-88h], xmm10
0x180021d93  mov     rdi, rcx
0x180021d96  mov     [rsp+1E0h+var_188], 1; int
0x180021d9e  lea     rcx, [rbp+0E0h+var_158]; int
0x180021da2  movaps  xmmword ptr [rax-98h], xmm11
0x180021daa  lea     rax, aScheduleoneoma_0; "ScheduleOneOmaDmSessionClient"
0x180021db1  mov     [rsp+1E0h+var_190], 1; int
0x180021db9  mov     [rbp+0E0h+var_130], rax
0x180021dbd  lea     rax, [rbp+0E0h+Data]
0x180021dc4  mov     [rbp+0E0h+var_128], rax
0x180021dc8  mov     eax, [rbp+0E0h+arg_50]
0x180021dce  mov     [rsp+1E0h+var_198], eax; int
0x180021dd2  mov     rax, [rbp+0E0h+arg_30]
0x180021dd9  mov     [rsp+1E0h+var_1A0], 0; int
0x180021de1  mov     [rsp+1E0h+var_1A8], r15; unsigned __int16 *
0x180021de6  mov     [rsp+1E0h+var_1B0], rax; unsigned __int16 *
0x180021deb  lea     rax, aWindirSystem32_1; "%windir%\\system32\\deviceenroller.exe "
0x180021df2  mov     qword ptr [rsp+1E0h+cbData], rax; unsigned __int16 *
0x180021df7  mov     [rsp+1E0h+lpData], rdx; OLECHAR *
0x180021dfc  lea     rdx, [rsp+1E0h+var_170]; int
0x180021e01  mov     [rbp+0E0h+Data], 0
0x180021e0b  mov     qword ptr [rbp+0E0h+var_158], 0
0x180021e13  mov     qword ptr [rsp+1E0h+var_170], 0
0x180021e1c  mov     [rbp+0E0h+arg_28], 0
0x180021e27  mov     qword ptr [rbp+0E0h+var_160], 0
0x180021e2f  mov     [rbp+0E0h+arg_38], 0
0x180021e3a  mov     [rsp+1E0h+var_168], 0
0x180021e43  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180021e48  mov     [rbp+0E0h+Data], eax
0x180021e4e  mov     ebx, eax
0x180021e50  test    eax, eax
0x180021e52  js      loc_180022078
0x180021e58  mov     rcx, [rbp+0E0h+arg_28]
0x180021e5f  lea     rdx, [rbp+0E0h+arg_38]
0x180021e66  mov     rax, [rcx]
0x180021e69  mov     rax, [rax+48h]
0x180021e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e72  mov     [rbp+0E0h+Data], eax
0x180021e78  mov     ebx, eax
0x180021e7a  test    eax, eax
0x180021e7c  js      loc_180022078
0x180021e82  mov     r9d, [rbp+0E0h+arg_20]
0x180021e89  lea     rcx, [rbp+0E0h+arg_38]
0x180021e90  mov     r8d, esi
0x180021e93  mov     edx, r14d
0x180021e96  call    ?AddTimeTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@KKK@Z; AddTimeTaskTriggers(ATL::CComPtr<ITriggerCollection> &,ulong,ulong,ulong)
0x180021e9b  mov     [rbp+0E0h+Data], eax
0x180021ea1  mov     ebx, eax
0x180021ea3  test    eax, eax
0x180021ea5  js      loc_180022078
0x180021eab  mov     rcx, [rbp+0E0h+arg_28]
0x180021eb2  mov     rdx, [rbp+0E0h+arg_38]
0x180021eb9  mov     rax, [rcx]
0x180021ebc  mov     rax, [rax+50h]
0x180021ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ec5  mov     [rbp+0E0h+Data], eax
0x180021ecb  mov     ebx, eax
0x180021ecd  test    eax, eax
0x180021ecf  js      loc_180022078
0x180021ed5  mov     rsi, qword ptr [rsp+1E0h+var_170]
0x180021eda  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x180021ede  mov     r14, [rsi]
0x180021ee1  call    cs:__imp_VariantInit
0x180021ee7  movups  xmm6, xmmword ptr [rbp+0E0h+pvarg]
0x180021eeb  lea     rcx, [rbp+0E0h+var_120]; pvarg
0x180021eef  movsd   xmm7, qword ptr [rbp+0E0h+pvarg+10h]
0x180021ef4  call    cs:__imp_VariantInit
0x180021efa  movups  xmm8, xmmword ptr [rbp+0E0h+var_120]
0x180021eff  mov     rcx, r15; psz
0x180021f02  movsd   xmm9, qword ptr [rbp+0E0h+var_120+10h]
0x180021f08  call    cs:__imp_SysAllocString
0x180021f0e  test    rax, rax
0x180021f11  jz      loc_180022143
0x180021f17  movsd   xmm11, qword ptr [rbp+0E0h+var_148+10h]
0x180021f1d  mov     ecx, 8
0x180021f22  mov     r15, [rbp+0E0h+arg_28]
0x180021f29  mov     word ptr [rbp+0E0h+var_148], cx
0x180021f2d  mov     ecx, 18h; Size
0x180021f32  mov     qword ptr [rbp+0E0h+var_148+8], rax
0x180021f36  movups  xmm10, xmmword ptr [rbp+0E0h+var_148]
0x180021f3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021f40  mov     rcx, rdi; psz
0x180021f43  mov     rbx, rax
0x180021f46  mov     qword ptr [rax+8], 0
0x180021f4e  mov     dword ptr [rax+10h], 1
0x180021f55  call    cs:__imp_SysAllocString
0x180021f5b  mov     [rbx], rax
0x180021f5e  test    rax, rax
0x180021f61  jnz     short loc_180021F6C
0x180021f63  test    rdi, rdi
0x180021f66  jnz     loc_180022143
0x180021f6c  lea     rcx, [rsp+1E0h+var_168]
0x180021f71  mov     [rbp+0E0h+var_150], rbx
0x180021f75  mov     qword ptr [rsp+1E0h+var_1A0], rcx
0x180021f7a  mov     rdx, rax
0x180021f7d  mov     rax, [r14+88h]
0x180021f84  lea     rcx, [rbp+0E0h+var_F0]
0x180021f88  mov     [rsp+1E0h+var_1A8], rcx
0x180021f8d  mov     r9d, 6
0x180021f93  lea     rcx, [rbp+0E0h+var_D0]
0x180021f97  mov     dword ptr [rsp+1E0h+var_1B0], 3
0x180021f9f  mov     qword ptr [rsp+1E0h+cbData], rcx
0x180021fa4  mov     r8, r15
0x180021fa7  lea     rcx, [rbp+0E0h+var_B0]
0x180021fab  movaps  [rbp+0E0h+var_F0], xmm6
0x180021faf  mov     [rsp+1E0h+lpData], rcx
0x180021fb4  mov     rcx, rsi
0x180021fb7  movsd   [rbp+0E0h+var_E0], xmm7
0x180021fbc  movaps  [rbp+0E0h+var_D0], xmm8
0x180021fc1  movsd   [rbp+0E0h+var_C0], xmm9
0x180021fc7  movaps  [rbp+0E0h+var_B0], xmm10
0x180021fcc  movsd   [rbp+0E0h+var_A0], xmm11
0x180021fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fd7  lea     rcx, [rbp+0E0h+var_150]; this
0x180021fdb  mov     [rbp+0E0h+Data], eax
0x180021fe1  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180021fe6  lea     rcx, [rbp+0E0h+var_148]; pvarg
0x180021fea  call    cs:__imp_VariantClear
0x180021ff0  test    eax, eax
0x180021ff2  js      loc_18002214E
0x180021ff8  lea     rcx, [rbp+0E0h+var_120]; pvarg
0x180021ffc  call    cs:__imp_VariantClear
0x180022002  test    eax, eax
0x180022004  js      loc_180022156
0x18002200a  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x18002200e  call    cs:__imp_VariantClear
0x180022014  test    eax, eax
0x180022016  js      loc_18002213B
0x18002201c  mov     ebx, [rbp+0E0h+Data]
0x180022022  test    ebx, ebx
0x180022024  jns     short loc_180022078
0x180022026  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x18002202d  lea     rax, [rbp+0E0h+Data]
0x180022034  mov     r9d, 4; dwType
0x18002203a  lea     r8, a24registertask; "24RegisterTaskDefinition"
0x180022041  mov     [rsp+1E0h+cbData], r9d; cbData
0x180022046  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002204d  mov     [rsp+1E0h+lpData], rax; lpData
0x180022052  call    cs:__imp_RegSetKeyValueW
0x180022058  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18002205d  mov     edx, [rbp+0E0h+Data]; int
0x180022063  lea     r8, aScheduleoneoma_0; "ScheduleOneOmaDmSessionClient"
0x18002206a  mov     rcx, rax; this
0x18002206d  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x180022072  mov     ebx, [rbp+0E0h+Data]
0x180022078  mov     rcx, [rsp+1E0h+var_168]
0x18002207d  test    rcx, rcx
0x180022080  jz      short loc_18002208E
0x180022082  mov     rax, [rcx]
0x180022085  mov     rax, [rax+10h]
0x180022089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002208e  mov     rcx, [rbp+0E0h+arg_38]
0x180022095  test    rcx, rcx
0x180022098  jz      short loc_1800220A6
0x18002209a  mov     rax, [rcx]
0x18002209d  mov     rax, [rax+10h]
0x1800220a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220a6  mov     rcx, qword ptr [rbp+0E0h+var_160]
0x1800220aa  test    rcx, rcx
0x1800220ad  jz      short loc_1800220BB
0x1800220af  mov     rax, [rcx]
0x1800220b2  mov     rax, [rax+10h]
0x1800220b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220bb  mov     rcx, [rbp+0E0h+arg_28]
0x1800220c2  test    rcx, rcx
0x1800220c5  jz      short loc_1800220D3
0x1800220c7  mov     rax, [rcx]
0x1800220ca  mov     rax, [rax+10h]
0x1800220ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220d3  mov     rcx, qword ptr [rsp+1E0h+var_170]
0x1800220d8  test    rcx, rcx
0x1800220db  jz      short loc_1800220E9
0x1800220dd  mov     rax, [rcx]
0x1800220e0  mov     rax, [rax+10h]
0x1800220e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220e9  mov     rcx, qword ptr [rbp+0E0h+var_158]
0x1800220ed  test    rcx, rcx
0x1800220f0  jz      short loc_1800220FE
0x1800220f2  mov     rdx, [rcx]
0x1800220f5  mov     rax, [rdx+10h]
0x1800220f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220fe  lea     rcx, [rbp+0E0h+var_130]; this
0x180022102  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180022107  lea     r11, [rsp+1E0h+var_28]
0x18002210f  mov     eax, ebx
0x180022111  movaps  xmm6, xmmword ptr [r11-18h]
0x180022116  movaps  xmm7, xmmword ptr [r11-28h]
0x18002211b  movaps  xmm8, xmmword ptr [r11-38h]
0x180022120  movaps  xmm9, xmmword ptr [r11-48h]
0x180022125  movaps  xmm10, xmmword ptr [r11-58h]
0x18002212a  movaps  xmm11, xmmword ptr [r11-68h]
0x18002212f  mov     rsp, r11
0x180022132  pop     r15
0x180022134  pop     r14
0x180022136  pop     rdi
0x180022137  pop     rsi
0x180022138  pop     rbx
0x180022139  pop     rbp
0x18002213a  retn
0x18002213b  mov     ecx, eax; int
0x18002213d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180022143  mov     ecx, 8007000Eh; int
0x180022148  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002214e  mov     ecx, eax; int
0x180022150  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180022156  mov     ecx, eax; int
0x180022158  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
