# CmsBPlusTable::operator delete(void *)

- ea: `0x14007f010`
- end: `0x14007f4af`
- name: `??3CmsBPlusTable@@SAXPEAX@Z`
- size: `1183`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140131f50`

## callees

- `0x14007f010`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f150`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f1a5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f1fa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f24f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f2d5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f150`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f1a5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f1fa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f24f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f2d5`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14007f297`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14007f297`
- `ntoskrnl!ExDeleteFastResource` at `0x14007f049`
- `ntoskrnl!ExDeleteFastResource` at `0x14007f049`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007f2e8`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007f2fb`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007f30c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007f31d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007f32e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007f2e8`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007f2fb`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007f30c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007f31d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007f32e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140200537`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140200555`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140200573`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140200591`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1402005af`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140200537`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140200555`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140200573`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140200591`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1402005af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f073`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f09d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f0cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f35d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f370`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f3a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f3d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f406`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f438`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f44b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f465`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f49e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f073`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f09d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f0cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f35d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f370`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f3a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f3d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f406`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f438`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f44b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f465`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f49e`

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
0x14007f010  push    rbx
0x14007f012  sub     rsp, 30h
0x14007f016  movzx   eax, byte ptr [rcx+0Ch]
0x14007f01a  mov     rbx, rcx
0x14007f01d  test    al, 1
0x14007f01f  jz      loc_14007F49C
0x14007f025  mov     [rsp+38h+arg_0], rbp
0x14007f02a  xor     ebp, ebp
0x14007f02c  mov     [rsp+38h+arg_10], rdi
0x14007f031  mov     rdi, [rcx+40h]
0x14007f035  test    al, 8
0x14007f037  jz      loc_14007F271
0x14007f03d  add     rcx, 220h
0x14007f044  mov     [rsp+38h+arg_8], rsi
0x14007f049  call    cs:__imp_ExDeleteFastResource
0x14007f050  nop     dword ptr [rax+rax+00h]
0x14007f055  mov     rcx, [rbx+3B0h]; P
0x14007f05c  test    rcx, rcx
0x14007f05f  jnz     loc_14007F35B
0x14007f065  mov     rcx, [rbx+4D8h]; P
0x14007f06c  test    rcx, rcx
0x14007f06f  jz      short loc_14007F07F
0x14007f071  xor     edx, edx; Tag
0x14007f073  call    cs:__imp_ExFreePoolWithTag
0x14007f07a  nop     dword ptr [rax+rax+00h]
0x14007f07f  mov     rcx, [rbx+5E0h]; P
0x14007f086  test    rcx, rcx
0x14007f089  jnz     loc_14007F36E
0x14007f08f  mov     rcx, [rbx+5C0h]; P
0x14007f096  test    rcx, rcx
0x14007f099  jz      short loc_14007F0A9
0x14007f09b  xor     edx, edx; Tag
0x14007f09d  call    cs:__imp_ExFreePoolWithTag
0x14007f0a4  nop     dword ptr [rax+rax+00h]
0x14007f0a9  mov     [rbx+4E0h], ebp
0x14007f0af  mov     [rbx+5C8h], ebp
0x14007f0b5  test    byte ptr [rbx+590h], 1
0x14007f0bc  jz      short loc_14007F0D8
0x14007f0be  mov     rcx, [rbx+588h]; P
0x14007f0c5  test    rcx, rcx
0x14007f0c8  jz      short loc_14007F0D8
0x14007f0ca  xor     edx, edx; Tag
0x14007f0cc  call    cs:__imp_ExFreePoolWithTag
0x14007f0d3  nop     dword ptr [rax+rax+00h]
0x14007f0d8  lea     rax, [rbx+598h]
0x14007f0df  mov     dword ptr [rbx+594h], 20h ; ' '
0x14007f0e9  mov     [rbx+588h], rax
0x14007f0f0  xorps   xmm0, xmm0
0x14007f0f3  mov     eax, [rsp+38h+var_14]
0x14007f0f7  mov     [rbx+57Ch], eax
0x14007f0fd  movups  xmmword ptr [rbx+568h], xmm0
0x14007f104  mov     [rbx+578h], ebp
0x14007f10a  mov     [rbx+580h], rbp
0x14007f111  mov     [rbx+590h], bpl
0x14007f118  mov     r8, [rbx+528h]
0x14007f11f  test    r8, r8
0x14007f122  jz      short loc_14007F16D
0x14007f124  mov     rsi, [r8-10h]
0x14007f128  add     r8, 0FFFFFFFFFFFFFFF0h
0x14007f12c  test    rsi, rsi
0x14007f12f  jz      loc_14007F39D
0x14007f135  cmp     [rsi+8], bpl
0x14007f139  jz      loc_14007F381
0x14007f13f  lea     rcx, [rsi+40h]; Lookaside
0x14007f143  mov     rdx, r8; Entry
0x14007f146  cmp     [rsi+9], bpl
0x14007f14a  jz      loc_14007F2FB
0x14007f150  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007f157  nop     dword ptr [rax+rax+00h]
0x14007f15c  mov     [rbx+528h], rbp
0x14007f163  mov     dword ptr [rbx+530h], 0FFFFFFFFh
0x14007f16d  mov     r8, [rbx+4E8h]
0x14007f174  test    r8, r8
0x14007f177  jz      short loc_14007F1C2
0x14007f179  mov     rsi, [r8-10h]
0x14007f17d  add     r8, 0FFFFFFFFFFFFFFF0h
0x14007f181  test    rsi, rsi
0x14007f184  jz      loc_14007F3CF
0x14007f18a  cmp     [rsi+8], bpl
0x14007f18e  jz      loc_14007F3B3
0x14007f194  lea     rcx, [rsi+40h]; Lookaside
0x14007f198  mov     rdx, r8; Entry
0x14007f19b  cmp     [rsi+9], bpl
0x14007f19f  jz      loc_14007F30C
0x14007f1a5  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007f1ac  nop     dword ptr [rax+rax+00h]
0x14007f1b1  mov     [rbx+4E8h], rbp
0x14007f1b8  mov     dword ptr [rbx+4F0h], 0FFFFFFFFh
0x14007f1c2  mov     r8, [rbx+340h]
0x14007f1c9  test    r8, r8
0x14007f1cc  jz      short loc_14007F217
0x14007f1ce  mov     rsi, [r8-10h]
0x14007f1d2  add     r8, 0FFFFFFFFFFFFFFF0h
0x14007f1d6  test    rsi, rsi
0x14007f1d9  jz      loc_14007F401
0x14007f1df  cmp     [rsi+8], bpl
0x14007f1e3  jz      loc_14007F3E5
0x14007f1e9  lea     rcx, [rsi+40h]; Lookaside
0x14007f1ed  mov     rdx, r8; Entry
0x14007f1f0  cmp     [rsi+9], bpl
0x14007f1f4  jz      loc_14007F31D
0x14007f1fa  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007f201  nop     dword ptr [rax+rax+00h]
0x14007f206  mov     [rbx+340h], rbp
0x14007f20d  mov     dword ptr [rbx+348h], 0FFFFFFFFh
0x14007f217  mov     r8, [rbx+300h]
0x14007f21e  test    r8, r8
0x14007f221  jz      short loc_14007F26C
0x14007f223  mov     rsi, [r8-10h]
0x14007f227  add     r8, 0FFFFFFFFFFFFFFF0h
0x14007f22b  test    rsi, rsi
0x14007f22e  jz      loc_14007F433
0x14007f234  cmp     [rsi+8], bpl
0x14007f238  jz      loc_14007F417
0x14007f23e  lea     rcx, [rsi+40h]; Lookaside
0x14007f242  mov     rdx, r8; Entry
0x14007f245  cmp     [rsi+9], bpl
0x14007f249  jz      loc_14007F32E
0x14007f24f  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007f256  nop     dword ptr [rax+rax+00h]
0x14007f25b  mov     [rbx+300h], rbp
0x14007f262  mov     dword ptr [rbx+308h], 0FFFFFFFFh
0x14007f26c  mov     rsi, [rsp+38h+arg_8]
0x14007f271  cmp     [rbx+28h], rbp
0x14007f275  jz      short loc_14007F2A3
0x14007f277  cmp     rbx, rdi
0x14007f27a  jz      loc_14007F33F
0x14007f280  mov     rcx, [rbx+1C0h]; P
0x14007f287  test    rcx, rcx
0x14007f28a  jnz     loc_14007F449
0x14007f290  lea     rcx, [rbx+140h]
0x14007f297  call    cs:__imp_ExCleanupAutoExpandPushLock
0x14007f29e  nop     dword ptr [rax+rax+00h]
0x14007f2a3  mov     rdi, [rsp+38h+arg_10]
0x14007f2a8  lea     r8, [rbx-10h]
0x14007f2ac  mov     rbx, [rbx-10h]
0x14007f2b0  mov     rbp, [rsp+38h+arg_0]
0x14007f2b5  test    rbx, rbx
0x14007f2b8  jz      loc_14007F499
0x14007f2be  cmp     byte ptr [rbx+8], 0
0x14007f2c2  jz      loc_14007F47D
0x14007f2c8  cmp     byte ptr [rbx+9], 0
0x14007f2cc  lea     rcx, [rbx+40h]; Lookaside
0x14007f2d0  mov     rdx, r8; Entry
0x14007f2d3  jz      short loc_14007F2E8
0x14007f2d5  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007f2dc  nop     dword ptr [rax+rax+00h]
0x14007f2e1  add     rsp, 30h
0x14007f2e5  pop     rbx
0x14007f2e6  retn
0x14007f2e8  call    cs:__imp_ExFreeToPagedLookasideList
0x14007f2ef  nop     dword ptr [rax+rax+00h]
0x14007f2f4  add     rsp, 30h
0x14007f2f8  pop     rbx
0x14007f2f9  retn
0x14007f2fb  call    cs:__imp_ExFreeToPagedLookasideList
0x14007f302  nop     dword ptr [rax+rax+00h]
0x14007f307  jmp     loc_14007F15C
0x14007f30c  call    cs:__imp_ExFreeToPagedLookasideList
0x14007f313  nop     dword ptr [rax+rax+00h]
0x14007f318  jmp     loc_14007F1B1
0x14007f31d  call    cs:__imp_ExFreeToPagedLookasideList
0x14007f324  nop     dword ptr [rax+rax+00h]
0x14007f329  jmp     loc_14007F206
0x14007f32e  call    cs:__imp_ExFreeToPagedLookasideList
0x14007f335  nop     dword ptr [rax+rax+00h]
0x14007f33a  jmp     loc_14007F25B
0x14007f33f  mov     rcx, [rbx+208h]; P
0x14007f346  test    rcx, rcx
0x14007f349  jnz     loc_14007F463
0x14007f34f  lea     rcx, [rbx+188h]
0x14007f356  jmp     loc_14007F297
0x14007f35b  xor     edx, edx; Tag
0x14007f35d  call    cs:__imp_ExFreePoolWithTag
0x14007f364  nop     dword ptr [rax+rax+00h]
0x14007f369  jmp     loc_14007F065
0x14007f36e  xor     edx, edx; Tag
0x14007f370  call    cs:__imp_ExFreePoolWithTag
0x14007f377  nop     dword ptr [rax+rax+00h]
0x14007f37c  jmp     loc_14007F08F
0x14007f381  mov     rcx, [rsi+58h]
0x14007f385  cmp     ecx, [rsi+50h]
0x14007f388  jl      loc_140200530
0x14007f38e  mov     rax, rcx
0x14007f391  shr     rax, 20h
0x14007f395  cmp     eax, ecx
0x14007f397  jge     loc_140200530
0x14007f39d  xor     edx, edx; Tag
0x14007f39f  mov     rcx, r8; P
0x14007f3a2  call    cs:__imp_ExFreePoolWithTag
0x14007f3a9  nop     dword ptr [rax+rax+00h]
0x14007f3ae  jmp     loc_14007F15C
0x14007f3b3  mov     rcx, [rsi+58h]
0x14007f3b7  cmp     ecx, [rsi+50h]
0x14007f3ba  jl      loc_14020054E
0x14007f3c0  mov     rax, rcx
0x14007f3c3  shr     rax, 20h
0x14007f3c7  cmp     eax, ecx
0x14007f3c9  jge     loc_14020054E
0x14007f3cf  xor     edx, edx; Tag
0x14007f3d1  mov     rcx, r8; P
0x14007f3d4  call    cs:__imp_ExFreePoolWithTag
0x14007f3db  nop     dword ptr [rax+rax+00h]
0x14007f3e0  jmp     loc_14007F1B1
0x14007f3e5  mov     rcx, [rsi+58h]
0x14007f3e9  cmp     ecx, [rsi+50h]
0x14007f3ec  jl      loc_14020056C
0x14007f3f2  mov     rax, rcx
0x14007f3f5  shr     rax, 20h
0x14007f3f9  cmp     eax, ecx
0x14007f3fb  jge     loc_14020056C
0x14007f401  xor     edx, edx; Tag
0x14007f403  mov     rcx, r8; P
0x14007f406  call    cs:__imp_ExFreePoolWithTag
0x14007f40d  nop     dword ptr [rax+rax+00h]
0x14007f412  jmp     loc_14007F206
0x14007f417  mov     rcx, [rsi+58h]
0x14007f41b  cmp     ecx, [rsi+50h]
0x14007f41e  jl      loc_14020058A
0x14007f424  mov     rax, rcx
0x14007f427  shr     rax, 20h
0x14007f42b  cmp     eax, ecx
0x14007f42d  jge     loc_14020058A
0x14007f433  xor     edx, edx; Tag
0x14007f435  mov     rcx, r8; P
0x14007f438  call    cs:__imp_ExFreePoolWithTag
0x14007f43f  nop     dword ptr [rax+rax+00h]
0x14007f444  jmp     loc_14007F25B
0x14007f449  xor     edx, edx; Tag
0x14007f44b  call    cs:__imp_ExFreePoolWithTag
0x14007f452  nop     dword ptr [rax+rax+00h]
0x14007f457  mov     [rbx+1C0h], rbp
0x14007f45e  jmp     loc_14007F290
0x14007f463  xor     edx, edx; Tag
0x14007f465  call    cs:__imp_ExFreePoolWithTag
0x14007f46c  nop     dword ptr [rax+rax+00h]
0x14007f471  mov     [rbx+208h], rbp
0x14007f478  jmp     loc_14007F34F
0x14007f47d  mov     rcx, [rbx+58h]
0x14007f481  cmp     ecx, [rbx+50h]
0x14007f484  jl      loc_1402005A8
0x14007f48a  mov     rax, rcx
0x14007f48d  shr     rax, 20h
0x14007f491  cmp     eax, ecx
0x14007f493  jge     loc_1402005A8
0x14007f499  mov     rcx, r8; P
0x14007f49c  xor     edx, edx; Tag
0x14007f49e  call    cs:__imp_ExFreePoolWithTag
0x14007f4a5  nop     dword ptr [rax+rax+00h]
0x14007f4aa  jmp     loc_14007F2E1
0x140200530  lea     rcx, [rsi+40h]; ListHead
0x140200534  mov     rdx, r8; ListEntry
0x140200537  call    cs:__imp_ExpInterlockedPushEntrySList
0x14020053e  nop     dword ptr [rax+rax+00h]
0x140200543  nop
0x140200544  lock inc dword ptr [rsi+58h]
0x140200548  nop
0x140200549  jmp     loc_14007F15C
0x14020054e  lea     rcx, [rsi+40h]; ListHead
0x140200552  mov     rdx, r8; ListEntry
0x140200555  call    cs:__imp_ExpInterlockedPushEntrySList
0x14020055c  nop     dword ptr [rax+rax+00h]
0x140200561  nop
0x140200562  lock inc dword ptr [rsi+58h]
0x140200566  nop
0x140200567  jmp     loc_14007F1B1
0x14020056c  lea     rcx, [rsi+40h]; ListHead
0x140200570  mov     rdx, r8; ListEntry
0x140200573  call    cs:__imp_ExpInterlockedPushEntrySList
0x14020057a  nop     dword ptr [rax+rax+00h]
0x14020057f  nop
0x140200580  lock inc dword ptr [rsi+58h]
0x140200584  nop
0x140200585  jmp     loc_14007F206
0x14020058a  lea     rcx, [rsi+40h]; ListHead
0x14020058e  mov     rdx, r8; ListEntry
0x140200591  call    cs:__imp_ExpInterlockedPushEntrySList
0x140200598  nop     dword ptr [rax+rax+00h]
0x14020059d  nop
0x14020059e  lock inc dword ptr [rsi+58h]
0x1402005a2  nop
0x1402005a3  jmp     loc_14007F25B
0x1402005a8  lea     rcx, [rbx+40h]; ListHead
0x1402005ac  mov     rdx, r8; ListEntry
0x1402005af  call    cs:__imp_ExpInterlockedPushEntrySList
0x1402005b6  nop     dword ptr [rax+rax+00h]
0x1402005bb  nop
0x1402005bc  lock inc dword ptr [rbx+58h]
0x1402005c0  nop
0x1402005c1  jmp     loc_14007F2E1
```
