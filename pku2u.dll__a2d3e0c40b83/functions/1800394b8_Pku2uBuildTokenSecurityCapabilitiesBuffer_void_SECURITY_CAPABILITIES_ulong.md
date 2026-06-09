# Pku2uBuildTokenSecurityCapabilitiesBuffer(void *,_SECURITY_CAPABILITIES * *,ulong *)

- ea: `0x1800394b8`
- end: `0x1800396b6`
- name: `?Pku2uBuildTokenSecurityCapabilitiesBuffer@@YAJPEAXPEAPEAU_SECURITY_CAPABILITIES@@PEAK@Z`
- size: `510`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _SECURITY_CAPABILITIES **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180038e7c`

## callees

- `0x180018870`
- `0x1800385ac`
- `0x18003866c`
- `0x180038a30`
- `0x1800394b8`
- `0x180044d98`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800395cb`
- `ntdll!RtlCopySid` at `0x18003963a`
- `ntdll!RtlCopySid` at `0x1800395cb`
- `ntdll!RtlCopySid` at `0x18003963a`
- `ntdll!RtlLengthSid` at `0x18003953f`
- `ntdll!RtlLengthSid` at `0x18003955f`
- `ntdll!RtlLengthSid` at `0x1800395bb`
- `ntdll!RtlLengthSid` at `0x180039626`
- `ntdll!RtlLengthSid` at `0x18003953f`
- `ntdll!RtlLengthSid` at `0x18003955f`
- `ntdll!RtlLengthSid` at `0x1800395bb`
- `ntdll!RtlLengthSid` at `0x180039626`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Pku2uBuildTokenSecurityCapabilitiesBuffer(
        HANDLE TokenHandle,
        struct _SECURITY_CAPABILITIES **a2,
        unsigned int *a3)
{
  unsigned int *v3; // rsi
  int NtToken; // ebx
  unsigned int *v6; // r13
  unsigned int v7; // r12d
  unsigned int v8; // edi
  struct _SECURITY_CAPABILITIES *v9; // rax
  struct _SECURITY_CAPABILITIES *v10; // r15
  struct _SID_AND_ATTRIBUTES *v11; // r14
  __int64 v12; // rax
  unsigned int v13; // r12d
  __int64 v14; // rbx
  ULONG v15; // eax
  __int64 v16; // rdi
  struct _SECURITY_CAPABILITIES *v18; // [rsp+28h] [rbp-18h] BYREF
  __int64 v19; // [rsp+30h] [rbp-10h] BYREF
  unsigned int *v20; // [rsp+38h] [rbp-8h] BYREF
  int v23; // [rsp+98h] [rbp+58h]

  v3 = a3;
  v19 = 0;
  NtToken = Pku2uQueryNtTokenBuffer<_TOKEN_APPCONTAINER_INFORMATION>(TokenHandle);
  if ( NtToken >= 0 )
  {
    v20 = 0;
    NtToken = Pku2uQueryNtTokenBuffer<_TOKEN_GROUPS>(TokenHandle);
    if ( NtToken >= 0 )
    {
      v6 = v20;
      v7 = 24;
      v23 = 24;
      if ( *v20 )
      {
        v8 = 0;
        do
          v7 += RtlLengthSid(*(PSID *)&v20[4 * v8++ + 2]) + 16;
        while ( v8 < *v20 );
        v23 = v7;
      }
      v9 = (struct _SECURITY_CAPABILITIES *)basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, v7);
      v10 = v9;
      v18 = v9;
      if ( v9 )
      {
        v11 = (struct _SID_AND_ATTRIBUTES *)&v9[1];
        v12 = *v20;
        if ( (_DWORD)v12 )
        {
          v10->CapabilityCount = v12;
          v10->Capabilities = v11;
          v11 += v12;
          if ( *v6 )
          {
            v13 = 0;
            do
            {
              v14 = 16LL * v13;
              v15 = RtlLengthSid(&v6[(unsigned __int64)v14 / 4 + 2]);
              v16 = v15;
              RtlCopySid(v15, v11, &v6[(unsigned __int64)v14 / 4 + 2]);
              v10->Capabilities[(unsigned __int64)v14 / 0x10].Sid = v11;
              v11 = (struct _SID_AND_ATTRIBUTES *)((char *)v11 + v16);
              ++v13;
            }
            while ( v13 < *v6 );
            v7 = v23;
            v3 = a3;
          }
        }
        if ( v11 != (struct _SID_AND_ATTRIBUTES *)((char *)v10 + v7) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v18 = 0;
        *a2 = v10;
        *v3 = v7;
        wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(&v18);
        NtToken = 0;
      }
      else
      {
        wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(&v18);
        NtToken = -1073741801;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(&v20);
  }
  wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(&v19);
  return (unsigned int)NtToken;
}

```

## disassembly

```asm
0x1800394b8  mov     [rsp-38h+arg_0], rbx
0x1800394bd  mov     [rsp-38h+arg_10], r8
0x1800394c2  mov     [rsp-38h+arg_8], rdx
0x1800394c7  push    rbp
0x1800394c8  push    rsi
0x1800394c9  push    rdi
0x1800394ca  push    r12
0x1800394cc  push    r13
0x1800394ce  push    r14
0x1800394d0  push    r15
0x1800394d2  mov     rbp, rsp
0x1800394d5  sub     rsp, 40h
0x1800394d9  mov     rsi, r8
0x1800394dc  mov     rdi, rcx
0x1800394df  mov     [rbp+var_10], 0
0x1800394e7  lea     r9, [rbp+arg_18]
0x1800394eb  lea     r8, [rbp+var_10]
0x1800394ef  call    ??$Pku2uQueryNtTokenBuffer@U_TOKEN_APPCONTAINER_INFORMATION@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_APPCONTAINER_INFORMATION@@PEAK@Z; Pku2uQueryNtTokenBuffer<_TOKEN_APPCONTAINER_INFORMATION>(void *,_TOKEN_INFORMATION_CLASS,_TOKEN_APPCONTAINER_INFORMATION * *,ulong *)
0x1800394f4  mov     ebx, eax
0x1800394f6  test    eax, eax
0x1800394f8  js      loc_180039693
0x1800394fe  mov     [rbp+var_8], 0
0x180039506  lea     r9, [rbp+arg_18]
0x18003950a  lea     r8, [rbp+var_8]
0x18003950e  mov     rcx, rdi; TokenHandle
0x180039511  call    ??$Pku2uQueryNtTokenBuffer@U_TOKEN_GROUPS@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_GROUPS@@PEAK@Z; Pku2uQueryNtTokenBuffer<_TOKEN_GROUPS>(void *,_TOKEN_INFORMATION_CLASS,_TOKEN_GROUPS * *,ulong *)
0x180039516  mov     ebx, eax
0x180039518  test    eax, eax
0x18003951a  js      loc_180039689
0x180039520  mov     rbx, [rbp+var_10]
0x180039524  mov     r13, [rbp+var_8]
0x180039528  mov     r12d, 18h
0x18003952e  mov     [rbp+arg_18], r12d
0x180039532  test    rbx, rbx
0x180039535  jz      short loc_18003954C
0x180039537  mov     rcx, [rbx]; Sid
0x18003953a  test    rcx, rcx
0x18003953d  jz      short loc_18003954C
0x18003953f  call    cs:__imp_RtlLengthSid
0x180039545  add     r12d, eax
0x180039548  mov     [rbp+arg_18], r12d
0x18003954c  cmp     dword ptr [r13+0], 0
0x180039551  jbe     short loc_180039578
0x180039553  xor     edi, edi
0x180039555  mov     ecx, edi
0x180039557  add     rcx, rcx
0x18003955a  mov     rcx, [r13+rcx*8+8]; Sid
0x18003955f  call    cs:__imp_RtlLengthSid
0x180039565  add     r12d, 10h
0x180039569  add     r12d, eax
0x18003956c  inc     edi
0x18003956e  cmp     edi, [r13+0]
0x180039572  jb      short loc_180039555
0x180039574  mov     [rbp+arg_18], r12d
0x180039578  mov     edx, r12d; unsigned __int64
0x18003957b  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180039582  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180039587  mov     r15, rax
0x18003958a  mov     [rbp+var_18], rax
0x18003958e  test    rax, rax
0x180039591  jnz     short loc_1800395A6
0x180039593  lea     rcx, [rbp+var_18]
0x180039597  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@$$A6AXPEAX@Z$1?Pku2uFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(void)
0x18003959c  mov     ebx, 0C0000017h
0x1800395a1  jmp     loc_180039689
0x1800395a6  lea     r14, [rax+18h]
0x1800395aa  test    rbx, rbx
0x1800395ad  jz      short loc_1800395E8
0x1800395af  cmp     qword ptr [rbx], 0
0x1800395b3  jz      short loc_1800395E8
0x1800395b5  mov     [rax], r14
0x1800395b8  mov     rcx, [rbx]; Sid
0x1800395bb  call    cs:__imp_RtlLengthSid
0x1800395c1  mov     edi, eax
0x1800395c3  mov     r8, [rbx]; SourceSid
0x1800395c6  mov     rdx, r14; DestinationSid
0x1800395c9  mov     ecx, eax; DestinationSidLength
0x1800395cb  call    cs:__imp_RtlCopySid
0x1800395d1  mov     ebx, eax
0x1800395d3  test    eax, eax
0x1800395d5  jns     short loc_1800395E5
0x1800395d7  lea     rcx, [rbp+var_18]
0x1800395db  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@$$A6AXPEAX@Z$1?Pku2uFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(void)
0x1800395e0  jmp     loc_180039689
0x1800395e5  add     r14, rdi
0x1800395e8  mov     eax, [r13+0]
0x1800395ec  test    eax, eax
0x1800395ee  jz      short loc_18003965C
0x1800395f0  mov     [r15+10h], eax
0x1800395f4  mov     [r15+8], r14
0x1800395f8  shl     rax, 4
0x1800395fc  add     r14, rax
0x1800395ff  mov     [rbp+var_20], 0
0x180039606  cmp     dword ptr [r13+0], 0
0x18003960b  jbe     short loc_18003965C
0x18003960d  mov     r12d, [rbp+var_20]
0x180039611  mov     esi, r12d
0x180039614  add     rsi, rsi
0x180039617  lea     rbx, ds:0[rsi*8]
0x18003961f  lea     rcx, [r13+8]
0x180039623  add     rcx, rbx; Sid
0x180039626  call    cs:__imp_RtlLengthSid
0x18003962c  mov     edi, eax
0x18003962e  lea     r8, [r13+8]
0x180039632  add     r8, rbx; SourceSid
0x180039635  mov     rdx, r14; DestinationSid
0x180039638  mov     ecx, eax; DestinationSidLength
0x18003963a  call    cs:__imp_RtlCopySid
0x180039640  mov     rcx, [r15+8]
0x180039644  mov     [rcx+rsi*8], r14
0x180039648  add     r14, rdi
0x18003964b  inc     r12d
0x18003964e  cmp     r12d, [r13+0]
0x180039652  jb      short loc_180039611
0x180039654  mov     r12d, [rbp+arg_18]
0x180039658  mov     rsi, [rbp+arg_10]
0x18003965c  mov     eax, r12d
0x18003965f  add     rax, r15
0x180039662  cmp     r14, rax
0x180039665  jz      short loc_18003966C
0x180039667  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003966c  mov     [rbp+var_18], 0
0x180039674  mov     rax, [rbp+arg_8]
0x180039678  mov     [rax], r15
0x18003967b  mov     [rsi], r12d
0x18003967e  lea     rcx, [rbp+var_18]
0x180039682  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@$$A6AXPEAX@Z$1?Pku2uFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(void)
0x180039687  xor     ebx, ebx
0x180039689  lea     rcx, [rbp+var_8]
0x18003968d  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@$$A6AXPEAX@Z$1?Pku2uFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(void)
0x180039692  nop
0x180039693  lea     rcx, [rbp+var_10]
0x180039697  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@$$A6AXPEAX@Z$1?Pku2uFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(void)
0x18003969c  mov     eax, ebx
0x18003969e  mov     rbx, [rsp+40h+arg_0]
0x1800396a6  add     rsp, 40h
0x1800396aa  pop     r15
0x1800396ac  pop     r14
0x1800396ae  pop     r13
0x1800396b0  pop     r12
0x1800396b2  pop     rdi
0x1800396b3  pop     rsi
0x1800396b4  pop     rbp
0x1800396b5  retn
```
