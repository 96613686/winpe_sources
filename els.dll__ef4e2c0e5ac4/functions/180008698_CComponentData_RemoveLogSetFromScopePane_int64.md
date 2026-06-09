# CComponentData::_RemoveLogSetFromScopePane(__int64)

- ea: `0x180008698`
- end: `0x180008721`
- name: `?_RemoveLogSetFromScopePane@CComponentData@@AEAAX_J@Z`
- size: `137`
- prototype: `void __fastcall(CComponentData *__hidden this, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800065d0`
- `0x180021820`

## callees

- `0x180004f68`
- `0x180008698`
- `0x180024010`

## pseudocode

```c
void __fastcall CComponentData::_RemoveLogSetFromScopePane(CComponentData *this, __int64 a2)
{
  _QWORD *v2; // rdi
  CDLink *v5; // rbx
  _QWORD *v6; // r14

  v2 = (_QWORD *)*((_QWORD *)this + 10);
  while ( v2 )
  {
    v5 = (CDLink *)v2;
    v6 = v2 + 1;
    v2 = (_QWORD *)v2[1];
    if ( a2 == *((_QWORD *)v5 + 6) )
    {
      if ( (*((_BYTE *)this + 56) & 0x10) != 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 145) + 32LL))(
          *((_QWORD *)this + 145),
          *((_QWORD *)v5 + 5),
          1);
      if ( *((_QWORD *)this + 10) )
      {
        if ( *((CDLink **)this + 10) == v5 )
          *((_QWORD *)this + 10) = *v6;
        CDLink::UnLink(v5);
      }
      (**(void (__fastcall ***)(CDLink *, __int64))v5)(v5, 1);
    }
  }
}

```

## disassembly

```asm
0x180008698  push    rbx
0x18000869a  push    rbp
0x18000869b  push    rsi
0x18000869c  push    rdi
0x18000869d  push    r14
0x18000869f  sub     rsp, 20h
0x1800086a3  mov     rdi, [rcx+50h]
0x1800086a7  mov     rbp, rdx
0x1800086aa  mov     rsi, rcx
0x1800086ad  jmp     short loc_180008711
0x1800086af  mov     rbx, rdi
0x1800086b2  lea     r14, [rdi+8]
0x1800086b6  mov     rdi, [r14]
0x1800086b9  cmp     rbp, [rbx+30h]
0x1800086bd  jnz     short loc_180008711
0x1800086bf  test    byte ptr [rsi+38h], 10h
0x1800086c3  jz      short loc_1800086E2
0x1800086c5  mov     rcx, [rsi+488h]
0x1800086cc  mov     r8d, 1
0x1800086d2  mov     rdx, [rbx+28h]
0x1800086d6  mov     rax, [rcx]
0x1800086d9  mov     rax, [rax+20h]
0x1800086dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086e2  cmp     qword ptr [rsi+50h], 0
0x1800086e7  jz      short loc_1800086FE
0x1800086e9  cmp     [rsi+50h], rbx
0x1800086ed  jnz     short loc_1800086F6
0x1800086ef  mov     rax, [r14]
0x1800086f2  mov     [rsi+50h], rax
0x1800086f6  mov     rcx, rbx; this
0x1800086f9  call    ?UnLink@CDLink@@QEAAXXZ; CDLink::UnLink(void)
0x1800086fe  mov     rax, [rbx]
0x180008701  mov     edx, 1
0x180008706  mov     rcx, rbx
0x180008709  mov     rax, [rax]
0x18000870c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008711  test    rdi, rdi
0x180008714  jnz     short loc_1800086AF
0x180008716  add     rsp, 20h
0x18000871a  pop     r14
0x18000871c  pop     rdi
0x18000871d  pop     rsi
0x18000871e  pop     rbp
0x18000871f  pop     rbx
0x180008720  retn
```
