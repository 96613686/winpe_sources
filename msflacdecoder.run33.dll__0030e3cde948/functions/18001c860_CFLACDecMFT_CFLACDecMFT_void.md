# CFLACDecMFT::~CFLACDecMFT(void)

- ea: `0x18001c860`
- end: `0x18001c8ae`
- name: `??1CFLACDecMFT@@UEAA@XZ`
- size: `78`
- prototype: `void __fastcall(CFLACDecMFT *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180016c68`
- `0x180016d70`
- `0x180017020`

## callees

- `0x18001c8d4`
- `0x18001cc90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c89b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c89b`

## pseudocode

```c
void __fastcall CFLACDecMFT::~CFLACDecMFT(CFLACDecMFT *this)
{
  *(_QWORD *)this = &CFLACDecMFT::`vftable'{for `CMFTSimpleBase'};
  *((_QWORD *)this + 19) = &CFLACDecMFT::`vftable'{for `CProcessSamplesCB'};
  CFLACDecMFT::CleanUp(this);
  *((_QWORD *)this + 120) = &CFlacDecTraceLogging::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  CMFTSimpleBase::~CMFTSimpleBase(this);
}

```

## disassembly

```asm
0x18001c860  push    rbx
0x18001c862  sub     rsp, 20h
0x18001c866  mov     rbx, rcx
0x18001c869  lea     rax, ??_7CFLACDecMFT@@6BCMFTSimpleBase@@@; const CFLACDecMFT::`vftable'{for `CMFTSimpleBase'}
0x18001c870  mov     [rcx], rax
0x18001c873  lea     rax, ??_7CFLACDecMFT@@6BCProcessSamplesCB@@@; const CFLACDecMFT::`vftable'{for `CProcessSamplesCB'}
0x18001c87a  mov     [rcx+98h], rax
0x18001c881  call    ?CleanUp@CFLACDecMFT@@AEAAJXZ; CFLACDecMFT::CleanUp(void)
0x18001c886  lea     rax, ??_7CFlacDecTraceLogging@@6B@; const CFlacDecTraceLogging::`vftable'
0x18001c88d  mov     [rbx+3C0h], rax
0x18001c894  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x18001c89b  call    cs:__imp_DeleteCriticalSection
0x18001c8a1  mov     rcx, rbx; this
0x18001c8a4  add     rsp, 20h
0x18001c8a8  pop     rbx
0x18001c8a9  jmp     ??1CMFTSimpleBase@@UEAA@XZ; CMFTSimpleBase::~CMFTSimpleBase(void)
```
