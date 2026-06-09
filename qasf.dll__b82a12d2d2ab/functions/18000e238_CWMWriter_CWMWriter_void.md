# CWMWriter::~CWMWriter(void)

- ea: `0x18000e238`
- end: `0x18000e3aa`
- name: `??1CWMWriter@@UEAA@XZ`
- size: `370`
- prototype: `void __fastcall(CWMWriter *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18000e3b0`

## callees

- `0x180001008`
- `0x180003678`
- `0x180006f10`
- `0x180007004`
- `0x18000e238`
- `0x18000f594`
- `0x18000f6ac`
- `0x180011304`
- `0x18001f010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000e384`
- `KERNEL32!DeleteCriticalSection` at `0x18000e384`

## pseudocode

```c
void __fastcall CWMWriter::~CWMWriter(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rcx
  void *v3; // rax
  unsigned __int64 v4; // rdx
  void *v5; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CWMWriter::`vftable'{for `CUnknown'};
  this->LockSemaphore = &CWMWriter::`vftable'{for `IBaseFilter'};
  this->SpinCount = (ULONG_PTR)&CMediaWrapperFilter::`vftable'{for `IAMovieSetup'};
  this[3].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CWMWriter::`vftable'{for `IMediaSeeking'};
  *(_QWORD *)&this[3].LockCount = &CWMWriter::`vftable'{for `IAMFilterMiscFlags'};
  this[3].OwningThread = &CWMWriter::`vftable'{for `IFileSinkFilter2'};
  this[3].LockSemaphore = &CWMWriter::`vftable'{for `ISpecifyPropertyPages'};
  this[3].SpinCount = (ULONG_PTR)&CWMWriter::`vftable'{for `IConfigAsfWriter2'};
  this[4].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CWMWriter::`vftable'{for `CPersistStream'};
  this[4].OwningThread = &CWMWriter::`vftable'{for `IWMHeaderInfo'};
  this[4].LockSemaphore = &CWMWriter::`vftable'{for `IServiceProvider'};
  this[4].SpinCount = (ULONG_PTR)&CWMWriter::`vftable'{for `IWMWriterPreprocess'};
  this[5].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CWMWriter::`vftable'{for `IWMStatusCallback'};
  CWMWriter::DeleteProfile((CWMWriter *)this);
  CWMWriter::ReleaseWMWriter((CWMWriter *)this);
  LockSemaphore = this[9].LockSemaphore;
  if ( LockSemaphore )
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)LockSemaphore + 16LL))(LockSemaphore);
  CWMWriter::DeletePins((CWMWriter *)this, 0);
  while ( 1 )
  {
    v3 = CBaseList::RemoveI((CBaseList *)&this[11].LockCount, *(struct __POSITION **)&this[11].LockCount);
    if ( !v3 )
      break;
    (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v3 + 24LL))(v3, 1);
  }
  v5 = *(void **)&this[7].LockCount;
  if ( v5 )
  {
    operator delete(v5, v4);
    *(_QWORD *)&this[7].LockCount = 0;
  }
  CBaseList::~CBaseList((CBaseList *)&this[11].LockCount);
  CBaseList::~CBaseList((CBaseList *)&this[10].LockCount);
  DeleteCriticalSection(this + 6);
  this[4].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CPersistStream::`vftable';
  CBaseFilter::~CBaseFilter((CBaseFilter *)this);
}

```

## disassembly

