# FvepAcquireRundownProtectionOrHold

- ea: `0x14002845c`
- end: `0x140028986`
- name: `FvepAcquireRundownProtectionOrHold`
- size: `1322`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140024b9c`
- `0x140027b28`
- `0x1400281d8`

## callees

- `0x14002845c`
- `0x140029a38`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140028494`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140028520`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140028832`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400288a3`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400288d4`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002890b`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140028938`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140028494`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140028520`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140028832`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400288a3`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400288d4`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002890b`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140028938`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140028855`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140028883`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140028855`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140028883`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400286af`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400286af`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140028962`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140028962`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140028749`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140028749`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400287c9`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400287c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400285a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002860a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002871f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400288ef`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400285a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002860a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002871f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400288ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400286e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002881b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028870`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400288bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028922`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400286e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002881b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028870`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400288bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028922`
- `ntoskrnl!KeBugCheckEx` at `0x1400287ad`
- `ntoskrnl!KeBugCheckEx` at `0x1400287fe`
- `ntoskrnl!KeBugCheckEx` at `0x1400287ad`
- `ntoskrnl!KeBugCheckEx` at `0x1400287fe`

## pseudocode

```c
__int64 __fastcall FvepAcquireRundownProtectionOrHold(__int64 a1, _QWORD *a2, unsigned __int8 a3)
{
  ULONG_PTR v3; // r14
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v5; // rcx
  signed int v8; // edi
  int v9; // ebp
  bool v10; // zf
  volatile signed __int32 *v11; // rax
  struct _NPAGED_LOOKASIDE_LIST *v12; // rcx
  char v14; // r15
  _QWORD *v15; // r8
  _QWORD *v16; // r9
  KIRQL v17; // dl
  _QWORD *v18; // r8
  _QWORD *v19; // r9
  _QWORD *v20; // rcx
  _QWORD *v21; // r8
  _QWORD *v22; // rcx
  _QWORD *v23; // rdx
  KIRQL v24; // al
  __int64 v25; // rcx
  __int64 **v26; // rdx
  NTSTATUS v27; // edx
  signed __int64 v28; // rax
  KSPIN_LOCK *v29; // r12
  KIRQL v30; // r14
  __int64 *v31; // rax
  __int64 *v32; // rsi
  __int64 NewIrqld; // [rsp+70h] [rbp+8h]
  signed __int64 NewIrql; // [rsp+70h] [rbp+8h]
  KIRQL NewIrqla; // [rsp+70h] [rbp+8h]
  KIRQL NewIrqlb; // [rsp+70h] [rbp+8h]
  KIRQL NewIrqlc; // [rsp+70h] [rbp+8h]

  v3 = a1 + 56;
  v5 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(a1 + 104);
  if ( v5 )
  {
    v8 = ExAcquireRundownProtectionCacheAware(v5) == 0 ? 0xC0000056 : 0;
  }
  else
  {
    v27 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 16), *(PVOID *)v3, File, 1u, 0x20u);
    while ( 1 )
    {
      NewIrql = *(_QWORD *)(v3 + 8);
      v28 = NewIrql;
      if ( (NewIrql & 0xFF000000000000LL) != 0 )
        break;
      v8 = v27;
      if ( v27 )
        goto LABEL_40;
      if ( (NewIrql & 0xFF000000000000LL) != 0 )
        KeBugCheckEx(0x120u, 0xEu, v3, 0, (unsigned int)NewIrql);
      LODWORD(NewIrql) = NewIrql + 1;
      if ( v28 == _InterlockedCompareExchange64((volatile signed __int64 *)(v3 + 8), NewIrql, v28) )
        goto LABEL_3;
    }
    if ( !v27 )
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 16), *(PVOID *)v3, 0x20u);
    v8 = -1073741738;
LABEL_40:
    if ( (NewIrql & 0xFF000000000000LL) == 0 )
      KeBugCheckEx(0x120u, 0xEu, v3, v8, (unsigned int)NewIrql);
  }
