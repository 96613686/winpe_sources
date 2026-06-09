# CAccStore::EraseDeadDocuments(void)

- ea: `0x18000d7b4`
- end: `0x18000d839`
- name: `?EraseDeadDocuments@CAccStore@@AEAAXXZ`
- size: `133`
- prototype: `void __fastcall(CAccStore *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d5a4`
- `0x18000d840`
- `0x18000dba0`

## callees

- `0x18000d7b4`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000d81d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d81d`

## pseudocode

```c
void __fastcall CAccStore::EraseDeadDocuments(CAccStore *this)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rbx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = (_QWORD *)**((_QWORD **)this + 4);
  while ( v2 != *((_QWORD **)this + 4) )
  {
    v4 = 0;
    v3 = v2;
    v2 = (_QWORD *)*v2;
    if ( (*(unsigned int (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v3[2] + 8LL) + 48LL))(
           *(_QWORD *)(v3[2] + 8LL),
           &v4) )
    {
      if ( v3 != *((_QWORD **)this + 4) )
      {
        *(_QWORD *)v3[1] = *v3;
        *(_QWORD *)(*v3 + 8LL) = v3[1];
        operator delete(v3);
        --*((_QWORD *)this + 5);
      }
    }
  }
}

```

## disassembly

```asm
0x18000d7b4  mov     [rsp+arg_8], rbx
0x18000d7b9  mov     [rsp+arg_10], rsi
0x18000d7be  push    rdi
0x18000d7bf  sub     rsp, 20h
0x18000d7c3  mov     rdi, [rcx+20h]
0x18000d7c7  mov     rsi, rcx
0x18000d7ca  mov     rdi, [rdi]
0x18000d7cd  cmp     rdi, [rsi+20h]
0x18000d7d1  jz      short loc_18000D829
0x18000d7d3  mov     [rsp+28h+arg_0], 0
0x18000d7dc  lea     rdx, [rsp+28h+arg_0]
0x18000d7e1  mov     rbx, rdi
0x18000d7e4  mov     rdi, [rdi]
0x18000d7e7  mov     rax, [rbx+10h]
0x18000d7eb  mov     rcx, [rax+8]
0x18000d7ef  mov     rax, [rcx]
0x18000d7f2  mov     rax, [rax+30h]
0x18000d7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7fb  test    eax, eax
0x18000d7fd  jz      short loc_18000D7CD
0x18000d7ff  cmp     rbx, [rsi+20h]
0x18000d803  jz      short loc_18000D7CD
0x18000d805  mov     rcx, [rbx+8]
0x18000d809  mov     rax, [rbx]
0x18000d80c  mov     [rcx], rax
0x18000d80f  mov     rcx, [rbx]
0x18000d812  mov     rax, [rbx+8]
0x18000d816  mov     [rcx+8], rax
0x18000d81a  mov     rcx, rbx
0x18000d81d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d823  dec     qword ptr [rsi+28h]
0x18000d827  jmp     short loc_18000D7CD
0x18000d829  mov     rbx, [rsp+28h+arg_8]
0x18000d82e  mov     rsi, [rsp+28h+arg_10]
0x18000d833  add     rsp, 20h
0x18000d837  pop     rdi
0x18000d838  retn
```
