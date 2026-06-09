# COdbcExecutionContext::CreateInstance(ushort *,IOdbcExecutionContext * *,ulong *,long,long)

- ea: `0x1800966ac`
- end: `0x180096dfc`
- name: `?CreateInstance@COdbcExecutionContext@@SAJPEAGPEAPEAVIOdbcExecutionContext@@PEAKJJ@Z`
- size: `1872`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, struct IOdbcExecutionContext **@<rdx>, unsigned int *@<r8>, int@<r9d>, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180096e04`

## callees

- `0x18000205c`
- `0x18001ad74`
- `0x18001dbbc`
- `0x18002d834`
- `0x180077e9c`
- `0x180078198`
- `0x180088a88`
- `0x180088e68`
- `0x180095ffc`
- `0x1800966ac`
- `0x180097614`
- `0x180098124`
- `0x18009f46c`
- `0x18009f51c`
- `0x18009f59c`
- `0x1800a5010`

## import_xrefs

- `KERNEL32!CreateSemaphoreW` at `0x1800968ce`
- `KERNEL32!CreateSemaphoreW` at `0x1800968ce`
- `KERNEL32!GetLastError` at `0x1800968e2`
- `KERNEL32!GetLastError` at `0x180096a80`
- `KERNEL32!GetLastError` at `0x1800968e2`
- `KERNEL32!GetLastError` at `0x180096a80`
- `KERNEL32!WaitForSingleObject` at `0x180096a51`
- `KERNEL32!WaitForSingleObject` at `0x180096a51`
- `KERNEL32!ReleaseSemaphore` at `0x180096d86`
- `KERNEL32!ReleaseSemaphore` at `0x180096d86`
- `KERNEL32!CloseHandle` at `0x1800969ff`
- `KERNEL32!CloseHandle` at `0x1800969ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall COdbcExecutionContext::CreateInstance(
        unsigned __int16 *a1,
        struct IOdbcExecutionContext **a2,
        unsigned int *a3,
        int a4,
        int PreviousCount)
{
  unsigned __int16 *v7; // r14
  signed int v8; // edi
  bool v9; // sf
  unsigned int v10; // eax
  bool v11; // sf
  unsigned int v12; // eax
  PVOID *v13; // rax
  LONG v14; // ebx
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HANDLE SemaphoreW; // rax
  void *v20; // r14
  signed int LastError; // eax
  unsigned int v22; // eax
  int v23; // ebx
  unsigned int v24; // eax
  int v25; // ebx
  unsigned int v26; // eax
  unsigned int v27; // eax
  DWORD v28; // eax
  signed int v29; // eax
  PVOID *v30; // rax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  COdbcExecutionContext *v36; // rax
  int v37; // edx
  COdbcExecutionContext *v38; // rbx
  unsigned int v39; // eax
  struct IOdbcExecutionContext *v40; // rax
  int v41; // ebx
  unsigned int v42; // eax
  unsigned int v44; // [rsp+20h] [rbp-60h]
  __int64 v45; // [rsp+28h] [rbp-58h]
  _QWORD v46[2]; // [rsp+40h] [rbp-40h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-30h] BYREF
  int v48; // [rsp+58h] [rbp-28h]
  int v50; // [rsp+D8h] [rbp+58h] BYREF

  v50 = a4;
  v7 = a1;
  v8 = 0;
  v46[0] = 0;
  PreviousCount = 0;
  if ( lInitialCount >= 0 )
    goto LABEL_27;
  if ( a4 )
  {
LABEL_21:
    if ( lInitialCount < 0 && _InterlockedCompareExchange(&lInitialCount, a4, -1) == -1 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
LABEL_28:
        if ( lInitialCount <= 0 )
          goto LABEL_89;
        if ( g_hExecContextSemaphore )
          goto LABEL_52;
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 && *((_BYTE *)v13 + 25) >= 4u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            &WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids,
            CurrentThreadActivityIdPrefix);
        }
        SemaphoreW = CreateSemaphoreW(0, lInitialCount, lInitialCount, 0);
        v20 = SemaphoreW;
        if ( !SemaphoreW )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v22 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              &WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids,
              v22,
              v8);
          }
          goto LABEL_86;
        }
        if ( _InterlockedCompareExchange64(
               (volatile signed __int64 *)&g_hExecContextSemaphore,
               (signed __int64)SemaphoreW,
               0) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v25 = (int)g_hExecContextSemaphore;
            v26 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_ddd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              18,
              &WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids,
              v26,
              v25,
              (_DWORD)v20);
          }
          CloseHandle(v20);
        }
        else
        {
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_56;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          {
LABEL_52:
            if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 && *((_BYTE *)v13 + 25) >= 4u )
            {
              v27 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids, v27);
            }
