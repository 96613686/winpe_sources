# OnRemoveCompleteStub(int,long,void *)

- ea: `0x14000bacc`
- end: `0x14000bba6`
- name: `?OnRemoveCompleteStub@@YAJHJPEAX@Z`
- size: `218`
- prototype: `__int64 __fastcall(int, int, RTL_SRWLOCK *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000ca90`
- `0x140017f70`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x14000bacc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000bb22`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000bb22`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000bb5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000bb5d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000bb54`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000bb54`

## pseudocode

```c
__int64 __fastcall OnRemoveCompleteStub(int a1, int a2, RTL_SRWLOCK *a3)
{
  struct _RPC_ASYNC_STATE *Ptr; // rcx
  int v6; // edx
  int v7; // r8d
  int v9; // [rsp+28h] [rbp-30h]
  unsigned int Reply; // [rsp+68h] [rbp+10h] BYREF

  Reply = a2;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      a2,
      (int)a3,
      51,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids);
  AcquireSRWLockExclusive(a3 + 21);
  if ( LODWORD(a3[20].Ptr) )
  {
    Reply = -2147418113;
  }
  else
  {
    *(_DWORD *)a3[13].Ptr = a1;
    Ptr = (struct _RPC_ASYNC_STATE *)a3[12].Ptr;
    LODWORD(a3[20].Ptr) = 1;
    RpcAsyncCompleteCall(Ptr, &Reply);
  }
  ReleaseSRWLockExclusive(a3 + 21);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v6,
      v7,
      52,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids,
      v9,
      Reply);
  return Reply;
}

```

## disassembly

```asm
0x14000bacc  mov     rax, rsp
0x14000bacf  mov     [rax+8], rbx
0x14000bad3  mov     [rax+18h], rbp
0x14000bad7  push    rsi
0x14000bad8  push    rdi
0x14000bad9  push    r14
0x14000badb  sub     rsp, 40h
0x14000badf  mov     rbx, r8
0x14000bae2  mov     [rax+10h], edx
0x14000bae5  mov     esi, ecx
0x14000bae7  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000baee  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000baf5  lea     r14, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000bafc  jz      short loc_14000BB18
0x14000bafe  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bb05  mov     r9d, 33h ; '3'; int
0x14000bb0b  mov     [rax-38h], r14
0x14000bb0f  mov     rcx, [rcx+28h]; int
0x14000bb13  call    WPP_RECORDER_SF_s
0x14000bb18  lea     rdi, [rbx+0A8h]
0x14000bb1f  mov     rcx, rdi; SRWLock
0x14000bb22  call    cs:__imp_AcquireSRWLockExclusive
0x14000bb28  cmp     dword ptr [rbx+0A0h], 0
0x14000bb2f  jz      short loc_14000BB3B
0x14000bb31  mov     [rsp+58h+Reply], 8000FFFFh
0x14000bb39  jmp     short loc_14000BB5A
0x14000bb3b  mov     rax, [rbx+68h]
0x14000bb3f  lea     rdx, [rsp+58h+Reply]; Reply
0x14000bb44  mov     [rax], esi
0x14000bb46  mov     rcx, [rbx+60h]; pAsync
0x14000bb4a  mov     dword ptr [rbx+0A0h], 1
0x14000bb54  call    cs:__imp_RpcAsyncCompleteCall
0x14000bb5a  mov     rcx, rdi; SRWLock
0x14000bb5d  call    cs:__imp_ReleaseSRWLockExclusive
0x14000bb63  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000bb6a  jz      short loc_14000BB8F
0x14000bb6c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bb73  mov     r9d, 34h ; '4'; int
0x14000bb79  mov     eax, [rsp+58h+Reply]
0x14000bb7d  mov     dword ptr [rsp+58h+var_28], eax; char
0x14000bb81  mov     [rsp+58h+MessageGuid], r14; MessageGuid
0x14000bb86  mov     rcx, [rcx+28h]; int
0x14000bb8a  call    WPP_RECORDER_SF_sd
0x14000bb8f  mov     eax, [rsp+58h+Reply]
0x14000bb93  mov     rbx, [rsp+58h+arg_0]
0x14000bb98  mov     rbp, [rsp+58h+arg_10]
0x14000bb9d  add     rsp, 40h
0x14000bba1  pop     r14
0x14000bba3  pop     rdi
0x14000bba4  pop     rsi
0x14000bba5  retn
```
