# CloseAndResetLogFile

- ea: `0x180009be0`
- end: `0x180009d2b`
- name: `CloseAndResetLogFile`
- size: `331`
- prototype: `BOOL __stdcall(HANDLE hLog)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009be0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180009cb6`
- `ntdll!RtlNtStatusToDosError` at `0x180009cb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009d0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cdf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180009c70`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180009c70`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180009c28`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180009c28`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009c9c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009c9c`

## pseudocode

```c
BOOL __stdcall CloseAndResetLogFile(HANDLE hLog)
{
  unsigned __int64 EventA; // rax
  DWORD LastError; // edi
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-20h] BYREF
  DWORD BytesReturned; // [rsp+78h] [rbp+18h] BYREF

  BytesReturned = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  EventA = (unsigned __int64)CreateEventA(0, 1, 0, 0);
  if ( EventA )
  {
    LastError = 0;
    Overlapped.hEvent = (HANDLE)(EventA | 1);
    if ( !DeviceIoControl(hLog, 0x8007A838, 0, 0, 0, 0, &BytesReturned, &Overlapped) )
    {
      LastError = GetLastError();
      if ( LastError == 997 )
      {
        if ( WaitForSingleObject(Overlapped.hEvent, 0xFFFFFFFF) )
          LastError = 1117;
        else
          LastError = RtlNtStatusToDosError(Overlapped.Internal);
      }
    }
    Overlapped.hEvent = (HANDLE)((unsigned __int64)Overlapped.hEvent & ~1uLL);
    CloseHandle(Overlapped.hEvent);
    if ( !CloseHandle(hLog) && !LastError )
      LastError = GetLastError();
    SetLastError(LastError);
    LODWORD(EventA) = LastError == 0;
  }
  return EventA;
}

```

## disassembly

```asm
0x180009be0  mov     [rsp-8+arg_0], rbx
0x180009be5  mov     [rsp-8+arg_10], rdi
0x180009bea  push    rbp
0x180009beb  mov     rbp, rsp
0x180009bee  sub     rsp, 60h
0x180009bf2  xor     r9d, r9d; lpName
0x180009bf5  mov     [rbp+BytesReturned], 0
0x180009bfc  mov     rbx, rcx
0x180009bff  mov     [rbp+Overlapped.Internal], 0
0x180009c07  xor     r8d, r8d; bInitialState
0x180009c0a  mov     [rbp+Overlapped.InternalHigh], 0
0x180009c12  xor     ecx, ecx; lpEventAttributes
0x180009c14  mov     qword ptr [rbp+Overlapped.10h], 0
0x180009c1c  lea     edx, [r9+1]; bManualReset
0x180009c20  mov     [rbp+Overlapped.hEvent], 0
0x180009c28  call    cs:__imp_CreateEventA
0x180009c2f  nop     dword ptr [rax+rax+00h]
0x180009c34  test    rax, rax
0x180009c37  jz      loc_180009D18
0x180009c3d  or      rax, 1
0x180009c41  xor     edi, edi
0x180009c43  mov     [rbp+Overlapped.hEvent], rax
0x180009c47  xor     r9d, r9d; nInBufferSize
0x180009c4a  lea     rax, [rbp+Overlapped]
0x180009c4e  xor     r8d, r8d; lpInBuffer
0x180009c51  mov     [rsp+60h+lpOverlapped], rax; lpOverlapped
0x180009c56  mov     edx, 8007A838h; dwIoControlCode
0x180009c5b  lea     rax, [rbp+BytesReturned]
0x180009c5f  mov     rcx, rbx; hDevice
0x180009c62  mov     [rsp+60h+lpBytesReturned], rax; lpBytesReturned
0x180009c67  mov     [rsp+60h+nOutBufferSize], edi; nOutBufferSize
0x180009c6b  mov     [rsp+60h+lpOutBuffer], rdi; lpOutBuffer
0x180009c70  call    cs:__imp_DeviceIoControl
0x180009c77  nop     dword ptr [rax+rax+00h]
0x180009c7c  test    eax, eax
0x180009c7e  jnz     short loc_180009CC4
0x180009c80  call    cs:__imp_GetLastError
0x180009c87  nop     dword ptr [rax+rax+00h]
0x180009c8c  mov     edi, eax
0x180009c8e  cmp     eax, 3E5h
0x180009c93  jnz     short loc_180009CC4
0x180009c95  mov     rcx, [rbp+Overlapped.hEvent]; hHandle
0x180009c99  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009c9c  call    cs:__imp_WaitForSingleObject
0x180009ca3  nop     dword ptr [rax+rax+00h]
0x180009ca8  test    eax, eax
0x180009caa  jz      short loc_180009CB3
0x180009cac  mov     edi, 45Dh
0x180009cb1  jmp     short loc_180009CC4
0x180009cb3  mov     ecx, dword ptr [rbp+Overlapped.Internal]; Status
0x180009cb6  call    cs:__imp_RtlNtStatusToDosError
0x180009cbd  nop     dword ptr [rax+rax+00h]
0x180009cc2  mov     edi, eax
0x180009cc4  mov     rcx, [rbp+Overlapped.hEvent]
0x180009cc8  and     rcx, 0FFFFFFFFFFFFFFFEh; hObject
0x180009ccc  mov     [rbp+Overlapped.hEvent], rcx
0x180009cd0  call    cs:__imp_CloseHandle
0x180009cd7  nop     dword ptr [rax+rax+00h]
0x180009cdc  mov     rcx, rbx; hObject
0x180009cdf  call    cs:__imp_CloseHandle
0x180009ce6  nop     dword ptr [rax+rax+00h]
0x180009ceb  test    eax, eax
0x180009ced  jnz     short loc_180009D01
0x180009cef  test    edi, edi
0x180009cf1  jnz     short loc_180009D01
0x180009cf3  call    cs:__imp_GetLastError
0x180009cfa  nop     dword ptr [rax+rax+00h]
0x180009cff  mov     edi, eax
0x180009d01  xor     ebx, ebx
0x180009d03  mov     ecx, edi; dwErrCode
0x180009d05  test    edi, edi
0x180009d07  setz    bl
0x180009d0a  call    cs:__imp_SetLastError
0x180009d11  nop     dword ptr [rax+rax+00h]
0x180009d16  mov     eax, ebx
0x180009d18  lea     r11, [rsp+60h+var_s0]
0x180009d1d  mov     rbx, [r11+10h]
0x180009d21  mov     rdi, [r11+20h]
0x180009d25  mov     rsp, r11
0x180009d28  pop     rbp
0x180009d29  retn
```
