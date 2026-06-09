# Pku2uQueryNtTokenBuffer<_TOKEN_GROUPS>(void *,_TOKEN_INFORMATION_CLASS,_TOKEN_GROUPS * *,ulong *)

- ea: `0x18003866c`
- end: `0x180038726`
- name: `??$Pku2uQueryNtTokenBuffer@U_TOKEN_GROUPS@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_GROUPS@@PEAK@Z`
- size: `186`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800394b8`

## callees

- `0x180018870`
- `0x18003866c`
- `0x180038a30`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18003869e`
- `ntdll!NtQueryInformationToken` at `0x1800386f0`
- `ntdll!NtQueryInformationToken` at `0x18003869e`
- `ntdll!NtQueryInformationToken` at `0x1800386f0`

## pseudocode

```c
NTSTATUS __fastcall Pku2uQueryNtTokenBuffer<_TOKEN_GROUPS>(HANDLE TokenHandle, __int64 a2, _QWORD *a3, ULONG *a4)
{
  NTSTATUS result; // eax
  NTSTATUS v8; // edi
  ULONG v9; // eax
  PVOID v10[7]; // [rsp+30h] [rbp-38h] BYREF
  ULONG TokenInformationLength; // [rsp+78h] [rbp+10h] BYREF

  TokenInformationLength = 0;
  result = NtQueryInformationToken(TokenHandle, TokenCapabilities, 0, 0, &TokenInformationLength);
  if ( result == -2147483643 || result == -1073741789 )
  {
    v10[0] = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, TokenInformationLength);
    if ( v10[0] )
    {
      v8 = NtQueryInformationToken(
             TokenHandle,
             TokenCapabilities,
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
0x18003866c  mov     [rsp+TokenInformationLength], edx
0x180038670  push    rbx
0x180038671  push    rsi
0x180038672  push    rdi
0x180038673  push    r14
0x180038675  sub     rsp, 48h
0x180038679  mov     rsi, r9
0x18003867c  mov     [rsp+68h+TokenInformationLength], 0
0x180038684  xor     r9d, r9d; TokenInformationLength
0x180038687  lea     rax, [rsp+68h+TokenInformationLength]
0x18003868c  mov     r14, r8
0x18003868f  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180038694  xor     r8d, r8d; TokenInformation
0x180038697  mov     rdi, rcx
0x18003869a  lea     edx, [r9+1Eh]; TokenInformationClass
0x18003869e  call    cs:__imp_NtQueryInformationToken
0x1800386a4  cmp     eax, 80000005h
0x1800386a9  jz      short loc_1800386B2
0x1800386ab  cmp     eax, 0C0000023h
0x1800386b0  jnz     short loc_18003871C
0x1800386b2  mov     edx, [rsp+68h+TokenInformationLength]; unsigned __int64
0x1800386b6  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x1800386bd  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x1800386c2  mov     [rsp+68h+var_38], rax
0x1800386c7  mov     rbx, rax
0x1800386ca  test    rax, rax
0x1800386cd  jnz     short loc_1800386D6
0x1800386cf  mov     edi, 0C0000017h
0x1800386d4  jmp     short loc_180038710
0x1800386d6  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x1800386db  lea     rax, [rsp+68h+TokenInformationLength]
0x1800386e0  mov     r8, rbx; TokenInformation
0x1800386e3  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800386e8  mov     edx, 1Eh; TokenInformationClass
0x1800386ed  mov     rcx, rdi; TokenHandle
0x1800386f0  call    cs:__imp_NtQueryInformationToken
0x1800386f6  mov     edi, eax
0x1800386f8  test    eax, eax
0x1800386fa  js      short loc_180038710
0x1800386fc  mov     eax, [rsp+68h+TokenInformationLength]
0x180038700  xor     edi, edi
0x180038702  mov     [r14], rbx
0x180038705  mov     [rsi], eax
0x180038707  mov     [rsp+68h+var_38], 0
0x180038710  lea     rcx, [rsp+68h+var_38]
0x180038715  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@$$A6AXPEAX@Z$1?Pku2uFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(void)
0x18003871a  mov     eax, edi
0x18003871c  add     rsp, 48h
0x180038720  pop     r14
0x180038722  pop     rdi
0x180038723  pop     rsi
0x180038724  pop     rbx
0x180038725  retn
```
