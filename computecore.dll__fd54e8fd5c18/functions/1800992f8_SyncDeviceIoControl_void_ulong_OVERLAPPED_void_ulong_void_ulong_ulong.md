# SyncDeviceIoControl(void *,ulong,_OVERLAPPED *,void *,ulong,void *,ulong,ulong *)

- ea: `0x1800992f8`
- end: `0x1800993e7`
- name: `?SyncDeviceIoControl@@YAHPEAXKPEAU_OVERLAPPED@@0K0KPEAK@Z`
- size: `239`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, DWORD dwIoControlCode@<edx>, struct _OVERLAPPED *@<r8>, void *@<r9>, DWORD nInBufferSize, void *, unsigned int, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18005e5a0`
- `0x18005e930`
- `0x18005f0b0`
- `0x180097848`
- `0x180099600`

## callees

- `0x1800067c0`
- `0x1800992f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099343`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009939e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009939e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800993c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800993c7`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800993bc`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800993bc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180099392`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180099392`

## pseudocode

```c
__int64 __fastcall SyncDeviceIoControl(
        HANDLE hFile,
        DWORD dwIoControlCode,
        struct _OVERLAPPED *a3,
        void *a4,
        DWORD nInBufferSize,
        void *lpOutBuffer,
        DWORD nOutBufferSize)
{
  unsigned __int64 EventW; // rax
  void *v11; // rdi
  unsigned int OverlappedResult; // ebx
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-58h] BYREF
  DWORD BytesReturned; // [rsp+60h] [rbp-38h] BYREF

  BytesReturned = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  EventW = (unsigned __int64)CreateEventW(0, 1, 0, 0);
  v11 = (void *)EventW;
  if ( EventW )
  {
    Overlapped.hEvent = (HANDLE)(EventW | 1);
    OverlappedResult = DeviceIoControl(
                         hFile,
                         dwIoControlCode,
                         a4,
                         nInBufferSize,
                         lpOutBuffer,
                         nOutBufferSize,
                         &BytesReturned,
                         &Overlapped);
    if ( !OverlappedResult && GetLastError() == 997 )
      OverlappedResult = GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1);
    CloseHandle(v11);
  }
  else
  {
    return 0;
  }
  return OverlappedResult;
}

```

## disassembly

```asm
0x1800992f8  push    rbx
0x1800992fa  push    rbp
0x1800992fb  push    rsi
0x1800992fc  push    rdi
0x1800992fd  push    r14
0x1800992ff  sub     rsp, 70h
0x180099303  mov     rax, cs:__security_cookie
0x18009930a  xor     rax, rsp
0x18009930d  mov     [rsp+98h+var_30], rax
0x180099312  mov     r14, [rsp+98h+arg_28]
0x18009931a  xorps   xmm0, xmm0
0x18009931d  mov     rbp, r9
0x180099320  mov     [rsp+98h+BytesReturned], 0
0x180099328  xor     r9d, r9d; lpName
0x18009932b  mov     ebx, edx
0x18009932d  mov     rsi, rcx
0x180099330  xor     r8d, r8d; bInitialState
0x180099333  xor     ecx, ecx; lpEventAttributes
0x180099335  movups  xmmword ptr [rsp+98h+Overlapped.Internal], xmm0
0x18009933a  lea     edx, [r9+1]; bManualReset
0x18009933e  movups  xmmword ptr [rsp+98h+Overlapped.10h], xmm0
0x180099343  call    cs:__imp_CreateEventW
0x180099349  mov     rdi, rax
0x18009934c  test    rax, rax
0x18009934f  jnz     short loc_180099355
0x180099351  xor     ebx, ebx
0x180099353  jmp     short loc_1800993CD
0x180099355  mov     r9d, [rsp+98h+nInBufferSize]; nInBufferSize
0x18009935d  or      rax, 1
0x180099361  mov     [rsp+98h+Overlapped.hEvent], rax
0x180099366  mov     r8, rbp; lpInBuffer
0x180099369  lea     rax, [rsp+98h+Overlapped]
0x18009936e  mov     edx, ebx; dwIoControlCode
0x180099370  mov     [rsp+98h+lpOverlapped], rax; lpOverlapped
0x180099375  mov     rcx, rsi; hDevice
0x180099378  lea     rax, [rsp+98h+BytesReturned]
0x18009937d  mov     [rsp+98h+lpBytesReturned], rax; lpBytesReturned
0x180099382  mov     eax, [rsp+98h+arg_30]
0x180099389  mov     [rsp+98h+nOutBufferSize], eax; nOutBufferSize
0x18009938d  mov     [rsp+98h+lpOutBuffer], r14; lpOutBuffer
0x180099392  call    cs:__imp_DeviceIoControl
0x180099398  mov     ebx, eax
0x18009939a  test    eax, eax
0x18009939c  jnz     short loc_1800993C4
0x18009939e  call    cs:__imp_GetLastError
0x1800993a4  cmp     eax, 3E5h
0x1800993a9  jnz     short loc_1800993C4
0x1800993ab  lea     r9d, [rbx+1]; bWait
0x1800993af  mov     rcx, rsi; hFile
0x1800993b2  lea     r8, [rsp+98h+BytesReturned]; lpNumberOfBytesTransferred
0x1800993b7  lea     rdx, [rsp+98h+Overlapped]; lpOverlapped
0x1800993bc  call    cs:__imp_GetOverlappedResult
0x1800993c2  mov     ebx, eax
0x1800993c4  mov     rcx, rdi; hObject
0x1800993c7  call    cs:__imp_CloseHandle
0x1800993cd  mov     eax, ebx
0x1800993cf  mov     rcx, [rsp+98h+var_30]
0x1800993d4  xor     rcx, rsp; StackCookie
0x1800993d7  call    __security_check_cookie
0x1800993dc  add     rsp, 70h
0x1800993e0  pop     r14
0x1800993e2  pop     rdi
0x1800993e3  pop     rsi
0x1800993e4  pop     rbp
0x1800993e5  pop     rbx
0x1800993e6  retn
```
