# SCHEDULER::~SCHEDULER(void)

- ea: `0x18001fd2c`
- end: `0x18001fd73`
- name: `??1SCHEDULER@@AEAA@XZ`
- size: `71`
- prototype: `void __fastcall(SCHEDULER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001fd7c`

## callees

- `0x18001fd2c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001fd59`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001fd59`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueEx` at `0x18001fd42`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueEx` at `0x18001fd42`

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
0x18001fd2c  push    rbx
0x18001fd2e  sub     rsp, 20h
0x18001fd32  mov     rbx, rcx
0x18001fd35  mov     rcx, [rcx+8]; TimerQueue
0x18001fd39  test    rcx, rcx
0x18001fd3c  jz      short loc_18001FD50
0x18001fd3e  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001fd42  call    cs:__imp_DeleteTimerQueueEx
0x18001fd48  mov     qword ptr [rbx+8], 0
0x18001fd50  mov     rcx, [rbx+10h]; hLibModule
0x18001fd54  test    rcx, rcx
0x18001fd57  jz      short loc_18001FD67
0x18001fd59  call    cs:__imp_FreeLibrary
0x18001fd5f  mov     qword ptr [rbx+10h], 0
0x18001fd67  mov     dword ptr [rbx], 78454353h
0x18001fd6d  add     rsp, 20h
0x18001fd71  pop     rbx
0x18001fd72  retn
```
