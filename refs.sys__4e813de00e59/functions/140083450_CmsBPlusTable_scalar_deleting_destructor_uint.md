# CmsBPlusTable::`scalar deleting destructor'(uint)

- ea: `0x140083450`
- end: `0x140083902`
- name: `??_GCmsBPlusTable@@UEAAPEAXI@Z`
- size: `1202`
- prototype: `void *__fastcall(CmsBPlusTable *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140083450`
- `0x140083908`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400835a0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400835f5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008364a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008369f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008371d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400835a0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400835f5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008364a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008369f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008371d`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x1400836e7`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x1400836e7`
- `ntoskrnl!ExDeleteFastResource` at `0x140083499`
- `ntoskrnl!ExDeleteFastResource` at `0x140083499`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140083738`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140083753`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140083764`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140083775`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140083786`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140083738`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140083753`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140083764`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140083775`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140083786`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14020071d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14020073b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140200759`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140200777`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140200796`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14020071d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14020073b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140200759`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140200777`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140200796`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400834c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400834ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008351c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400837b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400837c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400837fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008382c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008385e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083890`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400838a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400838bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402007af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400834c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400834ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008351c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400837b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400837c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400837fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008382c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008385e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083890`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400838a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400838bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402007af`

## pseudocode

```c
CmsBPlusTable *__fastcall CmsBPlusTable::`scalar deleting destructor'(CmsBPlusTable *this, char a2)
{
  char v4; // al
  CmsBPlusTable *v5; // rdi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rsi
  struct _SLIST_ENTRY *v13; // r8
  struct _NPAGED_LOOKASIDE_LIST *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rsi
  struct _SLIST_ENTRY *v17; // r8
  struct _NPAGED_LOOKASIDE_LIST *v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rsi
  struct _SLIST_ENTRY *v21; // r8
  struct _NPAGED_LOOKASIDE_LIST *v22; // rcx
  __int64 v23; // r8
  __int64 v24; // rsi
  struct _SLIST_ENTRY *v25; // r8
  struct _NPAGED_LOOKASIDE_LIST *v26; // rcx
  void *v27; // rcx
  char *v28; // rcx
  __int64 v29; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v30; // rcx
  char *v31; // rdx
  void *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  CmsBPlusTable *v39; // rcx
  int v40; // [rsp+24h] [rbp-14h]

  CmsBPlusTable::~CmsBPlusTable(this);
  if ( (a2 & 1) == 0 )
    return this;
  v4 = *((_BYTE *)this + 12);
  if ( (v4 & 1) == 0 )
  {
    v39 = this;
    goto LABEL_79;
  }
  v5 = (CmsBPlusTable *)*((_QWORD *)this + 8);
  if ( (v4 & 8) != 0 )
  {
    ExDeleteFastResource((char *)this + 544);
    v6 = (void *)*((_QWORD *)this + 118);
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
    v7 = (void *)*((_QWORD *)this + 155);
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
    v8 = (void *)*((_QWORD *)this + 188);
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
    v9 = (void *)*((_QWORD *)this + 184);
    if ( v9 )
      ExFreePoolWithTag(v9, 0);
    *((_DWORD *)this + 312) = 0;
    *((_DWORD *)this + 370) = 0;
    if ( (*((_BYTE *)this + 1424) & 1) != 0 )
    {
      v10 = (void *)*((_QWORD *)this + 177);
      if ( v10 )
        ExFreePoolWithTag(v10, 0);
    }
    *((_DWORD *)this + 357) = 32;
    *((_QWORD *)this + 177) = (char *)this + 1432;
    *((_DWORD *)this + 351) = v40;
    *(_OWORD *)((char *)this + 1384) = 0;
    *((_DWORD *)this + 350) = 0;
    *((_QWORD *)this + 176) = 0;
    *((_BYTE *)this + 1424) = 0;
    v11 = *((_QWORD *)this + 165);
    if ( !v11 )
      goto LABEL_21;
    v12 = *(_QWORD *)(v11 - 16);
    v13 = (struct _SLIST_ENTRY *)(v11 - 16);
    if ( !v12 )
      goto LABEL_60;
    if ( *(_BYTE *)(v12 + 8) )
    {
      v14 = (struct _NPAGED_LOOKASIDE_LIST *)(v12 + 64);
      if ( *(_BYTE *)(v12 + 9) )
        ExFreeToNPagedLookasideList(v14, v13);
      else
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v14, v13);
      goto LABEL_20;
    }
    v34 = *(_QWORD *)(v12 + 88);
    if ( (int)v34 < *(_DWORD *)(v12 + 80) || SHIDWORD(v34) >= (int)v34 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v12 + 64), v13);
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 88));
    }
    else
    {
LABEL_60:
      ExFreePoolWithTag(v13, 0);
    }
