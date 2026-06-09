# FvepInformRundownFinishedWithDisk

- ea: `0x14002a4e4`
- end: `0x14002a661`
- name: `FvepInformRundownFinishedWithDisk`
- size: `381`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000f9f0`
- `0x140025040`
- `0x140025b9c`
- `0x140028b28`
- `0x140029c84`
- `0x14002a3a0`
- `0x14002a3f0`
- `0x1400bb7e4`
- `0x1400bb9d0`
- `0x1400bc060`
- `0x1400bc1c0`
- `0x1400bd6a4`
- `0x1400d8e60`
- `0x1400df5f8`
- `0x1400df860`
- `0x1400e2bf8`

## callees

- `0x14002a4e4`
- `0x14002aa38`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002a559`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002a649`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002a559`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002a649`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002a5da`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002a5da`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002a631`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002a631`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a5b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a5b7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a587`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a587`

## pseudocode

```c
__int64 __fastcall FvepInformRundownFinishedWithDisk(__int64 a1, __int64 a2, unsigned __int8 a3)
{
  int v4; // edi
  __int64 v5; // rcx
  volatile signed __int32 *v7; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v9; // rcx
  void *v10; // rsi
  KIRQL v11; // r9
  _QWORD *v12; // r8
  _QWORD *i; // rdx
  _QWORD *v14; // rax
  _QWORD *v15; // rcx

  v4 = a3;
  v5 = *(_QWORD *)(a1 + 2352);
  if ( *(_QWORD *)(v5 + 8) )
  {
    v10 = 0;
    v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 16));
    v12 = (_QWORD *)(*(_QWORD *)(a1 + 2352) + 24LL);
    for ( i = (_QWORD *)*v12; i != v12; i = (_QWORD *)*i )
    {
      if ( i[2] == a2 && *((_DWORD *)i + 6) == v4 )
      {
        v14 = (_QWORD *)*i;
        if ( *(_QWORD **)(*i + 8LL) != i || (v15 = (_QWORD *)i[1], (_QWORD *)*v15 != i) )
          __fastfail(3u);
        *v15 = v14;
        v10 = i;
        v14[1] = v15;
        break;
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 2352) + 16LL), v11);
    if ( v10 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(a1 + 2352) + 8LL), v10);
  }
  if ( *(_DWORD *)(a1 + 2344) == 1 )
    v7 = *(volatile signed __int32 **)(a1 + 2352);
  else
    v7 = (volatile signed __int32 *)(*(_QWORD *)(a1 + 2352) + 296LL * HIDWORD(KeGetPcr()[1].LockArray));
  _InterlockedDecrement(v7);
  if ( !*(_BYTE *)(a1 + 1476) )
  {
    if ( (unsigned __int8)v4 >= 2u )
    {
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1464));
    }
    else if ( !(_BYTE)v4 )
    {
      return FvepReleaseRemoveLock(a1 + 56);
    }
    v9 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(a1 + 1456);
LABEL_10:
    ExReleaseRundownProtectionCacheAware(v9);
    return FvepReleaseRemoveLock(a1 + 56);
  }
  if ( (unsigned __int8)v4 >= 2u )
  {
    v9 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(a1 + 1464);
    goto LABEL_10;
  }
  if ( (_BYTE)v4 )
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)(a1 + 1448));
  return FvepReleaseRemoveLock(a1 + 56);
}

