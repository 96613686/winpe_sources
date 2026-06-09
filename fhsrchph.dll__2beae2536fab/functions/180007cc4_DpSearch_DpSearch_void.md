# DpSearch::~DpSearch(void)

- ea: `0x180007cc4`
- end: `0x180007d51`
- name: `??1DpSearch@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(void **this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004020`
- `0x180004a00`
- `0x18000b01e`
- `0x18000b125`

## callees

- `0x180007cc4`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007cd8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007cd8`

## pseudocode

```c
void __fastcall DpSearch::~DpSearch(void **this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  if ( (unsigned __int64)this[7] >= 8 )
    operator delete(this[4]);
  this[7] = (void *)7;
  this[6] = 0;
  *((_WORD *)this + 16) = 0;
  v2 = this[3];
  if ( v2 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = this[2];
  if ( v3 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = this[1];
  if ( v4 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( *this )
    (*(void (__fastcall **)(void *))(*(_QWORD *)*this + 16LL))(*this);
}

```

## disassembly

```asm
0x180007cc4  push    rbx
0x180007cc6  sub     rsp, 20h
0x180007cca  mov     rbx, rcx
0x180007ccd  cmp     qword ptr [rcx+38h], 8
0x180007cd2  jb      short loc_180007CDE
0x180007cd4  mov     rcx, [rcx+20h]
0x180007cd8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007cde  mov     qword ptr [rbx+38h], 7
0x180007ce6  mov     qword ptr [rbx+30h], 0
0x180007cee  xor     eax, eax
0x180007cf0  mov     [rbx+20h], ax
0x180007cf4  mov     rcx, [rbx+18h]
0x180007cf8  test    rcx, rcx
0x180007cfb  jz      short loc_180007D0A
0x180007cfd  mov     rax, [rcx]
0x180007d00  mov     rax, [rax+10h]
0x180007d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d09  nop
0x180007d0a  mov     rcx, [rbx+10h]
0x180007d0e  test    rcx, rcx
0x180007d11  jz      short loc_180007D20
0x180007d13  mov     rax, [rcx]
0x180007d16  mov     rax, [rax+10h]
0x180007d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d1f  nop
0x180007d20  mov     rcx, [rbx+8]
0x180007d24  test    rcx, rcx
0x180007d27  jz      short loc_180007D36
0x180007d29  mov     rax, [rcx]
0x180007d2c  mov     rax, [rax+10h]
0x180007d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d35  nop
0x180007d36  mov     rcx, [rbx]
0x180007d39  test    rcx, rcx
0x180007d3c  jz      short loc_180007D4B
0x180007d3e  mov     rax, [rcx]
0x180007d41  mov     rax, [rax+10h]
0x180007d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d4a  nop
0x180007d4b  add     rsp, 20h
0x180007d4f  pop     rbx
0x180007d50  retn
```
