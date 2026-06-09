# Rdp::Utils::TP::details::CCompletionPortIo::CompletionPortWorker(void)

- ea: `0x180010280`
- end: `0x18001031b`
- name: `?CompletionPortWorker@CCompletionPortIo@details@TP@Utils@Rdp@@AEAAXXZ`
- size: `155`
- prototype: `void __fastcall(Rdp::Utils::TP::details::CCompletionPortIo *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001003c`
- `0x180010280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102ed`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x1800102c9`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x1800102c9`

## pseudocode

```c
void __fastcall Rdp::Utils::TP::details::CCompletionPortIo::CompletionPortWorker(
        Rdp::Utils::TP::details::CCompletionPortIo *this)
{
  void *v2; // rcx
  BOOL QueuedCompletionStatus; // eax
  LPOVERLAPPED v4; // rdx
  DWORD LastError; // eax
  DWORD NumberOfBytesTransferred; // [rsp+40h] [rbp+8h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int64 CompletionKey; // [rsp+50h] [rbp+18h] BYREF

  while ( !*((_BYTE *)this + 24) )
  {
    v2 = *(void **)this;
    NumberOfBytesTransferred = 0;
    CompletionKey = 0;
    Overlapped = 0;
    QueuedCompletionStatus = GetQueuedCompletionStatus(
                               v2,
                               &NumberOfBytesTransferred,
                               &CompletionKey,
                               &Overlapped,
                               0xFFFFFFFF);
    if ( CompletionKey == 3735928559 )
      break;
    v4 = Overlapped;
    if ( Overlapped )
    {
      if ( QueuedCompletionStatus )
      {
        LastError = 0;
      }
      else
      {
        LastError = GetLastError();
        v4 = Overlapped;
      }
      if ( *((_QWORD *)this + 11) )
        std::_Func_class<void,void *,unsigned long,unsigned __int64>::operator()(
          (char *)this + 32,
          v4,
          LastError,
          NumberOfBytesTransferred);
    }
  }
}

```

## disassembly

```asm
0x180010280  push    rbx
0x180010282  sub     rsp, 30h
0x180010286  mov     rbx, rcx
0x180010289  mov     al, [rbx+18h]
0x18001028c  nop
0x18001028d  test    al, al
0x18001028f  jnz     loc_180010315
0x180010295  mov     rcx, [rbx]; CompletionPort
0x180010298  lea     r9, [rsp+38h+Overlapped]; lpOverlapped
0x18001029d  lea     r8, [rsp+38h+CompletionKey]; lpCompletionKey
0x1800102a2  mov     [rsp+38h+NumberOfBytesTransferred], 0
0x1800102aa  lea     rdx, [rsp+38h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800102af  mov     [rsp+38h+CompletionKey], 0
0x1800102b8  mov     [rsp+38h+Overlapped], 0
0x1800102c1  mov     [rsp+38h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1800102c9  call    cs:__imp_GetQueuedCompletionStatus
0x1800102cf  mov     ecx, 0DEADBEEFh
0x1800102d4  cmp     [rsp+38h+CompletionKey], rcx
0x1800102d9  jz      short loc_180010315
0x1800102db  mov     rdx, [rsp+38h+Overlapped]
0x1800102e0  test    rdx, rdx
0x1800102e3  jz      short loc_180010289
0x1800102e5  test    eax, eax
0x1800102e7  jz      short loc_1800102ED
0x1800102e9  xor     eax, eax
0x1800102eb  jmp     short loc_1800102F8
0x1800102ed  call    cs:__imp_GetLastError
0x1800102f3  mov     rdx, [rsp+38h+Overlapped]
0x1800102f8  lea     rcx, [rbx+20h]
0x1800102fc  cmp     qword ptr [rcx+38h], 0
0x180010301  jz      short loc_180010289
0x180010303  mov     r9d, [rsp+38h+NumberOfBytesTransferred]
0x180010308  mov     r8d, eax
0x18001030b  call    ??R?$_Func_class@XPEAXK_K@std@@QEBAXPEAXK_K@Z; std::_Func_class<void,void *,ulong,unsigned __int64>::operator()(void *,ulong,unsigned __int64)
0x180010310  jmp     loc_180010289
0x180010315  add     rsp, 30h
0x180010319  pop     rbx
0x18001031a  retn
```