```

## disassembly

```asm
0x14002a4e4  push    rbx
0x14002a4e6  push    rbp
0x14002a4e7  push    rsi
0x14002a4e8  push    rdi
0x14002a4e9  sub     rsp, 28h
0x14002a4ed  mov     rbx, rcx
0x14002a4f0  movzx   edi, r8b
0x14002a4f4  mov     rcx, [rcx+930h]
0x14002a4fb  mov     rbp, rdx
0x14002a4fe  cmp     qword ptr [rcx+8], 0
0x14002a503  jnz     short loc_14002A581
0x14002a505  cmp     dword ptr [rbx+928h], 1
0x14002a50c  jnz     short loc_14002A567
0x14002a50e  mov     rax, [rbx+930h]
0x14002a515  lock dec dword ptr [rax]
0x14002a518  cmp     byte ptr [rbx+5C4h], 0
0x14002a51f  jnz     short loc_14002A548
0x14002a521  cmp     dil, 2
0x14002a525  jnb     loc_14002A642
0x14002a52b  cmp     dil, 1
0x14002a52f  jnb     loc_14002A655
0x14002a535  lea     rcx, [rbx+38h]; BugCheckParameter2
0x14002a539  call    FvepReleaseRemoveLock
0x14002a53e  add     rsp, 28h
0x14002a542  pop     rdi
0x14002a543  pop     rsi
0x14002a544  pop     rbp
0x14002a545  pop     rbx
0x14002a546  retn
0x14002a548  cmp     dil, 2
0x14002a54c  jb      loc_14002A620
0x14002a552  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x14002a559  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14002a560  nop     dword ptr [rax+rax+00h]
0x14002a565  jmp     short loc_14002A535
0x14002a567  mov     eax, gs:1A4h
0x14002a56f  mov     ecx, eax
0x14002a571  imul    rax, rcx, 128h
0x14002a578  add     rax, [rbx+930h]
0x14002a57f  jmp     short loc_14002A515
0x14002a581  add     rcx, 10h; SpinLock
0x14002a585  xor     esi, esi
0x14002a587  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002a58e  nop     dword ptr [rax+rax+00h]
0x14002a593  mov     r8, [rbx+930h]
0x14002a59a  mov     r9b, al
0x14002a59d  add     r8, 18h
0x14002a5a1  mov     rdx, [r8]
0x14002a5a4  cmp     rdx, r8
0x14002a5a7  jnz     short loc_14002A610
0x14002a5a9  mov     rcx, [rbx+930h]
0x14002a5b0  mov     dl, r9b; NewIrql
0x14002a5b3  add     rcx, 10h; SpinLock
0x14002a5b7  call    cs:__imp_KeReleaseSpinLock
0x14002a5be  nop     dword ptr [rax+rax+00h]
0x14002a5c3  test    rsi, rsi
0x14002a5c6  jz      loc_14002A505
0x14002a5cc  mov     rcx, [rbx+930h]
0x14002a5d3  mov     rdx, rsi; Entry
0x14002a5d6  mov     rcx, [rcx+8]; Lookaside
0x14002a5da  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002a5e1  nop     dword ptr [rax+rax+00h]
0x14002a5e6  jmp     loc_14002A505
0x14002a5eb  mov     rax, [rdx]
0x14002a5ee  cmp     [rax+8], rdx
0x14002a5f2  jnz     short loc_14002A609
0x14002a5f4  mov     rcx, [rdx+8]
0x14002a5f8  cmp     [rcx], rdx
0x14002a5fb  jnz     short loc_14002A609
0x14002a5fd  mov     [rcx], rax
0x14002a600  mov     rsi, rdx
0x14002a603  mov     [rax+8], rcx
0x14002a607  jmp     short loc_14002A5A9
0x14002a609  mov     ecx, 3
0x14002a60e  int     29h; Win8: RtlFailFast(ecx)
0x14002a610  cmp     [rdx+10h], rbp
0x14002a614  jnz     short loc_14002A61B
0x14002a616  cmp     [rdx+18h], edi
0x14002a619  jz      short loc_14002A5EB
0x14002a61b  mov     rdx, [rdx]
0x14002a61e  jmp     short loc_14002A5A4
0x14002a620  cmp     dil, 1
0x14002a624  jb      loc_14002A535
0x14002a62a  lea     rcx, [rbx+5A8h]; RunRef
0x14002a631  call    cs:__imp_ExReleaseRundownProtection
0x14002a638  nop     dword ptr [rax+rax+00h]
0x14002a63d  jmp     loc_14002A535
0x14002a642  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x14002a649  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14002a650  nop     dword ptr [rax+rax+00h]
0x14002a655  mov     rcx, [rbx+5B0h]
0x14002a65c  jmp     loc_14002A559
```
