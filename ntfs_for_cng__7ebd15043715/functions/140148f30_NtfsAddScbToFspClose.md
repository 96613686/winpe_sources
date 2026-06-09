# NtfsAddScbToFspClose

- ea: `0x140148f30`
- end: `0x1401493ee`
- name: `NtfsAddScbToFspClose`
- size: `1214`
- prototype: `char __fastcall(__int64, _QWORD *, char, char, _QWORD *)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401289c0`
- `0x140128d50`
- `0x14012a0f0`
- `0x14014a930`
- `0x1401a2cb0`
- `0x14029c1b4`

## callees

- `0x1400054e8`
- `0x140023250`
- `0x140059250`
- `0x1400596c0`
- `0x140148f30`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x14014925d`
- `ntoskrnl!ExQueueWorkItem` at `0x14014925d`
- `ntoskrnl!IoSetActivityIdThread` at `0x1401490a1`
- `ntoskrnl!IoSetActivityIdThread` at `0x1401490a1`
- `ntoskrnl!IoClearActivityIdThread` at `0x14014926c`
- `ntoskrnl!IoClearActivityIdThread` at `0x14014926c`
- `ntoskrnl!IoTransferActivityId` at `0x140149398`
- `ntoskrnl!IoTransferActivityId` at `0x140149398`
- `ntoskrnl!EtwActivityIdControl` at `0x140149381`
- `ntoskrnl!EtwActivityIdControl` at `0x140149381`
- `ntoskrnl!IoGetActivityIdThread` at `0x140149086`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401490e1`
- `ntoskrnl!IoGetActivityIdThread` at `0x140149086`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401490e1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140148f7a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140148f7a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140149199`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14014923c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140149199`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14014923c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14014911b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401492fb`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14014911b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401492fb`
- `ntoskrnl!ExAcquireFastMutex` at `0x140148ff4`
- `ntoskrnl!ExAcquireFastMutex` at `0x140148ff4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140149068`
- `ntoskrnl!ExReleaseFastMutex` at `0x140149068`

## pseudocode

