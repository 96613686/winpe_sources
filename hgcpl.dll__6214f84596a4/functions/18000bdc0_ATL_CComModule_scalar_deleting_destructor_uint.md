# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x18000bdc0`
- end: `0x18000bdf9`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `57`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000bd88`
- `0x18000bdc0`
- `0x18000dedc`

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
0x18000bdc0  mov     [rsp+arg_0], rbx
0x18000bdc5  push    rdi
0x18000bdc6  sub     rsp, 20h
0x18000bdca  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x18000bdd1  mov     ebx, edx
0x18000bdd3  mov     [rcx], rax
0x18000bdd6  mov     rdi, rcx
0x18000bdd9  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000bdde  test    bl, 1
0x18000bde1  jz      short loc_18000BDEB
0x18000bde3  mov     rcx, rdi; lpMem
0x18000bde6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bdeb  mov     rbx, [rsp+28h+arg_0]
0x18000bdf0  mov     rax, rdi
0x18000bdf3  add     rsp, 20h
0x18000bdf7  pop     rdi
0x18000bdf8  retn
```
