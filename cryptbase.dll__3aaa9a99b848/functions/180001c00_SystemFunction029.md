# SystemFunction029

- ea: `0x180001c00`
- end: `0x180001f43`
- name: `SystemFunction029`
- size: `835`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001c00`
- `0x180003b50`

## import_xrefs

- `ntdll!NtClose` at `0x180001d62`
- `ntdll!NtClose` at `0x180001da1`
- `ntdll!NtClose` at `0x180001ea2`
- `ntdll!NtClose` at `0x180001d62`
- `ntdll!NtClose` at `0x180001da1`
- `ntdll!NtClose` at `0x180001ea2`
- `ntdll!NtOpenFile` at `0x180001e20`
- `ntdll!NtOpenFile` at `0x180001e20`
- `ntdll!RtlInitUnicodeString` at `0x180001dcb`
- `ntdll!RtlInitUnicodeString` at `0x180001dcb`
- `ntdll!NtQueryInformationToken` at `0x180001d8f`
- `ntdll!NtQueryInformationToken` at `0x180001d8f`
- `ntdll!NtFsControlFile` at `0x180001e71`
- `ntdll!NtFsControlFile` at `0x180001e71`
- `ntdll!NtOpenThreadToken` at `0x180001cb7`
- `ntdll!NtOpenThreadToken` at `0x180001d0d`
- `ntdll!NtOpenThreadToken` at `0x180001cb7`
- `ntdll!NtOpenThreadToken` at `0x180001d0d`
- `ntdll!NtWaitForSingleObject` at `0x180001e8f`
- `ntdll!NtWaitForSingleObject` at `0x180001e8f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180001ee8`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180001ee8`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001ce6`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001d2d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001d4c`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001ce6`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001d2d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001d4c`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180001c6e`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180001c6e`
- `RPCRT4!RpcImpersonateClient` at `0x180001cd8`
- `RPCRT4!RpcImpersonateClient` at `0x180001cd8`
- `RPCRT4!RpcRevertToSelf` at `0x180001d1f`
- `RPCRT4!RpcRevertToSelf` at `0x180001d3e`
- `RPCRT4!RpcRevertToSelf` at `0x180001d1f`
- `RPCRT4!RpcRevertToSelf` at `0x180001d3e`

## pseudocode

```c
RPC_STATUS __fastcall SystemFunction029(__int64 a1, _OWORD *a2)
{
  RPC_STATUS result; // eax
  RPC_STATUS v4; // eax
  NTSTATUS Status; // edi
  RPC_STATUS v6; // eax
  RPC_STATUS v7; // eax
  const WCHAR *v8; // rdx
  char i; // si
  NTSTATUS v10; // eax
  unsigned int ClientLocalFlag; // [rsp+50h] [rbp-69h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-61h] BYREF
  void *FileHandle; // [rsp+60h] [rbp-59h] BYREF
  ULONG ReturnLength; // [rsp+68h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-29h] BYREF
  _OWORD TokenInformation[3]; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v19; // [rsp+F0h] [rbp+37h]

  TokenHandle = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v19 = 0;
  ReturnLength = 0;
  FileHandle = 0;
  DestinationString = 0;
  ClientLocalFlag = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  *a2 = ErrorSessionKey;
  result = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  if ( result < 0 )
    return result;
  if ( ClientLocalFlag )
  {
    result = 1073741830;
    *a2 = LocalSessionKey;
    return result;
  }
  result = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( result < 0 )
  {
    if ( result != -1073741700 )
      return result;
    v4 = RpcImpersonateClient(0);
    result = I_RpcMapWin32Status(v4);
    if ( result < 0 )
      return result;
    Status = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
    if ( Status < 0 )
    {
      v6 = RpcRevertToSelf();
      I_RpcMapWin32Status(v6);
      return Status;
    }
    v7 = RpcRevertToSelf();
    Status = I_RpcMapWin32Status(v7);
    if ( Status < 0 )
    {
      NtClose(TokenHandle);
      return Status;
    }
  }
  Status = NtQueryInformationToken(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
  NtClose(TokenHandle);
  if ( Status < 0 )
    return Status;
  v8 = L"\\Device\\Srv2";
  for ( i = 0; ; i = 1 )
  {
    RtlInitUnicodeString(&DestinationString, v8);
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v10 = NtOpenFile(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 1u, 0);
    Status = v10;
    if ( v10 < 0 )
    {
      if ( v10 != -1073741772 )
        return Status;
      goto LABEL_26;
    }
    Status = NtFsControlFile(
               FileHandle,
               0,
               0,
               0,
               &IoStatusBlock,
               0x144038u,
               (char *)TokenInformation + 8,
               8u,
               a2,
               0x10u);
    if ( Status == 259 )
    {
      NtWaitForSingleObject(FileHandle, 0, 0);
      Status = IoStatusBlock.Status;
    }
    NtClose(FileHandle);
    if ( Status >= 0 )
      break;
    if ( Status != -1073741700 )
    {
      if ( Status != -1063780347 )
        return Status;
LABEL_26:
      Status = 1073741830;
      *a2 = LocalSessionKey;
      return Status;
    }
    if ( i )
      goto LABEL_26;
    v8 = L"\\Device\\LanmanServer";
  }
  if ( RtlCompareMemory(a2, &ErrorSessionKey, 0x10u) == 16 )
    return -1073741310;
  return Status;
}

```