```c
char __fastcall NtfsAddScbToFspClose(__int64 a1, _QWORD *a2, char a3, char a4, _QWORD *a5)
{
  _QWORD *v5; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // r15
  __int64 v11; // rcx
  _QWORD *v12; // rcx
  __int64 *v13; // rcx
  __int64 v14; // rdx
  __int64 **v15; // rax
  __int64 v16; // rax
  __int64 **v17; // rdx
  _QWORD *ActivityIdThread; // rax
  char *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  char v22; // r12
  __int64 v23; // r13
  __int64 v24; // rsi
  _QWORD *v25; // rcx
  _QWORD *v26; // rax
  char *v27; // r12
  struct _FAST_MUTEX *v28; // rdi
  __int64 v29; // rcx
  __int64 v30; // r9
  struct _FAST_MUTEX *v31; // r14
  _QWORD *v32; // rdx
  _QWORD *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rax
  bool v36; // zf
  _QWORD *v37; // rcx
  __int64 v38; // rax
  __int64 v40; // [rsp+20h] [rbp-60h]
  __int128 v42; // [rsp+38h] [rbp-48h] BYREF
  __int64 v43; // [rsp+48h] [rbp-38h]
  __int128 v44; // [rsp+50h] [rbp-30h] BYREF
  __int64 v45; // [rsp+60h] [rbp-20h]

  v5 = a5;
  v43 = 0;
  v42 = 0;
  if ( a5 || (v9 = ExAllocateFromLookasideListEx(&NtfsCloseEntryLookasideList), (v5 = v9) != 0) )
  {
    memset(v5, 0, 0x58u);
    v5[1] = v5;
    v10 = v5 + 2;
    *v5 = v5;
    v5[3] = v5 + 2;
    v5[2] = v5 + 2;
    v5[4] = a2;
    *((_BYTE *)v5 + 56) = 5;
    NtfsIncrementCloseCounts(v11, (__int64)a2, 1, 0);
    if ( a4 )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2[23] + 104LL) + 8LL));
      v13 = a2 + 21;
      v14 = a2[21];
      if ( v14 != a2[23] + 64LL )
      {
        if ( *(__int64 **)(v14 + 8) != v13
          || (v15 = (__int64 **)a2[22], *v15 != v13)
          || (*v15 = (__int64 *)v14,
              *(_QWORD *)(v14 + 8) = v15,
              v16 = a2[23] + 64LL,
              v17 = *(__int64 ***)(a2[23] + 72LL),
              *v17 != (__int64 *)v16) )
        {
LABEL_8:
          __fastfail(3u);
        }
        *v13 = v16;
        a2[22] = v17;
        *v17 = v13;
        *(_QWORD *)(v16 + 8) = v13;
      }
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2[23] + 104LL) + 8LL));
    }
    if ( a1 && (v12 = *(_QWORD **)(a1 + 120)) != 0 )
    {
      *((_QWORD *)&v42 + 1) = *v12;
      v43 = v12[1];
      v19 = (char *)&v42 + 8;
    }
    else
    {
      ActivityIdThread = (_QWORD *)IoGetActivityIdThread(v12);
      if ( ActivityIdThread )
      {
        *((_QWORD *)&v42 + 1) = *ActivityIdThread;
        v19 = (char *)&v42 + 8;
        v43 = ActivityIdThread[1];
      }
      else
      {
        v19 = 0;
      }
    }
    v20 = IoSetActivityIdThread(v19);
    v21 = v5[4];
    v22 = 0;
    v23 = v20;
    v45 = 0;
    v44 = 0;
    v24 = *(_QWORD *)(v21 + 192);
    if ( a1 )
    {
      v25 = *(_QWORD **)(a1 + 120);
      if ( v25 )
      {
        *((_QWORD *)&v44 + 1) = *v25;
        v45 = v25[1];
        *(_QWORD *)&v44 = (char *)&v44 + 8;
        v27 = (char *)&v44 + 8;
      }
      else
      {
        v26 = (_QWORD *)IoGetActivityIdThread(0);
        if ( v26 )
        {
          v27 = (char *)&v44 + 8;
          *((_QWORD *)&v44 + 1) = *v26;
          v45 = v26[1];
        }
        else
        {
          v27 = 0;
        }
        *(_QWORD *)&v44 = v27;
      }
      if ( v27 )
      {
        EtwActivityIdControl(3u, (LPGUID)(v5 + 9));
        v5[8] = v5 + 9;
        IoTransferActivityId(v27, v5[8]);
      }
      else
      {
        v5[8] = 0;
      }
      v28 = (struct _FAST_MUTEX *)(v24 + 8456);
      _InterlockedIncrement((volatile signed __int32 *)(v24 + 4904));
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v24 + 8456));
      if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
      {
        LODWORD(v40) = 2;
        McTemplateK0pq_EtwWriteTransfer(
          v29,
          (const EVENT_DESCRIPTOR *)WORKITEM_QUEUE,
          *(const GUID **)(a1 + 120),
          v30,
          v40);
      }
      v31 = (struct _FAST_MUTEX *)(v24 + 8456);
      v22 = 0;
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)(v24 + 4904));
      v28 = (struct _FAST_MUTEX *)(v24 + 8456);
      v31 = (struct _FAST_MUTEX *)(v24 + 8456);
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v24 + 8456));
    }
    if ( a3 )
    {
      v33 = *(_QWORD **)(v24 + 8448);
      if ( *v33 != v24 + 8440 )
        goto LABEL_8;
      *v5 = v24 + 8440;
      v5[1] = v33;
      *v33 = v5;
      *(_QWORD *)(v24 + 8448) = v5;
      v34 = *(_QWORD *)(v5[4] + 184LL);
      v35 = *(_QWORD *)(v34 + 272);
      if ( v35 )
      {
        v37 = *(_QWORD **)(v35 + 24);
        v38 = v35 + 16;
        if ( *v37 != v38 )
          goto LABEL_8;
        *v10 = v38;
        v5[3] = v37;
        *v37 = v10;
        *(_QWORD *)(v38 + 8) = v10;
      }
      else
      {
        *(_QWORD *)(v34 + 272) = v5;
      }
      if ( ++*(_DWORD *)(v24 + 8428) > *(_DWORD *)(v24 + 8432) )
        *(_DWORD *)(v24 + 8432) = *(_DWORD *)(v24 + 8428);
      ++*(_DWORD *)(*(_QWORD *)(v5[4] + 184LL) + 268LL);
      if ( *(_DWORD *)(v24 + 8428) > (unsigned int)NtfsMaxDelayCloseCount )
      {
        v36 = *(_BYTE *)(v24 + 8416) == 0;
        *(_BYTE *)(v24 + 8418) = 1;
        if ( v36 )
        {
          *(_BYTE *)(v24 + 8416) = 1;
          v22 = 1;
        }
      }
    }
    else
    {
      v32 = *(_QWORD **)(v24 + 8408);
      if ( *v32 != v24 + 8400 )
        goto LABEL_8;
      *v5 = v24 + 8400;
      v5[1] = v32;
      *v32 = v5;
      *(_QWORD *)(v24 + 8408) = v5;
      if ( ++*(_DWORD *)(v24 + 8420) > *(_DWORD *)(v24 + 8424) )
        *(_DWORD *)(v24 + 8424) = *(_DWORD *)(v24 + 8420);
      if ( !*(_BYTE *)(v24 + 8416) )
      {
        *(_BYTE *)(v24 + 8416) = 1;
        KeReleaseGuardedMutex(v31);
        goto LABEL_38;
      }
    }
    KeReleaseGuardedMutex(v28);
    if ( !v22 )
    {
LABEL_39:
      IoClearActivityIdThread(v23);
      LOBYTE(v9) = 1;
      return (char)v9;
    }
LABEL_38:
    _InterlockedIncrement((volatile signed __int32 *)(v24 + 284));
    ExQueueWorkItem((PWORK_QUEUE_ITEM)(v24 + 8368), CriticalWorkQueue);
    goto LABEL_39;
  }
  return (char)v9;
}

```

