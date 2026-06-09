# PageAllocator::AllocPagesForBytes(unsigned __int64)

- ea: `0x180026bc0`
- end: `0x180026f54`
- name: `?AllocPagesForBytes@PageAllocator@@QEAAPEAVPageAllocation@@_K@Z`
- size: `916`
- prototype: `struct PageAllocation *__fastcall(PSLIST_HEADER *this, unsigned __int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180026f60`
- `0x180027924`
- `0x180093860`
- `0x180129de0`

## callees

- `0x180008e7c`
- `0x1800215c0`
- `0x180026314`
- `0x180026bc0`
- `0x180028284`
- `0x18025a1fc`
- `0x18025a464`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x180026eef`
- `KERNEL32!InterlockedPushEntrySList` at `0x180026eef`
- `KERNEL32!InterlockedPopEntrySList` at `0x180026e9f`
- `KERNEL32!InterlockedPopEntrySList` at `0x180026e9f`

## pseudocode

```c
struct PageAllocation *__fastcall PageAllocator::AllocPagesForBytes(PSLIST_HEADER *this, unsigned __int64 a2)
{
  unsigned __int64 v2; // rax
  unsigned __int64 v4; // r15
  bool v5; // zf
  PSLIST_HEADER *v6; // r12
  PSLIST_HEADER *v7; // r14
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
  PSLIST_HEADER *v21; // r8
  PSLIST_HEADER v22; // rcx
  int v23; // edx
  PSLIST_HEADER v24; // rcx
  __int64 v25; // rdx
  unsigned __int64 v26; // rcx
  signed __int64 v27; // rax
  __int64 v28; // rdx
  PSLIST_ENTRY v29; // rax
  PSLIST_ENTRY v30; // r14
  int Next; // ebx
  int v32; // ebx
  struct Segment *v33; // rax
  struct PageSegment *v34; // [rsp+28h] [rbp-30h] BYREF

