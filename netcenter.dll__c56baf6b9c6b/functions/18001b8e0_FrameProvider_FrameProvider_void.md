# FrameProvider::~FrameProvider(void)

- ea: `0x18001b8e0`
- end: `0x18001b991`
- name: `??1FrameProvider@@MEAA@XZ`
- size: `177`
- prototype: `void __fastcall(FrameProvider *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001b9a0`

## callees

- `0x18001b8e0`
- `0x180023010`

## import_xrefs

- `DUI70!UnInitThread` at `0x18001b968`
- `DUI70!UnInitThread` at `0x18001b968`
- `DUI70!UnInitProcessPriv` at `0x18001b975`
- `DUI70!UnInitProcessPriv` at `0x18001b975`
- `DUI70!??1XProvider@DirectUI@@UEAA@XZ` at `0x18001b98a`

## pseudocode

```c
void __fastcall FrameProvider::~FrameProvider(FrameProvider *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &FrameProvider::`vftable'{for `DirectUI::XProvider'};
  *((_QWORD *)this + 5) = &FrameProvider::`vftable'{for `IDUIElementProviderInit'};
  *((_QWORD *)this + 6) = &FrameProvider::`vftable'{for `IFrameNotificationClient'};
  *((_QWORD *)this + 7) = &FrameProvider::`vftable'{for `IFrameShellViewClient'};
  *((_QWORD *)this + 8) = &FrameProvider::`vftable'{for `IObjectWithSite'};
  *((_QWORD *)this + 9) = &FrameProvider::`vftable'{for `IServiceProvider'};
  v2 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 78);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
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
0x18001b8e0  push    rbx
0x18001b8e2  sub     rsp, 20h
0x18001b8e6  lea     rax, ??_7FrameProvider@@6BXProvider@DirectUI@@@; const FrameProvider::`vftable'{for `DirectUI::XProvider'}
0x18001b8ed  mov     rbx, rcx
0x18001b8f0  mov     [rcx], rax
0x18001b8f3  lea     rax, ??_7FrameProvider@@6BIDUIElementProviderInit@@@; const FrameProvider::`vftable'{for `IDUIElementProviderInit'}
0x18001b8fa  mov     [rcx+28h], rax
0x18001b8fe  lea     rax, ??_7FrameProvider@@6BIFrameNotificationClient@@@; const FrameProvider::`vftable'{for `IFrameNotificationClient'}
0x18001b905  mov     [rcx+30h], rax
0x18001b909  lea     rax, ??_7FrameProvider@@6BIFrameShellViewClient@@@; const FrameProvider::`vftable'{for `IFrameShellViewClient'}
0x18001b910  mov     [rcx+38h], rax
0x18001b914  lea     rax, ??_7FrameProvider@@6BIObjectWithSite@@@; const FrameProvider::`vftable'{for `IObjectWithSite'}
0x18001b91b  mov     [rcx+40h], rax
0x18001b91f  lea     rax, ??_7FrameProvider@@6BIServiceProvider@@@; const FrameProvider::`vftable'{for `IServiceProvider'}
0x18001b926  mov     [rcx+48h], rax
0x18001b92a  mov     rcx, [rcx+50h]
0x18001b92e  mov     qword ptr [rbx+50h], 0
0x18001b936  test    rcx, rcx
0x18001b939  jz      short loc_18001B947
0x18001b93b  mov     rax, [rcx]
0x18001b93e  mov     rax, [rax+10h]
0x18001b942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b947  mov     rcx, [rbx+270h]
0x18001b94e  test    rcx, rcx
0x18001b951  jz      short loc_18001B95F
0x18001b953  mov     rax, [rcx]
0x18001b956  mov     rax, [rax+10h]
0x18001b95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b95f  cmp     dword ptr [rbx+268h], 0
0x18001b966  jl      short loc_18001B97B
0x18001b968  call    cs:__imp_UnInitThread
0x18001b96e  lea     rcx, __ImageBase
0x18001b975  call    cs:__imp_UnInitProcessPriv
0x18001b97b  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x18001b982  mov     rcx, rbx
0x18001b985  add     rsp, 20h
0x18001b989  pop     rbx
0x18001b98a  jmp     cs:__imp_??1XProvider@DirectUI@@UEAA@XZ; DirectUI::XProvider::~XProvider(void)
```
