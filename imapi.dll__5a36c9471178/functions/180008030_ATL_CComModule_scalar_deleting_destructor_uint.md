# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180008030`
- end: `0x180008069`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `57`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001144`
- `0x180008030`
- `0x1800092d0`

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
0x180008030  mov     [rsp+arg_0], rbx
0x180008035  push    rdi
0x180008036  sub     rsp, 20h
0x18000803a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180008041  mov     ebx, edx
0x180008043  mov     [rcx], rax
0x180008046  mov     rdi, rcx
0x180008049  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000804e  test    bl, 1
0x180008051  jz      short loc_18000805B
0x180008053  mov     rcx, rdi; Block
0x180008056  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000805b  mov     rbx, [rsp+28h+arg_0]
0x180008060  mov     rax, rdi
0x180008063  add     rsp, 20h
0x180008067  pop     rdi
0x180008068  retn
```