LABEL_56:
            v28 = WaitForSingleObject(g_hExecContextSemaphore, 0xFFFFFFFF);
            if ( v28 )
            {
              switch ( v28 )
              {
                case 0x80u:
                  v30 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v33 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_D(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      21,
                      &WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids,
                      v33);
                    v30 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  v8 = -2147467260;
                  goto LABEL_82;
                case 0x102u:
                  v30 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v32 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_D(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      22,
                      &WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids,
                      v32);
                    v30 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  v8 = -2147024638;
                  goto LABEL_82;
                case 0xFFFFFFFF:
                  v29 = GetLastError();
                  v8 = v29;
                  if ( v29 > 0 )
                    v8 = (unsigned __int16)v29 | 0x80070000;
                  v30 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_81;
                  }
                  v31 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_DD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    23,
                    &WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids,
                    v31,
                    v8);
                  break;
              }
            }
            else
            {
              PreviousCount = 1;
              v30 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
              {
                goto LABEL_81;
              }
              v34 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids, v34);
            }
            v30 = (PVOID *)WPP_GLOBAL_Control;
LABEL_81:
            if ( v8 < 0 )
            {
LABEL_82:
              if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 8) != 0 && *((_BYTE *)v30 + 25) >= 2u )
              {
                v35 = RdpWppGetCurrentThreadActivityIdPrefix();
                LODWORD(v45) = v8;
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  24,
                  (unsigned int)&WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids,
                  v35,
                  (__int64)"WaitForSingleObject(g_hExecContextSemaphore)",
                  v45);
              }
LABEL_86:
              if ( v8 >= 0 )
                goto LABEL_111;
              goto LABEL_104;
            }
            v7 = a1;
LABEL_89:
            v36 = (COdbcExecutionContext *)operator new(0x58u);
            v46[1] = v36;
            if ( v36 )
              v38 = COdbcExecutionContext::COdbcExecutionContext(v36, v37);
            else
              v38 = 0;
            if ( v38 )
            {
              TCntPtr<IOdbcExecutionContext>::SafeRelease(v46);
              v46[0] = v38;
              (*(void (__fastcall **)(COdbcExecutionContext *))(*(_QWORD *)v38 + 8LL))(v38);
              v8 = COdbcExecutionContext::Initialize(v38, v7, a3);
              if ( v8 >= 0 )
              {
                v40 = (struct IOdbcExecutionContext *)v46[0];
                v46[0] = 0;
                *a2 = v40;
                goto LABEL_111;
              }
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v39 = RdpWppGetCurrentThreadActivityIdPrefix();
                LODWORD(v45) = v8;
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  26,
                  (unsigned int)&WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids,
                  v39,
                  (__int64)"sp->Initialize",
                  v45);
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DssD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"sp", (__int64)"COdbcExecutionContext", 14);
              }
              v8 = -2147024882;
            }
            goto LABEL_104;
          }
          v23 = (int)g_hExecContextSemaphore;
          v24 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids, v24, v23);
        }
        v13 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_52;
      }
      v14 = lInitialCount;
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DL(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v17, v15, v14);
    }
LABEL_27:
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_28;
  }
  CTSRegEntry::CTSRegEntry(&phkResult, (const unsigned __int16 *)a2, (HKEY)a3, 0, v44);
  v8 = v48;
  v9 = v48 < 0;
  if ( v48 > 0 )
  {
    v8 = (unsigned __int16)v48 | 0x80070000;
    v9 = 1;
  }
  if ( !v9 )
  {
    CTSRegEntry::GetNumber((CTSRegEntry *)&phkResult, L"dMaxDBContexts", 0, &v50);
    v8 = v48;
    v11 = v48 < 0;
    if ( v48 > 0 )
    {
      v8 = (unsigned __int16)v48 | 0x80070000;
      v11 = 1;
    }
    if ( v11 || v50 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids, v12, 2);
      }
      v50 = 2;
      v8 = 0;
    }
    CTSRegEntry::~CTSRegEntry((CTSRegEntry *)&phkResult);
    a4 = v50;
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)&WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids,
      v10,
      (__int64)"regDBMaxContextValue",
      v8);
  }
  CTSRegEntry::~CTSRegEntry((CTSRegEntry *)&phkResult);
