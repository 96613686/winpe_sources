# PageAllocator::AllocAllocation(unsigned __int64)

- ea: `0x180010ae0`
- end: `0x180010e41`
- name: `?AllocAllocation@PageAllocator@@QEAAPEAVPageAllocation@@_K@Z`
- size: `865`
- prototype: `struct PageAllocation *__fastcall(PageAllocator *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180263b54`

## callees

- `0x1800052bc`
- `0x18000ef2c`
- `0x180010ae0`
- `0x180010e48`
- `0x18006a5f0`
- `0x180255a38`
- `0x180255c94`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x180010dd1`
- `KERNEL32!InterlockedPushEntrySList` at `0x180010dd1`
- `KERNEL32!InterlockedPopEntrySList` at `0x180010d9f`
- `KERNEL32!InterlockedPopEntrySList` at `0x180010d9f`

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
            v18 = _InterlockedExchangeAdd64(&qword_18043D988, v17);
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
      v27 = _InterlockedExchangeAdd64(&qword_18043D988, v26);
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
0x180010ae0  mov     r11, rsp
0x180010ae3  mov     [r11+18h], rbx
0x180010ae7  mov     [r11+20h], rbp
0x180010aeb  mov     [r11+10h], rdx
0x180010aef  mov     [r11+8], rcx
0x180010af3  push    rsi
0x180010af4  push    rdi
0x180010af5  push    r12
0x180010af7  push    r14
0x180010af9  push    r15
0x180010afb  sub     rsp, 30h
0x180010aff  mov     eax, [rcx+58h]
0x180010b02  mov     rdi, rcx
0x180010b05  mov     qword ptr [r11-30h], 0
0x180010b0d  mov     r12, rdx
0x180010b10  cmp     rdx, rax
0x180010b13  ja      loc_180010E03
0x180010b19  cmp     dword ptr [rcx+98h], 0
0x180010b20  mov     byte ptr [rcx+8Bh], 1
0x180010b27  jz      loc_180010D8E
0x180010b2d  mov     ebp, r12d
0x180010b30  lea     r15, [rdi+8]
0x180010b34  cmp     [rdi+68h], rbp
0x180010b38  jb      loc_180010C79
0x180010b3e  mov     r11d, 20h ; ' '
0x180010b44  mov     r14, r15
0x180010b47  sub     r11d, ebp
0x180010b4a  or      r8d, 0FFFFFFFFh
0x180010b4e  mov     r14, [r14]
0x180010b51  cmp     r14, r15
0x180010b54  jz      loc_180010C64
0x180010b5a  lea     rsi, [r14+10h]
0x180010b5e  mov     ebx, [rsi+38h]
0x180010b61  cmp     ebx, ebp
0x180010b63  jb      short loc_180010B4E
0x180010b65  mov     eax, [rsi+30h]
0x180010b68  mov     r10d, r8d
0x180010b6b  bsf     edx, eax
0x180010b6e  mov     r9d, r8d
0x180010b71  setnz   cl
0x180010b74  test    cl, cl
0x180010b76  mov     ecx, r11d
0x180010b79  cmovnz  r10d, edx
0x180010b7d  shr     r9d, cl
0x180010b80  mov     [rsp+58h+var_38], 0
0x180010b88  cmp     r10d, r8d
0x180010b8b  jz      short loc_180010B4E
0x180010b8d  mov     ecx, [rsi+20h]
0x180010b90  mov     rdx, [rsi+18h]
0x180010b94  sub     rdx, rcx
0x180010b97  mov     ecx, r10d
0x180010b9a  sub     rdx, rcx
0x180010b9d  cmp     rdx, rbp
0x180010ba0  jb      short loc_180010B4E
0x180010ba2  cmp     ebp, 1
0x180010ba5  jz      short loc_180010BD9
0x180010ba7  mov     ecx, r10d
0x180010baa  mov     edx, r9d
0x180010bad  shl     edx, cl
0x180010baf  mov     ecx, eax
0x180010bb1  and     ecx, edx
0x180010bb3  cmp     ecx, edx
0x180010bb5  jz      short loc_180010BD9
0x180010bb7  lea     ecx, [r10+1]
0x180010bbb  mov     edx, r8d
0x180010bbe  shl     edx, cl
0x180010bc0  and     edx, eax
0x180010bc2  bsf     r8d, edx
0x180010bc6  setnz   cl
0x180010bc9  or      r10d, 0FFFFFFFFh
0x180010bcd  test    cl, cl
0x180010bcf  cmovnz  r10d, r8d
0x180010bd3  or      r8d, 0FFFFFFFFh
0x180010bd7  jmp     short loc_180010B80
0x180010bd9  sub     ebx, ebp
0x180010bdb  mov     ecx, r10d
0x180010bde  shl     r9d, cl
0x180010be1  shl     r10d, 0Ch
0x180010be5  not     r9d
0x180010be8  and     r9d, eax
0x180010beb  mov     [rsi+30h], r9d
0x180010bef  mov     [rsi+38h], ebx
0x180010bf2  mov     ebx, r10d
0x180010bf5  add     rbx, [rsi+10h]
0x180010bf9  jz      loc_180010B4E
0x180010bff  mov     eax, ebp
0x180010c01  shl     eax, 0Ch
0x180010c04  mov     ecx, eax
0x180010c06  add     [rdi+0A0h], rcx
0x180010c0d  lock xadd cs:qword_18043D988, rax
0x180010c16  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180010c1d  jnz     loc_180010E2C
0x180010c23  cmp     dword ptr [rsi+38h], 0
0x180010c27  jz      short loc_180010CA7
0x180010c29  sub     [rdi+68h], rbp
0x180010c2d  cmp     dword ptr [rdi+98h], 0
0x180010c34  jz      loc_180010D57
0x180010c3a  test    rbx, rbx
0x180010c3d  jz      loc_180010E3A
0x180010c43  mov     [rbx], r12
0x180010c46  mov     [rbx+8], rsi
0x180010c4a  mov     rax, rbx
0x180010c4d  mov     rbx, [rsp+58h+arg_10]
0x180010c52  mov     rbp, [rsp+58h+arg_18]
0x180010c57  add     rsp, 30h
0x180010c5b  pop     r15
0x180010c5d  pop     r14
0x180010c5f  pop     r12
0x180010c61  pop     rdi
0x180010c62  pop     rsi
0x180010c63  retn
0x180010c64  cmp     ebp, 1
0x180010c67  jnz     short loc_180010C79
0x180010c69  mov     rcx, [rdi+80h]; ListHead
0x180010c70  test    rcx, rcx
0x180010c73  jnz     loc_180010D9F
0x180010c79  lea     rax, [rdi+28h]
0x180010c7d  mov     r8, [rax]
0x180010c80  cmp     r8, rax
0x180010c83  jnz     short loc_180010CDB
0x180010c85  lea     r8, [rsp+58h+var_30]; struct PageSegment **
0x180010c8a  mov     edx, ebp; unsigned int
0x180010c8c  mov     rcx, rdi; this
0x180010c8f  call    ?TryAllocDecommitedPages@PageAllocator@@IEAAPEADIPEAPEAVPageSegment@@@Z; PageAllocator::TryAllocDecommitedPages(uint,PageSegment * *)
0x180010c94  mov     rbx, rax
0x180010c97  test    rax, rax
0x180010c9a  jz      loc_180010D66
0x180010ca0  mov     rsi, [rsp+58h+var_30]
0x180010ca5  jmp     short loc_180010C2D
0x180010ca7  mov     rcx, [r14+8]
0x180010cab  mov     rax, [r14]
0x180010cae  mov     [rcx], rax
0x180010cb1  mov     rcx, [r14]
0x180010cb4  mov     rax, [r14+8]
0x180010cb8  mov     [rcx+8], rax
0x180010cbc  mov     rcx, [rdi+18h]
0x180010cc0  mov     rax, [rcx+8]
0x180010cc4  mov     [r14+8], rax
0x180010cc8  mov     [r14], rcx
0x180010ccb  mov     rax, [rcx+8]
0x180010ccf  mov     [rax], r14
0x180010cd2  mov     [rcx+8], r14
0x180010cd6  jmp     loc_180010C29
0x180010cdb  mov     rcx, [r8+8]
0x180010cdf  lea     rsi, [r8+10h]
0x180010ce3  mov     rax, [r8]
0x180010ce6  mov     edx, [rdi+58h]
0x180010ce9  mov     [rcx], rax
0x180010cec  mov     rcx, [r8]
0x180010cef  mov     rax, [r8+8]
0x180010cf3  mov     [rcx+8], rax
0x180010cf7  cmp     ebp, edx
0x180010cf9  jz      loc_180010DEB
0x180010cff  mov     rcx, [r15]
0x180010d02  mov     rax, [rcx+8]
0x180010d06  mov     [r8+8], rax
0x180010d0a  mov     [r8], rcx
0x180010d0d  mov     rax, [rcx+8]
0x180010d11  mov     [rax], r8
0x180010d14  mov     [rcx+8], r8
0x180010d18  mov     edx, ebp; unsigned int
0x180010d1a  mov     rcx, rsi; this
0x180010d1d  call    ?AllocPages@PageSegment@@QEAAPEADI@Z; PageSegment::AllocPages(uint)
0x180010d22  mov     rbx, rax
0x180010d25  mov     eax, ebp
0x180010d27  shl     eax, 0Ch
0x180010d2a  mov     ecx, eax
0x180010d2c  add     [rdi+0A0h], rcx
0x180010d33  lock xadd cs:qword_18043D988, rax
0x180010d3c  test    byte ptr cs:Microsoft_JScriptEnableBits+1, 2
0x180010d43  jz      loc_180010C29
0x180010d49  lea     r8, [rcx+rax]
0x180010d4d  call    McTemplateU0x_EventWriteTransfer
0x180010d52  jmp     loc_180010C29
0x180010d57  mov     dword ptr [rdi+0F0h], 0
0x180010d61  jmp     loc_180010C3A
0x180010d66  cmp     ebp, [rdi+58h]
0x180010d69  mov     edx, 18h
0x180010d6e  mov     rcx, rdi; this
0x180010d71  lea     eax, [rdx-10h]
0x180010d74  cmovnz  edx, eax
0x180010d77  add     rdx, rdi
0x180010d7a  call    ?AddPageSegment@PageAllocator@@IEAAPEAVPageSegment@@AEAV?$DListBase@VPageSegment@@@@@Z; PageAllocator::AddPageSegment(DListBase<PageSegment> &)
0x180010d7f  mov     rsi, rax
0x180010d82  test    rax, rax
0x180010d85  jnz     short loc_180010D18
0x180010d87  xor     ebx, ebx
0x180010d89  jmp     loc_180010CA0
0x180010d8e  lea     rcx, [rdi+0C8h]; this
0x180010d95  call    ?FastEnter@AsymetricCriticalSection@@QEAAXXZ; AsymetricCriticalSection::FastEnter(void)
0x180010d9a  jmp     loc_180010B2D
0x180010d9f  call    cs:__imp_InterlockedPopEntrySList
0x180010da5  mov     r14, rax
0x180010da8  test    rax, rax
0x180010dab  jz      loc_180010C79
0x180010db1  mov     rsi, [rax+8]
0x180010db5  mov     ebx, [rax+10h]
0x180010db8  mov     [rsp+58h+var_30], rsi
0x180010dbd  cmp     ebx, 1
0x180010dc0  jz      short loc_180010DF4
0x180010dc2  dec     ebx
0x180010dc4  mov     rdx, rax; ListEntry
0x180010dc7  mov     [rax+10h], ebx
0x180010dca  mov     rcx, [rdi+80h]; ListHead
0x180010dd1  call    cs:__imp_InterlockedPushEntrySList
0x180010dd7  shl     ebx, 0Ch
0x180010dda  add     rbx, r14
0x180010ddd  test    rbx, rbx
0x180010de0  jnz     loc_180010C2D
0x180010de6  jmp     loc_180010C79
0x180010deb  mov     rcx, [rdi+18h]
0x180010def  jmp     loc_180010D02
0x180010df4  xorps   xmm0, xmm0
0x180010df7  mov     rbx, r14
0x180010dfa  movups  xmmword ptr [rax], xmm0
0x180010dfd  movups  xmmword ptr [rax+10h], xmm0
0x180010e01  jmp     short loc_180010DDD
0x180010e03  mov     rdx, r12; unsigned __int64
0x180010e06  mov     rcx, rdi; this
0x180010e09  call    ?AllocSegment@PageAllocator@@IEAAPEAVSegment@@_K@Z; PageAllocator::AllocSegment(unsigned __int64)
0x180010e0e  mov     rsi, rax
0x180010e11  test    rax, rax
0x180010e14  jz      short loc_180010E3A
0x180010e16  mov     ecx, [rax+20h]
0x180010e19  mov     rdx, [rax+18h]
0x180010e1d  mov     rbx, [rax+10h]
0x180010e21  sub     rdx, rcx
0x180010e24  mov     [rbx], rdx
0x180010e27  jmp     loc_180010C46
0x180010e2c  lea     r8, [rcx+rax]
0x180010e30  call    McTemplateU0x_EventWriteTransfer
0x180010e35  jmp     loc_180010C23
0x180010e3a  xor     eax, eax
0x180010e3c  jmp     loc_180010C4D
```
