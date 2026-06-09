# ATL::CRegObject::~CRegObject(void)

- ea: `0x180008d34`
- end: `0x180008d63`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `47`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008e20`
- `0x18000b7bc`
- `0x18000ba34`

## callees

- `0x18000213c`
- `0x180008cf0`
- `0x180009a50`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  *(_QWORD *)this = &ATL::CRegObject::`vftable';
  ATL::CRegObject::ClearReplacements(this);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CRegObject *)((char *)this + 32));
  ATL::CExpansionVector::~CExpansionVector((ATL::CRegObject *)((char *)this + 8));
}

```

## disassembly

```asm
0x180008d34  push    rbx
0x180008d36  sub     rsp, 20h
0x180008d3a  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180008d41  mov     rbx, rcx
0x180008d44  mov     [rcx], rax
0x180008d47  call    ?ClearReplacements@CRegObject@ATL@@UEAAJXZ; ATL::CRegObject::ClearReplacements(void)
0x180008d4c  lea     rcx, [rbx+20h]; this
0x180008d50  call    ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
0x180008d55  lea     rcx, [rbx+8]; this
0x180008d59  add     rsp, 20h
0x180008d5d  pop     rbx
0x180008d5e  jmp     ??1CExpansionVector@ATL@@QEAA@XZ; ATL::CExpansionVector::~CExpansionVector(void)
```
