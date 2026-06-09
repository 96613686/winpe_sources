# FveReadWriteDriverCleanup

- ea: `0x1400ba6e8`
- end: `0x1400ba82c`
- name: `FveReadWriteDriverCleanup`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140070570`

## callees

- `0x14000f724`
- `0x140082b34`
- `0x1400ba6e8`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400ba814`
- `ntoskrnl!KeReleaseMutex` at `0x1400ba814`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ba723`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ba73b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ba777`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ba723`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ba73b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ba777`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ba710`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ba710`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba753`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba78f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba7a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba7f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba753`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba78f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba7a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba7f0`

## pseudocode

```c
LONG __fastcall FveReadWriteDriverCleanup(__int64 a1)
{
  struct _KMUTANT *v1; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v1 = (struct _KMUTANT *)(a1 + 9608);
  KeWaitForSingleObject((PVOID)(a1 + 9608), Executive, 0, 0, 0);
  ExDeleteNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 9000));
  v3 = *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 9008);
  if ( v3 )
  {
    ExDeleteNPagedLookasideList(v3);
    ExFreePoolWithTag(*(PVOID *)(a1 + 9008), 0x30455646u);
  }
  v4 = *(void **)(a1 + 9016);
  if ( v4 )
    PplDestroyLookasideList(v4);
  ExDeleteNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 9024));
  ExFreePoolWithTag(*(PVOID *)(a1 + 9000), 0x30455646u);
  ExFreePoolWithTag(*(PVOID *)(a1 + 9024), 0x656E6F4Eu);
  v5 = *(void **)(a1 + 1624);
  *(_QWORD *)(a1 + 9000) = 0;
  *(_QWORD *)(a1 + 9008) = 0;
  *(_QWORD *)(a1 + 9016) = 0;
  *(_QWORD *)(a1 + 9024) = 0;
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
0x1400ba6e8  mov     [rsp+arg_0], rbx
0x1400ba6ed  push    rdi
0x1400ba6ee  sub     rsp, 30h
0x1400ba6f2  lea     rdi, [rcx+2588h]
0x1400ba6f9  mov     [rsp+38h+Timeout], 0; Timeout
0x1400ba702  mov     rbx, rcx
0x1400ba705  xor     r9d, r9d; Alertable
0x1400ba708  mov     rcx, rdi; Object
0x1400ba70b  xor     r8d, r8d; WaitMode
0x1400ba70e  xor     edx, edx; WaitReason
0x1400ba710  call    cs:__imp_KeWaitForSingleObject
0x1400ba717  nop     dword ptr [rax+rax+00h]
0x1400ba71c  mov     rcx, [rbx+2328h]; Lookaside
0x1400ba723  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400ba72a  nop     dword ptr [rax+rax+00h]
0x1400ba72f  mov     rcx, [rbx+2330h]; Lookaside
0x1400ba736  test    rcx, rcx
0x1400ba739  jz      short loc_1400BA75F
0x1400ba73b  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400ba742  nop     dword ptr [rax+rax+00h]
0x1400ba747  mov     rcx, [rbx+2330h]; P
0x1400ba74e  mov     edx, 30455646h; Tag
0x1400ba753  call    cs:__imp_ExFreePoolWithTag
0x1400ba75a  nop     dword ptr [rax+rax+00h]
0x1400ba75f  mov     rcx, [rbx+2338h]; P
0x1400ba766  test    rcx, rcx
0x1400ba769  jz      short loc_1400BA770
0x1400ba76b  call    PplDestroyLookasideList
0x1400ba770  mov     rcx, [rbx+2340h]; Lookaside
0x1400ba777  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400ba77e  nop     dword ptr [rax+rax+00h]
0x1400ba783  mov     rcx, [rbx+2328h]; P
0x1400ba78a  mov     edx, 30455646h; Tag
0x1400ba78f  call    cs:__imp_ExFreePoolWithTag
0x1400ba796  nop     dword ptr [rax+rax+00h]
0x1400ba79b  mov     rcx, [rbx+2340h]; P
0x1400ba7a2  mov     edx, 656E6F4Eh; Tag
0x1400ba7a7  call    cs:__imp_ExFreePoolWithTag
0x1400ba7ae  nop     dword ptr [rax+rax+00h]
0x1400ba7b3  mov     rcx, [rbx+658h]; P
0x1400ba7ba  mov     qword ptr [rbx+2328h], 0
0x1400ba7c5  mov     qword ptr [rbx+2330h], 0
0x1400ba7d0  mov     qword ptr [rbx+2338h], 0
0x1400ba7db  mov     qword ptr [rbx+2340h], 0
0x1400ba7e6  test    rcx, rcx
0x1400ba7e9  jz      short loc_1400BA807
0x1400ba7eb  mov     edx, 30455646h; Tag
0x1400ba7f0  call    cs:__imp_ExFreePoolWithTag
0x1400ba7f7  nop     dword ptr [rax+rax+00h]
0x1400ba7fc  mov     qword ptr [rbx+658h], 0
0x1400ba807  mov     rcx, rbx
0x1400ba80a  call    FveConfigUnregisterEventCallbacks
0x1400ba80f  xor     edx, edx; Wait
0x1400ba811  mov     rcx, rdi; Mutex
0x1400ba814  call    cs:__imp_KeReleaseMutex
0x1400ba81b  nop     dword ptr [rax+rax+00h]
0x1400ba820  mov     rbx, [rsp+38h+arg_0]
0x1400ba825  add     rsp, 30h
0x1400ba829  pop     rdi
0x1400ba82a  retn
```
