# CmsAvlTableLite::AddToIndexEx(CmsTransactionCore *,SmsInternalPropertyDef const *,_CmsRow *,_SmsQuickIndex *,_SmsPreAllocatedRow *)

- ea: `0x140085f10`
- end: `0x14008666b`
- name: `?AddToIndexEx@CmsAvlTableLite@@QEAAJPEAVCmsTransactionCore@@PEBUSmsInternalPropertyDef@@PEAU_CmsRow@@PEAU_SmsQuickIndex@@PEAU_SmsPreAllocatedRow@@@Z`
- size: `1883`
- prototype: `__int64 __fastcall(CmsAvlTableLite *__hidden this, struct CmsTransactionCore *, const struct SmsInternalPropertyDef *, struct _CmsRow *, struct _SmsQuickIndex *, struct _SmsPreAllocatedRow *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140073080`
- `0x1400855e0`
- `0x14009a230`
- `0x14015fb0c`

## callees

- `0x140075200`
- `0x140075eb0`
- `0x140085e10`
- `0x140085f10`
- `0x1400c8574`
- `0x1401e9dc0`
- `0x1401e9e40`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140086539`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140086571`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140086539`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140086571`
- `ntoskrnl!ExAllocatePool2` at `0x1400862a7`
- `ntoskrnl!ExAllocatePool2` at `0x140086371`
- `ntoskrnl!ExAllocatePool2` at `0x1400863e8`
- `ntoskrnl!ExAllocatePool2` at `0x1400862a7`
- `ntoskrnl!ExAllocatePool2` at `0x140086371`
- `ntoskrnl!ExAllocatePool2` at `0x1400863e8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140086265`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008633f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140086265`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008633f`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f81e6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f81f8`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f81e6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f81f8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140086553`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008658c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140086553`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008658c`

## string_xrefs

- `0x1401f820a`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsAvlTableLite::AddToIndexEx(
        CmsAvlTableLite *this,
        struct CmsTransactionCore *a2,
        const struct SmsInternalPropertyDef *a3,
        unsigned __int64 a4,
        struct _SmsQuickIndex *a5,
        struct _RTL_AVL_ENTRY **a6)
{
  struct _SmsPreAllocatedRow *v6; // rsi
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // r15
  CmsAvlTableLite *v11; // r13
  __int16 v12; // r12
  struct _RTL_AVL_ENTRY *v13; // r15
  unsigned int v14; // r14d
  int v15; // r8d
  unsigned int v16; // edx
  unsigned int v17; // eax
  unsigned __int8 v18; // dl
  char *v19; // rcx
  char *v20; // rcx
  char *v21; // rax
  __int64 v22; // rcx
  struct _RTL_AVL_ENTRY **v23; // rdx
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rax
  __int64 v26; // rcx
  struct CmsTransactionCore *v27; // rdx
  int v28; // eax
  _QWORD *v30; // rsi
  _OWORD *v31; // rax
  unsigned __int64 v32; // rdx
  unsigned __int64 *v33; // rax
  int v34; // r13d
  unsigned int v35; // eax
  unsigned __int64 v36; // rsi
  unsigned int *v37; // r13
  unsigned __int64 v38; // rdx
  __int64 Pool2; // rax
  _WORD *v40; // r14
  unsigned __int64 v41; // rdx
  unsigned __int64 *v42; // rax
  __int64 v43; // r12
  unsigned __int64 v44; // rdx
  __int64 v45; // rax
  int v46; // ecx
  int v47; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v48; // rcx
  _WORD *v49; // rax
  struct _NPAGED_LOOKASIDE_LIST *v50; // rcx
  _WORD *v51; // rax
  int NodeOrParentIn; // eax
  unsigned __int64 i; // rdx
  bool v54; // zf
  char v55; // cl
  char v56; // al
  _QWORD v57[9]; // [rsp+30h] [rbp-48h] BYREF
  int v59; // [rsp+98h] [rbp+20h]
  __int16 v60; // [rsp+98h] [rbp+20h]
  __int64 v61; // [rsp+98h] [rbp+20h]
  unsigned __int8 v62; // [rsp+A8h] [rbp+30h]
  struct _SmsPreAllocatedRow *v63; // [rsp+A8h] [rbp+30h]

