# DeviceStatusNotificationStub(ulong,long,void *)

- ea: `0x14000b338`
- end: `0x14000b3b8`
- name: `?DeviceStatusNotificationStub@@YAJKJPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(int, unsigned int, RTL_SRWLOCK *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000c640`
- `0x140017a70`

## callees

- `0x14000b338`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b35a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b35a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b39e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b39e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000b395`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000b395`

## pseudocode

```c
__int64 __fastcall DeviceStatusNotificationStub(int a1, unsigned int a2, RTL_SRWLOCK *a3)
{
  RTL_SRWLOCK *v3; // rdi
  int v6; // ecx
  struct _RPC_ASYNC_STATE *Ptr; // rcx
  unsigned int Reply; // [rsp+38h] [rbp+10h] BYREF

  v3 = a3 + 21;
  Reply = a2;
  AcquireSRWLockExclusive(a3 + 21);
  if ( LODWORD(a3[20].Ptr) )
  {
    Reply = -2147418113;
  }
  else
  {
    v6 = 0;
    if ( !Reply )
      v6 = a1;
    *(_DWORD *)a3[13].Ptr = v6;
    Ptr = (struct _RPC_ASYNC_STATE *)a3[12].Ptr;
    LODWORD(a3[20].Ptr) = 1;
    RpcAsyncCompleteCall(Ptr, &Reply);
  }
  ReleaseSRWLockExclusive(v3);
  return Reply;
}

```

## disassembly

```asm
0x14000b338  mov     [rsp+arg_0], rbx
0x14000b33d  mov     [rsp+arg_10], rsi
0x14000b342  push    rdi
0x14000b343  sub     rsp, 20h
0x14000b347  lea     rdi, [r8+0A8h]
0x14000b34e  mov     [rsp+28h+Reply], edx
0x14000b352  mov     esi, ecx
0x14000b354  mov     rbx, r8
0x14000b357  mov     rcx, rdi; SRWLock
0x14000b35a  call    cs:__imp_AcquireSRWLockExclusive
0x14000b360  cmp     dword ptr [rbx+0A0h], 0
0x14000b367  jz      short loc_14000B373
0x14000b369  mov     [rsp+28h+Reply], 8000FFFFh
0x14000b371  jmp     short loc_14000B39B
0x14000b373  mov     rax, [rbx+68h]
0x14000b377  lea     rdx, [rsp+28h+Reply]; Reply
0x14000b37c  xor     ecx, ecx
0x14000b37e  cmp     [rsp+28h+Reply], ecx
0x14000b382  cmovz   ecx, esi
0x14000b385  mov     [rax], ecx
0x14000b387  mov     rcx, [rbx+60h]; pAsync
0x14000b38b  mov     dword ptr [rbx+0A0h], 1
0x14000b395  call    cs:__imp_RpcAsyncCompleteCall
0x14000b39b  mov     rcx, rdi; SRWLock
0x14000b39e  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b3a4  mov     eax, [rsp+28h+Reply]
0x14000b3a8  mov     rbx, [rsp+28h+arg_0]
0x14000b3ad  mov     rsi, [rsp+28h+arg_10]
0x14000b3b2  add     rsp, 20h
0x14000b3b6  pop     rdi
0x14000b3b7  retn
```
