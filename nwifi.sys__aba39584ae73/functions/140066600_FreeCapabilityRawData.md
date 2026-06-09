# FreeCapabilityRawData

- ea: `0x140066600`
- end: `0x1400667ea`
- name: `FreeCapabilityRawData`
- size: `490`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140021620`
- `0x140066b40`

## callees

- `0x140066600`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140066624`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140066663`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400666a2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400666e2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140066729`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140066770`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400667b7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140066624`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140066663`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400666a2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400666e2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140066729`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140066770`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400667b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066635`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066674`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400666b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400666f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006673a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066781`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400667c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066635`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066674`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400666b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400666f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006673a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066781`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400667c8`

## pseudocode

```c
void __fastcall FreeCapabilityRawData(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
  {
    v3 = v2 - 16;
    if ( *(_QWORD *)v3 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v3, (PVOID)v3);
    else
      ExFreePoolWithTag((PVOID)v3, *(_DWORD *)(v3 + 8));
    *(_QWORD *)(a1 + 8) = 0;
  }
  if ( *(_QWORD *)a1 )
  {
    v4 = *(_QWORD *)a1 - 16LL;
    if ( *(_QWORD *)v4 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v4, (PVOID)(*(_QWORD *)a1 - 16LL));
    else
      ExFreePoolWithTag((PVOID)v4, *(_DWORD *)(v4 + 8));
    *(_QWORD *)a1 = 0;
  }
  v5 = *(_QWORD *)(a1 + 16);
  if ( v5 )
  {
    v6 = v5 - 16;
    if ( *(_QWORD *)v6 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v6, (PVOID)v6);
    else
      ExFreePoolWithTag((PVOID)v6, *(_DWORD *)(v6 + 8));
    *(_QWORD *)(a1 + 16) = 0;
  }
  v7 = *(_QWORD *)(a1 + 32);
  if ( v7 )
  {
    v8 = v7 - 16;
    if ( *(_QWORD *)v8 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v8, (PVOID)v8);
    else
      ExFreePoolWithTag((PVOID)v8, *(_DWORD *)(v8 + 8));
    *(_QWORD *)(a1 + 32) = 0;
    *(_DWORD *)(a1 + 24) = 0;
  }
  v9 = *(_QWORD *)(a1 + 64);
  if ( v9 )
  {
    v10 = v9 - 16;
    if ( *(_QWORD *)v10 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v10, (PVOID)v10);
    else
      ExFreePoolWithTag((PVOID)v10, *(_DWORD *)(v10 + 8));
    *(_QWORD *)(a1 + 64) = 0;
    *(_DWORD *)(a1 + 56) = 0;
  }
  v11 = *(_QWORD *)(a1 + 48);
  if ( v11 )
  {
    v12 = v11 - 16;
    if ( *(_QWORD *)v12 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v12, (PVOID)v12);
    else
      ExFreePoolWithTag((PVOID)v12, *(_DWORD *)(v12 + 8));
    *(_QWORD *)(a1 + 48) = 0;
    *(_DWORD *)(a1 + 40) = 0;
  }
  v13 = *(_QWORD *)(a1 + 80);
  if ( v13 )
  {
    v14 = v13 - 16;
    if ( *(_QWORD *)v14 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v14, (PVOID)v14);
    else
      ExFreePoolWithTag((PVOID)v14, *(_DWORD *)(v14 + 8));
    *(_QWORD *)(a1 + 80) = 0;
    *(_DWORD *)(a1 + 72) = 0;
  }
}

```

## disassembly

