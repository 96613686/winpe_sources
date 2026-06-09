# ATL::CComModule::Term(void)

- ea: `0x1800061c8`
- end: `0x180006334`
- name: `?Term@CComModule@ATL@@QEAAXXZ`
- size: `364`
- prototype: `void __fastcall(ATL::CComModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800066f4`

## callees

- `0x1800061c8`
- `0x18000a576`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800062cb`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800062cb`
- `KERNEL32!HeapDestroy` at `0x180006305`
- `KERNEL32!HeapDestroy` at `0x180006323`
- `KERNEL32!HeapDestroy` at `0x180006305`
- `KERNEL32!HeapDestroy` at `0x180006323`
- `KERNEL32!DeleteCriticalSection` at `0x18000625c`
- `KERNEL32!DeleteCriticalSection` at `0x180006281`
- `KERNEL32!DeleteCriticalSection` at `0x1800062a6`
- `KERNEL32!DeleteCriticalSection` at `0x18000625c`
- `KERNEL32!DeleteCriticalSection` at `0x180006281`
- `KERNEL32!DeleteCriticalSection` at `0x1800062a6`

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

  v1 = (_QWORD *)qword_180012EE0;
  if ( qword_180012EE0 )
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
  if ( memcmp_0(&stru_180012F20, Buf2, 0x28u) )
    DeleteCriticalSection(&stru_180012F20);
  if ( memcmp_0(&CriticalSection, Buf2, 0x28u) )
    DeleteCriticalSection(&CriticalSection);
  v5 = (_QWORD *)qword_180012FA8;
  if ( qword_180012FA8 )
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
  if ( hHeap && byte_180012F80 )
  {
    v8 = qword_180012F98;
    if ( qword_180012F98 )
    {
      v9 = 0;
      do
      {
        v10 = *(void **)(v8 + 8 * v9);
        if ( v10 )
        {
          HeapDestroy(v10);
          v8 = qword_180012F98;
        }
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (unsigned int)v9 <= dword_180012F90 );
      v7 = hHeap;
    }
    HeapDestroy(v7);
  }
}

```

## disassembly

```asm
0x1800061c8  mov     [rsp+arg_0], rbx
0x1800061cd  push    rdi
0x1800061ce  sub     rsp, 50h
0x1800061d2  mov     rbx, cs:qword_180012EE0
0x1800061d9  test    rbx, rbx
0x1800061dc  jz      short loc_180006226
0x1800061de  jmp     short loc_180006220
0x1800061e0  mov     rcx, [rbx+20h]
0x1800061e4  test    rcx, rcx
0x1800061e7  jz      short loc_1800061F5
0x1800061e9  mov     rax, [rcx]
0x1800061ec  mov     rax, [rax+10h]
0x1800061f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061f5  mov     rax, [rbx+40h]
0x1800061f9  xor     ecx, ecx
0x1800061fb  mov     qword ptr [rbx+20h], 0
0x180006203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006208  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x180006212  mov     eax, 48h ; 'H'
0x180006217  lea     ecx, [rax-10h]
0x18000621a  cmovz   eax, ecx
0x18000621d  add     rbx, rax
0x180006220  cmp     qword ptr [rbx], 0
0x180006224  jnz     short loc_1800061E0
0x180006226  xor     eax, eax
0x180006228  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18000622d  xorps   xmm0, xmm0
0x180006230  mov     [rsp+58h+var_18], rax
0x180006235  lea     rcx, Buf1; Buf1
0x18000623c  movups  [rsp+58h+Buf2], xmm0
0x180006241  lea     ebx, [rax+28h]
0x180006244  mov     r8d, ebx; Size
0x180006247  movups  [rsp+58h+var_28], xmm0
0x18000624c  call    memcmp_0
0x180006251  test    eax, eax
0x180006253  jz      short loc_180006262
0x180006255  lea     rcx, Buf1; lpCriticalSection
0x18000625c  call    cs:__imp_DeleteCriticalSection
0x180006262  mov     r8, rbx; Size
0x180006265  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18000626a  lea     rcx, stru_180012F20; Buf1
0x180006271  call    memcmp_0
0x180006276  test    eax, eax
0x180006278  jz      short loc_180006287
0x18000627a  lea     rcx, stru_180012F20; lpCriticalSection
0x180006281  call    cs:__imp_DeleteCriticalSection
0x180006287  mov     r8, rbx; Size
0x18000628a  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18000628f  lea     rcx, CriticalSection; Buf1
0x180006296  call    memcmp_0
0x18000629b  test    eax, eax
0x18000629d  jz      short loc_1800062AC
0x18000629f  lea     rcx, CriticalSection; lpCriticalSection
0x1800062a6  call    cs:__imp_DeleteCriticalSection
0x1800062ac  mov     rdi, cs:qword_180012FA8
0x1800062b3  test    rdi, rdi
0x1800062b6  jz      short loc_1800062D9
0x1800062b8  mov     rcx, [rdi+8]
0x1800062bc  mov     rax, [rdi]
0x1800062bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062c4  mov     rbx, [rdi+10h]
0x1800062c8  mov     rcx, rdi
0x1800062cb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800062d1  mov     rdi, rbx
0x1800062d4  test    rbx, rbx
0x1800062d7  jnz     short loc_1800062B8
0x1800062d9  mov     rcx, cs:hHeap
0x1800062e0  test    rcx, rcx
0x1800062e3  jz      short loc_180006329
0x1800062e5  cmp     cs:byte_180012F80, 0
0x1800062ec  jz      short loc_180006329
0x1800062ee  mov     rdx, cs:qword_180012F98
0x1800062f5  test    rdx, rdx
0x1800062f8  jz      short loc_180006323
0x1800062fa  xor     ebx, ebx
0x1800062fc  mov     rcx, [rdx+rbx*8]; hHeap
0x180006300  test    rcx, rcx
0x180006303  jz      short loc_180006312
0x180006305  call    cs:__imp_HeapDestroy
0x18000630b  mov     rdx, cs:qword_180012F98
0x180006312  inc     ebx
0x180006314  cmp     ebx, cs:dword_180012F90
0x18000631a  jbe     short loc_1800062FC
0x18000631c  mov     rcx, cs:hHeap; hHeap
0x180006323  call    cs:__imp_HeapDestroy
0x180006329  mov     rbx, [rsp+58h+arg_0]
0x18000632e  add     rsp, 50h
0x180006332  pop     rdi
0x180006333  retn
```
