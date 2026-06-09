# NsiEnumerateObjectsAllParametersEx

- ea: `0x1800015d0`
- end: `0x1800016a3`
- name: `NsiEnumerateObjectsAllParametersEx`
- size: `211`
- prototype: `DWORD __fastcall(PVOID OutputBuffer)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800015d0`
- `0x180001cb0`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180001647`
- `ntdll!NtDeviceIoControlFile` at `0x180001647`
- `ntdll!NtWaitForSingleObject` at `0x180001692`
- `ntdll!NtWaitForSingleObject` at `0x180001692`
- `ntdll!RtlNtStatusToDosError` at `0x18000167a`
- `ntdll!RtlNtStatusToDosError` at `0x18000167a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001682`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001659`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001659`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800015fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800015fd`

## pseudocode

```c
DWORD __fastcall NsiEnumerateObjectsAllParametersEx(PVOID OutputBuffer)
{
  DWORD result; // eax
  HANDLE EventA; // rbx
  int Status; // edi
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

  IoStatusBlock = 0;
  result = NsiOpenDevice();
  if ( !result )
  {
    EventA = CreateEventA(0, 0, 0, 0);
    if ( EventA )
    {
      Status = NtDeviceIoControlFile(
                 g_NsiAsyncDeviceHandle,
                 EventA,
                 0,
                 0,
                 &IoStatusBlock,
                 0x12001Bu,
                 OutputBuffer,
                 0x70u,
                 OutputBuffer,
                 0x70u);
      if ( Status == 259 )
      {
        Status = NtWaitForSingleObject(EventA, 0, 0);
        if ( Status >= 0 )
          Status = IoStatusBlock.Status;
      }
      CloseHandle(EventA);
      if ( Status < 0 || Status == 261 )
        return RtlNtStatusToDosError(Status);
      else
        return 0;
    }
    else
    {
      return GetLastError();
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800015d0  push    rdi
0x1800015d2  sub     rsp, 60h
0x1800015d6  xorps   xmm0, xmm0
0x1800015d9  mov     rdi, rcx
0x1800015dc  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x1800015e1  call    NsiOpenDevice
0x1800015e6  test    eax, eax
0x1800015e8  jnz     loc_180001672
0x1800015ee  xor     r9d, r9d; lpName
0x1800015f1  mov     [rsp+68h+arg_0], rbx
0x1800015f6  xor     r8d, r8d; bInitialState
0x1800015f9  xor     edx, edx; bManualReset
0x1800015fb  xor     ecx, ecx; lpEventAttributes
0x1800015fd  call    cs:__imp_CreateEventA
0x180001603  mov     rbx, rax
0x180001606  test    rax, rax
0x180001609  jz      short loc_180001682
0x18000160b  mov     rcx, cs:g_NsiAsyncDeviceHandle; FileHandle
0x180001612  lea     rax, [rsp+68h+var_18]
0x180001617  mov     [rsp+68h+OutputBufferLength], 70h ; 'p'; OutputBufferLength
0x18000161f  xor     r9d, r9d; ApcContext
0x180001622  mov     [rsp+68h+OutputBuffer], rdi; OutputBuffer
0x180001627  xor     r8d, r8d; ApcRoutine
0x18000162a  mov     [rsp+68h+InputBufferLength], 70h ; 'p'; InputBufferLength
0x180001632  mov     rdx, rbx; Event
0x180001635  mov     [rsp+68h+InputBuffer], rdi; InputBuffer
0x18000163a  mov     [rsp+68h+IoControlCode], 12001Bh; IoControlCode
0x180001642  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x180001647  call    cs:__imp_NtDeviceIoControlFile
0x18000164d  mov     edi, eax
0x18000164f  cmp     eax, 103h
0x180001654  jz      short loc_18000168A
0x180001656  mov     rcx, rbx; hObject
0x180001659  call    cs:__imp_CloseHandle
0x18000165f  test    edi, edi
0x180001661  js      short loc_180001678
0x180001663  cmp     edi, 105h
0x180001669  jz      short loc_180001678
0x18000166b  xor     eax, eax
0x18000166d  mov     rbx, [rsp+68h+arg_0]
0x180001672  add     rsp, 60h
0x180001676  pop     rdi
0x180001677  retn
0x180001678  mov     ecx, edi; Status
0x18000167a  call    cs:__imp_RtlNtStatusToDosError
0x180001680  jmp     short loc_18000166D
0x180001682  call    cs:__imp_GetLastError
0x180001688  jmp     short loc_18000166D
0x18000168a  xor     r8d, r8d; Timeout
0x18000168d  xor     edx, edx; Alertable
0x18000168f  mov     rcx, rbx; Handle
0x180001692  call    cs:__imp_NtWaitForSingleObject
0x180001698  test    eax, eax
0x18000169a  mov     edi, eax
0x18000169c  cmovns  edi, dword ptr [rsp+68h+var_18]
0x1800016a1  jmp     short loc_180001656
```
