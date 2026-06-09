# CAccStore::~CAccStore(void)

- ea: `0x18000d5a4`
- end: `0x18000d656`
- name: `??1CAccStore@@QEAA@XZ`
- size: `178`
- prototype: `void __fastcall(CAccStore *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000f3f0`
- `0x18000fd50`
- `0x180011aa0`
- `0x180011d70`
- `0x180011ef0`

## callees

- `0x18000d5a4`
- `0x18000d7b4`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000d633`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d633`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d64f`
- `KERNEL32!CloseHandle` at `0x18000d5f9`
- `KERNEL32!CloseHandle` at `0x18000d5f9`

## pseudocode

```c
void __fastcall CAccStore::~CAccStore(CAccStore *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  _QWORD **v5; // rax
  _QWORD *v6; // rdx
  _QWORD *v7; // rcx
  _QWORD *v8; // rbx

  CAccStore::EraseDeadDocuments(this);
  v2 = *((_QWORD *)this + 7);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 8);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 32LL))(v3);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 16LL))(*((_QWORD *)this + 8));
  }
  v4 = (void *)*((_QWORD *)this + 6);
  if ( v4 )
    CloseHandle(v4);
  m_pTheStore = 0;
  v5 = (_QWORD **)*((_QWORD *)this + 4);
  v6 = *v5;
  *v5 = v5;
  *(_QWORD *)(*((_QWORD *)this + 4) + 8LL) = *((_QWORD *)this + 4);
  *((_QWORD *)this + 5) = 0;
  v7 = (_QWORD *)*((_QWORD *)this + 4);
  if ( v6 != v7 )
  {
    do
    {
      v8 = (_QWORD *)*v6;
      operator delete(v6);
      v6 = v8;
      v7 = (_QWORD *)*((_QWORD *)this + 4);
    }
    while ( v8 != v7 );
  }
  operator delete(v7);
}

```

## disassembly

```asm
0x18000d5a4  mov     [rsp+arg_0], rbx
0x18000d5a9  push    rdi
0x18000d5aa  sub     rsp, 20h
0x18000d5ae  mov     rdi, rcx
0x18000d5b1  call    ?EraseDeadDocuments@CAccStore@@AEAAXXZ; CAccStore::EraseDeadDocuments(void)
0x18000d5b6  mov     rcx, [rdi+38h]
0x18000d5ba  test    rcx, rcx
0x18000d5bd  jz      short loc_18000D5CB
0x18000d5bf  mov     rax, [rcx]
0x18000d5c2  mov     rax, [rax+10h]
0x18000d5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5cb  mov     rcx, [rdi+40h]
0x18000d5cf  test    rcx, rcx
0x18000d5d2  jz      short loc_18000D5F0
0x18000d5d4  mov     rax, [rcx]
0x18000d5d7  mov     rax, [rax+20h]
0x18000d5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5e0  mov     rcx, [rdi+40h]
0x18000d5e4  mov     rax, [rcx]
0x18000d5e7  mov     rax, [rax+10h]
0x18000d5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5f0  mov     rcx, [rdi+30h]; hObject
0x18000d5f4  test    rcx, rcx
0x18000d5f7  jz      short loc_18000D5FF
0x18000d5f9  call    cs:__imp_CloseHandle
0x18000d5ff  mov     cs:?m_pTheStore@@3PEAVCAccStore@@EA, 0; CAccStore * m_pTheStore
0x18000d60a  mov     rax, [rdi+20h]
0x18000d60e  mov     rdx, [rax]
0x18000d611  mov     [rax], rax
0x18000d614  mov     rax, [rdi+20h]
0x18000d618  mov     [rax+8], rax
0x18000d61c  mov     qword ptr [rdi+28h], 0
0x18000d624  mov     rcx, [rdi+20h]
0x18000d628  cmp     rdx, rcx
0x18000d62b  jz      short loc_18000D645
0x18000d62d  mov     rbx, [rdx]
0x18000d630  mov     rcx, rdx
0x18000d633  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d639  mov     rdx, rbx
0x18000d63c  mov     rcx, [rdi+20h]
0x18000d640  cmp     rbx, rcx
0x18000d643  jnz     short loc_18000D62D
0x18000d645  mov     rbx, [rsp+28h+arg_0]
0x18000d64a  add     rsp, 20h
0x18000d64e  pop     rdi
0x18000d64f  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
