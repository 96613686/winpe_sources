# NDownLevelCrew::TWorkCrew::~TWorkCrew(void)

- ea: `0x14005c258`
- end: `0x14005c306`
- name: `??1TWorkCrew@NDownLevelCrew@@UEAA@XZ`
- size: `174`
- prototype: `void __fastcall(PVOID this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14005c350`

## callees

- `0x14005c208`
- `0x14005c258`
- `0x14005c824`
- `0x14005cbf0`

## import_xrefs

- `KERNEL32!DeleteTimerQueueEx` at `0x14005c29b`
- `KERNEL32!DeleteTimerQueueEx` at `0x14005c29b`
- `KERNEL32!CloseHandle` at `0x14005c2ad`
- `KERNEL32!CloseHandle` at `0x14005c2bf`
- `KERNEL32!CloseHandle` at `0x14005c2ad`
- `KERNEL32!CloseHandle` at `0x14005c2bf`
- `KERNEL32!DeleteCriticalSection` at `0x14005c2e4`
- `KERNEL32!DeleteCriticalSection` at `0x14005c2e4`

## pseudocode

```c
void __fastcall NDownLevelCrew::TWorkCrew::~TWorkCrew(char *this, void **a2)
{
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &NDownLevelCrew::TWorkCrew::`vftable';
  if ( *((int *)this + 51) >= 0 )
  {
    if ( !*((_DWORD *)this + 42) )
      NDownLevelCrew::TWorkCrew::Shutdown(this, a2);
    NDownLevelCrew::TWorkCrew::FinishCancel(this);
  }
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    DeleteTimerQueueEx(v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v4 = (void *)*((_QWORD *)this + 22);
  if ( v4 )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 23);
  if ( v5 )
    CloseHandle(v5);
  NCoreLibrary::TList<NDownLevelCrew::TWorkItem::TInternalLink>::~TList<NDownLevelCrew::TWorkItem::TInternalLink>((__int64)(this + 128));
  NCoreLibrary::TList<NDownLevelCrew::TWorkItem::TInternalLink>::~TList<NDownLevelCrew::TWorkItem::TInternalLink>((__int64)(this + 88));
  if ( *((int *)this + 20) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(this + 32));
    *((_DWORD *)this + 20) = -2147467259;
  }
  *(_QWORD *)this = &NCoreLibrary::TReferenceCount::`vftable';
}

```

## disassembly

```asm
0x14005c258  mov     [rsp+arg_0], rbx
0x14005c25d  push    rdi
0x14005c25e  sub     rsp, 20h
0x14005c262  mov     rbx, rcx
0x14005c265  lea     rax, ??_7TWorkCrew@NDownLevelCrew@@6B@; const NDownLevelCrew::TWorkCrew::`vftable'
0x14005c26c  mov     [rcx], rax
0x14005c26f  cmp     dword ptr [rcx+0CCh], 0
0x14005c276  jl      short loc_14005C28E
0x14005c278  cmp     dword ptr [rcx+0A8h], 0
0x14005c27f  jnz     short loc_14005C286
0x14005c281  call    ?Shutdown@TWorkCrew@NDownLevelCrew@@QEAAJPEAPEAX@Z; NDownLevelCrew::TWorkCrew::Shutdown(void * *)
0x14005c286  mov     rcx, rbx; this
0x14005c289  call    ?FinishCancel@TWorkCrew@NDownLevelCrew@@AEAAJXZ; NDownLevelCrew::TWorkCrew::FinishCancel(void)
0x14005c28e  mov     rcx, [rbx+18h]; TimerQueue
0x14005c292  test    rcx, rcx
0x14005c295  jz      short loc_14005C2A1
0x14005c297  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x14005c29b  call    cs:__imp_DeleteTimerQueueEx
0x14005c2a1  mov     rcx, [rbx+0B0h]; hObject
0x14005c2a8  test    rcx, rcx
0x14005c2ab  jz      short loc_14005C2B3
0x14005c2ad  call    cs:__imp_CloseHandle
0x14005c2b3  mov     rcx, [rbx+0B8h]; hObject
0x14005c2ba  test    rcx, rcx
0x14005c2bd  jz      short loc_14005C2C5
0x14005c2bf  call    cs:__imp_CloseHandle
0x14005c2c5  lea     rcx, [rbx+80h]
0x14005c2cc  call    ??1?$TList@VTInternalLink@TWorkItem@NDownLevelCrew@@@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TList<NDownLevelCrew::TWorkItem::TInternalLink>::~TList<NDownLevelCrew::TWorkItem::TInternalLink>(void)
0x14005c2d1  lea     rcx, [rbx+58h]
0x14005c2d5  call    ??1?$TList@VTInternalLink@TWorkItem@NDownLevelCrew@@@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TList<NDownLevelCrew::TWorkItem::TInternalLink>::~TList<NDownLevelCrew::TWorkItem::TInternalLink>(void)
0x14005c2da  cmp     dword ptr [rbx+50h], 0
0x14005c2de  jl      short loc_14005C2F1
0x14005c2e0  lea     rcx, [rbx+20h]; lpCriticalSection
0x14005c2e4  call    cs:__imp_DeleteCriticalSection
0x14005c2ea  mov     dword ptr [rbx+50h], 80004005h
0x14005c2f1  lea     rax, ??_7TReferenceCount@NCoreLibrary@@6B@; const NCoreLibrary::TReferenceCount::`vftable'
0x14005c2f8  mov     [rbx], rax
0x14005c2fb  mov     rbx, [rsp+28h+arg_0]
0x14005c300  add     rsp, 20h
0x14005c304  pop     rdi
0x14005c305  retn
```
