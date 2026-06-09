# CChallengeContext::~CChallengeContext(void)

- ea: `0x180021cf4`
- end: `0x180021dea`
- name: `??1CChallengeContext@@IEAA@XZ`
- size: `246`
- prototype: `void __fastcall(CChallengeContext *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180021cb0`

## callees

- `0x180021cf4`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021dcc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021dcc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021de3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021d14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021d14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021d22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021d22`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180021d62`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180021dbf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180021d62`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180021dbf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180021d55`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180021db2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180021d55`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180021db2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021d3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021d9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021d3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021d9e`

## pseudocode

```c
void __fastcall CChallengeContext::~CChallengeContext(CChallengeContext *this)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rcx
  struct _TP_WAIT *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  void *v8; // rcx
  struct _TP_WAIT *v9; // rcx

  *(_QWORD *)this = &CChallengeContext::`vftable';
  v2 = (void *)*((_QWORD *)this + 9);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    *((_QWORD *)this + 9) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 34);
  if ( v4 )
    CloseHandle(v4);
  v5 = (struct _TP_WAIT *)*((_QWORD *)this + 35);
  if ( v5 )
  {
    WaitForThreadpoolWaitCallbacks(v5, 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 35));
  }
  v6 = *((_QWORD *)this + 7);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 8);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = (void *)*((_QWORD *)this + 25);
  if ( v8 )
    CloseHandle(v8);
  v9 = (struct _TP_WAIT *)*((_QWORD *)this + 26);
  if ( v9 )
  {
    WaitForThreadpoolWaitCallbacks(v9, 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 26));
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
}

```

## disassembly

```asm
0x180021cf4  mov     [rsp+arg_0], rbx
0x180021cf9  push    rdi
0x180021cfa  sub     rsp, 20h
0x180021cfe  mov     rbx, rcx
0x180021d01  lea     rax, ??_7CChallengeContext@@6B@; const CChallengeContext::`vftable'
0x180021d08  mov     [rcx], rax
0x180021d0b  mov     rdi, [rcx+48h]
0x180021d0f  test    rdi, rdi
0x180021d12  jz      short loc_180021D30
0x180021d14  call    cs:__imp_GetProcessHeap
0x180021d1a  mov     r8, rdi; lpMem
0x180021d1d  xor     edx, edx; dwFlags
0x180021d1f  mov     rcx, rax; hHeap
0x180021d22  call    cs:__imp_HeapFree
0x180021d28  mov     qword ptr [rbx+48h], 0
0x180021d30  mov     rcx, [rbx+110h]; hObject
0x180021d37  test    rcx, rcx
0x180021d3a  jz      short loc_180021D42
0x180021d3c  call    cs:__imp_CloseHandle
0x180021d42  mov     rcx, [rbx+118h]; pwa
0x180021d49  mov     edi, 1
0x180021d4e  test    rcx, rcx
0x180021d51  jz      short loc_180021D68
0x180021d53  mov     edx, edi; fCancelPendingCallbacks
0x180021d55  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180021d5b  mov     rcx, [rbx+118h]; pwa
0x180021d62  call    cs:__imp_CloseThreadpoolWait
0x180021d68  mov     rcx, [rbx+38h]
0x180021d6c  test    rcx, rcx
0x180021d6f  jz      short loc_180021D7D
0x180021d71  mov     rax, [rcx]
0x180021d74  mov     rax, [rax+10h]
0x180021d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d7d  mov     rcx, [rbx+40h]
0x180021d81  test    rcx, rcx
0x180021d84  jz      short loc_180021D92
0x180021d86  mov     rax, [rcx]
0x180021d89  mov     rax, [rax+10h]
0x180021d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d92  mov     rcx, [rbx+0C8h]; hObject
0x180021d99  test    rcx, rcx
0x180021d9c  jz      short loc_180021DA4
0x180021d9e  call    cs:__imp_CloseHandle
0x180021da4  mov     rcx, [rbx+0D0h]; pwa
0x180021dab  test    rcx, rcx
0x180021dae  jz      short loc_180021DC5
0x180021db0  mov     edx, edi; fCancelPendingCallbacks
0x180021db2  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180021db8  mov     rcx, [rbx+0D0h]; pwa
0x180021dbf  call    cs:__imp_CloseThreadpoolWait
0x180021dc5  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x180021dcc  call    cs:__imp_DeleteCriticalSection
0x180021dd2  lea     rcx, [rbx+128h]
0x180021dd9  mov     rbx, [rsp+28h+arg_0]
0x180021dde  add     rsp, 20h
0x180021de2  pop     rdi
0x180021de3  jmp     cs:__imp_DeleteCriticalSection
```
