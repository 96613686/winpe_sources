# CONTEXT_CONTAINER::~CONTEXT_CONTAINER(void)

- ea: `0x18000de40`
- end: `0x18000de7e`
- name: `??1CONTEXT_CONTAINER@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(CONTEXT_CONTAINER *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dd90`
- `0x18000e78c`
- `0x18000e7f0`
- `0x18001a7d0`
- `0x18001a91c`
- `0x18001f5d4`
- `0x18001f710`
- `0x18002931c`

## callees

- `0x18000e3a0`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000de77`

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
0x18000de40  push    rbx
0x18000de42  sub     rsp, 20h
0x18000de46  lea     rax, ??_7CONTEXT_CONTAINER@@6BIDispensedHttpModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'}
0x18000de4d  mov     rbx, rcx
0x18000de50  mov     [rcx], rax
0x18000de53  lea     rax, ??_7CONTEXT_CONTAINER@@6BIHttpConnectionModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'}
0x18000de5a  mov     [rcx+8], rax
0x18000de5e  lea     rax, ??_7CONTEXT_CONTAINER@@6BINamedContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'}
0x18000de65  mov     [rcx+10h], rax
0x18000de69  call    ?Cleanup@CONTEXT_CONTAINER@@QEAAXXZ; CONTEXT_CONTAINER::Cleanup(void)
0x18000de6e  lea     rcx, [rbx+18h]
0x18000de72  add     rsp, 20h
0x18000de76  pop     rbx
0x18000de77  jmp     cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
```