LABEL_20:
    *((_QWORD *)this + 165) = 0;
    *((_DWORD *)this + 332) = -1;
LABEL_21:
    v15 = *((_QWORD *)this + 157);
    if ( !v15 )
    {
LABEL_27:
      v19 = *((_QWORD *)this + 104);
      if ( !v19 )
      {
LABEL_33:
        v23 = *((_QWORD *)this + 96);
        if ( !v23 )
          goto LABEL_39;
        v24 = *(_QWORD *)(v23 - 16);
        v25 = (struct _SLIST_ENTRY *)(v23 - 16);
        if ( !v24 )
          goto LABEL_69;
        if ( *(_BYTE *)(v24 + 8) )
        {
          v26 = (struct _NPAGED_LOOKASIDE_LIST *)(v24 + 64);
          if ( *(_BYTE *)(v24 + 9) )
            ExFreeToNPagedLookasideList(v26, v25);
          else
            ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v26, v25);
          goto LABEL_38;
        }
        v37 = *(_QWORD *)(v24 + 88);
        if ( (int)v37 < *(_DWORD *)(v24 + 80) || SHIDWORD(v37) >= (int)v37 )
        {
          ExpInterlockedPushEntrySList((PSLIST_HEADER)(v24 + 64), v25);
          _InterlockedIncrement((volatile signed __int32 *)(v24 + 88));
        }
        else
        {
LABEL_69:
          ExFreePoolWithTag(v25, 0);
        }
LABEL_38:
        *((_QWORD *)this + 96) = 0;
        *((_DWORD *)this + 194) = -1;
        goto LABEL_39;
      }
      v20 = *(_QWORD *)(v19 - 16);
      v21 = (struct _SLIST_ENTRY *)(v19 - 16);
      if ( !v20 )
        goto LABEL_66;
      if ( *(_BYTE *)(v20 + 8) )
      {
        v22 = (struct _NPAGED_LOOKASIDE_LIST *)(v20 + 64);
        if ( *(_BYTE *)(v20 + 9) )
          ExFreeToNPagedLookasideList(v22, v21);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v22, v21);
        goto LABEL_32;
      }
      v36 = *(_QWORD *)(v20 + 88);
      if ( (int)v36 < *(_DWORD *)(v20 + 80) || SHIDWORD(v36) >= (int)v36 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v20 + 64), v21);
        _InterlockedIncrement((volatile signed __int32 *)(v20 + 88));
      }
      else
      {
LABEL_66:
        ExFreePoolWithTag(v21, 0);
      }
LABEL_32:
      *((_QWORD *)this + 104) = 0;
      *((_DWORD *)this + 210) = -1;
      goto LABEL_33;
    }
    v16 = *(_QWORD *)(v15 - 16);
    v17 = (struct _SLIST_ENTRY *)(v15 - 16);
    if ( !v16 )
      goto LABEL_63;
    if ( *(_BYTE *)(v16 + 8) )
    {
      v18 = (struct _NPAGED_LOOKASIDE_LIST *)(v16 + 64);
      if ( *(_BYTE *)(v16 + 9) )
        ExFreeToNPagedLookasideList(v18, v17);
      else
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v18, v17);
      goto LABEL_26;
    }
    v35 = *(_QWORD *)(v16 + 88);
    if ( (int)v35 < *(_DWORD *)(v16 + 80) || SHIDWORD(v35) >= (int)v35 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v16 + 64), v17);
      _InterlockedIncrement((volatile signed __int32 *)(v16 + 88));
    }
    else
    {
LABEL_63:
      ExFreePoolWithTag(v17, 0);
    }
LABEL_26:
    *((_QWORD *)this + 157) = 0;
    *((_DWORD *)this + 316) = -1;
    goto LABEL_27;
  }
