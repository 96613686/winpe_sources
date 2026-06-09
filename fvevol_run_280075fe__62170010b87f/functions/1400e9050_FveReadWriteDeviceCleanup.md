# FveReadWriteDeviceCleanup

- ea: `0x1400e9050`
- end: `0x1400e923b`
- name: `FveReadWriteDeviceCleanup`
- size: `491`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140023a64`
- `0x14002f430`
- `0x1400e9244`

## callees

- `0x14000b870`
- `0x1400cfb90`
- `0x1400e9050`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400e9225`
- `ntoskrnl!KeReleaseMutex` at `0x1400e9225`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400e91bb`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400e91bb`
- `ntoskrnl!MmFreeMappingAddress` at `0x1400e9167`
- `ntoskrnl!MmFreeMappingAddress` at `0x1400e9167`
- `ntoskrnl!IoFreeMdl` at `0x1400e918a`
- `ntoskrnl!IoFreeMdl` at `0x1400e918a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e907e`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e907e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e90d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e9117`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e913f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e91d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e9209`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e90d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e9117`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e913f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e91d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e9209`

## pseudocode

```c
LONG __fastcall FveReadWriteDeviceCleanup(__int64 a1, char a2)
{
  __int64 v2; // rsi
  int v5; // eax
  void *v6; // rcx
  __int64 v7; // rdx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  struct _MDL *v11; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v12; // rcx
  void *v13; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  KeWaitForSingleObject((PVOID)(v2 + 9608), Executive, 0, 0, 0);
  v5 = *(_DWORD *)(a1 + 4712);
  if ( v5 && (a2 || v5 != 1) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 4712));
    if ( a2 || *(int *)(a1 + 4712) <= 0 )
    {
      v6 = *(void **)(a1 + 2040);
      if ( v6 )
      {
        ExFreePoolWithTag(v6, 0x78455646u);
        *(_QWORD *)(a1 + 2040) = 0;
      }
      v7 = *(_QWORD *)(a1 + 2056);
      if ( v7 )
      {
        *(_QWORD *)(a1 + 2056) = 0;
        ReleaseSubIrp(a1, v7);
      }
      v8 = *(void **)(a1 + 2072);
      if ( v8 )
      {
        ExFreePoolWithTag(v8, 0x77455646u);
        *(_QWORD *)(a1 + 2072) = 0;
      }
      v9 = *(void **)(a1 + 2088);
      if ( v9 )
      {
        ExFreePoolWithTag(v9, 0x70455646u);
        *(_QWORD *)(a1 + 2088) = 0;
      }
      v10 = *(void **)(a1 + 2104);
      if ( v10 )
      {
        MmFreeMappingAddress(v10, 0x72455646u);
        *(_QWORD *)(a1 + 2104) = 0;
      }
      v11 = *(struct _MDL **)(a1 + 2112);
      if ( v11 )
      {
        IoFreeMdl(v11);
        *(_QWORD *)(a1 + 2112) = 0;
      }
      v12 = *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 2016);
      if ( v12 )
      {
        if ( v12 != *(struct _NPAGED_LOOKASIDE_LIST **)(v2 + 9008) )
        {
          ExDeleteNPagedLookasideList(v12);
          ExFreePoolWithTag(*(PVOID *)(a1 + 2016), 0x30455646u);
        }
        *(_QWORD *)(a1 + 2016) = 0;
      }
      *(_QWORD *)(a1 + 2024) = 0;
      if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline() )
      {
        v13 = *(void **)(a1 + 2176);
        if ( v13 )
        {
          ExFreePoolWithTag(v13, 0x30455646u);
          *(_QWORD *)(a1 + 2176) = 0;
        }
      }
    }
  }
  return KeReleaseMutex((PRKMUTEX)(v2 + 9608), 0);
}

```

## disassembly

