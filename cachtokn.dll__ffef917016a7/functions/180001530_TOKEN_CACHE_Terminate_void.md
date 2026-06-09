# TOKEN_CACHE::Terminate(void)

- ea: `0x180001530`
- end: `0x1800015a6`
- name: `?Terminate@TOKEN_CACHE@@QEAAXXZ`
- size: `118`
- prototype: `void __fastcall(TOKEN_CACHE *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180001fd8`
- `0x180002470`

## callees

- `0x180001530`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001562`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001562`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001575`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001575`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180001591`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180001591`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000154f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000154f`

## pseudocode

```c
void __fastcall TOKEN_CACHE::Terminate(TOKEN_CACHE *this)
{
  void *v2; // rcx
  void *v3; // rcx
  HKEY v4; // rcx
  void *v5; // rdx

  v2 = (void *)*((_QWORD *)this + 12);
  if ( v2 )
  {
    UnregisterWaitEx(v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 12) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 11);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 11) = 0;
  }
  v4 = (HKEY)*((_QWORD *)this + 10);
  if ( v4 )
  {
    RegCloseKey(v4);
    *((_QWORD *)this + 10) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 9);
  if ( v5 )
  {
    DeleteTimerQueueTimer(0, v5, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 9) = 0;
  }
}

```

## disassembly

```asm
0x180001530  mov     [rsp+arg_0], rbx
0x180001535  push    rdi
0x180001536  sub     rsp, 20h
0x18000153a  mov     rbx, rcx
0x18000153d  xor     edi, edi
0x18000153f  mov     rcx, [rcx+60h]; WaitHandle
0x180001543  test    rcx, rcx
0x180001546  jz      short loc_180001559
0x180001548  mov     rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000154f  call    cs:__imp_UnregisterWaitEx
0x180001555  mov     [rbx+60h], rdi
0x180001559  mov     rcx, [rbx+58h]; hObject
0x18000155d  test    rcx, rcx
0x180001560  jz      short loc_18000156C
0x180001562  call    cs:__imp_CloseHandle
0x180001568  mov     [rbx+58h], rdi
0x18000156c  mov     rcx, [rbx+50h]; hKey
0x180001570  test    rcx, rcx
0x180001573  jz      short loc_18000157F
0x180001575  call    cs:__imp_RegCloseKey
0x18000157b  mov     [rbx+50h], rdi
0x18000157f  mov     rdx, [rbx+48h]; Timer
0x180001583  test    rdx, rdx
0x180001586  jz      short loc_18000159B
0x180001588  xor     ecx, ecx; TimerQueue
0x18000158a  mov     r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180001591  call    cs:__imp_DeleteTimerQueueTimer
0x180001597  mov     [rbx+48h], rdi
0x18000159b  mov     rbx, [rsp+28h+arg_0]
0x1800015a0  add     rsp, 20h
0x1800015a4  pop     rdi
0x1800015a5  retn
```
