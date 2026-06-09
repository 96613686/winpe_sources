# CTpTimer::~CTpTimer(void)

- ea: `0x18000a6cc`
- end: `0x18000a738`
- name: `??1CTpTimer@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(CTpTimer *__hidden this)`
- caller_count: `24`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a5e4`
- `0x18000a740`
- `0x18000a8ac`
- `0x18000bf7c`
- `0x18004df58`
- `0x18007d38c`
- `0x18007d520`
- `0x18007ebf4`
- `0x1800985bc`
- `0x18009aa14`
- `0x1800a33c0`
- `0x1800b8f64`
- `0x1800b9c18`
- `0x1800b9e14`
- `0x1800f0f1c`
- `0x18010e55d`
- `0x180110b7c`
- `0x180110b95`
- `0x1801127af`
- `0x18011288f`
- `0x1801128c9`
- `0x18011320e`
- `0x180113224`
- `0x180117cad`

## callees

- `0x18000a6cc`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a704`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a704`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a6fb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a6fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a6ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a6ed`

## pseudocode

```c
void __fastcall CTpTimer::~CTpTimer(CTpTimer *this, __int64 a2)
{
  struct _TP_TIMER *v2; // rdi
  CTpTimer *v4; // rcx

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 8), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
  }
  v4 = (CTpTimer *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    LOBYTE(a2) = v4 != this;
    (*(void (__fastcall **)(CTpTimer *, __int64))(*(_QWORD *)v4 + 32LL))(v4, a2);
    *((_QWORD *)this + 7) = 0;
  }
}

```

## disassembly

```asm
0x18000a6cc  mov     [rsp+arg_0], rbx
0x18000a6d1  push    rdi
0x18000a6d2  sub     rsp, 20h
0x18000a6d6  mov     rdi, [rcx+40h]
0x18000a6da  mov     rbx, rcx
0x18000a6dd  test    rdi, rdi
0x18000a6e0  jz      short loc_18000A70A
0x18000a6e2  xor     r9d, r9d; msWindowLength
0x18000a6e5  xor     r8d, r8d; msPeriod
0x18000a6e8  xor     edx, edx; pftDueTime
0x18000a6ea  mov     rcx, rdi; pti
0x18000a6ed  call    cs:__imp_SetThreadpoolTimer
0x18000a6f3  mov     edx, 1; fCancelPendingCallbacks
0x18000a6f8  mov     rcx, rdi; pti
0x18000a6fb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a701  mov     rcx, rdi; pti
0x18000a704  call    cs:__imp_CloseThreadpoolTimer
0x18000a70a  mov     rcx, [rbx+38h]
0x18000a70e  test    rcx, rcx
0x18000a711  jz      short loc_18000A72D
0x18000a713  mov     rax, [rcx]
0x18000a716  cmp     rcx, rbx
0x18000a719  setnz   dl
0x18000a71c  mov     rax, [rax+20h]
0x18000a720  call    _guard_dispatch_icall
0x18000a725  mov     qword ptr [rbx+38h], 0
0x18000a72d  mov     rbx, [rsp+28h+arg_0]
0x18000a732  add     rsp, 20h
0x18000a736  pop     rdi
0x18000a737  retn
```
