# FveHwAccelCleanup

- ea: `0x1400ced7c`
- end: `0x1400cee5c`
- name: `FveHwAccelCleanup`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400716e8`

## callees

- `0x1400ced7c`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400cedd8`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400cee13`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400cedd8`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400cee13`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400cee49`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400cee49`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cedf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cee2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cedf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cee2b`
- `ext-ms-win-accel-api-km-l1-1-1!AccelDestroyOffloadWorkspace` at `0x1400cedb5`
- `ext-ms-win-accel-api-km-l1-1-1!AccelDestroyOffloadWorkspace` at `0x1400cedb5`
- `ext-ms-win-accel-api-km-l1-1-1!AccelCloseResource` at `0x1400ced9d`
- `ext-ms-win-accel-api-km-l1-1-1!AccelCloseResource` at `0x1400ced9d`

## pseudocode

```c
NTSTATUS __fastcall FveHwAccelCleanup(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v7; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v8; // rcx

  if ( (*(_DWORD *)(a1 + 9928) & 0x800000) == 0 )
  {
    v5 = *(_QWORD *)(a1 + 10736);
    if ( v5 )
      AccelCloseResource(v5);
  }
  v6 = *(_QWORD *)(a1 + 10728);
  if ( v6 )
  {
    AccelDestroyOffloadWorkspace(v6, a2, a3, a4);
    *(_QWORD *)(a1 + 10728) = 0;
  }
  v7 = *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 10712);
  if ( v7 )
  {
    ExDeleteNPagedLookasideList(v7);
    ExFreePoolWithTag(*(PVOID *)(a1 + 10712), 0x68455646u);
    *(_QWORD *)(a1 + 10712) = 0;
  }
  v8 = *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 10720);
  if ( v8 )
  {
    ExDeleteNPagedLookasideList(v8);
    ExFreePoolWithTag(*(PVOID *)(a1 + 10720), 0x68455646u);
    *(_QWORD *)(a1 + 10720) = 0;
  }
  return ExDeleteResourceLite((PERESOURCE)(a1 + 10600));
}

```

## disassembly

```asm
0x1400ced7c  push    rbx
0x1400ced7e  sub     rsp, 20h
0x1400ced82  test    dword ptr [rcx+26C8h], 800000h
0x1400ced8c  mov     rbx, rcx
0x1400ced8f  jnz     short loc_1400CEDA9
0x1400ced91  mov     rcx, [rcx+29F0h]
0x1400ced98  test    rcx, rcx
0x1400ced9b  jz      short loc_1400CEDA9
0x1400ced9d  call    cs:__imp_AccelCloseResource
0x1400ceda4  nop     dword ptr [rax+rax+00h]
0x1400ceda9  mov     rcx, [rbx+29E8h]
0x1400cedb0  test    rcx, rcx
0x1400cedb3  jz      short loc_1400CEDCC
0x1400cedb5  call    cs:__imp_AccelDestroyOffloadWorkspace
0x1400cedbc  nop     dword ptr [rax+rax+00h]
0x1400cedc1  mov     qword ptr [rbx+29E8h], 0
0x1400cedcc  mov     rcx, [rbx+29D8h]; Lookaside
0x1400cedd3  test    rcx, rcx
0x1400cedd6  jz      short loc_1400CEE07
0x1400cedd8  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400ceddf  nop     dword ptr [rax+rax+00h]
0x1400cede4  mov     rcx, [rbx+29D8h]; P
0x1400cedeb  mov     edx, 68455646h; Tag
0x1400cedf0  call    cs:__imp_ExFreePoolWithTag
0x1400cedf7  nop     dword ptr [rax+rax+00h]
0x1400cedfc  mov     qword ptr [rbx+29D8h], 0
0x1400cee07  mov     rcx, [rbx+29E0h]; Lookaside
0x1400cee0e  test    rcx, rcx
0x1400cee11  jz      short loc_1400CEE42
0x1400cee13  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400cee1a  nop     dword ptr [rax+rax+00h]
0x1400cee1f  mov     rcx, [rbx+29E0h]; P
0x1400cee26  mov     edx, 68455646h; Tag
0x1400cee2b  call    cs:__imp_ExFreePoolWithTag
0x1400cee32  nop     dword ptr [rax+rax+00h]
0x1400cee37  mov     qword ptr [rbx+29E0h], 0
0x1400cee42  lea     rcx, [rbx+2968h]; Resource
0x1400cee49  call    cs:__imp_ExDeleteResourceLite
0x1400cee50  nop     dword ptr [rax+rax+00h]
0x1400cee55  add     rsp, 20h
0x1400cee59  pop     rbx
0x1400cee5a  retn
```
