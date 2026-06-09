# CMSMQTrace::~CMSMQTrace(void)

- ea: `0x180014c04`
- end: `0x180014c29`
- name: `??1CMSMQTrace@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(CMSMQTrace *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000dd0c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180014c1c`
- `KERNEL32!DeleteCriticalSection` at `0x180014c1c`
- `ADVAPI32!UnregisterTraceGuids` at `0x180014c11`
- `ADVAPI32!UnregisterTraceGuids` at `0x180014c11`

## pseudocode

```c
void __fastcall CMSMQTrace::~CMSMQTrace(CMSMQTrace *this)
{
  UnregisterTraceGuids(*((_QWORD *)this + 11));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180014c04  push    rbx
0x180014c06  sub     rsp, 20h
0x180014c0a  mov     rbx, rcx
0x180014c0d  mov     rcx, [rcx+58h]; RegistrationHandle
0x180014c11  call    cs:__imp_UnregisterTraceGuids
0x180014c17  nop
0x180014c18  lea     rcx, [rbx+10h]; lpCriticalSection
0x180014c1c  call    cs:__imp_DeleteCriticalSection
0x180014c22  nop
0x180014c23  add     rsp, 20h
0x180014c27  pop     rbx
0x180014c28  retn
```
