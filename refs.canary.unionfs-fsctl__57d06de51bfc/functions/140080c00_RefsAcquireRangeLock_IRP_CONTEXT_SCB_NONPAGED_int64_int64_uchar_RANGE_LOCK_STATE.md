# RefsAcquireRangeLock(_IRP_CONTEXT *,_SCB_NONPAGED *,__int64,__int64,uchar,_RANGE_LOCK_STATE *)

- ea: `0x140080c00`
- end: `0x14008106e`
- name: `?RefsAcquireRangeLock@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB_NONPAGED@@_J2EPEAU_RANGE_LOCK_STATE@@@Z`
- size: `1134`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _SCB_NONPAGED *, __int64, __int64, char, struct _RANGE_LOCK_STATE *)`
- caller_count: `14`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x140008fd0`
- `0x14003b3f0`
- `0x1400e51d8`
- `0x1400e5a80`
- `0x1400e6ec0`
- `0x1400e785c`
- `0x1400e96c0`
- `0x1400eb8f8`
- `0x1400ec8dc`
- `0x14028aa64`
- `0x14028f01c`
- `0x140296eb0`
- `0x14029c098`
- `0x1402ac510`

## callees

- `0x140080c00`
- `0x140081670`
- `0x14008c030`
- `0x14008dbd0`
- `0x1400904c0`
- `0x1400a1730`
- `0x1400ca788`
- `0x1400cabd8`
- `0x1401e993c`
- `0x1401e9a0c`
- `0x1401e9ce0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140080d6c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140080e93`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401f79c6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140080d6c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140080e93`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401f79c6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140080ceb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140080e79`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140080ede`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140080f81`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401f79ad`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401f7a49`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140080ceb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140080e79`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140080ede`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140080f81`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401f79ad`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401f7a49`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140080db9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140080ebe`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140081057`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401f79df`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401f7a05`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401f7a7b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140080db9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140080ebe`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140081057`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401f79df`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401f7a05`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401f7a7b`

## pseudocode

