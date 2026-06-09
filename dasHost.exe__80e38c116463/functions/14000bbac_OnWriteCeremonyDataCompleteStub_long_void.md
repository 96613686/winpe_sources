# OnWriteCeremonyDataCompleteStub(long,void *)

- ea: `0x14000bbac`
- end: `0x14000bc6c`
- name: `?OnWriteCeremonyDataCompleteStub@@YAJJPEAX@Z`
- size: `192`
- prototype: `__int64 __fastcall(unsigned int, RTL_SRWLOCK *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000cb50`
- `0x1400184b0`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x14000bbac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000bbf8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000bbf8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000bc2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000bc2d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000bc24`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000bc24`

## pseudocode

```c
__int64 __fastcall OnWriteCeremonyDataCompleteStub(unsigned int a1, RTL_SRWLOCK *a2, int a3)
{
  struct _RPC_ASYNC_STATE *Ptr; // rcx
  int v5; // edx
  int v6; // r8d
  int v8; // [rsp+28h] [rbp-40h]
  unsigned int Reply; // [rsp+70h] [rbp+8h] BYREF

  Reply = a1;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      a3,
      47,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids);
  AcquireSRWLockExclusive(a2 + 21);
  if ( LODWORD(a2[20].Ptr) )
  {
    Reply = -2147418113;
  }
  else
  {
    Ptr = (struct _RPC_ASYNC_STATE *)a2[12].Ptr;
    LODWORD(a2[20].Ptr) = 1;
    RpcAsyncCompleteCall(Ptr, &Reply);
  }
  ReleaseSRWLockExclusive(a2 + 21);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v5,
      v6,
      48,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids,
      v8,
      Reply);
  return Reply;
}

```

## disassembly

```asm
0x14000bbac  push    rbx
0x14000bbae  push    rbp
0x14000bbaf  push    rsi
0x14000bbb0  push    rdi
0x14000bbb1  sub     rsp, 48h
0x14000bbb5  mov     rbx, rdx
0x14000bbb8  mov     [rsp+68h+Reply], ecx
0x14000bbbc  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000bbc3  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000bbca  lea     rbp, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000bbd1  jz      short loc_14000BBEE
0x14000bbd3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bbda  mov     r9d, 2Fh ; '/'; int
0x14000bbe0  mov     [rsp+68h+MessageGuid], rbp; MessageGuid
0x14000bbe5  mov     rcx, [rcx+28h]; int
0x14000bbe9  call    WPP_RECORDER_SF_s
0x14000bbee  lea     rdi, [rbx+0A8h]
0x14000bbf5  mov     rcx, rdi; SRWLock
0x14000bbf8  call    cs:__imp_AcquireSRWLockExclusive
0x14000bbfe  cmp     dword ptr [rbx+0A0h], 0
0x14000bc05  jz      short loc_14000BC11
0x14000bc07  mov     [rsp+68h+Reply], 8000FFFFh
0x14000bc0f  jmp     short loc_14000BC2A
0x14000bc11  mov     rcx, [rbx+60h]; pAsync
0x14000bc15  lea     rdx, [rsp+68h+Reply]; Reply
0x14000bc1a  mov     dword ptr [rbx+0A0h], 1
0x14000bc24  call    cs:__imp_RpcAsyncCompleteCall
0x14000bc2a  mov     rcx, rdi; SRWLock
0x14000bc2d  call    cs:__imp_ReleaseSRWLockExclusive
0x14000bc33  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000bc3a  jz      short loc_14000BC5F
0x14000bc3c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc43  mov     r9d, 30h ; '0'; int
0x14000bc49  mov     eax, [rsp+68h+Reply]
0x14000bc4d  mov     dword ptr [rsp+68h+var_38], eax; char
0x14000bc51  mov     [rsp+68h+MessageGuid], rbp; MessageGuid
0x14000bc56  mov     rcx, [rcx+28h]; int
0x14000bc5a  call    WPP_RECORDER_SF_sd
0x14000bc5f  mov     eax, [rsp+68h+Reply]
0x14000bc63  add     rsp, 48h
0x14000bc67  pop     rdi
0x14000bc68  pop     rsi
0x14000bc69  pop     rbp
0x14000bc6a  pop     rbx
0x14000bc6b  retn
```
