# VmbusTlDissociateListenerFromService

- ea: `0x1400093e0`
- end: `0x14000959a`
- name: `VmbusTlDissociateListenerFromService`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x140009060`

## callees

- `0x140001508`
- `0x1400093e0`
- `0x1400098f4`
- `0x14000a048`
- `0x14000a154`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009467`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009551`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009467`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009551`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000945b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140009545`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000945b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140009545`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009509`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009509`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400093fc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400093fc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400094f0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400094f0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000940f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000940f`

## string_xrefs

- `0x140009496`: `VmbusTlDissociateListenerFromService`
- `0x140009530`: `VmbusTlDissociateListenerFromService`
- `0x140009574`: `VmbusTlDissociateListenerFromService`

## pseudocode

```c
void __fastcall VmbusTlDissociateListenerFromService(_QWORD *a1)
{
  __int64 v1; // rbx
  __int64 v3; // rcx
  signed __int64 v4; // rax
  bool v5; // cc
  signed __int64 v6; // rax
  void (__fastcall *v7)(__int64); // rax

  v1 = a1[45];
  if ( v1 )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v1 + 16));
    if ( VmbusTlDeleteObjectFromTable(v3, (struct _RTL_AVL_TABLE *)(v1 + 168), a1 + 51, (__int64)a1) )
    {
      --*(_DWORD *)(v1 + 164);
      a1[42] = 0;
      a1[45] = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v1 + 16));
      KeLeaveCriticalRegion();
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlDissociateListenerFromService",
          193,
          v1,
          *(_QWORD *)(v1 + 8),
          (__int64)"Dereference object");
      v4 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v1 + 8), 0xFFFFFFFFFFFFFFFFuLL);
      v5 = v4 <= 1;
      v6 = v4 - 1;
      if ( v5 )
      {
        if ( v6 )
          __fastfail(0xEu);
        v7 = *(void (__fastcall **)(__int64))(v1 + 80);
        if ( v7 )
          v7(v1);
        if ( *(_DWORD *)(v1 + 88) == 1 )
        {
          ExFreePoolWithTag((PVOID)v1, 0x69706E56u);
        }
        else if ( *(_DWORD *)(v1 + 88) == 2 )
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v1 + 96), (PVOID)v1);
        }
      }
    }
    else
    {
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceServiceError(
          (unsigned int)"VmbusTlDissociateListenerFromService",
          197,
          -1073741823,
          v1 + 112,
          (__int64)(a1 + 51));
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v1 + 16));
      KeLeaveCriticalRegion();
    }
  }
  else if ( (unsigned int)dword_140013058 > 2 )
  {
    HvsocketTraceEndpointGuidError(
      (unsigned int)"VmbusTlDissociateListenerFromService",
      203,
      -1073741275,
      (_DWORD)a1,
      (__int64)(a1 + 51));
  }
}

```

## disassembly

