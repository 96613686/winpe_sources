# CheckForSocketDuplicationProtocol

- ea: `0x180023f14`
- end: `0x180023fcd`
- name: `CheckForSocketDuplicationProtocol`
- size: `185`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180023cc0`
- `0x18003b760`
- `0x18004642c`
- `0x1800485dc`
- `0x18004958c`
- `0x18004d924`
- `0x18005284c`

## callees

- `0x1800028b8`
- `0x180023f14`

## import_xrefs

- `ntdll!NtSetIoCompletion` at `0x180023faa`
- `ntdll!NtSetIoCompletion` at `0x180023faa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023f7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023f7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023f68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023f68`

## pseudocode

```c
void __fastcall CheckForSocketDuplicationProtocol(char *CompletionContext)
{
  if ( (*((_DWORD *)CompletionContext + 44) == 1
     && *((char **)CompletionContext + 50) == CompletionContext + 400
     && *((char **)CompletionContext + 40) == CompletionContext + 320
     || CompletionContext[208])
    && SockCheckAndReferenceAsyncThread() )
  {
    _InterlockedIncrement(*((volatile signed __int32 **)CompletionContext + 1));
    if ( CompletionContext[208] )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      CompletionContext[208] = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    }
    if ( NtSetIoCompletion(
           SockAsyncQueuePort,
           SockSanDupSockCtrlMsg,
           CompletionContext,
           0,
           *((_DWORD *)CompletionContext + 44)) < 0 )
      _InterlockedDecrement(&SockAsyncThreadReferenceCount);
  }
}

```

## disassembly

```asm
0x180023f14  mov     [rsp+arg_0], rbx
0x180023f19  push    rdi
0x180023f1a  sub     rsp, 30h
0x180023f1e  cmp     dword ptr [rcx+0B0h], 1
0x180023f25  mov     rdi, rcx
0x180023f28  jnz     short loc_180023F42
0x180023f2a  lea     rax, [rcx+190h]
0x180023f31  cmp     [rax], rax
0x180023f34  jnz     short loc_180023F42
0x180023f36  lea     rax, [rcx+140h]
0x180023f3d  cmp     [rax], rax
0x180023f40  jz      short loc_180023F4B
0x180023f42  cmp     byte ptr [rcx+0D0h], 0
0x180023f49  jz      short loc_180023FC1
0x180023f4b  call    SockCheckAndReferenceAsyncThread
0x180023f50  test    al, al
0x180023f52  jz      short loc_180023FC1
0x180023f54  mov     rax, [rdi+8]
0x180023f58  lock inc dword ptr [rax]
0x180023f5b  cmp     byte ptr [rdi+0D0h], 0
0x180023f62  jz      short loc_180023F8B
0x180023f64  lea     rcx, [rdi+30h]; lpCriticalSection
0x180023f68  call    cs:__imp_EnterCriticalSection
0x180023f6f  nop     dword ptr [rax+rax+00h]
0x180023f74  lea     rcx, [rdi+30h]; lpCriticalSection
0x180023f78  mov     byte ptr [rdi+0D0h], 0
0x180023f7f  call    cs:__imp_LeaveCriticalSection
0x180023f86  nop     dword ptr [rax+rax+00h]
0x180023f8b  mov     eax, [rdi+0B0h]
0x180023f91  lea     rdx, SockSanDupSockCtrlMsg; CompletionKey
0x180023f98  mov     rcx, cs:SockAsyncQueuePort; IoCompletionPortHandle
0x180023f9f  xor     r9d, r9d; CompletionStatus
0x180023fa2  mov     r8, rdi; CompletionContext
0x180023fa5  mov     qword ptr [rsp+38h+CompletionInformation], rax; CompletionInformation
0x180023faa  call    cs:__imp_NtSetIoCompletion
0x180023fb1  nop     dword ptr [rax+rax+00h]
0x180023fb6  test    eax, eax
0x180023fb8  jns     short loc_180023FC1
0x180023fba  lock dec cs:SockAsyncThreadReferenceCount
0x180023fc1  mov     rbx, [rsp+38h+arg_0]
0x180023fc6  add     rsp, 30h
0x180023fca  pop     rdi
0x180023fcb  retn
```
