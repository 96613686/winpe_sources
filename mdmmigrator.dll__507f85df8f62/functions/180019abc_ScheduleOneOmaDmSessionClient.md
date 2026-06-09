# ScheduleOneOmaDmSessionClient

- ea: `0x180019abc`
- end: `0x180019e50`
- name: `ScheduleOneOmaDmSessionClient`
- size: `916`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, unsigned int, __int64, unsigned __int16 *, __int64, int Data, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019904`

## callees

- `0x18000aa2c`
- `0x18000aab8`
- `0x18000ab84`
- `0x1800117c8`
- `0x180011d5c`
- `0x180012664`
- `0x180012ed4`
- `0x180019abc`
- `0x18001dce8`
- `0x18001e264`
- `0x180020010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180019c8d`
- `OLEAUT32!__imp_SysAllocString` at `0x180019c8d`
- `OLEAUT32!__imp_VariantInit` at `0x180019c5b`
- `OLEAUT32!__imp_VariantInit` at `0x180019c70`
- `OLEAUT32!__imp_VariantInit` at `0x180019c5b`
- `OLEAUT32!__imp_VariantInit` at `0x180019c70`
- `OLEAUT32!__imp_VariantClear` at `0x180019d45`
- `OLEAUT32!__imp_VariantClear` at `0x180019d4f`
- `OLEAUT32!__imp_VariantClear` at `0x180019d59`
- `OLEAUT32!__imp_VariantClear` at `0x180019d45`
- `OLEAUT32!__imp_VariantClear` at `0x180019d4f`
- `OLEAUT32!__imp_VariantClear` at `0x180019d59`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180019d95`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180019d95`

## string_xrefs

- `0x180019d80`: `24RegisterTaskDefinition`
- `0x180019b99`: `%windir%\system32\deviceenroller.exe `

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
  int v14; // ebx
  __int64 *v15; // rdi
  __int64 v16; // rbx
  __int128 v17; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v19; // xmm10
  IRecordInfo *v20; // xmm11_8
  __int64 (__fastcall *v21)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rsi
  __int128 v22; // xmm6
  IRecordInfo *v23; // xmm7_8
  __int64 v24; // rbx
  _bstr_t *v25; // rax
  __int64 v26; // rdx
  const struct std::nothrow_t *v27; // rdx
  CEnrollmentLogger *Logger; // rax
  int v30[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v31; // [rsp+80h] [rbp-88h] BYREF
  int v32[2]; // [rsp+88h] [rbp-80h] BYREF
  int v33[2]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v34[8]; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG v35; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v36[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v37; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v39; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v40; // [rsp+108h] [rbp+0h]
  __int128 v41; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v42; // [rsp+128h] [rbp+20h]
  __int128 v43; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v44; // [rsp+148h] [rbp+40h]

  Data = 0;
  v36[0] = "ScheduleOneOmaDmSessionClient";
  v36[1] = &Data;
  *(_QWORD *)v33 = 0;
  *(_QWORD *)v30 = 0;
  a6 = 0;
  *(_QWORD *)v32 = 0;
  a8 = 0;
  v31 = 0;
  v14 = CreateTask(
          v33,
          (__int64 *)v30,
          &a6,
          v32,
          a2,
          L"%windir%\\system32\\deviceenroller.exe ",
          a7,
          L"S-1-5-18",
          0,
          a11,
          1,
          1,
          0);
  Data = v14;
  if ( v14 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a6 + 72LL))(a6, &a8);
    Data = v14;
    if ( v14 >= 0 )
    {
      v14 = AddTimeTaskTriggers(&a8, a3, a4, a5);
      Data = v14;
      if ( v14 >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a6 + 80LL))(a6, a8);
        Data = v14;
        if ( v14 >= 0 )
        {
          v15 = *(__int64 **)v30;
          v16 = **(_QWORD **)v30;
          VariantInit(&pvarg);
          v17 = *(_OWORD *)&pvarg.vt;
          pRecInfo = pvarg.pRecInfo;
          VariantInit(&v37);
          v19 = *(_OWORD *)&v37.vt;
          v20 = v37.pRecInfo;
          v35.vt = 8;
          v35.llVal = (LONGLONG)SysAllocString(L"S-1-5-18");
          if ( !v35.llVal )
            _com_issue_error(-2147024882);
          v21 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v16 + 136);
          v22 = *(_OWORD *)&v35.vt;
          v23 = v35.pRecInfo;
          v24 = a6;
          v25 = _bstr_t::_bstr_t((_bstr_t *)v34, a1);
          if ( *(_QWORD *)v25 )
            v26 = **(_QWORD **)v25;
          else
            v26 = 0;
          v39 = v17;
          v40 = pRecInfo;
          v41 = v19;
          v42 = v20;
          v43 = v22;
          v44 = v23;
          Data = v21(v15, v26, v24, 6, &v43, &v41, 3, &v39, &v31);
          _bstr_t::~_bstr_t((_bstr_t *)v34, v27);
          VariantClear(&v35);
          VariantClear(&v37);
          VariantClear(&pvarg);
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
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v31);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&a8);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v32);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&a6);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v30);
  if ( *(_QWORD *)v33 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33 + 16LL))(*(_QWORD *)v33);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v36);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180019abc  mov     rax, rsp
0x180019abf  push    rbp
0x180019ac0  push    rbx
0x180019ac1  push    rsi
0x180019ac2  push    rdi
0x180019ac3  push    r12
0x180019ac5  push    r13
0x180019ac7  push    r14
0x180019ac9  lea     rbp, [rax-0E8h]
0x180019ad0  sub     rsp, 1B0h
0x180019ad7  movaps  xmmword ptr [rax-48h], xmm6
0x180019adb  movaps  xmmword ptr [rax-58h], xmm7
0x180019adf  movaps  xmmword ptr [rax-68h], xmm8
0x180019ae4  movaps  xmmword ptr [rax-78h], xmm9
0x180019ae9  movaps  xmmword ptr [rax-88h], xmm10
0x180019af1  movaps  xmmword ptr [rax-98h], xmm11
0x180019af9  mov     edi, r9d
0x180019afc  mov     esi, r8d
0x180019aff  mov     r14, rcx
0x180019b02  mov     [rbp+0E0h+Data], 0
0x180019b0c  lea     r13, aScheduleoneoma_0; "ScheduleOneOmaDmSessionClient"
0x180019b13  mov     [rbp+0E0h+var_130], r13
0x180019b17  lea     rax, [rbp+0E0h+Data]
0x180019b1e  mov     [rbp+0E0h+var_128], rax
0x180019b22  mov     qword ptr [rbp+0E0h+var_158], 0
0x180019b2a  mov     qword ptr [rsp+1E0h+var_170], 0
0x180019b33  mov     [rbp+0E0h+arg_28], 0
0x180019b3e  mov     qword ptr [rbp+0E0h+var_160], 0
0x180019b46  mov     [rbp+0E0h+arg_38], 0
0x180019b51  mov     [rsp+1E0h+var_168], 0
0x180019b5a  mov     [rsp+1E0h+var_180], 0; int
0x180019b62  mov     eax, 1
0x180019b67  mov     [rsp+1E0h+var_188], eax; int
0x180019b6b  mov     [rsp+1E0h+var_190], eax; int
0x180019b6f  mov     eax, [rbp+0E0h+arg_50]
0x180019b75  mov     [rsp+1E0h+var_198], eax; int
0x180019b79  mov     [rsp+1E0h+var_1A0], 0; int
0x180019b81  lea     r12, psz; "S-1-5-18"
0x180019b88  mov     [rsp+1E0h+var_1A8], r12; unsigned __int16 *
0x180019b8d  mov     rax, [rbp+0E0h+arg_30]
0x180019b94  mov     [rsp+1E0h+var_1B0], rax; unsigned __int16 *
0x180019b99  lea     rax, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe "
0x180019ba0  mov     qword ptr [rsp+1E0h+cbData], rax; unsigned __int16 *
0x180019ba5  mov     [rsp+1E0h+lpData], rdx; unsigned __int16 *
0x180019baa  lea     r9, [rbp+0E0h+var_160]; int
0x180019bae  lea     r8, [rbp+0E0h+arg_28]; int
0x180019bb5  lea     rdx, [rsp+1E0h+var_170]; int
0x180019bba  lea     rcx, [rbp+0E0h+var_158]; int
0x180019bbe  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180019bc3  mov     ebx, eax
0x180019bc5  mov     [rbp+0E0h+Data], eax
0x180019bcb  test    eax, eax
0x180019bcd  js      loc_180019DB7
0x180019bd3  mov     rcx, [rbp+0E0h+arg_28]
0x180019bda  mov     rax, [rcx]
0x180019bdd  lea     rdx, [rbp+0E0h+arg_38]
0x180019be4  mov     rax, [rax+48h]
0x180019be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bed  mov     ebx, eax
0x180019bef  mov     [rbp+0E0h+Data], eax
0x180019bf5  test    eax, eax
0x180019bf7  js      loc_180019DB7
0x180019bfd  mov     r9d, [rbp+0E0h+arg_20]
0x180019c04  mov     r8d, edi
0x180019c07  mov     edx, esi
0x180019c09  lea     rcx, [rbp+0E0h+arg_38]
0x180019c10  call    ?AddTimeTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@KKK@Z; AddTimeTaskTriggers(ATL::CComPtr<ITriggerCollection> &,ulong,ulong,ulong)
0x180019c15  mov     ebx, eax
0x180019c17  mov     [rbp+0E0h+Data], eax
0x180019c1d  test    eax, eax
0x180019c1f  js      loc_180019DB7
0x180019c25  mov     rcx, [rbp+0E0h+arg_28]
0x180019c2c  mov     rax, [rcx]
0x180019c2f  mov     rdx, [rbp+0E0h+arg_38]
0x180019c36  mov     rax, [rax+50h]
0x180019c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c3f  mov     ebx, eax
0x180019c41  mov     [rbp+0E0h+Data], eax
0x180019c47  test    eax, eax
0x180019c49  js      loc_180019DB7
0x180019c4f  mov     rdi, qword ptr [rsp+1E0h+var_170]
0x180019c54  mov     rbx, [rdi]
0x180019c57  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x180019c5b  call    cs:__imp_VariantInit
0x180019c61  movups  xmm8, xmmword ptr [rbp+0E0h+pvarg]
0x180019c66  movsd   xmm9, qword ptr [rbp+0E0h+pvarg+10h]
0x180019c6c  lea     rcx, [rbp+0E0h+var_120]; pvarg
0x180019c70  call    cs:__imp_VariantInit
0x180019c76  movups  xmm10, xmmword ptr [rbp+0E0h+var_120]
0x180019c7b  movsd   xmm11, qword ptr [rbp+0E0h+var_120+10h]
0x180019c81  mov     eax, 8
0x180019c86  mov     word ptr [rbp+0E0h+var_148], ax
0x180019c8a  mov     rcx, r12; psz
0x180019c8d  call    cs:__imp_SysAllocString
0x180019c93  mov     qword ptr [rbp+0E0h+var_148+8], rax
0x180019c97  test    rax, rax
0x180019c9a  jz      loc_180019E45
0x180019ca0  mov     rsi, [rbx+88h]
0x180019ca7  movups  xmm6, xmmword ptr [rbp+0E0h+var_148]
0x180019cab  movsd   xmm7, qword ptr [rbp+0E0h+var_148+10h]
0x180019cb0  mov     rbx, [rbp+0E0h+arg_28]
0x180019cb7  mov     rdx, r14; unsigned __int16 *
0x180019cba  lea     rcx, [rbp+0E0h+var_150]; this
0x180019cbe  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180019cc3  mov     rcx, [rax]
0x180019cc6  test    rcx, rcx
0x180019cc9  jz      short loc_180019CD0
0x180019ccb  mov     rdx, [rcx]
0x180019cce  jmp     short loc_180019CD2
0x180019cd0  xor     edx, edx
0x180019cd2  movaps  [rbp+0E0h+var_F0], xmm8
0x180019cd7  movsd   [rbp+0E0h+var_E0], xmm9
0x180019cdd  movaps  [rbp+0E0h+var_D0], xmm10
0x180019ce2  movsd   [rbp+0E0h+var_C0], xmm11
0x180019ce8  movaps  [rbp+0E0h+var_B0], xmm6
0x180019cec  movsd   [rbp+0E0h+var_A0], xmm7
0x180019cf1  lea     rax, [rsp+1E0h+var_168]
0x180019cf6  mov     qword ptr [rsp+1E0h+var_1A0], rax
0x180019cfb  lea     rax, [rbp+0E0h+var_F0]
0x180019cff  mov     [rsp+1E0h+var_1A8], rax
0x180019d04  mov     dword ptr [rsp+1E0h+var_1B0], 3
0x180019d0c  lea     rax, [rbp+0E0h+var_D0]
0x180019d10  mov     qword ptr [rsp+1E0h+cbData], rax
0x180019d15  lea     rax, [rbp+0E0h+var_B0]
0x180019d19  mov     [rsp+1E0h+lpData], rax
0x180019d1e  mov     r9d, 6
0x180019d24  mov     r8, rbx
0x180019d27  mov     rcx, rdi
0x180019d2a  mov     rax, rsi
0x180019d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d32  mov     [rbp+0E0h+Data], eax
0x180019d38  lea     rcx, [rbp+0E0h+var_150]; this
0x180019d3c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180019d41  lea     rcx, [rbp+0E0h+var_148]; pvarg
0x180019d45  call    cs:__imp_VariantClear
0x180019d4b  lea     rcx, [rbp+0E0h+var_120]; pvarg
0x180019d4f  call    cs:__imp_VariantClear
0x180019d55  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x180019d59  call    cs:__imp_VariantClear
0x180019d5f  mov     ebx, [rbp+0E0h+Data]
0x180019d65  test    ebx, ebx
0x180019d67  jns     short loc_180019DB7
0x180019d69  mov     r9d, 4; dwType
0x180019d6f  mov     [rsp+1E0h+cbData], r9d; cbData
0x180019d74  lea     rax, [rbp+0E0h+Data]
0x180019d7b  mov     [rsp+1E0h+lpData], rax; lpData
0x180019d80  lea     r8, a24registertask; "24RegisterTaskDefinition"
0x180019d87  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x180019d8e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019d95  call    cs:__imp_RegSetKeyValueW
0x180019d9b  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180019da0  mov     r8, r13; char *
0x180019da3  mov     edx, [rbp+0E0h+Data]; int
0x180019da9  mov     rcx, rax; this
0x180019dac  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x180019db1  mov     ebx, [rbp+0E0h+Data]
0x180019db7  lea     rcx, [rsp+1E0h+var_168]
0x180019dbc  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019dc1  nop
0x180019dc2  lea     rcx, [rbp+0E0h+arg_38]
0x180019dc9  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019dce  nop
0x180019dcf  lea     rcx, [rbp+0E0h+var_160]
0x180019dd3  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019dd8  nop
0x180019dd9  lea     rcx, [rbp+0E0h+arg_28]
0x180019de0  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019de5  nop
0x180019de6  lea     rcx, [rsp+1E0h+var_170]
0x180019deb  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180019df0  nop
0x180019df1  mov     rcx, qword ptr [rbp+0E0h+var_158]
0x180019df5  test    rcx, rcx
0x180019df8  jz      short loc_180019E06
0x180019dfa  mov     rdx, [rcx]
0x180019dfd  mov     rax, [rdx+10h]
0x180019e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e06  lea     rcx, [rbp+0E0h+var_130]; this
0x180019e0a  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180019e0f  mov     eax, ebx
0x180019e11  lea     r11, [rsp+1E0h+var_30]
0x180019e19  movaps  xmm6, xmmword ptr [r11-10h]
0x180019e1e  movaps  xmm7, xmmword ptr [r11-20h]
0x180019e23  movaps  xmm8, xmmword ptr [r11-30h]
0x180019e28  movaps  xmm9, xmmword ptr [r11-40h]
0x180019e2d  movaps  xmm10, xmmword ptr [r11-50h]
0x180019e32  movaps  xmm11, xmmword ptr [r11-60h]
0x180019e37  mov     rsp, r11
0x180019e3a  pop     r14
0x180019e3c  pop     r13
0x180019e3e  pop     r12
0x180019e40  pop     rdi
0x180019e41  pop     rsi
0x180019e42  pop     rbx
0x180019e43  pop     rbp
0x180019e44  retn
0x180019e45  mov     ecx, 8007000Eh; int
0x180019e4a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