  v6 = (struct _SmsPreAllocatedRow *)a6;
  v7 = 0;
  v57[0] = 0;
  v8 = a4;
  v11 = this;
  v12 = 0x8000;
  if ( a6 )
  {
    v13 = a6[4];
    v14 = 0;
    LOBYTE(a4) = 0;
    goto LABEL_3;
  }
  v34 = *(_DWORD *)(a4 + 16);
  v60 = v34;
  v63 = (struct _SmsPreAllocatedRow *)*(unsigned __int8 *)a4;
  v35 = ((v34 + 7) & 0xFFFFFFF8) + 32;
  v36 = v35;
  if ( v35 <= CmsAvlTableLite::SizeOfAllocationsOnLookaside2 )
  {
    if ( v35 <= CmsAvlTableLite::SizeOfAllocationsOnLookaside1 )
    {
      v37 = (unsigned int *)(qword_140262458 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
      if ( v36 > *v37 )
      {
        v37 = 0;
        v38 = v36 + 16;
        goto LABEL_64;
      }
      if ( !*((_BYTE *)v37 + 8) )
      {
        if ( (int)*((_QWORD *)v37 + 11) > (int)HIDWORD(*((_QWORD *)v37 + 11)) )
        {
          v46 = _InterlockedDecrement((volatile signed __int32 *)v37 + 22);
          if ( v46 >= (int)v37[23] && v46 >= 0 )
          {
            v49 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v37 + 4);
            goto LABEL_100;
          }
          _InterlockedIncrement((volatile signed __int32 *)v37 + 22);
        }
LABEL_87:
        v38 = v37[1];
LABEL_64:
        Pool2 = ExAllocatePool2(66, v38, 1766871885);
        v40 = (_WORD *)Pool2;
        if ( (Pool2 & 0xF) == 0 )
        {
          if ( !Pool2 )
          {
LABEL_102:
            LOWORD(v34) = v60;
            v12 = 0x2000;
            goto LABEL_103;
          }
LABEL_101:
          *(_QWORD *)v40 = v37;
          v40 += 8;
          goto LABEL_102;
        }
LABEL_130:
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      }
      v48 = (struct _NPAGED_LOOKASIDE_LIST *)(v37 + 16);
      if ( *((_BYTE *)v37 + 9) )
        v49 = ExAllocateFromNPagedLookasideList(v48);
      else
        v49 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v48);
LABEL_100:
      v40 = v49;
      if ( v49 )
        goto LABEL_101;
      goto LABEL_87;
    }
    KeGetCurrentProcessorNumberEx(0);
    v43 = qword_140262460;
    if ( v36 > *(unsigned int *)qword_140262460 )
    {
      v43 = 0;
      v44 = v36 + 16;
      goto LABEL_80;
    }
    if ( !*(_BYTE *)(qword_140262460 + 8) )
    {
      if ( (int)*(_QWORD *)(qword_140262460 + 88) > (int)HIDWORD(*(_QWORD *)(qword_140262460 + 88)) )
      {
        v47 = _InterlockedDecrement((volatile signed __int32 *)(qword_140262460 + 88));
        if ( v47 >= *(_DWORD *)(v43 + 92) && v47 >= 0 )
        {
          v51 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v43 + 64));
          goto LABEL_105;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v43 + 88));
      }
LABEL_94:
      v44 = *(unsigned int *)(v43 + 4);
LABEL_80:
      v45 = ExAllocatePool2(66, v44, 1766871885);
      v40 = (_WORD *)v45;
      if ( (v45 & 0xF) != 0 )
        goto LABEL_130;
      if ( !v45 )
      {
LABEL_107:
        v12 = 0x4000;
LABEL_103:
        if ( v40 )
        {
          v61 = (__int64)v40;
          goto LABEL_89;
        }
        return 3221225626LL;
      }
