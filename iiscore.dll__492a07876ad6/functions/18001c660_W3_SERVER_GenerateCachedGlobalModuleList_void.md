# W3_SERVER::GenerateCachedGlobalModuleList(void)

- ea: `0x18001c660`
- end: `0x18001c81e`
- name: `?GenerateCachedGlobalModuleList@W3_SERVER@@AEAAJXZ`
- size: `446`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e020`

## callees

- `0x18001c564`
- `0x18001c660`
- `0x18003773a`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001c6dc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001c733`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001c77e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001c7d2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001c6dc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001c733`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001c77e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001c7d2`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18001c6b4`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18001c6b4`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001c693`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001c693`

## pseudocode

```c
__int64 __fastcall W3_SERVER::GenerateCachedGlobalModuleList(W3_SERVER *this)
{
  BUFFER *v1; // rdi
  int v3; // esi
  __int64 v4; // rbx
  unsigned int Size; // r15d
  unsigned int v6; // eax
  unsigned int v7; // r15d
  _DWORD *Ptr; // rax
  W3_SERVER *v9; // rcx
  __int64 v10; // r13
  _DWORD *v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // r12
  __int64 i; // r14
  _QWORD *v15; // rax
  _DWORD *v16; // rax
  _DWORD *v17; // rax
  unsigned int v19; // [rsp+70h] [rbp+8h] BYREF
  int v20; // [rsp+78h] [rbp+10h]
  unsigned int v21; // [rsp+80h] [rbp+18h]
  _DWORD *v22; // [rsp+88h] [rbp+20h]

  v1 = (W3_SERVER *)((char *)this + 1056);
  memset_0((char *)this + 1056, 0, 0xB8u);
  if ( BUFFER::Resize(v1, 0x400u) )
  {
    v3 = 0;
    v4 = 0;
    Size = BUFFER::QuerySize(v1);
    v6 = *((_DWORD *)this + 152);
    v7 = Size >> 2;
    v19 = v7;
    v21 = v6;
    Ptr = BUFFER::QueryPtr(v1);
    v20 = 1;
    v10 = 0;
    v11 = Ptr;
    v22 = Ptr;
    while ( (unsigned int)v10 < 0x20 )
    {
      v12 = v21;
      v13 = 0;
      *((_DWORD *)this + v10 + 278) = v4;
      while ( (unsigned int)v13 < 5 )
      {
        for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
        {
          v15 = BUFFER::QueryPtr((W3_SERVER *)((char *)this + 560));
          v11 = v22;
          if ( (v20 & *(_DWORD *)(v15[i] + 4 * v13 + 152)) != 0 )
          {
            v22[v4] = i;
            v4 = (unsigned int)(v4 + 1);
            if ( (_DWORD)v4 == v7 )
            {
              v3 = W3_SERVER::DoubleExpandedModuleList(v9, v1, &v19);
              if ( v3 < 0 )
                return (unsigned int)v3;
              v16 = BUFFER::QueryPtr(v1);
              v7 = v19;
              v11 = v16;
              v22 = v16;
            }
          }
          v12 = v21;
        }
        v13 = (unsigned int)(v13 + 1);
      }
      v11[v4] = -1;
      v4 = (unsigned int)(v4 + 1);
      if ( (_DWORD)v4 == v7 )
      {
        v3 = W3_SERVER::DoubleExpandedModuleList(v9, v1, &v19);
        if ( v3 < 0 )
          return (unsigned int)v3;
        v17 = BUFFER::QueryPtr(v1);
        v7 = v19;
        v11 = v17;
        v22 = v17;
      }
      v20 *= 2;
      v10 = (unsigned int)(v10 + 1);
    }
    *((_DWORD *)this + 277) = v4;
    *((_DWORD *)this + 276) = 1;
  }
  else
  {
    return (unsigned int)-2147024888;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001c660  push    rbx
0x18001c662  push    rbp
0x18001c663  push    rsi
0x18001c664  push    rdi
0x18001c665  push    r12
0x18001c667  push    r13
0x18001c669  push    r14
0x18001c66b  push    r15
0x18001c66d  sub     rsp, 28h
0x18001c671  lea     rdi, [rcx+420h]
0x18001c678  mov     rbp, rcx
0x18001c67b  mov     rcx, rdi; void *
0x18001c67e  xor     edx, edx; Val
0x18001c680  mov     r8d, 0B8h; Size
0x18001c686  call    memset_0
0x18001c68b  mov     edx, 400h
0x18001c690  mov     rcx, rdi
0x18001c693  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18001c69a  nop     dword ptr [rax+rax+00h]
0x18001c69f  test    al, al
0x18001c6a1  jnz     short loc_18001C6AD
0x18001c6a3  mov     esi, 80070008h
0x18001c6a8  jmp     loc_18001C80A
0x18001c6ad  mov     rcx, rdi
0x18001c6b0  xor     esi, esi
0x18001c6b2  xor     ebx, ebx
0x18001c6b4  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18001c6bb  nop     dword ptr [rax+rax+00h]
0x18001c6c0  mov     r15d, eax
0x18001c6c3  mov     rcx, rdi
0x18001c6c6  mov     eax, [rbp+260h]
0x18001c6cc  shr     r15d, 2
0x18001c6d0  mov     [rsp+68h+arg_0], r15d
0x18001c6d5  mov     [rsp+68h+arg_10], eax
0x18001c6dc  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001c6e3  nop     dword ptr [rax+rax+00h]
0x18001c6e8  mov     [rsp+68h+arg_8], 1
0x18001c6f0  xor     r13d, r13d
0x18001c6f3  mov     rdx, rax
0x18001c6f6  mov     [rsp+68h+arg_18], rax
0x18001c6fe  cmp     r13d, 20h ; ' '
0x18001c702  jnb     loc_18001C7FA
0x18001c708  mov     eax, [rsp+68h+arg_10]
0x18001c70f  xor     r12d, r12d
0x18001c712  mov     [rbp+r13*4+458h], ebx
0x18001c71a  cmp     r12d, 5
0x18001c71e  jnb     loc_18001C7AE
0x18001c724  xor     r14d, r14d
0x18001c727  cmp     r14d, eax
0x18001c72a  jnb     short loc_18001C7A6
0x18001c72c  lea     rcx, [rbp+230h]
0x18001c733  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001c73a  nop     dword ptr [rax+rax+00h]
0x18001c73f  mov     edx, [rsp+68h+arg_8]
0x18001c743  mov     rax, [rax+r14*8]
0x18001c747  test    [rax+r12*4+98h], edx
0x18001c74f  mov     rdx, [rsp+68h+arg_18]
0x18001c757  jz      short loc_18001C79A
0x18001c759  mov     [rdx+rbx*4], r14d
0x18001c75d  inc     ebx
0x18001c75f  cmp     ebx, r15d
0x18001c762  jnz     short loc_18001C79A
0x18001c764  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x18001c769  mov     rdx, rdi; struct BUFFER *
0x18001c76c  call    ?DoubleExpandedModuleList@W3_SERVER@@AEAAJPEAVBUFFER@@PEAK@Z; W3_SERVER::DoubleExpandedModuleList(BUFFER *,ulong *)
0x18001c771  mov     esi, eax
0x18001c773  test    eax, eax
0x18001c775  js      loc_18001C80A
0x18001c77b  mov     rcx, rdi
0x18001c77e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001c785  nop     dword ptr [rax+rax+00h]
0x18001c78a  mov     r15d, [rsp+68h+arg_0]
0x18001c78f  mov     rdx, rax
0x18001c792  mov     [rsp+68h+arg_18], rax
0x18001c79a  mov     eax, [rsp+68h+arg_10]
0x18001c7a1  inc     r14d
0x18001c7a4  jmp     short loc_18001C727
0x18001c7a6  inc     r12d
0x18001c7a9  jmp     loc_18001C71A
0x18001c7ae  mov     dword ptr [rdx+rbx*4], 0FFFFFFFFh
0x18001c7b5  inc     ebx
0x18001c7b7  cmp     ebx, r15d
0x18001c7ba  jnz     short loc_18001C7EE
0x18001c7bc  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x18001c7c1  mov     rdx, rdi; struct BUFFER *
0x18001c7c4  call    ?DoubleExpandedModuleList@W3_SERVER@@AEAAJPEAVBUFFER@@PEAK@Z; W3_SERVER::DoubleExpandedModuleList(BUFFER *,ulong *)
0x18001c7c9  mov     esi, eax
0x18001c7cb  test    eax, eax
0x18001c7cd  js      short loc_18001C80A
0x18001c7cf  mov     rcx, rdi
0x18001c7d2  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001c7d9  nop     dword ptr [rax+rax+00h]
0x18001c7de  mov     r15d, [rsp+68h+arg_0]
0x18001c7e3  mov     rdx, rax
0x18001c7e6  mov     [rsp+68h+arg_18], rax
0x18001c7ee  shl     [rsp+68h+arg_8], 1
0x18001c7f2  inc     r13d
0x18001c7f5  jmp     loc_18001C6FE
0x18001c7fa  mov     [rbp+454h], ebx
0x18001c800  mov     dword ptr [rbp+450h], 1
0x18001c80a  mov     eax, esi
0x18001c80c  add     rsp, 28h
0x18001c810  pop     r15
0x18001c812  pop     r14
0x18001c814  pop     r13
0x18001c816  pop     r12
0x18001c818  pop     rdi
0x18001c819  pop     rsi
0x18001c81a  pop     rbp
0x18001c81b  pop     rbx
0x18001c81c  retn
```
