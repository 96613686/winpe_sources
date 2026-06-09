# VidSchiCheckHeadTimeout(_VIDSCH_GLOBAL *,uint,int *,uint *,unsigned __int64 *,_ULARGE_INTEGER *)

- ea: `0x1400210c0`
- end: `0x14002184a`
- name: `?VidSchiCheckHeadTimeout@@YAHPEAU_VIDSCH_GLOBAL@@IPEAHPEAIPEA_KPEAT_ULARGE_INTEGER@@@Z`
- size: `1930`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *, unsigned int, int *, unsigned int *, unsigned __int64 *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x140020fa0`

## callees

- `0x14001ca80`
- `0x14001cc60`
- `0x1400210c0`
- `0x140021850`
- `0x140021c90`
- `0x140043e4c`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002110f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002110f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021275`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002140f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021275`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002140f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140021465`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140021476`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140021465`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140021476`
- `ntoskrnl!KeSetEvent` at `0x14002167e`
- `ntoskrnl!KeSetEvent` at `0x14002167e`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400212e5`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400212e5`
- `watchdog!WdLogSingleEntry3` at `0x140021726`
- `watchdog!WdLogSingleEntry3` at `0x140021726`
- `watchdog!WdLogSingleEntry4` at `0x140021798`
- `watchdog!WdLogSingleEntry4` at `0x140021798`
- `dxgkrnl!g_TdrConfig` at `0x1400212f7`
- `dxgkrnl!g_TdrConfig` at `0x14002174a`
- `HAL!KeQueryPerformanceCounter` at `0x1400213e9`
- `HAL!KeQueryPerformanceCounter` at `0x1400213e9`

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
            v23 = (byte_140086204 & 0x20) == 0;
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
0x1400210c0  mov     [rsp-8+arg_18], r9
0x1400210c5  mov     [rsp-8+arg_10], r8
0x1400210ca  mov     [rsp-8+arg_8], edx
0x1400210ce  push    rbp
0x1400210cf  push    rsi
0x1400210d0  push    rdi
0x1400210d1  push    r13
0x1400210d3  lea     rbp, [rsp-2Fh]
0x1400210d8  sub     rsp, 0C8h
0x1400210df  mov     eax, edx
0x1400210e1  mov     rdi, rcx
0x1400210e4  add     rax, 1B9h
0x1400210ea  mov     [rbp+47h+var_50], 0
0x1400210f0  mov     r13, [rcx+rax*8]
0x1400210f4  lea     rsi, [rcx+rax*8]
0x1400210f8  add     rcx, 830h; SpinLock
0x1400210ff  mov     [rbp+47h+var_98], r13
0x140021103  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x140021107  mov     [rbp+47h+var_A0], rsi
0x14002110b  mov     [rbp+47h+var_70], rcx
0x14002110f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140021116  nop     dword ptr [rax+rax+00h]
0x14002111b  lea     rax, [rbp+47h+var_88]
0x14002111f  mov     byte ptr [rbp+47h+var_50], 1
0x140021123  xorps   xmm0, xmm0
0x140021126  mov     [rbp+47h+var_90], rdi
0x14002112a  movups  [rbp+47h+var_88], xmm0
0x14002112e  mov     qword ptr [rbp+47h+var_88+8], rax
0x140021132  lea     rax, [rbp+47h+var_88]
0x140021136  mov     qword ptr [rbp+47h+var_88], rax
0x14002113a  mov     [rbp+47h+var_78], 0
0x14002113e  mov     [rbp+47h+var_74], 2
0x140021145  cmp     dword ptr [r13+4], 4
0x14002114a  jge     short loc_140021159
0x14002114c  cmp     byte ptr [rdi+0A4h], 0
0x140021153  jz      loc_140021401
0x140021159  mov     [rsp+0E0h+var_20], rbx
0x140021161  xor     ebx, ebx
0x140021163  mov     [rsp+0E0h+var_30], r14
0x14002116b  mov     r14d, 0FFFFFFFFh
0x140021171  mov     [rsp+0E0h+var_28], r12
0x140021179  mov     [rsp+0E0h+var_38], r15
0x140021181  mov     r9, 0FFFFF78000000320h
0x14002118b  cmp     r14d, [rdi+0A0h]
0x140021192  jz      loc_14002121E
0x140021198  mov     rax, [rsi]
0x14002119b  cmp     r14d, 0FFFFFFFFh
0x14002119f  jz      loc_1400212B1
0x1400211a5  movsxd  rcx, r14d
0x1400211a8  mov     r15, [rax+rcx*8+28h]
0x1400211ad  test    r15, r15
0x1400211b0  jnz     short loc_1400211BB
0x1400211b2  mov     r13, [rbp+47h+var_98]
0x1400211b6  inc     r14d
0x1400211b9  jmp     short loc_140021181
0x1400211bb  mov     eax, [r15]
0x1400211be  test    al, 1
0x1400211c0  jnz     loc_140021587
0x1400211c6  cmp     byte ptr [rdi+43h], 0
0x1400211ca  jnz     loc_1400213E7
0x1400211d0  mov     r12, [r9]
0x1400211d3  mov     [r15+8], r12
0x1400211d7  cmp     dword ptr [r13+0CA4h], 0
0x1400211df  jz      short loc_14002120C
0x1400211e1  mov     eax, [r15+44h]
0x1400211e5  imul    r13, rax, 578h
0x1400211ec  add     r13, 78h ; 'x'
0x1400211f0  add     r13, r15
0x1400211f3  mov     eax, [r13+41Ch]
0x1400211fa  cmp     eax, 0Fh
0x1400211fd  jz      loc_1400212BA
0x140021203  cmp     eax, 5
0x140021206  jz      loc_1400212BA
0x14002120c  mov     ebx, [r15]
0x14002120f  and     ebx, 1
0x140021212  jz      short loc_1400211B2
0x140021214  mov     r9, 0FFFFF78000000320h
0x14002121e  mov     eax, [rbp+47h+var_74]
0x140021221  test    eax, eax
0x140021223  jz      short loc_140021261
0x140021225  cmp     [rbp+47h+var_78], 0
0x140021229  jnz     short loc_140021261
0x14002122b  cmp     eax, 1
0x14002122e  jnz     short loc_14002124C
0x140021230  mov     rcx, [rbp+47h+var_90]
0x140021234  mov     eax, [rcx+138h]
0x14002123a  cmp     eax, 1
0x14002123d  jz      loc_1400215D3
0x140021243  cmp     eax, 2
0x140021246  jz      loc_14002142B
0x14002124c  mov     rdi, qword ptr [rbp+47h+var_88]
0x140021250  lea     rax, [rbp+47h+var_88]
0x140021254  cmp     rdi, rax
0x140021257  jnz     loc_140021492
0x14002125d  mov     [rbp+47h+var_78], 1
0x140021261  cmp     byte ptr [rbp+47h+var_50], 0
0x140021265  jz      short loc_140021281
0x140021267  cmp     byte ptr [rbp+47h+var_50+1], 0
0x14002126b  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x14002126f  jnz     loc_140021465
0x140021275  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002127c  nop     dword ptr [rax+rax+00h]
0x140021281  mov     eax, ebx
0x140021283  mov     r12, [rsp+0E0h+var_28]
0x14002128b  mov     r15, [rsp+0E0h+var_38]
0x140021293  mov     rbx, [rsp+0E0h+var_20]
0x14002129b  mov     r14, [rsp+0E0h+var_30]
0x1400212a3  add     rsp, 0C8h
0x1400212aa  pop     r13
0x1400212ac  pop     rdi
0x1400212ad  pop     rsi
0x1400212ae  pop     rbp
0x1400212af  retn
0x1400212b1  mov     r15, [rax+20h]
0x1400212b5  jmp     loc_1400211AD
0x1400212ba  mov     rax, [r13+450h]
0x1400212c1  mov     rcx, [r13+530h]
0x1400212c8  cmp     rcx, rax
0x1400212cb  cmovbe  rcx, rax
0x1400212cf  cmp     r12, rcx
0x1400212d2  jbe     loc_1400211B2
0x1400212d8  sub     r12, rcx
0x1400212db  cmp     byte ptr [rdi+43h], 0
0x1400212df  jnz     loc_1400214FF
0x1400212e5  call    cs:__imp_KeQueryTimeIncrement
0x1400212ec  nop     dword ptr [rax+rax+00h]
0x1400212f1  mov     edx, eax
0x1400212f3  imul    rdx, r12
0x1400212f7  mov     rax, cs:?g_TdrConfig@@3U_TDR_CONFIG@@C; _TDR_CONFIG volatile g_TdrConfig
0x1400212fe  mov     ecx, [rax+4]
0x140021301  imul    rcx, 989680h
0x140021308  cmp     rdx, rcx
0x14002130b  jbe     loc_14002120C
0x140021311  cmp     byte ptr [rdi+43h], 0
0x140021315  mov     byte ptr [rbp+47h+arg_0], 0
0x140021319  jnz     loc_14002154F
0x14002131f  mov     rax, [rdi+10h]
0x140021323  test    dword ptr [rax+1BCh], 200h
0x14002132d  jnz     loc_1400216D9
0x140021333  or      dword ptr [r15], 1
0x140021337  mov     rsi, [rbp+47h+arg_10]
0x14002133b  mov     [r15+10h], r12
0x14002133f  mov     rax, [r13+450h]
0x140021346  mov     [r15+18h], rax
0x14002134a  mov     eax, [r13+480h]
0x140021351  mov     [rsi], r14d
0x140021354  test    al, 10h
0x140021356  jz      loc_1400214E8
0x14002135c  mov     rax, [r13+4A8h]
0x140021363  mov     ecx, [rax]
0x140021365  mov     r9d, ecx
0x140021368  shr     r9d, 0Ah
0x14002136c  or      r9d, ecx
0x14002136f  and     r9d, 3FFh
0x140021376  mov     rsi, [rbp+47h+var_A0]
0x14002137a  mov     ecx, 0FFFFFFFFh
0x14002137f  bsf     eax, r9d
0x140021383  mov     qword ptr [r15+20h], 0
0x14002138b  movzx   eax, al
0x14002138e  cmovnz  ecx, eax
0x140021391  mov     dword ptr [r15+28h], 0
0x140021399  xor     r10b, r10b
0x14002139c  mov     dword ptr [rbp+47h+arg_0], 0
0x1400213a3  test    r9d, r9d
0x1400213a6  jnz     loc_1400217BB
0x1400213ac  test    cs:byte_140086204, 20h
0x1400213b3  mov     rax, [rbp+47h+arg_20]
0x1400213b7  mov     rcx, [r15+20h]
0x1400213bb  mov     edx, [r15+28h]
0x1400213bf  mov     [rax], rcx
0x1400213c2  mov     rax, [rbp+47h+arg_18]
0x1400213c6  mov     [rax], edx
0x1400213c8  jnz     loc_140021818
0x1400213ce  mov     rcx, [rbp+47h+arg_28]
0x1400213d2  test    rcx, rcx
0x1400213d5  jz      loc_14002120C
0x1400213db  mov     rax, [r15+18h]
0x1400213df  mov     [rcx], rax
0x1400213e2  jmp     loc_14002120C
0x1400213e7  xor     ecx, ecx; PerformanceFrequency
0x1400213e9  call    cs:__imp_KeQueryPerformanceCounter
0x1400213f0  nop     dword ptr [rax+rax+00h]
0x1400213f5  mov     r12, rax
0x1400213f8  mov     [r15+8], rax
0x1400213fc  jmp     loc_1400211D7
0x140021401  cmp     byte ptr [rbp+47h+var_50+1], 0
0x140021405  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x140021409  mov     [rbp+47h+var_78], 1
0x14002140d  jnz     short loc_140021476
0x14002140f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140021416  nop     dword ptr [rax+rax+00h]
0x14002141b  xor     eax, eax
0x14002141d  add     rsp, 0C8h
0x140021424  pop     r13
0x140021426  pop     rdi
0x140021427  pop     rsi
0x140021428  pop     rbp
0x140021429  retn
0x14002142b  mov     rdi, qword ptr [rbp+47h+var_88]
0x14002142f  lea     rcx, [rbp+47h+var_88]
0x140021433  xor     al, al
0x140021435  cmp     rdi, rcx
0x140021438  jz      loc_140021250
0x14002143e  cmp     byte ptr [rdi-1Dh], 0
0x140021442  mov     rcx, [rdi]
0x140021445  jnz     loc_14002168F
0x14002144b  lea     rdx, [rbp+47h+var_88]
0x14002144f  cmp     rcx, rdx
0x140021452  jnz     loc_140021842
0x140021458  test    al, al
0x14002145a  jz      loc_14002124C
0x140021460  jmp     loc_14002165C
0x140021465  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14002146c  nop     dword ptr [rax+rax+00h]
0x140021471  jmp     loc_140021281
0x140021476  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14002147d  nop     dword ptr [rax+rax+00h]
0x140021482  xor     eax, eax
0x140021484  add     rsp, 0C8h
0x14002148b  pop     r13
0x14002148d  pop     rdi
0x14002148e  pop     rsi
0x14002148f  pop     rbp
0x140021490  retn
0x140021492  lea     rdx, [rdi-0B0h]; struct VIDSCH_HW_QUEUE *
0x140021499  xor     r8d, r8d; struct _KLOCK_QUEUE_HANDLE *
0x14002149c  lea     rcx, [rbp+47h+var_90]; this
0x1400214a0  call    ?ProcessHwQueue@HwQueueStagingList@@AEAAXPEAUVIDSCH_HW_QUEUE@@PEAU_KLOCK_QUEUE_HANDLE@@@Z; HwQueueStagingList::ProcessHwQueue(VIDSCH_HW_QUEUE *,_KLOCK_QUEUE_HANDLE *)
0x1400214a5  mov     rcx, [rdi]
0x1400214a8  cmp     [rcx+8], rdi
0x1400214ac  jnz     loc_1400215CC
0x1400214b2  mov     rax, [rdi+8]
0x1400214b6  cmp     [rax], rdi
0x1400214b9  jnz     loc_1400215CC
0x1400214bf  mov     [rax], rcx
0x1400214c2  mov     [rcx+8], rax
0x1400214c6  lea     rax, [rbp+47h+var_88]
0x1400214ca  mov     qword ptr [rdi], 0
0x1400214d1  mov     qword ptr [rdi+8], 0
0x1400214d9  mov     rdi, qword ptr [rbp+47h+var_88]
0x1400214dd  cmp     rdi, rax
0x1400214e0  jz      loc_14002125D
0x1400214e6  jmp     short loc_140021492
0x1400214e8  mov     ecx, [rdi+0A0h]
0x1400214ee  mov     r9d, 1
0x1400214f4  shl     r9d, cl
0x1400214f7  dec     r9d
0x1400214fa  jmp     loc_140021376
0x1400214ff  mov     rcx, [rdi+0BA8h]
0x140021506  mov     eax, 989680h
0x14002150b  mul     r12
0x14002150e  mov     [rbp+47h+arg_0], 0
0x140021516  test    rdx, rdx
0x140021519  jnz     short loc_140021526
0x14002151b  div     rcx
0x14002151e  mov     rdx, rax
0x140021521  jmp     loc_1400212F7
0x140021526  xor     edx, edx
0x140021528  mov     rax, r12
0x14002152b  div     rcx
0x14002152e  mov     r8, rax
0x140021531  imul    rax, rdx, 989680h
0x140021538  xor     edx, edx
0x14002153a  div     rcx
0x14002153d  mov     rdx, rax
0x140021540  imul    rax, r8, 989680h
0x140021547  add     rdx, rax
0x14002154a  jmp     loc_1400212F7
0x14002154f  test    byte ptr [rdi+0D24h], 8
0x140021556  jnz     loc_14002131F
0x14002155c  mov     r8d, [rbp+47h+arg_8]; unsigned int
0x140021560  lea     rax, [rbp+47h+arg_0]
0x140021564  xor     r9d, r9d; struct _KEVENT **
0x140021567  mov     [rsp+0E0h+var_C0], rax; bool *
0x14002156c  mov     rdx, rdi; struct _VIDSCH_GLOBAL *
0x14002156f  lea     rcx, [rbp+47h+var_90]; struct HwQueueStagingList *
0x140021573  call    ?VidSchiObserveHwFlipQueueUpdates@@YAXPEAVHwQueueStagingList@@PEAU_VIDSCH_GLOBAL@@IPEAPEAU_KEVENT@@PEA_N@Z; VidSchiObserveHwFlipQueueUpdates(HwQueueStagingList *,_VIDSCH_GLOBAL *,uint,_KEVENT * *,bool *)
0x140021578  cmp     byte ptr [rbp+47h+arg_0], 0
0x14002157c  jz      loc_14002131F
0x140021582  jmp     loc_14002120C
0x140021587  mov     rcx, [rbp+47h+arg_28]
0x14002158b  test    rcx, rcx
0x14002158e  jnz     loc_140021836
0x140021594  mov     rax, [rbp+47h+arg_10]
0x140021598  mov     rcx, [rbp+47h+arg_20]
0x14002159c  mov     [rax], r14d
0x14002159f  mov     rax, [r15+20h]
0x1400215a3  mov     [rcx], rax
0x1400215a6  mov     rcx, [rbp+47h+arg_18]
0x1400215aa  mov     eax, [r15+28h]
0x1400215ae  mov     [rcx], eax
0x1400215b0  lea     rcx, [rbp+47h+var_90]; this
0x1400215b4  call    ??1HwQueueStagingList@@QEAA@XZ; HwQueueStagingList::~HwQueueStagingList(void)
0x1400215b9  lea     rcx, [rbp+47h+var_70]; this
0x1400215bd  call    ?Release@AcquireSpinLock@@QEAAXXZ; AcquireSpinLock::Release(void)
0x1400215c2  mov     eax, 1
0x1400215c7  jmp     loc_140021283
0x1400215cc  mov     ecx, 3
0x1400215d1  int     29h; Win8: RtlFailFast(ecx)
0x1400215d3  mov     rdi, qword ptr [rbp+47h+var_88]
  ... truncated ...
```
