# CallStackTracing::~CallStackTracing(void)

- ea: `0x180002420`
- end: `0x180002467`
- name: `??1CallStackTracing@@QEAA@XZ`
- size: `71`
- prototype: `void __fastcall(CallStackTracing *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005180`

## callees

- `0x180001fd0`
- `0x180002470`
- `0x1800024d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002451`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002451`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002460`

## pseudocode

```c
void __fastcall CallStackTracing::~CallStackTracing(CallStackTracing *this)
{
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // r8
  void (*v4)(void *); // r9

  *(_QWORD *)this = &CallStackTracing::`vftable';
  CallStackTracing::Cleanup(this);
  `vector destructor iterator'((char *)this + 208, v2, v3, v4);
  CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>((char *)this + 104);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180002420  push    rbx
0x180002422  sub     rsp, 20h
0x180002426  lea     rax, ??_7CallStackTracing@@6B@; const CallStackTracing::`vftable'
0x18000242d  mov     rbx, rcx
0x180002430  mov     [rcx], rax
0x180002433  call    ?Cleanup@CallStackTracing@@IEAAXXZ; CallStackTracing::Cleanup(void)
0x180002438  lea     rcx, [rbx+0D0h]; void *
0x18000243f  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180002444  lea     rcx, [rbx+68h]
0x180002448  call    ??1?$CFreeList@VCallStackContextNode@@$0BA@@@UEAA@XZ; CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(void)
0x18000244d  lea     rcx, [rbx+38h]; lpCriticalSection
0x180002451  call    cs:__imp_DeleteCriticalSection
0x180002457  lea     rcx, [rbx+10h]
0x18000245b  add     rsp, 20h
0x18000245f  pop     rbx
0x180002460  jmp     cs:__imp_DeleteCriticalSection
```
