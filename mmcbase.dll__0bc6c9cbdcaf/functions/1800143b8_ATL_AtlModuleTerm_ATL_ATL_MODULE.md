# ATL::AtlModuleTerm(ATL::_ATL_MODULE *)

- ea: `0x1800143b8`
- end: `0x180014526`
- name: `?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z`
- size: `366`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180007ca8`

## callees

- `0x1800143b8`
- `0x18001b516`
- `0x18001d010`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x1800144bb`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x1800144bb`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800144f5`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180014513`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800144f5`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180014513`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001444c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014471`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014496`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001444c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014471`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014496`

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

  v1 = (_QWORD *)qword_18002C390;
  if ( qword_18002C390 )
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
  if ( memcmp_0(&CriticalSection, Buf2, 0x28u) )
    DeleteCriticalSection(&CriticalSection);
  if ( memcmp_0(&Buf1, Buf2, 0x28u) )
    DeleteCriticalSection(&Buf1);
  if ( memcmp_0(&stru_18002C3F8, Buf2, 0x28u) )
    DeleteCriticalSection(&stru_18002C3F8);
  v5 = (_QWORD *)qword_18002C458;
  if ( qword_18002C458 )
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
  v7 = qword_18002C3A0;
  if ( qword_18002C3A0 && byte_18002C430 )
  {
    v8 = qword_18002C448;
    if ( qword_18002C448 )
    {
      v9 = 0;
      do
      {
        v10 = *(void **)(v8 + 8 * v9);
        if ( v10 )
        {
          HeapDestroy(v10);
          v8 = qword_18002C448;
        }
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (unsigned int)v9 <= dword_18002C440 );
      v7 = qword_18002C3A0;
    }
    HeapDestroy(v7);
  }
  return 0;
}

```

## disassembly

```asm
0x1800143b8  mov     [rsp+arg_0], rbx
0x1800143bd  push    rdi
0x1800143be  sub     rsp, 50h
0x1800143c2  mov     rbx, cs:qword_18002C390
0x1800143c9  test    rbx, rbx
0x1800143cc  jz      short loc_180014416
0x1800143ce  jmp     short loc_180014410
0x1800143d0  mov     rcx, [rbx+20h]
0x1800143d4  test    rcx, rcx
0x1800143d7  jz      short loc_1800143E5
0x1800143d9  mov     rax, [rcx]
0x1800143dc  mov     rax, [rax+10h]
0x1800143e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143e5  mov     rax, [rbx+40h]
0x1800143e9  xor     ecx, ecx
0x1800143eb  mov     qword ptr [rbx+20h], 0
0x1800143f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143f8  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x180014402  mov     eax, 48h ; 'H'
0x180014407  lea     ecx, [rax-10h]
0x18001440a  cmovz   eax, ecx
0x18001440d  add     rbx, rax
0x180014410  cmp     qword ptr [rbx], 0
0x180014414  jnz     short loc_1800143D0
0x180014416  xor     eax, eax
0x180014418  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18001441d  xorps   xmm0, xmm0
0x180014420  mov     [rsp+58h+var_18], rax
0x180014425  lea     rcx, CriticalSection; Buf1
0x18001442c  movups  [rsp+58h+Buf2], xmm0
0x180014431  lea     ebx, [rax+28h]
0x180014434  mov     r8d, ebx; Size
0x180014437  movups  [rsp+58h+var_28], xmm0
0x18001443c  call    memcmp_0
0x180014441  test    eax, eax
0x180014443  jz      short loc_180014452
0x180014445  lea     rcx, CriticalSection; lpCriticalSection
0x18001444c  call    cs:__imp_DeleteCriticalSection
0x180014452  mov     r8, rbx; Size
0x180014455  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18001445a  lea     rcx, Buf1; Buf1
0x180014461  call    memcmp_0
0x180014466  test    eax, eax
0x180014468  jz      short loc_180014477
0x18001446a  lea     rcx, Buf1; lpCriticalSection
0x180014471  call    cs:__imp_DeleteCriticalSection
0x180014477  mov     r8, rbx; Size
0x18001447a  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18001447f  lea     rcx, stru_18002C3F8; Buf1
0x180014486  call    memcmp_0
0x18001448b  test    eax, eax
0x18001448d  jz      short loc_18001449C
0x18001448f  lea     rcx, stru_18002C3F8; lpCriticalSection
0x180014496  call    cs:__imp_DeleteCriticalSection
0x18001449c  mov     rdi, cs:qword_18002C458
0x1800144a3  test    rdi, rdi
0x1800144a6  jz      short loc_1800144C9
0x1800144a8  mov     rcx, [rdi+8]
0x1800144ac  mov     rax, [rdi]
0x1800144af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144b4  mov     rbx, [rdi+10h]
0x1800144b8  mov     rcx, rdi
0x1800144bb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800144c1  mov     rdi, rbx
0x1800144c4  test    rbx, rbx
0x1800144c7  jnz     short loc_1800144A8
0x1800144c9  mov     rcx, cs:qword_18002C3A0
0x1800144d0  test    rcx, rcx
0x1800144d3  jz      short loc_180014519
0x1800144d5  cmp     cs:byte_18002C430, 0
0x1800144dc  jz      short loc_180014519
0x1800144de  mov     rdx, cs:qword_18002C448
0x1800144e5  test    rdx, rdx
0x1800144e8  jz      short loc_180014513
0x1800144ea  xor     ebx, ebx
0x1800144ec  mov     rcx, [rdx+rbx*8]; hHeap
0x1800144f0  test    rcx, rcx
0x1800144f3  jz      short loc_180014502
0x1800144f5  call    cs:__imp_HeapDestroy
0x1800144fb  mov     rdx, cs:qword_18002C448
0x180014502  inc     ebx
0x180014504  cmp     ebx, cs:dword_18002C440
0x18001450a  jbe     short loc_1800144EC
0x18001450c  mov     rcx, cs:qword_18002C3A0; hHeap
0x180014513  call    cs:__imp_HeapDestroy
0x180014519  mov     rbx, [rsp+58h+arg_0]
0x18001451e  xor     eax, eax
0x180014520  add     rsp, 50h
0x180014524  pop     rdi
0x180014525  retn
```