  if ( a2 + 4111 >= a2 && a2 != -4112 )
  {
    v2 = *((unsigned int *)this + 22);
    v4 = (a2 + 4111) >> 12;
    v34 = 0;
    if ( v4 > v2 )
    {
      v33 = PageAllocator::AllocSegment((PageAllocator *)this, v4);
      v8 = v33;
      if ( v33 )
      {
        v16 = (char *)*((_QWORD *)v33 + 2);
        *(_QWORD *)v16 = *((_QWORD *)v33 + 3) - *((unsigned int *)v33 + 8);
        goto LABEL_30;
      }
      return 0;
    }
    v5 = *((_DWORD *)this + 38) == 0;
    *((_BYTE *)this + 139) = 1;
    if ( v5 )
      AsymetricCriticalSection::FastEnter((AsymetricCriticalSection *)(this + 25));
    v6 = this + 1;
    if ( (unsigned __int64)this[13] < (unsigned int)v4 )
      goto LABEL_34;
    v7 = this + 1;
LABEL_8:
    while ( 1 )
    {
      v7 = (PSLIST_HEADER *)*v7;
      if ( v7 == v6 )
        break;
      v8 = (struct PageSegment *)(v7 + 2);
      v9 = *((_DWORD *)v7 + 18);
      if ( v9 >= (unsigned int)v4 )
      {
        v10 = *((_DWORD *)v7 + 16);
        v11 = -1;
        v5 = !_BitScanForward(&v12, v10);
        if ( !v5 )
          v11 = v12;
        v13 = 0xFFFFFFFF >> (32 - v4);
        while ( v11 != -1 )
        {
          v14 = (unsigned __int64)v7[5] - *((unsigned int *)v7 + 12) - v11;
          if ( v14 < (unsigned int)v4 )
            break;
          if ( (_DWORD)v4 == 1 || (v14 = v13 << v11, ((unsigned int)v14 & v10) == (_DWORD)v14) )
          {
            *((_DWORD *)v7 + 16) = v10 & ~(v13 << v11);
            *((_DWORD *)v7 + 18) = v9 - v4;
            v16 = (char *)&v7[4][256 * v11];
            if ( !v16 )
              goto LABEL_8;
            v17 = (unsigned int)((_DWORD)v4 << 12);
            this[20] = (PSLIST_HEADER)((char *)this[20] + v17);
            v18 = _InterlockedExchangeAdd64(&qword_180443988, v17);
            if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
              McTemplateU0x_EventWriteTransfer(v17, v14, v17 + v18);
            if ( !*((_DWORD *)v7 + 18) )
            {
              v7[1]->Alignment = (ULONGLONG)*v7;
              (*v7)->Region = (ULONGLONG)v7[1];
              v22 = this[3];
              v7[1] = (PSLIST_HEADER)v22->Region;
              *v7 = v22;
              *(_QWORD *)v22->Region = v7;
              v22->Region = (ULONGLONG)v7;
            }
            goto LABEL_25;
          }
          v5 = !_BitScanForward(&v15, v10 & (-1 << (v11 + 1)));
          v11 = -1;
          if ( !v5 )
            v11 = v15;
        }
      }
    }
    if ( (_DWORD)v4 != 1 )
      goto LABEL_34;
    v20 = this[16];
    if ( !v20 )
      goto LABEL_34;
    v29 = InterlockedPopEntrySList(v20);
    v30 = v29;
    if ( !v29 )
      goto LABEL_34;
    v8 = (struct PageSegment *)*((_QWORD *)&v29->Next + 1);
    Next = (int)v29[1].Next;
    v34 = v8;
    if ( Next == 1 )
    {
      v16 = (char *)v29;
      *v29 = 0;
      v29[1] = 0;
    }
    else
    {
      v32 = Next - 1;
      LODWORD(v29[1].Next) = v32;
      InterlockedPushEntrySList(this[16], v29);
      v16 = (char *)v30 + (unsigned int)(v32 << 12);
    }
    if ( !v16 )
    {
LABEL_34:
      v21 = (PSLIST_HEADER *)this[5];
      if ( v21 == this + 5 )
      {
        v16 = PageAllocator::TryAllocDecommitedPages((PageAllocator *)this, v4, &v34);
        if ( v16 )
        {
LABEL_36:
          v8 = v34;
          goto LABEL_26;
        }
        v28 = 3;
        if ( (_DWORD)v4 != *((_DWORD *)this + 22) )
          v28 = 1;
        v8 = (struct PageSegment *)PageAllocator::AddPageSegment((PageAllocator *)this, (__int64)&this[v28]);
        if ( !v8 )
        {
          v16 = 0;
          goto LABEL_36;
        }
      }
      else
      {
        v8 = (struct PageSegment *)(v21 + 2);
        v23 = *((_DWORD *)this + 22);
        v21[1]->Alignment = (ULONGLONG)*v21;
        (*v21)->Region = (ULONGLONG)v21[1];
        if ( (_DWORD)v4 == v23 )
          v24 = this[3];
        else
          v24 = *v6;
        v21[1] = (PSLIST_HEADER)v24->Region;
        *v21 = v24;
        *(_QWORD *)v24->Region = v21;
        v24->Region = (ULONGLONG)v21;
      }
      v16 = PageSegment::AllocPages(v8, v4);
      v26 = (unsigned int)((_DWORD)v4 << 12);
      this[20] = (PSLIST_HEADER)((char *)this[20] + v26);
      v27 = _InterlockedExchangeAdd64(&qword_180443988, v26);
      if ( (Microsoft_JScriptEnableBits & 0x200) != 0 )
        McTemplateU0x_EventWriteTransfer(v26, v25, v26 + v27);
LABEL_25:
      this[13] = (PSLIST_HEADER)((char *)this[13] - (unsigned int)v4);
    }
LABEL_26:
    if ( !*((_DWORD *)this + 38) )
      *((_DWORD *)this + 60) = 0;
    if ( v16 )
    {
      *(_QWORD *)v16 = v4;
LABEL_30:
      *((_QWORD *)v16 + 1) = v8;
      return (struct PageAllocation *)v16;
    }
    return 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180026bc0  mov     r11, rsp
0x180026bc3  mov     [r11+18h], rbx
0x180026bc7  mov     [r11+20h], rbp
0x180026bcb  mov     [r11+10h], rdx
0x180026bcf  mov     [r11+8], rcx
0x180026bd3  push    rsi
0x180026bd4  push    rdi
0x180026bd5  push    r12
0x180026bd7  push    r14
0x180026bd9  push    r15
0x180026bdb  sub     rsp, 30h
0x180026bdf  mov     rax, rdx
0x180026be2  lea     r15, [rdx+100Fh]
0x180026be9  cmp     r15, rax
0x180026bec  jb      loc_180026F4D
0x180026bf2  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180026bf6  jz      loc_180026F4D
0x180026bfc  mov     eax, [rcx+58h]
0x180026bff  mov     rdi, rcx
0x180026c02  shr     r15, 0Ch
0x180026c06  mov     qword ptr [r11-30h], 0
0x180026c0e  cmp     r15, rax
0x180026c11  ja      loc_180026F0F
0x180026c17  cmp     dword ptr [rcx+98h], 0
0x180026c1e  mov     byte ptr [rcx+8Bh], 1
0x180026c25  jz      loc_180026E8E
0x180026c2b  mov     ebp, r15d
0x180026c2e  lea     r12, [rdi+8]
0x180026c32  cmp     [rdi+68h], rbp
0x180026c36  jb      loc_180026D78
0x180026c3c  mov     r11d, 20h ; ' '
0x180026c42  mov     r14, r12
0x180026c45  sub     r11d, ebp
0x180026c48  or      r8d, 0FFFFFFFFh
0x180026c4c  mov     r14, [r14]
0x180026c4f  cmp     r14, r12
0x180026c52  jz      loc_180026D63
0x180026c58  lea     rsi, [r14+10h]
0x180026c5c  mov     ebx, [rsi+38h]
0x180026c5f  cmp     ebx, ebp
0x180026c61  jb      short loc_180026C4C
0x180026c63  mov     eax, [rsi+30h]
0x180026c66  mov     r10d, r8d
0x180026c69  bsf     edx, eax
0x180026c6c  mov     r9d, r8d
0x180026c6f  setnz   cl
0x180026c72  test    cl, cl
0x180026c74  mov     ecx, r11d
0x180026c77  cmovnz  r10d, edx
0x180026c7b  shr     r9d, cl
0x180026c7e  mov     [rsp+58h+var_38], 0
0x180026c86  cmp     r10d, r8d
0x180026c89  jz      short loc_180026C4C
0x180026c8b  mov     ecx, [rsi+20h]
0x180026c8e  mov     rdx, [rsi+18h]
0x180026c92  sub     rdx, rcx
0x180026c95  mov     ecx, r10d
0x180026c98  sub     rdx, rcx
0x180026c9b  cmp     rdx, rbp
0x180026c9e  jb      short loc_180026C4C
0x180026ca0  cmp     ebp, 1
0x180026ca3  jz      short loc_180026CD7
0x180026ca5  mov     ecx, r10d
0x180026ca8  mov     edx, r9d
0x180026cab  shl     edx, cl
0x180026cad  mov     ecx, eax
0x180026caf  and     ecx, edx
0x180026cb1  cmp     ecx, edx
0x180026cb3  jz      short loc_180026CD7
0x180026cb5  lea     ecx, [r10+1]
0x180026cb9  mov     edx, r8d
0x180026cbc  shl     edx, cl
0x180026cbe  and     edx, eax
0x180026cc0  bsf     r8d, edx
0x180026cc4  setnz   cl
0x180026cc7  or      r10d, 0FFFFFFFFh
0x180026ccb  test    cl, cl
0x180026ccd  cmovnz  r10d, r8d
0x180026cd1  or      r8d, 0FFFFFFFFh
0x180026cd5  jmp     short loc_180026C7E
0x180026cd7  sub     ebx, ebp
0x180026cd9  mov     ecx, r10d
0x180026cdc  shl     r9d, cl
0x180026cdf  shl     r10d, 0Ch
0x180026ce3  not     r9d
0x180026ce6  and     r9d, eax
0x180026ce9  mov     [rsi+30h], r9d
0x180026ced  mov     [rsi+38h], ebx
0x180026cf0  mov     ebx, r10d
0x180026cf3  add     rbx, [rsi+10h]
0x180026cf7  jz      loc_180026C4C
0x180026cfd  mov     eax, ebp
0x180026cff  shl     eax, 0Ch
0x180026d02  mov     ecx, eax
0x180026d04  add     [rdi+0A0h], rcx
0x180026d0b  lock xadd cs:qword_180443988, rax
0x180026d14  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180026d1b  jnz     loc_180026F3F
0x180026d21  cmp     dword ptr [rsi+38h], 0
0x180026d25  jz      short loc_180026DA6
0x180026d27  sub     [rdi+68h], rbp
0x180026d2b  cmp     dword ptr [rdi+98h], 0
0x180026d32  jz      loc_180026E57
0x180026d38  test    rbx, rbx
0x180026d3b  jz      loc_180026F38
0x180026d41  mov     [rbx], r15
0x180026d44  mov     [rbx+8], rsi
0x180026d48  mov     rax, rbx
0x180026d4b  mov     rbx, [rsp+58h+arg_10]
0x180026d50  mov     rbp, [rsp+58h+arg_18]
0x180026d55  add     rsp, 30h
0x180026d59  pop     r15
0x180026d5b  pop     r14
0x180026d5d  pop     r12
0x180026d5f  pop     rdi
0x180026d60  pop     rsi
0x180026d61  retn
0x180026d63  cmp     ebp, 1
0x180026d66  jnz     short loc_180026D78
0x180026d68  mov     rcx, [rdi+80h]; ListHead
0x180026d6f  test    rcx, rcx
0x180026d72  jnz     loc_180026E9F
0x180026d78  lea     rax, [rdi+28h]
0x180026d7c  mov     r8, [rax]
0x180026d7f  cmp     r8, rax
0x180026d82  jnz     short loc_180026DDA
0x180026d84  lea     r8, [rsp+58h+var_30]; struct PageSegment **
0x180026d89  mov     edx, ebp; unsigned int
0x180026d8b  mov     rcx, rdi; this
0x180026d8e  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x180026d93  mov     rbx, rax
0x180026d96  test    rax, rax
0x180026d99  jz      loc_180026E66
0x180026d9f  mov     rsi, [rsp+58h+var_30]
0x180026da4  jmp     short loc_180026D2B
0x180026da6  mov     rcx, [r14+8]
0x180026daa  mov     rax, [r14]
0x180026dad  mov     [rcx], rax
0x180026db0  mov     rcx, [r14]
0x180026db3  mov     rax, [r14+8]
0x180026db7  mov     [rcx+8], rax
0x180026dbb  mov     rcx, [rdi+18h]
0x180026dbf  mov     rax, [rcx+8]
0x180026dc3  mov     [r14+8], rax
0x180026dc7  mov     [r14], rcx
0x180026dca  mov     rax, [rcx+8]
0x180026dce  mov     [rax], r14
0x180026dd1  mov     [rcx+8], r14
0x180026dd5  jmp     loc_180026D27
0x180026dda  mov     rcx, [r8+8]
0x180026dde  lea     rsi, [r8+10h]
0x180026de2  mov     rax, [r8]
0x180026de5  mov     edx, [rdi+58h]
0x180026de8  mov     [rcx], rax
0x180026deb  mov     rcx, [r8]
0x180026dee  mov     rax, [r8+8]
0x180026df2  mov     [rcx+8], rax
0x180026df6  cmp     ebp, edx
0x180026df8  jz      loc_180026ED7
0x180026dfe  mov     rcx, [r12]
0x180026e02  mov     rax, [rcx+8]
0x180026e06  mov     [r8+8], rax
0x180026e0a  mov     [r8], rcx
0x180026e0d  mov     rax, [rcx+8]
0x180026e11  mov     [rax], r8
0x180026e14  mov     [rcx+8], r8
0x180026e18  mov     edx, ebp; unsigned int
0x180026e1a  mov     rcx, rsi; this
0x180026e1d  call    ?AllocPages@PageSegment@@QEAAPEADI@Z; PageSegment::AllocPages(uint)
0x180026e22  mov     rbx, rax
0x180026e25  mov     eax, ebp
0x180026e27  shl     eax, 0Ch
0x180026e2a  mov     ecx, eax
0x180026e2c  add     [rdi+0A0h], rcx
0x180026e33  lock xadd cs:qword_180443988, rax
0x180026e3c  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180026e43  jz      loc_180026D27
0x180026e49  lea     r8, [rcx+rax]
0x180026e4d  call    McTemplateU0x_EventWriteTransfer
0x180026e52  jmp     loc_180026D27
0x180026e57  mov     dword ptr [rdi+0F0h], 0
0x180026e61  jmp     loc_180026D38
0x180026e66  cmp     ebp, [rdi+58h]
0x180026e69  mov     edx, 18h
0x180026e6e  mov     rcx, rdi; this
0x180026e71  lea     eax, [rdx-10h]
0x180026e74  cmovnz  edx, eax
0x180026e77  add     rdx, rdi
0x180026e7a  call    ?AddPageSegment@PageAllocator@@IEAAPEAVPageSegment@@AEAV?$DListBase@VPageSegment@@@@@Z; PageAllocator::AddPageSegment(DListBase<PageSegment> &)
0x180026e7f  mov     rsi, rax
0x180026e82  test    rax, rax
0x180026e85  jnz     short loc_180026E18
0x180026e87  xor     ebx, ebx
0x180026e89  jmp     loc_180026D9F
0x180026e8e  lea     rcx, [rdi+0C8h]; this
0x180026e95  call    ?FastEnter@AsymetricCriticalSection@@QEAAXXZ; AsymetricCriticalSection::FastEnter(void)
0x180026e9a  jmp     loc_180026C2B
0x180026e9f  call    cs:__imp_InterlockedPopEntrySList
0x180026ea6  nop     dword ptr [rax+rax+00h]
0x180026eab  mov     r14, rax
0x180026eae  test    rax, rax
0x180026eb1  jz      loc_180026D78
0x180026eb7  mov     rsi, [rax+8]
0x180026ebb  mov     ebx, [rax+10h]
0x180026ebe  mov     [rsp+58h+var_30], rsi
0x180026ec3  cmp     ebx, 1
0x180026ec6  jnz     short loc_180026EE0
0x180026ec8  xorps   xmm0, xmm0
0x180026ecb  mov     rbx, rax
0x180026ece  movups  xmmword ptr [rax], xmm0
0x180026ed1  movups  xmmword ptr [rax+10h], xmm0
0x180026ed5  jmp     short loc_180026F01
0x180026ed7  mov     rcx, [rdi+18h]
0x180026edb  jmp     loc_180026E02
0x180026ee0  dec     ebx
0x180026ee2  mov     rdx, r14; ListEntry
0x180026ee5  mov     [rax+10h], ebx
0x180026ee8  mov     rcx, [rdi+80h]; ListHead
0x180026eef  call    cs:__imp_InterlockedPushEntrySList
0x180026ef6  nop     dword ptr [rax+rax+00h]
0x180026efb  shl     ebx, 0Ch
0x180026efe  add     rbx, r14
0x180026f01  test    rbx, rbx
0x180026f04  jnz     loc_180026D2B
0x180026f0a  jmp     loc_180026D78
0x180026f0f  mov     rdx, r15; unsigned __int64
0x180026f12  mov     rcx, rdi; this
0x180026f15  call    ?AllocSegment@PageAllocator@@IEAAPEAVSegment@@_K@Z; PageAllocator::AllocSegment(unsigned __int64)
0x180026f1a  mov     rsi, rax
0x180026f1d  test    rax, rax
0x180026f20  jz      short loc_180026F38
0x180026f22  mov     rbx, [rax+10h]
0x180026f26  mov     eax, [rax+20h]
0x180026f29  mov     rcx, [rsi+18h]
0x180026f2d  sub     rcx, rax
0x180026f30  mov     [rbx], rcx
0x180026f33  jmp     loc_180026D44
0x180026f38  xor     ebx, ebx
0x180026f3a  jmp     loc_180026D48
0x180026f3f  lea     r8, [rcx+rax]
0x180026f43  call    McTemplateU0x_EventWriteTransfer
0x180026f48  jmp     loc_180026D21
0x180026f4d  xor     eax, eax
0x180026f4f  jmp     loc_180026D4B
```
