# UlRegisterConsumerCallback

- ea: `0x1400cd498`
- end: `0x1400cd5d9`
- name: `UlRegisterConsumerCallback`
- size: `321`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14013a2e0`

## callees

- `0x14000a350`
- `0x1400cd498`
- `0x1401d9c5c`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cd511`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cd58f`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cd511`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cd58f`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400cd4f2`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400cd4f2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cd51d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cd59b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cd51d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cd59b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cd4df`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cd4df`

## pseudocode

```c
unsigned __int8 __fastcall UlRegisterConsumerCallback(ULONG_PTR BugCheckParameter2, _QWORD *a2)
{
  __int64 v4; // rbx
  unsigned __int8 v5; // bl
  int v6; // eax
  _QWORD *v7; // rcx

  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qqP(
      1032,
      112,
      WPP_1911597aeee73f2bcf560a2021118daf_Traceguids,
      BugCheckParameter2,
      a2,
      UxSslConsumerCleanupHandler);
  v4 = *(_QWORD *)(BugCheckParameter2 + 8);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v4 + 280));
  if ( *(_BYTE *)(BugCheckParameter2 + 5) )
  {
    v5 = 0;
    ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(*(_QWORD *)(BugCheckParameter2 + 8) + 280LL));
    KeLeaveCriticalRegion();
  }
  else
  {
    a2[2] = BugCheckParameter2;
    v6 = _InterlockedIncrement((volatile signed __int32 *)BugCheckParameter2);
    if ( UxDebugCheckRefcount && v6 <= -1 )
      UlBugCheckEx(3u, BugCheckParameter2, 0xFu, v6);
    a2[3] = UxSslConsumerCleanupHandler;
    v7 = *(_QWORD **)(BugCheckParameter2 + 120);
    if ( *v7 != BugCheckParameter2 + 112 )
      __fastfail(3u);
    *a2 = BugCheckParameter2 + 112;
    a2[1] = v7;
    *v7 = a2;
    *(_QWORD *)(BugCheckParameter2 + 120) = a2;
    ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(*(_QWORD *)(BugCheckParameter2 + 8) + 280LL));
    KeLeaveCriticalRegion();
    v5 = 1;
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 113, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1400cd498  push    rbx
0x1400cd49a  push    rsi
0x1400cd49b  push    rdi
0x1400cd49c  push    r14
0x1400cd49e  sub     rsp, 38h
0x1400cd4a2  mov     rsi, rdx
0x1400cd4a5  mov     rdi, rcx
0x1400cd4a8  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400cd4af  lea     r14, UxSslConsumerCleanupHandler
0x1400cd4b6  jz      short loc_1400CD4DB
0x1400cd4b8  mov     edx, 70h ; 'p'
0x1400cd4bd  mov     [rsp+58h+var_30], r14
0x1400cd4c2  mov     ecx, 408h
0x1400cd4c7  mov     [rsp+58h+var_38], rsi
0x1400cd4cc  mov     r9, rdi
0x1400cd4cf  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cd4d6  call    WPP_SF_qqP
0x1400cd4db  mov     rbx, [rdi+8]
0x1400cd4df  call    cs:__imp_KeEnterCriticalRegion
0x1400cd4e6  nop     dword ptr [rax+rax+00h]
0x1400cd4eb  mov     rcx, [rbx+118h]
0x1400cd4f2  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400cd4f9  nop     dword ptr [rax+rax+00h]
0x1400cd4fe  cmp     byte ptr [rdi+5], 0
0x1400cd502  jz      short loc_1400CD52B
0x1400cd504  mov     rcx, [rdi+8]
0x1400cd508  xor     bl, bl
0x1400cd50a  mov     rcx, [rcx+118h]
0x1400cd511  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400cd518  nop     dword ptr [rax+rax+00h]
0x1400cd51d  call    cs:__imp_KeLeaveCriticalRegion
0x1400cd524  nop     dword ptr [rax+rax+00h]
0x1400cd529  jmp     short loc_1400CD5A9
0x1400cd52b  mov     [rsi+10h], rdi
0x1400cd52f  mov     eax, 1
0x1400cd534  lock xadd [rdi], eax
0x1400cd538  inc     eax
0x1400cd53a  cmp     cs:UxDebugCheckRefcount, 0
0x1400cd541  jz      short loc_1400CD55E
0x1400cd543  cmp     eax, 0FFFFFFFFh
0x1400cd546  jg      short loc_1400CD55E
0x1400cd548  mov     r8d, 0Fh; BugCheckParameter3
0x1400cd54e  movsxd  r9, eax; BugCheckParameter4
0x1400cd551  mov     rdx, rdi; BugCheckParameter2
0x1400cd554  lea     ecx, [r8-0Ch]; BugCheckParameter1
0x1400cd558  call    UlBugCheckEx
0x1400cd55e  lea     rax, [rdi+70h]
0x1400cd562  mov     [rsi+18h], r14
0x1400cd566  mov     rcx, [rax+8]
0x1400cd56a  cmp     [rcx], rax
0x1400cd56d  jz      short loc_1400CD576
0x1400cd56f  mov     ecx, 3
0x1400cd574  int     29h; Win8: RtlFailFast(ecx)
0x1400cd576  mov     [rsi], rax
0x1400cd579  mov     [rsi+8], rcx
0x1400cd57d  mov     [rcx], rsi
0x1400cd580  mov     [rax+8], rsi
0x1400cd584  mov     rcx, [rdi+8]
0x1400cd588  mov     rcx, [rcx+118h]
0x1400cd58f  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400cd596  nop     dword ptr [rax+rax+00h]
0x1400cd59b  call    cs:__imp_KeLeaveCriticalRegion
0x1400cd5a2  nop     dword ptr [rax+rax+00h]
0x1400cd5a7  mov     bl, 1
0x1400cd5a9  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400cd5b0  jz      short loc_1400CD5CC
0x1400cd5b2  movzx   r9d, bl
0x1400cd5b6  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cd5bd  mov     edx, 71h ; 'q'
0x1400cd5c2  mov     ecx, 408h
0x1400cd5c7  call    WPP_SF_d
0x1400cd5cc  mov     al, bl
0x1400cd5ce  add     rsp, 38h
0x1400cd5d2  pop     r14
0x1400cd5d4  pop     rdi
0x1400cd5d5  pop     rsi
0x1400cd5d6  pop     rbx
0x1400cd5d7  retn
```
