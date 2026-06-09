# CmsBPlusTable::operator delete(void *)

- ea: `0x140088b70`
- end: `0x14008900f`
- name: `??3CmsBPlusTable@@SAXPEAX@Z`
- size: `1183`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation`

## callers

- `0x14012dbc0`

## callees

- `0x140088b70`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088cb0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088d05`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088d5a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088daf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088e35`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088cb0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088d05`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088d5a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088daf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088e35`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x140088df7`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x140088df7`
- `ntoskrnl!ExDeleteFastResource` at `0x140088ba9`
- `ntoskrnl!ExDeleteFastResource` at `0x140088ba9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140088e48`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140088e5b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140088e6c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140088e7d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140088e8e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140088e48`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140088e5b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140088e6c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140088e7d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140088e8e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8d3d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8d5b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8d79`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8d97`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8db5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8d3d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8d5b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8d79`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8d97`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8db5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088bd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088bfd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088c2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088ebd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088ed0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088f02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088f34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088f66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088f98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088fab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088fc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088ffe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088bd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088bfd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088c2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088ebd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088ed0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088f02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088f34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088f66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088f98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088fab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088fc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088ffe`

## pseudocode

```c
void __fastcall CmsBPlusTable::operator delete(struct _SLIST_ENTRY *a1)
{
  char v1; // al
  struct _SLIST_ENTRY *v2; // rbx
  struct _SLIST_ENTRY *Next; // rdi
  struct _SLIST_ENTRY *v4; // rcx
  void *v5; // rcx
  struct _SLIST_ENTRY *v6; // rcx
  struct _SLIST_ENTRY *v7; // rcx
  void *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rsi
  struct _SLIST_ENTRY *v11; // r8
  struct _NPAGED_LOOKASIDE_LIST *v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rsi
  struct _SLIST_ENTRY *v15; // r8
  struct _NPAGED_LOOKASIDE_LIST *v16; // rcx
  struct _SLIST_ENTRY *v17; // r8
  struct _SLIST_ENTRY *v18; // rsi
  struct _SLIST_ENTRY *v19; // r8
  struct _NPAGED_LOOKASIDE_LIST *v20; // rcx
  struct _SLIST_ENTRY *v21; // r8
  struct _SLIST_ENTRY *v22; // rsi
  struct _SLIST_ENTRY *v23; // r8
  struct _NPAGED_LOOKASIDE_LIST *v24; // rcx
  struct _SLIST_ENTRY *v25; // rcx
  struct _SLIST_ENTRY *v26; // rcx
  struct _SLIST_ENTRY *v27; // r8
  struct _SLIST_ENTRY *v28; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v29; // rcx
  void *v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  int v36; // [rsp+24h] [rbp-14h]

  v1 = *((_BYTE *)&a1->Next + 12);
  v2 = a1;
  if ( (v1 & 1) == 0 )
    goto LABEL_71;
  Next = a1[4].Next;
  if ( (v1 & 8) != 0 )
  {
    ExDeleteFastResource(&a1[34]);
    v4 = v2[59].Next;
    if ( v4 )
      ExFreePoolWithTag(v4, 0);
    v5 = (void *)*((_QWORD *)&v2[77].Next + 1);
    if ( v5 )
      ExFreePoolWithTag(v5, 0);
    v6 = v2[94].Next;
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
    v7 = v2[92].Next;
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
    LODWORD(v2[78].Next) = 0;
    *((_DWORD *)&v2[92].Next + 2) = 0;
    if ( ((__int64)v2[89].Next & 1) != 0 )
    {
      v8 = (void *)*((_QWORD *)&v2[88].Next + 1);
      if ( v8 )
        ExFreePoolWithTag(v8, 0);
    }
    HIDWORD(v2[89].Next) = 32;
    *((_QWORD *)&v2[88].Next + 1) = (char *)v2 + 1432;
    *((_DWORD *)&v2[87].Next + 3) = v36;
    *(struct _SLIST_ENTRY *)((char *)&v2[86] + 8) = 0;
    *((_DWORD *)&v2[87].Next + 2) = 0;
    v2[88].Next = 0;
    LOBYTE(v2[89].Next) = 0;
    v9 = *((_QWORD *)&v2[82].Next + 1);
    if ( !v9 )
      goto LABEL_20;
    v10 = *(_QWORD *)(v9 - 16);
    v11 = (struct _SLIST_ENTRY *)(v9 - 16);
    if ( !v10 )
      goto LABEL_58;
    if ( *(_BYTE *)(v10 + 8) )
    {
      v12 = (struct _NPAGED_LOOKASIDE_LIST *)(v10 + 64);
      if ( *(_BYTE *)(v10 + 9) )
        ExFreeToNPagedLookasideList(v12, v11);
      else
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v12, v11);
      goto LABEL_19;
    }
    v31 = *(_QWORD *)(v10 + 88);
    if ( (int)v31 < *(_DWORD *)(v10 + 80) || SHIDWORD(v31) >= (int)v31 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v10 + 64), v11);
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 88));
    }
    else
    {
LABEL_58:
      ExFreePoolWithTag(v11, 0);
    }
