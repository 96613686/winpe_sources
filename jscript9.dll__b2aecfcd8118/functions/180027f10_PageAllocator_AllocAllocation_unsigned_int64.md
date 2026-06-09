# PageAllocator::AllocAllocation(unsigned __int64)

- ea: `0x180027f10`
- end: `0x18002827e`
- name: `?AllocAllocation@PageAllocator@@QEAAPEAVPageAllocation@@_K@Z`
- size: `878`
- prototype: `struct PageAllocation *__fastcall(PageAllocator *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180268538`

## callees

- `0x180008e7c`
- `0x1800215c0`
- `0x180026314`
- `0x180027f10`
- `0x180028284`
- `0x18025a1fc`
- `0x18025a464`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x180028208`
- `KERNEL32!InterlockedPushEntrySList` at `0x180028208`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800281d0`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800281d0`

## pseudocode

```c
struct PageAllocation *__fastcall PageAllocator::AllocAllocation(PageAllocator *this, unsigned __int64 a2)
{
  unsigned __int64 v2; // rax
  bool v5; // zf
  char *v6; // r15
  char *v7; // r14
  struct PageSegment *v8; // rsi
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // r10d
  unsigned int v12; // edx
  unsigned int v13; // r9d
  unsigned __int64 v14; // rdx
  unsigned int v15; // r8d
  char *v16; // rbx
  unsigned __int64 v17; // rcx
  signed __int64 v18; // rax
  union _SLIST_HEADER *v20; // rcx
  PageAllocator *v21; // r8
  __int64 v22; // rcx
  int v23; // edx
  __int64 v24; // rcx
  __int64 v25; // rdx
  unsigned __int64 v26; // rcx
  signed __int64 v27; // rax
  PSLIST_ENTRY v28; // rax
  PSLIST_ENTRY v29; // r14
  int Next; // ebx
  int v31; // ebx
  struct Segment *v32; // rax
  struct PageSegment *v33; // [rsp+28h] [rbp-30h] BYREF

