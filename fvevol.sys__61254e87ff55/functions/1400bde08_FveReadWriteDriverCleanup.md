# FveReadWriteDriverCleanup

- ea: `0x1400bde08`
- end: `0x1400bdf4c`
- name: `FveReadWriteDriverCleanup`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140072540`

## callees

- `0x14000fa9c`
- `0x140084bd4`
- `0x1400bde08`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400bdf34`
- `ntoskrnl!KeReleaseMutex` at `0x1400bdf34`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400bde43`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400bde5b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400bde97`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400bde43`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400bde5b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400bde97`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bde30`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bde30`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bde73`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bdeaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bdec7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bdf10`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bde73`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bdeaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bdec7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bdf10`

## pseudocode

```c
LONG __fastcall FveReadWriteDriverCleanup(__int64 a1)
{
  struct _KMUTANT *v1; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v1 = (struct _KMUTANT *)(a1 + 9856);
  KeWaitForSingleObject((PVOID)(a1 + 9856), Executive, 0, 0, 0);
  ExDeleteNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 9248));
  v3 = *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 9256);
  if ( v3 )
  {
    ExDeleteNPagedLookasideList(v3);
    ExFreePoolWithTag(*(PVOID *)(a1 + 9256), 0x30455646u);
  }
  v4 = *(void **)(a1 + 9264);
  if ( v4 )
    PplDestroyLookasideList(v4);
  ExDeleteNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 9272));
  ExFreePoolWithTag(*(PVOID *)(a1 + 9248), 0x30455646u);
  ExFreePoolWithTag(*(PVOID *)(a1 + 9272), 0x656E6F4Eu);
  v5 = *(void **)(a1 + 1624);
  *(_QWORD *)(a1 + 9248) = 0;
  *(_QWORD *)(a1 + 9256) = 0;
  *(_QWORD *)(a1 + 9264) = 0;
  *(_QWORD *)(a1 + 9272) = 0;
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0x30455646u);
    *(_QWORD *)(a1 + 1624) = 0;
  }
  FveConfigUnregisterEventCallbacks(a1);
  return KeReleaseMutex(v1, 0);
}

```

## disassembly

```asm
0x1400bde08  mov     [rsp+arg_0], rbx
0x1400bde0d  push    rdi
0x1400bde0e  sub     rsp, 30h
0x1400bde12  lea     rdi, [rcx+2680h]
0x1400bde19  mov     [rsp+38h+Timeout], 0; Timeout
0x1400bde22  mov     rbx, rcx
0x1400bde25  xor     r9d, r9d; Alertable
0x1400bde28  mov     rcx, rdi; Object
0x1400bde2b  xor     r8d, r8d; WaitMode
0x1400bde2e  xor     edx, edx; WaitReason
0x1400bde30  call    cs:__imp_KeWaitForSingleObject
0x1400bde37  nop     dword ptr [rax+rax+00h]
0x1400bde3c  mov     rcx, [rbx+2420h]; Lookaside
0x1400bde43  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400bde4a  nop     dword ptr [rax+rax+00h]
0x1400bde4f  mov     rcx, [rbx+2428h]; Lookaside
0x1400bde56  test    rcx, rcx
0x1400bde59  jz      short loc_1400BDE7F
0x1400bde5b  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400bde62  nop     dword ptr [rax+rax+00h]
0x1400bde67  mov     rcx, [rbx+2428h]; P
0x1400bde6e  mov     edx, 30455646h; Tag
0x1400bde73  call    cs:__imp_ExFreePoolWithTag
0x1400bde7a  nop     dword ptr [rax+rax+00h]
0x1400bde7f  mov     rcx, [rbx+2430h]; P
0x1400bde86  test    rcx, rcx
0x1400bde89  jz      short loc_1400BDE90
0x1400bde8b  call    PplDestroyLookasideList
0x1400bde90  mov     rcx, [rbx+2438h]; Lookaside
0x1400bde97  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400bde9e  nop     dword ptr [rax+rax+00h]
0x1400bdea3  mov     rcx, [rbx+2420h]; P
0x1400bdeaa  mov     edx, 30455646h; Tag
0x1400bdeaf  call    cs:__imp_ExFreePoolWithTag
0x1400bdeb6  nop     dword ptr [rax+rax+00h]
0x1400bdebb  mov     rcx, [rbx+2438h]; P
0x1400bdec2  mov     edx, 656E6F4Eh; Tag
0x1400bdec7  call    cs:__imp_ExFreePoolWithTag
0x1400bdece  nop     dword ptr [rax+rax+00h]
0x1400bded3  mov     rcx, [rbx+658h]; P
0x1400bdeda  mov     qword ptr [rbx+2420h], 0
0x1400bdee5  mov     qword ptr [rbx+2428h], 0
0x1400bdef0  mov     qword ptr [rbx+2430h], 0
0x1400bdefb  mov     qword ptr [rbx+2438h], 0
0x1400bdf06  test    rcx, rcx
0x1400bdf09  jz      short loc_1400BDF27
0x1400bdf0b  mov     edx, 30455646h; Tag
0x1400bdf10  call    cs:__imp_ExFreePoolWithTag
0x1400bdf17  nop     dword ptr [rax+rax+00h]
0x1400bdf1c  mov     qword ptr [rbx+658h], 0
0x1400bdf27  mov     rcx, rbx
0x1400bdf2a  call    FveConfigUnregisterEventCallbacks
0x1400bdf2f  xor     edx, edx; Wait
0x1400bdf31  mov     rcx, rdi; Mutex
0x1400bdf34  call    cs:__imp_KeReleaseMutex
0x1400bdf3b  nop     dword ptr [rax+rax+00h]
0x1400bdf40  mov     rbx, [rsp+38h+arg_0]
0x1400bdf45  add     rsp, 30h
0x1400bdf49  pop     rdi
0x1400bdf4a  retn
```
