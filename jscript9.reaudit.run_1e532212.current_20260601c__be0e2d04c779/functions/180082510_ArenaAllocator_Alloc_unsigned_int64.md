# ArenaAllocator::Alloc(unsigned __int64)

- ea: `0x180082510`
- end: `0x180082bd6`
- name: `?Alloc@ArenaAllocator@@QEAAPEAD_K@Z`
- size: `1734`
- prototype: `char *__fastcall(ArenaAllocator *__hidden this, unsigned __int64)`
- caller_count: `426`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800139a0`
- `0x180014660`
- `0x180019560`
- `0x18001f7c4`
- `0x18003040c`
- `0x180030ac0`
- `0x1800311f4`
- `0x180031c38`
- `0x18003264c`
- `0x1800326c0`
- `0x1800353e8`
- `0x1800354d0`
- `0x180035770`
- `0x180035960`
- `0x180035ac0`
- `0x180035dd0`
- `0x1800361a4`
- `0x180036820`
- `0x180036d60`
- `0x180036f34`
- `0x1800376c4`
- `0x180037dec`
- `0x1800381b8`
- `0x180038868`
- `0x18003b57c`
- `0x18003c240`
- `0x18003c628`
- `0x18003e970`
- `0x1800437f0`
- `0x1800454f4`
- `0x1800457c0`
- `0x18004a430`
- `0x18004ad50`
- `0x18004b520`
- `0x18004bba0`
- `0x18004c2c0`
- `0x18004c530`
- `0x18004e294`
- `0x18004e3d0`
- `0x18004ed58`
- `0x18004f120`
- `0x18004f8a8`
- `0x180050070`
- `0x18005c708`
- `0x18005f910`
- `0x180060508`
- `0x180060c30`
- `0x180061640`
- `0x180065880`
- `0x180075ae4`

## callees

- `0x180004d60`
- `0x1800052bc`
- `0x18000ef2c`
- `0x18000f7c4`
- `0x180010e48`
- `0x18006a5f0`
- `0x180082510`
- `0x1801b10e0`
- `0x180255a38`
- `0x180255c94`
- `0x18035e010`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x180082711`
- `KERNEL32!InterlockedPushEntrySList` at `0x180082711`
- `KERNEL32!InterlockedPopEntrySList` at `0x180082b06`
- `KERNEL32!InterlockedPopEntrySList` at `0x180082b06`

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
              v39 = _InterlockedExchangeAdd64(&qword_18043D988, v3);
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
    v37 = _InterlockedExchangeAdd64(&qword_18043D988, v3);
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
0x180082510  mov     rax, rsp
0x180082513  mov     [rax+10h], rdx
0x180082517  mov     [rax+8], rcx
0x18008251b  push    rbx
0x18008251c  push    rsi
0x18008251d  sub     rsp, 68h
0x180082521  mov     rsi, rcx
0x180082524  mov     rbx, rdx
0x180082527  mov     rcx, [rcx+58h]
0x18008252b  test    rcx, rcx
0x18008252e  jz      short loc_180082567
0x180082530  lea     rax, [rdx-1]
0x180082534  cmp     rax, 3EFh
0x18008253a  ja      short loc_180082567
0x18008253c  add     rbx, 0Fh
0x180082540  and     rbx, 0FFFFFFFFFFFFFFF0h
0x180082544  mov     rax, rbx
0x180082547  shr     rax, 4
0x18008254b  lea     rdx, [rcx+rax*8]
0x18008254f  mov     rax, [rcx+rax*8-8]
0x180082554  test    rax, rax
0x180082557  jz      short loc_180082579
0x180082559  mov     rcx, [rax]
0x18008255c  mov     [rdx-8], rcx
0x180082560  add     rsp, 68h
0x180082564  pop     rsi
0x180082565  pop     rbx
0x180082566  retn
0x180082567  cmp     rbx, 0FFFFFFFFFFFFFFF0h
0x18008256b  jnb     loc_180082B58
0x180082571  add     rbx, 0Fh
0x180082575  and     rbx, 0FFFFFFFFFFFFFFF0h
0x180082579  mov     r9, [rsi+30h]
0x18008257d  mov     rax, [rsi+40h]
0x180082581  sub     rax, r9
0x180082584  cmp     rax, rbx
0x180082587  jb      short loc_18008259B
0x180082589  lea     rax, [r9+rbx]
0x18008258d  mov     [rsi+30h], rax
0x180082591  mov     rax, r9
0x180082594  add     rsp, 68h
0x180082598  pop     rsi
0x180082599  pop     rbx
0x18008259a  retn
0x18008259b  cmp     rbx, [rsi+48h]
0x18008259f  jbe     loc_180082641
0x1800825a5  mov     [rsp+78h+arg_10], rbp
0x1800825ad  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x1800825b4  mov     [rsp+78h+var_18], rdi
0x1800825b9  mov     [rsp+78h+var_20], r12
0x1800825be  mov     [rsp+78h+var_28], r13
0x1800825c3  lea     r13, [rbx+20h]
0x1800825c7  mov     [rsp+78h+var_30], r14
0x1800825cc  mov     [rsp+78h+var_38], r15
0x1800825d1  cmp     r13, rbx
0x1800825d4  jnb     loc_180082978
0x1800825da  mov     r13, rbp
0x1800825dd  lea     r14, [rsi+28h]
0x1800825e1  mov     rax, [rsi+8]
0x1800825e5  test    rax, rax
0x1800825e8  jz      short loc_180082606
0x1800825ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800825ef  mov     rcx, [r14]; this
0x1800825f2  mov     rdx, r13; unsigned __int64
0x1800825f5  call    ?AllocPagesForBytes@PageAllocator@@QEAAPEAVPageAllocation@@_K@Z; PageAllocator::AllocPagesForBytes(unsigned __int64)
0x1800825fa  mov     rdi, rax
0x1800825fd  test    rax, rax
0x180082600  jnz     loc_180082752
0x180082606  lea     r8, [rbx+10h]
0x18008260a  cmp     r8, rbx
0x18008260d  cmovb   r8, rbp
0x180082611  call    ??$AllocateArray@UHeapAllocator@@D$00@@YAPEADPEAUHeapAllocator@@P80@EAAPEAD_K@Z1@Z; AllocateArray<HeapAllocator,char,1>(HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x180082616  mov     r9, rax
0x180082619  test    rax, rax
0x18008261c  jz      loc_180082BC1
0x180082622  mov     [rax+8], rbx
0x180082626  mov     rax, [rsi+20h]
0x18008262a  mov     [r9], rax
0x18008262d  mov     [rsi+20h], r9
0x180082631  add     r9, 10h
0x180082635  mov     dword ptr [rsi+50h], 2
0x18008263c  jmp     loc_1800827E1
0x180082641  mov     r8, [rsi+10h]
0x180082645  xor     r10d, r10d
0x180082648  mov     r11, r8
0x18008264b  mov     r9d, 0Ah
0x180082651  mov     rdx, [r8]
0x180082654  mov     rax, [rdx+18h]
0x180082658  mov     rcx, [rdx+8]
0x18008265c  sub     rcx, rax
0x18008265f  cmp     rcx, rbx
0x180082662  jb      short loc_1800826C5
0x180082664  lea     r9, [rdx+20h]
0x180082668  add     r9, rax
0x18008266b  add     rax, rbx
0x18008266e  mov     [rdx+18h], rax
0x180082672  mov     rax, [rsi+48h]
0x180082676  cmp     rcx, rax
0x180082679  jnz     short loc_1800826BE
0x18008267b  mov     [rsi+48h], r10
0x18008267f  mov     rax, [r8+8]
0x180082683  sub     rcx, rbx
0x180082686  sub     rax, [r8+18h]
0x18008268a  cmp     rcx, rax
0x18008268d  ja      short loc_1800826EA
0x18008268f  cmp     rcx, 10h
0x180082693  jnb     loc_180082591
0x180082699  cmp     byte ptr [rsi+38h], 0
0x18008269d  jnz     loc_180082591
0x1800826a3  mov     rax, [rdx]
0x1800826a6  mov     [r11], rax
0x1800826a9  mov     rax, [rsi+18h]
0x1800826ad  mov     [rdx], rax
0x1800826b0  mov     rax, r9
0x1800826b3  mov     [rsi+18h], rdx
0x1800826b7  add     rsp, 68h
0x1800826bb  pop     rsi
0x1800826bc  pop     rbx
0x1800826bd  retn
0x1800826be  cmp     r10, rax
0x1800826c1  jbe     short loc_18008267F
0x1800826c3  jmp     short loc_18008267B
0x1800826c5  cmp     r10, rcx
0x1800826c8  cmovbe  r10, rcx
0x1800826cc  sub     r9d, 1
0x1800826d0  jz      loc_1800825A5
0x1800826d6  mov     r11, rdx
0x1800826d9  mov     rdx, [rdx]
0x1800826dc  test    rdx, rdx
0x1800826df  jnz     loc_180082654
0x1800826e5  jmp     loc_1800825A5
0x1800826ea  mov     rax, [rdx]
0x1800826ed  mov     rcx, rsi
0x1800826f0  mov     [r11], rax
0x1800826f3  call    ?SetCacheBlock@?$ArenaAllocatorBase@VInPlaceFreeListPolicy@@@@AEAAXPEAUBigBlock@@@Z; ArenaAllocatorBase<InPlaceFreeListPolicy>::SetCacheBlock(BigBlock *)
0x1800826f8  mov     rax, r9
0x1800826fb  add     rsp, 68h
0x1800826ff  pop     rsi
0x180082700  pop     rbx
0x180082701  retn
0x180082702  dec     edi
0x180082704  mov     rdx, rax; ListEntry
0x180082707  mov     [rax+10h], edi
0x18008270a  mov     rcx, [rbp+80h]; ListHead
0x180082711  call    cs:__imp_InterlockedPushEntrySList
0x180082717  shl     edi, 0Ch
0x18008271a  add     rdi, [rsp+78h+var_50]
0x18008271f  test    rdi, rdi
0x180082722  jz      loc_180082807
0x180082728  cmp     dword ptr [rbp+98h], 0
0x18008272f  jz      loc_180082AB2
0x180082735  lea     r14, [rsi+28h]
0x180082739  test    rdi, rdi
0x18008273c  jz      loc_180082BB5
0x180082742  mov     [rdi], r12
0x180082745  mov     [rdi+8], r15
0x180082749  test    rdi, rdi
0x18008274c  jz      loc_180082B4C
0x180082752  lea     rdx, [rdi+10h]
0x180082756  mov     [rdx+10h], rdi
0x18008275a  mov     rax, [rdi]
0x18008275d  shl     rax, 0Ch
0x180082761  sub     rax, 30h ; '0'
0x180082765  mov     qword ptr [rdx+18h], 0
0x18008276d  mov     [rdx+8], rax
0x180082771  inc     dword ptr [rsi+50h]
0x180082774  mov     rcx, [rsi+10h]
0x180082778  test    rcx, rcx
0x18008277b  jz      short loc_1800827AC
0x18008277d  mov     rax, [rsi+30h]
0x180082781  sub     rax, rcx
0x180082784  sub     rax, 20h ; ' '
0x180082788  mov     [rcx+18h], rax
0x18008278c  mov     eax, [rsi+40h]
0x18008278f  sub     eax, [rsi+30h]
0x180082792  cmp     eax, 10h
0x180082795  jb      loc_1800828BA
0x18008279b  mov     ecx, eax
0x18008279d  mov     rax, [rsi+48h]
0x1800827a1  cmp     rax, rcx
0x1800827a4  cmovbe  rax, rcx
0x1800827a8  mov     [rsi+48h], rax
0x1800827ac  mov     rcx, [rdx+18h]
0x1800827b0  mov     rax, [rsi+10h]
0x1800827b4  add     rcx, 20h ; ' '
0x1800827b8  add     rcx, rdx
0x1800827bb  mov     [rsi+30h], rcx
0x1800827bf  mov     rcx, [rdx+8]
0x1800827c3  add     rcx, 20h ; ' '
0x1800827c7  add     rcx, rdx
0x1800827ca  mov     [rsi+40h], rcx
0x1800827ce  mov     [rdx], rax
0x1800827d1  mov     r9, [rsi+30h]
0x1800827d5  mov     [rsi+10h], rdx
0x1800827d9  lea     rax, [r9+rbx]
0x1800827dd  mov     [rsi+30h], rax
0x1800827e1  mov     r14, [rsp+78h+var_30]
0x1800827e6  mov     r13, [rsp+78h+var_28]
0x1800827eb  mov     r12, [rsp+78h+var_20]
0x1800827f0  mov     rdi, [rsp+78h+var_18]
0x1800827f5  mov     rbp, [rsp+78h+arg_10]
0x1800827fd  mov     r15, [rsp+78h+var_38]
0x180082802  jmp     loc_180082591
0x180082807  lea     r9, [rbp+8]
0x18008280b  mov     r8, [rbp+28h]
0x18008280f  lea     rax, [rbp+28h]
0x180082813  cmp     r8, rax
0x180082816  jnz     short loc_18008283E
0x180082818  lea     r8, [rsp+78h+var_48]; struct PageSegment **
0x18008281d  mov     edx, r14d; unsigned int
0x180082820  mov     rcx, rbp; this
0x180082823  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x180082828  mov     rdi, rax
0x18008282b  test    rax, rax
0x18008282e  jz      loc_180082AC1
0x180082834  mov     r15, [rsp+78h+var_48]
0x180082839  jmp     loc_180082728
0x18008283e  mov     rcx, [r8+8]
0x180082842  lea     r15, [r8+10h]
0x180082846  mov     rax, [r8]
0x180082849  mov     edx, [rbp+58h]
0x18008284c  mov     [rcx], rax
0x18008284f  mov     rcx, [r8]
0x180082852  mov     rax, [r8+8]
0x180082856  mov     [rcx+8], rax
0x18008285a  cmp     r14d, edx
0x18008285d  jz      loc_180082B1C
0x180082863  mov     rcx, [r9]
0x180082866  mov     rax, [rcx+8]
0x18008286a  mov     [r8+8], rax
0x18008286e  mov     [r8], rcx
0x180082871  mov     rax, [rcx+8]
0x180082875  mov     [rax], r8
0x180082878  mov     [rcx+8], r8
0x18008287c  mov     edx, r14d; unsigned int
0x18008287f  mov     rcx, r15; this
0x180082882  call    ?AllocPages@PageSegment@@QEAAPEADI@Z; PageSegment::AllocPages(uint)
0x180082887  mov     rdi, rax
0x18008288a  mov     eax, r14d
0x18008288d  shl     eax, 0Ch
0x180082890  mov     ecx, eax
0x180082892  add     [rbp+0A0h], rcx
0x180082899  lock xadd cs:qword_18043D988, rax
0x1800828a2  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x1800828a9  jz      loc_180082937
0x1800828af  lea     r8, [rax+rcx]
0x1800828b3  call    McTemplateU0x_EventWriteTransfer
0x1800828b8  jmp     short loc_180082937
0x1800828ba  cmp     byte ptr [rsi+38h], 0
0x1800828be  jnz     loc_18008279B
0x1800828c4  mov     rcx, [rsi+10h]
0x1800828c8  mov     rax, [rcx]
0x1800828cb  mov     [rsi+10h], rax
0x1800828cf  mov     rax, [rsi+18h]
0x1800828d3  mov     [rcx], rax
0x1800828d6  mov     [rsi+18h], rcx
0x1800828da  jmp     loc_1800827AC
0x1800828df  mov     ecx, r9d
0x1800828e2  lea     rdx, [rbp+8]
0x1800828e6  shl     r10d, cl
0x1800828e9  sub     r11d, r14d
0x1800828ec  shl     r9d, 0Ch
0x1800828f0  not     r10d
0x1800828f3  and     r10d, eax
0x1800828f6  mov     edi, r9d
0x1800828f9  mov     [r15+30h], r10d
0x1800828fd  mov     [r15+38h], r11d
0x180082901  add     rdi, [r15+10h]
0x180082905  jz      loc_1800829E6
0x18008290b  mov     eax, r14d
0x18008290e  shl     eax, 0Ch
0x180082911  mov     ecx, eax
0x180082913  add     [rbp+0A0h], rcx
0x18008291a  lock xadd cs:qword_18043D988, rax
0x180082923  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x18008292a  jnz     loc_180082BA2
0x180082930  cmp     dword ptr [r15+38h], 0
0x180082935  jz      short loc_180082940
0x180082937  sub     [rbp+68h], r14
0x18008293b  jmp     loc_180082728
0x180082940  mov     rcx, [r8+8]
0x180082944  mov     rax, [r8]
0x180082947  mov     [rcx], rax
0x18008294a  mov     rcx, [r8]
0x18008294d  mov     rax, [r8+8]
0x180082951  mov     [rcx+8], rax
0x180082955  mov     rcx, [rbp+18h]
0x180082959  mov     rax, [rcx+8]
0x18008295d  mov     [r8+8], rax
0x180082961  mov     [r8], rcx
0x180082964  mov     rax, [rcx+8]
0x180082968  mov     [rax], r8
0x18008296b  mov     [rcx+8], r8
0x18008296f  sub     [rbp+68h], r14
0x180082973  jmp     loc_180082728
0x180082978  lea     r12, [r13+100Fh]
0x18008297f  cmp     r12, r13
0x180082982  jb      loc_1800825DD
0x180082988  cmp     r12, rbp
0x18008298b  jz      loc_1800825DD
  ... truncated ...
```
