# NlTransportGetIpAddress(ushort *,ulong *)

- ea: `0x180055680`
- end: `0x180055823`
- name: `?NlTransportGetIpAddress@@YAEPEAGPEAK@Z`
- size: `419`
- prototype: `char __fastcall(PCWSTR SourceString, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180055050`

## callees

- `0x180007278`
- `0x18000d100`
- `0x18000e270`
- `0x180055680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800557ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800557ac`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800557a2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800557a2`
- `ntdll!NtClose` at `0x1800557f9`
- `ntdll!NtClose` at `0x1800557f9`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800556ec`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800556ec`
- `ntdll!NtOpenFile` at `0x18005575c`
- `ntdll!NtOpenFile` at `0x18005575c`
- `WS2_32!__imp_htonl` at `0x1800557cc`
- `WS2_32!__imp_htonl` at `0x1800557cc`

## string_xrefs

- `0x1800557d8`: `NlTransportGetIpAddress: %ws Cannot NtOpenFile %lx\n`

## pseudocode

```c
char __fastcall NlTransportGetIpAddress(PCWSTR SourceString, unsigned int *a2)
{
  char v4; // bl
  NTSTATUS inited; // eax
  NTSTATUS Status; // eax
  DWORD LastError; // eax
  unsigned int v8; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  void *FileHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  u_long OutBuffer[68]; // [rsp+A0h] [rbp-60h] BYREF

  *a2 = 0;
  FileHandle = 0;
  BytesReturned = 0;
  v4 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( inited >= 0 )
  {
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Status = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 0, 0);
    if ( Status < 0 || (Status = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
    {
      NlPrintRoutine(
        0x100u,
        L"NlTransportGetIpAddress: %ws Cannot NtOpenFile %lx\n",
        SourceString,
        (unsigned int)Status);
    }
    else if ( DeviceIoControl(FileHandle, 0x2100A6u, 0, 0, OutBuffer, 0x104u, &BytesReturned, 0) )
    {
      *a2 = htonl(OutBuffer[0]);
      v4 = 1;
    }
    else
    {
      LastError = GetLastError();
      v8 = NetpApiStatusToNtStatus(LastError);
      if ( v8 != -1073741822 )
        NlPrintRoutine(0x100u, L"NlTransportGetIpAddress: %ws Cannot DeviceIoControl %lx\n", SourceString, v8);
    }
  }
  else
  {
    NlPrintRoutine(
      0x100u,
      L"NlTransportGetIpAddress: RtlInitUnicodeStringEx on TransportName failed: 0x%08x\n",
      (unsigned int)inited);
  }
  if ( FileHandle )
    NtClose(FileHandle);
  return v4;
}

```

## disassembly

```asm
0x180055680  mov     [rsp-8+arg_10], rbx
0x180055685  push    rbp
0x180055686  push    rsi
0x180055687  push    rdi
0x180055688  lea     rbp, [rsp-0C0h]
0x180055690  sub     rsp, 1C0h
0x180055697  mov     rax, cs:__security_cookie
0x18005569e  xor     rax, rsp
0x1800556a1  mov     [rbp+0D0h+var_20], rax
0x1800556a8  xorps   xmm1, xmm1
0x1800556ab  mov     dword ptr [rdx], 0
0x1800556b1  xorps   xmm0, xmm0
0x1800556b4  mov     [rsp+1D0h+FileHandle], 0
0x1800556bd  mov     rsi, rdx
0x1800556c0  mov     [rsp+1D0h+BytesReturned], 0
0x1800556c8  mov     rdx, rcx; SourceString
0x1800556cb  mov     rdi, rcx
0x1800556ce  lea     rcx, [rsp+1D0h+DestinationString]; DestinationString
0x1800556d3  xor     bl, bl
0x1800556d5  movups  xmmword ptr [rsp+1D0h+IoStatusBlock], xmm0
0x1800556da  movups  xmmword ptr [rsp+1D0h+ObjectAttributes.Length], xmm1
0x1800556df  movups  xmmword ptr [rbp+0D0h+ObjectAttributes.ObjectName], xmm1
0x1800556e3  movups  xmmword ptr [rbp+0D0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800556e7  movups  xmmword ptr [rsp+1D0h+DestinationString.Length], xmm0
0x1800556ec  call    cs:__imp_RtlInitUnicodeStringEx
0x1800556f2  test    eax, eax
0x1800556f4  jns     short loc_18005570F
0x1800556f6  mov     r8d, eax
0x1800556f9  lea     rdx, aNltransportget_0; "NlTransportGetIpAddress: RtlInitUnicode"...
0x180055700  mov     ecx, 100h; unsigned int
0x180055705  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005570a  jmp     loc_1800557EF
0x18005570f  lea     rax, [rsp+1D0h+DestinationString]
0x180055714  mov     [rsp+1D0h+OpenOptions], 0; OpenOptions
0x18005571c  xorps   xmm0, xmm0
0x18005571f  mov     [rbp+0D0h+ObjectAttributes.ObjectName], rax
0x180055723  lea     r9, [rsp+1D0h+IoStatusBlock]; IoStatusBlock
0x180055728  mov     [rsp+1D0h+ObjectAttributes.Length], 30h ; '0'
0x180055730  lea     r8, [rsp+1D0h+ObjectAttributes]; ObjectAttributes
0x180055735  mov     [rsp+1D0h+ObjectAttributes.RootDirectory], 0
0x18005573e  mov     edx, 100000h; DesiredAccess
0x180055743  mov     [rbp+0D0h+ObjectAttributes.Attributes], 40h ; '@'
0x18005574a  lea     rcx, [rsp+1D0h+FileHandle]; FileHandle
0x18005574f  mov     [rsp+1D0h+ShareAccess], 0; ShareAccess
0x180055757  movdqu  xmmword ptr [rbp+0D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005575c  call    cs:__imp_NtOpenFile
0x180055762  test    eax, eax
0x180055764  js      short loc_1800557D8
0x180055766  mov     eax, dword ptr [rsp+1D0h+IoStatusBlock]
0x18005576a  test    eax, eax
0x18005576c  js      short loc_1800557D8
0x18005576e  mov     rcx, [rsp+1D0h+FileHandle]; hDevice
0x180055773  lea     rax, [rsp+1D0h+BytesReturned]
0x180055778  mov     [rsp+1D0h+lpOverlapped], 0; lpOverlapped
0x180055781  xor     r9d, r9d; nInBufferSize
0x180055784  mov     [rsp+1D0h+lpBytesReturned], rax; lpBytesReturned
0x180055789  xor     r8d, r8d; lpInBuffer
0x18005578c  lea     rax, [rbp+0D0h+OutBuffer]
0x180055790  mov     [rsp+1D0h+OpenOptions], 104h; nOutBufferSize
0x180055798  mov     edx, 2100A6h; dwIoControlCode
0x18005579d  mov     qword ptr [rsp+1D0h+ShareAccess], rax; lpOutBuffer
0x1800557a2  call    cs:__imp_DeviceIoControl
0x1800557a8  test    eax, eax
0x1800557aa  jnz     short loc_1800557C9
0x1800557ac  call    cs:__imp_GetLastError
0x1800557b2  mov     ecx, eax
0x1800557b4  call    NetpApiStatusToNtStatus
0x1800557b9  cmp     eax, 0C0000002h
0x1800557be  jz      short loc_1800557EF
0x1800557c0  lea     rdx, aNltransportget_1; "NlTransportGetIpAddress: %ws Cannot Dev"...
0x1800557c7  jmp     short loc_1800557DF
0x1800557c9  mov     ecx, [rbp+0D0h+OutBuffer]; hostlong
0x1800557cc  call    cs:__imp_htonl
0x1800557d2  mov     [rsi], eax
0x1800557d4  mov     bl, 1
0x1800557d6  jmp     short loc_1800557EF
0x1800557d8  lea     rdx, aNltransportget; "NlTransportGetIpAddress: %ws Cannot NtO"...
0x1800557df  mov     r9d, eax
0x1800557e2  mov     r8, rdi
0x1800557e5  mov     ecx, 100h; unsigned int
0x1800557ea  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800557ef  mov     rcx, [rsp+1D0h+FileHandle]; Handle
0x1800557f4  test    rcx, rcx
0x1800557f7  jz      short loc_1800557FF
0x1800557f9  call    cs:__imp_NtClose
0x1800557ff  mov     al, bl
0x180055801  mov     rcx, [rbp+0D0h+var_20]
0x180055808  xor     rcx, rsp; StackCookie
0x18005580b  call    __security_check_cookie
0x180055810  mov     rbx, [rsp+1D0h+arg_10]
0x180055818  add     rsp, 1C0h
0x18005581f  pop     rdi
0x180055820  pop     rsi
0x180055821  pop     rbp
0x180055822  retn
```