```c
void __fastcall RefsAcquireRangeLock(
        struct _IRP_CONTEXT *a1,
        struct _SCB_NONPAGED *a2,
        __int64 a3,
        __int64 a4,
        char a5,
        struct _RANGE_LOCK_STATE *a6)
{
  struct _IRP_CONTEXT *v7; // rbx
  __int64 v8; // rax
  char v9; // cl
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int128 v14; // rdi
  KSPIN_LOCK *v15; // r14
  KSPIN_LOCK **v16; // rbx
  NTSTATUS inserted; // r15d
  _QWORD *i; // r10
  unsigned __int64 j; // rax
  __int64 v21; // rcx
  char v22; // dl
  __int64 v23; // rcx
  __int64 v24; // r8
  char v25; // al
  _QWORD *v26; // rdx
  __int64 v27; // rax
  _QWORD *v28; // rbx
  _QWORD *v29; // rax
  unsigned __int64 v30; // rax
  char v31; // cl
  unsigned __int64 v32; // rdi
  __int64 v33; // rdx
  __int64 v34; // r14
  KSPIN_LOCK *v35; // rbx
  KSPIN_LOCK **v36; // rsi
  _QWORD *v37; // rax
  NTSTATUS v38; // r15d
  int v39; // eax
  _QWORD *v40; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-29h] BYREF
  __int128 v43; // [rsp+60h] [rbp-11h] BYREF

  v7 = a1;
  if ( (*((_DWORD *)a1 + 1) & 0x40) != 0 )
    return;
  v8 = *((_QWORD *)a2 + 7);
  LockHandle.LockQueue = 0;
  v43 = 0;
  if ( !a5 )
  {
    v9 = 14;
    if ( *(_DWORD *)(v8 + 552) == 12 )
      v9 = 12;
    v10 = 1 << v9;
    *(_QWORD *)&LockHandle.OldIrql = 0;
    v11 = v10 - 1;
    v12 = -v10;
    *(_QWORD *)&v14 = a3 & v12;
    v13 = v12 & (a3 + a4 + v11);
    *((_QWORD *)&v14 + 1) = v13 - 1;
    if ( v13 - 1 < (a3 & (unsigned __int64)v12) && v13 != (_QWORD)v14 )
    {
      inserted = -1073741407;
      goto LABEL_44;
    }
    v15 = (KSPIN_LOCK *)*((_QWORD *)a2 + 8);
    v16 = (KSPIN_LOCK **)((char *)a2 + 64);
    if ( !v15 )
    {
      inserted = FsLibPrivateInitializeRangeLock((char *)a2 + 64);
      if ( inserted < 0 )
        goto LABEL_43;
      v15 = *v16;
    }
    inserted = 0;
    v43 = v14;
    if ( !v15[1] )
    {
      KeAcquireInStackQueuedSpinLock(v15, &LockHandle);
      if ( !v15[1] )
      {
        v40 = ExAllocateFromNPagedLookasideList(&FsLibRangeLockIntLookasideList);
        v15[1] = (KSPIN_LOCK)v40;
        if ( !v40 )
        {
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          inserted = -1073741670;
          goto LABEL_43;
        }
        v40[1] = 0;
        *(_QWORD *)v15[1] = 0;
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    if ( v15[3] )
    {
      KeAcquireInStackQueuedSpinLock(v15, &LockHandle);
      if ( v15[3] && !(unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v15, &v43, 0) )
        goto LABEL_56;
      v25 = FsLibPrivateSearchArrayForRange(v15[2], &v43);
    }
    else
    {
      KeAcquireInStackQueuedSpinLock(v15, &LockHandle);
      for ( i = (_QWORD *)v15[2]; i; i = (_QWORD *)*i )
      {
        for ( j = i[1]; _BitScanForward64((unsigned __int64 *)&v21, j); j &= ~(1LL << v22) )
        {
          v22 = v21;
          v23 = 2 * v21;
          v24 = i[v23 + 2];
          if ( (__int64)v43 > v24 )
            goto LABEL_16;
          if ( v24 <= *((__int64 *)&v43 + 1) )
            goto LABEL_18;
          if ( (__int64)v43 >= v24 )
          {
LABEL_16:
            if ( (__int64)v43 <= i[v23 + 3] )
            {
LABEL_18:
              v25 = 0;
              goto LABEL_19;
            }
          }
        }
      }
      v25 = 1;
    }
LABEL_19:
    if ( v25 )
    {
      v26 = (_QWORD *)v15[1];
      do
      {
        v27 = v26[1];
        if ( v27 != -1 )
        {
          v30 = ~v27;
          goto LABEL_26;
        }
        v28 = v26;
        v26 = (_QWORD *)*v26;
      }
      while ( v26 );
      v29 = ExAllocateFromNPagedLookasideList(&FsLibRangeLockIntLookasideList);
      *v28 = v29;
      v26 = v29;
      if ( !v29 )
      {
        inserted = -1073741670;
        goto LABEL_27;
      }
      v29[1] = 0;
      *v29 = 0;
      v30 = -1;
LABEL_26:
      _BitScanForward64(&v30, v30);
      *(_QWORD *)a6 = v26;
      *((_QWORD *)a6 + 1) = 1LL << v30;
      v26[1] |= 1LL << v30;
      *(_OWORD *)&v26[2 * v30 + 2] = v43;
LABEL_27:
      KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_28:
      if ( inserted >= 0 )
        return;
LABEL_43:
      v7 = a1;
LABEL_44:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          18,
          WPP_31376ab3b8073048edfb14e725e449b5_Traceguids,
          (unsigned int)inserted);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(inserted, v7, "ResrcSup.c", 0xE54u);
      RefsRaiseStatusInternal(v7, inserted, a3);
      __debugbreak();
    }
LABEL_56:
    inserted = FsLibInsertWaitingLock(v15, &v43, 0x80000000LL, &LockHandle, a6);
    goto LABEL_28;
  }
  v31 = *(_BYTE *)(v8 + 552);
  v32 = a3 >> v31 << v31;
  v33 = (a3 + a4 + *(unsigned int *)(v8 + 544)) >> v31 << v31;
  *(_QWORD *)&LockHandle.OldIrql = 0;
  v34 = v33 - 1;
  if ( v33 - 1 < v32 && v33 != v32 )
  {
    v38 = -1073741407;
    goto LABEL_77;
  }
  v35 = (KSPIN_LOCK *)*((_QWORD *)a2 + 8);
  v36 = (KSPIN_LOCK **)((char *)a2 + 64);
  if ( !v35 )
  {
    v39 = FsLibPrivateInitializeRangeLock((char *)a2 + 64);
    if ( v39 < 0 )
    {
      v38 = v39;
      goto LABEL_49;
    }
    v35 = *v36;
  }
  *(_QWORD *)&v43 = v32;
  *((_QWORD *)&v43 + 1) = v34;
  if ( !v35[2] )
  {
    KeAcquireInStackQueuedSpinLock(v35, &LockHandle);
    if ( !v35[2] )
    {
      v37 = ExAllocateFromNPagedLookasideList(&FsLibRangeLockIntLookasideList);
      v35[2] = (KSPIN_LOCK)v37;
      if ( !v37 )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v38 = -1073741670;
        goto LABEL_49;
      }
      v37[1] = 0;
      *(_QWORD *)v35[2] = 0;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  if ( v35[3] )
  {
    KeAcquireInStackQueuedSpinLock(v35, &LockHandle);
    if ( v35[3] && !(unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v35, &v43, 0) )
      goto LABEL_76;
  }
  else
  {
    KeAcquireInStackQueuedSpinLock(v35, &LockHandle);
  }
  if ( (unsigned __int8)FsLibPrivateCheckForExclusiveRangeLockAccess(v35, &v43) )
  {
    v38 = FsLibPrivateInsertRangeLockExclusive(v35, &v43, a6);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    goto LABEL_48;
  }
LABEL_76:
  v38 = FsLibInsertWaitingLock(v35, &v43, 2147483649LL, &LockHandle, a6);
LABEL_48:
  if ( v38 < 0 )
  {
LABEL_49:
    v7 = a1;
LABEL_77:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_31376ab3b8073048edfb14e725e449b5_Traceguids,
        (unsigned int)v38);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(v38, v7, "ResrcSup.c", 0xE63u);
    RefsRaiseStatusInternal(v7, v38, a3);
    JUMPOUT(0x1401F7B18LL);
  }
}

```

