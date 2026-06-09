# SmsBindable::`scalar deleting destructor'(uint)

- ea: `0x140092400`
- end: `0x14009278f`
- name: `??_GSmsBindable@@QEAAPEAXI@Z`
- size: `911`
- prototype: `void *__fastcall(PVOID P, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14008b528`
- `0x140090bf0`

## callees

- `0x140092400`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14009251b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140092570`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400925c5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140092616`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14009251b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140092570`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400925c5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140092616`
- `ntoskrnl!ExDeleteFastResource` at `0x140092412`
- `ntoskrnl!ExDeleteFastResource` at `0x140092412`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14009264a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14009265b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14009266c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14009267d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14009264a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14009265b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14009266c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14009267d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f9779`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f9797`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f97b5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f97d3`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f9779`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f9797`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f97b5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f97d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009243c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140092466`
- `ntoskrnl!ExFreePoolWithTag` at `0x140092497`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009268d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400926a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400926d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140092704`
- `ntoskrnl!ExFreePoolWithTag` at `0x140092736`
- `ntoskrnl!ExFreePoolWithTag` at `0x140092768`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009277e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009243c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140092466`
- `ntoskrnl!ExFreePoolWithTag` at `0x140092497`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009268d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400926a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400926d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140092704`
- `ntoskrnl!ExFreePoolWithTag` at `0x140092736`
- `ntoskrnl!ExFreePoolWithTag` at `0x140092768`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009277e`

## pseudocode

```c
_QWORD *__fastcall SmsBindable::`scalar deleting destructor'(_QWORD *P, char a2)
{
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdi
  struct _SLIST_ENTRY *v11; // r8
  struct _NPAGED_LOOKASIDE_LIST *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdi
  struct _SLIST_ENTRY *v15; // r8
  struct _NPAGED_LOOKASIDE_LIST *v16; // rcx
  void *v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rdi
  struct _SLIST_ENTRY *v20; // r8
  struct _NPAGED_LOOKASIDE_LIST *v21; // rcx
  void *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rdi
  struct _SLIST_ENTRY *v25; // r8
  struct _NPAGED_LOOKASIDE_LIST *v26; // rcx
  void *v27; // rdx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33; // [rsp+24h] [rbp-34h]

  ExDeleteFastResource(P + 1);
  v4 = (void *)P[51];
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  v5 = (void *)P[88];
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  v6 = (void *)P[121];
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  v7 = (void *)P[117];
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  *((_DWORD *)P + 178) = 0;
  *((_DWORD *)P + 236) = 0;
  if ( (P[111] & 1) != 0 )
  {
    v8 = (void *)P[110];
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
  }
  *((_DWORD *)P + 223) = 32;
  P[110] = P + 112;
  *((_DWORD *)P + 217) = v33;
  *((_OWORD *)P + 53) = 0;
  *((_DWORD *)P + 216) = 0;
  P[109] = 0;
  *((_BYTE *)P + 888) = 0;
  v9 = P[98];
  if ( !v9 )
    goto LABEL_18;
  v10 = *(_QWORD *)(v9 - 16);
  v11 = (struct _SLIST_ENTRY *)(v9 - 16);
  if ( !v10 )
    goto LABEL_45;
  if ( *(_BYTE *)(v10 + 8) )
  {
    v12 = (struct _NPAGED_LOOKASIDE_LIST *)(v10 + 64);
    if ( *(_BYTE *)(v10 + 9) )
      ExFreeToNPagedLookasideList(v12, v11);
    else
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v12, v11);
    goto LABEL_17;
  }
  v29 = *(_QWORD *)(v10 + 88);
  if ( (int)v29 < *(_DWORD *)(v10 + 80) || SHIDWORD(v29) >= (int)v29 )
  {
    ExpInterlockedPushEntrySList((PSLIST_HEADER)(v10 + 64), v11);
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 88));
  }
  else
  {
LABEL_45:
    ExFreePoolWithTag(v11, 0);
  }
LABEL_17:
  P[98] = 0;
  *((_DWORD *)P + 198) = -1;
