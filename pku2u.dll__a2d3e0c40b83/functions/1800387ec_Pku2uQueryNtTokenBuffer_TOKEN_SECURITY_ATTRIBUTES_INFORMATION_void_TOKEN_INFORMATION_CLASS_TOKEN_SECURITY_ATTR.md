# Pku2uQueryNtTokenBuffer<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(void *,_TOKEN_INFORMATION_CLASS,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,ulong *)

- ea: `0x1800387ec`
- end: `0x1800388a6`
- name: `??$Pku2uQueryNtTokenBuffer@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAK@Z`
- size: `186`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180038e7c`

## callees

- `0x180018870`
- `0x1800387ec`
- `0x180038a30`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18003881e`
- `ntdll!NtQueryInformationToken` at `0x180038870`
- `ntdll!NtQueryInformationToken` at `0x18003881e`
- `ntdll!NtQueryInformationToken` at `0x180038870`

## pseudocode

```c
NTSTATUS __fastcall Pku2uQueryNtTokenBuffer<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(
        HANDLE TokenHandle,
        __int64 a2,
        _QWORD *a3,
        ULONG *a4)
{
  NTSTATUS result; // eax
  NTSTATUS v8; // edi
  ULONG v9; // eax
  PVOID v10[7]; // [rsp+30h] [rbp-38h] BYREF
  ULONG TokenInformationLength; // [rsp+78h] [rbp+10h] BYREF

  TokenInformationLength = 0;
  result = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
  if ( result == -2147483643 || result == -1073741789 )
  {
    v10[0] = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, TokenInformationLength);
    if ( v10[0] )
    {
      v8 = NtQueryInformationToken(
             TokenHandle,
             TokenSecurityAttributes,
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
0x1800387ec  mov     [rsp+TokenInformationLength], edx
0x1800387f0  push    rbx
0x1800387f1  push    rsi
0x1800387f2  push    rdi
0x1800387f3  push    r14
0x1800387f5  sub     rsp, 48h
0x1800387f9  mov     rsi, r9
0x1800387fc  mov     [rsp+68h+TokenInformationLength], 0
0x180038804  xor     r9d, r9d; TokenInformationLength
0x180038807  lea     rax, [rsp+68h+TokenInformationLength]
0x18003880c  mov     r14, r8
0x18003880f  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180038814  xor     r8d, r8d; TokenInformation
0x180038817  mov     rdi, rcx
0x18003881a  lea     edx, [r9+27h]; TokenInformationClass
0x18003881e  call    cs:__imp_NtQueryInformationToken
0x180038824  cmp     eax, 80000005h
0x180038829  jz      short loc_180038832
0x18003882b  cmp     eax, 0C0000023h
0x180038830  jnz     short loc_18003889C
0x180038832  mov     edx, [rsp+68h+TokenInformationLength]; unsigned __int64
0x180038836  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18003883d  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180038842  mov     [rsp+68h+var_38], rax
0x180038847  mov     rbx, rax
0x18003884a  test    rax, rax
0x18003884d  jnz     short loc_180038856
0x18003884f  mov     edi, 0C0000017h
0x180038854  jmp     short loc_180038890
0x180038856  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x18003885b  lea     rax, [rsp+68h+TokenInformationLength]
0x180038860  mov     r8, rbx; TokenInformation
0x180038863  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180038868  mov     edx, 27h ; '''; TokenInformationClass
0x18003886d  mov     rcx, rdi; TokenHandle
0x180038870  call    cs:__imp_NtQueryInformationToken
0x180038876  mov     edi, eax
0x180038878  test    eax, eax
0x18003887a  js      short loc_180038890
0x18003887c  mov     eax, [rsp+68h+TokenInformationLength]
0x180038880  xor     edi, edi
0x180038882  mov     [r14], rbx
0x180038885  mov     [rsi], eax
0x180038887  mov     [rsp+68h+var_38], 0
0x180038890  lea     rcx, [rsp+68h+var_38]
0x180038895  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@$$A6AXPEAX@Z$1?Pku2uFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(void)
0x18003889a  mov     eax, edi
0x18003889c  add     rsp, 48h
0x1800388a0  pop     r14
0x1800388a2  pop     rdi
0x1800388a3  pop     rsi
0x1800388a4  pop     rbx
0x1800388a5  retn
```
