# CLogFileCtrl::TerminateLog(void)

- ea: `0x180003240`
- end: `0x1800032e1`
- name: `?TerminateLog@CLogFileCtrl@@UEAAJXZ`
- size: `161`
- prototype: `__int64 __fastcall(CLogFileCtrl *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001fcc`
- `0x180006720`

## callees

- `0x180001048`
- `0x180003240`
- `0x18000d0e0`

## import_xrefs

- `IisRTL!??1STR@@QEAA@XZ` at `0x18000328f`
- `IisRTL!??1STR@@QEAA@XZ` at `0x18000328f`
- `IisRTL!RemoveWorkItem` at `0x1800032ac`
- `IisRTL!RemoveWorkItem` at `0x1800032ac`
- `KERNEL32!EnterCriticalSection` at `0x18000325c`
- `KERNEL32!EnterCriticalSection` at `0x18000325c`
- `KERNEL32!LeaveCriticalSection` at `0x1800032c6`
- `KERNEL32!LeaveCriticalSection` at `0x1800032c6`

## pseudocode

```c
__int64 __fastcall CLogFileCtrl::TerminateLog(CLogFileCtrl *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  LONG *v3; // rcx
  __int64 v4; // rdi
  unsigned int v5; // ecx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 368);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
  v3 = (LONG *)*((_QWORD *)this + 7);
  *((_DWORD *)this + 88) = 1;
  if ( v3 )
  {
    ILOG_FILE::CloseFile(v3);
    v4 = *((_QWORD *)this + 7);
    if ( v4 )
    {
      ILOG_FILE::CloseFile(*((LONG **)this + 7));
      STR::~STR((STR *)(v4 + 64));
      operator delete((void *)v4);
    }
    *((_QWORD *)this + 7) = 0;
  }
  v5 = *((_DWORD *)this + 30);
  if ( v5 )
    RemoveWorkItem(v5);
  *((_DWORD *)this + 30) = 0;
  *((_DWORD *)this + 88) = 0;
  LeaveCriticalSection(v1);
  return 1;
}

```

## disassembly

```asm
0x180003240  mov     [rsp+arg_0], rbx
0x180003245  mov     [rsp+arg_8], rsi
0x18000324a  push    rdi
0x18000324b  sub     rsp, 20h
0x18000324f  lea     rsi, [rcx+170h]
0x180003256  mov     rbx, rcx
0x180003259  mov     rcx, rsi; lpCriticalSection
0x18000325c  call    cs:__imp_EnterCriticalSection
0x180003262  mov     rcx, [rbx+38h]; this
0x180003266  mov     dword ptr [rbx+160h], 1
0x180003270  test    rcx, rcx
0x180003273  jz      short loc_1800032A5
0x180003275  call    ?CloseFile@ILOG_FILE@@QEAAHXZ; ILOG_FILE::CloseFile(void)
0x18000327a  mov     rdi, [rbx+38h]
0x18000327e  test    rdi, rdi
0x180003281  jz      short loc_18000329D
0x180003283  mov     rcx, rdi; this
0x180003286  call    ?CloseFile@ILOG_FILE@@QEAAHXZ; ILOG_FILE::CloseFile(void)
0x18000328b  lea     rcx, [rdi+40h]
0x18000328f  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x180003295  mov     rcx, rdi; Block
0x180003298  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000329d  mov     qword ptr [rbx+38h], 0
0x1800032a5  mov     ecx, [rbx+78h]
0x1800032a8  test    ecx, ecx
0x1800032aa  jz      short loc_1800032B2
0x1800032ac  call    cs:__imp_?RemoveWorkItem@@YAHK@Z; RemoveWorkItem(ulong)
0x1800032b2  mov     rcx, rsi; lpCriticalSection
0x1800032b5  mov     dword ptr [rbx+78h], 0
0x1800032bc  mov     dword ptr [rbx+160h], 0
0x1800032c6  call    cs:__imp_LeaveCriticalSection
0x1800032cc  mov     rbx, [rsp+28h+arg_0]
0x1800032d1  mov     eax, 1
0x1800032d6  mov     rsi, [rsp+28h+arg_8]
0x1800032db  add     rsp, 20h
0x1800032df  pop     rdi
0x1800032e0  retn
```
