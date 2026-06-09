# CHwCommandBuffer::AddBitBltCommand(BITBLT_DATA *,uint,tagRECT const *,tagPOINT const *)

- ea: `0x14000f370`
- end: `0x14000fbad`
- name: `?AddBitBltCommand@CHwCommandBuffer@@QEAAHPEAUBITBLT_DATA@@IPEBUtagRECT@@PEBUtagPOINT@@@Z`
- size: `2109`
- prototype: `int(CHwCommandBuffer *__hidden this, struct BITBLT_DATA *, unsigned int, const struct tagRECT *, const struct tagPOINT *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14000ddd0`
- `0x14002d4b4`

## callees

- `0x14000f370`
- `0x14000fbb4`
- `0x1400101a0`
- `0x1400106ec`
- `0x140010798`
- `0x140010850`
- `0x1400372d0`
- `0x140037340`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000f60f`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000f749`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000f7a3`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000f836`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000f60f`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000f749`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000f7a3`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000f836`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000f635`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000f76f`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000f7c9`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000f85c`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000f635`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000f76f`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000f7c9`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000f85c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f5f1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f72b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f785`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f818`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f5f1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f72b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f785`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f818`
- `ntoskrnl!DbgPrint` at `0x14000f905`
- `ntoskrnl!DbgPrint` at `0x14000f99f`
- `ntoskrnl!DbgPrint` at `0x14000f905`
- `ntoskrnl!DbgPrint` at `0x14000f99f`
- `ntoskrnl!KdDebuggerEnabled` at `0x14000f8ee`
- `ntoskrnl!KdDebuggerEnabled` at `0x14000f988`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000f92c`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000f9c6`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000f92c`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000f9c6`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000fa29`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000fa7c`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000facf`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000fb22`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000fb75`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000fa29`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000fa7c`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000facf`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000fb22`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000fb75`
- `watchdog!WdLogSingleEntry0` at `0x14000f916`
- `watchdog!WdLogSingleEntry0` at `0x14000f9b0`
- `watchdog!WdLogSingleEntry0` at `0x14000fa13`
- `watchdog!WdLogSingleEntry0` at `0x14000fa66`
- `watchdog!WdLogSingleEntry0` at `0x14000fab9`
- `watchdog!WdLogSingleEntry0` at `0x14000fb0c`
- `watchdog!WdLogSingleEntry0` at `0x14000fb5f`
- `watchdog!WdLogSingleEntry0` at `0x14000f916`
- `watchdog!WdLogSingleEntry0` at `0x14000f9b0`
- `watchdog!WdLogSingleEntry0` at `0x14000fa13`
- `watchdog!WdLogSingleEntry0` at `0x14000fa66`
- `watchdog!WdLogSingleEntry0` at `0x14000fab9`
- `watchdog!WdLogSingleEntry0` at `0x14000fb0c`
- `watchdog!WdLogSingleEntry0` at `0x14000fb5f`

## string_xrefs

- `0x14000f8fe`: `Attempt to insert NULL allocation to the allocation list`
- `0x14000f998`: `Attempt to insert NULL allocation to the allocation list`

## pseudocode

```c
__int64 __fastcall CHwCommandBuffer::AddBitBltCommand(
        CHwCommandBuffer *this,
        struct BITBLT_DATA *a2,
        unsigned int a3,
        const struct tagRECT *a4,
        const struct tagPOINT *a5)
{
  __int64 v5; // r11
  CCommandBufferMutex *v6; // r14
  unsigned int v8; // ebp
  __int64 v11; // r12
  CDDPDEV *v12; // r10
  unsigned int v13; // r8d
  __int64 v14; // rcx
  _DWORD *v15; // rcx
  char v16; // al
  int v17; // edi
  __int64 i; // r14
  int v19; // edi
  __int64 j; // rcx
  __int64 v21; // rdi
  __int128 v22; // xmm0
  void (__fastcall ***v23)(_QWORD, CHwCommandBuffer *, __int64, __int64, const struct tagPOINT *); // r10
  void (__fastcall *v24)(_QWORD, CHwCommandBuffer *, __int64, __int64, const struct tagPOINT *); // r11
  void (__fastcall ***v25)(_QWORD, CHwCommandBuffer *, _QWORD, _QWORD, _QWORD); // rcx
  __int64 v26; // rbx
  __int64 v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // rdi
  __int64 v31; // rbx
  __int64 v32; // rbx
  __int64 v33; // rdx
  __int64 v34; // rbx
  _QWORD *v35; // rax
  _QWORD *v36; // rax
  _QWORD *v37; // rax
  _QWORD *v38; // rax
  _QWORD *v39; // rax
  _QWORD *v40; // rax
  _QWORD *v41; // rax
  _OWORD v42[6]; // [rsp+30h] [rbp-68h] BYREF
  CCommandBufferMutex *v43; // [rsp+A0h] [rbp+8h]
  const struct tagRECT *v44; // [rsp+B8h] [rbp+20h]

  v44 = a4;
  v5 = *((_QWORD *)this + 4);
  v6 = (CCommandBufferMutex *)*((_QWORD *)a2 + 4);
  v8 = 16 * a3;
  v43 = v6;
  v11 = 16 * a3 + 80;
  if ( (unsigned __int64)(v5 + v11) > *((_QWORD *)this + 3)
    || (v12 = *(CDDPDEV **)this, v13 = *((_DWORD *)this + 530), v13 > *(_DWORD *)(*(_QWORD *)this + 12712LL)) )
  {
    v28 = *(_QWORD *)this;
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 12696LL) + 32LL) != *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 12696LL)
                                                                                 + 16LL) )
    {
      if ( KeGetCurrentThread() == *(struct _KTHREAD **)(v28 + 2568) )
      {
        CDDPDEV::FlushGdiOutput((CDDPDEV *)v28, 0);
      }
      else if ( v6 && *((_BYTE *)v6 + 9) )
      {
        CCommandBufferMutex::EnableWorkerThreadAccess(v6);
        if ( KeGetCurrentIrql() )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 785;
          v40 = (_QWORD *)WdLogNewEntry5_WdAssertion();
          v40[3] = gCddImageInfo;
          v40[4] = (unsigned int)dword_14003E570;
          v40[5] = 215857758;
          WdLogGlobalForLineNumber = 785;
        }
        v29 = *(_QWORD *)(v28 + 5488);
        ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v29);
        *(_DWORD *)(v28 + 3648) = 2;
        CddIssueCommand(v28, 13);
        ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v29);
        CCommandBufferMutex::DisableWorkerThreadAccess(v6);
      }
      else
      {
        if ( KeGetCurrentIrql() )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 785;
          v41 = (_QWORD *)WdLogNewEntry5_WdAssertion();
          v41[3] = gCddImageInfo;
          v41[4] = (unsigned int)dword_14003E570;
          v41[5] = 215857758;
          WdLogGlobalForLineNumber = 785;
        }
        v34 = *(_QWORD *)(v28 + 5488);
        ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v34);
        *(_DWORD *)(v28 + 3648) = 2;
        CddIssueCommand(v28, 13);
        ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v34);
      }
    }
    v33 = *(_QWORD *)(v28 + 12696);
    if ( *(_DWORD *)(v33 + 32) != *(_DWORD *)(v33 + 16) )
      return 0;
