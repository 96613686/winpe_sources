# SBuffer::Replace(SBuffer::Iterator const &,uint,uint)

- ea: `0x140010354`
- end: `0x140010453`
- name: `?Replace@SBuffer@@QEAAXAEBVIterator@1@II@Z`
- size: `255`
- prototype: `void __fastcall(SBuffer *this, const struct SBuffer::Iterator *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b578`

## callees

- `0x1400102cc`
- `0x140010354`
- `0x140013f0a`

## pseudocode

```c
void __fastcall SBuffer::Replace(SBuffer *this, const struct SBuffer::Iterator *a2, unsigned int a3, int a4)
{
  int v4; // r10d
  int v5; // edi
  unsigned int v7; // r15d
  unsigned int v8; // r10d
  int v10; // esi
  __int64 v11; // rbp
  unsigned int v12; // edi
  __int64 v13; // rax
  int v14; // r14d
  __int64 v15; // rax
  unsigned int v16; // edi

  v4 = *((_DWORD *)this + 4);
  v5 = *(_DWORD *)this;
  v7 = *(_DWORD *)a2 - v4;
  v8 = *(_DWORD *)this - *(_DWORD *)a2 + v4;
  if ( v8 < a3 )
    a3 = v8;
  v10 = a4 - a3;
  v11 = v7 + a3;
  if ( (int)(a4 - a3) >= 0 )
  {
    if ( v10 > 0 )
    {
      v14 = v5 + v10;
      if ( (unsigned int)(v5 + v10) > *((_DWORD *)this + 1) )
        SBuffer::ReallocateBuffer((const void **)this, (unsigned int)(3 * v14) >> 1, 1);
      v15 = *((_QWORD *)this + 2) + v7;
      *(_DWORD *)this = v14;
      *(_QWORD *)a2 = v15;
      v16 = v5 - v11;
      if ( v16 )
        memmove_0(
          (void *)((unsigned int)v11 + *((_QWORD *)this + 2) + v10),
          (const void *)(*((_QWORD *)this + 2) + v11),
          v16);
    }
  }
  else
  {
    if ( v5 != (_DWORD)v11 )
    {
      memmove_0(
        (void *)((unsigned int)v11 + *((_QWORD *)this + 2) + v10),
        (const void *)(*((_QWORD *)this + 2) + v11),
        (unsigned int)(v5 - v11));
      v5 = *(_DWORD *)this;
    }
    v12 = v10 + v5;
    if ( v12 > *((_DWORD *)this + 1) )
      SBuffer::ReallocateBuffer((const void **)this, v12, 1);
    v13 = *((_QWORD *)this + 2) + v7;
    *(_DWORD *)this = v12;
    *(_QWORD *)a2 = v13;
  }
}

```

## disassembly

```asm
0x140010354  mov     rax, rsp
0x140010357  mov     [rax+8], rbx
0x14001035b  mov     [rax+10h], rbp
0x14001035f  mov     [rax+18h], rsi
0x140010363  mov     [rax+20h], rdi
0x140010367  push    r12
0x140010369  push    r14
0x14001036b  push    r15
0x14001036d  sub     rsp, 20h
0x140010371  mov     r10d, [rcx+10h]
0x140010375  mov     esi, r9d
0x140010378  mov     edi, [rcx]
0x14001037a  mov     r12, rdx
0x14001037d  mov     r15d, [rdx]
0x140010380  mov     eax, edi
0x140010382  sub     eax, [rdx]
0x140010384  sub     r15d, r10d
0x140010387  add     r10d, eax
0x14001038a  mov     rbx, rcx
0x14001038d  cmp     r10d, r8d
0x140010390  cmovb   r8d, r10d
0x140010394  sub     esi, r8d
0x140010397  lea     ebp, [r15+r8]
0x14001039b  jns     short loc_1400103E7
0x14001039d  mov     ecx, edi
0x14001039f  sub     ecx, ebp
0x1400103a1  jz      short loc_1400103C1
0x1400103a3  mov     rax, [rbx+10h]
0x1400103a7  mov     r8d, ecx; Size
0x1400103aa  mov     r9d, ebp
0x1400103ad  movsxd  rcx, esi
0x1400103b0  add     rcx, rax
0x1400103b3  lea     rdx, [rax+rbp]; Src
0x1400103b7  add     rcx, r9; void *
0x1400103ba  call    memmove_0
0x1400103bf  mov     edi, [rbx]
0x1400103c1  add     edi, esi
0x1400103c3  cmp     edi, [rbx+4]
0x1400103c6  jbe     short loc_1400103D8
0x1400103c8  mov     r8d, 1
0x1400103ce  mov     edx, edi
0x1400103d0  mov     rcx, rbx
0x1400103d3  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x1400103d8  mov     eax, r15d
0x1400103db  add     rax, [rbx+10h]
0x1400103df  mov     [rbx], edi
0x1400103e1  mov     [r12], rax
0x1400103e5  jmp     short loc_140010434
0x1400103e7  test    esi, esi
0x1400103e9  jle     short loc_140010434
0x1400103eb  lea     r14d, [rdi+rsi]
0x1400103ef  cmp     r14d, [rcx+4]
0x1400103f3  jbe     short loc_140010406
0x1400103f5  lea     edx, [r14+r14*2]
0x1400103f9  mov     r8d, 1
0x1400103ff  shr     edx, 1
0x140010401  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x140010406  mov     eax, r15d
0x140010409  add     rax, [rbx+10h]
0x14001040d  mov     [rbx], r14d
0x140010410  mov     [r12], rax
0x140010414  sub     edi, ebp
0x140010416  jz      short loc_140010434
0x140010418  mov     rax, [rbx+10h]
0x14001041c  mov     r9d, ebp
0x14001041f  movsxd  rcx, esi
0x140010422  add     rcx, rax
0x140010425  mov     r8d, edi; Size
0x140010428  lea     rdx, [rax+rbp]; Src
0x14001042c  add     rcx, r9; void *
0x14001042f  call    memmove_0
0x140010434  mov     rbx, [rsp+38h+arg_0]
0x140010439  mov     rbp, [rsp+38h+arg_8]
0x14001043e  mov     rsi, [rsp+38h+arg_10]
0x140010443  mov     rdi, [rsp+38h+arg_18]
0x140010448  add     rsp, 20h
0x14001044c  pop     r15
0x14001044e  pop     r14
0x140010450  pop     r12
0x140010452  retn
```