LABEL_19:
    *((_QWORD *)&v2[82].Next + 1) = 0;
    LODWORD(v2[83].Next) = -1;
LABEL_20:
    v13 = *((_QWORD *)&v2[78].Next + 1);
    if ( !v13 )
    {
LABEL_26:
      v17 = v2[52].Next;
      if ( !v17 )
      {
LABEL_32:
        v21 = v2[48].Next;
        if ( !v21 )
          goto LABEL_38;
        v22 = v21[-1].Next;
        v23 = v21 - 1;
        if ( !v22 )
          goto LABEL_67;
        if ( *((_BYTE *)&v22->Next + 8) )
        {
          v24 = (struct _NPAGED_LOOKASIDE_LIST *)&v22[4];
          if ( *((_BYTE *)&v22->Next + 9) )
            ExFreeToNPagedLookasideList(v24, v23);
          else
            ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v24, v23);
          goto LABEL_37;
        }
        v34 = *((_QWORD *)&v22[5].Next + 1);
        if ( (int)v34 < SLODWORD(v22[5].Next) || SHIDWORD(v34) >= (int)v34 )
        {
          ExpInterlockedPushEntrySList((PSLIST_HEADER)&v22[4], v23);
          _InterlockedIncrement((volatile signed __int32 *)&v22[5].Next + 2);
        }
        else
        {
LABEL_67:
          ExFreePoolWithTag(v23, 0);
        }
LABEL_37:
        v2[48].Next = 0;
        *((_DWORD *)&v2[48].Next + 2) = -1;
        goto LABEL_38;
      }
      v18 = v17[-1].Next;
      v19 = v17 - 1;
      if ( !v18 )
        goto LABEL_64;
      if ( *((_BYTE *)&v18->Next + 8) )
      {
        v20 = (struct _NPAGED_LOOKASIDE_LIST *)&v18[4];
        if ( *((_BYTE *)&v18->Next + 9) )
          ExFreeToNPagedLookasideList(v20, v19);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v20, v19);
        goto LABEL_31;
      }
      v33 = *((_QWORD *)&v18[5].Next + 1);
      if ( (int)v33 < SLODWORD(v18[5].Next) || SHIDWORD(v33) >= (int)v33 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)&v18[4], v19);
        _InterlockedIncrement((volatile signed __int32 *)&v18[5].Next + 2);
      }
      else
      {
LABEL_64:
        ExFreePoolWithTag(v19, 0);
      }
LABEL_31:
      v2[52].Next = 0;
      *((_DWORD *)&v2[52].Next + 2) = -1;
      goto LABEL_32;
    }
    v14 = *(_QWORD *)(v13 - 16);
    v15 = (struct _SLIST_ENTRY *)(v13 - 16);
    if ( !v14 )
      goto LABEL_61;
    if ( *(_BYTE *)(v14 + 8) )
    {
      v16 = (struct _NPAGED_LOOKASIDE_LIST *)(v14 + 64);
      if ( *(_BYTE *)(v14 + 9) )
        ExFreeToNPagedLookasideList(v16, v15);
      else
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v16, v15);
      goto LABEL_25;
    }
    v32 = *(_QWORD *)(v14 + 88);
    if ( (int)v32 < *(_DWORD *)(v14 + 80) || SHIDWORD(v32) >= (int)v32 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v14 + 64), v15);
      _InterlockedIncrement((volatile signed __int32 *)(v14 + 88));
    }
    else
    {
LABEL_61:
      ExFreePoolWithTag(v15, 0);
    }
LABEL_25:
    *((_QWORD *)&v2[78].Next + 1) = 0;
    LODWORD(v2[79].Next) = -1;
    goto LABEL_26;
  }
