# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x140005dc0`
- end: `0x140005dff`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `63`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001794`
- `0x140005b3c`
- `0x140005dc0`

## pseudocode

```c
ATL::CComModule *__fastcall ATL::CComModule::`scalar deleting destructor'(ATL::CComModule *this, unsigned int a2)
{
  char v2; // bl

  v2 = a2;
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::~CAtlModule(this, a2);
  if ( (v2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140005dc0  mov     [rsp+arg_0], rbx
0x140005dc5  push    rdi
0x140005dc6  sub     rsp, 20h
0x140005dca  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x140005dd1  mov     ebx, edx
0x140005dd3  mov     [rcx], rax
0x140005dd6  mov     rdi, rcx
0x140005dd9  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x140005dde  test    bl, 1
0x140005de1  jz      short loc_140005DF0
0x140005de3  mov     edx, 50h ; 'P'
0x140005de8  mov     rcx, rdi; Block
0x140005deb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005df0  mov     rbx, [rsp+28h+arg_0]
0x140005df5  mov     rax, rdi
0x140005df8  add     rsp, 20h
0x140005dfc  pop     rdi
0x140005dfd  retn
```
