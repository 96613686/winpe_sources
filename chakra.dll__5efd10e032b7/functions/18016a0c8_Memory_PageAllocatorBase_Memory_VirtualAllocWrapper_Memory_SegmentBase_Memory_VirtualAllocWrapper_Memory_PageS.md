# Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::DecommitNow(bool)

- ea: `0x18016a0c8`
- end: `0x18016a526`
- name: `?DecommitNow@?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@QEAAX_N@Z`
- size: `1118`
- prototype: ``
- caller_count: `6`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800773f8`
- `0x180169efc`
- `0x1801b3820`
- `0x180268494`
- `0x18026d158`
- `0x18026de64`

## callees

- `0x180076910`
- `0x180076db0`
- `0x180076e44`
- `0x18016a0c8`
- `0x18016a52c`
- `0x18016abb0`
- `0x18016aeb0`
- `0x180285c58`
- `0x180286018`
- `0x180286054`
- `0x1802863b0`
- `0x18028645c`
- `0x18028652c`
- `0x1805a9c5a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18016a430`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18016a430`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18016a419`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18016a419`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18016a122`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18016a122`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18016a3f6`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18016a3f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LONGLONG __fastcall Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::DecommitNow(
        __int64 a1,
        char a2)
{
  LONGLONG result; // rax
  _QWORD *v4; // rcx
  unsigned __int64 v5; // r14
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rsi
  __int64 v8; // rbp
  _QWORD *v9; // r13
  _QWORD *v10; // r15
  __int64 v11; // r12
  __int64 v12; // rdx
  int v13; // eax
  _QWORD **v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  _QWORD **v19; // r9
  __int64 v20; // rcx
  _QWORD *v21; // rbx
  __int64 v22; // rax
  _QWORD *v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // r8
  __int64 v27; // rax
  _QWORD *v28; // rbx
  __int64 v29; // rcx
  PSLIST_ENTRY v30; // rax
  PSLIST_ENTRY v31; // rsi
  __int64 v32; // rbx
  __int64 v33; // rdx
  int v34; // ecx
  _DWORD *v35; // rbx
  unsigned int Next; // r14d
  __int64 SegmentList; // r12
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  LARGE_INTEGER PerformanceCount; // [rsp+20h] [rbp-48h] BYREF
  __int64 v42; // [rsp+28h] [rbp-40h]

  v42 = -2;
  result = *(_QWORD *)(a1 + 208);
  if ( result )
  {
    ++*(_QWORD *)(result + 48);
    result = Js::Tick::ToMicroseconds(*(Js::Tick **)(a1 + 208));
    if ( result )
    {
      PerformanceCount = Js::Tick::s_luBegin;
      QueryPerformanceCounter(&PerformanceCount);
      v4 = *(_QWORD **)(a1 + 208);
      result = PerformanceCount.QuadPart - Js::Tick::s_luBegin.QuadPart - *v4;
      if ( result > v4[1] )
        v4[1] = result;
    }
  }
  if ( !*(_BYTE *)(a1 + 160) || !*(_QWORD *)(a1 + 168) )
    goto LABEL_7;
  while ( 1 )
  {
    v30 = InterlockedPopEntrySList((PSLIST_HEADER)(*(_QWORD *)(a1 + 168) + 64LL));
    v31 = v30;
    if ( !v30 )
      break;
    if ( *(_BYTE *)(a1 + 179) )
      goto LABEL_38;
    v35 = (_DWORD *)*((_QWORD *)&v30->Next + 1);
    Next = (unsigned int)v30[1].Next;
    SegmentList = Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::GetSegmentList(
                    a1,
                    v35);
    if ( a2 )
    {
      Memory::PageSegmentBase<Memory::VirtualAllocWrapper>::DecommitPages<0>(v35, v31, Next);
      Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::SubUsedBytes(
        a1,
        (unsigned __int64)Next << 12);
      *(_QWORD *)(a1 + 240) -= (unsigned __int64)Next << 12;
      v33 = *(_QWORD *)(a1 + 240);
      v34 = v35[33];
      if ( v35[6] - v35[10] != v34 )
        goto LABEL_40;
      v38 = (unsigned int)(v34 << 12);
      *(_QWORD *)(a1 + 240) = v38 + v33;
      v39 = *((_QWORD *)v35 + 3) << 12;
      v40 = v33 + v38 - v39;
      *(_QWORD *)(a1 + 240) = v40;
      *(_QWORD *)(a1 + 232) -= v39;
      --*(_QWORD *)(a1 + 248);
      DListBase<Memory::PageSegmentBase<Memory::VirtualAllocWrapper>,FakeCount>::RemoveElement<Memory::NoThrowHeapAllocator>(
        v40,
        v33,
        v35);
    }
    else
    {
      memset_0(v31, 0, Next << 12);
      Memory::PageSegmentBase<Memory::VirtualAllocWrapper>::ReleasePages(v35, v31, Next);
      Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::SubUsedBytes(
        a1,
        (unsigned __int64)Next << 12);
LABEL_40:
      Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::TransferSegment(
        a1,
        v35,
        SegmentList);
    }
  }
  v32 = *(_QWORD *)(a1 + 168);
  EnterCriticalSection((LPCRITICAL_SECTION)(v32 + 16));
  *(_BYTE *)(a1 + 177) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v32 + 16));
LABEL_38:
  result = Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::FlushBackgroundPages(a1);
LABEL_7:
  if ( *(_QWORD *)(a1 + 120) )
  {
    result = Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::UpdateMinFreePageCount(a1);
    if ( a2 )
    {
      v5 = 0;
    }
    else
    {
      result = *(_QWORD *)(a1 + 184) >> 1;
      v5 = 4096;
      if ( (unsigned __int64)(*(_QWORD *)(a1 + 120) - result) > 0x1000 )
        v5 = *(_QWORD *)(a1 + 120) - result;
    }
    v6 = *(_QWORD *)(a1 + 120);
    if ( v5 < v6 )
    {
      v7 = v6 - v5;
      v8 = 0;
      v9 = (_QWORD *)(a1 + 72);
      v10 = (_QWORD *)(a1 + 72);
      do
      {
        if ( !v7 )
          break;
        v10 = (_QWORD *)*v10;
        if ( v10 == v9 )
          break;
        v11 = Memory::PageSegmentBase<Memory::VirtualAllocWrapper>::DecommitFreePages(v10 + 2, v7);
        *(_QWORD *)(a1 + 240) -= v11 << 12;
        v12 = *(_QWORD *)(a1 + 240);
        v8 += v11;
        v13 = *((_DWORD *)v10 + 37);
        if ( v13 == *(_DWORD *)(a1 + 104) )
        {
          v25 = (unsigned int)(v13 << 12);
          v26 = (unsigned int)v25;
          *(_QWORD *)(a1 + 240) = v25 + v12;
          v27 = v10[5] << 12;
          *(_QWORD *)(a1 + 240) = v12 + v26 - v27;
          *(_QWORD *)(a1 + 232) -= v27;
          --*(_QWORD *)(a1 + 248);
          v28 = (_QWORD *)v10[1];
          *v28 = *v10;
          v29 = *v10;
          *(_QWORD *)(v29 + 8) = v10[1];
          Memory::DeleteObject<Memory::NoThrowHeapAllocator,0,DListNode<Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>>(
            v29,
            v10);
          v10 = v28;
        }
        v7 -= v11;
      }
      while ( !*(_BYTE *)(a1 + 179) );
      if ( !*(_BYTE *)(a1 + 179) )
      {
        while ( v7 )
        {
          v14 = (_QWORD **)(a1 + 56);
          v15 = *(_QWORD *)(a1 + 56);
          if ( v15 == a1 + 56 )
            break;
          if ( v7 < *(unsigned int *)(a1 + 104) )
          {
            v22 = Memory::PageSegmentBase<Memory::VirtualAllocWrapper>::DecommitFreePages(v15 + 16, v7);
            *(_QWORD *)(a1 + 240) -= v22 << 12;
            v8 += v22;
            v23 = *v14;
            *(_QWORD *)(*v14)[1] = **v14;
            *(_QWORD *)(*v23 + 8LL) = v23[1];
            v24 = *v9;
            v23[1] = *(_QWORD *)(*v9 + 8LL);
            *v23 = v24;
            **(_QWORD **)(v24 + 8) = v23;
            *(_QWORD *)(v24 + 8) = v23;
            v7 = 0;
          }
          else
          {
            v16 = *(_QWORD *)(v15 + 40) << 12;
            *(_QWORD *)(a1 + 240) -= v16;
            *(_QWORD *)(a1 + 232) -= v16;
            --*(_QWORD *)(a1 + 248);
            DListBase<Memory::PageSegmentBase<Memory::VirtualAllocWrapper>,FakeCount>::RemoveHead<Memory::NoThrowHeapAllocator>(a1 + 56);
            v17 = *(unsigned int *)(a1 + 104);
            v7 -= v17;
            v8 += v17;
          }
          if ( *(_BYTE *)(a1 + 179) )
            goto LABEL_26;
        }
        v19 = (_QWORD **)(a1 + 24);
        do
        {
          if ( !v7 )
            break;
          v21 = *v19;
          if ( *v19 == (_QWORD *)(a1 + 24) )
            break;
          v18 = Memory::PageSegmentBase<Memory::VirtualAllocWrapper>::DecommitFreePages(v21 + 2, v7);
          *(_QWORD *)(a1 + 240) -= v18 << 12;
          v8 += v18;
          v19 = (_QWORD **)v21[1];
          *v19 = (_QWORD *)*v21;
          *(_QWORD *)(*v21 + 8LL) = v21[1];
          v20 = *v9;
          v21[1] = *(_QWORD *)(*v9 + 8LL);
          *v21 = v20;
          **(_QWORD **)(v20 + 8) = v21;
          *(_QWORD *)(v20 + 8) = v21;
          v7 -= v18;
        }
        while ( !*(_BYTE *)(a1 + 179) );
      }
LABEL_26:
      *(_QWORD *)(a1 + 120) = v5 + v7;
      result = *(_QWORD *)(a1 + 208);
      if ( result )
      {
        *(_QWORD *)(result + 56) += v8;
        result = v5 + v7;
        *(_QWORD *)(*(_QWORD *)(a1 + 208) + 64LL) += v5 + v7;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18016a0c8  mov     rax, rsp
0x18016a0cb  mov     [rax+10h], dl
0x18016a0ce  mov     [rax+8], rcx
0x18016a0d2  push    rbp
0x18016a0d3  push    rsi
0x18016a0d4  push    rdi
0x18016a0d5  push    r12
0x18016a0d7  push    r13
0x18016a0d9  push    r14
0x18016a0db  push    r15
0x18016a0dd  sub     rsp, 30h
0x18016a0e1  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x18016a0e9  mov     [rax+18h], rbx
0x18016a0ed  mov     rdi, rcx
0x18016a0f0  mov     rax, [rcx+0D0h]
0x18016a0f7  test    rax, rax
0x18016a0fa  jz      short loc_18016A14E
0x18016a0fc  inc     qword ptr [rax+30h]
0x18016a100  mov     rcx, [rcx+0D0h]; this
0x18016a107  call    ?ToMicroseconds@Tick@Js@@QEBA_KXZ; Js::Tick::ToMicroseconds(void)
0x18016a10c  test    rax, rax
0x18016a10f  jz      short loc_18016A14E
0x18016a111  mov     rax, qword ptr cs:?s_luBegin@Tick@Js@@0_KA; unsigned __int64 Js::Tick::s_luBegin ...
0x18016a118  mov     qword ptr [rsp+68h+PerformanceCount], rax
0x18016a11d  lea     rcx, [rsp+68h+PerformanceCount]; lpPerformanceCount
0x18016a122  call    cs:__imp_QueryPerformanceCounter
0x18016a129  nop     dword ptr [rax+rax+00h]
0x18016a12e  mov     rcx, [rdi+0D0h]
0x18016a135  mov     rax, qword ptr [rsp+68h+PerformanceCount]
0x18016a13a  sub     rax, qword ptr cs:?s_luBegin@Tick@Js@@0_KA; unsigned __int64 Js::Tick::s_luBegin ...
0x18016a141  sub     rax, [rcx]
0x18016a144  cmp     rax, [rcx+8]
0x18016a148  jle     short loc_18016A14E
0x18016a14a  mov     [rcx+8], rax
0x18016a14e  mov     r15b, [rsp+68h+arg_8]
0x18016a153  cmp     byte ptr [rdi+0A0h], 0
0x18016a15a  jz      short loc_18016A16A
0x18016a15c  cmp     qword ptr [rdi+0A8h], 0
0x18016a164  jnz     loc_18016A3EB
0x18016a16a  cmp     qword ptr [rdi+78h], 0
0x18016a16f  jnz     short loc_18016A18A
0x18016a171  mov     rbx, [rsp+68h+arg_10]
0x18016a179  add     rsp, 30h
0x18016a17d  pop     r15
0x18016a17f  pop     r14
0x18016a181  pop     r13
0x18016a183  pop     r12
0x18016a185  pop     rdi
0x18016a186  pop     rsi
0x18016a187  pop     rbp
0x18016a188  retn
0x18016a18a  mov     rcx, rdi
0x18016a18d  call    ?UpdateMinFreePageCount@?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@IEAAXXZ; Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::UpdateMinFreePageCount(void)
0x18016a192  test    r15b, r15b
0x18016a195  jz      loc_18016A319
0x18016a19b  xor     r14d, r14d
0x18016a19e  mov     rsi, [rdi+78h]
0x18016a1a2  cmp     r14, rsi
0x18016a1a5  jnb     short loc_18016A171
0x18016a1a7  sub     rsi, r14
0x18016a1aa  xor     ebp, ebp
0x18016a1ac  lea     r13, [rdi+48h]
0x18016a1b0  mov     r15, r13
0x18016a1b3  test    rsi, rsi
0x18016a1b6  jz      short loc_18016A203
0x18016a1b8  mov     r15, [r15]
0x18016a1bb  cmp     r15, r13
0x18016a1be  jz      short loc_18016A203
0x18016a1c0  lea     rcx, [r15+10h]
0x18016a1c4  mov     rdx, rsi
0x18016a1c7  call    ?DecommitFreePages@?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@Memory@@QEAA_K_K@Z; Memory::PageSegmentBase<Memory::VirtualAllocWrapper>::DecommitFreePages(unsigned __int64)
0x18016a1cc  mov     r12, rax
0x18016a1cf  mov     rcx, rax
0x18016a1d2  shl     rcx, 0Ch
0x18016a1d6  sub     [rdi+0F0h], rcx
0x18016a1dd  mov     rdx, [rdi+0F0h]
0x18016a1e4  add     rbp, rax
0x18016a1e7  mov     eax, [r15+94h]
0x18016a1ee  cmp     eax, [rdi+68h]
0x18016a1f1  jz      loc_18016A392
0x18016a1f7  sub     rsi, r12
0x18016a1fa  cmp     byte ptr [rdi+0B3h], 0
0x18016a201  jz      short loc_18016A1B3
0x18016a203  cmp     byte ptr [rdi+0B3h], 0
0x18016a20a  jnz     loc_18016A2CC
0x18016a210  xor     al, al
0x18016a212  test    rsi, rsi
0x18016a215  jz      loc_18016A300
0x18016a21b  lea     rbx, [rdi+38h]
0x18016a21f  mov     rcx, [rbx]
0x18016a222  cmp     rcx, rbx
0x18016a225  jz      loc_18016A2FC
0x18016a22b  mov     eax, [rdi+68h]
0x18016a22e  cmp     rsi, rax
0x18016a231  jb      loc_18016A33C
0x18016a237  mov     rax, [rcx+28h]
0x18016a23b  shl     rax, 0Ch
0x18016a23f  sub     [rdi+0F0h], rax
0x18016a246  sub     [rdi+0E8h], rax
0x18016a24d  dec     qword ptr [rdi+0F8h]
0x18016a254  mov     rcx, rbx
0x18016a257  call    ??$RemoveHead@VNoThrowHeapAllocator@Memory@@@?$DListBase@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@Memory@@VFakeCount@@@@QEAAXPEAVNoThrowHeapAllocator@Memory@@@Z; DListBase<Memory::PageSegmentBase<Memory::VirtualAllocWrapper>,FakeCount>::RemoveHead<Memory::NoThrowHeapAllocator>(Memory::NoThrowHeapAllocator *)
0x18016a25c  mov     eax, [rdi+68h]
0x18016a25f  sub     rsi, rax
0x18016a262  add     rbp, rax
0x18016a265  mov     al, [rdi+0B3h]
0x18016a26b  test    al, al
0x18016a26d  jz      short loc_18016A212
0x18016a26f  jmp     short loc_18016A2CC
0x18016a271  lea     rcx, [rbx+10h]
0x18016a275  mov     rdx, rsi
0x18016a278  call    ?DecommitFreePages@?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@Memory@@QEAA_K_K@Z; Memory::PageSegmentBase<Memory::VirtualAllocWrapper>::DecommitFreePages(unsigned __int64)
0x18016a27d  mov     r8, rax
0x18016a280  mov     rcx, rax
0x18016a283  shl     rcx, 0Ch
0x18016a287  sub     [rdi+0F0h], rcx
0x18016a28e  add     rbp, rax
0x18016a291  mov     r9, [rbx+8]
0x18016a295  mov     rcx, [rbx]
0x18016a298  mov     [r9], rcx
0x18016a29b  mov     rdx, [rbx]
0x18016a29e  mov     rcx, [rbx+8]
0x18016a2a2  mov     [rdx+8], rcx
0x18016a2a6  mov     rcx, [r13+0]
0x18016a2aa  mov     rax, [rcx+8]
0x18016a2ae  mov     [rbx+8], rax
0x18016a2b2  mov     [rbx], rcx
0x18016a2b5  mov     rax, [rcx+8]
0x18016a2b9  mov     [rax], rbx
0x18016a2bc  mov     [rcx+8], rbx
0x18016a2c0  sub     rsi, r8
0x18016a2c3  cmp     byte ptr [rdi+0B3h], 0
0x18016a2ca  jz      short loc_18016A307
0x18016a2cc  lea     rax, [r14+rsi]
0x18016a2d0  mov     [rdi+78h], rax
0x18016a2d4  mov     rax, [rdi+0D0h]
0x18016a2db  test    rax, rax
0x18016a2de  jz      loc_18016A171
0x18016a2e4  add     [rax+38h], rbp
0x18016a2e8  mov     rcx, [rdi+0D0h]
0x18016a2ef  lea     rax, [r14+rsi]
0x18016a2f3  add     [rcx+40h], rax
0x18016a2f7  jmp     loc_18016A171
0x18016a2fc  test    al, al
0x18016a2fe  jnz     short loc_18016A2CC
0x18016a300  lea     r15, [rdi+18h]
0x18016a304  mov     r9, r15
0x18016a307  test    rsi, rsi
0x18016a30a  jz      short loc_18016A2CC
0x18016a30c  mov     rbx, [r9]
0x18016a30f  cmp     rbx, r15
0x18016a312  jz      short loc_18016A2CC
0x18016a314  jmp     loc_18016A271
0x18016a319  mov     rax, [rdi+0B8h]
0x18016a320  shr     rax, 1
0x18016a323  mov     rcx, [rdi+78h]
0x18016a327  sub     rcx, rax
0x18016a32a  mov     r14d, 1000h
0x18016a330  cmp     rcx, r14
0x18016a333  cmova   r14, rcx
0x18016a337  jmp     loc_18016A19E
0x18016a33c  add     rcx, 10h
0x18016a340  mov     rdx, rsi
0x18016a343  call    ?DecommitFreePages@?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@Memory@@QEAA_K_K@Z; Memory::PageSegmentBase<Memory::VirtualAllocWrapper>::DecommitFreePages(unsigned __int64)
0x18016a348  mov     rcx, rax
0x18016a34b  shl     rcx, 0Ch
0x18016a34f  sub     [rdi+0F0h], rcx
0x18016a356  add     rbp, rax
0x18016a359  mov     rdx, [rbx]
0x18016a35c  mov     rcx, [rdx+8]
0x18016a360  mov     rax, [rdx]
0x18016a363  mov     [rcx], rax
0x18016a366  mov     rcx, [rdx]
0x18016a369  mov     rax, [rdx+8]
0x18016a36d  mov     [rcx+8], rax
0x18016a371  mov     rcx, [r13+0]
0x18016a375  mov     rax, [rcx+8]
0x18016a379  mov     [rdx+8], rax
0x18016a37d  mov     [rdx], rcx
0x18016a380  mov     rax, [rcx+8]
0x18016a384  mov     [rax], rdx
0x18016a387  mov     [rcx+8], rdx
0x18016a38b  xor     esi, esi
0x18016a38d  jmp     loc_18016A265
0x18016a392  shl     eax, 0Ch
0x18016a395  mov     r8d, eax
0x18016a398  lea     rcx, [rax+rdx]
0x18016a39c  mov     [rdi+0F0h], rcx
0x18016a3a3  mov     rax, [r15+28h]
0x18016a3a7  shl     rax, 0Ch
0x18016a3ab  sub     r8, rax
0x18016a3ae  add     r8, rdx
0x18016a3b1  mov     [rdi+0F0h], r8
0x18016a3b8  sub     [rdi+0E8h], rax
0x18016a3bf  dec     qword ptr [rdi+0F8h]
0x18016a3c6  mov     rbx, [r15+8]
0x18016a3ca  mov     rax, [r15]
0x18016a3cd  mov     [rbx], rax
0x18016a3d0  mov     rcx, [r15]
0x18016a3d3  mov     rax, [r15+8]
0x18016a3d7  mov     [rcx+8], rax
0x18016a3db  mov     rdx, r15
0x18016a3de  call    ??$DeleteObject@VNoThrowHeapAllocator@Memory@@$0A@V?$DListNode@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@Memory@@@@@Memory@@YAXPEAVNoThrowHeapAllocator@0@PEAV?$DListNode@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@Memory@@@@@Z; Memory::DeleteObject<Memory::NoThrowHeapAllocator,0,DListNode<Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>>(Memory::NoThrowHeapAllocator *,DListNode<Memory::PageSegmentBase<Memory::VirtualAllocWrapper>> *)
0x18016a3e3  mov     r15, rbx
0x18016a3e6  jmp     loc_18016A1F7
0x18016a3eb  mov     rcx, [rdi+0A8h]
0x18016a3f2  add     rcx, 40h ; '@'; ListHead
0x18016a3f6  call    cs:__imp_InterlockedPopEntrySList
0x18016a3fd  nop     dword ptr [rax+rax+00h]
0x18016a402  mov     rsi, rax
0x18016a405  test    rax, rax
0x18016a408  jnz     loc_18016A491
0x18016a40e  mov     rbx, [rdi+0A8h]
0x18016a415  lea     rcx, [rbx+10h]; lpCriticalSection
0x18016a419  call    cs:__imp_EnterCriticalSection
0x18016a420  nop     dword ptr [rax+rax+00h]
0x18016a425  mov     [rdi+0B1h], sil
0x18016a42c  lea     rcx, [rbx+10h]; lpCriticalSection
0x18016a430  call    cs:__imp_LeaveCriticalSection
0x18016a437  nop     dword ptr [rax+rax+00h]
0x18016a43c  nop
0x18016a43d  mov     rcx, rdi
0x18016a440  call    ?FlushBackgroundPages@?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@QEAAXXZ; Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::FlushBackgroundPages(void)
0x18016a445  jmp     loc_18016A16A
0x18016a44a  mov     rdx, rsi
0x18016a44d  mov     rcx, rbx
0x18016a450  call    ??$DecommitPages@$0A@@?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@Memory@@QEAAXPEAXI@Z; Memory::PageSegmentBase<Memory::VirtualAllocWrapper>::DecommitPages<0>(void *,uint)
0x18016a455  mov     rdx, rbp
0x18016a458  mov     rcx, rdi
0x18016a45b  call    ?SubUsedBytes@?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@AEAAX_K@Z; Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::SubUsedBytes(unsigned __int64)
0x18016a460  sub     [rdi+0F0h], rbp
0x18016a467  mov     rdx, [rdi+0F0h]
0x18016a46e  mov     ecx, [rbx+84h]
0x18016a474  mov     eax, [rbx+18h]
0x18016a477  sub     eax, [rbx+28h]
0x18016a47a  cmp     eax, ecx
0x18016a47c  jz      short loc_18016A4E8
0x18016a47e  mov     r8, r12
0x18016a481  mov     rdx, rbx
0x18016a484  mov     rcx, rdi
0x18016a487  call    ?TransferSegment@?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@IEAAXPEAV?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@PEAV?$DListBase@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@Memory@@VFakeCount@@@@@Z; Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::TransferSegment(Memory::PageSegmentBase<Memory::VirtualAllocWrapper> *,DListBase<Memory::PageSegmentBase<Memory::VirtualAllocWrapper>,FakeCount> *)
0x18016a48c  jmp     loc_18016A3EB
0x18016a491  cmp     byte ptr [rdi+0B3h], 0
0x18016a498  jnz     short loc_18016A43D
0x18016a49a  mov     rbx, [rax+8]
0x18016a49e  mov     r14d, [rax+10h]
0x18016a4a2  mov     rdx, rbx
0x18016a4a5  mov     rcx, rdi
0x18016a4a8  call    ?GetSegmentList@?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@IEAAPEAV?$DListBase@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@Memory@@VFakeCount@@@@PEAV?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Z; Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::GetSegmentList(Memory::PageSegmentBase<Memory::VirtualAllocWrapper> *)
0x18016a4ad  mov     r12, rax
0x18016a4b0  mov     ebp, r14d
0x18016a4b3  shl     rbp, 0Ch
0x18016a4b7  mov     r8d, r14d
0x18016a4ba  test    r15b, r15b
0x18016a4bd  jnz     short loc_18016A44A
0x18016a4bf  shl     r8d, 0Ch; Size
0x18016a4c3  xor     edx, edx; Val
0x18016a4c5  mov     rcx, rsi; void *
0x18016a4c8  call    memset_0
0x18016a4cd  mov     r8d, r14d
0x18016a4d0  mov     rdx, rsi
0x18016a4d3  mov     rcx, rbx
0x18016a4d6  call    ?ReleasePages@?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@Memory@@QEAAXPEAXI@Z; Memory::PageSegmentBase<Memory::VirtualAllocWrapper>::ReleasePages(void *,uint)
0x18016a4db  mov     rdx, rbp
0x18016a4de  mov     rcx, rdi
0x18016a4e1  call    ?SubUsedBytes@?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@AEAAX_K@Z; Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::SubUsedBytes(unsigned __int64)
0x18016a4e6  jmp     short loc_18016A47E
0x18016a4e8  shl     ecx, 0Ch
0x18016a4eb  lea     rax, [rcx+rdx]
0x18016a4ef  mov     [rdi+0F0h], rax
0x18016a4f6  mov     rax, [rbx+18h]
0x18016a4fa  shl     rax, 0Ch
0x18016a4fe  sub     rcx, rax
0x18016a501  add     rcx, rdx
0x18016a504  mov     [rdi+0F0h], rcx
0x18016a50b  sub     [rdi+0E8h], rax
0x18016a512  dec     qword ptr [rdi+0F8h]
0x18016a519  mov     r8, rbx
0x18016a51c  call    ??$RemoveElement@VNoThrowHeapAllocator@Memory@@@?$DListBase@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@Memory@@VFakeCount@@@@QEAAXPEAVNoThrowHeapAllocator@Memory@@PEAV?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Z; DListBase<Memory::PageSegmentBase<Memory::VirtualAllocWrapper>,FakeCount>::RemoveElement<Memory::NoThrowHeapAllocator>(Memory::NoThrowHeapAllocator *,Memory::PageSegmentBase<Memory::VirtualAllocWrapper> *)
0x18016a521  jmp     loc_18016A3EB
```