LABEL_39:
  if ( *((_QWORD *)this + 5) )
  {
    if ( this == v5 )
    {
      v33 = (void *)*((_QWORD *)this + 65);
      if ( v33 )
      {
        ExFreePoolWithTag(v33, 0);
        *((_QWORD *)this + 65) = 0;
      }
      v28 = (char *)this + 392;
    }
    else
    {
      v27 = (void *)*((_QWORD *)this + 56);
      if ( v27 )
      {
        ExFreePoolWithTag(v27, 0);
        *((_QWORD *)this + 56) = 0;
      }
      v28 = (char *)this + 320;
    }
    ExCleanupAutoExpandPushLock(v28);
  }
  v29 = *((_QWORD *)this - 2);
  if ( !v29 )
  {
LABEL_72:
    v39 = (CmsBPlusTable *)((char *)this - 16);
LABEL_79:
    ExFreePoolWithTag(v39, 0);
    return this;
  }
  if ( !*(_BYTE *)(v29 + 8) )
  {
    v38 = *(_QWORD *)(v29 + 88);
    if ( (int)v38 < *(_DWORD *)(v29 + 80) || SHIDWORD(v38) >= (int)v38 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v29 + 64), (PSLIST_ENTRY)this - 1);
      _InterlockedIncrement((volatile signed __int32 *)(v29 + 88));
      return this;
    }
    goto LABEL_72;
  }
  v30 = (struct _NPAGED_LOOKASIDE_LIST *)(v29 + 64);
  v31 = (char *)this - 16;
  if ( *(_BYTE *)(v29 + 9) )
  {
    ExFreeToNPagedLookasideList(v30, v31);
    return this;
  }
  ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v30, v31);
  return this;
}

