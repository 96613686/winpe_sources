# GetLogIoStatistics

- ea: `0x18000b9d0`
- end: `0x18000bb31`
- name: `GetLogIoStatistics`
- size: `353`
- prototype: `BOOL __stdcall(HANDLE hLog, PVOID pvStatsBuffer, ULONG cbStatsBuffer, CLFS_IOSTATS_CLASS eStatsClass, PULONG pcbStatsWritten)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b9d0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000bade`
- `ntdll!RtlNtStatusToDosError` at `0x18000bade`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000baa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000baa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000baf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000baf8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ba98`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ba98`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000ba54`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000ba54`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000bac4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000bac4`

## pseudocode

```c
BOOL __stdcall GetLogIoStatistics(
        HANDLE hLog,
        PVOID pvStatsBuffer,
        ULONG cbStatsBuffer,
        CLFS_IOSTATS_CLASS eStatsClass,
        PULONG pcbStatsWritten)
{
  PULONG v5; // rdi
  DWORD v9; // ecx
  unsigned __int64 EventA; // rax
  DWORD LastError; // ebx
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-28h] BYREF
  DWORD BytesReturned; // [rsp+A8h] [rbp+40h] BYREF

  v5 = pcbStatsWritten;
  BytesReturned = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( pcbStatsWritten )
    *pcbStatsWritten = 0;
  if ( !pvStatsBuffer )
  {
    v9 = 1784;
LABEL_5:
    SetLastError(v9);
    return 0;
  }
  if ( cbStatsBuffer < 0x10 )
  {
    v9 = 122;
    goto LABEL_5;
  }
  EventA = (unsigned __int64)CreateEventA(0, 1, 0, 0);
  if ( !EventA )
    return 0;
  Overlapped.hEvent = (HANDLE)(EventA | 1);
  LastError = 0;
  if ( !DeviceIoControl(hLog, 0x8007A852, 0, 0, pvStatsBuffer, cbStatsBuffer, &BytesReturned, &Overlapped) )
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
  if ( v5 )
    *v5 = BytesReturned;
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x18000b9d0  push    rbp
0x18000b9d2  push    rbx
0x18000b9d3  push    rsi
0x18000b9d4  push    rdi
0x18000b9d5  push    r14
0x18000b9d7  push    r15
0x18000b9d9  mov     rbp, rsp
0x18000b9dc  sub     rsp, 68h
0x18000b9e0  mov     rdi, [rbp+pcbStatsWritten]
0x18000b9e4  mov     esi, r8d
0x18000b9e7  mov     [rbp+BytesReturned], 0
0x18000b9ee  mov     r14, rdx
0x18000b9f1  mov     [rbp+Overlapped.Internal], 0
0x18000b9f9  mov     r15, rcx
0x18000b9fc  mov     [rbp+Overlapped.InternalHigh], 0
0x18000ba04  mov     qword ptr [rbp+Overlapped.10h], 0
0x18000ba0c  mov     [rbp+Overlapped.hEvent], 0
0x18000ba14  test    rdi, rdi
0x18000ba17  jz      short loc_18000BA1F
0x18000ba19  mov     dword ptr [rdi], 0
0x18000ba1f  test    r14, r14
0x18000ba22  jnz     short loc_18000BA3C
0x18000ba24  mov     ecx, 6F8h; dwErrCode
0x18000ba29  call    cs:__imp_SetLastError
0x18000ba30  nop     dword ptr [rax+rax+00h]
0x18000ba35  xor     eax, eax
0x18000ba37  jmp     loc_18000BB23
0x18000ba3c  cmp     esi, 10h
0x18000ba3f  jnb     short loc_18000BA48
0x18000ba41  mov     ecx, 7Ah ; 'z'
0x18000ba46  jmp     short loc_18000BA29
0x18000ba48  xor     r9d, r9d; lpName
0x18000ba4b  xor     r8d, r8d; bInitialState
0x18000ba4e  xor     ecx, ecx; lpEventAttributes
0x18000ba50  lea     edx, [r9+1]; bManualReset
0x18000ba54  call    cs:__imp_CreateEventA
0x18000ba5b  nop     dword ptr [rax+rax+00h]
0x18000ba60  test    rax, rax
0x18000ba63  jz      short loc_18000BA35
0x18000ba65  or      rax, 1
0x18000ba69  xor     r9d, r9d; nInBufferSize
0x18000ba6c  mov     [rbp+Overlapped.hEvent], rax
0x18000ba70  xor     r8d, r8d; lpInBuffer
0x18000ba73  lea     rax, [rbp+Overlapped]
0x18000ba77  mov     edx, 8007A852h; dwIoControlCode
0x18000ba7c  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18000ba81  mov     rcx, r15; hDevice
0x18000ba84  lea     rax, [rbp+BytesReturned]
0x18000ba88  xor     ebx, ebx
0x18000ba8a  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x18000ba8f  mov     [rsp+68h+nOutBufferSize], esi; nOutBufferSize
0x18000ba93  mov     [rsp+68h+lpOutBuffer], r14; lpOutBuffer
0x18000ba98  call    cs:__imp_DeviceIoControl
0x18000ba9f  nop     dword ptr [rax+rax+00h]
0x18000baa4  test    eax, eax
0x18000baa6  jnz     short loc_18000BAEC
0x18000baa8  call    cs:__imp_GetLastError
0x18000baaf  nop     dword ptr [rax+rax+00h]
0x18000bab4  mov     ebx, eax
0x18000bab6  cmp     eax, 3E5h
0x18000babb  jnz     short loc_18000BAEC
0x18000babd  mov     rcx, [rbp+Overlapped.hEvent]; hHandle
0x18000bac1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000bac4  call    cs:__imp_WaitForSingleObject
0x18000bacb  nop     dword ptr [rax+rax+00h]
0x18000bad0  test    eax, eax
0x18000bad2  jz      short loc_18000BADB
0x18000bad4  mov     ebx, 45Dh
0x18000bad9  jmp     short loc_18000BAEC
0x18000badb  mov     ecx, dword ptr [rbp+Overlapped.Internal]; Status
0x18000bade  call    cs:__imp_RtlNtStatusToDosError
0x18000bae5  nop     dword ptr [rax+rax+00h]
0x18000baea  mov     ebx, eax
0x18000baec  mov     rcx, [rbp+Overlapped.hEvent]
0x18000baf0  and     rcx, 0FFFFFFFFFFFFFFFEh; hObject
0x18000baf4  mov     [rbp+Overlapped.hEvent], rcx
0x18000baf8  call    cs:__imp_CloseHandle
0x18000baff  nop     dword ptr [rax+rax+00h]
0x18000bb04  test    rdi, rdi
0x18000bb07  jz      short loc_18000BB0E
0x18000bb09  mov     eax, [rbp+BytesReturned]
0x18000bb0c  mov     [rdi], eax
0x18000bb0e  mov     ecx, ebx; dwErrCode
0x18000bb10  call    cs:__imp_SetLastError
0x18000bb17  nop     dword ptr [rax+rax+00h]
0x18000bb1c  xor     eax, eax
0x18000bb1e  test    ebx, ebx
0x18000bb20  setz    al
0x18000bb23  add     rsp, 68h
0x18000bb27  pop     r15
0x18000bb29  pop     r14
0x18000bb2b  pop     rdi
0x18000bb2c  pop     rsi
0x18000bb2d  pop     rbx
0x18000bb2e  pop     rbp
0x18000bb2f  retn
```
