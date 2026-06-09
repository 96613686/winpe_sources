# CMSMQTrace::~CMSMQTrace(void)

- ea: `0x1800210f4`
- end: `0x180021119`
- name: `??1CMSMQTrace@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(CMSMQTrace *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180013794`

## import_xrefs

- `ADVAPI32!UnregisterTraceGuids` at `0x180021101`
- `ADVAPI32!UnregisterTraceGuids` at `0x180021101`
- `KERNEL32!DeleteCriticalSection` at `0x18002110c`
- `KERNEL32!DeleteCriticalSection` at `0x18002110c`

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
0x1800210f4  push    rbx
0x1800210f6  sub     rsp, 20h
0x1800210fa  mov     rbx, rcx
0x1800210fd  mov     rcx, [rcx+58h]; RegistrationHandle
0x180021101  call    cs:__imp_UnregisterTraceGuids
0x180021107  nop
0x180021108  lea     rcx, [rbx+10h]; lpCriticalSection
0x18002110c  call    cs:__imp_DeleteCriticalSection
0x180021112  nop
0x180021113  add     rsp, 20h
0x180021117  pop     rbx
0x180021118  retn
```
