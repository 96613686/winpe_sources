# FrameProvider::~FrameProvider(void)

- ea: `0x18002dc64`
- end: `0x18002dd01`
- name: `??1FrameProvider@@MEAA@XZ`
- size: `157`
- prototype: `void __fastcall(FrameProvider *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002dd10`

## callees

- `0x18001f61c`
- `0x18002dc64`
- `0x180032010`

## import_xrefs

- `DUI70!UnInitProcessPriv` at `0x18002dce5`
- `DUI70!UnInitProcessPriv` at `0x18002dce5`
- `DUI70!UnInitThread` at `0x18002dcd8`
- `DUI70!UnInitThread` at `0x18002dcd8`
- `DUI70!??1XProvider@DirectUI@@UEAA@XZ` at `0x18002dcfa`

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
  _InterlockedDecrement(&g_cRefCount);
  DirectUI::XProvider::~XProvider(this);
}

```

## disassembly

```asm
0x18002dc64  push    rbx
0x18002dc66  sub     rsp, 20h
0x18002dc6a  lea     rax, ??_7FrameProvider@@6BXProvider@DirectUI@@@; const FrameProvider::`vftable'{for `DirectUI::XProvider'}
0x18002dc71  mov     rbx, rcx
0x18002dc74  mov     [rcx], rax
0x18002dc77  lea     rax, ??_7FrameProvider@@6BIDUIElementProviderInit@@@; const FrameProvider::`vftable'{for `IDUIElementProviderInit'}
0x18002dc7e  mov     [rcx+28h], rax
0x18002dc82  lea     rax, ??_7FrameProvider@@6BIFrameNotificationClient@@@; const FrameProvider::`vftable'{for `IFrameNotificationClient'}
0x18002dc89  mov     [rcx+30h], rax
0x18002dc8d  lea     rax, ??_7FrameProvider@@6BIFrameShellViewClient@@@; const FrameProvider::`vftable'{for `IFrameShellViewClient'}
0x18002dc94  mov     [rcx+38h], rax
0x18002dc98  lea     rax, ??_7FrameProvider@@6BIObjectWithSite@@@; const FrameProvider::`vftable'{for `IObjectWithSite'}
0x18002dc9f  mov     [rcx+40h], rax
0x18002dca3  lea     rax, ??_7FrameProvider@@6BIServiceProvider@@@; const FrameProvider::`vftable'{for `IServiceProvider'}
0x18002dcaa  mov     [rcx+48h], rax
0x18002dcae  add     rcx, 50h ; 'P'
0x18002dcb2  call    ??$SafeRelease@UIUnknown@@@@YAXPEAPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown * *)
0x18002dcb7  mov     rcx, [rbx+270h]
0x18002dcbe  test    rcx, rcx
0x18002dcc1  jz      short loc_18002DCCF
0x18002dcc3  mov     rax, [rcx]
0x18002dcc6  mov     rax, [rax+10h]
0x18002dcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dccf  cmp     dword ptr [rbx+268h], 0
0x18002dcd6  jl      short loc_18002DCEB
0x18002dcd8  call    cs:__imp_UnInitThread
0x18002dcde  lea     rcx, __ImageBase
0x18002dce5  call    cs:__imp_UnInitProcessPriv
0x18002dceb  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x18002dcf2  mov     rcx, rbx
0x18002dcf5  add     rsp, 20h
0x18002dcf9  pop     rbx
0x18002dcfa  jmp     cs:__imp_??1XProvider@DirectUI@@UEAA@XZ; DirectUI::XProvider::~XProvider(void)
```
