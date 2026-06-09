# FvepAcquireRundownProtectionOrHold

- ea: `0x14002945c`
- end: `0x140029986`
- name: `FvepAcquireRundownProtectionOrHold`
- size: `1322`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140025b9c`
- `0x140028b28`
- `0x1400291d8`

## callees

- `0x14002945c`
- `0x14002aa38`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140029494`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140029520`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140029832`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400298a3`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400298d4`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002990b`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140029938`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140029494`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140029520`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140029832`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400298a3`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400298d4`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002990b`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140029938`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140029855`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140029883`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140029855`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140029883`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400296af`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400296af`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140029962`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140029962`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140029749`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140029749`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400297c9`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400297c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400295a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002960a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002971f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400298ef`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400295a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002960a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002971f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400298ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400296e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002981b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029870`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400298bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029922`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400296e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002981b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029870`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400298bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029922`
- `ntoskrnl!KeBugCheckEx` at `0x1400297ad`
- `ntoskrnl!KeBugCheckEx` at `0x1400297fe`
- `ntoskrnl!KeBugCheckEx` at `0x1400297ad`
- `ntoskrnl!KeBugCheckEx` at `0x1400297fe`

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
        NewIrqlb = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 2272));
        if ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 1448)) )
        {
          v14 = 0;
          v18 = a2 + 21;
          *(_BYTE *)(a2[23] + 3LL) |= 1u;
          v19 = *(_QWORD **)(a1 + 2264);
          if ( *v19 != a1 + 2256 )
            goto LABEL_57;
          *v18 = a1 + 2256;
          a2[22] = v19;
          v8 = 259;
          *v19 = v18;
          *(_QWORD *)(a1 + 2264) = v18;
          FvepReleaseRemoveLock(v3);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 2272), NewIrqlb);
        if ( v14 )
LABEL_22:
          v9 = 1;
        goto LABEL_12;
      }
      v29 = (KSPIN_LOCK *)(a1 + 2272);
      NewIrqla = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 2272));
      if ( !ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1464)) )
      {
        v14 = 0;
        v15 = a2 + 21;
        *(_BYTE *)(a2[23] + 3LL) |= 1u;
        v16 = *(_QWORD **)(a1 + 2264);
        if ( *v16 != a1 + 2256 )
          goto LABEL_57;
        *v15 = a1 + 2256;
        a2[22] = v16;
        v8 = 259;
        *v16 = v15;
        *(_QWORD *)(a1 + 2264) = v15;
        FvepReleaseRemoveLock(v3);
      }
      v17 = NewIrqla;
    }
    else
    {
      v29 = (KSPIN_LOCK *)(a1 + 2272);
      if ( !ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1456)) )
      {
        NewIrqlc = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 2272));
        if ( !ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1456)) )
        {
          v14 = 0;
          *(_BYTE *)(a2[23] + 3LL) |= 1u;
          v20 = a2 + 21;
          v21 = *(_QWORD **)(a1 + 2264);
          if ( *v21 != a1 + 2256 )
            goto LABEL_57;
          *v20 = a1 + 2256;
          v8 = 259;
          a2[22] = v21;
          *v21 = v20;
          *(_QWORD *)(a1 + 2264) = v20;
          FvepReleaseRemoveLock(v3);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 2272), NewIrqlc);
        if ( !v14 )
          goto LABEL_12;
      }
      if ( ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1464)) )
        goto LABEL_11;
      v30 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 2272));
      if ( !ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1464)) )
      {
        v14 = 0;
        if ( a3 >= 2u )
        {
          *(_BYTE *)(a2[23] + 3LL) |= 1u;
          v22 = a2 + 21;
          v23 = *(_QWORD **)(a1 + 2264);
          if ( *v23 != a1 + 2256 )
            goto LABEL_57;
          *v22 = a1 + 2256;
          v8 = 259;
          a2[22] = v23;
          *v23 = v22;
          *(_QWORD *)(a1 + 2264) = v22;
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
    v11 = *(_DWORD *)(a1 + 2344) == 1
        ? *(volatile signed __int32 **)(a1 + 2352)
        : (volatile signed __int32 *)(*(_QWORD *)(a1 + 2352) + 296LL * HIDWORD(KeGetPcr()[1].LockArray));
    _InterlockedAdd(v11, 1u);
    v12 = *(struct _NPAGED_LOOKASIDE_LIST **)(*(_QWORD *)(a1 + 2352) + 8LL);
    if ( v12 )
    {
      v31 = (__int64 *)ExAllocateFromNPagedLookasideList(v12);
      v32 = v31;
      if ( v31 )
      {
        v31[2] = (__int64)a2;
        *((_DWORD *)v31 + 6) = v9;
        v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(a1 + 2352) + 16LL));
        v25 = *(_QWORD *)(a1 + 2352) + 24LL;
        v26 = *(__int64 ***)(*(_QWORD *)(a1 + 2352) + 32LL);
        if ( *v26 == (__int64 *)v25 )
        {
          *v32 = v25;
          v32[1] = (__int64)v26;
          *v26 = v32;
          *(_QWORD *)(v25 + 8) = v32;
          KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 2352) + 16LL), v24);
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
0x14002945c  mov     [rsp+arg_8], rbx
0x140029461  mov     [rsp+arg_10], r8b
0x140029466  push    rbp
0x140029467  push    rsi
0x140029468  push    rdi
0x140029469  push    r12
0x14002946b  push    r13
0x14002946d  push    r14
0x14002946f  push    r15
0x140029471  sub     rsp, 30h
0x140029475  lea     r14, [rcx+38h]
0x140029479  mov     rbx, rcx
0x14002947c  mov     rcx, [r14+30h]; RunRefCacheAware
0x140029480  mov     r12b, r8b
0x140029483  mov     r13, rdx
0x140029486  mov     esi, 1
0x14002948b  test    rcx, rcx
0x14002948e  jz      loc_140029730
0x140029494  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14002949b  nop     dword ptr [rax+rax+00h]
0x1400294a0  neg     al
0x1400294a2  sbb     edi, edi
0x1400294a4  not     edi
0x1400294a6  and     edi, 0C0000056h
0x1400294ac  xor     ebp, ebp
0x1400294ae  test    edi, edi
0x1400294b0  jns     short loc_140029509
0x1400294b2  jnz     short loc_1400294F1
0x1400294b4  mov     rax, [r13+78h]
0x1400294b8  mov     qword ptr [rsp+68h+NewIrql], rax
0x1400294bd  mov     [rsp+71h], bpl
0x1400294c2  mov     rax, qword ptr [rsp+68h+NewIrql]
0x1400294c7  mov     [r13+78h], rax
0x1400294cb  cmp     [rbx+928h], esi
0x1400294d1  jnz     short loc_140029540
0x1400294d3  mov     rax, [rbx+930h]
0x1400294da  lock add [rax], esi
0x1400294dd  mov     rax, [rbx+930h]
0x1400294e4  mov     rcx, [rax+8]; Lookaside
0x1400294e8  test    rcx, rcx
0x1400294eb  jnz     loc_140029962
0x1400294f1  mov     rbx, [rsp+68h+arg_8]
0x1400294f6  mov     eax, edi
0x1400294f8  add     rsp, 30h
0x1400294fc  pop     r15
0x1400294fe  pop     r14
0x140029500  pop     r13
0x140029502  pop     r12
0x140029504  pop     rdi
0x140029505  pop     rsi
0x140029506  pop     rbp
0x140029507  retn
0x140029509  mov     r15b, sil
0x14002950c  cmp     [rbx+5C4h], bpl
0x140029513  jz      loc_14002989C
0x140029519  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x140029520  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140029527  nop     dword ptr [rax+rax+00h]
0x14002952c  test    al, al
0x14002952e  jz      loc_14002980B
0x140029534  mov     ebp, 2
0x140029539  test    edi, edi
0x14002953b  jmp     loc_1400294B2
0x140029540  mov     eax, gs:1A4h
0x140029548  mov     ecx, eax
0x14002954a  imul    rax, rcx, 128h
0x140029551  add     rax, [rbx+930h]
0x140029558  jmp     short loc_1400294DA
0x14002955a  mov     rcx, [r13+0B8h]
0x140029561  lea     rdx, [rbx+8D0h]
0x140029568  xor     r15b, r15b
0x14002956b  lea     r8, [r13+0A8h]
0x140029572  or      [rcx+3], sil
0x140029576  mov     r9, [rdx+8]
0x14002957a  cmp     [r9], rdx
0x14002957d  jnz     loc_14002997F
0x140029583  mov     [r8], rdx
0x140029586  mov     rcx, r14; BugCheckParameter2
0x140029589  mov     [r8+8], r9
0x14002958d  mov     edi, 103h
0x140029592  mov     [r9], r8
0x140029595  mov     [rdx+8], r8
0x140029599  call    FvepReleaseRemoveLock
0x14002959e  mov     dl, [rsp+68h+NewIrql]; NewIrql
0x1400295a2  mov     rcx, r12; SpinLock
0x1400295a5  call    cs:__imp_KeReleaseSpinLock
0x1400295ac  nop     dword ptr [rax+rax+00h]
0x1400295b1  test    r15b, r15b
0x1400295b4  jz      short loc_140029539
0x1400295b6  jmp     loc_140029534
0x1400295bb  mov     rcx, [r13+0B8h]
0x1400295c2  lea     rdx, [rbx+8D0h]
0x1400295c9  xor     r15b, r15b
0x1400295cc  lea     r8, [r13+0A8h]
0x1400295d3  or      [rcx+3], sil
0x1400295d7  mov     r9, [rdx+8]
0x1400295db  cmp     [r9], rdx
0x1400295de  jnz     loc_14002997F
0x1400295e4  mov     [r8], rdx
0x1400295e7  mov     rcx, r14; BugCheckParameter2
0x1400295ea  mov     [r8+8], r9
0x1400295ee  mov     edi, 103h
0x1400295f3  mov     [r9], r8
0x1400295f6  mov     [rdx+8], r8
0x1400295fa  call    FvepReleaseRemoveLock
0x1400295ff  mov     dl, [rsp+68h+NewIrql]; NewIrql
0x140029603  lea     rcx, [rbx+8E0h]; SpinLock
0x14002960a  call    cs:__imp_KeReleaseSpinLock
0x140029611  nop     dword ptr [rax+rax+00h]
0x140029616  test    r15b, r15b
0x140029619  jz      loc_140029539
0x14002961f  mov     ebp, esi
0x140029621  jmp     loc_140029539
0x140029626  mov     rcx, [r13+0B8h]
0x14002962d  lea     rdx, [rbx+8D0h]
0x140029634  xor     r15b, r15b
0x140029637  or      [rcx+3], sil
0x14002963b  lea     rcx, [r13+0A8h]
0x140029642  mov     r8, [rdx+8]
0x140029646  cmp     [r8], rdx
0x140029649  jnz     loc_14002997F
0x14002964f  mov     [rcx], rdx
0x140029652  mov     edi, 103h
0x140029657  mov     [rcx+8], r8
0x14002965b  mov     [r8], rcx
0x14002965e  mov     [rdx+8], rcx
0x140029662  mov     rcx, r14; BugCheckParameter2
0x140029665  call    FvepReleaseRemoveLock
0x14002966a  jmp     loc_1400298E8
0x14002966f  mov     rcx, [r13+0B8h]
0x140029676  lea     rax, [rbx+8D0h]
0x14002967d  or      [rcx+3], sil
0x140029681  lea     rcx, [r13+0A8h]
0x140029688  mov     rdx, [rax+8]
0x14002968c  cmp     [rdx], rax
0x14002968f  jnz     loc_14002997F
0x140029695  mov     [rcx], rax
0x140029698  mov     edi, 103h
0x14002969d  mov     [rcx+8], rdx
0x1400296a1  mov     [rdx], rcx
0x1400296a4  mov     [rax+8], rcx
0x1400296a8  mov     rcx, [rbx+5B0h]; RunRefCacheAware
0x1400296af  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400296b6  nop     dword ptr [rax+rax+00h]
0x1400296bb  lea     rcx, [rbx+38h]; BugCheckParameter2
0x1400296bf  call    FvepReleaseRemoveLock
0x1400296c4  mov     ebp, esi
0x1400296c6  mov     dl, r14b
0x1400296c9  jmp     loc_1400295A2
0x1400296ce  mov     [rax+10h], r13
0x1400296d2  mov     [rax+18h], ebp
0x1400296d5  mov     rcx, [rbx+930h]
0x1400296dc  add     rcx, 10h; SpinLock
0x1400296e0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400296e7  nop     dword ptr [rax+rax+00h]
0x1400296ec  mov     rcx, [rbx+930h]
0x1400296f3  add     rcx, 18h
0x1400296f7  mov     rdx, [rcx+8]
0x1400296fb  cmp     [rdx], rcx
0x1400296fe  jnz     loc_14002997F
0x140029704  mov     [rsi], rcx
0x140029707  mov     [rsi+8], rdx
0x14002970b  mov     [rdx], rsi
0x14002970e  mov     dl, al; NewIrql
0x140029710  mov     [rcx+8], rsi
0x140029714  mov     rcx, [rbx+930h]
0x14002971b  add     rcx, 10h; SpinLock
0x14002971f  call    cs:__imp_KeReleaseSpinLock
0x140029726  nop     dword ptr [rax+rax+00h]
0x14002972b  jmp     loc_1400294F1
0x140029730  mov     rdx, [r14]; Tag
0x140029733  lea     r8, File; File
0x14002973a  mov     r9d, esi; Line
0x14002973d  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x140029745  lea     rcx, [r14+10h]; RemoveLock
0x140029749  call    cs:__imp_IoAcquireRemoveLockEx
0x140029750  nop     dword ptr [rax+rax+00h]
0x140029755  mov     edx, eax
0x140029757  mov     r15d, 0FF0000h
0x14002975d  mov     rax, [r14+8]
0x140029761  mov     rcx, rax
0x140029764  mov     qword ptr [rsp+68h+NewIrql], rax
0x140029769  shr     rcx, 20h
0x14002976d  test    r15d, ecx
0x140029770  jnz     short loc_1400297BA
0x140029772  mov     edi, edx
0x140029774  test    edx, edx
0x140029776  jnz     short loc_1400297DA
0x140029778  test    [rsp+74h], r15d
0x14002977d  jnz     short loc_140029795
0x14002977f  add     dword ptr [rsp+68h+NewIrql], esi
0x140029783  mov     rcx, qword ptr [rsp+68h+NewIrql]
0x140029788  lock cmpxchg [r14+8], rcx
0x14002978e  jnz     short loc_14002975D
0x140029790  jmp     loc_1400294AC
0x140029795  mov     eax, dword ptr [rsp+68h+NewIrql]
0x140029799  xor     r9d, r9d; BugCheckParameter3
0x14002979c  mov     r8, r14; BugCheckParameter2
0x14002979f  mov     qword ptr [rsp+68h+RemlockSize], rax; BugCheckParameter4
0x1400297a4  mov     ecx, 120h; BugCheckCode
0x1400297a9  lea     edx, [r9+0Eh]; BugCheckParameter1
0x1400297ad  call    cs:__imp_KeBugCheckEx
0x1400297ba  test    edx, edx
0x1400297bc  jnz     short loc_1400297D5
0x1400297be  lea     r8d, [rdx+20h]; RemlockSize
0x1400297c2  mov     rdx, [r14]; Tag
0x1400297c5  lea     rcx, [r14+10h]; RemoveLock
0x1400297c9  call    cs:__imp_IoReleaseRemoveLockEx
0x1400297d0  nop     dword ptr [rax+rax+00h]
0x1400297d5  mov     edi, 0C0000056h
0x1400297da  test    [rsp+74h], r15d
0x1400297df  jnz     loc_1400294AC
0x1400297e5  mov     eax, dword ptr [rsp+68h+NewIrql]
0x1400297e9  mov     r8, r14; BugCheckParameter2
0x1400297ec  movsxd  r9, edi; BugCheckParameter3
0x1400297ef  mov     edx, 0Eh; BugCheckParameter1
0x1400297f4  mov     ecx, 120h; BugCheckCode
0x1400297f9  mov     qword ptr [rsp+68h+RemlockSize], rax; BugCheckParameter4
0x1400297fe  call    cs:__imp_KeBugCheckEx
0x14002980b  cmp     r12b, 2
0x14002980f  jb      short loc_14002984B
0x140029811  lea     r12, [rbx+8E0h]
0x140029818  mov     rcx, r12; SpinLock
0x14002981b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140029822  nop     dword ptr [rax+rax+00h]
0x140029827  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x14002982e  mov     [rsp+68h+NewIrql], al
0x140029832  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140029839  nop     dword ptr [rax+rax+00h]
0x14002983e  test    al, al
0x140029840  jnz     loc_14002959E
0x140029846  jmp     loc_14002955A
0x14002984b  lea     r12, [rbx+5A8h]
0x140029852  mov     rcx, r12; RunRef
0x140029855  call    cs:__imp_ExAcquireRundownProtection
0x14002985c  nop     dword ptr [rax+rax+00h]
0x140029861  test    al, al
0x140029863  jnz     loc_14002961F
0x140029869  lea     rcx, [rbx+8E0h]; SpinLock
0x140029870  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140029877  nop     dword ptr [rax+rax+00h]
0x14002987c  mov     rcx, r12; RunRef
0x14002987f  mov     [rsp+68h+NewIrql], al
0x140029883  call    cs:__imp_ExAcquireRundownProtection
0x14002988a  nop     dword ptr [rax+rax+00h]
0x14002988f  test    al, al
0x140029891  jnz     loc_1400295FF
0x140029897  jmp     loc_1400295BB
0x14002989c  mov     rcx, [rbx+5B0h]; RunRefCacheAware
0x1400298a3  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x1400298aa  nop     dword ptr [rax+rax+00h]
0x1400298af  lea     r12, [rbx+8E0h]
0x1400298b6  test    al, al
0x1400298b8  jnz     short loc_140029904
0x1400298ba  mov     rcx, r12; SpinLock
0x1400298bd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400298c4  nop     dword ptr [rax+rax+00h]
0x1400298c9  mov     rcx, [rbx+5B0h]; RunRefCacheAware
0x1400298d0  mov     [rsp+68h+NewIrql], al
0x1400298d4  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x1400298db  nop     dword ptr [rax+rax+00h]
0x1400298e0  test    al, al
0x1400298e2  jz      loc_140029626
0x1400298e8  mov     dl, [rsp+68h+NewIrql]; NewIrql
0x1400298ec  mov     rcx, r12; SpinLock
0x1400298ef  call    cs:__imp_KeReleaseSpinLock
0x1400298f6  nop     dword ptr [rax+rax+00h]
0x1400298fb  test    r15b, r15b
0x1400298fe  jz      loc_140029539
0x140029904  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x14002990b  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140029912  nop     dword ptr [rax+rax+00h]
0x140029917  test    al, al
0x140029919  jnz     loc_140029534
0x14002991f  mov     rcx, r12; SpinLock
0x140029922  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140029929  nop     dword ptr [rax+rax+00h]
0x14002992e  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x140029935  mov     r14b, al
0x140029938  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14002993f  nop     dword ptr [rax+rax+00h]
0x140029944  test    al, al
0x140029946  jnz     loc_1400296C4
0x14002994c  xor     r15b, r15b
0x14002994f  cmp     [rsp+68h+arg_10], 2
0x140029957  jb      loc_1400296C4
0x14002995d  jmp     loc_14002966F
0x140029962  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140029969  nop     dword ptr [rax+rax+00h]
0x14002996e  mov     rsi, rax
0x140029971  test    rax, rax
0x140029974  jz      loc_1400294F1
0x14002997a  jmp     loc_1400296CE
0x14002997f  mov     ecx, 3
0x140029984  int     29h; Win8: RtlFailFast(ecx)
```
