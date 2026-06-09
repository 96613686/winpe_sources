# CList<tagPORTDEST *>::~CList<tagPORTDEST *>(void)

- ea: `0x18000a56c`
- end: `0x18000a5b1`
- name: `??1?$CList@PEAUtagPORTDEST@@@@UEAA@XZ`
- size: `69`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000a5b8`
- `0x18000a6d0`
- `0x1800125bc`
- `0x1800127d0`
- `0x180013ed4`
- `0x18001d7c8`
- `0x180021c1a`

## callees

- `0x1800012c4`
- `0x18000a56c`

## pseudocode

```c
void __fastcall CList<tagPORTDEST *>::~CList<tagPORTDEST *>(_QWORD *a1)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rbx

  *a1 = &CList<IDirectMusicPort *>::`vftable';
  v2 = (_QWORD *)a1[1];
  if ( v2 )
  {
    do
    {
      v3 = (_QWORD *)v2[1];
      operator delete(v2);
      a1[1] = v3;
      v2 = v3;
    }
    while ( v3 );
  }
}

```

## disassembly

```asm
0x18000a56c  mov     [rsp+arg_0], rbx
0x18000a571  push    rdi
0x18000a572  sub     rsp, 20h
0x18000a576  lea     rax, ??_7?$CList@PEAUIDirectMusicPort@@@@6B@; const CList<IDirectMusicPort *>::`vftable'
0x18000a57d  mov     rdi, rcx
0x18000a580  mov     [rcx], rax
0x18000a583  mov     rcx, [rcx+8]; void *
0x18000a587  test    rcx, rcx
0x18000a58a  jz      short loc_18000A5A6
0x18000a58c  mov     rbx, [rcx+8]
0x18000a590  mov     edx, 18h; unsigned __int64
0x18000a595  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a59a  mov     [rdi+8], rbx
0x18000a59e  mov     rcx, rbx
0x18000a5a1  test    rbx, rbx
0x18000a5a4  jnz     short loc_18000A58C
0x18000a5a6  mov     rbx, [rsp+28h+arg_0]
0x18000a5ab  add     rsp, 20h
0x18000a5af  pop     rdi
0x18000a5b0  retn
```
