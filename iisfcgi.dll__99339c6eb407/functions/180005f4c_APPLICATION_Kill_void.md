# APPLICATION::Kill(void)

- ea: `0x180005f4c`
- end: `0x18000602e`
- name: `?Kill@APPLICATION@@QEAAXXZ`
- size: `226`
- prototype: `void __fastcall(APPLICATION *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000794c`
- `0x180008164`
- `0x1800086bc`

## callees

- `0x180005030`
- `0x180005f4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fe6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005fbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000600d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000601b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000600d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000601b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005ff7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005ff7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180005fdc`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180005fdc`

## pseudocode

```c
void __fastcall APPLICATION::Kill(APPLICATION *this)
{
  void *v2; // r14
  void *v3; // r15
  void *v4; // rbp
  void *v5; // rsi

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v2 = (void *)*((_QWORD *)this + 27);
  v3 = (void *)*((_QWORD *)this + 28);
  v4 = (void *)*((_QWORD *)this + 29);
  v5 = (void *)*((_QWORD *)this + 30);
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_DWORD *)this + 63) = -1;
  *((_QWORD *)this + 30) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( v3 && !DeleteTimerQueueTimer(*(HANDLE *)(*((_QWORD *)this + 12) + 152LL), v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    GetLastError();
  if ( v2 )
  {
    UnregisterWaitEx(v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    APPLICATION::DereferenceApplication(this);
  }
  if ( v4 )
    CloseHandle(v4);
  if ( v5 )
    CloseHandle(v5);
}

```

## disassembly

```asm
0x180005f4c  push    rbx
0x180005f4e  push    rbp
0x180005f4f  push    rsi
0x180005f50  push    rdi
0x180005f51  push    r14
0x180005f53  push    r15
0x180005f55  sub     rsp, 28h
0x180005f59  mov     rdi, rcx
0x180005f5c  add     rcx, 70h ; 'p'; lpCriticalSection
0x180005f60  call    cs:__imp_EnterCriticalSection
0x180005f66  mov     r14, [rdi+0D8h]
0x180005f6d  lea     rcx, [rdi+70h]; lpCriticalSection
0x180005f71  mov     r15, [rdi+0E0h]
0x180005f78  mov     rbp, [rdi+0E8h]
0x180005f7f  mov     rsi, [rdi+0F0h]
0x180005f86  mov     qword ptr [rdi+0D8h], 0
0x180005f91  mov     qword ptr [rdi+0E0h], 0
0x180005f9c  mov     qword ptr [rdi+0E8h], 0
0x180005fa7  mov     dword ptr [rdi+0FCh], 0FFFFFFFFh
0x180005fb1  mov     qword ptr [rdi+0F0h], 0
0x180005fbc  call    cs:__imp_LeaveCriticalSection
0x180005fc2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005fc6  test    r15, r15
0x180005fc9  jz      short loc_180005FEC
0x180005fcb  mov     rcx, [rdi+60h]
0x180005fcf  mov     r8, rbx; CompletionEvent
0x180005fd2  mov     rdx, r15; Timer
0x180005fd5  mov     rcx, [rcx+98h]; TimerQueue
0x180005fdc  call    cs:__imp_DeleteTimerQueueTimer
0x180005fe2  test    eax, eax
0x180005fe4  jnz     short loc_180005FEC
0x180005fe6  call    cs:__imp_GetLastError
0x180005fec  test    r14, r14
0x180005fef  jz      short loc_180006005
0x180005ff1  mov     rdx, rbx; CompletionEvent
0x180005ff4  mov     rcx, r14; WaitHandle
0x180005ff7  call    cs:__imp_UnregisterWaitEx
0x180005ffd  mov     rcx, rdi; this
0x180006000  call    ?DereferenceApplication@APPLICATION@@QEAAXXZ; APPLICATION::DereferenceApplication(void)
0x180006005  test    rbp, rbp
0x180006008  jz      short loc_180006013
0x18000600a  mov     rcx, rbp; hObject
0x18000600d  call    cs:__imp_CloseHandle
0x180006013  test    rsi, rsi
0x180006016  jz      short loc_180006021
0x180006018  mov     rcx, rsi; hObject
0x18000601b  call    cs:__imp_CloseHandle
0x180006021  add     rsp, 28h
0x180006025  pop     r15
0x180006027  pop     r14
0x180006029  pop     rdi
0x18000602a  pop     rsi
0x18000602b  pop     rbp
0x18000602c  pop     rbx
0x18000602d  retn
```
