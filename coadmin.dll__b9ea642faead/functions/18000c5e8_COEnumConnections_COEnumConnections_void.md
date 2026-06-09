# COEnumConnections::~COEnumConnections(void)

- ea: `0x18000c5e8`
- end: `0x18000c646`
- name: `??1COEnumConnections@@QEAA@XZ`
- size: `94`
- prototype: `void __fastcall(COEnumConnections *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000c9a0`
- `0x18000ca70`
- `0x18000d570`

## callees

- `0x1800010b0`
- `0x18000c5e8`
- `0x180010010`

## pseudocode

```c
void __fastcall COEnumConnections::~COEnumConnections(COEnumConnections *this)
{
  bool v1; // zf
  unsigned int i; // edi
  __int64 v4; // rcx

  v1 = *((_QWORD *)this + 4) == 0;
  *(_QWORD *)this = &COEnumConnections::`vftable';
  if ( !v1 )
  {
    for ( i = 0; i < *((_DWORD *)this + 7); ++i )
    {
      v4 = *(_QWORD *)(*((_QWORD *)this + 4) + 16LL * i);
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    operator delete[](*((void **)this + 4));
  }
}

```

## disassembly

```asm
0x18000c5e8  mov     [rsp+arg_0], rbx
0x18000c5ed  push    rdi
0x18000c5ee  sub     rsp, 20h
0x18000c5f2  cmp     qword ptr [rcx+20h], 0
0x18000c5f7  lea     rax, ??_7COEnumConnections@@6B@; const COEnumConnections::`vftable'
0x18000c5fe  mov     [rcx], rax
0x18000c601  mov     rbx, rcx
0x18000c604  jz      short loc_18000C63B
0x18000c606  xor     edi, edi
0x18000c608  cmp     [rcx+1Ch], edi
0x18000c60b  jbe     short loc_18000C632
0x18000c60d  mov     rax, [rbx+20h]
0x18000c611  mov     ecx, edi
0x18000c613  add     rcx, rcx
0x18000c616  mov     rcx, [rax+rcx*8]
0x18000c61a  test    rcx, rcx
0x18000c61d  jz      short loc_18000C62B
0x18000c61f  mov     rax, [rcx]
0x18000c622  mov     rax, [rax+10h]
0x18000c626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c62b  inc     edi
0x18000c62d  cmp     edi, [rbx+1Ch]
0x18000c630  jb      short loc_18000C60D
0x18000c632  mov     rcx, [rbx+20h]; Block
0x18000c636  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000c63b  mov     rbx, [rsp+28h+arg_0]
0x18000c640  add     rsp, 20h
0x18000c644  pop     rdi
0x18000c645  retn
```
