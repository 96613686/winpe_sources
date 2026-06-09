# RefsDeactivateUsnJournal

- ea: `0x1c00a9ccc`
- end: `0x1c00aa3a5`
- name: `RefsDeactivateUsnJournal`
- size: `1753`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1c00a08f8`
- `0x1c01ce254`

## callees

- `0x1c0002ef8`
- `0x1c000440c`
- `0x1c00045c4`
- `0x1c0005818`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c003b27c`
- `0x1c0068168`
- `0x1c009d564`
- `0x1c00a7b30`
- `0x1c00a9ccc`
- `0x1c01c7228`
- `0x1c01d3848`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c00aa1eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00aa1eb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00a9da1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00aa030`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00aa345`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00aa37c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00a9da1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00aa030`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00aa345`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00aa37c`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1c00a9f9c`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1c00a9f9c`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c00a9d57`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c00a9e76`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c00a9ea4`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c00aa159`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c00aa2a1`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c00a9d57`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c00a9e76`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c00a9ea4`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c00aa159`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c00aa2a1`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c00a9d6b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c00a9f1d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c00a9f3d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c00aa28b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c00aa30f`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c00a9d6b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c00a9f1d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c00a9f3d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c00aa28b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c00aa30f`
- `ntoskrnl!CcPurgeCacheSection` at `0x1c00aa117`
- `ntoskrnl!CcPurgeCacheSection` at `0x1c00aa117`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c00a9db7`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c00aa042`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c00a9db7`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c00aa042`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c00a9dd6`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c00aa061`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c00a9dd6`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c00aa061`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c00a9d22`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c00aa096`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c00a9d22`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c00aa096`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c00a9d3d`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c00a9d92`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c00aa0b2`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c00aa36d`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c00a9d3d`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c00a9d92`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c00aa0b2`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c00aa36d`
- `ntoskrnl!KeSetEvent` at `0x1c00aa267`
- `ntoskrnl!KeSetEvent` at `0x1c00aa267`

## pseudocode

```c
void __fastcall RefsDeactivateUsnJournal(__int64 a1, __int64 a2, __int64 a3)
{
  struct _ERESOURCE *v3; // rdi
  char v4; // r12
  char v8; // r15
  struct _FAST_MUTEX *v9; // r14
  __int64 NextFcbTableEntry; // rdi
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r14
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // r15
  __int64 *v19; // rax
  __int64 v20; // rdx
  __int64 **v21; // rcx
  __int64 *v22; // rax
  __int64 v23; // rdx
  __int64 **v24; // rcx
  __int64 NextChildScb; // rax
  __int64 v26; // rax
  int v27; // edx
  char v28; // al
  __int64 v29; // rax
  __int64 *v30; // rdi
  __int64 *v31; // r15
  __int64 v32; // r9
  __int64 *v33; // rcx
  __int64 **v34; // rax
  _QWORD **v35; // rdx
  __int64 v36; // rcx
  _QWORD *v37; // r8
  __int64 *v38; // rax
  __int64 v39; // rcx
  __int64 **v40; // r8
  _QWORD *v41; // rax
  char v42; // [rsp+60h] [rbp+8h]
  __int64 v43; // [rsp+68h] [rbp+10h] BYREF

  v43 = 0;
  v3 = (struct _ERESOURCE *)(a2 + 1176);
  v4 = 0;
  if ( (*(_DWORD *)(a1 + 4) & 0x2000) != 0 )
  {
    v8 = 1;
    v42 = 1;
  }
  else
  {
    v8 = 0;
    v42 = 0;
    ExAcquireResourceExclusiveLite(v3, 1u);
    RtlCaptureStackBackTrace(0, 9u, (PVOID *)(a2 + 1280), 0);
    *(_DWORD *)(a1 + 4) |= 0x2000u;
  }
  v9 = (struct _FAST_MUTEX *)(a2 + 1104);
  ExAcquireFastMutex((PFAST_MUTEX)(a2 + 1104));
  *(_DWORD *)(a2 + 4) &= ~0x80000u;
  ExReleaseFastMutex((PFAST_MUTEX)(a2 + 1104));
  if ( !v8 )
  {
    *(_DWORD *)(a1 + 4) &= 0xFFFFCFFF;
    RtlCaptureStackBackTrace(0, 9u, (PVOID *)(a2 + 1352), 0);
    ExReleaseResourceLite(v3);
  }
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 536));
  NextFcbTableEntry = RefsGetNextFcbTableEntry(a2, &v43);
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 536));
  if ( NextFcbTableEntry )
  {
    do
    {
      v13 = 0;
      if ( *(_QWORD *)(NextFcbTableEntry + 104) )
      {
        LOBYTE(v12) = 1;
        RefsAcquirePagingResourceExclusive(v11, NextFcbTableEntry, v12);
        v4 = 1;
      }
      RefsAcquireExclusiveFcb(a1, NextFcbTableEntry, 0, 5);
      if ( !v4 && *(_QWORD *)(NextFcbTableEntry + 104) )
      {
        RefsReleaseFcb(a1, NextFcbTableEntry);
        LOBYTE(v16) = 1;
        RefsAcquirePagingResourceExclusive(v17, NextFcbTableEntry, v16);
        RefsAcquireExclusiveFcb(a1, NextFcbTableEntry, 0, 5);
        v4 = 1;
      }
      *(_DWORD *)(NextFcbTableEntry + 4) &= ~0x800000u;
      *(_QWORD *)(NextFcbTableEntry + 208) = 0;
      v18 = NextFcbTableEntry + 216;
      if ( *(_QWORD *)(NextFcbTableEntry + 216) )
      {
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(NextFcbTableEntry + 96) + 8LL));
        if ( *(_QWORD *)v18 )
        {
          if ( *(_QWORD *)(*(_QWORD *)v18 + 32LL) )
          {
            ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(NextFcbTableEntry + 88) + 984LL));
            v19 = (__int64 *)(*(_QWORD *)v18 + 32LL);
            v20 = *v19;
            if ( *v19 )
            {
              if ( *(__int64 **)(v20 + 8) != v19 || (v21 = *(__int64 ***)(*(_QWORD *)v18 + 40LL), *v21 != v19) )
LABEL_83:
                __fastfail(3u);
              *v21 = (__int64 *)v20;
              *(_QWORD *)(v20 + 8) = v21;
              v22 = (__int64 *)(*(_QWORD *)v18 + 16LL);
              v23 = *v22;
              if ( *v22 )
              {
                if ( *(__int64 **)(v23 + 8) != v22 )
                  goto LABEL_83;
                v24 = *(__int64 ***)(*(_QWORD *)v18 + 24LL);
                if ( *v24 != v22 )
                  goto LABEL_83;
                *v24 = (__int64 *)v23;
                *(_QWORD *)(v23 + 8) = v24;
                *(_QWORD *)(*(_QWORD *)v18 + 16LL) = 0;
              }
            }
            ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(NextFcbTableEntry + 88) + 984LL));
          }
          RefsDecrementFcbUsnRecordReferenceCountAndFreeIt(NextFcbTableEntry + 216);
          *(_QWORD *)v18 = 0;
        }
        ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(NextFcbTableEntry + 96) + 8LL));
      }
      while ( 1 )
      {
        NextChildScb = RefsGetNextChildScb(NextFcbTableEntry, v13, v14, v15);
        v13 = NextChildScb;
        if ( !NextChildScb )
          break;
        if ( *(_WORD *)NextChildScb == 2053 )
        {
          if ( (*(_DWORD *)(*(_QWORD *)(NextChildScb + 128) + 4LL) & 0x4000005) == 1
            && (*(_DWORD *)(NextChildScb + 304) & 0x40) == 0
            && FsRtlOplockIsFastIoPossible((POPLOCK)(NextChildScb + 88)) )
          {
            if ( *(_DWORD *)(v13 + 248)
              || (v26 = *(_QWORD *)(v13 + 336)) != 0 && *(_BYTE *)(v26 + 16)
              || (v27 = *(_DWORD *)(*(_QWORD *)(v13 + 128) + 4LL), (v27 & 0x2000000) != 0)
              || (*(_BYTE *)(*(_QWORD *)(v13 + 120) + 4LL) & 0x20) != 0
              || (v27 & 0x80000) != 0 )
            {
              v28 = 2;
            }
            else
            {
              v28 = 1;
            }
          }
          else
          {
            v28 = 0;
          }
          *(_BYTE *)(v13 + 5) = v28;
        }
      }
      RefsReleaseFcb(a1, NextFcbTableEntry);
      if ( v4 )
      {
        if ( *(_WORD *)NextFcbTableEntry != 2050 )
          NextFcbTableEntry = *(_QWORD *)(NextFcbTableEntry + 120);
        ExReleaseResourceLite(*(PERESOURCE *)(NextFcbTableEntry + 104));
        v4 = 0;
      }
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 536));
      NextFcbTableEntry = RefsGetNextFcbTableEntry(a2, &v43);
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 536));
    }
    while ( NextFcbTableEntry );
    v8 = v42;
    v9 = (struct _FAST_MUTEX *)(a2 + 1104);
  }
  if ( !v8 )
  {
    ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1176), 1u);
    RtlCaptureStackBackTrace(0, 9u, (PVOID *)(a2 + 1280), 0);
    *(_DWORD *)(a1 + 4) |= 0x2000u;
  }
  if ( a3 )
  {
    LOBYTE(v12) = 1;
    RefsAcquirePagingResourceExclusive(v11, a3, v12);
    RefsAcquireExclusiveScbWithFlags(a1, a3, 1);
  }
  v29 = *(_QWORD *)(a2 + 40);
  *(_DWORD *)(a2 + 4) |= 0x100000u;
  *(_DWORD *)(a2 + 1168) = 0;
  *(_QWORD *)(a2 + 1160) = v29;
  *(_QWORD *)(a2 + 40) = 0;
  if ( a3 )
    CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a3 + 240) + 8LL), 0, 0, 0);
  *(_QWORD *)(a2 + 904) = 0;
  *(_QWORD *)(a2 + 896) = 0;
  *(_QWORD *)(a2 + 888) = 0;
  *(_QWORD *)(a2 + 880) = 0;
  *(_QWORD *)(a2 + 936) = 0;
  *(_QWORD *)(a2 + 928) = 0;
  if ( a3 )
  {
    ExAcquireFastMutex(v9);
    v30 = *(__int64 **)(a2 + 1088);
    if ( v30 != (__int64 *)(a2 + 1088) )
    {
      do
      {
        v31 = (__int64 *)*v30;
        if ( (unsigned __int8)RefsClearCancelRoutine(v30[6]) )
        {
          if ( (*((_DWORD *)v30 + 17) & 1) != 0 )
          {
            v33 = (__int64 *)*v30;
            if ( *(__int64 **)(*v30 + 8) != v30 )
              goto LABEL_83;
            v34 = (__int64 **)v30[1];
            if ( *v34 != v30 )
              goto LABEL_83;
            *v34 = v33;
            v33[1] = (__int64)v34;
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741129);
            RefsExtendedCompleteRequestInternal(0, (IRP *)v30[6], -1073741129, v32);
            ExFreePoolWithTag(v30, 0);
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                48,
                WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids,
                3221226167LL);
            }
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741129);
            *((_DWORD *)v30 + 16) = -1073741129;
            KeSetEvent((PRKEVENT)v30 + 1, 0, 0);
          }
        }
        v30 = v31;
      }
      while ( v31 != (__int64 *)(a2 + 1088) );
      v8 = v42;
    }
    ExReleaseFastMutex((PFAST_MUTEX)(a2 + 1104));
    ExAcquireFastMutex((PFAST_MUTEX)(a2 + 984));
    v35 = (_QWORD **)(a2 + 968);
    while ( 1 )
    {
      v41 = *v35;
      if ( *v35 == v35 )
        break;
      v36 = *v41;
      if ( *(_QWORD **)(*v41 + 8LL) != v41 )
        goto LABEL_83;
      v37 = (_QWORD *)v41[1];
      if ( (_QWORD *)*v37 != v41 )
        goto LABEL_83;
      *v37 = v36;
      *(_QWORD *)(v36 + 8) = v37;
      *v41 = 0;
      v38 = v41 - 2;
      v39 = *v38;
      if ( *v38 )
      {
        if ( *(__int64 **)(v39 + 8) != v38 )
          goto LABEL_83;
        v40 = (__int64 **)v38[1];
        if ( *v40 != v38 )
          goto LABEL_83;
        *v40 = (__int64 *)v39;
        *(_QWORD *)(v39 + 8) = v40;
      }
    }
    ExReleaseFastMutex((PFAST_MUTEX)(a2 + 984));
    NtOfsCloseAttributeSafe(a1, a3);
    RefsReleaseFcb(a1, *(_QWORD *)(a3 + 120));
    if ( *(_WORD *)a3 != 2050 )
      a3 = *(_QWORD *)(a3 + 120);
    ExReleaseResourceLite(*(PERESOURCE *)(a3 + 104));
  }
  if ( !v8 )
  {
    *(_DWORD *)(a1 + 4) &= 0xFFFFCFFF;
    RtlCaptureStackBackTrace(0, 9u, (PVOID *)(a2 + 1352), 0);
    ExReleaseResourceLite((PERESOURCE)(a2 + 1176));
  }
}

