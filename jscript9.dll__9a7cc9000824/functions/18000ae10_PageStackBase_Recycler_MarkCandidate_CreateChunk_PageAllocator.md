# PageStackBase<Recycler::MarkCandidate>::CreateChunk(PageAllocator *)

- ea: `0x18000ae10`
- end: `0x18000b0f7`
- name: `?CreateChunk@?$PageStackBase@UMarkCandidate@Recycler@@@@QEAAPEAUChunk@1@PEAVPageAllocator@@@Z`
- size: `743`
- prototype: ``
- caller_count: `12`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005650`
- `0x1800057d0`
- `0x180005970`
- `0x1800078b0`
- `0x180007d80`
- `0x180009ea8`
- `0x18000a02c`
- `0x18000aaa4`
- `0x18000ad60`
- `0x180131aa0`
- `0x18015027c`
- `0x1801b0f1c`

## callees

- `0x180008e7c`
- `0x18000ae10`
- `0x1800215c0`
- `0x180026314`
- `0x180028284`
- `0x18025a464`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x18000b0bf`
- `KERNEL32!InterlockedPushEntrySList` at `0x18000b0bf`
- `KERNEL32!InterlockedPopEntrySList` at `0x18000b06f`
- `KERNEL32!InterlockedPopEntrySList` at `0x18000b06f`

## pseudocode

```c
char *__fastcall PageStackBase<Recycler::MarkCandidate>::CreateChunk(__int64 a1, __int64 a2)
{
  bool v2; // zf
  __int64 *v4; // r15
  __int64 *v5; // r14
  struct PageSegment *v6; // rsi
  int v7; // r8d
  unsigned int v8; // r9d
  unsigned int v9; // edx
  unsigned int v10; // ecx
  __int64 v11; // rcx
  int v12; // r9d
  __int64 v13; // rdx
  char *v14; // rbx
  signed __int64 v15; // r8
  union _SLIST_HEADER *v17; // rcx
  _QWORD **v18; // r8
  __int64 v19; // rcx
  int v20; // edx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  signed __int64 v24; // r8
  PSLIST_ENTRY v25; // rax
  PSLIST_ENTRY v26; // rbp
  int Next; // ebx
  int v28; // ebx
  struct PageSegment *v29; // [rsp+28h] [rbp-30h] BYREF

  v2 = *(_DWORD *)(a2 + 152) == 0;
  v29 = 0;
  *(_BYTE *)(a2 + 139) = 1;
  if ( v2 )
    AsymetricCriticalSection::FastEnter((AsymetricCriticalSection *)(a2 + 200));
  v4 = (__int64 *)(a2 + 8);
  if ( *(_QWORD *)(a2 + 104) )
  {
    v5 = (__int64 *)(a2 + 8);
    while ( 1 )
    {
      v5 = (__int64 *)*v5;
      if ( v5 == v4 )
        break;
      v6 = (struct PageSegment *)(v5 + 2);
      v7 = *((_DWORD *)v5 + 18);
      if ( v7 )
      {
        v8 = *((_DWORD *)v5 + 16);
        v9 = -1;
        v2 = !_BitScanForward(&v10, v8);
        if ( !v2 )
          v9 = v10;
        if ( v9 != -1 )
        {
          v11 = v5[5] - *((unsigned int *)v5 + 12) - v9;
          if ( v5[5] - *((unsigned int *)v5 + 12) != v9 )
          {
            v12 = v8 & ~(1 << v9);
            v13 = v9 << 12;
            *((_DWORD *)v5 + 16) = v12;
            *((_DWORD *)v5 + 18) = v7 - 1;
            v14 = (char *)(v5[4] + (unsigned int)v13);
            if ( v14 )
            {
              *(_QWORD *)(a2 + 160) += 4096LL;
              v15 = _InterlockedExchangeAdd64(&qword_180443988, 0x1000u);
              if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
                McTemplateU0x_EventWriteTransfer(v11, v13, v15 + 4096);
              if ( !*((_DWORD *)v5 + 18) )
              {
                *(_QWORD *)v5[1] = *v5;
                *(_QWORD *)(*v5 + 8) = v5[1];
                v19 = *(_QWORD *)(a2 + 24);
                v5[1] = *(_QWORD *)(v19 + 8);
                *v5 = v19;
                **(_QWORD **)(v19 + 8) = v5;
                *(_QWORD *)(v19 + 8) = v5;
              }
              goto LABEL_16;
            }
          }
        }
      }
    }
    v17 = *(union _SLIST_HEADER **)(a2 + 128);
    if ( v17 )
    {
      v25 = InterlockedPopEntrySList(v17);
      v26 = v25;
      if ( v25 )
      {
        v6 = (struct PageSegment *)*((_QWORD *)&v25->Next + 1);
        Next = (int)v25[1].Next;
        v29 = v6;
        if ( Next == 1 )
        {
          v14 = (char *)v25;
          *v25 = 0;
          v25[1] = 0;
        }
        else
        {
          v28 = Next - 1;
          LODWORD(v25[1].Next) = v28;
          InterlockedPushEntrySList(*(PSLIST_HEADER *)(a2 + 128), v25);
          v14 = (char *)v26 + (unsigned int)(v28 << 12);
        }
        if ( v14 )
          goto LABEL_17;
      }
    }
  }
  v18 = *(_QWORD ***)(a2 + 40);
  if ( v18 == (_QWORD **)(a2 + 40) )
  {
    v14 = PageAllocator::TryAllocDecommitedPages((PageAllocator *)a2, 1u, &v29);
    if ( v14 )
    {
LABEL_24:
      v6 = v29;
      goto LABEL_17;
    }
    v6 = (struct PageSegment *)PageAllocator::AddPageSegment((PageAllocator *)a2);
    if ( !v6 )
    {
      v14 = 0;
      goto LABEL_24;
    }
  }
  else
  {
    v6 = (struct PageSegment *)(v18 + 2);
    v20 = *(_DWORD *)(a2 + 88);
    *v18[1] = *v18;
    (*v18)[1] = v18[1];
    if ( v20 == 1 )
      v21 = *(_QWORD **)(a2 + 24);
    else
      v21 = (_QWORD *)*v4;
    v18[1] = (_QWORD *)v21[1];
    *v18 = v21;
    *(_QWORD *)v21[1] = v18;
    v21[1] = v18;
  }
  v14 = PageSegment::AllocPages(v6, 1u);
  *(_QWORD *)(a2 + 160) += 4096LL;
  v24 = _InterlockedExchangeAdd64(&qword_180443988, 0x1000u);
  if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
    McTemplateU0x_EventWriteTransfer(v23, v22, v24 + 4096);
LABEL_16:
  --*(_QWORD *)(a2 + 104);
LABEL_17:
  if ( !*(_DWORD *)(a2 + 152) )
    *(_DWORD *)(a2 + 240) = 0;
  if ( !v14 )
    return 0;
  *((_QWORD *)v14 + 1) = v6;
  *((_QWORD *)v14 + 3) = v14 + 4096;
  return v14;
}

```

