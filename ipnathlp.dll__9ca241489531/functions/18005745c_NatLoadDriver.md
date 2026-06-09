# NatLoadDriver

- ea: `0x18005745c`
- end: `0x18005759b`
- name: `NatLoadDriver`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x180047810`

## callees

- `0x180032024`
- `0x18004b9e8`
- `0x180057374`
- `0x18005745c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180057503`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180057503`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005756d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005756d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005757a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005757a`
- `ntdll!RtlInitUnicodeString` at `0x1800574a4`
- `ntdll!RtlInitUnicodeString` at `0x1800574a4`
- `ntdll!NtLoadDriver` at `0x1800574af`
- `ntdll!NtLoadDriver` at `0x1800574af`
- `ntdll!NtDeviceIoControlFile` at `0x180057558`
- `ntdll!NtDeviceIoControlFile` at `0x180057558`
- `ntdll!RtlNtStatusToDosError` at `0x1800574da`
- `ntdll!RtlNtStatusToDosError` at `0x1800574da`

## string_xrefs

- `0x180057498`: `\Registry\Machine\System\CurrentControlSet\Services\IPNAT`

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
  if ( !NatEnableLoadDriverPrivilege((PBOOLEAN)&OldValue) )
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
0x18005745c  mov     rax, rsp
0x18005745f  mov     [rax+10h], rbx
0x180057463  mov     [rax+8], rcx
0x180057467  push    rdi
0x180057468  sub     rsp, 70h
0x18005746c  xorps   xmm0, xmm0
0x18005746f  mov     byte ptr [rax+8], 0
0x180057473  xorps   xmm1, xmm1
0x180057476  lea     rcx, [rax+8]; OldValue
0x18005747a  movups  xmmword ptr [rax-18h], xmm0
0x18005747e  mov     rdi, rdx
0x180057481  movups  xmmword ptr [rax-28h], xmm1
0x180057485  call    NatEnableLoadDriverPrivilege
0x18005748a  test    al, al
0x18005748c  jnz     short loc_180057498
0x18005748e  mov     eax, 5
0x180057493  jmp     loc_18005758D
0x180057498  lea     rdx, NatServicePath; "\\Registry\\Machine\\System\\CurrentCon"...
0x18005749f  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1800574a4  call    cs:__imp_RtlInitUnicodeString
0x1800574aa  lea     rcx, [rsp+78h+DestinationString]; DriverServiceName
0x1800574af  call    cs:__imp_NtLoadDriver
0x1800574b5  lea     rcx, [rsp+78h+OldValue]; OldValue
0x1800574bd  mov     ebx, eax
0x1800574bf  call    NatDisableLoadDriverPrivilege
0x1800574c4  mov     eax, 80000000h
0x1800574c9  lea     ecx, [rbx+rax]
0x1800574cc  test    eax, ecx
0x1800574ce  jnz     short loc_1800574E5
0x1800574d0  cmp     ebx, 0C000010Eh
0x1800574d6  jz      short loc_1800574E5
0x1800574d8  mov     ecx, ebx; Status
0x1800574da  call    cs:__imp_RtlNtStatusToDosError
0x1800574e0  jmp     loc_18005758D
0x1800574e5  lea     rcx, NatFileHandle; FileHandle
0x1800574ec  call    NatOpenDriver
0x1800574f1  test    eax, eax
0x1800574f3  jnz     loc_18005758D
0x1800574f9  xor     r9d, r9d; lpName
0x1800574fc  xor     r8d, r8d; bInitialState
0x1800574ff  xor     edx, edx; bManualReset
0x180057501  xor     ecx, ecx; lpEventAttributes
0x180057503  call    cs:__imp_CreateEventW
0x180057509  mov     rbx, rax
0x18005750c  test    rax, rax
0x18005750f  jnz     short loc_180057516
0x180057511  lea     eax, [rbx+8]
0x180057514  jmp     short loc_18005758D
0x180057516  mov     eax, [rdi+0Ch]
0x180057519  xor     r9d, r9d; ApcContext
0x18005751c  mov     rcx, cs:NatFileHandle; FileHandle
0x180057523  add     eax, 8
0x180057526  mov     [rsp+78h+OutputBufferLength], 0; OutputBufferLength
0x18005752e  xor     r8d, r8d; ApcRoutine
0x180057531  mov     [rsp+78h+OutputBuffer], 0; OutputBuffer
0x18005753a  mov     rdx, rbx; Event
0x18005753d  mov     [rsp+78h+InputBufferLength], eax; InputBufferLength
0x180057541  lea     rax, [rsp+78h+var_18]
0x180057546  mov     [rsp+78h+InputBuffer], rdi; InputBuffer
0x18005754b  mov     [rsp+78h+IoControlCode], 128000h; IoControlCode
0x180057553  mov     [rsp+78h+IoStatusBlock], rax; IoStatusBlock
0x180057558  call    cs:__imp_NtDeviceIoControlFile
0x18005755e  mov     edi, eax
0x180057560  cmp     eax, 103h
0x180057565  jnz     short loc_180057577
0x180057567  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005756a  mov     rcx, rbx; hHandle
0x18005756d  call    cs:__imp_WaitForSingleObject
0x180057573  mov     edi, dword ptr [rsp+78h+var_18]
0x180057577  mov     rcx, rbx; hObject
0x18005757a  call    cs:__imp_CloseHandle
0x180057580  test    edi, edi
0x180057582  jns     short loc_18005758B
0x180057584  mov     ecx, edi
0x180057586  jmp     loc_1800574DA
0x18005758b  xor     eax, eax
0x18005758d  mov     rbx, [rsp+78h+arg_8]
0x180057595  add     rsp, 70h
0x180057599  pop     rdi
0x18005759a  retn
```
