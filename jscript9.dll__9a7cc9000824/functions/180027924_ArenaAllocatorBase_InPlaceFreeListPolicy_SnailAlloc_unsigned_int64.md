# ArenaAllocatorBase<InPlaceFreeListPolicy>::SnailAlloc(unsigned __int64)

- ea: `0x180027924`
- end: `0x180027f07`
- name: `?SnailAlloc@?$ArenaAllocatorBase@VInPlaceFreeListPolicy@@@@AEAAPEAD_K@Z`
- size: `1507`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038c24`
- `0x180039630`
- `0x180091620`
- `0x180137d4c`
- `0x18013ddf4`
- `0x18013f028`
- `0x18014bb38`
- `0x18014f2f4`

## callees

- `0x180004f94`
- `0x180008e7c`
- `0x1800215c0`
- `0x180026314`
- `0x180026bc0`
- `0x180027924`
- `0x180028284`
- `0x1801b3d5c`
- `0x18025a1fc`
- `0x18025a464`
- `0x180364010`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x180027e84`
- `KERNEL32!InterlockedPushEntrySList` at `0x180027e84`
- `KERNEL32!InterlockedPopEntrySList` at `0x180027cb5`
- `KERNEL32!InterlockedPopEntrySList` at `0x180027cb5`

## pseudocode

