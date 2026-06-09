# HvSocketAcceptIncomingConnection

- ea: `0x1400059b8`
- end: `0x140005d6c`
- name: `HvSocketAcceptIncomingConnection`
- size: `948`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001b578`
- `0x14001c2d0`

## callees

- `0x140001ba0`
- `0x1400023b0`
- `0x1400059b8`
- `0x14000975c`
- `0x140009ec0`
- `0x14000a048`
- `0x14000b86c`
- `0x14000bfe0`
- `0x140019268`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005a57`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005a57`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005ac0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005bdb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005d08`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005ac0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005bdb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005d08`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005ae3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005bfe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005c19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005d2b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005d46`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005ae3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005bfe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005c19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005d2b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005d46`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140005aa6`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140005aa6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140005ad7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140005bf2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140005c0d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140005d1f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140005d3a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140005ad7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140005bf2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140005c0d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140005d1f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140005d3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005cd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005cd0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400059d9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005a34`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400059d9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005a34`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005cba`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005cba`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400059ec`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140005a44`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400059ec`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140005a44`
- `ntoskrnl!PsGetProcessId` at `0x140005b13`
- `ntoskrnl!PsGetProcessId` at `0x140005b13`
- `ntoskrnl!ObfReferenceObject` at `0x140005b51`
- `ntoskrnl!ObfReferenceObject` at `0x140005b51`

## string_xrefs

- `0x140005a1b`: `HvSocketAcceptIncomingConnection`
- `0x140005b2d`: `HvSocketAcceptIncomingConnection`
- `0x140005ba6`: `HvSocketAcceptIncomingConnection`
- `0x140005c6d`: `HvSocketAcceptIncomingConnection`

## pseudocode

```c
__int64 __fastcall HvSocketAcceptIncomingConnection(__int64 a1, __int64 a2)
{
  unsigned int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rbp
  KIRQL v9; // al
  KIRQL v10; // r15
  struct _KPROCESS *v11; // rcx
  struct _KPROCESS *v12; // rcx
  unsigned int ProcessId; // eax
  void *v14; // rcx
  unsigned int v15; // eax
  __int64 v16; // rdi
  signed __int64 v17; // rax
  bool v18; // cc
  signed __int64 v19; // rax
  void (__fastcall *v20)(__int64); // rax
  unsigned int v22; // [rsp+68h] [rbp+10h] BYREF

  v4 = -1073741823;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 16));
  v8 = *(_QWORD *)(a2 + 872);
  if ( !v8 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v6, v5, v7);
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointError("HvSocketAcceptIncomingConnection", 347, 3221225473LL, a2);
    goto LABEL_34;
  }
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v8 + 16));
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 72));
  v10 = v9;
  if ( *(_BYTE *)(a2 + 296) || (*(_DWORD *)(a2 + 516) & 0x280) != 0 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 72), v9);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a2 + 872) + 16LL));
    KeLeaveCriticalRegion();
LABEL_34:
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 16));
    KeLeaveCriticalRegion();
    return v4;
  }
  v11 = *(struct _KPROCESS **)(a1 + 272);
  if ( v11 )
  {
    if ( PsChargeProcessPoolQuota(v11, (POOL_TYPE)512, 0x470u) < 0 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 72), v10);
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a2 + 872) + 16LL));
      KeLeaveCriticalRegion();
      v4 = -1073741801;
      if ( (unsigned int)dword_140013058 > 2 )
      {
        v12 = *(struct _KPROCESS **)(a1 + 272);
        if ( v12 )
          ProcessId = (unsigned int)PsGetProcessId(v12);
        else
          ProcessId = 0;
        HvsocketTraceGuidULongError(
          (unsigned int)"HvSocketAcceptIncomingConnection",
          375,
          -1073741801,
          a1 + 156,
          ProcessId);
      }
      goto LABEL_34;
    }
    v14 = *(void **)(a1 + 272);
    *(_QWORD *)(a2 + 272) = v14;
    ObfReferenceObject(v14);
    _InterlockedAdd64((volatile signed __int64 *)VmbusProviderContext + 161, 0x470u);
    _InterlockedAdd64((volatile signed __int64 *)VmbusProviderContext + 162, 1u);
  }
  HvSocketBeginProcessingConnectionLocked(a2);
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"HvSocketAcceptIncomingConnection",
      389,
      a1,
      *(_QWORD *)(a1 + 8),
      (__int64)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 8)) <= 1 )
    __fastfail(0xEu);
  *(_QWORD *)(a2 + 944) = a1;
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 72), v10);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a2 + 872) + 16LL));
  KeLeaveCriticalRegion();
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 16));
  KeLeaveCriticalRegion();
  v15 = VmbusTlAcceptConnection(*(_QWORD *)(a2 + 936), a2);
  v16 = *(_QWORD *)(a2 + 936);
  v4 = v15;
  v22 = v15;
  if ( v16 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketAcceptIncomingConnection",
        413,
        v16,
        *(_QWORD *)(v16 + 8),
        (__int64)"Dereference object");
    v17 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v16 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v18 = v17 <= 1;
    v19 = v17 - 1;
    if ( v18 )
    {
      if ( v19 )
        __fastfail(0xEu);
      v20 = *(void (__fastcall **)(__int64))(v16 + 80);
      if ( v20 )
        v20(v16);
      if ( *(_DWORD *)(v16 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v16, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v16 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v16 + 96), (PVOID)v16);
      }
    }
    *(_QWORD *)(a2 + 936) = 0;
  }
  if ( v4 != 259 )
  {
    VmbusTlConnectComplete((char *)a2, (int *)&v22);
    return v22;
  }
  return v4;
}

```

