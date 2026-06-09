# RegSecCheckIfAclValid

- ea: `0x180017b54`
- end: `0x180017df5`
- name: `RegSecCheckIfAclValid`
- size: `673`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017f6c`

## callees

- `0x180007740`
- `0x180017b54`
- `0x180018538`
- `0x18001d698`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180017cd2`
- `ntdll!RtlReleaseResource` at `0x180017dcc`
- `ntdll!RtlReleaseResource` at `0x180017cd2`
- `ntdll!RtlReleaseResource` at `0x180017dcc`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x180017d5e`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x180017d5e`
- `ntdll!RtlAcquireResourceExclusive` at `0x180017c92`
- `ntdll!RtlAcquireResourceExclusive` at `0x180017d27`
- `ntdll!RtlAcquireResourceExclusive` at `0x180017c92`
- `ntdll!RtlAcquireResourceExclusive` at `0x180017d27`
- `ntdll!NtOpenThreadToken` at `0x180017bde`
- `ntdll!NtOpenThreadToken` at `0x180017bde`
- `ntdll!NtClose` at `0x180017c5a`
- `ntdll!NtClose` at `0x180017dd5`
- `ntdll!NtClose` at `0x180017c5a`
- `ntdll!NtClose` at `0x180017dd5`
- `ntdll!NtSetInformationThread` at `0x180017c0e`
- `ntdll!NtSetInformationThread` at `0x180017c4d`
- `ntdll!NtSetInformationThread` at `0x180017c0e`
- `ntdll!NtSetInformationThread` at `0x180017c4d`
- `ntdll!RtlFreeHeap` at `0x180017cb7`
- `ntdll!RtlFreeHeap` at `0x180017d7c`
- `ntdll!RtlFreeHeap` at `0x180017d98`
- `ntdll!RtlFreeHeap` at `0x180017cb7`
- `ntdll!RtlFreeHeap` at `0x180017d7c`
- `ntdll!RtlFreeHeap` at `0x180017d98`
- `ntdll!NtQueryKey` at `0x180017cfd`
- `ntdll!NtQueryKey` at `0x180017cfd`
- `ntdll!RtlInitUnicodeStringEx` at `0x180017bad`
- `ntdll!RtlInitUnicodeStringEx` at `0x180017bad`

## string_xrefs

- `0x180017b86`: `\Registry\Machine\System\CurrentControlSet\Control\SecurePipeServers\winreg`

## pseudocode

```c
NTSTATUS RegSecCheckIfAclValid()
{
  NTSTATUS result; // eax
  int SDFromRegistry; // ebx
  NTSTATUS v2; // edi
  HANDLE v3; // rdi
  int ResultLength; // [rsp+20h] [rbp-E0h]
  unsigned __int8 GroupDefaulted[8]; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v8; // [rsp+48h] [rbp-B8h] BYREF
  __int64 ThreadInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v11; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+78h] [rbp-88h]
  __int64 v13; // [rsp+80h] [rbp-80h]
  __int128 v14; // [rsp+88h] [rbp-78h]
  __int64 KeyInformation[24]; // [rsp+A0h] [rbp-60h] BYREF

  *(_QWORD *)&v11 = 48;
  KeyHandle = 0;
  TokenHandle = 0;
  ThreadInformation = 0;
  DestinationString = 0;
  v8 = 0;
  v13 = 64;
  RtlInitUnicodeStringEx(&DestinationString, RemoteRegistryKey);
  *((_QWORD *)&v11 + 1) = 0;
  p_DestinationString = &DestinationString;
  v14 = 0;
  result = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000000u, 1u, &TokenHandle);
  if ( ((result + 1073741732) & 0xFFFFFFDF) != 0 )
  {
    if ( result )
      return result;
    ThreadInformation = 0;
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
  else
  {
    TokenHandle = 0;
  }
  SDFromRegistry = Wow64NtOpenKey(&KeyHandle, 0x20019u, &v11, 0, ResultLength);
  if ( TokenHandle
    && (v2 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u),
        NtClose(TokenHandle),
        v2 < 0) )
  {
    SDFromRegistry = v2;
  }
  else if ( SDFromRegistry >= 0 )
  {
    v3 = KeyHandle;
    SDFromRegistry = NtQueryKey(KeyHandle, KeyBasicInformation, KeyInformation, 0xC0u, &v8);
    if ( SDFromRegistry >= 0 && KeyInformation[0] > WinregChange )
    {
      RtlAcquireResourceExclusive(RegSecReloadLock, 1u);
      if ( KeyInformation[0] > WinregChange )
      {
        if ( RemoteRegistrySD )
        {
          KeyHandle = 0;
          GroupDefaulted[0] = 0;
          if ( RtlGetGroupSecurityDescriptor(RemoteRegistrySD, &KeyHandle, GroupDefaulted) >= 0 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, KeyHandle);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, RemoteRegistrySD);
          RemoteRegistrySD = 0;
        }
        SDFromRegistry = RegSecReadSDFromRegistry(v3, (struct _ACL **)&RemoteRegistrySD);
        if ( SDFromRegistry >= 0 )
          WinregChange = KeyInformation[0];
      }
      RtlReleaseResource(RegSecReloadLock);
    }
    NtClose(v3);
    return SDFromRegistry;
  }
  if ( SDFromRegistry == -1073741766 || SDFromRegistry == -1073741772 )
  {
    if ( WinregChange )
    {
      RtlAcquireResourceExclusive(RegSecReloadLock, 1u);
      if ( WinregChange )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, RemoteRegistrySD);
        RemoteRegistrySD = 0;
        WinregChange = 0;
      }
      RtlReleaseResource(RegSecReloadLock);
    }
    return 0;
  }
  return SDFromRegistry;
}

```

