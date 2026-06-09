# VIDMM_GLOBAL::OpenLocalAllocation(VIDMM_GLOBAL_ALLOC *,VIDMM_PROCESS *,bool)

- ea: `0x1400f2fbc`
- end: `0x1400f34e2`
- name: `?OpenLocalAllocation@VIDMM_GLOBAL@@QEAAPEAUVIDMM_LOCAL_ALLOC@@PEAUVIDMM_GLOBAL_ALLOC@@PEAVVIDMM_PROCESS@@_N@Z`
- size: `1318`
- prototype: `struct VIDMM_LOCAL_ALLOC *__fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_GLOBAL_ALLOC *, struct VIDMM_PROCESS *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400f24e0`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002e6c0`
- `0x140058f50`
- `0x140059030`
- `0x1400f2fbc`
- `0x1400f4b80`
- `0x1400f5f60`
- `0x1400feb90`
- `0x14010e958`
- `0x14011a1b4`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1400f349c`
- `ntoskrnl!KeStackAttachProcess` at `0x1400f349c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400f34d1`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400f34d1`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f300c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f33cc`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f300c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f33cc`
- `watchdog!WdLogSingleEntry0` at `0x1400f30d8`
- `watchdog!WdLogSingleEntry0` at `0x1400f32d6`
- `watchdog!WdLogSingleEntry0` at `0x1400f32f5`
- `watchdog!WdLogSingleEntry0` at `0x1400f331c`
- `watchdog!WdLogSingleEntry0` at `0x1400f30d8`
- `watchdog!WdLogSingleEntry0` at `0x1400f32d6`
- `watchdog!WdLogSingleEntry0` at `0x1400f32f5`
- `watchdog!WdLogSingleEntry0` at `0x1400f331c`
- `watchdog!WdLogSingleEntry1` at `0x1400f3369`
- `watchdog!WdLogSingleEntry1` at `0x1400f3369`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f3000`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f3165`

## string_xrefs

- `0x1400f32e7`: `Trying to open allocation on non graphics process.`
- `0x1400f332d`: `Trying to open a non-shareable allocation more than once.\n`
- `0x1400f3306`: `Trying to open Alloc backed by ExistingSysMem from non-owner's process.`

## pseudocode

