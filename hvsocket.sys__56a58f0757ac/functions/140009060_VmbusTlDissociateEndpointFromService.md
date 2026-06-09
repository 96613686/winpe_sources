# VmbusTlDissociateEndpointFromService

- ea: `0x140009060`
- end: `0x1400093da`
- name: `VmbusTlDissociateEndpointFromService`
- size: `890`
- prototype: `void __fastcall(char *P)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x14001f1ec`
- `0x14001f464`

## callees

- `0x140008e7c`
- `0x140009060`
- `0x1400093e0`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000917a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400092ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400092d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000917a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400092ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400092d6`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x1400091e2`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x1400091e2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000916e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400092ae`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400092ca`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000916e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400092ae`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400092ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000936d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400093c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000936d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400093c0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009070`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000918f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400091ab`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009070`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000918f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400091ab`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140009354`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400093aa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140009354`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400093aa`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140009080`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000919f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400091bb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140009080`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000919f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400091bb`

## string_xrefs

- `0x1400090d3`: `VmbusTlDissociateEndpointFromService`
- `0x14000913a`: `VmbusTlDissociateEndpointFromService`
- `0x14000927a`: `VmbusTlDissociateEndpointFromService`
- `0x1400092f1`: `VmbusTlDissociateEndpointFromService`

## pseudocode

```c
void __fastcall VmbusTlDissociateEndpointFromService(char *P)
{
  int v2; // eax
  __int64 v3; // rbx
  __int64 v4; // rsi
  PNPAGED_LOOKASIDE_LIST *v5; // rdi
  __int64 v6; // rax
  PNPAGED_LOOKASIDE_LIST **v7; // rcx
  signed __int64 v8; // rax
  bool v9; // cc
  signed __int64 v10; // rax
  signed __int64 v11; // rax
  signed __int64 v12; // rax
  void (__fastcall *v13)(__int64); // rax
  void (__fastcall *v14)(__int64); // rax

  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(P + 16));
  v2 = *((_DWORD *)P + 26);
  if ( v2 == 3 )
  {
    v3 = *((_QWORD *)P + 45);
    v4 = *((_QWORD *)P + 46);
    if ( v3 )
    {
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (const int *)"VmbusTlDissociateEndpointFromService",
          70,
          *((_QWORD *)P + 45),
          *(_QWORD *)(v3 + 8),
          (const int *)"Reference object");
      if ( _InterlockedIncrement64((volatile signed __int64 *)(v3 + 8)) <= 1 )
        __fastfail(0xEu);
    }
    VmbusTlDissociateListenerFromService(P);
  }
  else if ( v2 == 2 )
  {
    v3 = *((_QWORD *)P + 109);
    v4 = *((_QWORD *)P + 92);
    if ( v3 )
    {
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (const int *)"VmbusTlDissociateEndpointFromService",
          82,
          *((_QWORD *)P + 109),
          *(_QWORD *)(v3 + 8),
          (const int *)"Reference object");
      if ( _InterlockedIncrement64((volatile signed __int64 *)(v3 + 8)) <= 1 )
        __fastfail(0xEu);
    }
    VmbusTlDissociateConnectionFromService(P);
  }
  else
  {
    v3 = 0;
    v4 = 0;
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(P + 16));
  KeLeaveCriticalRegion();
  if ( v3 )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v4 + 16));
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v3 + 16));
    if ( *(_DWORD *)(v3 + 156) == 1 )
    {
      if ( RtlIsGenericTableEmptyAvl((PRTL_AVL_TABLE)(v3 + 168)) )
      {
        if ( *(_QWORD *)(v3 + 272) == v3 + 272 && *(_QWORD *)(v3 + 288) == v3 + 288 && *(_QWORD *)(v3 + 312) == v3 + 312 )
        {
          v5 = (PNPAGED_LOOKASIDE_LIST *)(v3 + 96);
          v6 = *(_QWORD *)(v3 + 96);
          if ( v6 != v3 + 96 )
          {
            if ( *(PNPAGED_LOOKASIDE_LIST **)(v6 + 8) != v5 || (v7 = *(PNPAGED_LOOKASIDE_LIST ***)(v3 + 104), *v7 != v5) )
              __fastfail(3u);
            *v7 = (PNPAGED_LOOKASIDE_LIST *)v6;
            *(_QWORD *)(v6 + 8) = v7;
            *(_QWORD *)(v3 + 104) = v3 + 96;
            *v5 = (PNPAGED_LOOKASIDE_LIST)v5;
            if ( (unsigned int)dword_140013058 > 5 )
              HvsocketTraceReferenceCount(
                (const int *)"VmbusTlDissociateEndpointFromService",
                111,
                v3,
                *(_QWORD *)(v3 + 8),
                (const int *)"Dereference object");
            v8 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v3 + 8), 0xFFFFFFFFFFFFFFFFuLL);
            v9 = v8 <= 1;
            v10 = v8 - 1;
            if ( v9 )
            {
              if ( v10 )
                __fastfail(0xEu);
              v13 = *(void (__fastcall **)(__int64))(v3 + 80);
              if ( v13 )
                v13(v3);
              if ( *(_DWORD *)(v3 + 88) == 1 )
              {
                ExFreePoolWithTag((PVOID)v3, 0x69706E56u);
              }
              else if ( *(_DWORD *)(v3 + 88) == 2 )
              {
                ExFreeToNPagedLookasideList(*v5, (PVOID)v3);
              }
            }
          }
        }
      }
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v3 + 16));
    KeLeaveCriticalRegion();
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v4 + 16));
    KeLeaveCriticalRegion();
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlDissociateEndpointFromService",
        115,
        v3,
        *(_QWORD *)(v3 + 8),
        (const int *)"Dereference object");
    v11 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v3 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v9 = v11 <= 1;
    v12 = v11 - 1;
    if ( v9 )
    {
      if ( v12 )
        __fastfail(0xEu);
      v14 = *(void (__fastcall **)(__int64))(v3 + 80);
      if ( v14 )
        v14(v3);
      if ( *(_DWORD *)(v3 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v3, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v3 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v3 + 96), (PVOID)v3);
      }
    }
  }
}