LABEL_106:
      *(_QWORD *)v40 = v43;
      v40 += 8;
      goto LABEL_107;
    }
    v50 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140262460 + 64);
    if ( *(_BYTE *)(qword_140262460 + 9) )
      v51 = ExAllocateFromNPagedLookasideList(v50);
    else
      v51 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v50);
LABEL_105:
    v40 = v51;
    if ( v51 )
      goto LABEL_106;
    goto LABEL_94;
  }
  v61 = ExAllocatePool2(66, ((v34 + 7) & 0xFFFFFFF8) + 32, 1766871885);
  v40 = (_WORD *)v61;
  if ( v61 )
  {
LABEL_89:
    v40[14] = 0;
    v6 = (struct _SmsPreAllocatedRow *)v8;
    memmove(v40 + 16, *(const void **)(v8 + 24), *(unsigned int *)(v8 + 16));
    LOBYTE(a4) = 1;
    v13 = (struct _RTL_AVL_ENTRY *)v61;
    *((_BYTE *)v40 + 26) = 32;
    v40[14] |= v12;
    v40[15] = v34;
    v11 = this;
    *((_BYTE *)v40 + 27) = (_BYTE)v63;
    v14 = 0;
LABEL_3:
    v15 = 2;
    v16 = *((unsigned __int8 *)a2 + 96);
    v17 = 5;
    v62 = a4;
    if ( (*(_DWORD *)a2 & 0x8000LL) == 0 )
      v17 = 2;
    v59 = 2;
    if ( v16 < v17 )
    {
      v18 = v16 + 1;
      *((_BYTE *)a2 + 96) = v18;
      if ( v18 <= 2u )
        v19 = (char *)a2 - 24;
      else
        v19 = (char *)a2 + 784;
      v20 = &v19[40 * v18];
      *(_QWORD *)v20 = v6;
      *((_WORD *)v20 + 16) = 0;
      *((_QWORD *)v20 + 1) = a3;
      *((_QWORD *)v20 + 2) = *((_QWORD *)a3 + 7);
      LOBYTE(v16) = *((_BYTE *)a2 + 96);
    }
    if ( (_BYTE)a4 )
    {
      if ( (unsigned __int8)v16 <= 2u )
        v21 = (char *)a2 + 9;
      else
        v21 = (char *)a2 + 817;
      v21[40 * (unsigned __int8)v16] = 1;
    }
    v22 = *((unsigned __int8 *)a2 + 96);
    v23 = (struct _RTL_AVL_ENTRY **)((char *)a2 + 40 * v22);
    if ( (unsigned __int8)v22 > 2u )
      v23 += 101;
    *v23 = v13;
    if ( a5 && *((_QWORD *)a5 + 1) )
    {
      a4 = *(_QWORD *)a5;
      if ( !*(_QWORD *)a5 )
      {
        v15 = *((_DWORD *)a5 + 4);
        v30 = (_QWORD *)((char *)v11 + 16);
        v59 = v15;
        v7 = *((_QWORD *)a5 + 1);
        goto LABEL_44;
      }
      if ( *((_WORD *)a3 + 2) == 3 )
      {
        if ( !*((_QWORD *)v11 + 2) )
        {
          v15 = 0;
          v59 = 0;
LABEL_25:
          v25 = 0;
          goto LABEL_36;
        }
        v7 = *(_QWORD *)a5;
        v41 = **((_QWORD **)v6 + 1);
        while ( 1 )
        {
          while ( 1 )
          {
            v42 = v7 ? (unsigned __int64 *)(v7 + *(unsigned __int8 *)(v7 + 26)) : 0LL;
            if ( v41 >= *v42 )
              break;
            if ( !*(_QWORD *)(v7 + 8) )
              goto LABEL_25;
            v7 = *(_QWORD *)(v7 + 8);
          }
          if ( v41 < v42[1] + *v42 )
            break;
          if ( !*(_QWORD *)(v7 + 16) )
          {
            v15 = 3;
            v25 = 0;
            v59 = 3;
            goto LABEL_36;
          }
          v7 = *(_QWORD *)(v7 + 16);
        }
        v15 = 1;
        v25 = v7;
      }
      else
      {
        NodeOrParentIn = FindNodeOrParentInSubtree<MST_AVL_DEFAULT_PROTOTYPE>(
                           (_DWORD)v11,
                           (_DWORD)a2,
                           2,
                           a4,
                           (__int64)v57);
        v7 = v57[0];
        v15 = NodeOrParentIn;
        v25 = v57[0];
        if ( v15 != 1 )
          v25 = 0;
      }
      v59 = v15;
    }
    else
    {
      v24 = *((_QWORD *)v11 + 2);
      if ( *((_WORD *)a3 + 2) == 3 )
      {
        if ( v24 )
        {
          v7 = *((_QWORD *)v11 + 2);
          v32 = **((_QWORD **)v6 + 1);
          while ( 1 )
          {
            while ( 1 )
            {
              v33 = v7 ? (unsigned __int64 *)(v7 + *(unsigned __int8 *)(v7 + 26)) : 0LL;
              if ( v32 >= *v33 )
                break;
              if ( !*(_QWORD *)(v7 + 8) )
                goto LABEL_19;
              v7 = *(_QWORD *)(v7 + 8);
            }
            if ( v32 < v33[1] + *v33 )
              break;
            if ( !*(_QWORD *)(v7 + 16) )
            {
              v15 = 3;
              v25 = 0;
              v59 = 3;
              goto LABEL_37;
            }
            v7 = *(_QWORD *)(v7 + 16);
          }
          v15 = 1;
          v59 = 1;
          v25 = v7;
        }
        else
        {
          v15 = 0;
LABEL_19:
          v59 = v15;
          v25 = 0;
        }
        goto LABEL_37;
      }
      if ( v24 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v26 = *((unsigned __int8 *)a2 + 96);
            v7 = v24;
            v27 = (unsigned __int8)v26 <= 2u
                ? (struct CmsTransactionCore *)((char *)a2 - 24)
                : (struct CmsTransactionCore *)((char *)a2 + 784);
            LODWORD(v57[0]) = *(unsigned __int8 *)(v24 + 27);
            v57[1] = v24 + *(unsigned __int8 *)(v24 + 26);
            WORD2(v57[0]) = 0;
            v28 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *))(**((_QWORD **)v27 + 5 * v26 + 2) + 8LL))(
                    *((_QWORD *)v27 + 5 * v26 + 2),
                    (__int64)v27 + 40 * v26,
                    v57);
            if ( v28 )
              break;
            v24 = *(_QWORD *)(v7 + 8);
            if ( !v24 )
            {
              v15 = 2;
              goto LABEL_35;
            }
          }
          if ( v28 != 1 )
            break;
          v24 = *(_QWORD *)(v7 + 16);
          if ( !v24 )
          {
            v15 = 3;
            goto LABEL_35;
          }
        }
        v15 = 1;
        v59 = 1;
        v25 = v7;
      }
      else
      {
        v15 = 0;
LABEL_35:
        v59 = v15;
        v25 = 0;
      }
    }
