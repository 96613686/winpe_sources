# ATL::CComModule::Term(void)

- ea: `0x180012108`
- end: `0x180012274`
- name: `?Term@CComModule@ATL@@QEAAXXZ`
- size: `364`
- prototype: `void __fastcall(ATL::CComModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012718`

## callees

- `0x180012108`
- `0x180012af6`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001220b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001220b`
- `KERNEL32!DeleteCriticalSection` at `0x18001219c`
- `KERNEL32!DeleteCriticalSection` at `0x1800121c1`
- `KERNEL32!DeleteCriticalSection` at `0x1800121e6`
- `KERNEL32!DeleteCriticalSection` at `0x18001219c`
- `KERNEL32!DeleteCriticalSection` at `0x1800121c1`
- `KERNEL32!DeleteCriticalSection` at `0x1800121e6`
- `KERNEL32!HeapDestroy` at `0x180012245`
- `KERNEL32!HeapDestroy` at `0x180012263`
- `KERNEL32!HeapDestroy` at `0x180012245`
- `KERNEL32!HeapDestroy` at `0x180012263`

## pseudocode

```c
void __fastcall ATL::CComModule::Term(ATL::CComModule *this)
{
  _QWORD *v1; // rbx
  __int64 v2; // rcx
  void (__fastcall *v3)(_QWORD); // rax
  __int64 v4; // rax
  _QWORD *v5; // rdi
  _QWORD *v6; // rbx
  HANDLE v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rbx
  void *v10; // rcx
  _OWORD Buf2[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v12; // [rsp+40h] [rbp-18h]

  v1 = (_QWORD *)qword_180024B20;
  if ( qword_180024B20 )
  {
    while ( *v1 )
    {
      v2 = v1[4];
      if ( v2 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
      v3 = (void (__fastcall *)(_QWORD))v1[8];
      v1[4] = 0;
      v3(0);
      v4 = 72;
      if ( _Module == 176 )
        v4 = 56;
      v1 = (_QWORD *)((char *)v1 + v4);
    }
  }
  v12 = 0;
  memset(Buf2, 0, sizeof(Buf2));
  if ( memcmp_0(&Buf1, Buf2, 0x28u) )
    DeleteCriticalSection(&Buf1);
  if ( memcmp_0(&stru_180024B60, Buf2, 0x28u) )
    DeleteCriticalSection(&stru_180024B60);
  if ( memcmp_0(&CriticalSection, Buf2, 0x28u) )
    DeleteCriticalSection(&CriticalSection);
  v5 = (_QWORD *)qword_180024BE8;
  if ( qword_180024BE8 )
  {
    do
    {
      ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
      v6 = (_QWORD *)v5[2];
      operator delete(v5);
      v5 = v6;
    }
    while ( v6 );
  }
  v7 = hHeap;
  if ( hHeap && byte_180024BC0 )
  {
    v8 = qword_180024BD8;
    if ( qword_180024BD8 )
    {
      v9 = 0;
      do
      {
        v10 = *(void **)(v8 + 8 * v9);
        if ( v10 )
        {
          HeapDestroy(v10);
          v8 = qword_180024BD8;
        }
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (unsigned int)v9 <= dword_180024BD0 );
      v7 = hHeap;
    }
    HeapDestroy(v7);
  }
}

```

## disassembly

```asm
0x180012108  mov     [rsp+arg_0], rbx
0x18001210d  push    rdi
0x18001210e  sub     rsp, 50h
0x180012112  mov     rbx, cs:qword_180024B20
0x180012119  test    rbx, rbx
0x18001211c  jz      short loc_180012166
0x18001211e  jmp     short loc_180012160
0x180012120  mov     rcx, [rbx+20h]
0x180012124  test    rcx, rcx
0x180012127  jz      short loc_180012135
0x180012129  mov     rax, [rcx]
0x18001212c  mov     rax, [rax+10h]
0x180012130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012135  mov     rax, [rbx+40h]
0x180012139  xor     ecx, ecx
0x18001213b  mov     qword ptr [rbx+20h], 0
0x180012143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012148  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x180012152  mov     eax, 48h ; 'H'
0x180012157  lea     ecx, [rax-10h]
0x18001215a  cmovz   eax, ecx
0x18001215d  add     rbx, rax
0x180012160  cmp     qword ptr [rbx], 0
0x180012164  jnz     short loc_180012120
0x180012166  xor     eax, eax
0x180012168  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18001216d  xorps   xmm0, xmm0
0x180012170  mov     [rsp+58h+var_18], rax
0x180012175  lea     rcx, Buf1; Buf1
0x18001217c  movups  [rsp+58h+Buf2], xmm0
0x180012181  lea     ebx, [rax+28h]
0x180012184  mov     r8d, ebx; Size
0x180012187  movups  [rsp+58h+var_28], xmm0
0x18001218c  call    memcmp_0
0x180012191  test    eax, eax
0x180012193  jz      short loc_1800121A2
0x180012195  lea     rcx, Buf1; lpCriticalSection
0x18001219c  call    cs:__imp_DeleteCriticalSection
0x1800121a2  mov     r8, rbx; Size
0x1800121a5  lea     rdx, [rsp+58h+Buf2]; Buf2
0x1800121aa  lea     rcx, stru_180024B60; Buf1
0x1800121b1  call    memcmp_0
0x1800121b6  test    eax, eax
0x1800121b8  jz      short loc_1800121C7
0x1800121ba  lea     rcx, stru_180024B60; lpCriticalSection
0x1800121c1  call    cs:__imp_DeleteCriticalSection
0x1800121c7  mov     r8, rbx; Size
0x1800121ca  lea     rdx, [rsp+58h+Buf2]; Buf2
0x1800121cf  lea     rcx, CriticalSection; Buf1
0x1800121d6  call    memcmp_0
0x1800121db  test    eax, eax
0x1800121dd  jz      short loc_1800121EC
0x1800121df  lea     rcx, CriticalSection; lpCriticalSection
0x1800121e6  call    cs:__imp_DeleteCriticalSection
0x1800121ec  mov     rdi, cs:qword_180024BE8
0x1800121f3  test    rdi, rdi
0x1800121f6  jz      short loc_180012219
0x1800121f8  mov     rcx, [rdi+8]
0x1800121fc  mov     rax, [rdi]
0x1800121ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012204  mov     rbx, [rdi+10h]
0x180012208  mov     rcx, rdi
0x18001220b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012211  mov     rdi, rbx
0x180012214  test    rbx, rbx
0x180012217  jnz     short loc_1800121F8
0x180012219  mov     rcx, cs:hHeap
0x180012220  test    rcx, rcx
0x180012223  jz      short loc_180012269
0x180012225  cmp     cs:byte_180024BC0, 0
0x18001222c  jz      short loc_180012269
0x18001222e  mov     rdx, cs:qword_180024BD8
0x180012235  test    rdx, rdx
0x180012238  jz      short loc_180012263
0x18001223a  xor     ebx, ebx
0x18001223c  mov     rcx, [rdx+rbx*8]; hHeap
0x180012240  test    rcx, rcx
0x180012243  jz      short loc_180012252
0x180012245  call    cs:__imp_HeapDestroy
0x18001224b  mov     rdx, cs:qword_180024BD8
0x180012252  inc     ebx
0x180012254  cmp     ebx, cs:dword_180024BD0
0x18001225a  jbe     short loc_18001223C
0x18001225c  mov     rcx, cs:hHeap; hHeap
0x180012263  call    cs:__imp_HeapDestroy
0x180012269  mov     rbx, [rsp+58h+arg_0]
0x18001226e  add     rsp, 50h
0x180012272  pop     rdi
0x180012273  retn
```
