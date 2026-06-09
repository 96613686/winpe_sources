# VidSchiCheckHeadTimeout(_VIDSCH_GLOBAL *,uint,int *,uint *,unsigned __int64 *,_ULARGE_INTEGER *)

- ea: `0x140016960`
- end: `0x1400170ea`
- name: `?VidSchiCheckHeadTimeout@@YAHPEAU_VIDSCH_GLOBAL@@IPEAHPEAIPEA_KPEAT_ULARGE_INTEGER@@@Z`
- size: `1930`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *, unsigned int, int *, unsigned int *, unsigned __int64 *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x140016840`

## callees

- `0x140016960`
- `0x140017750`
- `0x140017930`
- `0x14001f640`
- `0x140040058`
- `0x140044050`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400169af`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400169af`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140016b15`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140016caf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140016b15`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140016caf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140016d05`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140016d16`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140016d05`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140016d16`
- `ntoskrnl!KeSetEvent` at `0x140016f1e`
- `ntoskrnl!KeSetEvent` at `0x140016f1e`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140016b85`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140016b85`
- `watchdog!WdLogSingleEntry3` at `0x140016fc6`
- `watchdog!WdLogSingleEntry3` at `0x140016fc6`
- `watchdog!WdLogSingleEntry4` at `0x140017038`
- `watchdog!WdLogSingleEntry4` at `0x140017038`
- `dxgkrnl!g_TdrConfig` at `0x140016b97`
- `dxgkrnl!g_TdrConfig` at `0x140016fea`
- `HAL!KeQueryPerformanceCounter` at `0x140016c89`
- `HAL!KeQueryPerformanceCounter` at `0x140016c89`

## pseudocode

```c
__int64 __fastcall VidSchiCheckHeadTimeout(
        KSPIN_LOCK *a1,
        unsigned int a2,
        int *a3,
        unsigned int *a4,
        unsigned __int64 *a5,
        union _ULARGE_INTEGER *a6)
{
  KSPIN_LOCK v7; // r13
  KSPIN_LOCK *v8; // rsi
  unsigned __int64 QuadPart; // r8
  unsigned int v10; // ebx
  int i; // r14d
  KSPIN_LOCK v12; // rax
  LARGE_INTEGER *v13; // r15
  LARGE_INTEGER PerformanceCounter; // r12
  LARGE_INTEGER *v15; // r13
  LONG HighPart; // eax
  int v17; // eax
  KSPIN_LOCK *v18; // rdi
  LARGE_INTEGER v20; // rcx
  unsigned __int64 v21; // r12
  unsigned __int64 v22; // rdx
  bool v23; // zf
  int *v24; // rsi
  DWORD LowPart; // eax
  unsigned int v26; // r9d
  char v27; // cl
  int v28; // eax
  char j; // r10
  unsigned __int64 v30; // rcx
  unsigned int v31; // edx
  char v32; // al
  KSPIN_LOCK *v33; // rcx
  KSPIN_LOCK v34; // rcx
  KSPIN_LOCK *v35; // rax
  KSPIN_LOCK v36; // rcx
  unsigned __int64 *v37; // rcx
  _QWORD *v38; // rcx
  __int64 *v39; // rdx
  __int64 v40; // rax
  struct _KEVENT *v41; // rcx
  KSPIN_LOCK **v42; // rax
  KSPIN_LOCK *v43; // rax
  KSPIN_LOCK **v44; // rdx
  unsigned __int64 v45; // rsi
  unsigned __int64 v46; // rbx
  LARGE_INTEGER v47; // rbx
  __int64 v48; // rax
  LARGE_INTEGER v49; // rdx
  int v50; // eax
  KSPIN_LOCK *v51; // [rsp+40h] [rbp-59h]
  KSPIN_LOCK v52; // [rsp+48h] [rbp-51h]
  KSPIN_LOCK *v53; // [rsp+50h] [rbp-49h] BYREF
  __int64 v54; // [rsp+58h] [rbp-41h] BYREF
  __int64 *v55; // [rsp+60h] [rbp-39h]
  char v56; // [rsp+68h] [rbp-31h]
  int v57; // [rsp+6Ch] [rbp-2Dh]
  char *v58; // [rsp+70h] [rbp-29h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+78h] [rbp-21h] BYREF
  __int16 v60; // [rsp+90h] [rbp-9h]
  unsigned __int64 v61; // [rsp+F0h] [rbp+57h] BYREF
  unsigned int v62; // [rsp+F8h] [rbp+5Fh]
  int *v63; // [rsp+100h] [rbp+67h]
  unsigned int *v64; // [rsp+108h] [rbp+6Fh]

