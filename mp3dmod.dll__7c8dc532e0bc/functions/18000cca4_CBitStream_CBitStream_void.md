# CBitStream::~CBitStream(void)

- ea: `0x18000cca4`
- end: `0x18000cccb`
- name: `??1CBitStream@@UEAA@XZ`
- size: `39`
- prototype: `void __fastcall(CBitStream *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000cc1c`
- `0x18000cc84`
- `0x1800104e0`

## callees

- `0x18000cca4`
- `0x18000e308`

## pseudocode

```c
void __fastcall CBitStream::~CBitStream(CBitStream *this)
{
  bool v1; // zf
  void *v2; // rcx

  v1 = *((_BYTE *)this + 56) == 0;
  *(_QWORD *)this = &CBitStream::`vftable';
  if ( !v1 )
  {
    v2 = (void *)*((_QWORD *)this + 6);
    if ( v2 )
      operator delete(v2);
  }
}

```

## disassembly

```asm
0x18000cca4  sub     rsp, 28h
0x18000cca8  cmp     byte ptr [rcx+38h], 0
0x18000ccac  lea     rax, ??_7CBitStream@@6B@; const CBitStream::`vftable'
0x18000ccb3  mov     [rcx], rax
0x18000ccb6  jz      short loc_18000CCC6
0x18000ccb8  mov     rcx, [rcx+30h]; Block
0x18000ccbc  test    rcx, rcx
0x18000ccbf  jz      short loc_18000CCC6
0x18000ccc1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ccc6  add     rsp, 28h
0x18000ccca  retn
```