```c
char *__fastcall ArenaAllocatorBase<InPlaceFreeListPolicy>::SnailAlloc(unsigned __int64 a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v3; // r12
  unsigned __int64 v4; // r14
  PageAllocator **v5; // r15
  void (*v6)(void); // rax
  char *v7; // rbx
  __int64 v8; // r8
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  char *result; // rax
  _QWORD *v12; // r9
  unsigned __int64 v13; // r8
  _QWORD *v14; // r10
  int v15; // r11d
  __int64 v16; // rax
  char *v17; // r11
  unsigned __int64 v18; // rcx
  signed __int64 v19; // rax
  _QWORD *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rcx
  unsigned int v23; // eax
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rax
  __int64 v26; // rax
  unsigned __int64 v27; // rbx
  __int64 v28; // rsi
  bool v29; // zf
  unsigned __int64 v30; // r15
  unsigned __int64 *v31; // r9
  unsigned __int64 *v32; // r13
  char v33; // r8
  struct PageSegment *v34; // rbp
  unsigned int v35; // ebx
  unsigned int v36; // eax
  unsigned int v37; // edx
  unsigned int v38; // r11d
  unsigned int v39; // r10d
  char v40; // cl
  unsigned int v41; // r8d
  union _SLIST_HEADER *v42; // rcx
  PSLIST_ENTRY v43; // rax
  PSLIST_ENTRY v44; // r13
  _QWORD **v45; // r8
  _QWORD *v46; // rcx
  int v47; // edx
  _QWORD *v48; // rcx
  signed __int64 v49; // rax
  int Next; // ebx
  int v51; // ebx
  struct Segment *v52; // rax
  struct PageSegment *v53; // [rsp+28h] [rbp-50h] BYREF
  unsigned __int64 v54; // [rsp+30h] [rbp-48h]

  v2 = a1;
  v3 = a2;
  if ( a2 > *(_QWORD *)(a1 + 72) )
  {
LABEL_2:
    v4 = v3 + 32;
    if ( v3 + 32 < v3 )
    {
      v4 = -1;
LABEL_4:
      v5 = (PageAllocator **)(v2 + 40);
      goto LABEL_5;
    }
    if ( v3 + 4143 < v3 + 32 || v3 == -4144 )
      goto LABEL_4;
    v27 = (v3 + 4143) >> 12;
    v5 = (PageAllocator **)(v2 + 40);
    v28 = *(_QWORD *)(v2 + 40);
    v54 = v27;
    v53 = 0;
    if ( v27 > *(unsigned int *)(v28 + 88) )
    {
      v52 = PageAllocator::AllocSegment((PageAllocator *)v28, v27);
      v34 = v52;
      if ( !v52 )
        goto LABEL_5;
      v7 = (char *)*((_QWORD *)v52 + 2);
      a1 = *((_QWORD *)v52 + 3) - *((unsigned int *)v52 + 8);
      *(_QWORD *)v7 = a1;
      goto LABEL_28;
    }
    v29 = *(_DWORD *)(v28 + 152) == 0;
    *(_BYTE *)(v28 + 139) = 1;
    if ( v29 )
      AsymetricCriticalSection::FastEnter((AsymetricCriticalSection *)(v28 + 200));
    v30 = (unsigned int)v27;
    v31 = (unsigned __int64 *)(v28 + 8);
    if ( *(_QWORD *)(v28 + 104) >= (unsigned __int64)(unsigned int)v27 )
    {
      v32 = (unsigned __int64 *)(v28 + 8);
      v33 = 32 - v27;
LABEL_42:
      while ( 1 )
      {
        v32 = (unsigned __int64 *)*v32;
        if ( v32 == v31 )
          break;
        v34 = (struct PageSegment *)(v32 + 2);
        v35 = *((_DWORD *)v32 + 18);
        if ( v35 >= (unsigned int)v30 )
        {
          v36 = *((_DWORD *)v32 + 16);
          v29 = !_BitScanForward(&v37, v36);
          v38 = -1;
          if ( !v29 )
            v38 = v37;
          v39 = 0xFFFFFFFF >> v33;
          while ( 1 )
          {
            v33 = 32 - v30;
            if ( v38 == -1 )
              break;
            a2 = v32[5] - *((unsigned int *)v32 + 12) - v38;
            if ( a2 < v30 )
              break;
            if ( (_DWORD)v30 == 1 || (a2 = v39 << v38, (v36 & (v39 << v38)) == (_DWORD)a2) )
            {
              *((_DWORD *)v32 + 16) = v36 & ~(v39 << v38);
              *((_DWORD *)v32 + 18) = v35 - v30;
              v7 = (char *)(v32[4] + (v38 << 12));
              if ( !v7 )
                goto LABEL_42;
              a1 = (unsigned int)((_DWORD)v30 << 12);
              *(_QWORD *)(v28 + 160) += a1;
              v19 = _InterlockedExchangeAdd64(&qword_180443988, a1);
              if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
                McTemplateU0x_EventWriteTransfer(a1, a2, v19 + a1);
              if ( !*((_DWORD *)v32 + 18) )
              {
                *(_QWORD *)v32[1] = *v32;
                *(_QWORD *)(*v32 + 8) = v32[1];
                a1 = *(_QWORD *)(v28 + 24);
                v32[1] = *(_QWORD *)(a1 + 8);
                *v32 = a1;
                **(_QWORD **)(a1 + 8) = v32;
                *(_QWORD *)(a1 + 8) = v32;
              }
              goto LABEL_23;
            }
            v40 = v38 + 1;
            v38 = -1;
            v29 = !_BitScanForward(&v41, v36 & (-1 << v40));
            if ( !v29 )
              v38 = v41;
          }
        }
      }
      if ( (_DWORD)v30 == 1 )
      {
        v42 = *(union _SLIST_HEADER **)(v28 + 128);
        if ( v42 )
        {
          v43 = InterlockedPopEntrySList(v42);
          v44 = v43;
          if ( v43 )
          {
            v34 = (struct PageSegment *)*((_QWORD *)&v43->Next + 1);
            Next = (int)v43[1].Next;
            v53 = v34;
            if ( Next == 1 )
            {
              v7 = (char *)v43;
              *v43 = 0;
              v43[1] = 0;
            }
            else
            {
              v51 = Next - 1;
              LODWORD(v43[1].Next) = v51;
              InterlockedPushEntrySList(*(PSLIST_HEADER *)(v28 + 128), v43);
              v7 = (char *)v44 + (unsigned int)(v51 << 12);
            }
            if ( v7 )
              goto LABEL_24;
          }
          v31 = (unsigned __int64 *)(v28 + 8);
        }
      }
    }
    v45 = *(_QWORD ***)(v28 + 40);
    if ( v45 == (_QWORD **)(v28 + 40) )
    {
      v7 = PageAllocator::TryAllocDecommitedPages((PageAllocator *)v28, v30, &v53);
      if ( v7 )
      {
LABEL_60:
        v34 = v53;
LABEL_24:
        if ( !*(_DWORD *)(v28 + 152) )
          *(_DWORD *)(v28 + 240) = 0;
        v5 = (PageAllocator **)(v2 + 40);
        if ( !v7 )
          goto LABEL_5;
        *(_QWORD *)v7 = v54;
LABEL_28:
        *((_QWORD *)v7 + 1) = v34;
        if ( v7 )
        {
LABEL_29:
          v20 = v7 + 16;
          *((_QWORD *)v7 + 4) = v7;
          v21 = (*(_QWORD *)v7 << 12) - 48LL;
          *((_QWORD *)v7 + 5) = 0;
          *((_QWORD *)v7 + 3) = v21;
          ++*(_DWORD *)(v2 + 80);
          v22 = *(_QWORD *)(v2 + 16);
          if ( v22 )
          {
            *(_QWORD *)(v22 + 24) = *(_QWORD *)(v2 + 48) - v22 - 32;
            v23 = *(_DWORD *)(v2 + 64) - *(_DWORD *)(v2 + 48);
            if ( v23 >= 0x10 || *(_BYTE *)(v2 + 56) )
            {
              v24 = v23;
              v25 = *(_QWORD *)(v2 + 72);
              if ( v25 <= v24 )
                v25 = v24;
              *(_QWORD *)(v2 + 72) = v25;
            }
            else
            {
              v46 = *(_QWORD **)(v2 + 16);
              *(_QWORD *)(v2 + 16) = *v46;
              *v46 = *(_QWORD *)(v2 + 24);
              *(_QWORD *)(v2 + 24) = v46;
            }
          }
          v26 = *(_QWORD *)(v2 + 16);
          *(_QWORD *)(v2 + 48) = &v7[*((_QWORD *)v7 + 5) + 48];
          *(_QWORD *)(v2 + 64) = (char *)v20 + *((_QWORD *)v7 + 3) + 32;
          *v20 = v26;
          result = *(char **)(v2 + 48);
          *(_QWORD *)(v2 + 16) = v20;
          *(_QWORD *)(v2 + 48) = &result[v3];
          return result;
        }
LABEL_5:
        v6 = *(void (**)(void))(v2 + 8);
        if ( !v6 || (v6(), (v7 = (char *)PageAllocator::AllocPagesForBytes(*v5, v4)) == 0) )
        {
          v8 = v3 + 16;
          if ( v3 + 16 < v3 )
            v8 = -1;
          v9 = (_QWORD *)AllocateArray<HeapAllocator,char,1>(a1, a2, v8);
          v10 = v9;
          if ( v9 )
          {
            v9[1] = v3;
            *v9 = *(_QWORD *)(v2 + 32);
            result = (char *)(v9 + 2);
            *(_QWORD *)(v2 + 32) = v10;
            *(_DWORD *)(v2 + 80) = 2;
          }
          else
          {
            if ( *(_QWORD *)v2 )
              (*(void (__fastcall **)(_QWORD))v2)(0);
            return 0;
          }
          return result;
        }
        goto LABEL_29;
      }
      v34 = (struct PageSegment *)PageAllocator::AddPageSegment((PageAllocator *)v28);
      if ( !v34 )
      {
        v7 = 0;
        goto LABEL_60;
      }
    }
    else
    {
      v34 = (struct PageSegment *)(v45 + 2);
      v47 = *(_DWORD *)(v28 + 88);
      *v45[1] = *v45;
      (*v45)[1] = v45[1];
      if ( (_DWORD)v30 == v47 )
        v48 = *(_QWORD **)(v28 + 24);
      else
        v48 = (_QWORD *)*v31;
      v45[1] = (_QWORD *)v48[1];
      *v45 = v48;
      *(_QWORD *)v48[1] = v45;
      v48[1] = v45;
    }
    v7 = PageSegment::AllocPages(v34, v30);
    a1 = (unsigned int)((_DWORD)v30 << 12);
    *(_QWORD *)(v28 + 160) += a1;
    v49 = _InterlockedExchangeAdd64(&qword_180443988, a1);
    if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
      McTemplateU0x_EventWriteTransfer(a1, a2, v49 + a1);
LABEL_23:
    *(_QWORD *)(v28 + 104) -= v30;
    goto LABEL_24;
  }
  v12 = *(_QWORD **)(a1 + 16);
  v13 = 0;
  v14 = v12;
  a2 = *v12;
  v15 = 10;
  while ( 1 )
  {
    v16 = *(_QWORD *)(a2 + 24);
    a1 = *(_QWORD *)(a2 + 8) - v16;
    if ( a1 >= v3 )
      break;
    if ( v13 <= a1 )
      v13 = *(_QWORD *)(a2 + 8) - v16;
    if ( --v15 )
    {
      v14 = (_QWORD *)a2;
      a2 = *(_QWORD *)a2;
      if ( a2 )
        continue;
    }
    goto LABEL_2;
  }
  v17 = (char *)(v16 + a2);
  *(_QWORD *)(a2 + 24) = v3 + v16;
  if ( a1 == *(_QWORD *)(v2 + 72) || v13 > *(_QWORD *)(v2 + 72) )
    *(_QWORD *)(v2 + 72) = v13;
  v18 = a1 - v3;
  if ( v18 > v12[1] - v12[3] )
  {
    *v14 = *(_QWORD *)a2;
    ArenaAllocatorBase<InPlaceFreeListPolicy>::SetCacheBlock(v2, a2, v13, v12);
  }
  else if ( v18 < 0x10 && !*(_BYTE *)(v2 + 56) )
  {
    *v14 = *(_QWORD *)a2;
    *(_QWORD *)a2 = *(_QWORD *)(v2 + 24);
    *(_QWORD *)(v2 + 24) = a2;
  }
  return v17 + 32;
}

```