LABEL_53:
    *(_BYTE *)(v33 + 2144) = 0;
    *(_DWORD *)(v33 + 2120) = 0;
    return 0;
  }
  v14 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 && *(_BYTE *)(v14 + 20) )
    v15 = (_DWORD *)(v14 + 4);
  else
    v15 = (_DWORD *)*((_QWORD *)a2 + 3);
  v16 = *((_BYTE *)this + 2144);
  *((_DWORD *)this + 530) = v13 + (v15[2] - *v15) * (v15[3] - v15[1]);
  if ( *((_BYTE *)a2 + 116) != v16 && v5 != *((_QWORD *)this + 2) )
  {
    CDDPDEV::FlushNoMutex(v12, v6, 0, 2u);
    return 0;
  }
  *((_DWORD *)this + 525) = *((_DWORD *)this + 524);
  v17 = *((_DWORD *)a2 + 24);
  if ( !v17 && (*((_DWORD *)v12 + 686) & 0x100) != 0 && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("Attempt to insert NULL allocation to the allocation list");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 28;
    v35 = (_QWORD *)WdLogNewEntry5_WdError();
    v35[3] = gCddImageInfo;
    v35[4] = (unsigned int)dword_14003E570;
    v35[5] = 215857758;
    WdLogGlobalForLineNumber = 28;
    __debugbreak();
    a4 = v44;
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 524); i = (unsigned int)(i + 1) )
  {
    if ( *((_DWORD *)this + 2 * i + 12) == v17 )
      goto LABEL_10;
  }
  if ( (_DWORD)i == 256 )
  {
    LODWORD(i) = -1;
  }
  else
  {
    *((_QWORD *)this + i + 6) = 0;
    *((_DWORD *)this + 2 * i + 12) = v17;
    *((_DWORD *)this + 2 * i + 13) = 0;
    *((_DWORD *)this + 524) = i + 1;
  }
