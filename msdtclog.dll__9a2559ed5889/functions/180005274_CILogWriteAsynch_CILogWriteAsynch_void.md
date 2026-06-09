# CILogWriteAsynch::~CILogWriteAsynch(void)

- ea: `0x180005274`
- end: `0x1800052b1`
- name: `??1CILogWriteAsynch@@QEAA@XZ`
- size: `61`
- prototype: `void __fastcall(CILogWriteAsynch *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180014222`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005290`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000529f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005290`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000529f`

## pseudocode

```c
void __fastcall CILogWriteAsynch::~CILogWriteAsynch(CILogWriteAsynch *this)
{
  *((_QWORD *)this + 11) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  *((_QWORD *)this + 4) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
}

```

## disassembly

```asm
0x180005274  mov     [rsp+arg_0], rbx
0x180005279  push    rdi
0x18000527a  sub     rsp, 20h
0x18000527e  mov     rbx, rcx
0x180005281  lea     rdi, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x180005288  mov     [rcx+58h], rdi
0x18000528c  add     rcx, 60h ; '`'; lpCriticalSection
0x180005290  call    cs:__imp_DeleteCriticalSection
0x180005296  nop
0x180005297  mov     [rbx+20h], rdi
0x18000529b  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000529f  call    cs:__imp_DeleteCriticalSection
0x1800052a5  nop
0x1800052a6  mov     rbx, [rsp+28h+arg_0]
0x1800052ab  add     rsp, 20h
0x1800052af  pop     rdi
0x1800052b0  retn
```
