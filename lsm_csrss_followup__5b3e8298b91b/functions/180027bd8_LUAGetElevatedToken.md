# LUAGetElevatedToken

- ea: `0x180027bd8`
- end: `0x180027cef`
- name: `LUAGetElevatedToken`
- size: `279`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d3b4`
- `0x180054fd0`

## callees

- `0x180027bd8`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x180027cba`
- `ntdll!NtDuplicateToken` at `0x180027cba`
- `ntdll!NtQueryInformationToken` at `0x180027c33`
- `ntdll!NtQueryInformationToken` at `0x180027c69`
- `ntdll!NtQueryInformationToken` at `0x180027cd2`
- `ntdll!NtQueryInformationToken` at `0x180027c33`
- `ntdll!NtQueryInformationToken` at `0x180027c69`
- `ntdll!NtQueryInformationToken` at `0x180027cd2`

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
0x180027bd8  push    rbp
0x180027bda  push    rbx
0x180027bdb  push    rdi
0x180027bdc  mov     rbp, rsp
0x180027bdf  sub     rsp, 70h
0x180027be3  xorps   xmm0, xmm0
0x180027be6  mov     qword ptr [rdx], 0
0x180027bed  mov     r9d, 4; TokenInformationLength
0x180027bf3  mov     [rbp+arg_10], 0
0x180027bfa  mov     rdi, rdx
0x180027bfd  mov     [rbp+arg_18], 0
0x180027c04  lea     rax, [rbp+arg_10]
0x180027c08  mov     [rbp+TokenInformation], 0
0x180027c0f  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180027c13  mov     [rbp+var_40], 0
0x180027c1b  lea     edx, [r9+0Eh]; TokenInformationClass
0x180027c1f  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180027c24  mov     rbx, rcx
0x180027c27  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180027c2b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180027c2f  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180027c33  call    cs:__imp_NtQueryInformationToken
0x180027c39  mov     ecx, eax
0x180027c3b  test    eax, eax
0x180027c3d  js      loc_180027CE5
0x180027c43  cmp     [rbp+TokenInformation], 2
0x180027c47  jz      short loc_180027C7B
0x180027c49  cmp     [rbp+TokenInformation], 1
0x180027c4d  lea     rax, [rbp+arg_10]
0x180027c51  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180027c56  mov     rcx, rbx; TokenHandle
0x180027c59  jnz     short loc_180027CC4
0x180027c5b  mov     r9d, 4; TokenInformationLength
0x180027c61  lea     r8, [rbp+arg_18]; TokenInformation
0x180027c65  lea     edx, [r9+10h]; TokenInformationClass
0x180027c69  call    cs:__imp_NtQueryInformationToken
0x180027c6f  mov     ecx, eax
0x180027c71  test    eax, eax
0x180027c73  js      short loc_180027CE5
0x180027c75  cmp     [rbp+arg_18], 0
0x180027c79  jz      short loc_180027CE5
0x180027c7b  xorps   xmm0, xmm0
0x180027c7e  mov     [rsp+70h+NewTokenHandle], rdi; NewTokenHandle
0x180027c83  xor     r9d, r9d; EffectiveOnly
0x180027c86  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180027c8d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180027c91  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180027c99  xor     edx, edx; DesiredAccess
0x180027c9b  mov     [rbp+ObjectAttributes.Attributes], 0
0x180027ca2  mov     rcx, rbx; ExistingTokenHandle
0x180027ca5  mov     [rbp+ObjectAttributes.ObjectName], 0
0x180027cad  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180027cb2  mov     dword ptr [rsp+70h+ReturnLength], 1; TokenType
0x180027cba  call    cs:__imp_NtDuplicateToken
0x180027cc0  mov     ecx, eax
0x180027cc2  jmp     short loc_180027CE5
0x180027cc4  mov     r9d, 8; TokenInformationLength
0x180027cca  lea     r8, [rbp+var_40]; TokenInformation
0x180027cce  lea     edx, [r9+0Bh]; TokenInformationClass
0x180027cd2  call    cs:__imp_NtQueryInformationToken
0x180027cd8  mov     ecx, eax
0x180027cda  test    eax, eax
0x180027cdc  js      short loc_180027CE5
0x180027cde  mov     rax, [rbp+var_40]
0x180027ce2  mov     [rdi], rax
0x180027ce5  mov     eax, ecx
0x180027ce7  add     rsp, 70h
0x180027ceb  pop     rdi
0x180027cec  pop     rbx
0x180027ced  pop     rbp
0x180027cee  retn
```
