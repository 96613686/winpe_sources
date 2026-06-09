# NlpGetPrimaryCredentialByUserSid

- ea: `0x180040274`
- end: `0x180040330`
- name: `NlpGetPrimaryCredentialByUserSid`
- size: `188`
- prototype: `__int64 __fastcall(PSID Sid1)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001a470`

## callees

- `0x18000df40`
- `0x18000ed70`
- `0x180040274`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800402cb`
- `ntdll!RtlEqualSid` at `0x1800402cb`
- `ntdll!RtlReleaseResource` at `0x1800402ed`
- `ntdll!RtlReleaseResource` at `0x1800402ed`
- `ntdll!RtlAcquireResourceShared` at `0x1800402ab`
- `ntdll!RtlAcquireResourceShared` at `0x1800402ab`

## string_xrefs

- `0x180040314`: `NlpGetPrimaryCredentialByUserSid`

## pseudocode

```c
__int64 __fastcall NlpGetPrimaryCredentialByUserSid(PSID Sid1, __int64 a2)
{
  char v5; // di
  __int64 i; // rbx
  unsigned int PrimaryCredential; // ebx
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF

  v8 = 0;
  if ( !Sid1 )
    return 3221225485LL;
  v5 = 0;
  RtlAcquireResourceShared(&NlpActiveLogonLock, 1u);
  for ( i = NlpActiveLogonListAnchor; (__int64 *)i != &NlpActiveLogonListAnchor; i = *(_QWORD *)i )
  {
    if ( RtlEqualSid(Sid1, *(PSID *)(i + 64)) )
    {
      v5 = 1;
      v8 = *(_QWORD *)(i + 44);
      break;
    }
  }
  RtlReleaseResource(&NlpActiveLogonLock);
  if ( v5 )
    PrimaryCredential = NlpGetPrimaryCredential(&v8, a2, 0);
  else
    PrimaryCredential = -1073741729;
  NtlmTraceStatusViaWpp_0("NlpGetPrimaryCredentialByUserSid", 2280, PrimaryCredential);
  return PrimaryCredential;
}

```

## disassembly

```asm
0x180040274  mov     [rsp+arg_10], r8
0x180040279  push    rbx
0x18004027a  push    rbp
0x18004027b  push    rsi
0x18004027c  push    rdi
0x18004027d  sub     rsp, 28h
0x180040281  mov     [rsp+48h+arg_10], 0
0x18004028a  mov     rbp, rdx
0x18004028d  mov     rsi, rcx
0x180040290  test    rcx, rcx
0x180040293  jnz     short loc_18004029F
0x180040295  mov     eax, 0C000000Dh
0x18004029a  jmp     loc_180040327
0x18004029f  xor     dil, dil
0x1800402a2  lea     rcx, NlpActiveLogonLock; Resource
0x1800402a9  mov     dl, 1; Wait
0x1800402ab  call    cs:__imp_RtlAcquireResourceShared
0x1800402b1  mov     rbx, cs:NlpActiveLogonListAnchor
0x1800402b8  lea     rax, NlpActiveLogonListAnchor
0x1800402bf  cmp     rbx, rax
0x1800402c2  jz      short loc_1800402E6
0x1800402c4  mov     rdx, [rbx+40h]; Sid2
0x1800402c8  mov     rcx, rsi; Sid1
0x1800402cb  call    cs:__imp_RtlEqualSid
0x1800402d1  test    al, al
0x1800402d3  jnz     short loc_1800402DA
0x1800402d5  mov     rbx, [rbx]
0x1800402d8  jmp     short loc_1800402B8
0x1800402da  mov     rax, [rbx+2Ch]
0x1800402de  mov     dil, 1
0x1800402e1  mov     [rsp+48h+arg_10], rax
0x1800402e6  lea     rcx, NlpActiveLogonLock; Resource
0x1800402ed  call    cs:__imp_RtlReleaseResource
0x1800402f3  test    dil, dil
0x1800402f6  jnz     short loc_1800402FF
0x1800402f8  mov     ebx, 0C000005Fh
0x1800402fd  jmp     short loc_180040311
0x1800402ff  xor     r8d, r8d
0x180040302  lea     rcx, [rsp+48h+arg_10]
0x180040307  mov     rdx, rbp
0x18004030a  call    NlpGetPrimaryCredential
0x18004030f  mov     ebx, eax
0x180040311  mov     r8d, ebx
0x180040314  lea     rcx, aNlpgetprimaryc_0; "NlpGetPrimaryCredentialByUserSid"
0x18004031b  mov     edx, 8E8h
0x180040320  call    NtlmTraceStatusViaWpp_0
0x180040325  mov     eax, ebx
0x180040327  add     rsp, 28h
0x18004032b  pop     rdi
0x18004032c  pop     rsi
0x18004032d  pop     rbp
0x18004032e  pop     rbx
0x18004032f  retn
```
