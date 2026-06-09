# VidMmDemoteAllocationsToFitGlobalAlloc

- ea: `0x14010cce8`
- end: `0x14010d42e`
- name: `VidMmDemoteAllocationsToFitGlobalAlloc`
- size: `1862`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14010ca48`

## callees

- `0x1400a5b68`
- `0x1400fb87c`
- `0x1400ff470`
- `0x14010307c`
- `0x1401088d0`
- `0x14010cce8`
- `0x1401103ac`

## import_xrefs

- `ntoskrnl!PsIsSystemProcess` at `0x14010d019`
- `ntoskrnl!PsIsSystemProcess` at `0x14010d019`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14010d376`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14010d376`
- `ntoskrnl!DbgPrintEx` at `0x14010d399`
- `ntoskrnl!DbgPrintEx` at `0x14010d3c0`
- `ntoskrnl!DbgPrintEx` at `0x14010d399`
- `ntoskrnl!DbgPrintEx` at `0x14010d3c0`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010cf2d`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010cfaa`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010d06c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010d0e7`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010d22b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010d295`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010d303`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010cf2d`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010cfaa`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010d06c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010d0e7`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010d22b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010d295`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010d303`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14010cf1f`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14010cf9e`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14010d060`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14010d0db`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14010d21c`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14010d286`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14010d2f2`

## string_xrefs

- `0x14010d3b6`: `\nWe broke into the debugger to allow a chance for debugging this issue.\n\nTo disable debug breaks on high priority allocation page-in failures, run "?? dxgmms2!g_DemotedHighPriAllocDebugMode=1"\nor "ed 0x%p 1"\nTo re-attempt the suspend attempt for debugging purposes, run "?? dxgmms2!g_DemotedHighPriAllocDebugMode=2"\nor "ed 0x%p 2"\n\n`

## pseudocode

