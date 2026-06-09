# FrameProvider::~FrameProvider(void)

- ea: `0x1800165a8`
- end: `0x180016645`
- name: `??1FrameProvider@@MEAA@XZ`
- size: `157`
- prototype: `void __fastcall(FrameProvider *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180016650`

## callees

- `0x18000b280`
- `0x1800165a8`
- `0x18001a010`

## import_xrefs

- `DUI70!UnInitProcessPriv` at `0x180016629`
- `DUI70!UnInitProcessPriv` at `0x180016629`
- `DUI70!UnInitThread` at `0x18001661c`
- `DUI70!UnInitThread` at `0x18001661c`
- `DUI70!??1XProvider@DirectUI@@UEAA@XZ` at `0x18001663e`

## pseudocode

```c
void __fastcall FrameProvider::~FrameProvider(FrameProvider *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &FrameProvider::`vftable'{for `DirectUI::XProvider'};
  *((_QWORD *)this + 5) = &FrameProvider::`vftable'{for `IDUIElementProviderInit'};
  *((_QWORD *)this + 6) = &FrameProvider::`vftable'{for `IFrameNotificationClient'};
  *((_QWORD *)this + 7) = &FrameProvider::`vftable'{for `IFrameShellViewClient'};
  *((_QWORD *)this + 8) = &FrameProvider::`vftable'{for `IObjectWithSite'};
  *((_QWORD *)this + 9) = &FrameProvider::`vftable'{for `IServiceProvider'};
  SafeRelease<IUnknown>((char *)this + 80);
  v2 = *((_QWORD *)this + 78);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *((int *)this + 154) >= 0 )
  {
    UnInitThread();
    UnInitProcessPriv(&_ImageBase);
  }
  _InterlockedDecrement(&g_cLocks);
  DirectUI::XProvider::~XProvider(this);
}

```

## disassembly

```asm
0x1800165a8  push    rbx
0x1800165aa  sub     rsp, 20h
0x1800165ae  lea     rax, ??_7FrameProvider@@6BXProvider@DirectUI@@@; const FrameProvider::`vftable'{for `DirectUI::XProvider'}
0x1800165b5  mov     rbx, rcx
0x1800165b8  mov     [rcx], rax
0x1800165bb  lea     rax, ??_7FrameProvider@@6BIDUIElementProviderInit@@@; const FrameProvider::`vftable'{for `IDUIElementProviderInit'}
0x1800165c2  mov     [rcx+28h], rax
0x1800165c6  lea     rax, ??_7FrameProvider@@6BIFrameNotificationClient@@@; const FrameProvider::`vftable'{for `IFrameNotificationClient'}
0x1800165cd  mov     [rcx+30h], rax
0x1800165d1  lea     rax, ??_7FrameProvider@@6BIFrameShellViewClient@@@; const FrameProvider::`vftable'{for `IFrameShellViewClient'}
0x1800165d8  mov     [rcx+38h], rax
0x1800165dc  lea     rax, ??_7FrameProvider@@6BIObjectWithSite@@@; const FrameProvider::`vftable'{for `IObjectWithSite'}
0x1800165e3  mov     [rcx+40h], rax
0x1800165e7  lea     rax, ??_7FrameProvider@@6BIServiceProvider@@@; const FrameProvider::`vftable'{for `IServiceProvider'}
0x1800165ee  mov     [rcx+48h], rax
0x1800165f2  add     rcx, 50h ; 'P'
0x1800165f6  call    ??$SafeRelease@UIUnknown@@@@YAXPEAPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown * *)
0x1800165fb  mov     rcx, [rbx+270h]
0x180016602  test    rcx, rcx
0x180016605  jz      short loc_180016613
0x180016607  mov     rax, [rcx]
0x18001660a  mov     rax, [rax+10h]
0x18001660e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016613  cmp     dword ptr [rbx+268h], 0
0x18001661a  jl      short loc_18001662F
0x18001661c  call    cs:__imp_UnInitThread
0x180016622  lea     rcx, __ImageBase
0x180016629  call    cs:__imp_UnInitProcessPriv
0x18001662f  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x180016636  mov     rcx, rbx
0x180016639  add     rsp, 20h
0x18001663d  pop     rbx
0x18001663e  jmp     cs:__imp_??1XProvider@DirectUI@@UEAA@XZ; DirectUI::XProvider::~XProvider(void)
```
