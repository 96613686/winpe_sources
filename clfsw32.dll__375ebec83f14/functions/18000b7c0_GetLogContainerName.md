# GetLogContainerName

- ea: `0x18000b7c0`
- end: `0x18000b92d`
- name: `GetLogContainerName`
- size: `365`
- prototype: `BOOL __stdcall(HANDLE hLog, CLFS_CONTAINER_ID cidLogicalContainer, LPCWSTR pwstrContainerName, ULONG cLenContainerName, PULONG pcActualLenContainerName)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b7c0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000b8d1`
- `ntdll!RtlNtStatusToDosError` at `0x18000b8d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b823`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b8f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b823`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b8f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b89b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b89b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8eb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b88b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b88b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000b842`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000b842`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b8b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b8b7`

## pseudocode

```c
BOOL __stdcall GetLogContainerName(
        HANDLE hLog,
        CLFS_CONTAINER_ID cidLogicalContainer,
        LPCWSTR pwstrContainerName,
        ULONG cLenContainerName,
        PULONG pcActualLenContainerName)
{
  PULONG v5; // rdi
  unsigned __int64 EventA; // rax
  DWORD LastError; // ebx
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-20h] BYREF
  CLFS_CONTAINER_ID InBuffer; // [rsp+98h] [rbp+38h] BYREF
  DWORD BytesReturned; // [rsp+A0h] [rbp+40h] BYREF

  InBuffer = cidLogicalContainer;
  v5 = pcActualLenContainerName;
  BytesReturned = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( pcActualLenContainerName )
    *pcActualLenContainerName = 0;
  if ( !pwstrContainerName && cLenContainerName )
  {
    SetLastError(0x57u);
    return 0;
  }
  EventA = (unsigned __int64)CreateEventA(0, 1, 0, 0);
  if ( !EventA )
    return 0;
  Overlapped.hEvent = (HANDLE)(EventA | 1);
  LastError = 0;
  if ( !DeviceIoControl(
          hLog,
          0x8007684A,
          &InBuffer,
          4u,
          (LPVOID)pwstrContainerName,
          2 * cLenContainerName,
          &BytesReturned,
          &Overlapped) )
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
  SetLastError(LastError);
  if ( v5 )
    *v5 = BytesReturned >> 1;
  return LastError == 0;
}

```

## disassembly

