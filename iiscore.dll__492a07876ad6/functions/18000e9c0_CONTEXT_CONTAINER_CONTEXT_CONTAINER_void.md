# CONTEXT_CONTAINER::~CONTEXT_CONTAINER(void)

- ea: `0x18000e9c0`
- end: `0x18000ea03`
- name: `??1CONTEXT_CONTAINER@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(CONTEXT_CONTAINER *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e908`
- `0x18000f3f4`
- `0x18000f460`
- `0x18001be58`
- `0x18001bfb8`
- `0x1800211a8`
- `0x1800212f8`
- `0x18002b7a8`

## callees

- `0x18000ef70`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000e9f7`

## pseudocode

```c
void __fastcall CONTEXT_CONTAINER::~CONTEXT_CONTAINER(CONTEXT_CONTAINER *this)
{
  *(_QWORD *)this = &CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'};
  *((_QWORD *)this + 1) = &CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'};
  *((_QWORD *)this + 2) = &CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'};
  CONTEXT_CONTAINER::Cleanup(this);
  CReaderWriterLock3::~CReaderWriterLock3((CONTEXT_CONTAINER *)((char *)this + 24));
}

```

## disassembly

```asm
0x18000e9c0  push    rbx
0x18000e9c2  sub     rsp, 20h
0x18000e9c6  lea     rax, ??_7CONTEXT_CONTAINER@@6BIDispensedHttpModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'}
0x18000e9cd  mov     rbx, rcx
0x18000e9d0  mov     [rcx], rax
0x18000e9d3  lea     rax, ??_7CONTEXT_CONTAINER@@6BIHttpConnectionModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'}
0x18000e9da  mov     [rcx+8], rax
0x18000e9de  lea     rax, ??_7CONTEXT_CONTAINER@@6BINamedContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'}
0x18000e9e5  mov     [rcx+10h], rax
0x18000e9e9  call    ?Cleanup@CONTEXT_CONTAINER@@QEAAXXZ; CONTEXT_CONTAINER::Cleanup(void)
0x18000e9ee  lea     rcx, [rbx+18h]
0x18000e9f2  add     rsp, 20h
0x18000e9f6  pop     rbx
0x18000e9f7  jmp     cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
```