## disassembly

```asm
0x18000ae10  mov     rax, rsp
0x18000ae13  mov     [rax+18h], rbx
0x18000ae17  mov     [rax+10h], rdx
0x18000ae1b  mov     [rax+8], rcx
0x18000ae1f  push    rbp
0x18000ae20  push    rsi
0x18000ae21  push    rdi
0x18000ae22  push    r14
0x18000ae24  push    r15
0x18000ae26  sub     rsp, 30h
0x18000ae2a  cmp     dword ptr [rdx+98h], 0
0x18000ae31  mov     rdi, rdx
0x18000ae34  mov     qword ptr [rax-30h], 0
0x18000ae3c  mov     byte ptr [rdx+8Bh], 1
0x18000ae43  jz      loc_18000B05E
0x18000ae49  cmp     qword ptr [rdi+68h], 1
0x18000ae4e  lea     r15, [rdi+8]
0x18000ae52  jb      loc_18000AF3F
0x18000ae58  mov     r14, r15
0x18000ae5b  or      r10d, 0FFFFFFFFh
0x18000ae5f  mov     r14, [r14]
0x18000ae62  cmp     r14, r15
0x18000ae65  jz      loc_18000AF2F
0x18000ae6b  lea     rsi, [r14+10h]
0x18000ae6f  mov     r8d, [rsi+38h]
0x18000ae73  cmp     r8d, 1
0x18000ae77  jb      short loc_18000AE5F
0x18000ae79  mov     r9d, [rsi+30h]
0x18000ae7d  mov     edx, r10d
0x18000ae80  bsf     ecx, r9d
0x18000ae84  mov     [rsp+58h+var_38], 0
0x18000ae8c  setnz   al
0x18000ae8f  test    al, al
0x18000ae91  cmovnz  edx, ecx
0x18000ae94  cmp     edx, r10d
0x18000ae97  jz      short loc_18000AE5F
0x18000ae99  mov     eax, [rsi+20h]
0x18000ae9c  mov     rcx, [rsi+18h]
0x18000aea0  sub     rcx, rax
0x18000aea3  mov     eax, edx
0x18000aea5  sub     rcx, rax
0x18000aea8  cmp     rcx, 1
0x18000aeac  jb      short loc_18000AE5F
0x18000aeae  btr     r9d, edx
0x18000aeb2  shl     edx, 0Ch
0x18000aeb5  mov     [rsi+30h], r9d
0x18000aeb9  lea     eax, [r8-1]
0x18000aebd  mov     ebx, edx
0x18000aebf  mov     [rsi+38h], eax
0x18000aec2  add     rbx, [rsi+10h]
0x18000aec6  jz      short loc_18000AE5F
0x18000aec8  mov     r8d, 1000h
0x18000aece  add     [rdi+0A0h], r8
0x18000aed5  lock xadd cs:qword_180443988, r8
0x18000aede  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x18000aee5  jnz     loc_18000B0DF
0x18000aeeb  cmp     dword ptr [rsi+38h], 0
0x18000aeef  jz      short loc_18000AF70
0x18000aef1  dec     qword ptr [rdi+68h]
0x18000aef5  cmp     dword ptr [rdi+98h], 0
0x18000aefc  jz      loc_18000B026
0x18000af02  test    rbx, rbx
0x18000af05  jz      loc_18000B0F0
0x18000af0b  lea     rcx, [rbx+1000h]
0x18000af12  mov     [rbx+8], rsi
0x18000af16  mov     [rbx+18h], rcx
0x18000af1a  mov     rax, rbx
0x18000af1d  mov     rbx, [rsp+58h+arg_10]
0x18000af22  add     rsp, 30h
0x18000af26  pop     r15
0x18000af28  pop     r14
0x18000af2a  pop     rdi
0x18000af2b  pop     rsi
0x18000af2c  pop     rbp
0x18000af2d  retn
0x18000af2f  mov     rcx, [rdi+80h]; ListHead
0x18000af36  test    rcx, rcx
0x18000af39  jnz     loc_18000B06F
0x18000af3f  lea     rax, [rdi+28h]
0x18000af43  mov     r8, [rax]
0x18000af46  cmp     r8, rax
0x18000af49  jnz     short loc_18000AFA4
0x18000af4b  lea     r8, [rsp+58h+var_30]; struct PageSegment **
0x18000af50  mov     edx, 1; unsigned int
0x18000af55  mov     rcx, rdi; this
0x18000af58  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x18000af5d  mov     rbx, rax
0x18000af60  test    rax, rax
0x18000af63  jz      loc_18000B035
0x18000af69  mov     rsi, [rsp+58h+var_30]
0x18000af6e  jmp     short loc_18000AEF5
0x18000af70  mov     rcx, [r14+8]
0x18000af74  mov     rax, [r14]
0x18000af77  mov     [rcx], rax
0x18000af7a  mov     rcx, [r14]
0x18000af7d  mov     rax, [r14+8]
0x18000af81  mov     [rcx+8], rax
0x18000af85  mov     rcx, [rdi+18h]
0x18000af89  mov     rax, [rcx+8]
0x18000af8d  mov     [r14+8], rax
0x18000af91  mov     [r14], rcx
0x18000af94  mov     rax, [rcx+8]
0x18000af98  mov     [rax], r14
0x18000af9b  mov     [rcx+8], r14
0x18000af9f  jmp     loc_18000AEF1
0x18000afa4  mov     rcx, [r8+8]
0x18000afa8  lea     rsi, [r8+10h]
0x18000afac  mov     rax, [r8]
0x18000afaf  mov     edx, [rdi+58h]
0x18000afb2  mov     [rcx], rax
0x18000afb5  mov     rcx, [r8]
0x18000afb8  mov     rax, [r8+8]
0x18000afbc  mov     [rcx+8], rax
0x18000afc0  cmp     edx, 1
0x18000afc3  jz      loc_18000B0A7
0x18000afc9  mov     rcx, [r15]
0x18000afcc  mov     rax, [rcx+8]
0x18000afd0  mov     [r8+8], rax
0x18000afd4  mov     [r8], rcx
0x18000afd7  mov     rax, [rcx+8]
0x18000afdb  mov     [rax], r8
0x18000afde  mov     [rcx+8], r8
0x18000afe2  mov     edx, 1; unsigned int
0x18000afe7  mov     rcx, rsi; this
0x18000afea  call    ?AllocPages@PageSegment@@QEAAPEADI@Z; PageSegment::AllocPages(uint)
0x18000afef  mov     r8d, 1000h
0x18000aff5  mov     rbx, rax
0x18000aff8  add     [rdi+0A0h], r8
0x18000afff  lock xadd cs:qword_180443988, r8
0x18000b008  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x18000b00f  jz      loc_18000AEF1
0x18000b015  add     r8, 1000h
0x18000b01c  call    McTemplateU0x_EventWriteTransfer
0x18000b021  jmp     loc_18000AEF1
0x18000b026  mov     dword ptr [rdi+0F0h], 0
0x18000b030  jmp     loc_18000AF02
0x18000b035  cmp     dword ptr [rdi+58h], 1
0x18000b039  mov     edx, 18h
0x18000b03e  mov     rcx, rdi; this
0x18000b041  lea     eax, [rdx-10h]
0x18000b044  cmovnz  edx, eax
0x18000b047  add     rdx, rdi
0x18000b04a  call    ?AddPageSegment@PageAllocator@@IEAAPEAVPageSegment@@AEAV?$DListBase@VPageSegment@@@@@Z; PageAllocator::AddPageSegment(DListBase<PageSegment> &)
0x18000b04f  mov     rsi, rax
0x18000b052  test    rax, rax
0x18000b055  jnz     short loc_18000AFE2
0x18000b057  xor     ebx, ebx
0x18000b059  jmp     loc_18000AF69
0x18000b05e  lea     rcx, [rdi+0C8h]; this
0x18000b065  call    ?FastEnter@AsymetricCriticalSection@@QEAAXXZ; AsymetricCriticalSection::FastEnter(void)
0x18000b06a  jmp     loc_18000AE49
0x18000b06f  call    cs:__imp_InterlockedPopEntrySList
0x18000b076  nop     dword ptr [rax+rax+00h]
0x18000b07b  mov     rbp, rax
0x18000b07e  test    rax, rax
0x18000b081  jz      loc_18000AF3F
0x18000b087  mov     rsi, [rax+8]
0x18000b08b  mov     ebx, [rax+10h]
0x18000b08e  mov     [rsp+58h+var_30], rsi
0x18000b093  cmp     ebx, 1
0x18000b096  jnz     short loc_18000B0B0
0x18000b098  xorps   xmm0, xmm0
0x18000b09b  mov     rbx, rax
0x18000b09e  movups  xmmword ptr [rax], xmm0
0x18000b0a1  movups  xmmword ptr [rax+10h], xmm0
0x18000b0a5  jmp     short loc_18000B0D1
0x18000b0a7  mov     rcx, [rdi+18h]
0x18000b0ab  jmp     loc_18000AFCC
0x18000b0b0  dec     ebx
0x18000b0b2  mov     rdx, rbp; ListEntry
0x18000b0b5  mov     [rax+10h], ebx
0x18000b0b8  mov     rcx, [rdi+80h]; ListHead
0x18000b0bf  call    cs:__imp_InterlockedPushEntrySList
0x18000b0c6  nop     dword ptr [rax+rax+00h]
0x18000b0cb  shl     ebx, 0Ch
0x18000b0ce  add     rbx, rbp
0x18000b0d1  test    rbx, rbx
0x18000b0d4  jnz     loc_18000AEF5
0x18000b0da  jmp     loc_18000AF3F
0x18000b0df  add     r8, 1000h
0x18000b0e6  call    McTemplateU0x_EventWriteTransfer
0x18000b0eb  jmp     loc_18000AEEB
0x18000b0f0  xor     eax, eax
0x18000b0f2  jmp     loc_18000AF1D
```
