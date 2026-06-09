# REDIRECTION_BLOB::~REDIRECTION_BLOB(void)

- ea: `0x1800025d4`
- end: `0x180002670`
- name: `??1REDIRECTION_BLOB@@AEAA@XZ`
- size: `156`
- prototype: `void __fastcall(REDIRECTION_BLOB *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800029b0`

## callees

- `0x180001048`
- `0x1800025d4`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000262c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002635`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002650`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000262c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002635`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002650`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002669`

## pseudocode

```c
void __fastcall REDIRECTION_BLOB::~REDIRECTION_BLOB(REDIRECTION_BLOB *this)
{
  _QWORD **v2; // rsi
  _QWORD *v3; // rax
  __int64 v4; // rcx
  _QWORD *v5; // rdx
  _QWORD *v6; // rdi

  *(_QWORD *)this = &REDIRECTION_BLOB::`vftable';
  v2 = (_QWORD **)((char *)this + 144);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    v4 = *v3;
    if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
      __fastfail(3u);
    *v5 = v4;
    v6 = v3 - 14;
    *(_QWORD *)(v4 + 8) = v5;
    *v3 = 0;
    if ( v3 != (_QWORD *)112 )
    {
      STRU::~STRU((STRU *)(v6 + 7));
      STRU::~STRU((STRU *)v6);
      operator delete(v6);
    }
  }
  STRU::~STRU((REDIRECTION_BLOB *)((char *)this + 88));
  STRU::~STRU((REDIRECTION_BLOB *)((char *)this + 32));
}

```

## disassembly

```asm
0x1800025d4  mov     [rsp+arg_0], rbx
0x1800025d9  mov     [rsp+arg_8], rsi
0x1800025de  push    rdi
0x1800025df  sub     rsp, 20h
0x1800025e3  lea     rax, ??_7REDIRECTION_BLOB@@6B@; const REDIRECTION_BLOB::`vftable'
0x1800025ea  mov     rbx, rcx
0x1800025ed  mov     [rcx], rax
0x1800025f0  lea     rsi, [rcx+90h]
0x1800025f7  mov     rax, [rsi]
0x1800025fa  cmp     rax, rsi
0x1800025fd  jz      short loc_18000264C
0x1800025ff  mov     rcx, [rax]
0x180002602  cmp     [rcx+8], rax
0x180002606  jnz     short loc_180002645
0x180002608  mov     rdx, [rax+8]
0x18000260c  cmp     [rdx], rax
0x18000260f  jnz     short loc_180002645
0x180002611  mov     [rdx], rcx
0x180002614  lea     rdi, [rax-70h]
0x180002618  mov     [rcx+8], rdx
0x18000261c  mov     qword ptr [rax], 0
0x180002623  test    rdi, rdi
0x180002626  jz      short loc_1800025F7
0x180002628  lea     rcx, [rdi+38h]
0x18000262c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002632  mov     rcx, rdi
0x180002635  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000263b  mov     rcx, rdi; Block
0x18000263e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002643  jmp     short loc_1800025F7
0x180002645  mov     ecx, 3
0x18000264a  int     29h; Win8: RtlFailFast(ecx)
0x18000264c  lea     rcx, [rbx+58h]
0x180002650  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002656  lea     rcx, [rbx+20h]
0x18000265a  mov     rbx, [rsp+28h+arg_0]
0x18000265f  mov     rsi, [rsp+28h+arg_8]
0x180002664  add     rsp, 20h
0x180002668  pop     rdi
0x180002669  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
