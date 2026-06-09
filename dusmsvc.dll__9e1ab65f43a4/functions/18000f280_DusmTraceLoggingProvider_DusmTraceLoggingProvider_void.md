# DusmTraceLoggingProvider::~DusmTraceLoggingProvider(void)

- ea: `0x18000f280`
- end: `0x18000f2a0`
- name: `??1DusmTraceLoggingProvider@@UEAA@XZ`
- size: `32`
- prototype: `void __fastcall(DusmTraceLoggingProvider *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f970`

## callees

- `0x18000f468`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f28d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f28d`

## pseudocode

```c
void __fastcall DusmTraceLoggingProvider::~DusmTraceLoggingProvider(DusmTraceLoggingProvider *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  wil::TraceLoggingProvider::~TraceLoggingProvider(this);
}

```

## disassembly

```asm
0x18000f280  push    rbx
0x18000f282  sub     rsp, 20h
0x18000f286  mov     rbx, rcx
0x18000f289  add     rcx, 70h ; 'p'; lpCriticalSection
0x18000f28d  call    cs:__imp_DeleteCriticalSection
0x18000f293  mov     rcx, rbx; this
0x18000f296  add     rsp, 20h
0x18000f29a  pop     rbx
0x18000f29b  jmp     ??1TraceLoggingProvider@wil@@MEAA@XZ; wil::TraceLoggingProvider::~TraceLoggingProvider(void)
```
