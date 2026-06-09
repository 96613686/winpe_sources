# NtAdvanceLogBaseInternal(void *,_CLS_LSN *,void *,uchar,_OVERLAPPED *)

- ea: `0x1800089bc`
- end: `0x180008af1`
- name: `?NtAdvanceLogBaseInternal@@YAKPEAXPEAT_CLS_LSN@@0EPEAU_OVERLAPPED@@@Z`
- size: `309`
- prototype: `unsigned int __fastcall(HANDLE hDevice, union _CLS_LSN *lpInBuffer, void *, unsigned __int8, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e004`

## callees

- `0x1800089bc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180008ab4`
- `ntdll!RtlNtStatusToDosError` at `0x180008ab4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ad2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ad2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008a6e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008a6e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008a17`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008a17`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008a9a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008a9a`

## pseudocode

```c
__int64 __fastcall NtAdvanceLogBaseInternal(HANDLE hDevice, union _CLS_LSN *lpInBuffer, void *a3)
{
  unsigned __int64 EventA; // rax
  DWORD LastError; // ebx
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-20h] BYREF
  DWORD BytesReturned; // [rsp+88h] [rbp+28h] BYREF

  memset(&Overlapped, 0, sizeof(Overlapped));
  BytesReturned = 0;
  if ( !lpInBuffer )
    return 87;
  EventA = (unsigned __int64)CreateEventA(0, 0, 0, 0);
  if ( !EventA )
    return 8;
  Overlapped.hEvent = (HANDLE)(EventA | 1);
  if ( DeviceIoControl(hDevice, 0x8007A85C, lpInBuffer, 8u, 0, 0, &BytesReturned, &Overlapped) )
  {
    LastError = 0;
  }
  else
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
  CloseHandle((HANDLE)((unsigned __int64)Overlapped.hEvent & 0xFFFFFFFFFFFFFFFEuLL));
  return LastError;
}

```

## disassembly

```asm
0x1800089bc  mov     [rsp-8+arg_0], rbx
0x1800089c1  mov     [rsp-8+arg_8], rdi
0x1800089c6  mov     byte ptr [rsp-8+BytesReturned], r9b
0x1800089cb  push    rbp
0x1800089cc  mov     rbp, rsp
0x1800089cf  sub     rsp, 60h
0x1800089d3  mov     [rbp+Overlapped.Internal], 0
0x1800089db  mov     rbx, rdx
0x1800089de  mov     [rbp+Overlapped.InternalHigh], 0
0x1800089e6  mov     rdi, rcx
0x1800089e9  mov     qword ptr [rbp+Overlapped.10h], 0
0x1800089f1  mov     [rbp+Overlapped.hEvent], 0
0x1800089f9  mov     [rbp+BytesReturned], 0
0x180008a00  test    rdx, rdx
0x180008a03  jnz     short loc_180008A0D
0x180008a05  lea     eax, [rdx+57h]
0x180008a08  jmp     loc_180008AE0
0x180008a0d  xor     r9d, r9d; lpName
0x180008a10  xor     r8d, r8d; bInitialState
0x180008a13  xor     edx, edx; bManualReset
0x180008a15  xor     ecx, ecx; lpEventAttributes
0x180008a17  call    cs:__imp_CreateEventA
0x180008a1e  nop     dword ptr [rax+rax+00h]
0x180008a23  test    rax, rax
0x180008a26  jnz     short loc_180008A32
0x180008a28  mov     eax, 8
0x180008a2d  jmp     loc_180008AE0
0x180008a32  or      rax, 1
0x180008a36  mov     r9d, 8; nInBufferSize
0x180008a3c  mov     [rbp+Overlapped.hEvent], rax
0x180008a40  mov     r8, rbx; lpInBuffer
0x180008a43  lea     rax, [rbp+Overlapped]
0x180008a47  mov     edx, 8007A85Ch; dwIoControlCode
0x180008a4c  mov     [rsp+60h+lpOverlapped], rax; lpOverlapped
0x180008a51  mov     rcx, rdi; hDevice
0x180008a54  lea     rax, [rbp+BytesReturned]
0x180008a58  mov     [rsp+60h+lpBytesReturned], rax; lpBytesReturned
0x180008a5d  mov     [rsp+60h+nOutBufferSize], 0; nOutBufferSize
0x180008a65  mov     [rsp+60h+lpOutBuffer], 0; lpOutBuffer
0x180008a6e  call    cs:__imp_DeviceIoControl
0x180008a75  nop     dword ptr [rax+rax+00h]
0x180008a7a  test    eax, eax
0x180008a7c  jnz     short loc_180008AC4
0x180008a7e  call    cs:__imp_GetLastError
0x180008a85  nop     dword ptr [rax+rax+00h]
0x180008a8a  mov     ebx, eax
0x180008a8c  cmp     eax, 3E5h
0x180008a91  jnz     short loc_180008AC6
0x180008a93  mov     rcx, [rbp+Overlapped.hEvent]; hHandle
0x180008a97  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008a9a  call    cs:__imp_WaitForSingleObject
0x180008aa1  nop     dword ptr [rax+rax+00h]
0x180008aa6  test    eax, eax
0x180008aa8  jz      short loc_180008AB1
0x180008aaa  mov     ebx, 45Dh
0x180008aaf  jmp     short loc_180008AC6
0x180008ab1  mov     ecx, dword ptr [rbp+Overlapped.Internal]; Status
0x180008ab4  call    cs:__imp_RtlNtStatusToDosError
0x180008abb  nop     dword ptr [rax+rax+00h]
0x180008ac0  mov     ebx, eax
0x180008ac2  jmp     short loc_180008AC6
0x180008ac4  xor     ebx, ebx
0x180008ac6  mov     rcx, [rbp+Overlapped.hEvent]
0x180008aca  and     rcx, 0FFFFFFFFFFFFFFFEh; hObject
0x180008ace  mov     [rbp+Overlapped.hEvent], rcx
0x180008ad2  call    cs:__imp_CloseHandle
0x180008ad9  nop     dword ptr [rax+rax+00h]
0x180008ade  mov     eax, ebx
0x180008ae0  mov     rbx, [rsp+60h+arg_0]
0x180008ae5  mov     rdi, [rsp+60h+arg_8]
0x180008aea  add     rsp, 60h
0x180008aee  pop     rbp
0x180008aef  retn
```
