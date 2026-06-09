# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180008b10`
- end: `0x180008b4a`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `58`
- prototype: `ATL::CComModule *__fastcall(ATL::CComModule *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180008b10`
- `0x18000bcdc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008b36`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008b36`

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
0x180008b10  mov     [rsp+arg_0], rbx
0x180008b15  push    rdi
0x180008b16  sub     rsp, 20h
0x180008b1a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180008b21  mov     ebx, edx
0x180008b23  mov     [rcx], rax
0x180008b26  mov     rdi, rcx
0x180008b29  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x180008b2e  test    bl, 1
0x180008b31  jz      short loc_180008B3C
0x180008b33  mov     rcx, rdi
0x180008b36  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008b3c  mov     rbx, [rsp+28h+arg_0]
0x180008b41  mov     rax, rdi
0x180008b44  add     rsp, 20h
0x180008b48  pop     rdi
0x180008b49  retn
```
