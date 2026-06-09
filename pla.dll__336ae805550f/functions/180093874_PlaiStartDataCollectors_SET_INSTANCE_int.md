# PlaiStartDataCollectors(_SET_INSTANCE *,int *)

- ea: `0x180093874`
- end: `0x180094332`
- name: `?PlaiStartDataCollectors@@YAJPEAU_SET_INSTANCE@@PEAH@Z`
- size: `2750`
- prototype: `__int64 __fastcall(struct _SET_INSTANCE *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1801334e8`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18000d8c0`
- `0x180012ef0`
- `0x18002b3a0`
- `0x180093874`
- `0x1801350fc`
- `0x1801355ac`
- `0x180135bb0`
- `0x180136f94`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093d5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800940ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093d5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800940ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180093a2b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180093a2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180094053`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180094053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800942f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800942f4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180093d40`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180093d40`

## pseudocode

```c
__int64 __fastcall PlaiStartDataCollectors(struct _SET_INSTANCE *a1, int *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rax
  int **v7; // rcx
  int **v8; // r9
  int v9; // eax
  __int64 v10; // rax
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v13; // rax
  __int64 v14; // xmm6_8
  int i; // esi
  _QWORD *v16; // rdi
  struct _SET_INSTANCE **v17; // rcx
  __int128 v18; // xmm0
  _QWORD *v19; // r12
  int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  HAlertDataCollector *v24; // rax
  HAlertDataCollector *v25; // rax
  HConfigurationDataCollector *v26; // rax
  HDataCollector *v27; // rax
  HDataCollector *v28; // rbx
  HDataCollector *v29; // rax
  HANDLE Thread; // rax
  DWORD v31; // eax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  DWORD v38; // eax
  __int64 v39; // rax
  DWORD v40; // eax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  void *v44; // rcx
  int dwCreationFlags; // [rsp+28h] [rbp-E0h]
  __int64 v47; // [rsp+78h] [rbp-90h] BYREF
  int *v48; // [rsp+80h] [rbp-88h] BYREF
  int v49; // [rsp+88h] [rbp-80h] BYREF
  int v50; // [rsp+8Ch] [rbp-7Ch] BYREF
  __int64 v51; // [rsp+90h] [rbp-78h] BYREF
  __int128 v52; // [rsp+98h] [rbp-70h]
  __int64 v53; // [rsp+A8h] [rbp-60h]
  __int128 v54; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v55; // [rsp+C8h] [rbp-40h]
  unsigned __int16 v56[64]; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int16 v57[64]; // [rsp+158h] [rbp+50h] BYREF
  unsigned __int16 v58[64]; // [rsp+1D8h] [rbp+D0h] BYREF
  unsigned __int16 v59[64]; // [rsp+258h] [rbp+150h] BYREF
  unsigned __int16 v60[64]; // [rsp+2D8h] [rbp+1D0h] BYREF
  unsigned __int16 v61[64]; // [rsp+358h] [rbp+250h] BYREF
  unsigned __int16 v62[64]; // [rsp+3D8h] [rbp+2D0h] BYREF
  unsigned __int16 v63[64]; // [rsp+458h] [rbp+350h] BYREF
  unsigned __int16 v64[64]; // [rsp+4D8h] [rbp+3D0h] BYREF
  unsigned __int16 v65[64]; // [rsp+558h] [rbp+450h] BYREF
  unsigned __int16 v66[64]; // [rsp+5D8h] [rbp+4D0h] BYREF
  unsigned __int16 v67[64]; // [rsp+658h] [rbp+550h] BYREF
  unsigned __int16 v68[64]; // [rsp+6D8h] [rbp+5D0h] BYREF

  v48 = a2;
  *a2 = 0;
  v51 = 0;
  v53 = 0;
  v49 = 0;
  v3 = *((_QWORD *)a1 + 15);
  v50 = 0;
  v52 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 56LL))(v3, &v51);
  v5 = v4;
  if ( v4 < 0 )
  {
    LODWORD(v47) = 0;
    LODWORD(v48) = v4;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_115;
    }
    PlaiWhoAmI(v56, 0x4000000000000800uLL);
    v6 = -1;
    do
      ++v6;
    while ( v56[v6] );
    v7 = (int **)&v47;
    v8 = &v48;
LABEL_114:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v8, 4, byte_180147320, 1, v7, 4);
    goto LABEL_115;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v51 + 56LL))(v51, &v49);
  v5 = v9;
  if ( v9 < 0 )
  {
    LODWORD(v48) = 0;
    LODWORD(v47) = v9;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_115;
    }
    PlaiWhoAmI(v57, 0x4000000000000800uLL);
    v10 = -1;
    do
      ++v10;
    while ( v57[v10] );
LABEL_113:
    v8 = (int **)&v47;
    v7 = &v48;
    goto LABEL_114;
  }
  *((_DWORD *)a1 + 36) = v49;
  *((_DWORD *)a1 + 37) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)a1 + 17) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v5 = PlaiHResultFromWin32(LastError);
    LODWORD(v48) = 0;
    LODWORD(v47) = v5;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_115;
    }
    PlaiWhoAmI(v58, 0x4000000000000800uLL);
    v13 = -1;
    do
      ++v13;
    while ( v58[v13] );
    goto LABEL_113;
  }
  v14 = v53;
  DWORD2(v52) = 0;
  LOWORD(v52) = 3;
  for ( i = 0; i < v49; DWORD2(v52) = i )
  {
    v16 = PlaiAlloc(0x60u, 1, 1, byte_180147320, dwCreationFlags);
    if ( !v16 )
    {
      v5 = -2147024882;
      LODWORD(v47) = -2147024882;
      LODWORD(v48) = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v64, 0x4000000000000800uLL);
        v37 = -1;
        do
          ++v37;
        while ( v64[v37] );
        goto LABEL_113;
      }
      goto LABEL_115;
    }
    ++*((_DWORD *)a1 + 24);
    v17 = (struct _SET_INSTANCE **)*((_QWORD *)a1 + 14);
    if ( *v17 != (struct _SET_INSTANCE *)((char *)a1 + 104) )
      __fastfail(3u);
    v18 = v52;
    *v16 = (char *)a1 + 104;
    v19 = v16 + 11;
    v16[1] = v17;
    *v17 = (struct _SET_INSTANCE *)v16;
    *((_QWORD *)a1 + 14) = v16;
    v16[7] = a1;
    v54 = v18;
    v55 = v14;
    v20 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD *))(*(_QWORD *)v51 + 64LL))(v51, &v54, v16 + 11);
    v5 = v20;
    if ( v20 < 0 )
    {
      LODWORD(v47) = v20;
      LODWORD(v48) = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v63, 0x4000000000000800uLL);
        v36 = -1;
        do
          ++v36;
        while ( v63[v36] );
        goto LABEL_113;
      }
      goto LABEL_115;
    }
    v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v19 + 192LL))(*v19, v16 + 3);
    v5 = v21;
    if ( v21 < 0 )
    {
      LODWORD(v47) = v21;
      LODWORD(v48) = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v62, 0x4000000000000800uLL);
        v35 = -1;
        do
          ++v35;
        while ( v62[v35] );
        goto LABEL_113;
      }
      goto LABEL_115;
    }
    v22 = *v19;
    *((_DWORD *)v16 + 8) = i;
    v23 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 72LL))(v22, &v50);
    v5 = v23;
    if ( v23 < 0 )
    {
      LODWORD(v47) = v23;
      LODWORD(v48) = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v61, 0x4000000000000800uLL);
        v34 = -1;
        do
          ++v34;
        while ( v61[v34] );
        goto LABEL_113;
      }
      goto LABEL_115;
    }
    if ( !v50 )
    {
      v29 = (HDataCollector *)operator new(0x110u, byte_180147320, 0);
      v28 = v29;
      if ( v29 )
      {
        HDataCollector::HDataCollector(v29, (struct _COLLECTOR_INSTANCE *)v16);
        *(_QWORD *)v28 = &HPerformanceCounterDataCollector::`vftable';
        (**(void (__fastcall ***)(_QWORD, GUID *, __int64))*v19)(
          *v19,
          &IID_IPerformanceCounterDataCollector,
          (__int64)v28 + 216);
        *((_DWORD *)v28 + 65) = 0x20000;
        *((_DWORD *)v28 + 56) = 0;
        *((_QWORD *)v28 + 29) = 0;
        *((_QWORD *)v28 + 30) = 0;
        *((_QWORD *)v28 + 31) = 0;
        goto LABEL_42;
      }
