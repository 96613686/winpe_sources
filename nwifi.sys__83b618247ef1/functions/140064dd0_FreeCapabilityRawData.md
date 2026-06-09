# FreeCapabilityRawData

- ea: `0x140064dd0`
- end: `0x140064fba`
- name: `FreeCapabilityRawData`
- size: `490`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140021620`
- `0x140065310`

## callees

- `0x140064dd0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064df4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064e33`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064e72`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064eb2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064ef9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064f40`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064f87`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064df4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064e33`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064e72`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064eb2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064ef9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064f40`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064f87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064e05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064e44`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064e83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064ec3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064e05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064e44`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064e83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064ec3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f98`

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
0x140064dd0  push    rbx
0x140064dd2  sub     rsp, 20h
0x140064dd6  mov     rbx, rcx
0x140064dd9  mov     rcx, [rcx+8]
0x140064ddd  test    rcx, rcx
0x140064de0  jz      short loc_140064E19
0x140064de2  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140064de6  mov     rax, [rcx]
0x140064de9  test    rax, rax
0x140064dec  jz      short loc_140064E02
0x140064dee  mov     rdx, rcx; Entry
0x140064df1  mov     rcx, rax; Lookaside
0x140064df4  call    cs:__imp_ExFreeToNPagedLookasideList
0x140064dfb  nop     dword ptr [rax+rax+00h]
0x140064e00  jmp     short loc_140064E11
0x140064e02  mov     edx, [rcx+8]; Tag
0x140064e05  call    cs:__imp_ExFreePoolWithTag
0x140064e0c  nop     dword ptr [rax+rax+00h]
0x140064e11  mov     qword ptr [rbx+8], 0
0x140064e19  mov     rcx, [rbx]
0x140064e1c  test    rcx, rcx
0x140064e1f  jz      short loc_140064E57
0x140064e21  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140064e25  mov     rax, [rcx]
0x140064e28  test    rax, rax
0x140064e2b  jz      short loc_140064E41
0x140064e2d  mov     rdx, rcx; Entry
0x140064e30  mov     rcx, rax; Lookaside
0x140064e33  call    cs:__imp_ExFreeToNPagedLookasideList
0x140064e3a  nop     dword ptr [rax+rax+00h]
0x140064e3f  jmp     short loc_140064E50
0x140064e41  mov     edx, [rcx+8]; Tag
0x140064e44  call    cs:__imp_ExFreePoolWithTag
0x140064e4b  nop     dword ptr [rax+rax+00h]
0x140064e50  mov     qword ptr [rbx], 0
0x140064e57  mov     rcx, [rbx+10h]
0x140064e5b  test    rcx, rcx
0x140064e5e  jz      short loc_140064E97
0x140064e60  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140064e64  mov     rax, [rcx]
0x140064e67  test    rax, rax
0x140064e6a  jz      short loc_140064E80
0x140064e6c  mov     rdx, rcx; Entry
0x140064e6f  mov     rcx, rax; Lookaside
0x140064e72  call    cs:__imp_ExFreeToNPagedLookasideList
0x140064e79  nop     dword ptr [rax+rax+00h]
0x140064e7e  jmp     short loc_140064E8F
0x140064e80  mov     edx, [rcx+8]; Tag
0x140064e83  call    cs:__imp_ExFreePoolWithTag
0x140064e8a  nop     dword ptr [rax+rax+00h]
0x140064e8f  mov     qword ptr [rbx+10h], 0
0x140064e97  mov     rcx, [rbx+20h]
0x140064e9b  test    rcx, rcx
0x140064e9e  jz      short loc_140064EDE
0x140064ea0  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140064ea4  mov     rax, [rcx]
0x140064ea7  test    rax, rax
0x140064eaa  jz      short loc_140064EC0
0x140064eac  mov     rdx, rcx; Entry
0x140064eaf  mov     rcx, rax; Lookaside
0x140064eb2  call    cs:__imp_ExFreeToNPagedLookasideList
0x140064eb9  nop     dword ptr [rax+rax+00h]
0x140064ebe  jmp     short loc_140064ECF
0x140064ec0  mov     edx, [rcx+8]; Tag
0x140064ec3  call    cs:__imp_ExFreePoolWithTag
0x140064eca  nop     dword ptr [rax+rax+00h]
0x140064ecf  mov     qword ptr [rbx+20h], 0
0x140064ed7  mov     dword ptr [rbx+18h], 0
0x140064ede  mov     rcx, [rbx+40h]
0x140064ee2  test    rcx, rcx
0x140064ee5  jz      short loc_140064F25
0x140064ee7  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140064eeb  mov     rax, [rcx]
0x140064eee  test    rax, rax
0x140064ef1  jz      short loc_140064F07
0x140064ef3  mov     rdx, rcx; Entry
0x140064ef6  mov     rcx, rax; Lookaside
0x140064ef9  call    cs:__imp_ExFreeToNPagedLookasideList
0x140064f00  nop     dword ptr [rax+rax+00h]
0x140064f05  jmp     short loc_140064F16
0x140064f07  mov     edx, [rcx+8]; Tag
0x140064f0a  call    cs:__imp_ExFreePoolWithTag
0x140064f11  nop     dword ptr [rax+rax+00h]
0x140064f16  mov     qword ptr [rbx+40h], 0
0x140064f1e  mov     dword ptr [rbx+38h], 0
0x140064f25  mov     rcx, [rbx+30h]
0x140064f29  test    rcx, rcx
0x140064f2c  jz      short loc_140064F6C
0x140064f2e  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140064f32  mov     rax, [rcx]
0x140064f35  test    rax, rax
0x140064f38  jz      short loc_140064F4E
0x140064f3a  mov     rdx, rcx; Entry
0x140064f3d  mov     rcx, rax; Lookaside
0x140064f40  call    cs:__imp_ExFreeToNPagedLookasideList
0x140064f47  nop     dword ptr [rax+rax+00h]
0x140064f4c  jmp     short loc_140064F5D
0x140064f4e  mov     edx, [rcx+8]; Tag
0x140064f51  call    cs:__imp_ExFreePoolWithTag
0x140064f58  nop     dword ptr [rax+rax+00h]
0x140064f5d  mov     qword ptr [rbx+30h], 0
0x140064f65  mov     dword ptr [rbx+28h], 0
0x140064f6c  mov     rcx, [rbx+50h]
0x140064f70  test    rcx, rcx
0x140064f73  jz      short loc_140064FB3
0x140064f75  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140064f79  mov     rax, [rcx]
0x140064f7c  test    rax, rax
0x140064f7f  jz      short loc_140064F95
0x140064f81  mov     rdx, rcx; Entry
0x140064f84  mov     rcx, rax; Lookaside
0x140064f87  call    cs:__imp_ExFreeToNPagedLookasideList
0x140064f8e  nop     dword ptr [rax+rax+00h]
0x140064f93  jmp     short loc_140064FA4
0x140064f95  mov     edx, [rcx+8]; Tag
0x140064f98  call    cs:__imp_ExFreePoolWithTag
0x140064f9f  nop     dword ptr [rax+rax+00h]
0x140064fa4  mov     qword ptr [rbx+50h], 0
0x140064fac  mov     dword ptr [rbx+48h], 0
0x140064fb3  add     rsp, 20h
0x140064fb7  pop     rbx
0x140064fb8  retn
```
