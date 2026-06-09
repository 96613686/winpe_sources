# ATL::AtlModuleTerm(ATL::_ATL_MODULE *)

- ea: `0x18000c6d4`
- end: `0x18000c841`
- name: `?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z`
- size: `365`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180001270`

## callees

- `0x18000178c`
- `0x18000c6d4`
- `0x180027366`
- `0x180029010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000c768`
- `KERNEL32!DeleteCriticalSection` at `0x18000c78d`
- `KERNEL32!DeleteCriticalSection` at `0x18000c7b2`
- `KERNEL32!DeleteCriticalSection` at `0x18000c768`
- `KERNEL32!DeleteCriticalSection` at `0x18000c78d`
- `KERNEL32!DeleteCriticalSection` at `0x18000c7b2`
- `KERNEL32!HeapDestroy` at `0x18000c810`
- `KERNEL32!HeapDestroy` at `0x18000c82e`
- `KERNEL32!HeapDestroy` at `0x18000c810`
- `KERNEL32!HeapDestroy` at `0x18000c82e`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleTerm(struct ATL::_ATL_MODULE *a1)
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
  __int64 v13; // [rsp+40h] [rbp-18h]

  v1 = (_QWORD *)qword_180038600;
  if ( qword_180038600 )
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
  v13 = 0;
  memset(Buf2, 0, sizeof(Buf2));
  if ( memcmp_0(&Buf1, Buf2, 0x28u) )
    DeleteCriticalSection(&Buf1);
  if ( memcmp_0(&stru_180038640, Buf2, 0x28u) )
    DeleteCriticalSection(&stru_180038640);
  if ( memcmp_0(&CriticalSection, Buf2, 0x28u) )
    DeleteCriticalSection(&CriticalSection);
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
  if ( hHeap && byte_1800386A0 )
  {
    v8 = qword_1800386B8;
    if ( qword_1800386B8 )
    {
      v9 = 0;
      do
      {
        v10 = *(void **)(v8 + 8 * v9);
        if ( v10 )
        {
          HeapDestroy(v10);
          v8 = qword_1800386B8;
        }
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (unsigned int)v9 <= dword_1800386B0 );
      v7 = hHeap;
    }
    HeapDestroy(v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c6d4  mov     [rsp+arg_0], rbx
0x18000c6d9  push    rdi
0x18000c6da  sub     rsp, 50h
0x18000c6de  mov     rbx, cs:qword_180038600
0x18000c6e5  test    rbx, rbx
0x18000c6e8  jz      short loc_18000C732
0x18000c6ea  jmp     short loc_18000C72C
0x18000c6ec  mov     rcx, [rbx+20h]
0x18000c6f0  test    rcx, rcx
0x18000c6f3  jz      short loc_18000C701
0x18000c6f5  mov     rax, [rcx]
0x18000c6f8  mov     rax, [rax+10h]
0x18000c6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c701  mov     rax, [rbx+40h]
0x18000c705  xor     ecx, ecx
0x18000c707  mov     qword ptr [rbx+20h], 0
0x18000c70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c714  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x18000c71e  mov     eax, 48h ; 'H'
0x18000c723  lea     ecx, [rax-10h]
0x18000c726  cmovz   eax, ecx
0x18000c729  add     rbx, rax
0x18000c72c  cmp     qword ptr [rbx], 0
0x18000c730  jnz     short loc_18000C6EC
0x18000c732  xor     eax, eax
0x18000c734  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18000c739  xorps   xmm0, xmm0
0x18000c73c  mov     [rsp+58h+var_18], rax
0x18000c741  lea     rcx, Buf1; Buf1
0x18000c748  movups  [rsp+58h+Buf2], xmm0
0x18000c74d  lea     ebx, [rax+28h]
0x18000c750  mov     r8d, ebx; Size
0x18000c753  movups  [rsp+58h+var_28], xmm0
0x18000c758  call    memcmp_0
0x18000c75d  test    eax, eax
0x18000c75f  jz      short loc_18000C76E
0x18000c761  lea     rcx, Buf1; lpCriticalSection
0x18000c768  call    cs:__imp_DeleteCriticalSection
0x18000c76e  mov     r8, rbx; Size
0x18000c771  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18000c776  lea     rcx, stru_180038640; Buf1
0x18000c77d  call    memcmp_0
0x18000c782  test    eax, eax
0x18000c784  jz      short loc_18000C793
0x18000c786  lea     rcx, stru_180038640; lpCriticalSection
0x18000c78d  call    cs:__imp_DeleteCriticalSection
0x18000c793  mov     r8, rbx; Size
0x18000c796  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18000c79b  lea     rcx, CriticalSection; Buf1
0x18000c7a2  call    memcmp_0
0x18000c7a7  test    eax, eax
0x18000c7a9  jz      short loc_18000C7B8
0x18000c7ab  lea     rcx, CriticalSection; lpCriticalSection
0x18000c7b2  call    cs:__imp_DeleteCriticalSection
0x18000c7b8  mov     rdi, cs:Block
0x18000c7bf  test    rdi, rdi
0x18000c7c2  jz      short loc_18000C7E4
0x18000c7c4  mov     rcx, [rdi+8]
0x18000c7c8  mov     rax, [rdi]
0x18000c7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7d0  mov     rbx, [rdi+10h]
0x18000c7d4  mov     rcx, rdi; Block
0x18000c7d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c7dc  mov     rdi, rbx
0x18000c7df  test    rbx, rbx
0x18000c7e2  jnz     short loc_18000C7C4
0x18000c7e4  mov     rcx, cs:hHeap
0x18000c7eb  test    rcx, rcx
0x18000c7ee  jz      short loc_18000C834
0x18000c7f0  cmp     cs:byte_1800386A0, 0
0x18000c7f7  jz      short loc_18000C834
0x18000c7f9  mov     rdx, cs:qword_1800386B8
0x18000c800  test    rdx, rdx
0x18000c803  jz      short loc_18000C82E
0x18000c805  xor     ebx, ebx
0x18000c807  mov     rcx, [rdx+rbx*8]; hHeap
0x18000c80b  test    rcx, rcx
0x18000c80e  jz      short loc_18000C81D
0x18000c810  call    cs:__imp_HeapDestroy
0x18000c816  mov     rdx, cs:qword_1800386B8
0x18000c81d  inc     ebx
0x18000c81f  cmp     ebx, cs:dword_1800386B0
0x18000c825  jbe     short loc_18000C807
0x18000c827  mov     rcx, cs:hHeap; hHeap
0x18000c82e  call    cs:__imp_HeapDestroy
0x18000c834  mov     rbx, [rsp+58h+arg_0]
0x18000c839  xor     eax, eax
0x18000c83b  add     rsp, 50h
0x18000c83f  pop     rdi
0x18000c840  retn
```