```c
struct VIDMM_LOCAL_ALLOC *__fastcall VIDMM_GLOBAL::OpenLocalAllocation(
        VIDMM_GLOBAL *this,
        struct VIDMM_GLOBAL_ALLOC *a2,
        struct VIDMM_PROCESS *a3,
        char a4)
{
  __int64 v4; // r13
  struct VIDMM_PROCESS *v6; // rbp
  struct VIDMM_GLOBAL_ALLOC *v9; // rsi
  struct VIDMM_GLOBAL_ALLOC *v10; // rdx
  VIDMM_GLOBAL *v11; // rcx
  __int64 v12; // rax
  char *v13; // rdi
  char **v14; // rax
  int v15; // ecx
  int v16; // r8d
  __int64 v17; // rax
  const wchar_t *v18; // r9
  int v19; // edx
  char v21; // al
  _DWORD *v22; // rsi
  __int64 v23; // r8
  char *v24; // r14
  __int64 v25; // rcx
  char **v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rcx
  struct _KAPC_STATE ApcState; // [rsp+50h] [rbp-78h] BYREF

  v4 = *(_QWORD *)a2;
  v6 = a3;
  if ( !a3 )
    v6 = (struct VIDMM_PROCESS *)*((_QWORD *)this + 4584);
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(this) + 24) = a2;
    WdLogGlobalForLineNumber = 14643;
  }
  if ( !v6 )
  {
    WdLogSingleEntry0(1);
    v17 = 14654;
    v18 = L"Trying to open allocation on non graphics process.";
LABEL_40:
    v19 = 0x40000;
    goto LABEL_14;
  }
  v9 = (struct VIDMM_GLOBAL_ALLOC *)((char *)a2 + 112);
  v10 = (struct VIDMM_GLOBAL_ALLOC *)*((_QWORD *)a2 + 14);
  if ( v10 != (struct VIDMM_GLOBAL_ALLOC *)((char *)a2 + 112) && (**((_DWORD **)a2 + 49) & 0x20000000) == 0 )
  {
    WdLogSingleEntry0(1);
    v17 = 14664;
    v18 = L"Trying to open a non-shareable allocation more than once.\n";
    goto LABEL_40;
  }
  v11 = (VIDMM_GLOBAL *)(**((_DWORD **)a2 + 49) & 0x20000010);
  if ( (_DWORD)v11 == 536870928 )
  {
    v27 = *((_QWORD *)a2 + 6);
    if ( v27 )
    {
      if ( *(struct VIDMM_PROCESS **)(v27 + 8) != v6 )
      {
        if ( v6 == *((struct VIDMM_PROCESS **)this + 4584) )
          return 0;
        WdLogSingleEntry0(1);
        v17 = 14683;
        v18 = L"Trying to open Alloc backed by ExistingSysMem from non-owner's process.";
        goto LABEL_40;
      }
    }
  }
  if ( (*((_DWORD *)v6 + 40) & 0x20) != 0 )
  {
LABEL_10:
    v12 = operator new(80, 842033494, 256);
    v13 = (char *)v12;
    if ( !v12 )
    {
      _InterlockedIncrement(&dword_140087690);
      WdLogSingleEntry0(6);
      v17 = 14766;
      v18 = L"Couldn't allocate memory for local alloc object.";
      v19 = 262145;
LABEL_14:
      WdLogGlobalForLineNumber = v17;
      DxgkLogInternalTriageEvent(v15, v19, v16, (_DWORD)v18, v17, 0, 0, 0);
      return 0;
    }
    *(_QWORD *)v12 = a2;
    *(_QWORD *)(v12 + 8) = v6;
    *(_BYTE *)(v12 + 24) = (8 * a4) | *(_BYTE *)(v12 + 24) & 0xF7;
    *(_QWORD *)(v12 + 40) = v12 + 32;
    *(_QWORD *)(v12 + 32) = v12 + 32;
    ++*((_DWORD *)a2 + 32);
    v14 = (char **)*((_QWORD *)a2 + 15);
    if ( *v14 != (char *)v9 )
LABEL_12:
      __fastfail(3u);
    v24 = v13 + 48;
    *((_QWORD *)v13 + 6) = v9;
    *((_QWORD *)v13 + 7) = v14;
    *v14 = v13 + 48;
    *((_QWORD *)a2 + 15) = v13 + 48;
    v22 = (_DWORD *)((char *)a2 + 32);
    if ( (*((_DWORD *)a2 + 8) & 0x20) != 0
      && (int)VIDMM_GLOBAL::CommitLocalBackingStore(this, (struct VIDMM_LOCAL_ALLOC *)v13) < 0 )
    {
      VIDMM_GLOBAL::UncommitLocalBackingStore(this, (struct VIDMM_LOCAL_ALLOC *)v13, 1);
      --*((_DWORD *)a2 + 32);
      v25 = *(_QWORD *)v24;
      if ( *(char **)(*(_QWORD *)v24 + 8LL) == v24 )
      {
        v26 = (char **)*((_QWORD *)v13 + 7);
        if ( *v26 == v24 )
        {
          *v26 = (char *)v25;
          *(_QWORD *)(v25 + 8) = v26;
          operator delete(v13);
          return 0;
        }
      }
      goto LABEL_12;
    }
  }
  else
  {
    while ( 1 )
    {
      if ( v10 == v9 )
        goto LABEL_10;
      v13 = (char *)v10 - 48;
      if ( *((struct VIDMM_PROCESS **)v10 - 5) == v6 )
        break;
      v10 = *(struct VIDMM_GLOBAL_ALLOC **)v10;
    }
    v21 = v13[24];
    if ( (v21 & 1) != 0 )
    {
      v13[24] = v21 & 0xFE;
      WdLogSingleEntry1(4, (char *)v10 - 48);
      WdLogGlobalForLineNumber = 14718;
      v28 = *((_QWORD *)a2 + 6);
      if ( !v28 || (*(_BYTE *)(v28 + 24) & 1) != 0 )
      {
        *((_QWORD *)a2 + 6) = v13;
        if ( (*(_DWORD *)(v4 + 64) & 1) != 0 )
          VidMmRecordAlloc(
            *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * ((*(_DWORD *)(v4 + 60) >> 2) & 0x3F)),
            v4,
            *((_QWORD *)v13 + 1),
            0);
      }
    }
    if ( g_IsInternalReleaseOrDbg )
    {
      *(_QWORD *)(WdLogNewEntry5_WdTrace(v11) + 24) = v13;
      WdLogGlobalForLineNumber = 14743;
    }
    v22 = (_DWORD *)((char *)a2 + 32);
  }
  ++*((_DWORD *)v13 + 7);
  if ( (**((_DWORD **)a2 + 49) & 0x20000000) != 0 )
  {
    v23 = *((_QWORD *)a2 + 6);
    if ( v23 && (*v22 & 4) == 0 )
      goto LABEL_25;
    if ( (*(_BYTE *)v22 & 0x60) == 0x60 )
    {
      VIDMM_GLOBAL::TransferAllocationDecommit(
        v11,
        a2,
        (struct VIDMM_LOCAL_ALLOC *)v23,
        (struct VIDMM_LOCAL_ALLOC *)v13);
      v23 = *((_QWORD *)a2 + 6);
    }
    if ( (*v22 & 4) != 0 && (*(_DWORD *)(v4 + 64) & 1) != 0 )
    {
      VidMmRecordAlloc(
        *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * ((*(_DWORD *)(v4 + 60) >> 2) & 0x3F)),
        v4,
        *(_QWORD *)(v23 + 8),
        1);
      VidMmRecordAlloc(
        *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * ((*(_DWORD *)(v4 + 60) >> 2) & 0x3F)),
        v4,
        *((_QWORD *)v13 + 1),
        0);
    }
    *((_QWORD *)v13 + 1) = v6;
    if ( *((_QWORD *)a2 + 6) )
    {
      *(_QWORD *)v13 = a2;
      v29 = *((_QWORD *)a2 + 6);
      if ( (*(_BYTE *)(v29 + 24) & 1) == 0 )
      {
        memset(&ApcState, 0, sizeof(ApcState));
        KeStackAttachProcess(*(PRKPROCESS *)(*(_QWORD *)(v29 + 8) + 16LL), &ApcState);
        VIDMM_GLOBAL::CloseOneAllocation(this, (__int64 **)(*(_QWORD *)(*((_QWORD *)a2 + 6) + 32LL) - 40LL), 0, 0, 0, 0);
        KeUnstackDetachProcess(&ApcState);
      }
    }
    *v22 &= ~4u;
  }
  *((_QWORD *)a2 + 6) = v13;
LABEL_25:
  if ( *((_DWORD *)a2 + 18) )
    (*(void (__fastcall **)(_QWORD, __int64, __int64 (__fastcall *)(), __int64, _DWORD, _DWORD, _DWORD))(**(_QWORD **)(*((_QWORD *)this + 4560) + 8LL * ((*(_DWORD *)(v4 + 60) >> 2) & 0x3F)) + 104LL))(
      *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * ((*(_DWORD *)(v4 + 60) >> 2) & 0x3F)),
      v4,
      AddResidencyPerfCountersCB,
      *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v6 + 4) + 8LL * *(unsigned int *)(*((_QWORD *)this + 3) + 240LL)) + 8LL)
    + 304LL * ((unsigned __int8)*(_DWORD *)(v4 + 60) >> 2)
    + 8,
      0,
      0,
      *(_QWORD *)(v4 + 16) >> 12);
  return (struct VIDMM_LOCAL_ALLOC *)v13;
}

```