```c
char VidMmDemoteAllocationsToFitGlobalAlloc(union _LARGE_INTEGER *a1, _DWORD *a2, __int64 a3, ...)
{
  LONGLONG QuadPart; // r15
  __int64 v4; // r13
  _DWORD *v5; // rbx
  __int64 v6; // r9
  int v7; // r10d
  int v8; // ecx
  char v9; // al
  __int16 v10; // r8
  unsigned __int16 v11; // r8
  unsigned int v12; // eax
  __int64 v13; // r14
  int v14; // edx
  __int64 v15; // r10
  _QWORD *v16; // rdi
  unsigned int v17; // r12d
  __int64 v18; // rsi
  unsigned int v19; // eax
  unsigned int v20; // edi
  __int64 v21; // rdx
  _DWORD *v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r10
  __int16 v25; // r11
  _QWORD **v26; // r15
  _QWORD *v27; // rax
  __int64 v28; // rbx
  _QWORD *v29; // r14
  __int64 v30; // rax
  __int64 v31; // r9
  __int64 v32; // rax
  _QWORD *v33; // rbx
  __int64 v34; // rcx
  _QWORD *v35; // rax
  __int64 v36; // rdi
  _QWORD *v37; // r15
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rax
  _QWORD *v45; // rax
  _QWORD *v46; // rcx
  _QWORD *v47; // rax
  __int64 v48; // rdx
  unsigned __int64 v49; // rbx
  __int64 v50; // rax
  __int64 v51; // rdx
  unsigned __int64 LargestGap; // rbx
  __int64 v53; // rax
  __int64 v55; // rdx
  unsigned __int64 v56; // rbx
  _QWORD *v57; // rax
  __int64 v58; // [rsp+28h] [rbp-91h]
  int v59; // [rsp+58h] [rbp-61h]
  int v60; // [rsp+5Ch] [rbp-5Dh]
  unsigned int v61; // [rsp+60h] [rbp-59h]
  bool v62; // [rsp+64h] [rbp-55h]
  unsigned __int16 v63; // [rsp+68h] [rbp-51h]
  unsigned int v64; // [rsp+6Ch] [rbp-4Dh] BYREF
  unsigned int v65; // [rsp+70h] [rbp-49h]
  _QWORD *v66; // [rsp+78h] [rbp-41h]
  LONGLONG v67; // [rsp+80h] [rbp-39h]
  __int64 v68; // [rsp+88h] [rbp-31h] BYREF
  __int64 v69; // [rsp+90h] [rbp-29h]
  unsigned int v70; // [rsp+98h] [rbp-21h]
  _DWORD v71[2]; // [rsp+A0h] [rbp-19h]
  _QWORD *v72; // [rsp+A8h] [rbp-11h]
  _BYTE v73[88]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int16 v74; // [rsp+118h] [rbp+5Fh]
  __int64 v77; // [rsp+130h] [rbp+77h] BYREF
  va_list va; // [rsp+130h] [rbp+77h]
  __int64 v79; // [rsp+138h] [rbp+7Fh]
  va_list va1; // [rsp+140h] [rbp+87h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v77 = va_arg(va1, _QWORD);
  v79 = va_arg(va1, _QWORD);
  QuadPart = a1->QuadPart;
  v4 = *(_QWORD *)a2;
  v5 = a2;
  v67 = a1->QuadPart;
  VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR::VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR(
    (VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR *)v73,
    a1 + 43,
    (unsigned int *)&a1[48].HighPart,
    1);
  v59 = *(_DWORD *)(v4 + 40);
  if ( !v59 )
  {
LABEL_92:
    VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR::~VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR((VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR *)v73);
    return 0;
  }
  v7 = *(_DWORD *)(v4 + 40);
  v8 = 0;
  v60 = 0;
  LOWORD(v6) = *(_DWORD *)(v4 + 48) == 0 ? 6 : 0;
  v74 = v6;
  while ( 1 )
  {
    if ( (unsigned __int16)v6 <= 5u )
    {
      v9 = v6;
      LOWORD(v6) = v6 + 1;
      v74 = v6;
      v10 = (*(_DWORD *)(v4 + 48) >> (6 * v9)) & 0x1F;
      if ( v10 )
      {
        v11 = v10 - 1;
        v63 = v11;
        v62 = ((*(_DWORD *)(v4 + 48) >> (6 * v6)) & 0x20) == 0;
        goto LABEL_8;
      }
LABEL_90:
      v8 = v60;
      goto LABEL_91;
    }
    v11 = v8;
    v12 = (unsigned __int8)v8;
    LOWORD(v8) = v8 + 1;
    v63 = v11;
    v60 = v8;
    if ( _bittest(&v7, v12) )
      break;
LABEL_91:
    if ( !v7 )
      goto LABEL_92;
  }
  v62 = 1;
LABEL_8:
  v59 &= ~(1 << v11);
  v13 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(QuadPart + 36480)
                                          + 8
                                          * (((unsigned __int64)*(unsigned int *)(*(_QWORD *)v5 + 60LL) >> 2) & 0x3F))
                              + 2280LL)
                  + 8LL * v11);
  v69 = v13;
  if ( *(_DWORD *)(v13 + 108) != 1 )
  {
LABEL_89:
    v7 = v59;
    goto LABEL_90;
  }
  v14 = 0;
  v15 = a3;
  v61 = 0;
  if ( (v5[6] & 4) != 0 )
  {
    if ( (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 136LL) & 2) == 0 )
      v14 = 7;
    v61 = v14;
  }
  v16 = (_QWORD *)(v13 + 112);
  v66 = (_QWORD *)(v13 + 112);
  while ( 2 )
  {
    v17 = 2013265919;
    v18 = *(_QWORD *)(v4 + 16) + (*(_QWORD *)(v4 + 16) >> 2);
    v68 = v18;
LABEL_15:
    v19 = (*(unsigned __int8 *)(v15 + 58) >> 4) & 1;
    v64 = 0;
    v65 = v19;
    v71[0] = 0;
    v71[1] = 2;
LABEL_16:
    v70 = v71[v19];
    if ( v70 != 2 )
    {
      v33 = (_QWORD *)*v16;
      if ( (_QWORD *)*v16 != v16 )
      {
        while ( 1 )
        {
          v34 = *(v33 - 3);
          v72 = (_QWORD *)*v33;
          if ( !(unsigned __int8)PsIsSystemProcess(*(_QWORD *)(v34 + 16)) )
          {
            v35 = (_QWORD *)v33[2];
            if ( v35 != v33 + 2 )
              break;
          }
LABEL_54:
          v33 = v72;
          if ( v72 == v16 )
          {
            v5 = a2;
            v13 = v69;
            goto LABEL_58;
          }
        }
        while ( 1 )
        {
          v36 = v35[4];
          LOBYTE(v6) = v79;
          v37 = (_QWORD *)*v35;
          if ( (unsigned __int8)VIDMM_DEVICE::CanSuspendThisDevice(v36, a3, v70, v6) )
          {
            if ( g_IsInternalReleaseOrDbg )
            {
              *(_QWORD *)(WdLogNewEntry5_WdTrace(v39, v38) + 24) = v36;
              WdLogGlobalForLineNumber = 2600;
            }
            LOBYTE(v77) = 0;
            v41 = *(_DWORD *)(*(_QWORD *)a2 + 60LL) >> 2;
            LOWORD(v41) = v41 & 0x3F;
            LOWORD(v58) = v63;
            VIDMM_DEVICE::FaultAllDemotableAllocations(v36, v38, v40, v41, v58, v61, v17, &v64, &v68, (__int64 *)va);
            if ( !(_BYTE)v77 )
              goto LABEL_50;
            if ( g_IsInternalReleaseOrDbg )
            {
              v44 = WdLogNewEntry5_WdTrace(v43, v42);
              *(_QWORD *)(v44 + 24) = v36;
              *(_QWORD *)(v44 + 32) = v17;
              WdLogGlobalForLineNumber = 2617;
            }
            v45 = (_QWORD *)*v33;
            if ( *v33 )
            {
              if ( (_QWORD *)v45[1] != v33
                || (v46 = (_QWORD *)v33[1], (_QWORD *)*v46 != v33)
                || (v16 = v66, *v46 = v45, v45[1] = v46, v47 = (_QWORD *)v16[1], (_QWORD *)*v47 != v16) )
              {
                __fastfail(3u);
              }
              *v33 = v16;
              v33[1] = v47;
              *v47 = v33;
              v16[1] = v33;
            }
            else
            {
LABEL_50:
              v16 = v66;
            }
            v18 = v68;
            if ( !v68 )
              break;
          }
          v35 = v37;
          if ( v37 == v33 + 2 )
          {
            v16 = v66;
            goto LABEL_54;
          }
        }
        v13 = v69;
        LOBYTE(v6) = v62;
        LargestGap = VIDMM_SEGMENT::GetLargestGap(v69, a2, v61, v6);
        if ( g_IsInternalReleaseOrDbg )
        {
          v53 = WdLogNewEntry5_WdTrace(*(_QWORD *)&g_IsInternalReleaseOrDbg, v51);
          *(_QWORD *)(v53 + 24) = LargestGap;
          *(_QWORD *)(v53 + 32) = *(_QWORD *)(v4 + 16);
          WdLogGlobalForLineNumber = 2649;
        }
        if ( LargestGap >= *(_QWORD *)(v4 + 16) )
          goto LABEL_75;
LABEL_71:
        v5 = a2;
        v15 = a3;
        QuadPart = v67;
        continue;
      }
      v5 = a2;
LABEL_59:
      v15 = a3;
      v19 = v65 + 1;
      v65 = v19;
      if ( v19 >= 2 )
      {
        if ( v64 - 1 > 0xC7FFFFFE )
          goto LABEL_76;
        if ( v17 == 2013265919 )
        {
          v17 = -939524097;
          if ( v64 <= 0x9FFFFFFF )
            v17 = -1610612737;
          goto LABEL_15;
        }
        if ( v17 == -1610612737 )
        {
          v15 = a3;
          v17 = -939524097;
          goto LABEL_15;
        }
LABEL_76:
        if ( v18 != *(_QWORD *)(v4 + 16) + (*(_QWORD *)(v4 + 16) >> 2) )
        {
          LOBYTE(v6) = v62;
          v56 = VIDMM_SEGMENT::GetLargestGap(v13, v5, 0, v6);
          if ( g_IsInternalReleaseOrDbg )
          {
            v57 = (_QWORD *)WdLogNewEntry5_WdTrace(*(_QWORD *)&g_IsInternalReleaseOrDbg, v55);
            v57[3] = v13;
            v57[4] = v56;
            v57[5] = *(_QWORD *)(v4 + 16);
            WdLogGlobalForLineNumber = 2743;
          }
          if ( v56 >= *(_QWORD *)(v4 + 16) )
            goto LABEL_75;
        }
        v5 = a2;
        if ( (VIDMM_GLOBAL::_Config & 0x40) == 0
          || (_BYTE)v79 == 2
          || *(_DWORD *)(v4 + 56) < 0xA0000000 && (a2[6] & 1) != 0
          || !dword_140086644
          || g_DemotedHighPriAllocDebugMode
          || KdRefreshDebuggerNotPresent()
          || (DbgPrintEx(0x65u, 0, "\nCouldn't find preferred memory for a high priority allocation 0x%p.\n", a2),
              DbgPrintEx(
                0x65u,
                0,
                "\n"
                "We broke into the debugger to allow a chance for debugging this issue.\n"
                "\n"
                "To disable debug breaks on high priority allocation page-in failures, run \"?? dxgmms2!g_DemotedHighPriA"
                "llocDebugMode=1\"\n"
                "or \"ed 0x%p 1\"\n"
                "To re-attempt the suspend attempt for debugging purposes, run \"?? dxgmms2!g_DemotedHighPriAllocDebugMod"
                "e=2\"\n"
                "or \"ed 0x%p 2\"\n"
                "\n",
                (const void *)&g_DemotedHighPriAllocDebugMode,
                (const void *)&g_DemotedHighPriAllocDebugMode),
              __debugbreak(),
              v15 = a3,
              g_DemotedHighPriAllocDebugMode != 2) )
        {
          v6 = v74;
          goto LABEL_89;
        }
        continue;
      }
      goto LABEL_16;
    }
    break;
  }
  v20 = v17;
  if ( (v5[6] & 1) != 0 && v17 >= *(_DWORD *)(v4 + 56) - 1 )
    v20 = *(_DWORD *)(v4 + 56) - 1;
  v26 = (_QWORD **)((char *)VIDMM_PROCESS::GetCommitmentInformation(
                              *(VIDMM_PROCESS **)(v15 + 8),
                              *(_DWORD *)(*(_QWORD *)(QuadPart + 24) + 240LL),
                              *(_WORD *)(v13 + 68),
                              *(_WORD *)(v13 + 70))
                  + 40);
  v27 = *v26;
  if ( *v26 == v26 )
  {
    v16 = (_QWORD *)(v13 + 112);
LABEL_58:
    QuadPart = v67;
    goto LABEL_59;
  }
  while ( 1 )
  {
    v28 = v27[4];
    v29 = (_QWORD *)*v27;
    if ( v28 == v24 )
    {
      if ( (VIDMM_GLOBAL::_Config & 0x40) == 0 )
        goto LABEL_34;
      v22 = a2;
      if ( *(_DWORD *)(*(_QWORD *)a2 + 56LL) < 0xA0000000 && (a2[6] & 1) != 0 )
        goto LABEL_34;
    }
    if ( (*(_BYTE *)(v24 + 58) & 0x10) != 0 && v28 != v24 )
      goto LABEL_34;
    if ( g_IsInternalReleaseOrDbg )
    {
      v30 = WdLogNewEntry5_WdTrace(v22, v21);
      v25 = 63;
      *(_QWORD *)(v30 + 24) = v28;
      WdLogGlobalForLineNumber = 2511;
    }
    LOBYTE(v77) = 0;
    v31 = *(_DWORD *)(*(_QWORD *)a2 + 60LL) >> 2;
    LOWORD(v31) = v25 & v31;
    LOWORD(v58) = v63;
    VIDMM_DEVICE::FaultAllDemotableAllocations(v28, v21, v23, v31, v58, v61, v20, &v64, &v68, (__int64 *)va);
    if ( (_BYTE)v77 && g_IsInternalReleaseOrDbg )
    {
      v32 = WdLogNewEntry5_WdTrace(v22, v21);
      v22 = (_DWORD *)v20;
      *(_QWORD *)(v32 + 24) = v28;
      *(_QWORD *)(v32 + 32) = v20;
      WdLogGlobalForLineNumber = 2529;
    }
    v18 = v68;
    if ( !v68 )
      break;
    v24 = a3;
    v25 = 63;
LABEL_34:
    v27 = v29;
    if ( v29 == v26 )
    {
      v5 = a2;
      v13 = v69;
      v16 = v66;
      goto LABEL_58;
    }
  }
  v13 = v69;
  LOBYTE(v6) = v62;
  v49 = VIDMM_SEGMENT::GetLargestGap(v69, a2, v61, v6);
  if ( g_IsInternalReleaseOrDbg )
  {
    v50 = WdLogNewEntry5_WdTrace(*(_QWORD *)&g_IsInternalReleaseOrDbg, v48);
    *(_QWORD *)(v50 + 24) = v49;
    *(_QWORD *)(v50 + 32) = *(_QWORD *)(v4 + 16);
    WdLogGlobalForLineNumber = 2545;
  }
  if ( v49 < *(_QWORD *)(v4 + 16) )
  {
    v16 = (_QWORD *)(v13 + 112);
    goto LABEL_71;
  }
LABEL_75:
  VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR::~VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR((VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR *)v73);
  return 1;
}

```