LABEL_10:
  v19 = *((_DWORD *)a2 + 25);
  if ( !v19 && (*(_DWORD *)(*(_QWORD *)this + 2744LL) & 0x100) != 0 && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("Attempt to insert NULL allocation to the allocation list");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 28;
    v36 = (_QWORD *)WdLogNewEntry5_WdError();
    v36[3] = gCddImageInfo;
    v36[4] = (unsigned int)dword_14003E570;
    v36[5] = 215857758;
    WdLogGlobalForLineNumber = 28;
    __debugbreak();
    a4 = v44;
  }
  for ( j = 0; (unsigned int)j < *((_DWORD *)this + 524); j = (unsigned int)(j + 1) )
  {
    if ( *((_DWORD *)this + 2 * j + 12) == v19 )
    {
      *((_DWORD *)this + 2 * j + 13) |= 1u;
      goto LABEL_15;
    }
  }
  if ( (_DWORD)j == 256 )
  {
    LODWORD(j) = -1;
  }
  else
  {
    *((_QWORD *)this + j + 6) = 0;
    *((_DWORD *)this + 2 * j + 12) = v19;
    *((_DWORD *)this + 2 * j + 13) = 1;
    *((_DWORD *)this + 524) = j + 1;
  }
LABEL_15:
  if ( (_DWORD)i == -1 || (_DWORD)j == -1 )
  {
    if ( *((_DWORD *)this + 525) > 0x100u )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 90;
      v37 = (_QWORD *)WdLogNewEntry5_WdAssertion();
      v37[3] = gCddImageInfo;
      v37[4] = (unsigned int)dword_14003E570;
      v37[5] = 215857758;
      WdLogGlobalForLineNumber = 90;
    }
    v30 = *(_QWORD *)this;
    *((_DWORD *)this + 524) = *((_DWORD *)this + 525);
    if ( *(_DWORD *)(*(_QWORD *)(v30 + 12696) + 32LL) != *(_DWORD *)(*(_QWORD *)(v30 + 12696) + 16LL) )
    {
      if ( KeGetCurrentThread() == *(struct _KTHREAD **)(v30 + 2568) )
      {
        CDDPDEV::FlushGdiOutput((CDDPDEV *)v30, 0);
      }
      else if ( v43 && *((_BYTE *)v43 + 9) )
      {
        CCommandBufferMutex::EnableWorkerThreadAccess(v43);
        if ( KeGetCurrentIrql() )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 785;
          v38 = (_QWORD *)WdLogNewEntry5_WdAssertion();
          v38[3] = gCddImageInfo;
          v38[4] = (unsigned int)dword_14003E570;
          v38[5] = 215857758;
          WdLogGlobalForLineNumber = 785;
        }
        v31 = *(_QWORD *)(v30 + 5488);
        ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v31);
        *(_DWORD *)(v30 + 3648) = 2;
        CddIssueCommand(v30, 13);
        ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v31);
        CCommandBufferMutex::DisableWorkerThreadAccess(v43);
      }
      else
      {
        if ( KeGetCurrentIrql() )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 785;
          v39 = (_QWORD *)WdLogNewEntry5_WdAssertion();
          v39[3] = gCddImageInfo;
          v39[4] = (unsigned int)dword_14003E570;
          v39[5] = 215857758;
          WdLogGlobalForLineNumber = 785;
        }
        v32 = *(_QWORD *)(v30 + 5488);
        ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v32);
        *(_DWORD *)(v30 + 3648) = 2;
        CddIssueCommand(v30, 13);
        ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v32);
      }
    }
    v33 = *(_QWORD *)(v30 + 12696);
    if ( *(_DWORD *)(v33 + 32) != *(_DWORD *)(v33 + 16) )
      return 0;
    goto LABEL_53;
  }
  v21 = *((_QWORD *)this + 4);
  *(_DWORD *)v21 = 1;
  *(_DWORD *)(v21 + 4) = v11;
  *(_DWORD *)(v21 + 44) = j;
  *(_DWORD *)(v21 + 40) = i;
  *(_OWORD *)(v21 + 8) = *(_OWORD *)*((_QWORD *)a2 + 1);
  v22 = *(_OWORD *)*((_QWORD *)a2 + 3);
  *(_DWORD *)(v21 + 48) = a3;
  *(_QWORD *)(v21 + 56) = v21 + 80;
  *(_OWORD *)(v21 + 24) = v22;
  *(_WORD *)(v21 + 64) = *((_WORD *)a2 + 52);
  *(_WORD *)(v21 + 66) = *((_WORD *)a2 + 53);
  *(_DWORD *)(v21 + 68) = *((_DWORD *)a2 + 27);
  *(_DWORD *)(v21 + 72) = *((_DWORD *)a2 + 28);
  memmove((void *)(v21 + 80), a4, v8);
  *((_QWORD *)this + 4) += v11;
  *((_QWORD *)this + 5) = v21;
  *((_BYTE *)this + 2144) = *((_BYTE *)a2 + 116);
  *(_BYTE *)(*(_QWORD *)this + 2753LL) = 1;
  v23 = (void (__fastcall ***)(_QWORD, CHwCommandBuffer *, __int64, __int64, const struct tagPOINT *))*((_QWORD *)a2 + 11);
  if ( v23 )
  {
    v24 = **v23;
    if ( a3 > 8 )
      v24(v23, this, v21 + 24, 1, a5);
    else
      v24(v23, this, (__int64)v44, a3, a5);
  }
  v25 = (void (__fastcall ***)(_QWORD, CHwCommandBuffer *, _QWORD, _QWORD, _QWORD))*((_QWORD *)a2 + 10);
  if ( v25 )
    (**v25)(v25, this, 0, 0, 0);
  v26 = *(_QWORD *)this;
  memset(v42, 0, 48);
  LODWORD(v42[0]) = 2;
  if ( (*(unsigned int (**)(void))(v26 + 80))() )
    (*(void (__fastcall **)(__int64, _QWORD, _OWORD *))(v26 + 264))(3039, 0, v42);
  return 1;
}

