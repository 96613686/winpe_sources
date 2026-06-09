# LOGGING::~LOGGING(void)

- ea: `0x1800027e4`
- end: `0x18000283b`
- name: `??1LOGGING@@AEAA@XZ`
- size: `87`
- prototype: `void __fastcall(LOGGING *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e10`

## callees

- `0x1800027e4`
- `0x180004010`

## import_xrefs

- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180002834`

## pseudocode

```c
void __fastcall LOGGING::~LOGGING(LOGGING *this)
{
  __int64 v2; // rcx

  *((_DWORD *)this + 2) = 1734831980;
  *(_QWORD *)this = &LOGGING::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 32LL))(v2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
  MULTISZA::~MULTISZA((LOGGING *)((char *)this + 24));
}

```

## disassembly

```asm
0x1800027e4  push    rbx
0x1800027e6  sub     rsp, 20h
0x1800027ea  lea     rax, ??_7LOGGING@@6B@; const LOGGING::`vftable'
0x1800027f1  mov     dword ptr [rcx+8], 67676F6Ch
0x1800027f8  mov     [rcx], rax
0x1800027fb  mov     rbx, rcx
0x1800027fe  mov     rcx, [rcx+10h]
0x180002802  test    rcx, rcx
0x180002805  jz      short loc_18000282B
0x180002807  mov     rax, [rcx]
0x18000280a  mov     rax, [rax+20h]
0x18000280e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002813  mov     rcx, [rbx+10h]
0x180002817  mov     rax, [rcx]
0x18000281a  mov     rax, [rax+10h]
0x18000281e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002823  mov     qword ptr [rbx+10h], 0
0x18000282b  lea     rcx, [rbx+18h]
0x18000282f  add     rsp, 20h
0x180002833  pop     rbx
0x180002834  jmp     cs:__imp_??1MULTISZA@@QEAA@XZ; MULTISZA::~MULTISZA(void)
```