```asm
0x18000e238  mov     [rsp+arg_0], rbx
0x18000e23d  push    rdi
0x18000e23e  sub     rsp, 20h
0x18000e242  lea     rax, ??_7CWMWriter@@6BCUnknown@@@; const CWMWriter::`vftable'{for `CUnknown'}
0x18000e249  mov     rbx, rcx
0x18000e24c  mov     [rcx], rax
0x18000e24f  lea     rax, ??_7CWMWriter@@6BIBaseFilter@@@; const CWMWriter::`vftable'{for `IBaseFilter'}
0x18000e256  mov     [rcx+18h], rax
0x18000e25a  lea     rax, ??_7CMediaWrapperFilter@@6BIAMovieSetup@@@; const CMediaWrapperFilter::`vftable'{for `IAMovieSetup'}
0x18000e261  mov     [rcx+20h], rax
0x18000e265  lea     rax, ??_7CWMWriter@@6BIMediaSeeking@@@; const CWMWriter::`vftable'{for `IMediaSeeking'}
0x18000e26c  mov     [rcx+78h], rax
0x18000e270  lea     rax, ??_7CWMWriter@@6BIAMFilterMiscFlags@@@; const CWMWriter::`vftable'{for `IAMFilterMiscFlags'}
0x18000e277  mov     [rcx+80h], rax
0x18000e27e  lea     rax, ??_7CWMWriter@@6BIFileSinkFilter2@@@; const CWMWriter::`vftable'{for `IFileSinkFilter2'}
0x18000e285  mov     [rcx+88h], rax
0x18000e28c  lea     rax, ??_7CWMWriter@@6BISpecifyPropertyPages@@@; const CWMWriter::`vftable'{for `ISpecifyPropertyPages'}
0x18000e293  mov     [rcx+90h], rax
0x18000e29a  lea     rax, ??_7CWMWriter@@6BIConfigAsfWriter2@@@; const CWMWriter::`vftable'{for `IConfigAsfWriter2'}
0x18000e2a1  mov     [rcx+98h], rax
0x18000e2a8  lea     rax, ??_7CWMWriter@@6BCPersistStream@@@; const CWMWriter::`vftable'{for `CPersistStream'}
0x18000e2af  mov     [rcx+0A0h], rax
0x18000e2b6  lea     rax, ??_7CWMWriter@@6BIWMHeaderInfo@@@; const CWMWriter::`vftable'{for `IWMHeaderInfo'}
0x18000e2bd  mov     [rcx+0B0h], rax
0x18000e2c4  lea     rax, ??_7CWMWriter@@6BIServiceProvider@@@; const CWMWriter::`vftable'{for `IServiceProvider'}
0x18000e2cb  mov     [rcx+0B8h], rax
0x18000e2d2  lea     rax, ??_7CWMWriter@@6BIWMWriterPreprocess@@@; const CWMWriter::`vftable'{for `IWMWriterPreprocess'}
0x18000e2d9  mov     [rcx+0C0h], rax
0x18000e2e0  lea     rax, ??_7CWMWriter@@6BIWMStatusCallback@@@; const CWMWriter::`vftable'{for `IWMStatusCallback'}
0x18000e2e7  mov     [rcx+0C8h], rax
0x18000e2ee  call    ?DeleteProfile@CWMWriter@@QEAAXXZ; CWMWriter::DeleteProfile(void)
0x18000e2f3  mov     rcx, rbx; this
0x18000e2f6  call    ?ReleaseWMWriter@CWMWriter@@QEAAXXZ; CWMWriter::ReleaseWMWriter(void)
0x18000e2fb  mov     rcx, [rbx+180h]
0x18000e302  test    rcx, rcx
0x18000e305  jz      short loc_18000E313
0x18000e307  mov     rax, [rcx]
0x18000e30a  mov     rax, [rax+10h]
0x18000e30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e313  xor     edx, edx; int
0x18000e315  mov     rcx, rbx; this
0x18000e318  call    ?DeletePins@CWMWriter@@QEAAXH@Z; CWMWriter::DeletePins(int)
0x18000e31d  lea     rdi, [rbx+1C0h]
0x18000e324  jmp     short loc_18000E33A
0x18000e326  mov     rcx, [r8]
0x18000e329  mov     edx, 1
0x18000e32e  mov     rax, [rcx+18h]
0x18000e332  mov     rcx, r8
0x18000e335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e33a  mov     rdx, [rdi]; struct __POSITION *
0x18000e33d  mov     rcx, rdi; this
0x18000e340  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18000e345  mov     r8, rax
0x18000e348  test    rax, rax
0x18000e34b  jnz     short loc_18000E326
0x18000e34d  mov     rcx, [rbx+120h]; void *
0x18000e354  test    rcx, rcx
0x18000e357  jz      short loc_18000E369
0x18000e359  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e35e  mov     qword ptr [rbx+120h], 0
0x18000e369  mov     rcx, rdi; this
0x18000e36c  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x18000e371  lea     rcx, [rbx+198h]; this
0x18000e378  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x18000e37d  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x18000e384  call    cs:__imp_DeleteCriticalSection
0x18000e38a  lea     rax, ??_7CPersistStream@@6B@; const CPersistStream::`vftable'
0x18000e391  mov     rcx, rbx; this
0x18000e394  mov     [rbx+0A0h], rax
0x18000e39b  mov     rbx, [rsp+28h+arg_0]
0x18000e3a0  add     rsp, 20h
0x18000e3a4  pop     rdi
0x18000e3a5  jmp     ??1CBaseFilter@@UEAA@XZ; CBaseFilter::~CBaseFilter(void)
```
