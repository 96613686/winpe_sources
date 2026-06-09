# UlpFreeConsumer

- ea: `0x140095f70`
- end: `0x140096223`
- name: `UlpFreeConsumer`
- size: `691`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400953dc`
- `0x1400955d8`
- `0x1400b37f4`
- `0x1400cf398`

## callees

- `0x14000a350`
- `0x140062110`
- `0x140092530`
- `0x140095f70`
- `0x14009622c`
- `0x140096348`
- `0x1400af4c0`
- `0x1400b3e00`
- `0x140105a28`
- `0x1401c3f58`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140095fe0`
- `ntoskrnl!ZwClose` at `0x140095fe0`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400960a3`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400960a3`
- `ntoskrnl!ObfDereferenceObject` at `0x140095fc7`
- `ntoskrnl!ObfDereferenceObject` at `0x140095ff9`
- `ntoskrnl!ObfDereferenceObject` at `0x140095fc7`
- `ntoskrnl!ObfDereferenceObject` at `0x140095ff9`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x14009605b`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x14009605b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400960af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400960d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400960af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400960d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400961ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400961ec`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400960cb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400960cb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140096038`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140096038`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140096016`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140096048`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140096016`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140096048`

## pseudocode

```c
void __fastcall UlpFreeConsumer(volatile signed __int32 **P)
{
  volatile signed __int32 *v2; // rcx
  volatile signed __int32 *v3; // rcx
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rcx
  char v6; // si
  volatile signed __int32 *v7; // rbx
  char v8; // bl
  volatile signed __int32 *v9; // rcx
  volatile signed __int32 *v10; // rdx
  int v11; // eax
  volatile signed __int32 *v12; // rdx
  int v13; // eax
  volatile signed __int32 *v14; // rdx
  int v15; // eax
  volatile signed __int32 *v16; // rcx

  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 49, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, P);
  if ( P[13] )
    UlFreeCapturedProcessIdentity();
  v2 = P[2];
  if ( v2 )
    UlFreePerNode((void *)v2);
  v3 = P[11];
  if ( v3 )
  {
    ObfDereferenceObject((PVOID)v3);
    P[11] = 0;
  }
  v4 = P[10];
  if ( v4 )
  {
    ZwClose((HANDLE)v4);
    P[10] = 0;
  }
  v5 = P[9];
  if ( v5 )
  {
    ObfDereferenceObject((PVOID)v5);
    P[9] = 0;
  }
  if ( P[1] )
  {
    v6 = 0;
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(*((_QWORD *)P[1] + 41) + 4144LL, 0);
    v7 = P[1];
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(*((_QWORD *)v7 + 35));
    v8 = *((_BYTE *)P + 128);
    *((_BYTE *)P + 128) = 0;
    if ( *((_BYTE *)P + 144) )
    {
      UlpDetachConsumerFromRequestQueue(P);
      v9 = P[1];
      *((_BYTE *)P + 144) = 0;
      v6 = UlpAttemptRequestQueueCleanup(v9);
    }
    ExReleaseCacheAwarePushLockExclusive(*((_QWORD *)P[1] + 35));
    KeLeaveCriticalRegion();
    ExReleasePushLockExclusiveEx(*((_QWORD *)P[1] + 41) + 4144LL, 0);
    KeLeaveCriticalRegion();
    if ( v8 )
    {
      v10 = (volatile signed __int32 *)(*((_QWORD *)P[1] + 41) + 4208LL);
      v11 = _InterlockedDecrement(v10);
      if ( UxDebugCheckRefcount && v11 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)v10, 0xAu, v11);
      if ( !v11 )
        UxPodCheckZombieCleanup(*((_QWORD *)P[1] + 41));
    }
    v12 = P[1];
    v13 = _InterlockedDecrement(v12);
    if ( UxDebugCheckRefcount && v13 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v12, 6u, v13);
    if ( !v13 )
      UlFreeRequestQueue((PSECURITY_DESCRIPTOR *)P[1]);
    if ( v6 )
    {
      v14 = P[1];
      v15 = _InterlockedDecrement(v14);
      if ( UxDebugCheckRefcount && v15 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)v14, 1u, v15);
      if ( !v15 )
        UlFreeRequestQueue((PSECURITY_DESCRIPTOR *)P[1]);
    }
    P[1] = 0;
  }
  v16 = P[17];
  if ( v16 )
  {
    UxPodDereferenceSilo(*((PVOID *)v16 + 8), 0x50416C55u, 6u);
    P[17] = 0;
  }
  *((_DWORD *)P + 6) = 1885424757;
  ExFreePoolWithTag(P, 0);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 50, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
}

```

