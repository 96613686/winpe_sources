# CArticulation::~CArticulation(void)

- ea: `0x180009790`
- end: `0x18000980b`
- name: `??1CArticulation@@QEAA@XZ`
- size: `123`
- prototype: `void __fastcall(CArticulation *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000dcc0`
- `0x18000df64`
- `0x180010798`
- `0x180010840`

## callees

- `0x1800012c4`
- `0x180009790`
- `0x180009814`

## pseudocode

```c
void __fastcall CArticulation::~CArticulation(CArticulation *this)
{
  void *v2; // rcx
  _QWORD *v3; // rdi
  void *v4; // rcx
  void *v5; // rcx

  if ( *((_DWORD *)this + 2) )
    CArticulation::Cleanup(this);
  v2 = (void *)*((_QWORD *)this + 7);
  if ( !v2 )
    goto LABEL_5;
  while ( 1 )
  {
    operator delete(v2);
LABEL_5:
    v3 = (_QWORD *)*((_QWORD *)this + 4);
    if ( !v3 )
      break;
    *((_QWORD *)this + 4) = *v3;
    *v3 = 0;
    v4 = (void *)v3[1];
    if ( v4 )
    {
      operator delete(v4);
      v3[1] = 0;
    }
    v2 = v3;
  }
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
    operator delete(v5);
}

```

## disassembly

```asm
0x180009790  mov     [rsp+arg_0], rbx
0x180009795  push    rdi
0x180009796  sub     rsp, 20h
0x18000979a  cmp     dword ptr [rcx+8], 0
0x18000979e  mov     rbx, rcx
0x1800097a1  jz      short loc_1800097A8
0x1800097a3  call    ?Cleanup@CArticulation@@AEAAXXZ; CArticulation::Cleanup(void)
0x1800097a8  mov     rcx, [rbx+38h]; void *
0x1800097ac  test    rcx, rcx
0x1800097af  jz      short loc_1800097BB
0x1800097b1  mov     edx, 1; unsigned __int64
0x1800097b6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800097bb  mov     rdi, [rbx+20h]
0x1800097bf  test    rdi, rdi
0x1800097c2  jz      short loc_1800097F2
0x1800097c4  mov     rax, [rdi]
0x1800097c7  mov     [rbx+20h], rax
0x1800097cb  mov     qword ptr [rdi], 0
0x1800097d2  mov     rcx, [rdi+8]; void *
0x1800097d6  test    rcx, rcx
0x1800097d9  jz      short loc_1800097E8
0x1800097db  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800097e0  mov     qword ptr [rdi+8], 0
0x1800097e8  mov     edx, 18h
0x1800097ed  mov     rcx, rdi
0x1800097f0  jmp     short loc_1800097B6
0x1800097f2  mov     rcx, [rbx+18h]; void *
0x1800097f6  test    rcx, rcx
0x1800097f9  jz      short loc_180009800
0x1800097fb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009800  mov     rbx, [rsp+28h+arg_0]
0x180009805  add     rsp, 20h
0x180009809  pop     rdi
0x18000980a  retn
```
