# RxpSiloCreateNotification

- ea: `0x1400234b0`
- end: `0x14002385e`
- name: `RxpSiloCreateNotification`
- size: `942`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x140015230`
- `0x140016e70`
- `0x140017370`
- `0x1400234b0`
- `0x140025d00`
- `0x140026080`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140023615`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400236a3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140023774`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140023615`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400236a3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140023774`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002366c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140023713`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400237b8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002366c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140023713`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400237b8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023726`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023726`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400235ff`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400235ff`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x140023513`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x140023513`
- `ntoskrnl!PsIsHostSilo` at `0x140023522`
- `ntoskrnl!PsIsHostSilo` at `0x140023522`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400235c7`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400235c7`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14002380b`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14002380b`
- `ntoskrnl!PsCreateSiloContext` at `0x140023586`
- `ntoskrnl!PsCreateSiloContext` at `0x140023586`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x140023753`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x140023753`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140023732`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400237c4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140023732`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400237c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400235ea`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140023765`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400235ea`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140023765`

## pseudocode

```c
__int64 __fastcall RxpSiloCreateNotification(__int64 a1)
{
  __int64 v1; // rsi
  __int64 EffectiveServerSilo; // rax
  int v5; // eax
  int v6; // ebx
  _QWORD *v7; // rax
  NPAGED_LOOKASIDE_LIST *i; // r14
  ULONG *v9; // rsi
  __int64 (__fastcall *v10)(ULONG *, void *); // rax
  ULONG v11; // eax
  int inserted; // eax
  __int64 v13; // rcx
  __int64 *v14; // rax
  void *v15; // [rsp+88h] [rbp+50h] BYREF

  v1 = RxContextLookasideList.L.Future[8];
  v15 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_ca93da986bfe30d99490b155dbdc514b_Traceguids, a1);
  }
  EffectiveServerSilo = PsGetEffectiveServerSilo(a1);
  if ( (unsigned __int8)PsIsHostSilo(EffectiveServerSilo) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_ca93da986bfe30d99490b155dbdc514b_Traceguids, a1);
    }
    return 0;
  }
  else
  {
    v5 = PsCreateSiloContext(a1, (unsigned int)(8 * v1 + 48), 512, RxpSiloCleanupNotification, &v15);
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_ca93da986bfe30d99490b155dbdc514b_Traceguids, a1, v5);
      }
    }
    else
    {
      memset(v15, 0, 8 * v1 + 48);
      *(_WORD *)v15 = -5356;
      *((_DWORD *)v15 + 1) = v1;
      ExInitializeRundownProtection((PEX_RUNDOWN_REF)v15 + 4);
      v7 = (char *)v15 + 16;
      *((_QWORD *)v15 + 3) = (char *)v15 + 16;
      *v7 = v7;
      *((_QWORD *)v15 + 5) = a1;
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite(&Resource, 1u);
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)&RxContextLookasideList.L.AllocateEx);
      for ( i = *(NPAGED_LOOKASIDE_LIST **)&RxContextLookasideList.L.Future[4];
            i != (NPAGED_LOOKASIDE_LIST *)&RxContextLookasideList.L.Future[4];
            i = (NPAGED_LOOKASIDE_LIST *)i->L.ListHead.Alignment )
      {
        v9 = &i[-4].L.Future[8];
        if ( i->L.Future[0] == 1 && (v9[84] & 0x2000) != 0 && *(_QWORD *)(*((_QWORD *)v9 + 44) + 632LL) )
        {
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)&RxContextLookasideList.L.AllocateEx);
          v10 = *(__int64 (__fastcall **)(ULONG *, void *))(*((_QWORD *)v9 + 44) + 632LL);
          if ( v10 )
            v6 = v10(&i[-4].L.Future[8], v15);
          else
            v6 = -1073741822;
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)&RxContextLookasideList.L.AllocateEx);
          if ( v6 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                15,
                WPP_ca93da986bfe30d99490b155dbdc514b_Traceguids,
                &i[-4].L.Future[8],
                v15);
            }
            break;
          }
          v11 = v9[325];
          if ( v11 != -1 )
            *((_QWORD *)v15 + 1) |= 1LL << v11;
        }
      }
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)&RxContextLookasideList.L.AllocateEx);
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
      if ( v6 >= 0 )
      {
        inserted = PsInsertPermanentSiloContext(a1, (unsigned int)g_RxSiloContextSlot, v15);
        v6 = inserted;
        if ( inserted < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              16,
              WPP_ca93da986bfe30d99490b155dbdc514b_Traceguids,
              a1,
              inserted);
          }
        }
        else
        {
          KeEnterCriticalRegion();
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)&RxContextLookasideList.L.AllocateEx);
          v13 = qword_140043140;
          if ( *(__int64 **)(qword_140043140 + 8) != &qword_140043140 )
            __fastfail(3u);
          v14 = (__int64 *)((char *)v15 + 16);
          *((_QWORD *)v15 + 3) = &qword_140043140;
          *v14 = v13;
          *(_QWORD *)(v13 + 8) = v14;
          qword_140043140 = (__int64)v14;
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)&RxContextLookasideList.L.AllocateEx);
          KeLeaveCriticalRegion();
        }
      }
      PsDereferenceSiloContext(v15);
    }
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x1400234b0  push    rbp
0x1400234b2  push    rbx
0x1400234b3  push    rsi
0x1400234b4  push    rdi
0x1400234b5  push    r12
0x1400234b7  push    r13
0x1400234b9  push    r14
0x1400234bb  push    r15
0x1400234bd  mov     rbp, rsp
0x1400234c0  sub     rsp, 38h
0x1400234c4  mov     esi, dword ptr cs:RxContextLookasideList.L+78h
0x1400234ca  mov     rdi, rcx
0x1400234cd  mov     [rbp+arg_8], 0
0x1400234d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400234dc  lea     r12, WPP_GLOBAL_Control
0x1400234e3  lea     r14, WPP_ca93da986bfe30d99490b155dbdc514b_Traceguids
0x1400234ea  cmp     rcx, r12
0x1400234ed  jz      short loc_140023510
0x1400234ef  bt      dword ptr [rcx+2Ch], 0Fh
0x1400234f4  jnb     short loc_140023510
0x1400234f6  cmp     byte ptr [rcx+29h], 2
0x1400234fa  jb      short loc_140023510
0x1400234fc  mov     rcx, [rcx+18h]
0x140023500  mov     edx, 0Dh
0x140023505  mov     r9, rdi
0x140023508  mov     r8, r14
0x14002350b  call    WPP_SF_q
0x140023510  mov     rcx, rdi
0x140023513  call    cs:__imp_PsGetEffectiveServerSilo
0x14002351a  nop     dword ptr [rax+rax+00h]
0x14002351f  mov     rcx, rax
0x140023522  call    cs:__imp_PsIsHostSilo
0x140023529  nop     dword ptr [rax+rax+00h]
0x14002352e  test    al, al
0x140023530  jz      short loc_140023566
0x140023532  mov     rcx, cs:WPP_GLOBAL_Control
0x140023539  cmp     rcx, r12
0x14002353c  jz      short loc_14002355F
0x14002353e  bt      dword ptr [rcx+2Ch], 0Fh
0x140023543  jnb     short loc_14002355F
0x140023545  cmp     byte ptr [rcx+29h], 2
0x140023549  jb      short loc_14002355F
0x14002354b  mov     rcx, [rcx+18h]
0x14002354f  mov     edx, 0Eh
0x140023554  mov     r9, rdi
0x140023557  mov     r8, r14
0x14002355a  call    WPP_SF_q
0x14002355f  xor     eax, eax
0x140023561  jmp     loc_14002384C
0x140023566  lea     rax, [rbp+arg_8]
0x14002356a  mov     r8d, 200h
0x140023570  lea     edx, ds:30h[rsi*8]
0x140023577  mov     [rsp+38h+var_18], rax
0x14002357c  lea     r9, RxpSiloCleanupNotification
0x140023583  mov     rcx, rdi
0x140023586  call    cs:__imp_PsCreateSiloContext
0x14002358d  nop     dword ptr [rax+rax+00h]
0x140023592  mov     ebx, eax
0x140023594  test    eax, eax
0x140023596  js      loc_140023819
0x14002359c  mov     rcx, [rbp+arg_8]; void *
0x1400235a0  lea     r8, ds:30h[rsi*8]; Size
0x1400235a8  xor     edx, edx; Val
0x1400235aa  call    memset
0x1400235af  mov     rcx, [rbp+arg_8]
0x1400235b3  mov     word ptr [rcx], 0EB14h
0x1400235b8  mov     rcx, [rbp+arg_8]
0x1400235bc  mov     [rcx+4], esi
0x1400235bf  mov     rcx, [rbp+arg_8]
0x1400235c3  add     rcx, 20h ; ' '; RunRef
0x1400235c7  call    cs:__imp_ExInitializeRundownProtection
0x1400235ce  nop     dword ptr [rax+rax+00h]
0x1400235d3  mov     rax, [rbp+arg_8]
0x1400235d7  add     rax, 10h
0x1400235db  mov     [rax+8], rax
0x1400235df  mov     [rax], rax
0x1400235e2  mov     rax, [rbp+arg_8]
0x1400235e6  mov     [rax+28h], rdi
0x1400235ea  call    cs:__imp_KeEnterCriticalRegion
0x1400235f1  nop     dword ptr [rax+rax+00h]
0x1400235f6  mov     dl, 1; Wait
0x1400235f8  lea     rcx, Resource; Resource
0x1400235ff  call    cs:__imp_ExAcquireResourceSharedLite
0x140023606  nop     dword ptr [rax+rax+00h]
0x14002360b  lea     r13, RxContextLookasideList.L.30h
0x140023612  mov     rcx, r13; FastMutex
0x140023615  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002361c  nop     dword ptr [rax+rax+00h]
0x140023621  mov     r14, qword ptr cs:RxContextLookasideList.L+68h
0x140023628  lea     rax, RxContextLookasideList.L+68h
0x14002362f  cmp     r14, rax
0x140023632  jz      loc_140023710
0x140023638  lea     rsi, [r14-188h]
0x14002363f  cmp     dword ptr [rsi+1E0h], 1
0x140023646  jnz     loc_1400236CE
0x14002364c  test    dword ptr [rsi+150h], 2000h
0x140023656  jz      short loc_1400236CE
0x140023658  mov     rax, [rsi+160h]
0x14002365f  cmp     qword ptr [rax+278h], 0
0x140023667  jz      short loc_1400236CE
0x140023669  mov     rcx, r13; FastMutex
0x14002366c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140023673  nop     dword ptr [rax+rax+00h]
0x140023678  mov     rax, [rsi+160h]
0x14002367f  mov     rax, [rax+278h]
0x140023686  test    rax, rax
0x140023689  jnz     short loc_140023692
0x14002368b  mov     ebx, 0C0000002h
0x140023690  jmp     short loc_1400236A0
0x140023692  mov     rdx, [rbp+arg_8]
0x140023696  mov     rcx, rsi
0x140023699  call    _guard_dispatch_icall
0x14002369e  mov     ebx, eax
0x1400236a0  mov     rcx, r13; FastMutex
0x1400236a3  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400236aa  nop     dword ptr [rax+rax+00h]
0x1400236af  test    ebx, ebx
0x1400236b1  js      short loc_1400236D6
0x1400236b3  mov     eax, [rsi+514h]
0x1400236b9  cmp     eax, 0FFFFFFFFh
0x1400236bc  jz      short loc_1400236CE
0x1400236be  mov     rdx, [rbp+arg_8]
0x1400236c2  mov     rcx, [rdx+8]
0x1400236c6  bts     rcx, rax
0x1400236ca  mov     [rdx+8], rcx
0x1400236ce  mov     r14, [r14]
0x1400236d1  jmp     loc_140023628
0x1400236d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400236dd  cmp     rcx, r12
0x1400236e0  jz      short loc_140023710
0x1400236e2  bt      dword ptr [rcx+2Ch], 0Fh
0x1400236e7  jnb     short loc_140023710
0x1400236e9  cmp     byte ptr [rcx+29h], 1
0x1400236ed  jb      short loc_140023710
0x1400236ef  mov     rax, [rbp+arg_8]
0x1400236f3  lea     r8, WPP_ca93da986bfe30d99490b155dbdc514b_Traceguids
0x1400236fa  mov     rcx, [rcx+18h]
0x1400236fe  mov     edx, 0Fh
0x140023703  mov     r9, rsi
0x140023706  mov     [rsp+38h+var_18], rax
0x14002370b  call    WPP_SF_qq
0x140023710  mov     rcx, r13; FastMutex
0x140023713  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002371a  nop     dword ptr [rax+rax+00h]
0x14002371f  lea     rcx, Resource; Resource
0x140023726  call    cs:__imp_ExReleaseResourceLite
0x14002372d  nop     dword ptr [rax+rax+00h]
0x140023732  call    cs:__imp_KeLeaveCriticalRegion
0x140023739  nop     dword ptr [rax+rax+00h]
0x14002373e  test    ebx, ebx
0x140023740  js      loc_140023807
0x140023746  mov     r8, [rbp+arg_8]
0x14002374a  mov     rcx, rdi
0x14002374d  mov     edx, cs:g_RxSiloContextSlot
0x140023753  call    cs:__imp_PsInsertPermanentSiloContext
0x14002375a  nop     dword ptr [rax+rax+00h]
0x14002375f  mov     ebx, eax
0x140023761  test    eax, eax
0x140023763  js      short loc_1400237D2
0x140023765  call    cs:__imp_KeEnterCriticalRegion
0x14002376c  nop     dword ptr [rax+rax+00h]
0x140023771  mov     rcx, r13; FastMutex
0x140023774  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002377b  nop     dword ptr [rax+rax+00h]
0x140023780  mov     rcx, cs:qword_140043140
0x140023787  lea     rdx, qword_140043140
0x14002378e  cmp     [rcx+8], rdx
0x140023792  jz      short loc_14002379B
0x140023794  mov     ecx, 3
0x140023799  int     29h; Win8: RtlFailFast(ecx)
0x14002379b  mov     rax, [rbp+arg_8]
0x14002379f  add     rax, 10h
0x1400237a3  mov     [rax+8], rdx
0x1400237a7  mov     [rax], rcx
0x1400237aa  mov     [rcx+8], rax
0x1400237ae  mov     rcx, r13; FastMutex
0x1400237b1  mov     cs:qword_140043140, rax
0x1400237b8  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400237bf  nop     dword ptr [rax+rax+00h]
0x1400237c4  call    cs:__imp_KeLeaveCriticalRegion
0x1400237cb  nop     dword ptr [rax+rax+00h]
0x1400237d0  jmp     short loc_140023807
0x1400237d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400237d9  cmp     rcx, r12
0x1400237dc  jz      short loc_140023807
0x1400237de  bt      dword ptr [rcx+2Ch], 0Fh
0x1400237e3  jnb     short loc_140023807
0x1400237e5  cmp     byte ptr [rcx+29h], 1
0x1400237e9  jb      short loc_140023807
0x1400237eb  mov     rcx, [rcx+18h]
0x1400237ef  lea     r8, WPP_ca93da986bfe30d99490b155dbdc514b_Traceguids
0x1400237f6  mov     edx, 10h
0x1400237fb  mov     dword ptr [rsp+38h+var_18], eax
0x1400237ff  mov     r9, rdi
0x140023802  call    WPP_SF_qD
0x140023807  mov     rcx, [rbp+arg_8]
0x14002380b  call    cs:__imp_PsDereferenceSiloContext
0x140023812  nop     dword ptr [rax+rax+00h]
0x140023817  jmp     short loc_14002384A
0x140023819  mov     rcx, cs:WPP_GLOBAL_Control
0x140023820  cmp     rcx, r12
0x140023823  jz      short loc_14002384A
0x140023825  bt      dword ptr [rcx+2Ch], 0Fh
0x14002382a  jnb     short loc_14002384A
0x14002382c  cmp     byte ptr [rcx+29h], 1
0x140023830  jb      short loc_14002384A
0x140023832  mov     rcx, [rcx+18h]
0x140023836  mov     edx, 11h
0x14002383b  mov     r9, rdi
0x14002383e  mov     dword ptr [rsp+38h+var_18], eax
0x140023842  mov     r8, r14
0x140023845  call    WPP_SF_qD
0x14002384a  mov     eax, ebx
0x14002384c  add     rsp, 38h
0x140023850  pop     r15
0x140023852  pop     r14
0x140023854  pop     r13
0x140023856  pop     r12
0x140023858  pop     rdi
0x140023859  pop     rsi
0x14002385a  pop     rbx
0x14002385b  pop     rbp
0x14002385c  retn
```
