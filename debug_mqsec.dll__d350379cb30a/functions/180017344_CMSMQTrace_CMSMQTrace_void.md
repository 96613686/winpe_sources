# CMSMQTrace::~CMSMQTrace(void)

- ea: `0x180017344`
- end: `0x180017369`
- name: `??1CMSMQTrace@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(CMSMQTrace *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180013b18`

## import_xrefs

- `ADVAPI32!UnregisterTraceGuids` at `0x180017351`
- `ADVAPI32!UnregisterTraceGuids` at `0x180017351`
- `KERNEL32!DeleteCriticalSection` at `0x18001735c`
- `KERNEL32!DeleteCriticalSection` at `0x18001735c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMSMQTrace::~CMSMQTrace(CMSMQTrace *this)
{
  UnregisterTraceGuids(*((_QWORD *)this + 11));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180017344  push    rbx
0x180017346  sub     rsp, 20h
0x18001734a  mov     rbx, rcx
0x18001734d  mov     rcx, [rcx+58h]; RegistrationHandle
0x180017351  call    cs:__imp_UnregisterTraceGuids
0x180017357  nop
0x180017358  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001735c  call    cs:__imp_DeleteCriticalSection
0x180017362  nop
0x180017363  add     rsp, 20h
0x180017367  pop     rbx
0x180017368  retn
```
