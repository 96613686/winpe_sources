# Pku2uQueryNtTokenBuffer<_TOKEN_PRIVILEGES>(void *,_TOKEN_INFORMATION_CLASS,_TOKEN_PRIVILEGES * *,ulong *)

- ea: `0x18003872c`
- end: `0x1800387e6`
- name: `??$Pku2uQueryNtTokenBuffer@U_TOKEN_PRIVILEGES@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_PRIVILEGES@@PEAK@Z`
- size: `186`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180038e7c`

## callees

- `0x180018870`
- `0x18003872c`
- `0x180038a30`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18003875e`
- `ntdll!NtQueryInformationToken` at `0x1800387b0`
- `ntdll!NtQueryInformationToken` at `0x18003875e`
- `ntdll!NtQueryInformationToken` at `0x1800387b0`

## pseudocode

```c
NTSTATUS __fastcall Pku2uQueryNtTokenBuffer<_TOKEN_PRIVILEGES>(HANDLE TokenHandle, __int64 a2, _QWORD *a3, ULONG *a4)
{
  NTSTATUS result; // eax
  NTSTATUS v8; // edi
  ULONG v9; // eax
  PVOID v10[7]; // [rsp+30h] [rbp-38h] BYREF
  ULONG TokenInformationLength; // [rsp+78h] [rbp+10h] BYREF

  TokenInformationLength = 0;
  result = NtQueryInformationToken(TokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength);
  if ( result == -2147483643 || result == -1073741789 )
  {
    v10[0] = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, TokenInformationLength);
    if ( v10[0] )
    {
      v8 = NtQueryInformationToken(
             TokenHandle,
             TokenPrivileges,
             v10[0],
             TokenInformationLength,
             &TokenInformationLength);
      if ( v8 >= 0 )
      {
        v9 = TokenInformationLength;
        v8 = 0;
        *a3 = v10[0];
        *a4 = v9;
        v10[0] = 0;
      }
    }
    else
    {
      v8 = -1073741801;
    }
    wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(v10);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18003872c  mov     [rsp+TokenInformationLength], edx
0x180038730  push    rbx
0x180038731  push    rsi
0x180038732  push    rdi
0x180038733  push    r14
0x180038735  sub     rsp, 48h
0x180038739  mov     rsi, r9
0x18003873c  mov     [rsp+68h+TokenInformationLength], 0
0x180038744  xor     r9d, r9d; TokenInformationLength
0x180038747  lea     rax, [rsp+68h+TokenInformationLength]
0x18003874c  mov     r14, r8
0x18003874f  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180038754  xor     r8d, r8d; TokenInformation
0x180038757  mov     rdi, rcx
0x18003875a  lea     edx, [r9+3]; TokenInformationClass
0x18003875e  call    cs:__imp_NtQueryInformationToken
0x180038764  cmp     eax, 80000005h
0x180038769  jz      short loc_180038772
0x18003876b  cmp     eax, 0C0000023h
0x180038770  jnz     short loc_1800387DC
0x180038772  mov     edx, [rsp+68h+TokenInformationLength]; unsigned __int64
0x180038776  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18003877d  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180038782  mov     [rsp+68h+var_38], rax
0x180038787  mov     rbx, rax
0x18003878a  test    rax, rax
0x18003878d  jnz     short loc_180038796
0x18003878f  mov     edi, 0C0000017h
0x180038794  jmp     short loc_1800387D0
0x180038796  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x18003879b  lea     rax, [rsp+68h+TokenInformationLength]
0x1800387a0  mov     r8, rbx; TokenInformation
0x1800387a3  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800387a8  mov     edx, 3; TokenInformationClass
0x1800387ad  mov     rcx, rdi; TokenHandle
0x1800387b0  call    cs:__imp_NtQueryInformationToken
0x1800387b6  mov     edi, eax
0x1800387b8  test    eax, eax
0x1800387ba  js      short loc_1800387D0
0x1800387bc  mov     eax, [rsp+68h+TokenInformationLength]
0x1800387c0  xor     edi, edi
0x1800387c2  mov     [r14], rbx
0x1800387c5  mov     [rsi], eax
0x1800387c7  mov     [rsp+68h+var_38], 0
0x1800387d0  lea     rcx, [rsp+68h+var_38]
0x1800387d5  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@$$A6AXPEAX@Z$1?Pku2uFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(void)
0x1800387da  mov     eax, edi
0x1800387dc  add     rsp, 48h
0x1800387e0  pop     r14
0x1800387e2  pop     rdi
0x1800387e3  pop     rsi
0x1800387e4  pop     rbx
0x1800387e5  retn
```
