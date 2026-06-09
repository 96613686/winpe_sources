# UlRegisterConsumerCallback

- ea: `0x1400cd3b8`
- end: `0x1400cd4f9`
- name: `UlRegisterConsumerCallback`
- size: `321`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14013a3d0`

## callees

- `0x14000a350`
- `0x1400cd3b8`
- `0x1401d9c5c`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cd431`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cd4af`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cd431`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cd4af`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400cd412`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400cd412`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cd43d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cd4bb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cd43d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cd4bb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cd3ff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cd3ff`

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
0x1400cd3b8  push    rbx
0x1400cd3ba  push    rsi
0x1400cd3bb  push    rdi
0x1400cd3bc  push    r14
0x1400cd3be  sub     rsp, 38h
0x1400cd3c2  mov     rsi, rdx
0x1400cd3c5  mov     rdi, rcx
0x1400cd3c8  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400cd3cf  lea     r14, UxSslConsumerCleanupHandler
0x1400cd3d6  jz      short loc_1400CD3FB
0x1400cd3d8  mov     edx, 70h ; 'p'
0x1400cd3dd  mov     [rsp+58h+var_30], r14
0x1400cd3e2  mov     ecx, 408h
0x1400cd3e7  mov     [rsp+58h+var_38], rsi
0x1400cd3ec  mov     r9, rdi
0x1400cd3ef  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cd3f6  call    WPP_SF_qqP
0x1400cd3fb  mov     rbx, [rdi+8]
0x1400cd3ff  call    cs:__imp_KeEnterCriticalRegion
0x1400cd406  nop     dword ptr [rax+rax+00h]
0x1400cd40b  mov     rcx, [rbx+118h]
0x1400cd412  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400cd419  nop     dword ptr [rax+rax+00h]
0x1400cd41e  cmp     byte ptr [rdi+5], 0
0x1400cd422  jz      short loc_1400CD44B
0x1400cd424  mov     rcx, [rdi+8]
0x1400cd428  xor     bl, bl
0x1400cd42a  mov     rcx, [rcx+118h]
0x1400cd431  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400cd438  nop     dword ptr [rax+rax+00h]
0x1400cd43d  call    cs:__imp_KeLeaveCriticalRegion
0x1400cd444  nop     dword ptr [rax+rax+00h]
0x1400cd449  jmp     short loc_1400CD4C9
0x1400cd44b  mov     [rsi+10h], rdi
0x1400cd44f  mov     eax, 1
0x1400cd454  lock xadd [rdi], eax
0x1400cd458  inc     eax
0x1400cd45a  cmp     cs:UxDebugCheckRefcount, 0
0x1400cd461  jz      short loc_1400CD47E
0x1400cd463  cmp     eax, 0FFFFFFFFh
0x1400cd466  jg      short loc_1400CD47E
0x1400cd468  mov     r8d, 0Fh; BugCheckParameter3
0x1400cd46e  movsxd  r9, eax; BugCheckParameter4
0x1400cd471  mov     rdx, rdi; BugCheckParameter2
0x1400cd474  lea     ecx, [r8-0Ch]; BugCheckParameter1
0x1400cd478  call    UlBugCheckEx
0x1400cd47e  lea     rax, [rdi+70h]
0x1400cd482  mov     [rsi+18h], r14
0x1400cd486  mov     rcx, [rax+8]
0x1400cd48a  cmp     [rcx], rax
0x1400cd48d  jz      short loc_1400CD496
0x1400cd48f  mov     ecx, 3
0x1400cd494  int     29h; Win8: RtlFailFast(ecx)
0x1400cd496  mov     [rsi], rax
0x1400cd499  mov     [rsi+8], rcx
0x1400cd49d  mov     [rcx], rsi
0x1400cd4a0  mov     [rax+8], rsi
0x1400cd4a4  mov     rcx, [rdi+8]
0x1400cd4a8  mov     rcx, [rcx+118h]
0x1400cd4af  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400cd4b6  nop     dword ptr [rax+rax+00h]
0x1400cd4bb  call    cs:__imp_KeLeaveCriticalRegion
0x1400cd4c2  nop     dword ptr [rax+rax+00h]
0x1400cd4c7  mov     bl, 1
0x1400cd4c9  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400cd4d0  jz      short loc_1400CD4EC
0x1400cd4d2  movzx   r9d, bl
0x1400cd4d6  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cd4dd  mov     edx, 71h ; 'q'
0x1400cd4e2  mov     ecx, 408h
0x1400cd4e7  call    WPP_SF_d
0x1400cd4ec  mov     al, bl
0x1400cd4ee  add     rsp, 38h
0x1400cd4f2  pop     r14
0x1400cd4f4  pop     rdi
0x1400cd4f5  pop     rsi
0x1400cd4f6  pop     rbx
0x1400cd4f7  retn
```