```asm
0x1400093e0  push    rbx
0x1400093e2  push    rbp
0x1400093e3  push    rsi
0x1400093e4  push    rdi
0x1400093e5  sub     rsp, 38h
0x1400093e9  mov     rbx, [rcx+168h]
0x1400093f0  mov     rdi, rcx
0x1400093f3  test    rbx, rbx
0x1400093f6  jz      loc_14000955F
0x1400093fc  call    cs:__imp_KeEnterCriticalRegion
0x140009403  nop     dword ptr [rax+rax+00h]
0x140009408  lea     rsi, [rbx+10h]
0x14000940c  mov     rcx, rsi; FastMutex
0x14000940f  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140009416  nop     dword ptr [rax+rax+00h]
0x14000941b  lea     rbp, [rdi+198h]
0x140009422  mov     r9, rdi
0x140009425  mov     r8, rbp
0x140009428  lea     rdx, [rbx+0A8h]
0x14000942f  call    VmbusTlDeleteObjectFromTable
0x140009434  test    al, al
0x140009436  jz      loc_140009517
0x14000943c  dec     dword ptr [rbx+0A4h]
0x140009442  mov     rcx, rsi; FastMutex
0x140009445  mov     qword ptr [rdi+150h], 0
0x140009450  mov     qword ptr [rdi+168h], 0
0x14000945b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140009462  nop     dword ptr [rax+rax+00h]
0x140009467  call    cs:__imp_KeLeaveCriticalRegion
0x14000946e  nop     dword ptr [rax+rax+00h]
0x140009473  mov     eax, cs:dword_140013058
0x140009479  cmp     eax, 5
0x14000947c  jbe     short loc_1400094A2
0x14000947e  mov     r9, [rbx+8]
0x140009482  lea     rax, aDereferenceObj; "Dereference object"
0x140009489  mov     r8, rbx
0x14000948c  mov     [rsp+58h+var_38], rax
0x140009491  mov     edx, 0C1h
0x140009496  lea     rcx, aVmbustldissoci_2; "VmbusTlDissociateListenerFromService"
0x14000949d  call    HvsocketTraceReferenceCount
0x1400094a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400094a6  lock xadd [rbx+8], rax
0x1400094ac  sub     rax, 1
0x1400094b0  jg      loc_140009590
0x1400094b6  test    rax, rax
0x1400094b9  jz      short loc_1400094C7
0x1400094bb  mov     ecx, 0Eh
0x1400094c0  int     29h; Win8: RtlFailFast(ecx)
0x1400094c2  jmp     loc_140009590
0x1400094c7  mov     rax, [rbx+50h]
0x1400094cb  test    rax, rax
0x1400094ce  jz      short loc_1400094D8
0x1400094d0  mov     rcx, rbx
0x1400094d3  call    _guard_dispatch_icall
0x1400094d8  mov     ecx, [rbx+58h]
0x1400094db  sub     ecx, 1
0x1400094de  jz      short loc_140009501
0x1400094e0  cmp     ecx, 1
0x1400094e3  jnz     loc_140009590
0x1400094e9  mov     rcx, [rbx+60h]; Lookaside
0x1400094ed  mov     rdx, rbx; Entry
0x1400094f0  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400094f7  nop     dword ptr [rax+rax+00h]
0x1400094fc  jmp     loc_140009590
0x140009501  mov     edx, 69706E56h; Tag
0x140009506  mov     rcx, rbx; P
0x140009509  call    cs:__imp_ExFreePoolWithTag
0x140009510  nop     dword ptr [rax+rax+00h]
0x140009515  jmp     short loc_140009590
0x140009517  mov     eax, cs:dword_140013058
0x14000951d  cmp     eax, 2
0x140009520  jbe     short loc_140009542
0x140009522  lea     r9, [rbx+70h]
0x140009526  mov     [rsp+58h+var_38], rbp
0x14000952b  mov     edx, 0C5h
0x140009530  lea     rcx, aVmbustldissoci_2; "VmbusTlDissociateListenerFromService"
0x140009537  mov     r8d, 0C0000001h
0x14000953d  call    HvsocketTraceServiceError
0x140009542  mov     rcx, rsi; FastMutex
0x140009545  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14000954c  nop     dword ptr [rax+rax+00h]
0x140009551  call    cs:__imp_KeLeaveCriticalRegion
0x140009558  nop     dword ptr [rax+rax+00h]
0x14000955d  jmp     short loc_140009590
0x14000955f  mov     eax, cs:dword_140013058
0x140009565  cmp     eax, 2
0x140009568  jbe     short loc_140009590
0x14000956a  lea     rax, [rcx+198h]
0x140009571  mov     r9, rdi
0x140009574  lea     rcx, aVmbustldissoci_2; "VmbusTlDissociateListenerFromService"
0x14000957b  mov     [rsp+58h+var_38], rax
0x140009580  mov     edx, 0CBh
0x140009585  mov     r8d, 0C0000225h
0x14000958b  call    HvsocketTraceEndpointGuidError
0x140009590  add     rsp, 38h
0x140009594  pop     rdi
0x140009595  pop     rsi
0x140009596  pop     rbp
0x140009597  pop     rbx
0x140009598  retn
```