## disassembly

```asm
0x180017b54  push    rbp
0x180017b56  push    rbx
0x180017b57  push    rsi
0x180017b58  push    rdi
0x180017b59  lea     rbp, [rsp-78h]
0x180017b5e  sub     rsp, 178h
0x180017b65  mov     rax, cs:__security_cookie
0x180017b6c  xor     rax, rsp
0x180017b6f  mov     [rbp+90h+var_30], rax
0x180017b73  xor     esi, esi
0x180017b75  mov     qword ptr [rsp+190h+var_128], 30h ; '0'
0x180017b7e  xorps   xmm0, xmm0
0x180017b81  mov     [rsp+190h+KeyHandle], rsi
0x180017b86  lea     rdx, RemoteRegistryKey; "\\Registry\\Machine\\System\\CurrentCon"...
0x180017b8d  mov     [rsp+190h+TokenHandle], rsi
0x180017b92  lea     rcx, [rsp+190h+DestinationString]; DestinationString
0x180017b97  mov     [rsp+190h+ThreadInformation], rsi
0x180017b9c  movups  xmmword ptr [rsp+190h+DestinationString.Length], xmm0
0x180017ba1  mov     [rsp+190h+var_148], esi
0x180017ba5  mov     [rbp+90h+var_110], 40h ; '@'
0x180017bad  call    cs:__imp_RtlInitUnicodeStringEx
0x180017bb3  lea     rax, [rsp+190h+DestinationString]
0x180017bb8  mov     [rsp+190h+var_120], rsi
0x180017bbd  xorps   xmm0, xmm0
0x180017bc0  mov     [rsp+190h+var_118], rax
0x180017bc5  lea     rdi, [rsi-2]
0x180017bc9  mov     r8b, 1; OpenAsSelf
0x180017bcc  mov     rcx, rdi; ThreadHandle
0x180017bcf  lea     r9, [rsp+190h+TokenHandle]; TokenHandle
0x180017bd4  mov     edx, 2000000h; DesiredAccess
0x180017bd9  movdqu  [rbp+90h+var_108], xmm0
0x180017bde  call    cs:__imp_NtOpenThreadToken
0x180017be4  lea     ecx, [rax+3FFFFFA4h]
0x180017bea  test    ecx, 0FFFFFFDFh
0x180017bf0  jz      short loc_180017C16
0x180017bf2  test    eax, eax
0x180017bf4  jnz     loc_180017DDD
0x180017bfa  lea     r9d, [rsi+8]; ThreadInformationLength
0x180017bfe  mov     [rsp+190h+ThreadInformation], rsi
0x180017c03  lea     r8, [rsp+190h+ThreadInformation]; ThreadInformation
0x180017c08  mov     rcx, rdi; ThreadHandle
0x180017c0b  lea     edx, [rsi+5]; ThreadInformationClass
0x180017c0e  call    cs:__imp_NtSetInformationThread
0x180017c14  jmp     short loc_180017C1B
0x180017c16  mov     [rsp+190h+TokenHandle], rsi
0x180017c1b  xor     r9d, r9d; int
0x180017c1e  lea     r8, [rsp+190h+var_128]; int
0x180017c23  mov     edx, 20019h; int
0x180017c28  lea     rcx, [rsp+190h+KeyHandle]; int
0x180017c2d  call    Wow64NtOpenKey
0x180017c32  mov     ebx, eax
0x180017c34  cmp     [rsp+190h+TokenHandle], rsi
0x180017c39  jz      short loc_180017C68
0x180017c3b  mov     r9d, 8; ThreadInformationLength
0x180017c41  lea     r8, [rsp+190h+TokenHandle]; ThreadInformation
0x180017c46  mov     rcx, rdi; ThreadHandle
0x180017c49  lea     edx, [r9-3]; ThreadInformationClass
0x180017c4d  call    cs:__imp_NtSetInformationThread
0x180017c53  mov     rcx, [rsp+190h+TokenHandle]; Handle
0x180017c58  mov     edi, eax
0x180017c5a  call    cs:__imp_NtClose
0x180017c60  test    edi, edi
0x180017c62  jns     short loc_180017C68
0x180017c64  mov     ebx, edi
0x180017c66  jmp     short loc_180017C6C
0x180017c68  test    ebx, ebx
0x180017c6a  jns     short loc_180017CDF
0x180017c6c  cmp     ebx, 0C000003Ah
0x180017c72  jz      short loc_180017C80
0x180017c74  cmp     ebx, 0C0000034h
0x180017c7a  jnz     loc_180017DDB
0x180017c80  cmp     cs:WinregChange, rsi
0x180017c87  jz      short loc_180017CD8
0x180017c89  mov     rcx, cs:RegSecReloadLock; Resource
0x180017c90  mov     dl, 1; Wait
0x180017c92  call    cs:__imp_RtlAcquireResourceExclusive
0x180017c98  cmp     cs:WinregChange, rsi
0x180017c9f  jz      short loc_180017CCB
0x180017ca1  mov     rcx, gs:60h
0x180017caa  xor     edx, edx; Flags
0x180017cac  mov     r8, cs:RemoteRegistrySD; P
0x180017cb3  mov     rcx, [rcx+30h]; HeapHandle
0x180017cb7  call    cs:__imp_RtlFreeHeap
0x180017cbd  mov     cs:RemoteRegistrySD, rsi
0x180017cc4  mov     cs:WinregChange, rsi
0x180017ccb  mov     rcx, cs:RegSecReloadLock; Resource
0x180017cd2  call    cs:__imp_RtlReleaseResource
0x180017cd8  mov     ebx, esi
0x180017cda  jmp     loc_180017DDB
0x180017cdf  mov     rdi, [rsp+190h+KeyHandle]
0x180017ce4  lea     rax, [rsp+190h+var_148]
0x180017ce9  mov     rcx, rdi; KeyHandle
0x180017cec  mov     qword ptr [rsp+190h+ResultLength], rax; ResultLength
0x180017cf1  mov     r9d, 0C0h; Length
0x180017cf7  lea     r8, [rbp+90h+KeyInformation]; KeyInformation
0x180017cfb  xor     edx, edx; KeyInformationClass
0x180017cfd  call    cs:__imp_NtQueryKey
0x180017d03  mov     ebx, eax
0x180017d05  test    eax, eax
0x180017d07  js      loc_180017DD2
0x180017d0d  mov     rax, cs:WinregChange
0x180017d14  cmp     [rbp+90h+KeyInformation], rax
0x180017d18  jle     loc_180017DD2
0x180017d1e  mov     rcx, cs:RegSecReloadLock; Resource
0x180017d25  mov     dl, 1; Wait
0x180017d27  call    cs:__imp_RtlAcquireResourceExclusive
0x180017d2d  mov     rax, cs:WinregChange
0x180017d34  cmp     [rbp+90h+KeyInformation], rax
0x180017d38  jle     loc_180017DC5
0x180017d3e  mov     rcx, cs:RemoteRegistrySD; SecurityDescriptor
0x180017d45  test    rcx, rcx
0x180017d48  jz      short loc_180017DA5
0x180017d4a  lea     r8, [rsp+190h+GroupDefaulted]; GroupDefaulted
0x180017d4f  mov     [rsp+190h+KeyHandle], rsi
0x180017d54  lea     rdx, [rsp+190h+KeyHandle]; Group
0x180017d59  mov     [rsp+190h+GroupDefaulted], sil
0x180017d5e  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x180017d64  test    eax, eax
0x180017d66  js      short loc_180017D82
0x180017d68  mov     rcx, gs:60h
0x180017d71  xor     edx, edx; Flags
0x180017d73  mov     r8, [rsp+190h+KeyHandle]; P
0x180017d78  mov     rcx, [rcx+30h]; HeapHandle
0x180017d7c  call    cs:__imp_RtlFreeHeap
0x180017d82  mov     rcx, gs:60h
0x180017d8b  xor     edx, edx; Flags
0x180017d8d  mov     r8, cs:RemoteRegistrySD; P
0x180017d94  mov     rcx, [rcx+30h]; HeapHandle
0x180017d98  call    cs:__imp_RtlFreeHeap
0x180017d9e  mov     cs:RemoteRegistrySD, rsi
0x180017da5  lea     rdx, RemoteRegistrySD
0x180017dac  mov     rcx, rdi; Handle
0x180017daf  call    RegSecReadSDFromRegistry
0x180017db4  mov     ebx, eax
0x180017db6  test    eax, eax
0x180017db8  js      short loc_180017DC5
0x180017dba  mov     rax, [rbp+90h+KeyInformation]
0x180017dbe  mov     cs:WinregChange, rax
0x180017dc5  mov     rcx, cs:RegSecReloadLock; Resource
0x180017dcc  call    cs:__imp_RtlReleaseResource
0x180017dd2  mov     rcx, rdi; Handle
0x180017dd5  call    cs:__imp_NtClose
0x180017ddb  mov     eax, ebx
0x180017ddd  mov     rcx, [rbp+90h+var_30]
0x180017de1  xor     rcx, rsp; StackCookie
0x180017de4  call    __security_check_cookie
0x180017de9  add     rsp, 178h
0x180017df0  pop     rdi
0x180017df1  pop     rsi
0x180017df2  pop     rbx
0x180017df3  pop     rbp
0x180017df4  retn
```
