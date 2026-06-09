# ArenaAllocatorBase<InPlaceFreeListPolicy>::RealAlloc(unsigned __int64)

- ea: `0x180026f60`
- end: `0x1800275ef`
- name: `?RealAlloc@?$ArenaAllocatorBase@VInPlaceFreeListPolicy@@@@AEAAPEAD_K@Z`
- size: `1679`
- prototype: `_QWORD *__fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038060`

## callees

- `0x180004f94`
- `0x180008e7c`
- `0x1800215c0`
- `0x180026314`
- `0x180026bc0`
- `0x180026f60`
- `0x180028284`
- `0x1801b3d5c`
- `0x18025a1fc`
- `0x18025a464`
- `0x180364010`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x1800270d4`
- `KERNEL32!InterlockedPushEntrySList` at `0x1800270d4`
- `KERNEL32!InterlockedPopEntrySList` at `0x180027522`
- `KERNEL32!InterlockedPopEntrySList` at `0x180027522`

## pseudocode

```c
_QWORD *__fastcall ArenaAllocatorBase<InPlaceFreeListPolicy>::RealAlloc(__int64 a1, unsigned __int64 a2)
{
  _QWORD *result; // rax
  unsigned __int64 v4; // rsi
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // r15
  PSLIST_HEADER **v7; // r12
  void (*v8)(void); // rax
  char *v9; // rbx
  __int64 v10; // r8
  _QWORD *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  _QWORD *v15; // r9
  unsigned __int64 *v16; // r8
  unsigned __int64 v17; // r10
  _QWORD *v18; // r11
  int v19; // r9d
  __int64 v20; // rax
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rcx
  int v23; // ebx
  _QWORD *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned int v27; // eax
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rax
  __int64 v30; // rax
  unsigned __int64 *v31; // r9
  _QWORD **v32; // r8
  __int64 v33; // r13
  int v34; // edx
  _QWORD *v35; // rcx
  signed __int64 v36; // rax
  _QWORD *v37; // rcx
  unsigned __int64 *v38; // rcx
  signed __int64 v39; // rax
  __int64 v40; // rbp
  unsigned __int64 v41; // r14
  bool v42; // zf
  unsigned int v43; // r11d
  unsigned int v44; // eax
  unsigned int v45; // r9d
  unsigned int v46; // edx
  unsigned int v47; // r10d
  int v48; // edx
  unsigned int v49; // r8d
  __int64 v50; // rdx
  __int64 v51; // r9
  PSLIST_ENTRY v52; // rax
  int Next; // ebx
  struct Segment *v54; // rax
  unsigned __int64 *v55; // r8
  unsigned __int64 *v56; // [rsp+28h] [rbp-50h]
  PSLIST_ENTRY v57; // [rsp+28h] [rbp-50h]
  struct PageSegment *v58; // [rsp+30h] [rbp-48h] BYREF

  result = *(_QWORD **)(a1 + 48);
  v4 = a2;
  v5 = *(_QWORD *)(a1 + 64) - (_QWORD)result;
  if ( v5 >= a2 )
  {
    *(_QWORD *)(a1 + 48) = (char *)result + a2;
    return result;
  }
  if ( a2 > *(_QWORD *)(a1 + 72) )
  {
LABEL_4:
    v6 = v4 + 32;
    if ( v4 + 32 < v4 )
    {
      v6 = -1;
LABEL_6:
      v7 = (PSLIST_HEADER **)(a1 + 40);
      goto LABEL_7;
    }
    if ( v4 + 4143 < v4 + 32 || v4 == -4144 )
      goto LABEL_6;
    v40 = *(_QWORD *)(a1 + 40);
    v7 = (PSLIST_HEADER **)(a1 + 40);
    v41 = (v4 + 4143) >> 12;
    v58 = 0;
    if ( v41 > *(unsigned int *)(v40 + 88) )
    {
      v54 = PageAllocator::AllocSegment((PageAllocator *)v40, v41);
      v33 = (__int64)v54;
      if ( !v54 )
        goto LABEL_7;
      v9 = (char *)*((_QWORD *)v54 + 2);
      v5 = *((_QWORD *)v54 + 3) - *((unsigned int *)v54 + 8);
      *(_QWORD *)v9 = v5;
      goto LABEL_27;
    }
    v42 = *(_DWORD *)(v40 + 152) == 0;
    *(_BYTE *)(v40 + 139) = 1;
    if ( v42 )
      AsymetricCriticalSection::FastEnter((AsymetricCriticalSection *)(v40 + 200));
    if ( *(_QWORD *)(v40 + 104) < (unsigned __int64)(unsigned int)v41 )
    {
      v31 = (unsigned __int64 *)(v40 + 8);
    }
    else
    {
      v38 = (unsigned __int64 *)(v40 + 8);
      v55 = (unsigned __int64 *)(v40 + 8);
LABEL_59:
      while ( 1 )
      {
        v55 = (unsigned __int64 *)*v55;
        v56 = v55;
        if ( v55 == v38 )
          break;
        v43 = *((_DWORD *)v55 + 18);
        v33 = (__int64)(v55 + 2);
        if ( v43 >= (unsigned int)v41 )
        {
          v44 = *((_DWORD *)v55 + 16);
          v45 = -1;
          v42 = !_BitScanForward(&v46, v44);
          if ( !v42 )
            v45 = v46;
          v47 = 0xFFFFFFFF >> (32 - v41);
          while ( 1 )
          {
            v55 = v56;
            v38 = (unsigned __int64 *)(v40 + 8);
            if ( v45 == -1 )
              break;
            a2 = *(_QWORD *)(v33 + 24) - *(unsigned int *)(v33 + 32) - v45;
            v38 = (unsigned __int64 *)(v40 + 8);
            if ( a2 < (unsigned int)v41 )
              break;
            if ( (_DWORD)v41 == 1 || (a2 = v47 << v45, (v44 & (v47 << v45)) == (_DWORD)a2) )
            {
              v38 = (unsigned __int64 *)(v40 + 8);
              *(_DWORD *)(v33 + 48) = v44 & ~(v47 << v45);
              *(_DWORD *)(v33 + 56) = v43 - v41;
              v9 = (char *)(*(_QWORD *)(v33 + 16) + (v45 << 12));
              if ( !v9 )
                goto LABEL_59;
              v5 = (unsigned int)((_DWORD)v41 << 12);
              *(_QWORD *)(v40 + 160) += v5;
              v39 = _InterlockedExchangeAdd64(&qword_180443988, v5);
              if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
              {
                McTemplateU0x_EventWriteTransfer(v5, a2, v39 + v5);
                v55 = v56;
              }
              if ( !*(_DWORD *)(v33 + 56) )
              {
                *(_QWORD *)v55[1] = *v55;
                *(_QWORD *)(*v55 + 8) = v55[1];
                v5 = *(_QWORD *)(v40 + 24);
                v55[1] = *(_QWORD *)(v5 + 8);
                *v55 = v5;
                **(_QWORD **)(v5 + 8) = v55;
                *(_QWORD *)(v5 + 8) = v55;
                *(_QWORD *)(v40 + 104) -= (unsigned int)v41;
                goto LABEL_23;
              }
              goto LABEL_50;
            }
            v48 = -1 << (v45 + 1);
            v45 = -1;
            v42 = !_BitScanForward(&v49, v44 & v48);
            if ( !v42 )
              v45 = v49;
          }
        }
      }
      if ( (_DWORD)v41 != 1 || !*(_QWORD *)(v40 + 128) )
        goto LABEL_73;
      v52 = InterlockedPopEntrySList(*(PSLIST_HEADER *)(v40 + 128));
      v57 = v52;
      if ( !v52 )
      {
        v38 = (unsigned __int64 *)(v40 + 8);
LABEL_73:
        v31 = v38;
        goto LABEL_36;
      }
      v33 = *((_QWORD *)&v52->Next + 1);
      Next = (int)v52[1].Next;
      v58 = (struct PageSegment *)v33;
      if ( Next == 1 )
      {
        v9 = (char *)v52;
        *v52 = 0;
        v52[1] = 0;
      }
      else
      {
        v23 = Next - 1;
        LODWORD(v52[1].Next) = v23;
        InterlockedPushEntrySList(*(PSLIST_HEADER *)(v40 + 128), v52);
        v9 = (char *)v57 + (unsigned int)(v23 << 12);
      }
      if ( v9 )
        goto LABEL_23;
      v31 = (unsigned __int64 *)(v40 + 8);
    }
LABEL_36:
    v32 = *(_QWORD ***)(v40 + 40);
    if ( v32 == (_QWORD **)(v40 + 40) )
    {
      v9 = PageAllocator::TryAllocDecommitedPages((PageAllocator *)v40, v41, &v58);
      if ( v9 )
      {
        v33 = (__int64)v58;
LABEL_23:
        if ( !*(_DWORD *)(v40 + 152) )
          *(_DWORD *)(v40 + 240) = 0;
        v7 = (PSLIST_HEADER **)(a1 + 40);
        if ( !v9 )
        {
LABEL_7:
          v8 = *(void (**)(void))(a1 + 8);
          if ( !v8 || (v8(), (v9 = (char *)PageAllocator::AllocPagesForBytes(*v7, v6)) == 0) )
          {
            v10 = v4 + 16;
            if ( v4 + 16 < v4 )
              v10 = -1;
            v11 = (_QWORD *)AllocateArray<HeapAllocator,char,1>(v5, a2, v10);
            if ( v11 )
            {
              v11[1] = v4;
              *v11 = *(_QWORD *)(a1 + 32);
              *(_QWORD *)(a1 + 32) = v11;
              v15 = v11 + 2;
              *(_DWORD *)(a1 + 80) = 2;
            }
            else
            {
              if ( *(_QWORD *)a1 )
                (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD))a1)(v13, v12, v14, 0);
              return 0;
            }
            return v15;
          }
LABEL_28:
          v24 = v9 + 16;
          *((_QWORD *)v9 + 4) = v9;
          v25 = (*(_QWORD *)v9 << 12) - 48LL;
          *((_QWORD *)v9 + 5) = 0;
          *((_QWORD *)v9 + 3) = v25;
          ++*(_DWORD *)(a1 + 80);
          v26 = *(_QWORD *)(a1 + 16);
          if ( v26 )
          {
            *(_QWORD *)(v26 + 24) = *(_QWORD *)(a1 + 48) - v26 - 32;
            v27 = *(_DWORD *)(a1 + 64) - *(_DWORD *)(a1 + 48);
            if ( v27 >= 0x10 || *(_BYTE *)(a1 + 56) )
            {
              v28 = v27;
              v29 = *(_QWORD *)(a1 + 72);
              if ( v29 <= v28 )
                v29 = v28;
              *(_QWORD *)(a1 + 72) = v29;
            }
            else
            {
              v37 = *(_QWORD **)(a1 + 16);
              *(_QWORD *)(a1 + 16) = *v37;
              *v37 = *(_QWORD *)(a1 + 24);
              *(_QWORD *)(a1 + 24) = v37;
            }
          }
          v30 = *(_QWORD *)(a1 + 16);
          *(_QWORD *)(a1 + 48) = &v9[*((_QWORD *)v9 + 5) + 48];
          *(_QWORD *)(a1 + 64) = (char *)v24 + *((_QWORD *)v9 + 3) + 32;
          *v24 = v30;
          v15 = *(_QWORD **)(a1 + 48);
          *(_QWORD *)(a1 + 16) = v24;
          *(_QWORD *)(a1 + 48) = (char *)v15 + v4;
          return v15;
        }
        *(_QWORD *)v9 = v41;
LABEL_27:
        *((_QWORD *)v9 + 1) = v33;
        if ( v9 )
          goto LABEL_28;
        goto LABEL_7;
      }
      v50 = 24;
      if ( (_DWORD)v41 != *(_DWORD *)(v40 + 88) )
        v50 = 8;
      v33 = PageAllocator::AddPageSegment((PageAllocator *)v40, v40 + v50);
      if ( !v33 )
      {
        v33 = (__int64)v58;
        v9 = 0;
        goto LABEL_23;
      }
    }
    else
    {
      v33 = (__int64)(v32 + 2);
      v34 = *(_DWORD *)(v40 + 88);
      *v32[1] = *v32;
      (*v32)[1] = v32[1];
      if ( (_DWORD)v41 == v34 )
        v35 = *(_QWORD **)(v40 + 24);
      else
        v35 = (_QWORD *)*v31;
      v32[1] = (_QWORD *)v35[1];
      *v32 = v35;
      *(_QWORD *)v35[1] = v32;
      v35[1] = v32;
    }
    v9 = PageSegment::AllocPages((PageSegment *)v33, v41);
    v5 = (unsigned int)((_DWORD)v41 << 12);
    *(_QWORD *)(v40 + 160) += v5;
    v36 = _InterlockedExchangeAdd64(&qword_180443988, v5);
    if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
      McTemplateU0x_EventWriteTransfer(v5, a2, v36 + v5);
