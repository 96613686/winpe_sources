# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180008de0`
- end: `0x180008e19`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `57`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001240`
- `0x180008de0`
- `0x18000b644`

## pseudocode

```c
ATL::CComModule *__fastcall ATL::CComModule::`scalar deleting destructor'(ATL::CComModule *this, char a2)
{
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::Term(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008de0  mov     [rsp+arg_0], rbx
0x180008de5  push    rdi
0x180008de6  sub     rsp, 20h
0x180008dea  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180008df1  mov     ebx, edx
0x180008df3  mov     [rcx], rax
0x180008df6  mov     rdi, rcx
0x180008df9  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x180008dfe  test    bl, 1
0x180008e01  jz      short loc_180008E0B
0x180008e03  mov     rcx, rdi; Block
0x180008e06  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008e0b  mov     rbx, [rsp+28h+arg_0]
0x180008e10  mov     rax, rdi
0x180008e13  add     rsp, 20h
0x180008e17  pop     rdi
0x180008e18  retn
```
