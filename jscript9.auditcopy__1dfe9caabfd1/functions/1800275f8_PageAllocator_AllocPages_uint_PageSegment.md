# PageAllocator::AllocPages(uint,PageSegment * *)

- ea: `0x1800275f8`
- end: `0x18002791c`
- name: `?AllocPages@PageAllocator@@QEAAPEADIPEAPEAVPageSegment@@@Z`
- size: `804`
- prototype: `char *__fastcall(PageAllocator *__hidden this, unsigned int, struct PageSegment **)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000d060`
- `0x1800266f0`
- `0x180127874`

## callees

- `0x180008e7c`
- `0x1800215c0`
- `0x180026314`
- `0x1800275f8`
- `0x180028284`
- `0x18025a464`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x1800277b7`
- `KERNEL32!InterlockedPushEntrySList` at `0x1800277b7`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800278c7`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800278c7`

## pseudocode

```c
char *__fastcall PageAllocator::AllocPages(PageAllocator *this, unsigned int a2, struct PageSegment **a3)
{
  bool v3; // zf
  char *v5; // r15
  char *v6; // r14
  PageSegment *v7; // rbp
  unsigned int v8; // ebx
  unsigned int v9; // eax
  unsigned int v10; // r10d
  unsigned int v11; // edx
  unsigned int v12; // r9d
  unsigned __int64 v13; // rdx
  unsigned int v14; // r8d
  char *v15; // rbx
  __int64 v16; // rsi
  __int64 v17; // rcx
  union _SLIST_HEADER *v18; // rcx
  PageAllocator *v19; // r8
  __int64 v20; // rdx
  int v21; // ebx
  __int64 v23; // rcx
  int v24; // edx
  __int64 v25; // rcx
  __int64 v26; // rsi
  __int64 v27; // rdx
  __int64 v28; // rcx
  PSLIST_ENTRY v29; // rax
  PSLIST_ENTRY v30; // rbp
  int Next; // ebx

  v3 = *((_DWORD *)this + 38) == 0;
  *((_BYTE *)this + 139) = 1;
  if ( v3 )
    AsymetricCriticalSection::FastEnter((PageAllocator *)((char *)this + 200));
  v5 = (char *)this + 8;
  if ( *((_QWORD *)this + 13) < (unsigned __int64)a2 )
    goto LABEL_25;
  v6 = (char *)this + 8;
LABEL_5:
  while ( 1 )
  {
    v6 = *(char **)v6;
    if ( v6 == v5 )
      break;
    v7 = (PageSegment *)(v6 + 16);
    v8 = *((_DWORD *)v6 + 18);
    if ( v8 >= a2 )
    {
      v9 = *((_DWORD *)v6 + 16);
      v10 = -1;
      v3 = !_BitScanForward(&v11, v9);
      if ( !v3 )
        v10 = v11;
      v12 = 0xFFFFFFFF >> (32 - a2);
      while ( v10 != -1 )
      {
        v13 = *((_QWORD *)v6 + 5) - v10 - *((unsigned int *)v6 + 12);
        if ( v13 < a2 )
          break;
        if ( a2 == 1 || (v13 = v12 << v10, (v9 & (v12 << v10)) == (_DWORD)v13) )
        {
          *((_DWORD *)v6 + 16) = v9 & ~(v12 << v10);
          *((_DWORD *)v6 + 18) = v8 - a2;
          v15 = (char *)(*((_QWORD *)v6 + 4) + (v10 << 12));
          if ( !v15 )
            goto LABEL_5;
          v16 = a2 << 12;
          *((_QWORD *)this + 20) += (unsigned int)v16;
          v17 = _InterlockedExchangeAdd64(&qword_180443988, (unsigned int)v16);
          if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
            McTemplateU0x_EventWriteTransfer(v17, v13, v16 + v17);
          if ( !*((_DWORD *)v6 + 18) )
          {
            **((_QWORD **)v6 + 1) = *(_QWORD *)v6;
            *(_QWORD *)(*(_QWORD *)v6 + 8LL) = *((_QWORD *)v6 + 1);
            v23 = *((_QWORD *)this + 3);
            *((_QWORD *)v6 + 1) = *(_QWORD *)(v23 + 8);
            *(_QWORD *)v6 = v23;
            **(_QWORD **)(v23 + 8) = v6;
            *(_QWORD *)(v23 + 8) = v6;
          }
          goto LABEL_22;
        }
        v3 = !_BitScanForward(&v14, v9 & (-1 << (v10 + 1)));
        v10 = -1;
        if ( !v3 )
          v10 = v14;
      }
    }
  }
  if ( a2 != 1 )
    goto LABEL_25;
  v18 = (union _SLIST_HEADER *)*((_QWORD *)this + 16);
  if ( !v18 )
    goto LABEL_25;
  v29 = InterlockedPopEntrySList(v18);
  v30 = v29;
  if ( !v29 )
    goto LABEL_25;
  *a3 = (struct PageSegment *)*((_QWORD *)&v29->Next + 1);
  Next = (int)v29[1].Next;
  if ( Next == 1 )
  {
    v15 = (char *)v29;
    *v29 = 0;
    v29[1] = 0;
  }
  else
  {
    v21 = Next - 1;
    LODWORD(v29[1].Next) = v21;
    InterlockedPushEntrySList(*((PSLIST_HEADER *)this + 16), v29);
    v15 = (char *)v30 + (unsigned int)(v21 << 12);
  }
  if ( !v15 )
  {
LABEL_25:
    v19 = (PageAllocator *)*((_QWORD *)this + 5);
    if ( v19 == (PageAllocator *)((char *)this + 40) )
    {
      v15 = PageAllocator::TryAllocDecommitedPages(this, a2, a3);
      if ( v15 )
        goto LABEL_33;
      v20 = 24;
      if ( a2 != *((_DWORD *)this + 22) )
        v20 = 8;
      v7 = (PageSegment *)PageAllocator::AddPageSegment(this, (__int64)this + v20);
      if ( !v7 )
        goto LABEL_33;
    }
    else
    {
      v7 = (PageAllocator *)((char *)v19 + 16);
      v24 = *((_DWORD *)this + 22);
      **((_QWORD **)v19 + 1) = *(_QWORD *)v19;
      *(_QWORD *)(*(_QWORD *)v19 + 8LL) = *((_QWORD *)v19 + 1);
      if ( a2 == v24 )
        v25 = *((_QWORD *)this + 3);
      else
        v25 = *(_QWORD *)v5;
      *((_QWORD *)v19 + 1) = *(_QWORD *)(v25 + 8);
      *(_QWORD *)v19 = v25;
      **(_QWORD **)(v25 + 8) = v19;
      *(_QWORD *)(v25 + 8) = v19;
    }
    v26 = a2 << 12;
    v15 = PageSegment::AllocPages(v7, a2);
    *((_QWORD *)this + 20) += (unsigned int)v26;
    v28 = _InterlockedExchangeAdd64(&qword_180443988, (unsigned int)v26);
    if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
      McTemplateU0x_EventWriteTransfer(v28, v27, v26 + v28);
LABEL_22:
    *((_QWORD *)this + 13) -= a2;
    *a3 = v7;
  }
LABEL_33:
  if ( !*((_DWORD *)this + 38) )
    *((_DWORD *)this + 60) = 0;
  return v15;
}

