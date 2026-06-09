# W3_IMAGE_RECORD::DereferenceImageRecord(void)

- ea: `0x180012150`
- end: `0x180012182`
- name: `?DereferenceImageRecord@W3_IMAGE_RECORD@@QEAAXXZ`
- size: `50`
- prototype: `void __fastcall(W3_IMAGE_RECORD *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011d90`
- `0x180012188`
- `0x180012370`

## callees

- `0x180001060`
- `0x180012150`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18001216e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001216e`

## pseudocode

```c
void __fastcall W3_IMAGE_RECORD::DereferenceImageRecord(W3_IMAGE_RECORD *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this, 0xFFFFFFFF) == 1 )
  {
    if ( this )
    {
      STRU::~STRU((W3_IMAGE_RECORD *)((char *)this + 8));
      operator delete(this);
    }
  }
}

```

## disassembly

```asm
0x180012150  push    rbx
0x180012152  sub     rsp, 20h
0x180012156  mov     rbx, rcx
0x180012159  or      eax, 0FFFFFFFFh
0x18001215c  lock xadd [rcx], eax
0x180012160  cmp     eax, 1
0x180012163  jnz     short loc_18001217C
0x180012165  test    rcx, rcx
0x180012168  jz      short loc_18001217C
0x18001216a  add     rcx, 8
0x18001216e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180012174  mov     rcx, rbx; Block
0x180012177  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001217c  add     rsp, 20h
0x180012180  pop     rbx
0x180012181  retn
```