  v64 = a4;
  v63 = a3;
  v62 = a2;
  v60 = 0;
  v8 = &a1[a2 + 441];
  v52 = *v8;
  v7 = v52;
  v51 = v8;
  v58 = (char *)(a1 + 262);
  KeAcquireInStackQueuedSpinLock(a1 + 262, &LockHandle);
  LOBYTE(v60) = 1;
  v53 = a1;
  v55 = &v54;
  v54 = (__int64)&v54;
  v56 = 0;
  v57 = 2;
  if ( *(int *)(v52 + 4) < 4 && !*((_BYTE *)a1 + 164) )
  {
    v56 = 1;
    if ( HIBYTE(v60) )
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    else
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    return 0;
  }
  v10 = 0;
  for ( i = -1; ; ++i )
  {
    if ( i == *((_DWORD *)a1 + 40) )
    {
LABEL_16:
      if ( !v57 || v56 )
        goto LABEL_24;
      if ( v57 != 1 )
        goto LABEL_21;
      v17 = *((_DWORD *)v53 + 78);
      if ( v17 == 1 )
      {
        v18 = (KSPIN_LOCK *)v54;
        if ( (__int64 *)v54 == &v54 )
          goto LABEL_22;
        v38 = v53 + 36;
        if ( *(_QWORD **)(*v38 + 8LL) != v38 )
          goto LABEL_72;
        v39 = (__int64 *)v53[37];
        if ( (_QWORD *)*v39 != v38 )
          goto LABEL_72;
        if ( *(__int64 **)(v54 + 8) != &v54 )
          goto LABEL_72;
        if ( (__int64 *)*v55 != &v54 )
          goto LABEL_72;
        *v39 = (__int64)&v54;
        v38[1] = v55;
        *v55 = (__int64)v38;
        v40 = v54;
        v55 = v39;
        if ( *(__int64 **)(v54 + 8) != &v54 || (__int64 *)*v39 != &v54 )
          goto LABEL_72;
        *v39 = v54;
        *(_QWORD *)(v40 + 8) = v39;
        v55 = &v54;
        v54 = (__int64)&v54;
      }
      else
      {
        if ( v17 != 2 )
          goto LABEL_21;
        v18 = (KSPIN_LOCK *)v54;
        v32 = 0;
        if ( (__int64 *)v54 == &v54 )
          goto LABEL_22;
        while ( 1 )
        {
          v33 = (KSPIN_LOCK *)*v18;
          if ( *((_BYTE *)v18 - 29) )
          {
            if ( (KSPIN_LOCK *)v33[1] != v18 )
              goto LABEL_72;
            v42 = (KSPIN_LOCK **)v18[1];
            if ( *v42 != v18 )
              goto LABEL_72;
            *v42 = v33;
            v33[1] = (KSPIN_LOCK)v42;
            v43 = v53 + 36;
            v44 = (KSPIN_LOCK **)v53[37];
            if ( *v44 != v53 + 36 )
              goto LABEL_72;
            *v18 = (KSPIN_LOCK)v43;
            v18[1] = (KSPIN_LOCK)v44;
            *v44 = v18;
            v43[1] = (KSPIN_LOCK)v18;
            v32 = 1;
          }
          if ( v33 == (KSPIN_LOCK *)&v54 )
            break;
          v18 = v33;
        }
        if ( !v32 )
        {
LABEL_21:
          v18 = (KSPIN_LOCK *)v54;
LABEL_22:
          if ( v18 == (KSPIN_LOCK *)&v54 )
          {
LABEL_23:
            v56 = 1;
LABEL_24:
            if ( (_BYTE)v60 )
            {
              if ( HIBYTE(v60) )
                KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
              else
                KeReleaseInStackQueuedSpinLock(&LockHandle);
            }
            return v10;
          }
          while ( 1 )
          {
            HwQueueStagingList::ProcessHwQueue((HwQueueStagingList *)&v53, (struct VIDSCH_HW_QUEUE *)(v18 - 22), 0);
            v34 = *v18;
            if ( *(KSPIN_LOCK **)(*v18 + 8) != v18 )
              break;
            v35 = (KSPIN_LOCK *)v18[1];
            if ( (KSPIN_LOCK *)*v35 != v18 )
              break;
            *v35 = v34;
            *(_QWORD *)(v34 + 8) = v35;
            *v18 = 0;
            v18[1] = 0;
            v18 = (KSPIN_LOCK *)v54;
            if ( (__int64 *)v54 == &v54 )
              goto LABEL_23;
          }
LABEL_72:
          __fastfail(3u);
        }
      }
      *((_BYTE *)v53 + 304) = 0;
      v41 = (struct _KEVENT *)(v53 + 193);
      v53[197] = MEMORY[0xFFFFF78000000320];
      KeSetEvent(v41, 0, 0);
      goto LABEL_21;
    }
    v12 = *v8;
    if ( i == -1 )
      v13 = *(LARGE_INTEGER **)(v12 + 32);
    else
      v13 = *(LARGE_INTEGER **)(v12 + 8LL * i + 40);
    if ( !v13 )
      goto LABEL_8;
    if ( (v13->LowPart & 1) != 0 )
      break;
    if ( *((_BYTE *)a1 + 67) )
    {
      PerformanceCounter = KeQueryPerformanceCounter(0);
      v13[1] = PerformanceCounter;
    }
    else
    {
      PerformanceCounter.QuadPart = MEMORY[0xFFFFF78000000320];
      v13[1].QuadPart = MEMORY[0xFFFFF78000000320];
    }
    if ( *(_DWORD *)(v7 + 3236) )
    {
      v15 = &v13[175 * (unsigned int)v13[8].HighPart + 15];
      HighPart = v15[131].HighPart;
      if ( HighPart == 15 || HighPart == 5 )
      {
        v20 = v15[166];
        if ( v20.QuadPart <= (unsigned __int64)v15[138].QuadPart )
          v20 = v15[138];
        if ( PerformanceCounter.QuadPart <= (unsigned __int64)v20.QuadPart )
          goto LABEL_8;
        v21 = PerformanceCounter.QuadPart - v20.QuadPart;
        if ( *((_BYTE *)a1 + 67) )
        {
          v36 = a1[373];
          v61 = 0;
          if ( is_mul_ok(v21, 0x989680u) )
          {
            v22 = v21 * (unsigned __int128)0x989680uLL / v36;
          }
          else
          {
            QuadPart = v21 / v36;
            v22 = 10000000 * (v21 / v36) + 10000000 * (v21 % v36) / v36;
          }
        }
        else
        {
          v22 = v21 * KeQueryTimeIncrement();
        }
        if ( v22 > 10000000 * (unsigned __int64)g_TdrConfig[1] )
        {
          v23 = *((_BYTE *)a1 + 67) == 0;
          LOBYTE(v61) = 0;
          if ( v23
            || (*((_BYTE *)a1 + 3364) & 8) != 0
            || (VidSchiObserveHwFlipQueueUpdates(
                  (struct HwQueueStagingList *)&v53,
                  (struct _VIDSCH_GLOBAL *)a1,
                  v62,
                  0,
                  (bool *)&v61),
                !(_BYTE)v61) )
          {
            if ( (*(_DWORD *)(a1[2] + 444) & 0x200) != 0 )
            {
              v45 = __rdtsc();
              v46 = __readmsr(0x400000F6u);
              v61 = 10 * (v45 - v46) / *((unsigned int *)KeGetCurrentPrcb() + 17);
              WdLogSingleEntry3(8, v46, v45, v61);
              WdLogGlobalForLineNumber = 4774;
              if ( v46 > v45 || v61 <= 10000000 * (unsigned __int64)g_TdrConfig[1] )
                goto LABEL_87;
              if ( ++v13[5].HighPart < 2u )
              {
                v47.QuadPart = MEMORY[0xFFFFF78000000320];
                ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WdLogSingleEntry4)(
                  3,
                  (unsigned int)v13[5].HighPart,
                  2,
                  (LARGE_INTEGER)v15[138].QuadPart,
                  MEMORY[0xFFFFF78000000320]);
                WdLogGlobalForLineNumber = 5527;
                v15[138] = v47;
                v13[6].QuadPart = (LONGLONG)v15;
LABEL_87:
                v8 = v51;
                goto LABEL_15;
              }
            }
            v13->LowPart |= 1u;
            v24 = v63;
            v13[2].QuadPart = v21;
            v13[3] = v15[138];
            LowPart = v15[144].LowPart;
            *v24 = i;
            if ( (LowPart & 0x10) != 0 )
              v26 = ((unsigned __int16)*(_DWORD *)v15[149].QuadPart
                   | (unsigned __int16)(*(_DWORD *)v15[149].QuadPart >> 10))
                  & 0x3FF;
            else
              v26 = (1 << *((_DWORD *)a1 + 40)) - 1;
            v8 = v51;
            v27 = -1;
            v23 = !_BitScanForward((unsigned int *)&v28, v26);
            v13[4].QuadPart = 0;
            if ( !v23 )
              v27 = v28;
            v13[5].LowPart = 0;
            for ( j = 0; ; ++j )
            {
              LODWORD(v61) = 0;
              if ( !v26 )
                break;
              QuadPart = v15[149].QuadPart;
              v48 = j * ((8 * *(_DWORD *)(QuadPart + 8) + 231) & 0xFFFFFFF8);
              v49 = *(LARGE_INTEGER *)(v48 + QuadPart + 32);
              if ( v49.QuadPart )
              {
                v13[4] = v49;
                v13[5].LowPart = *(_DWORD *)(v48 + QuadPart + 24);
                break;
              }
              v50 = 1 << v27;
              v27 = -1;
              v26 &= ~v50;
              v23 = !_BitScanForward((unsigned int *)&v50, v26);
              if ( !v23 )
                v27 = v50;
            }
            v23 = (byte_140087204 & 0x20) == 0;
            v30 = v13[4].QuadPart;
            v31 = v13[5].LowPart;
            *a5 = v30;
            *v64 = v31;
            if ( !v23 )
              McTemplateK0pqqx_EtwWriteTransfer(v30, v31, QuadPart, a1[2], v62, v31, v30);
            if ( a6 )
              *a6 = (union _ULARGE_INTEGER)v13[3].QuadPart;
          }
        }
      }
    }
LABEL_15:
    v10 = v13->LowPart & 1;
    if ( v10 )
      goto LABEL_16;
LABEL_8:
    v7 = v52;
  }
  if ( a6 )
    *a6 = (union _ULARGE_INTEGER)v13[3].QuadPart;
  v37 = a5;
  *v63 = i;
  *v37 = v13[4].QuadPart;
  *v64 = v13[5].LowPart;
  HwQueueStagingList::~HwQueueStagingList((HwQueueStagingList *)&v53);
  AcquireSpinLock::Release((AcquireSpinLock *)&v58);
  return 1;
}