```

## disassembly

```asm
0x140009060  push    rbx
0x140009062  push    rbp
0x140009063  push    rsi
0x140009064  push    rdi
0x140009065  push    r12
0x140009067  push    r14
0x140009069  sub     rsp, 38h
0x14000906d  mov     rdi, rcx
0x140009070  call    cs:__imp_KeEnterCriticalRegion
0x140009077  nop     dword ptr [rax+rax+00h]
0x14000907c  lea     rcx, [rdi+10h]; FastMutex
0x140009080  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140009087  nop     dword ptr [rax+rax+00h]
0x14000908c  mov     eax, [rdi+68h]
0x14000908f  mov     r14d, 1
0x140009095  lea     r12d, [r14+0Dh]
0x140009099  cmp     eax, 3
0x14000909c  jnz     short loc_1400090FF
0x14000909e  mov     rbx, [rdi+168h]
0x1400090a5  mov     rsi, [rdi+170h]
0x1400090ac  test    rbx, rbx
0x1400090af  jz      short loc_1400090F5
0x1400090b1  mov     eax, cs:dword_140013058
0x1400090b7  cmp     eax, 5
0x1400090ba  jbe     short loc_1400090DF
0x1400090bc  mov     r9, [rbx+8]
0x1400090c0  lea     rax, aReferenceObjec; "Reference object"
0x1400090c7  mov     r8, rbx
0x1400090ca  mov     [rsp+68h+var_48], rax
0x1400090cf  lea     edx, [r14+45h]
0x1400090d3  lea     rcx, aVmbustldissoci; "VmbusTlDissociateEndpointFromService"
0x1400090da  call    HvsocketTraceReferenceCount
0x1400090df  mov     rax, r14
0x1400090e2  lock xadd [rbx+8], rax
0x1400090e8  add     rax, r14
0x1400090eb  cmp     rax, r14
0x1400090ee  jg      short loc_1400090F5
0x1400090f0  mov     rcx, r12
0x1400090f3  int     29h; Win8: RtlFailFast(ecx)
0x1400090f5  mov     rcx, rdi
0x1400090f8  call    VmbusTlDissociateListenerFromService
0x1400090fd  jmp     short loc_14000916A
0x1400090ff  cmp     eax, 2
0x140009102  jnz     short loc_140009166
0x140009104  mov     rbx, [rdi+368h]
0x14000910b  mov     rsi, [rdi+2E0h]
0x140009112  test    rbx, rbx
0x140009115  jz      short loc_14000915C
0x140009117  mov     eax, cs:dword_140013058
0x14000911d  cmp     eax, 5
0x140009120  jbe     short loc_140009146
0x140009122  mov     r9, [rbx+8]
0x140009126  lea     rax, aReferenceObjec; "Reference object"
0x14000912d  mov     r8, rbx
0x140009130  mov     [rsp+68h+var_48], rax
0x140009135  mov     edx, 52h ; 'R'
0x14000913a  lea     rcx, aVmbustldissoci; "VmbusTlDissociateEndpointFromService"
0x140009141  call    HvsocketTraceReferenceCount
0x140009146  mov     rax, r14
0x140009149  lock xadd [rbx+8], rax
0x14000914f  add     rax, r14
0x140009152  cmp     rax, r14
0x140009155  jg      short loc_14000915C
0x140009157  mov     rcx, r12
0x14000915a  int     29h; Win8: RtlFailFast(ecx)
0x14000915c  mov     rcx, rdi; P
0x14000915f  call    VmbusTlDissociateConnectionFromService
0x140009164  jmp     short loc_14000916A
0x140009166  xor     ebx, ebx
0x140009168  xor     esi, esi
0x14000916a  lea     rcx, [rdi+10h]; FastMutex
0x14000916e  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140009175  nop     dword ptr [rax+rax+00h]
0x14000917a  call    cs:__imp_KeLeaveCriticalRegion
0x140009181  nop     dword ptr [rax+rax+00h]
0x140009186  test    rbx, rbx
0x140009189  jz      loc_1400093CC
0x14000918f  call    cs:__imp_KeEnterCriticalRegion
0x140009196  nop     dword ptr [rax+rax+00h]
0x14000919b  lea     rcx, [rsi+10h]; FastMutex
0x14000919f  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400091a6  nop     dword ptr [rax+rax+00h]
0x1400091ab  call    cs:__imp_KeEnterCriticalRegion
0x1400091b2  nop     dword ptr [rax+rax+00h]
0x1400091b7  lea     rcx, [rbx+10h]; FastMutex
0x1400091bb  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400091c2  nop     dword ptr [rax+rax+00h]
0x1400091c7  lea     rdi, aDereferenceObj; "Dereference object"
0x1400091ce  cmp     [rbx+9Ch], r14d
0x1400091d5  jnz     loc_1400092AA
0x1400091db  lea     rcx, [rbx+0A8h]; Table
0x1400091e2  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x1400091e9  nop     dword ptr [rax+rax+00h]
0x1400091ee  test    al, al
0x1400091f0  jz      loc_1400092AA
0x1400091f6  lea     rax, [rbx+110h]
0x1400091fd  cmp     [rax], rax
0x140009200  jnz     loc_1400092AA
0x140009206  lea     rax, [rbx+120h]
0x14000920d  cmp     [rax], rax
0x140009210  jnz     loc_1400092AA
0x140009216  lea     rax, [rbx+138h]
0x14000921d  cmp     [rax], rax
0x140009220  jnz     loc_1400092AA
0x140009226  lea     rdi, [rbx+60h]
0x14000922a  mov     rax, [rdi]
0x14000922d  cmp     rax, rdi
0x140009230  jz      short loc_1400092A3
0x140009232  cmp     [rax+8], rdi
0x140009236  jnz     loc_14000937E
0x14000923c  mov     rcx, [rdi+8]
0x140009240  cmp     [rcx], rdi
0x140009243  jnz     loc_14000937E
0x140009249  mov     [rcx], rax
0x14000924c  mov     [rax+8], rcx
0x140009250  mov     [rdi+8], rdi
0x140009254  mov     [rdi], rdi
0x140009257  mov     eax, cs:dword_140013058
0x14000925d  cmp     eax, 5
0x140009260  jbe     short loc_140009286
0x140009262  mov     r9, [rbx+8]
0x140009266  lea     rax, aDereferenceObj; "Dereference object"
0x14000926d  mov     r8, rbx
0x140009270  mov     [rsp+68h+var_48], rax
0x140009275  mov     edx, 6Fh ; 'o'
0x14000927a  lea     rcx, aVmbustldissoci; "VmbusTlDissociateEndpointFromService"
0x140009281  call    HvsocketTraceReferenceCount
0x140009286  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000928a  lock xadd [rbx+8], rax
0x140009290  sub     rax, r14
0x140009293  jg      short loc_1400092A3
0x140009295  test    rax, rax
0x140009298  jz      loc_14000932C
0x14000929e  mov     rcx, r12
0x1400092a1  int     29h; Win8: RtlFailFast(ecx)
0x1400092a3  lea     rdi, aDereferenceObj; "Dereference object"
0x1400092aa  lea     rcx, [rbx+10h]; FastMutex
0x1400092ae  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400092b5  nop     dword ptr [rax+rax+00h]
0x1400092ba  call    cs:__imp_KeLeaveCriticalRegion
0x1400092c1  nop     dword ptr [rax+rax+00h]
0x1400092c6  lea     rcx, [rsi+10h]; FastMutex
0x1400092ca  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400092d1  nop     dword ptr [rax+rax+00h]
0x1400092d6  call    cs:__imp_KeLeaveCriticalRegion
0x1400092dd  nop     dword ptr [rax+rax+00h]
0x1400092e2  mov     eax, cs:dword_140013058
0x1400092e8  cmp     eax, 5
0x1400092eb  jbe     short loc_14000930A
0x1400092ed  mov     r9, [rbx+8]
0x1400092f1  lea     rcx, aVmbustldissoci; "VmbusTlDissociateEndpointFromService"
0x1400092f8  mov     r8, rbx
0x1400092fb  mov     [rsp+68h+var_48], rdi
0x140009300  mov     edx, 73h ; 's'
0x140009305  call    HvsocketTraceReferenceCount
0x14000930a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000930e  lock xadd [rbx+8], rax
0x140009314  sub     rax, r14
0x140009317  jg      loc_1400093CC
0x14000931d  test    rax, rax
0x140009320  jz      short loc_140009385
0x140009322  mov     rcx, r12
0x140009325  int     29h; Win8: RtlFailFast(ecx)
0x140009327  jmp     loc_1400093CC
0x14000932c  mov     rax, [rbx+50h]
0x140009330  test    rax, rax
0x140009333  jz      short loc_14000933D
0x140009335  mov     rcx, rbx
0x140009338  call    _guard_dispatch_icall
0x14000933d  mov     ecx, [rbx+58h]
0x140009340  sub     ecx, r14d
0x140009343  jz      short loc_140009365
0x140009345  cmp     ecx, r14d
0x140009348  jnz     loc_1400092A3
0x14000934e  mov     rcx, [rdi]; Lookaside
0x140009351  mov     rdx, rbx; Entry
0x140009354  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000935b  nop     dword ptr [rax+rax+00h]
0x140009360  jmp     loc_1400092A3
0x140009365  mov     edx, 69706E56h; Tag
0x14000936a  mov     rcx, rbx; P
0x14000936d  call    cs:__imp_ExFreePoolWithTag
0x140009374  nop     dword ptr [rax+rax+00h]
0x140009379  jmp     loc_1400092A3
0x14000937e  mov     ecx, 3
0x140009383  int     29h; Win8: RtlFailFast(ecx)
0x140009385  mov     rax, [rbx+50h]
0x140009389  test    rax, rax
0x14000938c  jz      short loc_140009396
0x14000938e  mov     rcx, rbx
0x140009391  call    _guard_dispatch_icall
0x140009396  mov     ecx, [rbx+58h]
0x140009399  sub     ecx, r14d
0x14000939c  jz      short loc_1400093B8
0x14000939e  cmp     ecx, r14d
0x1400093a1  jnz     short loc_1400093CC
0x1400093a3  mov     rcx, [rbx+60h]; Lookaside
0x1400093a7  mov     rdx, rbx; Entry
0x1400093aa  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400093b1  nop     dword ptr [rax+rax+00h]
0x1400093b6  jmp     short loc_1400093CC
0x1400093b8  mov     edx, 69706E56h; Tag
0x1400093bd  mov     rcx, rbx; P
0x1400093c0  call    cs:__imp_ExFreePoolWithTag
0x1400093c7  nop     dword ptr [rax+rax+00h]
0x1400093cc  add     rsp, 38h
0x1400093d0  pop     r14
0x1400093d2  pop     r12
0x1400093d4  pop     rdi
0x1400093d5  pop     rsi
0x1400093d6  pop     rbp
0x1400093d7  pop     rbx
0x1400093d8  retn
```
