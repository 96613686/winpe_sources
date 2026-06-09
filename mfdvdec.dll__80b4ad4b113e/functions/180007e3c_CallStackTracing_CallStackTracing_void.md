# CallStackTracing::~CallStackTracing(void)

- ea: `0x180007e3c`
- end: `0x180007ea8`
- name: `??1CallStackTracing@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(CallStackTracing *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d490`

## callees

- `0x180005fb0`
- `0x180007dbc`
- `0x180007e3c`
- `0x180008180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007e88`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007e88`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007ea1`

## pseudocode

```c
void __fastcall CallStackTracing::~CallStackTracing(CallStackTracing *this)
{
  __int64 v2; // rdi
  char *v3; // rsi

  *(_QWORD *)this = &CallStackTracing::`vftable';
  CallStackTracing::Cleanup(this);
  v2 = 124;
  v3 = (char *)this + 2192;
  do
  {
    v3 -= 16;
    rgbtransYUY2FulloutRight(v3);
    --v2;
  }
  while ( v2 );
  CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>((char *)this + 104);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180007e3c  mov     [rsp+arg_0], rbx
0x180007e41  mov     [rsp+arg_8], rsi
0x180007e46  push    rdi
0x180007e47  sub     rsp, 20h
0x180007e4b  lea     rax, ??_7CallStackTracing@@6B@; const CallStackTracing::`vftable'
0x180007e52  mov     rbx, rcx
0x180007e55  mov     [rcx], rax
0x180007e58  call    ?Cleanup@CallStackTracing@@IEAAXXZ; CallStackTracing::Cleanup(void)
0x180007e5d  mov     edi, 7Ch ; '|'
0x180007e62  lea     rsi, [rbx+890h]
0x180007e69  sub     rsi, 10h
0x180007e6d  mov     rcx, rsi
0x180007e70  call    rgbtransYUY2FulloutRight
0x180007e75  sub     rdi, 1
0x180007e79  jnz     short loc_180007E69
0x180007e7b  lea     rcx, [rbx+68h]
0x180007e7f  call    ??1?$CFreeList@VCallStackContextNode@@$0BA@@@UEAA@XZ; CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(void)
0x180007e84  lea     rcx, [rbx+38h]; lpCriticalSection
0x180007e88  call    cs:__imp_DeleteCriticalSection
0x180007e8e  lea     rcx, [rbx+10h]
0x180007e92  mov     rbx, [rsp+28h+arg_0]
0x180007e97  mov     rsi, [rsp+28h+arg_8]
0x180007e9c  add     rsp, 20h
0x180007ea0  pop     rdi
0x180007ea1  jmp     cs:__imp_DeleteCriticalSection
```
