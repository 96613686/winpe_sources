# ATL::CComModule::Term(void)

- ea: `0x180004500`
- end: `0x18000466b`
- name: `?Term@CComModule@ATL@@QEAAXXZ`
- size: `363`
- prototype: `void __fastcall(ATL::CComModule *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004a74`

## callees

- `0x1800012d0`
- `0x180004500`
- `0x180015ca6`
- `0x180017010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180004594`
- `KERNEL32!DeleteCriticalSection` at `0x1800045b9`
- `KERNEL32!DeleteCriticalSection` at `0x1800045de`
- `KERNEL32!DeleteCriticalSection` at `0x180004594`
- `KERNEL32!DeleteCriticalSection` at `0x1800045b9`
- `KERNEL32!DeleteCriticalSection` at `0x1800045de`
- `KERNEL32!HeapDestroy` at `0x18000463c`
- `KERNEL32!HeapDestroy` at `0x18000465a`
- `KERNEL32!HeapDestroy` at `0x18000463c`
- `KERNEL32!HeapDestroy` at `0x18000465a`

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

  v1 = (_QWORD *)qword_18001EB50;
  if ( qword_18001EB50 )
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
  if ( memcmp_0(&stru_18001EB90, Buf2, 0x28u) )
    DeleteCriticalSection(&stru_18001EB90);
  if ( memcmp_0(&stru_18001EBB8, Buf2, 0x28u) )
    DeleteCriticalSection(&stru_18001EBB8);
  v5 = Block;
  if ( Block )
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
  if ( hHeap && byte_18001EBF0 )
  {
    v8 = qword_18001EC08;
    if ( qword_18001EC08 )
    {
      v9 = 0;
      do
      {
        v10 = *(void **)(v8 + 8 * v9);
        if ( v10 )
        {
          HeapDestroy(v10);
          v8 = qword_18001EC08;
        }
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (unsigned int)v9 <= dword_18001EC00 );
      v7 = hHeap;
    }
    HeapDestroy(v7);
  }
}

```

## disassembly

```asm
0x180004500  mov     [rsp+arg_0], rbx
0x180004505  push    rdi
0x180004506  sub     rsp, 50h
0x18000450a  mov     rbx, cs:qword_18001EB50
0x180004511  test    rbx, rbx
0x180004514  jz      short loc_18000455E
0x180004516  jmp     short loc_180004558
0x180004518  mov     rcx, [rbx+20h]
0x18000451c  test    rcx, rcx
0x18000451f  jz      short loc_18000452D
0x180004521  mov     rax, [rcx]
0x180004524  mov     rax, [rax+10h]
0x180004528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000452d  mov     rax, [rbx+40h]
0x180004531  xor     ecx, ecx
0x180004533  mov     qword ptr [rbx+20h], 0
0x18000453b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004540  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x18000454a  mov     eax, 48h ; 'H'
0x18000454f  lea     ecx, [rax-10h]
0x180004552  cmovz   eax, ecx
0x180004555  add     rbx, rax
0x180004558  cmp     qword ptr [rbx], 0
0x18000455c  jnz     short loc_180004518
0x18000455e  xor     eax, eax
0x180004560  lea     rdx, [rsp+58h+Buf2]; Buf2
0x180004565  xorps   xmm0, xmm0
0x180004568  mov     [rsp+58h+var_18], rax
0x18000456d  lea     rcx, Buf1; Buf1
0x180004574  movups  [rsp+58h+Buf2], xmm0
0x180004579  lea     ebx, [rax+28h]
0x18000457c  mov     r8d, ebx; Size
0x18000457f  movups  [rsp+58h+var_28], xmm0
0x180004584  call    memcmp_0
0x180004589  test    eax, eax
0x18000458b  jz      short loc_18000459A
0x18000458d  lea     rcx, Buf1; lpCriticalSection
0x180004594  call    cs:__imp_DeleteCriticalSection
0x18000459a  mov     r8, rbx; Size
0x18000459d  lea     rdx, [rsp+58h+Buf2]; Buf2
0x1800045a2  lea     rcx, stru_18001EB90; Buf1
0x1800045a9  call    memcmp_0
0x1800045ae  test    eax, eax
0x1800045b0  jz      short loc_1800045BF
0x1800045b2  lea     rcx, stru_18001EB90; lpCriticalSection
0x1800045b9  call    cs:__imp_DeleteCriticalSection
0x1800045bf  mov     r8, rbx; Size
0x1800045c2  lea     rdx, [rsp+58h+Buf2]; Buf2
0x1800045c7  lea     rcx, stru_18001EBB8; Buf1
0x1800045ce  call    memcmp_0
0x1800045d3  test    eax, eax
0x1800045d5  jz      short loc_1800045E4
0x1800045d7  lea     rcx, stru_18001EBB8; lpCriticalSection
0x1800045de  call    cs:__imp_DeleteCriticalSection
0x1800045e4  mov     rdi, cs:Block
0x1800045eb  test    rdi, rdi
0x1800045ee  jz      short loc_180004610
0x1800045f0  mov     rcx, [rdi+8]
0x1800045f4  mov     rax, [rdi]
0x1800045f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045fc  mov     rbx, [rdi+10h]
0x180004600  mov     rcx, rdi; Block
0x180004603  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004608  mov     rdi, rbx
0x18000460b  test    rbx, rbx
0x18000460e  jnz     short loc_1800045F0
0x180004610  mov     rcx, cs:hHeap
0x180004617  test    rcx, rcx
0x18000461a  jz      short loc_180004660
0x18000461c  cmp     cs:byte_18001EBF0, 0
0x180004623  jz      short loc_180004660
0x180004625  mov     rdx, cs:qword_18001EC08
0x18000462c  test    rdx, rdx
0x18000462f  jz      short loc_18000465A
0x180004631  xor     ebx, ebx
0x180004633  mov     rcx, [rdx+rbx*8]; hHeap
0x180004637  test    rcx, rcx
0x18000463a  jz      short loc_180004649
0x18000463c  call    cs:__imp_HeapDestroy
0x180004642  mov     rdx, cs:qword_18001EC08
0x180004649  inc     ebx
0x18000464b  cmp     ebx, cs:dword_18001EC00
0x180004651  jbe     short loc_180004633
0x180004653  mov     rcx, cs:hHeap; hHeap
0x18000465a  call    cs:__imp_HeapDestroy
0x180004660  mov     rbx, [rsp+58h+arg_0]
0x180004665  add     rsp, 50h
0x180004669  pop     rdi
0x18000466a  retn
```
