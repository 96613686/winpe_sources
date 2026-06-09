# FreeRSNMessageKeyData(NWF_RSN_KEY_DATA *)

- ea: `0x140048dc8`
- end: `0x1400491b6`
- name: `?FreeRSNMessageKeyData@@YAXPEAUNWF_RSN_KEY_DATA@@@Z`
- size: `1006`
- prototype: `void __fastcall(struct NWF_RSN_KEY_DATA *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140044320`
- `0x1400447e0`
- `0x1400455c8`
- `0x140050fb8`
- `0x14005291c`

## callees

- `0x140036918`
- `0x140048dc8`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048dfb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048e37`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048e73`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048eaf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048eeb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048f27`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048f63`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048fa2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048fe4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140049026`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140049068`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400490b7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400490f9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004913b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004917d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048dfb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048e37`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048e73`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048eaf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048eeb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048f27`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048f63`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048fa2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048fe4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140049026`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140049068`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400490b7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400490f9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004913b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004917d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048e0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048e48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048e84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048ec0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048efc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048f38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048f74`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048fb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048ff5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049037`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049079`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400490c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004910a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004914c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004918e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048e0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048e48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048e84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048ec0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048efc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048f38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048f74`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048fb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048ff5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049037`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049079`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400490c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004910a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004914c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004918e`

## pseudocode

```c
void __fastcall FreeRSNMessageKeyData(struct NWF_RSN_KEY_DATA *a1)
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
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx

  if ( a1 )
  {
    v2 = *((_QWORD *)a1 + 3);
    if ( v2 )
    {
      v3 = v2 - 16;
      if ( *(_QWORD *)v3 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v3, (PVOID)v3);
      else
        ExFreePoolWithTag((PVOID)v3, *(_DWORD *)(v3 + 8));
      *((_QWORD *)a1 + 3) = 0;
    }
    v4 = *((_QWORD *)a1 + 1);
    if ( v4 )
    {
      v5 = v4 - 16;
      if ( *(_QWORD *)v5 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v5, (PVOID)v5);
      else
        ExFreePoolWithTag((PVOID)v5, *(_DWORD *)(v5 + 8));
      *((_QWORD *)a1 + 1) = 0;
    }
    v6 = *((_QWORD *)a1 + 5);
    if ( v6 )
    {
      v7 = v6 - 16;
      if ( *(_QWORD *)v7 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v7, (PVOID)v7);
      else
        ExFreePoolWithTag((PVOID)v7, *(_DWORD *)(v7 + 8));
      *((_QWORD *)a1 + 5) = 0;
    }
    v8 = *((_QWORD *)a1 + 7);
    if ( v8 )
    {
      v9 = v8 - 16;
      if ( *(_QWORD *)v9 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v9, (PVOID)v9);
      else
        ExFreePoolWithTag((PVOID)v9, *(_DWORD *)(v9 + 8));
      *((_QWORD *)a1 + 7) = 0;
    }
    v10 = *((_QWORD *)a1 + 9);
    if ( v10 )
    {
      v11 = v10 - 16;
      if ( *(_QWORD *)v11 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v11, (PVOID)v11);
      else
        ExFreePoolWithTag((PVOID)v11, *(_DWORD *)(v11 + 8));
      *((_QWORD *)a1 + 9) = 0;
    }
    v12 = *((_QWORD *)a1 + 11);
    if ( v12 )
    {
      v13 = v12 - 16;
      if ( *(_QWORD *)v13 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v13, (PVOID)v13);
      else
        ExFreePoolWithTag((PVOID)v13, *(_DWORD *)(v13 + 8));
      *((_QWORD *)a1 + 11) = 0;
    }
    v14 = *((_QWORD *)a1 + 13);
    if ( v14 )
    {
      v15 = v14 - 16;
      if ( *(_QWORD *)v15 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v15, (PVOID)v15);
      else
        ExFreePoolWithTag((PVOID)v15, *(_DWORD *)(v15 + 8));
      *((_QWORD *)a1 + 13) = 0;
    }
    v16 = *((_QWORD *)a1 + 18);
    if ( v16 )
    {
      v17 = v16 - 16;
      if ( *(_QWORD *)v17 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v17, (PVOID)v17);
      else
        ExFreePoolWithTag((PVOID)v17, *(_DWORD *)(v17 + 8));
      *((_QWORD *)a1 + 18) = 0;
    }
    v18 = *((_QWORD *)a1 + 20);
    if ( v18 )
    {
      v19 = v18 - 16;
      if ( *(_QWORD *)v19 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v19, (PVOID)v19);
      else
        ExFreePoolWithTag((PVOID)v19, *(_DWORD *)(v19 + 8));
      *((_QWORD *)a1 + 20) = 0;
    }
    v20 = *((_QWORD *)a1 + 22);
    if ( v20 )
    {
      v21 = v20 - 16;
      if ( *(_QWORD *)v21 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v21, (PVOID)v21);
      else
        ExFreePoolWithTag((PVOID)v21, *(_DWORD *)(v21 + 8));
      *((_QWORD *)a1 + 22) = 0;
    }
    v22 = *((_QWORD *)a1 + 24);
    if ( v22 )
    {
      v23 = v22 - 16;
      if ( *(_QWORD *)v23 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v23, (PVOID)v23);
      else
        ExFreePoolWithTag((PVOID)v23, *(_DWORD *)(v23 + 8));
      *((_QWORD *)a1 + 24) = 0;
    }
    if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline() )
    {
      v24 = *((_QWORD *)a1 + 26);
      if ( v24 )
      {
        v25 = v24 - 16;
        if ( *(_QWORD *)v25 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v25, (PVOID)v25);
        else
          ExFreePoolWithTag((PVOID)v25, *(_DWORD *)(v25 + 8));
        *((_QWORD *)a1 + 26) = 0;
      }
      v26 = *((_QWORD *)a1 + 28);
      if ( v26 )
      {
        v27 = v26 - 16;
        if ( *(_QWORD *)v27 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v27, (PVOID)v27);
        else
          ExFreePoolWithTag((PVOID)v27, *(_DWORD *)(v27 + 8));
        *((_QWORD *)a1 + 28) = 0;
      }
      v28 = *((_QWORD *)a1 + 30);
      if ( v28 )
      {
        v29 = v28 - 16;
        if ( *(_QWORD *)v29 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v29, (PVOID)v29);
        else
          ExFreePoolWithTag((PVOID)v29, *(_DWORD *)(v29 + 8));
        *((_QWORD *)a1 + 30) = 0;
      }
      v30 = *((_QWORD *)a1 + 32);
      if ( v30 )
      {
        v31 = v30 - 16;
        if ( *(_QWORD *)v31 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v31, (PVOID)v31);
        else
          ExFreePoolWithTag((PVOID)v31, *(_DWORD *)(v31 + 8));
      }
    }
    memset(a1, 0, 0x108u);
  }
}