## disassembly

```asm
0x140080c00  mov     r11, rsp
0x140080c03  push    rbp
0x140080c04  push    rbx
0x140080c05  push    r13
0x140080c07  lea     rbp, [r11-4Fh]
0x140080c0b  sub     rsp, 0A0h
0x140080c12  mov     rax, cs:__security_cookie
0x140080c19  xor     rax, rsp
0x140080c1c  mov     [rbp+47h+var_48], rax
0x140080c20  mov     eax, [rcx+4]
0x140080c23  mov     r10, rdx
0x140080c26  mov     r13, [rbp+47h+arg_28]
0x140080c2a  mov     rbx, rcx
0x140080c2d  mov     [rbp+47h+var_80], rcx
0x140080c31  test    al, 40h
0x140080c33  jnz     loc_140080DF3
0x140080c39  cmp     [rbp+47h+arg_20], 0
0x140080c3d  xorps   xmm0, xmm0
0x140080c40  mov     rax, [rdx+38h]
0x140080c44  mov     [r11-20h], rsi
0x140080c48  mov     [r11-28h], rdi
0x140080c4c  mov     [r11-38h], r14
0x140080c50  mov     [r11-40h], r15
0x140080c54  movups  xmmword ptr [rbp+47h+LockHandle.LockQueue.Next], xmm0
0x140080c58  movups  [rbp+47h+var_58], xmm0
0x140080c5c  jnz     loc_140080E1D
0x140080c62  mov     eax, [rax+228h]
0x140080c68  mov     ecx, 0Eh
0x140080c6d  cmp     eax, 0Ch
0x140080c70  mov     [r11-30h], r12
0x140080c74  mov     r12d, 1
0x140080c7a  cmovz   cx, ax
0x140080c7e  mov     eax, r12d
0x140080c81  shl     eax, cl
0x140080c83  movsxd  rcx, eax
0x140080c86  xor     eax, eax
0x140080c88  mov     rdx, rcx
0x140080c8b  mov     qword ptr [rbp+47h+LockHandle.OldIrql], rax
0x140080c8f  dec     rcx
0x140080c92  neg     rdx
0x140080c95  add     rcx, r9
0x140080c98  mov     rdi, rdx
0x140080c9b  add     rcx, r8
0x140080c9e  and     rdi, r8
0x140080ca1  and     rcx, rdx
0x140080ca4  lea     rsi, [rcx-1]
0x140080ca8  cmp     rsi, rdi
0x140080cab  jb      loc_140080F59
0x140080cb1  mov     r14, [r10+40h]
0x140080cb5  lea     rbx, [r10+40h]
0x140080cb9  test    r14, r14
0x140080cbc  jz      loc_140080F6A
0x140080cc2  xor     r15d, r15d
0x140080cc5  mov     qword ptr [rbp+47h+var_58], rdi
0x140080cc9  mov     qword ptr [rbp+47h+var_58+8], rsi
0x140080ccd  cmp     [r14+8], r15
0x140080cd1  jz      loc_1401F79A6
0x140080cd7  mov     rax, [r14+18h]
0x140080cdb  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x140080cdf  mov     rcx, r14; SpinLock
0x140080ce2  test    rax, rax
0x140080ce5  jnz     loc_140080F81
0x140080ceb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140080cf2  nop     dword ptr [rax+rax+00h]
0x140080cf7  mov     r10, [r14+10h]
0x140080cfb  mov     r11, qword ptr [rbp+47h+var_58+8]
0x140080cff  mov     r9, qword ptr [rbp+47h+var_58]
0x140080d03  test    r10, r10
0x140080d06  jz      loc_140080E14
0x140080d0c  mov     rax, [r10+8]
0x140080d10  bsf     rcx, rax
0x140080d14  jz      loc_140080E0C
0x140080d1a  mov     edx, ecx
0x140080d1c  add     rcx, rcx
0x140080d1f  mov     r8, [r10+rcx*8+10h]
0x140080d24  cmp     r9, r8
0x140080d27  jg      short loc_140080D33
0x140080d29  cmp     r8, r11
0x140080d2c  jle     short loc_140080D40
0x140080d2e  cmp     r9, r8
0x140080d31  jl      short loc_140080D3A
0x140080d33  cmp     r9, [r10+rcx*8+18h]
0x140080d38  jle     short loc_140080D40
0x140080d3a  btr     rax, rdx
0x140080d3e  jmp     short loc_140080D10
0x140080d40  xor     al, al
0x140080d42  test    al, al
0x140080d44  jz      loc_140080FB3
0x140080d4a  mov     rdx, [r14+8]
0x140080d4e  xchg    ax, ax
0x140080d50  mov     rax, [rdx+8]
0x140080d54  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140080d58  jnz     short loc_140080D8F
0x140080d5a  mov     rbx, rdx
0x140080d5d  mov     rdx, [rdx]
0x140080d60  test    rdx, rdx
0x140080d63  jnz     short loc_140080D50
0x140080d65  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x140080d6c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140080d73  nop     dword ptr [rax+rax+00h]
0x140080d78  mov     [rbx], rax
0x140080d7b  mov     rdx, rax
0x140080d7e  test    rax, rax
0x140080d81  jnz     loc_1401F7A2E
0x140080d87  mov     r15d, 0C000009Ah
0x140080d8d  jmp     short loc_140080DB5
0x140080d8f  not     rax
0x140080d92  bsf     rax, rax
0x140080d96  mov     [r13+0], rdx
0x140080d9a  mov     ecx, eax
0x140080d9c  inc     rax
0x140080d9f  shl     r12, cl
0x140080da2  mov     [r13+8], r12
0x140080da6  or      [rdx+8], r12
0x140080daa  movups  xmm0, [rbp+47h+var_58]
0x140080dae  add     rax, rax
0x140080db1  movups  xmmword ptr [rdx+rax*8], xmm0
0x140080db5  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x140080db9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140080dc0  nop     dword ptr [rax+rax+00h]
0x140080dc5  test    r15d, r15d
0x140080dc8  js      loc_140080F11
0x140080dce  mov     r12, [rsp+0B0h+var_28]
0x140080dd6  mov     r14, [rsp+0B0h+var_30]
0x140080dde  mov     rdi, [rsp+0B0h+var_20]
0x140080de6  mov     rsi, [rsp+98h]
0x140080dee  mov     r15, [rsp+0B0h+var_38]
0x140080df3  mov     rcx, [rbp+47h+var_48]
0x140080df7  xor     rcx, rsp; StackCookie
0x140080dfa  call    __security_check_cookie
0x140080dff  add     rsp, 0A0h
0x140080e06  pop     r13
0x140080e08  pop     rbx
0x140080e09  pop     rbp
0x140080e0a  retn
0x140080e0c  mov     r10, [r10]
0x140080e0f  jmp     loc_140080D03
0x140080e14  movzx   eax, r12b
0x140080e18  jmp     loc_140080D42
0x140080e1d  movsx   ecx, byte ptr [rax+228h]
0x140080e24  mov     rdi, r8
0x140080e27  mov     edx, [rax+220h]
0x140080e2d  xor     eax, eax
0x140080e2f  add     rdx, r9
0x140080e32  sar     rdi, cl
0x140080e35  add     rdx, r8
0x140080e38  shl     rdi, cl
0x140080e3b  sar     rdx, cl
0x140080e3e  shl     rdx, cl
0x140080e41  mov     qword ptr [rbp+47h+LockHandle.OldIrql], rax
0x140080e45  lea     r14, [rdx-1]
0x140080e49  cmp     r14, rdi
0x140080e4c  jb      loc_140081027
0x140080e52  mov     rbx, [r10+40h]
0x140080e56  lea     rsi, [r10+40h]
0x140080e5a  test    rbx, rbx
0x140080e5d  jz      loc_14008103B
0x140080e63  mov     qword ptr [rbp+47h+var_58], rdi
0x140080e67  mov     qword ptr [rbp+47h+var_58+8], r14
0x140080e6b  cmp     qword ptr [rbx+10h], 0
0x140080e70  jnz     short loc_140080ECA
0x140080e72  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x140080e76  mov     rcx, rbx; SpinLock
0x140080e79  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140080e80  nop     dword ptr [rax+rax+00h]
0x140080e85  cmp     qword ptr [rbx+10h], 0
0x140080e8a  jnz     short loc_140080EBA
0x140080e8c  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x140080e93  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140080e9a  nop     dword ptr [rax+rax+00h]
0x140080e9f  mov     [rbx+10h], rax
0x140080ea3  test    rax, rax
0x140080ea6  jz      loc_140081053
0x140080eac  xor     r15d, r15d
0x140080eaf  mov     [rax+8], r15
0x140080eb3  mov     rax, [rbx+10h]
0x140080eb7  mov     [rax], r15
0x140080eba  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x140080ebe  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140080ec5  nop     dword ptr [rax+rax+00h]
0x140080eca  mov     rax, [rbx+18h]
0x140080ece  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x140080ed2  mov     rcx, rbx; SpinLock
0x140080ed5  test    rax, rax
0x140080ed8  jz      loc_1401F7A49
0x140080ede  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140080ee5  nop     dword ptr [rax+rax+00h]
0x140080eea  cmp     qword ptr [rbx+18h], 0
0x140080eef  lea     rdx, [rbp+47h+var_58]
0x140080ef3  jz      loc_1401F7A59
0x140080ef9  xor     r8d, r8d
0x140080efc  mov     rcx, rbx
0x140080eff  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x140080f04  test    al, al
0x140080f06  jnz     loc_1401F7A55
0x140080f0c  jmp     loc_1401F7A8D
0x140080f11  mov     rbx, [rbp+47h+var_80]
0x140080f15  mov     rcx, cs:WPP_GLOBAL_Control
0x140080f1c  lea     rax, WPP_GLOBAL_Control
0x140080f23  cmp     rcx, rax
0x140080f26  jnz     loc_140080FD6
0x140080f2c  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140080f33  test    al, al
0x140080f35  jnz     loc_14008100A
0x140080f3b  mov     edx, r15d; int
0x140080f3e  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140080f41  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x140080f46  int     3; Trap to Debugger
0x140080f47  test    r15d, r15d
0x140080f4a  jns     loc_140080DD6
0x140080f50  mov     rbx, [rbp+47h+var_80]
0x140080f54  jmp     loc_1401F7AB0
0x140080f59  cmp     rcx, rdi
0x140080f5c  jz      loc_140080CB1
0x140080f62  mov     r15d, 0C00001A1h
0x140080f68  jmp     short loc_140080F15
0x140080f6a  mov     rcx, rbx
0x140080f6d  call    FsLibPrivateInitializeRangeLock
0x140080f72  mov     r15d, eax
0x140080f75  test    eax, eax
0x140080f77  js      short loc_140080F11
0x140080f79  mov     r14, [rbx]
0x140080f7c  jmp     loc_140080CC2
0x140080f81  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140080f88  nop     dword ptr [rax+rax+00h]
0x140080f8d  lea     rdx, [rbp+47h+var_58]
0x140080f91  cmp     [r14+18h], r15
0x140080f95  jz      loc_1401F7A17
0x140080f9b  xor     r8d, r8d
0x140080f9e  mov     rcx, r14
0x140080fa1  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x140080fa6  test    al, al
0x140080fa8  jz      short loc_140080FB3
0x140080faa  lea     rdx, [rbp+47h+var_58]
0x140080fae  jmp     loc_1401F7A17
0x140080fb3  lea     r9, [rbp+47h+LockHandle]
0x140080fb7  mov     [rsp+20h], r13
0x140080fbc  mov     r8d, 80000000h
0x140080fc2  lea     rdx, [rbp+47h+var_58]
0x140080fc6  mov     rcx, r14
0x140080fc9  call    FsLibInsertWaitingLock
0x140080fce  mov     r15d, eax
0x140080fd1  jmp     loc_140080DC5
0x140080fd6  test    dword ptr [rcx+2Ch], 100h
0x140080fdd  jz      loc_140080F2C
0x140080fe3  cmp     byte ptr [rcx+29h], 4
0x140080fe7  jb      loc_140080F2C
0x140080fed  mov     rcx, [rcx+18h]
0x140080ff1  lea     r8, WPP_31376ab3b8073048edfb14e725e449b5_Traceguids
0x140080ff8  mov     edx, 12h
0x140080ffd  mov     r9d, r15d
0x140081000  call    WPP_SF_d
0x140081005  jmp     loc_140080F2C
0x14008100a  mov     r9d, 0E54h; unsigned int
0x140081010  lea     r8, aResrcsupC; "ResrcSup.c"
0x140081017  mov     rdx, rbx; struct _IRP_CONTEXT *
0x14008101a  mov     ecx, r15d; Status
0x14008101d  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140081022  jmp     loc_140080F3B
0x140081027  cmp     rdx, rdi
0x14008102a  jz      loc_140080E52
0x140081030  mov     r15d, 0C00001A1h
0x140081036  jmp     loc_1401F7AB0
0x14008103b  mov     rcx, rsi
0x14008103e  call    FsLibPrivateInitializeRangeLock
0x140081043  test    eax, eax
0x140081045  jns     loc_1401F7A41
0x14008104b  mov     r15d, eax
0x14008104e  jmp     loc_140080F50
0x140081053  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x140081057  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14008105e  nop     dword ptr [rax+rax+00h]
0x140081063  mov     r15d, 0C000009Ah
0x140081069  jmp     loc_140080F50
0x1401f79a6  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x1401f79aa  mov     rcx, r14; SpinLock
0x1401f79ad  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1401f79b4  nop     dword ptr [rax+rax+00h]
0x1401f79b9  cmp     [r14+8], r15
0x1401f79bd  jnz     short loc_1401F7A01
0x1401f79bf  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x1401f79c6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1401f79cd  nop     dword ptr [rax+rax+00h]
0x1401f79d2  mov     [r14+8], rax
0x1401f79d6  test    rax, rax
0x1401f79d9  jnz     short loc_1401F79F6
0x1401f79db  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x1401f79df  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1401f79e6  nop     dword ptr [rax+rax+00h]
0x1401f79eb  mov     r15d, 0C000009Ah
0x1401f79f1  jmp     loc_140080F11
0x1401f79f6  mov     [rax+8], r15
0x1401f79fa  mov     rax, [r14+8]
0x1401f79fe  mov     [rax], r15
0x1401f7a01  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x1401f7a05  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1401f7a0c  nop     dword ptr [rax+rax+00h]
0x1401f7a11  nop
0x1401f7a12  jmp     loc_140080CD7
0x1401f7a17  mov     rax, r14
  ... truncated ...
```
