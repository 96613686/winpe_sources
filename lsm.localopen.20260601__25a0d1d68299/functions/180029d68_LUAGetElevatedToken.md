# LUAGetElevatedToken

- ea: `0x180029d68`
- end: `0x180029e98`
- name: `LUAGetElevatedToken`
- size: `304`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002f3c0`
- `0x180058770`

## callees

- `0x180029d68`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x180029e56`
- `ntdll!NtDuplicateToken` at `0x180029e56`
- `ntdll!NtQueryInformationToken` at `0x180029dc3`
- `ntdll!NtQueryInformationToken` at `0x180029dff`
- `ntdll!NtQueryInformationToken` at `0x180029e74`
- `ntdll!NtQueryInformationToken` at `0x180029dc3`
- `ntdll!NtQueryInformationToken` at `0x180029dff`
- `ntdll!NtQueryInformationToken` at `0x180029e74`

## pseudocode

```c
__int64 __fastcall LUAGetElevatedToken(HANDLE TokenHandle, PHANDLE NewTokenHandle)
{
  NTSTATUS v4; // ecx
  void *v6; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF
  int TokenInformation; // [rsp+98h] [rbp+28h] BYREF
  ULONG ReturnLength; // [rsp+A0h] [rbp+30h] BYREF
  int v10; // [rsp+A8h] [rbp+38h] BYREF

  *NewTokenHandle = 0;
  ReturnLength = 0;
  v10 = 0;
  TokenInformation = 0;
  v6 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( v4 >= 0 )
  {
    if ( TokenInformation == 2 )
    {
LABEL_6:
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      return (unsigned int)NtDuplicateToken(TokenHandle, 0, &ObjectAttributes, 0, TokenPrimary, NewTokenHandle);
    }
    if ( TokenInformation == 1 )
    {
      v4 = NtQueryInformationToken(TokenHandle, TokenElevation, &v10, 4u, &ReturnLength);
      if ( v4 >= 0 && v10 )
        goto LABEL_6;
    }
    else
    {
      v4 = NtQueryInformationToken(TokenHandle, TokenLinkedToken, &v6, 8u, &ReturnLength);
      if ( v4 >= 0 )
        *NewTokenHandle = v6;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180029d68  push    rbp
0x180029d6a  push    rbx
0x180029d6b  push    rdi
0x180029d6c  mov     rbp, rsp
0x180029d6f  sub     rsp, 70h
0x180029d73  xorps   xmm0, xmm0
0x180029d76  mov     qword ptr [rdx], 0
0x180029d7d  mov     r9d, 4; TokenInformationLength
0x180029d83  mov     [rbp+arg_10], 0
0x180029d8a  mov     rdi, rdx
0x180029d8d  mov     [rbp+arg_18], 0
0x180029d94  lea     rax, [rbp+arg_10]
0x180029d98  mov     [rbp+TokenInformation], 0
0x180029d9f  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180029da3  mov     [rbp+var_40], 0
0x180029dab  lea     edx, [r9+0Eh]; TokenInformationClass
0x180029daf  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180029db4  mov     rbx, rcx
0x180029db7  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180029dbb  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180029dbf  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180029dc3  call    cs:__imp_NtQueryInformationToken
0x180029dca  nop     dword ptr [rax+rax+00h]
0x180029dcf  mov     ecx, eax
0x180029dd1  test    eax, eax
0x180029dd3  js      loc_180029E8D
0x180029dd9  cmp     [rbp+TokenInformation], 2
0x180029ddd  jz      short loc_180029E17
0x180029ddf  cmp     [rbp+TokenInformation], 1
0x180029de3  lea     rax, [rbp+arg_10]
0x180029de7  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180029dec  mov     rcx, rbx; TokenHandle
0x180029def  jnz     short loc_180029E66
0x180029df1  mov     r9d, 4; TokenInformationLength
0x180029df7  lea     r8, [rbp+arg_18]; TokenInformation
0x180029dfb  lea     edx, [r9+10h]; TokenInformationClass
0x180029dff  call    cs:__imp_NtQueryInformationToken
0x180029e06  nop     dword ptr [rax+rax+00h]
0x180029e0b  mov     ecx, eax
0x180029e0d  test    eax, eax
0x180029e0f  js      short loc_180029E8D
0x180029e11  cmp     [rbp+arg_18], 0
0x180029e15  jz      short loc_180029E8D
0x180029e17  xorps   xmm0, xmm0
0x180029e1a  mov     [rsp+70h+NewTokenHandle], rdi; NewTokenHandle
0x180029e1f  xor     r9d, r9d; EffectiveOnly
0x180029e22  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180029e29  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180029e2d  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180029e35  xor     edx, edx; DesiredAccess
0x180029e37  mov     [rbp+ObjectAttributes.Attributes], 0
0x180029e3e  mov     rcx, rbx; ExistingTokenHandle
0x180029e41  mov     [rbp+ObjectAttributes.ObjectName], 0
0x180029e49  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180029e4e  mov     dword ptr [rsp+70h+ReturnLength], 1; TokenType
0x180029e56  call    cs:__imp_NtDuplicateToken
0x180029e5d  nop     dword ptr [rax+rax+00h]
0x180029e62  mov     ecx, eax
0x180029e64  jmp     short loc_180029E8D
0x180029e66  mov     r9d, 8; TokenInformationLength
0x180029e6c  lea     r8, [rbp+var_40]; TokenInformation
0x180029e70  lea     edx, [r9+0Bh]; TokenInformationClass
0x180029e74  call    cs:__imp_NtQueryInformationToken
0x180029e7b  nop     dword ptr [rax+rax+00h]
0x180029e80  mov     ecx, eax
0x180029e82  test    eax, eax
0x180029e84  js      short loc_180029E8D
0x180029e86  mov     rax, [rbp+var_40]
0x180029e8a  mov     [rdi], rax
0x180029e8d  mov     eax, ecx
0x180029e8f  add     rsp, 70h
0x180029e93  pop     rdi
0x180029e94  pop     rbx
0x180029e95  pop     rbp
0x180029e96  retn
```
