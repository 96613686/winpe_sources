# VMR9::CImageSync::~CImageSync(void)

- ea: `0x1800e70f8`
- end: `0x1800e71db`
- name: `??1CImageSync@VMR9@@UEAA@XZ`
- size: `227`
- prototype: `void __fastcall(VMR9::CImageSync *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800e71f0`

## callees

- `0x180025158`
- `0x1800e70f8`
- `0x18015e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800e7183`
- `KERNEL32!DeleteCriticalSection` at `0x1800e7196`
- `KERNEL32!DeleteCriticalSection` at `0x1800e71a6`
- `KERNEL32!DeleteCriticalSection` at `0x1800e7183`
- `KERNEL32!DeleteCriticalSection` at `0x1800e7196`
- `KERNEL32!DeleteCriticalSection` at `0x1800e71a6`
- `KERNEL32!CloseHandle` at `0x1800e7140`
- `KERNEL32!CloseHandle` at `0x1800e7140`

## pseudocode

```c
void __fastcall VMR9::CImageSync::~CImageSync(VMR9::CImageSync *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &VMR9::CImageSync::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &VMR9::CImageSync::`vftable'{for `VMR9::IImageSync9'};
  *((_QWORD *)this + 4) = &VMR9::CImageSync::`vftable'{for `VMR9::IImageSyncControl9'};
  *((_QWORD *)this + 5) = &VMR9::CImageSync::`vftable'{for `IPresenterStatistics'};
  *((_QWORD *)this + 6) = &CImageSync::`vftable'{for `IQualProp'};
  v2 = (void *)*((_QWORD *)this + 10);
  if ( v2 )
    CloseHandle(v2);
  v3 = *((_QWORD *)this + 25);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 28);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 432));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 4);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 3);
  CAMEvent::~CAMEvent((VMR9::CImageSync *)((char *)this + 72));
  CAMEvent::~CAMEvent((VMR9::CImageSync *)((char *)this + 64));
  CAMEvent::~CAMEvent((VMR9::CImageSync *)((char *)this + 56));
  _InterlockedDecrement(&CBaseObject::m_cObjects);
}

```

## disassembly

```asm
0x1800e70f8  push    rbx
0x1800e70fa  sub     rsp, 20h
0x1800e70fe  lea     rax, ??_7CImageSync@VMR9@@6BCUnknown@@@; const VMR9::CImageSync::`vftable'{for `CUnknown'}
0x1800e7105  mov     rbx, rcx
0x1800e7108  mov     [rcx], rax
0x1800e710b  lea     rax, ??_7CImageSync@VMR9@@6BIImageSync9@1@@; const VMR9::CImageSync::`vftable'{for `VMR9::IImageSync9'}
0x1800e7112  mov     [rcx+18h], rax
0x1800e7116  lea     rax, ??_7CImageSync@VMR9@@6BIImageSyncControl9@1@@; const VMR9::CImageSync::`vftable'{for `VMR9::IImageSyncControl9'}
0x1800e711d  mov     [rcx+20h], rax
0x1800e7121  lea     rax, ??_7CImageSync@VMR9@@6BIPresenterStatistics@@@; const VMR9::CImageSync::`vftable'{for `IPresenterStatistics'}
0x1800e7128  mov     [rcx+28h], rax
0x1800e712c  lea     rax, ??_7CImageSync@@6BIQualProp@@@; const CImageSync::`vftable'{for `IQualProp'}
0x1800e7133  mov     [rcx+30h], rax
0x1800e7137  mov     rcx, [rcx+50h]; hObject
0x1800e713b  test    rcx, rcx
0x1800e713e  jz      short loc_1800E714C
0x1800e7140  call    cs:__imp_CloseHandle
0x1800e7147  nop     dword ptr [rax+rax+00h]
0x1800e714c  mov     rcx, [rbx+0C8h]
0x1800e7153  test    rcx, rcx
0x1800e7156  jz      short loc_1800E7164
0x1800e7158  mov     rax, [rcx]
0x1800e715b  mov     rax, [rax+10h]
0x1800e715f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7164  mov     rcx, [rbx+0E0h]
0x1800e716b  test    rcx, rcx
0x1800e716e  jz      short loc_1800E717C
0x1800e7170  mov     rax, [rcx]
0x1800e7173  mov     rax, [rax+10h]
0x1800e7177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e717c  lea     rcx, [rbx+1B0h]; lpCriticalSection
0x1800e7183  call    cs:__imp_DeleteCriticalSection
0x1800e718a  nop     dword ptr [rax+rax+00h]
0x1800e718f  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x1800e7196  call    cs:__imp_DeleteCriticalSection
0x1800e719d  nop     dword ptr [rax+rax+00h]
0x1800e71a2  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800e71a6  call    cs:__imp_DeleteCriticalSection
0x1800e71ad  nop     dword ptr [rax+rax+00h]
0x1800e71b2  lea     rcx, [rbx+48h]; this
0x1800e71b6  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x1800e71bb  lea     rcx, [rbx+40h]; this
0x1800e71bf  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x1800e71c4  lea     rcx, [rbx+38h]; this
0x1800e71c8  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x1800e71cd  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800e71d4  add     rsp, 20h
0x1800e71d8  pop     rbx
0x1800e71d9  retn
```
