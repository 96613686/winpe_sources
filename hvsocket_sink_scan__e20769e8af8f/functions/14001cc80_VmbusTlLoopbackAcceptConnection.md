# VmbusTlLoopbackAcceptConnection

- ea: `0x14001cc80`
- end: `0x14001cf4d`
- name: `VmbusTlLoopbackAcceptConnection`
- size: `717`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001350`
- `0x1400023b0`
- `0x140006448`
- `0x1400068ac`
- `0x14000975c`
- `0x1400098f4`
- `0x14000a048`
- `0x14000bfe0`
- `0x14001cc80`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001cdc6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ce4b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001cdc6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ce4b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001cdba`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ce3f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001cdba`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ce3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cf27`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cf27`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001cd39`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001cdd2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001cd39`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001cdd2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cf11`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cf11`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001cd49`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001cde2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001cd49`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001cde2`

## pseudocode

```c
__int64 __fastcall VmbusTlLoopbackAcceptConnection(char *P, __int64 a2)
{
  __int64 v4; // rbx
  int v5; // edi
  __int64 v6; // rdx
  signed __int64 v7; // rax
  bool v8; // cc
  signed __int64 v9; // rax
  void (__fastcall *v10)(__int64); // rax
  __int64 v12; // [rsp+60h] [rbp+8h] BYREF

  v12 = 0;
  v4 = VmbusTlLoopbackReferenceEndpointDeliveryQueue();
  if ( v4 )
  {
    v5 = VmbusTlCreateObject(1u, 112, &v12);
    if ( v5 >= 0 )
    {
      KeEnterCriticalRegion();
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 16));
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlLoopbackAcceptConnection",
          232,
          (_DWORD)P,
          *((_QWORD *)P + 1),
          (__int64)"Reference object");
      if ( _InterlockedIncrement64((volatile signed __int64 *)P + 1) <= 1 )
        __fastfail(0xEu);
      v6 = v12;
      *(_QWORD *)(v12 + 104) = P;
      *(_QWORD *)(v6 + 96) = P + 800;
      VmbusTlLoopbackSetEndpointDeliveryQueue(a2, v6);
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 16));
      KeLeaveCriticalRegion();
      KeEnterCriticalRegion();
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(P + 16));
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlLoopbackAcceptConnection",
          243,
          a2,
          *(_QWORD *)(a2 + 8),
          (__int64)"Reference object");
      if ( _InterlockedIncrement64((volatile signed __int64 *)(a2 + 8)) <= 1 )
        __fastfail(0xEu);
      *(_QWORD *)(v4 + 104) = a2;
      *(_QWORD *)(v4 + 96) = a2 + 800;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(P + 16));
      KeLeaveCriticalRegion();
      LODWORD(v12) = 0;
      VmbusTlConnectComplete(P, (int *)&v12);
      v5 = v12;
      if ( (int)v12 < 0 && (unsigned int)dword_140013058 > 2 )
        HvsocketTraceEndpointGuidError(
          (unsigned int)"VmbusTlLoopbackAcceptConnection",
          265,
          v12,
          a2,
          (__int64)(P + 464));
    }
    else if ( (unsigned int)dword_140013058 > 2 )
    {
      HvsocketTraceEndpointError("VmbusTlLoopbackAcceptConnection", 226, (unsigned int)v5, a2);
    }
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlLoopbackAcceptConnection",
        271,
        v4,
        *(_QWORD *)(v4 + 8),
        (__int64)"Dereference object");
    v7 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v4 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v8 = v7 <= 1;
    v9 = v7 - 1;
    if ( v8 )
    {
      if ( v9 )
        __fastfail(0xEu);
      v10 = *(void (__fastcall **)(__int64))(v4 + 80);
      if ( v10 )
        v10(v4);
      if ( *(_DWORD *)(v4 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v4, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v4 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v4 + 96), (PVOID)v4);
      }
    }
  }
  else
  {
    v5 = -1073741299;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointGuidError(
        (unsigned int)"VmbusTlLoopbackAcceptConnection",
        216,
        -1073741299,
        a2,
        (__int64)(P + 464));
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001cc80  mov     [rsp+arg_8], rbx
0x14001cc85  mov     [rsp+arg_10], rbp
0x14001cc8a  push    rsi
0x14001cc8b  push    rdi
0x14001cc8c  push    r12
0x14001cc8e  push    r13
0x14001cc90  push    r15
0x14001cc92  sub     rsp, 30h
0x14001cc96  mov     rsi, rdx
0x14001cc99  mov     [rsp+58h+arg_0], 0
0x14001cca2  mov     rbp, rcx
0x14001cca5  call    VmbusTlLoopbackReferenceEndpointDeliveryQueue
0x14001ccaa  mov     rbx, rax
0x14001ccad  test    rax, rax
0x14001ccb0  jnz     short loc_14001CCEE
0x14001ccb2  mov     eax, cs:dword_140013058
0x14001ccb8  mov     edi, 0C000020Dh
0x14001ccbd  cmp     eax, 2
0x14001ccc0  jbe     loc_14001CF33
0x14001ccc6  lea     rax, [rbp+1D0h]
0x14001cccd  mov     r9, rsi
0x14001ccd0  mov     r8d, edi
0x14001ccd3  mov     [rsp+58h+var_38], rax
0x14001ccd8  mov     edx, 0D8h
0x14001ccdd  lea     rcx, aVmbustlloopbac_2; "VmbusTlLoopbackAcceptConnection"
0x14001cce4  call    HvsocketTraceEndpointGuidError
0x14001cce9  jmp     loc_14001CF33
0x14001ccee  mov     edx, 70h ; 'p'
0x14001ccf3  lea     r8, [rsp+58h+arg_0]
0x14001ccf8  lea     r15d, [rdx-6Fh]
0x14001ccfc  mov     ecx, r15d
0x14001ccff  call    VmbusTlCreateObject
0x14001cd04  lea     r12d, [r15+0Dh]
0x14001cd08  mov     edi, eax
0x14001cd0a  test    eax, eax
0x14001cd0c  jns     short loc_14001CD39
0x14001cd0e  mov     eax, cs:dword_140013058
0x14001cd14  cmp     eax, 2
0x14001cd17  jbe     loc_14001CEA2
0x14001cd1d  mov     r9, rsi
0x14001cd20  lea     rcx, aVmbustlloopbac_2; "VmbusTlLoopbackAcceptConnection"
0x14001cd27  mov     r8d, edi
0x14001cd2a  mov     edx, 0E2h
0x14001cd2f  call    HvsocketTraceEndpointError
0x14001cd34  jmp     loc_14001CEA2
0x14001cd39  call    cs:__imp_KeEnterCriticalRegion
0x14001cd40  nop     dword ptr [rax+rax+00h]
0x14001cd45  lea     rcx, [rsi+10h]; FastMutex
0x14001cd49  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001cd50  nop     dword ptr [rax+rax+00h]
0x14001cd55  mov     eax, cs:dword_140013058
0x14001cd5b  lea     r13, aReferenceObjec; "Reference object"
0x14001cd62  cmp     eax, 5
0x14001cd65  jbe     short loc_14001CD84
0x14001cd67  mov     r9, [rbp+8]
0x14001cd6b  lea     rcx, aVmbustlloopbac_2; "VmbusTlLoopbackAcceptConnection"
0x14001cd72  mov     r8, rbp
0x14001cd75  mov     [rsp+58h+var_38], r13
0x14001cd7a  mov     edx, 0E8h
0x14001cd7f  call    HvsocketTraceReferenceCount
0x14001cd84  mov     rax, r15
0x14001cd87  lock xadd [rbp+8], rax
0x14001cd8d  add     rax, r15
0x14001cd90  cmp     rax, r15
0x14001cd93  jg      short loc_14001CD9A
0x14001cd95  mov     rcx, r12
0x14001cd98  int     29h; Win8: RtlFailFast(ecx)
0x14001cd9a  mov     rdx, [rsp+58h+arg_0]
0x14001cd9f  lea     rax, [rbp+320h]
0x14001cda6  mov     rcx, rsi
0x14001cda9  mov     [rdx+68h], rbp
0x14001cdad  mov     [rdx+60h], rax
0x14001cdb1  call    VmbusTlLoopbackSetEndpointDeliveryQueue
0x14001cdb6  lea     rcx, [rsi+10h]; FastMutex
0x14001cdba  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001cdc1  nop     dword ptr [rax+rax+00h]
0x14001cdc6  call    cs:__imp_KeLeaveCriticalRegion
0x14001cdcd  nop     dword ptr [rax+rax+00h]
0x14001cdd2  call    cs:__imp_KeEnterCriticalRegion
0x14001cdd9  nop     dword ptr [rax+rax+00h]
0x14001cdde  lea     rcx, [rbp+10h]; FastMutex
0x14001cde2  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001cde9  nop     dword ptr [rax+rax+00h]
0x14001cdee  mov     eax, cs:dword_140013058
0x14001cdf4  cmp     eax, 5
0x14001cdf7  jbe     short loc_14001CE16
0x14001cdf9  mov     r9, [rsi+8]
0x14001cdfd  lea     rcx, aVmbustlloopbac_2; "VmbusTlLoopbackAcceptConnection"
0x14001ce04  mov     r8, rsi
0x14001ce07  mov     [rsp+58h+var_38], r13
0x14001ce0c  mov     edx, 0F3h
0x14001ce11  call    HvsocketTraceReferenceCount
0x14001ce16  mov     rax, r15
0x14001ce19  lock xadd [rsi+8], rax
0x14001ce1f  add     rax, r15
0x14001ce22  cmp     rax, r15
0x14001ce25  jg      short loc_14001CE2C
0x14001ce27  mov     rcx, r12
0x14001ce2a  int     29h; Win8: RtlFailFast(ecx)
0x14001ce2c  lea     rax, [rsi+320h]
0x14001ce33  mov     [rbx+68h], rsi
0x14001ce37  lea     rcx, [rbp+10h]; FastMutex
0x14001ce3b  mov     [rbx+60h], rax
0x14001ce3f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001ce46  nop     dword ptr [rax+rax+00h]
0x14001ce4b  call    cs:__imp_KeLeaveCriticalRegion
0x14001ce52  nop     dword ptr [rax+rax+00h]
0x14001ce57  lea     rdx, [rsp+58h+arg_0]
0x14001ce5c  mov     dword ptr [rsp+58h+arg_0], 0
0x14001ce64  mov     rcx, rbp; P
0x14001ce67  call    VmbusTlConnectComplete
0x14001ce6c  mov     edi, dword ptr [rsp+58h+arg_0]
0x14001ce70  test    edi, edi
0x14001ce72  jns     short loc_14001CEA2
0x14001ce74  mov     eax, cs:dword_140013058
0x14001ce7a  cmp     eax, 2
0x14001ce7d  jbe     short loc_14001CEA2
0x14001ce7f  lea     rax, [rbp+1D0h]
0x14001ce86  mov     r9, rsi
0x14001ce89  mov     r8d, edi
0x14001ce8c  mov     [rsp+58h+var_38], rax
0x14001ce91  mov     edx, 109h
0x14001ce96  lea     rcx, aVmbustlloopbac_2; "VmbusTlLoopbackAcceptConnection"
0x14001ce9d  call    HvsocketTraceEndpointGuidError
0x14001cea2  mov     eax, cs:dword_140013058
0x14001cea8  cmp     eax, 5
0x14001ceab  jbe     short loc_14001CED1
0x14001cead  mov     r9, [rbx+8]
0x14001ceb1  lea     rax, aDereferenceObj; "Dereference object"
0x14001ceb8  mov     r8, rbx
0x14001cebb  mov     [rsp+58h+var_38], rax
0x14001cec0  mov     edx, 10Fh
0x14001cec5  lea     rcx, aVmbustlloopbac_2; "VmbusTlLoopbackAcceptConnection"
0x14001cecc  call    HvsocketTraceReferenceCount
0x14001ced1  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001ced5  lock xadd [rbx+8], rax
0x14001cedb  sub     rax, r15
0x14001cede  jg      short loc_14001CF33
0x14001cee0  test    rax, rax
0x14001cee3  jz      short loc_14001CEEC
0x14001cee5  mov     rcx, r12
0x14001cee8  int     29h; Win8: RtlFailFast(ecx)
0x14001ceea  jmp     short loc_14001CF33
0x14001ceec  mov     rax, [rbx+50h]
0x14001cef0  test    rax, rax
0x14001cef3  jz      short loc_14001CEFD
0x14001cef5  mov     rcx, rbx
0x14001cef8  call    _guard_dispatch_icall
0x14001cefd  mov     ecx, [rbx+58h]
0x14001cf00  sub     ecx, r15d
0x14001cf03  jz      short loc_14001CF1F
0x14001cf05  cmp     ecx, r15d
0x14001cf08  jnz     short loc_14001CF33
0x14001cf0a  mov     rcx, [rbx+60h]; Lookaside
0x14001cf0e  mov     rdx, rbx; Entry
0x14001cf11  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001cf18  nop     dword ptr [rax+rax+00h]
0x14001cf1d  jmp     short loc_14001CF33
0x14001cf1f  mov     edx, 69706E56h; Tag
0x14001cf24  mov     rcx, rbx; P
0x14001cf27  call    cs:__imp_ExFreePoolWithTag
0x14001cf2e  nop     dword ptr [rax+rax+00h]
0x14001cf33  mov     rbx, [rsp+58h+arg_8]
0x14001cf38  mov     eax, edi
0x14001cf3a  mov     rbp, [rsp+58h+arg_10]
0x14001cf3f  add     rsp, 30h
0x14001cf43  pop     r15
0x14001cf45  pop     r13
0x14001cf47  pop     r12
0x14001cf49  pop     rdi
0x14001cf4a  pop     rsi
0x14001cf4b  retn
```