LABEL_36:
    a4 = v62;
LABEL_37:
    if ( v25 )
    {
      if ( a5 )
      {
        *(_QWORD *)a5 = v25;
        *((_QWORD *)a5 + 1) = v25;
        *((_DWORD *)a5 + 4) = 3;
        *((_DWORD *)a5 + 5) = *((_DWORD *)v11 + 10);
      }
      --*((_BYTE *)a2 + 96);
      if ( v13 )
      {
        if ( (_BYTE)a4 )
          CmsAvlTableLite::FreeIndexEntry(v13);
      }
      return (unsigned int)-1073741771;
    }
    v30 = (_QWORD *)((char *)v11 + 16);
LABEL_44:
    ++*((_DWORD *)v11 + 10);
    if ( v15 != 1 )
    {
      v31 = (_OWORD *)((__int64 (__fastcall *)(CmsAvlTableLite *, _QWORD, struct CmsTransactionCore *, unsigned __int64))qword_140262628)(
                        v11,
                        0,
                        a2,
                        a4);
      if ( v31 )
      {
        *v31 = 0;
        *(_OWORD *)((char *)v31 + 10) = 0;
        ++*((_DWORD *)v11 + 8);
        if ( v59 )
        {
          if ( v59 == 2 )
            *(_QWORD *)(v7 + 8) = v31;
          else
            *(_QWORD *)(v7 + 16) = v31;
          *(_QWORD *)v31 = v7;
          *((_BYTE *)v11 + 24) = -1;
          for ( i = *(_QWORD *)v31; ; v7 = i )
          {
            v54 = *(_QWORD *)(i + 8) == (_QWORD)v31;
            v55 = -1;
            v56 = *(_BYTE *)(v7 + 24);
            if ( !v54 )
              v55 = 1;
            if ( v56 )
              break;
            i = *(_QWORD *)v7;
            v31 = (_OWORD *)v7;
            *(_BYTE *)(v7 + 24) = v55;
          }
          if ( v56 == v55 )
            RebalanceNode((struct _RTL_AVL_ENTRY *)v7);
          else
            *(_BYTE *)(v7 + 24) = 0;
        }
        else
        {
          *v30 = v31;
          *(_QWORD *)v31 = v11;
        }
      }
    }
    if ( a5 )
    {
      *(_QWORD *)a5 = v13;
      *((_QWORD *)a5 + 1) = v13;
      *((_DWORD *)a5 + 4) = 1;
      *((_DWORD *)a5 + 5) = *((_DWORD *)v11 + 10);
    }
    --*((_BYTE *)a2 + 96);
    return v14;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140085f10  mov     [rsp+arg_8], rbx