LABEL_41:
      v28 = 0;
      goto LABEL_42;
    }
    if ( v50 != 1 )
    {
      if ( v50 == 2 )
      {
        v26 = (HConfigurationDataCollector *)operator new(0x120u, byte_180147320, 0);
        if ( v26 )
        {
          v25 = HConfigurationDataCollector::HConfigurationDataCollector(v26, (struct _COLLECTOR_INSTANCE *)v16);
          goto LABEL_38;
        }
      }
      else
      {
        if ( v50 != 3 )
          goto LABEL_45;
        v24 = (HAlertDataCollector *)operator new(0x128u, byte_180147320, 0);
        if ( v24 )
        {
          v25 = HAlertDataCollector::HAlertDataCollector(v24, (struct _COLLECTOR_INSTANCE *)v16);
LABEL_38:
          v16[10] = v25;
          goto LABEL_45;
        }
      }
      v25 = 0;
      goto LABEL_38;
    }
    *v48 = 1;
    v27 = (HDataCollector *)operator new(0x148u, byte_180147320, 0);
    v28 = v27;
    if ( !v27 )
      goto LABEL_41;
    HDataCollector::HDataCollector(v27, (struct _COLLECTOR_INSTANCE *)v16);
    *(_QWORD *)v28 = &HTraceDataCollector::`vftable';
    (**(void (__fastcall ***)(_QWORD, GUID *, __int64))*v19)(*v19, &IID_ITraceDataCollector, (__int64)v28 + 288);
    *((_QWORD *)v28 + 33) = 0;
    *((_QWORD *)v28 + 35) = 0;
    *((_QWORD *)v28 + 37) = 0;
    *((_QWORD *)v28 + 38) = 0;
    *((_QWORD *)v28 + 39) = 0;
    *((_DWORD *)v28 + 80) = 0;
LABEL_42:
    v16[10] = v28;
LABEL_45:
    if ( !v16[10] )
    {
      v5 = -2147024882;
      LODWORD(v47) = -2147024882;
      LODWORD(v48) = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v60, 0x4000000000000800uLL);
        v33 = -1;
        do
          ++v33;
        while ( v60[v33] );
        goto LABEL_113;
      }
      goto LABEL_115;
    }
    Thread = CreateThread(0, 0, PlaiCollectorControl, v16, 0, 0);
    v16[6] = Thread;
    if ( !Thread )
    {
      v31 = GetLastError();
      v5 = PlaiHResultFromWin32(v31);
      LODWORD(v48) = 0;
      LODWORD(v47) = v5;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v59, 0x4000000000000800uLL);
        v32 = -1;
        do
          ++v32;
        while ( v59[v32] );
        goto LABEL_113;
      }
      goto LABEL_115;
    }
    ++i;
  }
  if ( v49 > 0 && (v38 = WaitForSingleObject(*((HANDLE *)a1 + 17), 0x1D4C0u)) != 0 )
  {
    if ( v38 == 258 )
    {
      v5 = -2144337653;
      LODWORD(v47) = -2144337653;
      LODWORD(v48) = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v67, 0x4000000000000800uLL);
        v42 = -1;
        do
          ++v42;
        while ( v67[v42] );
        goto LABEL_113;
      }
    }
    else if ( v38 == -1 )
    {
      v40 = GetLastError();
      v5 = PlaiHResultFromWin32(v40);
      LODWORD(v48) = 0;
      LODWORD(v47) = v5;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v66, 0x4000000000000800uLL);
        v41 = -1;
        do
          ++v41;
        while ( v66[v41] );
        goto LABEL_113;
      }
    }
    else
    {
      v5 = -2147467259;
      LODWORD(v47) = -2147467259;
      LODWORD(v48) = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v65, 0x4000000000000800uLL);
        v39 = -1;
        do
          ++v39;
        while ( v65[v39] );
        goto LABEL_113;
      }
    }
  }
  else
  {
    v5 = *((_DWORD *)a1 + 37);
    if ( v5 < 0 )
    {
      LODWORD(v48) = 0;
      LODWORD(v47) = v5;
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v68, 0x4000000000000800uLL);
          v43 = -1;
          do
            ++v43;
          while ( v68[v43] );
          goto LABEL_113;
        }
      }
    }
  }
LABEL_115:
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  if ( v5 < 0 )
    PlaiWaitForStop(a1);
  v44 = (void *)*((_QWORD *)a1 + 17);
  if ( v44 )
  {
    CloseHandle(v44);
    *((_QWORD *)a1 + 17) = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180093874  mov     rax, rsp
0x180093877  mov     [rax+18h], rbx
0x18009387b  push    rbp
0x18009387c  push    rsi
0x18009387d  push    rdi
0x18009387e  push    r12
0x180093880  push    r13
0x180093882  push    r14
0x180093884  push    r15
0x180093886  lea     rbp, [rax-6A8h]
0x18009388d  sub     rsp, 770h
0x180093894  movaps  xmmword ptr [rax-48h], xmm6
0x180093898  mov     rax, cs:__security_cookie
0x18009389f  xor     rax, rsp
0x1800938a2  mov     [rbp+6A0h+var_50], rax
0x1800938a9  xor     r12d, r12d
0x1800938ac  mov     [rsp+7A0h+var_728], rdx
0x1800938b1  mov     [rdx], r12d
0x1800938b4  mov     r13, rcx
0x1800938b7  xor     ecx, ecx
0x1800938b9  mov     [rbp+6A0h+var_718], r12
0x1800938bd  mov     [rbp+6A0h+var_700], rcx
0x1800938c1  lea     rdx, [rbp+6A0h+var_718]
0x1800938c5  mov     [rbp+6A0h+var_720], r12d
0x1800938c9  xorps   xmm0, xmm0
0x1800938cc  mov     rcx, [r13+78h]
0x1800938d0  mov     [rbp+6A0h+var_71C], r12d
0x1800938d4  movups  [rbp+6A0h+var_710], xmm0
0x1800938d8  mov     rax, [rcx]
0x1800938db  mov     rax, [rax+38h]
0x1800938df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800938e4  mov     ebx, eax
0x1800938e6  test    eax, eax
0x1800938e8  jns     loc_180093979
0x1800938ee  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800938f5  mov     dword ptr [rsp+7A0h+var_730], r12d
0x1800938fa  mov     dword ptr [rsp+7A0h+var_728], eax
0x1800938fe  jz      loc_1800942C3
0x180093904  mov     rdx, 4000000000000800h; unsigned __int64
0x18009390e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180093915  jz      loc_1800942C3
0x18009391b  mov     rax, cs:qword_180169748
0x180093922  and     rax, rdx
0x180093925  cmp     cs:qword_180169748, rax
0x18009392c  jnz     loc_1800942C3
0x180093932  lea     rcx, [rbp+6A0h+var_6D0]; unsigned __int16 *
0x180093936  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009393b  lea     rcx, [rbp+6A0h+var_6D0]
0x18009393f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180093943  inc     rax
0x180093946  cmp     [rcx+rax*2], r12w
0x18009394b  jnz     short loc_180093943
0x18009394d  lea     ecx, [rax+rax]
0x180093950  mov     r14d, 1
0x180093956  add     rcx, 2
0x18009395a  lea     rax, [rbp+6A0h+var_6D0]
0x18009395e  mov     [rsp+7A0h+var_740], rcx
0x180093963  lea     r15, byte_180147320
0x18009396a  lea     rcx, [rsp+7A0h+var_730]
0x18009396f  lea     r9, [rsp+7A0h+var_728]
0x180093974  jmp     loc_180094274
0x180093979  mov     rcx, [rbp+6A0h+var_718]
0x18009397d  lea     rdx, [rbp+6A0h+var_720]
0x180093981  mov     rax, [rcx]
0x180093984  mov     rax, [rax+38h]
0x180093988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009398d  mov     ebx, eax
0x18009398f  test    eax, eax
0x180093991  jns     short loc_180093A0B
0x180093993  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009399a  mov     dword ptr [rsp+7A0h+var_728], r12d
0x18009399f  mov     dword ptr [rsp+7A0h+var_730], eax
0x1800939a3  jz      loc_1800942C3
0x1800939a9  mov     rdx, 4000000000000800h; unsigned __int64
0x1800939b3  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800939ba  jz      loc_1800942C3
0x1800939c0  mov     rax, cs:qword_180169748
0x1800939c7  and     rax, rdx
0x1800939ca  cmp     cs:qword_180169748, rax
0x1800939d1  jnz     loc_1800942C3
0x1800939d7  lea     rcx, [rbp+6A0h+var_650]; unsigned __int16 *
0x1800939db  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800939e0  lea     rcx, [rbp+6A0h+var_650]
0x1800939e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800939e8  inc     rax
0x1800939eb  cmp     [rcx+rax*2], r12w
0x1800939f0  jnz     short loc_1800939E8
0x1800939f2  lea     ecx, [rax+rax]
0x1800939f5  mov     r14d, 1
0x1800939fb  lea     rax, [rbp+6A0h+var_650]
0x1800939ff  lea     r15, byte_180147320
0x180093a06  jmp     loc_180094261
0x180093a0b  mov     eax, [rbp+6A0h+var_720]
0x180093a0e  xor     r9d, r9d; lpName
0x180093a11  xor     r8d, r8d; bInitialState
0x180093a14  mov     [r13+90h], eax
0x180093a1b  xor     ecx, ecx; lpEventAttributes
0x180093a1d  mov     [r13+94h], r12d
0x180093a24  lea     r14d, [r9+1]
0x180093a28  mov     edx, r14d; bManualReset
0x180093a2b  call    cs:__imp_CreateEventW
0x180093a31  mov     [r13+88h], rax
0x180093a38  test    rax, rax
0x180093a3b  jnz     loc_180093AC4
0x180093a41  call    cs:__imp_GetLastError
0x180093a47  mov     ecx, eax; unsigned int
0x180093a49  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180093a4e  cmp     dword ptr cs:xmmword_180169738, r12d
0x180093a55  mov     ebx, eax
0x180093a57  mov     dword ptr [rsp+7A0h+var_728], r12d
0x180093a5c  mov     dword ptr [rsp+7A0h+var_730], eax
0x180093a60  jz      loc_1800942C3
0x180093a66  mov     rdx, 4000000000000800h; unsigned __int64
0x180093a70  test    qword ptr cs:xmmword_180169738+8, rdx
0x180093a77  jz      loc_1800942C3
0x180093a7d  mov     rax, cs:qword_180169748
0x180093a84  and     rax, rdx
0x180093a87  cmp     cs:qword_180169748, rax
0x180093a8e  jnz     loc_1800942C3
0x180093a94  lea     rcx, [rbp+6A0h+var_5D0]; unsigned __int16 *
0x180093a9b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180093aa0  lea     rcx, [rbp+6A0h+var_5D0]
0x180093aa7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180093aab  inc     rax
0x180093aae  cmp     [rcx+rax*2], r12w
0x180093ab3  jnz     short loc_180093AAB
0x180093ab5  lea     ecx, [rax+rax]
0x180093ab8  lea     rax, [rbp+6A0h+var_5D0]
0x180093abf  jmp     loc_1800939FF
0x180093ac4  movsd   xmm6, [rbp+6A0h+var_700]
0x180093ac9  lea     r15, byte_180147320
0x180093ad0  mov     ebx, 3
0x180093ad5  mov     dword ptr [rbp+6A0h+var_710+8], r12d
0x180093ad9  mov     word ptr [rbp+6A0h+var_710], bx
0x180093add  mov     esi, r12d
0x180093ae0  mov     eax, [rbp+6A0h+var_720]
0x180093ae3  cmp     esi, eax
0x180093ae5  jge     loc_18009403F
0x180093aeb  mov     r9, r15; char *
0x180093aee  mov     r8d, r14d; int
0x180093af1  mov     edx, r14d; int
0x180093af4  mov     ecx, 60h ; '`'; dwBytes
0x180093af9  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x180093afe  mov     rdi, rax
0x180093b01  test    rax, rax
0x180093b04  jz      loc_180093FC4
0x180093b0a  add     [r13+60h], r14d
0x180093b0e  lea     rax, [r13+68h]
0x180093b12  mov     rcx, [rax+8]
0x180093b16  cmp     [rcx], rax
0x180093b19  jnz     loc_180093FBD
0x180093b1f  movups  xmm0, [rbp+6A0h+var_710]
0x180093b23  mov     [rdi], rax
0x180093b26  lea     r12, [rdi+58h]
0x180093b2a  mov     [rdi+8], rcx
0x180093b2e  lea     rdx, [rbp+6A0h+var_6F0]
0x180093b32  mov     [rcx], rdi
0x180093b35  mov     r8, r12
0x180093b38  mov     [rax+8], rdi
0x180093b3c  mov     [rdi+38h], r13
0x180093b40  mov     rcx, [rbp+6A0h+var_718]
0x180093b44  movaps  [rbp+6A0h+var_6F0], xmm0
0x180093b48  movsd   [rbp+6A0h+var_6E0], xmm6
0x180093b4d  mov     rax, [rcx]
0x180093b50  mov     rax, [rax+40h]
0x180093b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093b59  mov     ebx, eax
0x180093b5b  test    eax, eax
0x180093b5d  js      loc_180093F46
0x180093b63  mov     rcx, [r12]
0x180093b67  lea     rdx, [rdi+18h]
0x180093b6b  mov     rax, [rcx]
0x180093b6e  mov     rax, [rax+0C0h]
0x180093b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093b7a  mov     ebx, eax
0x180093b7c  test    eax, eax
0x180093b7e  js      loc_180093ECF
0x180093b84  mov     rcx, [r12]
0x180093b88  lea     rdx, [rbp+6A0h+var_71C]
0x180093b8c  mov     [rdi+20h], esi
0x180093b8f  mov     rax, [rcx]
0x180093b92  mov     rax, [rax+48h]
0x180093b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093b9b  mov     ebx, eax
0x180093b9d  test    eax, eax
0x180093b9f  js      loc_180093E58
0x180093ba5  mov     ecx, [rbp+6A0h+var_71C]
0x180093ba8  test    ecx, ecx
0x180093baa  jz      loc_180093CA6
0x180093bb0  sub     ecx, r14d
0x180093bb3  jz      short loc_180093C19
0x180093bb5  sub     ecx, r14d
0x180093bb8  jz      short loc_180093BE8
0x180093bba  cmp     ecx, r14d
0x180093bbd  jnz     loc_180093D1B
0x180093bc3  xor     r8d, r8d; int
0x180093bc6  mov     rdx, r15; char *
0x180093bc9  mov     ecx, 128h; dwBytes
0x180093bce  call    ??2@YAPEAX_KPEBDH@Z; operator new(unsigned __int64,char const *,int)
0x180093bd3  xor     r12d, r12d
0x180093bd6  test    rax, rax
0x180093bd9  jz      short loc_180093C0D
0x180093bdb  mov     rdx, rdi; struct _COLLECTOR_INSTANCE *
0x180093bde  mov     rcx, rax; this
0x180093be1  call    ??0HAlertDataCollector@@QEAA@PEAU_COLLECTOR_INSTANCE@@@Z; HAlertDataCollector::HAlertDataCollector(_COLLECTOR_INSTANCE *)
0x180093be6  jmp     short loc_180093C10
0x180093be8  xor     r8d, r8d; int
0x180093beb  mov     rdx, r15; char *
0x180093bee  mov     ecx, 120h; dwBytes
0x180093bf3  call    ??2@YAPEAX_KPEBDH@Z; operator new(unsigned __int64,char const *,int)
0x180093bf8  xor     r12d, r12d
0x180093bfb  test    rax, rax
0x180093bfe  jz      short loc_180093C0D
0x180093c00  mov     rdx, rdi; struct _COLLECTOR_INSTANCE *
0x180093c03  mov     rcx, rax; this
0x180093c06  call    ??0HConfigurationDataCollector@@QEAA@PEAU_COLLECTOR_INSTANCE@@@Z; HConfigurationDataCollector::HConfigurationDataCollector(_COLLECTOR_INSTANCE *)
0x180093c0b  jmp     short loc_180093C10
0x180093c0d  mov     rax, r12
0x180093c10  mov     [rdi+50h], rax
0x180093c14  jmp     loc_180093D1E
0x180093c19  mov     rax, [rsp+7A0h+var_728]
0x180093c1e  xor     r8d, r8d; int
0x180093c21  mov     rdx, r15; char *
0x180093c24  mov     ecx, 148h; dwBytes
0x180093c29  mov     [rax], r14d
0x180093c2c  call    ??2@YAPEAX_KPEBDH@Z; operator new(unsigned __int64,char const *,int)
0x180093c31  mov     rbx, rax
0x180093c34  test    rax, rax
0x180093c37  jz      short loc_180093C9A
0x180093c39  mov     rdx, rdi; struct _COLLECTOR_INSTANCE *
0x180093c3c  mov     rcx, rax; this
0x180093c3f  call    ??0HDataCollector@@QEAA@PEAU_COLLECTOR_INSTANCE@@@Z; HDataCollector::HDataCollector(_COLLECTOR_INSTANCE *)
0x180093c44  lea     rax, ??_7HTraceDataCollector@@6B@; const HTraceDataCollector::`vftable'
0x180093c4b  mov     [rbx], rax
0x180093c4e  lea     r8, [rbx+120h]
0x180093c55  mov     rcx, [r12]
0x180093c59  mov     rdx, [rcx]
0x180093c5c  mov     rax, [rdx]
0x180093c5f  lea     rdx, IID_ITraceDataCollector
0x180093c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c6b  xor     r12d, r12d
0x180093c6e  mov     [rbx+108h], r12
0x180093c75  mov     [rbx+118h], r12
0x180093c7c  mov     [rbx+128h], r12
0x180093c83  mov     [rbx+130h], r12
0x180093c8a  mov     [rbx+138h], r12
0x180093c91  mov     [rbx+140h], r12d
0x180093c98  jmp     short loc_180093CA0
0x180093c9a  xor     r12d, r12d
0x180093c9d  mov     ebx, r12d
0x180093ca0  mov     [rdi+50h], rbx
0x180093ca4  jmp     short loc_180093D1E
0x180093ca6  xor     r8d, r8d; int
0x180093ca9  mov     rdx, r15; char *
0x180093cac  mov     ecx, 110h; dwBytes
0x180093cb1  call    ??2@YAPEAX_KPEBDH@Z; operator new(unsigned __int64,char const *,int)
0x180093cb6  mov     rbx, rax
0x180093cb9  test    rax, rax
0x180093cbc  jz      short loc_180093C9A
0x180093cbe  mov     rdx, rdi; struct _COLLECTOR_INSTANCE *
0x180093cc1  mov     rcx, rax; this
0x180093cc4  call    ??0HDataCollector@@QEAA@PEAU_COLLECTOR_INSTANCE@@@Z; HDataCollector::HDataCollector(_COLLECTOR_INSTANCE *)
0x180093cc9  lea     rax, ??_7HPerformanceCounterDataCollector@@6B@; const HPerformanceCounterDataCollector::`vftable'
0x180093cd0  mov     [rbx], rax
0x180093cd3  lea     r8, [rbx+0D8h]
0x180093cda  mov     rcx, [r12]
0x180093cde  mov     rdx, [rcx]
0x180093ce1  mov     rax, [rdx]
0x180093ce4  lea     rdx, IID_IPerformanceCounterDataCollector
0x180093ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093cf0  xor     r12d, r12d
0x180093cf3  mov     dword ptr [rbx+104h], 20000h
0x180093cfd  mov     [rbx+0E0h], r12d
0x180093d04  mov     [rbx+0E8h], r12
0x180093d0b  mov     [rbx+0F0h], r12
0x180093d12  mov     [rbx+0F8h], r12
0x180093d19  jmp     short loc_180093CA0
0x180093d1b  xor     r12d, r12d
0x180093d1e  cmp     [rdi+50h], r12
0x180093d22  jz      loc_180093DDD
0x180093d28  mov     [rsp+7A0h+lpThreadId], r12; lpThreadId
0x180093d2d  lea     r8, ?PlaiCollectorControl@@YAKPEAX@Z; lpStartAddress
0x180093d34  mov     r9, rdi; lpParameter
0x180093d37  mov     [rsp+7A0h+dwCreationFlags], r12d; dwCreationFlags
0x180093d3c  xor     edx, edx; dwStackSize
0x180093d3e  xor     ecx, ecx; lpThreadAttributes
0x180093d40  call    cs:__imp_CreateThread
0x180093d46  mov     [rdi+30h], rax
0x180093d4a  test    rax, rax
0x180093d4d  jz      short loc_180093D5A
0x180093d4f  add     esi, r14d
0x180093d52  mov     dword ptr [rbp+6A0h+var_710+8], esi
0x180093d55  jmp     loc_180093AE0
0x180093d5a  call    cs:__imp_GetLastError
0x180093d60  mov     ecx, eax; unsigned int
0x180093d62  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180093d67  cmp     dword ptr cs:xmmword_180169738, r12d
0x180093d6e  mov     ebx, eax
0x180093d70  mov     dword ptr [rsp+7A0h+var_728], r12d
0x180093d75  mov     dword ptr [rsp+7A0h+var_730], eax
  ... truncated ...
```
