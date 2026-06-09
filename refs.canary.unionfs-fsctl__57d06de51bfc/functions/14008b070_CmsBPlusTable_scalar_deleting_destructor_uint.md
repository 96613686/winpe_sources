# CmsBPlusTable::`scalar deleting destructor'(uint)

- ea: `0x14008b070`
- end: `0x14008b522`
- name: `??_GCmsBPlusTable@@UEAAPEAXI@Z`
- size: `1202`
- prototype: `void *__fastcall(CmsBPlusTable *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x14008b070`
- `0x14008b528`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008b1c0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008b215`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008b26a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008b2bf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008b33d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008b1c0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008b215`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008b26a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008b2bf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008b33d`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14008b307`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14008b307`
- `ntoskrnl!ExDeleteFastResource` at `0x14008b0b9`
- `ntoskrnl!ExDeleteFastResource` at `0x14008b0b9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008b358`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008b373`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008b384`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008b395`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008b3a6`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008b358`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008b373`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008b384`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008b395`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008b3a6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8e4d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8e6b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8e89`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8ea7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8ec6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8e4d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8e6b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8e89`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8ea7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f8ec6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b0e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b10d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b13c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b3d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b3e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b41a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b44c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b47e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b4b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b4c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b4dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f8edf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b0e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b10d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b13c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b3d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b3e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b41a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b44c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b47e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b4b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b4c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b4dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f8edf`

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
0x14008b070  mov     [rsp+arg_10], rbx
0x14008b075  push    rdi
0x14008b076  sub     rsp, 30h
0x14008b07a  mov     edi, edx
0x14008b07c  mov     rbx, rcx
0x14008b07f  call    ??1CmsBPlusTable@@UEAA@XZ; CmsBPlusTable::~CmsBPlusTable(void)
0x14008b084  test    dil, 1
0x14008b088  jz      loc_14008B349
0x14008b08e  movzx   eax, byte ptr [rbx+0Ch]
0x14008b092  test    al, 1
0x14008b094  jz      loc_14008B51A
0x14008b09a  mov     rdi, [rbx+40h]
0x14008b09e  mov     [rsp+38h+arg_0], rbp
0x14008b0a3  xor     ebp, ebp
0x14008b0a5  test    al, 8
0x14008b0a7  jz      loc_14008B2E1
0x14008b0ad  lea     rcx, [rbx+220h]
0x14008b0b4  mov     [rsp+38h+arg_8], rsi
0x14008b0b9  call    cs:__imp_ExDeleteFastResource
0x14008b0c0  nop     dword ptr [rax+rax+00h]
0x14008b0c5  mov     rcx, [rbx+3B0h]; P
0x14008b0cc  test    rcx, rcx
0x14008b0cf  jnz     loc_14008B3D3
0x14008b0d5  mov     rcx, [rbx+4D8h]; P
0x14008b0dc  test    rcx, rcx
0x14008b0df  jz      short loc_14008B0EF
0x14008b0e1  xor     edx, edx; Tag
0x14008b0e3  call    cs:__imp_ExFreePoolWithTag
0x14008b0ea  nop     dword ptr [rax+rax+00h]
0x14008b0ef  mov     rcx, [rbx+5E0h]; P
0x14008b0f6  test    rcx, rcx
0x14008b0f9  jnz     loc_14008B3E6
0x14008b0ff  mov     rcx, [rbx+5C0h]; P
0x14008b106  test    rcx, rcx
0x14008b109  jz      short loc_14008B119
0x14008b10b  xor     edx, edx; Tag
0x14008b10d  call    cs:__imp_ExFreePoolWithTag
0x14008b114  nop     dword ptr [rax+rax+00h]
0x14008b119  mov     [rbx+4E0h], ebp
0x14008b11f  mov     [rbx+5C8h], ebp
0x14008b125  test    byte ptr [rbx+590h], 1
0x14008b12c  jz      short loc_14008B148
0x14008b12e  mov     rcx, [rbx+588h]; P
0x14008b135  test    rcx, rcx
0x14008b138  jz      short loc_14008B148
0x14008b13a  xor     edx, edx; Tag
0x14008b13c  call    cs:__imp_ExFreePoolWithTag
0x14008b143  nop     dword ptr [rax+rax+00h]
0x14008b148  lea     rax, [rbx+598h]
0x14008b14f  mov     dword ptr [rbx+594h], 20h ; ' '
0x14008b159  mov     [rbx+588h], rax
0x14008b160  xorps   xmm0, xmm0
0x14008b163  mov     eax, [rsp+38h+var_14]
0x14008b167  mov     [rbx+57Ch], eax
0x14008b16d  movups  xmmword ptr [rbx+568h], xmm0
0x14008b174  mov     [rbx+578h], ebp
0x14008b17a  mov     [rbx+580h], rbp
0x14008b181  mov     [rbx+590h], bpl
0x14008b188  mov     r8, [rbx+528h]
0x14008b18f  test    r8, r8
0x14008b192  jz      short loc_14008B1DD
0x14008b194  mov     rsi, [r8-10h]
0x14008b198  add     r8, 0FFFFFFFFFFFFFFF0h
0x14008b19c  test    rsi, rsi
0x14008b19f  jz      loc_14008B415
0x14008b1a5  cmp     [rsi+8], bpl
0x14008b1a9  jz      loc_14008B3F9
0x14008b1af  lea     rcx, [rsi+40h]; Lookaside
0x14008b1b3  mov     rdx, r8; Entry
0x14008b1b6  cmp     [rsi+9], bpl
0x14008b1ba  jz      loc_14008B373
0x14008b1c0  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008b1c7  nop     dword ptr [rax+rax+00h]
0x14008b1cc  mov     [rbx+528h], rbp
0x14008b1d3  mov     dword ptr [rbx+530h], 0FFFFFFFFh
0x14008b1dd  mov     r8, [rbx+4E8h]
0x14008b1e4  test    r8, r8
0x14008b1e7  jz      short loc_14008B232
0x14008b1e9  mov     rsi, [r8-10h]
0x14008b1ed  add     r8, 0FFFFFFFFFFFFFFF0h
0x14008b1f1  test    rsi, rsi
0x14008b1f4  jz      loc_14008B447
0x14008b1fa  cmp     [rsi+8], bpl
0x14008b1fe  jz      loc_14008B42B
0x14008b204  lea     rcx, [rsi+40h]; Lookaside
0x14008b208  mov     rdx, r8; Entry
0x14008b20b  cmp     [rsi+9], bpl
0x14008b20f  jz      loc_14008B384
0x14008b215  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008b21c  nop     dword ptr [rax+rax+00h]
0x14008b221  mov     [rbx+4E8h], rbp
0x14008b228  mov     dword ptr [rbx+4F0h], 0FFFFFFFFh
0x14008b232  mov     r8, [rbx+340h]
0x14008b239  test    r8, r8
0x14008b23c  jz      short loc_14008B287
0x14008b23e  mov     rsi, [r8-10h]
0x14008b242  add     r8, 0FFFFFFFFFFFFFFF0h
0x14008b246  test    rsi, rsi
0x14008b249  jz      loc_14008B479
0x14008b24f  cmp     [rsi+8], bpl
0x14008b253  jz      loc_14008B45D
0x14008b259  lea     rcx, [rsi+40h]; Lookaside
0x14008b25d  mov     rdx, r8; Entry
0x14008b260  cmp     [rsi+9], bpl
0x14008b264  jz      loc_14008B395
0x14008b26a  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008b271  nop     dword ptr [rax+rax+00h]
0x14008b276  mov     [rbx+340h], rbp
0x14008b27d  mov     dword ptr [rbx+348h], 0FFFFFFFFh
0x14008b287  mov     r8, [rbx+300h]
0x14008b28e  test    r8, r8
0x14008b291  jz      short loc_14008B2DC
0x14008b293  mov     rsi, [r8-10h]
0x14008b297  add     r8, 0FFFFFFFFFFFFFFF0h
0x14008b29b  test    rsi, rsi
0x14008b29e  jz      loc_14008B4AB
0x14008b2a4  cmp     [rsi+8], bpl
0x14008b2a8  jz      loc_14008B48F
0x14008b2ae  lea     rcx, [rsi+40h]; Lookaside
0x14008b2b2  mov     rdx, r8; Entry
0x14008b2b5  cmp     [rsi+9], bpl
0x14008b2b9  jz      loc_14008B3A6
0x14008b2bf  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008b2c6  nop     dword ptr [rax+rax+00h]
0x14008b2cb  mov     [rbx+300h], rbp
0x14008b2d2  mov     dword ptr [rbx+308h], 0FFFFFFFFh
0x14008b2dc  mov     rsi, [rsp+38h+arg_8]
0x14008b2e1  cmp     [rbx+28h], rbp
0x14008b2e5  jz      short loc_14008B313
0x14008b2e7  cmp     rbx, rdi
0x14008b2ea  jz      loc_14008B3B7
0x14008b2f0  mov     rcx, [rbx+1C0h]; P
0x14008b2f7  test    rcx, rcx
0x14008b2fa  jnz     loc_14008B4C1
0x14008b300  lea     rcx, [rbx+140h]
0x14008b307  call    cs:__imp_ExCleanupAutoExpandPushLock
0x14008b30e  nop     dword ptr [rax+rax+00h]
0x14008b313  mov     rdi, [rbx-10h]
0x14008b317  mov     rbp, [rsp+38h+arg_0]
0x14008b31c  test    rdi, rdi
0x14008b31f  jz      loc_14008B511
0x14008b325  cmp     byte ptr [rdi+8], 0
0x14008b329  jz      loc_14008B4F5
0x14008b32f  cmp     byte ptr [rdi+9], 0
0x14008b333  lea     rcx, [rdi+40h]; Lookaside
0x14008b337  lea     rdx, [rbx-10h]; Entry
0x14008b33b  jz      short loc_14008B358
0x14008b33d  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008b344  nop     dword ptr [rax+rax+00h]
0x14008b349  mov     rax, rbx
0x14008b34c  mov     rbx, [rsp+38h+arg_10]
0x14008b351  add     rsp, 30h
0x14008b355  pop     rdi
0x14008b356  retn
0x14008b358  call    cs:__imp_ExFreeToPagedLookasideList
0x14008b35f  nop     dword ptr [rax+rax+00h]
0x14008b364  mov     rax, rbx
0x14008b367  mov     rbx, [rsp+38h+arg_10]
0x14008b36c  add     rsp, 30h
0x14008b370  pop     rdi
0x14008b371  retn
0x14008b373  call    cs:__imp_ExFreeToPagedLookasideList
0x14008b37a  nop     dword ptr [rax+rax+00h]
0x14008b37f  jmp     loc_14008B1CC
0x14008b384  call    cs:__imp_ExFreeToPagedLookasideList
0x14008b38b  nop     dword ptr [rax+rax+00h]
0x14008b390  jmp     loc_14008B221
0x14008b395  call    cs:__imp_ExFreeToPagedLookasideList
0x14008b39c  nop     dword ptr [rax+rax+00h]
0x14008b3a1  jmp     loc_14008B276
0x14008b3a6  call    cs:__imp_ExFreeToPagedLookasideList
0x14008b3ad  nop     dword ptr [rax+rax+00h]
0x14008b3b2  jmp     loc_14008B2CB
0x14008b3b7  mov     rcx, [rbx+208h]; P
0x14008b3be  test    rcx, rcx
0x14008b3c1  jnz     loc_14008B4DB
0x14008b3c7  lea     rcx, [rbx+188h]
0x14008b3ce  jmp     loc_14008B307
0x14008b3d3  xor     edx, edx; Tag
0x14008b3d5  call    cs:__imp_ExFreePoolWithTag
0x14008b3dc  nop     dword ptr [rax+rax+00h]
0x14008b3e1  jmp     loc_14008B0D5
0x14008b3e6  xor     edx, edx; Tag
0x14008b3e8  call    cs:__imp_ExFreePoolWithTag
0x14008b3ef  nop     dword ptr [rax+rax+00h]
0x14008b3f4  jmp     loc_14008B0FF
0x14008b3f9  mov     rcx, [rsi+58h]
0x14008b3fd  cmp     ecx, [rsi+50h]
0x14008b400  jl      loc_1401F8E46
0x14008b406  mov     rax, rcx
0x14008b409  shr     rax, 20h
0x14008b40d  cmp     eax, ecx
0x14008b40f  jge     loc_1401F8E46
0x14008b415  xor     edx, edx; Tag
0x14008b417  mov     rcx, r8; P
0x14008b41a  call    cs:__imp_ExFreePoolWithTag
0x14008b421  nop     dword ptr [rax+rax+00h]
0x14008b426  jmp     loc_14008B1CC
0x14008b42b  mov     rcx, [rsi+58h]
0x14008b42f  cmp     ecx, [rsi+50h]
0x14008b432  jl      loc_1401F8E64
0x14008b438  mov     rax, rcx
0x14008b43b  shr     rax, 20h
0x14008b43f  cmp     eax, ecx
0x14008b441  jge     loc_1401F8E64
0x14008b447  xor     edx, edx; Tag
0x14008b449  mov     rcx, r8; P
0x14008b44c  call    cs:__imp_ExFreePoolWithTag
0x14008b453  nop     dword ptr [rax+rax+00h]
0x14008b458  jmp     loc_14008B221
0x14008b45d  mov     rcx, [rsi+58h]
0x14008b461  cmp     ecx, [rsi+50h]
0x14008b464  jl      loc_1401F8E82
0x14008b46a  mov     rax, rcx
0x14008b46d  shr     rax, 20h
0x14008b471  cmp     eax, ecx
0x14008b473  jge     loc_1401F8E82
0x14008b479  xor     edx, edx; Tag
0x14008b47b  mov     rcx, r8; P
0x14008b47e  call    cs:__imp_ExFreePoolWithTag
0x14008b485  nop     dword ptr [rax+rax+00h]
0x14008b48a  jmp     loc_14008B276
0x14008b48f  mov     rcx, [rsi+58h]
0x14008b493  cmp     ecx, [rsi+50h]
0x14008b496  jl      loc_1401F8EA0
0x14008b49c  mov     rax, rcx
0x14008b49f  shr     rax, 20h
0x14008b4a3  cmp     eax, ecx
0x14008b4a5  jge     loc_1401F8EA0
0x14008b4ab  xor     edx, edx; Tag
0x14008b4ad  mov     rcx, r8; P
0x14008b4b0  call    cs:__imp_ExFreePoolWithTag
0x14008b4b7  nop     dword ptr [rax+rax+00h]
0x14008b4bc  jmp     loc_14008B2CB
0x14008b4c1  xor     edx, edx; Tag
0x14008b4c3  call    cs:__imp_ExFreePoolWithTag
0x14008b4ca  nop     dword ptr [rax+rax+00h]
0x14008b4cf  mov     [rbx+1C0h], rbp
0x14008b4d6  jmp     loc_14008B300
0x14008b4db  xor     edx, edx; Tag
0x14008b4dd  call    cs:__imp_ExFreePoolWithTag
0x14008b4e4  nop     dword ptr [rax+rax+00h]
0x14008b4e9  mov     [rbx+208h], rbp
0x14008b4f0  jmp     loc_14008B3C7
0x14008b4f5  mov     rcx, [rdi+58h]
0x14008b4f9  cmp     ecx, [rdi+50h]
0x14008b4fc  jl      loc_1401F8EBE
0x14008b502  mov     rax, rcx
0x14008b505  shr     rax, 20h
0x14008b509  cmp     eax, ecx
0x14008b50b  jge     loc_1401F8EBE
0x14008b511  lea     rcx, [rbx-10h]; P
0x14008b515  jmp     loc_1401F8EDD
0x14008b51a  mov     rcx, rbx
0x14008b51d  jmp     loc_1401F8EDD
0x1401f8e46  lea     rcx, [rsi+40h]; ListHead
0x1401f8e4a  mov     rdx, r8; ListEntry
0x1401f8e4d  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f8e54  nop     dword ptr [rax+rax+00h]
0x1401f8e59  nop
0x1401f8e5a  lock inc dword ptr [rsi+58h]
0x1401f8e5e  nop
0x1401f8e5f  jmp     loc_14008B1CC
0x1401f8e64  lea     rcx, [rsi+40h]; ListHead
0x1401f8e68  mov     rdx, r8; ListEntry
0x1401f8e6b  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f8e72  nop     dword ptr [rax+rax+00h]
0x1401f8e77  nop
0x1401f8e78  lock inc dword ptr [rsi+58h]
0x1401f8e7c  nop
0x1401f8e7d  jmp     loc_14008B221
0x1401f8e82  lea     rcx, [rsi+40h]; ListHead
0x1401f8e86  mov     rdx, r8; ListEntry
0x1401f8e89  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f8e90  nop     dword ptr [rax+rax+00h]
0x1401f8e95  nop
0x1401f8e96  lock inc dword ptr [rsi+58h]
0x1401f8e9a  nop
0x1401f8e9b  jmp     loc_14008B276
0x1401f8ea0  lea     rcx, [rsi+40h]; ListHead
0x1401f8ea4  mov     rdx, r8; ListEntry
0x1401f8ea7  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f8eae  nop     dword ptr [rax+rax+00h]
0x1401f8eb3  nop
0x1401f8eb4  lock inc dword ptr [rsi+58h]
0x1401f8eb8  nop
0x1401f8eb9  jmp     loc_14008B2CB
0x1401f8ebe  lea     rcx, [rdi+40h]; ListHead
0x1401f8ec2  lea     rdx, [rbx-10h]; ListEntry
0x1401f8ec6  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f8ecd  nop     dword ptr [rax+rax+00h]
0x1401f8ed2  nop
0x1401f8ed3  lock inc dword ptr [rdi+58h]
0x1401f8ed7  nop
0x1401f8ed8  jmp     loc_14008B349
0x1401f8edd  xor     edx, edx; Tag
0x1401f8edf  call    cs:__imp_ExFreePoolWithTag
0x1401f8ee6  nop     dword ptr [rax+rax+00h]
0x1401f8eeb  nop
0x1401f8eec  jmp     loc_14008B349
  ... truncated ...
```
