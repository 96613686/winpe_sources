# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x14000c3c0`
- end: `0x14000c3fe`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001c54`
- `0x14000c3c0`
- `0x14000e130`

## pseudocode

```c
ATL::CComModule *__fastcall ATL::CComModule::`scalar deleting destructor'(ATL::CComModule *this, unsigned int a2)
{
  char v2; // bl

  v2 = a2;
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::Term(this, a2);
  if ( (v2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000c3c0  mov     [rsp+arg_0], rbx
0x14000c3c5  push    rdi
0x14000c3c6  sub     rsp, 20h
0x14000c3ca  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x14000c3d1  mov     ebx, edx
0x14000c3d3  mov     [rcx], rax
0x14000c3d6  mov     rdi, rcx
0x14000c3d9  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x14000c3de  test    bl, 1
0x14000c3e1  jz      short loc_14000C3F0
0x14000c3e3  mov     edx, 50h ; 'P'
0x14000c3e8  mov     rcx, rdi; Block
0x14000c3eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c3f0  mov     rbx, [rsp+28h+arg_0]
0x14000c3f5  mov     rax, rdi
0x14000c3f8  add     rsp, 20h
0x14000c3fc  pop     rdi
0x14000c3fd  retn
```
