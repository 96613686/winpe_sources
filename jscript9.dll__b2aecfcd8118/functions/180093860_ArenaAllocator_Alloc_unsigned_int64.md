# ArenaAllocator::Alloc(unsigned __int64)

- ea: `0x180093860`
- end: `0x180093f36`
- name: `?Alloc@ArenaAllocator@@QEAAPEAD_K@Z`
- size: `1750`
- prototype: `char *__fastcall(ArenaAllocator *__hidden this, unsigned __int64)`
- caller_count: `425`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bfb0`
- `0x18000c9bc`
- `0x18000f3cc`
- `0x18000fa80`
- `0x1800101bc`
- `0x180010718`
- `0x180010868`
- `0x1800112e0`
- `0x180011c0c`
- `0x180011db0`
- `0x180012204`
- `0x180014774`
- `0x18002a954`
- `0x180038060`
- `0x180038c24`
- `0x1800392e8`
- `0x180039630`
- `0x18003a040`
- `0x18003e260`
- `0x18003f38c`
- `0x18003f40c`
- `0x18003f564`
- `0x18003fb20`
- `0x18003fec8`
- `0x1800401d4`
- `0x180040908`
- `0x180040b64`
- `0x180041160`
- `0x1800418e0`
- `0x180042184`
- `0x1800439c8`
- `0x180044110`
- `0x1800443b0`
- `0x18004556c`
- `0x180045cb4`
- `0x180046c8c`
- `0x1800473b0`
- `0x180048a80`
- `0x180049724`
- `0x18004a904`
- `0x18004b07c`
- `0x18004b388`
- `0x18004b8dc`
- `0x180050bf0`
- `0x180051684`
- `0x180051ed0`
- `0x18005a1c0`
- `0x1800625c8`
- `0x180062c38`
- `0x180064c3c`

## callees

- `0x180004f94`
- `0x180008e7c`
- `0x1800215c0`
- `0x180026314`
- `0x180026bc0`
- `0x180028284`
- `0x180093860`
- `0x1801b3d5c`
- `0x18025a1fc`
- `0x18025a464`
- `0x180364010`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x180093a65`
- `KERNEL32!InterlockedPushEntrySList` at `0x180093a65`
- `KERNEL32!InterlockedPopEntrySList` at `0x180093e60`
- `KERNEL32!InterlockedPopEntrySList` at `0x180093e60`

## pseudocode

