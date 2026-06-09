# CLogFileCtrl::~CLogFileCtrl(void)

- ea: `0x180001fcc`
- end: `0x18000202b`
- name: `??1CLogFileCtrl@@MEAA@XZ`
- size: `95`
- prototype: `void __fastcall(CLogFileCtrl *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003984`
- `0x1800075f4`
- `0x18000bf30`

## callees

- `0x180003240`

## import_xrefs

- `IisRTL!??1STR@@QEAA@XZ` at `0x180001fee`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180001ffb`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180002008`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180002015`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180001fee`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180001ffb`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180002008`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180002015`
- `KERNEL32!DeleteCriticalSection` at `0x180001fe1`
- `KERNEL32!DeleteCriticalSection` at `0x180001fe1`
- `KERNEL32!DeleteCriticalSection` at `0x180002024`

## pseudocode

```c
void __fastcall CLogFileCtrl::~CLogFileCtrl(CLogFileCtrl *this)
{
  CLogFileCtrl::TerminateLog(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
  STR::~STR((CLogFileCtrl *)((char *)this + 296));
  STR::~STR((CLogFileCtrl *)((char *)this + 240));
  STR::~STR((CLogFileCtrl *)((char *)this + 184));
  STR::~STR((CLogFileCtrl *)((char *)this + 128));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180001fcc  push    rbx
0x180001fce  sub     rsp, 20h
0x180001fd2  mov     rbx, rcx
0x180001fd5  call    ?TerminateLog@CLogFileCtrl@@UEAAJXZ; CLogFileCtrl::TerminateLog(void)
0x180001fda  lea     rcx, [rbx+170h]; lpCriticalSection
0x180001fe1  call    cs:__imp_DeleteCriticalSection
0x180001fe7  lea     rcx, [rbx+128h]
0x180001fee  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x180001ff4  lea     rcx, [rbx+0F0h]
0x180001ffb  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x180002001  lea     rcx, [rbx+0B8h]
0x180002008  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x18000200e  lea     rcx, [rbx+80h]
0x180002015  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x18000201b  lea     rcx, [rbx+10h]
0x18000201f  add     rsp, 20h
0x180002023  pop     rbx
0x180002024  jmp     cs:__imp_DeleteCriticalSection
```
