# EnergyWizardImpl::Analyze(ushort const *,ushort const *)

- ea: `0x18005e4d4`
- end: `0x18005e76a`
- name: `?Analyze@EnergyWizardImpl@@QEAAJPEBG0@Z`
- size: `662`
- prototype: `__int64 __fastcall(EnergyWizardImpl *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005e110`

## callees

- `0x180008740`
- `0x180023560`
- `0x1800363ec`
- `0x180036b8c`
- `0x18004ca90`
- `0x18004d8fc`
- `0x18005e4d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e593`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18005e67e`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18005e67e`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18005e582`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18005e618`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18005e582`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18005e618`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18005e70f`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18005e720`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18005e70f`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18005e720`
- `api-ms-win-eventing-tdh-l1-1-0!TdhUnloadManifest` at `0x18005e741`
- `api-ms-win-eventing-tdh-l1-1-0!TdhUnloadManifest` at `0x18005e741`

## pseudocode

```c
__int64 __fastcall EnergyWizardImpl::Analyze(EnergyWizardImpl *this, WCHAR *a2, WCHAR *a3)
{
  EnergyWizardImpl *v5; // rsi
  Troubleshooter **v6; // rbx
  signed int v7; // edi
  signed int LastError; // eax
  ULONG v9; // edx
  Troubleshooter **v10; // rbx
  _QWORD *v11; // rbx
  WCHAR *v12; // rcx
  ULONG64 HandleArray[2]; // [rsp+30h] [rbp-208h] BYREF
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+40h] [rbp-1F8h] BYREF

  v5 = this;
  memset_0(&Logfile, 0, sizeof(Logfile));
  *(__m128i *)HandleArray = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v6 = *(Troubleshooter ***)v5;
  if ( *((_QWORD *)v5 + 1) == *(_QWORD *)v5 )
  {
    v7 = -2147467259;
    goto LABEL_28;
  }
  *((_DWORD *)v5 + 28) = 0;
  while ( v6 != *((Troubleshooter ***)v5 + 1) )
  {
    try
    {
      if ( !*v6 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      Troubleshooter::ValidateSelf(*v6);
      Troubleshooter::InitializeAnalysis(*v6++);
    }
    catch ( std::bad_alloc )
    {
      v5 = this;
      v7 = -2147024882;
      goto LABEL_28;
    }
    catch ( ... )
    {
      v5 = this;
      v7 = -2147467259;
      goto LABEL_28;
    }
  }
  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.LogFileName = a2;
  Logfile.EventCallback = (PEVENT_CALLBACK)EventRecordCallback;
  Logfile.LogFileMode = 0x10000000;
  Logfile.Context = v5;
  HandleArray[0] = OpenTraceW(&Logfile);
  if ( HandleArray[0] == -1 )
    goto LABEL_6;
  v9 = 1;
  *((_DWORD *)v5 + 26) += Logfile.LogfileHeader.EventsLost;
  *((_DWORD *)v5 + 27) += Logfile.LogfileHeader.BuffersLost;
  *((_QWORD *)v5 + 9) = Logfile.LogfileHeader.StartTime.QuadPart;
  *((_QWORD *)v5 + 10) = Logfile.LogfileHeader.EndTime.QuadPart;
  if ( a3 )
  {
    memset_0(&Logfile, 0, sizeof(Logfile));
    Logfile.LogFileName = a3;
    Logfile.EventCallback = (PEVENT_CALLBACK)EventRecordCallback;
    Logfile.LogFileMode = 0x10000000;
    Logfile.Context = v5;
    HandleArray[1] = OpenTraceW(&Logfile);
    if ( HandleArray[1] == -1 )
    {
LABEL_6:
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError <= 0 )
        goto LABEL_28;
      v7 = (unsigned __int16)LastError;
      goto LABEL_8;
    }
    *((_DWORD *)v5 + 26) += Logfile.LogfileHeader.EventsLost;
    *((_DWORD *)v5 + 27) += Logfile.LogfileHeader.BuffersLost;
    if ( *((_QWORD *)v5 + 9) > Logfile.LogfileHeader.StartTime.QuadPart
      || (v9 = 2, *((_QWORD *)v5 + 10) < Logfile.LogfileHeader.EndTime.QuadPart) )
    {
      v7 = -2147024809;
      goto LABEL_28;
    }
  }
  *((_DWORD *)v5 + 22) = 0;
  v7 = ProcessTrace(HandleArray, v9, 0, 0);
  if ( !v7 )
  {
    if ( !*((_DWORD *)v5 + 22) )
    {
      v10 = *(Troubleshooter ***)v5;
      while ( v10 != *((Troubleshooter ***)v5 + 1) )
      {
        try
        {
          if ( !*v10 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          Troubleshooter::ValidateSelf(*v10);
          Troubleshooter::CompleteAnalysis(*v10++);
        }
        catch ( std::bad_alloc )
        {
          v5 = this;
          v7 = -2147024882;
          goto LABEL_28;
        }
        catch ( ... )
        {
          v5 = this;
          v7 = -2147467259;
          goto LABEL_28;
        }
      }
      *((_DWORD *)v5 + 28) = 1;
      goto LABEL_28;
    }
    v7 = *((_DWORD *)v5 + 22);
  }
  if ( v7 > 0 )
  {
    v7 = (unsigned __int16)v7;
LABEL_8:
    v7 |= 0x80070000;
  }
LABEL_28:
  if ( HandleArray[0] != -1 )
    CloseTrace(HandleArray[0]);
  if ( HandleArray[1] != -1 )
    CloseTrace(HandleArray[1]);
  v11 = (_QWORD *)*((_QWORD *)v5 + 15);
  while ( 1 )
  {
    v11 = (_QWORD *)*v11;
    if ( v11 == *((_QWORD **)v5 + 15) )
      break;
    v12 = (WCHAR *)(v11 + 2);
    if ( v11[5] > 7u )
      v12 = *(WCHAR **)v12;
    TdhUnloadManifest(v12);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005e4d4  push    rbx
0x18005e4d6  push    rsi
0x18005e4d7  push    rdi
0x18005e4d8  push    r13
0x18005e4da  push    r14
0x18005e4dc  sub     rsp, 210h
0x18005e4e3  mov     rax, cs:__security_cookie
0x18005e4ea  xor     rax, rsp
0x18005e4ed  mov     [rsp+238h+var_38], rax
0x18005e4f5  mov     r14, r8
0x18005e4f8  mov     rdi, rdx
0x18005e4fb  mov     rsi, rcx
0x18005e4fe  mov     [rsp+238h+var_210], rcx
0x18005e503  mov     r13d, 1C0h
0x18005e509  mov     r8d, r13d; Size
0x18005e50c  xor     edx, edx; Val
0x18005e50e  lea     rcx, [rsp+238h+Logfile]; void *
0x18005e513  call    memset_0
0x18005e518  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18005e520  movups  xmmword ptr [rsp+238h+HandleArray], xmm0
0x18005e525  mov     rbx, [rsi]
0x18005e528  cmp     [rsi+8], rbx
0x18005e52c  jnz     short loc_18005E538
0x18005e52e  mov     edi, 80004005h
0x18005e533  jmp     loc_18005E704
0x18005e538  mov     dword ptr [rsi+70h], 0
0x18005e53f  cmp     rbx, [rsi+8]
0x18005e543  jnz     loc_18005E6D5
0x18005e549  mov     r8, r13; Size
0x18005e54c  xor     edx, edx; Val
0x18005e54e  lea     rcx, [rsp+238h+Logfile]; void *
0x18005e553  call    memset_0
0x18005e558  mov     [rsp+238h+Logfile.LogFileName], rdi
0x18005e55d  lea     rbx, ?EventRecordCallback@@YAXPEAU_EVENT_RECORD@@@Z; EventRecordCallback(_EVENT_RECORD *)
0x18005e564  mov     qword ptr [rsp+238h+Logfile.1A8h], rbx
0x18005e56c  mov     edi, 10000000h
0x18005e571  mov     dword ptr [rsp+238h+Logfile.1Ch], edi
0x18005e575  mov     [rsp+238h+Logfile.Context], rsi
0x18005e57d  lea     rcx, [rsp+238h+Logfile]; Logfile
0x18005e582  call    cs:__imp_OpenTraceW
0x18005e588  mov     [rsp+238h+HandleArray], rax
0x18005e58d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005e591  jnz     short loc_18005E5B1
0x18005e593  call    cs:__imp_GetLastError
0x18005e599  mov     edi, eax
0x18005e59b  test    eax, eax
0x18005e59d  jle     loc_18005E704
0x18005e5a3  movzx   edi, ax
0x18005e5a6  or      edi, 80070000h
0x18005e5ac  jmp     loc_18005E704
0x18005e5b1  mov     edx, 1; HandleCount
0x18005e5b6  mov     eax, dword ptr [rsp+238h+Logfile.LogfileHeader.28h+8]
0x18005e5bd  add     [rsi+68h], eax
0x18005e5c0  mov     eax, [rsp+238h+Logfile.LogfileHeader.BuffersLost]
0x18005e5c7  add     [rsi+6Ch], eax
0x18005e5ca  mov     rax, qword ptr [rsp+238h+Logfile.LogfileHeader.StartTime]
0x18005e5d2  mov     [rsi+48h], rax
0x18005e5d6  mov     rax, qword ptr [rsp+238h+Logfile.LogfileHeader.EndTime]
0x18005e5de  mov     [rsi+50h], rax
0x18005e5e2  test    r14, r14
0x18005e5e5  jz      loc_18005E66C
0x18005e5eb  mov     r8, r13; Size
0x18005e5ee  xor     edx, edx; Val
0x18005e5f0  lea     rcx, [rsp+238h+Logfile]; void *
0x18005e5f5  call    memset_0
0x18005e5fa  mov     [rsp+238h+Logfile.LogFileName], r14
0x18005e5ff  mov     qword ptr [rsp+238h+Logfile.1A8h], rbx
0x18005e607  mov     dword ptr [rsp+238h+Logfile.1Ch], edi
0x18005e60b  mov     [rsp+238h+Logfile.Context], rsi
0x18005e613  lea     rcx, [rsp+238h+Logfile]; Logfile
0x18005e618  call    cs:__imp_OpenTraceW
0x18005e61e  mov     [rsp+238h+HandleArray+8], rax
0x18005e623  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005e627  jz      loc_18005E593
0x18005e62d  mov     eax, dword ptr [rsp+238h+Logfile.LogfileHeader.28h+8]
0x18005e634  add     [rsi+68h], eax
0x18005e637  mov     eax, [rsp+238h+Logfile.LogfileHeader.BuffersLost]
0x18005e63e  add     [rsi+6Ch], eax
0x18005e641  mov     rax, qword ptr [rsp+238h+Logfile.LogfileHeader.StartTime]
0x18005e649  cmp     [rsi+48h], rax
0x18005e64d  jg      short loc_18005E662
0x18005e64f  mov     edx, 2
0x18005e654  mov     rax, qword ptr [rsp+238h+Logfile.LogfileHeader.EndTime]
0x18005e65c  cmp     [rsi+50h], rax
0x18005e660  jge     short loc_18005E66C
0x18005e662  mov     edi, 80070057h
0x18005e667  jmp     loc_18005E704
0x18005e66c  mov     dword ptr [rsi+58h], 0
0x18005e673  xor     r9d, r9d; EndTime
0x18005e676  xor     r8d, r8d; StartTime
0x18005e679  lea     rcx, [rsp+238h+HandleArray]; HandleArray
0x18005e67e  call    cs:__imp_ProcessTrace
0x18005e684  mov     edi, eax
0x18005e686  test    eax, eax
0x18005e688  jnz     short loc_18005E692
0x18005e68a  cmp     [rsi+58h], eax
0x18005e68d  jz      short loc_18005E69E
0x18005e68f  mov     edi, [rsi+58h]
0x18005e692  test    edi, edi
0x18005e694  jle     short loc_18005E704
0x18005e696  movzx   edi, di
0x18005e699  jmp     loc_18005E5A6
0x18005e69e  mov     rbx, [rsi]
0x18005e6a1  cmp     rbx, [rsi+8]
0x18005e6a5  jnz     short loc_18005E6B0
0x18005e6a7  mov     dword ptr [rsi+70h], 1
0x18005e6ae  jmp     short loc_18005E704
0x18005e6b0  cmp     qword ptr [rbx], 0
0x18005e6b4  jnz     short loc_18005E6BB
0x18005e6b6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005e6bb  mov     rcx, [rbx]; this
0x18005e6be  call    ?ValidateSelf@Troubleshooter@@QEAAKXZ; Troubleshooter::ValidateSelf(void)
0x18005e6c3  mov     rcx, [rbx]; this
0x18005e6c6  call    ?CompleteAnalysis@Troubleshooter@@QEAAXXZ; Troubleshooter::CompleteAnalysis(void)
0x18005e6cb  add     rbx, 8
0x18005e6cf  jmp     short loc_18005E6A1
0x18005e6d1  jmp     short loc_18005E6FB
0x18005e6d3  jmp     short loc_18005E6FB
0x18005e6d5  cmp     qword ptr [rbx], 0
0x18005e6d9  jnz     short loc_18005E6E0
0x18005e6db  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005e6e0  mov     rcx, [rbx]; this
0x18005e6e3  call    ?ValidateSelf@Troubleshooter@@QEAAKXZ; Troubleshooter::ValidateSelf(void)
0x18005e6e8  mov     rcx, [rbx]; this
0x18005e6eb  call    ?InitializeAnalysis@Troubleshooter@@QEAAXXZ; Troubleshooter::InitializeAnalysis(void)
0x18005e6f0  add     rbx, 8
0x18005e6f4  jmp     loc_18005E53F
0x18005e6f9  jmp     short $+2
0x18005e6fb  mov     rsi, [rsp+238h+var_210]
0x18005e700  mov     edi, [rsp+238h+var_218]
0x18005e704  mov     rcx, [rsp+238h+HandleArray]; TraceHandle
0x18005e709  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005e70d  jz      short loc_18005E715
0x18005e70f  call    cs:__imp_CloseTrace
0x18005e715  mov     rcx, [rsp+238h+HandleArray+8]; TraceHandle
0x18005e71a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005e71e  jz      short loc_18005E726
0x18005e720  call    cs:__imp_CloseTrace
0x18005e726  mov     rbx, [rsi+78h]
0x18005e72a  mov     rbx, [rbx]
0x18005e72d  cmp     rbx, [rsi+78h]
0x18005e731  jz      short loc_18005E749
0x18005e733  lea     rcx, [rbx+10h]
0x18005e737  cmp     qword ptr [rbx+28h], 7
0x18005e73c  jbe     short loc_18005E741
0x18005e73e  mov     rcx, [rcx]; Manifest
0x18005e741  call    cs:__imp_TdhUnloadManifest
0x18005e747  jmp     short loc_18005E72A
0x18005e749  mov     eax, edi
0x18005e74b  mov     rcx, [rsp+238h+var_38]
0x18005e753  xor     rcx, rsp; StackCookie
0x18005e756  call    __security_check_cookie
0x18005e75b  add     rsp, 210h
0x18005e762  pop     r14
0x18005e764  pop     r13
0x18005e766  pop     rdi
0x18005e767  pop     rsi
0x18005e768  pop     rbx
0x18005e769  retn
```
