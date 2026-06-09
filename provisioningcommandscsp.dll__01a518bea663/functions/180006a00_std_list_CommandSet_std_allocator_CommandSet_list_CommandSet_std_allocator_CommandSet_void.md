# std::list<CommandSet,std::allocator<CommandSet>>::~list<CommandSet,std::allocator<CommandSet>>(void)

- ea: `0x180006a00`
- end: `0x180006a68`
- name: `??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ`
- size: `104`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007360`
- `0x180009290`
- `0x18000b1c8`
- `0x18000c144`
- `0x18000cfb5`
- `0x18000d2d6`
- `0x18000d4fb`
- `0x18000d54b`

## callees

- `0x180006a00`
- `0x18000a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006a41`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006a41`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006a61`

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
0x180006a00  mov     [rsp+arg_0], rbx
0x180006a05  mov     [rsp+arg_8], rsi
0x180006a0a  push    rdi
0x180006a0b  sub     rsp, 20h
0x180006a0f  mov     rax, [rcx]
0x180006a12  mov     rdi, rcx
0x180006a15  mov     rsi, [rax]
0x180006a18  mov     [rax], rax
0x180006a1b  mov     rax, [rcx]
0x180006a1e  mov     [rax+8], rax
0x180006a22  mov     qword ptr [rcx+8], 0
0x180006a2a  mov     rcx, [rcx]
0x180006a2d  cmp     rsi, rcx
0x180006a30  jz      short loc_180006A52
0x180006a32  mov     rbx, [rsi]
0x180006a35  lea     rcx, [rsi+10h]; this
0x180006a39  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x180006a3e  mov     rcx, rsi
0x180006a41  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006a47  mov     rcx, [rdi]
0x180006a4a  mov     rsi, rbx
0x180006a4d  cmp     rbx, rcx
0x180006a50  jnz     short loc_180006A32
0x180006a52  mov     rbx, [rsp+28h+arg_0]
0x180006a57  mov     rsi, [rsp+28h+arg_8]
0x180006a5c  add     rsp, 20h
0x180006a60  pop     rdi
0x180006a61  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
