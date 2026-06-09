# ProcessTrace

- ea: `0x180007500`
- end: `0x180007a18`
- name: `ProcessTrace`
- size: `1304`
- prototype: `ULONG __stdcall(PTRACEHANDLE HandleArray, ULONG HandleCount, LPFILETIME StartTime, LPFILETIME EndTime)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, loader_planting`

## callees

- `0x180001008`
- `0x180001560`
- `0x180001eb2`
- `0x180001ff0`
- `0x180002020`
- `0x180003304`
- `0x1800038f8`
- `0x18000390c`
- `0x180003cf0`
- `0x180004da0`
- `0x180004fe8`
- `0x180007500`
- `0x18000f098`
- `0x18000f90c`
- `0x18000fc74`
- `0x18000fe48`
- `0x180012674`
- `0x1800157b0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800077b0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007a01`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180015a39`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800077b0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007a01`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180015a39`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000775d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000797f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000775d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000797f`
- `ntdll!RtlSetLastWin32Error` at `0x180007962`
- `ntdll!RtlSetLastWin32Error` at `0x1800079e0`
- `ntdll!RtlSetLastWin32Error` at `0x180007962`
- `ntdll!RtlSetLastWin32Error` at `0x1800079e0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000757c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000757c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007889`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000790f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007889`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000790f`

## pseudocode

