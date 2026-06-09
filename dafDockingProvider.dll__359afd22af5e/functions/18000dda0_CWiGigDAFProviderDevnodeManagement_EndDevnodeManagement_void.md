# CWiGigDAFProviderDevnodeManagement::EndDevnodeManagement(void)

- ea: `0x18000dda0`
- end: `0x18000de5e`
- name: `?EndDevnodeManagement@CWiGigDAFProviderDevnodeManagement@@UEAAJXZ`
- size: `190`
- prototype: `__int64 __fastcall(CWiGigDAFProviderDevnodeManagement *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cb40`
- `0x18000dda0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ddf7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ddf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de4b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000de2a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000de2a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000de18`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000de18`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000de37`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000de37`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderDevnodeManagement::EndDevnodeManagement(CWiGigDAFProviderDevnodeManagement *this)
{
  struct _TP_TIMER *v2; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      (unsigned int)&WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids,
      (_DWORD)this,
      (__int64)this + 12);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 632));
  *((_BYTE *)this + 672) = 1;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 85);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 85), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 85));
    *((_QWORD *)this + 85) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 632));
  return 0;
}

```

## disassembly

```asm
0x18000dda0  mov     [rsp+arg_0], rbx
0x18000dda5  push    rdi
0x18000dda6  sub     rsp, 30h
0x18000ddaa  mov     rbx, rcx
0x18000ddad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddb4  lea     rax, WPP_GLOBAL_Control
0x18000ddbb  cmp     rcx, rax
0x18000ddbe  jz      short loc_18000DDED
0x18000ddc0  cmp     byte ptr [rcx+19h], 3
0x18000ddc4  jb      short loc_18000DDED
0x18000ddc6  test    byte ptr [rcx+1Ch], 1
0x18000ddca  jz      short loc_18000DDED
0x18000ddcc  mov     rcx, [rcx+10h]
0x18000ddd0  lea     rax, [rbx+0Ch]
0x18000ddd4  mov     edx, 1Dh
0x18000ddd9  mov     [rsp+38h+var_18], rax
0x18000ddde  mov     r9, rbx
0x18000dde1  lea     r8, WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids
0x18000dde8  call    WPP_SF_qS
0x18000dded  lea     rdi, [rbx+278h]
0x18000ddf4  mov     rcx, rdi; lpCriticalSection
0x18000ddf7  call    cs:__imp_EnterCriticalSection
0x18000ddfd  mov     byte ptr [rbx+2A0h], 1
0x18000de04  mov     rcx, [rbx+2A8h]; pti
0x18000de0b  test    rcx, rcx
0x18000de0e  jz      short loc_18000DE48
0x18000de10  xor     r9d, r9d; msWindowLength
0x18000de13  xor     r8d, r8d; msPeriod
0x18000de16  xor     edx, edx; pftDueTime
0x18000de18  call    cs:__imp_SetThreadpoolTimer
0x18000de1e  mov     rcx, [rbx+2A8h]; pti
0x18000de25  mov     edx, 1; fCancelPendingCallbacks
0x18000de2a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000de30  mov     rcx, [rbx+2A8h]; pti
0x18000de37  call    cs:__imp_CloseThreadpoolTimer
0x18000de3d  mov     qword ptr [rbx+2A8h], 0
0x18000de48  mov     rcx, rdi; lpCriticalSection
0x18000de4b  call    cs:__imp_LeaveCriticalSection
0x18000de51  mov     rbx, [rsp+38h+arg_0]
0x18000de56  xor     eax, eax
0x18000de58  add     rsp, 30h
0x18000de5c  pop     rdi
0x18000de5d  retn
```