## disassembly

```asm
0x1400f2fbc  mov     [rsp+arg_18], rbx
0x1400f2fc1  push    rbp
0x1400f2fc2  push    rsi
0x1400f2fc3  push    rdi
0x1400f2fc4  push    r12
0x1400f2fc6  push    r13
0x1400f2fc8  push    r14
0x1400f2fca  push    r15
0x1400f2fcc  sub     rsp, 90h
0x1400f2fd3  mov     rax, cs:__security_cookie
0x1400f2fda  xor     rax, rsp
0x1400f2fdd  mov     [rsp+0C8h+var_48], rax
0x1400f2fe5  mov     r13, [rdx]
0x1400f2fe8  xor     r12d, r12d
0x1400f2feb  mov     r14b, r9b
0x1400f2fee  mov     rbp, r8
0x1400f2ff1  mov     rbx, rdx
0x1400f2ff4  mov     r15, rcx
0x1400f2ff7  test    r8, r8
0x1400f2ffa  jz      loc_1400F32C5
0x1400f3000  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400f3007  cmp     [rax], r12b
0x1400f300a  jz      short loc_1400F3026
0x1400f300c  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400f3013  nop     dword ptr [rax+rax+00h]
0x1400f3018  mov     [rax+18h], rbx
0x1400f301c  mov     cs:WdLogGlobalForLineNumber, 3933h
0x1400f3026  test    rbp, rbp
0x1400f3029  jz      loc_1400F32D1
0x1400f302f  lea     rsi, [rbx+70h]
0x1400f3033  mov     rdx, [rsi]
0x1400f3036  cmp     rdx, rsi
0x1400f3039  jz      short loc_1400F304E
0x1400f303b  mov     rax, [rbx+188h]
0x1400f3042  test    dword ptr [rax], 20000000h
0x1400f3048  jz      loc_1400F3317
0x1400f304e  mov     rax, [rbx+188h]
0x1400f3055  mov     ecx, [rax]
0x1400f3057  mov     eax, 20000010h
0x1400f305c  and     ecx, eax; this
0x1400f305e  cmp     ecx, eax
0x1400f3060  jz      loc_1400F3336
0x1400f3066  mov     eax, [rbp+0A0h]
0x1400f306c  test    al, 20h
0x1400f306e  jz      loc_1400F3142
0x1400f3074  mov     edx, 32306956h
0x1400f3079  mov     ecx, 50h ; 'P'
0x1400f307e  mov     r8d, 100h
0x1400f3084  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400f3089  mov     rdi, rax
0x1400f308c  test    rax, rax
0x1400f308f  jz      short loc_1400F30CC
0x1400f3091  mov     [rax], rbx
0x1400f3094  mov     [rax+8], rbp
0x1400f3098  mov     al, [rax+18h]
0x1400f309b  and     al, 0F7h
0x1400f309d  shl     r14b, 3
0x1400f30a1  or      al, r14b
0x1400f30a4  mov     [rdi+18h], al
0x1400f30a7  lea     rax, [rdi+20h]
0x1400f30ab  mov     [rax+8], rax
0x1400f30af  mov     [rax], rax
0x1400f30b2  inc     dword ptr [rbx+80h]
0x1400f30b8  mov     rax, [rsi+8]
0x1400f30bc  cmp     [rax], rsi
0x1400f30bf  jz      loc_1400F3250
0x1400f30c5  mov     ecx, 3
0x1400f30ca  int     29h; Win8: RtlFailFast(ecx)
0x1400f30cc  lock inc cs:dword_140087690
0x1400f30d3  mov     ecx, 6
0x1400f30d8  call    cs:__imp_WdLogSingleEntry0
0x1400f30df  nop     dword ptr [rax+rax+00h]
0x1400f30e4  mov     eax, 39AEh
0x1400f30e9  lea     r9, aCouldnTAllocat_25; "Couldn't allocate memory for local allo"...
0x1400f30f0  mov     edx, 40001h
0x1400f30f5  mov     [rsp+0C8h+var_90], r12
0x1400f30fa  mov     [rsp+0C8h+var_98], r12
0x1400f30ff  mov     [rsp+0C8h+var_A0], r12
0x1400f3104  mov     qword ptr [rsp+0C8h+var_A8], rax
0x1400f3109  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f310f  call    DxgkLogInternalTriageEvent
0x1400f3114  xor     eax, eax
0x1400f3116  mov     rcx, [rsp+0C8h+var_48]
0x1400f311e  xor     rcx, rsp; StackCookie
0x1400f3121  call    __security_check_cookie
0x1400f3126  mov     rbx, [rsp+0C8h+arg_18]
0x1400f312e  add     rsp, 90h
0x1400f3135  pop     r15
0x1400f3137  pop     r14
0x1400f3139  pop     r13
0x1400f313b  pop     r12
0x1400f313d  pop     rdi
0x1400f313e  pop     rsi
0x1400f313f  pop     rbp
0x1400f3140  retn
0x1400f3142  cmp     rdx, rsi
0x1400f3145  jz      loc_1400F3074
0x1400f314b  lea     rdi, [rdx-30h]
0x1400f314f  cmp     [rdi+8], rbp
0x1400f3153  jz      short loc_1400F315A
0x1400f3155  mov     rdx, [rdx]
0x1400f3158  jmp     short loc_1400F3142
0x1400f315a  mov     al, [rdi+18h]
0x1400f315d  test    al, 1
0x1400f315f  jnz     loc_1400F335C
0x1400f3165  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400f316c  cmp     [rax], r12b
0x1400f316f  jnz     loc_1400F33CC
0x1400f3175  lea     rsi, [rbx+20h]
0x1400f3179  inc     dword ptr [rdi+1Ch]
0x1400f317c  mov     rax, [rbx+188h]
0x1400f3183  test    dword ptr [rax], 20000000h
0x1400f3189  jnz     loc_1400F3216
0x1400f318f  mov     [rbx+30h], rdi
0x1400f3193  cmp     [rbx+48h], r12d
0x1400f3197  jnz     short loc_1400F31A1
0x1400f3199  mov     rax, rdi
0x1400f319c  jmp     loc_1400F3116
0x1400f31a1  mov     r9d, [r13+3Ch]
0x1400f31a5  mov     rdx, r13
0x1400f31a8  mov     rax, [r15+8E80h]
0x1400f31af  mov     ecx, r9d
0x1400f31b2  mov     r11, [r13+10h]
0x1400f31b6  shr     rcx, 2
0x1400f31ba  and     ecx, 3Fh
0x1400f31bd  shr     r11, 0Ch
0x1400f31c1  mov     dword ptr [rsp+0C8h+var_98], r11d
0x1400f31c6  mov     dword ptr [rsp+0C8h+var_A0], r12d
0x1400f31cb  mov     dword ptr [rsp+0C8h+var_A8], r12d
0x1400f31d0  mov     rbx, [rax+rcx*8]
0x1400f31d4  mov     rax, [r15+18h]
0x1400f31d8  mov     r10, [rbx]
0x1400f31db  mov     ecx, [rax+0F0h]
0x1400f31e1  mov     rax, [rbp+20h]
0x1400f31e5  mov     r8, [rax+rcx*8]
0x1400f31e9  mov     eax, r9d
0x1400f31ec  shr     eax, 2
0x1400f31ef  mov     rcx, rbx
0x1400f31f2  and     eax, 3Fh
0x1400f31f5  imul    r9, rax, 130h
0x1400f31fc  mov     rax, [r10+68h]
0x1400f3200  add     r9, 8
0x1400f3204  add     r9, [r8+8]
0x1400f3208  lea     r8, AddResidencyPerfCountersCB
0x1400f320f  call    _guard_dispatch_icall
0x1400f3214  jmp     short loc_1400F3199
0x1400f3216  mov     r8, [rbx+30h]; struct VIDMM_LOCAL_ALLOC *
0x1400f321a  test    r8, r8
0x1400f321d  jnz     loc_1400F33EB
0x1400f3223  mov     eax, [rsi]
0x1400f3225  and     eax, 60h
0x1400f3228  cmp     al, 60h ; '`'
0x1400f322a  jz      loc_1400F33FA
0x1400f3230  mov     eax, [rsi]
0x1400f3232  test    al, 4
0x1400f3234  jnz     loc_1400F340E
0x1400f323a  mov     [rdi+8], rbp
0x1400f323e  cmp     [rbx+30h], r12
0x1400f3242  jnz     loc_1400F346C
0x1400f3248  and     dword ptr [rsi], 0FFFFFFFBh
0x1400f324b  jmp     loc_1400F318F
0x1400f3250  lea     r14, [rdi+30h]
0x1400f3254  mov     [r14], rsi
0x1400f3257  mov     [r14+8], rax
0x1400f325b  mov     [rax], r14
0x1400f325e  mov     [rsi+8], r14
0x1400f3262  lea     rsi, [rbx+20h]
0x1400f3266  mov     eax, [rsi]
0x1400f3268  test    al, 20h
0x1400f326a  jz      loc_1400F3179
0x1400f3270  mov     rdx, rdi; struct VIDMM_LOCAL_ALLOC *
0x1400f3273  mov     rcx, r15; this
0x1400f3276  call    ?CommitLocalBackingStore@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_LOCAL_ALLOC@@@Z; VIDMM_GLOBAL::CommitLocalBackingStore(VIDMM_LOCAL_ALLOC *)
0x1400f327b  test    eax, eax
0x1400f327d  jns     loc_1400F3179
0x1400f3283  mov     r8b, 1; bool
0x1400f3286  mov     rdx, rdi; struct VIDMM_LOCAL_ALLOC *
0x1400f3289  mov     rcx, r15; this
0x1400f328c  call    ?UncommitLocalBackingStore@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_LOCAL_ALLOC@@_N@Z; VIDMM_GLOBAL::UncommitLocalBackingStore(VIDMM_LOCAL_ALLOC *,bool)
0x1400f3291  dec     dword ptr [rbx+80h]
0x1400f3297  mov     rcx, [r14]
0x1400f329a  cmp     [rcx+8], r14
0x1400f329e  jnz     loc_1400F30C5
0x1400f32a4  mov     rax, [r14+8]
0x1400f32a8  cmp     [rax], r14
0x1400f32ab  jnz     loc_1400F30C5
0x1400f32b1  mov     [rax], rcx
0x1400f32b4  mov     [rcx+8], rax
0x1400f32b8  mov     rcx, rdi; void *
0x1400f32bb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400f32c0  jmp     loc_1400F3114
0x1400f32c5  mov     rbp, [rcx+8F40h]
0x1400f32cc  jmp     loc_1400F3000
0x1400f32d1  mov     ecx, 1
0x1400f32d6  call    cs:__imp_WdLogSingleEntry0
0x1400f32dd  nop     dword ptr [rax+rax+00h]
0x1400f32e2  mov     eax, 393Eh
0x1400f32e7  lea     r9, aTryingToOpenAl; "Trying to open allocation on non graphi"...
0x1400f32ee  jmp     short loc_1400F330D
0x1400f32f0  mov     ecx, 1
0x1400f32f5  call    cs:__imp_WdLogSingleEntry0
0x1400f32fc  nop     dword ptr [rax+rax+00h]
0x1400f3301  mov     eax, 395Bh
0x1400f3306  lea     r9, aTryingToOpenAl_0; "Trying to open Alloc backed by Existing"...
0x1400f330d  mov     edx, 40000h
0x1400f3312  jmp     loc_1400F30F5
0x1400f3317  mov     ecx, 1
0x1400f331c  call    cs:__imp_WdLogSingleEntry0
0x1400f3323  nop     dword ptr [rax+rax+00h]
0x1400f3328  mov     eax, 3948h
0x1400f332d  lea     r9, aTryingToOpenAN; "Trying to open a non-shareable allocati"...
0x1400f3334  jmp     short loc_1400F330D
0x1400f3336  mov     rax, [rbx+30h]
0x1400f333a  test    rax, rax
0x1400f333d  jz      loc_1400F3066
0x1400f3343  cmp     [rax+8], rbp
0x1400f3347  jz      loc_1400F3066
0x1400f334d  cmp     rbp, [r15+8F40h]
0x1400f3354  jz      loc_1400F3114
0x1400f335a  jmp     short loc_1400F32F0
0x1400f335c  and     al, 0FEh
0x1400f335e  mov     [rdi+18h], al
0x1400f3361  mov     rdx, rdi
0x1400f3364  mov     ecx, 4
0x1400f3369  call    cs:__imp_WdLogSingleEntry1
0x1400f3370  nop     dword ptr [rax+rax+00h]
0x1400f3375  mov     cs:WdLogGlobalForLineNumber, 397Eh
0x1400f337f  mov     rax, [rbx+30h]
0x1400f3383  test    rax, rax
0x1400f3386  jz      short loc_1400F3392
0x1400f3388  test    byte ptr [rax+18h], 1
0x1400f338c  jz      loc_1400F3165
0x1400f3392  mov     [rbx+30h], rdi
0x1400f3396  mov     eax, [r13+40h]
0x1400f339a  test    al, 1
0x1400f339c  jz      loc_1400F3165
0x1400f33a2  mov     eax, [r13+3Ch]
0x1400f33a6  xor     r9d, r9d
0x1400f33a9  mov     rcx, [r15+8E80h]
0x1400f33b0  mov     rdx, r13
0x1400f33b3  mov     r8, [rdi+8]
0x1400f33b7  shr     rax, 2
0x1400f33bb  and     eax, 3Fh
0x1400f33be  mov     rcx, [rcx+rax*8]
0x1400f33c2  call    ?VidMmRecordAlloc@@YAXPEAUVIDMM_PHYSICAL_ADAPTER@@PEAUVIDMM_PHYSICAL_ALLOC@@PEAVVIDMM_PROCESS@@W4VIDMM_ALLOC_RECORD_TYPE@@@Z; VidMmRecordAlloc(VIDMM_PHYSICAL_ADAPTER *,VIDMM_PHYSICAL_ALLOC *,VIDMM_PROCESS *,VIDMM_ALLOC_RECORD_TYPE)
0x1400f33c7  jmp     loc_1400F3165
0x1400f33cc  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400f33d3  nop     dword ptr [rax+rax+00h]
0x1400f33d8  mov     [rax+18h], rdi
0x1400f33dc  mov     cs:WdLogGlobalForLineNumber, 3997h
0x1400f33e6  jmp     loc_1400F3175
0x1400f33eb  mov     eax, [rsi]
0x1400f33ed  test    al, 4
0x1400f33ef  jz      loc_1400F3193
0x1400f33f5  jmp     loc_1400F3223
0x1400f33fa  mov     r9, rdi; struct VIDMM_LOCAL_ALLOC *
0x1400f33fd  mov     rdx, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1400f3400  call    ?TransferAllocationDecommit@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@PEAUVIDMM_LOCAL_ALLOC@@1@Z; VIDMM_GLOBAL::TransferAllocationDecommit(VIDMM_GLOBAL_ALLOC *,VIDMM_LOCAL_ALLOC *,VIDMM_LOCAL_ALLOC *)
0x1400f3405  mov     r8, [rbx+30h]
0x1400f3409  jmp     loc_1400F3230
0x1400f340e  mov     eax, [r13+40h]
0x1400f3412  test    al, 1
0x1400f3414  jz      loc_1400F323A
0x1400f341a  mov     eax, [r13+3Ch]
0x1400f341e  mov     r9d, 1
0x1400f3424  mov     rcx, [r15+8E80h]
0x1400f342b  mov     rdx, r13
0x1400f342e  mov     r8, [r8+8]
0x1400f3432  shr     rax, 2
0x1400f3436  and     eax, 3Fh
0x1400f3439  mov     rcx, [rcx+rax*8]
0x1400f343d  call    ?VidMmRecordAlloc@@YAXPEAUVIDMM_PHYSICAL_ADAPTER@@PEAUVIDMM_PHYSICAL_ALLOC@@PEAVVIDMM_PROCESS@@W4VIDMM_ALLOC_RECORD_TYPE@@@Z; VidMmRecordAlloc(VIDMM_PHYSICAL_ADAPTER *,VIDMM_PHYSICAL_ALLOC *,VIDMM_PROCESS *,VIDMM_ALLOC_RECORD_TYPE)
0x1400f3442  mov     eax, [r13+3Ch]
0x1400f3446  xor     r9d, r9d
0x1400f3449  mov     rcx, [r15+8E80h]
0x1400f3450  mov     rdx, r13
0x1400f3453  mov     r8, [rdi+8]
0x1400f3457  shr     rax, 2
0x1400f345b  and     eax, 3Fh
0x1400f345e  mov     rcx, [rcx+rax*8]
0x1400f3462  call    ?VidMmRecordAlloc@@YAXPEAUVIDMM_PHYSICAL_ADAPTER@@PEAUVIDMM_PHYSICAL_ALLOC@@PEAVVIDMM_PROCESS@@W4VIDMM_ALLOC_RECORD_TYPE@@@Z; VidMmRecordAlloc(VIDMM_PHYSICAL_ADAPTER *,VIDMM_PHYSICAL_ALLOC *,VIDMM_PROCESS *,VIDMM_ALLOC_RECORD_TYPE)
0x1400f3467  jmp     loc_1400F323A
0x1400f346c  mov     [rdi], rbx
0x1400f346f  mov     rcx, [rbx+30h]
0x1400f3473  test    byte ptr [rcx+18h], 1
0x1400f3477  jnz     loc_1400F3248
0x1400f347d  xorps   xmm0, xmm0
0x1400f3480  lea     rdx, [rsp+0C8h+ApcState]; ApcState
0x1400f3485  movups  xmmword ptr [rsp+0C8h+ApcState.ApcListHead.Flink], xmm0
0x1400f348a  movups  xmmword ptr [rsp+0C8h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400f348f  movups  xmmword ptr [rsp+0C8h+ApcState.Process], xmm0
0x1400f3494  mov     rcx, [rcx+8]
0x1400f3498  mov     rcx, [rcx+10h]; PROCESS
0x1400f349c  call    cs:__imp_KeStackAttachProcess
0x1400f34a3  nop     dword ptr [rax+rax+00h]
0x1400f34a8  mov     rcx, [rbx+30h]
0x1400f34ac  xor     r9d, r9d; bool
0x1400f34af  mov     [rsp+0C8h+var_A0], r12; struct _KEVENT **
0x1400f34b4  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC **
0x1400f34b7  mov     dword ptr [rsp+0C8h+var_A8], r12d; struct _D3DDDICB_DESTROYALLOCATION2FLAGS
  ... truncated ...
```
