# SockSanFreeProvider

- ea: `0x180042b50`
- end: `0x180042bc1`
- name: `SockSanFreeProvider`
- size: `113`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `14`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003e820`
- `0x180041b44`
- `0x1800423ec`
- `0x1800427e8`
- `0x180044bc8`
- `0x18004c324`
- `0x18004cb1c`
- `0x18004cd90`
- `0x18004d1d8`
- `0x18004d924`
- `0x18004e9dc`
- `0x18004eda0`
- `0x1800514d0`
- `0x180051b7c`

## callees

- `0x1800028b8`
- `0x180038104`
- `0x180042b50`

## import_xrefs

- `ntdll!NtSetIoCompletion` at `0x180042ba3`
- `ntdll!NtSetIoCompletion` at `0x180042ba3`

## pseudocode

```c
char __fastcall SockSanFreeProvider(PVOID CompletionContext)
{
  NTSTATUS v2; // eax

  LOBYTE(v2) = SockCheckAndReferenceAsyncThread();
  if ( (_BYTE)v2 )
  {
    v2 = NtSetIoCompletion(SockAsyncQueuePort, SockSanAsyncFreeProvider, CompletionContext, 0, 0);
    if ( v2 < 0 )
      _InterlockedDecrement(&SockAsyncThreadReferenceCount);
  }
  else if ( (xmmword_180063D60 & 2) != 0 )
  {
    LOBYTE(v2) = WPP_SF_(1025, 57, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
  }
  return v2;
}

```

## disassembly

```asm
0x180042b50  push    rbx
0x180042b52  sub     rsp, 30h
0x180042b56  mov     rbx, rcx
0x180042b59  call    SockCheckAndReferenceAsyncThread
0x180042b5e  test    al, al
0x180042b60  jnz     short loc_180042B86
0x180042b62  test    byte ptr cs:xmmword_180063D60, 2
0x180042b69  jz      short loc_180042BBA
0x180042b6b  mov     edx, 39h ; '9'
0x180042b70  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x180042b77  mov     ecx, 401h
0x180042b7c  add     rsp, 30h
0x180042b80  pop     rbx
0x180042b81  jmp     WPP_SF_
0x180042b86  mov     rcx, cs:SockAsyncQueuePort; IoCompletionPortHandle
0x180042b8d  lea     rdx, SockSanAsyncFreeProvider; CompletionKey
0x180042b94  xor     r9d, r9d; CompletionStatus
0x180042b97  mov     qword ptr [rsp+38h+CompletionInformation], 0; CompletionInformation
0x180042ba0  mov     r8, rbx; CompletionContext
0x180042ba3  call    cs:__imp_NtSetIoCompletion
0x180042baa  nop     dword ptr [rax+rax+00h]
0x180042baf  test    eax, eax
0x180042bb1  jns     short loc_180042BBA
0x180042bb3  lock dec cs:SockAsyncThreadReferenceCount
0x180042bba  add     rsp, 30h
0x180042bbe  pop     rbx
0x180042bbf  retn
```