```

## disassembly

```asm
0x140048dc8  test    rcx, rcx
0x140048dcb  jz      locret_1400491B4
0x140048dd1  mov     [rsp+arg_0], rbx
0x140048dd6  push    rdi
0x140048dd7  sub     rsp, 20h
0x140048ddb  mov     rbx, rcx
0x140048dde  xor     edi, edi
0x140048de0  mov     rcx, [rcx+18h]
0x140048de4  test    rcx, rcx
0x140048de7  jz      short loc_140048E1C
0x140048de9  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140048ded  mov     rax, [rcx]
0x140048df0  test    rax, rax
0x140048df3  jz      short loc_140048E09
0x140048df5  mov     rdx, rcx; Entry
0x140048df8  mov     rcx, rax; Lookaside
0x140048dfb  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048e02  nop     dword ptr [rax+rax+00h]
0x140048e07  jmp     short loc_140048E18
0x140048e09  mov     edx, [rcx+8]; Tag
0x140048e0c  call    cs:__imp_ExFreePoolWithTag
0x140048e13  nop     dword ptr [rax+rax+00h]
0x140048e18  mov     [rbx+18h], rdi
0x140048e1c  mov     rcx, [rbx+8]
0x140048e20  test    rcx, rcx
0x140048e23  jz      short loc_140048E58
0x140048e25  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140048e29  mov     rax, [rcx]
0x140048e2c  test    rax, rax
0x140048e2f  jz      short loc_140048E45
0x140048e31  mov     rdx, rcx; Entry
0x140048e34  mov     rcx, rax; Lookaside
0x140048e37  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048e3e  nop     dword ptr [rax+rax+00h]
0x140048e43  jmp     short loc_140048E54
0x140048e45  mov     edx, [rcx+8]; Tag
0x140048e48  call    cs:__imp_ExFreePoolWithTag
0x140048e4f  nop     dword ptr [rax+rax+00h]
0x140048e54  mov     [rbx+8], rdi
0x140048e58  mov     rcx, [rbx+28h]
0x140048e5c  test    rcx, rcx
0x140048e5f  jz      short loc_140048E94
0x140048e61  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140048e65  mov     rax, [rcx]
0x140048e68  test    rax, rax
0x140048e6b  jz      short loc_140048E81
0x140048e6d  mov     rdx, rcx; Entry
0x140048e70  mov     rcx, rax; Lookaside
0x140048e73  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048e7a  nop     dword ptr [rax+rax+00h]
0x140048e7f  jmp     short loc_140048E90
0x140048e81  mov     edx, [rcx+8]; Tag
0x140048e84  call    cs:__imp_ExFreePoolWithTag
0x140048e8b  nop     dword ptr [rax+rax+00h]
0x140048e90  mov     [rbx+28h], rdi
0x140048e94  mov     rcx, [rbx+38h]
0x140048e98  test    rcx, rcx
0x140048e9b  jz      short loc_140048ED0
0x140048e9d  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140048ea1  mov     rax, [rcx]
0x140048ea4  test    rax, rax
0x140048ea7  jz      short loc_140048EBD
0x140048ea9  mov     rdx, rcx; Entry
0x140048eac  mov     rcx, rax; Lookaside
0x140048eaf  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048eb6  nop     dword ptr [rax+rax+00h]
0x140048ebb  jmp     short loc_140048ECC
0x140048ebd  mov     edx, [rcx+8]; Tag
0x140048ec0  call    cs:__imp_ExFreePoolWithTag
0x140048ec7  nop     dword ptr [rax+rax+00h]
0x140048ecc  mov     [rbx+38h], rdi
0x140048ed0  mov     rcx, [rbx+48h]
0x140048ed4  test    rcx, rcx
0x140048ed7  jz      short loc_140048F0C
0x140048ed9  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140048edd  mov     rax, [rcx]
0x140048ee0  test    rax, rax
0x140048ee3  jz      short loc_140048EF9
0x140048ee5  mov     rdx, rcx; Entry
0x140048ee8  mov     rcx, rax; Lookaside
0x140048eeb  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048ef2  nop     dword ptr [rax+rax+00h]
0x140048ef7  jmp     short loc_140048F08
0x140048ef9  mov     edx, [rcx+8]; Tag
0x140048efc  call    cs:__imp_ExFreePoolWithTag
0x140048f03  nop     dword ptr [rax+rax+00h]
0x140048f08  mov     [rbx+48h], rdi
0x140048f0c  mov     rcx, [rbx+58h]
0x140048f10  test    rcx, rcx
0x140048f13  jz      short loc_140048F48
0x140048f15  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140048f19  mov     rax, [rcx]
0x140048f1c  test    rax, rax
0x140048f1f  jz      short loc_140048F35
0x140048f21  mov     rdx, rcx; Entry
0x140048f24  mov     rcx, rax; Lookaside
0x140048f27  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048f2e  nop     dword ptr [rax+rax+00h]
0x140048f33  jmp     short loc_140048F44
0x140048f35  mov     edx, [rcx+8]; Tag
0x140048f38  call    cs:__imp_ExFreePoolWithTag
0x140048f3f  nop     dword ptr [rax+rax+00h]
0x140048f44  mov     [rbx+58h], rdi
0x140048f48  mov     rcx, [rbx+68h]
0x140048f4c  test    rcx, rcx
0x140048f4f  jz      short loc_140048F84
0x140048f51  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140048f55  mov     rax, [rcx]
0x140048f58  test    rax, rax
0x140048f5b  jz      short loc_140048F71
0x140048f5d  mov     rdx, rcx; Entry
0x140048f60  mov     rcx, rax; Lookaside
0x140048f63  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048f6a  nop     dword ptr [rax+rax+00h]
0x140048f6f  jmp     short loc_140048F80
0x140048f71  mov     edx, [rcx+8]; Tag
0x140048f74  call    cs:__imp_ExFreePoolWithTag
0x140048f7b  nop     dword ptr [rax+rax+00h]
0x140048f80  mov     [rbx+68h], rdi
0x140048f84  mov     rcx, [rbx+90h]
0x140048f8b  test    rcx, rcx
0x140048f8e  jz      short loc_140048FC6
0x140048f90  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140048f94  mov     rax, [rcx]
0x140048f97  test    rax, rax
0x140048f9a  jz      short loc_140048FB0
0x140048f9c  mov     rdx, rcx; Entry
0x140048f9f  mov     rcx, rax; Lookaside
0x140048fa2  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048fa9  nop     dword ptr [rax+rax+00h]
0x140048fae  jmp     short loc_140048FBF
0x140048fb0  mov     edx, [rcx+8]; Tag
0x140048fb3  call    cs:__imp_ExFreePoolWithTag
0x140048fba  nop     dword ptr [rax+rax+00h]
0x140048fbf  mov     [rbx+90h], rdi
0x140048fc6  mov     rcx, [rbx+0A0h]
0x140048fcd  test    rcx, rcx
0x140048fd0  jz      short loc_140049008
0x140048fd2  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140048fd6  mov     rax, [rcx]
0x140048fd9  test    rax, rax
0x140048fdc  jz      short loc_140048FF2
0x140048fde  mov     rdx, rcx; Entry
0x140048fe1  mov     rcx, rax; Lookaside
0x140048fe4  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048feb  nop     dword ptr [rax+rax+00h]
0x140048ff0  jmp     short loc_140049001
0x140048ff2  mov     edx, [rcx+8]; Tag
0x140048ff5  call    cs:__imp_ExFreePoolWithTag
0x140048ffc  nop     dword ptr [rax+rax+00h]
0x140049001  mov     [rbx+0A0h], rdi
0x140049008  mov     rcx, [rbx+0B0h]
0x14004900f  test    rcx, rcx
0x140049012  jz      short loc_14004904A
0x140049014  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140049018  mov     rax, [rcx]
0x14004901b  test    rax, rax
0x14004901e  jz      short loc_140049034
0x140049020  mov     rdx, rcx; Entry
0x140049023  mov     rcx, rax; Lookaside
0x140049026  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004902d  nop     dword ptr [rax+rax+00h]
0x140049032  jmp     short loc_140049043
0x140049034  mov     edx, [rcx+8]; Tag
0x140049037  call    cs:__imp_ExFreePoolWithTag
0x14004903e  nop     dword ptr [rax+rax+00h]
0x140049043  mov     [rbx+0B0h], rdi
0x14004904a  mov     rcx, [rbx+0C0h]
0x140049051  test    rcx, rcx
0x140049054  jz      short loc_14004908C
0x140049056  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004905a  mov     rax, [rcx]
0x14004905d  test    rax, rax
0x140049060  jz      short loc_140049076
0x140049062  mov     rdx, rcx; Entry
0x140049065  mov     rcx, rax; Lookaside
0x140049068  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004906f  nop     dword ptr [rax+rax+00h]
0x140049074  jmp     short loc_140049085
0x140049076  mov     edx, [rcx+8]; Tag
0x140049079  call    cs:__imp_ExFreePoolWithTag
0x140049080  nop     dword ptr [rax+rax+00h]
0x140049085  mov     [rbx+0C0h], rdi
0x14004908c  call    Feature_53299205__private_IsEnabledDeviceUsageNoInline
0x140049091  test    eax, eax
0x140049093  jz      loc_14004919A
0x140049099  mov     rcx, [rbx+0D0h]
0x1400490a0  test    rcx, rcx
0x1400490a3  jz      short loc_1400490DB
0x1400490a5  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400490a9  mov     rax, [rcx]
0x1400490ac  test    rax, rax
0x1400490af  jz      short loc_1400490C5
0x1400490b1  mov     rdx, rcx; Entry
0x1400490b4  mov     rcx, rax; Lookaside
0x1400490b7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400490be  nop     dword ptr [rax+rax+00h]
0x1400490c3  jmp     short loc_1400490D4
0x1400490c5  mov     edx, [rcx+8]; Tag
0x1400490c8  call    cs:__imp_ExFreePoolWithTag
0x1400490cf  nop     dword ptr [rax+rax+00h]
0x1400490d4  mov     [rbx+0D0h], rdi
0x1400490db  mov     rcx, [rbx+0E0h]
0x1400490e2  test    rcx, rcx
0x1400490e5  jz      short loc_14004911D
0x1400490e7  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400490eb  mov     rax, [rcx]
0x1400490ee  test    rax, rax
0x1400490f1  jz      short loc_140049107
0x1400490f3  mov     rdx, rcx; Entry
0x1400490f6  mov     rcx, rax; Lookaside
0x1400490f9  call    cs:__imp_ExFreeToNPagedLookasideList
0x140049100  nop     dword ptr [rax+rax+00h]
0x140049105  jmp     short loc_140049116
0x140049107  mov     edx, [rcx+8]; Tag
0x14004910a  call    cs:__imp_ExFreePoolWithTag
0x140049111  nop     dword ptr [rax+rax+00h]
0x140049116  mov     [rbx+0E0h], rdi
0x14004911d  mov     rcx, [rbx+0F0h]
0x140049124  test    rcx, rcx
0x140049127  jz      short loc_14004915F
0x140049129  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004912d  mov     rax, [rcx]
0x140049130  test    rax, rax
0x140049133  jz      short loc_140049149
0x140049135  mov     rdx, rcx; Entry
0x140049138  mov     rcx, rax; Lookaside
0x14004913b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140049142  nop     dword ptr [rax+rax+00h]
0x140049147  jmp     short loc_140049158
0x140049149  mov     edx, [rcx+8]; Tag
0x14004914c  call    cs:__imp_ExFreePoolWithTag
0x140049153  nop     dword ptr [rax+rax+00h]
0x140049158  mov     [rbx+0F0h], rdi
0x14004915f  mov     rcx, [rbx+100h]
0x140049166  test    rcx, rcx
0x140049169  jz      short loc_14004919A
0x14004916b  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004916f  mov     rax, [rcx]
0x140049172  test    rax, rax
0x140049175  jz      short loc_14004918B
0x140049177  mov     rdx, rcx; Entry
0x14004917a  mov     rcx, rax; Lookaside
0x14004917d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140049184  nop     dword ptr [rax+rax+00h]
0x140049189  jmp     short loc_14004919A
0x14004918b  mov     edx, [rcx+8]; Tag
0x14004918e  call    cs:__imp_ExFreePoolWithTag
0x140049195  nop     dword ptr [rax+rax+00h]
0x14004919a  xor     edx, edx; Val
0x14004919c  mov     r8d, 108h; Size
0x1400491a2  mov     rcx, rbx; void *
0x1400491a5  call    memset
0x1400491aa  mov     rbx, [rsp+28h+arg_0]
0x1400491af  add     rsp, 20h
0x1400491b3  pop     rdi
0x1400491b4  retn
```
