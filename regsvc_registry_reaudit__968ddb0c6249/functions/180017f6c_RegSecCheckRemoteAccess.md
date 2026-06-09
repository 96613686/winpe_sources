# RegSecCheckRemoteAccess

- ea: `0x180017f6c`
- end: `0x1800180ae`
- name: `RegSecCheckRemoteAccess`
- size: `322`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18001a710`
- `0x18001aad0`

## callees

- `0x180007740`
- `0x180017b54`
- `0x180017f6c`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180017ff5`
- `ntdll!RtlReleaseResource` at `0x180018069`
- `ntdll!RtlReleaseResource` at `0x1800180a6`
- `ntdll!RtlReleaseResource` at `0x180017ff5`
- `ntdll!RtlReleaseResource` at `0x180018069`
- `ntdll!RtlReleaseResource` at `0x1800180a6`
- `ntdll!NtAccessCheck` at `0x18001805a`
- `ntdll!NtAccessCheck` at `0x18001805a`
- `ntdll!RtlAcquireResourceShared` at `0x180017fbb`
- `ntdll!RtlAcquireResourceShared` at `0x180017fbb`
- `ntdll!NtOpenThreadToken` at `0x180017fe4`
- `ntdll!NtOpenThreadToken` at `0x180017fe4`
- `ntdll!NtClose` at `0x180018073`
- `ntdll!NtClose` at `0x180018073`

## pseudocode

```c
__int64 RegSecCheckRemoteAccess()
{
  NTSTATUS v1; // ebx
  ULONG ReturnLength; // [rsp+40h] [rbp-29h] BYREF
  int AccessStatus; // [rsp+44h] [rbp-25h] BYREF
  DWORD GrantedAccess; // [rsp+48h] [rbp-21h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-19h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-9h] BYREF

  GrantedAccess = 0;
  AccessStatus = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  if ( RegSecCheckIfAclValid() < 0 )
    return 0;
  RtlAcquireResourceShared(RegSecReloadLock, 1u);
  if ( RemoteRegistrySD )
  {
    if ( NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000000u, 1u, &TokenHandle) < 0 )
    {
      RtlReleaseResource(RegSecReloadLock);
      return 0;
    }
    ReturnLength = 68;
    v1 = NtAccessCheck(
           RemoteRegistrySD,
           TokenHandle,
           0x2000000u,
           &RemoteRegistryMappings,
           &PrivilegeSet,
           &ReturnLength,
           &GrantedAccess,
           &AccessStatus);
    RtlReleaseResource(RegSecReloadLock);
    NtClose(TokenHandle);
    if ( v1 < 0 || AccessStatus < 0 || (GrantedAccess & 3) == 0 )
      return 0;
  }
  else
  {
    RtlReleaseResource(RegSecReloadLock);
  }
  return 1;
}

```

## disassembly

```asm
0x180017f6c  mov     [rsp-8+arg_0], rbx
0x180017f71  push    rbp
0x180017f72  lea     rbp, [rsp-57h]
0x180017f77  sub     rsp, 0C0h
0x180017f7e  mov     rax, cs:__security_cookie
0x180017f85  xor     rax, rsp
0x180017f88  mov     [rbp+57h+var_10], rax
0x180017f8c  mov     [rbp+57h+var_78], 0
0x180017f93  mov     [rbp+57h+var_7C], 0
0x180017f9a  mov     [rbp+57h+TokenHandle], 0
0x180017fa2  mov     [rbp+57h+var_80], 0
0x180017fa9  call    RegSecCheckIfAclValid
0x180017fae  test    eax, eax
0x180017fb0  js      short loc_180017FFB
0x180017fb2  mov     rcx, cs:RegSecReloadLock; Resource
0x180017fb9  mov     dl, 1; Wait
0x180017fbb  call    cs:__imp_RtlAcquireResourceShared
0x180017fc1  cmp     cs:RemoteRegistrySD, 0
0x180017fc9  jz      loc_18001809F
0x180017fcf  mov     ebx, 2000000h
0x180017fd4  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180017fd8  mov     edx, ebx; DesiredAccess
0x180017fda  mov     r8b, 1; OpenAsSelf
0x180017fdd  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180017fe4  call    cs:__imp_NtOpenThreadToken
0x180017fea  test    eax, eax
0x180017fec  jns     short loc_18001801A
0x180017fee  mov     rcx, cs:RegSecReloadLock; Resource
0x180017ff5  call    cs:__imp_RtlReleaseResource
0x180017ffb  xor     eax, eax
0x180017ffd  mov     rcx, [rbp+57h+var_10]
0x180018001  xor     rcx, rsp; StackCookie
0x180018004  call    __security_check_cookie
0x180018009  mov     rbx, [rsp+0C0h+arg_0]
0x180018011  add     rsp, 0C0h
0x180018018  pop     rbp
0x180018019  retn
0x18001801a  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x18001801e  lea     rax, [rbp+57h+var_7C]
0x180018022  mov     rcx, cs:RemoteRegistrySD; SecurityDescriptor
0x180018029  lea     r9, RemoteRegistryMappings; GenericMapping
0x180018030  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x180018035  mov     r8d, ebx; DesiredAccess
0x180018038  lea     rax, [rbp+57h+var_78]
0x18001803c  mov     [rbp+57h+var_80], 44h ; 'D'
0x180018043  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x180018048  lea     rax, [rbp+57h+var_80]
0x18001804c  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180018051  lea     rax, [rbp+57h+var_60]
0x180018055  mov     [rsp+0C0h+PrivilegeSet], rax; PrivilegeSet
0x18001805a  call    cs:__imp_NtAccessCheck
0x180018060  mov     rcx, cs:RegSecReloadLock; Resource
0x180018067  mov     ebx, eax
0x180018069  call    cs:__imp_RtlReleaseResource
0x18001806f  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180018073  call    cs:__imp_NtClose
0x180018079  test    ebx, ebx
0x18001807b  js      loc_180017FFB
0x180018081  cmp     [rbp+57h+var_7C], 0
0x180018085  jl      loc_180017FFB
0x18001808b  test    byte ptr [rbp+57h+var_78], 3
0x18001808f  jz      loc_180017FFB
0x180018095  mov     eax, 1
0x18001809a  jmp     loc_180017FFD
0x18001809f  mov     rcx, cs:RegSecReloadLock; Resource
0x1800180a6  call    cs:__imp_RtlReleaseResource
0x1800180ac  jmp     short loc_180018095
```