```

## disassembly

```asm
0x1c00a9ccc  mov     [rsp+arg_10], rbx
0x1c00a9cd1  push    rbp
0x1c00a9cd2  push    rsi
0x1c00a9cd3  push    rdi
0x1c00a9cd4  push    r12
0x1c00a9cd6  push    r13
0x1c00a9cd8  push    r14
0x1c00a9cda  push    r15
0x1c00a9cdc  sub     rsp, 20h
0x1c00a9ce0  and     [rsp+58h+arg_8], 0
0x1c00a9ce6  lea     rdi, [rdx+498h]
0x1c00a9ced  xor     r12b, r12b
0x1c00a9cf0  mov     r14d, 2000h
0x1c00a9cf6  mov     rbp, r8
0x1c00a9cf9  mov     rbx, rdx
0x1c00a9cfc  mov     rsi, rcx
0x1c00a9cff  mov     r13d, 9
0x1c00a9d05  test    [rcx+4], r14d
0x1c00a9d09  jz      short loc_1C00A9D15
0x1c00a9d0b  mov     r15b, 1
0x1c00a9d0e  mov     [rsp+58h+arg_0], r15b
0x1c00a9d13  jmp     short loc_1C00A9D4D
0x1c00a9d15  xor     r15b, r15b
0x1c00a9d18  mov     dl, 1; Wait
0x1c00a9d1a  mov     rcx, rdi; Resource
0x1c00a9d1d  mov     [rsp+58h+arg_0], r15b
0x1c00a9d22  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1c00a9d29  nop     dword ptr [rax+rax+00h]
0x1c00a9d2e  lea     r8, [rbx+500h]; BackTrace
0x1c00a9d35  xor     r9d, r9d; BackTraceHash
0x1c00a9d38  mov     edx, r13d; FramesToCapture
0x1c00a9d3b  xor     ecx, ecx; FramesToSkip
0x1c00a9d3d  call    cs:__imp_RtlCaptureStackBackTrace
0x1c00a9d44  nop     dword ptr [rax+rax+00h]
0x1c00a9d49  or      [rsi+4], r14d
0x1c00a9d4d  lea     r14, [rbx+450h]
0x1c00a9d54  mov     rcx, r14; FastMutex
0x1c00a9d57  call    cs:__imp_ExAcquireFastMutex
0x1c00a9d5e  nop     dword ptr [rax+rax+00h]
0x1c00a9d63  btr     dword ptr [rbx+4], 13h
0x1c00a9d68  mov     rcx, r14; FastMutex
0x1c00a9d6b  call    cs:__imp_ExReleaseFastMutex
0x1c00a9d72  nop     dword ptr [rax+rax+00h]
0x1c00a9d77  test    r15b, r15b
0x1c00a9d7a  jnz     short loc_1C00A9DAD
0x1c00a9d7c  and     dword ptr [rsi+4], 0FFFFCFFFh
0x1c00a9d83  lea     r8, [rbx+548h]; BackTrace
0x1c00a9d8a  xor     r9d, r9d; BackTraceHash
0x1c00a9d8d  mov     edx, r13d; FramesToCapture
0x1c00a9d90  xor     ecx, ecx; FramesToSkip
0x1c00a9d92  call    cs:__imp_RtlCaptureStackBackTrace
0x1c00a9d99  nop     dword ptr [rax+rax+00h]
0x1c00a9d9e  mov     rcx, rdi; Resource
0x1c00a9da1  call    cs:__imp_ExReleaseResourceLite
0x1c00a9da8  nop     dword ptr [rax+rax+00h]
0x1c00a9dad  lea     r13, [rbx+218h]
0x1c00a9db4  mov     rcx, r13; Mutex
0x1c00a9db7  call    cs:__imp_KeAcquireGuardedMutex
0x1c00a9dbe  nop     dword ptr [rax+rax+00h]
0x1c00a9dc3  lea     rdx, [rsp+58h+arg_8]
0x1c00a9dc8  mov     rcx, rbx
0x1c00a9dcb  call    RefsGetNextFcbTableEntry
0x1c00a9dd0  mov     rcx, r13; Mutex
0x1c00a9dd3  mov     rdi, rax
0x1c00a9dd6  call    cs:__imp_KeReleaseGuardedMutex
0x1c00a9ddd  nop     dword ptr [rax+rax+00h]
0x1c00a9de2  test    rdi, rdi
0x1c00a9de5  jz      loc_1C00AA082
0x1c00a9deb  xor     r15d, r15d
0x1c00a9dee  mov     r14, r15
0x1c00a9df1  cmp     [rdi+68h], r15
0x1c00a9df5  jz      short loc_1C00A9E05
0x1c00a9df7  mov     r8b, 1
0x1c00a9dfa  mov     rdx, rdi
0x1c00a9dfd  call    RefsAcquirePagingResourceExclusive
0x1c00a9e02  mov     r12b, 1
0x1c00a9e05  mov     r9d, 5
0x1c00a9e0b  xor     r8d, r8d
0x1c00a9e0e  mov     rdx, rdi
0x1c00a9e11  mov     rcx, rsi
0x1c00a9e14  call    RefsAcquireExclusiveFcb
0x1c00a9e19  test    r12b, r12b
0x1c00a9e1c  jnz     short loc_1C00A9E51
0x1c00a9e1e  cmp     [rdi+68h], r15
0x1c00a9e22  jz      short loc_1C00A9E51
0x1c00a9e24  mov     rdx, rdi
0x1c00a9e27  mov     rcx, rsi
0x1c00a9e2a  call    RefsReleaseFcb
0x1c00a9e2f  mov     r8b, 1
0x1c00a9e32  mov     rdx, rdi
0x1c00a9e35  call    RefsAcquirePagingResourceExclusive
0x1c00a9e3a  mov     r9d, 5
0x1c00a9e40  xor     r8d, r8d
0x1c00a9e43  mov     rdx, rdi
0x1c00a9e46  mov     rcx, rsi
0x1c00a9e49  call    RefsAcquireExclusiveFcb
0x1c00a9e4e  mov     r12b, 1
0x1c00a9e51  btr     dword ptr [rdi+4], 17h
0x1c00a9e56  mov     [rdi+0D0h], r15
0x1c00a9e5d  lea     r15, [rdi+0D8h]
0x1c00a9e64  cmp     qword ptr [r15], 0
0x1c00a9e68  jz      loc_1C00A9F49
0x1c00a9e6e  mov     rcx, [rdi+60h]
0x1c00a9e72  add     rcx, 8; FastMutex
0x1c00a9e76  call    cs:__imp_ExAcquireFastMutex
0x1c00a9e7d  nop     dword ptr [rax+rax+00h]
0x1c00a9e82  mov     rax, [r15]
0x1c00a9e85  test    rax, rax
0x1c00a9e88  jz      loc_1C00A9F35
0x1c00a9e8e  cmp     qword ptr [rax+20h], 0
0x1c00a9e93  jz      loc_1C00A9F29
0x1c00a9e99  mov     rcx, [rdi+58h]
0x1c00a9e9d  add     rcx, 3D8h; FastMutex
0x1c00a9ea4  call    cs:__imp_ExAcquireFastMutex
0x1c00a9eab  nop     dword ptr [rax+rax+00h]
0x1c00a9eb0  mov     rax, [r15]
0x1c00a9eb3  add     rax, 20h ; ' '
0x1c00a9eb7  mov     rdx, [rax]
0x1c00a9eba  test    rdx, rdx
0x1c00a9ebd  jz      short loc_1C00A9F12
0x1c00a9ebf  cmp     [rdx+8], rax
0x1c00a9ec3  jnz     loc_1C00AA39E
0x1c00a9ec9  mov     rcx, [rax+8]
0x1c00a9ecd  cmp     [rcx], rax
0x1c00a9ed0  jnz     loc_1C00AA39E
0x1c00a9ed6  mov     [rcx], rdx
0x1c00a9ed9  mov     [rdx+8], rcx
0x1c00a9edd  mov     rax, [r15]
0x1c00a9ee0  add     rax, 10h
0x1c00a9ee4  mov     rdx, [rax]
0x1c00a9ee7  test    rdx, rdx
0x1c00a9eea  jz      short loc_1C00A9F12
0x1c00a9eec  cmp     [rdx+8], rax
0x1c00a9ef0  jnz     loc_1C00AA39E
0x1c00a9ef6  mov     rcx, [rax+8]
0x1c00a9efa  cmp     [rcx], rax
0x1c00a9efd  jnz     loc_1C00AA39E
0x1c00a9f03  mov     [rcx], rdx
0x1c00a9f06  mov     [rdx+8], rcx
0x1c00a9f0a  mov     rax, [r15]
0x1c00a9f0d  and     qword ptr [rax+10h], 0
0x1c00a9f12  mov     rcx, [rdi+58h]
0x1c00a9f16  add     rcx, 3D8h; FastMutex
0x1c00a9f1d  call    cs:__imp_ExReleaseFastMutex
0x1c00a9f24  nop     dword ptr [rax+rax+00h]
0x1c00a9f29  mov     rcx, r15
0x1c00a9f2c  call    RefsDecrementFcbUsnRecordReferenceCountAndFreeIt
0x1c00a9f31  and     qword ptr [r15], 0
0x1c00a9f35  mov     rcx, [rdi+60h]
0x1c00a9f39  add     rcx, 8; FastMutex
0x1c00a9f3d  call    cs:__imp_ExReleaseFastMutex
0x1c00a9f44  nop     dword ptr [rax+rax+00h]
0x1c00a9f49  xor     r15d, r15d
0x1c00a9f4c  mov     r13d, 805h
0x1c00a9f52  mov     rdx, r14
0x1c00a9f55  mov     rcx, rdi
0x1c00a9f58  call    RefsGetNextChildScb
0x1c00a9f5d  mov     r14, rax
0x1c00a9f60  test    rax, rax
0x1c00a9f63  jz      loc_1C00AA007
0x1c00a9f69  movzx   edx, word ptr [rax]
0x1c00a9f6c  cmp     dx, r13w
0x1c00a9f70  jnz     short loc_1C00A9F52
0x1c00a9f72  mov     rax, [rax+80h]
0x1c00a9f79  mov     ecx, [rax+4]
0x1c00a9f7c  and     ecx, 4000005h
0x1c00a9f82  cmp     ecx, 1
0x1c00a9f85  jnz     short loc_1C00A9FFB
0x1c00a9f87  cmp     dx, r13w
0x1c00a9f8b  jnz     short loc_1C00A9FFB
0x1c00a9f8d  mov     eax, [r14+130h]
0x1c00a9f94  test    al, 40h
0x1c00a9f96  jnz     short loc_1C00A9FFB
0x1c00a9f98  lea     rcx, [r14+58h]; Oplock
0x1c00a9f9c  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x1c00a9fa3  nop     dword ptr [rax+rax+00h]
0x1c00a9fa8  test    al, al
0x1c00a9faa  jz      short loc_1C00A9FFB
0x1c00a9fac  cmp     [r14+0F8h], r15d
0x1c00a9fb3  jnz     short loc_1C00A9FF4
0x1c00a9fb5  mov     rax, [r14+150h]
0x1c00a9fbc  test    rax, rax
0x1c00a9fbf  jz      short loc_1C00A9FC7
0x1c00a9fc1  cmp     [rax+10h], r15b
0x1c00a9fc5  jnz     short loc_1C00A9FF4
0x1c00a9fc7  mov     rax, [r14+80h]
0x1c00a9fce  mov     edx, [rax+4]
0x1c00a9fd1  bt      edx, 19h
0x1c00a9fd5  jb      short loc_1C00A9FF4
0x1c00a9fd7  mov     rax, [r14+78h]
0x1c00a9fdb  test    byte ptr [rax+4], 20h
0x1c00a9fdf  setz    cl
0x1c00a9fe2  bt      edx, 13h
0x1c00a9fe6  setnb   al
0x1c00a9fe9  test    al, cl
0x1c00a9feb  jz      short loc_1C00A9FF4
0x1c00a9fed  mov     eax, 1
0x1c00a9ff2  jmp     short loc_1C00A9FFE
0x1c00a9ff4  mov     eax, 2
0x1c00a9ff9  jmp     short loc_1C00A9FFE
0x1c00a9ffb  mov     eax, r15d
0x1c00a9ffe  mov     [r14+5], al
0x1c00aa002  jmp     loc_1C00A9F52
0x1c00aa007  mov     rdx, rdi
0x1c00aa00a  mov     rcx, rsi
0x1c00aa00d  call    RefsReleaseFcb
0x1c00aa012  lea     r13, [rbx+218h]
0x1c00aa019  test    r12b, r12b
0x1c00aa01c  jz      short loc_1C00AA03F
0x1c00aa01e  mov     eax, 802h
0x1c00aa023  cmp     ax, [rdi]
0x1c00aa026  jz      short loc_1C00AA02C
0x1c00aa028  mov     rdi, [rdi+78h]
0x1c00aa02c  mov     rcx, [rdi+68h]; Resource
0x1c00aa030  call    cs:__imp_ExReleaseResourceLite
0x1c00aa037  nop     dword ptr [rax+rax+00h]
0x1c00aa03c  mov     r12b, r15b
0x1c00aa03f  mov     rcx, r13; Mutex
0x1c00aa042  call    cs:__imp_KeAcquireGuardedMutex
0x1c00aa049  nop     dword ptr [rax+rax+00h]
0x1c00aa04e  lea     rdx, [rsp+58h+arg_8]
0x1c00aa053  mov     rcx, rbx
0x1c00aa056  call    RefsGetNextFcbTableEntry
0x1c00aa05b  mov     rcx, r13; Mutex
0x1c00aa05e  mov     rdi, rax
0x1c00aa061  call    cs:__imp_KeReleaseGuardedMutex
0x1c00aa068  nop     dword ptr [rax+rax+00h]
0x1c00aa06d  test    rdi, rdi
0x1c00aa070  jnz     loc_1C00A9DEE
0x1c00aa076  mov     r15b, [rsp+58h+arg_0]
0x1c00aa07b  lea     r14, [rbx+450h]
0x1c00aa082  xor     r13d, r13d
0x1c00aa085  lea     r12, [rbx+498h]
0x1c00aa08c  test    r15b, r15b
0x1c00aa08f  jnz     short loc_1C00AA0C3
0x1c00aa091  mov     dl, 1; Wait
0x1c00aa093  mov     rcx, r12; Resource
0x1c00aa096  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1c00aa09d  nop     dword ptr [rax+rax+00h]
0x1c00aa0a2  lea     r8, [rbx+500h]; BackTrace
0x1c00aa0a9  xor     r9d, r9d; BackTraceHash
0x1c00aa0ac  lea     edx, [r13+9]; FramesToCapture
0x1c00aa0b0  xor     ecx, ecx; FramesToSkip
0x1c00aa0b2  call    cs:__imp_RtlCaptureStackBackTrace
0x1c00aa0b9  nop     dword ptr [rax+rax+00h]
0x1c00aa0be  bts     dword ptr [rsi+4], 0Dh
0x1c00aa0c3  test    rbp, rbp
0x1c00aa0c6  jz      short loc_1C00AA0E4
0x1c00aa0c8  mov     r8b, 1
0x1c00aa0cb  mov     rdx, rbp
0x1c00aa0ce  call    RefsAcquirePagingResourceExclusive
0x1c00aa0d3  mov     r8d, 1
0x1c00aa0d9  mov     rdx, rbp
0x1c00aa0dc  mov     rcx, rsi
0x1c00aa0df  call    RefsAcquireExclusiveScbWithFlags
0x1c00aa0e4  mov     rax, [rbx+28h]
0x1c00aa0e8  bts     dword ptr [rbx+4], 14h
0x1c00aa0ed  mov     [rbx+490h], r13d
0x1c00aa0f4  mov     [rbx+488h], rax
0x1c00aa0fb  mov     [rbx+28h], r13
0x1c00aa0ff  test    rbp, rbp
0x1c00aa102  jz      short loc_1C00AA123
0x1c00aa104  mov     rcx, [rbp+0F0h]
0x1c00aa10b  xor     r9d, r9d; Flags
0x1c00aa10e  add     rcx, 8; SectionObjectPointer
0x1c00aa112  xor     r8d, r8d; Length
0x1c00aa115  xor     edx, edx; FileOffset
0x1c00aa117  call    cs:__imp_CcPurgeCacheSection
0x1c00aa11e  nop     dword ptr [rax+rax+00h]
0x1c00aa123  mov     [rbx+388h], r13
0x1c00aa12a  mov     [rbx+380h], r13
0x1c00aa131  mov     [rbx+378h], r13
0x1c00aa138  mov     [rbx+370h], r13
0x1c00aa13f  mov     [rbx+3A8h], r13
0x1c00aa146  mov     [rbx+3A0h], r13
0x1c00aa14d  test    rbp, rbp
0x1c00aa150  jz      loc_1C00AA351
0x1c00aa156  mov     rcx, r14; FastMutex
0x1c00aa159  call    cs:__imp_ExAcquireFastMutex
0x1c00aa160  nop     dword ptr [rax+rax+00h]
0x1c00aa165  lea     r14, [rbx+440h]
0x1c00aa16c  mov     rdi, [r14]
0x1c00aa16f  cmp     rdi, r14
0x1c00aa172  jz      loc_1C00AA284
0x1c00aa178  mov     rcx, [rdi+30h]
0x1c00aa17c  mov     r15, [rdi]
0x1c00aa17f  call    RefsClearCancelRoutine
0x1c00aa184  test    al, al
0x1c00aa186  jz      loc_1C00AA273
0x1c00aa18c  mov     eax, [rdi+44h]
0x1c00aa18f  test    al, 1
0x1c00aa191  jz      short loc_1C00AA1F9
0x1c00aa193  mov     rcx, [rdi]
0x1c00aa196  cmp     [rcx+8], rdi
0x1c00aa19a  jnz     loc_1C00AA39E
0x1c00aa1a0  mov     rax, [rdi+8]
0x1c00aa1a4  cmp     [rax], rdi
0x1c00aa1a7  jnz     loc_1C00AA39E
0x1c00aa1ad  mov     [rax], rcx
0x1c00aa1b0  mov     [rcx+8], rax
  ... truncated ...
```
