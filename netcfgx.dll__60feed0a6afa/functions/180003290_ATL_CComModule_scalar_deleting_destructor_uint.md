# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180003290`
- end: `0x1800032ce`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001fec`
- `0x180003290`
- `0x180005c4c`

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
0x180003290  mov     [rsp+arg_0], rbx
0x180003295  push    rdi
0x180003296  sub     rsp, 20h
0x18000329a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x1800032a1  mov     ebx, edx
0x1800032a3  mov     [rcx], rax
0x1800032a6  mov     rdi, rcx
0x1800032a9  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x1800032ae  test    bl, 1
0x1800032b1  jz      short loc_1800032C0
0x1800032b3  mov     edx, 50h ; 'P'; unsigned __int64
0x1800032b8  mov     rcx, rdi; void *
0x1800032bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800032c0  mov     rbx, [rsp+28h+arg_0]
0x1800032c5  mov     rax, rdi
0x1800032c8  add     rsp, 20h
0x1800032cc  pop     rdi
0x1800032cd  retn
```