## disassembly

```asm
0x1400059b8  mov     [rsp+arg_0], rbx
0x1400059bd  mov     [rsp+arg_10], rbp
0x1400059c2  push    rsi
0x1400059c3  push    rdi
0x1400059c4  push    r12
0x1400059c6  push    r14
0x1400059c8  push    r15
0x1400059ca  sub     rsp, 30h
0x1400059ce  mov     rbx, rdx
0x1400059d1  mov     rdi, rcx
0x1400059d4  mov     esi, 0C0000001h
0x1400059d9  call    cs:__imp_KeEnterCriticalRegion
0x1400059e0  nop     dword ptr [rax+rax+00h]
0x1400059e5  lea     r14, [rbx+10h]
0x1400059e9  mov     rcx, r14; FastMutex
0x1400059ec  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400059f3  nop     dword ptr [rax+rax+00h]
0x1400059f8  mov     rbp, [rbx+368h]
0x1400059ff  test    rbp, rbp
0x140005a02  jnz     short loc_140005A34
0x140005a04  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140005a09  mov     eax, cs:dword_140013058
0x140005a0f  cmp     eax, 2
0x140005a12  jbe     loc_140005D37
0x140005a18  mov     r9, rbx
0x140005a1b  lea     rcx, aHvsocketaccept; "HvSocketAcceptIncomingConnection"
0x140005a22  mov     r8d, esi
0x140005a25  mov     edx, 15Bh
0x140005a2a  call    HvsocketTraceEndpointError
0x140005a2f  jmp     loc_140005D37
0x140005a34  call    cs:__imp_KeEnterCriticalRegion
0x140005a3b  nop     dword ptr [rax+rax+00h]
0x140005a40  lea     rcx, [rbp+10h]; FastMutex
0x140005a44  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140005a4b  nop     dword ptr [rax+rax+00h]
0x140005a50  lea     rbp, [rbx+48h]
0x140005a54  mov     rcx, rbp; SpinLock
0x140005a57  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005a5e  nop     dword ptr [rax+rax+00h]
0x140005a63  cmp     byte ptr [rbx+128h], 0
0x140005a6a  mov     r15b, al
0x140005a6d  jnz     loc_140005D02
0x140005a73  test    dword ptr [rbx+204h], 280h
0x140005a7d  jnz     loc_140005D02
0x140005a83  mov     rcx, [rdi+110h]; Process
0x140005a8a  mov     esi, 1
0x140005a8f  test    rcx, rcx
0x140005a92  jz      loc_140005B7B
0x140005a98  mov     r12d, 470h
0x140005a9e  mov     edx, 200h; PoolType
0x140005aa3  mov     r8d, r12d; Amount
0x140005aa6  call    cs:__imp_PsChargeProcessPoolQuota
0x140005aad  nop     dword ptr [rax+rax+00h]
0x140005ab2  test    eax, eax
0x140005ab4  jns     loc_140005B43
0x140005aba  mov     dl, r15b; NewIrql
0x140005abd  mov     rcx, rbp; SpinLock
0x140005ac0  call    cs:__imp_KeReleaseSpinLock
0x140005ac7  nop     dword ptr [rax+rax+00h]
0x140005acc  mov     rcx, [rbx+368h]
0x140005ad3  add     rcx, 10h; FastMutex
0x140005ad7  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140005ade  nop     dword ptr [rax+rax+00h]
0x140005ae3  call    cs:__imp_KeLeaveCriticalRegion
0x140005aea  nop     dword ptr [rax+rax+00h]
0x140005aef  mov     eax, cs:dword_140013058
0x140005af5  mov     esi, 0C0000017h
0x140005afa  cmp     eax, 2
0x140005afd  jbe     loc_140005D37
0x140005b03  mov     rcx, [rdi+110h]; Process
0x140005b0a  test    rcx, rcx
0x140005b0d  jnz     short loc_140005B13
0x140005b0f  xor     eax, eax
0x140005b11  jmp     short loc_140005B1F
0x140005b13  call    cs:__imp_PsGetProcessId
0x140005b1a  nop     dword ptr [rax+rax+00h]
0x140005b1f  lea     r9, [rdi+9Ch]
0x140005b26  mov     dword ptr [rsp+58h+var_38], eax
0x140005b2a  mov     r8d, esi
0x140005b2d  lea     rcx, aHvsocketaccept; "HvSocketAcceptIncomingConnection"
0x140005b34  mov     edx, 177h
0x140005b39  call    HvsocketTraceGuidULongError
0x140005b3e  jmp     loc_140005D37
0x140005b43  mov     rcx, [rdi+110h]; Object
0x140005b4a  mov     [rbx+110h], rcx
0x140005b51  call    cs:__imp_ObfReferenceObject
0x140005b58  nop     dword ptr [rax+rax+00h]
0x140005b5d  mov     rax, cs:VmbusProviderContext
0x140005b64  lock add [rax+508h], r12
0x140005b6c  mov     rax, cs:VmbusProviderContext
0x140005b73  lock add [rax+510h], rsi
0x140005b7b  mov     rcx, rbx
0x140005b7e  call    HvSocketBeginProcessingConnectionLocked
0x140005b83  mov     eax, cs:dword_140013058
0x140005b89  cmp     eax, 5
0x140005b8c  jbe     short loc_140005BB2
0x140005b8e  mov     r9, [rdi+8]
0x140005b92  lea     rax, aReferenceObjec; "Reference object"
0x140005b99  mov     r8, rdi
0x140005b9c  mov     [rsp+58h+var_38], rax
0x140005ba1  mov     edx, 185h
0x140005ba6  lea     rcx, aHvsocketaccept; "HvSocketAcceptIncomingConnection"
0x140005bad  call    HvsocketTraceReferenceCount
0x140005bb2  mov     rax, rsi
0x140005bb5  lock xadd [rdi+8], rax
0x140005bbb  add     rax, rsi
0x140005bbe  mov     r12d, 0Eh
0x140005bc4  cmp     rax, rsi
0x140005bc7  jg      short loc_140005BCE
0x140005bc9  mov     ecx, r12d
0x140005bcc  int     29h; Win8: RtlFailFast(ecx)
0x140005bce  mov     dl, r15b; NewIrql
0x140005bd1  mov     [rbx+3B0h], rdi
0x140005bd8  mov     rcx, rbp; SpinLock
0x140005bdb  call    cs:__imp_KeReleaseSpinLock
0x140005be2  nop     dword ptr [rax+rax+00h]
0x140005be7  mov     rcx, [rbx+368h]
0x140005bee  add     rcx, 10h; FastMutex
0x140005bf2  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140005bf9  nop     dword ptr [rax+rax+00h]
0x140005bfe  call    cs:__imp_KeLeaveCriticalRegion
0x140005c05  nop     dword ptr [rax+rax+00h]
0x140005c0a  mov     rcx, r14; FastMutex
0x140005c0d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140005c14  nop     dword ptr [rax+rax+00h]
0x140005c19  call    cs:__imp_KeLeaveCriticalRegion
0x140005c20  nop     dword ptr [rax+rax+00h]
0x140005c25  mov     rcx, [rbx+3A8h]
0x140005c2c  mov     rdx, rbx
0x140005c2f  call    VmbusTlAcceptConnection
0x140005c34  mov     rdi, [rbx+3A8h]
0x140005c3b  mov     esi, eax
0x140005c3d  mov     [rsp+58h+arg_8], eax
0x140005c41  test    rdi, rdi
0x140005c44  jz      loc_140005CE7
0x140005c4a  mov     ecx, cs:dword_140013058
0x140005c50  cmp     ecx, 5
0x140005c53  jbe     short loc_140005C79
0x140005c55  mov     r9, [rdi+8]
0x140005c59  lea     rax, aDereferenceObj; "Dereference object"
0x140005c60  mov     r8, rdi
0x140005c63  mov     [rsp+58h+var_38], rax
0x140005c68  mov     edx, 19Dh
0x140005c6d  lea     rcx, aHvsocketaccept; "HvSocketAcceptIncomingConnection"
0x140005c74  call    HvsocketTraceReferenceCount
0x140005c79  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005c7d  lock xadd [rdi+8], rax
0x140005c83  sub     rax, 1
0x140005c87  jg      short loc_140005CDC
0x140005c89  test    rax, rax
0x140005c8c  jz      short loc_140005C95
0x140005c8e  mov     rcx, r12
0x140005c91  int     29h; Win8: RtlFailFast(ecx)
0x140005c93  jmp     short loc_140005CDC
0x140005c95  mov     rax, [rdi+50h]
0x140005c99  test    rax, rax
0x140005c9c  jz      short loc_140005CA6
0x140005c9e  mov     rcx, rdi
0x140005ca1  call    _guard_dispatch_icall
0x140005ca6  mov     ecx, [rdi+58h]
0x140005ca9  sub     ecx, 1
0x140005cac  jz      short loc_140005CC8
0x140005cae  cmp     ecx, 1
0x140005cb1  jnz     short loc_140005CDC
0x140005cb3  mov     rcx, [rdi+60h]; Lookaside
0x140005cb7  mov     rdx, rdi; Entry
0x140005cba  call    cs:__imp_ExFreeToNPagedLookasideList
0x140005cc1  nop     dword ptr [rax+rax+00h]
0x140005cc6  jmp     short loc_140005CDC
0x140005cc8  mov     edx, 69706E56h; Tag
0x140005ccd  mov     rcx, rdi; P
0x140005cd0  call    cs:__imp_ExFreePoolWithTag
0x140005cd7  nop     dword ptr [rax+rax+00h]
0x140005cdc  mov     qword ptr [rbx+3A8h], 0
0x140005ce7  cmp     esi, 103h
0x140005ced  jz      short loc_140005D52
0x140005cef  lea     rdx, [rsp+58h+arg_8]
0x140005cf4  mov     rcx, rbx; P
0x140005cf7  call    VmbusTlConnectComplete
0x140005cfc  mov     esi, [rsp+58h+arg_8]
0x140005d00  jmp     short loc_140005D52
0x140005d02  mov     dl, r15b; NewIrql
0x140005d05  mov     rcx, rbp; SpinLock
0x140005d08  call    cs:__imp_KeReleaseSpinLock
0x140005d0f  nop     dword ptr [rax+rax+00h]
0x140005d14  mov     rcx, [rbx+368h]
0x140005d1b  add     rcx, 10h; FastMutex
0x140005d1f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140005d26  nop     dword ptr [rax+rax+00h]
0x140005d2b  call    cs:__imp_KeLeaveCriticalRegion
0x140005d32  nop     dword ptr [rax+rax+00h]
0x140005d37  mov     rcx, r14; FastMutex
0x140005d3a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140005d41  nop     dword ptr [rax+rax+00h]
0x140005d46  call    cs:__imp_KeLeaveCriticalRegion
0x140005d4d  nop     dword ptr [rax+rax+00h]
0x140005d52  mov     rbx, [rsp+58h+arg_0]
0x140005d57  mov     eax, esi
0x140005d59  mov     rbp, [rsp+58h+arg_10]
0x140005d5e  add     rsp, 30h
0x140005d62  pop     r15
0x140005d64  pop     r14
0x140005d66  pop     r12
0x140005d68  pop     rdi
0x140005d69  pop     rsi
0x140005d6a  retn
```
