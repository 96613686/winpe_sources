# CStagingPool::GetGdiSurface(int,int,tagRECT const *,CDDBITMAP_GDIDESC *,uchar)

- ea: `0x14000c33c`
- end: `0x14000c728`
- name: `?GetGdiSurface@CStagingPool@@QEAAJHHPEBUtagRECT@@PEAUCDDBITMAP_GDIDESC@@E@Z`
- size: `1004`
- prototype: `__int64 __usercall@<rax>(CStagingPool *__hidden this@<rcx>, int@<edx>, int@<r8d>, const struct tagRECT *@<r9>, struct CDDBITMAP_GDIDESC *, unsigned __int8)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140002504`
- `0x140004904`
- `0x14000a254`
- `0x14000c2e0`
- `0x14000ca00`
- `0x1400161b0`
- `0x140017518`
- `0x140019458`
- `0x1400200e8`
- `0x140033548`

## callees

- `0x14000c33c`
- `0x14000cf80`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000c383`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c3c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c717`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c383`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c3c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c717`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000c447`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000c5ba`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000c66d`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000c447`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000c5ba`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000c66d`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000c477`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000c560`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000c630`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000c477`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000c560`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000c630`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000c4ba`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000c58d`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000c67c`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000c4ba`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000c58d`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000c67c`
- `watchdog!WdLogSingleEntry2` at `0x14000c5dd`
- `watchdog!WdLogSingleEntry2` at `0x14000c5dd`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000c3f4`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000c6d2`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000c3f4`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000c6d2`
- `watchdog!WdLogSingleEntry0` at `0x14000c3dd`
- `watchdog!WdLogSingleEntry0` at `0x14000c6bb`
- `watchdog!WdLogSingleEntry0` at `0x14000c3dd`
- `watchdog!WdLogSingleEntry0` at `0x14000c6bb`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000c5f4`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000c5f4`

## pseudocode

