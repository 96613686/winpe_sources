# CIOPort::FPostIoPacketCore(ulong,CThreadState *)

- ea: `0x1801152c0`
- end: `0x180115352`
- name: `?FPostIoPacketCore@CIOPort@@IEAA_NKPEAUCThreadState@@@Z`
- size: `146`
- prototype: `bool __fastcall(CIOPort *__hidden this, unsigned int, struct CThreadState *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180114be0`
- `0x1801151c0`

## callees

- `0x180114b38`
- `0x1801152c0`
- `0x1801179cc`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1801152dc`
- `KERNEL32!GetCurrentThreadId` at `0x1801152dc`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18011530e`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18011530e`

## pseudocode

```c
char __fastcall CIOPort::FPostIoPacketCore(HANDLE *this, unsigned int a2, struct CThreadState *a3)
{
  ULONG_PTR v4; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v7; // rcx
  unsigned int v8; // esi
  struct CThreadState *v9; // r9

  v4 = a2;
  CurrentThreadId = GetCurrentThreadId();
  v8 = CurrentThreadId;
  if ( (Microsoft_Office_ThreadpoolEnableBits & 0x10) != 0 )
    McTemplateU0qq_EventWriteTransfer(v7, TPPortPacketPosted, (unsigned int)v4, CurrentThreadId);
  if ( PostQueuedCompletionStatus(this[16], v8, v4, 0) )
  {
    (*((void (__fastcall **)(HANDLE *, _QWORD, struct CThreadState *))*this + 2))(this, 0, a3);
    return 1;
  }
  else
  {
    CIOPort::AfterPacketSubmitFailure((CIOPort *)this, v4, v8, v9);
    return 0;
  }
}

```

## disassembly

```asm
0x1801152c0  mov     [rsp+arg_0], rbx
0x1801152c5  mov     [rsp+arg_8], rbp
0x1801152ca  mov     [rsp+arg_10], rsi
0x1801152cf  push    rdi
0x1801152d0  sub     rsp, 20h
0x1801152d4  mov     rbp, r8
0x1801152d7  mov     edi, edx
0x1801152d9  mov     rbx, rcx
0x1801152dc  call    cs:__imp_GetCurrentThreadId
0x1801152e2  test    cs:Microsoft_Office_ThreadpoolEnableBits, 10h
0x1801152e9  mov     esi, eax
0x1801152eb  jz      short loc_1801152FF
0x1801152ed  mov     r9d, eax
0x1801152f0  lea     rdx, TPPortPacketPosted
0x1801152f7  mov     r8d, edi
0x1801152fa  call    McTemplateU0qq_EventWriteTransfer
0x1801152ff  mov     rcx, [rbx+80h]; CompletionPort
0x180115306  mov     r8, rdi; dwCompletionKey
0x180115309  xor     r9d, r9d; lpOverlapped
0x18011530c  mov     edx, esi; dwNumberOfBytesTransferred
0x18011530e  call    cs:__imp_PostQueuedCompletionStatus
0x180115314  mov     rcx, rbx; this
0x180115317  test    eax, eax
0x180115319  jz      short loc_180115331
0x18011531b  mov     rax, [rbx]
0x18011531e  mov     r8, rbp
0x180115321  xor     edx, edx
0x180115323  mov     rax, [rax+10h]
0x180115327  call    cs:__guard_dispatch_icall_fptr
0x18011532d  mov     al, 1
0x18011532f  jmp     short loc_18011533D
0x180115331  mov     r8d, esi; unsigned int
0x180115334  mov     edx, edi; unsigned int
0x180115336  call    ?AfterPacketSubmitFailure@CIOPort@@IEAAXKKPEAUCThreadState@@@Z; CIOPort::AfterPacketSubmitFailure(ulong,ulong,CThreadState *)
0x18011533b  xor     al, al
0x18011533d  mov     rbx, [rsp+28h+arg_0]
0x180115342  mov     rbp, [rsp+28h+arg_8]
0x180115347  mov     rsi, [rsp+28h+arg_10]
0x18011534c  add     rsp, 20h
0x180115350  pop     rdi
0x180115351  retn
```
