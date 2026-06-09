# SmsBindable::`scalar deleting destructor'(uint)

- ea: `0x14008bf10`
- end: `0x14008c29f`
- name: `??_GSmsBindable@@QEAAPEAXI@Z`
- size: `911`
- prototype: `void *__fastcall(PVOID P, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140083908`
- `0x14008a5e0`

## callees

- `0x14008bf10`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008c02b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008c080`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008c0d5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008c126`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008c02b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008c080`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008c0d5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008c126`
- `ntoskrnl!ExDeleteFastResource` at `0x14008bf22`
- `ntoskrnl!ExDeleteFastResource` at `0x14008bf22`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008c15a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008c16b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008c17c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008c18d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008c15a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008c16b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008c17c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14008c18d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140201345`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140201363`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140201381`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14020139f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140201345`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140201363`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140201381`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14020139f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008bf4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008bf76`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008bfa7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c19d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c1b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c1e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c214`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c246`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c278`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c28e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008bf4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008bf76`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008bfa7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c19d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c1b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c1e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c214`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c246`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c278`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c28e`

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
0x14008bf10  push    rbx
0x14008bf12  push    rbp
0x14008bf13  push    rsi
0x14008bf14  push    rdi
0x14008bf15  sub     rsp, 38h
0x14008bf19  mov     rbx, rcx
0x14008bf1c  mov     esi, edx
0x14008bf1e  add     rcx, 8
0x14008bf22  call    cs:__imp_ExDeleteFastResource
0x14008bf29  nop     dword ptr [rax+rax+00h]
0x14008bf2e  mov     rcx, [rbx+198h]; P
0x14008bf35  test    rcx, rcx
0x14008bf38  jnz     loc_14008C19B
0x14008bf3e  mov     rcx, [rbx+2C0h]; P
0x14008bf45  test    rcx, rcx
0x14008bf48  jz      short loc_14008BF58
0x14008bf4a  xor     edx, edx; Tag
0x14008bf4c  call    cs:__imp_ExFreePoolWithTag
0x14008bf53  nop     dword ptr [rax+rax+00h]
0x14008bf58  mov     rcx, [rbx+3C8h]; P
0x14008bf5f  test    rcx, rcx
0x14008bf62  jnz     loc_14008C1AE
0x14008bf68  mov     rcx, [rbx+3A8h]; P
0x14008bf6f  test    rcx, rcx
0x14008bf72  jz      short loc_14008BF82
0x14008bf74  xor     edx, edx; Tag
0x14008bf76  call    cs:__imp_ExFreePoolWithTag
0x14008bf7d  nop     dword ptr [rax+rax+00h]
0x14008bf82  xor     ebp, ebp
0x14008bf84  mov     [rbx+2C8h], ebp
0x14008bf8a  mov     [rbx+3B0h], ebp
0x14008bf90  test    byte ptr [rbx+378h], 1
0x14008bf97  jz      short loc_14008BFB3
0x14008bf99  mov     rcx, [rbx+370h]; P
0x14008bfa0  test    rcx, rcx
0x14008bfa3  jz      short loc_14008BFB3
0x14008bfa5  xor     edx, edx; Tag
0x14008bfa7  call    cs:__imp_ExFreePoolWithTag
0x14008bfae  nop     dword ptr [rax+rax+00h]
0x14008bfb3  lea     rax, [rbx+380h]
0x14008bfba  mov     dword ptr [rbx+37Ch], 20h ; ' '
0x14008bfc4  mov     [rbx+370h], rax
0x14008bfcb  xorps   xmm0, xmm0
0x14008bfce  mov     eax, [rsp+58h+var_34]
0x14008bfd2  mov     [rbx+364h], eax
0x14008bfd8  movups  xmmword ptr [rbx+350h], xmm0
0x14008bfdf  mov     [rbx+360h], ebp
0x14008bfe5  mov     [rbx+368h], rbp
0x14008bfec  mov     [rbx+378h], bpl
0x14008bff3  mov     r8, [rbx+310h]
0x14008bffa  test    r8, r8
0x14008bffd  jz      short loc_14008C048
0x14008bfff  mov     rdi, [r8-10h]
0x14008c003  add     r8, 0FFFFFFFFFFFFFFF0h
0x14008c007  test    rdi, rdi
0x14008c00a  jz      loc_14008C1DD
0x14008c010  cmp     [rdi+8], bpl
0x14008c014  jz      loc_14008C1C1
0x14008c01a  lea     rcx, [rdi+40h]; Lookaside
0x14008c01e  mov     rdx, r8; Entry
0x14008c021  cmp     [rdi+9], bpl
0x14008c025  jz      loc_14008C15A
0x14008c02b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008c032  nop     dword ptr [rax+rax+00h]
0x14008c037  mov     [rbx+310h], rbp
0x14008c03e  mov     dword ptr [rbx+318h], 0FFFFFFFFh
0x14008c048  mov     rax, [rbx+2D0h]
0x14008c04f  test    rax, rax
0x14008c052  jz      short loc_14008C09D
0x14008c054  mov     rdi, [rax-10h]
0x14008c058  lea     r8, [rax-10h]
0x14008c05c  test    rdi, rdi
0x14008c05f  jz      loc_14008C20F
0x14008c065  cmp     [rdi+8], bpl
0x14008c069  jz      loc_14008C1F3
0x14008c06f  lea     rcx, [rdi+40h]; Lookaside
0x14008c073  mov     rdx, r8; Entry
0x14008c076  cmp     [rdi+9], bpl
0x14008c07a  jz      loc_14008C16B
0x14008c080  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008c087  nop     dword ptr [rax+rax+00h]
0x14008c08c  mov     [rbx+2D0h], rbp
0x14008c093  mov     dword ptr [rbx+2D8h], 0FFFFFFFFh
0x14008c09d  mov     rax, [rbx+128h]
0x14008c0a4  test    rax, rax
0x14008c0a7  jz      short loc_14008C0F2
0x14008c0a9  mov     rdi, [rax-10h]
0x14008c0ad  lea     r8, [rax-10h]
0x14008c0b1  test    rdi, rdi
0x14008c0b4  jz      loc_14008C241
0x14008c0ba  cmp     [rdi+8], bpl
0x14008c0be  jz      loc_14008C225
0x14008c0c4  lea     rcx, [rdi+40h]; Lookaside
0x14008c0c8  mov     rdx, r8; Entry
0x14008c0cb  cmp     [rdi+9], bpl
0x14008c0cf  jz      loc_14008C17C
0x14008c0d5  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008c0dc  nop     dword ptr [rax+rax+00h]
0x14008c0e1  mov     [rbx+128h], rbp
0x14008c0e8  mov     dword ptr [rbx+130h], 0FFFFFFFFh
0x14008c0f2  mov     rax, [rbx+0E8h]
0x14008c0f9  test    rax, rax
0x14008c0fc  jz      short loc_14008C143
0x14008c0fe  mov     rdi, [rax-10h]
0x14008c102  lea     r8, [rax-10h]
0x14008c106  test    rdi, rdi
0x14008c109  jz      loc_14008C273
0x14008c10f  cmp     [rdi+8], bpl
0x14008c113  jz      loc_14008C257
0x14008c119  lea     rcx, [rdi+40h]; Lookaside
0x14008c11d  mov     rdx, r8; Entry
0x14008c120  cmp     [rdi+9], bpl
0x14008c124  jz      short loc_14008C18D
0x14008c126  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008c12d  nop     dword ptr [rax+rax+00h]
0x14008c132  mov     [rbx+0E8h], rbp
0x14008c139  mov     dword ptr [rbx+0F0h], 0FFFFFFFFh
0x14008c143  test    sil, 1
0x14008c147  jnz     loc_14008C289
0x14008c14d  mov     rax, rbx
0x14008c150  add     rsp, 38h
0x14008c154  pop     rdi
0x14008c155  pop     rsi
0x14008c156  pop     rbp
0x14008c157  pop     rbx
0x14008c158  retn
0x14008c15a  call    cs:__imp_ExFreeToPagedLookasideList
0x14008c161  nop     dword ptr [rax+rax+00h]
0x14008c166  jmp     loc_14008C037
0x14008c16b  call    cs:__imp_ExFreeToPagedLookasideList
0x14008c172  nop     dword ptr [rax+rax+00h]
0x14008c177  jmp     loc_14008C08C
0x14008c17c  call    cs:__imp_ExFreeToPagedLookasideList
0x14008c183  nop     dword ptr [rax+rax+00h]
0x14008c188  jmp     loc_14008C0E1
0x14008c18d  call    cs:__imp_ExFreeToPagedLookasideList
0x14008c194  nop     dword ptr [rax+rax+00h]
0x14008c199  jmp     short loc_14008C132
0x14008c19b  xor     edx, edx; Tag
0x14008c19d  call    cs:__imp_ExFreePoolWithTag
0x14008c1a4  nop     dword ptr [rax+rax+00h]
0x14008c1a9  jmp     loc_14008BF3E
0x14008c1ae  xor     edx, edx; Tag
0x14008c1b0  call    cs:__imp_ExFreePoolWithTag
0x14008c1b7  nop     dword ptr [rax+rax+00h]
0x14008c1bc  jmp     loc_14008BF68
0x14008c1c1  mov     rcx, [rdi+58h]
0x14008c1c5  cmp     ecx, [rdi+50h]
0x14008c1c8  jl      loc_14020133E
0x14008c1ce  mov     rax, rcx
0x14008c1d1  shr     rax, 20h
0x14008c1d5  cmp     eax, ecx
0x14008c1d7  jge     loc_14020133E
0x14008c1dd  xor     edx, edx; Tag
0x14008c1df  mov     rcx, r8; P
0x14008c1e2  call    cs:__imp_ExFreePoolWithTag
0x14008c1e9  nop     dword ptr [rax+rax+00h]
0x14008c1ee  jmp     loc_14008C037
0x14008c1f3  mov     rcx, [rdi+58h]
0x14008c1f7  cmp     ecx, [rdi+50h]
0x14008c1fa  jl      loc_14020135C
0x14008c200  mov     rax, rcx
0x14008c203  shr     rax, 20h
0x14008c207  cmp     eax, ecx
0x14008c209  jge     loc_14020135C
0x14008c20f  xor     edx, edx; Tag
0x14008c211  mov     rcx, r8; P
0x14008c214  call    cs:__imp_ExFreePoolWithTag
0x14008c21b  nop     dword ptr [rax+rax+00h]
0x14008c220  jmp     loc_14008C08C
0x14008c225  mov     rcx, [rdi+58h]
0x14008c229  cmp     ecx, [rdi+50h]
0x14008c22c  jl      loc_14020137A
0x14008c232  mov     rax, rcx
0x14008c235  shr     rax, 20h
0x14008c239  cmp     eax, ecx
0x14008c23b  jge     loc_14020137A
0x14008c241  xor     edx, edx; Tag
0x14008c243  mov     rcx, r8; P
0x14008c246  call    cs:__imp_ExFreePoolWithTag
0x14008c24d  nop     dword ptr [rax+rax+00h]
0x14008c252  jmp     loc_14008C0E1
0x14008c257  mov     rcx, [rdi+58h]
0x14008c25b  cmp     ecx, [rdi+50h]
0x14008c25e  jl      loc_140201398
0x14008c264  mov     rax, rcx
0x14008c267  shr     rax, 20h
0x14008c26b  cmp     eax, ecx
0x14008c26d  jge     loc_140201398
0x14008c273  xor     edx, edx; Tag
0x14008c275  mov     rcx, r8; P
0x14008c278  call    cs:__imp_ExFreePoolWithTag
0x14008c27f  nop     dword ptr [rax+rax+00h]
0x14008c284  jmp     loc_14008C132
0x14008c289  xor     edx, edx; Tag
0x14008c28b  mov     rcx, rbx; P
0x14008c28e  call    cs:__imp_ExFreePoolWithTag
0x14008c295  nop     dword ptr [rax+rax+00h]
0x14008c29a  jmp     loc_14008C14D
0x14020133e  lea     rcx, [rdi+40h]; ListHead
0x140201342  mov     rdx, r8; ListEntry
0x140201345  call    cs:__imp_ExpInterlockedPushEntrySList
0x14020134c  nop     dword ptr [rax+rax+00h]
0x140201351  nop
0x140201352  lock inc dword ptr [rdi+58h]
0x140201356  nop
0x140201357  jmp     loc_14008C037
0x14020135c  lea     rcx, [rdi+40h]; ListHead
0x140201360  mov     rdx, r8; ListEntry
0x140201363  call    cs:__imp_ExpInterlockedPushEntrySList
0x14020136a  nop     dword ptr [rax+rax+00h]
0x14020136f  nop
0x140201370  lock inc dword ptr [rdi+58h]
0x140201374  nop
0x140201375  jmp     loc_14008C08C
0x14020137a  lea     rcx, [rdi+40h]; ListHead
0x14020137e  mov     rdx, r8; ListEntry
0x140201381  call    cs:__imp_ExpInterlockedPushEntrySList
0x140201388  nop     dword ptr [rax+rax+00h]
0x14020138d  nop
0x14020138e  lock inc dword ptr [rdi+58h]
0x140201392  nop
0x140201393  jmp     loc_14008C0E1
0x140201398  lea     rcx, [rdi+40h]; ListHead
0x14020139c  mov     rdx, r8; ListEntry
0x14020139f  call    cs:__imp_ExpInterlockedPushEntrySList
0x1402013a6  nop     dword ptr [rax+rax+00h]
0x1402013ab  nop
0x1402013ac  lock inc dword ptr [rdi+58h]
0x1402013b0  nop
0x1402013b1  jmp     loc_14008C132
```
