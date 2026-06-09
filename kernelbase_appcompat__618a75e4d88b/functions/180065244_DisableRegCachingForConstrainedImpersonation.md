# DisableRegCachingForConstrainedImpersonation

- ea: `0x180065244`
- end: `0x1800652b3`
- name: `DisableRegCachingForConstrainedImpersonation`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180064f90`

## callees

- `0x180065244`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x18019b6c7`
- `ntdll!RtlInitializeSid` at `0x18019b6c7`
- `ntdll!RtlSubAuthoritySid` at `0x18019b6da`
- `ntdll!RtlSubAuthoritySid` at `0x18019b6f6`
- `ntdll!RtlSubAuthoritySid` at `0x18019b6da`
- `ntdll!RtlSubAuthoritySid` at `0x18019b6f6`
- `ntdll!RtlInitUnicodeString` at `0x18019b63a`
- `ntdll!RtlInitUnicodeString` at `0x18019b63a`
- `ntdll!RtlIsMultiSessionSku` at `0x180065281`
- `ntdll!RtlIsMultiSessionSku` at `0x180065281`
- `ntdll!NtQueryInformationToken` at `0x18019b61a`
- `ntdll!NtQueryInformationToken` at `0x18019b61a`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18019b698`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18019b718`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18019b698`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18019b718`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18019b678`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18019b678`
- `ntdll!RtlCapabilityCheck` at `0x18019b659`
- `ntdll!RtlCapabilityCheck` at `0x18019b659`

## string_xrefs

- `0x18019b62e`: `constrainedImpersonation`

## pseudocode

```c
NTSTATUS DisableRegCachingForConstrainedImpersonation()
{
  NTSTATUS result; // eax
  _BYTE v1[4]; // [rsp+30h] [rbp-D0h] BYREF
  int TokenInformation; // [rsp+34h] [rbp-CCh] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Sid[24]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v7[80]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v8[80]; // [rsp+C0h] [rbp-40h] BYREF

  v1[0] = 0;
  DestinationString = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  result = RtlIsMultiSessionSku();
  if ( !(_BYTE)result )
  {
    v1[0] = 0;
    result = NtQueryInformationToken(
               (HANDLE)0xFFFFFFFFFFFFFFFCLL,
               TokenIsAppContainer,
               &TokenInformation,
               4u,
               &ReturnLength);
    if ( result >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"constrainedImpersonation");
      if ( TokenInformation )
      {
        RtlCapabilityCheck(0, &DestinationString, v1);
      }
      else
      {
        if ( (int)RtlDeriveCapabilitySidsFromName(&DestinationString, v7, v8) >= 0 )
          RtlCheckTokenMembershipEx(-4, v7, 0, v1);
        if ( !v1[0] )
        {
          *(_DWORD *)IdentifierAuthority.Value = 0;
          *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
          RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
          *RtlSubAuthoritySid(Sid, 0) = 32;
          *RtlSubAuthoritySid(Sid, 1u) = 581;
          RtlCheckTokenMembershipEx(-4, Sid, 0, v1);
        }
      }
      result = v1[0];
      g_DisableCachingWhileImpersonated = v1[0];
    }
  }
  return result;
}

```

## disassembly

