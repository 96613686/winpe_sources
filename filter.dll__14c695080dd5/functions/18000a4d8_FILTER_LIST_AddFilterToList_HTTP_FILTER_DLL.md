# FILTER_LIST::AddFilterToList(HTTP_FILTER_DLL *)

- ea: `0x18000a4d8`
- end: `0x18000a6aa`
- name: `?AddFilterToList@FILTER_LIST@@QEAAJPEAVHTTP_FILTER_DLL@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(FILTER_LIST *__hidden this, struct HTTP_FILTER_DLL *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006e10`

## callees

- `0x18000a4d8`
- `0x18000c912`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a56e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a5a5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a5b2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a5ce`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a5ed`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a5fa`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a61a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a636`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a643`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a663`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a56e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a5a5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a5b2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a5ce`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a5ed`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a5fa`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a61a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a636`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a643`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a663`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000a4f4`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000a4f4`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000a514`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000a530`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000a549`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000a514`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000a530`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000a549`

## pseudocode

```c
__int64 __fastcall FILTER_LIST::AddFilterToList(FILTER_LIST *this, struct HTTP_FILTER_DLL *a2)
{
  BUFFER *v2; // rsi
  unsigned int Size; // eax
  int v6; // edx
  __int64 i; // r15
  _QWORD *Ptr; // rax
  size_t v10; // rdi
  char *v11; // rbx
  char *v12; // rax
  size_t v13; // rdi
  char *v14; // rbx
  char *v15; // rax
  size_t v16; // rdi
  char *v17; // rbx
  char *v18; // rax

  v2 = (FILTER_LIST *)((char *)this + 24);
  Size = BUFFER::QuerySize((FILTER_LIST *)((char *)this + 24));
  v6 = *((_DWORD *)this + 4);
  if ( v6 + 1 > Size >> 3
    && (!BUFFER::Resize(v2, 8 * v6 + 40)
     || !BUFFER::Resize((FILTER_LIST *)((char *)this + 136), 4 * *((_DWORD *)this + 4) + 20)
     || !BUFFER::Resize((FILTER_LIST *)((char *)this + 80), 4 * *((_DWORD *)this + 4) + 20)) )
  {
    return 2147942408LL;
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
  {
    Ptr = BUFFER::QueryPtr(v2);
    if ( ((*(_DWORD *)(Ptr[i] + 60LL) | *(_DWORD *)(Ptr[i] + 64LL)) & 0xE0000u) < ((*((_DWORD *)a2 + 15)
                                                                                  | *((_DWORD *)a2 + 16))
                                                                                 & 0xE0000u) )
      break;
  }
  v10 = 8LL * (unsigned int)(*((_DWORD *)this + 4) - i);
  v11 = (char *)BUFFER::QueryPtr(v2) + 8 * i;
  v12 = (char *)BUFFER::QueryPtr(v2);
  memmove_0(&v12[8 * i + 8], v11, v10);
  *((_QWORD *)BUFFER::QueryPtr(v2) + i) = a2;
  v13 = 4LL * (unsigned int)(*((_DWORD *)this + 4) - i);
  v14 = (char *)BUFFER::QueryPtr((FILTER_LIST *)((char *)this + 136)) + 4 * i;
  v15 = (char *)BUFFER::QueryPtr((FILTER_LIST *)((char *)this + 136));
  memmove_0(&v15[4 * i + 4], v14, v13);
  LODWORD(v14) = *((_DWORD *)a2 + 16);
  *((_DWORD *)BUFFER::QueryPtr((FILTER_LIST *)((char *)this + 136)) + i) = (_DWORD)v14;
  v16 = 4LL * (unsigned int)(*((_DWORD *)this + 4) - i);
  v17 = (char *)BUFFER::QueryPtr((FILTER_LIST *)((char *)this + 80)) + 4 * i;
  v18 = (char *)BUFFER::QueryPtr((FILTER_LIST *)((char *)this + 80));
  memmove_0(&v18[4 * i + 4], v17, v16);
  LODWORD(v17) = *((_DWORD *)a2 + 15);
  *((_DWORD *)BUFFER::QueryPtr((FILTER_LIST *)((char *)this + 80)) + i) = (_DWORD)v17;
  ++*((_DWORD *)this + 4);
  *((_DWORD *)this + 32) |= *((_DWORD *)a2 + 16);
  *((_DWORD *)this + 18) |= *((_DWORD *)a2 + 15);
  if ( !*((_DWORD *)a2 + 33) )
    *((_DWORD *)this + 46) = 0;
  return 0;
}

```

## disassembly

