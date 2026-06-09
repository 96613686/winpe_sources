# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x1800037b0`
- end: `0x1800037e9`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `57`
- prototype: `ATL::CComModule *__fastcall(ATL::CComModule *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001334`
- `0x1800037b0`
- `0x18000a3d0`

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
0x1800037b0  mov     [rsp+arg_0], rbx
0x1800037b5  push    rdi
0x1800037b6  sub     rsp, 20h
0x1800037ba  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x1800037c1  mov     ebx, edx
0x1800037c3  mov     [rcx], rax
0x1800037c6  mov     rdi, rcx
0x1800037c9  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x1800037ce  test    bl, 1
0x1800037d1  jz      short loc_1800037DB
0x1800037d3  mov     rcx, rdi; Block
0x1800037d6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800037db  mov     rbx, [rsp+28h+arg_0]
0x1800037e0  mov     rax, rdi
0x1800037e3  add     rsp, 20h
0x1800037e7  pop     rdi
0x1800037e8  retn
```