LABEL_3:
  v9 = 0;
  v10 = v8 == 0;
  if ( v8 >= 0 )
  {
    v14 = 1;
    if ( *(_BYTE *)(a1 + 1476) )
    {
      if ( ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1464)) )
      {
LABEL_11:
        v9 = 2;
LABEL_12:
        v10 = v8 == 0;
        goto LABEL_4;
      }
      if ( a3 < 2u )
      {
        if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 1448)) )
          goto LABEL_22;
        NewIrqlb = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 2256));
        if ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 1448)) )
        {
          v14 = 0;
          v18 = a2 + 21;
          *(_BYTE *)(a2[23] + 3LL) |= 1u;
          v19 = *(_QWORD **)(a1 + 2248);
          if ( *v19 != a1 + 2240 )
            goto LABEL_57;
          *v18 = a1 + 2240;
          a2[22] = v19;
          v8 = 259;
          *v19 = v18;
          *(_QWORD *)(a1 + 2248) = v18;
          FvepReleaseRemoveLock(v3);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 2256), NewIrqlb);
        if ( v14 )
LABEL_22:
          v9 = 1;
        goto LABEL_12;
      }
      v29 = (KSPIN_LOCK *)(a1 + 2256);
      NewIrqla = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 2256));
      if ( !ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1464)) )
      {
        v14 = 0;
        v15 = a2 + 21;
        *(_BYTE *)(a2[23] + 3LL) |= 1u;
        v16 = *(_QWORD **)(a1 + 2248);
        if ( *v16 != a1 + 2240 )
          goto LABEL_57;
        *v15 = a1 + 2240;
        a2[22] = v16;
        v8 = 259;
        *v16 = v15;
        *(_QWORD *)(a1 + 2248) = v15;
        FvepReleaseRemoveLock(v3);
      }
      v17 = NewIrqla;
    }
    else
    {
      v29 = (KSPIN_LOCK *)(a1 + 2256);
      if ( !ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1456)) )
      {
        NewIrqlc = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 2256));
        if ( !ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1456)) )
        {
          v14 = 0;
          *(_BYTE *)(a2[23] + 3LL) |= 1u;
          v20 = a2 + 21;
          v21 = *(_QWORD **)(a1 + 2248);
          if ( *v21 != a1 + 2240 )
            goto LABEL_57;
          *v20 = a1 + 2240;
          v8 = 259;
          a2[22] = v21;
          *v21 = v20;
          *(_QWORD *)(a1 + 2248) = v20;
          FvepReleaseRemoveLock(v3);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 2256), NewIrqlc);
        if ( !v14 )
          goto LABEL_12;
      }
      if ( ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1464)) )
        goto LABEL_11;
      v30 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 2256));
      if ( !ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1464)) )
      {
        v14 = 0;
        if ( a3 >= 2u )
        {
          *(_BYTE *)(a2[23] + 3LL) |= 1u;
          v22 = a2 + 21;
          v23 = *(_QWORD **)(a1 + 2248);
          if ( *v23 != a1 + 2240 )
            goto LABEL_57;
          *v22 = a1 + 2240;
          v8 = 259;
          a2[22] = v23;
          *v23 = v22;
          *(_QWORD *)(a1 + 2248) = v22;
          ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1456));
          FvepReleaseRemoveLock(a1 + 56);
        }
      }
      v9 = 1;
      v17 = v30;
    }
    KeReleaseSpinLock(v29, v17);
    if ( !v14 )
      goto LABEL_12;
    goto LABEL_11;
  }
