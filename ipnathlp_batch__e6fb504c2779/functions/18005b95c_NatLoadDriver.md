# NatLoadDriver

- ea: `0x18005b95c`
- end: `0x18005bac9`
- name: `NatLoadDriver`
- size: `365`
- prototype: `ULONG __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x18004b360`

## callees

- `0x18003477c`
- `0x18004f634`
- `0x18005b83c`
- `0x18005b95c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005ba15`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005ba15`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ba8e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ba8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005baa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005baa1`
- `ntdll!RtlInitUnicodeString` at `0x18005b9a4`
- `ntdll!RtlInitUnicodeString` at `0x18005b9a4`
- `ntdll!NtLoadDriver` at `0x18005b9b5`
- `ntdll!NtLoadDriver` at `0x18005b9b5`
- `ntdll!NtDeviceIoControlFile` at `0x18005ba73`
- `ntdll!NtDeviceIoControlFile` at `0x18005ba73`
- `ntdll!RtlNtStatusToDosError` at `0x18005b9e6`
- `ntdll!RtlNtStatusToDosError` at `0x18005b9e6`

## string_xrefs

- `0x18005b998`: `\Registry\Machine\System\CurrentControlSet\Services\IPNAT`

## pseudocode

```c
ULONG __fastcall NatLoadDriver(__int64 a1, _DWORD *a2)
{
  ULONG result; // eax
  NTSTATUS v4; // ebx
  NTSTATUS v5; // ecx
  HANDLE EventW; // rbx
  NTSTATUS Status; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-28h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-18h] BYREF
  __int64 OldValue; // [rsp+80h] [rbp+8h] BYREF

  OldValue = a1;
  LOBYTE(OldValue) = 0;
  IoStatusBlock = 0;
  DestinationString = 0;
  if ( !(unsigned __int8)NatEnableLoadDriverPrivilege((PBOOLEAN)&OldValue) )
    return 5;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\IPNAT");
  v4 = NtLoadDriver(&DestinationString);
  NatDisableLoadDriverPrivilege((PBOOLEAN)&OldValue);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -1073741554 )
  {
    v5 = v4;
    return RtlNtStatusToDosError(v5);
  }
  result = NatOpenDriver(&NatFileHandle);
  if ( !result )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( EventW )
    {
      Status = NtDeviceIoControlFile(NatFileHandle, EventW, 0, 0, &IoStatusBlock, 0x128000u, a2, a2[3] + 8, 0, 0);
      if ( Status == 259 )
      {
        WaitForSingleObject(EventW, 0xFFFFFFFF);
        Status = IoStatusBlock.Status;
      }
      CloseHandle(EventW);
      if ( Status < 0 )
      {
        v5 = Status;
        return RtlNtStatusToDosError(v5);
      }
      return 0;
    }
    else
    {
      return 8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005b95c  mov     rax, rsp
0x18005b95f  mov     [rax+10h], rbx
0x18005b963  mov     [rax+8], rcx
0x18005b967  push    rdi
0x18005b968  sub     rsp, 70h
0x18005b96c  xorps   xmm0, xmm0
0x18005b96f  mov     byte ptr [rax+8], 0
0x18005b973  xorps   xmm1, xmm1
0x18005b976  lea     rcx, [rax+8]; OldValue
0x18005b97a  movups  xmmword ptr [rax-18h], xmm0
0x18005b97e  mov     rdi, rdx
0x18005b981  movups  xmmword ptr [rax-28h], xmm1
0x18005b985  call    NatEnableLoadDriverPrivilege
0x18005b98a  test    al, al
0x18005b98c  jnz     short loc_18005B998
0x18005b98e  mov     eax, 5
0x18005b993  jmp     loc_18005BABA
0x18005b998  lea     rdx, NatServicePath; "\\Registry\\Machine\\System\\CurrentCon"...
0x18005b99f  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x18005b9a4  call    cs:__imp_RtlInitUnicodeString
0x18005b9ab  nop     dword ptr [rax+rax+00h]
0x18005b9b0  lea     rcx, [rsp+78h+DestinationString]; DriverServiceName
0x18005b9b5  call    cs:__imp_NtLoadDriver
0x18005b9bc  nop     dword ptr [rax+rax+00h]
0x18005b9c1  lea     rcx, [rsp+78h+OldValue]; OldValue
0x18005b9c9  mov     ebx, eax
0x18005b9cb  call    NatDisableLoadDriverPrivilege
0x18005b9d0  mov     eax, 80000000h
0x18005b9d5  lea     ecx, [rbx+rax]
0x18005b9d8  test    eax, ecx
0x18005b9da  jnz     short loc_18005B9F7
0x18005b9dc  cmp     ebx, 0C000010Eh
0x18005b9e2  jz      short loc_18005B9F7
0x18005b9e4  mov     ecx, ebx; Status
0x18005b9e6  call    cs:__imp_RtlNtStatusToDosError
0x18005b9ed  nop     dword ptr [rax+rax+00h]
0x18005b9f2  jmp     loc_18005BABA
0x18005b9f7  lea     rcx, NatFileHandle; FileHandle
0x18005b9fe  call    NatOpenDriver
0x18005ba03  test    eax, eax
0x18005ba05  jnz     loc_18005BABA
0x18005ba0b  xor     r9d, r9d; lpName
0x18005ba0e  xor     r8d, r8d; bInitialState
0x18005ba11  xor     edx, edx; bManualReset
0x18005ba13  xor     ecx, ecx; lpEventAttributes
0x18005ba15  call    cs:__imp_CreateEventW
0x18005ba1c  nop     dword ptr [rax+rax+00h]
0x18005ba21  mov     rbx, rax
0x18005ba24  test    rax, rax
0x18005ba27  jnz     short loc_18005BA31
0x18005ba29  lea     eax, [rbx+8]
0x18005ba2c  jmp     loc_18005BABA
0x18005ba31  mov     eax, [rdi+0Ch]
0x18005ba34  xor     r9d, r9d; ApcContext
0x18005ba37  mov     rcx, cs:NatFileHandle; FileHandle
0x18005ba3e  add     eax, 8
0x18005ba41  mov     [rsp+78h+OutputBufferLength], 0; OutputBufferLength
0x18005ba49  xor     r8d, r8d; ApcRoutine
0x18005ba4c  mov     [rsp+78h+OutputBuffer], 0; OutputBuffer
0x18005ba55  mov     rdx, rbx; Event
0x18005ba58  mov     [rsp+78h+InputBufferLength], eax; InputBufferLength
0x18005ba5c  lea     rax, [rsp+78h+var_18]
0x18005ba61  mov     [rsp+78h+InputBuffer], rdi; InputBuffer
0x18005ba66  mov     [rsp+78h+IoControlCode], 128000h; IoControlCode
0x18005ba6e  mov     [rsp+78h+IoStatusBlock], rax; IoStatusBlock
0x18005ba73  call    cs:__imp_NtDeviceIoControlFile
0x18005ba7a  nop     dword ptr [rax+rax+00h]
0x18005ba7f  mov     edi, eax
0x18005ba81  cmp     eax, 103h
0x18005ba86  jnz     short loc_18005BA9E
0x18005ba88  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005ba8b  mov     rcx, rbx; hHandle
0x18005ba8e  call    cs:__imp_WaitForSingleObject
0x18005ba95  nop     dword ptr [rax+rax+00h]
0x18005ba9a  mov     edi, dword ptr [rsp+78h+var_18]
0x18005ba9e  mov     rcx, rbx; hObject
0x18005baa1  call    cs:__imp_CloseHandle
0x18005baa8  nop     dword ptr [rax+rax+00h]
0x18005baad  test    edi, edi
0x18005baaf  jns     short loc_18005BAB8
0x18005bab1  mov     ecx, edi
0x18005bab3  jmp     loc_18005B9E6
0x18005bab8  xor     eax, eax
0x18005baba  mov     rbx, [rsp+78h+arg_8]
0x18005bac2  add     rsp, 70h
0x18005bac6  pop     rdi
0x18005bac7  retn
```