## disassembly

```asm
0x140095f70  push    rbx
0x140095f72  push    rbp
0x140095f73  push    rsi
0x140095f74  push    rdi
0x140095f75  push    r14
0x140095f77  sub     rsp, 20h
0x140095f7b  mov     rdi, rcx
0x140095f7e  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140095f85  jz      short loc_140095FA0
0x140095f87  mov     edx, 31h ; '1'
0x140095f8c  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140095f93  mov     ecx, 408h
0x140095f98  mov     r9, rdi
0x140095f9b  call    WPP_SF_q
0x140095fa0  lea     rcx, [rdi+68h]
0x140095fa4  xor     ebp, ebp
0x140095fa6  cmp     [rcx], rbp
0x140095fa9  jz      short loc_140095FB0
0x140095fab  call    UlFreeCapturedProcessIdentity
0x140095fb0  mov     rcx, [rdi+10h]; void *
0x140095fb4  test    rcx, rcx
0x140095fb7  jz      short loc_140095FBE
0x140095fb9  call    UlFreePerNode
0x140095fbe  mov     rcx, [rdi+58h]; Object
0x140095fc2  test    rcx, rcx
0x140095fc5  jz      short loc_140095FD7
0x140095fc7  call    cs:__imp_ObfDereferenceObject
0x140095fce  nop     dword ptr [rax+rax+00h]
0x140095fd3  mov     [rdi+58h], rbp
0x140095fd7  mov     rcx, [rdi+50h]; Handle
0x140095fdb  test    rcx, rcx
0x140095fde  jz      short loc_140095FF0
0x140095fe0  call    cs:__imp_ZwClose
0x140095fe7  nop     dword ptr [rax+rax+00h]
0x140095fec  mov     [rdi+50h], rbp
0x140095ff0  mov     rcx, [rdi+48h]; Object
0x140095ff4  test    rcx, rcx
0x140095ff7  jz      short loc_140096009
0x140095ff9  call    cs:__imp_ObfDereferenceObject
0x140096000  nop     dword ptr [rax+rax+00h]
0x140096005  mov     [rdi+48h], rbp
0x140096009  cmp     [rdi+8], rbp
0x14009600d  jz      loc_1400961B9
0x140096013  mov     sil, bpl
0x140096016  call    cs:__imp_KeEnterCriticalRegion
0x14009601d  nop     dword ptr [rax+rax+00h]
0x140096022  mov     rax, [rdi+8]
0x140096026  mov     r14d, 1030h
0x14009602c  xor     edx, edx
0x14009602e  mov     rcx, [rax+148h]
0x140096035  add     rcx, r14
0x140096038  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14009603f  nop     dword ptr [rax+rax+00h]
0x140096044  mov     rbx, [rdi+8]
0x140096048  call    cs:__imp_KeEnterCriticalRegion
0x14009604f  nop     dword ptr [rax+rax+00h]
0x140096054  mov     rcx, [rbx+118h]
0x14009605b  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x140096062  nop     dword ptr [rax+rax+00h]
0x140096067  mov     bl, [rdi+80h]
0x14009606d  mov     [rdi+80h], bpl
0x140096074  cmp     [rdi+90h], bpl
0x14009607b  jz      short loc_140096098
0x14009607d  mov     rcx, rdi
0x140096080  call    UlpDetachConsumerFromRequestQueue
0x140096085  mov     rcx, [rdi+8]
0x140096089  mov     [rdi+90h], bpl
0x140096090  call    UlpAttemptRequestQueueCleanup
0x140096095  mov     sil, al
0x140096098  mov     rcx, [rdi+8]
0x14009609c  mov     rcx, [rcx+118h]
0x1400960a3  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400960aa  nop     dword ptr [rax+rax+00h]
0x1400960af  call    cs:__imp_KeLeaveCriticalRegion
0x1400960b6  nop     dword ptr [rax+rax+00h]
0x1400960bb  mov     rcx, [rdi+8]
0x1400960bf  xor     edx, edx
0x1400960c1  mov     rcx, [rcx+148h]
0x1400960c8  add     rcx, r14
0x1400960cb  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400960d2  nop     dword ptr [rax+rax+00h]
0x1400960d7  call    cs:__imp_KeLeaveCriticalRegion
0x1400960de  nop     dword ptr [rax+rax+00h]
0x1400960e3  or      r14d, 0FFFFFFFFh
0x1400960e7  test    bl, bl
0x1400960e9  jz      short loc_14009613A
0x1400960eb  mov     rax, [rdi+8]
0x1400960ef  mov     rdx, [rax+148h]
0x1400960f6  mov     eax, r14d
0x1400960f9  add     rdx, 1070h; BugCheckParameter2
0x140096100  lock xadd [rdx], eax
0x140096104  add     eax, r14d
0x140096107  cmp     cs:UxDebugCheckRefcount, bpl
0x14009610e  jz      short loc_140096126
0x140096110  cmp     eax, r14d
0x140096113  jg      short loc_140096126
0x140096115  movsxd  r9, eax; BugCheckParameter4
0x140096118  lea     ecx, [r14+4]; BugCheckParameter1
0x14009611c  lea     r8d, [r14+0Bh]; BugCheckParameter3
0x140096120  call    UlBugCheckEx
0x140096126  test    eax, eax
0x140096128  jnz     short loc_14009613A
0x14009612a  mov     rcx, [rdi+8]
0x14009612e  mov     rcx, [rcx+148h]
0x140096135  call    UxPodCheckZombieCleanup
0x14009613a  mov     rdx, [rdi+8]; BugCheckParameter2
0x14009613e  mov     eax, r14d
0x140096141  lock xadd [rdx], eax
0x140096145  add     eax, r14d
0x140096148  cmp     cs:UxDebugCheckRefcount, bpl
0x14009614f  jz      short loc_140096168
0x140096151  cmp     eax, r14d
0x140096154  jg      short loc_140096168
0x140096156  mov     ecx, 3; BugCheckParameter1
0x14009615b  movsxd  r9, eax; BugCheckParameter4
0x14009615e  lea     r8d, [rcx+3]; BugCheckParameter3
0x140096162  call    UlBugCheckEx
0x140096168  test    eax, eax
0x14009616a  jnz     short loc_140096175
0x14009616c  mov     rcx, [rdi+8]; P
0x140096170  call    UlFreeRequestQueue
0x140096175  test    sil, sil
0x140096178  jz      short loc_1400961B5
0x14009617a  mov     rdx, [rdi+8]; BugCheckParameter2
0x14009617e  mov     eax, r14d
0x140096181  lock xadd [rdx], eax
0x140096185  add     eax, r14d
0x140096188  cmp     cs:UxDebugCheckRefcount, bpl
0x14009618f  jz      short loc_1400961A8
0x140096191  cmp     eax, r14d
0x140096194  jg      short loc_1400961A8
0x140096196  mov     ecx, 3; BugCheckParameter1
0x14009619b  movsxd  r9, eax; BugCheckParameter4
0x14009619e  lea     r8d, [rcx-2]; BugCheckParameter3
0x1400961a2  call    UlBugCheckEx
0x1400961a8  test    eax, eax
0x1400961aa  jnz     short loc_1400961B5
0x1400961ac  mov     rcx, [rdi+8]; P
0x1400961b0  call    UlFreeRequestQueue
0x1400961b5  mov     [rdi+8], rbp
0x1400961b9  mov     rcx, [rdi+88h]
0x1400961c0  test    rcx, rcx
0x1400961c3  jz      short loc_1400961E0
0x1400961c5  mov     rcx, [rcx+40h]; Object
0x1400961c9  mov     edx, 50416C55h; Tag
0x1400961ce  mov     r8d, 6; BugCheckParameter3
0x1400961d4  call    UxPodDereferenceSilo
0x1400961d9  mov     [rdi+88h], rbp
0x1400961e0  xor     edx, edx; Tag
0x1400961e2  mov     dword ptr [rdi+18h], 70614C75h
0x1400961e9  mov     rcx, rdi; P
0x1400961ec  call    cs:__imp_ExFreePoolWithTag
0x1400961f3  nop     dword ptr [rax+rax+00h]
0x1400961f8  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400961ff  jz      short loc_140096217
0x140096201  mov     edx, 32h ; '2'
0x140096206  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x14009620d  mov     ecx, 408h
0x140096212  call    WPP_SF_
0x140096217  add     rsp, 20h
0x14009621b  pop     r14
0x14009621d  pop     rdi
0x14009621e  pop     rsi
0x14009621f  pop     rbp
0x140096220  pop     rbx
0x140096221  retn
```
