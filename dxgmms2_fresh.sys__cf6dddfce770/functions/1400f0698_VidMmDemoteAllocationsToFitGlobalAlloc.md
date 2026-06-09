# VidMmDemoteAllocationsToFitGlobalAlloc

- ea: `0x1400f0698`
- end: `0x1400f0dde`
- name: `VidMmDemoteAllocationsToFitGlobalAlloc`
- size: `1862`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400f03f8`

## callees

- `0x1400a63f8`
- `0x1400f0698`
- `0x1401066fc`
- `0x140108f30`
- `0x14010aec8`
- `0x14010cd7c`
- `0x140112b4c`

## import_xrefs

- `ntoskrnl!PsIsSystemProcess` at `0x1400f09c9`
- `ntoskrnl!PsIsSystemProcess` at `0x1400f09c9`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400f0d26`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400f0d26`
- `ntoskrnl!DbgPrintEx` at `0x1400f0d49`
- `ntoskrnl!DbgPrintEx` at `0x1400f0d70`
- `ntoskrnl!DbgPrintEx` at `0x1400f0d49`
- `ntoskrnl!DbgPrintEx` at `0x1400f0d70`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f08dd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f095a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f0a1c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f0a97`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f0bdb`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f0c45`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f0cb3`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f08dd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f095a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f0a1c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f0a97`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f0bdb`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f0c45`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f0cb3`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f08cf`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f094e`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f0a10`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f0a8b`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f0bcc`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f0c36`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f0ca2`

## string_xrefs

