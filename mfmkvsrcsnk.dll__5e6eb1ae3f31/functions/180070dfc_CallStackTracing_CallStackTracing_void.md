# CallStackTracing::~CallStackTracing(void)

- ea: `0x180070dfc`
- end: `0x180070e53`
- name: `??1CallStackTracing@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(CallStackTracing *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800ae440`

## callees

- `0x18004f300`
- `0x180070d9c`
- `0x180070fe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180070e3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180070e3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180070e4c`

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
0x180070dfc  push    rbx
0x180070dfe  sub     rsp, 20h
0x180070e02  lea     rax, ??_7CallStackTracing@@6B@; const CallStackTracing::`vftable'
0x180070e09  mov     rbx, rcx
0x180070e0c  mov     [rcx], rax
0x180070e0f  call    ?Cleanup@CallStackTracing@@IEAAXXZ; CallStackTracing::Cleanup(void)
0x180070e14  mov     edx, 10h; unsigned __int64
0x180070e19  lea     rcx, [rbx+0D0h]; void *
0x180070e20  lea     r9, ?LogInstance@MkvMfByteStreamHandler@MkvMfSourceLib@@UEAAXW4_MF_TELEMETRY_SESSION_LOG_REASON@@@Z; void (*)(void *)
0x180070e27  lea     r8d, [rdx+6Ch]; unsigned __int64
0x180070e2b  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180070e30  lea     rcx, [rbx+68h]
0x180070e34  call    ??1?$CFreeList@VCallStackContextNode@@$0BA@@@UEAA@XZ; CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(void)
0x180070e39  lea     rcx, [rbx+38h]; lpCriticalSection
0x180070e3d  call    cs:__imp_DeleteCriticalSection
0x180070e43  lea     rcx, [rbx+10h]
0x180070e47  add     rsp, 20h
0x180070e4b  pop     rbx
0x180070e4c  jmp     cs:__imp_DeleteCriticalSection
```
