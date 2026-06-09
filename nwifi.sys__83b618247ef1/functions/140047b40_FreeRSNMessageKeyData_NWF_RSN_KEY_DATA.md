# FreeRSNMessageKeyData(NWF_RSN_KEY_DATA *)

- ea: `0x140047b40`
- end: `0x140047f2e`
- name: `?FreeRSNMessageKeyData@@YAXPEAUNWF_RSN_KEY_DATA@@@Z`
- size: `1006`
- prototype: `void __fastcall(struct NWF_RSN_KEY_DATA *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400437a0`
- `0x140043c60`
- `0x140044a48`
- `0x14004f7f0`
- `0x140051154`

## callees

- `0x1400366f8`
- `0x140047b40`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047b73`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047baf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047beb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047c27`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047c63`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047c9f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047cdb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047d1a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047d5c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047d9e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047de0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047e2f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047e71`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047eb3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047ef5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047b73`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047baf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047beb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047c27`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047c63`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047c9f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047cdb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047d1a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047d5c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047d9e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047de0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047e2f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047e71`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047eb3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047ef5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047b84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047bc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047bfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047c38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047c74`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047cb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047cec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047d2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047d6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047daf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047df1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047e40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047e82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047ec4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047f06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047b84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047bc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047bfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047c38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047c74`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047cb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047cec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047d2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047d6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047daf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047df1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047e40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047e82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047ec4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047f06`

## pseudocode

```c
void __fastcall FreeRSNMessageKeyData(struct NWF_RSN_KEY_DATA *a1, __int64 a2, __int64 a3, __int64 a4)
{
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
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx

  if ( a1 )
  {
    v5 = *((_QWORD *)a1 + 3);
    if ( v5 )
    {
      v6 = v5 - 16;
      if ( *(_QWORD *)v6 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v6, (PVOID)v6);
      else
        ExFreePoolWithTag((PVOID)v6, *(_DWORD *)(v6 + 8));
      *((_QWORD *)a1 + 3) = 0;
    }
    v7 = *((_QWORD *)a1 + 1);
    if ( v7 )
    {
      v8 = v7 - 16;
      if ( *(_QWORD *)v8 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v8, (PVOID)v8);
      else
        ExFreePoolWithTag((PVOID)v8, *(_DWORD *)(v8 + 8));
      *((_QWORD *)a1 + 1) = 0;
    }
    v9 = *((_QWORD *)a1 + 5);
    if ( v9 )
    {
      v10 = v9 - 16;
      if ( *(_QWORD *)v10 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v10, (PVOID)v10);
      else
        ExFreePoolWithTag((PVOID)v10, *(_DWORD *)(v10 + 8));
      *((_QWORD *)a1 + 5) = 0;
    }
    v11 = *((_QWORD *)a1 + 7);
    if ( v11 )
    {
      v12 = v11 - 16;
      if ( *(_QWORD *)v12 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v12, (PVOID)v12);
      else
        ExFreePoolWithTag((PVOID)v12, *(_DWORD *)(v12 + 8));
      *((_QWORD *)a1 + 7) = 0;
    }
    v13 = *((_QWORD *)a1 + 9);
    if ( v13 )
    {
      v14 = v13 - 16;
      if ( *(_QWORD *)v14 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v14, (PVOID)v14);
      else
        ExFreePoolWithTag((PVOID)v14, *(_DWORD *)(v14 + 8));
      *((_QWORD *)a1 + 9) = 0;
    }
    v15 = *((_QWORD *)a1 + 11);
    if ( v15 )
    {
      v16 = v15 - 16;
      if ( *(_QWORD *)v16 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v16, (PVOID)v16);
      else
        ExFreePoolWithTag((PVOID)v16, *(_DWORD *)(v16 + 8));
      *((_QWORD *)a1 + 11) = 0;
    }
    v17 = *((_QWORD *)a1 + 13);
    if ( v17 )
    {
      v18 = v17 - 16;
      if ( *(_QWORD *)v18 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v18, (PVOID)v18);
      else
        ExFreePoolWithTag((PVOID)v18, *(_DWORD *)(v18 + 8));
      *((_QWORD *)a1 + 13) = 0;
    }
    v19 = *((_QWORD *)a1 + 18);
    if ( v19 )
    {
      v20 = v19 - 16;
      if ( *(_QWORD *)v20 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v20, (PVOID)v20);
      else
        ExFreePoolWithTag((PVOID)v20, *(_DWORD *)(v20 + 8));
      *((_QWORD *)a1 + 18) = 0;
    }
    v21 = *((_QWORD *)a1 + 20);
    if ( v21 )
    {
      v22 = v21 - 16;
      if ( *(_QWORD *)v22 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v22, (PVOID)v22);
      else
        ExFreePoolWithTag((PVOID)v22, *(_DWORD *)(v22 + 8));
      *((_QWORD *)a1 + 20) = 0;
    }
    v23 = *((_QWORD *)a1 + 22);
    if ( v23 )
    {
      v24 = v23 - 16;
      if ( *(_QWORD *)v24 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v24, (PVOID)v24);
      else
        ExFreePoolWithTag((PVOID)v24, *(_DWORD *)(v24 + 8));
      *((_QWORD *)a1 + 22) = 0;
    }
    v25 = *((_QWORD *)a1 + 24);
    if ( v25 )
    {
      v26 = v25 - 16;
      if ( *(_QWORD *)v26 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v26, (PVOID)v26);
      else
        ExFreePoolWithTag((PVOID)v26, *(_DWORD *)(v26 + 8));
      *((_QWORD *)a1 + 24) = 0;
    }
    if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline(v25, a2, a3, a4) )
    {
      v27 = *((_QWORD *)a1 + 26);
      if ( v27 )
      {
        v28 = v27 - 16;
        if ( *(_QWORD *)v28 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v28, (PVOID)v28);
        else
          ExFreePoolWithTag((PVOID)v28, *(_DWORD *)(v28 + 8));
        *((_QWORD *)a1 + 26) = 0;
      }
      v29 = *((_QWORD *)a1 + 28);
      if ( v29 )
      {
        v30 = v29 - 16;
        if ( *(_QWORD *)v30 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v30, (PVOID)v30);
        else
          ExFreePoolWithTag((PVOID)v30, *(_DWORD *)(v30 + 8));
        *((_QWORD *)a1 + 28) = 0;
      }
      v31 = *((_QWORD *)a1 + 30);
      if ( v31 )
      {
        v32 = v31 - 16;
        if ( *(_QWORD *)v32 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v32, (PVOID)v32);
        else
          ExFreePoolWithTag((PVOID)v32, *(_DWORD *)(v32 + 8));
        *((_QWORD *)a1 + 30) = 0;
      }
      v33 = *((_QWORD *)a1 + 32);
      if ( v33 )
      {
        v34 = v33 - 16;
        if ( *(_QWORD *)v34 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v34, (PVOID)v34);
        else
          ExFreePoolWithTag((PVOID)v34, *(_DWORD *)(v34 + 8));
      }
    }
    memset(a1, 0, 0x108u);
  }
}

