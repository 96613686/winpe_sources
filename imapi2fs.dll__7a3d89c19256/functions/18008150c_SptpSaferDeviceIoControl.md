# SptpSaferDeviceIoControl

- ea: `0x18008150c`
- end: `0x1800815d0`
- name: `SptpSaferDeviceIoControl`
- size: `196`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, LPVOID, int, LPDWORD lpNumberOfBytesTransferred)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18008130c`

## callees

- `0x18008150c`

## import_xrefs

- `KERNEL32!CreateEventA` at `0x180081539`
- `KERNEL32!CreateEventA` at `0x180081539`
- `KERNEL32!GetOverlappedResult` at `0x1800815ab`
- `KERNEL32!GetOverlappedResult` at `0x1800815ab`
- `KERNEL32!DeviceIoControl` at `0x180081583`
- `KERNEL32!DeviceIoControl` at `0x180081583`
- `KERNEL32!CloseHandle` at `0x1800815b8`
- `KERNEL32!CloseHandle` at `0x1800815b8`
- `KERNEL32!GetLastError` at `0x18008158f`
- `KERNEL32!GetLastError` at `0x18008158f`

## pseudocode

```c
HANDLE __fastcall SptpSaferDeviceIoControl(
        HANDLE hFile,
        __int64 a2,
        void *a3,
        __int64 a4,
        LPVOID lpOutBuffer,
        int a6,
        LPDWORD lpNumberOfBytesTransferred)
{
  HANDLE result; // rax
  unsigned int OverlappedResult; // ebx
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-28h] BYREF

  memset(&Overlapped, 0, 24);
  result = CreateEventA(0, 1, 0, 0);
  Overlapped.hEvent = result;
  if ( result )
  {
    OverlappedResult = DeviceIoControl(
                         hFile,
                         0x4D014u,
                         a3,
                         0x50u,
                         lpOutBuffer,
                         0x50u,
                         lpNumberOfBytesTransferred,
                         &Overlapped);
    if ( !OverlappedResult && GetLastError() == 997 )
      OverlappedResult = GetOverlappedResult(hFile, &Overlapped, lpNumberOfBytesTransferred, 1);
    CloseHandle(Overlapped.hEvent);
    return (HANDLE)OverlappedResult;
  }
  return result;
}

```

## disassembly

```asm
0x18008150c  mov     rax, rsp
0x18008150f  mov     [rax+8], rbx
0x180081513  mov     [rax+10h], rsi
0x180081517  push    rdi
0x180081518  sub     rsp, 60h
0x18008151c  xorps   xmm0, xmm0
0x18008151f  xor     r9d, r9d; lpName
0x180081522  mov     rbx, r8
0x180081525  mov     rsi, rcx
0x180081528  xor     r8d, r8d; bInitialState
0x18008152b  xor     ecx, ecx; lpEventAttributes
0x18008152d  movups  xmmword ptr [rax-28h], xmm0
0x180081531  lea     edx, [r9+1]; bManualReset
0x180081535  movups  xmmword ptr [rax-18h], xmm0
0x180081539  call    cs:__imp_CreateEventA
0x18008153f  mov     [rsp+68h+Overlapped.hEvent], rax
0x180081544  test    rax, rax
0x180081547  jz      short loc_1800815C0
0x180081549  mov     rdi, [rsp+68h+lpNumberOfBytesTransferred]
0x180081551  lea     rax, [rsp+68h+Overlapped]
0x180081556  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18008155b  mov     r9d, 50h ; 'P'; nInBufferSize
0x180081561  mov     rax, [rsp+68h+arg_20]
0x180081569  mov     r8, rbx; lpInBuffer
0x18008156c  mov     [rsp+68h+lpBytesReturned], rdi; lpBytesReturned
0x180081571  mov     edx, 4D014h; dwIoControlCode
0x180081576  mov     [rsp+68h+nOutBufferSize], r9d; nOutBufferSize
0x18008157b  mov     rcx, rsi; hDevice
0x18008157e  mov     [rsp+68h+lpOutBuffer], rax; lpOutBuffer
0x180081583  call    cs:__imp_DeviceIoControl
0x180081589  mov     ebx, eax
0x18008158b  test    eax, eax
0x18008158d  jnz     short loc_1800815B3
0x18008158f  call    cs:__imp_GetLastError
0x180081595  cmp     eax, 3E5h
0x18008159a  jnz     short loc_1800815B3
0x18008159c  lea     r9d, [rbx+1]; bWait
0x1800815a0  mov     r8, rdi; lpNumberOfBytesTransferred
0x1800815a3  lea     rdx, [rsp+68h+Overlapped]; lpOverlapped
0x1800815a8  mov     rcx, rsi; hFile
0x1800815ab  call    cs:__imp_GetOverlappedResult
0x1800815b1  mov     ebx, eax
0x1800815b3  mov     rcx, [rsp+68h+Overlapped.hEvent]; hObject
0x1800815b8  call    cs:__imp_CloseHandle
0x1800815be  mov     eax, ebx
0x1800815c0  mov     rbx, [rsp+68h+arg_0]
0x1800815c5  mov     rsi, [rsp+68h+arg_8]
0x1800815ca  add     rsp, 60h
0x1800815ce  pop     rdi
0x1800815cf  retn
```
