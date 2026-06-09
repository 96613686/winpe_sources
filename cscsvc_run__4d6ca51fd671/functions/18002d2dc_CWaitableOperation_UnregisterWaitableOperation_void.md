# CWaitableOperation::UnregisterWaitableOperation(void)

- ea: `0x18002d2dc`
- end: `0x18002d3f7`
- name: `?UnregisterWaitableOperation@CWaitableOperation@@QEAAXXZ`
- size: `283`
- prototype: `void __fastcall(CWaitableOperation *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18005ea20`
- `0x18005f860`

## callees

- `0x18002d2dc`
- `0x18004fef4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d2f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d3be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d2f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d3be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d34a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d34a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d3f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002d3c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002d3c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002d341`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002d341`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002d387`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002d387`

## pseudocode

```c
void __fastcall CWaitableOperation::UnregisterWaitableOperation(CWaitableOperation *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  *((_DWORD *)this + 8) = 1;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids,
      *((_QWORD *)this + 2));
  }
  SetThreadpoolWait(*((PTP_WAIT *)this + 2), 0, 0);
  LeaveCriticalSection(v1);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids,
      *((_QWORD *)this + 2));
  }
  WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 2), 1);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids,
      *((_QWORD *)this + 2));
  }
  EnterCriticalSection(v1);
  CloseThreadpoolWait(*((PTP_WAIT *)this + 2));
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 9) = 0;
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x18002d2dc  mov     [rsp+arg_0], rbx
0x18002d2e1  mov     [rsp+arg_8], rdi
0x18002d2e6  push    r14
0x18002d2e8  sub     rsp, 20h
0x18002d2ec  lea     rdi, [rcx+28h]
0x18002d2f0  mov     rbx, rcx
0x18002d2f3  mov     rcx, rdi; lpCriticalSection
0x18002d2f6  call    cs:__imp_EnterCriticalSection
0x18002d2fc  mov     dword ptr [rbx+20h], 1
0x18002d303  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d30a  lea     r14, WPP_GLOBAL_Control
0x18002d311  cmp     rcx, r14
0x18002d314  jz      short loc_18002D338
0x18002d316  test    dword ptr [rcx+1Ch], 10000h
0x18002d31d  jz      short loc_18002D338
0x18002d31f  mov     r9, [rbx+10h]
0x18002d323  lea     r8, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids
0x18002d32a  mov     rcx, [rcx+10h]
0x18002d32e  mov     edx, 0Ch
0x18002d333  call    WPP_SF_q
0x18002d338  mov     rcx, [rbx+10h]; pwa
0x18002d33c  xor     r8d, r8d; pftTimeout
0x18002d33f  xor     edx, edx; h
0x18002d341  call    cs:__imp_SetThreadpoolWait
0x18002d347  mov     rcx, rdi; lpCriticalSection
0x18002d34a  call    cs:__imp_LeaveCriticalSection
0x18002d350  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d357  cmp     rcx, r14
0x18002d35a  jz      short loc_18002D37E
0x18002d35c  test    dword ptr [rcx+1Ch], 10000h
0x18002d363  jz      short loc_18002D37E
0x18002d365  mov     r9, [rbx+10h]
0x18002d369  lea     r8, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids
0x18002d370  mov     rcx, [rcx+10h]
0x18002d374  mov     edx, 0Dh
0x18002d379  call    WPP_SF_q
0x18002d37e  mov     rcx, [rbx+10h]; pwa
0x18002d382  mov     edx, 1; fCancelPendingCallbacks
0x18002d387  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18002d38d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d394  cmp     rcx, r14
0x18002d397  jz      short loc_18002D3BB
0x18002d399  test    dword ptr [rcx+1Ch], 10000h
0x18002d3a0  jz      short loc_18002D3BB
0x18002d3a2  mov     r9, [rbx+10h]
0x18002d3a6  lea     r8, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids
0x18002d3ad  mov     rcx, [rcx+10h]
0x18002d3b1  mov     edx, 0Eh
0x18002d3b6  call    WPP_SF_q
0x18002d3bb  mov     rcx, rdi; lpCriticalSection
0x18002d3be  call    cs:__imp_EnterCriticalSection
0x18002d3c4  mov     rcx, [rbx+10h]; pwa
0x18002d3c8  call    cs:__imp_CloseThreadpoolWait
0x18002d3ce  mov     rcx, rdi
0x18002d3d1  mov     qword ptr [rbx+10h], 0
0x18002d3d9  mov     dword ptr [rbx+24h], 0
0x18002d3e0  mov     rbx, [rsp+28h+arg_0]
0x18002d3e5  mov     rdi, [rsp+28h+arg_8]
0x18002d3ea  add     rsp, 20h
0x18002d3ee  pop     r14
0x18002d3f0  jmp     cs:__imp_LeaveCriticalSection
```