```c
__int64 __fastcall CStagingPool::GetGdiSurface(
        CStagingPool *this,
        int a2,
        int a3,
        const struct tagRECT *a4,
        struct CDDBITMAP_GDIDESC *a5,
        unsigned __int8 a6)
{
  _QWORD *v9; // rdi
  NTSTATUS v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rcx
  __int64 v16; // rdi
  char *v17; // r14
  CStagingPool **v18; // rax
  CStagingPool *v19; // rdx
  __int64 v20; // rbp
  unsigned __int8 *Rect; // r9
  int v22; // edx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rbp
  __int64 v26; // rcx
  _QWORD *v27; // rax
  __int64 v28; // rbp
  __int64 v29; // rdx
  _QWORD *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  _QWORD *v33; // rax

  if ( a6 )
  {
    v9 = *(_QWORD **)(*(_QWORD *)this + 7160LL);
    v10 = KeWaitForSingleObject(v9, Executive, 0, 0, 0);
    if ( v10 != 258 )
    {
      v9[4] = KeGetCurrentThread();
      if ( v10 < 0 )
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 1059;
        v33 = (_QWORD *)WdLogNewEntry5_WdError(v32, v31);
        v33[3] = gCddImageInfo;
        v33[4] = (unsigned int)dword_14003E570;
        v33[5] = 215857758;
        WdLogGlobalForLineNumber = 1059;
        return 3221225473LL;
      }
    }
  }
  if ( !*((_DWORD *)this + 2) )
    goto LABEL_7;
  if ( KeWaitForSingleObject(*((PVOID *)this + 101), Executive, 0, 0, 0) )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 1085;
    v13 = (_QWORD *)WdLogNewEntry5_WdError(v12, v11);
    v13[3] = gCddImageInfo;
    v13[4] = (unsigned int)dword_14003E570;
    v13[5] = 215857758;
    WdLogGlobalForLineNumber = 1085;
LABEL_7:
    if ( !a6 )
      return 3221225473LL;
    v14 = *(_QWORD *)(*(_QWORD *)this + 7160LL);
    if ( !*(_QWORD *)(v14 + 32) )
      return 3221225473LL;
    *(_QWORD *)(v14 + 32) = 0;
    goto LABEL_10;
  }
  v16 = *(_QWORD *)(*(_QWORD *)this + 2904LL);
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v16);
  v17 = (char *)this + 792;
  v18 = (CStagingPool **)*((_QWORD *)this + 99);
  if ( v18[1] != (CStagingPool *)((char *)this + 792) || (v19 = *v18, *((CStagingPool ***)*v18 + 1) != v18) )
LABEL_23:
    __fastfail(3u);
  *(_QWORD *)v17 = v19;
  *((_QWORD *)v19 + 1) = v17;
  *((_QWORD *)a5 + 1) = v18;
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v16);
  v20 = *(_QWORD *)(*((_QWORD *)a5 + 1) + 16LL);
  Rect = CStagingPoolBase::AllocateRect(this, a2, a3, a4, 1, (struct tagRECT *)((char *)a5 + 36), (int *)(v20 + 64));
  if ( !Rect || (v22 = *(_DWORD *)(*((_QWORD *)this + 11) + 40LL)) == 0 )
  {
    WdLogSingleEntry2(4, Rect, *(unsigned int *)(*((_QWORD *)this + 11) + 40LL));
    WdLogGlobalForLineNumber = 1104;
    v27 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v27[3] = gCddImageInfo;
    v27[4] = (unsigned int)dword_14003E570;
    v27[5] = 215857758;
    WdLogGlobalForLineNumber = 1104;
    v28 = *(_QWORD *)(*(_QWORD *)this + 2904LL);
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v28);
    v29 = *(_QWORD *)v17;
    if ( *(char **)(*(_QWORD *)v17 + 8LL) == v17 )
    {
      v30 = (_QWORD *)*((_QWORD *)a5 + 1);
      *v30 = v29;
      v30[1] = v17;
      *(_QWORD *)(v29 + 8) = v30;
      *(_QWORD *)v17 = v30;
      KeReleaseSemaphore(*((PRKSEMAPHORE *)this + 101), 0, 1, 0);
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v28);
      if ( !a6 )
        return 3221225473LL;
      v14 = *(_QWORD *)(*(_QWORD *)this + 7160LL);
      if ( !*(_QWORD *)(v14 + 32) )
        return 3221225473LL;
      *(_QWORD *)(v14 + 32) = 0;
LABEL_10:
      KeReleaseSemaphore((PRKSEMAPHORE)v14, 0, 1, 0);
      return 3221225473LL;
    }
    goto LABEL_23;
  }
  *((_DWORD *)a5 + 4) = v22;
  *((_QWORD *)a5 + 3) = *((_QWORD *)this + 11);
  v23 = *((_QWORD *)a5 + 1);
  *((_QWORD *)a5 + 7) = this;
  *(_QWORD *)a5 = v20;
  *(_QWORD *)(v23 + 32) = *((_QWORD *)this + 11);
  v24 = *(_DWORD *)(v20 + 64) * a3;
  *(_QWORD *)(v20 + 56) = Rect;
  *(_QWORD *)(v20 + 48) = Rect;
  *(_DWORD *)(v20 + 32) = a2;
  *(_DWORD *)(v20 + 36) = a3;
  *(_DWORD *)(v20 + 40) = v24;
  v25 = *(_QWORD *)(*(_QWORD *)this + 2904LL);
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v25);
  if ( !*(_DWORD *)(*((_QWORD *)this + 11) + 144LL) )
    KeWaitForSingleObject(*((PVOID *)this + 7), Executive, 0, 0, 0);
  ++*(_DWORD *)(*((_QWORD *)this + 11) + 144LL);
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v25);
  if ( a6 )
  {
    v26 = *(_QWORD *)(*(_QWORD *)this + 7160LL);
    if ( *(_QWORD *)(v26 + 32) )
    {
      *(_QWORD *)(v26 + 32) = 0;
      KeReleaseSemaphore((PRKSEMAPHORE)v26, 0, 1, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000c33c  mov     [rsp+arg_18], r9
0x14000c341  push    rbx
0x14000c342  push    rbp
0x14000c343  push    rsi
0x14000c344  push    rdi
0x14000c345  push    r12
0x14000c347  push    r13
0x14000c349  push    r14
0x14000c34b  push    r15
0x14000c34d  sub     rsp, 48h
0x14000c351  mov     sil, [rsp+88h+arg_28]
0x14000c359  xor     ebp, ebp
0x14000c35b  mov     r12d, r8d
0x14000c35e  mov     r13d, edx
0x14000c361  mov     rbx, rcx
0x14000c364  test    sil, sil
0x14000c367  jz      short loc_14000C3AB
0x14000c369  mov     rax, [rcx]
0x14000c36c  xor     r9d, r9d; Alertable
0x14000c36f  xor     r8d, r8d; WaitMode
0x14000c372  mov     [rsp+88h+Timeout], rbp; Timeout
0x14000c377  xor     edx, edx; WaitReason
0x14000c379  mov     rdi, [rax+1BF8h]
0x14000c380  mov     rcx, rdi; Object
0x14000c383  call    cs:__imp_KeWaitForSingleObject
0x14000c38a  nop     dword ptr [rax+rax+00h]
0x14000c38f  cmp     eax, 102h
0x14000c394  jz      short loc_14000C3AB
0x14000c396  mov     rcx, gs:188h
0x14000c39f  mov     [rdi+20h], rcx
0x14000c3a3  test    eax, eax
0x14000c3a5  js      loc_14000C6B6
0x14000c3ab  cmp     [rbx+8], ebp
0x14000c3ae  jz      short loc_14000C423
0x14000c3b0  mov     rcx, [rbx+328h]; Object
0x14000c3b7  xor     r9d, r9d; Alertable
0x14000c3ba  xor     r8d, r8d; WaitMode
0x14000c3bd  mov     [rsp+88h+Timeout], rbp; Timeout
0x14000c3c2  xor     edx, edx; WaitReason
0x14000c3c4  call    cs:__imp_KeWaitForSingleObject
0x14000c3cb  nop     dword ptr [rax+rax+00h]
0x14000c3d0  test    eax, eax
0x14000c3d2  jz      loc_14000C46A
0x14000c3d8  mov     ecx, 2
0x14000c3dd  call    cs:__imp_WdLogSingleEntry0
0x14000c3e4  nop     dword ptr [rax+rax+00h]
0x14000c3e9  mov     edi, 43Dh
0x14000c3ee  mov     cs:WdLogGlobalForLineNumber, edi
0x14000c3f4  call    cs:__imp_WdLogNewEntry5_WdError
0x14000c3fb  nop     dword ptr [rax+rax+00h]
0x14000c400  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000c407  mov     [rax+18h], rcx
0x14000c40b  mov     ecx, cs:dword_14003E570
0x14000c411  mov     [rax+20h], rcx
0x14000c415  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000c41d  mov     cs:WdLogGlobalForLineNumber, edi
0x14000c423  test    sil, sil
0x14000c426  jz      short loc_14000C453
0x14000c428  mov     rax, [rbx]
0x14000c42b  mov     rcx, [rax+1BF8h]; Semaphore
0x14000c432  cmp     [rcx+20h], rbp
0x14000c436  jz      short loc_14000C453
0x14000c438  mov     [rcx+20h], rbp
0x14000c43c  mov     r8d, 1; Adjustment
0x14000c442  xor     r9d, r9d; Wait
0x14000c445  xor     edx, edx; Increment
0x14000c447  call    cs:__imp_KeReleaseSemaphore
0x14000c44e  nop     dword ptr [rax+rax+00h]
0x14000c453  mov     eax, 0C0000001h
0x14000c458  add     rsp, 48h
0x14000c45c  pop     r15
0x14000c45e  pop     r14
0x14000c460  pop     r13
0x14000c462  pop     r12
0x14000c464  pop     rdi
0x14000c465  pop     rsi
0x14000c466  pop     rbp
0x14000c467  pop     rbx
0x14000c468  retn
0x14000c46a  mov     rax, [rbx]
0x14000c46d  mov     rdi, [rax+0B58h]
0x14000c474  mov     rcx, rdi
0x14000c477  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000c47e  nop     dword ptr [rax+rax+00h]
0x14000c483  lea     r14, [rbx+318h]
0x14000c48a  mov     rax, [r14]
0x14000c48d  cmp     [rax+8], r14
0x14000c491  jnz     loc_14000C645
0x14000c497  mov     rdx, [rax]
0x14000c49a  cmp     [rdx+8], rax
0x14000c49e  jnz     loc_14000C645
0x14000c4a4  mov     r15, [rsp+88h+arg_20]
0x14000c4ac  mov     rcx, rdi
0x14000c4af  mov     [r14], rdx
0x14000c4b2  mov     [rdx+8], r14
0x14000c4b6  mov     [r15+8], rax
0x14000c4ba  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000c4c1  nop     dword ptr [rax+rax+00h]
0x14000c4c6  mov     rax, [r15+8]
0x14000c4ca  mov     edi, 1
0x14000c4cf  mov     r9, [rsp+88h+arg_18]; struct tagRECT *
0x14000c4d7  mov     r8d, r12d; int
0x14000c4da  mov     edx, r13d; int
0x14000c4dd  mov     rbp, [rax+10h]
0x14000c4e1  lea     rax, [r15+24h]
0x14000c4e5  lea     rcx, [rbp+40h]
0x14000c4e9  mov     [rsp+88h+var_58], rcx; int *
0x14000c4ee  mov     rcx, rbx; this
0x14000c4f1  mov     [rsp+88h+var_60], rax; struct tagRECT *
0x14000c4f6  mov     dword ptr [rsp+88h+Timeout], edi; int
0x14000c4fa  call    ?AllocateRect@CStagingPoolBase@@QEAAPEAEHHPEBUtagRECT@@HPEAU2@PEAJ@Z; CStagingPoolBase::AllocateRect(int,int,tagRECT const *,int,tagRECT *,long *)
0x14000c4ff  mov     r9, rax
0x14000c502  test    rax, rax
0x14000c505  jz      loc_14000C5CD
0x14000c50b  mov     rcx, [rbx+58h]
0x14000c50f  mov     edx, [rcx+28h]
0x14000c512  test    edx, edx
0x14000c514  jz      loc_14000C5CD
0x14000c51a  mov     [r15+10h], edx
0x14000c51e  mov     rcx, [rbx+58h]
0x14000c522  mov     [r15+18h], rcx
0x14000c526  mov     rcx, [r15+8]
0x14000c52a  mov     [r15+38h], rbx
0x14000c52e  mov     [r15], rbp
0x14000c531  mov     rax, [rbx+58h]
0x14000c535  mov     [rcx+20h], rax
0x14000c539  mov     eax, r12d
0x14000c53c  imul    eax, [rbp+40h]
0x14000c540  mov     [rbp+38h], r9
0x14000c544  mov     [rbp+30h], r9
0x14000c548  mov     [rbp+20h], r13d
0x14000c54c  mov     [rbp+24h], r12d
0x14000c550  mov     [rbp+28h], eax
0x14000c553  mov     rax, [rbx]
0x14000c556  mov     rbp, [rax+0B58h]
0x14000c55d  mov     rcx, rbp
0x14000c560  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000c567  nop     dword ptr [rax+rax+00h]
0x14000c56c  mov     rax, [rbx+58h]
0x14000c570  xor     r14d, r14d
0x14000c573  cmp     [rax+90h], r14d
0x14000c57a  jz      loc_14000C706
0x14000c580  mov     rax, [rbx+58h]
0x14000c584  mov     rcx, rbp
0x14000c587  add     [rax+90h], edi
0x14000c58d  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000c594  nop     dword ptr [rax+rax+00h]
0x14000c599  test    sil, sil
0x14000c59c  jz      short loc_14000C5C6
0x14000c59e  mov     rax, [rbx]
0x14000c5a1  mov     rcx, [rax+1BF8h]; Semaphore
0x14000c5a8  cmp     [rcx+20h], r14
0x14000c5ac  jz      short loc_14000C5C6
0x14000c5ae  xor     r9d, r9d; Wait
0x14000c5b1  mov     [rcx+20h], r14
0x14000c5b5  mov     r8d, edi; Adjustment
0x14000c5b8  xor     edx, edx; Increment
0x14000c5ba  call    cs:__imp_KeReleaseSemaphore
0x14000c5c1  nop     dword ptr [rax+rax+00h]
0x14000c5c6  xor     eax, eax
0x14000c5c8  jmp     loc_14000C458
0x14000c5cd  mov     rax, [rbx+58h]
0x14000c5d1  mov     rdx, r9
0x14000c5d4  mov     ecx, 4
0x14000c5d9  mov     r8d, [rax+28h]
0x14000c5dd  call    cs:__imp_WdLogSingleEntry2
0x14000c5e4  nop     dword ptr [rax+rax+00h]
0x14000c5e9  mov     ebp, 450h
0x14000c5ee  mov     cs:WdLogGlobalForLineNumber, ebp
0x14000c5f4  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14000c5fb  nop     dword ptr [rax+rax+00h]
0x14000c600  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000c607  mov     [rax+18h], rcx
0x14000c60b  mov     ecx, cs:dword_14003E570
0x14000c611  mov     [rax+20h], rcx
0x14000c615  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000c61d  mov     cs:WdLogGlobalForLineNumber, ebp
0x14000c623  mov     rax, [rbx]
0x14000c626  mov     rbp, [rax+0B58h]
0x14000c62d  mov     rcx, rbp
0x14000c630  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000c637  nop     dword ptr [rax+rax+00h]
0x14000c63c  mov     rdx, [r14]
0x14000c63f  cmp     [rdx+8], r14
0x14000c643  jz      short loc_14000C64C
0x14000c645  mov     ecx, 3
0x14000c64a  int     29h; Win8: RtlFailFast(ecx)
0x14000c64c  mov     rax, [r15+8]
0x14000c650  xor     r9d, r9d; Wait
0x14000c653  mov     r8d, edi; Adjustment
0x14000c656  mov     [rax], rdx
0x14000c659  mov     [rax+8], r14
0x14000c65d  mov     [rdx+8], rax
0x14000c661  xor     edx, edx; Increment
0x14000c663  mov     [r14], rax
0x14000c666  mov     rcx, [rbx+328h]; Semaphore
0x14000c66d  call    cs:__imp_KeReleaseSemaphore
0x14000c674  nop     dword ptr [rax+rax+00h]
0x14000c679  mov     rcx, rbp
0x14000c67c  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000c683  nop     dword ptr [rax+rax+00h]
0x14000c688  test    sil, sil
0x14000c68b  jz      loc_14000C453
0x14000c691  mov     rax, [rbx]
0x14000c694  mov     rcx, [rax+1BF8h]
0x14000c69b  cmp     qword ptr [rcx+20h], 0
0x14000c6a0  jz      loc_14000C453
0x14000c6a6  mov     qword ptr [rcx+20h], 0
0x14000c6ae  mov     r8d, edi
0x14000c6b1  jmp     loc_14000C442
0x14000c6b6  mov     ecx, 2
0x14000c6bb  call    cs:__imp_WdLogSingleEntry0
0x14000c6c2  nop     dword ptr [rax+rax+00h]
0x14000c6c7  mov     ebx, 423h
0x14000c6cc  mov     cs:WdLogGlobalForLineNumber, ebx
0x14000c6d2  call    cs:__imp_WdLogNewEntry5_WdError
0x14000c6d9  nop     dword ptr [rax+rax+00h]
0x14000c6de  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000c6e5  mov     [rax+18h], rcx
0x14000c6e9  mov     ecx, cs:dword_14003E570
0x14000c6ef  mov     [rax+20h], rcx
0x14000c6f3  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000c6fb  mov     cs:WdLogGlobalForLineNumber, ebx
0x14000c701  jmp     loc_14000C453
0x14000c706  mov     rcx, [rbx+38h]; Object
0x14000c70a  xor     r9d, r9d; Alertable
0x14000c70d  xor     r8d, r8d; WaitMode
0x14000c710  mov     [rsp+88h+Timeout], r14; Timeout
0x14000c715  xor     edx, edx; WaitReason
0x14000c717  call    cs:__imp_KeWaitForSingleObject
0x14000c71e  nop     dword ptr [rax+rax+00h]
0x14000c723  jmp     loc_14000C580
```