```

## disassembly

```asm
0x1800275f8  mov     rax, rsp
0x1800275fb  mov     [rax+20h], rbx
0x1800275ff  mov     [rax+18h], r8
0x180027603  mov     [rax+10h], edx
0x180027606  mov     [rax+8], rcx
0x18002760a  push    rbp
0x18002760b  push    rsi
0x18002760c  push    rdi
0x18002760d  push    r12
0x18002760f  push    r13
0x180027611  push    r14
0x180027613  push    r15
0x180027615  sub     rsp, 30h
0x180027619  cmp     dword ptr [rcx+98h], 0
0x180027620  mov     rdi, rcx
0x180027623  mov     byte ptr [rcx+8Bh], 1
0x18002762a  jz      loc_1800278B6
0x180027630  mov     esi, [rsp+68h+arg_8]
0x180027634  lea     r15, [rdi+8]
0x180027638  mov     r13d, esi
0x18002763b  mov     r12, [rsp+68h+arg_10]
0x180027643  cmp     [rdi+68h], rsi
0x180027647  jb      loc_18002775E
0x18002764d  mov     r11d, 20h ; ' '
0x180027653  mov     r14, r15
0x180027656  sub     r11d, esi
0x180027659  or      r8d, 0FFFFFFFFh
0x18002765d  mov     r14, [r14]
0x180027660  cmp     r14, r15
0x180027663  jz      loc_180027749
0x180027669  lea     rbp, [r14+10h]
0x18002766d  mov     ebx, [rbp+38h]
0x180027670  cmp     ebx, esi
0x180027672  jb      short loc_18002765D
0x180027674  mov     eax, [rbp+30h]
0x180027677  mov     r10d, r8d
0x18002767a  bsf     edx, eax
0x18002767d  mov     r9d, r8d
0x180027680  setnz   cl
0x180027683  test    cl, cl
0x180027685  mov     ecx, r11d
0x180027688  cmovnz  r10d, edx
0x18002768c  shr     r9d, cl
0x18002768f  mov     [rsp+68h+var_48], 0
0x180027697  cmp     r10d, r8d
0x18002769a  jz      short loc_18002765D
0x18002769c  mov     rdx, [rbp+18h]
0x1800276a0  mov     ecx, r10d
0x1800276a3  sub     rdx, rcx
0x1800276a6  mov     ecx, [rbp+20h]
0x1800276a9  sub     rdx, rcx
0x1800276ac  cmp     rdx, r13
0x1800276af  jb      short loc_18002765D
0x1800276b1  cmp     esi, 1
0x1800276b4  jz      short loc_1800276E8
0x1800276b6  mov     ecx, r10d
0x1800276b9  mov     edx, r9d
0x1800276bc  shl     edx, cl
0x1800276be  mov     ecx, edx
0x1800276c0  and     ecx, eax
0x1800276c2  cmp     ecx, edx
0x1800276c4  jz      short loc_1800276E8
0x1800276c6  lea     ecx, [r10+1]
0x1800276ca  mov     edx, r8d
0x1800276cd  shl     edx, cl
0x1800276cf  and     edx, eax
0x1800276d1  bsf     r8d, edx
0x1800276d5  setnz   cl
0x1800276d8  or      r10d, 0FFFFFFFFh
0x1800276dc  test    cl, cl
0x1800276de  cmovnz  r10d, r8d
0x1800276e2  or      r8d, 0FFFFFFFFh
0x1800276e6  jmp     short loc_18002768F
0x1800276e8  sub     ebx, esi
0x1800276ea  mov     ecx, r10d
0x1800276ed  shl     r9d, cl
0x1800276f0  shl     r10d, 0Ch
0x1800276f4  not     r9d
0x1800276f7  and     r9d, eax
0x1800276fa  mov     [rbp+30h], r9d
0x1800276fe  mov     [rbp+38h], ebx
0x180027701  mov     ebx, r10d
0x180027704  add     rbx, [rbp+10h]
0x180027708  jz      loc_18002765D
0x18002770e  shl     esi, 0Ch
0x180027711  mov     eax, esi
0x180027713  add     [rdi+0A0h], rax
0x18002771a  mov     ecx, esi
0x18002771c  lock xadd cs:qword_180443988, rcx
0x180027725  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x18002772c  jnz     loc_18002790E
0x180027732  cmp     dword ptr [rbp+38h], 0
0x180027736  jz      loc_1800277F7
0x18002773c  sub     [rdi+68h], r13
0x180027740  mov     [r12], rbp
0x180027744  jmp     loc_1800277CE
0x180027749  cmp     esi, 1
0x18002774c  jnz     short loc_18002775E
0x18002774e  mov     rcx, [rdi+80h]; ListHead
0x180027755  test    rcx, rcx
0x180027758  jnz     loc_1800278C7
0x18002775e  lea     rax, [rdi+28h]
0x180027762  mov     r8, [rax]
0x180027765  cmp     r8, rax
0x180027768  jnz     loc_18002782B
0x18002776e  mov     r8, r12; struct PageSegment **
0x180027771  mov     edx, esi; unsigned int
0x180027773  mov     rcx, rdi; this
0x180027776  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x18002777b  mov     rbx, rax
0x18002777e  test    rax, rax
0x180027781  jnz     short loc_1800277CE
0x180027783  cmp     esi, [rdi+58h]
0x180027786  lea     edx, [rax+18h]
0x180027789  lea     eax, [rbx+8]
0x18002778c  mov     rcx, rdi; this
0x18002778f  cmovnz  edx, eax
0x180027792  add     rdx, rdi
0x180027795  call    ?AddPageSegment@PageAllocator@@IEAAPEAVPageSegment@@AEAV?$DListBase@VPageSegment@@@@@Z; PageAllocator::AddPageSegment(DListBase<PageSegment> &)
0x18002779a  mov     rbp, rax
0x18002779d  test    rax, rax
0x1800277a0  jnz     loc_180027868
0x1800277a6  jmp     short loc_1800277CE
0x1800277a8  dec     ebx
0x1800277aa  mov     rdx, rbp; ListEntry
0x1800277ad  mov     [rax+10h], ebx
0x1800277b0  mov     rcx, [rdi+80h]; ListHead
0x1800277b7  call    cs:__imp_InterlockedPushEntrySList
0x1800277be  nop     dword ptr [rax+rax+00h]
0x1800277c3  shl     ebx, 0Ch
0x1800277c6  add     rbx, rbp
0x1800277c9  test    rbx, rbx
0x1800277cc  jz      short loc_18002775E
0x1800277ce  cmp     dword ptr [rdi+98h], 0
0x1800277d5  jz      loc_1800278A7
0x1800277db  mov     rax, rbx
0x1800277de  mov     rbx, [rsp+68h+arg_18]
0x1800277e6  add     rsp, 30h
0x1800277ea  pop     r15
0x1800277ec  pop     r14
0x1800277ee  pop     r13
0x1800277f0  pop     r12
0x1800277f2  pop     rdi
0x1800277f3  pop     rsi
0x1800277f4  pop     rbp
0x1800277f5  retn
0x1800277f7  mov     rcx, [r14+8]
0x1800277fb  mov     rax, [r14]
0x1800277fe  mov     [rcx], rax
0x180027801  mov     rcx, [r14]
0x180027804  mov     rax, [r14+8]
0x180027808  mov     [rcx+8], rax
0x18002780c  mov     rcx, [rdi+18h]
0x180027810  mov     rax, [rcx+8]
0x180027814  mov     [r14+8], rax
0x180027818  mov     [r14], rcx
0x18002781b  mov     rax, [rcx+8]
0x18002781f  mov     [rax], r14
0x180027822  mov     [rcx+8], r14
0x180027826  jmp     loc_18002773C
0x18002782b  mov     rcx, [r8+8]
0x18002782f  lea     rbp, [r8+10h]
0x180027833  mov     rax, [r8]
0x180027836  mov     edx, [rdi+58h]
0x180027839  mov     [rcx], rax
0x18002783c  mov     rcx, [r8]
0x18002783f  mov     rax, [r8+8]
0x180027843  mov     [rcx+8], rax
0x180027847  cmp     esi, edx
0x180027849  jz      loc_180027905
0x18002784f  mov     rcx, [r15]
0x180027852  mov     rax, [rcx+8]
0x180027856  mov     [r8+8], rax
0x18002785a  mov     [r8], rcx
0x18002785d  mov     rax, [rcx+8]
0x180027861  mov     [rax], r8
0x180027864  mov     [rcx+8], r8
0x180027868  mov     edx, esi; unsigned int
0x18002786a  mov     rcx, rbp; this
0x18002786d  call    ?AllocPages@PageSegment@@QEAAPEADI@Z; PageSegment::AllocPages(uint)
0x180027872  shl     esi, 0Ch
0x180027875  mov     rbx, rax
0x180027878  mov     eax, esi
0x18002787a  add     [rdi+0A0h], rax
0x180027881  mov     ecx, esi
0x180027883  lock xadd cs:qword_180443988, rcx
0x18002788c  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180027893  jz      loc_18002773C
0x180027899  lea     r8, [rsi+rcx]
0x18002789d  call    McTemplateU0x_EventWriteTransfer
0x1800278a2  jmp     loc_18002773C
0x1800278a7  mov     dword ptr [rdi+0F0h], 0
0x1800278b1  jmp     loc_1800277DB
0x1800278b6  lea     rcx, [rdi+0C8h]; this
0x1800278bd  call    ?FastEnter@AsymetricCriticalSection@@QEAAXXZ; AsymetricCriticalSection::FastEnter(void)
0x1800278c2  jmp     loc_180027630
0x1800278c7  call    cs:__imp_InterlockedPopEntrySList
0x1800278ce  nop     dword ptr [rax+rax+00h]
0x1800278d3  mov     rbp, rax
0x1800278d6  test    rax, rax
0x1800278d9  jz      loc_18002775E
0x1800278df  mov     rcx, [rax+8]
0x1800278e3  mov     [r12], rcx
0x1800278e7  mov     ebx, [rax+10h]
0x1800278ea  cmp     ebx, 1
0x1800278ed  jnz     loc_1800277A8
0x1800278f3  xorps   xmm0, xmm0
0x1800278f6  mov     rbx, rax
0x1800278f9  movups  xmmword ptr [rax], xmm0
0x1800278fc  movups  xmmword ptr [rax+10h], xmm0
0x180027900  jmp     loc_1800277C9
0x180027905  mov     rcx, [rdi+18h]
0x180027909  jmp     loc_180027852
0x18002790e  lea     r8, [rsi+rcx]
0x180027912  call    McTemplateU0x_EventWriteTransfer
0x180027917  jmp     loc_180027732
```
