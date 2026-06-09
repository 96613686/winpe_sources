# OpenEventW

- ea: `0x1800b62a0`
- end: `0x1800b64f9`
- name: `OpenEventW`
- size: `601`
- prototype: `HANDLE __stdcall(DWORD dwDesiredAccess, BOOL bInheritHandle, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b61e0`

## callees

- `0x1800134a0`
- `0x18006e604`
- `0x1800b62a0`
- `0x180197010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800b62eb`
- `ntdll!RtlInitUnicodeString` at `0x1800b62eb`
- `ntdll!NtClose` at `0x1800b6446`
- `ntdll!NtClose` at `0x1800b6455`
- `ntdll!NtClose` at `0x1800b64ee`
- `ntdll!NtClose` at `0x1800b6446`
- `ntdll!NtClose` at `0x1800b6455`
- `ntdll!NtClose` at `0x1800b64ee`
- `ntdll!NtOpenProcessToken` at `0x1800b63d8`
- `ntdll!NtOpenProcessToken` at `0x1800b63d8`
- `ntdll!NtOpenThreadToken` at `0x1800b6486`
- `ntdll!NtOpenThreadToken` at `0x1800b6486`
- `ntdll!NtSetInformationThread` at `0x1800b64ad`
- `ntdll!NtSetInformationThread` at `0x1800b64e4`
- `ntdll!NtSetInformationThread` at `0x1800b64ad`
- `ntdll!NtSetInformationThread` at `0x1800b64e4`
- `ntdll!NtOpenEvent` at `0x1800b6355`
- `ntdll!NtOpenEvent` at `0x1800b6355`

## pseudocode

```c
HANDLE __stdcall OpenEventW(DWORD dwDesiredAccess, BOOL bInheritHandle, LPCWSTR lpName)
{
  void *v5; // rbx
  NTSTATUS v6; // eax
  int v8; // r15d
  int NamedObjectDirectoryForToken; // r14d
  HANDLE v10; // rcx
  HANDLE TokenHandle; // [rsp+38h] [rbp-29h] BYREF
  __int64 ThreadInformation; // [rsp+40h] [rbp-21h] BYREF
  HANDLE EventHandle; // [rsp+48h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-1h] BYREF
  HANDLE v16; // [rsp+D8h] [rbp+77h] BYREF
  HANDLE Handle; // [rsp+E0h] [rbp+7Fh] BYREF

  EventHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( !lpName )
  {
    BaseSetLastNTError(3221225485LL);
    return 0;
  }
  RtlInitUnicodeString(&DestinationString, lpName);
  v5 = (void *)BaseNamedObjectDirectory;
  v16 = 0;
  TokenHandle = 0;
  ThreadInformation = 0;
  Handle = 0;
  if ( BaseNamedObjectDirectory )
    goto LABEL_3;
  v5 = 0;
  v8 = 0;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    NamedObjectDirectoryForToken = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 4u, 1u, &v16);
    if ( NamedObjectDirectoryForToken < 0 )
      goto LABEL_15;
    ThreadInformation = 0;
    NamedObjectDirectoryForToken = NtSetInformationThread(
                                     (HANDLE)0xFFFFFFFFFFFFFFFELL,
                                     ThreadImpersonationToken,
                                     &ThreadInformation,
                                     8u);
    if ( NamedObjectDirectoryForToken < 0 )
      goto LABEL_15;
    v8 = 1;
  }
  NamedObjectDirectoryForToken = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( NamedObjectDirectoryForToken >= 0 )
  {
    NamedObjectDirectoryForToken = BasepGetNamedObjectDirectoryForToken(TokenHandle, 0, 1, 15, &Handle);
    if ( NamedObjectDirectoryForToken >= 0 )
    {
      if ( !_InterlockedCompareExchange64(&BaseNamedObjectDirectory, (signed __int64)Handle, 0) )
        Handle = 0;
      v5 = (void *)BaseNamedObjectDirectory;
    }
  }
LABEL_15:
  v10 = v16;
  if ( v16 )
  {
    if ( v8 )
    {
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &v16, 8u);
      v10 = v16;
    }
    NtClose(v10);
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( Handle )
    NtClose(Handle);
  if ( NamedObjectDirectoryForToken < 0 )
  {
    BaseSetLastNTError((unsigned int)NamedObjectDirectoryForToken);
    return 0;
  }
LABEL_3:
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v5;
  ObjectAttributes.Attributes = bInheritHandle ? 2 : 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( pfnAdjustObjectAttributesForPrivateNamespace )
    pfnAdjustObjectAttributesForPrivateNamespace(&ObjectAttributes);
  v6 = NtOpenEvent(&EventHandle, dwDesiredAccess, &ObjectAttributes);
  if ( v6 >= 0 )
    return EventHandle;
  BaseSetLastNTError((unsigned int)v6);
  return 0;
}

```