## disassembly

```asm
0x140148f30  push    rbp
0x140148f32  push    rbx
0x140148f33  push    rsi
0x140148f34  push    rdi
0x140148f35  push    r14
0x140148f37  mov     rbp, rsp
0x140148f3a  sub     rsp, 80h
0x140148f41  mov     rax, cs:__security_cookie
0x140148f48  xor     rax, rsp
0x140148f4b  mov     [rbp+var_18], rax
0x140148f4f  mov     rbx, [rbp+arg_20]
0x140148f53  xor     eax, eax
0x140148f55  mov     [rbp+var_50], r8b
0x140148f59  xorps   xmm0, xmm0
0x140148f5c  mov     [rbp+var_38], rax
0x140148f60  movzx   esi, r9b
0x140148f64  mov     rdi, rdx
0x140148f67  mov     r14, rcx
0x140148f6a  movups  [rbp+var_48], xmm0
0x140148f6e  test    rbx, rbx
0x140148f71  jnz     short loc_140148F92
0x140148f73  lea     rcx, NtfsCloseEntryLookasideList; Lookaside
0x140148f7a  call    cs:__imp_ExAllocateFromLookasideListEx
0x140148f81  nop     dword ptr [rax+rax+00h]
0x140148f86  mov     rbx, rax
0x140148f89  test    rax, rax
0x140148f8c  jz      loc_140149370
0x140148f92  mov     [rsp+80h+arg_10], r12
0x140148f9a  xor     edx, edx; Val
0x140148f9c  mov     [rsp+80h+var_8], r13
0x140148fa1  mov     r8d, 58h ; 'X'; Size
0x140148fa7  mov     rcx, rbx; void *
0x140148faa  mov     [rsp+80h+var_10], r15
0x140148faf  call    memset
0x140148fb4  mov     [rbx+8], rbx
0x140148fb8  lea     r15, [rbx+10h]
0x140148fbc  mov     [rbx], rbx
0x140148fbf  xor     r9d, r9d
0x140148fc2  mov     [r15+8], r15
0x140148fc6  mov     r8b, 1
0x140148fc9  mov     [r15], r15
0x140148fcc  mov     rdx, rdi
0x140148fcf  mov     [rbx+20h], rdi
0x140148fd3  mov     byte ptr [rbx+38h], 5
0x140148fd7  call    NtfsIncrementCloseCounts
0x140148fdc  test    sil, sil
0x140148fdf  jz      loc_140149074
0x140148fe5  mov     rax, [rdi+0B8h]
0x140148fec  mov     rcx, [rax+68h]
0x140148ff0  add     rcx, 8; FastMutex
0x140148ff4  call    cs:__imp_ExAcquireFastMutex
0x140148ffb  nop     dword ptr [rax+rax+00h]
0x140149000  mov     rax, [rdi+0B8h]
0x140149007  lea     rcx, [rdi+0A8h]
0x14014900e  mov     rdx, [rcx]
0x140149011  add     rax, 40h ; '@'
0x140149015  cmp     rdx, rax
0x140149018  jz      short loc_140149059
0x14014901a  cmp     [rdx+8], rcx
0x14014901e  jnz     short loc_140149044
0x140149020  mov     rax, [rcx+8]
0x140149024  cmp     [rax], rcx
0x140149027  jnz     short loc_140149044
0x140149029  mov     [rax], rdx
0x14014902c  mov     [rdx+8], rax
0x140149030  mov     rax, [rdi+0B8h]
0x140149037  add     rax, 40h ; '@'
0x14014903b  mov     rdx, [rax+8]
0x14014903f  cmp     [rdx], rax
0x140149042  jz      short loc_14014904B
0x140149044  mov     ecx, 3
0x140149049  int     29h; Win8: RtlFailFast(ecx)
0x14014904b  mov     [rcx], rax
0x14014904e  mov     [rcx+8], rdx
0x140149052  mov     [rdx], rcx
0x140149055  mov     [rax+8], rcx
0x140149059  mov     rax, [rdi+0B8h]
0x140149060  mov     rcx, [rax+68h]
0x140149064  add     rcx, 8; FastMutex
0x140149068  call    cs:__imp_ExReleaseFastMutex
0x14014906f  nop     dword ptr [rax+rax+00h]
0x140149074  test    r14, r14
0x140149077  jz      short loc_140149086
0x140149079  mov     rcx, [r14+78h]
0x14014907d  test    rcx, rcx
0x140149080  jnz     loc_1401492A7
0x140149086  call    cs:__imp_IoGetActivityIdThread
0x14014908d  nop     dword ptr [rax+rax+00h]
0x140149092  test    rax, rax
0x140149095  jnz     loc_14014930C
0x14014909b  xor     ecx, ecx
0x14014909d  mov     qword ptr [rbp+var_48], rcx
0x1401490a1  call    cs:__imp_IoSetActivityIdThread
0x1401490a8  nop     dword ptr [rax+rax+00h]
0x1401490ad  mov     rcx, [rbx+20h]
0x1401490b1  xor     r12b, r12b
0x1401490b4  mov     r13, rax
0x1401490b7  xorps   xmm0, xmm0
0x1401490ba  xor     eax, eax
0x1401490bc  mov     [rbp+var_20], rax
0x1401490c0  movups  [rbp+var_30], xmm0
0x1401490c4  mov     rsi, [rcx+0C0h]
0x1401490cb  test    r14, r14
0x1401490ce  jz      loc_1401492E7
0x1401490d4  mov     rcx, [r14+78h]
0x1401490d8  test    rcx, rcx
0x1401490db  jnz     loc_1401492C7
0x1401490e1  call    cs:__imp_IoGetActivityIdThread
0x1401490e8  nop     dword ptr [rax+rax+00h]
0x1401490ed  test    rax, rax
0x1401490f0  jnz     loc_140149324
0x1401490f6  xor     r12d, r12d
0x1401490f9  mov     qword ptr [rbp+var_30], r12
0x1401490fd  test    r12, r12
0x140149100  jnz     loc_140149375
0x140149106  mov     [rbx+40h], r12
0x14014910a  lea     rdi, [rsi+2108h]
0x140149111  lock inc dword ptr [rsi+1328h]
0x140149118  mov     rcx, rdi; Mutex
0x14014911b  call    cs:__imp_KeAcquireGuardedMutex
0x140149122  nop     dword ptr [rax+rax+00h]
0x140149127  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x14014912e  jnz     loc_1401493AD
0x140149134  mov     r14, rdi
0x140149137  xor     r12b, r12b
0x14014913a  cmp     [rbp+var_50], 0
0x14014913e  jnz     short loc_1401491AA
0x140149140  lea     rax, [rsi+20D0h]
0x140149147  mov     rdx, [rax+8]
0x14014914b  cmp     [rdx], rax
0x14014914e  jnz     loc_140149044
0x140149154  mov     [rbx], rax
0x140149157  mov     [rbx+8], rdx
0x14014915b  mov     [rdx], rbx
0x14014915e  mov     [rax+8], rbx
0x140149162  mov     eax, [rsi+20E4h]
0x140149168  inc     eax
0x14014916a  mov     [rsi+20E4h], eax
0x140149170  mov     eax, [rsi+20E4h]
0x140149176  cmp     eax, [rsi+20E8h]
0x14014917c  ja      loc_14014933C
0x140149182  cmp     byte ptr [rsi+20E0h], 0
0x140149189  jnz     loc_140149239
0x14014918f  mov     rcx, r14; Mutex
0x140149192  mov     byte ptr [rsi+20E0h], 1
0x140149199  call    cs:__imp_KeReleaseGuardedMutex
0x1401491a0  nop     dword ptr [rax+rax+00h]
0x1401491a5  jmp     loc_14014924D
0x1401491aa  lea     rax, [rsi+20F8h]
0x1401491b1  mov     rcx, [rax+8]
0x1401491b5  cmp     [rcx], rax
0x1401491b8  jnz     loc_140149044
0x1401491be  mov     [rbx], rax
0x1401491c1  mov     [rbx+8], rcx
0x1401491c5  mov     [rcx], rbx
0x1401491c8  mov     [rax+8], rbx
0x1401491cc  mov     rax, [rbx+20h]
0x1401491d0  mov     rcx, [rax+0B8h]
0x1401491d7  mov     rax, [rcx+110h]
0x1401491de  test    rax, rax
0x1401491e1  jnz     loc_1401493CA
0x1401491e7  mov     [rcx+110h], rbx
0x1401491ee  mov     eax, [rsi+20ECh]
0x1401491f4  inc     eax
0x1401491f6  mov     [rsi+20ECh], eax
0x1401491fc  mov     eax, [rsi+20ECh]
0x140149202  cmp     eax, [rsi+20F0h]
0x140149208  jbe     short loc_140149216
0x14014920a  mov     eax, [rsi+20ECh]
0x140149210  mov     [rsi+20F0h], eax
0x140149216  mov     rax, [rbx+20h]
0x14014921a  mov     rcx, [rax+0B8h]
0x140149221  inc     dword ptr [rcx+10Ch]
0x140149227  mov     eax, [rsi+20ECh]
0x14014922d  cmp     eax, cs:NtfsMaxDelayCloseCount
0x140149233  ja      loc_14014934D
0x140149239  mov     rcx, rdi; Mutex
0x14014923c  call    cs:__imp_KeReleaseGuardedMutex
0x140149243  nop     dword ptr [rax+rax+00h]
0x140149248  test    r12b, r12b
0x14014924b  jz      short loc_140149269
0x14014924d  lock inc dword ptr [rsi+11Ch]
0x140149254  lea     rcx, [rsi+20B0h]; WorkItem
0x14014925b  xor     edx, edx; QueueType
0x14014925d  call    cs:__imp_ExQueueWorkItem
0x140149264  nop     dword ptr [rax+rax+00h]
0x140149269  mov     rcx, r13
0x14014926c  call    cs:__imp_IoClearActivityIdThread
0x140149273  nop     dword ptr [rax+rax+00h]
0x140149278  mov     r13, [rsp+80h+var_8]
0x14014927d  mov     al, 1
0x14014927f  mov     r12, [rsp+80h+arg_10]
0x140149287  mov     r15, [rsp+80h+var_10]
0x14014928c  mov     rcx, [rbp+var_18]
0x140149290  xor     rcx, rsp; StackCookie
0x140149293  call    __security_check_cookie
0x140149298  add     rsp, 80h
0x14014929f  pop     r14
0x1401492a1  pop     rdi
0x1401492a2  pop     rsi
0x1401492a3  pop     rbx
0x1401492a4  pop     rbp
0x1401492a5  retn
0x1401492a7  mov     rax, [rcx]
0x1401492aa  mov     qword ptr [rbp+var_48+8], rax
0x1401492ae  mov     rax, [rcx+8]
0x1401492b2  mov     [rbp+var_38], rax
0x1401492b6  lea     rax, [rbp+var_48+8]
0x1401492ba  mov     qword ptr [rbp+var_48], rax
0x1401492be  mov     rcx, qword ptr [rbp+var_48]
0x1401492c2  jmp     loc_1401490A1
0x1401492c7  mov     rax, [rcx]
0x1401492ca  mov     qword ptr [rbp+var_30+8], rax
0x1401492ce  mov     rax, [rcx+8]
0x1401492d2  mov     [rbp+var_20], rax
0x1401492d6  lea     rax, [rbp+var_30+8]
0x1401492da  mov     qword ptr [rbp+var_30], rax
0x1401492de  mov     r12, qword ptr [rbp+var_30]
0x1401492e2  jmp     loc_1401490FD
0x1401492e7  lock inc dword ptr [rsi+1328h]
0x1401492ee  lea     rdi, [rsi+2108h]
0x1401492f5  mov     rcx, rdi; Mutex
0x1401492f8  mov     r14, rdi
0x1401492fb  call    cs:__imp_KeAcquireGuardedMutex
0x140149302  nop     dword ptr [rax+rax+00h]
0x140149307  jmp     loc_14014913A
0x14014930c  mov     rcx, [rax]
0x14014930f  mov     qword ptr [rbp+var_48+8], rcx
0x140149313  lea     rcx, [rbp+var_48+8]
0x140149317  mov     rax, [rax+8]
0x14014931b  mov     [rbp+var_38], rax
0x14014931f  jmp     loc_14014909D
0x140149324  mov     rcx, [rax]
0x140149327  lea     r12, [rbp+var_30+8]
0x14014932b  mov     qword ptr [rbp+var_30+8], rcx
0x14014932f  mov     rax, [rax+8]
0x140149333  mov     [rbp+var_20], rax
0x140149337  jmp     loc_1401490F9
0x14014933c  mov     eax, [rsi+20E4h]
0x140149342  mov     [rsi+20E8h], eax
0x140149348  jmp     loc_140149182
0x14014934d  cmp     byte ptr [rsi+20E0h], 0
0x140149354  mov     byte ptr [rsi+20E2h], 1
0x14014935b  jnz     loc_140149239
0x140149361  mov     byte ptr [rsi+20E0h], 1
0x140149368  mov     r12b, 1
0x14014936b  jmp     loc_140149239
0x140149370  jmp     loc_14014928C
0x140149375  lea     rdi, [rbx+48h]
0x140149379  mov     ecx, 3; ControlCode
0x14014937e  mov     rdx, rdi; ActivityId
0x140149381  call    cs:__imp_EtwActivityIdControl
0x140149388  nop     dword ptr [rax+rax+00h]
0x14014938d  mov     [rbx+40h], rdi
0x140149391  mov     rcx, r12
0x140149394  mov     rdx, [rbx+40h]
0x140149398  call    cs:__imp_IoTransferActivityId
0x14014939f  nop     dword ptr [rax+rax+00h]
0x1401493a4  mov     rax, [rbx+40h]
0x1401493a8  jmp     loc_14014910A
0x1401493ad  mov     r8, [r14+78h]
0x1401493b1  lea     rdx, WORKITEM_QUEUE
0x1401493b8  mov     [rsp+80h+var_60], 2
0x1401493c0  call    McTemplateK0pq_EtwWriteTransfer
0x1401493c5  jmp     loc_140149134
0x1401493ca  mov     rcx, [rax+18h]
0x1401493ce  add     rax, 10h
0x1401493d2  cmp     [rcx], rax
0x1401493d5  jnz     loc_140149044
0x1401493db  mov     [r15], rax
0x1401493de  mov     [r15+8], rcx
0x1401493e2  mov     [rcx], r15
0x1401493e5  mov     [rax+8], r15
0x1401493e9  jmp     loc_1401491EE
```