```asm
0x18000a4d8  push    rbx
0x18000a4da  push    rbp
0x18000a4db  push    rsi
0x18000a4dc  push    rdi
0x18000a4dd  push    r13
0x18000a4df  push    r14
0x18000a4e1  push    r15
0x18000a4e3  sub     rsp, 20h
0x18000a4e7  lea     rsi, [rcx+18h]
0x18000a4eb  mov     r14, rcx
0x18000a4ee  mov     rcx, rsi
0x18000a4f1  mov     r13, rdx
0x18000a4f4  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000a4fa  mov     edx, [r14+10h]
0x18000a4fe  shr     eax, 3
0x18000a501  lea     r8d, [rdx+1]
0x18000a505  cmp     r8d, eax
0x18000a508  jbe     short loc_18000A55D
0x18000a50a  lea     edx, ds:28h[rdx*8]
0x18000a511  mov     rcx, rsi
0x18000a514  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000a51a  test    al, al
0x18000a51c  jz      short loc_18000A553
0x18000a51e  mov     edx, [r14+10h]
0x18000a522  lea     rcx, [r14+88h]
0x18000a529  lea     edx, ds:14h[rdx*4]
0x18000a530  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000a536  test    al, al
0x18000a538  jz      short loc_18000A553
0x18000a53a  mov     edx, [r14+10h]
0x18000a53e  lea     rcx, [r14+50h]
0x18000a542  lea     edx, ds:14h[rdx*4]
0x18000a549  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000a54f  test    al, al
0x18000a551  jnz     short loc_18000A55D
0x18000a553  mov     eax, 80070008h
0x18000a558  jmp     loc_18000A69B
0x18000a55d  xor     r15d, r15d
0x18000a560  cmp     [r14+10h], r15d
0x18000a564  jbe     short loc_18000A597
0x18000a566  mov     ebx, 0E0000h
0x18000a56b  mov     rcx, rsi
0x18000a56e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a574  mov     rdx, [rax+r15*8]
0x18000a578  mov     eax, [r13+40h]
0x18000a57c  or      eax, [r13+3Ch]
0x18000a580  and     eax, ebx
0x18000a582  mov     ecx, [rdx+40h]
0x18000a585  or      ecx, [rdx+3Ch]
0x18000a588  and     ecx, ebx
0x18000a58a  cmp     ecx, eax
0x18000a58c  jb      short loc_18000A597
0x18000a58e  inc     r15d
0x18000a591  cmp     r15d, [r14+10h]
0x18000a595  jb      short loc_18000A56B
0x18000a597  mov     edi, [r14+10h]
0x18000a59b  mov     rcx, rsi
0x18000a59e  sub     edi, r15d
0x18000a5a1  shl     rdi, 3
0x18000a5a5  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a5ab  mov     rcx, rsi
0x18000a5ae  lea     rbx, [rax+r15*8]
0x18000a5b2  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a5b8  mov     r8, rdi; Size
0x18000a5bb  mov     rdx, rbx; Src
0x18000a5be  lea     rcx, [rax+8]
0x18000a5c2  lea     rcx, [rcx+r15*8]; void *
0x18000a5c6  call    memmove_0
0x18000a5cb  mov     rcx, rsi
0x18000a5ce  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a5d4  lea     rsi, [r14+88h]
0x18000a5db  mov     rcx, rsi
0x18000a5de  mov     [rax+r15*8], r13
0x18000a5e2  mov     edi, [r14+10h]
0x18000a5e6  sub     edi, r15d
0x18000a5e9  shl     rdi, 2
0x18000a5ed  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a5f3  mov     rcx, rsi
0x18000a5f6  lea     rbx, [rax+r15*4]
0x18000a5fa  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a600  mov     r8, rdi; Size
0x18000a603  mov     rdx, rbx; Src
0x18000a606  lea     rcx, [rax+4]
0x18000a60a  lea     rcx, [rcx+r15*4]; void *
0x18000a60e  call    memmove_0
0x18000a613  mov     ebx, [r13+40h]
0x18000a617  mov     rcx, rsi
0x18000a61a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a620  lea     rsi, [r14+50h]
0x18000a624  mov     rcx, rsi
0x18000a627  mov     [rax+r15*4], ebx
0x18000a62b  mov     edi, [r14+10h]
0x18000a62f  sub     edi, r15d
0x18000a632  shl     rdi, 2
0x18000a636  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a63c  mov     rcx, rsi
0x18000a63f  lea     rbx, [rax+r15*4]
0x18000a643  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a649  mov     r8, rdi; Size
0x18000a64c  mov     rdx, rbx; Src
0x18000a64f  lea     rcx, [rax+4]
0x18000a653  lea     rcx, [rcx+r15*4]; void *
0x18000a657  call    memmove_0
0x18000a65c  mov     ebx, [r13+3Ch]
0x18000a660  mov     rcx, rsi
0x18000a663  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a669  mov     [rax+r15*4], ebx
0x18000a66d  inc     dword ptr [r14+10h]
0x18000a671  mov     eax, [r13+40h]
0x18000a675  or      [r14+80h], eax
0x18000a67c  mov     eax, [r13+3Ch]
0x18000a680  or      [r14+48h], eax
0x18000a684  cmp     dword ptr [r13+84h], 0
0x18000a68c  jnz     short loc_18000A699
0x18000a68e  mov     dword ptr [r14+0B8h], 0
0x18000a699  xor     eax, eax
0x18000a69b  add     rsp, 20h
0x18000a69f  pop     r15
0x18000a6a1  pop     r14
0x18000a6a3  pop     r13
0x18000a6a5  pop     rdi
0x18000a6a6  pop     rsi
0x18000a6a7  pop     rbp
0x18000a6a8  pop     rbx
0x18000a6a9  retn
```
