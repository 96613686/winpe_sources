# SmallHeapBlock::ReassignPages(Recycler *)

- ea: `0x1800290e8`
- end: `0x180029696`
- name: `?ReassignPages@SmallHeapBlock@@QEAAHPEAVRecycler@@@Z`
- size: `1454`
- prototype: `__int64 __fastcall(SmallHeapBlock *__hidden this, struct Recycler *)`
- caller_count: `10`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001f140`
- `0x18002893c`
- `0x180028c80`
- `0x180029a38`
- `0x18002a464`
- `0x180034410`
- `0x180036b00`
- `0x180068450`
- `0x1800dbe00`
- `0x180120910`

## callees

- `0x180008e7c`
- `0x1800215c0`
- `0x180022da4`
- `0x180026040`
- `0x180026314`
- `0x180028284`
- `0x1800290e8`
- `0x180161a60`
- `0x18016d384`
- `0x1801751c8`
- `0x1801cc26b`
- `0x18025a464`

## import_xrefs

- `msvcrt!free` at `0x180029648`
- `msvcrt!free` at `0x180029648`
- `KERNEL32!InterlockedPushEntrySList` at `0x18002954a`
- `KERNEL32!InterlockedPushEntrySList` at `0x18002954a`
- `KERNEL32!InterlockedPopEntrySList` at `0x180029513`
- `KERNEL32!InterlockedPopEntrySList` at `0x180029513`

## pseudocode

```c
__int64 __fastcall SmallHeapBlock::ReassignPages(SmallHeapBlock *this, struct Recycler *a2)
{
  bool v2; // zf
  char *v5; // rbx
  char *v6; // r15
  char *v7; // rdi
  struct PageSegment *v8; // rsi
  int v9; // r9d
  unsigned int v10; // r8d
  unsigned int v11; // edx
  unsigned int v12; // ecx
  __int64 v13; // rcx
  int v14; // r8d
  __int64 v15; // rdx
  char *v16; // rbp
  signed __int64 v17; // r8
  unsigned __int64 v18; // r15
  unsigned int v19; // ebx
  void **v20; // r14
  char *i; // rdi
  _DWORD *v22; // rcx
  unsigned int v23; // edi
  unsigned int v24; // r14d
  __int64 v25; // rdx
  unsigned int v26; // esi
  volatile signed __int32 *v27; // rdx
  char *v29; // rdi
  char *v30; // rcx
  PageAllocator *v31; // rcx
  union _SLIST_HEADER *v32; // rcx
  char *v33; // rdi
  int v34; // edx
  _QWORD *v35; // rcx
  __int64 v36; // rcx
  signed __int64 v37; // r8
  __int64 v38; // rcx
  PSLIST_ENTRY v39; // rax
  PSLIST_ENTRY v40; // r14
  int Next; // edi
  int v42; // edi
  char *v43; // rax
  void *v44; // rax
  void *v45; // rdi
  struct PageSegment *v46; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v47; // [rsp+28h] [rbp-50h]
  _DWORD *v48; // [rsp+30h] [rbp-48h]

  v2 = *((_BYTE *)this + 24) == 2;
  v46 = 0;
  if ( v2 )
    v5 = (char *)*((_QWORD *)a2 + 1);
  else
    v5 = (char *)a2 + 16;
  v2 = *((_DWORD *)v5 + 38) == 0;
  v5[139] = 1;
  if ( v2 )
    AsymetricCriticalSection::FastEnter((AsymetricCriticalSection *)(v5 + 200));
  v6 = v5 + 8;
  if ( *((_QWORD *)v5 + 13) )
  {
    v7 = v5 + 8;
    while ( 1 )
    {
      v7 = *(char **)v7;
      if ( v7 == v6 )
        break;
      v8 = (struct PageSegment *)(v7 + 16);
      v9 = *((_DWORD *)v7 + 18);
      if ( v9 )
      {
        v10 = *((_DWORD *)v7 + 16);
        v11 = -1;
        v2 = !_BitScanForward(&v12, v10);
        v47 = 0;
        if ( !v2 )
          v11 = v12;
        if ( v11 != -1 )
        {
          v13 = *((_QWORD *)v7 + 5) - *((unsigned int *)v7 + 12) - v11;
          if ( v13 )
          {
            v14 = v10 & ~(1 << v11);
            v15 = v11 << 12;
            *((_DWORD *)v7 + 16) = v14;
            *((_DWORD *)v7 + 18) = v9 - 1;
            v16 = (char *)(*((_QWORD *)v7 + 4) + (unsigned int)v15);
            if ( v16 )
            {
              *((_QWORD *)v5 + 20) += 4096LL;
              v17 = _InterlockedExchangeAdd64(&qword_180443988, 0x1000u);
              if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
                McTemplateU0x_EventWriteTransfer(v13, v15, v17 + 4096);
              if ( !*((_DWORD *)v7 + 18) )
              {
                **((_QWORD **)v7 + 1) = *(_QWORD *)v7;
                *(_QWORD *)(*(_QWORD *)v7 + 8LL) = *((_QWORD *)v7 + 1);
                v38 = *((_QWORD *)v5 + 3);
                *((_QWORD *)v7 + 1) = *(_QWORD *)(v38 + 8);
                *(_QWORD *)v7 = v38;
                **(_QWORD **)(v38 + 8) = v7;
                *(_QWORD *)(v38 + 8) = v7;
              }
              goto LABEL_18;
            }
          }
        }
      }
    }
    v32 = (union _SLIST_HEADER *)*((_QWORD *)v5 + 16);
    if ( v32 )
    {
      v39 = InterlockedPopEntrySList(v32);
      v40 = v39;
      if ( v39 )
      {
        v8 = (struct PageSegment *)*((_QWORD *)&v39->Next + 1);
        Next = (int)v39[1].Next;
        v46 = v8;
        if ( Next == 1 )
        {
          v16 = (char *)v39;
          *v39 = 0;
          v39[1] = 0;
        }
        else
        {
          v42 = Next - 1;
          LODWORD(v39[1].Next) = v42;
          InterlockedPushEntrySList(*((PSLIST_HEADER *)v5 + 16), v39);
          v16 = (char *)v40 + (unsigned int)(v42 << 12);
        }
        if ( v16 )
          goto LABEL_19;
      }
    }
  }
  v33 = (char *)*((_QWORD *)v5 + 5);
  if ( v33 != v5 + 40 )
  {
    v8 = (struct PageSegment *)(v33 + 16);
    v34 = *((_DWORD *)v5 + 22);
    **((_QWORD **)v33 + 1) = *(_QWORD *)v33;
    *(_QWORD *)(*(_QWORD *)v33 + 8LL) = *((_QWORD *)v33 + 1);
    if ( v34 == 1 )
      v35 = (_QWORD *)*((_QWORD *)v5 + 3);
    else
      v35 = *(_QWORD **)v6;
    *((_QWORD *)v33 + 1) = v35[1];
    *(_QWORD *)v33 = v35;
    *(_QWORD *)v35[1] = v33;
    v35[1] = v33;
    goto LABEL_53;
  }
  v16 = PageAllocator::TryAllocDecommitedPages((PageAllocator *)v5, 1u, &v46);
  if ( v16 )
  {
LABEL_61:
    v8 = v46;
    goto LABEL_19;
  }
  v8 = (struct PageSegment *)PageAllocator::AddPageSegment((PageAllocator *)v5);
  if ( !v8 )
  {
    v16 = 0;
    goto LABEL_61;
  }
LABEL_53:
  v16 = PageSegment::AllocPages(v8, 1u);
  *((_QWORD *)v5 + 20) += 4096LL;
  v37 = _InterlockedExchangeAdd64(&qword_180443988, 0x1000u);
  if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
    McTemplateU0x_EventWriteTransfer(v36, v15, v37 + 4096);
LABEL_18:
  --*((_QWORD *)v5 + 13);
LABEL_19:
  if ( !*((_DWORD *)v5 + 38) )
    *((_DWORD *)v5 + 60) = 0;
  if ( v16 )
  {
    ++*((_QWORD *)a2 + 66);
    v18 = 1;
    v19 = 0x100000 - ((unsigned int)v16 >> 12);
    *((_QWORD *)this + 2) = v8;
    *((_QWORD *)this + 1) = v16;
    if ( v19 > 1 )
      v19 = 1;
    while ( 2 )
    {
      v20 = (void **)((char *)a2 + 360);
LABEL_25:
      for ( i = (char *)*v20; i; i = (char *)*((_QWORD *)i + 1) )
      {
        if ( *(_DWORD *)i == HIDWORD(v16) )
          goto LABEL_28;
      }
      v43 = (char *)operator new[]<HeapAllocator>(32800, v15, 1, HeapAllocator::NoThrowAllocZero);
      i = v43;
      if ( v43 )
      {
        memset_0(v43, 0, 0x8020u);
        *(_DWORD *)i = HIDWORD(v16);
        *((_QWORD *)i + 1) = *v20;
        *v20 = i;
LABEL_28:
        v22 = i + 16;
        v23 = (unsigned __int8)((unsigned int)v16 >> 12);
        v24 = v19;
        v25 = (unsigned int)v16 >> 20;
        v48 = v22;
        v26 = v19;
        if ( v19 >= 256 - v23 )
          v24 = 256 - v23;
        while ( 1 )
        {
          LODWORD(v46) = v25;
          v27 = *(volatile signed __int32 **)&v22[2 * v25 + 2];
          v47 = v23;
          if ( v27 )
          {
            if ( v23 < v24 + v23 )
            {
              memset64((void *)&v27[2 * v23 + 2], (unsigned __int64)this, v24);
              v22 = v48;
            }
            _InterlockedAdd(v27, v24);
            v15 = (unsigned int)v46;
          }
          else
          {
            v44 = (void *)operator new[]<HeapAllocator>(2056, 0, 1, HeapAllocator::NoThrowAllocZero);
            v45 = v44;
            if ( !v44 )
              goto LABEL_82;
            memset_0(v44, 0, 0x808u);
            if ( !HeapBlockMap32::L2MapChunk::Set((HeapBlockMap32::L2MapChunk *)v45, v47, v24, this) )
            {
              free(v45);
LABEL_82:
              if ( v19 != v26 )
                HeapBlockMap32::ClearHeapBlockImpl<0>(v48, v16, v19 - v26);
              v20 = (void **)((char *)a2 + 360);
              goto LABEL_85;
            }
            v22 = v48;
            v15 = (unsigned int)v46;
            *(_QWORD *)&v48[2 * (unsigned int)v46 + 2] = v45;
            ++*v22;
          }
          v26 -= v24;
          if ( !v26 )
            break;
          v24 = 256;
          v23 = 0;
          v25 = (unsigned int)(v15 + 1);
          if ( v26 < 0x100 )
            v24 = v26;
        }
        v18 -= v19;
        if ( !v18 )
          return 1;
        v20 = (void **)((char *)a2 + 360);
        v16 += 4096 * (unsigned __int64)v19;
        v19 = 0x100000;
        if ( v18 < 0x100000 )
        {
          v19 = v18;
          continue;
        }
        goto LABEL_25;
      }
      break;
    }
LABEL_85:
    if ( v18 != 1 )
      HeapBlockMap64::ClearHeapBlockImpl<0>(v20, v16, 1 - v18);
    v29 = (char *)a2 + 16;
    if ( *((_BYTE *)this + 24) == 2 )
      v30 = (char *)*((_QWORD *)a2 + 1);
    else
      v30 = (char *)a2 + 16;
    if ( !*((_DWORD *)v30 + 38) )
      AsymetricCriticalSection::FastEnter((AsymetricCriticalSection *)(v30 + 200));
    if ( *((_BYTE *)this + 24) == 2 )
      v31 = (PageAllocator *)*((_QWORD *)a2 + 1);
    else
      v31 = (struct Recycler *)((char *)a2 + 16);
    PageAllocator::ReleasePages(v31, *((void **)this + 1), 1u, *((struct PageSegment **)this + 2));
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 1) = 0;
    if ( *((_BYTE *)this + 24) == 2 )
      v29 = (char *)*((_QWORD *)a2 + 1);
    if ( !*((_DWORD *)v29 + 38) )
      *((_DWORD *)v29 + 60) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800290e8  mov     rax, rsp
0x1800290eb  mov     [rax+18h], rbx
0x1800290ef  mov     [rax+10h], rdx
0x1800290f3  mov     [rax+8], rcx
0x1800290f7  push    rbp
0x1800290f8  push    rsi
0x1800290f9  push    rdi
0x1800290fa  push    r12
0x1800290fc  push    r13
0x1800290fe  push    r14
0x180029100  push    r15
0x180029102  sub     rsp, 40h
0x180029106  cmp     byte ptr [rcx+18h], 2
0x18002910a  mov     r13, rcx
0x18002910d  mov     qword ptr [rax-58h], 0
0x180029115  mov     r12, rdx
0x180029118  jz      loc_18002946C
0x18002911e  lea     rbx, [rdx+10h]
0x180029122  cmp     dword ptr [rbx+98h], 0
0x180029129  mov     ebp, 1
0x18002912e  mov     [rbx+8Bh], bpl
0x180029135  jz      loc_1800294F7
0x18002913b  lea     r15, [rbx+8]
0x18002913f  cmp     [rbx+68h], rbp
0x180029143  jb      loc_180029358
0x180029149  mov     rdi, r15
0x18002914c  or      r10d, 0FFFFFFFFh
0x180029150  mov     rdi, [rdi]
0x180029153  cmp     rdi, r15
0x180029156  jz      loc_180029348
0x18002915c  lea     rsi, [rdi+10h]
0x180029160  mov     r9d, [rsi+38h]
0x180029164  cmp     r9d, ebp
0x180029167  jb      short loc_180029150
0x180029169  mov     r8d, [rsi+30h]
0x18002916d  mov     edx, r10d
0x180029170  bsf     ecx, r8d
0x180029174  mov     [rsp+78h+var_50], 0
0x18002917c  setnz   al
0x18002917f  test    al, al
0x180029181  cmovnz  edx, ecx
0x180029184  cmp     edx, r10d
0x180029187  jz      short loc_180029150
0x180029189  mov     eax, [rsi+20h]
0x18002918c  mov     rcx, [rsi+18h]
0x180029190  sub     rcx, rax
0x180029193  mov     eax, edx
0x180029195  sub     rcx, rax
0x180029198  cmp     rcx, rbp
0x18002919b  jb      short loc_180029150
0x18002919d  btr     r8d, edx
0x1800291a1  shl     edx, 0Ch
0x1800291a4  mov     [rsi+30h], r8d
0x1800291a8  lea     eax, [r9-1]
0x1800291ac  mov     ebp, edx
0x1800291ae  mov     [rsi+38h], eax
0x1800291b1  add     rbp, [rsi+10h]
0x1800291b5  jz      loc_18002943E
0x1800291bb  mov     r8d, 1000h
0x1800291c1  add     [rbx+0A0h], r8
0x1800291c8  lock xadd cs:qword_180443988, r8
0x1800291d1  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x1800291d8  jnz     loc_180029595
0x1800291de  cmp     dword ptr [rsi+38h], 0
0x1800291e2  jz      loc_18002940A
0x1800291e8  dec     qword ptr [rbx+68h]
0x1800291ec  cmp     dword ptr [rbx+98h], 0
0x1800291f3  jz      loc_1800294BB
0x1800291f9  test    rbp, rbp
0x1800291fc  jz      loc_18002932D
0x180029202  mov     r8d, 1
0x180029208  mov     eax, ebp
0x18002920a  add     [r12+210h], r8
0x180029212  mov     ebx, 100000h
0x180029217  shr     eax, 0Ch
0x18002921a  mov     r15d, r8d
0x18002921d  sub     ebx, eax
0x18002921f  mov     [r13+10h], rsi
0x180029223  cmp     ebx, r8d
0x180029226  mov     [r13+8], rbp
0x18002922a  cmova   ebx, r8d
0x18002922e  lea     r14, [r12+168h]
0x180029236  mov     rdi, [r14]
0x180029239  mov     rsi, rbp
0x18002923c  shr     rsi, 20h
0x180029240  test    rdi, rdi
0x180029243  jz      loc_1800295A6
0x180029249  cmp     [rdi], esi
0x18002924b  jnz     loc_180029401
0x180029251  lea     rcx, [rdi+10h]
0x180029255  mov     eax, ebp
0x180029257  shr     eax, 0Ch
0x18002925a  mov     edx, ebp
0x18002925c  movzx   edi, al
0x18002925f  mov     r14d, ebx
0x180029262  mov     eax, 100h
0x180029267  shr     edx, 14h
0x18002926a  sub     eax, edi
0x18002926c  mov     [rsp+78h+var_48], rcx
0x180029271  cmp     ebx, eax
0x180029273  mov     esi, ebx
0x180029275  cmovnb  r14d, eax
0x180029279  mov     dword ptr [rsp+78h+var_58], edx
0x18002927d  mov     rdx, [rcx+rdx*8+8]
0x180029282  mov     [rsp+78h+var_50], edi
0x180029286  test    rdx, rdx
0x180029289  jz      loc_1800295EA
0x18002928f  lea     eax, [r14+rdi]
0x180029293  cmp     edi, eax
0x180029295  jnb     short loc_1800292AE
0x180029297  mov     eax, edi
0x180029299  inc     rax
0x18002929c  mov     ecx, r14d
0x18002929f  lea     rdi, [rdx+rax*8]
0x1800292a3  mov     rax, r13
0x1800292a6  rep stosq
0x1800292a9  mov     rcx, [rsp+78h+var_48]
0x1800292ae  lock add [rdx], r14d
0x1800292b2  mov     edx, dword ptr [rsp+78h+var_58]
0x1800292b6  sub     esi, r14d
0x1800292b9  jnz     loc_1800293EA
0x1800292bf  mov     eax, ebx
0x1800292c1  sub     r15, rax
0x1800292c4  jnz     loc_180029494
0x1800292ca  mov     eax, r8d
0x1800292cd  jmp     short loc_18002932F
0x1800292cf  mov     bpl, 2
0x1800292d2  lea     rdi, [r12+10h]
0x1800292d7  cmp     [r13+18h], bpl
0x1800292db  jz      loc_180029476
0x1800292e1  mov     rcx, rdi
0x1800292e4  xor     ebx, ebx
0x1800292e6  cmp     [rcx+98h], ebx
0x1800292ec  jz      loc_18002956C
0x1800292f2  cmp     [r13+18h], bpl
0x1800292f6  jz      loc_180029480
0x1800292fc  mov     rcx, rdi; this
0x1800292ff  mov     r9, [r13+10h]; struct PageSegment *
0x180029303  mov     r8d, esi; unsigned int
0x180029306  mov     rdx, [r13+8]; void *
0x18002930a  call    ?ReleasePages@PageAllocator@@QEAAXPEAXIPEAVPageSegment@@@Z; PageAllocator::ReleasePages(void *,uint,PageSegment *)
0x18002930f  mov     [r13+10h], rbx
0x180029313  mov     [r13+8], rbx
0x180029317  cmp     [r13+18h], bpl
0x18002931b  jz      loc_18002948A
0x180029321  cmp     [rdi+98h], ebx
0x180029327  jz      loc_180029508
0x18002932d  xor     eax, eax
0x18002932f  mov     rbx, [rsp+78h+arg_10]
0x180029337  add     rsp, 40h
0x18002933b  pop     r15
0x18002933d  pop     r14
0x18002933f  pop     r13
0x180029341  pop     r12
0x180029343  pop     rdi
0x180029344  pop     rsi
0x180029345  pop     rbp
0x180029346  retn
0x180029348  mov     rcx, [rbx+80h]; ListHead
0x18002934f  test    rcx, rcx
0x180029352  jnz     loc_180029513
0x180029358  lea     rax, [rbx+28h]
0x18002935c  mov     rdi, [rax]
0x18002935f  cmp     rdi, rax
0x180029362  jz      loc_180029448
0x180029368  mov     rcx, [rdi+8]
0x18002936c  lea     rsi, [rdi+10h]
0x180029370  mov     rax, [rdi]
0x180029373  mov     edx, [rbx+58h]
0x180029376  mov     [rcx], rax
0x180029379  mov     rcx, [rdi]
0x18002937c  mov     rax, [rdi+8]
0x180029380  mov     [rcx+8], rax
0x180029384  cmp     edx, 1
0x180029387  jz      loc_18002957D
0x18002938d  mov     rcx, [r15]
0x180029390  mov     rax, [rcx+8]
0x180029394  mov     [rdi+8], rax
0x180029398  mov     [rdi], rcx
0x18002939b  mov     rax, [rcx+8]
0x18002939f  mov     [rax], rdi
0x1800293a2  mov     [rcx+8], rdi
0x1800293a6  mov     edx, 1; unsigned int
0x1800293ab  mov     rcx, rsi; this
0x1800293ae  call    ?AllocPages@PageSegment@@QEAAPEADI@Z; PageSegment::AllocPages(uint)
0x1800293b3  mov     r8d, 1000h
0x1800293b9  mov     rbp, rax
0x1800293bc  add     [rbx+0A0h], r8
0x1800293c3  lock xadd cs:qword_180443988, r8
0x1800293cc  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x1800293d3  jz      loc_1800291E8
0x1800293d9  add     r8, 1000h
0x1800293e0  call    McTemplateU0x_EventWriteTransfer
0x1800293e5  jmp     loc_1800291E8
0x1800293ea  mov     r14d, 100h
0x1800293f0  xor     edi, edi
0x1800293f2  add     edx, r8d
0x1800293f5  cmp     esi, r14d
0x1800293f8  cmovb   r14d, esi
0x1800293fc  jmp     loc_180029279
0x180029401  mov     rdi, [rdi+8]
0x180029405  jmp     loc_180029240
0x18002940a  mov     rcx, [rdi+8]
0x18002940e  mov     rax, [rdi]
0x180029411  mov     [rcx], rax
0x180029414  mov     rcx, [rdi]
0x180029417  mov     rax, [rdi+8]
0x18002941b  mov     [rcx+8], rax
0x18002941f  mov     rcx, [rbx+18h]
0x180029423  mov     rax, [rcx+8]
0x180029427  mov     [rdi+8], rax
0x18002942b  mov     [rdi], rcx
0x18002942e  mov     rax, [rcx+8]
0x180029432  mov     [rax], rdi
0x180029435  mov     [rcx+8], rdi
0x180029439  jmp     loc_1800291E8
0x18002943e  mov     ebp, 1
0x180029443  jmp     loc_180029150
0x180029448  lea     r8, [rsp+78h+var_58]; struct PageSegment **
0x18002944d  mov     edx, 1; unsigned int
0x180029452  mov     rcx, rbx; this
0x180029455  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x18002945a  mov     rbp, rax
0x18002945d  test    rax, rax
0x180029460  jz      short loc_1800294CA
0x180029462  mov     rsi, [rsp+78h+var_58]
0x180029467  jmp     loc_1800291EC
0x18002946c  mov     rbx, [r12+8]
0x180029471  jmp     loc_180029122
0x180029476  mov     rcx, [r12+8]
0x18002947b  jmp     loc_1800292E4
0x180029480  mov     rcx, [r12+8]
0x180029485  jmp     loc_1800292FF
0x18002948a  mov     rdi, [r12+8]
0x18002948f  jmp     loc_180029321
0x180029494  shl     rax, 0Ch
0x180029498  lea     r14, [r12+168h]
0x1800294a0  add     rbp, rax
0x1800294a3  mov     eax, 100000h
0x1800294a8  mov     ebx, eax
0x1800294aa  cmp     r15, rax
0x1800294ad  jnb     loc_180029236
0x1800294b3  mov     ebx, r15d
0x1800294b6  jmp     loc_18002922E
0x1800294bb  mov     dword ptr [rbx+0F0h], 0
0x1800294c5  jmp     loc_1800291F9
0x1800294ca  cmp     dword ptr [rbx+58h], 1
0x1800294ce  mov     edx, 18h
0x1800294d3  mov     rcx, rbx; this
0x1800294d6  lea     eax, [rdx-10h]
0x1800294d9  cmovnz  edx, eax
0x1800294dc  add     rdx, rbx
0x1800294df  call    ?AddPageSegment@PageAllocator@@IEAAPEAVPageSegment@@AEAV?$DListBase@VPageSegment@@@@@Z; PageAllocator::AddPageSegment(DListBase<PageSegment> &)
0x1800294e4  mov     rsi, rax
0x1800294e7  test    rax, rax
0x1800294ea  jnz     loc_1800293A6
0x1800294f0  xor     ebp, ebp
0x1800294f2  jmp     loc_180029462
0x1800294f7  lea     rcx, [rbx+0C8h]; this
0x1800294fe  call    ?FastEnter@AsymetricCriticalSection@@QEAAXXZ; AsymetricCriticalSection::FastEnter(void)
0x180029503  jmp     loc_18002913B
0x180029508  mov     [rdi+0F0h], ebx
0x18002950e  jmp     loc_18002932D
0x180029513  call    cs:__imp_InterlockedPopEntrySList
0x18002951a  nop     dword ptr [rax+rax+00h]
0x18002951f  mov     r14, rax
0x180029522  test    rax, rax
0x180029525  jz      loc_180029358
0x18002952b  mov     rsi, [rax+8]
0x18002952f  mov     edi, [rax+10h]
0x180029532  mov     [rsp+78h+var_58], rsi
0x180029537  cmp     edi, ebp
0x180029539  jz      short loc_180029586
0x18002953b  dec     edi
0x18002953d  mov     rdx, rax; ListEntry
0x180029540  mov     [rax+10h], edi
0x180029543  mov     rcx, [rbx+80h]; ListHead
0x18002954a  call    cs:__imp_InterlockedPushEntrySList
0x180029551  nop     dword ptr [rax+rax+00h]
0x180029556  shl     edi, 0Ch
0x180029559  mov     ebp, edi
0x18002955b  add     rbp, r14
0x18002955e  test    rbp, rbp
0x180029561  jnz     loc_1800291EC
0x180029567  jmp     loc_180029358
0x18002956c  add     rcx, 0C8h; this
0x180029573  call    ?FastEnter@AsymetricCriticalSection@@QEAAXXZ; AsymetricCriticalSection::FastEnter(void)
0x180029578  jmp     loc_1800292F2
0x18002957d  mov     rcx, [rbx+18h]
0x180029581  jmp     loc_180029390
0x180029586  xorps   xmm0, xmm0
0x180029589  mov     rbp, r14
0x18002958c  movups  xmmword ptr [rax], xmm0
0x18002958f  movups  xmmword ptr [rax+10h], xmm0
0x180029593  jmp     short loc_18002955E
0x180029595  add     r8, 1000h
0x18002959c  call    McTemplateU0x_EventWriteTransfer
0x1800295a1  jmp     loc_1800291DE
0x1800295a6  lea     r9, ?NoThrowAllocZero@HeapAllocator@@QEAAPEAD_K@Z; HeapAllocator::NoThrowAllocZero(unsigned __int64)
0x1800295ad  mov     ecx, 8020h
  ... truncated ...
```
