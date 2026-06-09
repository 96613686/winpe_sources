# PageAllocator::DecommitNow(bool)

- ea: `0x1800086e0`
- end: `0x1800089d8`
- name: `?DecommitNow@PageAllocator@@QEAAX_N@Z`
- size: `760`
- prototype: `void __fastcall(PageAllocator *__hidden this, bool)`
- caller_count: `5`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800045e4`
- `0x18000812c`
- `0x1800084a0`
- `0x180008650`
- `0x18002141c`

## callees

- `0x1800060e0`
- `0x18000612c`
- `0x1800086e0`
- `0x1800089e0`
- `0x180008e3c`
- `0x180008f78`
- `0x180021614`
- `0x18002185c`
- `0x180127de4`
- `0x180150824`
- `0x1801cc26b`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x1800088ac`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800088ac`
- `KERNEL32!EnterCriticalSection` at `0x1800088cb`
- `KERNEL32!EnterCriticalSection` at `0x1800088cb`
- `KERNEL32!LeaveCriticalSection` at `0x1800088e9`
- `KERNEL32!LeaveCriticalSection` at `0x1800088e9`

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
0x1800086e0  mov     rax, rsp
0x1800086e3  mov     [rax+18h], rbx
0x1800086e7  mov     [rax+10h], dl
0x1800086ea  mov     [rax+8], rcx
0x1800086ee  push    rbp
0x1800086ef  push    rsi
0x1800086f0  push    rdi
0x1800086f1  push    r12
0x1800086f3  push    r13
0x1800086f5  push    r14
0x1800086f7  push    r15
0x1800086f9  sub     rsp, 20h
0x1800086fd  cmp     byte ptr [rcx+88h], 0
0x180008704  mov     bpl, dl
0x180008707  mov     rdi, rcx
0x18000870a  jz      short loc_18000871C
0x18000870c  mov     rcx, [rcx+80h]
0x180008713  test    rcx, rcx
0x180008716  jnz     loc_1800088A8
0x18000871c  cmp     qword ptr [rdi+68h], 0
0x180008721  jz      loc_180008819
0x180008727  mov     rcx, rdi; this
0x18000872a  call    ?UpdateMinFreePageCount@PageAllocator@@IEAAXXZ; PageAllocator::UpdateMinFreePageCount(void)
0x18000872f  test    bpl, bpl
0x180008732  jnz     loc_18000885D
0x180008738  mov     rax, [rdi+90h]
0x18000873f  mov     ebp, 1000h
0x180008744  mov     rcx, [rdi+68h]
0x180008748  shr     rax, 1
0x18000874b  sub     rcx, rax
0x18000874e  cmp     rcx, rbp
0x180008751  cmova   rbp, rcx
0x180008755  mov     rsi, [rdi+68h]
0x180008759  cmp     rbp, rsi
0x18000875c  jnb     loc_180008819
0x180008762  lea     r12, [rdi+38h]
0x180008766  mov     r14, r12
0x180008769  sub     rsi, rbp
0x18000876c  jz      short loc_1800087C1
0x18000876e  lea     r15, [rdi+58h]
0x180008772  mov     r14, [r14]
0x180008775  cmp     r14, r12
0x180008778  jnz     loc_18000882F
0x18000877e  test    rsi, rsi
0x180008781  jz      short loc_1800087C1
0x180008783  lea     rbx, [rdi+28h]
0x180008787  mov     rdx, [rbx]
0x18000878a  cmp     rdx, rbx
0x18000878d  jz      short loc_1800087C1
0x18000878f  mov     eax, [r15]
0x180008792  cmp     rsi, rax
0x180008795  jb      loc_180008995
0x18000879b  mov     rcx, [rdx+8]
0x18000879f  mov     rax, [rdx]
0x1800087a2  mov     [rcx], rax
0x1800087a5  mov     rcx, [rdx]
0x1800087a8  mov     rax, [rdx+8]
0x1800087ac  mov     [rcx+8], rax
0x1800087b0  call    ??$DeleteObject@VNoThrowHeapAllocator@@V?$DListNode@VPageSegment@@@@@@YAXPEAVNoThrowHeapAllocator@@PEAV?$DListNode@VPageSegment@@@@@Z; DeleteObject<NoThrowHeapAllocator,DListNode<PageSegment>>(NoThrowHeapAllocator *,DListNode<PageSegment> *)
0x1800087b5  mov     eax, [r15]
0x1800087b8  lea     r15, [rdi+58h]
0x1800087bc  sub     rsi, rax
0x1800087bf  jnz     short loc_180008787
0x1800087c1  lea     r14, [rdi+8]
0x1800087c5  mov     r8, r14
0x1800087c8  test    rsi, rsi
0x1800087cb  jz      short loc_180008815
0x1800087cd  mov     rbx, [r8]
0x1800087d0  cmp     rbx, r14
0x1800087d3  jz      short loc_180008815
0x1800087d5  lea     rcx, [rbx+10h]; this
0x1800087d9  mov     rdx, rsi; unsigned __int64
0x1800087dc  call    ?DecommitFreePages@PageSegment@@QEAA_K_K@Z; PageSegment::DecommitFreePages(unsigned __int64)
0x1800087e1  mov     rcx, [rbx]
0x1800087e4  mov     r8, [rbx+8]
0x1800087e8  mov     [r8], rcx
0x1800087eb  mov     rdx, [rbx]
0x1800087ee  mov     rcx, [rbx+8]
0x1800087f2  mov     [rdx+8], rcx
0x1800087f6  mov     rdx, [r12]
0x1800087fa  mov     rcx, [rdx+8]
0x1800087fe  mov     [rbx+8], rcx
0x180008802  mov     [rbx], rdx
0x180008805  mov     rcx, [rdx+8]
0x180008809  mov     [rcx], rbx
0x18000880c  mov     [rdx+8], rbx
0x180008810  sub     rsi, rax
0x180008813  jnz     short loc_1800087CD
0x180008815  mov     [rdi+68h], rbp
0x180008819  mov     rbx, [rsp+58h+arg_10]
0x18000881e  add     rsp, 20h
0x180008822  pop     r15
0x180008824  pop     r14
0x180008826  pop     r13
0x180008828  pop     r12
0x18000882a  pop     rdi
0x18000882b  pop     rsi
0x18000882c  pop     rbp
0x18000882d  retn
0x18000882f  lea     rcx, [r14+10h]; this
0x180008833  mov     rdx, rsi; unsigned __int64
0x180008836  call    ?DecommitFreePages@PageSegment@@QEAA_K_K@Z; PageSegment::DecommitFreePages(unsigned __int64)
0x18000883b  lea     r15, [rdi+58h]
0x18000883f  mov     r13, rax
0x180008842  mov     ecx, [r15]
0x180008845  cmp     [r14+4Ch], ecx
0x180008849  jz      loc_180008970
0x18000884f  sub     rsi, r13
0x180008852  jnz     loc_180008772
0x180008858  jmp     loc_18000877E
0x18000885d  xor     ebp, ebp
0x18000885f  jmp     loc_180008755
0x180008864  mov     r8d, r14d
0x180008867  mov     rdx, rbx
0x18000886a  mov     rcx, rsi
0x18000886d  call    ??$DecommitPages@$0A@@PageSegment@@QEAAXPEAXI@Z; PageSegment::DecommitPages<0>(void *,uint)
0x180008872  mov     rdx, r15; unsigned __int64
0x180008875  mov     rcx, rdi; this
0x180008878  call    ?SubUsedBytes@PageAllocator@@AEAAX_K@Z; PageAllocator::SubUsedBytes(unsigned __int64)
0x18000887d  mov     ecx, [rsi+20h]
0x180008880  mov     rdx, [rsi+18h]
0x180008884  mov     eax, [rsi+3Ch]
0x180008887  sub     rdx, rcx
0x18000888a  cmp     rdx, rax
0x18000888d  jz      loc_180008963
0x180008893  mov     r8, r12
0x180008896  mov     rdx, rsi
0x180008899  mov     rcx, rdi
0x18000889c  call    ?TransferSegment@PageAllocator@@IEAAXPEAVPageSegment@@PEAV?$DListBase@VPageSegment@@@@@Z; PageAllocator::TransferSegment(PageSegment *,DListBase<PageSegment> *)
0x1800088a1  mov     rcx, [rdi+80h]
0x1800088a8  add     rcx, 40h ; '@'; ListHead
0x1800088ac  call    cs:__imp_InterlockedPopEntrySList
0x1800088b3  nop     dword ptr [rax+rax+00h]
0x1800088b8  mov     rbx, rax
0x1800088bb  test    rax, rax
0x1800088be  jnz     short loc_180008902
0x1800088c0  mov     rcx, [rdi+80h]
0x1800088c7  add     rcx, 10h; lpCriticalSection
0x1800088cb  call    cs:__imp_EnterCriticalSection
0x1800088d2  nop     dword ptr [rax+rax+00h]
0x1800088d7  mov     rcx, [rdi+80h]
0x1800088de  add     rcx, 10h; lpCriticalSection
0x1800088e2  mov     byte ptr [rdi+8Ah], 0
0x1800088e9  call    cs:__imp_LeaveCriticalSection
0x1800088f0  nop     dword ptr [rax+rax+00h]
0x1800088f5  mov     rcx, rdi; this
0x1800088f8  call    ?FlushBackgroundPages@PageAllocator@@QEAAXXZ; PageAllocator::FlushBackgroundPages(void)
0x1800088fd  jmp     loc_18000871C
0x180008902  mov     rsi, [rbx+8]
0x180008906  mov     rcx, rdi
0x180008909  mov     r14d, [rbx+10h]
0x18000890d  mov     rdx, rsi
0x180008910  call    ?GetSegmentList@PageAllocator@@IEAAPEAV?$DListBase@VPageSegment@@@@PEAVPageSegment@@@Z; PageAllocator::GetSegmentList(PageSegment *)
0x180008915  mov     r15d, r14d
0x180008918  mov     r12, rax
0x18000891b  shl     r15d, 0Ch
0x18000891f  test    bpl, bpl
0x180008922  jnz     loc_180008864
0x180008928  mov     r8d, r15d; Size
0x18000892b  xor     edx, edx; Val
0x18000892d  mov     rcx, rbx; void *
0x180008930  call    memset_0
0x180008935  sub     ebx, [rsi+10h]
0x180008938  or      eax, 0FFFFFFFFh
0x18000893b  mov     ecx, 20h ; ' '
0x180008940  shr     ebx, 0Ch
0x180008943  sub     ecx, r14d
0x180008946  mov     edx, r15d; unsigned __int64
0x180008949  shr     eax, cl
0x18000894b  mov     cl, bl
0x18000894d  shl     eax, cl
0x18000894f  mov     rcx, rdi; this
0x180008952  or      [rsi+30h], eax
0x180008955  add     [rsi+38h], r14d
0x180008959  call    ?SubUsedBytes@PageAllocator@@AEAAX_K@Z; PageAllocator::SubUsedBytes(unsigned __int64)
0x18000895e  jmp     loc_180008893
0x180008963  mov     r8, rsi
0x180008966  call    ??$RemoveElement@VNoThrowHeapAllocator@@@?$DListBase@VSegment@@@@QEAAXPEAVNoThrowHeapAllocator@@PEAVSegment@@@Z; DListBase<Segment>::RemoveElement<NoThrowHeapAllocator>(NoThrowHeapAllocator *,Segment *)
0x18000896b  jmp     loc_1800088A1
0x180008970  mov     rcx, [r14]
0x180008973  mov     rdx, r14
0x180008976  mov     rbx, [r14+8]
0x18000897a  mov     [rbx], rcx
0x18000897d  mov     r8, [r14]
0x180008980  mov     rcx, [r14+8]
0x180008984  mov     [r8+8], rcx
0x180008988  call    ??$DeleteObject@VNoThrowHeapAllocator@@V?$DListNode@VPageSegment@@@@@@YAXPEAVNoThrowHeapAllocator@@PEAV?$DListNode@VPageSegment@@@@@Z; DeleteObject<NoThrowHeapAllocator,DListNode<PageSegment>>(NoThrowHeapAllocator *,DListNode<PageSegment> *)
0x18000898d  mov     r14, rbx
0x180008990  jmp     loc_18000884F
0x180008995  lea     rcx, [rdx+10h]; this
0x180008999  mov     rdx, rsi; unsigned __int64
0x18000899c  call    ?DecommitFreePages@PageSegment@@QEAA_K_K@Z; PageSegment::DecommitFreePages(unsigned __int64)
0x1800089a1  mov     rdx, [rbx]
0x1800089a4  mov     rcx, [rdx+8]
0x1800089a8  mov     rax, [rdx]
0x1800089ab  mov     [rcx], rax
0x1800089ae  mov     rcx, [rdx]
0x1800089b1  mov     rax, [rdx+8]
0x1800089b5  mov     [rcx+8], rax
0x1800089b9  mov     rcx, [r12]
0x1800089bd  mov     rax, [rcx+8]
0x1800089c1  mov     [rdx+8], rax
0x1800089c5  mov     [rdx], rcx
0x1800089c8  mov     rax, [rcx+8]
0x1800089cc  mov     [rax], rdx
0x1800089cf  mov     [rcx+8], rdx
0x1800089d3  jmp     loc_180008815
```
