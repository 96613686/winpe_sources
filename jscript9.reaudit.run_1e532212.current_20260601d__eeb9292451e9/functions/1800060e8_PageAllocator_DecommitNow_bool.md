# PageAllocator::DecommitNow(bool)

- ea: `0x1800060e8`
- end: `0x1800063cd`
- name: `?DecommitNow@PageAllocator@@QEAAX_N@Z`
- size: `741`
- prototype: `void __fastcall(PageAllocator *__hidden this, bool)`
- caller_count: `5`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005ba4`
- `0x180005eec`
- `0x180006058`
- `0x18006a458`
- `0x18010fd20`

## callees

- `0x180004930`
- `0x180004df4`
- `0x180004e34`
- `0x1800060e8`
- `0x1800063d4`
- `0x18000b2c8`
- `0x18000b314`
- `0x18003ee9c`
- `0x18006a638`
- `0x18006a878`
- `0x1801c989b`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x1800062b3`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800062b3`
- `KERNEL32!EnterCriticalSection` at `0x1800062cc`
- `KERNEL32!EnterCriticalSection` at `0x1800062cc`
- `KERNEL32!LeaveCriticalSection` at `0x1800062e4`
- `KERNEL32!LeaveCriticalSection` at `0x1800062e4`

## pseudocode

```c
void __fastcall PageAllocator::DecommitNow(PageAllocator *this, char a2)
{
  union _SLIST_HEADER *v4; // rcx
  unsigned __int64 v5; // rbp
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
  char *v8; // r12
  char *v9; // r14
  unsigned __int64 v10; // rsi
  unsigned int *v11; // r15
  _QWORD **v12; // rbx
  _QWORD *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  PageAllocator **i; // r8
  PageAllocator *v17; // rbx
  unsigned __int64 v18; // rax
  __int64 v19; // rdx
  unsigned __int64 v20; // r13
  __int64 v21; // rcx
  __int64 v22; // rdx
  PSLIST_ENTRY v23; // rax
  PSLIST_ENTRY v24; // rbx
  struct _RTL_CRITICAL_SECTION *v25; // rcx
  __int64 v26; // rsi
  unsigned int Next; // r14d
  __int64 SegmentList; // r12
  unsigned int v29; // r15d
  char *v30; // rbx
  __int64 v31; // rcx
  _QWORD *v32; // rdx
  __int64 v33; // rcx

  if ( !*((_BYTE *)this + 136) )
    goto LABEL_3;
  v4 = (union _SLIST_HEADER *)*((_QWORD *)this + 16);
  if ( !v4 )
    goto LABEL_3;
  while ( 1 )
  {
    v23 = InterlockedPopEntrySList(v4 + 4);
    v24 = v23;
    if ( !v23 )
      break;
    v26 = *((_QWORD *)&v23->Next + 1);
    Next = (unsigned int)v23[1].Next;
    SegmentList = PageAllocator::GetSegmentList(this, v26);
    v29 = Next << 12;
    if ( !a2 )
    {
      memset_0(v24, 0, v29);
      *(_DWORD *)(v26 + 48) |= 0xFFFFFFFF >> (32 - Next) << ((unsigned int)((_DWORD)v24 - *(_DWORD *)(v26 + 16)) >> 12);
      *(_DWORD *)(v26 + 56) += Next;
      PageAllocator::SubUsedBytes(this, v29);
LABEL_27:
      PageAllocator::TransferSegment(this, v26, SegmentList);
      goto LABEL_28;
    }
    PageSegment::DecommitPages<0>(v26, v24, Next);
    PageAllocator::SubUsedBytes(this, Next << 12);
    v21 = *(unsigned int *)(v26 + 32);
    v22 = *(_QWORD *)(v26 + 24) - v21;
    if ( v22 != *(_DWORD *)(v26 + 60) )
      goto LABEL_27;
    DListBase<Segment>::RemoveElement<NoThrowHeapAllocator>(v21, v22, v26);
LABEL_28:
    v4 = (union _SLIST_HEADER *)*((_QWORD *)this + 16);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 16) + 16LL));
  v25 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)this + 16) + 16LL);
  *((_BYTE *)this + 138) = 0;
  LeaveCriticalSection(v25);
  PageAllocator::FlushBackgroundPages(this);