LABEL_50:
    *(_QWORD *)(v40 + 104) -= (unsigned int)v41;
    goto LABEL_23;
  }
  v16 = *(unsigned __int64 **)(a1 + 16);
  v17 = 0;
  v18 = v16;
  v19 = 10;
  a2 = *v16;
  while ( 1 )
  {
    v20 = *(_QWORD *)(a2 + 24);
    v5 = *(_QWORD *)(a2 + 8) - v20;
    if ( v5 >= v4 )
      break;
    if ( v17 <= v5 )
      v17 = *(_QWORD *)(a2 + 8) - v20;
    if ( --v19 )
    {
      v18 = (_QWORD *)a2;
      a2 = *(_QWORD *)a2;
      if ( a2 )
        continue;
    }
    goto LABEL_4;
  }
  v15 = (_QWORD *)(v20 + a2 + 32);
  *(_QWORD *)(a2 + 24) = v4 + v20;
  v21 = *(_QWORD *)(a1 + 72);
  if ( v5 == v21 || v17 > v21 )
    *(_QWORD *)(a1 + 72) = v17;
  v22 = v5 - v4;
  if ( v22 <= v16[1] - v16[3] )
  {
    if ( v22 < 0x10 && !*(_BYTE *)(a1 + 56) )
    {
      *v18 = *(_QWORD *)a2;
      *(_QWORD *)a2 = *(_QWORD *)(a1 + 24);
      result = v15;
      *(_QWORD *)(a1 + 24) = a2;
      return result;
    }
    return v15;
  }
  *v18 = *(_QWORD *)a2;
  ArenaAllocatorBase<InPlaceFreeListPolicy>::SetCacheBlock(a1, (_QWORD *)a2);
  return (_QWORD *)v51;
}

