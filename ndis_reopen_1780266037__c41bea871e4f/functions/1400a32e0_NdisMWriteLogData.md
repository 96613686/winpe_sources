# NdisMWriteLogData

- ea: `0x1400a32e0`
- end: `0x1400a34e9`
- name: `NdisMWriteLogData`
- size: `521`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE LogHandle, PVOID LogBuffer, UINT LogBufferSize)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400a32e0`
- `0x1400eb4c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a33dd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a3421`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a33dd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a3421`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400a34c9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400a34c9`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400a3307`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400a3307`
- `ntoskrnl!IofCompleteRequest` at `0x1400a349f`
- `ntoskrnl!IofCompleteRequest` at `0x1400a349f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400a3317`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400a3317`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400a34b6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400a34b6`

## pseudocode

```c
NDIS_STATUS __stdcall NdisMWriteLogData(NDIS_HANDLE LogHandle, PVOID LogBuffer, UINT LogBufferSize)
{
  UINT v6; // r14d
  __int64 v7; // rax
  __int64 v8; // r14
  char *v9; // rcx
  NDIS_STATUS v10; // ebp
  char *v11; // rdx
  size_t v12; // r8
  unsigned int v13; // edx
  unsigned int v14; // eax
  unsigned int v15; // ecx
  __int64 v16; // rbx
  struct _MDL *v17; // rcx
  unsigned int ByteCount; // esi
  __int16 v19; // dx
  char *v20; // rcx
  size_t v21; // r8
  char *v22; // rdx
  char *MappedSystemVa; // r14
  __int64 v24; // rcx
  unsigned int v25; // eax
  unsigned int v26; // ecx
  KIRQL Irql; // [rsp+90h] [rbp+18h] BYREF

  Irql = 0;
  IoAcquireCancelSpinLock(&Irql);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)LogHandle + 1);
  v6 = *((_DWORD *)LogHandle + 6);
  if ( LogBufferSize > v6 )
  {
    v10 = -2147483643;
    goto LABEL_31;
  }
  v7 = *((unsigned int *)LogHandle + 8);
  v8 = v6 - (unsigned int)v7;
  v9 = (char *)LogHandle + v7 + 40;
  v10 = 0;
  v11 = (char *)LogBuffer;
  if ( LogBufferSize > (unsigned int)v8 )
  {
    memmove(v9, LogBuffer, (unsigned int)v8);
    v11 = (char *)LogBuffer + v8;
    v12 = LogBufferSize - (unsigned int)v8;
    v9 = (char *)LogHandle + 40;
  }
  else
  {
    v12 = LogBufferSize;
  }
  memmove(v9, v11, v12);
  *((_DWORD *)LogHandle + 7) += LogBufferSize;
  v13 = *((_DWORD *)LogHandle + 7);
  v14 = *((_DWORD *)LogHandle + 6);
  if ( v13 > v14 )
  {
    *((_DWORD *)LogHandle + 7) = v14;
    v13 = v14;
  }
  *((_DWORD *)LogHandle + 8) += LogBufferSize;
  v15 = *((_DWORD *)LogHandle + 8);
  if ( v15 >= v14 )
  {
    v15 -= v14;
    *((_DWORD *)LogHandle + 8) = v15;
  }
  if ( v13 == v14 )
    *((_DWORD *)LogHandle + 9) = v15;
  v16 = *((_QWORD *)LogHandle + 2);
  if ( v16 )
  {
    *((_QWORD *)LogHandle + 2) = 0;
    v17 = *(struct _MDL **)(v16 + 8);
    ByteCount = v17->ByteCount;
    if ( ByteCount > v13 )
      ByteCount = v13;
    v19 = v17->MdlFlags & 5;
    if ( v14 - *((_DWORD *)LogHandle + 9) < ByteCount )
    {
      if ( v19 )
        MappedSystemVa = (char *)v17->MappedSystemVa;
      else
        MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v17, 0, MmCached, 0, 0, 0x40000000u);
      if ( MappedSystemVa )
      {
        memmove(
          MappedSystemVa,
          (char *)LogHandle + *((unsigned int *)LogHandle + 9) + 40,
          (unsigned int)(*((_DWORD *)LogHandle + 6) - *((_DWORD *)LogHandle + 9)));
        v22 = (char *)LogHandle + 40;
        v24 = *((unsigned int *)LogHandle + 6);
        v21 = ByteCount + *((_DWORD *)LogHandle + 9) - (_DWORD)v24;
        v20 = &MappedSystemVa[v24 - *((unsigned int *)LogHandle + 9)];
        goto LABEL_25;
      }
    }
    else
    {
      if ( v19 )
        v20 = (char *)v17->MappedSystemVa;
      else
        v20 = (char *)MmMapLockedPagesSpecifyCache(v17, 0, MmCached, 0, 0, 0x40000000u);
      if ( v20 )
      {
        v21 = ByteCount;
        v22 = (char *)LogHandle + *((unsigned int *)LogHandle + 9) + 40;
LABEL_25:
        memmove(v20, v22, v21);
LABEL_27:
        *((_DWORD *)LogHandle + 9) += ByteCount;
        *((_DWORD *)LogHandle + 7) -= ByteCount;
        v25 = *((_DWORD *)LogHandle + 9);
        v26 = *((_DWORD *)LogHandle + 6);
        if ( v25 >= v26 )
          *((_DWORD *)LogHandle + 9) = v25 - v26;
        *(_QWORD *)(v16 + 56) = ByteCount;
        _InterlockedExchange64((volatile __int64 *)(v16 + 104), 0);
        *(_DWORD *)(v16 + 48) = 0;
        IofCompleteRequest((PIRP)v16, 2);
        goto LABEL_31;
      }
    }
    v10 = -1073741670;
    goto LABEL_27;
  }
