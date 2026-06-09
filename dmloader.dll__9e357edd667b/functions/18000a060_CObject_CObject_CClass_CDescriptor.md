# CObject::CObject(CClass *,CDescriptor *)

- ea: `0x18000a060`
- end: `0x18000a0de`
- name: `??0CObject@@QEAA@PEAVCClass@@PEAVCDescriptor@@@Z`
- size: `126`
- prototype: `CObject *(CObject *__hidden this, struct CClass *, struct CDescriptor *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a958`
- `0x18000ad04`
- `0x18000bbc4`

## callees

- `0x180009fdc`
- `0x18000a060`
- `0x18000a484`

## pseudocode

```c
CObject *__fastcall CObject::CObject(CObject *this, struct CClass *a2, struct CDescriptor *a3)
{
  *(_QWORD *)this = 0;
  CDescriptor::CDescriptor((CObject *)((char *)this + 8));
  *((_DWORD *)this + 48) = 0;
  *((_QWORD *)this + 26) = a2;
  *((_QWORD *)this + 23) = 0;
  CDescriptor::Copy((CObject *)((char *)this + 8), a3);
  *((_DWORD *)this + 4) &= ~0x200u;
  if ( (*((_BYTE *)this + 16) & 2) == 0 )
  {
    *(_OWORD *)((char *)this + 36) = *(_OWORD *)((char *)a2 + 36);
    *((_DWORD *)this + 4) |= *((_DWORD *)a2 + 4) & 2;
  }
  *((_QWORD *)this + 25) = 0;
  return this;
}

```

## disassembly

```asm
0x18000a060  push    rbx
0x18000a062  push    rbp
0x18000a063  push    rsi
0x18000a064  push    rdi
0x18000a065  sub     rsp, 28h
0x18000a069  mov     rsi, rcx
0x18000a06c  mov     qword ptr [rcx], 0
0x18000a073  add     rcx, 8; this
0x18000a077  mov     rdi, r8
0x18000a07a  mov     rbp, rdx
0x18000a07d  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x18000a082  mov     rdx, rdi; struct CDescriptor *
0x18000a085  mov     dword ptr [rsi+0C0h], 0
0x18000a08f  lea     rcx, [rsi+8]; this
0x18000a093  mov     [rsi+0D0h], rbp
0x18000a09a  mov     qword ptr [rsi+0B8h], 0
0x18000a0a5  call    ?Copy@CDescriptor@@QEAAXPEAV1@@Z; CDescriptor::Copy(CDescriptor *)
0x18000a0aa  btr     dword ptr [rsi+10h], 9
0x18000a0af  test    byte ptr [rsi+10h], 2
0x18000a0b3  jnz     short loc_18000A0C7
0x18000a0b5  movups  xmm0, xmmword ptr [rbp+24h]
0x18000a0b9  movdqu  xmmword ptr [rsi+24h], xmm0
0x18000a0be  mov     eax, [rbp+10h]
0x18000a0c1  and     eax, 2
0x18000a0c4  or      [rsi+10h], eax
0x18000a0c7  mov     qword ptr [rsi+0C8h], 0
0x18000a0d2  mov     rax, rsi
0x18000a0d5  add     rsp, 28h
0x18000a0d9  pop     rdi
0x18000a0da  pop     rsi
0x18000a0db  pop     rbp
0x18000a0dc  pop     rbx
0x18000a0dd  retn
```