```

## disassembly

```asm
0x180026f60  mov     r11, rsp
0x180026f63  mov     [r11+10h], rdx
0x180026f67  mov     [r11+8], rcx
0x180026f6b  push    rsi
0x180026f6c  push    rdi
0x180026f6d  sub     rsp, 68h
0x180026f71  mov     rax, [rcx+30h]
0x180026f75  mov     rdi, rcx
0x180026f78  mov     rcx, [rcx+40h]
0x180026f7c  mov     rsi, rdx
0x180026f7f  sub     rcx, rax
0x180026f82  cmp     rcx, rdx
0x180026f85  jb      short loc_180026F97
0x180026f87  lea     rcx, [rax+rdx]
0x180026f8b  mov     [rdi+30h], rcx
0x180026f8f  add     rsp, 68h
0x180026f93  pop     rdi
0x180026f94  pop     rsi
0x180026f95  retn
0x180026f97  cmp     rsi, [rdi+48h]
0x180026f9b  jbe     loc_18002703E
0x180026fa1  mov     [rsp+78h+arg_10], rbx
0x180026fa9  mov     [rsp+78h+var_18], rbp
0x180026fae  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180026fb5  mov     [rsp+78h+var_20], r12
0x180026fba  mov     [rsp+78h+var_28], r13
0x180026fbf  mov     [rsp+78h+var_30], r14
0x180026fc4  mov     [rsp+78h+var_38], r15
0x180026fc9  lea     r15, [rsi+20h]
0x180026fcd  cmp     r15, rsi
0x180026fd0  jnb     loc_180027344
0x180026fd6  mov     r15, rbp
0x180026fd9  lea     r12, [rdi+28h]
0x180026fdd  mov     rax, [rdi+8]
0x180026fe1  test    rax, rax
0x180026fe4  jz      short loc_180027003
0x180026fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026feb  mov     rcx, [r12]; this
0x180026fef  mov     rdx, r15; unsigned __int64
0x180026ff2  call    ?AllocPagesForBytes@PageAllocator@@QEAAPEAVPageAllocation@@_K@Z; PageAllocator::AllocPagesForBytes(unsigned __int64)
0x180026ff7  mov     rbx, rax
0x180026ffa  test    rax, rax
0x180026ffd  jnz     loc_18002711B
0x180027003  lea     r8, [rsi+10h]
0x180027007  cmp     r8, rsi
0x18002700a  cmovb   r8, rbp
0x18002700e  call    ??$AllocateArray@UHeapAllocator@@D$00@@YAPEADPEAUHeapAllocator@@P80@EAAPEAD_K@Z1@Z; AllocateArray<HeapAllocator,char,1>(HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x180027013  mov     r9, rax
0x180027016  test    rax, rax
0x180027019  jz      loc_1800275DA
0x18002701f  mov     [rax+8], rsi
0x180027023  mov     rax, [rdi+20h]
0x180027027  mov     [r9], rax
0x18002702a  mov     [rdi+20h], r9
0x18002702e  add     r9, 10h
0x180027032  mov     dword ptr [rdi+50h], 2
0x180027039  jmp     loc_1800271AA
0x18002703e  mov     r8, [rdi+10h]
0x180027042  xor     r10d, r10d
0x180027045  mov     r11, r8
0x180027048  mov     r9d, 0Ah
0x18002704e  mov     rdx, [r8]
0x180027051  mov     rax, [rdx+18h]
0x180027055  mov     rcx, [rdx+8]
0x180027059  sub     rcx, rax
0x18002705c  cmp     rcx, rsi
0x18002705f  jb      loc_180027490
0x180027065  lea     r9, [rdx+20h]
0x180027069  add     r9, rax
0x18002706c  add     rax, rsi
0x18002706f  mov     [rdx+18h], rax
0x180027073  mov     rax, [rdi+48h]
0x180027077  cmp     rcx, rax
0x18002707a  jnz     loc_180027482
0x180027080  mov     [rdi+48h], r10
0x180027084  mov     rax, [r8+8]
0x180027088  sub     rcx, rsi
0x18002708b  sub     rax, [r8+18h]
0x18002708f  cmp     rcx, rax
0x180027092  ja      loc_180027509
0x180027098  cmp     rcx, 10h
0x18002709c  jnb     loc_1800271CB
0x1800270a2  cmp     byte ptr [rdi+38h], 0
0x1800270a6  jnz     loc_1800271CB
0x1800270ac  mov     rax, [rdx]
0x1800270af  mov     [r11], rax
0x1800270b2  mov     rax, [rdi+18h]
0x1800270b6  mov     [rdx], rax
0x1800270b9  mov     rax, r9
0x1800270bc  mov     [rdi+18h], rdx
0x1800270c0  jmp     loc_180026F8F
0x1800270c5  dec     ebx
0x1800270c7  mov     rdx, rax; ListEntry
0x1800270ca  mov     [rax+10h], ebx
0x1800270cd  mov     rcx, [rbp+80h]; ListHead
0x1800270d4  call    cs:__imp_InterlockedPushEntrySList
0x1800270db  nop     dword ptr [rax+rax+00h]
0x1800270e0  shl     ebx, 0Ch
0x1800270e3  add     rbx, [rsp+78h+var_50]
0x1800270e8  test    rbx, rbx
0x1800270eb  jz      loc_1800271D3
0x1800270f1  cmp     dword ptr [rbp+98h], 0
0x1800270f8  jz      loc_1800274B5
0x1800270fe  lea     r12, [rdi+28h]
0x180027102  test    rbx, rbx
0x180027105  jz      loc_1800275CE
0x18002710b  mov     [rbx], r14
0x18002710e  mov     [rbx+8], r13
0x180027112  test    rbx, rbx
0x180027115  jz      loc_180027571
0x18002711b  lea     rdx, [rbx+10h]
0x18002711f  mov     [rdx+10h], rbx
0x180027123  mov     rax, [rbx]
0x180027126  shl     rax, 0Ch
0x18002712a  sub     rax, 30h ; '0'
0x18002712e  mov     qword ptr [rdx+18h], 0
0x180027136  mov     [rdx+8], rax
0x18002713a  inc     dword ptr [rdi+50h]
0x18002713d  mov     rcx, [rdi+10h]
0x180027141  test    rcx, rcx
0x180027144  jz      short loc_180027175
0x180027146  mov     rax, [rdi+30h]
0x18002714a  sub     rax, rcx
0x18002714d  sub     rax, 20h ; ' '
0x180027151  mov     [rcx+18h], rax
0x180027155  mov     eax, [rdi+40h]
0x180027158  sub     eax, [rdi+30h]
0x18002715b  cmp     eax, 10h
0x18002715e  jb      loc_180027286
0x180027164  mov     ecx, eax
0x180027166  mov     rax, [rdi+48h]
0x18002716a  cmp     rax, rcx
0x18002716d  cmovbe  rax, rcx
0x180027171  mov     [rdi+48h], rax
0x180027175  mov     rcx, [rdx+18h]
0x180027179  mov     rax, [rdi+10h]
0x18002717d  add     rcx, 20h ; ' '
0x180027181  add     rcx, rdx
0x180027184  mov     [rdi+30h], rcx
0x180027188  mov     rcx, [rdx+8]
0x18002718c  add     rcx, 20h ; ' '
0x180027190  add     rcx, rdx
0x180027193  mov     [rdi+40h], rcx
0x180027197  mov     [rdx], rax
0x18002719a  mov     r9, [rdi+30h]
0x18002719e  mov     [rdi+10h], rdx
0x1800271a2  lea     rax, [r9+rsi]
0x1800271a6  mov     [rdi+30h], rax
0x1800271aa  mov     r14, [rsp+78h+var_30]
0x1800271af  mov     r13, [rsp+78h+var_28]
0x1800271b4  mov     r12, [rsp+78h+var_20]
0x1800271b9  mov     rbp, [rsp+78h+var_18]
0x1800271be  mov     rbx, [rsp+78h+arg_10]
0x1800271c6  mov     r15, [rsp+78h+var_38]
0x1800271cb  mov     rax, r9
0x1800271ce  jmp     loc_180026F8F
0x1800271d3  lea     r9, [rbp+8]
0x1800271d7  mov     r8, [rbp+28h]
0x1800271db  lea     rax, [rbp+28h]
0x1800271df  cmp     r8, rax
0x1800271e2  jnz     short loc_18002720A
0x1800271e4  lea     r8, [rsp+78h+var_48]; struct PageSegment **
0x1800271e9  mov     edx, r12d; unsigned int
0x1800271ec  mov     rcx, rbp; this
0x1800271ef  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x1800271f4  mov     rbx, rax
0x1800271f7  test    rax, rax
0x1800271fa  jz      loc_1800274C4
0x180027200  mov     r13, [rsp+78h+var_48]
0x180027205  jmp     loc_1800270F1
0x18002720a  mov     rcx, [r8+8]
0x18002720e  lea     r13, [r8+10h]
0x180027212  mov     rax, [r8]
0x180027215  mov     edx, [rbp+58h]
0x180027218  mov     [rcx], rax
0x18002721b  mov     rcx, [r8]
0x18002721e  mov     rax, [r8+8]
0x180027222  mov     [rcx+8], rax
0x180027226  cmp     r12d, edx
0x180027229  jz      loc_180027541
0x18002722f  mov     rcx, [r9]
0x180027232  mov     rax, [rcx+8]
0x180027236  mov     [r8+8], rax
0x18002723a  mov     [r8], rcx
0x18002723d  mov     rax, [rcx+8]
0x180027241  mov     [rax], r8
0x180027244  mov     [rcx+8], r8
0x180027248  mov     edx, r12d; unsigned int
0x18002724b  mov     rcx, r13; this
0x18002724e  call    ?AllocPages@PageSegment@@QEAAPEADI@Z; PageSegment::AllocPages(uint)
0x180027253  mov     rbx, rax
0x180027256  mov     eax, r12d
0x180027259  shl     eax, 0Ch
0x18002725c  mov     ecx, eax
0x18002725e  add     [rbp+0A0h], rcx
0x180027265  lock xadd cs:qword_180443988, rax
0x18002726e  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180027275  jz      loc_180027303
0x18002727b  lea     r8, [rax+rcx]
0x18002727f  call    McTemplateU0x_EventWriteTransfer
0x180027284  jmp     short loc_180027303
0x180027286  cmp     byte ptr [rdi+38h], 0
0x18002728a  jnz     loc_180027164
0x180027290  mov     rcx, [rdi+10h]
0x180027294  mov     rax, [rcx]
0x180027297  mov     [rdi+10h], rax
0x18002729b  mov     rax, [rdi+18h]
0x18002729f  mov     [rcx], rax
0x1800272a2  mov     [rdi+18h], rcx
0x1800272a6  jmp     loc_180027175
0x1800272ab  mov     ecx, r9d
0x1800272ae  sub     r11d, r12d
0x1800272b1  shl     r10d, cl
0x1800272b4  lea     rcx, [rbp+8]
0x1800272b8  shl     r9d, 0Ch
0x1800272bc  not     r10d
0x1800272bf  and     r10d, eax
0x1800272c2  mov     ebx, r9d
0x1800272c5  mov     [r13+30h], r10d
0x1800272c9  mov     [r13+38h], r11d
0x1800272cd  add     rbx, [r13+10h]
0x1800272d1  jz      loc_1800273B2
0x1800272d7  mov     eax, r12d
0x1800272da  shl     eax, 0Ch
0x1800272dd  mov     ecx, eax
0x1800272df  add     [rbp+0A0h], rcx
0x1800272e6  lock xadd cs:qword_180443988, rax
0x1800272ef  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x1800272f6  jnz     loc_1800275BB
0x1800272fc  cmp     dword ptr [r13+38h], 0
0x180027301  jz      short loc_18002730C
0x180027303  sub     [rbp+68h], r12
0x180027307  jmp     loc_1800270F1
0x18002730c  mov     rcx, [r8+8]
0x180027310  mov     rax, [r8]
0x180027313  mov     [rcx], rax
0x180027316  mov     rcx, [r8]
0x180027319  mov     rax, [r8+8]
0x18002731d  mov     [rcx+8], rax
0x180027321  mov     rcx, [rbp+18h]
0x180027325  mov     rax, [rcx+8]
0x180027329  mov     [r8+8], rax
0x18002732d  mov     [r8], rcx
0x180027330  mov     rax, [rcx+8]
0x180027334  mov     [rax], r8
0x180027337  mov     [rcx+8], r8
0x18002733b  sub     [rbp+68h], r12
0x18002733f  jmp     loc_1800270F1
0x180027344  lea     r14, [r15+100Fh]
0x18002734b  cmp     r14, r15
0x18002734e  jb      loc_180026FD9
0x180027354  cmp     r14, rbp
0x180027357  jz      loc_180026FD9
0x18002735d  mov     rbp, [rdi+28h]
0x180027361  lea     r12, [rdi+28h]
0x180027365  shr     r14, 0Ch
0x180027369  mov     [rsp+78h+var_48], 0
0x180027372  mov     eax, [rbp+58h]
0x180027375  cmp     r14, rax
0x180027378  ja      loc_18002757D
0x18002737e  cmp     dword ptr [rbp+98h], 0
0x180027385  mov     byte ptr [rbp+8Bh], 1
0x18002738c  jz      loc_1800274F8
0x180027392  mov     r12d, r14d
0x180027395  cmp     [rbp+68h], r12
0x180027399  jb      loc_1800275B2
0x18002739f  mov     eax, 20h ; ' '
0x1800273a4  lea     rcx, [rbp+8]
0x1800273a8  sub     eax, r12d
0x1800273ab  mov     r8, rcx
0x1800273ae  mov     [rsp+78h+var_58], eax
0x1800273b2  mov     r8, [r8]
0x1800273b5  mov     [rsp+78h+var_50], r8
0x1800273ba  cmp     r8, rcx
0x1800273bd  jz      loc_180027464
0x1800273c3  mov     r11d, [r8+48h]
0x1800273c7  lea     r13, [r8+10h]
0x1800273cb  cmp     r11d, r12d
0x1800273ce  jb      short loc_1800273B2
0x1800273d0  mov     eax, [r13+30h]
0x1800273d4  mov     r9d, 0FFFFFFFFh
0x1800273da  bsf     edx, eax
0x1800273dd  mov     r10d, 0FFFFFFFFh
0x1800273e3  setnz   cl
0x1800273e6  test    cl, cl
0x1800273e8  mov     ecx, [rsp+78h+var_58]
0x1800273ec  cmovnz  r9d, edx
0x1800273f0  shr     r10d, cl
0x1800273f3  mov     r8, [rsp+78h+var_50]
0x1800273f8  lea     rcx, [rbp+8]
0x1800273fc  mov     [rsp+78h+var_54], 0
0x180027404  cmp     r9d, 0FFFFFFFFh
0x180027408  jz      short loc_1800273B2
0x18002740a  mov     ecx, [r13+20h]
0x18002740e  mov     rdx, [r13+18h]
0x180027412  sub     rdx, rcx
0x180027415  mov     ecx, r9d
0x180027418  sub     rdx, rcx
0x18002741b  lea     rcx, [rbp+8]
0x18002741f  cmp     rdx, r12
  ... truncated ...
```
