# WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue(void)

- ea: `0x18000d3c0`
- end: `0x18000d425`
- name: `??1ThreadPoolWorkQueue@WcmCommon@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(WcmCommon::ThreadPoolWorkQueue *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d094`

## callees

- `0x18000ca4c`
- `0x18000d3c0`
- `0x18000ec74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d41e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000d3f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000d3f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000d3fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000d3fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000d40a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000d40a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue(WcmCommon::ThreadPoolWorkQueue *this)
{
  struct _TP_WORK *v2; // rdi
  struct _TP_POOL *v3; // rcx

  WcmCommon::ThreadPoolWorkQueue::Cancel(this);
  WcmCommon::ThreadPoolWorkQueue::_unnamed_type_m_lockedData_::__unnamed_type_m_lockedData_((char *)this + 152);
  v2 = (struct _TP_WORK *)*((_QWORD *)this + 16);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 16), 1);
    CloseThreadpoolWork(v2);
  }
  v3 = (struct _TP_POOL *)*((_QWORD *)this + 15);
  if ( v3 )
    CloseThreadpool(v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18000d3c0  mov     [rsp+arg_0], rbx
0x18000d3c5  push    rdi
0x18000d3c6  sub     rsp, 20h
0x18000d3ca  mov     rbx, rcx
0x18000d3cd  call    ?Cancel@ThreadPoolWorkQueue@WcmCommon@@QEAAXXZ; WcmCommon::ThreadPoolWorkQueue::Cancel(void)
0x18000d3d2  lea     rcx, [rbx+98h]
0x18000d3d9  call    WcmCommon__ThreadPoolWorkQueue___unnamed_type_m_lockedData_____unnamed_type_m_lockedData_
0x18000d3de  mov     rdi, [rbx+80h]
0x18000d3e5  test    rdi, rdi
0x18000d3e8  jz      short loc_18000D401
0x18000d3ea  mov     edx, 1; fCancelPendingCallbacks
0x18000d3ef  mov     rcx, rdi; pwk
0x18000d3f2  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000d3f8  mov     rcx, rdi; pwk
0x18000d3fb  call    cs:__imp_CloseThreadpoolWork
0x18000d401  mov     rcx, [rbx+78h]; ptpp
0x18000d405  test    rcx, rcx
0x18000d408  jz      short loc_18000D410
0x18000d40a  call    cs:__imp_CloseThreadpool
0x18000d410  lea     rcx, [rbx+8]
0x18000d414  mov     rbx, [rsp+28h+arg_0]
0x18000d419  add     rsp, 20h
0x18000d41d  pop     rdi
0x18000d41e  jmp     cs:__imp_DeleteCriticalSection
```
