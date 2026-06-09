# NtfsFspCloseInternal

- ea: `0x14013af10`
- end: `0x14013b85c`
- name: `NtfsFspCloseInternal`
- size: `2380`
- prototype: ``
- caller_count: `11`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140020524`
- `0x1400df880`
- `0x140138c20`
- `0x14013ae70`
- `0x1401a0dd0`
- `0x1401a2cb0`
- `0x1401aa6dc`
- `0x1401aae60`
- `0x1401cfc18`
- `0x1401d1f5c`
- `0x140230888`

## callees

- `0x1400054e8`
- `0x140007ea0`
- `0x1400082b0`
- `0x140012ab0`
- `0x140016ea0`
- `0x140017030`
- `0x140017480`
- `0x1400291f0`
- `0x140029d80`
- `0x140059250`
- `0x1400596c0`
- `0x140139ed0`
- `0x14013ad80`
- `0x14013af10`
- `0x14013b870`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14013af76`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14013af76`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14013b2c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14013b6d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14013b2c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14013b6d0`
- `ntoskrnl!IoSetActivityIdThread` at `0x14013b0c3`
- `ntoskrnl!IoSetActivityIdThread` at `0x14013b0c3`
- `ntoskrnl!IoClearActivityIdThread` at `0x14013b243`
- `ntoskrnl!IoClearActivityIdThread` at `0x14013b6b2`
- `ntoskrnl!IoClearActivityIdThread` at `0x14013b243`
- `ntoskrnl!IoClearActivityIdThread` at `0x14013b6b2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013b25e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013b25e`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b081`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b5c0`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b67c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b84b`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b081`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b5c0`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b67c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b84b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14013afff`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14013b4fe`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14013b5a2`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14013afff`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14013b4fe`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14013b5a2`
- `ntoskrnl!ExRaiseStatus` at `0x14013b6ee`
- `ntoskrnl!ExRaiseStatus` at `0x14013b6ee`

## pseudocode

```c
void __fastcall NtfsFspCloseInternal(void *a1, __int64 a2, char a3, char a4, char a5)
{
  char **v7; // r15
  unsigned int v8; // r14d
  __int64 v9; // rdx
  char *v10; // rbx
  __int64 v11; // rcx
  char **v12; // rax
  char v13; // r15
  _QWORD *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // r13
  __int64 v17; // r12
  int v18; // ebx
  __int64 v19; // rcx
  bool v20; // sf
  char *v21; // rcx
  __int64 v22; // r8
  char *v23; // r9
  __int64 v24; // r8
  char **v25; // rax
  __int64 v26; // r9
  char **v27; // r8
  _QWORD *v28; // rbx
  bool v29; // bl
  __int64 v30; // rcx
  char v32; // [rsp+51h] [rbp-E7h]
  char v33; // [rsp+52h] [rbp-E6h]
  void *v34; // [rsp+58h] [rbp-E0h] BYREF
  _WORD *v35; // [rsp+60h] [rbp-D8h] BYREF
  unsigned int v36; // [rsp+68h] [rbp-D0h]
  __int64 v37; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v38; // [rsp+78h] [rbp-C0h]
  PVOID Entry; // [rsp+80h] [rbp-B8h]
  char **v40; // [rsp+88h] [rbp-B0h]
  char *v41; // [rsp+90h] [rbp-A8h]
  __int64 v42; // [rsp+98h] [rbp-A0h]
  __int64 v43; // [rsp+A0h] [rbp-98h]
  __int64 v44; // [rsp+A8h] [rbp-90h]
  __int64 v45; // [rsp+B0h] [rbp-88h]
  _BYTE v46[32]; // [rsp+B8h] [rbp-80h] BYREF
  __int64 v47; // [rsp+D8h] [rbp-60h]
  __int128 v48; // [rsp+E0h] [rbp-58h] BYREF
  __int64 v49; // [rsp+F0h] [rbp-48h]

  v45 = a2;
  memset(v46, 0, sizeof(v46));
  v47 = 0;
  v37 = 0;
  v48 = 0;
  v49 = 0;
  KeEnterCriticalRegion();
  v7 = (char **)(a2 + 8440);
  v40 = v7;
  if ( *v7 == (char *)v7 )
  {
    v28 = (_QWORD *)(a2 + 8400);
    if ( (_QWORD *)*v28 == v28 )
    {
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 8456));
      v29 = *v7 == (char *)v7 && (_QWORD *)*v28 == v28;
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 8456));
      if ( v29 )
        goto LABEL_38;
    }
  }
  v8 = 0;
  v32 = 0;
  v41 = (char *)(a2 + 8440);
  if ( a1 )
  {
    v34 = a1;
  }
  else
  {
    v34 = 0;
    NtfsInitializeIrpContextInternal(0, 1, 0, (__int64 *)&v34);
    a1 = v34;
    if ( !v34 )
    {
      KeAcquireGuardedMutex(&stru_140095AE8);
      v32 = 1;
      a1 = qword_140095B20;
      v34 = qword_140095B20;
      v35 = qword_140095B20;
      memset(qword_140095B20, 0, 0x290u);
      if ( !(unsigned int)NtfsInitializeIrpContextInternal(0, 1, 0, (__int64 *)&v35) )
        v35[1] = 656;
    }
  }
  *((_QWORD *)a1 + 13) = a2;
  if ( a2 && (*(_DWORD *)(a2 + 24) & 0x20000) != 0 )
    *((_QWORD *)a1 + 2) |= 0x100000uLL;
  else
    *((_QWORD *)a1 + 2) &= ~0x100000uLL;
  v42 = NtfsInitializeTopLevelIrp(v46, 1, a2);
  do
  {
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 8456));
    v9 = a2 + 8400;
    v10 = *(char **)(a2 + 8400);
    if ( v10 == (char *)(a2 + 8400) )
    {
      v10 = 0;
    }
    else
    {
      v11 = *(_QWORD *)v10;
      if ( *(char **)(*(_QWORD *)v10 + 8LL) != v10 )
        goto LABEL_70;
      v12 = (char **)*((_QWORD *)v10 + 1);
      if ( *v12 != v10 )
        goto LABEL_70;
      *v12 = (char *)v11;
      *(_QWORD *)(v11 + 8) = v12;
      --*(_DWORD *)(a2 + 8420);
    }
    v13 = 0;
    if ( !v10 )
    {
      if ( !a4 || *(_BYTE *)(a2 + 8417) )
        goto LABEL_46;
      if ( !*(_BYTE *)(a2 + 8418) )
        goto LABEL_13;
      if ( a5 || *(_DWORD *)(a2 + 8428) > (unsigned int)NtfsMinDelayCloseCount )
      {
LABEL_46:
        v21 = *v40;
        if ( *v40 != v41 )
        {
          v22 = *(_QWORD *)(*((_QWORD *)v21 + 4) + 184LL);
          if ( *(char **)(v22 + 272) == v21 )
          {
            v23 = (char *)*((_QWORD *)v21 + 2);
            if ( v23 == v21 + 16 )
              *(_QWORD *)(v22 + 272) = 0;
            else
              *(_QWORD *)(v22 + 272) = v23 - 16;
          }
          v24 = *(_QWORD *)v21;
          if ( *(char **)(*(_QWORD *)v21 + 8LL) != v21
            || (v25 = (char **)*((_QWORD *)v21 + 1), *v25 != v21)
            || (*v25 = (char *)v24,
                *(_QWORD *)(v24 + 8) = v25,
                v26 = *((_QWORD *)v21 + 2),
                *(char **)(v26 + 8) != v21 + 16)
            || (v27 = (char **)*((_QWORD *)v21 + 3), *v27 != v21 + 16) )
          {
LABEL_70:
            __fastfail(3u);
          }
          v10 = v21;
          *v27 = (char *)v26;
          *(_QWORD *)(v26 + 8) = v27;
          --*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v21 + 4) + 184LL) + 268LL);
          --*(_DWORD *)(a2 + 8428);
          v13 = 1;
        }
      }
      else if ( *(_BYTE *)(a2 + 8418) )
      {
        *(_BYTE *)(a2 + 8418) = 0;
      }
    }
