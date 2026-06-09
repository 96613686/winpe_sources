# TpCheckTerminateWorker

- ea: `0x1800432a0`
- end: `0x18004333f`
- name: `TpCheckTerminateWorker`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180043140`

## callees

- `0x1800195a0`
- `0x18001a080`
- `0x1800432a0`
- `0x180043348`
- `0x1801593cc`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x1800432f9`: `ThreadPool: attempt to terminate a worker thread via handle %p\nContact the owner of the function calling Terminate/Exit thread.\n`

## pseudocode

```c
void __fastcall TpCheckTerminateWorker(const void *a1)
{
  EXCEPTION_RECORD ExceptionRecord; // [rsp+20h] [rbp-B8h] BYREF

  memset_thunk_772440563353939046(&ExceptionRecord, 0, 0x98u);
  if ( (unsigned __int8)TppIsWorkerThread(a1) )
  {
    DbgPrintEx(
      84,
      0,
      "ThreadPool: attempt to terminate a worker thread via handle %p\n"
      "Contact the owner of the function calling Terminate/Exit thread.\n",
      a1);
    memset_thunk_772440563353939046(&ExceptionRecord, 0, 0x98u);
    ExceptionRecord.ExceptionCode = -1073740004;
    ExceptionRecord.NumberParameters = 1;
    ExceptionRecord.ExceptionInformation[0] = (unsigned __int64)a1;
    RtlRaiseException(&ExceptionRecord);
  }
}

```

## disassembly

```asm
0x1800432a0  push    rbx
0x1800432a2  sub     rsp, 0D0h
0x1800432a9  mov     rax, cs:__security_cookie
0x1800432b0  xor     rax, rsp
0x1800432b3  mov     [rsp+0D8h+var_18], rax
0x1800432bb  mov     rbx, rcx
0x1800432be  xor     edx, edx; Val
0x1800432c0  mov     r8d, 98h; Size
0x1800432c6  lea     rcx, [rsp+0D8h+ExceptionRecord]; void *
0x1800432cb  call    memset$thunk$772440563353939046
0x1800432d0  mov     rcx, rbx
0x1800432d3  call    TppIsWorkerThread
0x1800432d8  test    al, al
0x1800432da  jnz     short loc_1800432F6
0x1800432dc  mov     rcx, [rsp+0D8h+var_18]
0x1800432e4  xor     rcx, rsp; StackCookie
0x1800432e7  call    __security_check_cookie
0x1800432ec  add     rsp, 0D0h
0x1800432f3  pop     rbx
0x1800432f4  retn
0x1800432f6  mov     r9, rbx
0x1800432f9  lea     r8, aThreadpoolAtte; "ThreadPool: attempt to terminate a work"...
0x180043300  xor     edx, edx
0x180043302  lea     ecx, [rdx+54h]
0x180043305  call    DbgPrintEx
0x18004330a  xor     edx, edx; Val
0x18004330c  mov     r8d, 98h; Size
0x180043312  lea     rcx, [rsp+0D8h+ExceptionRecord]; void *
0x180043317  call    memset$thunk$772440563353939046
0x18004331c  mov     [rsp+0D8h+ExceptionRecord.ExceptionCode], 0C000071Ch
0x180043324  mov     [rsp+0D8h+ExceptionRecord.NumberParameters], 1
0x18004332c  mov     [rsp+0D8h+ExceptionRecord.ExceptionInformation], rbx
0x180043331  lea     rcx, [rsp+0D8h+ExceptionRecord]; ExceptionRecord
0x180043336  call    RtlRaiseException
0x18004333b  jmp     short loc_1800432DC
0x18004333d  jmp     short loc_1800432DC
0x180165d33  push    rbp
0x180165d35  sub     rsp, 20h
0x180165d39  mov     rbp, rdx
0x180165d3c  call    TppReportExceptionFilter
0x180165d41  nop
0x180165d42  add     rsp, 20h
0x180165d46  pop     rbp
0x180165d47  retn
```