  v2 = *((unsigned int *)this + 22);
  v33 = 0;
  if ( a2 <= v2 )
  {
    v5 = *((_DWORD *)this + 38) == 0;
    *((_BYTE *)this + 139) = 1;
    if ( v5 )
      AsymetricCriticalSection::FastEnter((PageAllocator *)((char *)this + 200));
    v6 = (char *)this + 8;
    if ( *((_QWORD *)this + 13) < (unsigned __int64)(unsigned int)a2 )
      goto LABEL_31;
    v7 = (char *)this + 8;
LABEL_6:
    while ( 1 )
    {
      v7 = *(char **)v7;
      if ( v7 == v6 )
        break;
      v8 = (struct PageSegment *)(v7 + 16);
      v9 = *((_DWORD *)v7 + 18);
      if ( v9 >= (unsigned int)a2 )
      {
        v10 = *((_DWORD *)v7 + 16);
        v11 = -1;
        v5 = !_BitScanForward(&v12, v10);
        if ( !v5 )
          v11 = v12;
        v13 = 0xFFFFFFFF >> (32 - a2);
        while ( v11 != -1 )
        {
          v14 = *((_QWORD *)v7 + 5) - *((unsigned int *)v7 + 12) - v11;
          if ( v14 < (unsigned int)a2 )
            break;
          if ( (_DWORD)a2 == 1 || (v14 = v13 << v11, ((unsigned int)v14 & v10) == (_DWORD)v14) )
          {
            *((_DWORD *)v7 + 16) = v10 & ~(v13 << v11);
            *((_DWORD *)v7 + 18) = v9 - a2;
            v16 = (char *)(*((_QWORD *)v7 + 4) + (v11 << 12));
            if ( !v16 )
              goto LABEL_6;
            v17 = (unsigned int)((_DWORD)a2 << 12);
            *((_QWORD *)this + 20) += v17;
            v18 = _InterlockedExchangeAdd64(&qword_180443988, v17);
            if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
              McTemplateU0x_EventWriteTransfer(v17, v14, v17 + v18);
            if ( !*((_DWORD *)v7 + 18) )
            {
              **((_QWORD **)v7 + 1) = *(_QWORD *)v7;
              *(_QWORD *)(*(_QWORD *)v7 + 8LL) = *((_QWORD *)v7 + 1);
              v22 = *((_QWORD *)this + 3);
              *((_QWORD *)v7 + 1) = *(_QWORD *)(v22 + 8);
              *(_QWORD *)v7 = v22;
              **(_QWORD **)(v22 + 8) = v7;
              *(_QWORD *)(v22 + 8) = v7;
            }
            goto LABEL_23;
          }
          v5 = !_BitScanForward(&v15, v10 & (-1 << (v11 + 1)));
          v11 = -1;
          if ( !v5 )
            v11 = v15;
        }
      }
    }
    if ( (_DWORD)a2 != 1 )
      goto LABEL_31;
    v20 = (union _SLIST_HEADER *)*((_QWORD *)this + 16);
    if ( !v20 )
      goto LABEL_31;
    v28 = InterlockedPopEntrySList(v20);
    v29 = v28;
    if ( !v28 )
      goto LABEL_31;
    v8 = (struct PageSegment *)*((_QWORD *)&v28->Next + 1);
    Next = (int)v28[1].Next;
    v33 = v8;
    if ( Next == 1 )
    {
      v16 = (char *)v28;
      *v28 = 0;
      v28[1] = 0;
    }
    else
    {
      v31 = Next - 1;
      LODWORD(v28[1].Next) = v31;
      InterlockedPushEntrySList(*((PSLIST_HEADER *)this + 16), v28);
      v16 = (char *)v29 + (unsigned int)(v31 << 12);
    }
    if ( !v16 )
    {
LABEL_31:
      v21 = (PageAllocator *)*((_QWORD *)this + 5);
      if ( v21 == (PageAllocator *)((char *)this + 40) )
      {
        v16 = PageAllocator::TryAllocDecommitedPages(this, a2, &v33);
        if ( v16 )
        {
LABEL_33:
          v8 = v33;
          goto LABEL_24;
        }
        v8 = (struct PageSegment *)PageAllocator::AddPageSegment(this);
        if ( !v8 )
        {
          v16 = 0;
          goto LABEL_33;
        }
      }
      else
      {
        v8 = (PageAllocator *)((char *)v21 + 16);
        v23 = *((_DWORD *)this + 22);
        **((_QWORD **)v21 + 1) = *(_QWORD *)v21;
        *(_QWORD *)(*(_QWORD *)v21 + 8LL) = *((_QWORD *)v21 + 1);
        if ( (_DWORD)a2 == v23 )
          v24 = *((_QWORD *)this + 3);
        else
          v24 = *(_QWORD *)v6;
        *((_QWORD *)v21 + 1) = *(_QWORD *)(v24 + 8);
        *(_QWORD *)v21 = v24;
        **(_QWORD **)(v24 + 8) = v21;
        *(_QWORD *)(v24 + 8) = v21;
      }
      v16 = PageSegment::AllocPages(v8, a2);
      v26 = (unsigned int)((_DWORD)a2 << 12);
      *((_QWORD *)this + 20) += v26;
      v27 = _InterlockedExchangeAdd64(&qword_180443988, v26);
      if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
        McTemplateU0x_EventWriteTransfer(v26, v25, v26 + v27);
LABEL_23:
      *((_QWORD *)this + 13) -= (unsigned int)a2;
    }
LABEL_24:
    if ( !*((_DWORD *)this + 38) )
      *((_DWORD *)this + 60) = 0;
    if ( v16 )
    {
      *(_QWORD *)v16 = a2;
LABEL_28:
      *((_QWORD *)v16 + 1) = v8;
      return (struct PageAllocation *)v16;
    }
    return 0;
  }
  v32 = PageAllocator::AllocSegment(this, a2);
  v8 = v32;
  if ( v32 )
  {
    v16 = (char *)*((_QWORD *)v32 + 2);
    *(_QWORD *)v16 = *((_QWORD *)v32 + 3) - *((unsigned int *)v32 + 8);
    goto LABEL_28;
  }
  return 0;
}