LABEL_13:
    if ( *(_BYTE *)(a2 + 8417)
      && (*(_QWORD *)v9 == v9 || (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v9 + 32LL) + 184LL) + 4LL) & 1) == 0) )
    {
      *(_BYTE *)(a2 + 8417) = 0;
    }
    if ( !v13 && a4 && !v10 && a3 )
      *(_BYTE *)(a2 + 8416) = 0;
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 8456));
    if ( !v10 )
      break;
    Entry = v10;
    v14 = (_QWORD *)*((_QWORD *)v10 + 8);
    if ( v14 )
    {
      *((_QWORD *)&v48 + 1) = *v14;
      v49 = v14[1];
      *(_QWORD *)&v48 = (char *)&v48 + 8;
    }
    else
    {
      *(_QWORD *)&v48 = 0;
    }
    v38 = IoSetActivityIdThread(v48);
    if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
      McTemplateK0pq_EtwWriteTransfer(v15, WORKITEM_START, v48);
    v16 = *((_QWORD *)v10 + 4);
    v43 = v16;
    v37 = *((_QWORD *)v10 + 5);
    v17 = *((_QWORD *)v10 + 6);
    v44 = v17;
    LODWORD(v35) = (unsigned __int8)v10[56];
    v33 = v10[57];
    *((_DWORD *)a1 + 1) &= 0xDE6B4008;
    *((_DWORD *)a1 + 2) &= 0xFFFFFFFC;
    *((_DWORD *)a1 + 1) |= 0x400u;
    *((_DWORD *)a1 + 3) |= 0x41u;
    if ( v13 )
      *((_QWORD *)a1 + 2) |= 0x8000uLL;
    else
      *((_QWORD *)a1 + 2) &= ~0x8000uLL;
    v8 = 0;
    v18 = (int)v35;
    do
    {
      NtfsUpdateIrpContextWithTopLevel(a1, v42);
      if ( v8 == -1073741432 )
        NtfsCheckpointForLogFileFull(a1);
      if ( a1 )
        NtfsPreRequestProcessingExtend((_DWORD)a1);
      v8 = NtfsCommonClose((_DWORD)a1, v16, *(_QWORD *)(v16 + 184), a2, (__int64)&v37, v17, v18, v33, 1);
      v36 = v8;
      if ( (v8 == -1073741432 || v8 == -1073741608) && !a4 )
      {
        *((_DWORD *)a1 + 1) &= ~0x400u;
        if ( NtfsStatusDebugFlags && v8 - 298 > 1 && v8 != -1073741608 && v8 + 2147483643 > 1 )
          NtfsStatusTraceAndDebugInternal(a1, v8, 525286);
        NtfsExtendedCompleteRequestInternal(a1, 0, v8, 0, (v8 & 0x80000000) == 0);
        if ( v32 )
          KeReleaseGuardedMutex(&stru_140095AE8);
        if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
          McTemplateK0pq_EtwWriteTransfer(v30, WORKITEM_COMPLETE, v48);
        IoClearActivityIdThread(v38);
        NtfsQueueClose(0, Entry, 0);
        KeLeaveCriticalRegion();
        if ( NtfsStatusDebugFlags && v8 - 298 > 1 && v8 != -1073741608 && v8 + 2147483643 > 1 )
          NtfsStatusTraceAndDebugInternal(0, v8, 525312);
        ExRaiseStatus(v8);
      }
    }
    while ( v8 == -1073741432 || v8 == -1073741608 );
    if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
      McTemplateK0pq_EtwWriteTransfer(v19, WORKITEM_COMPLETE, v48);
    IoClearActivityIdThread(v38);
    ExFreeToLookasideListEx(&NtfsCloseEntryLookasideList, Entry);
  }
  while ( a3 );
  if ( !NtfsStatusDebugFlags )
    goto LABEL_35;
  v20 = (v8 & 0x80000000) != 0;
  if ( v8 )
  {
    if ( v8 != 294
      && v8 - 298 > 1
      && v8 < 0xFFFFFFED
      && v8 != -1073741802
      && v8 != -1073741807
      && v8 + 2147483643 > 1
      && v8 != 259 )
    {
      NtfsStatusTraceAndDebugInternal(a1, v8, 525341);
    }
LABEL_35:
    v20 = (v8 & 0x80000000) != 0;
  }
  NtfsExtendedCompleteRequestInternal(a1, 0, v8, 0, !v20);
  if ( v32 )
    KeReleaseGuardedMutex(&stru_140095AE8);
