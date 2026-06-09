# WS_DeactivateAddress(WS_ADDRESS *)

- ea: `0x1800c6060`
- end: `0x1800c6178`
- name: `?WS_DeactivateAddress@@YAXPEAUWS_ADDRESS@@@Z`
- size: `280`
- prototype: `void __fastcall(struct WS_ADDRESS *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180098b00`
- `0x1800c7438`

## callees

- `0x180060e18`
- `0x18006108c`
- `0x180094418`
- `0x1800c6060`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800c6143`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800c6143`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c6128`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c6128`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c60f7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c60f7`
- `WS2_32!__imp_closesocket` at `0x1800c6159`
- `WS2_32!__imp_closesocket` at `0x1800c6167`
- `WS2_32!__imp_closesocket` at `0x1800c6159`
- `WS2_32!__imp_closesocket` at `0x1800c6167`

## pseudocode

```c
void __fastcall WS_DeactivateAddress(struct WS_ADDRESS *a1)
{
  SOCKET v2; // r14
  SOCKET v3; // rbp
  signed __int32 v4; // r8d
  PTP_TIMER *v5; // rsi
  PTP_IO *v6; // rdi
  unsigned int v7; // edx
  unsigned int v8; // edx

  if ( *((_DWORD *)a1 + 3) == 1 || *((_DWORD *)a1 + 3) == 6 || *((_DWORD *)a1 + 3) == 9 || *((_DWORD *)a1 + 3) == 12 )
  {
    v2 = *((_QWORD *)a1 + 25);
    v3 = *((_QWORD *)a1 + 26);
    CSpinLock::Lock((struct WS_ADDRESS *)((char *)a1 + 120));
    *((_QWORD *)a1 + 25) = 0;
    *((_QWORD *)a1 + 26) = 0;
    v4 = _InterlockedIncrement((volatile signed __int32 *)a1 + 4);
    _InterlockedExchange(
      (volatile __int32 *)a1 + 30,
      ((*((_DWORD *)a1 + 30) - 0x10000000) & 0xF0000000) != 0 ? *((_DWORD *)a1 + 30) - 0x10000000 : 0);
    if ( v4 == 1 )
    {
      SetThreadpoolTimer(**((PTP_TIMER **)a1 + 13), 0, 0, 0);
      v5 = (PTP_TIMER *)*((_QWORD *)a1 + 13);
      v6 = (PTP_IO *)*((_QWORD *)a1 + 83);
      *((_QWORD *)a1 + 13) = 0;
      *((_QWORD *)a1 + 83) = 0;
      if ( v5 )
      {
        WaitForThreadpoolTimerCallbacks(*v5, 1);
        RPC_THREAD_POOL_TIMER::`scalar deleting destructor'((RPC_THREAD_POOL_TIMER *)v5, v7);
      }
      if ( v6 )
      {
        WaitForThreadpoolIoCallbacks(*v6, 1);
        RPC_THREAD_POOL_IO::`scalar deleting destructor'((RPC_THREAD_POOL_IO *)v6, v8);
      }
      if ( v2 )
        closesocket(v2);
      if ( v3 )
        closesocket(v3);
    }
  }
}

```

## disassembly

```asm
0x1800c6060  push    rbx
0x1800c6062  push    rbp
0x1800c6063  push    rsi
0x1800c6064  push    rdi
0x1800c6065  push    r14
0x1800c6067  sub     rsp, 20h
0x1800c606b  mov     edx, [rcx+0Ch]
0x1800c606e  mov     rbx, rcx
0x1800c6071  sub     edx, 1
0x1800c6074  jz      short loc_1800C6089
0x1800c6076  sub     edx, 5
0x1800c6079  jz      short loc_1800C6089
0x1800c607b  sub     edx, 3
0x1800c607e  jz      short loc_1800C6089
0x1800c6080  cmp     edx, 3
0x1800c6083  jnz     loc_1800C616D
0x1800c6089  mov     r14, [rcx+0C8h]
0x1800c6090  mov     rbp, [rcx+0D0h]
0x1800c6097  add     rcx, 78h ; 'x'; this
0x1800c609b  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x1800c60a0  mov     r8d, 1
0x1800c60a6  mov     qword ptr [rbx+0C8h], 0
0x1800c60b1  mov     qword ptr [rbx+0D0h], 0
0x1800c60bc  lock xadd [rbx+10h], r8d
0x1800c60c2  mov     edx, [rbx+78h]
0x1800c60c5  inc     r8d
0x1800c60c8  add     edx, 0F0000000h
0x1800c60ce  mov     eax, edx
0x1800c60d0  and     eax, 0F0000000h
0x1800c60d5  neg     eax
0x1800c60d7  sbb     ecx, ecx
0x1800c60d9  and     ecx, edx
0x1800c60db  xchg    ecx, [rbx+78h]
0x1800c60de  cmp     r8d, 1
0x1800c60e2  jnz     loc_1800C616D
0x1800c60e8  mov     rcx, [rbx+68h]
0x1800c60ec  xor     r9d, r9d; msWindowLength
0x1800c60ef  xor     r8d, r8d; msPeriod
0x1800c60f2  xor     edx, edx; pftDueTime
0x1800c60f4  mov     rcx, [rcx]; pti
0x1800c60f7  call    cs:__imp_SetThreadpoolTimer
0x1800c60fd  mov     rsi, [rbx+68h]
0x1800c6101  mov     rdi, [rbx+298h]
0x1800c6108  mov     qword ptr [rbx+68h], 0
0x1800c6110  mov     qword ptr [rbx+298h], 0
0x1800c611b  test    rsi, rsi
0x1800c611e  jz      short loc_1800C6136
0x1800c6120  mov     rcx, [rsi]; pti
0x1800c6123  mov     edx, 1; fCancelPendingCallbacks
0x1800c6128  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800c612e  mov     rcx, rsi; this
0x1800c6131  call    ??_GRPC_THREAD_POOL_TIMER@@QEAAPEAXI@Z; RPC_THREAD_POOL_TIMER::`scalar deleting destructor'(uint)
0x1800c6136  test    rdi, rdi
0x1800c6139  jz      short loc_1800C6151
0x1800c613b  mov     rcx, [rdi]; pio
0x1800c613e  mov     edx, 1; fCancelPendingCallbacks
0x1800c6143  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800c6149  mov     rcx, rdi; this
0x1800c614c  call    ??_GRPC_THREAD_POOL_IO@@QEAAPEAXI@Z; RPC_THREAD_POOL_IO::`scalar deleting destructor'(uint)
0x1800c6151  test    r14, r14
0x1800c6154  jz      short loc_1800C615F
0x1800c6156  mov     rcx, r14; s
0x1800c6159  call    cs:__imp_closesocket
0x1800c615f  test    rbp, rbp
0x1800c6162  jz      short loc_1800C616D
0x1800c6164  mov     rcx, rbp; s
0x1800c6167  call    cs:__imp_closesocket
0x1800c616d  add     rsp, 20h
0x1800c6171  pop     r14
0x1800c6173  pop     rdi
0x1800c6174  pop     rsi
0x1800c6175  pop     rbp
0x1800c6176  pop     rbx
0x1800c6177  retn
```
