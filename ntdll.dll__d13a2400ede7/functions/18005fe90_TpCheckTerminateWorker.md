# TpCheckTerminateWorker

- ea: `0x18005fe90`
- end: `0x18005ff2f`
- name: `TpCheckTerminateWorker`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18005fd30`

## callees

- `0x1800195a0`
- `0x18001a080`
- `0x18005fe90`
- `0x18005ff38`
- `0x180159d5c`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x18005fee9`: `ThreadPool: attempt to terminate a worker thread via handle %p\nContact the owner of the function calling Terminate/Exit thread.\n`

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
0x18005fe90  push    rbx
0x18005fe92  sub     rsp, 0D0h
0x18005fe99  mov     rax, cs:__security_cookie
0x18005fea0  xor     rax, rsp
0x18005fea3  mov     [rsp+0D8h+var_18], rax
0x18005feab  mov     rbx, rcx
0x18005feae  xor     edx, edx; Val
0x18005feb0  mov     r8d, 98h; Size
0x18005feb6  lea     rcx, [rsp+0D8h+ExceptionRecord]; void *
0x18005febb  call    memset$thunk$772440563353939046
0x18005fec0  mov     rcx, rbx
0x18005fec3  call    TppIsWorkerThread
0x18005fec8  test    al, al
0x18005feca  jnz     short loc_18005FEE6
0x18005fecc  mov     rcx, [rsp+0D8h+var_18]
0x18005fed4  xor     rcx, rsp; StackCookie
0x18005fed7  call    __security_check_cookie
0x18005fedc  add     rsp, 0D0h
0x18005fee3  pop     rbx
0x18005fee4  retn
0x18005fee6  mov     r9, rbx
0x18005fee9  lea     r8, aThreadpoolAtte; "ThreadPool: attempt to terminate a work"...
0x18005fef0  xor     edx, edx
0x18005fef2  lea     ecx, [rdx+54h]
0x18005fef5  call    DbgPrintEx
0x18005fefa  xor     edx, edx; Val
0x18005fefc  mov     r8d, 98h; Size
0x18005ff02  lea     rcx, [rsp+0D8h+ExceptionRecord]; void *
0x18005ff07  call    memset$thunk$772440563353939046
0x18005ff0c  mov     [rsp+0D8h+ExceptionRecord.ExceptionCode], 0C000071Ch
0x18005ff14  mov     [rsp+0D8h+ExceptionRecord.NumberParameters], 1
0x18005ff1c  mov     [rsp+0D8h+ExceptionRecord.ExceptionInformation], rbx
0x18005ff21  lea     rcx, [rsp+0D8h+ExceptionRecord]; ExceptionRecord
0x18005ff26  call    RtlRaiseException
0x18005ff2b  jmp     short loc_18005FECC
0x18005ff2d  jmp     short loc_18005FECC
0x180166843  push    rbp
0x180166845  sub     rsp, 20h
0x180166849  mov     rbp, rdx
0x18016684c  call    TppReportExceptionFilter
0x180166851  nop
0x180166852  add     rsp, 20h
0x180166856  pop     rbp
0x180166857  retn
```