## disassembly

```asm
0x180001c00  push    rbp
0x180001c02  push    rbx
0x180001c03  push    r14
0x180001c05  lea     rbp, [rsp-47h]
0x180001c0a  sub     rsp, 100h
0x180001c11  mov     rax, cs:__security_cookie
0x180001c18  xor     rax, rsp
0x180001c1b  mov     [rbp+57h+var_18], rax
0x180001c1f  xorps   xmm0, xmm0
0x180001c22  xor     r14d, r14d
0x180001c25  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180001c29  mov     rbx, rdx
0x180001c2c  xor     eax, eax
0x180001c2e  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180001c32  xor     ecx, ecx; BindingHandle
0x180001c34  mov     [rbp+57h+TokenHandle], r14
0x180001c38  movups  [rbp+57h+TokenInformation], xmm0
0x180001c3c  mov     [rbp+57h+var_20], rax
0x180001c40  movups  [rbp+57h+var_40], xmm0
0x180001c44  mov     [rbp+57h+var_A8], r14d
0x180001c48  movups  [rbp+57h+var_30], xmm0
0x180001c4c  mov     [rbp+57h+FileHandle], r14
0x180001c50  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180001c54  mov     [rbp+57h+ClientLocalFlag], r14d
0x180001c58  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180001c5c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180001c60  movups  xmm0, cs:ErrorSessionKey
0x180001c67  movups  xmmword ptr [rdx], xmm0
0x180001c6a  lea     rdx, [rbp+57h+ClientLocalFlag]; ClientLocalFlag
0x180001c6e  call    cs:__imp_I_RpcBindingIsClientLocal
0x180001c75  nop     dword ptr [rax+rax+00h]
0x180001c7a  test    eax, eax
0x180001c7c  js      loc_180001F2A
0x180001c82  mov     [rsp+110h+arg_10], rdi
0x180001c8a  cmp     [rbp+57h+ClientLocalFlag], r14d
0x180001c8e  jz      short loc_180001CA4
0x180001c90  movups  xmm0, cs:LocalSessionKey
0x180001c97  mov     eax, 40000006h
0x180001c9c  movups  xmmword ptr [rbx], xmm0
0x180001c9f  jmp     loc_180001F22
0x180001ca4  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180001ca8  mov     r8b, 1; OpenAsSelf
0x180001cab  mov     edx, 8; DesiredAccess
0x180001cb0  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180001cb7  call    cs:__imp_NtOpenThreadToken
0x180001cbe  nop     dword ptr [rax+rax+00h]
0x180001cc3  test    eax, eax
0x180001cc5  jns     loc_180001D73
0x180001ccb  cmp     eax, 0C000007Ch
0x180001cd0  jnz     loc_180001F22
0x180001cd6  xor     ecx, ecx; BindingHandle
0x180001cd8  call    cs:__imp_RpcImpersonateClient
0x180001cdf  nop     dword ptr [rax+rax+00h]
0x180001ce4  mov     ecx, eax; Status
0x180001ce6  call    cs:__imp_I_RpcMapWin32Status
0x180001ced  nop     dword ptr [rax+rax+00h]
0x180001cf2  test    eax, eax
0x180001cf4  js      loc_180001F22
0x180001cfa  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180001cfe  mov     r8b, 1; OpenAsSelf
0x180001d01  mov     edx, 8; DesiredAccess
0x180001d06  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180001d0d  call    cs:__imp_NtOpenThreadToken
0x180001d14  nop     dword ptr [rax+rax+00h]
0x180001d19  mov     edi, eax
0x180001d1b  test    eax, eax
0x180001d1d  jns     short loc_180001D3E
0x180001d1f  call    cs:__imp_RpcRevertToSelf
0x180001d26  nop     dword ptr [rax+rax+00h]
0x180001d2b  mov     ecx, eax; Status
0x180001d2d  call    cs:__imp_I_RpcMapWin32Status
0x180001d34  nop     dword ptr [rax+rax+00h]
0x180001d39  jmp     loc_180001F20
0x180001d3e  call    cs:__imp_RpcRevertToSelf
0x180001d45  nop     dword ptr [rax+rax+00h]
0x180001d4a  mov     ecx, eax; Status
0x180001d4c  call    cs:__imp_I_RpcMapWin32Status
0x180001d53  nop     dword ptr [rax+rax+00h]
0x180001d58  mov     edi, eax
0x180001d5a  test    eax, eax
0x180001d5c  jns     short loc_180001D73
0x180001d5e  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180001d62  call    cs:__imp_NtClose
0x180001d69  nop     dword ptr [rax+rax+00h]
0x180001d6e  jmp     loc_180001F20
0x180001d73  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180001d77  lea     rax, [rbp+57h+var_A8]
0x180001d7b  mov     r9d, 38h ; '8'; TokenInformationLength
0x180001d81  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x180001d86  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180001d8a  mov     edx, 0Ah; TokenInformationClass
0x180001d8f  call    cs:__imp_NtQueryInformationToken
0x180001d96  nop     dword ptr [rax+rax+00h]
0x180001d9b  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180001d9f  mov     edi, eax
0x180001da1  call    cs:__imp_NtClose
0x180001da8  nop     dword ptr [rax+rax+00h]
0x180001dad  test    edi, edi
0x180001daf  js      loc_180001F20
0x180001db5  mov     [rsp+110h+arg_0], rsi
0x180001dbd  lea     rdx, aDeviceSrv2; "\\Device\\Srv2"
0x180001dc4  xor     sil, sil
0x180001dc7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180001dcb  call    cs:__imp_RtlInitUnicodeString
0x180001dd2  nop     dword ptr [rax+rax+00h]
0x180001dd7  nop     word ptr [rax+rax+00000000h]
0x180001de0  lea     rax, [rbp+57h+DestinationString]
0x180001de4  mov     [rsp+110h+OpenOptions], r14d; OpenOptions
0x180001de9  xorps   xmm0, xmm0
0x180001dec  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180001df0  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180001df4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180001dfb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180001dff  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180001e03  mov     edx, 0C0000000h; DesiredAccess
0x180001e08  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180001e0f  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180001e13  mov     dword ptr [rsp+110h+ReturnLength], 1; ShareAccess
0x180001e1b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180001e20  call    cs:__imp_NtOpenFile
0x180001e27  nop     dword ptr [rax+rax+00h]
0x180001e2c  mov     edi, eax
0x180001e2e  test    eax, eax
0x180001e30  js      loc_180001F02
0x180001e36  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180001e3a  lea     rax, [rbp+57h+TokenInformation+8]
0x180001e3e  mov     [rsp+110h+OutputBufferLength], 10h; OutputBufferLength
0x180001e46  xor     r9d, r9d; ApcContext
0x180001e49  mov     [rsp+110h+OutputBuffer], rbx; OutputBuffer
0x180001e4e  xor     r8d, r8d; ApcRoutine
0x180001e51  mov     [rsp+110h+InputBufferLength], 8; InputBufferLength
0x180001e59  xor     edx, edx; Event
0x180001e5b  mov     [rsp+110h+InputBuffer], rax; InputBuffer
0x180001e60  lea     rax, [rbp+57h+IoStatusBlock]
0x180001e64  mov     [rsp+110h+OpenOptions], 144038h; FsControlCode
0x180001e6c  mov     [rsp+110h+ReturnLength], rax; IoStatusBlock
0x180001e71  call    cs:__imp_NtFsControlFile
0x180001e78  nop     dword ptr [rax+rax+00h]
0x180001e7d  mov     edi, eax
0x180001e7f  cmp     eax, 103h
0x180001e84  jnz     short loc_180001E9E
0x180001e86  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180001e8a  xor     r8d, r8d; Timeout
0x180001e8d  xor     edx, edx; Alertable
0x180001e8f  call    cs:__imp_NtWaitForSingleObject
0x180001e96  nop     dword ptr [rax+rax+00h]
0x180001e9b  mov     edi, dword ptr [rbp+57h+IoStatusBlock]
0x180001e9e  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180001ea2  call    cs:__imp_NtClose
0x180001ea9  nop     dword ptr [rax+rax+00h]
0x180001eae  test    edi, edi
0x180001eb0  jns     short loc_180001ED8
0x180001eb2  cmp     edi, 0C000007Ch
0x180001eb8  jnz     short loc_180001ECE
0x180001eba  test    sil, sil
0x180001ebd  jnz     short loc_180001F09
0x180001ebf  mov     sil, 1
0x180001ec2  lea     rdx, aDeviceLanmanse; "\\Device\\LanmanServer"
0x180001ec9  jmp     loc_180001DC7
0x180001ece  cmp     edi, 0C0980005h
0x180001ed4  jz      short loc_180001F09
0x180001ed6  jmp     short loc_180001F18
0x180001ed8  mov     r8d, 10h; Length
0x180001ede  lea     rdx, ErrorSessionKey; Source2
0x180001ee5  mov     rcx, rbx; Source1
0x180001ee8  call    cs:__imp_RtlCompareMemory
0x180001eef  nop     dword ptr [rax+rax+00h]
0x180001ef4  cmp     rax, 10h
0x180001ef8  mov     ecx, 0C0000202h
0x180001efd  cmovz   edi, ecx
0x180001f00  jmp     short loc_180001F18
0x180001f02  cmp     eax, 0C0000034h
0x180001f07  jnz     short loc_180001F18
0x180001f09  movups  xmm0, cs:LocalSessionKey
0x180001f10  mov     edi, 40000006h
0x180001f15  movups  xmmword ptr [rbx], xmm0
0x180001f18  mov     rsi, [rsp+110h+arg_0]
0x180001f20  mov     eax, edi
0x180001f22  mov     rdi, [rsp+110h+arg_10]
0x180001f2a  mov     rcx, [rbp+57h+var_18]
0x180001f2e  xor     rcx, rsp; StackCookie
0x180001f31  call    __security_check_cookie
0x180001f36  add     rsp, 100h
0x180001f3d  pop     r14
0x180001f3f  pop     rbx
0x180001f40  pop     rbp
0x180001f41  retn
```