## disassembly

```asm
0x180027924  mov     rax, rsp
0x180027927  mov     [rax+18h], rbx
0x18002792b  mov     [rax+10h], rdx
0x18002792f  mov     [rax+8], rcx
0x180027933  push    rbp
0x180027934  push    rsi
0x180027935  push    rdi
0x180027936  push    r12
0x180027938  push    r13
0x18002793a  push    r14
0x18002793c  push    r15
0x18002793e  sub     rsp, 40h
0x180027942  mov     rdi, rcx
0x180027945  mov     r12, rdx
0x180027948  cmp     rdx, [rcx+48h]
0x18002794c  jbe     short loc_1800279C8
0x18002794e  lea     r14, [r12+20h]
0x180027953  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180027957  cmp     r14, r12
0x18002795a  jnb     loc_180027B95
0x180027960  mov     r14, rsi
0x180027963  lea     r15, [rdi+28h]
0x180027967  mov     rax, [rdi+8]
0x18002796b  test    rax, rax
0x18002796e  jz      short loc_18002798C
0x180027970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027975  mov     rcx, [r15]; this
0x180027978  mov     rdx, r14; unsigned __int64
0x18002797b  call    ?AllocPagesForBytes@PageAllocator@@QEAAPEAVPageAllocation@@_K@Z; PageAllocator::AllocPagesForBytes(unsigned __int64)
0x180027980  mov     rbx, rax
0x180027983  test    rax, rax
0x180027986  jnz     loc_180027AB6
0x18002798c  lea     r8, [r12+10h]
0x180027991  cmp     r8, r12
0x180027994  cmovb   r8, rsi
0x180027998  call    ??$AllocateArray@UHeapAllocator@@D$00@@YAPEADPEAUHeapAllocator@@P80@EAAPEAD_K@Z1@Z; AllocateArray<HeapAllocator,char,1>(HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x18002799d  mov     rcx, rax
0x1800279a0  test    rax, rax
0x1800279a3  jz      loc_180027EF3
0x1800279a9  mov     [rax+8], r12
0x1800279ad  mov     rax, [rdi+20h]
0x1800279b1  mov     [rcx], rax
0x1800279b4  lea     rax, [rcx+10h]
0x1800279b8  mov     [rdi+20h], rcx
0x1800279bc  mov     dword ptr [rdi+50h], 2
0x1800279c3  jmp     loc_180027B45
0x1800279c8  mov     r9, [rdi+10h]
0x1800279cc  xor     r8d, r8d
0x1800279cf  mov     r10, r9
0x1800279d2  mov     rdx, [r9]
0x1800279d5  lea     r11d, [r8+0Ah]
0x1800279d9  mov     rax, [rdx+18h]
0x1800279dd  mov     rcx, [rdx+8]
0x1800279e1  sub     rcx, rax
0x1800279e4  cmp     rcx, r12
0x1800279e7  jb      loc_180027DB6
0x1800279ed  lea     r11, [rax+rdx]
0x1800279f1  add     rax, r12
0x1800279f4  mov     [rdx+18h], rax
0x1800279f8  cmp     rcx, [rdi+48h]
0x1800279fc  jnz     loc_180027D28
0x180027a02  mov     [rdi+48h], r8
0x180027a06  mov     rax, [r9+8]
0x180027a0a  sub     rcx, r12
0x180027a0d  sub     rax, [r9+18h]
0x180027a11  cmp     rcx, rax
0x180027a14  ja      loc_180027E48
0x180027a1a  cmp     rcx, 10h
0x180027a1e  jb      loc_180027DDB
0x180027a24  lea     rax, [r11+20h]
0x180027a28  jmp     loc_180027B45
0x180027a2d  sub     ebx, r15d
0x180027a30  mov     ecx, r11d
0x180027a33  shl     r10d, cl
0x180027a36  shl     r11d, 0Ch
0x180027a3a  not     r10d
0x180027a3d  and     r10d, eax
0x180027a40  mov     [rbp+30h], r10d
0x180027a44  mov     [rbp+38h], ebx
0x180027a47  mov     ebx, r11d
0x180027a4a  add     rbx, [rbp+10h]
0x180027a4e  jz      loc_180027C09
0x180027a54  mov     eax, r15d
0x180027a57  shl     eax, 0Ch
0x180027a5a  mov     ecx, eax
0x180027a5c  add     [rsi+0A0h], rcx
0x180027a63  lock xadd cs:qword_180443988, rax
0x180027a6c  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180027a73  jnz     loc_180027EE5
0x180027a79  cmp     dword ptr [rbp+38h], 0
0x180027a7d  jz      loc_180027B5E
0x180027a83  sub     [rsi+68h], r15
0x180027a87  cmp     dword ptr [rsi+98h], 0
0x180027a8e  jz      loc_180027DFB
0x180027a94  lea     r15, [rdi+28h]
0x180027a98  test    rbx, rbx
0x180027a9b  jz      loc_180027EB3
0x180027aa1  mov     rax, [rsp+78h+var_48]
0x180027aa6  mov     [rbx], rax
0x180027aa9  mov     [rbx+8], rbp
0x180027aad  test    rbx, rbx
0x180027ab0  jz      loc_180027EB3
0x180027ab6  lea     rdx, [rbx+10h]
0x180027aba  mov     [rdx+10h], rbx
0x180027abe  mov     rax, [rbx]
0x180027ac1  shl     rax, 0Ch
0x180027ac5  sub     rax, 30h ; '0'
0x180027ac9  mov     qword ptr [rdx+18h], 0
0x180027ad1  mov     [rdx+8], rax
0x180027ad5  inc     dword ptr [rdi+50h]
0x180027ad8  mov     rcx, [rdi+10h]
0x180027adc  test    rcx, rcx
0x180027adf  jz      short loc_180027B10
0x180027ae1  mov     rax, [rdi+30h]
0x180027ae5  sub     rax, rcx
0x180027ae8  sub     rax, 20h ; ' '
0x180027aec  mov     [rcx+18h], rax
0x180027af0  mov     eax, [rdi+40h]
0x180027af3  sub     eax, [rdi+30h]
0x180027af6  cmp     eax, 10h
0x180027af9  jb      loc_180027D03
0x180027aff  mov     ecx, eax
0x180027b01  mov     rax, [rdi+48h]
0x180027b05  cmp     rax, rcx
0x180027b08  cmovbe  rax, rcx
0x180027b0c  mov     [rdi+48h], rax
0x180027b10  mov     rcx, [rdx+18h]
0x180027b14  mov     rax, [rdi+10h]
0x180027b18  add     rcx, 20h ; ' '
0x180027b1c  add     rcx, rdx
0x180027b1f  mov     [rdi+30h], rcx
0x180027b23  mov     rcx, [rdx+8]
0x180027b27  add     rcx, 20h ; ' '
0x180027b2b  add     rcx, rdx
0x180027b2e  mov     [rdi+40h], rcx
0x180027b32  mov     [rdx], rax
0x180027b35  mov     rax, [rdi+30h]
0x180027b39  mov     [rdi+10h], rdx
0x180027b3d  lea     rcx, [rax+r12]
0x180027b41  mov     [rdi+30h], rcx
0x180027b45  mov     rbx, [rsp+78h+arg_10]
0x180027b4d  add     rsp, 40h
0x180027b51  pop     r15
0x180027b53  pop     r14
0x180027b55  pop     r13
0x180027b57  pop     r12
0x180027b59  pop     rdi
0x180027b5a  pop     rsi
0x180027b5b  pop     rbp
0x180027b5c  retn
0x180027b5e  mov     rcx, [r13+8]
0x180027b62  mov     rax, [r13+0]
0x180027b66  mov     [rcx], rax
0x180027b69  mov     rcx, [r13+0]
0x180027b6d  mov     rax, [r13+8]
0x180027b71  mov     [rcx+8], rax
0x180027b75  mov     rcx, [rsi+18h]
0x180027b79  mov     rax, [rcx+8]
0x180027b7d  mov     [r13+8], rax
0x180027b81  mov     [r13+0], rcx
0x180027b85  mov     rax, [rcx+8]
0x180027b89  mov     [rax], r13
0x180027b8c  mov     [rcx+8], r13
0x180027b90  jmp     loc_180027A83
0x180027b95  lea     rbx, [r14+100Fh]
0x180027b9c  cmp     rbx, r14
0x180027b9f  jb      loc_180027963
0x180027ba5  cmp     rbx, rsi
0x180027ba8  jz      loc_180027963
0x180027bae  shr     rbx, 0Ch
0x180027bb2  lea     r15, [rdi+28h]
0x180027bb6  mov     rsi, [r15]
0x180027bb9  mov     [rsp+78h+var_48], rbx
0x180027bbe  mov     [rsp+78h+var_50], 0
0x180027bc7  mov     eax, [rsi+58h]
0x180027bca  cmp     rbx, rax
0x180027bcd  ja      loc_180027EBC
0x180027bd3  cmp     dword ptr [rsi+98h], 0
0x180027bda  mov     byte ptr [rsi+8Bh], 1
0x180027be1  jz      loc_180027E37
0x180027be7  mov     r15d, ebx
0x180027bea  lea     r9, [rsi+8]
0x180027bee  cmp     [rsi+68h], r15
0x180027bf2  jb      loc_180027CD1
0x180027bf8  mov     r8d, 20h ; ' '
0x180027bfe  mov     r13, r9
0x180027c01  sub     r8d, r15d
0x180027c04  mov     [rsp+78h+var_58], r8d
0x180027c09  mov     r13, [r13+0]
0x180027c0d  cmp     r13, r9
0x180027c10  jz      loc_180027CA3
0x180027c16  lea     rbp, [r13+10h]
0x180027c1a  mov     ebx, [rbp+38h]
0x180027c1d  cmp     ebx, r15d
0x180027c20  jb      short loc_180027C09
0x180027c22  mov     eax, [rbp+30h]
0x180027c25  bsf     edx, eax
0x180027c28  setnz   cl
0x180027c2b  or      r11d, 0FFFFFFFFh
0x180027c2f  test    cl, cl
0x180027c31  mov     ecx, r8d
0x180027c34  cmovnz  r11d, edx
0x180027c38  or      r10d, 0FFFFFFFFh
0x180027c3c  shr     r10d, cl
0x180027c3f  mov     r8d, [rsp+78h+var_58]
0x180027c44  mov     [rsp+78h+var_54], 0
0x180027c4c  cmp     r11d, 0FFFFFFFFh
0x180027c50  jz      short loc_180027C09
0x180027c52  mov     ecx, [rbp+20h]
0x180027c55  mov     rdx, [rbp+18h]
0x180027c59  sub     rdx, rcx
0x180027c5c  mov     ecx, r11d
0x180027c5f  sub     rdx, rcx
0x180027c62  cmp     rdx, r15
0x180027c65  jb      short loc_180027C09
0x180027c67  cmp     r15d, 1
0x180027c6b  jz      loc_180027A2D
0x180027c71  mov     ecx, r11d
0x180027c74  mov     edx, r10d
0x180027c77  shl     edx, cl
0x180027c79  mov     ecx, edx
0x180027c7b  and     ecx, eax
0x180027c7d  cmp     ecx, edx
0x180027c7f  jz      loc_180027A2D
0x180027c85  lea     ecx, [r11+1]
0x180027c89  or      r11d, 0FFFFFFFFh
0x180027c8d  mov     edx, r11d
0x180027c90  shl     edx, cl
0x180027c92  and     edx, eax
0x180027c94  bsf     r8d, edx
0x180027c98  setnz   cl
0x180027c9b  test    cl, cl
0x180027c9d  cmovnz  r11d, r8d
0x180027ca1  jmp     short loc_180027C3F
0x180027ca3  cmp     r15d, 1
0x180027ca7  jnz     short loc_180027CD1
0x180027ca9  mov     rcx, [rsi+80h]; ListHead
0x180027cb0  test    rcx, rcx
0x180027cb3  jz      short loc_180027CD1
0x180027cb5  call    cs:__imp_InterlockedPopEntrySList
0x180027cbc  nop     dword ptr [rax+rax+00h]
0x180027cc1  mov     r13, rax
0x180027cc4  test    rax, rax
0x180027cc7  jnz     loc_180027E64
0x180027ccd  lea     r9, [rsi+8]
0x180027cd1  lea     rax, [rsi+28h]
0x180027cd5  mov     r8, [rax]
0x180027cd8  cmp     r8, rax
0x180027cdb  jnz     short loc_180027D37
0x180027cdd  lea     r8, [rsp+78h+var_50]; struct PageSegment **
0x180027ce2  mov     edx, r15d; unsigned int
0x180027ce5  mov     rcx, rsi; this
0x180027ce8  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x180027ced  mov     rbx, rax
0x180027cf0  test    rax, rax
0x180027cf3  jz      loc_180027E0A
0x180027cf9  mov     rbp, [rsp+78h+var_50]
0x180027cfe  jmp     loc_180027A87
0x180027d03  cmp     byte ptr [rdi+38h], 0
0x180027d07  jnz     loc_180027AFF
0x180027d0d  mov     rcx, [rdi+10h]
0x180027d11  mov     rax, [rcx]
0x180027d14  mov     [rdi+10h], rax
0x180027d18  mov     rax, [rdi+18h]
0x180027d1c  mov     [rcx], rax
0x180027d1f  mov     [rdi+18h], rcx
0x180027d23  jmp     loc_180027B10
0x180027d28  cmp     r8, [rdi+48h]
0x180027d2c  jbe     loc_180027A06
0x180027d32  jmp     loc_180027A02
0x180027d37  mov     rcx, [r8+8]
0x180027d3b  lea     rbp, [r8+10h]
0x180027d3f  mov     rax, [r8]
0x180027d42  mov     edx, [rsi+58h]
0x180027d45  mov     [rcx], rax
0x180027d48  mov     rcx, [r8]
0x180027d4b  mov     rax, [r8+8]
0x180027d4f  mov     [rcx+8], rax
0x180027d53  cmp     r15d, edx
0x180027d56  jz      loc_180027E5B
0x180027d5c  mov     rcx, [r9]
0x180027d5f  mov     rax, [rcx+8]
0x180027d63  mov     [r8+8], rax
0x180027d67  mov     [r8], rcx
0x180027d6a  mov     rax, [rcx+8]
0x180027d6e  mov     [rax], r8
0x180027d71  mov     [rcx+8], r8
0x180027d75  mov     edx, r15d; unsigned int
0x180027d78  mov     rcx, rbp; this
0x180027d7b  call    ?AllocPages@PageSegment@@QEAAPEADI@Z; PageSegment::AllocPages(uint)
0x180027d80  mov     rbx, rax
0x180027d83  mov     eax, r15d
0x180027d86  shl     eax, 0Ch
0x180027d89  mov     ecx, eax
0x180027d8b  add     [rsi+0A0h], rcx
0x180027d92  lock xadd cs:qword_180443988, rax
0x180027d9b  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180027da2  jz      loc_180027A83
0x180027da8  lea     r8, [rax+rcx]
0x180027dac  call    McTemplateU0x_EventWriteTransfer
  ... truncated ...
```