LABEL_18:
  v13 = P[90];
  if ( !v13 )
    goto LABEL_24;
  v14 = *(_QWORD *)(v13 - 16);
  v15 = (struct _SLIST_ENTRY *)(v13 - 16);
  if ( !v14 )
    goto LABEL_48;
  if ( *(_BYTE *)(v14 + 8) )
  {
    v16 = (struct _NPAGED_LOOKASIDE_LIST *)(v14 + 64);
    v17 = (void *)(v13 - 16);
    if ( *(_BYTE *)(v14 + 9) )
      ExFreeToNPagedLookasideList(v16, v17);
    else
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v16, v17);
    goto LABEL_23;
  }
  v30 = *(_QWORD *)(v14 + 88);
  if ( (int)v30 < *(_DWORD *)(v14 + 80) || SHIDWORD(v30) >= (int)v30 )
  {
    ExpInterlockedPushEntrySList((PSLIST_HEADER)(v14 + 64), v15);
    _InterlockedIncrement((volatile signed __int32 *)(v14 + 88));
  }
  else
  {
LABEL_48:
    ExFreePoolWithTag(v15, 0);
  }
LABEL_23:
  P[90] = 0;
  *((_DWORD *)P + 182) = -1;
LABEL_24:
  v18 = P[37];
  if ( v18 )
  {
    v19 = *(_QWORD *)(v18 - 16);
    v20 = (struct _SLIST_ENTRY *)(v18 - 16);
    if ( !v19 )
      goto LABEL_51;
    if ( *(_BYTE *)(v19 + 8) )
    {
      v21 = (struct _NPAGED_LOOKASIDE_LIST *)(v19 + 64);
      v22 = (void *)(v18 - 16);
      if ( *(_BYTE *)(v19 + 9) )
        ExFreeToNPagedLookasideList(v21, v22);
      else
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v21, v22);
      goto LABEL_29;
    }
    v31 = *(_QWORD *)(v19 + 88);
    if ( (int)v31 < *(_DWORD *)(v19 + 80) || SHIDWORD(v31) >= (int)v31 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v19 + 64), v20);
      _InterlockedIncrement((volatile signed __int32 *)(v19 + 88));
    }
    else
    {
LABEL_51:
      ExFreePoolWithTag(v20, 0);
    }
LABEL_29:
    P[37] = 0;
    *((_DWORD *)P + 76) = -1;
  }
  v23 = P[29];
  if ( !v23 )
    goto LABEL_36;
  v24 = *(_QWORD *)(v23 - 16);
  v25 = (struct _SLIST_ENTRY *)(v23 - 16);
  if ( !v24 )
    goto LABEL_54;
  if ( *(_BYTE *)(v24 + 8) )
  {
    v26 = (struct _NPAGED_LOOKASIDE_LIST *)(v24 + 64);
    v27 = (void *)(v23 - 16);
    if ( *(_BYTE *)(v24 + 9) )
      ExFreeToNPagedLookasideList(v26, v27);
    else
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v26, v27);
    goto LABEL_35;
  }
  v32 = *(_QWORD *)(v24 + 88);
  if ( (int)v32 < *(_DWORD *)(v24 + 80) || SHIDWORD(v32) >= (int)v32 )
  {
    ExpInterlockedPushEntrySList((PSLIST_HEADER)(v24 + 64), v25);
    _InterlockedIncrement((volatile signed __int32 *)(v24 + 88));
  }
  else
  {
LABEL_54:
    ExFreePoolWithTag(v25, 0);
  }
LABEL_35:
  P[29] = 0;
  *((_DWORD *)P + 60) = -1;
LABEL_36:
  if ( (a2 & 1) != 0 )
    ExFreePoolWithTag(P, 0);
  return P;
}