```

## disassembly

```asm
0x140047b40  test    rcx, rcx
0x140047b43  jz      locret_140047F2C
0x140047b49  mov     [rsp+arg_0], rbx
0x140047b4e  push    rdi
0x140047b4f  sub     rsp, 20h
0x140047b53  mov     rbx, rcx
0x140047b56  xor     edi, edi
0x140047b58  mov     rcx, [rcx+18h]
0x140047b5c  test    rcx, rcx
0x140047b5f  jz      short loc_140047B94
0x140047b61  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047b65  mov     rax, [rcx]
0x140047b68  test    rax, rax
0x140047b6b  jz      short loc_140047B81
0x140047b6d  mov     rdx, rcx; Entry
0x140047b70  mov     rcx, rax; Lookaside
0x140047b73  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047b7a  nop     dword ptr [rax+rax+00h]
0x140047b7f  jmp     short loc_140047B90
0x140047b81  mov     edx, [rcx+8]; Tag
0x140047b84  call    cs:__imp_ExFreePoolWithTag
0x140047b8b  nop     dword ptr [rax+rax+00h]
0x140047b90  mov     [rbx+18h], rdi
0x140047b94  mov     rcx, [rbx+8]
0x140047b98  test    rcx, rcx
0x140047b9b  jz      short loc_140047BD0
0x140047b9d  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047ba1  mov     rax, [rcx]
0x140047ba4  test    rax, rax
0x140047ba7  jz      short loc_140047BBD
0x140047ba9  mov     rdx, rcx; Entry
0x140047bac  mov     rcx, rax; Lookaside
0x140047baf  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047bb6  nop     dword ptr [rax+rax+00h]
0x140047bbb  jmp     short loc_140047BCC
0x140047bbd  mov     edx, [rcx+8]; Tag
0x140047bc0  call    cs:__imp_ExFreePoolWithTag
0x140047bc7  nop     dword ptr [rax+rax+00h]
0x140047bcc  mov     [rbx+8], rdi
0x140047bd0  mov     rcx, [rbx+28h]
0x140047bd4  test    rcx, rcx
0x140047bd7  jz      short loc_140047C0C
0x140047bd9  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047bdd  mov     rax, [rcx]
0x140047be0  test    rax, rax
0x140047be3  jz      short loc_140047BF9
0x140047be5  mov     rdx, rcx; Entry
0x140047be8  mov     rcx, rax; Lookaside
0x140047beb  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047bf2  nop     dword ptr [rax+rax+00h]
0x140047bf7  jmp     short loc_140047C08
0x140047bf9  mov     edx, [rcx+8]; Tag
0x140047bfc  call    cs:__imp_ExFreePoolWithTag
0x140047c03  nop     dword ptr [rax+rax+00h]
0x140047c08  mov     [rbx+28h], rdi
0x140047c0c  mov     rcx, [rbx+38h]
0x140047c10  test    rcx, rcx
0x140047c13  jz      short loc_140047C48
0x140047c15  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047c19  mov     rax, [rcx]
0x140047c1c  test    rax, rax
0x140047c1f  jz      short loc_140047C35
0x140047c21  mov     rdx, rcx; Entry
0x140047c24  mov     rcx, rax; Lookaside
0x140047c27  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047c2e  nop     dword ptr [rax+rax+00h]
0x140047c33  jmp     short loc_140047C44
0x140047c35  mov     edx, [rcx+8]; Tag
0x140047c38  call    cs:__imp_ExFreePoolWithTag
0x140047c3f  nop     dword ptr [rax+rax+00h]
0x140047c44  mov     [rbx+38h], rdi
0x140047c48  mov     rcx, [rbx+48h]
0x140047c4c  test    rcx, rcx
0x140047c4f  jz      short loc_140047C84
0x140047c51  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047c55  mov     rax, [rcx]
0x140047c58  test    rax, rax
0x140047c5b  jz      short loc_140047C71
0x140047c5d  mov     rdx, rcx; Entry
0x140047c60  mov     rcx, rax; Lookaside
0x140047c63  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047c6a  nop     dword ptr [rax+rax+00h]
0x140047c6f  jmp     short loc_140047C80
0x140047c71  mov     edx, [rcx+8]; Tag
0x140047c74  call    cs:__imp_ExFreePoolWithTag
0x140047c7b  nop     dword ptr [rax+rax+00h]
0x140047c80  mov     [rbx+48h], rdi
0x140047c84  mov     rcx, [rbx+58h]
0x140047c88  test    rcx, rcx
0x140047c8b  jz      short loc_140047CC0
0x140047c8d  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047c91  mov     rax, [rcx]
0x140047c94  test    rax, rax
0x140047c97  jz      short loc_140047CAD
0x140047c99  mov     rdx, rcx; Entry
0x140047c9c  mov     rcx, rax; Lookaside
0x140047c9f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047ca6  nop     dword ptr [rax+rax+00h]
0x140047cab  jmp     short loc_140047CBC
0x140047cad  mov     edx, [rcx+8]; Tag
0x140047cb0  call    cs:__imp_ExFreePoolWithTag
0x140047cb7  nop     dword ptr [rax+rax+00h]
0x140047cbc  mov     [rbx+58h], rdi
0x140047cc0  mov     rcx, [rbx+68h]
0x140047cc4  test    rcx, rcx
0x140047cc7  jz      short loc_140047CFC
0x140047cc9  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047ccd  mov     rax, [rcx]
0x140047cd0  test    rax, rax
0x140047cd3  jz      short loc_140047CE9
0x140047cd5  mov     rdx, rcx; Entry
0x140047cd8  mov     rcx, rax; Lookaside
0x140047cdb  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047ce2  nop     dword ptr [rax+rax+00h]
0x140047ce7  jmp     short loc_140047CF8
0x140047ce9  mov     edx, [rcx+8]; Tag
0x140047cec  call    cs:__imp_ExFreePoolWithTag
0x140047cf3  nop     dword ptr [rax+rax+00h]
0x140047cf8  mov     [rbx+68h], rdi
0x140047cfc  mov     rcx, [rbx+90h]
0x140047d03  test    rcx, rcx
0x140047d06  jz      short loc_140047D3E
0x140047d08  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047d0c  mov     rax, [rcx]
0x140047d0f  test    rax, rax
0x140047d12  jz      short loc_140047D28
0x140047d14  mov     rdx, rcx; Entry
0x140047d17  mov     rcx, rax; Lookaside
0x140047d1a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047d21  nop     dword ptr [rax+rax+00h]
0x140047d26  jmp     short loc_140047D37
0x140047d28  mov     edx, [rcx+8]; Tag
0x140047d2b  call    cs:__imp_ExFreePoolWithTag
0x140047d32  nop     dword ptr [rax+rax+00h]
0x140047d37  mov     [rbx+90h], rdi
0x140047d3e  mov     rcx, [rbx+0A0h]
0x140047d45  test    rcx, rcx
0x140047d48  jz      short loc_140047D80
0x140047d4a  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047d4e  mov     rax, [rcx]
0x140047d51  test    rax, rax
0x140047d54  jz      short loc_140047D6A
0x140047d56  mov     rdx, rcx; Entry
0x140047d59  mov     rcx, rax; Lookaside
0x140047d5c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047d63  nop     dword ptr [rax+rax+00h]
0x140047d68  jmp     short loc_140047D79
0x140047d6a  mov     edx, [rcx+8]; Tag
0x140047d6d  call    cs:__imp_ExFreePoolWithTag
0x140047d74  nop     dword ptr [rax+rax+00h]
0x140047d79  mov     [rbx+0A0h], rdi
0x140047d80  mov     rcx, [rbx+0B0h]
0x140047d87  test    rcx, rcx
0x140047d8a  jz      short loc_140047DC2
0x140047d8c  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047d90  mov     rax, [rcx]
0x140047d93  test    rax, rax
0x140047d96  jz      short loc_140047DAC
0x140047d98  mov     rdx, rcx; Entry
0x140047d9b  mov     rcx, rax; Lookaside
0x140047d9e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047da5  nop     dword ptr [rax+rax+00h]
0x140047daa  jmp     short loc_140047DBB
0x140047dac  mov     edx, [rcx+8]; Tag
0x140047daf  call    cs:__imp_ExFreePoolWithTag
0x140047db6  nop     dword ptr [rax+rax+00h]
0x140047dbb  mov     [rbx+0B0h], rdi
0x140047dc2  mov     rcx, [rbx+0C0h]
0x140047dc9  test    rcx, rcx
0x140047dcc  jz      short loc_140047E04
0x140047dce  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047dd2  mov     rax, [rcx]
0x140047dd5  test    rax, rax
0x140047dd8  jz      short loc_140047DEE
0x140047dda  mov     rdx, rcx; Entry
0x140047ddd  mov     rcx, rax; Lookaside
0x140047de0  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047de7  nop     dword ptr [rax+rax+00h]
0x140047dec  jmp     short loc_140047DFD
0x140047dee  mov     edx, [rcx+8]; Tag
0x140047df1  call    cs:__imp_ExFreePoolWithTag
0x140047df8  nop     dword ptr [rax+rax+00h]
0x140047dfd  mov     [rbx+0C0h], rdi
0x140047e04  call    Feature_53299205__private_IsEnabledDeviceUsageNoInline
0x140047e09  test    eax, eax
0x140047e0b  jz      loc_140047F12
0x140047e11  mov     rcx, [rbx+0D0h]
0x140047e18  test    rcx, rcx
0x140047e1b  jz      short loc_140047E53
0x140047e1d  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047e21  mov     rax, [rcx]
0x140047e24  test    rax, rax
0x140047e27  jz      short loc_140047E3D
0x140047e29  mov     rdx, rcx; Entry
0x140047e2c  mov     rcx, rax; Lookaside
0x140047e2f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047e36  nop     dword ptr [rax+rax+00h]
0x140047e3b  jmp     short loc_140047E4C
0x140047e3d  mov     edx, [rcx+8]; Tag
0x140047e40  call    cs:__imp_ExFreePoolWithTag
0x140047e47  nop     dword ptr [rax+rax+00h]
0x140047e4c  mov     [rbx+0D0h], rdi
0x140047e53  mov     rcx, [rbx+0E0h]
0x140047e5a  test    rcx, rcx
0x140047e5d  jz      short loc_140047E95
0x140047e5f  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047e63  mov     rax, [rcx]
0x140047e66  test    rax, rax
0x140047e69  jz      short loc_140047E7F
0x140047e6b  mov     rdx, rcx; Entry
0x140047e6e  mov     rcx, rax; Lookaside
0x140047e71  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047e78  nop     dword ptr [rax+rax+00h]
0x140047e7d  jmp     short loc_140047E8E
0x140047e7f  mov     edx, [rcx+8]; Tag
0x140047e82  call    cs:__imp_ExFreePoolWithTag
0x140047e89  nop     dword ptr [rax+rax+00h]
0x140047e8e  mov     [rbx+0E0h], rdi
0x140047e95  mov     rcx, [rbx+0F0h]
0x140047e9c  test    rcx, rcx
0x140047e9f  jz      short loc_140047ED7
0x140047ea1  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047ea5  mov     rax, [rcx]
0x140047ea8  test    rax, rax
0x140047eab  jz      short loc_140047EC1
0x140047ead  mov     rdx, rcx; Entry
0x140047eb0  mov     rcx, rax; Lookaside
0x140047eb3  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047eba  nop     dword ptr [rax+rax+00h]
0x140047ebf  jmp     short loc_140047ED0
0x140047ec1  mov     edx, [rcx+8]; Tag
0x140047ec4  call    cs:__imp_ExFreePoolWithTag
0x140047ecb  nop     dword ptr [rax+rax+00h]
0x140047ed0  mov     [rbx+0F0h], rdi
0x140047ed7  mov     rcx, [rbx+100h]
0x140047ede  test    rcx, rcx
0x140047ee1  jz      short loc_140047F12
0x140047ee3  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047ee7  mov     rax, [rcx]
0x140047eea  test    rax, rax
0x140047eed  jz      short loc_140047F03
0x140047eef  mov     rdx, rcx; Entry
0x140047ef2  mov     rcx, rax; Lookaside
0x140047ef5  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047efc  nop     dword ptr [rax+rax+00h]
0x140047f01  jmp     short loc_140047F12
0x140047f03  mov     edx, [rcx+8]; Tag
0x140047f06  call    cs:__imp_ExFreePoolWithTag
0x140047f0d  nop     dword ptr [rax+rax+00h]
0x140047f12  xor     edx, edx; Val
0x140047f14  mov     r8d, 108h; Size
0x140047f1a  mov     rcx, rbx; void *
0x140047f1d  call    memset
0x140047f22  mov     rbx, [rsp+28h+arg_0]
0x140047f27  add     rsp, 20h
0x140047f2b  pop     rdi
0x140047f2c  retn
```
