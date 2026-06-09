# std::_Temporary_owner<IdToken>::~_Temporary_owner<IdToken>(void)

- ea: `0x140007590`
- end: `0x1400075b9`
- name: `??1?$_Temporary_owner@VIdToken@@@std@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(IdToken **)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14002ce3a`
- `0x14002dea7`
- `0x14002ee81`

## callees

- `0x1400028ac`
- `0x140007590`
- `0x1400079a8`

## pseudocode

```c
void __fastcall std::_Temporary_owner<IdToken>::~_Temporary_owner<IdToken>(IdToken **a1)
{
  IdToken *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    IdToken::~IdToken(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x140007590  push    rbx
0x140007592  sub     rsp, 20h
0x140007596  mov     rbx, [rcx]
0x140007599  test    rbx, rbx
0x14000759c  jz      short loc_1400075B3
0x14000759e  mov     rcx, rbx; this
0x1400075a1  call    ??1IdToken@@QEAA@XZ; IdToken::~IdToken(void)
0x1400075a6  mov     edx, 50h ; 'P'
0x1400075ab  mov     rcx, rbx; Block
0x1400075ae  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x1400075b3  add     rsp, 20h
0x1400075b7  pop     rbx
0x1400075b8  retn
```
