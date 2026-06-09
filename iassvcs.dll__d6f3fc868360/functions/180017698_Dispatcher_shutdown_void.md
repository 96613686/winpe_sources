# Dispatcher::shutdown(void)

- ea: `0x180017698`
- end: `0x18001771a`
- name: `?shutdown@Dispatcher@@QEAAXXZ`
- size: `130`
- prototype: `void __fastcall(Dispatcher *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cd50`
- `0x18000cda0`

## callees

- `0x180017698`

## import_xrefs

- `KERNEL32!TryEnterCriticalSection` at `0x1800176b6`
- `KERNEL32!TryEnterCriticalSection` at `0x1800176b6`
- `KERNEL32!SwitchToThread` at `0x1800176a9`
- `KERNEL32!SwitchToThread` at `0x1800176a9`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180017709`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180017709`
- `KERNEL32!EnterCriticalSection` at `0x1800176c9`
- `KERNEL32!EnterCriticalSection` at `0x1800176c9`
- `KERNEL32!LeaveCriticalSection` at `0x1800176f0`
- `KERNEL32!LeaveCriticalSection` at `0x1800176f0`

## pseudocode

```c
void __fastcall Dispatcher::shutdown(Dispatcher *this)
{
  int v1; // ebx
  int v2; // ebx

  v1 = 0;
  while ( !TryEnterCriticalSection(&dispatcher) )
  {
    if ( ++v1 >= 100 )
    {
      EnterCriticalSection(&dispatcher);
      break;
    }
    SwitchToThread();
  }
  v2 = qword_180024F18;
  dword_180024F40 = 1;
  HIDWORD(qword_180024F18) = 0;
  LeaveCriticalSection(&dispatcher);
  for ( ; v2; --v2 )
    PostQueuedCompletionStatus(CompletionPort, 0, 0, 0);
}

```

## disassembly

```asm
0x180017698  push    rbx
0x18001769a  sub     rsp, 20h
0x18001769e  xor     ebx, ebx
0x1800176a0  jmp     short loc_1800176AF
0x1800176a2  inc     ebx
0x1800176a4  cmp     ebx, 64h ; 'd'
0x1800176a7  jge     short loc_1800176C2
0x1800176a9  call    cs:__imp_SwitchToThread
0x1800176af  lea     rcx, ?dispatcher@@3VDispatcher@@A; lpCriticalSection
0x1800176b6  call    cs:__imp_TryEnterCriticalSection
0x1800176bc  test    eax, eax
0x1800176be  jz      short loc_1800176A2
0x1800176c0  jmp     short loc_1800176CF
0x1800176c2  lea     rcx, ?dispatcher@@3VDispatcher@@A; lpCriticalSection
0x1800176c9  call    cs:__imp_EnterCriticalSection
0x1800176cf  mov     ebx, dword ptr cs:qword_180024F18
0x1800176d5  lea     rcx, ?dispatcher@@3VDispatcher@@A; lpCriticalSection
0x1800176dc  mov     cs:dword_180024F40, 1
0x1800176e6  mov     dword ptr cs:qword_180024F18+4, 0
0x1800176f0  call    cs:__imp_LeaveCriticalSection
0x1800176f6  test    ebx, ebx
0x1800176f8  jz      short loc_180017714
0x1800176fa  mov     rcx, cs:CompletionPort; CompletionPort
0x180017701  xor     r9d, r9d; lpOverlapped
0x180017704  xor     r8d, r8d; dwCompletionKey
0x180017707  xor     edx, edx; dwNumberOfBytesTransferred
0x180017709  call    cs:__imp_PostQueuedCompletionStatus
0x18001770f  add     ebx, 0FFFFFFFFh
0x180017712  jnz     short loc_1800176FA
0x180017714  add     rsp, 20h
0x180017718  pop     rbx
0x180017719  retn
```
