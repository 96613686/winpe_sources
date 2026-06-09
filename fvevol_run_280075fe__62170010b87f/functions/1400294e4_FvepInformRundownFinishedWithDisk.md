# FvepInformRundownFinishedWithDisk

- ea: `0x1400294e4`
- end: `0x140029661`
- name: `FvepInformRundownFinishedWithDisk`
- size: `381`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140024040`
- `0x140024b9c`
- `0x140027b28`
- `0x140028c84`
- `0x1400293a0`
- `0x1400293f0`
- `0x1400b9714`
- `0x1400b9900`
- `0x1400b9f84`
- `0x1400d4980`
- `0x1400dc768`
- `0x1400dc9d0`
- `0x1400e02d8`

## callees

- `0x1400294e4`
- `0x140029a38`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140029559`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140029649`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140029559`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140029649`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400295da`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400295da`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140029631`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140029631`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400295b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400295b7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029587`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029587`

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
  v5 = *(_QWORD *)(a1 + 2336);
  if ( *(_QWORD *)(v5 + 8) )
  {
    v10 = 0;
    v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 16));
    v12 = (_QWORD *)(*(_QWORD *)(a1 + 2336) + 24LL);
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
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 2336) + 16LL), v11);
    if ( v10 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(a1 + 2336) + 8LL), v10);
  }
  if ( *(_DWORD *)(a1 + 2328) == 1 )
    v7 = *(volatile signed __int32 **)(a1 + 2336);
  else
    v7 = (volatile signed __int32 *)(*(_QWORD *)(a1 + 2336) + 296LL * HIDWORD(KeGetPcr()[1].LockArray));
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
0x1400294e4  push    rbx
0x1400294e6  push    rbp
0x1400294e7  push    rsi
0x1400294e8  push    rdi
0x1400294e9  sub     rsp, 28h
0x1400294ed  mov     rbx, rcx
0x1400294f0  movzx   edi, r8b
0x1400294f4  mov     rcx, [rcx+920h]
0x1400294fb  mov     rbp, rdx
0x1400294fe  cmp     qword ptr [rcx+8], 0
0x140029503  jnz     short loc_140029581
0x140029505  cmp     dword ptr [rbx+918h], 1
0x14002950c  jnz     short loc_140029567
0x14002950e  mov     rax, [rbx+920h]
0x140029515  lock dec dword ptr [rax]
0x140029518  cmp     byte ptr [rbx+5C4h], 0
0x14002951f  jnz     short loc_140029548
0x140029521  cmp     dil, 2
0x140029525  jnb     loc_140029642
0x14002952b  cmp     dil, 1
0x14002952f  jnb     loc_140029655
0x140029535  lea     rcx, [rbx+38h]; BugCheckParameter2
0x140029539  call    FvepReleaseRemoveLock
0x14002953e  add     rsp, 28h
0x140029542  pop     rdi
0x140029543  pop     rsi
0x140029544  pop     rbp
0x140029545  pop     rbx
0x140029546  retn
0x140029548  cmp     dil, 2
0x14002954c  jb      loc_140029620
0x140029552  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x140029559  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140029560  nop     dword ptr [rax+rax+00h]
0x140029565  jmp     short loc_140029535
0x140029567  mov     eax, gs:1A4h
0x14002956f  mov     ecx, eax
0x140029571  imul    rax, rcx, 128h
0x140029578  add     rax, [rbx+920h]
0x14002957f  jmp     short loc_140029515
0x140029581  add     rcx, 10h; SpinLock
0x140029585  xor     esi, esi
0x140029587  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002958e  nop     dword ptr [rax+rax+00h]
0x140029593  mov     r8, [rbx+920h]
0x14002959a  mov     r9b, al
0x14002959d  add     r8, 18h
0x1400295a1  mov     rdx, [r8]
0x1400295a4  cmp     rdx, r8
0x1400295a7  jnz     short loc_140029610
0x1400295a9  mov     rcx, [rbx+920h]
0x1400295b0  mov     dl, r9b; NewIrql
0x1400295b3  add     rcx, 10h; SpinLock
0x1400295b7  call    cs:__imp_KeReleaseSpinLock
0x1400295be  nop     dword ptr [rax+rax+00h]
0x1400295c3  test    rsi, rsi
0x1400295c6  jz      loc_140029505
0x1400295cc  mov     rcx, [rbx+920h]
0x1400295d3  mov     rdx, rsi; Entry
0x1400295d6  mov     rcx, [rcx+8]; Lookaside
0x1400295da  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400295e1  nop     dword ptr [rax+rax+00h]
0x1400295e6  jmp     loc_140029505
0x1400295eb  mov     rax, [rdx]
0x1400295ee  cmp     [rax+8], rdx
0x1400295f2  jnz     short loc_140029609
0x1400295f4  mov     rcx, [rdx+8]
0x1400295f8  cmp     [rcx], rdx
0x1400295fb  jnz     short loc_140029609
0x1400295fd  mov     [rcx], rax
0x140029600  mov     rsi, rdx
0x140029603  mov     [rax+8], rcx
0x140029607  jmp     short loc_1400295A9
0x140029609  mov     ecx, 3
0x14002960e  int     29h; Win8: RtlFailFast(ecx)
0x140029610  cmp     [rdx+10h], rbp
0x140029614  jnz     short loc_14002961B
0x140029616  cmp     [rdx+18h], edi
0x140029619  jz      short loc_1400295EB
0x14002961b  mov     rdx, [rdx]
0x14002961e  jmp     short loc_1400295A4
0x140029620  cmp     dil, 1
0x140029624  jb      loc_140029535
0x14002962a  lea     rcx, [rbx+5A8h]; RunRef
0x140029631  call    cs:__imp_ExReleaseRundownProtection
0x140029638  nop     dword ptr [rax+rax+00h]
0x14002963d  jmp     loc_140029535
0x140029642  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x140029649  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140029650  nop     dword ptr [rax+rax+00h]
0x140029655  mov     rcx, [rbx+5B0h]
0x14002965c  jmp     loc_140029559
```
