# RmpWnfGetPublisherSid

- ea: `0x18002de14`
- end: `0x18002dee6`
- name: `RmpWnfGetPublisherSid`
- size: `210`
- prototype: `__int64 __fastcall(PSID DestinationSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800241e4`

## callees

- `0x18001b7e0`
- `0x18001c10c`
- `0x18002de14`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18002dead`
- `ntdll!RtlCopySid` at `0x18002dead`
- `ntdll!NtClose` at `0x18002debd`
- `ntdll!NtClose` at `0x18002debd`
- `ntdll!NtOpenProcessToken` at `0x18002de6a`
- `ntdll!NtOpenProcessToken` at `0x18002de6a`
- `ntdll!NtQueryInformationToken` at `0x18002de94`
- `ntdll!NtQueryInformationToken` at `0x18002de94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002de57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002de57`

## pseudocode

```c
__int64 __fastcall RmpWnfGetPublisherSid(PSID DestinationSid)
{
  HANDLE CurrentProcess; // rax
  NTSTATUS v3; // ebx
  ULONG ReturnLength; // [rsp+30h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-80h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  ReturnLength = 0;
  memset_0(TokenInformation, 0, 0x58u);
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  v3 = NtOpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  if ( v3 >= 0 )
  {
    v3 = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength);
    if ( v3 >= 0 )
      RtlCopySid(0x44u, DestinationSid, TokenInformation[0]);
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002de14  mov     [rsp+arg_8], rbx
0x18002de19  push    rdi
0x18002de1a  sub     rsp, 0B0h
0x18002de21  mov     rax, cs:__security_cookie
0x18002de28  xor     rax, rsp
0x18002de2b  mov     [rsp+0B8h+var_18], rax
0x18002de33  xor     edx, edx; Val
0x18002de35  mov     [rsp+0B8h+var_88], 0
0x18002de3d  mov     rdi, rcx
0x18002de40  lea     rcx, [rsp+0B8h+TokenInformation]; void *
0x18002de45  lea     r8d, [rdx+58h]; Size
0x18002de49  call    memset_0
0x18002de4e  mov     [rsp+0B8h+TokenHandle], 0
0x18002de57  call    cs:__imp_GetCurrentProcess
0x18002de5d  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x18002de62  mov     edx, 8; DesiredAccess
0x18002de67  mov     rcx, rax; ProcessHandle
0x18002de6a  call    cs:__imp_NtOpenProcessToken
0x18002de70  mov     ebx, eax
0x18002de72  test    eax, eax
0x18002de74  js      short loc_18002DEB3
0x18002de76  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x18002de7b  lea     rax, [rsp+0B8h+var_88]
0x18002de80  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18002de86  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18002de8b  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18002de90  lea     edx, [r9-57h]; TokenInformationClass
0x18002de94  call    cs:__imp_NtQueryInformationToken
0x18002de9a  mov     ebx, eax
0x18002de9c  test    eax, eax
0x18002de9e  js      short loc_18002DEB3
0x18002dea0  mov     r8, [rsp+0B8h+TokenInformation]; SourceSid
0x18002dea5  mov     rdx, rdi; DestinationSid
0x18002dea8  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18002dead  call    cs:__imp_RtlCopySid
0x18002deb3  mov     rcx, [rsp+0B8h+TokenHandle]; Handle
0x18002deb8  test    rcx, rcx
0x18002debb  jz      short loc_18002DEC3
0x18002debd  call    cs:__imp_NtClose
0x18002dec3  mov     eax, ebx
0x18002dec5  mov     rcx, [rsp+0B8h+var_18]
0x18002decd  xor     rcx, rsp; StackCookie
0x18002ded0  call    __security_check_cookie
0x18002ded5  mov     rbx, [rsp+0B8h+arg_8]
0x18002dedd  add     rsp, 0B0h
0x18002dee4  pop     rdi
0x18002dee5  retn
```