LABEL_104:
  if ( v46[0] )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v46[0] + 16LL) + 24LL))(v46[0] + 16LL);
    TCntPtr<IOdbcExecutionContext>::SafeRelease(v46);
    v46[0] = 0;
  }
  else if ( PreviousCount )
  {
    PreviousCount = 0;
    ReleaseSemaphore(g_hExecContextSemaphore, 1, &PreviousCount);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v41 = PreviousCount + 1;
      v42 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids, v42, v41);
    }
  }
LABEL_111:
  TCntPtr<IOdbcExecutionContext>::SafeRelease(v46);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800966ac  mov     [rsp-38h+arg_8], rbx
0x1800966b1  mov     [rsp-38h+arg_18], r9d
0x1800966b6  mov     [rsp-38h+arg_0], rcx
0x1800966bb  push    rbp
0x1800966bc  push    rsi
0x1800966bd  push    rdi
0x1800966be  push    r12
0x1800966c0  push    r13
0x1800966c2  push    r14
0x1800966c4  push    r15
0x1800966c6  mov     rbp, rsp
0x1800966c9  sub     rsp, 80h
0x1800966d0  mov     r13, r8
0x1800966d3  mov     r12, rdx
0x1800966d6  mov     r14, rcx
0x1800966d9  xor     edi, edi
0x1800966db  and     [rbp+var_40], rdi
0x1800966df  and     [rbp+PreviousCount], edi
0x1800966e2  lea     rbx, WPP_GLOBAL_Control
0x1800966e9  mov     sil, 8
0x1800966ec  lea     r15, WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids
0x1800966f3  cmp     cs:lInitialCount, edi
0x1800966f9  jge     loc_18009686D
0x1800966ff  test    r9d, r9d
0x180096702  jnz     loc_180096815
0x180096708  lea     rcx, [rbp+phkResult]; phkResult
0x18009670c  call    ??0CTSRegEntry@@QEAA@PEBGPEAUHKEY__@@HK@Z; CTSRegEntry::CTSRegEntry(ushort const *,HKEY__ *,int,ulong)
0x180096711  nop
0x180096712  mov     edi, [rbp+var_28]
0x180096715  test    edi, edi
0x180096717  jle     short loc_180096724
0x180096719  movzx   edi, di
0x18009671c  or      edi, 80070000h
0x180096722  test    edi, edi
0x180096724  jns     short loc_18009678E
0x180096726  lea     r15, WPP_a54ac2b0381c3bab89433c243409aa7a_Traceguids
0x18009672d  mov     sil, 8
0x180096730  mov     rax, cs:WPP_GLOBAL_Control
0x180096737  cmp     rax, rbx
0x18009673a  jz      short loc_180096779
0x18009673c  test    [rax+1Ch], sil
0x180096740  jz      short loc_180096779
0x180096742  cmp     byte ptr [rax+19h], 2
0x180096746  jb      short loc_180096779
0x180096748  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009674d  mov     r9d, eax
0x180096750  mov     rax, cs:WPP_GLOBAL_Control
0x180096757  mov     edx, 0Ch
0x18009675c  mov     dword ptr [rsp+80h+var_58], edi
0x180096760  lea     rcx, aRegdbmaxcontex; "regDBMaxContextValue"
0x180096767  mov     [rsp+80h+var_60], rcx
0x18009676c  mov     r8, r15
0x18009676f  mov     rcx, [rax+10h]
0x180096773  call    WPP_SF_DsD
0x180096778  nop
0x180096779  lea     rcx, [rbp+phkResult]; this
0x18009677d  call    ??1CTSRegEntry@@QEAA@XZ; CTSRegEntry::~CTSRegEntry(void)
0x180096782  lea     r14, WPP_GLOBAL_Control
0x180096789  jmp     loc_180096D41
0x18009678e  lea     r9, [rbp+arg_18]; int *
0x180096792  xor     r8d, r8d; int
0x180096795  lea     rdx, aDmaxdbcontexts; "dMaxDBContexts"
0x18009679c  lea     rcx, [rbp+phkResult]; this
0x1800967a0  call    ?GetNumber@CTSRegEntry@@QEAAJPEBGJPEAJ@Z; CTSRegEntry::GetNumber(ushort const *,long,long *)
0x1800967a5  mov     edi, [rbp+var_28]
0x1800967a8  test    edi, edi
0x1800967aa  jle     short loc_1800967B7
0x1800967ac  movzx   edi, di
0x1800967af  or      edi, 80070000h
0x1800967b5  test    edi, edi
0x1800967b7  js      short loc_1800967BF
0x1800967b9  cmp     [rbp+arg_18], 0
0x1800967bd  jge     short loc_180096808
0x1800967bf  mov     rax, cs:WPP_GLOBAL_Control
0x1800967c6  cmp     rax, rbx
0x1800967c9  jz      short loc_1800967FF
0x1800967cb  test    [rax+1Ch], sil
0x1800967cf  jz      short loc_1800967FF
0x1800967d1  cmp     byte ptr [rax+19h], 3
0x1800967d5  jb      short loc_1800967FF
0x1800967d7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800967dc  mov     r9d, eax
0x1800967df  mov     rax, cs:WPP_GLOBAL_Control
0x1800967e6  mov     edx, 0Dh
0x1800967eb  mov     dword ptr [rsp+80h+var_60], 2
0x1800967f3  mov     r8, r15
0x1800967f6  mov     rcx, [rax+10h]
0x1800967fa  call    WPP_SF_DD
0x1800967ff  mov     [rbp+arg_18], 2
0x180096806  xor     edi, edi
0x180096808  lea     rcx, [rbp+phkResult]; this
0x18009680c  call    ??1CTSRegEntry@@QEAA@XZ; CTSRegEntry::~CTSRegEntry(void)
0x180096811  mov     r9d, [rbp+arg_18]
0x180096815  cmp     cs:lInitialCount, 0
0x18009681c  jge     short loc_18009686D
0x18009681e  or      eax, 0FFFFFFFFh
0x180096821  lock cmpxchg cs:lInitialCount, r9d
0x18009682a  jnz     short loc_18009686D
0x18009682c  mov     rax, cs:WPP_GLOBAL_Control
0x180096833  cmp     rax, rbx
0x180096836  jz      short loc_180096874
0x180096838  test    [rax+1Ch], sil
0x18009683c  jz      short loc_180096874
0x18009683e  cmp     byte ptr [rax+19h], 4
0x180096842  jb      short loc_180096874
0x180096844  mov     ebx, cs:lInitialCount
0x18009684a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009684f  mov     r9d, eax
0x180096852  mov     rax, cs:WPP_GLOBAL_Control
0x180096859  mov     dword ptr [rsp+80h+var_60], ebx
0x18009685d  mov     rcx, [rax+10h]
0x180096861  call    WPP_SF_DL
0x180096866  lea     rbx, WPP_GLOBAL_Control
0x18009686d  mov     rax, cs:WPP_GLOBAL_Control
0x180096874  cmp     cs:lInitialCount, 0
0x18009687b  jle     loc_180096C13
0x180096881  cmp     cs:?g_hExecContextSemaphore@@3PEAXEA, 0; void * g_hExecContextSemaphore
0x180096889  jnz     loc_180096A12
0x18009688f  cmp     rax, rbx
0x180096892  jz      short loc_1800968C0
0x180096894  test    [rax+1Ch], sil
0x180096898  jz      short loc_1800968C0
0x18009689a  cmp     byte ptr [rax+19h], 4
0x18009689e  jb      short loc_1800968C0
0x1800968a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800968a5  mov     r9d, eax
0x1800968a8  mov     rax, cs:WPP_GLOBAL_Control
0x1800968af  mov     edx, 0Fh
0x1800968b4  mov     r8, r15
0x1800968b7  mov     rcx, [rax+10h]
0x1800968bb  call    WPP_SF_D
0x1800968c0  xor     r9d, r9d; lpName
0x1800968c3  mov     edx, cs:lInitialCount; lInitialCount
0x1800968c9  mov     r8d, edx; lMaximumCount
0x1800968cc  xor     ecx, ecx; lpSemaphoreAttributes
0x1800968ce  call    cs:__imp_CreateSemaphoreW
0x1800968d5  nop     dword ptr [rax+rax+00h]
0x1800968da  mov     r14, rax
0x1800968dd  test    rax, rax
0x1800968e0  jnz     short loc_18009694A
0x1800968e2  call    cs:__imp_GetLastError
0x1800968e9  nop     dword ptr [rax+rax+00h]
0x1800968ee  mov     edi, eax
0x1800968f0  test    eax, eax
0x1800968f2  jle     short loc_1800968FD
0x1800968f4  movzx   edi, ax
0x1800968f7  or      edi, 80070000h
0x1800968fd  mov     rax, cs:WPP_GLOBAL_Control
0x180096904  cmp     rax, rbx
0x180096907  jz      loc_180096C02
0x18009690d  test    [rax+1Ch], sil
0x180096911  jz      loc_180096C02
0x180096917  cmp     byte ptr [rax+19h], 2
0x18009691b  jb      loc_180096C02
0x180096921  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180096926  mov     r9d, eax
0x180096929  mov     rax, cs:WPP_GLOBAL_Control
0x180096930  mov     edx, 10h
0x180096935  mov     dword ptr [rsp+80h+var_60], edi
0x180096939  mov     r8, r15
0x18009693c  mov     rcx, [rax+10h]
0x180096940  call    WPP_SF_DD
0x180096945  jmp     loc_180096C02
0x18009694a  xor     eax, eax
0x18009694c  lock cmpxchg cs:?g_hExecContextSemaphore@@3PEAXEA, r14; void * g_hExecContextSemaphore
0x180096955  jnz     short loc_1800969AE
0x180096957  mov     rax, cs:WPP_GLOBAL_Control
0x18009695e  cmp     rax, rbx
0x180096961  jz      loc_180096A43
0x180096967  test    [rax+1Ch], sil
0x18009696b  jz      loc_180096A12
0x180096971  cmp     byte ptr [rax+19h], 4
0x180096975  jb      loc_180096A12
0x18009697b  mov     ebx, dword ptr cs:?g_hExecContextSemaphore@@3PEAXEA; void * g_hExecContextSemaphore
0x180096981  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180096986  mov     r9d, eax
0x180096989  mov     rax, cs:WPP_GLOBAL_Control
0x180096990  mov     edx, 11h
0x180096995  mov     dword ptr [rsp+80h+var_60], ebx
0x180096999  mov     r8, r15
0x18009699c  mov     rcx, [rax+10h]
0x1800969a0  call    WPP_SF_DD
0x1800969a5  lea     rbx, WPP_GLOBAL_Control
0x1800969ac  jmp     short loc_180096A0B
0x1800969ae  mov     rax, cs:WPP_GLOBAL_Control
0x1800969b5  cmp     rax, rbx
0x1800969b8  jz      short loc_1800969FC
0x1800969ba  test    [rax+1Ch], sil
0x1800969be  jz      short loc_1800969FC
0x1800969c0  cmp     byte ptr [rax+19h], 2
0x1800969c4  jb      short loc_1800969FC
0x1800969c6  mov     ebx, dword ptr cs:?g_hExecContextSemaphore@@3PEAXEA; void * g_hExecContextSemaphore
0x1800969cc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800969d1  mov     r9d, eax
0x1800969d4  mov     rax, cs:WPP_GLOBAL_Control
0x1800969db  mov     edx, 12h
0x1800969e0  mov     dword ptr [rsp+80h+var_58], r14d
0x1800969e5  mov     dword ptr [rsp+80h+var_60], ebx
0x1800969e9  mov     r8, r15
0x1800969ec  mov     rcx, [rax+10h]
0x1800969f0  call    WPP_SF_ddd
0x1800969f5  lea     rbx, WPP_GLOBAL_Control
0x1800969fc  mov     rcx, r14; hObject
0x1800969ff  call    cs:__imp_CloseHandle
0x180096a06  nop     dword ptr [rax+rax+00h]
0x180096a0b  mov     rax, cs:WPP_GLOBAL_Control
0x180096a12  cmp     rax, rbx
0x180096a15  jz      short loc_180096A43
0x180096a17  test    [rax+1Ch], sil
0x180096a1b  jz      short loc_180096A43
0x180096a1d  cmp     byte ptr [rax+19h], 4
0x180096a21  jb      short loc_180096A43
0x180096a23  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180096a28  mov     r9d, eax
0x180096a2b  mov     rax, cs:WPP_GLOBAL_Control
0x180096a32  mov     edx, 13h
0x180096a37  mov     r8, r15
0x180096a3a  mov     rcx, [rax+10h]
0x180096a3e  call    WPP_SF_D
0x180096a43  or      r14d, 0FFFFFFFFh
0x180096a47  mov     edx, r14d; dwMilliseconds
0x180096a4a  mov     rcx, cs:?g_hExecContextSemaphore@@3PEAXEA; hHandle
0x180096a51  call    cs:__imp_WaitForSingleObject
0x180096a58  nop     dword ptr [rax+rax+00h]
0x180096a5d  test    eax, eax
0x180096a5f  jz      loc_180096B77
0x180096a65  cmp     eax, 80h
0x180096a6a  jz      loc_180096B31
0x180096a70  cmp     eax, 102h
0x180096a75  jz      short loc_180096AE8
0x180096a77  cmp     eax, r14d
0x180096a7a  jnz     loc_180096BB6
0x180096a80  call    cs:__imp_GetLastError
0x180096a87  nop     dword ptr [rax+rax+00h]
0x180096a8c  mov     edi, eax
0x180096a8e  test    eax, eax
0x180096a90  jle     short loc_180096A9B
0x180096a92  movzx   edi, ax
0x180096a95  or      edi, 80070000h
0x180096a9b  mov     rax, cs:WPP_GLOBAL_Control
0x180096aa2  cmp     rax, rbx
0x180096aa5  jz      loc_180096BBD
0x180096aab  test    [rax+1Ch], sil
0x180096aaf  jz      loc_180096BBD
0x180096ab5  cmp     byte ptr [rax+19h], 2
0x180096ab9  jb      loc_180096BBD
0x180096abf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180096ac4  mov     r9d, eax
0x180096ac7  mov     rax, cs:WPP_GLOBAL_Control
0x180096ace  mov     edx, 17h
0x180096ad3  mov     dword ptr [rsp+80h+var_60], edi
0x180096ad7  mov     r8, r15
0x180096ada  mov     rcx, [rax+10h]
0x180096ade  call    WPP_SF_DD
0x180096ae3  jmp     loc_180096BB6
0x180096ae8  mov     rax, cs:WPP_GLOBAL_Control
0x180096aef  cmp     rax, rbx
0x180096af2  jz      short loc_180096B27
0x180096af4  test    [rax+1Ch], sil
0x180096af8  jz      short loc_180096B27
0x180096afa  cmp     byte ptr [rax+19h], 2
0x180096afe  jb      short loc_180096B27
0x180096b00  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180096b05  mov     r9d, eax
0x180096b08  mov     rax, cs:WPP_GLOBAL_Control
0x180096b0f  mov     edx, 16h
0x180096b14  mov     r8, r15
0x180096b17  mov     rcx, [rax+10h]
0x180096b1b  call    WPP_SF_D
0x180096b20  mov     rax, cs:WPP_GLOBAL_Control
0x180096b27  mov     edi, 80070102h
0x180096b2c  jmp     loc_180096BC1
0x180096b31  mov     rax, cs:WPP_GLOBAL_Control
0x180096b38  cmp     rax, rbx
0x180096b3b  jz      short loc_180096B70
0x180096b3d  test    [rax+1Ch], sil
0x180096b41  jz      short loc_180096B70
0x180096b43  cmp     byte ptr [rax+19h], 2
0x180096b47  jb      short loc_180096B70
0x180096b49  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180096b4e  mov     r9d, eax
0x180096b51  mov     rax, cs:WPP_GLOBAL_Control
0x180096b58  mov     edx, 15h
0x180096b5d  mov     r8, r15
0x180096b60  mov     rcx, [rax+10h]
0x180096b64  call    WPP_SF_D
0x180096b69  mov     rax, cs:WPP_GLOBAL_Control
0x180096b70  mov     edi, 80004004h
0x180096b75  jmp     short loc_180096BC1
0x180096b77  mov     [rbp+PreviousCount], 1
0x180096b7e  mov     rax, cs:WPP_GLOBAL_Control
0x180096b85  cmp     rax, rbx
0x180096b88  jz      short loc_180096BBD
0x180096b8a  test    [rax+1Ch], sil
0x180096b8e  jz      short loc_180096BBD
0x180096b90  cmp     byte ptr [rax+19h], 4
0x180096b94  jb      short loc_180096BBD
0x180096b96  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180096b9b  mov     r9d, eax
0x180096b9e  mov     rax, cs:WPP_GLOBAL_Control
  ... truncated ...
```
