# W3_SERVER::GenerateCachedGlobalModuleList(void)

- ea: `0x18001af30`
- end: `0x18001b0c5`
- name: `?GenerateCachedGlobalModuleList@W3_SERVER@@AEAAJXZ`
- size: `405`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c6fc`

## callees

- `0x18001ae54`
- `0x18001af30`
- `0x18003439a`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001afa0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001afed`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001b032`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001b080`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001afa0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001afed`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001b032`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001b080`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18001af7e`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18001af7e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001af63`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001af63`

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
0x18001af30  push    rbx
0x18001af32  push    rbp
0x18001af33  push    rsi
0x18001af34  push    rdi
0x18001af35  push    r12
0x18001af37  push    r13
0x18001af39  push    r14
0x18001af3b  push    r15
0x18001af3d  sub     rsp, 28h
0x18001af41  lea     rdi, [rcx+420h]
0x18001af48  mov     rbp, rcx
0x18001af4b  mov     rcx, rdi; void *
0x18001af4e  xor     edx, edx; Val
0x18001af50  mov     r8d, 0B8h; Size
0x18001af56  call    memset_0
0x18001af5b  mov     edx, 400h
0x18001af60  mov     rcx, rdi
0x18001af63  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18001af69  test    al, al
0x18001af6b  jnz     short loc_18001AF77
0x18001af6d  mov     esi, 80070008h
0x18001af72  jmp     loc_18001B0B2
0x18001af77  mov     rcx, rdi
0x18001af7a  xor     esi, esi
0x18001af7c  xor     ebx, ebx
0x18001af7e  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18001af84  mov     r15d, eax
0x18001af87  mov     rcx, rdi
0x18001af8a  mov     eax, [rbp+260h]
0x18001af90  shr     r15d, 2
0x18001af94  mov     [rsp+68h+arg_0], r15d
0x18001af99  mov     [rsp+68h+arg_10], eax
0x18001afa0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001afa6  mov     [rsp+68h+arg_8], 1
0x18001afae  xor     r13d, r13d
0x18001afb1  mov     rdx, rax
0x18001afb4  mov     [rsp+68h+arg_18], rax
0x18001afbc  cmp     r13d, 20h ; ' '
0x18001afc0  jnb     loc_18001B0A2
0x18001afc6  mov     eax, [rsp+68h+arg_10]
0x18001afcd  xor     r12d, r12d
0x18001afd0  mov     [rbp+r13*4+458h], ebx
0x18001afd8  cmp     r12d, 5
0x18001afdc  jnb     short loc_18001B05C
0x18001afde  xor     r14d, r14d
0x18001afe1  cmp     r14d, eax
0x18001afe4  jnb     short loc_18001B054
0x18001afe6  lea     rcx, [rbp+230h]
0x18001afed  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001aff3  mov     edx, [rsp+68h+arg_8]
0x18001aff7  mov     rax, [rax+r14*8]
0x18001affb  test    [rax+r12*4+98h], edx
0x18001b003  mov     rdx, [rsp+68h+arg_18]
0x18001b00b  jz      short loc_18001B048
0x18001b00d  mov     [rdx+rbx*4], r14d
0x18001b011  inc     ebx
0x18001b013  cmp     ebx, r15d
0x18001b016  jnz     short loc_18001B048
0x18001b018  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x18001b01d  mov     rdx, rdi; struct BUFFER *
0x18001b020  call    ?DoubleExpandedModuleList@W3_SERVER@@AEAAJPEAVBUFFER@@PEAK@Z; W3_SERVER::DoubleExpandedModuleList(BUFFER *,ulong *)
0x18001b025  mov     esi, eax
0x18001b027  test    eax, eax
0x18001b029  js      loc_18001B0B2
0x18001b02f  mov     rcx, rdi
0x18001b032  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001b038  mov     r15d, [rsp+68h+arg_0]
0x18001b03d  mov     rdx, rax
0x18001b040  mov     [rsp+68h+arg_18], rax
0x18001b048  mov     eax, [rsp+68h+arg_10]
0x18001b04f  inc     r14d
0x18001b052  jmp     short loc_18001AFE1
0x18001b054  inc     r12d
0x18001b057  jmp     loc_18001AFD8
0x18001b05c  mov     dword ptr [rdx+rbx*4], 0FFFFFFFFh
0x18001b063  inc     ebx
0x18001b065  cmp     ebx, r15d
0x18001b068  jnz     short loc_18001B096
0x18001b06a  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x18001b06f  mov     rdx, rdi; struct BUFFER *
0x18001b072  call    ?DoubleExpandedModuleList@W3_SERVER@@AEAAJPEAVBUFFER@@PEAK@Z; W3_SERVER::DoubleExpandedModuleList(BUFFER *,ulong *)
0x18001b077  mov     esi, eax
0x18001b079  test    eax, eax
0x18001b07b  js      short loc_18001B0B2
0x18001b07d  mov     rcx, rdi
0x18001b080  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001b086  mov     r15d, [rsp+68h+arg_0]
0x18001b08b  mov     rdx, rax
0x18001b08e  mov     [rsp+68h+arg_18], rax
0x18001b096  shl     [rsp+68h+arg_8], 1
0x18001b09a  inc     r13d
0x18001b09d  jmp     loc_18001AFBC
0x18001b0a2  mov     [rbp+454h], ebx
0x18001b0a8  mov     dword ptr [rbp+450h], 1
0x18001b0b2  mov     eax, esi
0x18001b0b4  add     rsp, 28h
0x18001b0b8  pop     r15
0x18001b0ba  pop     r14
0x18001b0bc  pop     r13
0x18001b0be  pop     r12
0x18001b0c0  pop     rdi
0x18001b0c1  pop     rsi
0x18001b0c2  pop     rbp
0x18001b0c3  pop     rbx
0x18001b0c4  retn
```