## disassembly

```asm
0x1800b62a0  mov     r11, rsp
0x1800b62a3  push    rbp
0x1800b62a4  push    rsi
0x1800b62a5  push    rdi
0x1800b62a6  push    r12
0x1800b62a8  lea     rbp, [r11-5Fh]
0x1800b62ac  sub     rsp, 98h
0x1800b62b3  xorps   xmm0, xmm0
0x1800b62b6  xor     r12d, r12d
0x1800b62b9  xor     eax, eax
0x1800b62bb  mov     [rbp+57h+EventHandle], r12
0x1800b62bf  mov     edi, edx
0x1800b62c1  mov     esi, ecx
0x1800b62c3  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800b62c7  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800b62cb  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800b62cf  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800b62d3  test    r8, r8
0x1800b62d6  jz      loc_1800B638B
0x1800b62dc  mov     [r11+8], rbx
0x1800b62e0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800b62e4  mov     rdx, r8; SourceString
0x1800b62e7  mov     [r11+10h], r14
0x1800b62eb  call    cs:__imp_RtlInitUnicodeString
0x1800b62f1  mov     rbx, cs:BaseNamedObjectDirectory
0x1800b62f8  mov     [rbp+57h+arg_10], r12
0x1800b62fc  mov     [rbp+57h+TokenHandle], r12
0x1800b6300  mov     [rbp+57h+ThreadInformation], r12
0x1800b6304  mov     [rbp+57h+Handle], r12
0x1800b6308  test    rbx, rbx
0x1800b630b  jz      loc_1800B63A4
0x1800b6311  neg     edi
0x1800b6313  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800b631a  xorps   xmm0, xmm0
0x1800b631d  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1800b6321  sbb     eax, eax
0x1800b6323  and     eax, 2
0x1800b6326  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x1800b6329  lea     rax, [rbp+57h+DestinationString]
0x1800b632d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800b6331  mov     rax, cs:pfnAdjustObjectAttributesForPrivateNamespace
0x1800b6338  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b633d  test    rax, rax
0x1800b6340  jz      short loc_1800B634B
0x1800b6342  lea     rcx, [rbp+57h+ObjectAttributes]
0x1800b6346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b634b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800b634f  mov     edx, esi; DesiredAccess
0x1800b6351  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x1800b6355  call    cs:__imp_NtOpenEvent
0x1800b635b  test    eax, eax
0x1800b635d  js      short loc_1800B6380
0x1800b635f  mov     rax, [rbp+57h+EventHandle]
0x1800b6363  mov     rbx, [rsp+0B0h+arg_0]
0x1800b636b  mov     r14, [rsp+0B0h+arg_8]
0x1800b6373  add     rsp, 98h
0x1800b637a  pop     r12
0x1800b637c  pop     rdi
0x1800b637d  pop     rsi
0x1800b637e  pop     rbp
0x1800b637f  retn
0x1800b6380  mov     ecx, eax
0x1800b6382  call    BaseSetLastNTError
0x1800b6387  xor     eax, eax
0x1800b6389  jmp     short loc_1800B6363
0x1800b638b  mov     ecx, 0C000000Dh
0x1800b6390  call    BaseSetLastNTError
0x1800b6395  xor     eax, eax
0x1800b6397  add     rsp, 98h
0x1800b639e  pop     r12
0x1800b63a0  pop     rdi
0x1800b63a1  pop     rsi
0x1800b63a2  pop     rbp
0x1800b63a3  retn
0x1800b63a4  mov     rax, gs:30h
0x1800b63ad  mov     rbx, r12
0x1800b63b0  mov     [rsp+90h], r15
0x1800b63b8  mov     r15d, r12d
0x1800b63bb  cmp     [rax+179Ch], r12d
0x1800b63c2  jnz     loc_1800B6473
0x1800b63c8  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800b63cc  mov     edx, 8; DesiredAccess
0x1800b63d1  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800b63d8  call    cs:__imp_NtOpenProcessToken
0x1800b63de  mov     r14d, eax
0x1800b63e1  test    eax, eax
0x1800b63e3  js      short loc_1800B6428
0x1800b63e5  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800b63e9  lea     rax, [rbp+57h+Handle]
0x1800b63ed  xor     edx, edx
0x1800b63ef  mov     [rsp+20h], rax; __int64
0x1800b63f4  mov     r9d, 0Fh
0x1800b63fa  mov     r8d, 1
0x1800b6400  call    BasepGetNamedObjectDirectoryForToken
0x1800b6405  mov     r14d, eax
0x1800b6408  test    eax, eax
0x1800b640a  js      short loc_1800B6428
0x1800b640c  mov     rcx, [rbp+57h+Handle]
0x1800b6410  xor     eax, eax
0x1800b6412  lock cmpxchg cs:BaseNamedObjectDirectory, rcx
0x1800b641b  jnz     short loc_1800B6421
0x1800b641d  mov     [rbp+57h+Handle], r12
0x1800b6421  mov     rbx, cs:BaseNamedObjectDirectory
0x1800b6428  mov     rcx, [rbp+57h+arg_10]
0x1800b642c  test    rcx, rcx
0x1800b642f  jnz     loc_1800B64C9
0x1800b6435  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800b6439  mov     r15, [rsp+90h]
0x1800b6441  test    rcx, rcx
0x1800b6444  jz      short loc_1800B644C
0x1800b6446  call    cs:__imp_NtClose
0x1800b644c  mov     rcx, [rbp+57h+Handle]; Handle
0x1800b6450  test    rcx, rcx
0x1800b6453  jz      short loc_1800B645B
0x1800b6455  call    cs:__imp_NtClose
0x1800b645b  test    r14d, r14d
0x1800b645e  jns     loc_1800B6311
0x1800b6464  mov     ecx, r14d
0x1800b6467  call    BaseSetLastNTError
0x1800b646c  xor     eax, eax
0x1800b646e  jmp     loc_1800B6363
0x1800b6473  lea     r9, [rbp+57h+arg_10]; TokenHandle
0x1800b6477  mov     r8b, 1; OpenAsSelf
0x1800b647a  mov     edx, 4; DesiredAccess
0x1800b647f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800b6486  call    cs:__imp_NtOpenThreadToken
0x1800b648c  mov     r14d, eax
0x1800b648f  test    eax, eax
0x1800b6491  js      short loc_1800B6428
0x1800b6493  mov     r9d, 8; ThreadInformationLength
0x1800b6499  mov     [rbp+57h+ThreadInformation], r12
0x1800b649d  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x1800b64a1  mov     edx, 5; ThreadInformationClass
0x1800b64a6  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800b64ad  call    cs:__imp_NtSetInformationThread
0x1800b64b3  mov     r14d, eax
0x1800b64b6  test    eax, eax
0x1800b64b8  js      loc_1800B6428
0x1800b64be  mov     r15d, 1
0x1800b64c4  jmp     loc_1800B63C8
0x1800b64c9  test    r15d, r15d
0x1800b64cc  jz      short loc_1800B64EE
0x1800b64ce  mov     r9d, 8; ThreadInformationLength
0x1800b64d4  lea     r8, [rbp+57h+arg_10]; ThreadInformation
0x1800b64d8  mov     edx, 5; ThreadInformationClass
0x1800b64dd  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800b64e4  call    cs:__imp_NtSetInformationThread
0x1800b64ea  mov     rcx, [rbp+57h+arg_10]; Handle
0x1800b64ee  call    cs:__imp_NtClose
0x1800b64f4  jmp     loc_1800B6435
```