LABEL_3:
  if ( *((_QWORD *)this + 13) )
  {
    PageAllocator::UpdateMinFreePageCount(this);
    if ( a2 )
    {
      v5 = 0;
    }
    else
    {
      v5 = 4096;
      v6 = *((_QWORD *)this + 18) >> 1;
      if ( (unsigned __int64)(*((_QWORD *)this + 13) - v6) > 0x1000 )
        v5 = *((_QWORD *)this + 13) - v6;
    }
    v7 = *((_QWORD *)this + 13);
    if ( v5 < v7 )
    {
      v8 = (char *)this + 56;
      v9 = (char *)this + 56;
      v10 = v7 - v5;
      if ( v10 )
      {
        v11 = (unsigned int *)((char *)this + 88);
        do
        {
          v9 = *(char **)v9;
          if ( v9 == v8 )
            break;
          v11 = (unsigned int *)((char *)this + 88);
          v20 = PageSegment::DecommitFreePages((PageSegment *)(v9 + 16), v10);
          if ( *((_DWORD *)v9 + 19) == *((_DWORD *)this + 22) )
          {
            v30 = (char *)*((_QWORD *)v9 + 1);
            *(_QWORD *)v30 = *(_QWORD *)v9;
            v31 = *((_QWORD *)v9 + 1);
            *(_QWORD *)(*(_QWORD *)v9 + 8LL) = v31;
            DeleteObject<NoThrowHeapAllocator,DListNode<PageSegment>>(v31, v9);
            v9 = v30;
          }
          v10 -= v20;
        }
        while ( v10 );
        if ( v10 )
        {
          v12 = (_QWORD **)((char *)this + 40);
          do
          {
            v13 = *v12;
            if ( *v12 == v12 )
              break;
            if ( v10 < *v11 )
            {
              PageSegment::DecommitFreePages((PageSegment *)(v13 + 2), v10);
              v32 = *v12;
              *(_QWORD *)(*v12)[1] = **v12;
              *(_QWORD *)(*v32 + 8LL) = v32[1];
              v33 = *(_QWORD *)v8;
              v32[1] = *(_QWORD *)(*(_QWORD *)v8 + 8LL);
              *v32 = v33;
              **(_QWORD **)(v33 + 8) = v32;
              *(_QWORD *)(v33 + 8) = v32;
              goto LABEL_19;
            }
            *(_QWORD *)v13[1] = *v13;
            v14 = *v13;
            *(_QWORD *)(v14 + 8) = v13[1];
            DeleteObject<NoThrowHeapAllocator,DListNode<PageSegment>>(v14, v13);
            v15 = *v11;
            v11 = (unsigned int *)((char *)this + 88);
            v10 -= v15;
          }
          while ( v10 );
        }
      }
      for ( i = (PageAllocator **)((char *)this + 8); v10; v10 -= v18 )
      {
        v17 = *i;
        if ( *i == (PageAllocator *)((char *)this + 8) )
          break;
        v18 = PageSegment::DecommitFreePages((PageAllocator *)((char *)v17 + 16), v10);
        i = (PageAllocator **)*((_QWORD *)v17 + 1);
        *i = *(PageAllocator **)v17;
        *(_QWORD *)(*(_QWORD *)v17 + 8LL) = *((_QWORD *)v17 + 1);
        v19 = *(_QWORD *)v8;
        *((_QWORD *)v17 + 1) = *(_QWORD *)(*(_QWORD *)v8 + 8LL);
        *(_QWORD *)v17 = v19;
        **(_QWORD **)(v19 + 8) = v17;
        *(_QWORD *)(v19 + 8) = v17;
      }
LABEL_19:
      *((_QWORD *)this + 13) = v5;
    }
  }
}