```c
char *__fastcall ArenaAllocator::Alloc(ArenaAllocator *this, unsigned __int64 *a2)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rbx
  char *result; // rax
  char *v6; // r9
  unsigned __int64 v7; // r13
  PageAllocator **v8; // r14
  void (*v9)(void); // rax
  char *v10; // rdi
  __int64 v11; // r8
  _QWORD *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned __int64 *v16; // r8
  unsigned __int64 v17; // r10
  unsigned __int64 *v18; // r11
  int v19; // r9d
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rcx
  __int64 v23; // r9
  int v24; // edi
  _QWORD *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rcx
  unsigned int v28; // eax
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // rax
  __int64 v31; // rax
  unsigned __int64 *v32; // r9
  _QWORD **v33; // r8
  struct PageSegment *v34; // r15
  int v35; // edx
  _QWORD *v36; // rcx
  signed __int64 v37; // rax
  _QWORD *v38; // rcx
  signed __int64 v39; // rax
  __int64 v40; // rbp
  unsigned __int64 v41; // r12
  bool v42; // zf
  unsigned int v43; // r11d
  unsigned int v44; // eax
  unsigned int v45; // r9d
  unsigned int v46; // edx
  unsigned int v47; // r10d
  int v48; // edx
  unsigned int v49; // r8d
  union _SLIST_HEADER *v50; // rcx
  PSLIST_ENTRY v51; // rax
  int Next; // edi
  struct Segment *v53; // rax
  unsigned __int64 *v54; // r8
  unsigned __int64 *v55; // [rsp+28h] [rbp-50h]
  PSLIST_ENTRY v56; // [rsp+28h] [rbp-50h]
  struct PageSegment *v57; // [rsp+30h] [rbp-48h] BYREF

  v3 = *((_QWORD *)this + 11);
  if ( v3 && (unsigned __int64)a2 - 1 <= 0x3EF )
  {
    v4 = ((unsigned __int64)a2 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
    a2 = (unsigned __int64 *)(v3 + 8 * (v4 >> 4));
    result = (char *)*(a2 - 1);
    if ( result )
    {
      *(a2 - 1) = *(_QWORD *)result;
      return result;
    }
  }
  else if ( (unsigned __int64)a2 >= 0xFFFFFFFFFFFFFFF0uLL )
  {
    v4 = -16;
  }
  else
  {
    v4 = ((unsigned __int64)a2 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
  }
  v6 = (char *)*((_QWORD *)this + 6);
  if ( *((_QWORD *)this + 8) - (_QWORD)v6 >= v4 )
  {
    *((_QWORD *)this + 6) = &v6[v4];
    return v6;
  }
  if ( v4 > *((_QWORD *)this + 9) )
  {
LABEL_11:
    v7 = v4 + 32;
    if ( v4 + 32 < v4 )
    {
      v7 = -1;
LABEL_13:
      v8 = (PageAllocator **)((char *)this + 40);
      goto LABEL_14;
    }
    if ( v4 + 4143 < v4 + 32 || v4 == -4144 )
      goto LABEL_13;
    v40 = *((_QWORD *)this + 5);
    v8 = (PageAllocator **)((char *)this + 40);
    v41 = (v4 + 4143) >> 12;
    v57 = 0;
    if ( v41 > *(unsigned int *)(v40 + 88) )
    {
      v53 = PageAllocator::AllocSegment((PageAllocator *)v40, v41);
      v34 = v53;
      if ( !v53 )
        goto LABEL_14;
      v10 = (char *)*((_QWORD *)v53 + 2);
      v3 = *((_QWORD *)v53 + 3) - *((unsigned int *)v53 + 8);
      *(_QWORD *)v10 = v3;
      goto LABEL_42;
    }
    v42 = *(_DWORD *)(v40 + 152) == 0;
    *(_BYTE *)(v40 + 139) = 1;
    if ( v42 )
      AsymetricCriticalSection::FastEnter((AsymetricCriticalSection *)(v40 + 200));
    if ( *(_QWORD *)(v40 + 104) < (unsigned __int64)(unsigned int)v41 )
    {
      v32 = (unsigned __int64 *)(v40 + 8);
    }
    else
    {
      a2 = (unsigned __int64 *)(v40 + 8);
      v54 = (unsigned __int64 *)(v40 + 8);
LABEL_73:
      while ( 1 )
      {
        v54 = (unsigned __int64 *)*v54;
        v55 = v54;
        if ( v54 == a2 )
          break;
        v43 = *((_DWORD *)v54 + 18);
        v34 = (struct PageSegment *)(v54 + 2);
        if ( v43 >= (unsigned int)v41 )
        {
          v44 = *((_DWORD *)v54 + 16);
          v45 = -1;
          v42 = !_BitScanForward(&v46, v44);
          if ( !v42 )
            v45 = v46;
          v47 = 0xFFFFFFFF >> (32 - v41);
          while ( 1 )
          {
            v54 = v55;
            a2 = (unsigned __int64 *)(v40 + 8);
            if ( v45 == -1 )
              break;
            a2 = (unsigned __int64 *)(v40 + 8);
            if ( *((_QWORD *)v34 + 3) - v45 - (unsigned __int64)*((unsigned int *)v34 + 8) < (unsigned int)v41 )
              break;
            if ( (_DWORD)v41 == 1 || (v44 & (v47 << v45)) == v47 << v45 )
            {
              a2 = (unsigned __int64 *)(v40 + 8);
              *((_DWORD *)v34 + 12) = v44 & ~(v47 << v45);
              *((_DWORD *)v34 + 14) = v43 - v41;
              v10 = (char *)(*((_QWORD *)v34 + 2) + (v45 << 12));
              if ( !v10 )
                goto LABEL_73;
              v3 = (unsigned int)((_DWORD)v41 << 12);
              *(_QWORD *)(v40 + 160) += v3;
              v39 = _InterlockedExchangeAdd64(&qword_180443988, v3);
              if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
              {
                McTemplateU0x_EventWriteTransfer(v3, a2, v39 + v3);
                v54 = v55;
              }
              if ( !*((_DWORD *)v34 + 14) )
              {
                *(_QWORD *)v54[1] = *v54;
                *(_QWORD *)(*v54 + 8) = v54[1];
                v3 = *(_QWORD *)(v40 + 24);
                v54[1] = *(_QWORD *)(v3 + 8);
                *v54 = v3;
                **(_QWORD **)(v3 + 8) = v54;
                *(_QWORD *)(v3 + 8) = v54;
                *(_QWORD *)(v40 + 104) -= (unsigned int)v41;
                goto LABEL_38;
              }
              goto LABEL_64;
            }
            v48 = -1 << (v45 + 1);
            v45 = -1;
            v42 = !_BitScanForward(&v49, v44 & v48);
            if ( !v42 )
              v45 = v49;
          }
        }
      }
      if ( (_DWORD)v41 != 1 )
        goto LABEL_87;
      v50 = *(union _SLIST_HEADER **)(v40 + 128);
      if ( !v50 )
        goto LABEL_87;
      v51 = InterlockedPopEntrySList(v50);
      v56 = v51;
      if ( !v51 )
      {
        a2 = (unsigned __int64 *)(v40 + 8);
LABEL_87:
        v32 = a2;
        goto LABEL_50;
      }
      v34 = (struct PageSegment *)*((_QWORD *)&v51->Next + 1);
      Next = (int)v51[1].Next;
      v57 = v34;
      if ( Next == 1 )
      {
        v10 = (char *)v51;
        *v51 = 0;
        v51[1] = 0;
      }
      else
      {
        v24 = Next - 1;
        LODWORD(v51[1].Next) = v24;
        InterlockedPushEntrySList(*(PSLIST_HEADER *)(v40 + 128), v51);
        v10 = (char *)v56 + (unsigned int)(v24 << 12);
      }
      if ( v10 )
        goto LABEL_38;
      v32 = (unsigned __int64 *)(v40 + 8);
    }
LABEL_50:
    v33 = *(_QWORD ***)(v40 + 40);
    if ( v33 == (_QWORD **)(v40 + 40) )
    {
      v10 = PageAllocator::TryAllocDecommitedPages((PageAllocator *)v40, v41, &v57);
      if ( v10 )
      {
        v34 = v57;
LABEL_38:
        if ( !*(_DWORD *)(v40 + 152) )
          *(_DWORD *)(v40 + 240) = 0;
        v8 = (PageAllocator **)((char *)this + 40);
        if ( !v10 )
        {
LABEL_14:
          v9 = (void (*)(void))*((_QWORD *)this + 1);
          if ( !v9 || (v9(), (v10 = (char *)PageAllocator::AllocPagesForBytes(*v8, v7)) == 0) )
          {
            v11 = v4 + 16;
            if ( v4 + 16 < v4 )
              v11 = -1;
            v12 = (_QWORD *)AllocateArray<HeapAllocator,char,1>(v3, a2, v11);
            if ( v12 )
            {
              v12[1] = v4;
              *v12 = *((_QWORD *)this + 4);
              *((_QWORD *)this + 4) = v12;
              v6 = (char *)(v12 + 2);
              *((_DWORD *)this + 20) = 2;
            }
            else
            {
              if ( *(_QWORD *)this )
                (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD))this)(v14, v13, v15, 0);
              return 0;
            }
            return v6;
          }
LABEL_43:
          v25 = v10 + 16;
          *((_QWORD *)v10 + 4) = v10;
          v26 = (*(_QWORD *)v10 << 12) - 48LL;
          *((_QWORD *)v10 + 5) = 0;
          *((_QWORD *)v10 + 3) = v26;
          ++*((_DWORD *)this + 20);
          v27 = *((_QWORD *)this + 2);
          if ( v27 )
          {
            *(_QWORD *)(v27 + 24) = *((_QWORD *)this + 6) - v27 - 32;
            v28 = *((_DWORD *)this + 16) - *((_DWORD *)this + 12);
            if ( v28 >= 0x10 || *((_BYTE *)this + 56) )
            {
              v29 = v28;
              v30 = *((_QWORD *)this + 9);
              if ( v30 <= v29 )
                v30 = v29;
              *((_QWORD *)this + 9) = v30;
            }
            else
            {
              v38 = (_QWORD *)*((_QWORD *)this + 2);
              *((_QWORD *)this + 2) = *v38;
              *v38 = *((_QWORD *)this + 3);
              *((_QWORD *)this + 3) = v38;
            }
          }
          v31 = *((_QWORD *)this + 2);
          *((_QWORD *)this + 6) = &v10[*((_QWORD *)v10 + 5) + 48];
          *((_QWORD *)this + 8) = (char *)v25 + *((_QWORD *)v10 + 3) + 32;
          *v25 = v31;
          v6 = (char *)*((_QWORD *)this + 6);
          *((_QWORD *)this + 2) = v25;
          *((_QWORD *)this + 6) = &v6[v4];
          return v6;
        }
        *(_QWORD *)v10 = v41;
LABEL_42:
        *((_QWORD *)v10 + 1) = v34;
        if ( v10 )
          goto LABEL_43;
        goto LABEL_14;
      }
      v34 = (struct PageSegment *)PageAllocator::AddPageSegment((PageAllocator *)v40);
      if ( !v34 )
      {
        v34 = v57;
        v10 = 0;
        goto LABEL_38;
      }
    }
    else
    {
      v34 = (struct PageSegment *)(v33 + 2);
      v35 = *(_DWORD *)(v40 + 88);
      *v33[1] = *v33;
      (*v33)[1] = v33[1];
      if ( (_DWORD)v41 == v35 )
        v36 = *(_QWORD **)(v40 + 24);
      else
        v36 = (_QWORD *)*v32;
      v33[1] = (_QWORD *)v36[1];
      *v33 = v36;
      *(_QWORD *)v36[1] = v33;
      v36[1] = v33;
    }
    v10 = PageSegment::AllocPages(v34, v41);
    v3 = (unsigned int)((_DWORD)v41 << 12);
    *(_QWORD *)(v40 + 160) += v3;
    v37 = _InterlockedExchangeAdd64(&qword_180443988, v3);
    if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
      McTemplateU0x_EventWriteTransfer(v3, a2, v37 + v3);
LABEL_64:
    *(_QWORD *)(v40 + 104) -= (unsigned int)v41;
    goto LABEL_38;
  }
  v16 = (unsigned __int64 *)*((_QWORD *)this + 2);
  v17 = 0;
  v18 = v16;
  v19 = 10;
  a2 = (unsigned __int64 *)*v16;
  while ( 1 )
  {
    v20 = a2[3];
    v3 = a2[1] - v20;
    if ( v3 >= v4 )
      break;
    if ( v17 <= v3 )
      v17 = a2[1] - v20;
    if ( --v19 )
    {
      v18 = a2;
      a2 = (unsigned __int64 *)*a2;
      if ( a2 )
        continue;
    }
    goto LABEL_11;
  }
  v6 = (char *)a2 + v20 + 32;
  a2[3] = v4 + v20;
  v21 = *((_QWORD *)this + 9);
  if ( v3 == v21 || v17 > v21 )
    *((_QWORD *)this + 9) = v17;
  v22 = v3 - v4;
  if ( v22 > v16[1] - v16[3] )
  {
    *v18 = *a2;
    ArenaAllocatorBase<InPlaceFreeListPolicy>::SetCacheBlock(this, a2, v16, v6);
    return (char *)v23;
  }
  else
  {
    if ( v22 >= 0x10 || *((_BYTE *)this + 56) )
      return v6;
    *v18 = *a2;
    *a2 = *((_QWORD *)this + 3);
    result = v6;
    *((_QWORD *)this + 3) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x180093860  mov     rax, rsp
0x180093863  mov     [rax+10h], rdx
0x180093867  mov     [rax+8], rcx
0x18009386b  push    rbx
0x18009386c  push    rsi
0x18009386d  sub     rsp, 68h
0x180093871  mov     rsi, rcx
0x180093874  mov     rbx, rdx
0x180093877  mov     rcx, [rcx+58h]
0x18009387b  test    rcx, rcx
0x18009387e  jz      short loc_1800938B8
0x180093880  lea     rax, [rdx-1]
0x180093884  cmp     rax, 3EFh
0x18009388a  ja      short loc_1800938B8
0x18009388c  add     rbx, 0Fh
0x180093890  and     rbx, 0FFFFFFFFFFFFFFF0h
0x180093894  mov     rax, rbx
0x180093897  shr     rax, 4
0x18009389b  lea     rdx, [rcx+rax*8]
0x18009389f  mov     rax, [rcx+rax*8-8]
0x1800938a4  test    rax, rax
0x1800938a7  jz      short loc_1800938CA
0x1800938a9  mov     rcx, [rax]
0x1800938ac  mov     [rdx-8], rcx
0x1800938b0  add     rsp, 68h
0x1800938b4  pop     rsi
0x1800938b5  pop     rbx
0x1800938b6  retn
0x1800938b8  cmp     rbx, 0FFFFFFFFFFFFFFF0h
0x1800938bc  jnb     loc_180093EB8
0x1800938c2  add     rbx, 0Fh
0x1800938c6  and     rbx, 0FFFFFFFFFFFFFFF0h
0x1800938ca  mov     r9, [rsi+30h]
0x1800938ce  mov     rax, [rsi+40h]
0x1800938d2  sub     rax, r9
0x1800938d5  cmp     rax, rbx
0x1800938d8  jb      short loc_1800938ED
0x1800938da  lea     rax, [r9+rbx]
0x1800938de  mov     [rsi+30h], rax
0x1800938e2  mov     rax, r9
0x1800938e5  add     rsp, 68h
0x1800938e9  pop     rsi
0x1800938ea  pop     rbx
0x1800938eb  retn
0x1800938ed  cmp     rbx, [rsi+48h]
0x1800938f1  jbe     loc_180093993
0x1800938f7  mov     [rsp+78h+arg_10], rbp
0x1800938ff  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180093906  mov     [rsp+78h+var_18], rdi
0x18009390b  mov     [rsp+78h+var_20], r12
0x180093910  mov     [rsp+78h+var_28], r13
0x180093915  lea     r13, [rbx+20h]
0x180093919  mov     [rsp+78h+var_30], r14
0x18009391e  mov     [rsp+78h+var_38], r15
0x180093923  cmp     r13, rbx
0x180093926  jnb     loc_180093CD2
0x18009392c  mov     r13, rbp
0x18009392f  lea     r14, [rsi+28h]
0x180093933  mov     rax, [rsi+8]
0x180093937  test    rax, rax
0x18009393a  jz      short loc_180093958
0x18009393c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093941  mov     rcx, [r14]; this
0x180093944  mov     rdx, r13; unsigned __int64
0x180093947  call    ?AllocPagesForBytes@PageAllocator@@QEAAPEAVPageAllocation@@_K@Z; PageAllocator::AllocPagesForBytes(unsigned __int64)
0x18009394c  mov     rdi, rax
0x18009394f  test    rax, rax
0x180093952  jnz     loc_180093AAC
0x180093958  lea     r8, [rbx+10h]
0x18009395c  cmp     r8, rbx
0x18009395f  cmovb   r8, rbp
0x180093963  call    ??$AllocateArray@UHeapAllocator@@D$00@@YAPEADPEAUHeapAllocator@@P80@EAAPEAD_K@Z1@Z; AllocateArray<HeapAllocator,char,1>(HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x180093968  mov     r9, rax
0x18009396b  test    rax, rax
0x18009396e  jz      loc_180093F21
0x180093974  mov     [rax+8], rbx
0x180093978  mov     rax, [rsi+20h]
0x18009397c  mov     [r9], rax
0x18009397f  mov     [rsi+20h], r9
0x180093983  add     r9, 10h
0x180093987  mov     dword ptr [rsi+50h], 2
0x18009398e  jmp     loc_180093B3B
0x180093993  mov     r8, [rsi+10h]
0x180093997  xor     r10d, r10d
0x18009399a  mov     r11, r8
0x18009399d  mov     r9d, 0Ah
0x1800939a3  mov     rdx, [r8]
0x1800939a6  mov     rax, [rdx+18h]
0x1800939aa  mov     rcx, [rdx+8]
0x1800939ae  sub     rcx, rax
0x1800939b1  cmp     rcx, rbx
0x1800939b4  jb      short loc_180093A18
0x1800939b6  lea     r9, [rdx+20h]
0x1800939ba  add     r9, rax
0x1800939bd  add     rax, rbx
0x1800939c0  mov     [rdx+18h], rax
0x1800939c4  mov     rax, [rsi+48h]
0x1800939c8  cmp     rcx, rax
0x1800939cb  jnz     short loc_180093A11
0x1800939cd  mov     [rsi+48h], r10
0x1800939d1  mov     rax, [r8+8]
0x1800939d5  sub     rcx, rbx
0x1800939d8  sub     rax, [r8+18h]
0x1800939dc  cmp     rcx, rax
0x1800939df  ja      short loc_180093A3D
0x1800939e1  cmp     rcx, 10h
0x1800939e5  jnb     loc_1800938E2
0x1800939eb  cmp     byte ptr [rsi+38h], 0
0x1800939ef  jnz     loc_1800938E2
0x1800939f5  mov     rax, [rdx]
0x1800939f8  mov     [r11], rax
0x1800939fb  mov     rax, [rsi+18h]
0x1800939ff  mov     [rdx], rax
0x180093a02  mov     rax, r9
0x180093a05  mov     [rsi+18h], rdx
0x180093a09  add     rsp, 68h
0x180093a0d  pop     rsi
0x180093a0e  pop     rbx
0x180093a0f  retn
0x180093a11  cmp     r10, rax
0x180093a14  jbe     short loc_1800939D1
0x180093a16  jmp     short loc_1800939CD
0x180093a18  cmp     r10, rcx
0x180093a1b  cmovbe  r10, rcx
0x180093a1f  sub     r9d, 1
0x180093a23  jz      loc_1800938F7
0x180093a29  mov     r11, rdx
0x180093a2c  mov     rdx, [rdx]
0x180093a2f  test    rdx, rdx
0x180093a32  jnz     loc_1800939A6
0x180093a38  jmp     loc_1800938F7
0x180093a3d  mov     rax, [rdx]
0x180093a40  mov     rcx, rsi
0x180093a43  mov     [r11], rax
0x180093a46  call    ?SetCacheBlock@?$ArenaAllocatorBase@VInPlaceFreeListPolicy@@@@AEAAXPEAUBigBlock@@@Z; ArenaAllocatorBase<InPlaceFreeListPolicy>::SetCacheBlock(BigBlock *)
0x180093a4b  mov     rax, r9
0x180093a4e  add     rsp, 68h
0x180093a52  pop     rsi
0x180093a53  pop     rbx
0x180093a54  retn
0x180093a56  dec     edi
0x180093a58  mov     rdx, rax; ListEntry
0x180093a5b  mov     [rax+10h], edi
0x180093a5e  mov     rcx, [rbp+80h]; ListHead
0x180093a65  call    cs:__imp_InterlockedPushEntrySList
0x180093a6c  nop     dword ptr [rax+rax+00h]
0x180093a71  shl     edi, 0Ch
0x180093a74  add     rdi, [rsp+78h+var_50]
0x180093a79  test    rdi, rdi
0x180093a7c  jz      loc_180093B61
0x180093a82  cmp     dword ptr [rbp+98h], 0
0x180093a89  jz      loc_180093E0C
0x180093a8f  lea     r14, [rsi+28h]
0x180093a93  test    rdi, rdi
0x180093a96  jz      loc_180093F15
0x180093a9c  mov     [rdi], r12
0x180093a9f  mov     [rdi+8], r15
0x180093aa3  test    rdi, rdi
0x180093aa6  jz      loc_180093EAC
0x180093aac  lea     rdx, [rdi+10h]
0x180093ab0  mov     [rdx+10h], rdi
0x180093ab4  mov     rax, [rdi]
0x180093ab7  shl     rax, 0Ch
0x180093abb  sub     rax, 30h ; '0'
0x180093abf  mov     qword ptr [rdx+18h], 0
0x180093ac7  mov     [rdx+8], rax
0x180093acb  inc     dword ptr [rsi+50h]
0x180093ace  mov     rcx, [rsi+10h]
0x180093ad2  test    rcx, rcx
0x180093ad5  jz      short loc_180093B06
0x180093ad7  mov     rax, [rsi+30h]
0x180093adb  sub     rax, rcx
0x180093ade  sub     rax, 20h ; ' '
0x180093ae2  mov     [rcx+18h], rax
0x180093ae6  mov     eax, [rsi+40h]
0x180093ae9  sub     eax, [rsi+30h]
0x180093aec  cmp     eax, 10h
0x180093aef  jb      loc_180093C14
0x180093af5  mov     ecx, eax
0x180093af7  mov     rax, [rsi+48h]
0x180093afb  cmp     rax, rcx
0x180093afe  cmovbe  rax, rcx
0x180093b02  mov     [rsi+48h], rax
0x180093b06  mov     rcx, [rdx+18h]
0x180093b0a  mov     rax, [rsi+10h]
0x180093b0e  add     rcx, 20h ; ' '
0x180093b12  add     rcx, rdx
0x180093b15  mov     [rsi+30h], rcx
0x180093b19  mov     rcx, [rdx+8]
0x180093b1d  add     rcx, 20h ; ' '
0x180093b21  add     rcx, rdx
0x180093b24  mov     [rsi+40h], rcx
0x180093b28  mov     [rdx], rax
0x180093b2b  mov     r9, [rsi+30h]
0x180093b2f  mov     [rsi+10h], rdx
0x180093b33  lea     rax, [r9+rbx]
0x180093b37  mov     [rsi+30h], rax
0x180093b3b  mov     r14, [rsp+78h+var_30]
0x180093b40  mov     r13, [rsp+78h+var_28]
0x180093b45  mov     r12, [rsp+78h+var_20]
0x180093b4a  mov     rdi, [rsp+78h+var_18]
0x180093b4f  mov     rbp, [rsp+78h+arg_10]
0x180093b57  mov     r15, [rsp+78h+var_38]
0x180093b5c  jmp     loc_1800938E2
0x180093b61  lea     r9, [rbp+8]
0x180093b65  mov     r8, [rbp+28h]
0x180093b69  lea     rax, [rbp+28h]
0x180093b6d  cmp     r8, rax
0x180093b70  jnz     short loc_180093B98
0x180093b72  lea     r8, [rsp+78h+var_48]; struct PageSegment **
0x180093b77  mov     edx, r14d; unsigned int
0x180093b7a  mov     rcx, rbp; this
0x180093b7d  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x180093b82  mov     rdi, rax
0x180093b85  test    rax, rax
0x180093b88  jz      loc_180093E1B
0x180093b8e  mov     r15, [rsp+78h+var_48]
0x180093b93  jmp     loc_180093A82
0x180093b98  mov     rcx, [r8+8]
0x180093b9c  lea     r15, [r8+10h]
0x180093ba0  mov     rax, [r8]
0x180093ba3  mov     edx, [rbp+58h]
0x180093ba6  mov     [rcx], rax
0x180093ba9  mov     rcx, [r8]
0x180093bac  mov     rax, [r8+8]
0x180093bb0  mov     [rcx+8], rax
0x180093bb4  cmp     r14d, edx
0x180093bb7  jz      loc_180093E7C
0x180093bbd  mov     rcx, [r9]
0x180093bc0  mov     rax, [rcx+8]
0x180093bc4  mov     [r8+8], rax
0x180093bc8  mov     [r8], rcx
0x180093bcb  mov     rax, [rcx+8]
0x180093bcf  mov     [rax], r8
0x180093bd2  mov     [rcx+8], r8
0x180093bd6  mov     edx, r14d; unsigned int
0x180093bd9  mov     rcx, r15; this
0x180093bdc  call    ?AllocPages@PageSegment@@QEAAPEADI@Z; PageSegment::AllocPages(uint)
0x180093be1  mov     rdi, rax
0x180093be4  mov     eax, r14d
0x180093be7  shl     eax, 0Ch
0x180093bea  mov     ecx, eax
0x180093bec  add     [rbp+0A0h], rcx
0x180093bf3  lock xadd cs:qword_180443988, rax
0x180093bfc  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180093c03  jz      loc_180093C91
0x180093c09  lea     r8, [rax+rcx]
0x180093c0d  call    McTemplateU0x_EventWriteTransfer
0x180093c12  jmp     short loc_180093C91
0x180093c14  cmp     byte ptr [rsi+38h], 0
0x180093c18  jnz     loc_180093AF5
0x180093c1e  mov     rcx, [rsi+10h]
0x180093c22  mov     rax, [rcx]
0x180093c25  mov     [rsi+10h], rax
0x180093c29  mov     rax, [rsi+18h]
0x180093c2d  mov     [rcx], rax
0x180093c30  mov     [rsi+18h], rcx
0x180093c34  jmp     loc_180093B06
0x180093c39  mov     ecx, r9d
0x180093c3c  lea     rdx, [rbp+8]
0x180093c40  shl     r10d, cl
0x180093c43  sub     r11d, r14d
0x180093c46  shl     r9d, 0Ch
0x180093c4a  not     r10d
0x180093c4d  and     r10d, eax
0x180093c50  mov     edi, r9d
0x180093c53  mov     [r15+30h], r10d
0x180093c57  mov     [r15+38h], r11d
0x180093c5b  add     rdi, [r15+10h]
0x180093c5f  jz      loc_180093D40
0x180093c65  mov     eax, r14d
0x180093c68  shl     eax, 0Ch
0x180093c6b  mov     ecx, eax
0x180093c6d  add     [rbp+0A0h], rcx
0x180093c74  lock xadd cs:qword_180443988, rax
0x180093c7d  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180093c84  jnz     loc_180093F02
0x180093c8a  cmp     dword ptr [r15+38h], 0
0x180093c8f  jz      short loc_180093C9A
0x180093c91  sub     [rbp+68h], r14
0x180093c95  jmp     loc_180093A82
0x180093c9a  mov     rcx, [r8+8]
0x180093c9e  mov     rax, [r8]
0x180093ca1  mov     [rcx], rax
0x180093ca4  mov     rcx, [r8]
0x180093ca7  mov     rax, [r8+8]
0x180093cab  mov     [rcx+8], rax
0x180093caf  mov     rcx, [rbp+18h]
0x180093cb3  mov     rax, [rcx+8]
0x180093cb7  mov     [r8+8], rax
0x180093cbb  mov     [r8], rcx
0x180093cbe  mov     rax, [rcx+8]
0x180093cc2  mov     [rax], r8
0x180093cc5  mov     [rcx+8], r8
0x180093cc9  sub     [rbp+68h], r14
0x180093ccd  jmp     loc_180093A82
0x180093cd2  lea     r12, [r13+100Fh]
0x180093cd9  cmp     r12, r13
0x180093cdc  jb      loc_18009392F
0x180093ce2  cmp     r12, rbp
  ... truncated ...
```