```asm
0x18000b7c0  mov     [rsp-28h+arg_0], rbx
0x18000b7c5  mov     [rsp-28h+InBuffer], edx
0x18000b7c9  push    rbp
0x18000b7ca  push    rsi
0x18000b7cb  push    rdi
0x18000b7cc  push    r14
0x18000b7ce  push    r15
0x18000b7d0  mov     rbp, rsp
0x18000b7d3  sub     rsp, 60h
0x18000b7d7  mov     rdi, [rbp+pcActualLenContainerName]
0x18000b7db  mov     esi, r9d
0x18000b7de  mov     [rbp+BytesReturned], 0
0x18000b7e5  mov     r14, r8
0x18000b7e8  mov     [rbp+Overlapped.Internal], 0
0x18000b7f0  mov     r15, rcx
0x18000b7f3  mov     [rbp+Overlapped.InternalHigh], 0
0x18000b7fb  mov     qword ptr [rbp+Overlapped.10h], 0
0x18000b803  mov     [rbp+Overlapped.hEvent], 0
0x18000b80b  test    rdi, rdi
0x18000b80e  jz      short loc_18000B816
0x18000b810  mov     dword ptr [rdi], 0
0x18000b816  test    r14, r14
0x18000b819  jnz     short loc_18000B836
0x18000b81b  test    esi, esi
0x18000b81d  jz      short loc_18000B836
0x18000b81f  lea     ecx, [r14+57h]; dwErrCode
0x18000b823  call    cs:__imp_SetLastError
0x18000b82a  nop     dword ptr [rax+rax+00h]
0x18000b82f  xor     eax, eax
0x18000b831  jmp     loc_18000B918
0x18000b836  xor     r9d, r9d; lpName
0x18000b839  xor     r8d, r8d; bInitialState
0x18000b83c  xor     ecx, ecx; lpEventAttributes
0x18000b83e  lea     edx, [r9+1]; bManualReset
0x18000b842  call    cs:__imp_CreateEventA
0x18000b849  nop     dword ptr [rax+rax+00h]
0x18000b84e  test    rax, rax
0x18000b851  jz      short loc_18000B82F
0x18000b853  or      rax, 1
0x18000b857  lea     rcx, [rbp+Overlapped]
0x18000b85b  mov     [rsp+60h+lpOverlapped], rcx; lpOverlapped
0x18000b860  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000b864  lea     rcx, [rbp+BytesReturned]
0x18000b868  mov     [rbp+Overlapped.hEvent], rax
0x18000b86c  mov     [rsp+60h+lpBytesReturned], rcx; lpBytesReturned
0x18000b871  lea     eax, [rsi+rsi]
0x18000b874  mov     [rsp+60h+nOutBufferSize], eax; nOutBufferSize
0x18000b878  xor     ebx, ebx
0x18000b87a  mov     rcx, r15; hDevice
0x18000b87d  mov     [rsp+60h+lpOutBuffer], r14; lpOutBuffer
0x18000b882  mov     edx, 8007684Ah; dwIoControlCode
0x18000b887  lea     r9d, [rbx+4]; nInBufferSize
0x18000b88b  call    cs:__imp_DeviceIoControl
0x18000b892  nop     dword ptr [rax+rax+00h]
0x18000b897  test    eax, eax
0x18000b899  jnz     short loc_18000B8DF
0x18000b89b  call    cs:__imp_GetLastError
0x18000b8a2  nop     dword ptr [rax+rax+00h]
0x18000b8a7  mov     ebx, eax
0x18000b8a9  cmp     eax, 3E5h
0x18000b8ae  jnz     short loc_18000B8DF
0x18000b8b0  mov     rcx, [rbp+Overlapped.hEvent]; hHandle
0x18000b8b4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b8b7  call    cs:__imp_WaitForSingleObject
0x18000b8be  nop     dword ptr [rax+rax+00h]
0x18000b8c3  test    eax, eax
0x18000b8c5  jz      short loc_18000B8CE
0x18000b8c7  mov     ebx, 45Dh
0x18000b8cc  jmp     short loc_18000B8DF
0x18000b8ce  mov     ecx, dword ptr [rbp+Overlapped.Internal]; Status
0x18000b8d1  call    cs:__imp_RtlNtStatusToDosError
0x18000b8d8  nop     dword ptr [rax+rax+00h]
0x18000b8dd  mov     ebx, eax
0x18000b8df  mov     rcx, [rbp+Overlapped.hEvent]
0x18000b8e3  and     rcx, 0FFFFFFFFFFFFFFFEh; hObject
0x18000b8e7  mov     [rbp+Overlapped.hEvent], rcx
0x18000b8eb  call    cs:__imp_CloseHandle
0x18000b8f2  nop     dword ptr [rax+rax+00h]
0x18000b8f7  mov     ecx, ebx; dwErrCode
0x18000b8f9  call    cs:__imp_SetLastError
0x18000b900  nop     dword ptr [rax+rax+00h]
0x18000b905  test    rdi, rdi
0x18000b908  jz      short loc_18000B911
0x18000b90a  mov     eax, [rbp+BytesReturned]
0x18000b90d  shr     eax, 1
0x18000b90f  mov     [rdi], eax
0x18000b911  xor     eax, eax
0x18000b913  test    ebx, ebx
0x18000b915  setz    al
0x18000b918  mov     rbx, [rsp+60h+arg_0]
0x18000b920  add     rsp, 60h
0x18000b924  pop     r15
0x18000b926  pop     r14
0x18000b928  pop     rdi
0x18000b929  pop     rsi
0x18000b92a  pop     rbp
0x18000b92b  retn
```