```

## disassembly

```asm
0x1800060e8  mov     rax, rsp
0x1800060eb  mov     [rax+18h], rbx
0x1800060ef  mov     [rax+10h], dl
0x1800060f2  mov     [rax+8], rcx
0x1800060f6  push    rbp
0x1800060f7  push    rsi
0x1800060f8  push    rdi
0x1800060f9  push    r12
0x1800060fb  push    r13
0x1800060fd  push    r14
0x1800060ff  push    r15
0x180006101  sub     rsp, 20h
0x180006105  cmp     byte ptr [rcx+88h], 0
0x18000610c  mov     bpl, dl
0x18000610f  mov     rdi, rcx
0x180006112  jz      short loc_180006124
0x180006114  mov     rcx, [rcx+80h]
0x18000611b  test    rcx, rcx
0x18000611e  jnz     loc_1800062AF
0x180006124  cmp     qword ptr [rdi+68h], 0
0x180006129  jz      loc_180006221
0x18000612f  mov     rcx, rdi; this
0x180006132  call    ?UpdateMinFreePageCount@PageAllocator@@IEAAXXZ; PageAllocator::UpdateMinFreePageCount(void)
0x180006137  test    bpl, bpl
0x18000613a  jnz     loc_180006264
0x180006140  mov     rax, [rdi+90h]
0x180006147  mov     ebp, 1000h
0x18000614c  mov     rcx, [rdi+68h]
0x180006150  shr     rax, 1
0x180006153  sub     rcx, rax
0x180006156  cmp     rcx, rbp
0x180006159  cmova   rbp, rcx
0x18000615d  mov     rsi, [rdi+68h]
0x180006161  cmp     rbp, rsi
0x180006164  jnb     loc_180006221
0x18000616a  lea     r12, [rdi+38h]
0x18000616e  mov     r14, r12
0x180006171  sub     rsi, rbp
0x180006174  jz      short loc_1800061C9
0x180006176  lea     r15, [rdi+58h]
0x18000617a  mov     r14, [r14]
0x18000617d  cmp     r14, r12
0x180006180  jnz     loc_180006236
0x180006186  test    rsi, rsi
0x180006189  jz      short loc_1800061C9
0x18000618b  lea     rbx, [rdi+28h]
0x18000618f  mov     rdx, [rbx]
0x180006192  cmp     rdx, rbx
0x180006195  jz      short loc_1800061C9
0x180006197  mov     eax, [r15]
0x18000619a  cmp     rsi, rax
0x18000619d  jb      loc_18000638A
0x1800061a3  mov     rcx, [rdx+8]
0x1800061a7  mov     rax, [rdx]
0x1800061aa  mov     [rcx], rax
0x1800061ad  mov     rcx, [rdx]
0x1800061b0  mov     rax, [rdx+8]
0x1800061b4  mov     [rcx+8], rax
0x1800061b8  call    ??$DeleteObject@VNoThrowHeapAllocator@@V?$DListNode@VPageSegment@@@@@@YAXPEAVNoThrowHeapAllocator@@PEAV?$DListNode@VPageSegment@@@@@Z; DeleteObject<NoThrowHeapAllocator,DListNode<PageSegment>>(NoThrowHeapAllocator *,DListNode<PageSegment> *)
0x1800061bd  mov     eax, [r15]
0x1800061c0  lea     r15, [rdi+58h]
0x1800061c4  sub     rsi, rax
0x1800061c7  jnz     short loc_18000618F
0x1800061c9  lea     r14, [rdi+8]
0x1800061cd  mov     r8, r14
0x1800061d0  test    rsi, rsi
0x1800061d3  jz      short loc_18000621D
0x1800061d5  mov     rbx, [r8]
0x1800061d8  cmp     rbx, r14
0x1800061db  jz      short loc_18000621D
0x1800061dd  lea     rcx, [rbx+10h]; this
0x1800061e1  mov     rdx, rsi; unsigned __int64
0x1800061e4  call    ?DecommitFreePages@PageSegment@@QEAA_K_K@Z; PageSegment::DecommitFreePages(unsigned __int64)
0x1800061e9  mov     rcx, [rbx]
0x1800061ec  mov     r8, [rbx+8]
0x1800061f0  mov     [r8], rcx
0x1800061f3  mov     rdx, [rbx]
0x1800061f6  mov     rcx, [rbx+8]
0x1800061fa  mov     [rdx+8], rcx
0x1800061fe  mov     rdx, [r12]
0x180006202  mov     rcx, [rdx+8]
0x180006206  mov     [rbx+8], rcx
0x18000620a  mov     [rbx], rdx
0x18000620d  mov     rcx, [rdx+8]
0x180006211  mov     [rcx], rbx
0x180006214  mov     [rdx+8], rbx
0x180006218  sub     rsi, rax
0x18000621b  jnz     short loc_1800061D5
0x18000621d  mov     [rdi+68h], rbp
0x180006221  mov     rbx, [rsp+58h+arg_10]
0x180006226  add     rsp, 20h
0x18000622a  pop     r15
0x18000622c  pop     r14
0x18000622e  pop     r13
0x180006230  pop     r12
0x180006232  pop     rdi
0x180006233  pop     rsi
0x180006234  pop     rbp
0x180006235  retn
0x180006236  lea     rcx, [r14+10h]; this
0x18000623a  mov     rdx, rsi; unsigned __int64
0x18000623d  call    ?DecommitFreePages@PageSegment@@QEAA_K_K@Z; PageSegment::DecommitFreePages(unsigned __int64)
0x180006242  lea     r15, [rdi+58h]
0x180006246  mov     r13, rax
0x180006249  mov     ecx, [r15]
0x18000624c  cmp     [r14+4Ch], ecx
0x180006250  jz      loc_180006365
0x180006256  sub     rsi, r13
0x180006259  jnz     loc_18000617A
0x18000625f  jmp     loc_180006186
0x180006264  xor     ebp, ebp
0x180006266  jmp     loc_18000615D
0x18000626b  mov     r8d, r14d
0x18000626e  mov     rdx, rbx
0x180006271  mov     rcx, rsi
0x180006274  call    ??$DecommitPages@$0A@@PageSegment@@QEAAXPEAXI@Z; PageSegment::DecommitPages<0>(void *,uint)
0x180006279  mov     rdx, r15; unsigned __int64
0x18000627c  mov     rcx, rdi; this
0x18000627f  call    ?SubUsedBytes@PageAllocator@@AEAAX_K@Z; PageAllocator::SubUsedBytes(unsigned __int64)
0x180006284  mov     ecx, [rsi+20h]
0x180006287  mov     rdx, [rsi+18h]
0x18000628b  mov     eax, [rsi+3Ch]
0x18000628e  sub     rdx, rcx
0x180006291  cmp     rdx, rax
0x180006294  jz      loc_180006358
0x18000629a  mov     r8, r12
0x18000629d  mov     rdx, rsi
0x1800062a0  mov     rcx, rdi
0x1800062a3  call    ?TransferSegment@PageAllocator@@IEAAXPEAVPageSegment@@PEAV?$DListBase@VPageSegment@@@@@Z; PageAllocator::TransferSegment(PageSegment *,DListBase<PageSegment> *)
0x1800062a8  mov     rcx, [rdi+80h]
0x1800062af  add     rcx, 40h ; '@'; ListHead
0x1800062b3  call    cs:__imp_InterlockedPopEntrySList
0x1800062b9  mov     rbx, rax
0x1800062bc  test    rax, rax
0x1800062bf  jnz     short loc_1800062F7
0x1800062c1  mov     rcx, [rdi+80h]
0x1800062c8  add     rcx, 10h; lpCriticalSection
0x1800062cc  call    cs:__imp_EnterCriticalSection
0x1800062d2  mov     rcx, [rdi+80h]
0x1800062d9  add     rcx, 10h; lpCriticalSection
0x1800062dd  mov     byte ptr [rdi+8Ah], 0
0x1800062e4  call    cs:__imp_LeaveCriticalSection
0x1800062ea  mov     rcx, rdi; this
0x1800062ed  call    ?FlushBackgroundPages@PageAllocator@@QEAAXXZ; PageAllocator::FlushBackgroundPages(void)
0x1800062f2  jmp     loc_180006124
0x1800062f7  mov     rsi, [rbx+8]
0x1800062fb  mov     rcx, rdi
0x1800062fe  mov     r14d, [rbx+10h]
0x180006302  mov     rdx, rsi
0x180006305  call    ?GetSegmentList@PageAllocator@@IEAAPEAV?$DListBase@VPageSegment@@@@PEAVPageSegment@@@Z; PageAllocator::GetSegmentList(PageSegment *)
0x18000630a  mov     r15d, r14d
0x18000630d  mov     r12, rax
0x180006310  shl     r15d, 0Ch
0x180006314  test    bpl, bpl
0x180006317  jnz     loc_18000626B
0x18000631d  mov     r8d, r15d; Size
0x180006320  xor     edx, edx; Val
0x180006322  mov     rcx, rbx; void *
0x180006325  call    memset_0
0x18000632a  sub     ebx, [rsi+10h]
0x18000632d  or      eax, 0FFFFFFFFh
0x180006330  mov     ecx, 20h ; ' '
0x180006335  shr     ebx, 0Ch
0x180006338  sub     ecx, r14d
0x18000633b  mov     edx, r15d; unsigned __int64
0x18000633e  shr     eax, cl
0x180006340  mov     cl, bl
0x180006342  shl     eax, cl
0x180006344  mov     rcx, rdi; this
0x180006347  or      [rsi+30h], eax
0x18000634a  add     [rsi+38h], r14d
0x18000634e  call    ?SubUsedBytes@PageAllocator@@AEAAX_K@Z; PageAllocator::SubUsedBytes(unsigned __int64)
0x180006353  jmp     loc_18000629A
0x180006358  mov     r8, rsi
0x18000635b  call    ??$RemoveElement@VNoThrowHeapAllocator@@@?$DListBase@VSegment@@@@QEAAXPEAVNoThrowHeapAllocator@@PEAVSegment@@@Z; DListBase<Segment>::RemoveElement<NoThrowHeapAllocator>(NoThrowHeapAllocator *,Segment *)
0x180006360  jmp     loc_1800062A8
0x180006365  mov     rcx, [r14]
0x180006368  mov     rdx, r14
0x18000636b  mov     rbx, [r14+8]
0x18000636f  mov     [rbx], rcx
0x180006372  mov     r8, [r14]
0x180006375  mov     rcx, [r14+8]
0x180006379  mov     [r8+8], rcx
0x18000637d  call    ??$DeleteObject@VNoThrowHeapAllocator@@V?$DListNode@VPageSegment@@@@@@YAXPEAVNoThrowHeapAllocator@@PEAV?$DListNode@VPageSegment@@@@@Z; DeleteObject<NoThrowHeapAllocator,DListNode<PageSegment>>(NoThrowHeapAllocator *,DListNode<PageSegment> *)
0x180006382  mov     r14, rbx
0x180006385  jmp     loc_180006256
0x18000638a  lea     rcx, [rdx+10h]; this
0x18000638e  mov     rdx, rsi; unsigned __int64
0x180006391  call    ?DecommitFreePages@PageSegment@@QEAA_K_K@Z; PageSegment::DecommitFreePages(unsigned __int64)
0x180006396  mov     rdx, [rbx]
0x180006399  mov     rcx, [rdx+8]
0x18000639d  mov     rax, [rdx]
0x1800063a0  mov     [rcx], rax
0x1800063a3  mov     rcx, [rdx]
0x1800063a6  mov     rax, [rdx+8]
0x1800063aa  mov     [rcx+8], rax
0x1800063ae  mov     rcx, [r12]
0x1800063b2  mov     rax, [rcx+8]
0x1800063b6  mov     [rdx+8], rax
0x1800063ba  mov     [rdx], rcx
0x1800063bd  mov     rax, [rcx+8]
0x1800063c1  mov     [rax], rdx
0x1800063c4  mov     [rcx+8], rdx
0x1800063c8  jmp     loc_18000621D
```
