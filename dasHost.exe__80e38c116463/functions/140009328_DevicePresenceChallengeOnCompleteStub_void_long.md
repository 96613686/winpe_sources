# DevicePresenceChallengeOnCompleteStub(void *,long)

- ea: `0x140009328`
- end: `0x1400093dd`
- name: `?DevicePresenceChallengeOnCompleteStub@@YAJPEAXJ@Z`
- size: `181`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140009850`
- `0x1400169f0`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x140009328`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000936e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000936e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000939e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000939e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140009394`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140009394`

## pseudocode

```c
__int64 __fastcall DevicePresenceChallengeOnCompleteStub(RTL_SRWLOCK *a1, int a2, int a3)
{
  struct _RPC_ASYNC_STATE *Ptr; // rcx
  int v5; // edx
  int v6; // r8d
  int v8; // [rsp+28h] [rbp-40h]
  unsigned int Reply; // [rsp+78h] [rbp+10h] BYREF

  Reply = a2;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 5), a2, a3, 18, &WPP_e7bcb4884d5632717339d31cbd6bbd09_Traceguids);
  AcquireSRWLockExclusive(a1 + 4);
  if ( LODWORD(a1[5].Ptr) )
  {
    Reply = -2147418113;
  }
  else
  {
    Ptr = (struct _RPC_ASYNC_STATE *)a1[3].Ptr;
    LODWORD(a1[5].Ptr) = 1;
    RpcAsyncCompleteCall(Ptr, &Reply);
  }
  ReleaseSRWLockExclusive(a1 + 4);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v5,
      v6,
      19,
      &WPP_e7bcb4884d5632717339d31cbd6bbd09_Traceguids,
      v8,
      Reply);
  return Reply;
}

```

## disassembly

```asm
0x140009328  push    rbx
0x14000932a  push    rbp
0x14000932b  push    rsi
0x14000932c  push    rdi
0x14000932d  sub     rsp, 48h
0x140009331  mov     rbx, rcx
0x140009334  mov     [rsp+68h+Reply], edx
0x140009338  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000933f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140009346  lea     rbp, WPP_e7bcb4884d5632717339d31cbd6bbd09_Traceguids
0x14000934d  jz      short loc_14000936A
0x14000934f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009356  mov     r9d, 12h; int
0x14000935c  mov     [rsp+68h+MessageGuid], rbp; MessageGuid
0x140009361  mov     rcx, [rcx+28h]; int
0x140009365  call    WPP_RECORDER_SF_s
0x14000936a  lea     rcx, [rbx+20h]; SRWLock
0x14000936e  call    cs:__imp_AcquireSRWLockExclusive
0x140009374  cmp     dword ptr [rbx+28h], 0
0x140009378  jz      short loc_140009384
0x14000937a  mov     [rsp+68h+Reply], 8000FFFFh
0x140009382  jmp     short loc_14000939A
0x140009384  mov     rcx, [rbx+18h]; pAsync
0x140009388  lea     rdx, [rsp+68h+Reply]; Reply
0x14000938d  mov     dword ptr [rbx+28h], 1
0x140009394  call    cs:__imp_RpcAsyncCompleteCall
0x14000939a  lea     rcx, [rbx+20h]; SRWLock
0x14000939e  call    cs:__imp_ReleaseSRWLockExclusive
0x1400093a4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400093ab  jz      short loc_1400093D0
0x1400093ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400093b4  mov     r9d, 13h; int
0x1400093ba  mov     eax, [rsp+68h+Reply]
0x1400093be  mov     dword ptr [rsp+68h+var_38], eax; char
0x1400093c2  mov     [rsp+68h+MessageGuid], rbp; MessageGuid
0x1400093c7  mov     rcx, [rcx+28h]; int
0x1400093cb  call    WPP_RECORDER_SF_sd
0x1400093d0  mov     eax, [rsp+68h+Reply]
0x1400093d4  add     rsp, 48h
0x1400093d8  pop     rdi
0x1400093d9  pop     rsi
0x1400093da  pop     rbp
0x1400093db  pop     rbx
0x1400093dc  retn
```
