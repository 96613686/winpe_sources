# AnalyzeTraces(SleepStudyReportData &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,TraceFileType)

- ea: `0x180041544`
- end: `0x180041776`
- name: `?AnalyzeTraces@@YAJAEAUSleepStudyReportData@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@W4TraceFileType@@@Z`
- size: `562`
- prototype: `__int64 __fastcall(struct SleepStudyReportData *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041060`
- `0x1800778f0`

## callees

- `0x180004e20`
- `0x1800363ec`
- `0x180036b8c`
- `0x180041544`
- `0x18004177c`
- `0x180041860`
- `0x18004ca90`
- `0x18004d8fc`
- `0x180066f28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800416d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800416d3`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18004170b`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18004170b`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x1800416c2`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x1800416c2`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18004171a`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18004171a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AnalyzeTraces(struct _FILETIME *a1, __int64 *a2, int a3)
{
  Troubleshooter *v6; // r14
  struct _FILETIME v7; // rdx
  struct _FILETIME v8; // rcx
  struct _FILETIME v9; // rax
  unsigned int v10; // edi
  __int64 i; // rbx
  WCHAR *v12; // rsi
  signed int LastError; // eax
  struct _FILETIME *p_EndTime; // r9
  struct _FILETIME *p_StartTime; // r8
  ULONG64 HandleArray; // [rsp+20h] [rbp-E0h] BYREF
  struct _FILETIME EndTime; // [rsp+28h] [rbp-D8h] BYREF
  struct _FILETIME StartTime; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[80]; // [rsp+40h] [rbp-C0h] BYREF
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v22[5]; // [rsp+250h] [rbp+150h] BYREF
  _QWORD v23[5]; // [rsp+278h] [rbp+178h] BYREF
  int v24; // [rsp+2A0h] [rbp+1A0h]
  GUID v25; // [rsp+2A4h] [rbp+1A4h]

  EndTime = 0;
  memset_0(&Logfile, 0, sizeof(Logfile));
  StartTime = 0;
  HandleArray = 0;
  ScreenOnTroubleshooter::ScreenOnTroubleshooter((ScreenOnTroubleshooter *)v20, (struct SleepStudyReportData *)a1);
  v22[2] = qword_18009F1D8;
  v22[0] = &SleepStudyTroubleshooter::`vftable';
  v22[3] = a1;
  v22[4] = 0;
  std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(v23);
  v23[3] = 0;
  v23[4] = 0;
  v24 = 0;
  v25 = GUID_NULL;
  v6 = (Troubleshooter *)v22;
  if ( a3 == 2 )
    v6 = (Troubleshooter *)v20;
  Troubleshooter::InitializeAnalysis(v6);
  v7 = a1[40];
  if ( v7 )
  {
    v8 = a1[39];
    v9 = (struct _FILETIME)(*(_QWORD *)&v8 - *(_QWORD *)&v7);
  }
  else
  {
    v9 = 0;
    v8 = (struct _FILETIME)0x7FFFFFFFFFFFFFFFLL;
  }
  EndTime = v8;
  StartTime = v9;
  v10 = 0;
  for ( i = *a2; i != a2[1]; i += 32 )
  {
    if ( *(_QWORD *)(i + 24) <= 7u )
      v12 = (WCHAR *)i;
    else
      v12 = *(WCHAR **)i;
    memset_0(&Logfile, 0, sizeof(Logfile));
    Logfile.LogFileName = v12;
    Logfile.LogFileMode = 0x10000000;
    Logfile.EventCallback = (PEVENT_CALLBACK)ProcessTroubleshooterTraceCallback;
    Logfile.Context = v6;
    HandleArray = OpenTraceW(&Logfile);
    if ( HandleArray == -1
      || (a3 ? (p_EndTime = &EndTime, p_StartTime = &StartTime) : (p_EndTime = 0, p_StartTime = 0),
          ProcessTrace(&HandleArray, 1u, p_StartTime, p_EndTime)) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      CloseTrace(HandleArray);
    }
  }
  Troubleshooter::CompleteAnalysis(v6);
  SleepStudyTroubleshooter::~SleepStudyTroubleshooter((SleepStudyTroubleshooter *)v22);
  ScreenOnTroubleshooter::~ScreenOnTroubleshooter((ScreenOnTroubleshooter *)v20);
  return v10;
}

