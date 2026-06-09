# CXMLTag::`vector deleting destructor'(uint)

- ea: `0x18000e900`
- end: `0x18000e934`
- name: `??_ECXMLTag@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CXMLTag *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x18000d200`
- `0x18000e900`
- `0x180014544`

## pseudocode

```c
CXMLTag *__fastcall CXMLTag::`vector deleting destructor'(CXMLTag *this, char a2)
{
  CXMLTag::~CXMLTag(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000e900  mov     [rsp+arg_0], rbx
0x18000e905  push    rdi
0x18000e906  sub     rsp, 20h
0x18000e90a  mov     ebx, edx
0x18000e90c  mov     rdi, rcx
0x18000e90f  call    ??1CXMLTag@@UEAA@XZ; CXMLTag::~CXMLTag(void)
0x18000e914  test    bl, 1
0x18000e917  jz      short loc_18000E926
0x18000e919  mov     edx, 5F8h
0x18000e91e  mov     rcx, rdi; Block
0x18000e921  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e926  mov     rbx, [rsp+28h+arg_0]
0x18000e92b  mov     rax, rdi
0x18000e92e  add     rsp, 20h
0x18000e932  pop     rdi
0x18000e933  retn
```