```

## disassembly

```asm
0x140083450  mov     [rsp+arg_10], rbx
0x140083455  push    rdi
0x140083456  sub     rsp, 30h
0x14008345a  mov     edi, edx
0x14008345c  mov     rbx, rcx
0x14008345f  call    ??1CmsBPlusTable@@UEAA@XZ; CmsBPlusTable::~CmsBPlusTable(void)
0x140083464  test    dil, 1
0x140083468  jz      loc_140083729
0x14008346e  movzx   eax, byte ptr [rbx+0Ch]
0x140083472  test    al, 1
0x140083474  jz      loc_1400838FA
0x14008347a  mov     rdi, [rbx+40h]
0x14008347e  mov     [rsp+38h+arg_0], rbp
0x140083483  xor     ebp, ebp
0x140083485  test    al, 8
0x140083487  jz      loc_1400836C1
0x14008348d  lea     rcx, [rbx+220h]
0x140083494  mov     [rsp+38h+arg_8], rsi
0x140083499  call    cs:__imp_ExDeleteFastResource
0x1400834a0  nop     dword ptr [rax+rax+00h]
0x1400834a5  mov     rcx, [rbx+3B0h]; P
0x1400834ac  test    rcx, rcx
0x1400834af  jnz     loc_1400837B3
0x1400834b5  mov     rcx, [rbx+4D8h]; P
0x1400834bc  test    rcx, rcx
0x1400834bf  jz      short loc_1400834CF
0x1400834c1  xor     edx, edx; Tag
0x1400834c3  call    cs:__imp_ExFreePoolWithTag
0x1400834ca  nop     dword ptr [rax+rax+00h]
0x1400834cf  mov     rcx, [rbx+5E0h]; P
0x1400834d6  test    rcx, rcx
0x1400834d9  jnz     loc_1400837C6
0x1400834df  mov     rcx, [rbx+5C0h]; P
0x1400834e6  test    rcx, rcx
0x1400834e9  jz      short loc_1400834F9
0x1400834eb  xor     edx, edx; Tag
0x1400834ed  call    cs:__imp_ExFreePoolWithTag
0x1400834f4  nop     dword ptr [rax+rax+00h]
0x1400834f9  mov     [rbx+4E0h], ebp
0x1400834ff  mov     [rbx+5C8h], ebp
0x140083505  test    byte ptr [rbx+590h], 1
0x14008350c  jz      short loc_140083528
0x14008350e  mov     rcx, [rbx+588h]; P
0x140083515  test    rcx, rcx
0x140083518  jz      short loc_140083528
0x14008351a  xor     edx, edx; Tag
0x14008351c  call    cs:__imp_ExFreePoolWithTag
0x140083523  nop     dword ptr [rax+rax+00h]
0x140083528  lea     rax, [rbx+598h]
0x14008352f  mov     dword ptr [rbx+594h], 20h ; ' '
0x140083539  mov     [rbx+588h], rax
0x140083540  xorps   xmm0, xmm0
0x140083543  mov     eax, [rsp+38h+var_14]
0x140083547  mov     [rbx+57Ch], eax
0x14008354d  movups  xmmword ptr [rbx+568h], xmm0
0x140083554  mov     [rbx+578h], ebp
0x14008355a  mov     [rbx+580h], rbp
0x140083561  mov     [rbx+590h], bpl
0x140083568  mov     r8, [rbx+528h]
0x14008356f  test    r8, r8
0x140083572  jz      short loc_1400835BD
0x140083574  mov     rsi, [r8-10h]
0x140083578  add     r8, 0FFFFFFFFFFFFFFF0h
0x14008357c  test    rsi, rsi
0x14008357f  jz      loc_1400837F5
0x140083585  cmp     [rsi+8], bpl
0x140083589  jz      loc_1400837D9
0x14008358f  lea     rcx, [rsi+40h]; Lookaside
0x140083593  mov     rdx, r8; Entry
0x140083596  cmp     [rsi+9], bpl
0x14008359a  jz      loc_140083753
0x1400835a0  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400835a7  nop     dword ptr [rax+rax+00h]
0x1400835ac  mov     [rbx+528h], rbp
0x1400835b3  mov     dword ptr [rbx+530h], 0FFFFFFFFh
0x1400835bd  mov     r8, [rbx+4E8h]
0x1400835c4  test    r8, r8
0x1400835c7  jz      short loc_140083612
0x1400835c9  mov     rsi, [r8-10h]
0x1400835cd  add     r8, 0FFFFFFFFFFFFFFF0h
0x1400835d1  test    rsi, rsi
0x1400835d4  jz      loc_140083827
0x1400835da  cmp     [rsi+8], bpl
0x1400835de  jz      loc_14008380B
0x1400835e4  lea     rcx, [rsi+40h]; Lookaside
0x1400835e8  mov     rdx, r8; Entry
0x1400835eb  cmp     [rsi+9], bpl
0x1400835ef  jz      loc_140083764
0x1400835f5  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400835fc  nop     dword ptr [rax+rax+00h]
0x140083601  mov     [rbx+4E8h], rbp
0x140083608  mov     dword ptr [rbx+4F0h], 0FFFFFFFFh
0x140083612  mov     r8, [rbx+340h]
0x140083619  test    r8, r8
0x14008361c  jz      short loc_140083667
0x14008361e  mov     rsi, [r8-10h]
0x140083622  add     r8, 0FFFFFFFFFFFFFFF0h
0x140083626  test    rsi, rsi
0x140083629  jz      loc_140083859
0x14008362f  cmp     [rsi+8], bpl
0x140083633  jz      loc_14008383D
0x140083639  lea     rcx, [rsi+40h]; Lookaside
0x14008363d  mov     rdx, r8; Entry
0x140083640  cmp     [rsi+9], bpl
0x140083644  jz      loc_140083775
0x14008364a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140083651  nop     dword ptr [rax+rax+00h]
0x140083656  mov     [rbx+340h], rbp
0x14008365d  mov     dword ptr [rbx+348h], 0FFFFFFFFh
0x140083667  mov     r8, [rbx+300h]
0x14008366e  test    r8, r8
0x140083671  jz      short loc_1400836BC
0x140083673  mov     rsi, [r8-10h]
0x140083677  add     r8, 0FFFFFFFFFFFFFFF0h
0x14008367b  test    rsi, rsi
0x14008367e  jz      loc_14008388B
0x140083684  cmp     [rsi+8], bpl
0x140083688  jz      loc_14008386F
0x14008368e  lea     rcx, [rsi+40h]; Lookaside
0x140083692  mov     rdx, r8; Entry
0x140083695  cmp     [rsi+9], bpl
0x140083699  jz      loc_140083786
0x14008369f  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400836a6  nop     dword ptr [rax+rax+00h]
0x1400836ab  mov     [rbx+300h], rbp
0x1400836b2  mov     dword ptr [rbx+308h], 0FFFFFFFFh
0x1400836bc  mov     rsi, [rsp+38h+arg_8]
0x1400836c1  cmp     [rbx+28h], rbp
0x1400836c5  jz      short loc_1400836F3
0x1400836c7  cmp     rbx, rdi
0x1400836ca  jz      loc_140083797
0x1400836d0  mov     rcx, [rbx+1C0h]; P
0x1400836d7  test    rcx, rcx
0x1400836da  jnz     loc_1400838A1
0x1400836e0  lea     rcx, [rbx+140h]
0x1400836e7  call    cs:__imp_ExCleanupAutoExpandPushLock
0x1400836ee  nop     dword ptr [rax+rax+00h]
0x1400836f3  mov     rdi, [rbx-10h]
0x1400836f7  mov     rbp, [rsp+38h+arg_0]
0x1400836fc  test    rdi, rdi
0x1400836ff  jz      loc_1400838F1
0x140083705  cmp     byte ptr [rdi+8], 0
0x140083709  jz      loc_1400838D5
0x14008370f  cmp     byte ptr [rdi+9], 0
0x140083713  lea     rcx, [rdi+40h]; Lookaside
0x140083717  lea     rdx, [rbx-10h]; Entry
0x14008371b  jz      short loc_140083738
0x14008371d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140083724  nop     dword ptr [rax+rax+00h]
0x140083729  mov     rax, rbx
0x14008372c  mov     rbx, [rsp+38h+arg_10]
0x140083731  add     rsp, 30h
0x140083735  pop     rdi
0x140083736  retn
0x140083738  call    cs:__imp_ExFreeToPagedLookasideList
0x14008373f  nop     dword ptr [rax+rax+00h]
0x140083744  mov     rax, rbx
0x140083747  mov     rbx, [rsp+38h+arg_10]
0x14008374c  add     rsp, 30h
0x140083750  pop     rdi
0x140083751  retn
0x140083753  call    cs:__imp_ExFreeToPagedLookasideList
0x14008375a  nop     dword ptr [rax+rax+00h]
0x14008375f  jmp     loc_1400835AC
0x140083764  call    cs:__imp_ExFreeToPagedLookasideList
0x14008376b  nop     dword ptr [rax+rax+00h]
0x140083770  jmp     loc_140083601
0x140083775  call    cs:__imp_ExFreeToPagedLookasideList
0x14008377c  nop     dword ptr [rax+rax+00h]
0x140083781  jmp     loc_140083656
0x140083786  call    cs:__imp_ExFreeToPagedLookasideList
0x14008378d  nop     dword ptr [rax+rax+00h]
0x140083792  jmp     loc_1400836AB
0x140083797  mov     rcx, [rbx+208h]; P
0x14008379e  test    rcx, rcx
0x1400837a1  jnz     loc_1400838BB
0x1400837a7  lea     rcx, [rbx+188h]
0x1400837ae  jmp     loc_1400836E7
0x1400837b3  xor     edx, edx; Tag
0x1400837b5  call    cs:__imp_ExFreePoolWithTag
0x1400837bc  nop     dword ptr [rax+rax+00h]
0x1400837c1  jmp     loc_1400834B5
0x1400837c6  xor     edx, edx; Tag
0x1400837c8  call    cs:__imp_ExFreePoolWithTag
0x1400837cf  nop     dword ptr [rax+rax+00h]
0x1400837d4  jmp     loc_1400834DF
0x1400837d9  mov     rcx, [rsi+58h]
0x1400837dd  cmp     ecx, [rsi+50h]
0x1400837e0  jl      loc_140200716
0x1400837e6  mov     rax, rcx
0x1400837e9  shr     rax, 20h
0x1400837ed  cmp     eax, ecx
0x1400837ef  jge     loc_140200716
0x1400837f5  xor     edx, edx; Tag
0x1400837f7  mov     rcx, r8; P
0x1400837fa  call    cs:__imp_ExFreePoolWithTag
0x140083801  nop     dword ptr [rax+rax+00h]
0x140083806  jmp     loc_1400835AC
0x14008380b  mov     rcx, [rsi+58h]
0x14008380f  cmp     ecx, [rsi+50h]
0x140083812  jl      loc_140200734
0x140083818  mov     rax, rcx
0x14008381b  shr     rax, 20h
0x14008381f  cmp     eax, ecx
0x140083821  jge     loc_140200734
0x140083827  xor     edx, edx; Tag
0x140083829  mov     rcx, r8; P
0x14008382c  call    cs:__imp_ExFreePoolWithTag
0x140083833  nop     dword ptr [rax+rax+00h]
0x140083838  jmp     loc_140083601
0x14008383d  mov     rcx, [rsi+58h]
0x140083841  cmp     ecx, [rsi+50h]
0x140083844  jl      loc_140200752
0x14008384a  mov     rax, rcx
0x14008384d  shr     rax, 20h
0x140083851  cmp     eax, ecx
0x140083853  jge     loc_140200752
0x140083859  xor     edx, edx; Tag
0x14008385b  mov     rcx, r8; P
0x14008385e  call    cs:__imp_ExFreePoolWithTag
0x140083865  nop     dword ptr [rax+rax+00h]
0x14008386a  jmp     loc_140083656
0x14008386f  mov     rcx, [rsi+58h]
0x140083873  cmp     ecx, [rsi+50h]
0x140083876  jl      loc_140200770
0x14008387c  mov     rax, rcx
0x14008387f  shr     rax, 20h
0x140083883  cmp     eax, ecx
0x140083885  jge     loc_140200770
0x14008388b  xor     edx, edx; Tag
0x14008388d  mov     rcx, r8; P
0x140083890  call    cs:__imp_ExFreePoolWithTag
0x140083897  nop     dword ptr [rax+rax+00h]
0x14008389c  jmp     loc_1400836AB
0x1400838a1  xor     edx, edx; Tag
0x1400838a3  call    cs:__imp_ExFreePoolWithTag
0x1400838aa  nop     dword ptr [rax+rax+00h]
0x1400838af  mov     [rbx+1C0h], rbp
0x1400838b6  jmp     loc_1400836E0
0x1400838bb  xor     edx, edx; Tag
0x1400838bd  call    cs:__imp_ExFreePoolWithTag
0x1400838c4  nop     dword ptr [rax+rax+00h]
0x1400838c9  mov     [rbx+208h], rbp
0x1400838d0  jmp     loc_1400837A7
0x1400838d5  mov     rcx, [rdi+58h]
0x1400838d9  cmp     ecx, [rdi+50h]
0x1400838dc  jl      loc_14020078E
0x1400838e2  mov     rax, rcx
0x1400838e5  shr     rax, 20h
0x1400838e9  cmp     eax, ecx
0x1400838eb  jge     loc_14020078E
0x1400838f1  lea     rcx, [rbx-10h]; P
0x1400838f5  jmp     loc_1402007AD
0x1400838fa  mov     rcx, rbx
0x1400838fd  jmp     loc_1402007AD
0x140200716  lea     rcx, [rsi+40h]; ListHead
0x14020071a  mov     rdx, r8; ListEntry
0x14020071d  call    cs:__imp_ExpInterlockedPushEntrySList
0x140200724  nop     dword ptr [rax+rax+00h]
0x140200729  nop
0x14020072a  lock inc dword ptr [rsi+58h]
0x14020072e  nop
0x14020072f  jmp     loc_1400835AC
0x140200734  lea     rcx, [rsi+40h]; ListHead
0x140200738  mov     rdx, r8; ListEntry
0x14020073b  call    cs:__imp_ExpInterlockedPushEntrySList
0x140200742  nop     dword ptr [rax+rax+00h]
0x140200747  nop
0x140200748  lock inc dword ptr [rsi+58h]
0x14020074c  nop
0x14020074d  jmp     loc_140083601
0x140200752  lea     rcx, [rsi+40h]; ListHead
0x140200756  mov     rdx, r8; ListEntry
0x140200759  call    cs:__imp_ExpInterlockedPushEntrySList
0x140200760  nop     dword ptr [rax+rax+00h]
0x140200765  nop
0x140200766  lock inc dword ptr [rsi+58h]
0x14020076a  nop
0x14020076b  jmp     loc_140083656
0x140200770  lea     rcx, [rsi+40h]; ListHead
0x140200774  mov     rdx, r8; ListEntry
0x140200777  call    cs:__imp_ExpInterlockedPushEntrySList
0x14020077e  nop     dword ptr [rax+rax+00h]
0x140200783  nop
0x140200784  lock inc dword ptr [rsi+58h]
0x140200788  nop
0x140200789  jmp     loc_1400836AB
0x14020078e  lea     rcx, [rdi+40h]; ListHead
0x140200792  lea     rdx, [rbx-10h]; ListEntry
0x140200796  call    cs:__imp_ExpInterlockedPushEntrySList
0x14020079d  nop     dword ptr [rax+rax+00h]
0x1402007a2  nop
0x1402007a3  lock inc dword ptr [rdi+58h]
0x1402007a7  nop
0x1402007a8  jmp     loc_140083729
0x1402007ad  xor     edx, edx; Tag
0x1402007af  call    cs:__imp_ExFreePoolWithTag
0x1402007b6  nop     dword ptr [rax+rax+00h]
0x1402007bb  nop
0x1402007bc  jmp     loc_140083729
  ... truncated ...
```