```

## disassembly

```asm
0x180041544  mov     [rsp-8+arg_8], rbx
0x180041549  mov     [rsp-8+arg_10], rsi
0x18004154e  push    rbp
0x18004154f  push    rdi
0x180041550  push    r12
0x180041552  push    r14
0x180041554  push    r15
0x180041556  lea     rbp, [rsp-1D0h]
0x18004155e  sub     rsp, 2D0h
0x180041565  mov     rax, cs:__security_cookie
0x18004156c  xor     rax, rsp
0x18004156f  mov     [rbp+1F0h+var_30], rax
0x180041576  mov     r12d, r8d
0x180041579  mov     r15, rdx
0x18004157c  mov     rbx, rcx
0x18004157f  mov     qword ptr [rsp+2F0h+EndTime.dwLowDateTime], 0
0x180041588  xor     edx, edx; Val
0x18004158a  mov     r8d, 1C0h; Size
0x180041590  lea     rcx, [rbp+1F0h+Logfile]; void *
0x180041594  call    memset_0
0x180041599  mov     qword ptr [rsp+2F0h+StartTime.dwLowDateTime], 0
0x1800415a2  mov     [rsp+2F0h+HandleArray], 0
0x1800415ab  mov     rdx, rbx; struct SleepStudyReportData *
0x1800415ae  lea     rcx, [rsp+2F0h+var_2B0]; this
0x1800415b3  call    ??0ScreenOnTroubleshooter@@QEAA@PEAUSleepStudyReportData@@@Z; ScreenOnTroubleshooter::ScreenOnTroubleshooter(SleepStudyReportData *)
0x1800415b8  nop
0x1800415b9  lea     rax, qword_18009F1D8
0x1800415c0  mov     [rbp+1F0h+var_90], rax
0x1800415c7  lea     rax, ??_7SleepStudyTroubleshooter@@6B@; const SleepStudyTroubleshooter::`vftable'
0x1800415ce  mov     [rbp+1F0h+var_A0], rax
0x1800415d5  mov     [rbp+1F0h+var_88], rbx
0x1800415dc  mov     [rbp+1F0h+var_80], 0
0x1800415e7  lea     rcx, [rbp+1F0h+var_78]; void *
0x1800415ee  call    ??0?$vector@VServicePowerRequest@@V?$allocator@VServicePowerRequest@@@std@@@std@@QEAA@XZ; std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(void)
0x1800415f3  mov     [rbp+1F0h+var_60], 0
0x1800415fe  mov     [rbp+1F0h+var_58], 0
0x180041609  mov     [rbp+1F0h+var_50], 0
0x180041613  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004161a  movdqu  [rbp+1F0h+var_4C], xmm0
0x180041622  lea     r14, [rbp+1F0h+var_A0]
0x180041629  lea     rax, [rsp+2F0h+var_2B0]
0x18004162e  cmp     r12d, 2
0x180041632  cmovz   r14, rax
0x180041636  mov     rcx, r14; this
0x180041639  call    ?InitializeAnalysis@Troubleshooter@@QEAAXXZ; Troubleshooter::InitializeAnalysis(void)
0x18004163e  mov     rdx, [rbx+140h]
0x180041645  test    rdx, rdx
0x180041648  jz      short loc_180041659
0x18004164a  mov     rcx, [rbx+138h]
0x180041651  mov     rax, rcx
0x180041654  sub     rax, rdx
0x180041657  jmp     short loc_180041665
0x180041659  xor     eax, eax
0x18004165b  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180041665  mov     qword ptr [rsp+2F0h+EndTime.dwLowDateTime], rcx
0x18004166a  mov     qword ptr [rsp+2F0h+StartTime.dwLowDateTime], rax
0x18004166f  xor     edi, edi
0x180041671  mov     rbx, [r15]
0x180041674  cmp     rbx, [r15+8]
0x180041678  jz      loc_180041729
0x18004167e  cmp     qword ptr [rbx+18h], 7
0x180041683  jbe     short loc_18004168A
0x180041685  mov     rsi, [rbx]
0x180041688  jmp     short loc_18004168D
0x18004168a  mov     rsi, rbx
0x18004168d  xor     edx, edx; Val
0x18004168f  mov     r8d, 1C0h; Size
0x180041695  lea     rcx, [rbp+1F0h+Logfile]; void *
0x180041699  call    memset_0
0x18004169e  mov     [rbp+1F0h+Logfile.LogFileName], rsi
0x1800416a2  mov     dword ptr [rbp+1F0h+Logfile.1Ch], 10000000h
0x1800416a9  lea     rax, ?ProcessTroubleshooterTraceCallback@@YAXPEAU_EVENT_RECORD@@@Z; ProcessTroubleshooterTraceCallback(_EVENT_RECORD *)
0x1800416b0  mov     qword ptr [rbp+1F0h+Logfile.1A8h], rax
0x1800416b7  mov     [rbp+1F0h+Logfile.Context], r14
0x1800416be  lea     rcx, [rbp+1F0h+Logfile]; Logfile
0x1800416c2  call    cs:__imp_OpenTraceW
0x1800416c8  mov     [rsp+2F0h+HandleArray], rax
0x1800416cd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800416d1  jnz     short loc_1800416EA
0x1800416d3  call    cs:__imp_GetLastError
0x1800416d9  mov     edi, eax
0x1800416db  test    eax, eax
0x1800416dd  jle     short loc_180041720
0x1800416df  movzx   edi, ax
0x1800416e2  or      edi, 80070000h
0x1800416e8  jmp     short loc_180041720
0x1800416ea  mov     edx, 1; HandleCount
0x1800416ef  lea     rcx, [rsp+2F0h+HandleArray]; HandleArray
0x1800416f4  test    r12d, r12d
0x1800416f7  jnz     short loc_180041701
0x1800416f9  xor     r9d, r9d
0x1800416fc  xor     r8d, r8d
0x1800416ff  jmp     short loc_18004170B
0x180041701  lea     r9, [rsp+2F0h+EndTime]; EndTime
0x180041706  lea     r8, [rsp+2F0h+StartTime]; StartTime
0x18004170b  call    cs:__imp_ProcessTrace
0x180041711  test    eax, eax
0x180041713  jnz     short loc_1800416D3
0x180041715  mov     rcx, [rsp+2F0h+HandleArray]; TraceHandle
0x18004171a  call    cs:__imp_CloseTrace
0x180041720  add     rbx, 20h ; ' '
0x180041724  jmp     loc_180041674
0x180041729  mov     rcx, r14; this
0x18004172c  call    ?CompleteAnalysis@Troubleshooter@@QEAAXXZ; Troubleshooter::CompleteAnalysis(void)
0x180041731  nop
0x180041732  lea     rcx, [rbp+1F0h+var_A0]; this
0x180041739  call    ??1SleepStudyTroubleshooter@@UEAA@XZ; SleepStudyTroubleshooter::~SleepStudyTroubleshooter(void)
0x18004173e  nop
0x18004173f  lea     rcx, [rsp+2F0h+var_2B0]; this
0x180041744  call    ??1ScreenOnTroubleshooter@@UEAA@XZ; ScreenOnTroubleshooter::~ScreenOnTroubleshooter(void)
0x180041749  mov     eax, edi
0x18004174b  mov     rcx, [rbp+1F0h+var_30]
0x180041752  xor     rcx, rsp; StackCookie
0x180041755  call    __security_check_cookie
0x18004175a  lea     r11, [rsp+2F0h+var_20]
0x180041762  mov     rbx, [r11+38h]
0x180041766  mov     rsi, [r11+40h]
0x18004176a  mov     rsp, r11
0x18004176d  pop     r15
0x18004176f  pop     r14
0x180041771  pop     r12
0x180041773  pop     rdi
0x180041774  pop     rbp
0x180041775  retn
```