```c
ULONG __stdcall ProcessTrace(PTRACEHANDLE HandleArray, ULONG HandleCount, LPFILETIME StartTime, LPFILETIME EndTime)
{
  unsigned __int64 v6; // r15
  _DWORD *v8; // r9
  ULONG v9; // ebx
  struct _FILETIME v11; // rsi
  struct _FILETIME v12; // r14
  unsigned __int64 v13; // rbx
  struct _TRACELOG_CONTEXT **v14; // rax
  struct _TRACELOG_CONTEXT **v15; // rdi
  unsigned int v16; // r9d
  struct _TRACELOG_CONTEXT *v17; // rax
  int v18; // r9d
  __int64 v19; // r8
  char v20; // bl
  unsigned int v21; // r12d
  struct _TRACELOG_CONTEXT *v22; // rsi
  const WCHAR *v23; // rcx
  unsigned int v24; // ebx
  struct _TRACELOG_CONTEXT *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  ULONG v28; // eax
  ULONG v29; // ebx
  unsigned int v30; // ebx
  struct _TRACELOG_CONTEXT *v31; // rcx
  struct _TRACELOG_CONTEXT *v32; // rcx
  unsigned int v33; // [rsp+30h] [rbp-1158h] BYREF
  unsigned int v34; // [rsp+34h] [rbp-1154h] BYREF
  unsigned int v35; // [rsp+38h] [rbp-1150h] BYREF
  unsigned int v36; // [rsp+3Ch] [rbp-114Ch]
  __int64 v37[2]; // [rsp+40h] [rbp-1148h] BYREF
  _BYTE v38[24]; // [rsp+50h] [rbp-1138h] BYREF
  int v39; // [rsp+68h] [rbp-1120h] BYREF
  char v40; // [rsp+6Ch] [rbp-111Ch]
  GUID ActivityId; // [rsp+70h] [rbp-1118h] BYREF
  _DWORD v42[4]; // [rsp+80h] [rbp-1108h] BYREF
  struct _EVENT_TRACE_PROPERTIES Properties; // [rsp+90h] [rbp-10F8h] BYREF
  _BYTE v44[32]; // [rsp+1110h] [rbp-78h] BYREF
  unsigned int *v45; // [rsp+1130h] [rbp-58h]
  __int64 v46; // [rsp+1138h] [rbp-50h]

  v6 = HandleCount;
  v33 = 0;
  TraceLoggingActivity<&_tlgProvider_t const * const g_hEtwUmDiagnosticProvider,16,5,_TlgReflectorTag_Param0IsHProvider>::TraceLoggingActivity<&_tlgProvider_t const * const g_hEtwUmDiagnosticProvider,16,5,_TlgReflectorTag_Param0IsHProvider>(&v39);
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v39 = 1;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
  {
    v34 = v6;
    if ( v40 && (v42[0] || v42[1] || v42[2] || v42[3]) )
      v8 = v42;
    else
      LODWORD(v8) = 0;
    v45 = &v34;
    v46 = 4;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_18001D020,
      (unsigned int)byte_1800188D3,
      (unsigned int)&ActivityId,
      (_DWORD)v8,
      3,
      (__int64)v44);
  }
  v37[0] = (__int64)&v39;
  v37[1] = (__int64)&v33;
  tlx::make_undo__lambda_fd10dbda222d270150adf0653ae4b862___(v38, v37);
  if ( !(_DWORD)v6 )
  {
    v9 = 24;
LABEL_19:
    v33 = v9;
    goto LABEL_20;
  }
  if ( !HandleArray )
  {
    v9 = 87;
    goto LABEL_19;
  }
  if ( StartTime )
    v11 = *StartTime;
  else
    v11 = 0;
  v37[0] = (__int64)v11;
  if ( EndTime )
    v12 = *EndTime;
  else
    v12 = (struct _FILETIME)0x7FFFFFFFFFFFFFFFLL;
  if ( !*(_QWORD *)&v12 )
    v12 = (struct _FILETIME)0x7FFFFFFFFFFFFFFFLL;
  if ( *(_QWORD *)&v12 < *(unsigned __int64 *)&v11 )
  {
    v9 = 1901;
    goto LABEL_19;
  }
  v13 = 8 * v6;
  if ( !is_mul_ok(v6, 8u) )
    v13 = -1;
  v14 = (struct _TRACELOG_CONTEXT **)operator new(v13, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v14;
  if ( v14 )
    memset_0(v14, 0, v13);
  if ( v15 )
  {
    RtlAcquireSRWLockExclusive(&EtwpConsumerLock);
    v33 = 0;
    v16 = 0;
    v36 = 0;
    while ( v16 < (unsigned int)v6 )
    {
      v17 = EtwpLookupTracelogContextLocked(HandleArray[v16]);
      v15[v19] = v17;
      if ( !v17 || *((_DWORD *)v17 + 6) )
      {
        v33 = 6;
        break;
      }
      *((_DWORD *)v17 + 6) = 1;
      v16 = v18 + 1;
      v36 = v16;
    }
    RtlReleaseSRWLockExclusive(&EtwpConsumerLock);
    if ( !v33 )
    {
      v20 = 3;
      v21 = 0;
      do
      {
        v22 = v15[v21];
        if ( (*((_DWORD *)v22 + 27) & 0x100) != 0 )
        {
          v34 = 0;
          v35 = 0;
          memset_0(&Properties, 0, 0x1078u);
          if ( v20 != 3 )
            goto LABEL_79;
          v23 = (const WCHAR *)*((_QWORD *)v22 + 11);
          if ( !v23 )
          {
            v29 = 123;
LABEL_73:
            RtlSetLastWin32Error(v29);
            v33 = v29;
            goto LABEL_74;
          }
          v33 = EtwpQueryRealTimeTraceProperties(v23, &Properties, &v35, &v34);
          if ( v33 )
            goto LABEL_74;
          v33 = EtwpGenerateLogHeaderForRealtime(&Properties, v35, (struct _TRACE_LOGFILE_HEADER *)((char *)v22 + 200));
          if ( v33 )
            goto LABEL_74;
          v24 = v34;
          if ( v34 == 0xFFFF )
          {
            *((_DWORD *)v22 + 128) = 1;
            v24 = 0;
          }
          *((_QWORD *)v15[v21] + 122) = CreateEventW(0, 1, 1, 0);
          v25 = v15[v21];
          if ( !*((_QWORD *)v25 + 122) )
          {
LABEL_80:
            v33 = 8;
            goto LABEL_74;
          }
          *((_DWORD *)v25 + 190) = v24;
          v20 = 1;
        }
        else if ( *((_BYTE *)v22 + 552) == 2 )
        {
          if ( v20 != 3 )
            goto LABEL_79;
          v20 = 2;
        }
        else
        {
          if ( v20 != 3 && v20 )
          {
LABEL_79:
            v29 = 87;
            goto LABEL_73;
          }
          v26 = *((_QWORD *)v22 + 10);
          if ( !v26 )
            goto LABEL_81;
          v27 = -1;
          do
            ++v27;
          while ( *(_WORD *)(v26 + 2 * v27) );
          if ( !v27 )
          {
LABEL_81:
            v29 = 161;
            goto LABEL_73;
          }
          *((_QWORD *)v15[v21] + 122) = CreateEventW(0, 1, 1, 0);
          if ( !*((_QWORD *)v15[v21] + 122) )
            goto LABEL_80;
          v20 = 0;
        }
        ++v21;
      }
      while ( v21 < (unsigned int)v6 );
      if ( v20 )
      {
        v32 = *v15;
        if ( v20 == 1 )
          v28 = EtwpProcessRealTimeTraces(v32, v37[0], *(_QWORD *)&v12);
        else
          v28 = EtwpProcessBufferStreamTrace(v32, v37[0], *(_QWORD *)&v12);
      }
      else
      {
        v28 = EtwpProcessTraceLog(v15, v6, v37[0], *(_QWORD *)&v12);
      }
      v33 = v28;
      if ( v28 )
        RtlSetLastWin32Error(v28);
    }
  }
  else
  {
    v33 = 14;
  }
LABEL_74:
  if ( v15 )
  {
    RtlAcquireSRWLockExclusive(&EtwpConsumerLock);
    v30 = 0;
    do
    {
      v31 = v15[v30];
      if ( v31 )
      {
        if ( *((_DWORD *)v31 + 6) == 1 )
        {
          *((_DWORD *)v31 + 6) = 0;
        }
        else if ( *((_DWORD *)v31 + 6) == 2 )
        {
          EtwpFreeTraceContextWithLock(v31);
        }
      }
      ++v30;
    }
    while ( v30 < (unsigned int)v6 );
    RtlReleaseSRWLockExclusive(&EtwpConsumerLock);
    operator delete(v15);
  }
  v9 = v33;
LABEL_20:
  if ( v38[16] )
    lambda_7a247250c1a07a0a9c95ab022b659a7d_::operator()(v38);
  TraceLoggingActivity<&_tlgProvider_t const * const g_hEtwUmDiagnosticProvider,16,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEtwUmDiagnosticProvider,16,5,_TlgReflectorTag_Param0IsHProvider>(&v39);
  return v9;
}

```