LABEL_4:
  if ( v10 )
  {
    NewIrqld = a2[15];
    BYTE1(NewIrqld) = v9;
    a2[15] = NewIrqld;
    v11 = *(_DWORD *)(a1 + 2328) == 1
        ? *(volatile signed __int32 **)(a1 + 2336)
        : (volatile signed __int32 *)(*(_QWORD *)(a1 + 2336) + 296LL * HIDWORD(KeGetPcr()[1].LockArray));
    _InterlockedAdd(v11, 1u);
    v12 = *(struct _NPAGED_LOOKASIDE_LIST **)(*(_QWORD *)(a1 + 2336) + 8LL);
    if ( v12 )
    {
      v31 = (__int64 *)ExAllocateFromNPagedLookasideList(v12);
      v32 = v31;
      if ( v31 )
      {
        v31[2] = (__int64)a2;
        *((_DWORD *)v31 + 6) = v9;
        v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(a1 + 2336) + 16LL));
        v25 = *(_QWORD *)(a1 + 2336) + 24LL;
        v26 = *(__int64 ***)(*(_QWORD *)(a1 + 2336) + 32LL);
        if ( *v26 == (__int64 *)v25 )
        {
          *v32 = v25;
          v32[1] = (__int64)v26;
          *v26 = v32;
          *(_QWORD *)(v25 + 8) = v32;
          KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 2336) + 16LL), v24);
          return (unsigned int)v8;
        }