LABEL_31:
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)LogHandle + 1);
  IoReleaseCancelSpinLock(Irql);
  return v10;
}

```

## disassembly

```asm
0x1400a32e0  mov     rax, rsp
0x1400a32e3  push    rbx
0x1400a32e4  push    rbp
0x1400a32e5  push    rsi
0x1400a32e6  push    rdi
0x1400a32e7  push    r12
0x1400a32e9  push    r13
0x1400a32eb  push    r14
0x1400a32ed  push    r15
0x1400a32ef  sub     rsp, 38h
0x1400a32f3  mov     rdi, rcx
0x1400a32f6  mov     esi, r8d
0x1400a32f9  xor     r13d, r13d
0x1400a32fc  lea     rcx, [rax+18h]; Irql
0x1400a3300  mov     [rax+18h], r13b
0x1400a3304  mov     r15, rdx
0x1400a3307  call    cs:__imp_IoAcquireCancelSpinLock
0x1400a330e  nop     dword ptr [rax+rax+00h]
0x1400a3313  lea     rcx, [rdi+8]; SpinLock
0x1400a3317  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400a331e  nop     dword ptr [rax+rax+00h]
0x1400a3323  mov     r14d, [rdi+18h]
0x1400a3327  cmp     esi, r14d
0x1400a332a  ja      loc_1400A34AD
0x1400a3330  mov     eax, [rdi+20h]
0x1400a3333  lea     rcx, [rdi+28h]
0x1400a3337  sub     r14d, eax
0x1400a333a  add     rcx, rax; void *
0x1400a333d  mov     ebp, r13d
0x1400a3340  mov     rdx, r15; Src
0x1400a3343  cmp     esi, r14d
0x1400a3346  ja      short loc_1400A334D
0x1400a3348  mov     r8d, esi
0x1400a334b  jmp     short loc_1400A3363
0x1400a334d  mov     r8d, r14d; Size
0x1400a3350  call    memmove
0x1400a3355  mov     r8d, esi
0x1400a3358  lea     rdx, [r14+r15]; Src
0x1400a335c  sub     r8d, r14d; Size
0x1400a335f  lea     rcx, [rdi+28h]; void *
0x1400a3363  call    memmove
0x1400a3368  add     [rdi+1Ch], esi
0x1400a336b  mov     edx, [rdi+1Ch]
0x1400a336e  mov     eax, [rdi+18h]
0x1400a3371  cmp     edx, eax
0x1400a3373  jbe     short loc_1400A337A
0x1400a3375  mov     [rdi+1Ch], eax
0x1400a3378  mov     edx, eax
0x1400a337a  add     [rdi+20h], esi
0x1400a337d  mov     ecx, [rdi+20h]
0x1400a3380  cmp     ecx, eax
0x1400a3382  jb      short loc_1400A3389
0x1400a3384  sub     ecx, eax
0x1400a3386  mov     [rdi+20h], ecx
0x1400a3389  cmp     edx, eax
0x1400a338b  jnz     short loc_1400A3390
0x1400a338d  mov     [rdi+24h], ecx
0x1400a3390  mov     rbx, [rdi+10h]
0x1400a3394  test    rbx, rbx
0x1400a3397  jz      loc_1400A34B2
0x1400a339d  mov     [rdi+10h], r13
0x1400a33a1  mov     rcx, [rbx+8]; MemoryDescriptorList
0x1400a33a5  mov     esi, [rcx+28h]
0x1400a33a8  cmp     esi, edx
0x1400a33aa  cmova   esi, edx
0x1400a33ad  movzx   edx, word ptr [rcx+0Ah]
0x1400a33b1  sub     eax, [rdi+24h]
0x1400a33b4  and     dx, 5
0x1400a33b8  cmp     eax, esi
0x1400a33ba  jb      short loc_1400A3400
0x1400a33bc  test    dx, dx
0x1400a33bf  jz      short loc_1400A33C7
0x1400a33c1  mov     rcx, [rcx+18h]
0x1400a33c5  jmp     short loc_1400A33EC
0x1400a33c7  xor     r9d, r9d; RequestedAddress
0x1400a33ca  mov     [rsp+78h+Priority], 40000000h; Priority
0x1400a33d2  xor     edx, edx; AccessMode
0x1400a33d4  mov     [rsp+78h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x1400a33d9  lea     r8d, [r9+1]; CacheType
0x1400a33dd  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400a33e4  nop     dword ptr [rax+rax+00h]
0x1400a33e9  mov     rcx, rax
0x1400a33ec  test    rcx, rcx
0x1400a33ef  jz      short loc_1400A346F
0x1400a33f1  mov     edx, [rdi+24h]
0x1400a33f4  add     rdx, 28h ; '('
0x1400a33f8  mov     r8d, esi
0x1400a33fb  add     rdx, rdi
0x1400a33fe  jmp     short loc_1400A3468
0x1400a3400  test    dx, dx
0x1400a3403  jz      short loc_1400A340B
0x1400a3405  mov     r14, [rcx+18h]
0x1400a3409  jmp     short loc_1400A3430
0x1400a340b  xor     r9d, r9d; RequestedAddress
0x1400a340e  mov     [rsp+78h+Priority], 40000000h; Priority
0x1400a3416  xor     edx, edx; AccessMode
0x1400a3418  mov     [rsp+78h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x1400a341d  lea     r8d, [r9+1]; CacheType
0x1400a3421  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400a3428  nop     dword ptr [rax+rax+00h]
0x1400a342d  mov     r14, rax
0x1400a3430  test    r14, r14
0x1400a3433  jz      short loc_1400A346F
0x1400a3435  mov     ecx, [rdi+24h]
0x1400a3438  mov     r8d, [rdi+18h]
0x1400a343c  sub     r8d, ecx; Size
0x1400a343f  lea     rdx, [rcx+28h]
0x1400a3443  mov     rcx, r14; void *
0x1400a3446  add     rdx, rdi; Src
0x1400a3449  call    memmove
0x1400a344e  mov     r9d, [rdi+24h]
0x1400a3452  lea     rdx, [rdi+28h]; Src
0x1400a3456  mov     ecx, [rdi+18h]
0x1400a3459  mov     r8d, r9d
0x1400a345c  sub     r8d, ecx
0x1400a345f  sub     rcx, r9
0x1400a3462  add     r8d, esi; Size
0x1400a3465  add     rcx, r14; void *
0x1400a3468  call    memmove
0x1400a346d  jmp     short loc_1400A3474
0x1400a346f  mov     ebp, 0C000009Ah
0x1400a3474  add     [rdi+24h], esi
0x1400a3477  sub     [rdi+1Ch], esi
0x1400a347a  mov     eax, [rdi+24h]
0x1400a347d  mov     ecx, [rdi+18h]
0x1400a3480  cmp     eax, ecx
0x1400a3482  jb      short loc_1400A3489
0x1400a3484  sub     eax, ecx
0x1400a3486  mov     [rdi+24h], eax
0x1400a3489  mov     eax, esi
0x1400a348b  mov     dl, 2; PriorityBoost
0x1400a348d  mov     [rbx+38h], rax
0x1400a3491  mov     rcx, rbx; Irp
0x1400a3494  mov     rax, r13
0x1400a3497  xchg    rax, [rbx+68h]
0x1400a349b  mov     [rbx+30h], r13d
0x1400a349f  call    cs:__imp_IofCompleteRequest
0x1400a34a6  nop     dword ptr [rax+rax+00h]
0x1400a34ab  jmp     short loc_1400A34B2
0x1400a34ad  mov     ebp, 80000005h
0x1400a34b2  lea     rcx, [rdi+8]; SpinLock
0x1400a34b6  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400a34bd  nop     dword ptr [rax+rax+00h]
0x1400a34c2  mov     cl, [rsp+78h+Irql]; Irql
0x1400a34c9  call    cs:__imp_IoReleaseCancelSpinLock
0x1400a34d0  nop     dword ptr [rax+rax+00h]
0x1400a34d5  mov     eax, ebp
0x1400a34d7  add     rsp, 38h
0x1400a34db  pop     r15
0x1400a34dd  pop     r14
0x1400a34df  pop     r13
0x1400a34e1  pop     r12
0x1400a34e3  pop     rdi
0x1400a34e4  pop     rsi
0x1400a34e5  pop     rbp
0x1400a34e6  pop     rbx
0x1400a34e7  retn
```