## disassembly

```asm
0x180007500  push    rbx
0x180007502  push    rsi
0x180007503  push    rdi
0x180007504  push    r12
0x180007506  push    r13
0x180007508  push    r14
0x18000750a  push    r15
0x18000750c  mov     eax, 1150h
0x180007511  call    _alloca_probe
0x180007516  sub     rsp, rax
0x180007519  mov     rax, cs:__security_cookie
0x180007520  xor     rax, rsp
0x180007523  mov     [rsp+1188h+var_48], rax
0x18000752b  mov     r14, r9
0x18000752e  mov     rbx, r8
0x180007531  mov     r15d, edx
0x180007534  mov     r12, rcx
0x180007537  xor     r13d, r13d
0x18000753a  mov     [rsp+1188h+var_1158], r13d
0x18000753f  lea     rcx, [rsp+1188h+var_1120]
0x180007544  call    ??0?$TraceLoggingActivity@$1?g_hEtwUmDiagnosticProvider@@3QEBU_tlgProvider_t@@EB$0BA@$04U_TlgReflectorTag_Param0IsHProvider@@@@QEAA@XZ; TraceLoggingActivity<&_tlgProvider_t const * const g_hEtwUmDiagnosticProvider,16,5,_TlgReflectorTag_Param0IsHProvider>::TraceLoggingActivity<&_tlgProvider_t const * const g_hEtwUmDiagnosticProvider,16,5,_TlgReflectorTag_Param0IsHProvider>(void)
0x180007549  mov     r8d, cs:dword_18001D020
0x180007550  cmp     r8d, 5
0x180007554  jbe     short loc_180007584
0x180007556  mov     rcx, cs:qword_18001D038
0x18000755d  mov     rax, cs:qword_18001D030
0x180007564  test    al, 10h
0x180007566  jz      short loc_180007584
0x180007568  mov     rax, rcx
0x18000756b  and     eax, 10h
0x18000756e  cmp     rax, rcx
0x180007571  jnz     short loc_180007584
0x180007573  lea     rdx, [rsp+1188h+ActivityId]; ActivityId
0x180007578  lea     ecx, [r13+3]; ControlCode
0x18000757c  call    cs:__imp_EventActivityIdControl
0x180007582  jmp     short loc_18000758C
0x180007584  xorps   xmm0, xmm0
0x180007587  movups  xmmword ptr [rsp+1188h+ActivityId.Data1], xmm0
0x18000758c  mov     [rsp+1188h+var_1120], 1
0x180007594  mov     eax, cs:dword_18001D020
0x18000759a  cmp     eax, 5
0x18000759d  jbe     loc_18000764F
0x1800075a3  mov     rcx, cs:qword_18001D038
0x1800075aa  mov     rax, cs:qword_18001D030
0x1800075b1  test    al, 10h
0x1800075b3  jz      loc_18000764F
0x1800075b9  mov     rax, rcx
0x1800075bc  and     eax, 10h
0x1800075bf  cmp     rax, rcx
0x1800075c2  jnz     loc_18000764F
0x1800075c8  mov     [rsp+1188h+var_1154], r15d
0x1800075cd  cmp     [rsp+1188h+var_111C], r13b
0x1800075d2  jz      short loc_180007606
0x1800075d4  cmp     [rsp+1188h+var_1108], r13d
0x1800075dc  jnz     short loc_1800075FC
0x1800075de  cmp     [rsp+1188h+var_1104], r13d
0x1800075e6  jnz     short loc_1800075FC
0x1800075e8  cmp     [rsp+1188h+var_1100], r13d
0x1800075f0  jnz     short loc_1800075FC
0x1800075f2  cmp     [rsp+1188h+var_10FC], r13d
0x1800075fa  jz      short loc_180007606
0x1800075fc  lea     r9, [rsp+1188h+var_1108]
0x180007604  jmp     short loc_180007609
0x180007606  mov     r9, r13
0x180007609  lea     rax, [rsp+1188h+var_1154]
0x18000760e  mov     [rsp+1188h+var_58], rax
0x180007616  mov     [rsp+1188h+var_50], 4
0x180007622  lea     rax, [rsp+1188h+var_78]
0x18000762a  mov     [rsp+1188h+var_1160], rax
0x18000762f  mov     [rsp+1188h+var_1168], 3
0x180007637  lea     r8, [rsp+1188h+ActivityId]
0x18000763c  lea     rdx, byte_1800188D3
0x180007643  lea     rcx, dword_18001D020
0x18000764a  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000764f  lea     rax, [rsp+1188h+var_1120]
0x180007654  mov     [rsp+1188h+var_1148], rax
0x180007659  lea     rax, [rsp+1188h+var_1158]
0x18000765e  mov     [rsp+1188h+var_1140], rax
0x180007663  lea     rdx, [rsp+1188h+var_1148]
0x180007668  lea     rcx, [rsp+1188h+var_1138]
0x18000766d  call    tlx__make_undo__lambda_fd10dbda222d270150adf0653ae4b862___
0x180007672  test    r15d, r15d
0x180007675  jnz     short loc_1800076BF
0x180007677  lea     ebx, [r15+18h]
0x18000767b  mov     [rsp+1188h+var_1158], ebx
0x18000767f  cmp     [rsp+1188h+var_1128], r13b
0x180007684  jz      short loc_180007690
0x180007686  lea     rcx, [rsp+1188h+var_1138]
0x18000768b  call    _lambda_7a247250c1a07a0a9c95ab022b659a7d___operator__
0x180007690  lea     rcx, [rsp+1188h+var_1120]
0x180007695  call    ??1?$TraceLoggingActivity@$1?g_hEtwUmDiagnosticProvider@@3QEBU_tlgProvider_t@@EB$0BA@$04U_TlgReflectorTag_Param0IsHProvider@@@@QEAA@XZ; TraceLoggingActivity<&_tlgProvider_t const * const g_hEtwUmDiagnosticProvider,16,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEtwUmDiagnosticProvider,16,5,_TlgReflectorTag_Param0IsHProvider>(void)
0x18000769a  mov     eax, ebx
0x18000769c  mov     rcx, [rsp+1188h+var_48]
0x1800076a4  xor     rcx, rsp; StackCookie
0x1800076a7  call    __security_check_cookie
0x1800076ac  add     rsp, 1150h
0x1800076b3  pop     r15
0x1800076b5  pop     r14
0x1800076b7  pop     r13
0x1800076b9  pop     r12
0x1800076bb  pop     rdi
0x1800076bc  pop     rsi
0x1800076bd  pop     rbx
0x1800076be  retn
0x1800076bf  test    r12, r12
0x1800076c2  jnz     short loc_1800076CB
0x1800076c4  lea     ebx, [r12+57h]
0x1800076c9  jmp     short loc_18000767B
0x1800076cb  test    rbx, rbx
0x1800076ce  jz      short loc_1800076D5
0x1800076d0  mov     rsi, [rbx]
0x1800076d3  jmp     short loc_1800076D8
0x1800076d5  mov     rsi, r13
0x1800076d8  mov     [rsp+1188h+var_1148], rsi
0x1800076dd  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800076e7  test    r14, r14
0x1800076ea  jz      short loc_1800076F1
0x1800076ec  mov     r14, [r14]
0x1800076ef  jmp     short loc_1800076F4
0x1800076f1  mov     r14, rax
0x1800076f4  test    r14, r14
0x1800076f7  cmovz   r14, rax
0x1800076fb  cmp     r14, rsi
0x1800076fe  jnb     short loc_18000770A
0x180007700  mov     ebx, 76Dh
0x180007705  jmp     loc_18000767B
0x18000770a  mov     eax, 8
0x18000770f  mul     r15
0x180007712  mov     rbx, rax
0x180007715  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000771c  cmovb   rbx, rax
0x180007720  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007727  mov     rcx, rbx; unsigned __int64
0x18000772a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000772f  mov     rdi, rax
0x180007732  test    rax, rax
0x180007735  jz      short loc_180007744
0x180007737  mov     r8, rbx; Size
0x18000773a  xor     edx, edx; Val
0x18000773c  mov     rcx, rax; void *
0x18000773f  call    memset_0
0x180007744  test    rdi, rdi
0x180007747  jnz     short loc_180007756
0x180007749  mov     [rsp+1188h+var_1158], 0Eh
0x180007751  jmp     loc_18000796F
0x180007756  lea     rcx, ?EtwpConsumerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK EtwpConsumerLock
0x18000775d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180007763  mov     [rsp+1188h+var_1158], r13d
0x180007768  mov     r9d, r13d
0x18000776b  mov     [rsp+1188h+var_114C], r13d
0x180007770  cmp     r9d, r15d
0x180007773  jnb     short loc_1800077A9
0x180007775  mov     r8d, r9d
0x180007778  mov     rcx, [r12+r8*8]; unsigned __int64
0x18000777c  call    ?EtwpLookupTracelogContextLocked@@YAPEAU_TRACELOG_CONTEXT@@_K@Z; EtwpLookupTracelogContextLocked(unsigned __int64)
0x180007781  mov     [rdi+r8*8], rax
0x180007785  test    rax, rax
0x180007788  jz      short loc_1800077A1
0x18000778a  cmp     [rax+18h], r13d
0x18000778e  jnz     short loc_1800077A1
0x180007790  mov     dword ptr [rax+18h], 1
0x180007797  inc     r9d
0x18000779a  mov     [rsp+1188h+var_114C], r9d
0x18000779f  jmp     short loc_180007770
0x1800077a1  mov     [rsp+1188h+var_1158], 6
0x1800077a9  lea     rcx, ?EtwpConsumerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK EtwpConsumerLock
0x1800077b0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800077b6  cmp     [rsp+1188h+var_1158], r13d
0x1800077bb  jnz     loc_18000796F
0x1800077c1  mov     bl, 3
0x1800077c3  mov     r12d, r13d
0x1800077c6  test    r15d, r15d
0x1800077c9  jz      loc_180007944
0x1800077cf  mov     r13d, r12d
0x1800077d2  mov     rsi, [rdi+r13*8]
0x1800077d6  test    dword ptr [rsi+6Ch], 100h
0x1800077dd  jz      loc_1800078B8
0x1800077e3  mov     [rsp+1188h+var_1154], 0
0x1800077eb  mov     [rsp+1188h+var_1150], 0
0x1800077f3  xor     edx, edx; Val
0x1800077f5  mov     r8d, 1078h; Size
0x1800077fb  lea     rcx, [rsp+1188h+Properties]; void *
0x180007803  call    memset_0
0x180007808  cmp     bl, 3
0x18000780b  jnz     loc_1800079A4
0x180007811  mov     rcx, [rsi+58h]; InstanceName
0x180007815  test    rcx, rcx
0x180007818  jz      loc_18000795B
0x18000781e  lea     r9, [rsp+1188h+var_1154]; unsigned int *
0x180007823  lea     r8, [rsp+1188h+var_1150]; unsigned int *
0x180007828  lea     rdx, [rsp+1188h+Properties]; Properties
0x180007830  call    ?EtwpQueryRealTimeTraceProperties@@YAKPEAGPEAU_REALTIME_TRACE_PROPERTIES@@PEAK2@Z; EtwpQueryRealTimeTraceProperties(ushort *,_REALTIME_TRACE_PROPERTIES *,ulong *,ulong *)
0x180007835  mov     [rsp+1188h+var_1158], eax
0x180007839  test    eax, eax
0x18000783b  jnz     loc_18000796C
0x180007841  lea     r8, [rsi+0C8h]; struct _TRACE_LOGFILE_HEADER *
0x180007848  mov     edx, [rsp+1188h+var_1150]; unsigned int
0x18000784c  lea     rcx, [rsp+1188h+Properties]; struct _EVENT_TRACE_PROPERTIES *
0x180007854  call    ?EtwpGenerateLogHeaderForRealtime@@YAKPEAU_EVENT_TRACE_PROPERTIES@@KPEAU_TRACE_LOGFILE_HEADER@@@Z; EtwpGenerateLogHeaderForRealtime(_EVENT_TRACE_PROPERTIES *,ulong,_TRACE_LOGFILE_HEADER *)
0x180007859  mov     [rsp+1188h+var_1158], eax
0x18000785d  test    eax, eax
0x18000785f  jnz     loc_18000796C
0x180007865  mov     ebx, [rsp+1188h+var_1154]
0x180007869  cmp     ebx, 0FFFFh
0x18000786f  jnz     short loc_18000787D
0x180007871  mov     dword ptr [rsi+200h], 1
0x18000787b  xor     ebx, ebx
0x18000787d  xor     r9d, r9d; lpName
0x180007880  lea     edx, [r9+1]; bManualReset
0x180007884  xor     ecx, ecx; lpEventAttributes
0x180007886  mov     r8d, edx; bInitialState
0x180007889  call    cs:__imp_CreateEventW
0x18000788f  mov     rcx, [rdi+r13*8]
0x180007893  mov     [rcx+3D0h], rax
0x18000789a  mov     rax, [rdi+r13*8]
0x18000789e  xor     r13d, r13d
0x1800078a1  cmp     [rax+3D0h], r13
0x1800078a8  jz      loc_1800079AB
0x1800078ae  mov     [rax+2F8h], ebx
0x1800078b4  mov     bl, 1
0x1800078b6  jmp     short loc_180007933
0x1800078b8  cmp     byte ptr [rsi+228h], 2
0x1800078bf  jnz     short loc_1800078D1
0x1800078c1  cmp     bl, 3
0x1800078c4  jnz     loc_1800079A4
0x1800078ca  mov     bl, 2
0x1800078cc  xor     r13d, r13d
0x1800078cf  jmp     short loc_180007933
0x1800078d1  xor     edx, edx
0x1800078d3  cmp     bl, 3
0x1800078d6  jz      short loc_1800078E0
0x1800078d8  test    bl, bl
0x1800078da  jnz     loc_1800079A4
0x1800078e0  mov     rcx, [rsi+50h]
0x1800078e4  test    rcx, rcx
0x1800078e7  jz      loc_1800079B5
0x1800078ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800078f1  inc     rax
0x1800078f4  cmp     [rcx+rax*2], dx
0x1800078f8  jnz     short loc_1800078F1
0x1800078fa  test    rax, rax
0x1800078fd  jz      loc_1800079B5
0x180007903  xor     r9d, r9d; lpName
0x180007906  lea     edx, [r9+1]; bManualReset
0x18000790a  xor     ecx, ecx; lpEventAttributes
0x18000790c  mov     r8d, edx; bInitialState
0x18000790f  call    cs:__imp_CreateEventW
0x180007915  mov     rcx, [rdi+r13*8]
0x180007919  mov     [rcx+3D0h], rax
0x180007920  mov     rax, [rdi+r13*8]
0x180007924  xor     r13d, r13d
0x180007927  cmp     [rax+3D0h], r13
0x18000792e  jz      short loc_1800079AB
0x180007930  mov     bl, r13b
0x180007933  inc     r12d
0x180007936  cmp     r12d, r15d
0x180007939  jb      loc_1800077CF
0x18000793f  mov     rsi, [rsp+1188h+var_1148]
0x180007944  test    bl, bl
0x180007946  jnz     short loc_1800079BC
0x180007948  mov     r9, r14; __int64
0x18000794b  mov     r8, rsi; __int64
0x18000794e  mov     edx, r15d; unsigned int
0x180007951  mov     rcx, rdi; struct _TRACELOG_CONTEXT **
0x180007954  call    ?EtwpProcessTraceLog@@YAKPEAPEAU_TRACELOG_CONTEXT@@K_J1@Z; EtwpProcessTraceLog(_TRACELOG_CONTEXT * *,ulong,__int64,__int64)
0x180007959  jmp     short loc_1800079D6
0x18000795b  mov     ebx, 7Bh ; '{'
0x180007960  mov     ecx, ebx; LastError
0x180007962  call    cs:__imp_RtlSetLastWin32Error
0x180007968  mov     [rsp+1188h+var_1158], ebx
0x18000796c  xor     r13d, r13d
0x18000796f  test    rdi, rdi
0x180007972  jz      loc_180007A0F
0x180007978  lea     rcx, ?EtwpConsumerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK EtwpConsumerLock
0x18000797f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180007985  mov     ebx, r13d
0x180007988  test    r15d, r15d
0x18000798b  jz      short loc_1800079FA
0x18000798d  mov     eax, ebx
0x18000798f  mov     rcx, [rdi+rax*8]; Block
0x180007993  test    rcx, rcx
0x180007996  jz      short loc_1800079F3
0x180007998  cmp     dword ptr [rcx+18h], 1
0x18000799c  jnz     short loc_1800079E8
0x18000799e  mov     [rcx+18h], r13d
0x1800079a2  jmp     short loc_1800079F3
0x1800079a4  mov     ebx, 57h ; 'W'
0x1800079a9  jmp     short loc_180007960
0x1800079ab  mov     [rsp+1188h+var_1158], 8
0x1800079b3  jmp     short loc_18000796F
0x1800079b5  mov     ebx, 0A1h
0x1800079ba  jmp     short loc_180007960
0x1800079bc  mov     r8, r14; unsigned __int64
0x1800079bf  mov     rdx, rsi; unsigned __int64
0x1800079c2  mov     rcx, [rdi]; struct _TRACELOG_CONTEXT *
0x1800079c5  cmp     bl, 1
0x1800079c8  jnz     short loc_1800079D1
0x1800079ca  call    ?EtwpProcessRealTimeTraces@@YAKPEAU_TRACELOG_CONTEXT@@_K1@Z; EtwpProcessRealTimeTraces(_TRACELOG_CONTEXT *,unsigned __int64,unsigned __int64)
0x1800079cf  jmp     short loc_1800079D6
0x1800079d1  call    ?EtwpProcessBufferStreamTrace@@YAKPEAU_TRACELOG_CONTEXT@@_K1@Z; EtwpProcessBufferStreamTrace(_TRACELOG_CONTEXT *,unsigned __int64,unsigned __int64)
  ... truncated ...
```
