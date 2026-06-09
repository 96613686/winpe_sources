# CAssociationWriteCallback::Release(void)

- ea: `0x1400185a0`
- end: `0x1400185d2`
- name: `?Release@CAssociationWriteCallback@@UEAAKXZ`
- size: `50`
- prototype: `__int64 __fastcall(CAssociationWriteCallback *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1400018d4`
- `0x1400185a0`

## pseudocode

```c
__int64 __fastcall CAssociationWriteCallback::Release(CAssociationWriteCallback *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &CAssociationWriteCallback::`vftable';
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x1400185a0  push    rbx
0x1400185a2  sub     rsp, 20h
0x1400185a6  or      ebx, 0FFFFFFFFh
0x1400185a9  lock xadd [rcx+8], ebx
0x1400185ae  sub     ebx, 1
0x1400185b1  jnz     short loc_1400185CA
0x1400185b3  test    rcx, rcx
0x1400185b6  jz      short loc_1400185CA
0x1400185b8  lea     rax, ??_7CAssociationWriteCallback@@6B@; const CAssociationWriteCallback::`vftable'
0x1400185bf  lea     edx, [rbx+28h]; unsigned __int64
0x1400185c2  mov     [rcx], rax
0x1400185c5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400185ca  mov     eax, ebx
0x1400185cc  add     rsp, 20h
0x1400185d0  pop     rbx
0x1400185d1  retn
```