LABEL_38:
  if ( *((_QWORD *)&v2[2].Next + 1) )
  {
    if ( v2 == Next )
    {
      v30 = (void *)*((_QWORD *)&v2[32].Next + 1);
      if ( v30 )
      {
        ExFreePoolWithTag(v30, 0);
        *((_QWORD *)&v2[32].Next + 1) = 0;
      }
      v26 = (struct _SLIST_ENTRY *)((char *)v2 + 392);
    }
    else
    {
      v25 = v2[28].Next;
      if ( v25 )
      {
        ExFreePoolWithTag(v25, 0);
        v2[28].Next = 0;
      }
      v26 = v2 + 20;
    }
    ExCleanupAutoExpandPushLock(v26);
  }
  v27 = v2 - 1;
  v28 = v2[-1].Next;
  if ( !v28 )
  {
LABEL_70:
    a1 = v27;
LABEL_71:
    ExFreePoolWithTag(a1, 0);
    return;
  }
  if ( !*((_BYTE *)&v28->Next + 8) )
  {
    v35 = *((_QWORD *)&v28[5].Next + 1);
    if ( (int)v35 < SLODWORD(v28[5].Next) || SHIDWORD(v35) >= (int)v35 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)&v28[4], v27);
      _InterlockedIncrement((volatile signed __int32 *)&v28[5].Next + 2);
      return;
    }
    goto LABEL_70;
  }
  v29 = (struct _NPAGED_LOOKASIDE_LIST *)&v28[4];
  if ( *((_BYTE *)&v28->Next + 9) )
    ExFreeToNPagedLookasideList(v29, v27);
  else
    ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v29, v27);
}

