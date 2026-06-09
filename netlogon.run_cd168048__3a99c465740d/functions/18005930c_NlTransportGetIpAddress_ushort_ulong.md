# NlTransportGetIpAddress(ushort *,ulong *)

- ea: `0x18005930c`
- end: `0x1800594d8`
- name: `?NlTransportGetIpAddress@@YAEPEAGPEAK@Z`
- size: `460`
- prototype: `unsigned __int8 __fastcall(PCWSTR SourceString, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180058c40`

## callees

- `0x180007518`
- `0x18000d7a0`
- `0x18000e910`
- `0x18005930c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005944e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005944e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005943e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005943e`
- `ntdll!NtClose` at `0x1800594a7`
- `ntdll!NtClose` at `0x1800594a7`
- `ntdll!RtlInitUnicodeStringEx` at `0x180059378`
- `ntdll!RtlInitUnicodeStringEx` at `0x180059378`
- `ntdll!NtOpenFile` at `0x1800593ee`
- `ntdll!NtOpenFile` at `0x1800593ee`
- `WS2_32!__imp_htonl` at `0x180059474`
- `WS2_32!__imp_htonl` at `0x180059474`

## string_xrefs

- `0x180059486`: `NlTransportGetIpAddress: %ws Cannot NtOpenFile %lx\n`

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
0x18005930c  mov     [rsp-8+arg_10], rbx
0x180059311  push    rbp
0x180059312  push    rsi
0x180059313  push    rdi
0x180059314  lea     rbp, [rsp-0C0h]
0x18005931c  sub     rsp, 1C0h
0x180059323  mov     rax, cs:__security_cookie
0x18005932a  xor     rax, rsp
0x18005932d  mov     [rbp+0D0h+var_20], rax
0x180059334  xorps   xmm1, xmm1
0x180059337  mov     dword ptr [rdx], 0
0x18005933d  xorps   xmm0, xmm0
0x180059340  mov     [rsp+1D0h+FileHandle], 0
0x180059349  mov     rsi, rdx
0x18005934c  mov     [rsp+1D0h+BytesReturned], 0
0x180059354  mov     rdx, rcx; SourceString
0x180059357  mov     rdi, rcx
0x18005935a  lea     rcx, [rsp+1D0h+DestinationString]; DestinationString
0x18005935f  xor     bl, bl
0x180059361  movups  xmmword ptr [rsp+1D0h+IoStatusBlock], xmm0
0x180059366  movups  xmmword ptr [rsp+1D0h+ObjectAttributes.Length], xmm1
0x18005936b  movups  xmmword ptr [rbp+0D0h+ObjectAttributes.ObjectName], xmm1
0x18005936f  movups  xmmword ptr [rbp+0D0h+ObjectAttributes.SecurityDescriptor], xmm1
0x180059373  movups  xmmword ptr [rsp+1D0h+DestinationString.Length], xmm0
0x180059378  call    cs:__imp_RtlInitUnicodeStringEx
0x18005937f  nop     dword ptr [rax+rax+00h]
0x180059384  test    eax, eax
0x180059386  jns     short loc_1800593A1
0x180059388  mov     r8d, eax
0x18005938b  lea     rdx, aNltransportget_0; "NlTransportGetIpAddress: RtlInitUnicode"...
0x180059392  mov     ecx, 100h; unsigned int
0x180059397  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005939c  jmp     loc_18005949D
0x1800593a1  lea     rax, [rsp+1D0h+DestinationString]
0x1800593a6  mov     [rsp+1D0h+OpenOptions], 0; OpenOptions
0x1800593ae  xorps   xmm0, xmm0
0x1800593b1  mov     [rbp+0D0h+ObjectAttributes.ObjectName], rax
0x1800593b5  lea     r9, [rsp+1D0h+IoStatusBlock]; IoStatusBlock
0x1800593ba  mov     [rsp+1D0h+ObjectAttributes.Length], 30h ; '0'
0x1800593c2  lea     r8, [rsp+1D0h+ObjectAttributes]; ObjectAttributes
0x1800593c7  mov     [rsp+1D0h+ObjectAttributes.RootDirectory], 0
0x1800593d0  mov     edx, 100000h; DesiredAccess
0x1800593d5  mov     [rbp+0D0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800593dc  lea     rcx, [rsp+1D0h+FileHandle]; FileHandle
0x1800593e1  mov     [rsp+1D0h+ShareAccess], 0; ShareAccess
0x1800593e9  movdqu  xmmword ptr [rbp+0D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800593ee  call    cs:__imp_NtOpenFile
0x1800593f5  nop     dword ptr [rax+rax+00h]
0x1800593fa  test    eax, eax
0x1800593fc  js      loc_180059486
0x180059402  mov     eax, dword ptr [rsp+1D0h+IoStatusBlock]
0x180059406  test    eax, eax
0x180059408  js      short loc_180059486
0x18005940a  mov     rcx, [rsp+1D0h+FileHandle]; hDevice
0x18005940f  lea     rax, [rsp+1D0h+BytesReturned]
0x180059414  mov     [rsp+1D0h+lpOverlapped], 0; lpOverlapped
0x18005941d  xor     r9d, r9d; nInBufferSize
0x180059420  mov     [rsp+1D0h+lpBytesReturned], rax; lpBytesReturned
0x180059425  xor     r8d, r8d; lpInBuffer
0x180059428  lea     rax, [rbp+0D0h+OutBuffer]
0x18005942c  mov     [rsp+1D0h+OpenOptions], 104h; nOutBufferSize
0x180059434  mov     edx, 2100A6h; dwIoControlCode
0x180059439  mov     qword ptr [rsp+1D0h+ShareAccess], rax; lpOutBuffer
0x18005943e  call    cs:__imp_DeviceIoControl
0x180059445  nop     dword ptr [rax+rax+00h]
0x18005944a  test    eax, eax
0x18005944c  jnz     short loc_180059471
0x18005944e  call    cs:__imp_GetLastError
0x180059455  nop     dword ptr [rax+rax+00h]
0x18005945a  mov     ecx, eax
0x18005945c  call    NetpApiStatusToNtStatus
0x180059461  cmp     eax, 0C0000002h
0x180059466  jz      short loc_18005949D
0x180059468  lea     rdx, aNltransportget_1; "NlTransportGetIpAddress: %ws Cannot Dev"...
0x18005946f  jmp     short loc_18005948D
0x180059471  mov     ecx, [rbp+0D0h+OutBuffer]; hostlong
0x180059474  call    cs:__imp_htonl
0x18005947b  nop     dword ptr [rax+rax+00h]
0x180059480  mov     [rsi], eax
0x180059482  mov     bl, 1
0x180059484  jmp     short loc_18005949D
0x180059486  lea     rdx, aNltransportget; "NlTransportGetIpAddress: %ws Cannot NtO"...
0x18005948d  mov     r9d, eax
0x180059490  mov     r8, rdi
0x180059493  mov     ecx, 100h; unsigned int
0x180059498  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005949d  mov     rcx, [rsp+1D0h+FileHandle]; Handle
0x1800594a2  test    rcx, rcx
0x1800594a5  jz      short loc_1800594B3
0x1800594a7  call    cs:__imp_NtClose
0x1800594ae  nop     dword ptr [rax+rax+00h]
0x1800594b3  mov     al, bl
0x1800594b5  mov     rcx, [rbp+0D0h+var_20]
0x1800594bc  xor     rcx, rsp; StackCookie
0x1800594bf  call    __security_check_cookie
0x1800594c4  mov     rbx, [rsp+1D0h+arg_10]
0x1800594cc  add     rsp, 1C0h
0x1800594d3  pop     rdi
0x1800594d4  pop     rsi
0x1800594d5  pop     rbp
0x1800594d6  retn
```
