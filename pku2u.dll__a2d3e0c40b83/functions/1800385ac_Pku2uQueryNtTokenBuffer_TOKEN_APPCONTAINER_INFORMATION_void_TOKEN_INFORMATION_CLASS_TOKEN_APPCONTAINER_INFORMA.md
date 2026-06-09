# Pku2uQueryNtTokenBuffer<_TOKEN_APPCONTAINER_INFORMATION>(void *,_TOKEN_INFORMATION_CLASS,_TOKEN_APPCONTAINER_INFORMATION * *,ulong *)

- ea: `0x1800385ac`
- end: `0x180038666`
- name: `??$Pku2uQueryNtTokenBuffer@U_TOKEN_APPCONTAINER_INFORMATION@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_APPCONTAINER_INFORMATION@@PEAK@Z`
- size: `186`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800394b8`

## callees

- `0x180018870`
- `0x1800385ac`
- `0x180038a30`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800385de`
- `ntdll!NtQueryInformationToken` at `0x180038630`
- `ntdll!NtQueryInformationToken` at `0x1800385de`
- `ntdll!NtQueryInformationToken` at `0x180038630`

## pseudocode

```c
NTSTATUS __fastcall Pku2uQueryNtTokenBuffer<_TOKEN_APPCONTAINER_INFORMATION>(
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
  result = NtQueryInformationToken(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength);
  if ( result == -2147483643 || result == -1073741789 )
  {
    v10[0] = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, TokenInformationLength);
    if ( v10[0] )
    {
      v8 = NtQueryInformationToken(
             TokenHandle,
             TokenAppContainerSid,
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
0x1800385ac  mov     [rsp+TokenInformationLength], edx
0x1800385b0  push    rbx
0x1800385b1  push    rsi
0x1800385b2  push    rdi
0x1800385b3  push    r14
0x1800385b5  sub     rsp, 48h
0x1800385b9  mov     rsi, r9
0x1800385bc  mov     [rsp+68h+TokenInformationLength], 0
0x1800385c4  xor     r9d, r9d; TokenInformationLength
0x1800385c7  lea     rax, [rsp+68h+TokenInformationLength]
0x1800385cc  mov     r14, r8
0x1800385cf  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800385d4  xor     r8d, r8d; TokenInformation
0x1800385d7  mov     rdi, rcx
0x1800385da  lea     edx, [r9+1Fh]; TokenInformationClass
0x1800385de  call    cs:__imp_NtQueryInformationToken
0x1800385e4  cmp     eax, 80000005h
0x1800385e9  jz      short loc_1800385F2
0x1800385eb  cmp     eax, 0C0000023h
0x1800385f0  jnz     short loc_18003865C
0x1800385f2  mov     edx, [rsp+68h+TokenInformationLength]; unsigned __int64
0x1800385f6  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x1800385fd  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180038602  mov     [rsp+68h+var_38], rax
0x180038607  mov     rbx, rax
0x18003860a  test    rax, rax
0x18003860d  jnz     short loc_180038616
0x18003860f  mov     edi, 0C0000017h
0x180038614  jmp     short loc_180038650
0x180038616  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x18003861b  lea     rax, [rsp+68h+TokenInformationLength]
0x180038620  mov     r8, rbx; TokenInformation
0x180038623  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180038628  mov     edx, 1Fh; TokenInformationClass
0x18003862d  mov     rcx, rdi; TokenHandle
0x180038630  call    cs:__imp_NtQueryInformationToken
0x180038636  mov     edi, eax
0x180038638  test    eax, eax
0x18003863a  js      short loc_180038650
0x18003863c  mov     eax, [rsp+68h+TokenInformationLength]
0x180038640  xor     edi, edi
0x180038642  mov     [r14], rbx
0x180038645  mov     [rsi], eax
0x180038647  mov     [rsp+68h+var_38], 0
0x180038650  lea     rcx, [rsp+68h+var_38]
0x180038655  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@$$A6AXPEAX@Z$1?Pku2uFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(void)
0x18003865a  mov     eax, edi
0x18003865c  add     rsp, 48h
0x180038660  pop     r14
0x180038662  pop     rdi
0x180038663  pop     rsi
0x180038664  pop     rbx
0x180038665  retn
```
