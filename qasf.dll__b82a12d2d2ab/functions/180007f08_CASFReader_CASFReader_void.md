# CASFReader::~CASFReader(void)

- ea: `0x180007f08`
- end: `0x180008020`
- name: `??1CASFReader@@UEAA@XZ`
- size: `280`
- prototype: `void __fastcall(CASFReader *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x1800080f0`

## callees

- `0x180001008`
- `0x180003678`
- `0x180006f10`
- `0x180007f08`
- `0x18000c9e4`
- `0x18001f010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008000`
- `KERNEL32!DeleteCriticalSection` at `0x18000800d`
- `KERNEL32!DeleteCriticalSection` at `0x180008000`
- `KERNEL32!DeleteCriticalSection` at `0x18000800d`
- `KERNEL32!CloseHandle` at `0x180007fc3`
- `KERNEL32!CloseHandle` at `0x180007fd5`
- `KERNEL32!CloseHandle` at `0x180007fe7`
- `KERNEL32!CloseHandle` at `0x180007fc3`
- `KERNEL32!CloseHandle` at `0x180007fd5`
- `KERNEL32!CloseHandle` at `0x180007fe7`

## pseudocode

```c
void __fastcall CASFReader::~CASFReader(struct _RTL_CRITICAL_SECTION *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rdx
  int v4; // edx
  __int64 v5; // rcx
  void *SpinCount; // rcx
  HANDLE LockSemaphore; // rcx
  void *v8; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CASFReader::`vftable'{for `CUnknown'};
  this->LockSemaphore = &CASFReader::`vftable'{for `IBaseFilter'};
  this->SpinCount = (ULONG_PTR)&CMediaWrapperFilter::`vftable'{for `IAMovieSetup'};
  this[3].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CASFReader::`vftable'{for `IFileSourceFilter'};
  *(_QWORD *)&this[3].LockCount = &CASFReader::`vftable'{for `IAMExtendedSeeking'};
  this[3].OwningThread = &CASFReader::`vftable'{for `IWMHeaderInfo'};
  this[3].LockSemaphore = &CASFReader::`vftable'{for `IWMReaderAdvanced2'};
  this[3].SpinCount = (ULONG_PTR)&CASFReader::`vftable'{for `IServiceProvider'};
  operator delete(this[6].DebugInfo, a2);
  operator delete(this[10].DebugInfo, v3);
  CASFReader::RemoveOutputPins((CASFReader *)this, v4);
  v5 = *(_QWORD *)&this[8].LockCount;
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *(_QWORD *)&this[8].LockCount = 0;
  }
  SpinCount = (void *)this[10].SpinCount;
  if ( SpinCount )
    CloseHandle(SpinCount);
  LockSemaphore = this[10].LockSemaphore;
  if ( LockSemaphore )
    CloseHandle(LockSemaphore);
  v8 = *(void **)&this[10].LockCount;
  if ( v8 )
    CloseHandle(v8);
  CBaseList::~CBaseList((CBaseList *)&this[7]);
  DeleteCriticalSection(this + 5);
  DeleteCriticalSection(this + 4);
  CBaseFilter::~CBaseFilter((CBaseFilter *)this);
}

```

## disassembly

```asm
0x180007f08  push    rbx
0x180007f0a  sub     rsp, 20h
0x180007f0e  lea     rax, ??_7CASFReader@@6BCUnknown@@@; const CASFReader::`vftable'{for `CUnknown'}
0x180007f15  mov     rbx, rcx
0x180007f18  mov     [rcx], rax
0x180007f1b  lea     rax, ??_7CASFReader@@6BIBaseFilter@@@; const CASFReader::`vftable'{for `IBaseFilter'}
0x180007f22  mov     [rcx+18h], rax
0x180007f26  lea     rax, ??_7CMediaWrapperFilter@@6BIAMovieSetup@@@; const CMediaWrapperFilter::`vftable'{for `IAMovieSetup'}
0x180007f2d  mov     [rcx+20h], rax
0x180007f31  lea     rax, ??_7CASFReader@@6BIFileSourceFilter@@@; const CASFReader::`vftable'{for `IFileSourceFilter'}
0x180007f38  mov     [rcx+78h], rax
0x180007f3c  lea     rax, ??_7CASFReader@@6BIAMExtendedSeeking@@@; const CASFReader::`vftable'{for `IAMExtendedSeeking'}
0x180007f43  mov     [rcx+80h], rax
0x180007f4a  lea     rax, ??_7CASFReader@@6BIWMHeaderInfo@@@; const CASFReader::`vftable'{for `IWMHeaderInfo'}
0x180007f51  mov     [rcx+88h], rax
0x180007f58  lea     rax, ??_7CASFReader@@6BIWMReaderAdvanced2@@@; const CASFReader::`vftable'{for `IWMReaderAdvanced2'}
0x180007f5f  mov     [rcx+90h], rax
0x180007f66  lea     rax, ??_7CASFReader@@6BIServiceProvider@@@; const CASFReader::`vftable'{for `IServiceProvider'}
0x180007f6d  mov     [rcx+98h], rax
0x180007f74  mov     rcx, [rcx+0F0h]; void *
0x180007f7b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007f80  mov     rcx, [rbx+190h]; void *
0x180007f87  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007f8c  mov     rcx, rbx; this
0x180007f8f  call    ?RemoveOutputPins@CASFReader@@QEAAXH@Z; CASFReader::RemoveOutputPins(int)
0x180007f94  mov     rcx, [rbx+148h]
0x180007f9b  test    rcx, rcx
0x180007f9e  jz      short loc_180007FB7
0x180007fa0  mov     rax, [rcx]
0x180007fa3  mov     rax, [rax+10h]
0x180007fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fac  mov     qword ptr [rbx+148h], 0
0x180007fb7  mov     rcx, [rbx+1B0h]; hObject
0x180007fbe  test    rcx, rcx
0x180007fc1  jz      short loc_180007FC9
0x180007fc3  call    cs:__imp_CloseHandle
0x180007fc9  mov     rcx, [rbx+1A8h]; hObject
0x180007fd0  test    rcx, rcx
0x180007fd3  jz      short loc_180007FDB
0x180007fd5  call    cs:__imp_CloseHandle
0x180007fdb  mov     rcx, [rbx+198h]; hObject
0x180007fe2  test    rcx, rcx
0x180007fe5  jz      short loc_180007FED
0x180007fe7  call    cs:__imp_CloseHandle
0x180007fed  lea     rcx, [rbx+118h]; this
0x180007ff4  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x180007ff9  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180008000  call    cs:__imp_DeleteCriticalSection
0x180008006  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x18000800d  call    cs:__imp_DeleteCriticalSection
0x180008013  mov     rcx, rbx; this
0x180008016  add     rsp, 20h
0x18000801a  pop     rbx
0x18000801b  jmp     ??1CBaseFilter@@UEAA@XZ; CBaseFilter::~CBaseFilter(void)
```
