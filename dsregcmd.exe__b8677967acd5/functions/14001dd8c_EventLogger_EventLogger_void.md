# EventLogger::~EventLogger(void)

- ea: `0x14001dd8c`
- end: `0x14001ddf4`
- name: `??1EventLogger@@UEAA@XZ`
- size: `104`
- prototype: `void __fastcall(EventLogger *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001de00`
- `0x14002fb70`

## callees

- `0x14001dd8c`
- `0x140030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001ddba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001ddba`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x14001dda8`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x14001dda8`

## pseudocode

```c
void __fastcall EventLogger::~EventLogger(EventLogger *this)
{
  void *v2; // rcx
  volatile signed __int32 *v3; // rdx

  *(_QWORD *)this = &EventLogger::`vftable';
  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    DeregisterEventSource(v2);
    *((_QWORD *)this + 1) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v3 = (volatile signed __int32 *)(*((_QWORD *)this + 2) - 24LL);
  if ( _InterlockedExchangeAdd(v3 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 8LL))(*(_QWORD *)v3);
  *(_QWORD *)this = &ILogger::`vftable';
}

```

## disassembly

```asm
0x14001dd8c  push    rbx
0x14001dd8e  sub     rsp, 20h
0x14001dd92  lea     rax, ??_7EventLogger@@6B@; const EventLogger::`vftable'
0x14001dd99  mov     rbx, rcx
0x14001dd9c  mov     [rcx], rax
0x14001dd9f  mov     rcx, [rcx+8]; hEventLog
0x14001dda3  test    rcx, rcx
0x14001dda6  jz      short loc_14001DDB6
0x14001dda8  call    cs:__imp_DeregisterEventSource
0x14001ddae  mov     qword ptr [rbx+8], 0
0x14001ddb6  lea     rcx, [rbx+18h]; lpCriticalSection
0x14001ddba  call    cs:__imp_DeleteCriticalSection
0x14001ddc0  mov     rdx, [rbx+10h]
0x14001ddc4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001ddc8  or      eax, 0FFFFFFFFh
0x14001ddcb  lock xadd [rdx+10h], eax
0x14001ddd0  sub     eax, 1
0x14001ddd3  jg      short loc_14001DDE4
0x14001ddd5  mov     rcx, [rdx]
0x14001ddd8  mov     rax, [rcx]
0x14001dddb  mov     rax, [rax+8]
0x14001dddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001dde4  lea     rax, ??_7ILogger@@6B@; const ILogger::`vftable'
0x14001ddeb  mov     [rbx], rax
0x14001ddee  add     rsp, 20h
0x14001ddf2  pop     rbx
0x14001ddf3  retn
```