```

## disassembly

```asm
0x140092400  push    rbx
0x140092402  push    rbp
0x140092403  push    rsi
0x140092404  push    rdi
0x140092405  sub     rsp, 38h
0x140092409  mov     rbx, rcx
0x14009240c  mov     esi, edx
0x14009240e  add     rcx, 8
0x140092412  call    cs:__imp_ExDeleteFastResource
0x140092419  nop     dword ptr [rax+rax+00h]
0x14009241e  mov     rcx, [rbx+198h]; P
0x140092425  test    rcx, rcx
0x140092428  jnz     loc_14009268B
0x14009242e  mov     rcx, [rbx+2C0h]; P
0x140092435  test    rcx, rcx
0x140092438  jz      short loc_140092448
0x14009243a  xor     edx, edx; Tag
0x14009243c  call    cs:__imp_ExFreePoolWithTag
0x140092443  nop     dword ptr [rax+rax+00h]
0x140092448  mov     rcx, [rbx+3C8h]; P
0x14009244f  test    rcx, rcx
0x140092452  jnz     loc_14009269E
0x140092458  mov     rcx, [rbx+3A8h]; P
0x14009245f  test    rcx, rcx
0x140092462  jz      short loc_140092472
0x140092464  xor     edx, edx; Tag
0x140092466  call    cs:__imp_ExFreePoolWithTag
0x14009246d  nop     dword ptr [rax+rax+00h]
0x140092472  xor     ebp, ebp
0x140092474  mov     [rbx+2C8h], ebp
0x14009247a  mov     [rbx+3B0h], ebp
0x140092480  test    byte ptr [rbx+378h], 1
0x140092487  jz      short loc_1400924A3
0x140092489  mov     rcx, [rbx+370h]; P
0x140092490  test    rcx, rcx
0x140092493  jz      short loc_1400924A3
0x140092495  xor     edx, edx; Tag
0x140092497  call    cs:__imp_ExFreePoolWithTag
0x14009249e  nop     dword ptr [rax+rax+00h]
0x1400924a3  lea     rax, [rbx+380h]
0x1400924aa  mov     dword ptr [rbx+37Ch], 20h ; ' '
0x1400924b4  mov     [rbx+370h], rax
0x1400924bb  xorps   xmm0, xmm0
0x1400924be  mov     eax, [rsp+58h+var_34]
0x1400924c2  mov     [rbx+364h], eax
0x1400924c8  movups  xmmword ptr [rbx+350h], xmm0
0x1400924cf  mov     [rbx+360h], ebp
0x1400924d5  mov     [rbx+368h], rbp
0x1400924dc  mov     [rbx+378h], bpl
0x1400924e3  mov     r8, [rbx+310h]
0x1400924ea  test    r8, r8
0x1400924ed  jz      short loc_140092538
0x1400924ef  mov     rdi, [r8-10h]
0x1400924f3  add     r8, 0FFFFFFFFFFFFFFF0h
0x1400924f7  test    rdi, rdi
0x1400924fa  jz      loc_1400926CD
0x140092500  cmp     [rdi+8], bpl
0x140092504  jz      loc_1400926B1
0x14009250a  lea     rcx, [rdi+40h]; Lookaside
0x14009250e  mov     rdx, r8; Entry
0x140092511  cmp     [rdi+9], bpl
0x140092515  jz      loc_14009264A
0x14009251b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140092522  nop     dword ptr [rax+rax+00h]
0x140092527  mov     [rbx+310h], rbp
0x14009252e  mov     dword ptr [rbx+318h], 0FFFFFFFFh
0x140092538  mov     rax, [rbx+2D0h]
0x14009253f  test    rax, rax
0x140092542  jz      short loc_14009258D
0x140092544  mov     rdi, [rax-10h]
0x140092548  lea     r8, [rax-10h]
0x14009254c  test    rdi, rdi
0x14009254f  jz      loc_1400926FF
0x140092555  cmp     [rdi+8], bpl
0x140092559  jz      loc_1400926E3
0x14009255f  lea     rcx, [rdi+40h]; Lookaside
0x140092563  mov     rdx, r8; Entry
0x140092566  cmp     [rdi+9], bpl
0x14009256a  jz      loc_14009265B
0x140092570  call    cs:__imp_ExFreeToNPagedLookasideList
0x140092577  nop     dword ptr [rax+rax+00h]
0x14009257c  mov     [rbx+2D0h], rbp
0x140092583  mov     dword ptr [rbx+2D8h], 0FFFFFFFFh
0x14009258d  mov     rax, [rbx+128h]
0x140092594  test    rax, rax
0x140092597  jz      short loc_1400925E2
0x140092599  mov     rdi, [rax-10h]
0x14009259d  lea     r8, [rax-10h]
0x1400925a1  test    rdi, rdi
0x1400925a4  jz      loc_140092731
0x1400925aa  cmp     [rdi+8], bpl
0x1400925ae  jz      loc_140092715
0x1400925b4  lea     rcx, [rdi+40h]; Lookaside
0x1400925b8  mov     rdx, r8; Entry
0x1400925bb  cmp     [rdi+9], bpl
0x1400925bf  jz      loc_14009266C
0x1400925c5  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400925cc  nop     dword ptr [rax+rax+00h]
0x1400925d1  mov     [rbx+128h], rbp
0x1400925d8  mov     dword ptr [rbx+130h], 0FFFFFFFFh
0x1400925e2  mov     rax, [rbx+0E8h]
0x1400925e9  test    rax, rax
0x1400925ec  jz      short loc_140092633
0x1400925ee  mov     rdi, [rax-10h]
0x1400925f2  lea     r8, [rax-10h]
0x1400925f6  test    rdi, rdi
0x1400925f9  jz      loc_140092763
0x1400925ff  cmp     [rdi+8], bpl
0x140092603  jz      loc_140092747
0x140092609  lea     rcx, [rdi+40h]; Lookaside
0x14009260d  mov     rdx, r8; Entry
0x140092610  cmp     [rdi+9], bpl
0x140092614  jz      short loc_14009267D
0x140092616  call    cs:__imp_ExFreeToNPagedLookasideList
0x14009261d  nop     dword ptr [rax+rax+00h]
0x140092622  mov     [rbx+0E8h], rbp
0x140092629  mov     dword ptr [rbx+0F0h], 0FFFFFFFFh
0x140092633  test    sil, 1
0x140092637  jnz     loc_140092779
0x14009263d  mov     rax, rbx
0x140092640  add     rsp, 38h
0x140092644  pop     rdi
0x140092645  pop     rsi
0x140092646  pop     rbp
0x140092647  pop     rbx
0x140092648  retn
0x14009264a  call    cs:__imp_ExFreeToPagedLookasideList
0x140092651  nop     dword ptr [rax+rax+00h]
0x140092656  jmp     loc_140092527
0x14009265b  call    cs:__imp_ExFreeToPagedLookasideList
0x140092662  nop     dword ptr [rax+rax+00h]
0x140092667  jmp     loc_14009257C
0x14009266c  call    cs:__imp_ExFreeToPagedLookasideList
0x140092673  nop     dword ptr [rax+rax+00h]
0x140092678  jmp     loc_1400925D1
0x14009267d  call    cs:__imp_ExFreeToPagedLookasideList
0x140092684  nop     dword ptr [rax+rax+00h]
0x140092689  jmp     short loc_140092622
0x14009268b  xor     edx, edx; Tag
0x14009268d  call    cs:__imp_ExFreePoolWithTag
0x140092694  nop     dword ptr [rax+rax+00h]
0x140092699  jmp     loc_14009242E
0x14009269e  xor     edx, edx; Tag
0x1400926a0  call    cs:__imp_ExFreePoolWithTag
0x1400926a7  nop     dword ptr [rax+rax+00h]
0x1400926ac  jmp     loc_140092458
0x1400926b1  mov     rcx, [rdi+58h]
0x1400926b5  cmp     ecx, [rdi+50h]
0x1400926b8  jl      loc_1401F9772
0x1400926be  mov     rax, rcx
0x1400926c1  shr     rax, 20h
0x1400926c5  cmp     eax, ecx
0x1400926c7  jge     loc_1401F9772
0x1400926cd  xor     edx, edx; Tag
0x1400926cf  mov     rcx, r8; P
0x1400926d2  call    cs:__imp_ExFreePoolWithTag
0x1400926d9  nop     dword ptr [rax+rax+00h]
0x1400926de  jmp     loc_140092527
0x1400926e3  mov     rcx, [rdi+58h]
0x1400926e7  cmp     ecx, [rdi+50h]
0x1400926ea  jl      loc_1401F9790
0x1400926f0  mov     rax, rcx
0x1400926f3  shr     rax, 20h
0x1400926f7  cmp     eax, ecx
0x1400926f9  jge     loc_1401F9790
0x1400926ff  xor     edx, edx; Tag
0x140092701  mov     rcx, r8; P
0x140092704  call    cs:__imp_ExFreePoolWithTag
0x14009270b  nop     dword ptr [rax+rax+00h]
0x140092710  jmp     loc_14009257C
0x140092715  mov     rcx, [rdi+58h]
0x140092719  cmp     ecx, [rdi+50h]
0x14009271c  jl      loc_1401F97AE
0x140092722  mov     rax, rcx
0x140092725  shr     rax, 20h
0x140092729  cmp     eax, ecx
0x14009272b  jge     loc_1401F97AE
0x140092731  xor     edx, edx; Tag
0x140092733  mov     rcx, r8; P
0x140092736  call    cs:__imp_ExFreePoolWithTag
0x14009273d  nop     dword ptr [rax+rax+00h]
0x140092742  jmp     loc_1400925D1
0x140092747  mov     rcx, [rdi+58h]
0x14009274b  cmp     ecx, [rdi+50h]
0x14009274e  jl      loc_1401F97CC
0x140092754  mov     rax, rcx
0x140092757  shr     rax, 20h
0x14009275b  cmp     eax, ecx
0x14009275d  jge     loc_1401F97CC
0x140092763  xor     edx, edx; Tag
0x140092765  mov     rcx, r8; P
0x140092768  call    cs:__imp_ExFreePoolWithTag
0x14009276f  nop     dword ptr [rax+rax+00h]
0x140092774  jmp     loc_140092622
0x140092779  xor     edx, edx; Tag
0x14009277b  mov     rcx, rbx; P
0x14009277e  call    cs:__imp_ExFreePoolWithTag
0x140092785  nop     dword ptr [rax+rax+00h]
0x14009278a  jmp     loc_14009263D
0x1401f9772  lea     rcx, [rdi+40h]; ListHead
0x1401f9776  mov     rdx, r8; ListEntry
0x1401f9779  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f9780  nop     dword ptr [rax+rax+00h]
0x1401f9785  nop
0x1401f9786  lock inc dword ptr [rdi+58h]
0x1401f978a  nop
0x1401f978b  jmp     loc_140092527
0x1401f9790  lea     rcx, [rdi+40h]; ListHead
0x1401f9794  mov     rdx, r8; ListEntry
0x1401f9797  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f979e  nop     dword ptr [rax+rax+00h]
0x1401f97a3  nop
0x1401f97a4  lock inc dword ptr [rdi+58h]
0x1401f97a8  nop
0x1401f97a9  jmp     loc_14009257C
0x1401f97ae  lea     rcx, [rdi+40h]; ListHead
0x1401f97b2  mov     rdx, r8; ListEntry
0x1401f97b5  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f97bc  nop     dword ptr [rax+rax+00h]
0x1401f97c1  nop
0x1401f97c2  lock inc dword ptr [rdi+58h]
0x1401f97c6  nop
0x1401f97c7  jmp     loc_1400925D1
0x1401f97cc  lea     rcx, [rdi+40h]; ListHead
0x1401f97d0  mov     rdx, r8; ListEntry
0x1401f97d3  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f97da  nop     dword ptr [rax+rax+00h]
0x1401f97df  nop
0x1401f97e0  lock inc dword ptr [rdi+58h]
0x1401f97e4  nop
0x1401f97e5  jmp     loc_140092622
```