```asm
0x140066600  push    rbx
0x140066602  sub     rsp, 20h
0x140066606  mov     rbx, rcx
0x140066609  mov     rcx, [rcx+8]
0x14006660d  test    rcx, rcx
0x140066610  jz      short loc_140066649
0x140066612  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140066616  mov     rax, [rcx]
0x140066619  test    rax, rax
0x14006661c  jz      short loc_140066632
0x14006661e  mov     rdx, rcx; Entry
0x140066621  mov     rcx, rax; Lookaside
0x140066624  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006662b  nop     dword ptr [rax+rax+00h]
0x140066630  jmp     short loc_140066641
0x140066632  mov     edx, [rcx+8]; Tag
0x140066635  call    cs:__imp_ExFreePoolWithTag
0x14006663c  nop     dword ptr [rax+rax+00h]
0x140066641  mov     qword ptr [rbx+8], 0
0x140066649  mov     rcx, [rbx]
0x14006664c  test    rcx, rcx
0x14006664f  jz      short loc_140066687
0x140066651  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140066655  mov     rax, [rcx]
0x140066658  test    rax, rax
0x14006665b  jz      short loc_140066671
0x14006665d  mov     rdx, rcx; Entry
0x140066660  mov     rcx, rax; Lookaside
0x140066663  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006666a  nop     dword ptr [rax+rax+00h]
0x14006666f  jmp     short loc_140066680
0x140066671  mov     edx, [rcx+8]; Tag
0x140066674  call    cs:__imp_ExFreePoolWithTag
0x14006667b  nop     dword ptr [rax+rax+00h]
0x140066680  mov     qword ptr [rbx], 0
0x140066687  mov     rcx, [rbx+10h]
0x14006668b  test    rcx, rcx
0x14006668e  jz      short loc_1400666C7
0x140066690  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140066694  mov     rax, [rcx]
0x140066697  test    rax, rax
0x14006669a  jz      short loc_1400666B0
0x14006669c  mov     rdx, rcx; Entry
0x14006669f  mov     rcx, rax; Lookaside
0x1400666a2  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400666a9  nop     dword ptr [rax+rax+00h]
0x1400666ae  jmp     short loc_1400666BF
0x1400666b0  mov     edx, [rcx+8]; Tag
0x1400666b3  call    cs:__imp_ExFreePoolWithTag
0x1400666ba  nop     dword ptr [rax+rax+00h]
0x1400666bf  mov     qword ptr [rbx+10h], 0
0x1400666c7  mov     rcx, [rbx+20h]
0x1400666cb  test    rcx, rcx
0x1400666ce  jz      short loc_14006670E
0x1400666d0  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400666d4  mov     rax, [rcx]
0x1400666d7  test    rax, rax
0x1400666da  jz      short loc_1400666F0
0x1400666dc  mov     rdx, rcx; Entry
0x1400666df  mov     rcx, rax; Lookaside
0x1400666e2  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400666e9  nop     dword ptr [rax+rax+00h]
0x1400666ee  jmp     short loc_1400666FF
0x1400666f0  mov     edx, [rcx+8]; Tag
0x1400666f3  call    cs:__imp_ExFreePoolWithTag
0x1400666fa  nop     dword ptr [rax+rax+00h]
0x1400666ff  mov     qword ptr [rbx+20h], 0
0x140066707  mov     dword ptr [rbx+18h], 0
0x14006670e  mov     rcx, [rbx+40h]
0x140066712  test    rcx, rcx
0x140066715  jz      short loc_140066755
0x140066717  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14006671b  mov     rax, [rcx]
0x14006671e  test    rax, rax
0x140066721  jz      short loc_140066737
0x140066723  mov     rdx, rcx; Entry
0x140066726  mov     rcx, rax; Lookaside
0x140066729  call    cs:__imp_ExFreeToNPagedLookasideList
0x140066730  nop     dword ptr [rax+rax+00h]
0x140066735  jmp     short loc_140066746
0x140066737  mov     edx, [rcx+8]; Tag
0x14006673a  call    cs:__imp_ExFreePoolWithTag
0x140066741  nop     dword ptr [rax+rax+00h]
0x140066746  mov     qword ptr [rbx+40h], 0
0x14006674e  mov     dword ptr [rbx+38h], 0
0x140066755  mov     rcx, [rbx+30h]
0x140066759  test    rcx, rcx
0x14006675c  jz      short loc_14006679C
0x14006675e  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140066762  mov     rax, [rcx]
0x140066765  test    rax, rax
0x140066768  jz      short loc_14006677E
0x14006676a  mov     rdx, rcx; Entry
0x14006676d  mov     rcx, rax; Lookaside
0x140066770  call    cs:__imp_ExFreeToNPagedLookasideList
0x140066777  nop     dword ptr [rax+rax+00h]
0x14006677c  jmp     short loc_14006678D
0x14006677e  mov     edx, [rcx+8]; Tag
0x140066781  call    cs:__imp_ExFreePoolWithTag
0x140066788  nop     dword ptr [rax+rax+00h]
0x14006678d  mov     qword ptr [rbx+30h], 0
0x140066795  mov     dword ptr [rbx+28h], 0
0x14006679c  mov     rcx, [rbx+50h]
0x1400667a0  test    rcx, rcx
0x1400667a3  jz      short loc_1400667E3
0x1400667a5  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400667a9  mov     rax, [rcx]
0x1400667ac  test    rax, rax
0x1400667af  jz      short loc_1400667C5
0x1400667b1  mov     rdx, rcx; Entry
0x1400667b4  mov     rcx, rax; Lookaside
0x1400667b7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400667be  nop     dword ptr [rax+rax+00h]
0x1400667c3  jmp     short loc_1400667D4
0x1400667c5  mov     edx, [rcx+8]; Tag
0x1400667c8  call    cs:__imp_ExFreePoolWithTag
0x1400667cf  nop     dword ptr [rax+rax+00h]
0x1400667d4  mov     qword ptr [rbx+50h], 0
0x1400667dc  mov     dword ptr [rbx+48h], 0
0x1400667e3  add     rsp, 20h
0x1400667e7  pop     rbx
0x1400667e8  retn
```
