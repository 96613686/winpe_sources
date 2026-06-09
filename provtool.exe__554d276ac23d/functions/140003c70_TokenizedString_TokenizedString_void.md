# TokenizedString::~TokenizedString(void)

- ea: `0x140003c70`
- end: `0x140003ccb`
- name: `??1TokenizedString@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(TokenizedString *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000e0dd`
- `0x14000e0ef`
- `0x14000e101`

## callees

- `0x140003c70`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140003c82`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003ca8`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003c82`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003ca8`

## pseudocode

```c
void __fastcall TokenizedString::~TokenizedString(TokenizedString *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
  }
  if ( *(_QWORD *)this )
  {
    operator delete(*(void **)this);
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x140003c70  push    rbx
0x140003c72  sub     rsp, 20h
0x140003c76  mov     rbx, rcx
0x140003c79  mov     rcx, [rcx+18h]
0x140003c7d  test    rcx, rcx
0x140003c80  jz      short loc_140003CA0
0x140003c82  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003c88  mov     qword ptr [rbx+18h], 0
0x140003c90  mov     qword ptr [rbx+20h], 0
0x140003c98  mov     qword ptr [rbx+28h], 0
0x140003ca0  mov     rcx, [rbx]
0x140003ca3  test    rcx, rcx
0x140003ca6  jz      short loc_140003CC5
0x140003ca8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003cae  mov     qword ptr [rbx], 0
0x140003cb5  mov     qword ptr [rbx+8], 0
0x140003cbd  mov     qword ptr [rbx+10h], 0
0x140003cc5  add     rsp, 20h
0x140003cc9  pop     rbx
0x140003cca  retn
```
