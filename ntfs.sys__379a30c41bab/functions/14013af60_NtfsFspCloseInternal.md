# NtfsFspCloseInternal

- ea: `0x14013af60`
- end: `0x14013b8ac`
- name: `NtfsFspCloseInternal`
- size: `2380`
- prototype: ``
- caller_count: `11`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140020524`
- `0x1400df880`
- `0x140138c70`
- `0x14013aec0`
- `0x1401a0e20`
- `0x1401a2d00`
- `0x1401aa72c`
- `0x1401aaeb0`
- `0x1401cfc68`
- `0x1401d1fac`
- `0x1402308d8`

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
- `0x1400592c0`
- `0x140059740`
- `0x140139f20`
- `0x14013add0`
- `0x14013af60`
- `0x14013b8c0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14013afc6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14013afc6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14013b315`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14013b720`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14013b315`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14013b720`
- `ntoskrnl!IoSetActivityIdThread` at `0x14013b113`
- `ntoskrnl!IoSetActivityIdThread` at `0x14013b113`
- `ntoskrnl!IoClearActivityIdThread` at `0x14013b293`
- `ntoskrnl!IoClearActivityIdThread` at `0x14013b702`
- `ntoskrnl!IoClearActivityIdThread` at `0x14013b293`
- `ntoskrnl!IoClearActivityIdThread` at `0x14013b702`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013b2ae`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013b2ae`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b0d1`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b610`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b6cc`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b89b`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b0d1`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b610`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b6cc`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013b89b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14013b04f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14013b54e`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14013b5f2`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14013b04f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14013b54e`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14013b5f2`
- `ntoskrnl!ExRaiseStatus` at `0x14013b73e`
- `ntoskrnl!ExRaiseStatus` at `0x14013b73e`

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
0x14013af60  mov     r11, rsp
0x14013af63  mov     [r11+20h], r9b
0x14013af67  push    rbx
0x14013af68  push    rsi
0x14013af69  push    rdi
0x14013af6a  push    r12
0x14013af6c  push    r13
0x14013af6e  push    r14
0x14013af70  push    r15
0x14013af72  sub     rsp, 100h
0x14013af79  mov     rax, cs:__security_cookie
0x14013af80  xor     rax, rsp
0x14013af83  mov     [rsp+138h+var_40], rax
0x14013af8b  movzx   r12d, r8b
0x14013af8f  mov     [rsp+138h+var_E8], r8b
0x14013af94  mov     rdi, rdx
0x14013af97  mov     rsi, rcx
0x14013af9a  mov     [rsp+138h+var_88], rdx
0x14013afa2  xorps   xmm0, xmm0
0x14013afa5  xor     eax, eax
0x14013afa7  movups  xmmword ptr [r11-80h], xmm0
0x14013afac  movups  xmmword ptr [r11-70h], xmm0
0x14013afb1  mov     [r11-60h], rax
0x14013afb5  xor     r13d, r13d
0x14013afb8  mov     [rsp+138h+var_C8], r13
0x14013afbd  movups  xmmword ptr [r11-58h], xmm0
0x14013afc2  mov     [r11-48h], rax
0x14013afc6  call    cs:__imp_KeEnterCriticalRegion
0x14013afcd  nop     dword ptr [rax+rax+00h]
0x14013afd2  lea     r15, [rdi+20F8h]
0x14013afd9  mov     [rsp+138h+var_B0], r15
0x14013afe1  cmp     [r15], r15
0x14013afe4  jz      loc_14013B5DB
0x14013afea  mov     [rsp+138h+var_E4], r12b
0x14013afef  mov     r14d, r13d
0x14013aff2  mov     [rsp+138h+var_E7], r13b
0x14013aff7  mov     [rsp+138h+var_A8], r15
0x14013afff  test    rsi, rsi
0x14013b002  jz      loc_14013B523
0x14013b008  mov     [rsp+138h+var_E0], rsi
0x14013b00d  mov     [rsi+68h], rdi
0x14013b011  test    rdi, rdi
0x14013b014  jz      short loc_14013B023
0x14013b016  test    dword ptr [rdi+18h], 20000h
0x14013b01d  jnz     loc_14013B86E
0x14013b023  and     qword ptr [rsi+10h], 0FFFFFFFFFFEFFFFFh
0x14013b02b  mov     r8, rdi
0x14013b02e  mov     edx, 1
0x14013b033  lea     rcx, [rsp+138h+var_80]
0x14013b03b  call    NtfsInitializeTopLevelIrp
0x14013b040  mov     [rsp+138h+var_A0], rax
0x14013b048  lea     rcx, [rdi+2108h]; Mutex
0x14013b04f  call    cs:__imp_KeAcquireGuardedMutex
0x14013b056  nop     dword ptr [rax+rax+00h]
0x14013b05b  lea     rdx, [rdi+20D0h]
0x14013b062  mov     rbx, [rdx]
0x14013b065  cmp     rbx, rdx
0x14013b068  jz      loc_14013B5A9
0x14013b06e  mov     rcx, [rbx]
0x14013b071  cmp     [rcx+8], rbx
0x14013b075  jnz     loc_14013B51C
0x14013b07b  mov     rax, [rbx+8]
0x14013b07f  cmp     [rax], rbx
0x14013b082  jnz     loc_14013B51C
0x14013b088  mov     [rax], rcx
0x14013b08b  mov     [rcx+8], rax
0x14013b08f  mov     eax, [rdi+20E4h]
0x14013b095  dec     eax
0x14013b097  mov     [rdi+20E4h], eax
0x14013b09d  xor     r15b, r15b
0x14013b0a0  movzx   r10d, [rsp+138h+arg_18]
0x14013b0a9  test    rbx, rbx
0x14013b0ac  jz      loc_14013B345
0x14013b0b2  movzx   eax, byte ptr [rdi+20E1h]
0x14013b0b9  test    al, al
0x14013b0bb  jnz     loc_14013B5B1
0x14013b0c1  test    r15b, r15b
0x14013b0c4  jz      loc_14013B43F
0x14013b0ca  lea     rcx, [rdi+2108h]; Mutex
0x14013b0d1  call    cs:__imp_KeReleaseGuardedMutex
0x14013b0d8  nop     dword ptr [rax+rax+00h]
0x14013b0dd  test    rbx, rbx
0x14013b0e0  jz      loc_14013B2CB
0x14013b0e6  mov     [rsp+138h+Entry], rbx
0x14013b0ee  mov     rcx, [rbx+40h]
0x14013b0f2  test    rcx, rcx
0x14013b0f5  jnz     loc_14013B4F0
0x14013b0fb  mov     [rsp+138h+var_58], r13
0x14013b103  mov     rax, [rsp+138h+var_58]
0x14013b10b  mov     rcx, [rsp+138h+var_58]
0x14013b113  call    cs:__imp_IoSetActivityIdThread
0x14013b11a  nop     dword ptr [rax+rax+00h]
0x14013b11f  mov     [rsp+138h+var_C0], rax
0x14013b124  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x14013b12b  jnz     loc_14013B629
0x14013b131  mov     r13, [rbx+20h]
0x14013b135  mov     [rsp+138h+var_98], r13
0x14013b13d  mov     rax, [rbx+28h]
0x14013b141  mov     [rsp+138h+var_C8], rax
0x14013b146  mov     r12, [rbx+30h]
0x14013b14a  mov     [rsp+138h+var_90], r12
0x14013b152  movzx   eax, byte ptr [rbx+38h]
0x14013b156  mov     dword ptr [rsp+138h+var_D8], eax
0x14013b15a  movzx   eax, byte ptr [rbx+39h]
0x14013b15e  mov     [rsp+138h+var_E6], al
0x14013b162  mov     [rsp+138h+var_E5], al
0x14013b166  and     dword ptr [rsi+4], 0DE6B4008h
0x14013b16d  and     dword ptr [rsi+8], 0FFFFFFFCh
0x14013b171  or      dword ptr [rsi+4], 400h
0x14013b178  or      dword ptr [rsi+0Ch], 41h
0x14013b17c  test    r15b, r15b
0x14013b17f  jz      loc_14013B432
0x14013b185  or      qword ptr [rsi+10h], 8000h
0x14013b18d  xor     eax, eax
0x14013b18f  mov     r14d, eax
0x14013b192  mov     ebx, dword ptr [rsp+138h+var_D8]
0x14013b196  movzx   r15d, [rsp+138h+var_E6]
0x14013b19c  mov     rdx, [rsp+138h+var_A0]
0x14013b1a4  mov     rcx, rsi
0x14013b1a7  call    NtfsUpdateIrpContextWithTopLevel
0x14013b1ac  nop
0x14013b1ad  cmp     r14d, 0C0000188h
0x14013b1b4  jnz     short loc_14013B1BE
0x14013b1b6  mov     rcx, rsi
0x14013b1b9  call    NtfsCheckpointForLogFileFull
0x14013b1be  test    rsi, rsi
0x14013b1c1  jz      short loc_14013B1CE
0x14013b1c3  mov     edx, r14d
0x14013b1c6  mov     rcx, rsi
0x14013b1c9  call    NtfsPreRequestProcessingExtend
0x14013b1ce  mov     [rsp+138h+var_F8], 1
0x14013b1d3  mov     [rsp+138h+var_100], r15b
0x14013b1d8  mov     [rsp+138h+var_108], ebx
0x14013b1dc  mov     [rsp+138h+var_110], r12
0x14013b1e1  lea     rax, [rsp+138h+var_C8]
0x14013b1e6  mov     [rsp+138h+var_118], rax
0x14013b1eb  mov     r9, rdi
0x14013b1ee  mov     r8, [r13+0B8h]
0x14013b1f5  mov     rdx, r13
0x14013b1f8  mov     rcx, rsi
0x14013b1fb  call    NtfsCommonClose
0x14013b200  mov     r14d, eax
0x14013b203  mov     [rsp+138h+var_D0], eax
0x14013b207  jmp     short loc_14013B24D
0x14013b209  mov     r8d, eax
0x14013b20c  xor     edx, edx
0x14013b20e  mov     rsi, [rsp+138h+var_E0]
0x14013b213  mov     rcx, rsi
0x14013b216  call    NtfsProcessException
0x14013b21b  mov     r14d, eax
0x14013b21e  mov     [rsp+138h+var_D0], eax
0x14013b222  mov     r13, [rsp+138h+var_98]
0x14013b22a  mov     r12, [rsp+138h+var_90]
0x14013b232  movzx   r15d, [rsp+138h+var_E5]
0x14013b238  mov     rdi, [rsp+138h+var_88]
0x14013b240  movzx   eax, [rsp+138h+var_E4]
0x14013b245  mov     [rsp+138h+var_E8], al
0x14013b249  mov     ebx, dword ptr [rsp+138h+var_D8]
0x14013b24d  cmp     r14d, 0C0000188h
0x14013b254  jz      loc_14013B67B
0x14013b25a  cmp     r14d, 0C00000D8h
0x14013b261  jz      loc_14013B67B
0x14013b267  cmp     r14d, 0C0000188h
0x14013b26e  jz      loc_14013B19C
0x14013b274  cmp     r14d, 0C00000D8h
0x14013b27b  jz      loc_14013B19C
0x14013b281  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x14013b288  jnz     loc_14013B64A
0x14013b28e  mov     rcx, [rsp+138h+var_C0]
0x14013b293  call    cs:__imp_IoClearActivityIdThread
0x14013b29a  nop     dword ptr [rax+rax+00h]
0x14013b29f  mov     rdx, [rsp+138h+Entry]; Entry
0x14013b2a7  lea     rcx, NtfsCloseEntryLookasideList; Lookaside
0x14013b2ae  call    cs:__imp_ExFreeToLookasideListEx
0x14013b2b5  nop     dword ptr [rax+rax+00h]
0x14013b2ba  cmp     [rsp+138h+var_E8], 0
0x14013b2bf  mov     r13d, 0
0x14013b2c5  jnz     loc_14013B048
0x14013b2cb  movzx   eax, cs:NtfsStatusDebugFlags
0x14013b2d2  test    al, al
0x14013b2d4  jnz     loc_14013B466
0x14013b2da  test    r14d, r14d
0x14013b2dd  mov     eax, 0
0x14013b2e2  setns   al
0x14013b2e5  mov     dword ptr [rsp+138h+var_118], eax
0x14013b2e9  xor     r9d, r9d
0x14013b2ec  mov     r8d, r14d
0x14013b2ef  xor     edx, edx
0x14013b2f1  mov     rcx, rsi
0x14013b2f4  call    NtfsExtendedCompleteRequestInternal
0x14013b2f9  cmp     [rsp+138h+var_E7], 0
0x14013b2fe  jnz     loc_14013B894
0x14013b304  cmp     [rsp+138h+arg_18], 0
0x14013b30c  jz      short loc_14013B315
0x14013b30e  lock dec dword ptr [rdi+11Ch]
0x14013b315  call    cs:__imp_KeLeaveCriticalRegion
0x14013b31c  nop     dword ptr [rax+rax+00h]
0x14013b321  mov     rcx, [rsp+138h+var_40]
0x14013b329  xor     rcx, rsp; StackCookie
0x14013b32c  call    __security_check_cookie
0x14013b331  add     rsp, 100h
0x14013b338  pop     r15
0x14013b33a  pop     r14
0x14013b33c  pop     r13
0x14013b33e  pop     r12
0x14013b340  pop     rdi
0x14013b341  pop     rsi
0x14013b342  pop     rbx
0x14013b343  retn
0x14013b345  test    r10b, r10b
0x14013b348  jz      short loc_14013B37E
0x14013b34a  movzx   eax, byte ptr [rdi+20E1h]
0x14013b351  test    al, al
0x14013b353  jnz     short loc_14013B37E
0x14013b355  cmp     [rdi+20E2h], r15b
0x14013b35c  jz      loc_14013B0B2
0x14013b362  cmp     [rsp+138h+arg_20], r15b
0x14013b36a  jnz     short loc_14013B37E
0x14013b36c  mov     eax, [rdi+20ECh]
0x14013b372  cmp     eax, cs:NtfsMinDelayCloseCount
0x14013b378  jbe     loc_14013B87B
0x14013b37e  mov     rcx, [rsp+138h+var_B0]
0x14013b386  mov     rcx, [rcx]
0x14013b389  cmp     rcx, [rsp+138h+var_A8]
0x14013b391  jz      loc_14013B0B2
0x14013b397  mov     rax, [rcx+20h]
0x14013b39b  mov     r8, [rax+0B8h]
0x14013b3a2  cmp     [r8+110h], rcx
0x14013b3a9  jnz     short loc_14013B3C2
0x14013b3ab  lea     rax, [rcx+10h]
0x14013b3af  mov     r9, [rax]
0x14013b3b2  cmp     r9, rax
0x14013b3b5  jnz     loc_14013B66B
0x14013b3bb  mov     [r8+110h], r13
0x14013b3c2  mov     r8, [rcx]
0x14013b3c5  cmp     [r8+8], rcx
0x14013b3c9  jnz     loc_14013B51C
0x14013b3cf  mov     rax, [rcx+8]
0x14013b3d3  cmp     [rax], rcx
0x14013b3d6  jnz     loc_14013B51C
0x14013b3dc  mov     [rax], r8
0x14013b3df  mov     [r8+8], rax
0x14013b3e3  lea     rax, [rcx+10h]
0x14013b3e7  mov     r9, [rax]
0x14013b3ea  cmp     [r9+8], rax
0x14013b3ee  jnz     loc_14013B51C
0x14013b3f4  mov     r8, [rcx+18h]
0x14013b3f8  cmp     [r8], rax
0x14013b3fb  jnz     loc_14013B51C
0x14013b401  mov     rbx, rcx
0x14013b404  mov     [r8], r9
0x14013b407  mov     [r9+8], r8
0x14013b40b  mov     rax, [rcx+20h]
0x14013b40f  mov     rcx, [rax+0B8h]
0x14013b416  dec     dword ptr [rcx+10Ch]
0x14013b41c  mov     eax, [rdi+20ECh]
0x14013b422  dec     eax
0x14013b424  mov     [rdi+20ECh], eax
0x14013b42a  mov     r15b, 1
0x14013b42d  jmp     loc_14013B0B2
0x14013b432  and     qword ptr [rsi+10h], 0FFFFFFFFFFFF7FFFh
0x14013b43a  jmp     loc_14013B18D
0x14013b43f  test    r10b, r10b
0x14013b442  jz      loc_14013B0CA
0x14013b448  test    rbx, rbx
0x14013b44b  jnz     loc_14013B0CA
0x14013b451  cmp     [rsp+138h+var_E8], bl
0x14013b455  jz      loc_14013B0CA
0x14013b45b  mov     [rdi+20E0h], bl
0x14013b461  jmp     loc_14013B0CA
0x14013b466  test    r14d, r14d
0x14013b469  jz      loc_14013B2DD
0x14013b46f  cmp     r14d, 126h
0x14013b476  jz      loc_14013B2DA
0x14013b47c  lea     eax, [r14-12Ah]
0x14013b483  cmp     eax, 1
0x14013b486  jbe     loc_14013B2DA
0x14013b48c  cmp     r14d, 0FFFFFFEDh
0x14013b490  jnb     loc_14013B2DA
0x14013b496  cmp     r14d, 0C00000D8h
0x14013b49d  jz      loc_14013B2DA
0x14013b4a3  cmp     r14d, 0C0000016h
0x14013b4aa  jz      loc_14013B2DA
0x14013b4b0  cmp     r14d, 0C0000011h
0x14013b4b7  jz      loc_14013B2DA
0x14013b4bd  lea     eax, [r14+7FFFFFFBh]
0x14013b4c4  cmp     eax, 1
0x14013b4c7  jbe     loc_14013B2DA
0x14013b4cd  cmp     r14d, 103h
0x14013b4d4  jz      loc_14013B2DA
0x14013b4da  mov     r8d, 8041Dh
0x14013b4e0  mov     edx, r14d
0x14013b4e3  mov     rcx, rsi
0x14013b4e6  call    NtfsStatusTraceAndDebugInternal
0x14013b4eb  jmp     loc_14013B2DA
0x14013b4f0  mov     rax, [rcx]
0x14013b4f3  mov     [rsp+138h+var_50], rax
0x14013b4fb  mov     rax, [rcx+8]
0x14013b4ff  mov     [rsp+138h+var_48], rax
0x14013b507  lea     rax, [rsp+138h+var_50]
  ... truncated ...
```