```

## disassembly

```asm
0x140088b70  push    rbx
0x140088b72  sub     rsp, 30h
0x140088b76  movzx   eax, byte ptr [rcx+0Ch]
0x140088b7a  mov     rbx, rcx
0x140088b7d  test    al, 1
0x140088b7f  jz      loc_140088FFC
0x140088b85  mov     [rsp+38h+arg_0], rbp
0x140088b8a  xor     ebp, ebp
0x140088b8c  mov     [rsp+38h+arg_10], rdi
0x140088b91  mov     rdi, [rcx+40h]
0x140088b95  test    al, 8
0x140088b97  jz      loc_140088DD1
0x140088b9d  add     rcx, 220h
0x140088ba4  mov     [rsp+38h+arg_8], rsi
0x140088ba9  call    cs:__imp_ExDeleteFastResource
0x140088bb0  nop     dword ptr [rax+rax+00h]
0x140088bb5  mov     rcx, [rbx+3B0h]; P
0x140088bbc  test    rcx, rcx
0x140088bbf  jnz     loc_140088EBB
0x140088bc5  mov     rcx, [rbx+4D8h]; P
0x140088bcc  test    rcx, rcx
0x140088bcf  jz      short loc_140088BDF
0x140088bd1  xor     edx, edx; Tag
0x140088bd3  call    cs:__imp_ExFreePoolWithTag
0x140088bda  nop     dword ptr [rax+rax+00h]
0x140088bdf  mov     rcx, [rbx+5E0h]; P
0x140088be6  test    rcx, rcx
0x140088be9  jnz     loc_140088ECE
0x140088bef  mov     rcx, [rbx+5C0h]; P
0x140088bf6  test    rcx, rcx
0x140088bf9  jz      short loc_140088C09
0x140088bfb  xor     edx, edx; Tag
0x140088bfd  call    cs:__imp_ExFreePoolWithTag
0x140088c04  nop     dword ptr [rax+rax+00h]
0x140088c09  mov     [rbx+4E0h], ebp
0x140088c0f  mov     [rbx+5C8h], ebp
0x140088c15  test    byte ptr [rbx+590h], 1
0x140088c1c  jz      short loc_140088C38
0x140088c1e  mov     rcx, [rbx+588h]; P
0x140088c25  test    rcx, rcx
0x140088c28  jz      short loc_140088C38
0x140088c2a  xor     edx, edx; Tag
0x140088c2c  call    cs:__imp_ExFreePoolWithTag
0x140088c33  nop     dword ptr [rax+rax+00h]
0x140088c38  lea     rax, [rbx+598h]
0x140088c3f  mov     dword ptr [rbx+594h], 20h ; ' '
0x140088c49  mov     [rbx+588h], rax
0x140088c50  xorps   xmm0, xmm0
0x140088c53  mov     eax, [rsp+38h+var_14]
0x140088c57  mov     [rbx+57Ch], eax
0x140088c5d  movups  xmmword ptr [rbx+568h], xmm0
0x140088c64  mov     [rbx+578h], ebp
0x140088c6a  mov     [rbx+580h], rbp
0x140088c71  mov     [rbx+590h], bpl
0x140088c78  mov     r8, [rbx+528h]
0x140088c7f  test    r8, r8
0x140088c82  jz      short loc_140088CCD
0x140088c84  mov     rsi, [r8-10h]
0x140088c88  add     r8, 0FFFFFFFFFFFFFFF0h
0x140088c8c  test    rsi, rsi
0x140088c8f  jz      loc_140088EFD
0x140088c95  cmp     [rsi+8], bpl
0x140088c99  jz      loc_140088EE1
0x140088c9f  lea     rcx, [rsi+40h]; Lookaside
0x140088ca3  mov     rdx, r8; Entry
0x140088ca6  cmp     [rsi+9], bpl
0x140088caa  jz      loc_140088E5B
0x140088cb0  call    cs:__imp_ExFreeToNPagedLookasideList
0x140088cb7  nop     dword ptr [rax+rax+00h]
0x140088cbc  mov     [rbx+528h], rbp
0x140088cc3  mov     dword ptr [rbx+530h], 0FFFFFFFFh
0x140088ccd  mov     r8, [rbx+4E8h]
0x140088cd4  test    r8, r8
0x140088cd7  jz      short loc_140088D22
0x140088cd9  mov     rsi, [r8-10h]
0x140088cdd  add     r8, 0FFFFFFFFFFFFFFF0h
0x140088ce1  test    rsi, rsi
0x140088ce4  jz      loc_140088F2F
0x140088cea  cmp     [rsi+8], bpl
0x140088cee  jz      loc_140088F13
0x140088cf4  lea     rcx, [rsi+40h]; Lookaside
0x140088cf8  mov     rdx, r8; Entry
0x140088cfb  cmp     [rsi+9], bpl
0x140088cff  jz      loc_140088E6C
0x140088d05  call    cs:__imp_ExFreeToNPagedLookasideList
0x140088d0c  nop     dword ptr [rax+rax+00h]
0x140088d11  mov     [rbx+4E8h], rbp
0x140088d18  mov     dword ptr [rbx+4F0h], 0FFFFFFFFh
0x140088d22  mov     r8, [rbx+340h]
0x140088d29  test    r8, r8
0x140088d2c  jz      short loc_140088D77
0x140088d2e  mov     rsi, [r8-10h]
0x140088d32  add     r8, 0FFFFFFFFFFFFFFF0h
0x140088d36  test    rsi, rsi
0x140088d39  jz      loc_140088F61
0x140088d3f  cmp     [rsi+8], bpl
0x140088d43  jz      loc_140088F45
0x140088d49  lea     rcx, [rsi+40h]; Lookaside
0x140088d4d  mov     rdx, r8; Entry
0x140088d50  cmp     [rsi+9], bpl
0x140088d54  jz      loc_140088E7D
0x140088d5a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140088d61  nop     dword ptr [rax+rax+00h]
0x140088d66  mov     [rbx+340h], rbp
0x140088d6d  mov     dword ptr [rbx+348h], 0FFFFFFFFh
0x140088d77  mov     r8, [rbx+300h]
0x140088d7e  test    r8, r8
0x140088d81  jz      short loc_140088DCC
0x140088d83  mov     rsi, [r8-10h]
0x140088d87  add     r8, 0FFFFFFFFFFFFFFF0h
0x140088d8b  test    rsi, rsi
0x140088d8e  jz      loc_140088F93
0x140088d94  cmp     [rsi+8], bpl
0x140088d98  jz      loc_140088F77
0x140088d9e  lea     rcx, [rsi+40h]; Lookaside
0x140088da2  mov     rdx, r8; Entry
0x140088da5  cmp     [rsi+9], bpl
0x140088da9  jz      loc_140088E8E
0x140088daf  call    cs:__imp_ExFreeToNPagedLookasideList
0x140088db6  nop     dword ptr [rax+rax+00h]
0x140088dbb  mov     [rbx+300h], rbp
0x140088dc2  mov     dword ptr [rbx+308h], 0FFFFFFFFh
0x140088dcc  mov     rsi, [rsp+38h+arg_8]
0x140088dd1  cmp     [rbx+28h], rbp
0x140088dd5  jz      short loc_140088E03
0x140088dd7  cmp     rbx, rdi
0x140088dda  jz      loc_140088E9F
0x140088de0  mov     rcx, [rbx+1C0h]; P
0x140088de7  test    rcx, rcx
0x140088dea  jnz     loc_140088FA9
0x140088df0  lea     rcx, [rbx+140h]
0x140088df7  call    cs:__imp_ExCleanupAutoExpandPushLock
0x140088dfe  nop     dword ptr [rax+rax+00h]
0x140088e03  mov     rdi, [rsp+38h+arg_10]
0x140088e08  lea     r8, [rbx-10h]
0x140088e0c  mov     rbx, [rbx-10h]
0x140088e10  mov     rbp, [rsp+38h+arg_0]
0x140088e15  test    rbx, rbx
0x140088e18  jz      loc_140088FF9
0x140088e1e  cmp     byte ptr [rbx+8], 0
0x140088e22  jz      loc_140088FDD
0x140088e28  cmp     byte ptr [rbx+9], 0
0x140088e2c  lea     rcx, [rbx+40h]; Lookaside
0x140088e30  mov     rdx, r8; Entry
0x140088e33  jz      short loc_140088E48
0x140088e35  call    cs:__imp_ExFreeToNPagedLookasideList
0x140088e3c  nop     dword ptr [rax+rax+00h]
0x140088e41  add     rsp, 30h
0x140088e45  pop     rbx
0x140088e46  retn
0x140088e48  call    cs:__imp_ExFreeToPagedLookasideList
0x140088e4f  nop     dword ptr [rax+rax+00h]
0x140088e54  add     rsp, 30h
0x140088e58  pop     rbx
0x140088e59  retn
0x140088e5b  call    cs:__imp_ExFreeToPagedLookasideList
0x140088e62  nop     dword ptr [rax+rax+00h]
0x140088e67  jmp     loc_140088CBC
0x140088e6c  call    cs:__imp_ExFreeToPagedLookasideList
0x140088e73  nop     dword ptr [rax+rax+00h]
0x140088e78  jmp     loc_140088D11
0x140088e7d  call    cs:__imp_ExFreeToPagedLookasideList
0x140088e84  nop     dword ptr [rax+rax+00h]
0x140088e89  jmp     loc_140088D66
0x140088e8e  call    cs:__imp_ExFreeToPagedLookasideList
0x140088e95  nop     dword ptr [rax+rax+00h]
0x140088e9a  jmp     loc_140088DBB
0x140088e9f  mov     rcx, [rbx+208h]; P
0x140088ea6  test    rcx, rcx
0x140088ea9  jnz     loc_140088FC3
0x140088eaf  lea     rcx, [rbx+188h]
0x140088eb6  jmp     loc_140088DF7
0x140088ebb  xor     edx, edx; Tag
0x140088ebd  call    cs:__imp_ExFreePoolWithTag
0x140088ec4  nop     dword ptr [rax+rax+00h]
0x140088ec9  jmp     loc_140088BC5
0x140088ece  xor     edx, edx; Tag
0x140088ed0  call    cs:__imp_ExFreePoolWithTag
0x140088ed7  nop     dword ptr [rax+rax+00h]
0x140088edc  jmp     loc_140088BEF
0x140088ee1  mov     rcx, [rsi+58h]
0x140088ee5  cmp     ecx, [rsi+50h]
0x140088ee8  jl      loc_1401F8D36
0x140088eee  mov     rax, rcx
0x140088ef1  shr     rax, 20h
0x140088ef5  cmp     eax, ecx
0x140088ef7  jge     loc_1401F8D36
0x140088efd  xor     edx, edx; Tag
0x140088eff  mov     rcx, r8; P
0x140088f02  call    cs:__imp_ExFreePoolWithTag
0x140088f09  nop     dword ptr [rax+rax+00h]
0x140088f0e  jmp     loc_140088CBC
0x140088f13  mov     rcx, [rsi+58h]
0x140088f17  cmp     ecx, [rsi+50h]
0x140088f1a  jl      loc_1401F8D54
0x140088f20  mov     rax, rcx
0x140088f23  shr     rax, 20h
0x140088f27  cmp     eax, ecx
0x140088f29  jge     loc_1401F8D54
0x140088f2f  xor     edx, edx; Tag
0x140088f31  mov     rcx, r8; P
0x140088f34  call    cs:__imp_ExFreePoolWithTag
0x140088f3b  nop     dword ptr [rax+rax+00h]
0x140088f40  jmp     loc_140088D11
0x140088f45  mov     rcx, [rsi+58h]
0x140088f49  cmp     ecx, [rsi+50h]
0x140088f4c  jl      loc_1401F8D72
0x140088f52  mov     rax, rcx
0x140088f55  shr     rax, 20h
0x140088f59  cmp     eax, ecx
0x140088f5b  jge     loc_1401F8D72
0x140088f61  xor     edx, edx; Tag
0x140088f63  mov     rcx, r8; P
0x140088f66  call    cs:__imp_ExFreePoolWithTag
0x140088f6d  nop     dword ptr [rax+rax+00h]
0x140088f72  jmp     loc_140088D66
0x140088f77  mov     rcx, [rsi+58h]
0x140088f7b  cmp     ecx, [rsi+50h]
0x140088f7e  jl      loc_1401F8D90
0x140088f84  mov     rax, rcx
0x140088f87  shr     rax, 20h
0x140088f8b  cmp     eax, ecx
0x140088f8d  jge     loc_1401F8D90
0x140088f93  xor     edx, edx; Tag
0x140088f95  mov     rcx, r8; P
0x140088f98  call    cs:__imp_ExFreePoolWithTag
0x140088f9f  nop     dword ptr [rax+rax+00h]
0x140088fa4  jmp     loc_140088DBB
0x140088fa9  xor     edx, edx; Tag
0x140088fab  call    cs:__imp_ExFreePoolWithTag
0x140088fb2  nop     dword ptr [rax+rax+00h]
0x140088fb7  mov     [rbx+1C0h], rbp
0x140088fbe  jmp     loc_140088DF0
0x140088fc3  xor     edx, edx; Tag
0x140088fc5  call    cs:__imp_ExFreePoolWithTag
0x140088fcc  nop     dword ptr [rax+rax+00h]
0x140088fd1  mov     [rbx+208h], rbp
0x140088fd8  jmp     loc_140088EAF
0x140088fdd  mov     rcx, [rbx+58h]
0x140088fe1  cmp     ecx, [rbx+50h]
0x140088fe4  jl      loc_1401F8DAE
0x140088fea  mov     rax, rcx
0x140088fed  shr     rax, 20h
0x140088ff1  cmp     eax, ecx
0x140088ff3  jge     loc_1401F8DAE
0x140088ff9  mov     rcx, r8; P
0x140088ffc  xor     edx, edx; Tag
0x140088ffe  call    cs:__imp_ExFreePoolWithTag
0x140089005  nop     dword ptr [rax+rax+00h]
0x14008900a  jmp     loc_140088E41
0x1401f8d36  lea     rcx, [rsi+40h]; ListHead
0x1401f8d3a  mov     rdx, r8; ListEntry
0x1401f8d3d  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f8d44  nop     dword ptr [rax+rax+00h]
0x1401f8d49  nop
0x1401f8d4a  lock inc dword ptr [rsi+58h]
0x1401f8d4e  nop
0x1401f8d4f  jmp     loc_140088CBC
0x1401f8d54  lea     rcx, [rsi+40h]; ListHead
0x1401f8d58  mov     rdx, r8; ListEntry
0x1401f8d5b  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f8d62  nop     dword ptr [rax+rax+00h]
0x1401f8d67  nop
0x1401f8d68  lock inc dword ptr [rsi+58h]
0x1401f8d6c  nop
0x1401f8d6d  jmp     loc_140088D11
0x1401f8d72  lea     rcx, [rsi+40h]; ListHead
0x1401f8d76  mov     rdx, r8; ListEntry
0x1401f8d79  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f8d80  nop     dword ptr [rax+rax+00h]
0x1401f8d85  nop
0x1401f8d86  lock inc dword ptr [rsi+58h]
0x1401f8d8a  nop
0x1401f8d8b  jmp     loc_140088D66
0x1401f8d90  lea     rcx, [rsi+40h]; ListHead
0x1401f8d94  mov     rdx, r8; ListEntry
0x1401f8d97  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f8d9e  nop     dword ptr [rax+rax+00h]
0x1401f8da3  nop
0x1401f8da4  lock inc dword ptr [rsi+58h]
0x1401f8da8  nop
0x1401f8da9  jmp     loc_140088DBB
0x1401f8dae  lea     rcx, [rbx+40h]; ListHead
0x1401f8db2  mov     rdx, r8; ListEntry
0x1401f8db5  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f8dbc  nop     dword ptr [rax+rax+00h]
0x1401f8dc1  nop
0x1401f8dc2  lock inc dword ptr [rbx+58h]
0x1401f8dc6  nop
0x1401f8dc7  jmp     loc_140088E41
```
