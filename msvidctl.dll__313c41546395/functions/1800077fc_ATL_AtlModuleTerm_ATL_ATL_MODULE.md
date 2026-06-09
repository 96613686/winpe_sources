# ATL::AtlModuleTerm(ATL::_ATL_MODULE *)

- ea: `0x1800077fc`
- end: `0x18000796e`
- name: `?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z`
- size: `370`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000cc34`

## callees

- `0x180004740`
- `0x1800077fc`
- `0x1800eee0c`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!HeapDestroy` at `0x18000793d`
- `KERNEL32!HeapDestroy` at `0x18000795b`
- `KERNEL32!HeapDestroy` at `0x18000793d`
- `KERNEL32!HeapDestroy` at `0x18000795b`
- `KERNEL32!DeleteCriticalSection` at `0x180007890`
- `KERNEL32!DeleteCriticalSection` at `0x1800078b5`
- `KERNEL32!DeleteCriticalSection` at `0x1800078da`
- `KERNEL32!DeleteCriticalSection` at `0x180007890`
- `KERNEL32!DeleteCriticalSection` at `0x1800078b5`
- `KERNEL32!DeleteCriticalSection` at `0x1800078da`

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

  v1 = (_QWORD *)qword_18021CFF0;
  if ( qword_18021CFF0 )
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
      if ( (_DWORD)_Module == 176 )
        v4 = 56;
      v1 = (_QWORD *)((char *)v1 + v4);
    }
  }
  v13 = 0;
  memset(Buf2, 0, sizeof(Buf2));
  if ( memcmp_0(&Buf1, Buf2, 0x28u) )
    DeleteCriticalSection(&Buf1);
  if ( memcmp_0(&stru_18021D030, Buf2, 0x28u) )
    DeleteCriticalSection(&stru_18021D030);
  if ( memcmp_0(&stru_18021D058, Buf2, 0x28u) )
    DeleteCriticalSection(&stru_18021D058);
  v5 = qword_18021D0B8;
  if ( qword_18021D0B8 )
  {
    do
    {
      ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
      v6 = (_QWORD *)v5[2];
      operator delete(v5, 0x18u);
      v5 = v6;
    }
    while ( v6 );
  }
  v7 = hHeap;
  if ( hHeap && byte_18021D090 )
  {
    v8 = qword_18021D0A8;
    if ( qword_18021D0A8 )
    {
      v9 = 0;
      do
      {
        v10 = *(void **)(v8 + 8 * v9);
        if ( v10 )
        {
          HeapDestroy(v10);
          v8 = qword_18021D0A8;
        }
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (unsigned int)v9 <= dword_18021D0A0 );
      v7 = hHeap;
    }
    HeapDestroy(v7);
  }
  return 0;
}

```

## disassembly

```asm
0x1800077fc  mov     [rsp+arg_0], rbx
0x180007801  push    rdi
0x180007802  sub     rsp, 50h
0x180007806  mov     rbx, cs:qword_18021CFF0
0x18000780d  test    rbx, rbx
0x180007810  jz      short loc_18000785A
0x180007812  jmp     short loc_180007854
0x180007814  mov     rcx, [rbx+20h]
0x180007818  test    rcx, rcx
0x18000781b  jz      short loc_180007829
0x18000781d  mov     rax, [rcx]
0x180007820  mov     rax, [rax+10h]
0x180007824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007829  mov     rax, [rbx+40h]
0x18000782d  xor     ecx, ecx
0x18000782f  mov     qword ptr [rbx+20h], 0
0x180007837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000783c  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x180007846  mov     eax, 48h ; 'H'
0x18000784b  lea     ecx, [rax-10h]
0x18000784e  cmovz   eax, ecx
0x180007851  add     rbx, rax
0x180007854  cmp     qword ptr [rbx], 0
0x180007858  jnz     short loc_180007814
0x18000785a  xor     eax, eax
0x18000785c  lea     rdx, [rsp+58h+Buf2]; Buf2
0x180007861  xorps   xmm0, xmm0
0x180007864  mov     [rsp+58h+var_18], rax
0x180007869  lea     rcx, Buf1; Buf1
0x180007870  movups  [rsp+58h+Buf2], xmm0
0x180007875  lea     ebx, [rax+28h]
0x180007878  mov     r8d, ebx; Size
0x18000787b  movups  [rsp+58h+var_28], xmm0
0x180007880  call    memcmp_0
0x180007885  test    eax, eax
0x180007887  jz      short loc_180007896
0x180007889  lea     rcx, Buf1; lpCriticalSection
0x180007890  call    cs:__imp_DeleteCriticalSection
0x180007896  mov     r8, rbx; Size
0x180007899  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18000789e  lea     rcx, stru_18021D030; Buf1
0x1800078a5  call    memcmp_0
0x1800078aa  test    eax, eax
0x1800078ac  jz      short loc_1800078BB
0x1800078ae  lea     rcx, stru_18021D030; lpCriticalSection
0x1800078b5  call    cs:__imp_DeleteCriticalSection
0x1800078bb  mov     r8, rbx; Size
0x1800078be  lea     rdx, [rsp+58h+Buf2]; Buf2
0x1800078c3  lea     rcx, stru_18021D058; Buf1
0x1800078ca  call    memcmp_0
0x1800078cf  test    eax, eax
0x1800078d1  jz      short loc_1800078E0
0x1800078d3  lea     rcx, stru_18021D058; lpCriticalSection
0x1800078da  call    cs:__imp_DeleteCriticalSection
0x1800078e0  mov     rdi, cs:qword_18021D0B8
0x1800078e7  test    rdi, rdi
0x1800078ea  jz      short loc_180007911
0x1800078ec  mov     rcx, [rdi+8]
0x1800078f0  mov     rax, [rdi]
0x1800078f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078f8  mov     rbx, [rdi+10h]
0x1800078fc  mov     edx, 18h; unsigned __int64
0x180007901  mov     rcx, rdi; void *
0x180007904  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007909  mov     rdi, rbx
0x18000790c  test    rbx, rbx
0x18000790f  jnz     short loc_1800078EC
0x180007911  mov     rcx, cs:hHeap
0x180007918  test    rcx, rcx
0x18000791b  jz      short loc_180007961
0x18000791d  cmp     cs:byte_18021D090, 0
0x180007924  jz      short loc_180007961
0x180007926  mov     rdx, cs:qword_18021D0A8
0x18000792d  test    rdx, rdx
0x180007930  jz      short loc_18000795B
0x180007932  xor     ebx, ebx
0x180007934  mov     rcx, [rdx+rbx*8]; hHeap
0x180007938  test    rcx, rcx
0x18000793b  jz      short loc_18000794A
0x18000793d  call    cs:__imp_HeapDestroy
0x180007943  mov     rdx, cs:qword_18021D0A8
0x18000794a  inc     ebx
0x18000794c  cmp     ebx, cs:dword_18021D0A0
0x180007952  jbe     short loc_180007934
0x180007954  mov     rcx, cs:hHeap; hHeap
0x18000795b  call    cs:__imp_HeapDestroy
0x180007961  mov     rbx, [rsp+58h+arg_0]
0x180007966  xor     eax, eax
0x180007968  add     rsp, 50h
0x18000796c  pop     rdi
0x18000796d  retn
```
