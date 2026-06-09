# NtfsAcquireRange

- ea: `0x1400100b0`
- end: `0x1400105cc`
- name: `NtfsAcquireRange`
- size: `1308`
- prototype: ``
- caller_count: `8`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x14000f02c`
- `0x14001d13c`
- `0x1400cc78c`
- `0x1401771e0`
- `0x14021ebd0`
- `0x1402336bc`
- `0x140234fd0`
- `0x1402447d0`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x1400100b0`
- `0x1400105d4`
- `0x140010670`
- `0x14001072c`
- `0x140010788`
- `0x140010858`
- `0x140036d14`
- `0x140038e9c`
- `0x140059250`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400101d5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140010318`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400101d5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140010318`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400101b7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001029e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400102fe`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001036d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400104a1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001054e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400101b7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001029e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400102fe`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001036d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400104a1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001054e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400101f2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400102d5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010348`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001052c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005db3e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400101f2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400102d5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010348`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001052c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005db3e`

## pseudocode

```c
char __fastcall NtfsAcquireRange(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5, __int64 a6)
{
  __int64 v6; // r11
  unsigned int v8; // edx
  int v9; // r10d
  int v10; // eax
  int v11; // edx
  int v12; // r12d
  __int64 v13; // rsi
  __int64 v14; // rdi
  unsigned __int64 v15; // rsi
  unsigned __int64 v16; // rdi
  KSPIN_LOCK **v17; // rcx
  unsigned __int64 v18; // rax
  KSPIN_LOCK *v19; // r14
  _QWORD *v20; // rax
  int v21; // r14d
  __int64 v22; // rax
  char result; // al
  KSPIN_LOCK *v24; // r14
  int inserted; // eax
  _QWORD *v26; // rax
  KSPIN_LOCK v27; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-49h] BYREF
  KSPIN_LOCK **v30; // [rsp+58h] [rbp-31h]
  __int128 v31; // [rsp+60h] [rbp-29h] BYREF
  __int128 v32; // [rsp+70h] [rbp-19h] BYREF

  v6 = a1;
  v8 = 0;
  v9 = a5 & 2;
  if ( (a5 & 2) == 0 && ((a5 & 4) != 0 || (*(_DWORD *)(a1 + 12) & 1) != 0) )
    v8 = 0x80000000;
  v10 = v8 | 1;
  if ( (a5 & 0x10) != 0 )
    v10 = v8;
  v11 = *(_DWORD *)(a2 + 452);
  v12 = v10 | 2;
  if ( (a5 & 0x20) == 0 )
    v12 = v10;
  if ( v11 )
  {
    v13 = -v11;
    v14 = v13 & (a3 + a4 + v11 - 1);
  }
  else
  {
    v13 = -*(_DWORD *)(*(_QWORD *)(a2 + 192) + 356LL);
    v14 = v13 & (a3 + a4 + *(_DWORD *)(*(_QWORD *)(a2 + 192) + 356LL) - 1);
  }
  *(_DWORD *)a6 &= 0xFFFFFFFC;
  v15 = a3 & v13;
  v16 = v14 - v15;
  v17 = (KSPIN_LOCK **)(*(_QWORD *)(a2 + 288) + 48LL);
  v30 = v17;
  v18 = v16 + v15 - 1;
  v31 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v32 = 0;
  if ( (v12 & 1) != 0 )
  {
    if ( v18 < v15 && v16 )
    {
      v21 = -1073741407;
      goto LABEL_18;
    }
    v24 = *v17;
    if ( !*v17 )
    {
      v21 = FsLibPrivateInitializeRangeLock();
      if ( v21 < 0 )
        goto LABEL_17;
      v18 = v16 + v15 - 1;
      v24 = *v30;
    }
    *(_QWORD *)&v32 = v15;
    *((_QWORD *)&v32 + 1) = v18;
    if ( !v24[2] )
    {
      KeAcquireInStackQueuedSpinLock(v24, &LockHandle);
      if ( !v24[2] )
      {
        v26 = ExAllocateFromNPagedLookasideList(&FsLibRangeLockIntLookasideList);
        v24[2] = (KSPIN_LOCK)v26;
        if ( !v26 )
          goto LABEL_16;
        v26[1] = 0;
        *(_QWORD *)v24[2] = 0;
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    if ( !v24[3] || (v12 & 2) != 0 )
    {
      KeAcquireInStackQueuedSpinLock(v24, &LockHandle);
    }
    else
    {
      KeAcquireInStackQueuedSpinLock(v24, &LockHandle);
      if ( v24[3] && !(unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v24, &v32, (unsigned __int8)v12) )
        goto LABEL_57;
    }
    if ( (unsigned __int8)FsLibPrivateCheckForExclusiveRangeLockAccess(v24) )
    {
      inserted = FsLibPrivateInsertRangeLockExclusive(v24, &v32, &v31);
      goto LABEL_28;
    }
LABEL_57:
    if ( v12 < 0 )
    {
      v21 = FsLibInsertWaitingLock(v24, &v32, v12 | 1u, &LockHandle, &v31);
      goto LABEL_17;
    }
LABEL_71:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v21 = -1073741739;
    goto LABEL_17;
  }
  if ( v18 >= v15 || !v16 )
  {
    v19 = *v17;
    if ( !*v17 )
    {
      v21 = FsLibPrivateInitializeRangeLock();
      if ( v21 < 0 )
        goto LABEL_17;
      v18 = v16 + v15 - 1;
      v19 = *v30;
    }
    *(_QWORD *)&v32 = v15;
    *((_QWORD *)&v32 + 1) = v18;
    if ( !v19[1] )
    {
      KeAcquireInStackQueuedSpinLock(v19, &LockHandle);
      if ( !v19[1] )
      {
        v20 = ExAllocateFromNPagedLookasideList(&FsLibRangeLockIntLookasideList);
        v19[1] = (KSPIN_LOCK)v20;
        if ( !v20 )
        {
LABEL_16:
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          v21 = -1073741670;
LABEL_17:
          v6 = a1;
          v9 = a5 & 2;
          goto LABEL_18;
        }
        v20[1] = 0;
        *(_QWORD *)v19[1] = 0;
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    if ( !v19[3] || (v12 & 2) != 0 )
    {
      KeAcquireInStackQueuedSpinLock(v19, &LockHandle);
      v27 = v19[2];
    }
    else
    {
      KeAcquireInStackQueuedSpinLock(v19, &LockHandle);
      if ( v19[3] && !(unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v19, &v32, (unsigned __int8)v12) )
      {
LABEL_66:
        if ( v12 < 0 )
        {
          v21 = FsLibInsertWaitingLock(v19, &v32, (unsigned int)v12, &LockHandle, &v31);
          goto LABEL_17;
        }
        goto LABEL_71;
      }
      v27 = v19[2];
    }
    if ( !(unsigned __int8)FsLibPrivateSearchArrayForRange(v27) )
      goto LABEL_66;
    inserted = FsLibPrivateInsertRangeLockShared(v19, &v32, &v31);
LABEL_28:
    v21 = inserted;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    goto LABEL_17;
  }
  v21 = -1073741407;
LABEL_18:
  if ( v21 == -1073741739 )
  {
    v21 = -1073741608;
  }
  else if ( v21 >= 0 )
  {
    *(_DWORD *)a6 |= 2 - ((a5 & 0x10) != 0);
    v22 = *(_QWORD *)(a2 + 288) + 48LL;
    *(_QWORD *)(a6 + 16) = v15;
    *(_QWORD *)(a6 + 8) = v22;
    result = 1;
    *(_QWORD *)(a6 + 24) = v16;
    return result;
  }
  if ( !v9 )
  {
    if ( NtfsStatusDebugFlags
      && (unsigned int)v21 < 0xFFFFFFED
      && v21 != -1073741802
      && v21 != -1073741807
      && (unsigned int)(v21 + 2147483643) > 1
      && v21 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(v6, (unsigned int)v21, 1903283);
      LODWORD(v6) = a1;
    }
    NtfsRaiseStatusInternal(v6, v21, 0, 0, 1903283);
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x1400100b0  push    rbp
0x1400100b2  push    rbx
0x1400100b3  push    rsi
0x1400100b4  push    rdi
0x1400100b5  push    r12
0x1400100b7  push    r13
0x1400100b9  push    r14
0x1400100bb  push    r15
0x1400100bd  lea     rbp, [rsp-0Fh]
0x1400100c2  sub     rsp, 98h
0x1400100c9  mov     rax, cs:__security_cookie
0x1400100d0  xor     rax, rsp
0x1400100d3  mov     [rbp+47h+var_50], rax
0x1400100d7  mov     rbx, [rbp+47h+arg_28]
0x1400100db  mov     r11, rcx
0x1400100de  mov     [rbp+47h+var_98], rcx
0x1400100e2  mov     r13, rdx
0x1400100e5  mov     ecx, dword ptr [rbp+47h+arg_20]
0x1400100e8  xor     edx, edx
0x1400100ea  mov     r10d, ecx
0x1400100ed  and     r10d, 2
0x1400100f1  mov     [rbp+47h+var_A0], r10d
0x1400100f5  jnz     short loc_140010105
0x1400100f7  test    cl, 4
0x1400100fa  jz      loc_1400102E6
0x140010100  mov     edx, 80000000h
0x140010105  mov     eax, edx
0x140010107  mov     r15d, ecx
0x14001010a  or      eax, 1
0x14001010d  and     r15d, 10h
0x140010111  cmovnz  eax, edx
0x140010114  mov     edx, [r13+1C4h]
0x14001011b  mov     r12d, eax
0x14001011e  or      r12d, 2
0x140010122  test    cl, 20h
0x140010125  cmovz   r12d, eax
0x140010129  test    edx, edx
0x14001012b  jz      loc_1400103A3
0x140010131  mov     eax, edx
0x140010133  neg     eax
0x140010135  movsxd  rcx, eax
0x140010138  lea     eax, [rdx-1]
0x14001013b  movsxd  rdi, eax
0x14001013e  mov     rsi, rcx
0x140010141  add     rdi, r9
0x140010144  add     rdi, r8
0x140010147  and     rdi, rcx
0x14001014a  and     dword ptr [rbx], 0FFFFFFFCh
0x14001014d  and     rsi, r8
0x140010150  mov     rcx, [r13+120h]
0x140010157  xorps   xmm0, xmm0
0x14001015a  sub     rdi, rsi
0x14001015d  add     rcx, 30h ; '0'
0x140010161  xor     edx, edx
0x140010163  mov     [rbp+47h+var_78], rcx
0x140010167  lea     rax, [rsi-1]
0x14001016b  mov     qword ptr [rbp+47h+LockHandle.OldIrql], rdx
0x14001016f  add     rax, rdi
0x140010172  movups  [rbp+47h+var_70], xmm0
0x140010176  movups  xmmword ptr [rbp+47h+LockHandle.LockQueue.Next], xmm0
0x14001017a  movups  [rbp+47h+var_60], xmm0
0x14001017e  test    r12b, 1
0x140010182  jnz     loc_140010266
0x140010188  cmp     rax, rsi
0x14001018b  jb      loc_140010501
0x140010191  mov     r14, [rcx]
0x140010194  test    r14, r14
0x140010197  jz      loc_1400103CE
0x14001019d  mov     qword ptr [rbp+47h+var_60], rsi
0x1400101a1  mov     qword ptr [rbp+47h+var_60+8], rax
0x1400101a5  cmp     qword ptr [r14+8], 0
0x1400101aa  jnz     loc_140010359
0x1400101b0  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x1400101b4  mov     rcx, r14; SpinLock
0x1400101b7  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400101be  nop     dword ptr [rax+rax+00h]
0x1400101c3  cmp     qword ptr [r14+8], 0
0x1400101c8  jnz     loc_140010528
0x1400101ce  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x1400101d5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400101dc  nop     dword ptr [rax+rax+00h]
0x1400101e1  mov     [r14+8], rax
0x1400101e5  test    rax, rax
0x1400101e8  jnz     loc_140010515
0x1400101ee  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x1400101f2  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400101f9  nop     dword ptr [rax+rax+00h]
0x1400101fe  mov     r14d, 0C000009Ah
0x140010204  mov     r11, [rbp+47h+var_98]
0x140010208  mov     r10d, [rbp+47h+var_A0]
0x14001020c  cmp     r14d, 0C0000055h
0x140010213  jz      loc_1400105AF
0x140010219  test    r14d, r14d
0x14001021c  js      loc_1400105BC
0x140010222  neg     r15d
0x140010225  sbb     eax, eax
0x140010227  add     eax, 2
0x14001022a  or      [rbx], eax
0x14001022c  mov     rax, [r13+120h]
0x140010233  add     rax, 30h ; '0'
0x140010237  mov     [rbx+10h], rsi
0x14001023b  mov     [rbx+8], rax
0x14001023f  mov     al, 1
0x140010241  mov     [rbx+18h], rdi
0x140010245  mov     rcx, [rbp+47h+var_50]
0x140010249  xor     rcx, rsp; StackCookie
0x14001024c  call    __security_check_cookie
0x140010251  add     rsp, 98h
0x140010258  pop     r15
0x14001025a  pop     r14
0x14001025c  pop     r13
0x14001025e  pop     r12
0x140010260  pop     rdi
0x140010261  pop     rsi
0x140010262  pop     rbx
0x140010263  pop     rbp
0x140010264  retn
0x140010266  cmp     rax, rsi
0x140010269  jb      loc_140010459
0x14001026f  mov     r14, [rcx]
0x140010272  test    r14, r14
0x140010275  jz      loc_14001046D
0x14001027b  mov     qword ptr [rbp+47h+var_60], rsi
0x14001027f  mov     qword ptr [rbp+47h+var_60+8], rax
0x140010283  cmp     qword ptr [r14+10h], 0
0x140010288  jz      short loc_1400102F7
0x14001028a  mov     rax, [r14+18h]
0x14001028e  test    rax, rax
0x140010291  jnz     loc_140010490
0x140010297  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x14001029b  mov     rcx, r14; SpinLock
0x14001029e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400102a5  nop     dword ptr [rax+rax+00h]
0x1400102aa  lea     rdx, [rbp+47h+var_60]
0x1400102ae  mov     rcx, r14
0x1400102b1  call    FsLibPrivateCheckForExclusiveRangeLockAccess
0x1400102b6  test    al, al
0x1400102b8  jz      loc_1400104D0
0x1400102be  lea     r8, [rbp+47h+var_70]
0x1400102c2  mov     rcx, r14
0x1400102c5  lea     rdx, [rbp+47h+var_60]
0x1400102c9  call    FsLibPrivateInsertRangeLockExclusive
0x1400102ce  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x1400102d2  mov     r14d, eax
0x1400102d5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400102dc  nop     dword ptr [rax+rax+00h]
0x1400102e1  jmp     loc_140010204
0x1400102e6  mov     eax, [r11+0Ch]
0x1400102ea  test    al, 1
0x1400102ec  jz      loc_140010105
0x1400102f2  jmp     loc_140010100
0x1400102f7  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x1400102fb  mov     rcx, r14; SpinLock
0x1400102fe  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140010305  nop     dword ptr [rax+rax+00h]
0x14001030a  cmp     qword ptr [r14+10h], 0
0x14001030f  jnz     short loc_140010344
0x140010311  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x140010318  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001031f  nop     dword ptr [rax+rax+00h]
0x140010324  mov     [r14+10h], rax
0x140010328  test    rax, rax
0x14001032b  jz      loc_1400101EE
0x140010331  mov     qword ptr [rax+8], 0
0x140010339  mov     rax, [r14+10h]
0x14001033d  mov     qword ptr [rax], 0
0x140010344  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x140010348  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001034f  nop     dword ptr [rax+rax+00h]
0x140010354  jmp     loc_14001028A
0x140010359  mov     rax, [r14+18h]
0x14001035d  test    rax, rax
0x140010360  jnz     loc_14001053D
0x140010366  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x14001036a  mov     rcx, r14; SpinLock
0x14001036d  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140010374  nop     dword ptr [rax+rax+00h]
0x140010379  mov     rcx, [r14+10h]
0x14001037d  lea     rdx, [rbp+47h+var_60]
0x140010381  call    FsLibPrivateSearchArrayForRange
0x140010386  test    al, al
0x140010388  jz      loc_140010582
0x14001038e  lea     r8, [rbp+47h+var_70]
0x140010392  mov     rcx, r14
0x140010395  lea     rdx, [rbp+47h+var_60]
0x140010399  call    FsLibPrivateInsertRangeLockShared
0x14001039e  jmp     loc_1400102CE
0x1400103a3  mov     rax, [r13+0C0h]
0x1400103aa  mov     ecx, [rax+164h]
0x1400103b0  mov     eax, ecx
0x1400103b2  neg     eax
0x1400103b4  movsxd  rdx, eax
0x1400103b7  mov     rsi, rdx
0x1400103ba  lea     eax, [rcx-1]
0x1400103bd  movsxd  rdi, eax
0x1400103c0  add     rdi, r9
0x1400103c3  add     rdi, r8
0x1400103c6  and     rdi, rdx
0x1400103c9  jmp     loc_14001014A
0x1400103ce  call    FsLibPrivateInitializeRangeLock
0x1400103d3  mov     r14d, eax
0x1400103d6  test    eax, eax
0x1400103d8  js      loc_140010204
0x1400103de  mov     r14, [rbp+47h+var_78]
0x1400103e2  lea     rax, [rsi-1]
0x1400103e6  add     rax, rdi
0x1400103e9  mov     r14, [r14]
0x1400103ec  jmp     loc_14001019D
0x1400103f1  movzx   eax, cs:NtfsStatusDebugFlags
0x1400103f8  test    al, al
0x1400103fa  jz      short loc_14001043E
0x1400103fc  cmp     r14d, 0FFFFFFEDh
0x140010400  jnb     short loc_14001043E
0x140010402  cmp     r14d, 0C0000016h
0x140010409  jz      short loc_14001043E
0x14001040b  cmp     r14d, 0C0000011h
0x140010412  jz      short loc_14001043E
0x140010414  lea     eax, [r14+7FFFFFFBh]
0x14001041b  cmp     eax, 1
0x14001041e  jbe     short loc_14001043E
0x140010420  cmp     r14d, 0C00000D8h
0x140010427  jz      short loc_14001043E
0x140010429  mov     r8d, 1D0AB3h
0x14001042f  mov     edx, r14d
0x140010432  mov     rcx, r11
0x140010435  call    NtfsStatusTraceAndDebugInternal
0x14001043a  mov     r11, [rbp+47h+var_98]
0x14001043e  xor     r9d, r9d
0x140010441  mov     [rsp+0D0h+var_B0], 1D0AB3h
0x14001044a  xor     r8d, r8d
0x14001044d  mov     edx, r14d
0x140010450  mov     rcx, r11
0x140010453  call    NtfsRaiseStatusInternal
0x140010458  int     3; Trap to Debugger
0x140010459  test    rdi, rdi
0x14001045c  jz      loc_14001026F
0x140010462  mov     r14d, 0C00001A1h
0x140010468  jmp     loc_14001020C
0x14001046d  call    FsLibPrivateInitializeRangeLock
0x140010472  mov     r14d, eax
0x140010475  test    eax, eax
0x140010477  js      loc_140010204
0x14001047d  mov     r14, [rbp+47h+var_78]
0x140010481  lea     rax, [rsi-1]
0x140010485  add     rax, rdi
0x140010488  mov     r14, [r14]
0x14001048b  jmp     loc_14001027B
0x140010490  test    r12b, 2
0x140010494  jnz     loc_140010297
0x14001049a  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x14001049e  mov     rcx, r14; SpinLock
0x1400104a1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400104a8  nop     dword ptr [rax+rax+00h]
0x1400104ad  cmp     qword ptr [r14+18h], 0
0x1400104b2  lea     rdx, [rbp+47h+var_60]
0x1400104b6  jz      loc_1400102AE
0x1400104bc  movzx   r8d, r12b
0x1400104c0  mov     rcx, r14
0x1400104c3  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x1400104c8  test    al, al
0x1400104ca  jnz     loc_1400102AA
0x1400104d0  test    r12d, r12d
0x1400104d3  jns     loc_14005DB3A
0x1400104d9  or      r12d, 1
0x1400104dd  lea     rax, [rbp+47h+var_70]
0x1400104e1  mov     r8d, r12d
0x1400104e4  mov     [rsp+0D0h+var_B0], rax
0x1400104e9  lea     r9, [rbp+47h+LockHandle]
0x1400104ed  mov     rcx, r14
0x1400104f0  lea     rdx, [rbp+47h+var_60]
0x1400104f4  call    FsLibInsertWaitingLock
0x1400104f9  mov     r14d, eax
0x1400104fc  jmp     loc_140010204
0x140010501  test    rdi, rdi
0x140010504  jz      loc_140010191
0x14001050a  mov     r14d, 0C00001A1h
0x140010510  jmp     loc_14001020C
0x140010515  mov     qword ptr [rax+8], 0
0x14001051d  mov     rax, [r14+8]
0x140010521  mov     qword ptr [rax], 0
0x140010528  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x14001052c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140010533  nop     dword ptr [rax+rax+00h]
0x140010538  jmp     loc_140010359
0x14001053d  test    r12b, 2
0x140010541  jnz     loc_140010366
0x140010547  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x14001054b  mov     rcx, r14; SpinLock
0x14001054e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140010555  nop     dword ptr [rax+rax+00h]
0x14001055a  cmp     qword ptr [r14+18h], 0
0x14001055f  lea     rdx, [rbp+47h+var_60]
0x140010563  jz      loc_14005DB55
0x140010569  movzx   r8d, r12b
0x14001056d  mov     rcx, r14
0x140010570  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x140010575  test    al, al
0x140010577  jz      short loc_140010582
0x140010579  lea     rdx, [rbp+47h+var_60]
0x14001057d  jmp     loc_14005DB55
  ... truncated ...
```