LABEL_57:
        __fastfail(3u);
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14002845c  mov     [rsp+arg_8], rbx
0x140028461  mov     [rsp+arg_10], r8b
0x140028466  push    rbp
0x140028467  push    rsi
0x140028468  push    rdi
0x140028469  push    r12
0x14002846b  push    r13
0x14002846d  push    r14
0x14002846f  push    r15
0x140028471  sub     rsp, 30h
0x140028475  lea     r14, [rcx+38h]
0x140028479  mov     rbx, rcx
0x14002847c  mov     rcx, [r14+30h]; RunRefCacheAware
0x140028480  mov     r12b, r8b
0x140028483  mov     r13, rdx
0x140028486  mov     esi, 1
0x14002848b  test    rcx, rcx
0x14002848e  jz      loc_140028730
0x140028494  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14002849b  nop     dword ptr [rax+rax+00h]
0x1400284a0  neg     al
0x1400284a2  sbb     edi, edi
0x1400284a4  not     edi
0x1400284a6  and     edi, 0C0000056h
0x1400284ac  xor     ebp, ebp
0x1400284ae  test    edi, edi
0x1400284b0  jns     short loc_140028509
0x1400284b2  jnz     short loc_1400284F1
0x1400284b4  mov     rax, [r13+78h]
0x1400284b8  mov     qword ptr [rsp+68h+NewIrql], rax
0x1400284bd  mov     [rsp+71h], bpl
0x1400284c2  mov     rax, qword ptr [rsp+68h+NewIrql]
0x1400284c7  mov     [r13+78h], rax
0x1400284cb  cmp     [rbx+918h], esi
0x1400284d1  jnz     short loc_140028540
0x1400284d3  mov     rax, [rbx+920h]
0x1400284da  lock add [rax], esi
0x1400284dd  mov     rax, [rbx+920h]
0x1400284e4  mov     rcx, [rax+8]; Lookaside
0x1400284e8  test    rcx, rcx
0x1400284eb  jnz     loc_140028962
0x1400284f1  mov     rbx, [rsp+68h+arg_8]
0x1400284f6  mov     eax, edi
0x1400284f8  add     rsp, 30h
0x1400284fc  pop     r15
0x1400284fe  pop     r14
0x140028500  pop     r13
0x140028502  pop     r12
0x140028504  pop     rdi
0x140028505  pop     rsi
0x140028506  pop     rbp
0x140028507  retn
0x140028509  mov     r15b, sil
0x14002850c  cmp     [rbx+5C4h], bpl
0x140028513  jz      loc_14002889C
0x140028519  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x140028520  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140028527  nop     dword ptr [rax+rax+00h]
0x14002852c  test    al, al
0x14002852e  jz      loc_14002880B
0x140028534  mov     ebp, 2
0x140028539  test    edi, edi
0x14002853b  jmp     loc_1400284B2
0x140028540  mov     eax, gs:1A4h
0x140028548  mov     ecx, eax
0x14002854a  imul    rax, rcx, 128h
0x140028551  add     rax, [rbx+920h]
0x140028558  jmp     short loc_1400284DA
0x14002855a  mov     rcx, [r13+0B8h]
0x140028561  lea     rdx, [rbx+8C0h]
0x140028568  xor     r15b, r15b
0x14002856b  lea     r8, [r13+0A8h]
0x140028572  or      [rcx+3], sil
0x140028576  mov     r9, [rdx+8]
0x14002857a  cmp     [r9], rdx
0x14002857d  jnz     loc_14002897F
0x140028583  mov     [r8], rdx
0x140028586  mov     rcx, r14; BugCheckParameter2
0x140028589  mov     [r8+8], r9
0x14002858d  mov     edi, 103h
0x140028592  mov     [r9], r8
0x140028595  mov     [rdx+8], r8
0x140028599  call    FvepReleaseRemoveLock
0x14002859e  mov     dl, [rsp+68h+NewIrql]; NewIrql
0x1400285a2  mov     rcx, r12; SpinLock
0x1400285a5  call    cs:__imp_KeReleaseSpinLock
0x1400285ac  nop     dword ptr [rax+rax+00h]
0x1400285b1  test    r15b, r15b
0x1400285b4  jz      short loc_140028539
0x1400285b6  jmp     loc_140028534
0x1400285bb  mov     rcx, [r13+0B8h]
0x1400285c2  lea     rdx, [rbx+8C0h]
0x1400285c9  xor     r15b, r15b
0x1400285cc  lea     r8, [r13+0A8h]
0x1400285d3  or      [rcx+3], sil
0x1400285d7  mov     r9, [rdx+8]
0x1400285db  cmp     [r9], rdx
0x1400285de  jnz     loc_14002897F
0x1400285e4  mov     [r8], rdx
0x1400285e7  mov     rcx, r14; BugCheckParameter2
0x1400285ea  mov     [r8+8], r9
0x1400285ee  mov     edi, 103h
0x1400285f3  mov     [r9], r8
0x1400285f6  mov     [rdx+8], r8
0x1400285fa  call    FvepReleaseRemoveLock
0x1400285ff  mov     dl, [rsp+68h+NewIrql]; NewIrql
0x140028603  lea     rcx, [rbx+8D0h]; SpinLock
0x14002860a  call    cs:__imp_KeReleaseSpinLock
0x140028611  nop     dword ptr [rax+rax+00h]
0x140028616  test    r15b, r15b
0x140028619  jz      loc_140028539
0x14002861f  mov     ebp, esi
0x140028621  jmp     loc_140028539
0x140028626  mov     rcx, [r13+0B8h]
0x14002862d  lea     rdx, [rbx+8C0h]
0x140028634  xor     r15b, r15b
0x140028637  or      [rcx+3], sil
0x14002863b  lea     rcx, [r13+0A8h]
0x140028642  mov     r8, [rdx+8]
0x140028646  cmp     [r8], rdx
0x140028649  jnz     loc_14002897F
0x14002864f  mov     [rcx], rdx
0x140028652  mov     edi, 103h
0x140028657  mov     [rcx+8], r8
0x14002865b  mov     [r8], rcx
0x14002865e  mov     [rdx+8], rcx
0x140028662  mov     rcx, r14; BugCheckParameter2
0x140028665  call    FvepReleaseRemoveLock
0x14002866a  jmp     loc_1400288E8
0x14002866f  mov     rcx, [r13+0B8h]
0x140028676  lea     rax, [rbx+8C0h]
0x14002867d  or      [rcx+3], sil
0x140028681  lea     rcx, [r13+0A8h]
0x140028688  mov     rdx, [rax+8]
0x14002868c  cmp     [rdx], rax
0x14002868f  jnz     loc_14002897F
0x140028695  mov     [rcx], rax
0x140028698  mov     edi, 103h
0x14002869d  mov     [rcx+8], rdx
0x1400286a1  mov     [rdx], rcx
0x1400286a4  mov     [rax+8], rcx
0x1400286a8  mov     rcx, [rbx+5B0h]; RunRefCacheAware
0x1400286af  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400286b6  nop     dword ptr [rax+rax+00h]
0x1400286bb  lea     rcx, [rbx+38h]; BugCheckParameter2
0x1400286bf  call    FvepReleaseRemoveLock
0x1400286c4  mov     ebp, esi
0x1400286c6  mov     dl, r14b
0x1400286c9  jmp     loc_1400285A2
0x1400286ce  mov     [rax+10h], r13
0x1400286d2  mov     [rax+18h], ebp
0x1400286d5  mov     rcx, [rbx+920h]
0x1400286dc  add     rcx, 10h; SpinLock
0x1400286e0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400286e7  nop     dword ptr [rax+rax+00h]
0x1400286ec  mov     rcx, [rbx+920h]
0x1400286f3  add     rcx, 18h
0x1400286f7  mov     rdx, [rcx+8]
0x1400286fb  cmp     [rdx], rcx
0x1400286fe  jnz     loc_14002897F
0x140028704  mov     [rsi], rcx
0x140028707  mov     [rsi+8], rdx
0x14002870b  mov     [rdx], rsi
0x14002870e  mov     dl, al; NewIrql
0x140028710  mov     [rcx+8], rsi
0x140028714  mov     rcx, [rbx+920h]
0x14002871b  add     rcx, 10h; SpinLock
0x14002871f  call    cs:__imp_KeReleaseSpinLock
0x140028726  nop     dword ptr [rax+rax+00h]
0x14002872b  jmp     loc_1400284F1
0x140028730  mov     rdx, [r14]; Tag
0x140028733  lea     r8, File; File
0x14002873a  mov     r9d, esi; Line
0x14002873d  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x140028745  lea     rcx, [r14+10h]; RemoveLock
0x140028749  call    cs:__imp_IoAcquireRemoveLockEx
0x140028750  nop     dword ptr [rax+rax+00h]
0x140028755  mov     edx, eax
0x140028757  mov     r15d, 0FF0000h
0x14002875d  mov     rax, [r14+8]
0x140028761  mov     rcx, rax
0x140028764  mov     qword ptr [rsp+68h+NewIrql], rax
0x140028769  shr     rcx, 20h
0x14002876d  test    r15d, ecx
0x140028770  jnz     short loc_1400287BA
0x140028772  mov     edi, edx
0x140028774  test    edx, edx
0x140028776  jnz     short loc_1400287DA
0x140028778  test    [rsp+74h], r15d
0x14002877d  jnz     short loc_140028795
0x14002877f  add     dword ptr [rsp+68h+NewIrql], esi
0x140028783  mov     rcx, qword ptr [rsp+68h+NewIrql]
0x140028788  lock cmpxchg [r14+8], rcx
0x14002878e  jnz     short loc_14002875D
0x140028790  jmp     loc_1400284AC
0x140028795  mov     eax, dword ptr [rsp+68h+NewIrql]
0x140028799  xor     r9d, r9d; BugCheckParameter3
0x14002879c  mov     r8, r14; BugCheckParameter2
0x14002879f  mov     qword ptr [rsp+68h+RemlockSize], rax; BugCheckParameter4
0x1400287a4  mov     ecx, 120h; BugCheckCode
0x1400287a9  lea     edx, [r9+0Eh]; BugCheckParameter1
0x1400287ad  call    cs:__imp_KeBugCheckEx
0x1400287ba  test    edx, edx
0x1400287bc  jnz     short loc_1400287D5
0x1400287be  lea     r8d, [rdx+20h]; RemlockSize
0x1400287c2  mov     rdx, [r14]; Tag
0x1400287c5  lea     rcx, [r14+10h]; RemoveLock
0x1400287c9  call    cs:__imp_IoReleaseRemoveLockEx
0x1400287d0  nop     dword ptr [rax+rax+00h]
0x1400287d5  mov     edi, 0C0000056h
0x1400287da  test    [rsp+74h], r15d
0x1400287df  jnz     loc_1400284AC
0x1400287e5  mov     eax, dword ptr [rsp+68h+NewIrql]
0x1400287e9  mov     r8, r14; BugCheckParameter2
0x1400287ec  movsxd  r9, edi; BugCheckParameter3
0x1400287ef  mov     edx, 0Eh; BugCheckParameter1
0x1400287f4  mov     ecx, 120h; BugCheckCode
0x1400287f9  mov     qword ptr [rsp+68h+RemlockSize], rax; BugCheckParameter4
0x1400287fe  call    cs:__imp_KeBugCheckEx
0x14002880b  cmp     r12b, 2
0x14002880f  jb      short loc_14002884B
0x140028811  lea     r12, [rbx+8D0h]
0x140028818  mov     rcx, r12; SpinLock
0x14002881b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140028822  nop     dword ptr [rax+rax+00h]
0x140028827  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x14002882e  mov     [rsp+68h+NewIrql], al
0x140028832  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140028839  nop     dword ptr [rax+rax+00h]
0x14002883e  test    al, al
0x140028840  jnz     loc_14002859E
0x140028846  jmp     loc_14002855A
0x14002884b  lea     r12, [rbx+5A8h]
0x140028852  mov     rcx, r12; RunRef
0x140028855  call    cs:__imp_ExAcquireRundownProtection
0x14002885c  nop     dword ptr [rax+rax+00h]
0x140028861  test    al, al
0x140028863  jnz     loc_14002861F
0x140028869  lea     rcx, [rbx+8D0h]; SpinLock
0x140028870  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140028877  nop     dword ptr [rax+rax+00h]
0x14002887c  mov     rcx, r12; RunRef
0x14002887f  mov     [rsp+68h+NewIrql], al
0x140028883  call    cs:__imp_ExAcquireRundownProtection
0x14002888a  nop     dword ptr [rax+rax+00h]
0x14002888f  test    al, al
0x140028891  jnz     loc_1400285FF
0x140028897  jmp     loc_1400285BB
0x14002889c  mov     rcx, [rbx+5B0h]; RunRefCacheAware
0x1400288a3  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x1400288aa  nop     dword ptr [rax+rax+00h]
0x1400288af  lea     r12, [rbx+8D0h]
0x1400288b6  test    al, al
0x1400288b8  jnz     short loc_140028904
0x1400288ba  mov     rcx, r12; SpinLock
0x1400288bd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400288c4  nop     dword ptr [rax+rax+00h]
0x1400288c9  mov     rcx, [rbx+5B0h]; RunRefCacheAware
0x1400288d0  mov     [rsp+68h+NewIrql], al
0x1400288d4  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x1400288db  nop     dword ptr [rax+rax+00h]
0x1400288e0  test    al, al
0x1400288e2  jz      loc_140028626
0x1400288e8  mov     dl, [rsp+68h+NewIrql]; NewIrql
0x1400288ec  mov     rcx, r12; SpinLock
0x1400288ef  call    cs:__imp_KeReleaseSpinLock
0x1400288f6  nop     dword ptr [rax+rax+00h]
0x1400288fb  test    r15b, r15b
0x1400288fe  jz      loc_140028539
0x140028904  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x14002890b  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140028912  nop     dword ptr [rax+rax+00h]
0x140028917  test    al, al
0x140028919  jnz     loc_140028534
0x14002891f  mov     rcx, r12; SpinLock
0x140028922  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140028929  nop     dword ptr [rax+rax+00h]
0x14002892e  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x140028935  mov     r14b, al
0x140028938  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14002893f  nop     dword ptr [rax+rax+00h]
0x140028944  test    al, al
0x140028946  jnz     loc_1400286C4
0x14002894c  xor     r15b, r15b
0x14002894f  cmp     [rsp+68h+arg_10], 2
0x140028957  jb      loc_1400286C4
0x14002895d  jmp     loc_14002866F
0x140028962  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140028969  nop     dword ptr [rax+rax+00h]
0x14002896e  mov     rsi, rax
0x140028971  test    rax, rax
0x140028974  jz      loc_1400284F1
0x14002897a  jmp     loc_1400286CE
0x14002897f  mov     ecx, 3
0x140028984  int     29h; Win8: RtlFailFast(ecx)
```
