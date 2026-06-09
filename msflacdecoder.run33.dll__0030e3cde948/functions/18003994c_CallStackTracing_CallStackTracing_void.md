# CallStackTracing::~CallStackTracing(void)

- ea: `0x18003994c`
- end: `0x180039993`
- name: `??1CallStackTracing@@QEAA@XZ`
- size: `71`
- prototype: `void __fastcall(CallStackTracing *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180055d20`

## callees

- `0x1800342b4`
- `0x1800398ec`
- `0x180039b10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003997d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003997d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003998c`

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
0x18003994c  push    rbx
0x18003994e  sub     rsp, 20h
0x180039952  lea     rax, ??_7CallStackTracing@@6B@; const CallStackTracing::`vftable'
0x180039959  mov     rbx, rcx
0x18003995c  mov     [rcx], rax
0x18003995f  call    ?Cleanup@CallStackTracing@@IEAAXXZ; CallStackTracing::Cleanup(void)
0x180039964  lea     rcx, [rbx+0D0h]; void *
0x18003996b  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180039970  lea     rcx, [rbx+68h]
0x180039974  call    ??1?$CFreeList@VCallStackContextNode@@$0BA@@@UEAA@XZ; CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(void)
0x180039979  lea     rcx, [rbx+38h]; lpCriticalSection
0x18003997d  call    cs:__imp_DeleteCriticalSection
0x180039983  lea     rcx, [rbx+10h]
0x180039987  add     rsp, 20h
0x18003998b  pop     rbx
0x18003998c  jmp     cs:__imp_DeleteCriticalSection
```
