# CImageSync::~CImageSync(void)

- ea: `0x1800c0458`
- end: `0x1800c053b`
- name: `??1CImageSync@@UEAA@XZ`
- size: `227`
- prototype: `void __fastcall(CImageSync *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800c0550`

## callees

- `0x180025158`
- `0x1800c0458`
- `0x18015e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800c04e3`
- `KERNEL32!DeleteCriticalSection` at `0x1800c04f6`
- `KERNEL32!DeleteCriticalSection` at `0x1800c0506`
- `KERNEL32!DeleteCriticalSection` at `0x1800c04e3`
- `KERNEL32!DeleteCriticalSection` at `0x1800c04f6`
- `KERNEL32!DeleteCriticalSection` at `0x1800c0506`
- `KERNEL32!CloseHandle` at `0x1800c04a0`
- `KERNEL32!CloseHandle` at `0x1800c04a0`

## pseudocode

```c
void __fastcall CImageSync::~CImageSync(CImageSync *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &CImageSync::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CImageSync::`vftable'{for `IImageSync'};
  *((_QWORD *)this + 4) = &CImageSync::`vftable'{for `IImageSyncControl'};
  *((_QWORD *)this + 5) = &CImageSync::`vftable'{for `IPresenterStatistics'};
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
  CAMEvent::~CAMEvent((CImageSync *)((char *)this + 72));
  CAMEvent::~CAMEvent((CImageSync *)((char *)this + 64));
  CAMEvent::~CAMEvent((CImageSync *)((char *)this + 56));
  _InterlockedDecrement(&CBaseObject::m_cObjects);
}

```

## disassembly

```asm
0x1800c0458  push    rbx
0x1800c045a  sub     rsp, 20h
0x1800c045e  lea     rax, ??_7CImageSync@@6BCUnknown@@@; const CImageSync::`vftable'{for `CUnknown'}
0x1800c0465  mov     rbx, rcx
0x1800c0468  mov     [rcx], rax
0x1800c046b  lea     rax, ??_7CImageSync@@6BIImageSync@@@; const CImageSync::`vftable'{for `IImageSync'}
0x1800c0472  mov     [rcx+18h], rax
0x1800c0476  lea     rax, ??_7CImageSync@@6BIImageSyncControl@@@; const CImageSync::`vftable'{for `IImageSyncControl'}
0x1800c047d  mov     [rcx+20h], rax
0x1800c0481  lea     rax, ??_7CImageSync@@6BIPresenterStatistics@@@; const CImageSync::`vftable'{for `IPresenterStatistics'}
0x1800c0488  mov     [rcx+28h], rax
0x1800c048c  lea     rax, ??_7CImageSync@@6BIQualProp@@@; const CImageSync::`vftable'{for `IQualProp'}
0x1800c0493  mov     [rcx+30h], rax
0x1800c0497  mov     rcx, [rcx+50h]; hObject
0x1800c049b  test    rcx, rcx
0x1800c049e  jz      short loc_1800C04AC
0x1800c04a0  call    cs:__imp_CloseHandle
0x1800c04a7  nop     dword ptr [rax+rax+00h]
0x1800c04ac  mov     rcx, [rbx+0C8h]
0x1800c04b3  test    rcx, rcx
0x1800c04b6  jz      short loc_1800C04C4
0x1800c04b8  mov     rax, [rcx]
0x1800c04bb  mov     rax, [rax+10h]
0x1800c04bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c04c4  mov     rcx, [rbx+0E0h]
0x1800c04cb  test    rcx, rcx
0x1800c04ce  jz      short loc_1800C04DC
0x1800c04d0  mov     rax, [rcx]
0x1800c04d3  mov     rax, [rax+10h]
0x1800c04d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c04dc  lea     rcx, [rbx+1B0h]; lpCriticalSection
0x1800c04e3  call    cs:__imp_DeleteCriticalSection
0x1800c04ea  nop     dword ptr [rax+rax+00h]
0x1800c04ef  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x1800c04f6  call    cs:__imp_DeleteCriticalSection
0x1800c04fd  nop     dword ptr [rax+rax+00h]
0x1800c0502  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800c0506  call    cs:__imp_DeleteCriticalSection
0x1800c050d  nop     dword ptr [rax+rax+00h]
0x1800c0512  lea     rcx, [rbx+48h]; this
0x1800c0516  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x1800c051b  lea     rcx, [rbx+40h]; this
0x1800c051f  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x1800c0524  lea     rcx, [rbx+38h]; this
0x1800c0528  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x1800c052d  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800c0534  add     rsp, 20h
0x1800c0538  pop     rbx
0x1800c0539  retn
```
