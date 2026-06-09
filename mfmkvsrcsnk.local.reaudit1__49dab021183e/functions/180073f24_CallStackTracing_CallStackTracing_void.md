# CallStackTracing::~CallStackTracing(void)

- ea: `0x180073f24`
- end: `0x180073f86`
- name: `??1CallStackTracing@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(CallStackTracing *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800b31a0`

## callees

- `0x180051528`
- `0x180073ec0`
- `0x180074148`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180073f65`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180073f65`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180073f7a`

## pseudocode

```c
void __fastcall CallStackTracing::~CallStackTracing(CallStackTracing *this)
{
  *(_QWORD *)this = &CallStackTracing::`vftable';
  CallStackTracing::Cleanup(this);
  `vector destructor iterator'((char *)this + 208, 0x10u, 0x7Cu, MkvMfSourceLib::MkvMfByteStreamHandler::LogInstance);
  CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>((char *)this + 104);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180073f24  push    rbx
0x180073f26  sub     rsp, 20h
0x180073f2a  lea     rax, ??_7CallStackTracing@@6B@; const CallStackTracing::`vftable'
0x180073f31  mov     rbx, rcx
0x180073f34  mov     [rcx], rax
0x180073f37  call    ?Cleanup@CallStackTracing@@IEAAXXZ; CallStackTracing::Cleanup(void)
0x180073f3c  mov     edx, 10h; unsigned __int64
0x180073f41  lea     rcx, [rbx+0D0h]; void *
0x180073f48  lea     r9, ?LogInstance@MkvMfByteStreamHandler@MkvMfSourceLib@@UEAAXW4_MF_TELEMETRY_SESSION_LOG_REASON@@@Z; void (*)(void *)
0x180073f4f  lea     r8d, [rdx+6Ch]; unsigned __int64
0x180073f53  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180073f58  lea     rcx, [rbx+68h]
0x180073f5c  call    ??1?$CFreeList@VCallStackContextNode@@$0BA@@@UEAA@XZ; CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(void)
0x180073f61  lea     rcx, [rbx+38h]; lpCriticalSection
0x180073f65  call    cs:__imp_DeleteCriticalSection
0x180073f6c  nop     dword ptr [rax+rax+00h]
0x180073f71  lea     rcx, [rbx+10h]
0x180073f75  add     rsp, 20h
0x180073f79  pop     rbx
0x180073f7a  jmp     cs:__imp_DeleteCriticalSection
```