- `0x1400f0d66`: `\nWe broke into the debugger to allow a chance for debugging this issue.\n\nTo disable debug breaks on high priority allocation page-in failures, run "?? dxgmms2!g_DemotedHighPriAllocDebugMode=1"\nor "ed 0x%p 1"\nTo re-attempt the suspend attempt for debugging purposes, run "?? dxgmms2!g_DemotedHighPriAllocDebugMode=2"\nor "ed 0x%p 2"\n\n`

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
                              + 2544LL)
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
    if ( (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 144LL) & 2) == 0 )
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
          || !dword_140087614
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
0x1400f0698  mov     rax, rsp
0x1400f069b  mov     [rax+20h], r9
0x1400f069f  mov     [rax+18h], r8
0x1400f06a3  mov     [rax+10h], rdx
0x1400f06a7  push    rbp
0x1400f06a8  push    rbx
0x1400f06a9  push    rsi
0x1400f06aa  push    rdi
0x1400f06ab  push    r12
0x1400f06ad  push    r13
0x1400f06af  push    r14
0x1400f06b1  push    r15
0x1400f06b3  lea     rbp, [rax-57h]
0x1400f06b7  sub     rsp, 0C8h
0x1400f06be  mov     r15, [rcx]
0x1400f06c1  lea     r8, [rcx+184h]; unsigned int *
0x1400f06c8  mov     r13, [rdx]
0x1400f06cb  mov     rbx, rdx
0x1400f06ce  lea     rdx, [rcx+158h]; union _LARGE_INTEGER *
0x1400f06d5  mov     [rbp+4Fh+var_88], r15
0x1400f06d9  mov     edi, 1
0x1400f06de  lea     rcx, [rbp+4Fh+var_58]; this
0x1400f06e2  mov     r9b, dil; bool
0x1400f06e5  call    ??0VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR@@QEAA@PEAT_LARGE_INTEGER@@PEAI_N@Z; VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR::VIDMM_WORKER_THREAD_PAGING_TIME_ACCUMULATOR(_LARGE_INTEGER *,uint *,bool)
0x1400f06ea  mov     eax, [r13+28h]
0x1400f06ee  xor     esi, esi
0x1400f06f0  mov     [rbp+4Fh+var_B0], eax
0x1400f06f3  test    eax, eax
0x1400f06f5  jz      loc_1400F0DB7
0x1400f06fb  mov     eax, [r13+30h]
0x1400f06ff  lea     r11d, [rdi+3Eh]
0x1400f0703  mov     r10d, [rbp+4Fh+var_B0]
0x1400f0707  neg     eax
0x1400f0709  mov     ecx, esi
0x1400f070b  sbb     r9w, r9w
0x1400f070f  mov     [rbp+4Fh+var_AC], ecx
0x1400f0712  not     r9w
0x1400f0716  and     r9w, 6
0x1400f071b  mov     [rbp+4Fh+arg_0], r9w
0x1400f0720  cmp     r9w, 5
0x1400f0725  ja      short loc_1400F076E
0x1400f0727  mov     edx, [r13+30h]
0x1400f072b  mov     r8d, edx
0x1400f072e  movzx   eax, r9w
0x1400f0732  add     r9w, di
0x1400f0736  mov     [rbp+4Fh+arg_0], r9w
0x1400f073b  lea     ecx, [rax+rax*2]
0x1400f073e  movzx   eax, r9w
0x1400f0742  add     ecx, ecx
0x1400f0744  shr     r8d, cl
0x1400f0747  and     r8w, 1Fh
0x1400f074c  jz      loc_1400F0DAB
0x1400f0752  sub     r8w, di
0x1400f0756  lea     ecx, [rax+rax*2]
0x1400f0759  add     ecx, ecx
0x1400f075b  mov     [rbp+4Fh+var_A0], r8d
0x1400f075f  shr     edx, cl
0x1400f0761  shr     edx, 5
0x1400f0764  not     dl
0x1400f0766  and     dl, dil
0x1400f0769  mov     [rbp+4Fh+var_A4], edx
0x1400f076c  jmp     short loc_1400F078D
0x1400f076e  movzx   r8d, cx
0x1400f0772  movzx   eax, cl
0x1400f0775  add     cx, di
0x1400f0778  mov     [rbp+4Fh+var_A0], r8d
0x1400f077c  bt      r10d, eax
0x1400f0780  mov     [rbp+4Fh+var_AC], ecx
0x1400f0783  jnb     loc_1400F0DAE
0x1400f0789  mov     byte ptr [rbp+4Fh+var_A4], dil
0x1400f078d  mov     cl, r8b
0x1400f0790  mov     eax, edi
0x1400f0792  shl     eax, cl
0x1400f0794  not     eax
0x1400f0796  and     [rbp+4Fh+var_B0], eax
0x1400f0799  mov     rax, [rbx]
0x1400f079c  mov     ecx, [rax+3Ch]
0x1400f079f  mov     rax, [r15+8E80h]
0x1400f07a6  shr     rcx, 2
0x1400f07aa  and     rcx, r11
0x1400f07ad  mov     rax, [rax+rcx*8]
0x1400f07b1  movzx   ecx, r8w
0x1400f07b5  mov     rax, [rax+9F0h]
0x1400f07bc  mov     r14, [rax+rcx*8]
0x1400f07c0  mov     [rbp+4Fh+var_78], r14
0x1400f07c4  cmp     [r14+6Ch], edi
0x1400f07c8  jnz     loc_1400F0DA7
0x1400f07ce  mov     eax, [rbx+18h]
0x1400f07d1  xor     edx, edx
0x1400f07d3  mov     r10, [rbp+4Fh+arg_10]
0x1400f07d7  mov     [rbp+4Fh+var_A8], edx
0x1400f07da  test    al, 4
0x1400f07dc  jz      short loc_1400F07F2
0x1400f07de  mov     rax, [r10+8]
0x1400f07e2  test    byte ptr [rax+90h], 2
0x1400f07e9  lea     eax, [rdx+7]
0x1400f07ec  cmovz   edx, eax
0x1400f07ef  mov     [rbp+4Fh+var_A8], edx
0x1400f07f2  lea     rdi, [r14+70h]
0x1400f07f6  mov     [rbp+4Fh+var_90], rdi
0x1400f07fa  mov     rax, [r13+10h]
0x1400f07fe  mov     r12d, 77FFFFFFh
0x1400f0804  mov     rsi, rax
0x1400f0807  shr     rsi, 2
0x1400f080b  add     rsi, rax
0x1400f080e  mov     [rbp+4Fh+var_80], rsi
0x1400f0812  movzx   eax, byte ptr [r10+3Ah]
0x1400f0817  shr     eax, 4
0x1400f081a  and     eax, 1
0x1400f081d  mov     [rbp+4Fh+var_9C], 0
0x1400f0824  mov     [rbp+4Fh+var_98], eax
0x1400f0827  mov     [rbp+4Fh+var_68], 0
0x1400f082e  mov     [rbp+4Fh+var_64], 2
0x1400f0835  cdqe
0x1400f0837  mov     eax, [rbp+rax*4+4Fh+var_68]
0x1400f083b  mov     [rbp+4Fh+var_70], eax
0x1400f083e  cmp     eax, 2
0x1400f0841  jnz     loc_1400F09AE
0x1400f0847  mov     eax, [rbx+18h]
0x1400f084a  mov     edi, r12d
0x1400f084d  test    al, 1
0x1400f084f  jz      short loc_1400F085D
0x1400f0851  mov     eax, [r13+38h]
0x1400f0855  dec     eax
0x1400f0857  cmp     r12d, eax
0x1400f085a  cmovnb  edi, eax
0x1400f085d  mov     rdx, [r15+18h]
0x1400f0861  movzx   r9d, word ptr [r14+46h]; unsigned __int16
0x1400f0866  movzx   r8d, word ptr [r14+44h]; unsigned __int16
0x1400f086b  mov     rcx, [r10+8]; this
0x1400f086f  mov     edx, [rdx+0F0h]; unsigned int
0x1400f0875  call    ?GetCommitmentInformation@VIDMM_PROCESS@@QEAAPEAUVIDMM_PROCESS_COMMITMENT_INFO@@IGG@Z; VIDMM_PROCESS::GetCommitmentInformation(uint,ushort,ushort)
0x1400f087a  lea     r15, [rax+28h]
0x1400f087e  mov     rax, [r15]
0x1400f0881  cmp     rax, r15
0x1400f0884  jz      loc_1400F0B3D
0x1400f088a  mov     rbx, [rax+20h]
0x1400f088e  mov     r14, [rax]
0x1400f0891  cmp     rbx, r10
0x1400f0894  jnz     short loc_1400F08BF
0x1400f0896  mov     eax, cs:?_Config@VIDMM_GLOBAL@@2U_VIDMM_CONFIGURATION@@A; _VIDMM_CONFIGURATION VIDMM_GLOBAL::_Config
0x1400f089c  test    al, 40h
0x1400f089e  jz      loc_1400F0991
0x1400f08a4  mov     rcx, [rbp+4Fh+arg_8]
0x1400f08a8  mov     rax, [rcx]
0x1400f08ab  cmp     dword ptr [rax+38h], 0A0000000h
0x1400f08b2  jnb     short loc_1400F08BF
0x1400f08b4  mov     eax, [rcx+18h]
0x1400f08b7  test    al, 1
0x1400f08b9  jnz     loc_1400F0991
0x1400f08bf  test    byte ptr [r10+3Ah], 10h
0x1400f08c4  jz      short loc_1400F08CF
0x1400f08c6  cmp     rbx, r10
0x1400f08c9  jnz     loc_1400F0991
0x1400f08cf  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400f08d6  xor     esi, esi
0x1400f08d8  cmp     [rax], sil
0x1400f08db  jz      short loc_1400F08FB
0x1400f08dd  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400f08e4  nop     dword ptr [rax+rax+00h]
0x1400f08e9  lea     r11d, [rsi+3Fh]
0x1400f08ed  mov     [rax+18h], rbx
0x1400f08f1  mov     cs:WdLogGlobalForLineNumber, 9CFh
0x1400f08fb  mov     rax, [rbp+4Fh+arg_8]
0x1400f08ff  mov     rcx, rbx
0x1400f0902  mov     byte ptr [rbp+4Fh+arg_18], sil
0x1400f0906  mov     rax, [rax]
0x1400f0909  mov     r9d, [rax+3Ch]
0x1400f090d  lea     rax, [rbp+4Fh+arg_18]
0x1400f0911  mov     [rsp+48h], rax
0x1400f0916  lea     rax, [rbp+4Fh+var_80]
0x1400f091a  mov     [rsp+100h+var_C0], rax
0x1400f091f  lea     rax, [rbp+4Fh+var_9C]
0x1400f0923  mov     [rsp+100h+var_C8], rax
0x1400f0928  mov     eax, [rbp+4Fh+var_A8]
0x1400f092b  mov     dword ptr [rsp+100h+var_D0], edi
0x1400f092f  mov     [rsp+100h+var_D8], eax
0x1400f0933  mov     eax, [rbp+4Fh+var_A0]
0x1400f0936  shr     r9d, 2
0x1400f093a  and     r9w, r11w
0x1400f093e  mov     word ptr [rsp+100h+var_E0], ax
0x1400f0943  call    ?FaultAllDemotableAllocations@VIDMM_DEVICE@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEBV1@GGW4VIDMM_PLACEMENT_RESTRICTION@@IPEAIPEA_KPEA_N@Z; VIDMM_DEVICE::FaultAllDemotableAllocations(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_DEVICE const *,ushort,ushort,VIDMM_PLACEMENT_RESTRICTION,uint,uint *,unsigned __int64 *,bool *)
0x1400f0948  cmp     byte ptr [rbp+4Fh+arg_18], sil
0x1400f094c  jz      short loc_1400F097A
0x1400f094e  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400f0955  cmp     [rax], sil
0x1400f0958  jz      short loc_1400F097A
0x1400f095a  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400f0961  nop     dword ptr [rax+rax+00h]
0x1400f0966  mov     ecx, edi
0x1400f0968  mov     [rax+18h], rbx
0x1400f096c  mov     [rax+20h], rcx
0x1400f0970  mov     cs:WdLogGlobalForLineNumber, 9E1h
0x1400f097a  mov     rsi, [rbp+4Fh+var_80]
0x1400f097e  test    rsi, rsi
0x1400f0981  jz      loc_1400F0BB4
0x1400f0987  mov     r10, [rbp+4Fh+arg_10]
0x1400f098b  mov     r11d, 3Fh ; '?'
0x1400f0991  mov     rax, r14
0x1400f0994  cmp     r14, r15
0x1400f0997  jnz     loc_1400F088A
0x1400f099d  mov     rbx, [rbp+4Fh+arg_8]
0x1400f09a1  mov     r14, [rbp+4Fh+var_78]
0x1400f09a5  mov     rdi, [rbp+4Fh+var_90]
0x1400f09a9  jmp     loc_1400F0B41
0x1400f09ae  mov     rbx, [rdi]
0x1400f09b1  cmp     rbx, rdi
0x1400f09b4  jz      loc_1400F0B37
0x1400f09ba  mov     rcx, [rbx-18h]
0x1400f09be  mov     rax, [rbx]
0x1400f09c1  mov     [rbp+4Fh+var_60], rax
0x1400f09c5  mov     rcx, [rcx+10h]
0x1400f09c9  call    cs:__imp_PsIsSystemProcess
0x1400f09d0  nop     dword ptr [rax+rax+00h]
0x1400f09d5  test    al, al
0x1400f09d7  jnz     loc_1400F0B20
0x1400f09dd  lea     r14, [rbx+10h]
0x1400f09e1  mov     rax, [r14]
0x1400f09e4  cmp     rax, r14
0x1400f09e7  jz      loc_1400F0B20
0x1400f09ed  mov     rdi, [rax+20h]
0x1400f09f1  mov     r9b, byte ptr [rbp+4Fh+arg_20]
0x1400f09f5  mov     rcx, rdi
0x1400f09f8  mov     r8d, [rbp+4Fh+var_70]
0x1400f09fc  mov     rdx, [rbp+4Fh+arg_10]
0x1400f0a00  mov     r15, [rax]
0x1400f0a03  call    ?CanSuspendThisDevice@VIDMM_DEVICE@@QEAA_NPEBV1@W4VIDMM_SUSPEND_CANDIDATE_PASS@@W4VIDMM_BUDGET_PRIORITY_BAND@@@Z; VIDMM_DEVICE::CanSuspendThisDevice(VIDMM_DEVICE const *,VIDMM_SUSPEND_CANDIDATE_PASS,VIDMM_BUDGET_PRIORITY_BAND)
0x1400f0a08  test    al, al
0x1400f0a0a  jz      loc_1400F0B10
0x1400f0a10  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400f0a17  cmp     byte ptr [rax], 0
0x1400f0a1a  jz      short loc_1400F0A36
0x1400f0a1c  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400f0a23  nop     dword ptr [rax+rax+00h]
0x1400f0a28  mov     [rax+18h], rdi
0x1400f0a2c  mov     cs:WdLogGlobalForLineNumber, 0A28h
0x1400f0a36  mov     rax, [rbp+4Fh+arg_8]
0x1400f0a3a  mov     rcx, rdi
0x1400f0a3d  mov     byte ptr [rbp+4Fh+arg_18], 0
0x1400f0a41  mov     rax, [rax]
0x1400f0a44  mov     r9d, [rax+3Ch]
0x1400f0a48  lea     rax, [rbp+4Fh+arg_18]
0x1400f0a4c  mov     [rsp+48h], rax
0x1400f0a51  lea     rax, [rbp+4Fh+var_80]
0x1400f0a55  mov     [rsp+100h+var_C0], rax
0x1400f0a5a  lea     rax, [rbp+4Fh+var_9C]
0x1400f0a5e  mov     [rsp+100h+var_C8], rax
0x1400f0a63  mov     eax, [rbp+4Fh+var_A8]
0x1400f0a66  mov     dword ptr [rsp+100h+var_D0], r12d
0x1400f0a6b  mov     [rsp+100h+var_D8], eax
0x1400f0a6f  mov     eax, [rbp+4Fh+var_A0]
0x1400f0a72  shr     r9d, 2
0x1400f0a76  and     r9w, 3Fh
0x1400f0a7b  mov     word ptr [rsp+100h+var_E0], ax
0x1400f0a80  call    ?FaultAllDemotableAllocations@VIDMM_DEVICE@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEBV1@GGW4VIDMM_PLACEMENT_RESTRICTION@@IPEAIPEA_KPEA_N@Z; VIDMM_DEVICE::FaultAllDemotableAllocations(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_DEVICE const *,ushort,ushort,VIDMM_PLACEMENT_RESTRICTION,uint,uint *,unsigned __int64 *,bool *)
0x1400f0a85  cmp     byte ptr [rbp+4Fh+arg_18], 0
0x1400f0a89  jz      short loc_1400F0AFF
0x1400f0a8b  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400f0a92  cmp     byte ptr [rax], 0
0x1400f0a95  jz      short loc_1400F0AB8
0x1400f0a97  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400f0a9e  nop     dword ptr [rax+rax+00h]
0x1400f0aa3  mov     ecx, r12d
0x1400f0aa6  mov     [rax+18h], rdi
0x1400f0aaa  mov     [rax+20h], rcx
0x1400f0aae  mov     cs:WdLogGlobalForLineNumber, 0A39h
0x1400f0ab8  mov     rax, [rbx]
0x1400f0abb  test    rax, rax
0x1400f0abe  jz      short loc_1400F0AFF
0x1400f0ac0  cmp     [rax+8], rbx
0x1400f0ac4  jnz     loc_1400F0DD7
0x1400f0aca  mov     rcx, [rbx+8]
0x1400f0ace  cmp     [rcx], rbx
0x1400f0ad1  jnz     loc_1400F0DD7
0x1400f0ad7  mov     rdi, [rbp+4Fh+var_90]
0x1400f0adb  mov     [rcx], rax
0x1400f0ade  mov     [rax+8], rcx
0x1400f0ae2  mov     rax, [rdi+8]
0x1400f0ae6  cmp     [rax], rdi
0x1400f0ae9  jnz     loc_1400F0DD7
0x1400f0aef  mov     [rbx], rdi
0x1400f0af2  mov     [rbx+8], rax
0x1400f0af6  mov     [rax], rbx
0x1400f0af9  mov     [rdi+8], rbx
0x1400f0afd  jmp     short loc_1400F0B03
0x1400f0aff  mov     rdi, [rbp+4Fh+var_90]
0x1400f0b03  mov     rsi, [rbp+4Fh+var_80]
0x1400f0b07  test    rsi, rsi
0x1400f0b0a  jz      loc_1400F0C1E
0x1400f0b10  mov     rax, r15
0x1400f0b13  cmp     r15, r14
0x1400f0b16  jnz     loc_1400F09ED
0x1400f0b1c  mov     rdi, [rbp+4Fh+var_90]
0x1400f0b20  mov     rbx, [rbp+4Fh+var_60]
0x1400f0b24  cmp     rbx, rdi
0x1400f0b27  jnz     loc_1400F09BA
0x1400f0b2d  mov     rbx, [rbp+4Fh+arg_8]
0x1400f0b31  mov     r14, [rbp+4Fh+var_78]
0x1400f0b35  jmp     short loc_1400F0B41
0x1400f0b37  mov     rbx, [rbp+4Fh+arg_8]
  ... truncated ...
```
