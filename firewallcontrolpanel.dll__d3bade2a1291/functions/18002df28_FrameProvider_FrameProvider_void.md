# FrameProvider::~FrameProvider(void)

- ea: `0x18002df28`
- end: `0x18002dfd9`
- name: `??1FrameProvider@@MEAA@XZ`
- size: `177`
- prototype: `void __fastcall(FrameProvider *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002dfe0`

## callees

- `0x18002df28`
- `0x180032010`

## import_xrefs

- `DUI70!UnInitThread` at `0x18002dfb0`
- `DUI70!UnInitThread` at `0x18002dfb0`
- `DUI70!UnInitProcessPriv` at `0x18002dfbd`
- `DUI70!UnInitProcessPriv` at `0x18002dfbd`
- `DUI70!??1XProvider@DirectUI@@UEAA@XZ` at `0x18002dfd2`

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
0x18002df28  push    rbx
0x18002df2a  sub     rsp, 20h
0x18002df2e  lea     rax, ??_7FrameProvider@@6BXProvider@DirectUI@@@; const FrameProvider::`vftable'{for `DirectUI::XProvider'}
0x18002df35  mov     rbx, rcx
0x18002df38  mov     [rcx], rax
0x18002df3b  lea     rax, ??_7FrameProvider@@6BIDUIElementProviderInit@@@; const FrameProvider::`vftable'{for `IDUIElementProviderInit'}
0x18002df42  mov     [rcx+28h], rax
0x18002df46  lea     rax, ??_7FrameProvider@@6BIFrameNotificationClient@@@; const FrameProvider::`vftable'{for `IFrameNotificationClient'}
0x18002df4d  mov     [rcx+30h], rax
0x18002df51  lea     rax, ??_7FrameProvider@@6BIFrameShellViewClient@@@; const FrameProvider::`vftable'{for `IFrameShellViewClient'}
0x18002df58  mov     [rcx+38h], rax
0x18002df5c  lea     rax, ??_7FrameProvider@@6BIObjectWithSite@@@; const FrameProvider::`vftable'{for `IObjectWithSite'}
0x18002df63  mov     [rcx+40h], rax
0x18002df67  lea     rax, ??_7FrameProvider@@6BIServiceProvider@@@; const FrameProvider::`vftable'{for `IServiceProvider'}
0x18002df6e  mov     [rcx+48h], rax
0x18002df72  mov     rcx, [rcx+50h]
0x18002df76  mov     qword ptr [rbx+50h], 0
0x18002df7e  test    rcx, rcx
0x18002df81  jz      short loc_18002DF8F
0x18002df83  mov     rax, [rcx]
0x18002df86  mov     rax, [rax+10h]
0x18002df8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df8f  mov     rcx, [rbx+270h]
0x18002df96  test    rcx, rcx
0x18002df99  jz      short loc_18002DFA7
0x18002df9b  mov     rax, [rcx]
0x18002df9e  mov     rax, [rax+10h]
0x18002dfa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfa7  cmp     dword ptr [rbx+268h], 0
0x18002dfae  jl      short loc_18002DFC3
0x18002dfb0  call    cs:__imp_UnInitThread
0x18002dfb6  lea     rcx, __ImageBase
0x18002dfbd  call    cs:__imp_UnInitProcessPriv
0x18002dfc3  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x18002dfca  mov     rcx, rbx
0x18002dfcd  add     rsp, 20h
0x18002dfd1  pop     rbx
0x18002dfd2  jmp     cs:__imp_??1XProvider@DirectUI@@UEAA@XZ; DirectUI::XProvider::~XProvider(void)
```