```asm
0x1400e9050  push    rbx
0x1400e9052  push    rbp
0x1400e9053  push    rsi
0x1400e9054  push    rdi
0x1400e9055  sub     rsp, 38h
0x1400e9059  mov     rsi, [rcx+8]
0x1400e905d  mov     dil, dl
0x1400e9060  mov     rbx, rcx
0x1400e9063  mov     [rsp+58h+Timeout], 0; Timeout
0x1400e906c  xor     r9d, r9d; Alertable
0x1400e906f  xor     r8d, r8d; WaitMode
0x1400e9072  xor     edx, edx; WaitReason
0x1400e9074  lea     rbp, [rsi+2588h]
0x1400e907b  mov     rcx, rbp; Object
0x1400e907e  call    cs:__imp_KeWaitForSingleObject
0x1400e9085  nop     dword ptr [rax+rax+00h]
0x1400e908a  mov     eax, [rbx+1268h]
0x1400e9090  test    eax, eax
0x1400e9092  jz      loc_1400E9220
0x1400e9098  test    dil, dil
0x1400e909b  jnz     short loc_1400E90A6
0x1400e909d  cmp     eax, 1
0x1400e90a0  jz      loc_1400E9220
0x1400e90a6  lock dec dword ptr [rbx+1268h]
0x1400e90ad  test    dil, dil
0x1400e90b0  jnz     short loc_1400E90BF
0x1400e90b2  cmp     dword ptr [rbx+1268h], 0
0x1400e90b9  jg      loc_1400E9220
0x1400e90bf  mov     rcx, [rbx+7F8h]; P
0x1400e90c6  test    rcx, rcx
0x1400e90c9  jz      short loc_1400E90E7
0x1400e90cb  mov     edx, 78455646h; Tag
0x1400e90d0  call    cs:__imp_ExFreePoolWithTag
0x1400e90d7  nop     dword ptr [rax+rax+00h]
0x1400e90dc  mov     qword ptr [rbx+7F8h], 0
0x1400e90e7  mov     rdx, [rbx+808h]
0x1400e90ee  test    rdx, rdx
0x1400e90f1  jz      short loc_1400E9106
0x1400e90f3  mov     rcx, rbx
0x1400e90f6  mov     qword ptr [rbx+808h], 0
0x1400e9101  call    ReleaseSubIrp
0x1400e9106  mov     rcx, [rbx+818h]; P
0x1400e910d  test    rcx, rcx
0x1400e9110  jz      short loc_1400E912E
0x1400e9112  mov     edx, 77455646h; Tag
0x1400e9117  call    cs:__imp_ExFreePoolWithTag
0x1400e911e  nop     dword ptr [rax+rax+00h]
0x1400e9123  mov     qword ptr [rbx+818h], 0
0x1400e912e  mov     rcx, [rbx+828h]; P
0x1400e9135  test    rcx, rcx
0x1400e9138  jz      short loc_1400E9156
0x1400e913a  mov     edx, 70455646h; Tag
0x1400e913f  call    cs:__imp_ExFreePoolWithTag
0x1400e9146  nop     dword ptr [rax+rax+00h]
0x1400e914b  mov     qword ptr [rbx+828h], 0
0x1400e9156  mov     rcx, [rbx+838h]; BaseAddress
0x1400e915d  test    rcx, rcx
0x1400e9160  jz      short loc_1400E917E
0x1400e9162  mov     edx, 72455646h; PoolTag
0x1400e9167  call    cs:__imp_MmFreeMappingAddress
0x1400e916e  nop     dword ptr [rax+rax+00h]
0x1400e9173  mov     qword ptr [rbx+838h], 0
0x1400e917e  mov     rcx, [rbx+840h]; Mdl
0x1400e9185  test    rcx, rcx
0x1400e9188  jz      short loc_1400E91A1
0x1400e918a  call    cs:__imp_IoFreeMdl
0x1400e9191  nop     dword ptr [rax+rax+00h]
0x1400e9196  mov     qword ptr [rbx+840h], 0
0x1400e91a1  mov     rcx, [rbx+7E0h]; Lookaside
0x1400e91a8  mov     edi, 30455646h
0x1400e91ad  test    rcx, rcx
0x1400e91b0  jz      short loc_1400E91E7
0x1400e91b2  cmp     rcx, [rsi+2330h]
0x1400e91b9  jz      short loc_1400E91DC
0x1400e91bb  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400e91c2  nop     dword ptr [rax+rax+00h]
0x1400e91c7  mov     rcx, [rbx+7E0h]; P
0x1400e91ce  mov     edx, edi; Tag
0x1400e91d0  call    cs:__imp_ExFreePoolWithTag
0x1400e91d7  nop     dword ptr [rax+rax+00h]
0x1400e91dc  mov     qword ptr [rbx+7E0h], 0
0x1400e91e7  mov     qword ptr [rbx+7E8h], 0
0x1400e91f2  call    Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline
0x1400e91f7  test    eax, eax
0x1400e91f9  jz      short loc_1400E9220
0x1400e91fb  mov     rcx, [rbx+880h]; P
0x1400e9202  test    rcx, rcx
0x1400e9205  jz      short loc_1400E9220
0x1400e9207  mov     edx, edi; Tag
0x1400e9209  call    cs:__imp_ExFreePoolWithTag
0x1400e9210  nop     dword ptr [rax+rax+00h]
0x1400e9215  mov     qword ptr [rbx+880h], 0
0x1400e9220  xor     edx, edx; Wait
0x1400e9222  mov     rcx, rbp; Mutex
0x1400e9225  call    cs:__imp_KeReleaseMutex
0x1400e922c  nop     dword ptr [rax+rax+00h]
0x1400e9231  add     rsp, 38h
0x1400e9235  pop     rdi
0x1400e9236  pop     rsi
0x1400e9237  pop     rbp
0x1400e9238  pop     rbx
0x1400e9239  retn
```