```

## disassembly

```asm
0x14000f370  mov     [rsp+arg_8], rbx
0x14000f375  mov     [rsp+arg_18], r9
0x14000f37a  push    rbp
0x14000f37b  push    rsi
0x14000f37c  push    rdi
0x14000f37d  push    r12
0x14000f37f  push    r13
0x14000f381  push    r14
0x14000f383  push    r15
0x14000f385  sub     rsp, 60h
0x14000f389  mov     r11, [rcx+20h]
0x14000f38d  mov     ebp, r8d
0x14000f390  mov     r14, [rdx+20h]
0x14000f394  mov     r15d, r8d
0x14000f397  shl     ebp, 4
0x14000f39a  mov     rsi, rdx
0x14000f39d  mov     rbx, rcx
0x14000f3a0  mov     [rsp+98h+arg_0], r14
0x14000f3a8  lea     r12d, [rbp+50h]
0x14000f3ac  lea     rax, [r11+r12]
0x14000f3b0  mov     r13d, r12d
0x14000f3b3  cmp     rax, [rcx+18h]
0x14000f3b7  ja      loc_14000F5A9
0x14000f3bd  mov     r10, [rcx]
0x14000f3c0  mov     r8d, [rcx+848h]
0x14000f3c7  cmp     r8d, [r10+31A8h]
0x14000f3ce  ja      loc_14000F5A9
0x14000f3d4  mov     rcx, [rdx]
0x14000f3d7  test    rcx, rcx
0x14000f3da  jnz     loc_14000F64E
0x14000f3e0  mov     rcx, [rdx+18h]
0x14000f3e4  mov     edx, [rcx+0Ch]
0x14000f3e7  sub     edx, [rcx+4]
0x14000f3ea  mov     eax, [rcx]
0x14000f3ec  mov     ecx, [rcx+8]
0x14000f3ef  sub     ecx, eax
0x14000f3f1  movzx   eax, byte ptr [rbx+860h]
0x14000f3f8  imul    edx, ecx
0x14000f3fb  add     edx, r8d
0x14000f3fe  mov     [rbx+848h], edx
0x14000f404  cmp     [rsi+74h], al
0x14000f407  jnz     loc_14000F8B8
0x14000f40d  mov     eax, [rbx+830h]
0x14000f413  mov     [rbx+834h], eax
0x14000f419  mov     edi, [rsi+60h]
0x14000f41c  test    edi, edi
0x14000f41e  jz      loc_14000F8DD
0x14000f424  mov     ecx, [rbx+830h]
0x14000f42a  xor     r14d, r14d
0x14000f42d  cmp     r14d, ecx
0x14000f430  jnb     loc_14000F661
0x14000f436  cmp     [rbx+r14*8+30h], edi
0x14000f43b  jnz     loc_14000F96D
0x14000f441  mov     edi, [rsi+64h]
0x14000f444  test    edi, edi
0x14000f446  jz      loc_14000F975
0x14000f44c  mov     eax, [rbx+830h]
0x14000f452  xor     ecx, ecx
0x14000f454  cmp     ecx, eax
0x14000f456  jnb     loc_14000F68A
0x14000f45c  cmp     [rbx+rcx*8+30h], edi
0x14000f460  jnz     loc_14000FA07
0x14000f466  or      dword ptr [rbx+rcx*8+34h], 1
0x14000f46b  cmp     r14d, 0FFFFFFFFh
0x14000f46f  jz      loc_14000F6C8
0x14000f475  cmp     ecx, 0FFFFFFFFh
0x14000f478  jz      loc_14000F6C8
0x14000f47e  mov     rdi, [rbx+20h]
0x14000f482  mov     rdx, r9; Src
0x14000f485  mov     r8d, ebp; Size
0x14000f488  mov     dword ptr [rdi], 1
0x14000f48e  mov     [rdi+4], r12d
0x14000f492  mov     [rdi+2Ch], ecx
0x14000f495  lea     rcx, [rdi+50h]; void *
0x14000f499  mov     [rdi+28h], r14d
0x14000f49d  mov     rax, [rsi+8]
0x14000f4a1  movups  xmm0, xmmword ptr [rax]
0x14000f4a4  movups  xmmword ptr [rdi+8], xmm0
0x14000f4a8  mov     rax, [rsi+18h]
0x14000f4ac  movups  xmm0, xmmword ptr [rax]
0x14000f4af  mov     [rdi+30h], r15d
0x14000f4b3  mov     [rdi+38h], rcx
0x14000f4b7  movups  xmmword ptr [rdi+18h], xmm0
0x14000f4bb  movzx   eax, word ptr [rsi+68h]
0x14000f4bf  mov     [rdi+40h], ax
0x14000f4c3  movzx   eax, word ptr [rsi+6Ah]
0x14000f4c7  mov     [rdi+42h], ax
0x14000f4cb  mov     eax, [rsi+6Ch]
0x14000f4ce  mov     [rdi+44h], eax
0x14000f4d1  mov     eax, [rsi+70h]
0x14000f4d4  mov     [rdi+48h], eax
0x14000f4d7  call    memmove
0x14000f4dc  add     [rbx+20h], r13
0x14000f4e0  mov     [rbx+28h], rdi
0x14000f4e4  movzx   eax, byte ptr [rsi+74h]
0x14000f4e8  mov     [rbx+860h], al
0x14000f4ee  mov     rax, [rbx]
0x14000f4f1  mov     byte ptr [rax+0AC1h], 1
0x14000f4f8  mov     r10, [rsi+58h]
0x14000f4fc  test    r10, r10
0x14000f4ff  jz      short loc_14000F537
0x14000f501  mov     rax, [r10]
0x14000f504  mov     rdx, rbx
0x14000f507  mov     r11, [rax]
0x14000f50a  cmp     r15d, 8
0x14000f50e  ja      loc_14000F7FC
0x14000f514  mov     rax, [rsp+98h+arg_20]
0x14000f51c  mov     r9d, r15d
0x14000f51f  mov     r8, [rsp+98h+arg_18]
0x14000f527  mov     [rsp+98h+var_78], rax
0x14000f52c  mov     rcx, r10
0x14000f52f  mov     rax, r11
0x14000f532  call    _guard_dispatch_icall
0x14000f537  mov     rcx, [rsi+50h]
0x14000f53b  test    rcx, rcx
0x14000f53e  jz      short loc_14000F55D
0x14000f540  mov     rax, [rcx]
0x14000f543  xor     r9d, r9d
0x14000f546  xor     r8d, r8d
0x14000f549  mov     [rsp+98h+var_78], 0
0x14000f552  mov     rdx, rbx
0x14000f555  mov     rax, [rax]
0x14000f558  call    _guard_dispatch_icall
0x14000f55d  mov     rbx, [rbx]
0x14000f560  xorps   xmm0, xmm0
0x14000f563  movups  [rsp+98h+var_68], xmm0
0x14000f568  mov     dword ptr [rsp+98h+var_68], 2
0x14000f570  movups  [rsp+98h+var_58], xmm0
0x14000f575  movups  [rsp+98h+var_48], xmm0
0x14000f57a  mov     rax, [rbx+50h]
0x14000f57e  call    _guard_dispatch_icall
0x14000f583  test    eax, eax
0x14000f585  jnz     loc_14000F880
0x14000f58b  mov     eax, 1
0x14000f590  mov     rbx, [rsp+98h+arg_8]
0x14000f598  add     rsp, 60h
0x14000f59c  pop     r15
0x14000f59e  pop     r14
0x14000f5a0  pop     r13
0x14000f5a2  pop     r12
0x14000f5a4  pop     rdi
0x14000f5a5  pop     rsi
0x14000f5a6  pop     rbp
0x14000f5a7  retn
0x14000f5a9  mov     rdi, [rcx]
0x14000f5ac  mov     rax, [rdi+3198h]
0x14000f5b3  mov     ecx, [rax+10h]
0x14000f5b6  cmp     [rax+20h], ecx
0x14000f5b9  jz      loc_14000F868
0x14000f5bf  mov     rax, gs:188h
0x14000f5c8  cmp     rax, [rdi+0A08h]
0x14000f5cf  jz      loc_14000F8AC
0x14000f5d5  test    r14, r14
0x14000f5d8  jz      loc_14000F818
0x14000f5de  cmp     byte ptr [r14+9], 0
0x14000f5e3  jz      loc_14000F818
0x14000f5e9  mov     rcx, r14; this
0x14000f5ec  call    ?EnableWorkerThreadAccess@CCommandBufferMutex@@QEAAXXZ; CCommandBufferMutex::EnableWorkerThreadAccess(void)
0x14000f5f1  call    cs:__imp_KeGetCurrentIrql
0x14000f5f8  nop     dword ptr [rax+rax+00h]
0x14000f5fd  test    al, al
0x14000f5ff  jnz     loc_14000FB07
0x14000f605  mov     rbx, [rdi+1570h]
0x14000f60c  mov     rcx, rbx
0x14000f60f  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000f616  nop     dword ptr [rax+rax+00h]
0x14000f61b  mov     edx, 0Dh
0x14000f620  mov     dword ptr [rdi+0E40h], 2
0x14000f62a  mov     rcx, rdi
0x14000f62d  call    ?CddIssueCommand@@YAJPEAUCDDPDEV@@W4_WORKERTHREAD_COMMAND@@@Z; CddIssueCommand(CDDPDEV *,_WORKERTHREAD_COMMAND)
0x14000f632  mov     rcx, rbx
0x14000f635  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000f63c  nop     dword ptr [rax+rax+00h]
0x14000f641  mov     rcx, r14; this
0x14000f644  call    ?DisableWorkerThreadAccess@CCommandBufferMutex@@QEAAXXZ; CCommandBufferMutex::DisableWorkerThreadAccess(void)
0x14000f649  jmp     loc_14000F868
0x14000f64e  cmp     byte ptr [rcx+14h], 0
0x14000f652  jz      loc_14000F3E0
0x14000f658  add     rcx, 4
0x14000f65c  jmp     loc_14000F3E4
0x14000f661  cmp     r14d, 100h
0x14000f668  jz      short loc_14000F6B3
0x14000f66a  xor     ecx, ecx
0x14000f66c  lea     eax, [r14+1]
0x14000f670  mov     [rbx+r14*8+30h], rcx
0x14000f675  mov     [rbx+r14*8+30h], edi
0x14000f67a  mov     [rbx+r14*8+34h], ecx
0x14000f67f  mov     [rbx+830h], eax
0x14000f685  jmp     loc_14000F441
0x14000f68a  cmp     ecx, 100h
0x14000f690  jz      short loc_14000F6BE
0x14000f692  xor     edx, edx
0x14000f694  lea     eax, [rcx+1]
0x14000f697  mov     [rbx+rcx*8+30h], rdx
0x14000f69c  mov     [rbx+rcx*8+30h], edi
0x14000f6a0  mov     dword ptr [rbx+rcx*8+34h], 1
0x14000f6a8  mov     [rbx+830h], eax
0x14000f6ae  jmp     loc_14000F46B
0x14000f6b3  mov     r14d, 0FFFFFFFFh
0x14000f6b9  jmp     loc_14000F441
0x14000f6be  mov     ecx, 0FFFFFFFFh
0x14000f6c3  jmp     loc_14000F46B
0x14000f6c8  cmp     dword ptr [rbx+834h], 100h
0x14000f6d2  ja      loc_14000FA0E
0x14000f6d8  mov     eax, [rbx+834h]
0x14000f6de  mov     rdi, [rbx]
0x14000f6e1  mov     [rbx+830h], eax
0x14000f6e7  mov     rax, [rdi+3198h]
0x14000f6ee  mov     ecx, [rax+10h]
0x14000f6f1  cmp     [rax+20h], ecx
0x14000f6f4  jz      loc_14000F7D5
0x14000f6fa  mov     rax, gs:188h
0x14000f703  cmp     rax, [rdi+0A08h]
0x14000f70a  jz      loc_14000F89D
0x14000f710  mov     rsi, [rsp+98h+arg_0]
0x14000f718  test    rsi, rsi
0x14000f71b  jz      short loc_14000F785
0x14000f71d  cmp     byte ptr [rsi+9], 0
0x14000f721  jz      short loc_14000F785
0x14000f723  mov     rcx, rsi; this
0x14000f726  call    ?EnableWorkerThreadAccess@CCommandBufferMutex@@QEAAXXZ; CCommandBufferMutex::EnableWorkerThreadAccess(void)
0x14000f72b  call    cs:__imp_KeGetCurrentIrql
0x14000f732  nop     dword ptr [rax+rax+00h]
0x14000f737  test    al, al
0x14000f739  jnz     loc_14000FA61
0x14000f73f  mov     rbx, [rdi+1570h]
0x14000f746  mov     rcx, rbx
0x14000f749  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000f750  nop     dword ptr [rax+rax+00h]
0x14000f755  mov     edx, 0Dh
0x14000f75a  mov     dword ptr [rdi+0E40h], 2
0x14000f764  mov     rcx, rdi
0x14000f767  call    ?CddIssueCommand@@YAJPEAUCDDPDEV@@W4_WORKERTHREAD_COMMAND@@@Z; CddIssueCommand(CDDPDEV *,_WORKERTHREAD_COMMAND)
0x14000f76c  mov     rcx, rbx
0x14000f76f  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000f776  nop     dword ptr [rax+rax+00h]
0x14000f77b  mov     rcx, rsi; this
0x14000f77e  call    ?DisableWorkerThreadAccess@CCommandBufferMutex@@QEAAXXZ; CCommandBufferMutex::DisableWorkerThreadAccess(void)
0x14000f783  jmp     short loc_14000F7D5
0x14000f785  call    cs:__imp_KeGetCurrentIrql
0x14000f78c  nop     dword ptr [rax+rax+00h]
0x14000f791  test    al, al
0x14000f793  jnz     loc_14000FAB4
0x14000f799  mov     rbx, [rdi+1570h]
0x14000f7a0  mov     rcx, rbx
0x14000f7a3  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000f7aa  nop     dword ptr [rax+rax+00h]
0x14000f7af  mov     edx, 0Dh
0x14000f7b4  mov     dword ptr [rdi+0E40h], 2
0x14000f7be  mov     rcx, rdi
0x14000f7c1  call    ?CddIssueCommand@@YAJPEAUCDDPDEV@@W4_WORKERTHREAD_COMMAND@@@Z; CddIssueCommand(CDDPDEV *,_WORKERTHREAD_COMMAND)
0x14000f7c6  mov     rcx, rbx
0x14000f7c9  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000f7d0  nop     dword ptr [rax+rax+00h]
0x14000f7d5  mov     rdx, [rdi+3198h]
0x14000f7dc  mov     ecx, [rdx+10h]
0x14000f7df  cmp     [rdx+20h], ecx
0x14000f7e2  jnz     short loc_14000F7F5
0x14000f7e4  mov     byte ptr [rdx+860h], 0
0x14000f7eb  mov     dword ptr [rdx+848h], 0
0x14000f7f5  xor     eax, eax
0x14000f7f7  jmp     loc_14000F590
0x14000f7fc  mov     rcx, [rsp+98h+arg_20]
0x14000f804  lea     r8, [rdi+18h]
0x14000f808  mov     [rsp+98h+var_78], rcx
0x14000f80d  mov     r9d, 1
0x14000f813  jmp     loc_14000F52C
0x14000f818  call    cs:__imp_KeGetCurrentIrql
0x14000f81f  nop     dword ptr [rax+rax+00h]
0x14000f824  test    al, al
0x14000f826  jnz     loc_14000FB5A
0x14000f82c  mov     rbx, [rdi+1570h]
0x14000f833  mov     rcx, rbx
0x14000f836  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000f83d  nop     dword ptr [rax+rax+00h]
0x14000f842  mov     edx, 0Dh
0x14000f847  mov     dword ptr [rdi+0E40h], 2
0x14000f851  mov     rcx, rdi
0x14000f854  call    ?CddIssueCommand@@YAJPEAUCDDPDEV@@W4_WORKERTHREAD_COMMAND@@@Z; CddIssueCommand(CDDPDEV *,_WORKERTHREAD_COMMAND)
0x14000f859  mov     rcx, rbx
0x14000f85c  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000f863  nop     dword ptr [rax+rax+00h]
0x14000f868  mov     rdx, [rdi+3198h]
0x14000f86f  mov     ecx, [rdx+10h]
0x14000f872  cmp     [rdx+20h], ecx
0x14000f875  jnz     loc_14000F7F5
0x14000f87b  jmp     loc_14000F7E4
0x14000f880  mov     rax, [rbx+108h]
0x14000f887  lea     r8, [rsp+98h+var_68]
0x14000f88c  xor     edx, edx
0x14000f88e  mov     ecx, 0BDFh
0x14000f893  call    _guard_dispatch_icall
0x14000f898  jmp     loc_14000F58B
0x14000f89d  xor     edx, edx; unsigned int
0x14000f89f  mov     rcx, rdi; this
0x14000f8a2  call    ?FlushGdiOutput@CDDPDEV@@QEAAXI@Z; CDDPDEV::FlushGdiOutput(uint)
0x14000f8a7  jmp     loc_14000F7D5
0x14000f8ac  xor     edx, edx; unsigned int
0x14000f8ae  mov     rcx, rdi; this
0x14000f8b1  call    ?FlushGdiOutput@CDDPDEV@@QEAAXI@Z; CDDPDEV::FlushGdiOutput(uint)
  ... truncated ...
```