## disassembly

```asm
0x14010cce8  mov     rax, rsp
0x14010cceb  mov     [rax+20h], r9
0x14010ccef  mov     [rax+18h], r8
0x14010ccf3  mov     [rax+10h], rdx
0x14010ccf7  push    rbp
0x14010ccf8  push    rbx
0x14010ccf9  push    rsi
0x14010ccfa  push    rdi
0x14010ccfb  push    r12
0x14010ccfd  push    r13
0x14010ccff  push    r14
0x14010cd01  push    r15
0x14010cd03  lea     rbp, [rax-57h]
0x14010cd07  sub     rsp, 0C8h
0x14010cd0e  mov     r15, [rcx]
0x14010cd11  lea     r8, [rcx+184h]; unsigned int *
0x14010cd18  mov     r13, [rdx]
0x14010cd1b  mov     rbx, rdx
0x14010cd1e  lea     rdx, [rcx+158h]; union _LARGE_INTEGER *
0x14010cd25  mov     [rbp+4Fh+var_88], r15
0x14010cd29  mov     edi, 1
0x14010cd2e  lea     rcx, [rbp+4Fh+var_58]; this
0x14010cd32  mov     r9b, dil; bool
0x14010cd35  call    ??0VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR@@QEAA@PEAT_LARGE_INTEGER@@PEAI_N@Z; VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR::VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR(_LARGE_INTEGER *,uint *,bool)
0x14010cd3a  mov     eax, [r13+28h]
0x14010cd3e  xor     esi, esi
0x14010cd40  mov     [rbp+4Fh+var_B0], eax
0x14010cd43  test    eax, eax
0x14010cd45  jz      loc_14010D407
0x14010cd4b  mov     eax, [r13+30h]
0x14010cd4f  lea     r11d, [rdi+3Eh]
0x14010cd53  mov     r10d, [rbp+4Fh+var_B0]
0x14010cd57  neg     eax
0x14010cd59  mov     ecx, esi
0x14010cd5b  sbb     r9w, r9w
0x14010cd5f  mov     [rbp+4Fh+var_AC], ecx
0x14010cd62  not     r9w
0x14010cd66  and     r9w, 6
0x14010cd6b  mov     [rbp+4Fh+arg_0], r9w
0x14010cd70  cmp     r9w, 5
0x14010cd75  ja      short loc_14010CDBE
0x14010cd77  mov     edx, [r13+30h]
0x14010cd7b  mov     r8d, edx
0x14010cd7e  movzx   eax, r9w
0x14010cd82  add     r9w, di
0x14010cd86  mov     [rbp+4Fh+arg_0], r9w
0x14010cd8b  lea     ecx, [rax+rax*2]
0x14010cd8e  movzx   eax, r9w
0x14010cd92  add     ecx, ecx
0x14010cd94  shr     r8d, cl
0x14010cd97  and     r8w, 1Fh
0x14010cd9c  jz      loc_14010D3FB
0x14010cda2  sub     r8w, di
0x14010cda6  lea     ecx, [rax+rax*2]
0x14010cda9  add     ecx, ecx
0x14010cdab  mov     [rbp+4Fh+var_A0], r8d
0x14010cdaf  shr     edx, cl
0x14010cdb1  shr     edx, 5
0x14010cdb4  not     dl
0x14010cdb6  and     dl, dil
0x14010cdb9  mov     [rbp+4Fh+var_A4], edx
0x14010cdbc  jmp     short loc_14010CDDD
0x14010cdbe  movzx   r8d, cx
0x14010cdc2  movzx   eax, cl
0x14010cdc5  add     cx, di
0x14010cdc8  mov     [rbp+4Fh+var_A0], r8d
0x14010cdcc  bt      r10d, eax
0x14010cdd0  mov     [rbp+4Fh+var_AC], ecx
0x14010cdd3  jnb     loc_14010D3FE
0x14010cdd9  mov     byte ptr [rbp+4Fh+var_A4], dil
0x14010cddd  mov     cl, r8b
0x14010cde0  mov     eax, edi
0x14010cde2  shl     eax, cl
0x14010cde4  not     eax
0x14010cde6  and     [rbp+4Fh+var_B0], eax
0x14010cde9  mov     rax, [rbx]
0x14010cdec  mov     ecx, [rax+3Ch]
0x14010cdef  mov     rax, [r15+8E80h]
0x14010cdf6  shr     rcx, 2
0x14010cdfa  and     rcx, r11
0x14010cdfd  mov     rax, [rax+rcx*8]
0x14010ce01  movzx   ecx, r8w
0x14010ce05  mov     rax, [rax+8E8h]
0x14010ce0c  mov     r14, [rax+rcx*8]
0x14010ce10  mov     [rbp+4Fh+var_78], r14
0x14010ce14  cmp     [r14+6Ch], edi
0x14010ce18  jnz     loc_14010D3F7
0x14010ce1e  mov     eax, [rbx+18h]
0x14010ce21  xor     edx, edx
0x14010ce23  mov     r10, [rbp+4Fh+arg_10]
0x14010ce27  mov     [rbp+4Fh+var_A8], edx
0x14010ce2a  test    al, 4
0x14010ce2c  jz      short loc_14010CE42
0x14010ce2e  mov     rax, [r10+8]
0x14010ce32  test    byte ptr [rax+88h], 2
0x14010ce39  lea     eax, [rdx+7]
0x14010ce3c  cmovz   edx, eax
0x14010ce3f  mov     [rbp+4Fh+var_A8], edx
0x14010ce42  lea     rdi, [r14+70h]
0x14010ce46  mov     [rbp+4Fh+var_90], rdi
0x14010ce4a  mov     rax, [r13+10h]
0x14010ce4e  mov     r12d, 77FFFFFFh
0x14010ce54  mov     rsi, rax
0x14010ce57  shr     rsi, 2
0x14010ce5b  add     rsi, rax
0x14010ce5e  mov     [rbp+4Fh+var_80], rsi
0x14010ce62  movzx   eax, byte ptr [r10+3Ah]
0x14010ce67  shr     eax, 4
0x14010ce6a  and     eax, 1
0x14010ce6d  mov     [rbp+4Fh+var_9C], 0
0x14010ce74  mov     [rbp+4Fh+var_98], eax
0x14010ce77  mov     [rbp+4Fh+var_68], 0
0x14010ce7e  mov     [rbp+4Fh+var_64], 2
0x14010ce85  cdqe
0x14010ce87  mov     eax, [rbp+rax*4+4Fh+var_68]
0x14010ce8b  mov     [rbp+4Fh+var_70], eax
0x14010ce8e  cmp     eax, 2
0x14010ce91  jnz     loc_14010CFFE
0x14010ce97  mov     eax, [rbx+18h]
0x14010ce9a  mov     edi, r12d
0x14010ce9d  test    al, 1
0x14010ce9f  jz      short loc_14010CEAD
0x14010cea1  mov     eax, [r13+38h]
0x14010cea5  dec     eax
0x14010cea7  cmp     r12d, eax
0x14010ceaa  cmovnb  edi, eax
0x14010cead  mov     rdx, [r15+18h]
0x14010ceb1  movzx   r9d, word ptr [r14+46h]; unsigned __int16
0x14010ceb6  movzx   r8d, word ptr [r14+44h]; unsigned __int16
0x14010cebb  mov     rcx, [r10+8]; this
0x14010cebf  mov     edx, [rdx+0F0h]; unsigned int
0x14010cec5  call    ?GetCommitmentInformation@VIDMM_PROCESS@@QEAAPEAUVIDMM_PROCESS_COMMITMENT_INFO@@IGG@Z; VIDMM_PROCESS::GetCommitmentInformation(uint,ushort,ushort)
0x14010ceca  lea     r15, [rax+28h]
0x14010cece  mov     rax, [r15]
0x14010ced1  cmp     rax, r15
0x14010ced4  jz      loc_14010D18D
0x14010ceda  mov     rbx, [rax+20h]
0x14010cede  mov     r14, [rax]
0x14010cee1  cmp     rbx, r10
0x14010cee4  jnz     short loc_14010CF0F
0x14010cee6  mov     eax, cs:?_Config@VIDMM_GLOBAL@@2U_VIDMM_CONFIGURATION@@A; _VIDMM_CONFIGURATION VIDMM_GLOBAL::_Config
0x14010ceec  test    al, 40h
0x14010ceee  jz      loc_14010CFE1
0x14010cef4  mov     rcx, [rbp+4Fh+arg_8]
0x14010cef8  mov     rax, [rcx]
0x14010cefb  cmp     dword ptr [rax+38h], 0A0000000h
0x14010cf02  jnb     short loc_14010CF0F
0x14010cf04  mov     eax, [rcx+18h]
0x14010cf07  test    al, 1
0x14010cf09  jnz     loc_14010CFE1
0x14010cf0f  test    byte ptr [r10+3Ah], 10h
0x14010cf14  jz      short loc_14010CF1F
0x14010cf16  cmp     rbx, r10
0x14010cf19  jnz     loc_14010CFE1
0x14010cf1f  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x14010cf26  xor     esi, esi
0x14010cf28  cmp     [rax], sil
0x14010cf2b  jz      short loc_14010CF4B
0x14010cf2d  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14010cf34  nop     dword ptr [rax+rax+00h]
0x14010cf39  lea     r11d, [rsi+3Fh]
0x14010cf3d  mov     [rax+18h], rbx
0x14010cf41  mov     cs:WdLogGlobalForLineNumber, 9CFh
0x14010cf4b  mov     rax, [rbp+4Fh+arg_8]
0x14010cf4f  mov     rcx, rbx
0x14010cf52  mov     byte ptr [rbp+4Fh+arg_18], sil
0x14010cf56  mov     rax, [rax]
0x14010cf59  mov     r9d, [rax+3Ch]
0x14010cf5d  lea     rax, [rbp+4Fh+arg_18]
0x14010cf61  mov     [rsp+48h], rax
0x14010cf66  lea     rax, [rbp+4Fh+var_80]
0x14010cf6a  mov     [rsp+100h+var_C0], rax
0x14010cf6f  lea     rax, [rbp+4Fh+var_9C]
0x14010cf73  mov     [rsp+100h+var_C8], rax
0x14010cf78  mov     eax, [rbp+4Fh+var_A8]
0x14010cf7b  mov     dword ptr [rsp+100h+var_D0], edi
0x14010cf7f  mov     [rsp+100h+var_D8], eax
0x14010cf83  mov     eax, [rbp+4Fh+var_A0]
0x14010cf86  shr     r9d, 2
0x14010cf8a  and     r9w, r11w
0x14010cf8e  mov     word ptr [rsp+100h+var_E0], ax
0x14010cf93  call    ?FaultAllDemotableAllocations@VIDMM_DEVICE@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEBV1@GGW4VIDMM_PLACEMENT_RESTRICTION@@IPEAIPEA_KPEA_N@Z; VIDMM_DEVICE::FaultAllDemotableAllocations(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_DEVICE const *,ushort,ushort,VIDMM_PLACEMENT_RESTRICTION,uint,uint *,unsigned __int64 *,bool *)
0x14010cf98  cmp     byte ptr [rbp+4Fh+arg_18], sil
0x14010cf9c  jz      short loc_14010CFCA
0x14010cf9e  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x14010cfa5  cmp     [rax], sil
0x14010cfa8  jz      short loc_14010CFCA
0x14010cfaa  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14010cfb1  nop     dword ptr [rax+rax+00h]
0x14010cfb6  mov     ecx, edi
0x14010cfb8  mov     [rax+18h], rbx
0x14010cfbc  mov     [rax+20h], rcx
0x14010cfc0  mov     cs:WdLogGlobalForLineNumber, 9E1h
0x14010cfca  mov     rsi, [rbp+4Fh+var_80]
0x14010cfce  test    rsi, rsi
0x14010cfd1  jz      loc_14010D204
0x14010cfd7  mov     r10, [rbp+4Fh+arg_10]
0x14010cfdb  mov     r11d, 3Fh ; '?'
0x14010cfe1  mov     rax, r14
0x14010cfe4  cmp     r14, r15
0x14010cfe7  jnz     loc_14010CEDA
0x14010cfed  mov     rbx, [rbp+4Fh+arg_8]
0x14010cff1  mov     r14, [rbp+4Fh+var_78]
0x14010cff5  mov     rdi, [rbp+4Fh+var_90]
0x14010cff9  jmp     loc_14010D191
0x14010cffe  mov     rbx, [rdi]
0x14010d001  cmp     rbx, rdi
0x14010d004  jz      loc_14010D187
0x14010d00a  mov     rcx, [rbx-18h]
0x14010d00e  mov     rax, [rbx]
0x14010d011  mov     [rbp+4Fh+var_60], rax
0x14010d015  mov     rcx, [rcx+10h]
0x14010d019  call    cs:__imp_PsIsSystemProcess
0x14010d020  nop     dword ptr [rax+rax+00h]
0x14010d025  test    al, al
0x14010d027  jnz     loc_14010D170
0x14010d02d  lea     r14, [rbx+10h]
0x14010d031  mov     rax, [r14]
0x14010d034  cmp     rax, r14
0x14010d037  jz      loc_14010D170
0x14010d03d  mov     rdi, [rax+20h]
0x14010d041  mov     r9b, byte ptr [rbp+4Fh+arg_20]
0x14010d045  mov     rcx, rdi
0x14010d048  mov     r8d, [rbp+4Fh+var_70]
0x14010d04c  mov     rdx, [rbp+4Fh+arg_10]
0x14010d050  mov     r15, [rax]
0x14010d053  call    ?CanSuspendThisDevice@VIDMM_DEVICE@@QEAA_NPEBV1@W4VIDMM_SUSPEND_CANDIDATE_PASS@@W4VIDMM_BUDGET_PRIORITY_BAND@@@Z; VIDMM_DEVICE::CanSuspendThisDevice(VIDMM_DEVICE const *,VIDMM_SUSPEND_CANDIDATE_PASS,VIDMM_BUDGET_PRIORITY_BAND)
0x14010d058  test    al, al
0x14010d05a  jz      loc_14010D160
0x14010d060  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x14010d067  cmp     byte ptr [rax], 0
0x14010d06a  jz      short loc_14010D086
0x14010d06c  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14010d073  nop     dword ptr [rax+rax+00h]
0x14010d078  mov     [rax+18h], rdi
0x14010d07c  mov     cs:WdLogGlobalForLineNumber, 0A28h
0x14010d086  mov     rax, [rbp+4Fh+arg_8]
0x14010d08a  mov     rcx, rdi
0x14010d08d  mov     byte ptr [rbp+4Fh+arg_18], 0
0x14010d091  mov     rax, [rax]
0x14010d094  mov     r9d, [rax+3Ch]
0x14010d098  lea     rax, [rbp+4Fh+arg_18]
0x14010d09c  mov     [rsp+48h], rax
0x14010d0a1  lea     rax, [rbp+4Fh+var_80]
0x14010d0a5  mov     [rsp+100h+var_C0], rax
0x14010d0aa  lea     rax, [rbp+4Fh+var_9C]
0x14010d0ae  mov     [rsp+100h+var_C8], rax
0x14010d0b3  mov     eax, [rbp+4Fh+var_A8]
0x14010d0b6  mov     dword ptr [rsp+100h+var_D0], r12d
0x14010d0bb  mov     [rsp+100h+var_D8], eax
0x14010d0bf  mov     eax, [rbp+4Fh+var_A0]
0x14010d0c2  shr     r9d, 2
0x14010d0c6  and     r9w, 3Fh
0x14010d0cb  mov     word ptr [rsp+100h+var_E0], ax
0x14010d0d0  call    ?FaultAllDemotableAllocations@VIDMM_DEVICE@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEBV1@GGW4VIDMM_PLACEMENT_RESTRICTION@@IPEAIPEA_KPEA_N@Z; VIDMM_DEVICE::FaultAllDemotableAllocations(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_DEVICE const *,ushort,ushort,VIDMM_PLACEMENT_RESTRICTION,uint,uint *,unsigned __int64 *,bool *)
0x14010d0d5  cmp     byte ptr [rbp+4Fh+arg_18], 0
0x14010d0d9  jz      short loc_14010D14F
0x14010d0db  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x14010d0e2  cmp     byte ptr [rax], 0
0x14010d0e5  jz      short loc_14010D108
0x14010d0e7  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14010d0ee  nop     dword ptr [rax+rax+00h]
0x14010d0f3  mov     ecx, r12d
0x14010d0f6  mov     [rax+18h], rdi
0x14010d0fa  mov     [rax+20h], rcx
0x14010d0fe  mov     cs:WdLogGlobalForLineNumber, 0A39h
0x14010d108  mov     rax, [rbx]
0x14010d10b  test    rax, rax
0x14010d10e  jz      short loc_14010D14F
0x14010d110  cmp     [rax+8], rbx
0x14010d114  jnz     loc_14010D427
0x14010d11a  mov     rcx, [rbx+8]
0x14010d11e  cmp     [rcx], rbx
0x14010d121  jnz     loc_14010D427
0x14010d127  mov     rdi, [rbp+4Fh+var_90]
0x14010d12b  mov     [rcx], rax
0x14010d12e  mov     [rax+8], rcx
0x14010d132  mov     rax, [rdi+8]
0x14010d136  cmp     [rax], rdi
0x14010d139  jnz     loc_14010D427
0x14010d13f  mov     [rbx], rdi
0x14010d142  mov     [rbx+8], rax
0x14010d146  mov     [rax], rbx
0x14010d149  mov     [rdi+8], rbx
0x14010d14d  jmp     short loc_14010D153
0x14010d14f  mov     rdi, [rbp+4Fh+var_90]
0x14010d153  mov     rsi, [rbp+4Fh+var_80]
0x14010d157  test    rsi, rsi
0x14010d15a  jz      loc_14010D26E
0x14010d160  mov     rax, r15
0x14010d163  cmp     r15, r14
0x14010d166  jnz     loc_14010D03D
0x14010d16c  mov     rdi, [rbp+4Fh+var_90]
0x14010d170  mov     rbx, [rbp+4Fh+var_60]
0x14010d174  cmp     rbx, rdi
0x14010d177  jnz     loc_14010D00A
0x14010d17d  mov     rbx, [rbp+4Fh+arg_8]
0x14010d181  mov     r14, [rbp+4Fh+var_78]
0x14010d185  jmp     short loc_14010D191
0x14010d187  mov     rbx, [rbp+4Fh+arg_8]
  ... truncated ...
```