0x140085f15  mov     [rsp+arg_0], rcx
0x140085f1a  push    rbp
0x140085f1b  push    rsi
0x140085f1c  push    rdi
0x140085f1d  push    r12
0x140085f1f  push    r13
0x140085f21  push    r14
0x140085f23  push    r15
0x140085f25  sub     rsp, 40h
0x140085f29  mov     rsi, [rsp+78h+arg_28]
0x140085f31  xor     ebx, ebx
0x140085f33  mov     [rsp+78h+var_48], rbx
0x140085f38  mov     r15, r9
0x140085f3b  mov     rbp, r8
0x140085f3e  mov     rdi, rdx
0x140085f41  mov     r13, rcx
0x140085f44  mov     r12d, 8000h
0x140085f4a  test    rsi, rsi
0x140085f4d  jz      loc_140086228
0x140085f53  mov     r15, [rsi+20h]
0x140085f57  xor     r14d, r14d
0x140085f5a  xor     r9b, r9b
0x140085f5d  mov     eax, [rdi]
0x140085f5f  mov     r8d, 2
0x140085f65  movzx   edx, byte ptr [rdi+60h]
0x140085f69  test    r12, rax
0x140085f6c  mov     eax, 5
0x140085f71  mov     byte ptr [rsp+78h+arg_28], r9b
0x140085f79  cmovz   eax, r8d
0x140085f7d  mov     dword ptr [rsp+78h+arg_18], r8d
0x140085f85  cmp     edx, eax
0x140085f87  jnb     short loc_140085FC2
0x140085f89  inc     dl
0x140085f8b  movzx   ecx, dl
0x140085f8e  mov     [rdi+60h], cl
0x140085f91  lea     rax, [rcx+rcx*4]
0x140085f95  cmp     cl, r8b
0x140085f98  jbe     loc_14008659D
0x140085f9e  lea     rcx, [rdi+310h]
0x140085fa5  lea     rcx, [rcx+rax*8]
0x140085fa9  xor     eax, eax
0x140085fab  mov     [rcx], rsi
0x140085fae  mov     [rcx+20h], ax
0x140085fb2  mov     [rcx+8], rbp
0x140085fb6  mov     rax, [rbp+38h]
0x140085fba  mov     [rcx+10h], rax
0x140085fbe  movzx   edx, byte ptr [rdi+60h]
0x140085fc2  test    r9b, r9b
0x140085fc5  jz      short loc_140085FE5
0x140085fc7  movzx   eax, dl
0x140085fca  lea     rcx, [rax+rax*4]
0x140085fce  cmp     dl, r8b
0x140085fd1  jbe     loc_1400865A6
0x140085fd7  lea     rax, [rdi+331h]
0x140085fde  lea     rax, [rax+rcx*8]
0x140085fe2  mov     byte ptr [rax], 1
0x140085fe5  movzx   ecx, byte ptr [rdi+60h]
0x140085fe9  lea     rax, [rcx+rcx*4]
0x140085fed  lea     rdx, [rdi+rax*8]
0x140085ff1  cmp     cl, r8b
0x140085ff4  jbe     short loc_140085FFD
0x140085ff6  add     rdx, 328h
0x140085ffd  mov     r12, [rsp+78h+arg_20]
0x140086005  mov     [rdx], r15
0x140086008  test    r12, r12
0x14008600b  jnz     short loc_140086038
0x14008600d  cmp     word ptr [rbp+4], 3
0x140086012  mov     ebp, 1
0x140086017  mov     rax, [r13+10h]
0x14008601b  jnz     short loc_14008607B
0x14008601d  test    rax, rax
0x140086020  jnz     loc_1400861A2
0x140086026  xor     r8d, r8d
0x140086029  mov     dword ptr [rsp+78h+arg_18], r8d
0x140086031  xor     eax, eax
0x140086033  jmp     loc_140086112
0x140086038  mov     rax, [r12+8]
0x14008603d  test    rax, rax
0x140086040  jz      short loc_14008600D
0x140086042  mov     r9, [r12]
0x140086046  test    r9, r9
0x140086049  jz      loc_1400861F5
0x14008604f  cmp     word ptr [rbp+4], 3
0x140086054  jnz     loc_1400865BD
0x14008605a  cmp     [r13+10h], rbx
0x14008605e  jnz     loc_1400862D4
0x140086064  xor     r8d, r8d
0x140086067  mov     dword ptr [rsp+78h+arg_18], r8d
0x14008606f  xor     eax, eax
0x140086071  mov     ebp, 1
0x140086076  jmp     loc_140086109
0x14008607b  test    rax, rax
0x14008607e  jz      loc_1400862CC
0x140086084  movzx   ecx, byte ptr [rdi+60h]
0x140086088  mov     rbx, rax
0x14008608b  lea     rax, [rcx+rcx*4]
0x14008608f  cmp     cl, 2
0x140086092  jbe     loc_1400865FE
0x140086098  lea     rdx, [rdi+310h]
0x14008609f  lea     rdx, [rdx+rax*8]
0x1400860a3  movzx   eax, byte ptr [rbx+1Bh]
0x1400860a7  mov     dword ptr [rsp+78h+var_48], eax
0x1400860ab  lea     r8, [rsp+78h+var_48]
0x1400860b0  movzx   eax, byte ptr [rbx+1Ah]
0x1400860b4  add     rax, rbx
0x1400860b7  mov     [rsp+78h+var_40], rax
0x1400860bc  xor     eax, eax
0x1400860be  mov     word ptr [rsp+78h+var_48+4], ax
0x1400860c3  mov     rcx, [rdx+10h]
0x1400860c7  mov     rax, [rcx]
0x1400860ca  mov     rax, [rax+8]
0x1400860ce  call    _guard_dispatch_icall
0x1400860d3  test    eax, eax
0x1400860d5  jnz     short loc_1400860E8
0x1400860d7  mov     rax, [rbx+8]
0x1400860db  test    rax, rax
0x1400860de  jnz     short loc_140086084
0x1400860e0  mov     r8d, 2
0x1400860e6  jmp     short loc_1400860FF
0x1400860e8  cmp     eax, ebp
0x1400860ea  jnz     loc_1400864B7
0x1400860f0  mov     rax, [rbx+10h]
0x1400860f4  test    rax, rax
0x1400860f7  jnz     short loc_140086084
0x1400860f9  mov     r8d, 3
0x1400860ff  mov     dword ptr [rsp+78h+arg_18], r8d
0x140086107  xor     eax, eax
0x140086109  movzx   r9d, byte ptr [rsp+78h+arg_28]
0x140086112  mov     rdx, r13
0x140086115  mov     ecx, 10h
0x14008611a  test    rax, rax
0x14008611d  jz      short loc_140086156
0x14008611f  test    r12, r12
0x140086122  jnz     loc_140086635
0x140086128  dec     byte ptr [rdi+60h]
0x14008612b  test    r15, r15
0x14008612e  jnz     loc_140086655
0x140086134  mov     r14d, 0C0000035h
0x14008613a  mov     eax, r14d
0x14008613d  mov     rbx, [rsp+78h+arg_8]
0x140086145  add     rsp, 40h
0x140086149  pop     r15
0x14008614b  pop     r14
0x14008614d  pop     r13
0x14008614f  pop     r12
0x140086151  pop     rdi
0x140086152  pop     rsi
0x140086153  pop     rbp
0x140086154  retn
0x140086156  lea     rsi, [rdx+rcx]
0x14008615a  inc     dword ptr [r13+28h]
0x14008615e  cmp     r8d, 1
0x140086162  jz      short loc_140086181
0x140086164  mov     rax, cs:qword_140262628
0x14008616b  mov     r8, rdi
0x14008616e  xor     edx, edx
0x140086170  mov     rcx, r13
0x140086173  call    _guard_dispatch_icall
0x140086178  test    rax, rax
0x14008617b  jnz     loc_140086607
0x140086181  test    r12, r12
0x140086184  jz      short loc_14008619D
0x140086186  mov     [r12], r15
0x14008618a  mov     [r12+8], r15
0x14008618f  mov     [r12+10h], ebp
0x140086194  mov     eax, [r13+28h]
0x140086198  mov     [r12+14h], eax
0x14008619d  dec     byte ptr [rdi+60h]
0x1400861a0  jmp     short loc_14008613A
0x1400861a2  mov     rbx, rax
0x1400861a5  mov     rax, [rsi+8]
0x1400861a9  mov     rdx, [rax]
0x1400861ac  nop     dword ptr [rax+00h]
0x1400861b0  test    rbx, rbx
0x1400861b3  jz      loc_1400864A9
0x1400861b9  movzx   eax, byte ptr [rbx+1Ah]
0x1400861bd  add     rax, rbx
0x1400861c0  mov     rcx, [rax]
0x1400861c3  cmp     rdx, rcx
0x1400861c6  jb      short loc_1400861E3
0x1400861c8  add     rcx, [rax+8]
0x1400861cc  cmp     rdx, rcx
0x1400861cf  jb      loc_1400865EC
0x1400861d5  mov     rax, [rbx+10h]
0x1400861d9  test    rax, rax
0x1400861dc  jz      short loc_140086213
0x1400861de  mov     rbx, rax
0x1400861e1  jmp     short loc_1400861B0
0x1400861e3  mov     rax, [rbx+8]
0x1400861e7  test    rax, rax
0x1400861ea  jz      loc_140086029
0x1400861f0  mov     rbx, rax
0x1400861f3  jmp     short loc_1400861B0
0x1400861f5  mov     r8d, [r12+10h]
0x1400861fa  lea     rsi, [r13+10h]
0x1400861fe  mov     dword ptr [rsp+78h+arg_18], r8d
0x140086206  mov     rbx, rax
0x140086209  mov     ebp, 1
0x14008620e  jmp     loc_14008615A
0x140086213  mov     r8d, 3
0x140086219  xor     eax, eax
0x14008621b  mov     dword ptr [rsp+78h+arg_18], r8d
0x140086223  jmp     loc_140086112
0x140086228  mov     r13d, [r9+10h]
0x14008622c  movzx   ecx, byte ptr [r9]
0x140086230  mov     dword ptr [rsp+78h+arg_18], r13d
0x140086238  mov     byte ptr [rsp+78h+arg_28], cl
0x14008623f  lea     eax, [r13+7]
0x140086243  and     eax, 0FFFFFFF8h
0x140086246  add     eax, 20h ; ' '
0x140086249  cmp     eax, cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x14008624f  mov     esi, eax
0x140086251  ja      loc_1400863DA
0x140086257  xor     ecx, ecx; ProcNumber
0x140086259  cmp     eax, cs:?SizeOfAllocationsOnLookaside1@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside1
0x14008625f  ja      loc_14008633F
0x140086265  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008626c  nop     dword ptr [rax+rax+00h]
0x140086271  xor     edx, edx
0x140086273  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140086279  lea     r13, [rdx+rdx*2]
0x14008627d  shl     r13, 6
0x140086281  add     r13, cs:qword_140262458
0x140086288  mov     eax, [r13+0]
0x14008628c  cmp     rsi, rax
0x14008628f  jbe     loc_140086396
0x140086295  xor     r13d, r13d
0x140086298  lea     rdx, [rsi+10h]
0x14008629c  mov     ecx, 42h ; 'B'
0x1400862a1  mov     r8d, 6950534Dh
0x1400862a7  call    cs:__imp_ExAllocatePool2
0x1400862ae  nop     dword ptr [rax+rax+00h]
0x1400862b3  mov     r14, rax
0x1400862b6  test    al, 0Fh
0x1400862b8  jnz     loc_1401F820A
0x1400862be  test    rax, rax
0x1400862c1  jz      loc_1400864F4
0x1400862c7  jmp     loc_1400864ED
0x1400862cc  xor     r8d, r8d
0x1400862cf  jmp     loc_1400860FF
0x1400862d4  mov     rax, [rsi+8]
0x1400862d8  mov     rbx, r9
0x1400862db  mov     rdx, [rax]
0x1400862de  xchg    ax, ax
0x1400862e0  test    rbx, rbx
0x1400862e3  jz      loc_1400864B0
0x1400862e9  movzx   eax, byte ptr [rbx+1Ah]
0x1400862ed  add     rax, rbx
0x1400862f0  mov     rcx, [rax]
0x1400862f3  cmp     rdx, rcx
0x1400862f6  jb      short loc_140086313
0x1400862f8  add     rcx, [rax+8]
0x1400862fc  cmp     rdx, rcx
0x1400862ff  jb      loc_1400865AF
0x140086305  mov     rax, [rbx+10h]
0x140086309  test    rax, rax
0x14008630c  jz      short loc_140086325
0x14008630e  mov     rbx, rax
0x140086311  jmp     short loc_1400862E0
0x140086313  mov     rax, [rbx+8]
0x140086317  test    rax, rax
0x14008631a  jz      loc_14008606F
0x140086320  mov     rbx, rax
0x140086323  jmp     short loc_1400862E0
0x140086325  mov     r8d, 3
0x14008632b  xor     eax, eax
0x14008632d  mov     dword ptr [rsp+78h+arg_18], r8d
0x140086335  mov     ebp, 1
0x14008633a  jmp     loc_140086109
0x14008633f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140086346  nop     dword ptr [rax+rax+00h]
0x14008634b  mov     r12, cs:qword_140262460
0x140086352  mov     eax, [r12]
0x140086356  cmp     rsi, rax
0x140086359  jbe     loc_14008645F
0x14008635f  xor     r12d, r12d
0x140086362  lea     rdx, [rsi+10h]
0x140086366  mov     ecx, 42h ; 'B'
0x14008636b  mov     r8d, 6950534Dh
0x140086371  call    cs:__imp_ExAllocatePool2
0x140086378  nop     dword ptr [rax+rax+00h]
0x14008637d  mov     r14, rax
0x140086380  test    al, 0Fh
0x140086382  jnz     loc_1401F820A
0x140086388  test    rax, rax
0x14008638b  jz      loc_140086523
0x140086391  jmp     loc_14008651C
0x140086396  cmp     [r13+8], bl
0x14008639a  jnz     loc_14008652B
0x1400863a0  mov     rcx, [r13+58h]
0x1400863a4  mov     rax, rcx
0x1400863a7  shr     rax, 20h
0x1400863ab  cmp     ecx, eax
0x1400863ad  jle     short loc_1400863D1
0x1400863af  nop
0x1400863b0  mov     ecx, 0FFFFFFFFh
0x1400863b5  lock xadd [r13+58h], ecx
0x1400863bb  nop
0x1400863bc  dec     ecx
  ... truncated ...
```