```

## disassembly

```asm
0x180027f10  mov     r11, rsp
0x180027f13  mov     [r11+18h], rbx
0x180027f17  mov     [r11+20h], rbp
0x180027f1b  mov     [r11+10h], rdx
0x180027f1f  mov     [r11+8], rcx
0x180027f23  push    rsi
0x180027f24  push    rdi
0x180027f25  push    r12
0x180027f27  push    r14
0x180027f29  push    r15
0x180027f2b  sub     rsp, 30h
0x180027f2f  mov     eax, [rcx+58h]
0x180027f32  mov     rdi, rcx
0x180027f35  mov     qword ptr [r11-30h], 0
0x180027f3d  mov     r12, rdx
0x180027f40  cmp     rdx, rax
0x180027f43  ja      loc_180028240
0x180027f49  cmp     dword ptr [rcx+98h], 0
0x180027f50  mov     byte ptr [rcx+8Bh], 1
0x180027f57  jz      loc_1800281BF
0x180027f5d  mov     ebp, r12d
0x180027f60  lea     r15, [rdi+8]
0x180027f64  cmp     [rdi+68h], rbp
0x180027f68  jb      loc_1800280AA
0x180027f6e  mov     r11d, 20h ; ' '
0x180027f74  mov     r14, r15
0x180027f77  sub     r11d, ebp
0x180027f7a  or      r8d, 0FFFFFFFFh
0x180027f7e  mov     r14, [r14]
0x180027f81  cmp     r14, r15
0x180027f84  jz      loc_180028095
0x180027f8a  lea     rsi, [r14+10h]
0x180027f8e  mov     ebx, [rsi+38h]
0x180027f91  cmp     ebx, ebp
0x180027f93  jb      short loc_180027F7E
0x180027f95  mov     eax, [rsi+30h]
0x180027f98  mov     r10d, r8d
0x180027f9b  bsf     edx, eax
0x180027f9e  mov     r9d, r8d
0x180027fa1  setnz   cl
0x180027fa4  test    cl, cl
0x180027fa6  mov     ecx, r11d
0x180027fa9  cmovnz  r10d, edx
0x180027fad  shr     r9d, cl
0x180027fb0  mov     [rsp+58h+var_38], 0
0x180027fb8  cmp     r10d, r8d
0x180027fbb  jz      short loc_180027F7E
0x180027fbd  mov     ecx, [rsi+20h]
0x180027fc0  mov     rdx, [rsi+18h]
0x180027fc4  sub     rdx, rcx
0x180027fc7  mov     ecx, r10d
0x180027fca  sub     rdx, rcx
0x180027fcd  cmp     rdx, rbp
0x180027fd0  jb      short loc_180027F7E
0x180027fd2  cmp     ebp, 1
0x180027fd5  jz      short loc_180028009
0x180027fd7  mov     ecx, r10d
0x180027fda  mov     edx, r9d
0x180027fdd  shl     edx, cl
0x180027fdf  mov     ecx, eax
0x180027fe1  and     ecx, edx
0x180027fe3  cmp     ecx, edx
0x180027fe5  jz      short loc_180028009
0x180027fe7  lea     ecx, [r10+1]
0x180027feb  mov     edx, r8d
0x180027fee  shl     edx, cl
0x180027ff0  and     edx, eax
0x180027ff2  bsf     r8d, edx
0x180027ff6  setnz   cl
0x180027ff9  or      r10d, 0FFFFFFFFh
0x180027ffd  test    cl, cl
0x180027fff  cmovnz  r10d, r8d
0x180028003  or      r8d, 0FFFFFFFFh
0x180028007  jmp     short loc_180027FB0
0x180028009  sub     ebx, ebp
0x18002800b  mov     ecx, r10d
0x18002800e  shl     r9d, cl
0x180028011  shl     r10d, 0Ch
0x180028015  not     r9d
0x180028018  and     r9d, eax
0x18002801b  mov     [rsi+30h], r9d
0x18002801f  mov     [rsi+38h], ebx
0x180028022  mov     ebx, r10d
0x180028025  add     rbx, [rsi+10h]
0x180028029  jz      loc_180027F7E
0x18002802f  mov     eax, ebp
0x180028031  shl     eax, 0Ch
0x180028034  mov     ecx, eax
0x180028036  add     [rdi+0A0h], rcx
0x18002803d  lock xadd cs:qword_180443988, rax
0x180028046  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x18002804d  jnz     loc_180028269
0x180028053  cmp     dword ptr [rsi+38h], 0
0x180028057  jz      short loc_1800280D8
0x180028059  sub     [rdi+68h], rbp
0x18002805d  cmp     dword ptr [rdi+98h], 0
0x180028064  jz      loc_180028188
0x18002806a  test    rbx, rbx
0x18002806d  jz      loc_180028277
0x180028073  mov     [rbx], r12
0x180028076  mov     [rbx+8], rsi
0x18002807a  mov     rax, rbx
0x18002807d  mov     rbx, [rsp+58h+arg_10]
0x180028082  mov     rbp, [rsp+58h+arg_18]
0x180028087  add     rsp, 30h
0x18002808b  pop     r15
0x18002808d  pop     r14
0x18002808f  pop     r12
0x180028091  pop     rdi
0x180028092  pop     rsi
0x180028093  retn
0x180028095  cmp     ebp, 1
0x180028098  jnz     short loc_1800280AA
0x18002809a  mov     rcx, [rdi+80h]; ListHead
0x1800280a1  test    rcx, rcx
0x1800280a4  jnz     loc_1800281D0
0x1800280aa  lea     rax, [rdi+28h]
0x1800280ae  mov     r8, [rax]
0x1800280b1  cmp     r8, rax
0x1800280b4  jnz     short loc_18002810C
0x1800280b6  lea     r8, [rsp+58h+var_30]; struct PageSegment **
0x1800280bb  mov     edx, ebp; unsigned int
0x1800280bd  mov     rcx, rdi; this
0x1800280c0  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x1800280c5  mov     rbx, rax
0x1800280c8  test    rax, rax
0x1800280cb  jz      loc_180028197
0x1800280d1  mov     rsi, [rsp+58h+var_30]
0x1800280d6  jmp     short loc_18002805D
0x1800280d8  mov     rcx, [r14+8]
0x1800280dc  mov     rax, [r14]
0x1800280df  mov     [rcx], rax
0x1800280e2  mov     rcx, [r14]
0x1800280e5  mov     rax, [r14+8]
0x1800280e9  mov     [rcx+8], rax
0x1800280ed  mov     rcx, [rdi+18h]
0x1800280f1  mov     rax, [rcx+8]
0x1800280f5  mov     [r14+8], rax
0x1800280f9  mov     [r14], rcx
0x1800280fc  mov     rax, [rcx+8]
0x180028100  mov     [rax], r14
0x180028103  mov     [rcx+8], r14
0x180028107  jmp     loc_180028059
0x18002810c  mov     rcx, [r8+8]
0x180028110  lea     rsi, [r8+10h]
0x180028114  mov     rax, [r8]
0x180028117  mov     edx, [rdi+58h]
0x18002811a  mov     [rcx], rax
0x18002811d  mov     rcx, [r8]
0x180028120  mov     rax, [r8+8]
0x180028124  mov     [rcx+8], rax
0x180028128  cmp     ebp, edx
0x18002812a  jz      loc_180028228
0x180028130  mov     rcx, [r15]
0x180028133  mov     rax, [rcx+8]
0x180028137  mov     [r8+8], rax
0x18002813b  mov     [r8], rcx
0x18002813e  mov     rax, [rcx+8]
0x180028142  mov     [rax], r8
0x180028145  mov     [rcx+8], r8
0x180028149  mov     edx, ebp; unsigned int
0x18002814b  mov     rcx, rsi; this
0x18002814e  call    ?AllocPages@PageSegment@@QEAAPEADI@Z; PageSegment::AllocPages(uint)
0x180028153  mov     rbx, rax
0x180028156  mov     eax, ebp
0x180028158  shl     eax, 0Ch
0x18002815b  mov     ecx, eax
0x18002815d  add     [rdi+0A0h], rcx
0x180028164  lock xadd cs:qword_180443988, rax
0x18002816d  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180028174  jz      loc_180028059
0x18002817a  lea     r8, [rcx+rax]
0x18002817e  call    McTemplateU0x_EventWriteTransfer
0x180028183  jmp     loc_180028059
0x180028188  mov     dword ptr [rdi+0F0h], 0
0x180028192  jmp     loc_18002806A
0x180028197  cmp     ebp, [rdi+58h]
0x18002819a  mov     edx, 18h
0x18002819f  mov     rcx, rdi; this
0x1800281a2  lea     eax, [rdx-10h]
0x1800281a5  cmovnz  edx, eax
0x1800281a8  add     rdx, rdi
0x1800281ab  call    ?AddPageSegment@PageAllocator@@IEAAPEAVPageSegment@@AEAV?$DListBase@VPageSegment@@@@@Z; PageAllocator::AddPageSegment(DListBase<PageSegment> &)
0x1800281b0  mov     rsi, rax
0x1800281b3  test    rax, rax
0x1800281b6  jnz     short loc_180028149
0x1800281b8  xor     ebx, ebx
0x1800281ba  jmp     loc_1800280D1
0x1800281bf  lea     rcx, [rdi+0C8h]; this
0x1800281c6  call    ?FastEnter@AsymetricCriticalSection@@QEAAXXZ; AsymetricCriticalSection::FastEnter(void)
0x1800281cb  jmp     loc_180027F5D
0x1800281d0  call    cs:__imp_InterlockedPopEntrySList
0x1800281d7  nop     dword ptr [rax+rax+00h]
0x1800281dc  mov     r14, rax
0x1800281df  test    rax, rax
0x1800281e2  jz      loc_1800280AA
0x1800281e8  mov     rsi, [rax+8]
0x1800281ec  mov     ebx, [rax+10h]
0x1800281ef  mov     [rsp+58h+var_30], rsi
0x1800281f4  cmp     ebx, 1
0x1800281f7  jz      short loc_180028231
0x1800281f9  dec     ebx
0x1800281fb  mov     rdx, rax; ListEntry
0x1800281fe  mov     [rax+10h], ebx
0x180028201  mov     rcx, [rdi+80h]; ListHead
0x180028208  call    cs:__imp_InterlockedPushEntrySList
0x18002820f  nop     dword ptr [rax+rax+00h]
0x180028214  shl     ebx, 0Ch
0x180028217  add     rbx, r14
0x18002821a  test    rbx, rbx
0x18002821d  jnz     loc_18002805D
0x180028223  jmp     loc_1800280AA
0x180028228  mov     rcx, [rdi+18h]
0x18002822c  jmp     loc_180028133
0x180028231  xorps   xmm0, xmm0
0x180028234  mov     rbx, r14
0x180028237  movups  xmmword ptr [rax], xmm0
0x18002823a  movups  xmmword ptr [rax+10h], xmm0
0x18002823e  jmp     short loc_18002821A
0x180028240  mov     rdx, r12; unsigned __int64
0x180028243  mov     rcx, rdi; this
0x180028246  call    ?AllocSegment@PageAllocator@@IEAAPEAVSegment@@_K@Z; PageAllocator::AllocSegment(unsigned __int64)
0x18002824b  mov     rsi, rax
0x18002824e  test    rax, rax
0x180028251  jz      short loc_180028277
0x180028253  mov     ecx, [rax+20h]
0x180028256  mov     rdx, [rax+18h]
0x18002825a  mov     rbx, [rax+10h]
0x18002825e  sub     rdx, rcx
0x180028261  mov     [rbx], rdx
0x180028264  jmp     loc_180028076
0x180028269  lea     r8, [rcx+rax]
0x18002826d  call    McTemplateU0x_EventWriteTransfer
0x180028272  jmp     loc_180028053
0x180028277  xor     eax, eax
0x180028279  jmp     loc_18002807D
```