```asm
0x180065244  mov     [rsp-8+arg_0], rdi
0x180065249  push    rbp
0x18006524a  lea     rbp, [rsp-20h]
0x18006524f  sub     rsp, 120h
0x180065256  mov     rax, cs:__security_cookie
0x18006525d  xor     rax, rsp
0x180065260  mov     [rbp+20h+var_10], rax
0x180065264  xorps   xmm0, xmm0
0x180065267  mov     [rsp+120h+var_F0], 0
0x18006526c  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x180065271  mov     [rsp+120h+TokenInformation], 0
0x180065279  mov     [rsp+120h+var_E8], 0
0x180065281  call    cs:__imp_RtlIsMultiSessionSku
0x180065288  nop     dword ptr [rax+rax+00h]
0x18006528d  test    al, al
0x18006528f  jz      loc_18019B5F2
0x180065295  mov     rcx, [rbp+20h+var_10]
0x180065299  xor     rcx, rsp; StackCookie
0x18006529c  call    __security_check_cookie
0x1800652a1  mov     rdi, [rsp+120h+arg_0]
0x1800652a9  add     rsp, 120h
0x1800652b0  pop     rbp
0x1800652b1  retn
0x18019b5f2  mov     r9d, 4; TokenInformationLength
0x18019b5f8  mov     [rsp+120h+var_F0], 0
0x18019b5fd  lea     rax, [rsp+120h+var_E8]
0x18019b602  mov     rdi, 0FFFFFFFFFFFFFFFCh
0x18019b609  lea     r8, [rsp+120h+TokenInformation]; TokenInformation
0x18019b60e  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18019b613  mov     rcx, rdi; TokenHandle
0x18019b616  lea     edx, [r9+19h]; TokenInformationClass
0x18019b61a  call    cs:__imp_NtQueryInformationToken
0x18019b621  nop     dword ptr [rax+rax+00h]
0x18019b626  test    eax, eax
0x18019b628  js      loc_180065295
0x18019b62e  lea     rdx, aConstrainedimp; "constrainedImpersonation"
0x18019b635  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x18019b63a  call    cs:__imp_RtlInitUnicodeString
0x18019b641  nop     dword ptr [rax+rax+00h]
0x18019b646  cmp     [rsp+120h+TokenInformation], 0
0x18019b64b  jz      short loc_18019B66A
0x18019b64d  lea     r8, [rsp+120h+var_F0]
0x18019b652  xor     ecx, ecx
0x18019b654  lea     rdx, [rsp+120h+DestinationString]
0x18019b659  call    cs:__imp_RtlCapabilityCheck
0x18019b660  nop     dword ptr [rax+rax+00h]
0x18019b665  jmp     loc_18019B724
0x18019b66a  lea     r8, [rbp+20h+var_60]
0x18019b66e  lea     rdx, [rsp+120h+var_B0]
0x18019b673  lea     rcx, [rsp+120h+DestinationString]
0x18019b678  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18019b67f  nop     dword ptr [rax+rax+00h]
0x18019b684  test    eax, eax
0x18019b686  js      short loc_18019B6A4
0x18019b688  lea     r9, [rsp+120h+var_F0]
0x18019b68d  xor     r8d, r8d
0x18019b690  lea     rdx, [rsp+120h+var_B0]
0x18019b695  mov     rcx, rdi
0x18019b698  call    cs:__imp_RtlCheckTokenMembershipEx
0x18019b69f  nop     dword ptr [rax+rax+00h]
0x18019b6a4  cmp     [rsp+120h+var_F0], 0
0x18019b6a9  jnz     short loc_18019B724
0x18019b6ab  mov     r8b, 2; SubAuthorityCount
0x18019b6ae  mov     dword ptr [rsp+120h+IdentifierAuthority.Value], 0
0x18019b6b6  lea     rdx, [rsp+120h+IdentifierAuthority]; IdentifierAuthority
0x18019b6bb  mov     word ptr [rsp+120h+IdentifierAuthority.Value+4], 500h
0x18019b6c2  lea     rcx, [rsp+120h+Sid]; Sid
0x18019b6c7  call    cs:__imp_RtlInitializeSid
0x18019b6ce  nop     dword ptr [rax+rax+00h]
0x18019b6d3  xor     edx, edx; SubAuthority
0x18019b6d5  lea     rcx, [rsp+120h+Sid]; Sid
0x18019b6da  call    cs:__imp_RtlSubAuthoritySid
0x18019b6e1  nop     dword ptr [rax+rax+00h]
0x18019b6e6  mov     edx, 1; SubAuthority
0x18019b6eb  lea     rcx, [rsp+120h+Sid]; Sid
0x18019b6f0  mov     dword ptr [rax], 20h ; ' '
0x18019b6f6  call    cs:__imp_RtlSubAuthoritySid
0x18019b6fd  nop     dword ptr [rax+rax+00h]
0x18019b702  lea     r9, [rsp+120h+var_F0]
0x18019b707  xor     r8d, r8d
0x18019b70a  lea     rdx, [rsp+120h+Sid]
0x18019b70f  mov     rcx, rdi
0x18019b712  mov     dword ptr [rax], 245h
0x18019b718  call    cs:__imp_RtlCheckTokenMembershipEx
0x18019b71f  nop     dword ptr [rax+rax+00h]
0x18019b724  movzx   eax, [rsp+120h+var_F0]
0x18019b729  mov     cs:g_DisableCachingWhileImpersonated, eax
0x18019b72f  jmp     loc_180065295
```
