# std::list<CommandSet,std::allocator<CommandSet>>::~list<CommandSet,std::allocator<CommandSet>>(void)

- ea: `0x140003560`
- end: `0x1400035c8`
- name: `??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ`
- size: `104`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000693c`
- `0x140008b38`
- `0x140009ecc`
- `0x14000a9a9`
- `0x14000ad45`
- `0x14000ada7`

## callees

- `0x140003560`
- `0x140007ce0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400035a1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400035a1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400035c1`

## pseudocode

```c
void __fastcall std::list<CommandSet>::~list<CommandSet>(_QWORD *a1)
{
  _QWORD *v2; // rsi
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  v2 = *(_QWORD **)*a1;
  *(_QWORD *)*a1 = *a1;
  *(_QWORD *)(*a1 + 8LL) = *a1;
  a1[1] = 0;
  v3 = (_QWORD *)*a1;
  if ( v2 != v3 )
  {
    do
    {
      v4 = (_QWORD *)*v2;
      CommandSet::~CommandSet((CommandSet *)(v2 + 2));
      operator delete(v2);
      v3 = (_QWORD *)*a1;
      v2 = v4;
    }
    while ( v4 != (_QWORD *)*a1 );
  }
  operator delete(v3);
}

```

## disassembly

```asm
0x140003560  mov     [rsp+arg_0], rbx
0x140003565  mov     [rsp+arg_8], rsi
0x14000356a  push    rdi
0x14000356b  sub     rsp, 20h
0x14000356f  mov     rax, [rcx]
0x140003572  mov     rdi, rcx
0x140003575  mov     rsi, [rax]
0x140003578  mov     [rax], rax
0x14000357b  mov     rax, [rcx]
0x14000357e  mov     [rax+8], rax
0x140003582  mov     qword ptr [rcx+8], 0
0x14000358a  mov     rcx, [rcx]
0x14000358d  cmp     rsi, rcx
0x140003590  jz      short loc_1400035B2
0x140003592  mov     rbx, [rsi]
0x140003595  lea     rcx, [rsi+10h]; this
0x140003599  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x14000359e  mov     rcx, rsi
0x1400035a1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400035a7  mov     rcx, [rdi]
0x1400035aa  mov     rsi, rbx
0x1400035ad  cmp     rbx, rcx
0x1400035b0  jnz     short loc_140003592
0x1400035b2  mov     rbx, [rsp+28h+arg_0]
0x1400035b7  mov     rsi, [rsp+28h+arg_8]
0x1400035bc  add     rsp, 20h
0x1400035c0  pop     rdi
0x1400035c1  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
