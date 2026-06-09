# Hns::Client::Notifications::NotificationCallbacks::NotificationContext::~NotificationContext(void)

- ea: `0x180004240`
- end: `0x1800042eb`
- name: `??1NotificationContext@NotificationCallbacks@Notifications@Client@Hns@@QEAA@XZ`
- size: `171`
- prototype: `void __fastcall(Hns::Client::Notifications::NotificationCallbacks::NotificationContext *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e10`
- `0x180004108`
- `0x180004210`
- `0x18000a1d0`
- `0x18000a608`
- `0x18000aaa0`

## callees

- `0x180004240`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000426d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800042af`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000426d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800042af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000427b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800042bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000427b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800042bd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180004284`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800042c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180004284`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800042c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180004256`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180004256`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004298`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004298`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042da`

## pseudocode

```c
void __fastcall Hns::Client::Notifications::NotificationCallbacks::NotificationContext::~NotificationContext(
        Hns::Client::Notifications::NotificationCallbacks::NotificationContext *this)
{
  struct _TP_WORK *v2; // rcx
  struct _TP_WAIT *v3; // rdi
  char *v4; // rcx
  struct _TP_WAIT *v5; // rdi
  char *v6; // rcx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 10);
  if ( v2 )
    CloseThreadpoolWork(v2);
  v3 = (struct _TP_WAIT *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 6), 0, 0);
    WaitForThreadpoolWaitCallbacks(v3, 1);
    CloseThreadpoolWait(v3);
  }
  v4 = (char *)*((_QWORD *)this + 5);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  v5 = (struct _TP_WAIT *)*((_QWORD *)this + 4);
  if ( v5 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 4), 0, 0);
    WaitForThreadpoolWaitCallbacks(v5, 1);
    CloseThreadpoolWait(v5);
  }
  v6 = (char *)*((_QWORD *)this + 3);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
}

```

## disassembly

```asm
0x180004240  mov     [rsp+arg_0], rbx
0x180004245  push    rdi
0x180004246  sub     rsp, 20h
0x18000424a  mov     rbx, rcx
0x18000424d  mov     rcx, [rcx+50h]; pwk
0x180004251  test    rcx, rcx
0x180004254  jz      short loc_18000425C
0x180004256  call    cs:__imp_CloseThreadpoolWork
0x18000425c  mov     rdi, [rbx+30h]
0x180004260  test    rdi, rdi
0x180004263  jz      short loc_18000428A
0x180004265  xor     r8d, r8d; pftTimeout
0x180004268  xor     edx, edx; h
0x18000426a  mov     rcx, rdi; pwa
0x18000426d  call    cs:__imp_SetThreadpoolWait
0x180004273  mov     edx, 1; fCancelPendingCallbacks
0x180004278  mov     rcx, rdi; pwa
0x18000427b  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180004281  mov     rcx, rdi; pwa
0x180004284  call    cs:__imp_CloseThreadpoolWait
0x18000428a  mov     rcx, [rbx+28h]; hObject
0x18000428e  lea     rax, [rcx-1]
0x180004292  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180004296  ja      short loc_18000429E
0x180004298  call    cs:__imp_CloseHandle
0x18000429e  mov     rdi, [rbx+20h]
0x1800042a2  test    rdi, rdi
0x1800042a5  jz      short loc_1800042CC
0x1800042a7  xor     r8d, r8d; pftTimeout
0x1800042aa  xor     edx, edx; h
0x1800042ac  mov     rcx, rdi; pwa
0x1800042af  call    cs:__imp_SetThreadpoolWait
0x1800042b5  mov     edx, 1; fCancelPendingCallbacks
0x1800042ba  mov     rcx, rdi; pwa
0x1800042bd  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800042c3  mov     rcx, rdi; pwa
0x1800042c6  call    cs:__imp_CloseThreadpoolWait
0x1800042cc  mov     rcx, [rbx+18h]; hObject
0x1800042d0  lea     rax, [rcx-1]
0x1800042d4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800042d8  ja      short loc_1800042E0
0x1800042da  call    cs:__imp_CloseHandle
0x1800042e0  mov     rbx, [rsp+28h+arg_0]
0x1800042e5  add     rsp, 20h
0x1800042e9  pop     rdi
0x1800042ea  retn
```
