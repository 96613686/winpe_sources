# SCHEDULER::~SCHEDULER(void)

- ea: `0x180021074`
- end: `0x1800210c8`
- name: `??1SCHEDULER@@AEAA@XZ`
- size: `84`
- prototype: `void __fastcall(SCHEDULER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800210d0`

## callees

- `0x180021074`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800210a7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800210a7`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueEx` at `0x18002108a`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueEx` at `0x18002108a`

## pseudocode

```c
void __fastcall SCHEDULER::~SCHEDULER(SCHEDULER *this)
{
  void *v2; // rcx
  HMODULE v3; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    DeleteTimerQueueEx(v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = (HMODULE)*((_QWORD *)this + 2);
  if ( v3 )
  {
    FreeLibrary(v3);
    *((_QWORD *)this + 2) = 0;
  }
  *(_DWORD *)this = 2017805139;
}

```

## disassembly

```asm
0x180021074  push    rbx
0x180021076  sub     rsp, 20h
0x18002107a  mov     rbx, rcx
0x18002107d  mov     rcx, [rcx+8]; TimerQueue
0x180021081  test    rcx, rcx
0x180021084  jz      short loc_18002109E
0x180021086  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002108a  call    cs:__imp_DeleteTimerQueueEx
0x180021091  nop     dword ptr [rax+rax+00h]
0x180021096  mov     qword ptr [rbx+8], 0
0x18002109e  mov     rcx, [rbx+10h]; hLibModule
0x1800210a2  test    rcx, rcx
0x1800210a5  jz      short loc_1800210BB
0x1800210a7  call    cs:__imp_FreeLibrary
0x1800210ae  nop     dword ptr [rax+rax+00h]
0x1800210b3  mov     qword ptr [rbx+10h], 0
0x1800210bb  mov     dword ptr [rbx], 78454353h
0x1800210c1  add     rsp, 20h
0x1800210c5  pop     rbx
0x1800210c6  retn
```