```

## disassembly

```asm
0x140016960  mov     [rsp-8+arg_18], r9
0x140016965  mov     [rsp-8+arg_10], r8
0x14001696a  mov     [rsp-8+arg_8], edx
0x14001696e  push    rbp
0x14001696f  push    rsi
0x140016970  push    rdi
0x140016971  push    r13
0x140016973  lea     rbp, [rsp-2Fh]
0x140016978  sub     rsp, 0C8h
0x14001697f  mov     eax, edx
0x140016981  mov     rdi, rcx
0x140016984  add     rax, 1B9h
0x14001698a  mov     [rbp+47h+var_50], 0
0x140016990  mov     r13, [rcx+rax*8]
0x140016994  lea     rsi, [rcx+rax*8]
0x140016998  add     rcx, 830h; SpinLock
0x14001699f  mov     [rbp+47h+var_98], r13
0x1400169a3  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x1400169a7  mov     [rbp+47h+var_A0], rsi
0x1400169ab  mov     [rbp+47h+var_70], rcx
0x1400169af  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400169b6  nop     dword ptr [rax+rax+00h]
0x1400169bb  lea     rax, [rbp+47h+var_88]
0x1400169bf  mov     byte ptr [rbp+47h+var_50], 1
0x1400169c3  xorps   xmm0, xmm0
0x1400169c6  mov     [rbp+47h+var_90], rdi
0x1400169ca  movups  [rbp+47h+var_88], xmm0
0x1400169ce  mov     qword ptr [rbp+47h+var_88+8], rax
0x1400169d2  lea     rax, [rbp+47h+var_88]
0x1400169d6  mov     qword ptr [rbp+47h+var_88], rax
0x1400169da  mov     [rbp+47h+var_78], 0
0x1400169de  mov     [rbp+47h+var_74], 2
0x1400169e5  cmp     dword ptr [r13+4], 4
0x1400169ea  jge     short loc_1400169F9
0x1400169ec  cmp     byte ptr [rdi+0A4h], 0
0x1400169f3  jz      loc_140016CA1
0x1400169f9  mov     [rsp+0E0h+var_20], rbx
0x140016a01  xor     ebx, ebx
0x140016a03  mov     [rsp+0E0h+var_30], r14
0x140016a0b  mov     r14d, 0FFFFFFFFh
0x140016a11  mov     [rsp+0E0h+var_28], r12
0x140016a19  mov     [rsp+0E0h+var_38], r15
0x140016a21  mov     r9, 0FFFFF78000000320h
0x140016a2b  cmp     r14d, [rdi+0A0h]
0x140016a32  jz      loc_140016ABE
0x140016a38  mov     rax, [rsi]
0x140016a3b  cmp     r14d, 0FFFFFFFFh
0x140016a3f  jz      loc_140016B51
0x140016a45  movsxd  rcx, r14d
0x140016a48  mov     r15, [rax+rcx*8+28h]
0x140016a4d  test    r15, r15
0x140016a50  jnz     short loc_140016A5B
0x140016a52  mov     r13, [rbp+47h+var_98]
0x140016a56  inc     r14d
0x140016a59  jmp     short loc_140016A21
0x140016a5b  mov     eax, [r15]
0x140016a5e  test    al, 1
0x140016a60  jnz     loc_140016E27
0x140016a66  cmp     byte ptr [rdi+43h], 0
0x140016a6a  jnz     loc_140016C87
0x140016a70  mov     r12, [r9]
0x140016a73  mov     [r15+8], r12
0x140016a77  cmp     dword ptr [r13+0CA4h], 0
0x140016a7f  jz      short loc_140016AAC
0x140016a81  mov     eax, [r15+44h]
0x140016a85  imul    r13, rax, 578h
0x140016a8c  add     r13, 78h ; 'x'
0x140016a90  add     r13, r15
0x140016a93  mov     eax, [r13+41Ch]
0x140016a9a  cmp     eax, 0Fh
0x140016a9d  jz      loc_140016B5A
0x140016aa3  cmp     eax, 5
0x140016aa6  jz      loc_140016B5A
0x140016aac  mov     ebx, [r15]
0x140016aaf  and     ebx, 1
0x140016ab2  jz      short loc_140016A52
0x140016ab4  mov     r9, 0FFFFF78000000320h
0x140016abe  mov     eax, [rbp+47h+var_74]
0x140016ac1  test    eax, eax
0x140016ac3  jz      short loc_140016B01
0x140016ac5  cmp     [rbp+47h+var_78], 0
0x140016ac9  jnz     short loc_140016B01
0x140016acb  cmp     eax, 1
0x140016ace  jnz     short loc_140016AEC
0x140016ad0  mov     rcx, [rbp+47h+var_90]
0x140016ad4  mov     eax, [rcx+138h]
0x140016ada  cmp     eax, 1
0x140016add  jz      loc_140016E73
0x140016ae3  cmp     eax, 2
0x140016ae6  jz      loc_140016CCB
0x140016aec  mov     rdi, qword ptr [rbp+47h+var_88]
0x140016af0  lea     rax, [rbp+47h+var_88]
0x140016af4  cmp     rdi, rax
0x140016af7  jnz     loc_140016D32
0x140016afd  mov     [rbp+47h+var_78], 1
0x140016b01  cmp     byte ptr [rbp+47h+var_50], 0
0x140016b05  jz      short loc_140016B21
0x140016b07  cmp     byte ptr [rbp+47h+var_50+1], 0
0x140016b0b  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x140016b0f  jnz     loc_140016D05
0x140016b15  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140016b1c  nop     dword ptr [rax+rax+00h]
0x140016b21  mov     eax, ebx
0x140016b23  mov     r12, [rsp+0E0h+var_28]
0x140016b2b  mov     r15, [rsp+0E0h+var_38]
0x140016b33  mov     rbx, [rsp+0E0h+var_20]
0x140016b3b  mov     r14, [rsp+0E0h+var_30]
0x140016b43  add     rsp, 0C8h
0x140016b4a  pop     r13
0x140016b4c  pop     rdi
0x140016b4d  pop     rsi
0x140016b4e  pop     rbp
0x140016b4f  retn
0x140016b51  mov     r15, [rax+20h]
0x140016b55  jmp     loc_140016A4D
0x140016b5a  mov     rax, [r13+450h]
0x140016b61  mov     rcx, [r13+530h]
0x140016b68  cmp     rcx, rax
0x140016b6b  cmovbe  rcx, rax
0x140016b6f  cmp     r12, rcx
0x140016b72  jbe     loc_140016A52
0x140016b78  sub     r12, rcx
0x140016b7b  cmp     byte ptr [rdi+43h], 0
0x140016b7f  jnz     loc_140016D9F
0x140016b85  call    cs:__imp_KeQueryTimeIncrement
0x140016b8c  nop     dword ptr [rax+rax+00h]
0x140016b91  mov     edx, eax
0x140016b93  imul    rdx, r12
0x140016b97  mov     rax, cs:?g_TdrConfig@@3U_TDR_CONFIG@@C; _TDR_CONFIG volatile g_TdrConfig
0x140016b9e  mov     ecx, [rax+4]
0x140016ba1  imul    rcx, 989680h
0x140016ba8  cmp     rdx, rcx
0x140016bab  jbe     loc_140016AAC
0x140016bb1  cmp     byte ptr [rdi+43h], 0
0x140016bb5  mov     byte ptr [rbp+47h+arg_0], 0
0x140016bb9  jnz     loc_140016DEF
0x140016bbf  mov     rax, [rdi+10h]
0x140016bc3  test    dword ptr [rax+1BCh], 200h
0x140016bcd  jnz     loc_140016F79
0x140016bd3  or      dword ptr [r15], 1
0x140016bd7  mov     rsi, [rbp+47h+arg_10]
0x140016bdb  mov     [r15+10h], r12
0x140016bdf  mov     rax, [r13+450h]
0x140016be6  mov     [r15+18h], rax
0x140016bea  mov     eax, [r13+480h]
0x140016bf1  mov     [rsi], r14d
0x140016bf4  test    al, 10h
0x140016bf6  jz      loc_140016D88
0x140016bfc  mov     rax, [r13+4A8h]
0x140016c03  mov     ecx, [rax]
0x140016c05  mov     r9d, ecx
0x140016c08  shr     r9d, 0Ah
0x140016c0c  or      r9d, ecx
0x140016c0f  and     r9d, 3FFh
0x140016c16  mov     rsi, [rbp+47h+var_A0]
0x140016c1a  mov     ecx, 0FFFFFFFFh
0x140016c1f  bsf     eax, r9d
0x140016c23  mov     qword ptr [r15+20h], 0
0x140016c2b  movzx   eax, al
0x140016c2e  cmovnz  ecx, eax
0x140016c31  mov     dword ptr [r15+28h], 0
0x140016c39  xor     r10b, r10b
0x140016c3c  mov     dword ptr [rbp+47h+arg_0], 0
0x140016c43  test    r9d, r9d
0x140016c46  jnz     loc_14001705B
0x140016c4c  test    cs:byte_140087204, 20h
0x140016c53  mov     rax, [rbp+47h+arg_20]
0x140016c57  mov     rcx, [r15+20h]
0x140016c5b  mov     edx, [r15+28h]
0x140016c5f  mov     [rax], rcx
0x140016c62  mov     rax, [rbp+47h+arg_18]
0x140016c66  mov     [rax], edx
0x140016c68  jnz     loc_1400170B8
0x140016c6e  mov     rcx, [rbp+47h+arg_28]
0x140016c72  test    rcx, rcx
0x140016c75  jz      loc_140016AAC
0x140016c7b  mov     rax, [r15+18h]
0x140016c7f  mov     [rcx], rax
0x140016c82  jmp     loc_140016AAC
0x140016c87  xor     ecx, ecx; PerformanceFrequency
0x140016c89  call    cs:__imp_KeQueryPerformanceCounter
0x140016c90  nop     dword ptr [rax+rax+00h]
0x140016c95  mov     r12, rax
0x140016c98  mov     [r15+8], rax
0x140016c9c  jmp     loc_140016A77
0x140016ca1  cmp     byte ptr [rbp+47h+var_50+1], 0
0x140016ca5  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x140016ca9  mov     [rbp+47h+var_78], 1
0x140016cad  jnz     short loc_140016D16
0x140016caf  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140016cb6  nop     dword ptr [rax+rax+00h]
0x140016cbb  xor     eax, eax
0x140016cbd  add     rsp, 0C8h
0x140016cc4  pop     r13
0x140016cc6  pop     rdi
0x140016cc7  pop     rsi
0x140016cc8  pop     rbp
0x140016cc9  retn
0x140016ccb  mov     rdi, qword ptr [rbp+47h+var_88]
0x140016ccf  lea     rcx, [rbp+47h+var_88]
0x140016cd3  xor     al, al
0x140016cd5  cmp     rdi, rcx
0x140016cd8  jz      loc_140016AF0
0x140016cde  cmp     byte ptr [rdi-1Dh], 0
0x140016ce2  mov     rcx, [rdi]
0x140016ce5  jnz     loc_140016F2F
0x140016ceb  lea     rdx, [rbp+47h+var_88]
0x140016cef  cmp     rcx, rdx
0x140016cf2  jnz     loc_1400170E2
0x140016cf8  test    al, al
0x140016cfa  jz      loc_140016AEC
0x140016d00  jmp     loc_140016EFC
0x140016d05  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140016d0c  nop     dword ptr [rax+rax+00h]
0x140016d11  jmp     loc_140016B21
0x140016d16  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140016d1d  nop     dword ptr [rax+rax+00h]
0x140016d22  xor     eax, eax
0x140016d24  add     rsp, 0C8h
0x140016d2b  pop     r13
0x140016d2d  pop     rdi
0x140016d2e  pop     rsi
0x140016d2f  pop     rbp
0x140016d30  retn
0x140016d32  lea     rdx, [rdi-0B0h]; struct VIDSCH_HW_QUEUE *
0x140016d39  xor     r8d, r8d; struct _KLOCK_QUEUE_HANDLE *
0x140016d3c  lea     rcx, [rbp+47h+var_90]; this
0x140016d40  call    ?ProcessHwQueue@HwQueueStagingList@@AEAAXPEAUVIDSCH_HW_QUEUE@@PEAU_KLOCK_QUEUE_HANDLE@@@Z; HwQueueStagingList::ProcessHwQueue(VIDSCH_HW_QUEUE *,_KLOCK_QUEUE_HANDLE *)
0x140016d45  mov     rcx, [rdi]
0x140016d48  cmp     [rcx+8], rdi
0x140016d4c  jnz     loc_140016E6C
0x140016d52  mov     rax, [rdi+8]
0x140016d56  cmp     [rax], rdi
0x140016d59  jnz     loc_140016E6C
0x140016d5f  mov     [rax], rcx
0x140016d62  mov     [rcx+8], rax
0x140016d66  lea     rax, [rbp+47h+var_88]
0x140016d6a  mov     qword ptr [rdi], 0
0x140016d71  mov     qword ptr [rdi+8], 0
0x140016d79  mov     rdi, qword ptr [rbp+47h+var_88]
0x140016d7d  cmp     rdi, rax
0x140016d80  jz      loc_140016AFD
0x140016d86  jmp     short loc_140016D32
0x140016d88  mov     ecx, [rdi+0A0h]
0x140016d8e  mov     r9d, 1
0x140016d94  shl     r9d, cl
0x140016d97  dec     r9d
0x140016d9a  jmp     loc_140016C16
0x140016d9f  mov     rcx, [rdi+0BA8h]
0x140016da6  mov     eax, 989680h
0x140016dab  mul     r12
0x140016dae  mov     [rbp+47h+arg_0], 0
0x140016db6  test    rdx, rdx
0x140016db9  jnz     short loc_140016DC6
0x140016dbb  div     rcx
0x140016dbe  mov     rdx, rax
0x140016dc1  jmp     loc_140016B97
0x140016dc6  xor     edx, edx
0x140016dc8  mov     rax, r12
0x140016dcb  div     rcx
0x140016dce  mov     r8, rax
0x140016dd1  imul    rax, rdx, 989680h
0x140016dd8  xor     edx, edx
0x140016dda  div     rcx
0x140016ddd  mov     rdx, rax
0x140016de0  imul    rax, r8, 989680h
0x140016de7  add     rdx, rax
0x140016dea  jmp     loc_140016B97
0x140016def  test    byte ptr [rdi+0D24h], 8
0x140016df6  jnz     loc_140016BBF
0x140016dfc  mov     r8d, [rbp+47h+arg_8]; unsigned int
0x140016e00  lea     rax, [rbp+47h+arg_0]
0x140016e04  xor     r9d, r9d; struct _KEVENT **
0x140016e07  mov     [rsp+0E0h+var_C0], rax; bool *
0x140016e0c  mov     rdx, rdi; struct _VIDSCH_GLOBAL *
0x140016e0f  lea     rcx, [rbp+47h+var_90]; struct HwQueueStagingList *
0x140016e13  call    ?VidSchiObserveHwFlipQueueUpdates@@YAXPEAVHwQueueStagingList@@PEAU_VIDSCH_GLOBAL@@IPEAPEAU_KEVENT@@PEA_N@Z; VidSchiObserveHwFlipQueueUpdates(HwQueueStagingList *,_VIDSCH_GLOBAL *,uint,_KEVENT * *,bool *)
0x140016e18  cmp     byte ptr [rbp+47h+arg_0], 0
0x140016e1c  jz      loc_140016BBF
0x140016e22  jmp     loc_140016AAC
0x140016e27  mov     rcx, [rbp+47h+arg_28]
0x140016e2b  test    rcx, rcx
0x140016e2e  jnz     loc_1400170D6
0x140016e34  mov     rax, [rbp+47h+arg_10]
0x140016e38  mov     rcx, [rbp+47h+arg_20]
0x140016e3c  mov     [rax], r14d
0x140016e3f  mov     rax, [r15+20h]
0x140016e43  mov     [rcx], rax
0x140016e46  mov     rcx, [rbp+47h+arg_18]
0x140016e4a  mov     eax, [r15+28h]
0x140016e4e  mov     [rcx], eax
0x140016e50  lea     rcx, [rbp+47h+var_90]; this
0x140016e54  call    ??1HwQueueStagingList@@QEAA@XZ; HwQueueStagingList::~HwQueueStagingList(void)
0x140016e59  lea     rcx, [rbp+47h+var_70]; this
0x140016e5d  call    ?Release@AcquireSpinLock@@QEAAXXZ; AcquireSpinLock::Release(void)
0x140016e62  mov     eax, 1
0x140016e67  jmp     loc_140016B23
0x140016e6c  mov     ecx, 3
0x140016e71  int     29h; Win8: RtlFailFast(ecx)
0x140016e73  mov     rdi, qword ptr [rbp+47h+var_88]
  ... truncated ...
```
