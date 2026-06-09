# ComputeService::Client::NotificationCallbacks::NotificationContext::~NotificationContext(void)

- ea: `0x180018828`
- end: `0x1800188d3`
- name: `??1NotificationContext@NotificationCallbacks@Client@ComputeService@@QEAA@XZ`
- size: `171`
- prototype: `void __fastcall(ComputeService::Client::NotificationCallbacks::NotificationContext *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001863c`
- `0x180018710`
- `0x1800187f8`
- `0x18002d5e0`
- `0x18002d984`
- `0x18002dd9c`

## callees

- `0x180018828`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180018855`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180018897`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180018855`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180018897`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180018863`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800188a5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180018863`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800188a5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001886c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800188ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001886c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800188ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001883e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001883e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800188c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800188c2`

## pseudocode

```c
void __fastcall ComputeService::Client::NotificationCallbacks::NotificationContext::~NotificationContext(
        ComputeService::Client::NotificationCallbacks::NotificationContext *this)
{
  struct _TP_WORK *v2; // rcx
  struct _TP_WAIT *v3; // rdi
  char *v4; // rcx
  struct _TP_WAIT *v5; // rdi
  char *v6; // rcx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 11);
  if ( v2 )
    CloseThreadpoolWork(v2);
  v3 = (struct _TP_WAIT *)*((_QWORD *)this + 7);
  if ( v3 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 7), 0, 0);
    WaitForThreadpoolWaitCallbacks(v3, 1);
    CloseThreadpoolWait(v3);
  }
  v4 = (char *)*((_QWORD *)this + 6);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  v5 = (struct _TP_WAIT *)*((_QWORD *)this + 5);
  if ( v5 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 5), 0, 0);
    WaitForThreadpoolWaitCallbacks(v5, 1);
    CloseThreadpoolWait(v5);
  }
  v6 = (char *)*((_QWORD *)this + 4);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
}

```

## disassembly

```asm
0x180018828  mov     [rsp+arg_0], rbx
0x18001882d  push    rdi
0x18001882e  sub     rsp, 20h
0x180018832  mov     rbx, rcx
0x180018835  mov     rcx, [rcx+58h]; pwk
0x180018839  test    rcx, rcx
0x18001883c  jz      short loc_180018844
0x18001883e  call    cs:__imp_CloseThreadpoolWork
0x180018844  mov     rdi, [rbx+38h]
0x180018848  test    rdi, rdi
0x18001884b  jz      short loc_180018872
0x18001884d  xor     r8d, r8d; pftTimeout
0x180018850  xor     edx, edx; h
0x180018852  mov     rcx, rdi; pwa
0x180018855  call    cs:__imp_SetThreadpoolWait
0x18001885b  mov     edx, 1; fCancelPendingCallbacks
0x180018860  mov     rcx, rdi; pwa
0x180018863  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180018869  mov     rcx, rdi; pwa
0x18001886c  call    cs:__imp_CloseThreadpoolWait
0x180018872  mov     rcx, [rbx+30h]; hObject
0x180018876  lea     rax, [rcx-1]
0x18001887a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001887e  ja      short loc_180018886
0x180018880  call    cs:__imp_CloseHandle
0x180018886  mov     rdi, [rbx+28h]
0x18001888a  test    rdi, rdi
0x18001888d  jz      short loc_1800188B4
0x18001888f  xor     r8d, r8d; pftTimeout
0x180018892  xor     edx, edx; h
0x180018894  mov     rcx, rdi; pwa
0x180018897  call    cs:__imp_SetThreadpoolWait
0x18001889d  mov     edx, 1; fCancelPendingCallbacks
0x1800188a2  mov     rcx, rdi; pwa
0x1800188a5  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800188ab  mov     rcx, rdi; pwa
0x1800188ae  call    cs:__imp_CloseThreadpoolWait
0x1800188b4  mov     rcx, [rbx+20h]; hObject
0x1800188b8  lea     rax, [rcx-1]
0x1800188bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800188c0  ja      short loc_1800188C8
0x1800188c2  call    cs:__imp_CloseHandle
0x1800188c8  mov     rbx, [rsp+28h+arg_0]
0x1800188cd  add     rsp, 20h
0x1800188d1  pop     rdi
0x1800188d2  retn
```