LABEL_38:
  if ( a4 )
    _InterlockedDecrement((volatile signed __int32 *)(a2 + 284));
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14013af10  mov     r11, rsp
0x14013af13  mov     [r11+20h], r9b
0x14013af17  push    rbx
0x14013af18  push    rsi
0x14013af19  push    rdi
0x14013af1a  push    r12
0x14013af1c  push    r13
0x14013af1e  push    r14
0x14013af20  push    r15
0x14013af22  sub     rsp, 100h
0x14013af29  mov     rax, cs:__security_cookie
0x14013af30  xor     rax, rsp
0x14013af33  mov     [rsp+138h+var_40], rax
0x14013af3b  movzx   r12d, r8b
0x14013af3f  mov     [rsp+138h+var_E8], r8b
0x14013af44  mov     rdi, rdx
0x14013af47  mov     rsi, rcx
0x14013af4a  mov     [rsp+138h+var_88], rdx
0x14013af52  xorps   xmm0, xmm0
0x14013af55  xor     eax, eax
0x14013af57  movups  xmmword ptr [r11-80h], xmm0
0x14013af5c  movups  xmmword ptr [r11-70h], xmm0
0x14013af61  mov     [r11-60h], rax
0x14013af65  xor     r13d, r13d
0x14013af68  mov     [rsp+138h+var_C8], r13
0x14013af6d  movups  xmmword ptr [r11-58h], xmm0
0x14013af72  mov     [r11-48h], rax
0x14013af76  call    cs:__imp_KeEnterCriticalRegion
0x14013af7d  nop     dword ptr [rax+rax+00h]
0x14013af82  lea     r15, [rdi+20F8h]
0x14013af89  mov     [rsp+138h+var_B0], r15
0x14013af91  cmp     [r15], r15
0x14013af94  jz      loc_14013B58B
0x14013af9a  mov     [rsp+138h+var_E4], r12b
0x14013af9f  mov     r14d, r13d
0x14013afa2  mov     [rsp+138h+var_E7], r13b
0x14013afa7  mov     [rsp+138h+var_A8], r15
0x14013afaf  test    rsi, rsi
0x14013afb2  jz      loc_14013B4D3
0x14013afb8  mov     [rsp+138h+var_E0], rsi
0x14013afbd  mov     [rsi+68h], rdi
0x14013afc1  test    rdi, rdi
0x14013afc4  jz      short loc_14013AFD3
0x14013afc6  test    dword ptr [rdi+18h], 20000h
0x14013afcd  jnz     loc_14013B81E
0x14013afd3  and     qword ptr [rsi+10h], 0FFFFFFFFFFEFFFFFh
0x14013afdb  mov     r8, rdi
0x14013afde  mov     edx, 1
0x14013afe3  lea     rcx, [rsp+138h+var_80]
0x14013afeb  call    NtfsInitializeTopLevelIrp
0x14013aff0  mov     [rsp+138h+var_A0], rax
0x14013aff8  lea     rcx, [rdi+2108h]; Mutex
0x14013afff  call    cs:__imp_KeAcquireGuardedMutex
0x14013b006  nop     dword ptr [rax+rax+00h]
0x14013b00b  lea     rdx, [rdi+20D0h]
0x14013b012  mov     rbx, [rdx]
0x14013b015  cmp     rbx, rdx
0x14013b018  jz      loc_14013B559
0x14013b01e  mov     rcx, [rbx]
0x14013b021  cmp     [rcx+8], rbx
0x14013b025  jnz     loc_14013B4CC
0x14013b02b  mov     rax, [rbx+8]
0x14013b02f  cmp     [rax], rbx
0x14013b032  jnz     loc_14013B4CC
0x14013b038  mov     [rax], rcx
0x14013b03b  mov     [rcx+8], rax
0x14013b03f  mov     eax, [rdi+20E4h]
0x14013b045  dec     eax
0x14013b047  mov     [rdi+20E4h], eax
0x14013b04d  xor     r15b, r15b
0x14013b050  movzx   r10d, [rsp+138h+arg_18]
0x14013b059  test    rbx, rbx
0x14013b05c  jz      loc_14013B2F5
0x14013b062  movzx   eax, byte ptr [rdi+20E1h]
0x14013b069  test    al, al
0x14013b06b  jnz     loc_14013B561
0x14013b071  test    r15b, r15b
0x14013b074  jz      loc_14013B3EF
0x14013b07a  lea     rcx, [rdi+2108h]; Mutex
0x14013b081  call    cs:__imp_KeReleaseGuardedMutex
0x14013b088  nop     dword ptr [rax+rax+00h]
0x14013b08d  test    rbx, rbx
0x14013b090  jz      loc_14013B27B
0x14013b096  mov     [rsp+138h+Entry], rbx
0x14013b09e  mov     rcx, [rbx+40h]
0x14013b0a2  test    rcx, rcx
0x14013b0a5  jnz     loc_14013B4A0
0x14013b0ab  mov     [rsp+138h+var_58], r13
0x14013b0b3  mov     rax, [rsp+138h+var_58]
0x14013b0bb  mov     rcx, [rsp+138h+var_58]
0x14013b0c3  call    cs:__imp_IoSetActivityIdThread
0x14013b0ca  nop     dword ptr [rax+rax+00h]
0x14013b0cf  mov     [rsp+138h+var_C0], rax
0x14013b0d4  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x14013b0db  jnz     loc_14013B5D9
0x14013b0e1  mov     r13, [rbx+20h]
0x14013b0e5  mov     [rsp+138h+var_98], r13
0x14013b0ed  mov     rax, [rbx+28h]
0x14013b0f1  mov     [rsp+138h+var_C8], rax
0x14013b0f6  mov     r12, [rbx+30h]
0x14013b0fa  mov     [rsp+138h+var_90], r12
0x14013b102  movzx   eax, byte ptr [rbx+38h]
0x14013b106  mov     dword ptr [rsp+138h+var_D8], eax
0x14013b10a  movzx   eax, byte ptr [rbx+39h]
0x14013b10e  mov     [rsp+138h+var_E6], al
0x14013b112  mov     [rsp+138h+var_E5], al
0x14013b116  and     dword ptr [rsi+4], 0DE6B4008h
0x14013b11d  and     dword ptr [rsi+8], 0FFFFFFFCh
0x14013b121  or      dword ptr [rsi+4], 400h
0x14013b128  or      dword ptr [rsi+0Ch], 41h
0x14013b12c  test    r15b, r15b
0x14013b12f  jz      loc_14013B3E2
0x14013b135  or      qword ptr [rsi+10h], 8000h
0x14013b13d  xor     eax, eax
0x14013b13f  mov     r14d, eax
0x14013b142  mov     ebx, dword ptr [rsp+138h+var_D8]
0x14013b146  movzx   r15d, [rsp+138h+var_E6]
0x14013b14c  mov     rdx, [rsp+138h+var_A0]
0x14013b154  mov     rcx, rsi
0x14013b157  call    NtfsUpdateIrpContextWithTopLevel
0x14013b15c  nop
0x14013b15d  cmp     r14d, 0C0000188h
0x14013b164  jnz     short loc_14013B16E
0x14013b166  mov     rcx, rsi
0x14013b169  call    NtfsCheckpointForLogFileFull
0x14013b16e  test    rsi, rsi
0x14013b171  jz      short loc_14013B17E
0x14013b173  mov     edx, r14d
0x14013b176  mov     rcx, rsi
0x14013b179  call    NtfsPreRequestProcessingExtend
0x14013b17e  mov     [rsp+138h+var_F8], 1
0x14013b183  mov     [rsp+138h+var_100], r15b
0x14013b188  mov     [rsp+138h+var_108], ebx
0x14013b18c  mov     [rsp+138h+var_110], r12
0x14013b191  lea     rax, [rsp+138h+var_C8]
0x14013b196  mov     [rsp+138h+var_118], rax
0x14013b19b  mov     r9, rdi
0x14013b19e  mov     r8, [r13+0B8h]
0x14013b1a5  mov     rdx, r13
0x14013b1a8  mov     rcx, rsi
0x14013b1ab  call    NtfsCommonClose
0x14013b1b0  mov     r14d, eax
0x14013b1b3  mov     [rsp+138h+var_D0], eax
0x14013b1b7  jmp     short loc_14013B1FD
0x14013b1b9  mov     r8d, eax
0x14013b1bc  xor     edx, edx
0x14013b1be  mov     rsi, [rsp+138h+var_E0]
0x14013b1c3  mov     rcx, rsi
0x14013b1c6  call    NtfsProcessException
0x14013b1cb  mov     r14d, eax
0x14013b1ce  mov     [rsp+138h+var_D0], eax
0x14013b1d2  mov     r13, [rsp+138h+var_98]
0x14013b1da  mov     r12, [rsp+138h+var_90]
0x14013b1e2  movzx   r15d, [rsp+138h+var_E5]
0x14013b1e8  mov     rdi, [rsp+138h+var_88]
0x14013b1f0  movzx   eax, [rsp+138h+var_E4]
0x14013b1f5  mov     [rsp+138h+var_E8], al
0x14013b1f9  mov     ebx, dword ptr [rsp+138h+var_D8]
0x14013b1fd  cmp     r14d, 0C0000188h
0x14013b204  jz      loc_14013B62B
0x14013b20a  cmp     r14d, 0C00000D8h
0x14013b211  jz      loc_14013B62B
0x14013b217  cmp     r14d, 0C0000188h
0x14013b21e  jz      loc_14013B14C
0x14013b224  cmp     r14d, 0C00000D8h
0x14013b22b  jz      loc_14013B14C
0x14013b231  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x14013b238  jnz     loc_14013B5FA
0x14013b23e  mov     rcx, [rsp+138h+var_C0]
0x14013b243  call    cs:__imp_IoClearActivityIdThread
0x14013b24a  nop     dword ptr [rax+rax+00h]
0x14013b24f  mov     rdx, [rsp+138h+Entry]; Entry
0x14013b257  lea     rcx, NtfsCloseEntryLookasideList; Lookaside
0x14013b25e  call    cs:__imp_ExFreeToLookasideListEx
0x14013b265  nop     dword ptr [rax+rax+00h]
0x14013b26a  cmp     [rsp+138h+var_E8], 0
0x14013b26f  mov     r13d, 0
0x14013b275  jnz     loc_14013AFF8
0x14013b27b  movzx   eax, cs:NtfsStatusDebugFlags
0x14013b282  test    al, al
0x14013b284  jnz     loc_14013B416
0x14013b28a  test    r14d, r14d
0x14013b28d  mov     eax, 0
0x14013b292  setns   al
0x14013b295  mov     dword ptr [rsp+138h+var_118], eax
0x14013b299  xor     r9d, r9d
0x14013b29c  mov     r8d, r14d
0x14013b29f  xor     edx, edx
0x14013b2a1  mov     rcx, rsi
0x14013b2a4  call    NtfsExtendedCompleteRequestInternal
0x14013b2a9  cmp     [rsp+138h+var_E7], 0
0x14013b2ae  jnz     loc_14013B844
0x14013b2b4  cmp     [rsp+138h+arg_18], 0
0x14013b2bc  jz      short loc_14013B2C5
0x14013b2be  lock dec dword ptr [rdi+11Ch]
0x14013b2c5  call    cs:__imp_KeLeaveCriticalRegion
0x14013b2cc  nop     dword ptr [rax+rax+00h]
0x14013b2d1  mov     rcx, [rsp+138h+var_40]
0x14013b2d9  xor     rcx, rsp; StackCookie
0x14013b2dc  call    __security_check_cookie
0x14013b2e1  add     rsp, 100h
0x14013b2e8  pop     r15
0x14013b2ea  pop     r14
0x14013b2ec  pop     r13
0x14013b2ee  pop     r12
0x14013b2f0  pop     rdi
0x14013b2f1  pop     rsi
0x14013b2f2  pop     rbx
0x14013b2f3  retn
0x14013b2f5  test    r10b, r10b
0x14013b2f8  jz      short loc_14013B32E
0x14013b2fa  movzx   eax, byte ptr [rdi+20E1h]
0x14013b301  test    al, al
0x14013b303  jnz     short loc_14013B32E
0x14013b305  cmp     [rdi+20E2h], r15b
0x14013b30c  jz      loc_14013B062
0x14013b312  cmp     [rsp+138h+arg_20], r15b
0x14013b31a  jnz     short loc_14013B32E
0x14013b31c  mov     eax, [rdi+20ECh]
0x14013b322  cmp     eax, cs:NtfsMinDelayCloseCount
0x14013b328  jbe     loc_14013B82B
0x14013b32e  mov     rcx, [rsp+138h+var_B0]
0x14013b336  mov     rcx, [rcx]
0x14013b339  cmp     rcx, [rsp+138h+var_A8]
0x14013b341  jz      loc_14013B062
0x14013b347  mov     rax, [rcx+20h]
0x14013b34b  mov     r8, [rax+0B8h]
0x14013b352  cmp     [r8+110h], rcx
0x14013b359  jnz     short loc_14013B372
0x14013b35b  lea     rax, [rcx+10h]
0x14013b35f  mov     r9, [rax]
0x14013b362  cmp     r9, rax
0x14013b365  jnz     loc_14013B61B
0x14013b36b  mov     [r8+110h], r13
0x14013b372  mov     r8, [rcx]
0x14013b375  cmp     [r8+8], rcx
0x14013b379  jnz     loc_14013B4CC
0x14013b37f  mov     rax, [rcx+8]
0x14013b383  cmp     [rax], rcx
0x14013b386  jnz     loc_14013B4CC
0x14013b38c  mov     [rax], r8
0x14013b38f  mov     [r8+8], rax
0x14013b393  lea     rax, [rcx+10h]
0x14013b397  mov     r9, [rax]
0x14013b39a  cmp     [r9+8], rax
0x14013b39e  jnz     loc_14013B4CC
0x14013b3a4  mov     r8, [rcx+18h]
0x14013b3a8  cmp     [r8], rax
0x14013b3ab  jnz     loc_14013B4CC
0x14013b3b1  mov     rbx, rcx
0x14013b3b4  mov     [r8], r9
0x14013b3b7  mov     [r9+8], r8
0x14013b3bb  mov     rax, [rcx+20h]
0x14013b3bf  mov     rcx, [rax+0B8h]
0x14013b3c6  dec     dword ptr [rcx+10Ch]
0x14013b3cc  mov     eax, [rdi+20ECh]
0x14013b3d2  dec     eax
0x14013b3d4  mov     [rdi+20ECh], eax
0x14013b3da  mov     r15b, 1
0x14013b3dd  jmp     loc_14013B062
0x14013b3e2  and     qword ptr [rsi+10h], 0FFFFFFFFFFFF7FFFh
0x14013b3ea  jmp     loc_14013B13D
0x14013b3ef  test    r10b, r10b
0x14013b3f2  jz      loc_14013B07A
0x14013b3f8  test    rbx, rbx
0x14013b3fb  jnz     loc_14013B07A
0x14013b401  cmp     [rsp+138h+var_E8], bl
0x14013b405  jz      loc_14013B07A
0x14013b40b  mov     [rdi+20E0h], bl
0x14013b411  jmp     loc_14013B07A
0x14013b416  test    r14d, r14d
0x14013b419  jz      loc_14013B28D
0x14013b41f  cmp     r14d, 126h
0x14013b426  jz      loc_14013B28A
0x14013b42c  lea     eax, [r14-12Ah]
0x14013b433  cmp     eax, 1
0x14013b436  jbe     loc_14013B28A
0x14013b43c  cmp     r14d, 0FFFFFFEDh
0x14013b440  jnb     loc_14013B28A
0x14013b446  cmp     r14d, 0C00000D8h
0x14013b44d  jz      loc_14013B28A
0x14013b453  cmp     r14d, 0C0000016h
0x14013b45a  jz      loc_14013B28A
0x14013b460  cmp     r14d, 0C0000011h
0x14013b467  jz      loc_14013B28A
0x14013b46d  lea     eax, [r14+7FFFFFFBh]
0x14013b474  cmp     eax, 1
0x14013b477  jbe     loc_14013B28A
0x14013b47d  cmp     r14d, 103h
0x14013b484  jz      loc_14013B28A
0x14013b48a  mov     r8d, 8041Dh
0x14013b490  mov     edx, r14d
0x14013b493  mov     rcx, rsi
0x14013b496  call    NtfsStatusTraceAndDebugInternal
0x14013b49b  jmp     loc_14013B28A
0x14013b4a0  mov     rax, [rcx]
0x14013b4a3  mov     [rsp+138h+var_50], rax
0x14013b4ab  mov     rax, [rcx+8]
0x14013b4af  mov     [rsp+138h+var_48], rax
0x14013b4b7  lea     rax, [rsp+138h+var_50]
  ... truncated ...
```
