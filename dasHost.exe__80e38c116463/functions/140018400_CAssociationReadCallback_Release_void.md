# CAssociationReadCallback::Release(void)

- ea: `0x140018400`
- end: `0x140018432`
- name: `?Release@CAssociationReadCallback@@UEAAKXZ`
- size: `50`
- prototype: `__int64 __fastcall(CAssociationReadCallback *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1400018d4`
- `0x140018400`

## pseudocode

```c
__int64 __fastcall CAssociationReadCallback::Release(CAssociationReadCallback *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &CAssociationReadCallback::`vftable';
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x140018400  push    rbx
0x140018402  sub     rsp, 20h
0x140018406  or      ebx, 0FFFFFFFFh
0x140018409  lock xadd [rcx+8], ebx
0x14001840e  sub     ebx, 1
0x140018411  jnz     short loc_14001842A
0x140018413  test    rcx, rcx
0x140018416  jz      short loc_14001842A
0x140018418  lea     rax, ??_7CAssociationReadCallback@@6B@; const CAssociationReadCallback::`vftable'
0x14001841f  lea     edx, [rbx+28h]; unsigned __int64
0x140018422  mov     [rcx], rax
0x140018425  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001842a  mov     eax, ebx
0x14001842c  add     rsp, 20h
0x140018430  pop     rbx
0x140018431  retn
```
