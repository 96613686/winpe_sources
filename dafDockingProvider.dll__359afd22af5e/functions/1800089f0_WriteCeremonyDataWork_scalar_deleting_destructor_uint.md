# WriteCeremonyDataWork::`scalar deleting destructor'(uint)

- ea: `0x1800089f0`
- end: `0x180008a4c`
- name: `??_GWriteCeremonyDataWork@@UEAAPEAXI@Z`
- size: `92`
- prototype: `WriteCeremonyDataWork *__fastcall(WriteCeremonyDataWork *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800014d0`
- `0x1800089f0`
- `0x18001f010`

## pseudocode

```c
WriteCeremonyDataWork *__fastcall WriteCeremonyDataWork::`scalar deleting destructor'(
        WriteCeremonyDataWork *this,
        char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)this = &WriteCeremonyDataWork::`vftable';
  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 1) = 0;
  }
  *(_QWORD *)this = &Work::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800089f0  mov     [rsp+arg_0], rbx
0x1800089f5  push    rdi
0x1800089f6  sub     rsp, 20h
0x1800089fa  mov     edi, edx
0x1800089fc  mov     rbx, rcx
0x1800089ff  lea     rax, ??_7WriteCeremonyDataWork@@6B@; const WriteCeremonyDataWork::`vftable'
0x180008a06  mov     [rcx], rax
0x180008a09  mov     rcx, [rcx+8]
0x180008a0d  test    rcx, rcx
0x180008a10  jz      short loc_180008A26
0x180008a12  mov     rax, [rcx]
0x180008a15  mov     rax, [rax+10h]
0x180008a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a1e  mov     qword ptr [rbx+8], 0
0x180008a26  lea     rax, ??_7Work@@6B@; const Work::`vftable'
0x180008a2d  mov     [rbx], rax
0x180008a30  test    dil, 1
0x180008a34  jz      short loc_180008A3E
0x180008a36  mov     rcx, rbx; Block
0x180008a39  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008a3e  mov     rax, rbx
0x180008a41  mov     rbx, [rsp+28h+arg_0]
0x180008a46  add     rsp, 20h
0x180008a4a  pop     rdi
0x180008a4b  retn
```
